---
title: 在 Linux 或 Windows Nano Server 主机上部署基于单容器的 .NET Core Web 应用
description: 适用于容器化 .NET 应用程序的体系结构 | 在 Linux 或 Windows Nano Server 主机上部署基于单容器的 .NET Core Web 应用
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/27/2018
ms.openlocfilehash: 45be99a86a52ed450b795ca5f91c01ab82c7da47
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197350"
---
# <a name="deploying-single-container-based-net-core-web-applications-on-linux-or-windows-nano-server-hosts"></a>在 Linux 或 Windows Nano Server 主机上部署基于单容器的 .NET Core Web 应用

_对于简单 Web 应用的整体部署，可以使用 Docker 容器。这样可以改进持续集成和持续部署管道，并有助于成功实现部署到生产环境。不再出现“为什么可以在我的计算机上正常运行，却不能在生产环境中正常运行？”的问题_

基于微服务的体系结构具有许多优势，但以增加复杂性为代价。 在某些情况下，成本超过了收益，在单个或几个容器中运行的单片式部署应用程序更为实用。

单片式应用程序可能不易分解到独立性良好的微服务。 你已经了解到，应按功能对微服务进行分区：它们应彼此独立运行，以提供复原能力更强的应用程序。 如果无法实现应用程序功能切片，将其分离只会增加复杂性。

应用程序可能尚不需要独立地扩展功能。 假设在 `eShopOnContainers` 参考应用程序的早期阶段，流量并未将分离的功能分配到不同的微服务。 流量足够小，为一项服务添加资源通常意味着为所有服务添加资源。 将应用程序分离到成离散的服务是画蛇添足，提供的优势极小。

此外，在应用程序开发前期，可能并不确定自然功能边界。 开发最小可独立产品时，自然分离可能尚未出现。

其中一些条件可能是临时的。 可首先创建单片式应用程序，稍后再分离要以微服务的形式开发和部署的某些功能。 而另一些条件可能对应用程序的容错空间至关重要，这意味着应用程序可能永远无法分解到多个微服务。

将应用程序分离到多个离散进程还会带来开销。 将功能分离到不同的进程则更复杂。 通信协议会变得更加复杂。 在服务之间必须使用异步通信，而不得使用方法调用。 移动到微服务体系结构时，需要添加在 `eShopOnContainers` 应用程序的微服务版本中实现的许多构建基块：事件总线处理、消息复原和重试、最终一致性等。

极简版的 eShopOnContainers（名为 [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) 并包含在同一 GitHub 存储库中）作为单片式 MVC 应用程序运行。 如上所述，选择这种设计带来了各种优势。 可从 GitHub 下载此应用程序的源代码，并在本地运行。 即使是这一单片式应用程序，在容器环境中部署也是有益的。

其一，容器化部署意味着应用程序的每个实例都在同一环境中运行。 这包括用于前期测试和开发的开发人员环境。 开发团队可在与生产环境完全相同的容器化环境中运行应用程序。

此外，容器化应用程序扩大成本较低。 如上文所示，容器环境比传统 VM 环境更有利于资源共享。

最后，容器化应用程序会强制分离业务逻辑和存储服务器。 应用程序扩大时，各种容器将全部依赖于单个物理存储介质。 此存储通常是运行 SQL Server 数据库的高可用性服务器。

## <a name="application-tour"></a>应用程序教程

[eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) 应用程序代表着某些作为单片式应用程序运行的 eShopOnContainers 应用程序，即在 .NET Core 上运行的基于 ASP.NET Core MVC 的应用程序。 它主要提供前几节所述的目录浏览功能。

该应用程序使用 SQL Server 数据库实现目录存储。 在基于容器的部署中，此单片式应用程序与基于微服务的应用程序可访问相同的数据存储。 该应用程序配置为在与单片式应用程序并列的容器中运行 SQL Server。 在生产环境中，SQL Server 会在 Docker 主机以外的高可用性计算机上运行。 为方便起见，在开发或测试环境中，建议在自己的容器中运行 SQL Server。

初始功能集仅提供浏览目录的功能。 通过更新实现容器化应用程序的完整功能集。 在 [ASP.NET Web 应用体系结构实践](https://aka.ms/webappebook)电子书和相关 [eShopOnWeb 示例应用程序](https://aka.ms/WebAppArchitecture)中介绍了更高级的单片式 Web 应用体系结构。

## <a name="docker-support"></a>Docker 支持

eShopOnWeb 项目在 .NET Core 上运行。 这意味着该项目可在基于 Linux 或基于 Windows 的容器中运行。 请注意，在 Docker 部署中，请对 SQL Server 使用相同的主机类型。 基于 Linux 的容器占用较小，是首选方案。

Visual Studio 提供了项目模板，可在解决方案中添加对 Docker 的支持。 右键单击该项目，单击“Docker 支持”前的“添加”。 该模板会在项目中添加 Dockerfile 以及一个可提供初始 docker-compose.yml 文件的新 docker-compose 项目。 从 GitHub 下载的 eShopOnWeb 项目中已完成此步骤。 可看到该解决方案包含 eShopOnWeb 项目和 docker-compose 项目，如图 6-1 所示。

![](./media/image1.png)

**图 6-1**. 单容器 Web 应用中的 **docker-compose** 项目

这些文件是标准 docker-compose 文件，与任何 Docker 项目一致。 可通过 Visual Studio 或命令行使用这些文件。 此应用程序在 .NET Core 上运行并使用 Linux 容器。 因此，还可在 Mac 或 Linux 计算机上对其进行编码、生成和运行。

docker-compose.yml 文件包含有关要生成的映像和要启动的容器的信息。 模板指定如何生成 `eshopweb` 映像并启动应用程序的容器。 需要通过包含 SQL Server 的映像（例如 `mssql-server-linux`）添加对 SQL Server 的依赖项，并添加针对 sql.data 映像的服务，用于 Docker 生成并启动该容器。 这些设置如下例所示：

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web
    build:
    context: ./eShopWeb
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  sql.data:
    image: microsoft/mssql-server-linux
```

`depends_on` 指令会告知 Docker：eShopWeb 映像依赖于 sql.data 映像。 `depends_on` 下面的行是使用 `microsoft/mssql-server-linux` 映像来生成标记为 `sql.data` 的映像的指令。

docker-compose 项目会在 docker-compose.yml 主节点下显示其他 docker-compose 文件，从视觉上指示这些文件相关联。 docker-compose-override.yml 文件包含适用于这两个服务的设置，如连接字符串和其他应用程序设置。

下面的示例演示 docker-compose.vs.debug.yml 文件，其中包含用于在 Visual Studio 中进行调试的设置。 在该文件中，eshopweb 映像中附加了 dev 标记。 这有助于分离调试与发布映像，避免意外将调试信息部署到生产环境：

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web:dev
    build:
    args:
    source: ${DOCKER_BUILD_SOURCE}
    environment:
      - DOTNET_USE_POLLING_FILE_WATCHER=1
    volumes:
      - ./eShopWeb:/app
      - ~/.nuget/packages:/root/.nuget/packages:ro
      - ~/clrdbg:/clrdbg:ro
    entrypoint: tail -f /dev/null
    labels:
      - "com.microsoft.visualstudio.targetoperatingsystem=linux"
```

添加的最后一个文件是 docker-compose.ci.build.yml。 在命令行中使用该文件，以便从 CI 服务器生成项目。 此组成文件会启动一个 Docker 容器，该容器将生成应用程序所需的映像。 下面的示例演示了 docker-compose.ci.build.yml 文件的内容：

```yml
version: '2'

services:
  ci-build:
    image: microsoft/aspnetcore-build:latest
    volumes:
      - .:/src
    working_dir: /src
  command: /bin/bash -c "dotnet restore ./eShopWeb.sln && dotnet publish  ./eShopWeb.sln -c Release -o ./obj/Docker/publish"
```

> [!NOTE]
> 从 .NET Core SDK 2.0 开始，执行 [dotnet publish](../../../core/tools/dotnet-publish.md) 时，[dotnet restore](../../../core/tools/dotnet-restore.md) 命令将自动执行。

请注意，该映像是 ASP.NET Core 生成映像。 该映像包括用于生成应用程序并创建所需映像的 SDK 和生成工具。 使用此文件运行 **docker-compose** 项目，会从映像启动生成容器，然后在该容器中生成应用程序的映像。 在将 docker-compose 文件指定为命令行的一部分以在 Docker 容器中生成应用程序，然后启动。

在 Visual Studio 中，可以在 Docker 容器中运行应用程序，具体方法是选择 **docker-compose** 项目作为启动项目，然后按 Ctrl+F5（F5 用于调试），像在其他任何应用程序中操作一样。 启动 docker-compose 项目时，Visual Studio 会使用 docker-compose.yml 文件、docker-compose.override.yml 文件，以及某个 docker-compose.vs.\* 文件来运行 docker-compose。 启动应用程序后，Visual Studio 将启动浏览器。

如果在调试程序中启动应用程序，Visual Studio 会附加到 Docker 中正在运行的应用程序。

## <a name="troubleshooting"></a>疑难解答

本节介绍本地运行容器时可能出现的一些问题，并提出了一些修复建议。

### <a name="stop-docker-containers"></a>停止 Docker 容器

启动容器化应用程序后，即使你停止调试，容器仍会继续运行。 可从命令行运行 `docker ps` 命令，查看运行中的容器。 `docker stop` 命令可停止正在运行的容器，如图 6-2 所示。

![](./media/image2.png)

**图 6-2**. 使用 docker ps 和 docker stop CLI 命令列出和停止容器

在不同的配置间切换时，可能需要停止正在运行的进程。 否则，运行 Web 应用的容器会使用应用程序的端口（此例中为 5106）。

### <a name="add-docker-to-your-projects"></a>将 Docker 添加到项目

添加 Docker 支持的向导会与正在运行的 Docker 进程通信。 如果启动向导时 Docker 未处于运行状态，则向导无法正常运行。 向导会检查当前的容器选择以添加正确的 Docker 支持。 若要添加对 Windows 容器的支持，请在配置了 Windows 容器的 Docker 运行的同时运行向导。 若要添加对 Linux 容器的支持，请在配置了 Linux 容器的 Docker 运行的同时运行向导。

>[!div class="step-by-step"]
[上一页](../docker-application-development-process/docker-app-development-workflow.md)
[下一页](../containerize-net-framework-applications/index.md)

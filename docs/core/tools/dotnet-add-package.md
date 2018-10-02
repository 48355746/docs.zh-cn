---
title: dotnet add package 命令 - .NET Core CLI
description: “dotnet add package”命令可便于添加对项目的 NuGet 包引用。
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 31dda9dbb101238b3a33d8b0d9a17765744480e0
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244388"
---
# <a name="dotnet-add-package"></a>dotnet add package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet add package` - 向项目文件添加包引用。

## <a name="synopsis"></a>摘要

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a>描述

使用 `dotnet add package` 命令可方便地向项目文件添加包引用。 运行该命令后，还有一个兼容性检查，确保包与项目中的框架兼容。 如果通过了该检查，则将 `<PackageReference>` 元素添加到项目文件并运行 [dotnet 还原](dotnet-restore.md)。

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

例如，将 `Newtonsoft.Json` 添加到 ToDo.csproj 后的输出如以下示例所示：

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\projects\ToDo\ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 235ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '10.0.3' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

*ToDo.csproj* 文件现包含用于引用的包的 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 元素。

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a>参数

`PROJECT`

指定项目文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。

`PACKAGE_NAME`

要添加的包引用。

## <a name="options"></a>选项

`-h|--help`

打印出有关命令的简短帮助。

`-f|--framework <FRAMEWORK>`

仅在以特定[框架](../../standard/frameworks.md)为目标时添加包引用。

`-n|--no-restore`

在不执行还原预览和兼容性检查的情况下添加包引用。

`--package-directory <PACKAGE_DIRECTORY>`

将包还原到指定的目录。

`-s|--source <SOURCE>`

使用还原操作期间的特定 NuGet 包源。

`-v|--version <VERSION>`

包的版本。

## <a name="examples"></a>示例

将 `Newtonsoft.Json` NuGet 包添加到项目：

`dotnet add package Newtonsoft.Json`

向项目添加特定版本的包：

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

使用特定的 NuGet 源添加包：

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`

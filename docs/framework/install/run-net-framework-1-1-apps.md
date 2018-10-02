---
title: 在 Windows 8、Windows 8.1 或 Windows 10 上运行 .NET Framework 1.1 应用
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3a7331d4488f4a0eeac71b0b866bc4b6864eed6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43469929"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>在 Windows 8、Windows 8.1 或 Windows 10 上运行 .NET Framework 1.1 应用

[!INCLUDE[win8](../../../includes/win8-md.md)]、[!INCLUDE[win81](../../../includes/win81-md.md)]、[!INCLUDE[winserver8](../../../includes/winserver8-md.md)]、[!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] 或 Windows 10 操作系统上不支持 .NET Framework 1.1。 在某些情况下，.NET Framework 1.1 专门标识为是运行应用所必需的。 在这些情况下，应联系独立软件供应商 (ISV) 以升级该应用，使其可在 [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] 或更高版本上运行。 有关其他信息，请参阅[从 .NET Framework 1.1 迁移](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)。

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a>从 CD 或下载中心安装 .NET Framework 1.1

在 [!INCLUDE[win8](../../../includes/win8-md.md)]、[!INCLUDE[win81](../../../includes/win81-md.md)]、[!INCLUDE[winserver8](../../../includes/winserver8-md.md)]、[!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] 或 Windows 10 上无法手动安装 .NET Framework 1.1。 它不再受支持。 如果尝试安装此包，将显示以下错误消息：“安装程序无法继续，因为该版本的 .NET Framework 与之前安装的版本不兼容”。 若要解决此问题，请安装 [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22)。 此版本包括 .NET Framework 2.0（.NET Framework 1.1 之后的版本），[!INCLUDE[win8](../../../includes/win8-md.md)]、[!INCLUDE[win81](../../../includes/win81-md.md)] 和 Windows 10 上支持 .NET Framework 2.0。 首先，应始终尝试安装该应用，确定其是否会自动更新到 .NET Framework 的更高版本。 如果不会，请联系 ISV 获取应用更新。

## <a name="see-also"></a>请参阅

[从 .NET Framework 1.1 迁移](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5](../../../docs/framework/install/dotnet-35-windows-10.md)

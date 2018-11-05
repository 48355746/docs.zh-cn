---
title: 适用于 Windows 应用商店应用的 .NET 的 MEF
ms.date: 03/30/2017
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39b7228de775f4dc92e932731ad9967315437e6e
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49121111"
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="55a1d-102">适用于 Windows 应用商店应用的 .NET 的 MEF</span><span class="sxs-lookup"><span data-stu-id="55a1d-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="55a1d-103"><xref:System.Composition?displayProperty=nameWithType> 及其子命名空间包含用于使用 Managed Extensibility Framework (MEF) 开发可扩展的 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用的类型。</span><span class="sxs-lookup"><span data-stu-id="55a1d-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="55a1d-104">这些名称空间是 [!INCLUDE[win8](../../../includes/win8-md.md)] 操作系统的 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 子集的一部分。</span><span class="sxs-lookup"><span data-stu-id="55a1d-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="55a1d-105">这些命名空间不是与 .NET Framework 一起分发的核心类库的一部分。</span><span class="sxs-lookup"><span data-stu-id="55a1d-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="55a1d-106">若要安装这些命名空间，请在 Visual Studio 中打开项目，从“项目”菜单中选择“管理 NuGet 包”，然后联机搜索 Microsoft.Composition 包。</span><span class="sxs-lookup"><span data-stu-id="55a1d-106">To install these namespaces, open your project in Visual Studio, choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
-   <span data-ttu-id="55a1d-107"><xref:System.Composition?displayProperty=nameWithType> 提供构成 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用的核心 MEF 的类。</span><span class="sxs-lookup"><span data-stu-id="55a1d-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
-   <span data-ttu-id="55a1d-108"><xref:System.Composition.Convention?displayProperty=nameWithType> 提供支持使用具有基于约定的配置模型的 MEF 的类型。</span><span class="sxs-lookup"><span data-stu-id="55a1d-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
-   <span data-ttu-id="55a1d-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> 提供对主机应用程序开发人员有用的 MEF 类型。</span><span class="sxs-lookup"><span data-stu-id="55a1d-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
-   <span data-ttu-id="55a1d-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> 提供由组合引擎内部使用的 MEF 类型。</span><span class="sxs-lookup"><span data-stu-id="55a1d-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="55a1d-111">有关 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 及其包含的命名空间和类型列表的详细信息，请参阅 Windows 开发人员中心的[适用于 Windows 应用商店应用的 .NET 概述](https://go.microsoft.com/fwlink/p/?LinkID=238312)。</span><span class="sxs-lookup"><span data-stu-id="55a1d-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](https://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a1d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="55a1d-112">See Also</span></span>  
 [<span data-ttu-id="55a1d-113">适用于 Microsoft Store 应用的 .NET 概述</span><span class="sxs-lookup"><span data-stu-id="55a1d-113">.NET for Windows Store apps overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=238312)  
 [<span data-ttu-id="55a1d-114">适用于 Windows 应用商店应用的 .NET - 支持的 API</span><span class="sxs-lookup"><span data-stu-id="55a1d-114">.NET for Windows Store apps – supported APIs</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=247912)  
 [<span data-ttu-id="55a1d-115">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="55a1d-115">Managed Extensibility Framework (MEF)</span></span>](../../../docs/framework/mef/index.md)

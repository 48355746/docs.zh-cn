---
title: 程序集和 DLL 的名称
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97bd152cff53fb1c2edb107b6d6b34bd91ca1c49
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "45972054"
---
# <a name="names-of-assemblies-and-dlls"></a>程序集和 DLL 的名称
程序集是托管代码程序的部署和标识单元。 虽然程序集可以跨一个或多个文件，但通常程序集与 DLL 是一对一映射的。 因此，本部分仅描述 DLL 命名约定，然后可以将其映射到程序集命名约定。  
  
 **✓ 要** 为程序集 DLL 选择能够使人联想到大量功能的名称，例如 System.Data。  
  
 程序集和 DLL 名称不必与命名空间名称相对应，但在命名程序集时应采用命名空间名称。 通常是根据程序集中包含的命名空间的公共前缀来命名 DLL。 例如，如果程序集的两个命名空间为 `MyCompany.MyTechnology.FirstFeature` 和 `MyCompany.MyTechnology.SecondFeature`，则可将其命名为 `MyCompany.MyTechnology.dll`。  
  
 **✓ 考虑**按照下面的模式命名 Dll：  
  
 `<Company>.<Component>.dll`  
  
 其中`<Component>`包含一个或多个以点号分隔的子句。 例如：  
  
 `Litware.Controls.dll`。  
  
 部分 © 2005，2009 Microsoft Corporation。*保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)

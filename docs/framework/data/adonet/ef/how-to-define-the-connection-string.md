---
title: 如何：定义连接字符串
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: f40b8bc68eda1cb4b64b34d12b2922da69929203
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210153"
---
# <a name="how-to-define-the-connection-string"></a>如何：定义连接字符串
本主题介绍如何定义在连接到概念模型时使用的连接字符串。 本主题基于[AdventureWorks 销售](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)概念模型。 AdventureWorks 销售模型将在 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 文档的与任务相关的所有主题中使用。 本主题假定你已配置[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]和定义 AdventureWorks 销售模型。 有关详细信息，请参阅[如何： 手动定义模型和映射文件](https://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a)。 本主题中的过程也包括在[如何： 手动配置实体框架项目](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)。  
  
> [!NOTE]
>  如果您使用[!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]向导在 Visual Studio 项目中，会自动生成.edmx 文件和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。 有关详细信息，请参阅[如何： 使用实体数据模型向导](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>定义实体框架连接字符串  
  
-   打开项目的应用程序配置文件 (app.config) 并添加以下连接字符串：  
  
  
  
     如果你的项目不具有应用程序配置文件，则可以添加一个通过选择**添加新项**从**项目**菜单中，选择**常规**类别中，选择**应用程序配置文件**，然后单击**添加**。  
  
## <a name="see-also"></a>请参阅  
 [快速入门](https://msdn.microsoft.com/library/0bc534be-789f-4819-b9f6-76e51d961675)  
 [如何： 创建新的.edmx 文件](https://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2)  
 [ADO.NET 实体数据模型工具](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)

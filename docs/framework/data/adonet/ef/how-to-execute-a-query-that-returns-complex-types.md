---
title: 如何：执行返回复杂类型的查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 013f1980d2ea13927871719aeea293cfce38b4d5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861889"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>如何：执行返回复杂类型的查询
本主题演示如何执行返回包含复杂类型属性的实体类型对象的 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 查询。  
  
### <a name="to-run-the-code-in-this-example"></a>运行本示例中的代码  
  
1.  添加[AdventureWorks 销售模型](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)到你的项目和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。 有关详细信息，请参阅[如何： 使用实体数据模型向导](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)。  
  
2.  在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  双击要显示在模型的.edmx 文件[模型浏览器窗口](https://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd)在实体设计器。 在实体设计器图面中，选择`Email`并`Phone`的属性`Contact`实体类型，然后右键单击并选择**重构为新的复杂类型**。  
  
4.  新的复杂类型与所选`Email`并`Phone`属性添加到**模型浏览器**。 复杂类型具有默认名称： 重命名类型为`EmailPhone`中**属性**窗口。 此外，新的 `ComplexProperty` 属性将添加到 `Contact` 实体类型。 将该属性重命名为 `EmailPhoneComplexType.`。  
  
     有关创建和修改复杂类型的使用实体数据模型向导的信息，请参阅[如何： 将现有属性重构为复杂类型属性](https://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb)和[如何： 创建和修改复杂类型](https://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## <a name="example"></a>示例  
 下面的示例执行返回的集合的查询`Contact`对象，并显示的两个属性`Contact`对象：`ContactID`的值和`EmailPhoneComplexType`复杂类型。  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]

---
title: 如何：使用 XPath 查询 LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: 3d4a75e4688725f2444d3bbc4d55bec828485a5d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511186"
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a>如何：使用 XPath 查询 LINQ to XML (C#)
本主题介绍一些扩展方法，通过这些扩展方法可以使用 XPath 查询 XML 树。 有关使用这些扩展方法的详细信息，请参见 <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>。  
  
 除非有很特别的理由（例如大量使用旧代码）需要使用 XPath 进行查询，否则不建议将 XPath 用于 LINQ to XML。 XPath 查询的执行性能比 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询低。  
  
## <a name="example"></a>示例  
 下面的示例创建一个小型 XML 树，并使用 <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> 选择一组元素。  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 该示例产生下面的输出：  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a>请参阅

- [高级查询技术 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)

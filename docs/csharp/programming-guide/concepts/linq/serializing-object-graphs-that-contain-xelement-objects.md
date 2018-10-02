---
title: 序列化包含 XElement 对象的对象图 (C#)
ms.date: 07/20/2015
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
ms.openlocfilehash: 2e82165421d31ec234de4806b59565fa675217ef
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698138"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a>序列化包含 XElement 对象的对象图 (C#)
本主题介绍序列化对象图的功能，其中对象图包含对类型为 <xref:System.Xml.Linq.XElement> 的对象的引用。 为便于执行这种类型的序列化，<xref:System.Xml.Linq.XElement> 实现了 <xref:System.Xml.Serialization.IXmlSerializable> 接口。  
  
 请注意，只有 <xref:System.Xml.Linq.XElement> 类才实现序列化。  
  
## <a name="in-this-section"></a>本节内容  
  
|主题|描述|  
|-----------|-----------------|  
|[如何：使用 XmlSerializer 进行序列化 (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|演示如何使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化。|  
|[如何：使用 DataContractSerializer 进行序列化 (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|演示如何使用 <xref:System.Runtime.Serialization.DataContractSerializer> 进行序列化。|  
  
## <a name="see-also"></a>请参阅

- [高级 LINQ to XML 编程 (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

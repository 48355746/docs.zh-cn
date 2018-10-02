---
title: XML 数据类型的转换
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cec2b85c55871c8a21a74e79cfcdd041fa063bec
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45664574"
---
# <a name="conversion-of-xml-data-types"></a>XML 数据类型的转换
XmlConvert 类中的大多数方法用于在字符串和强类型格式之间转换数据。 这些方法与区域设置无关。 这意味着它们在执行转换时不考虑任何区域设置。  
  
## <a name="reading-string-as-types"></a>将字符串作为类型读取  
 下面的示例读取字符串，并将它转换为 DateTime 类型。  
  
 给定以下 XML 输入：  
  
 **输入**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 下面的代码将字符串转换为 DateTime 格式：  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a>将字符串作为类型写入  
 下面的示例读取 Int32，并将它转换为字符串。  
  
 给定以下 XML 输入：  
  
 **输入**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 下面的代码将 Int32 转换为 String：  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>请参阅

- [将字符串转换为 .NET Framework 数据类型](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
- [将 .NET Framework 类型转换为字符串](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)

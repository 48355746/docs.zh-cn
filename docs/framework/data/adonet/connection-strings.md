---
title: 在 ADO.NET 中的连接字符串
ms.date: 03/30/2017
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 1e6e2b6870195c99279639e1f4576a30b7126d4d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583680"
---
# <a name="connection-strings-in-adonet"></a>在 ADO.NET 中的连接字符串
.NET Framework 2.0 引入了用于处理连接字符串的新功能（包括将新的关键字引入到连接字符串生成器类），这将有助于在运行时创建有效的连接字符串。  
  
连接字符串包含作为参数从数据提供程序传递到数据源的初始化信息。 其语法取决于数据提供程序，并且会在试图打开连接的过程中对连接字符串进行分析。 语法错误会生成运行时异常，但其他错误只有在数据源收到连接信息后才会发生。 经过验证后，数据源将应用连接字符串中指定的选项并打开连接。
  
连接字符串的格式是使用分号分隔的键/值参数对列表：
  
    keyword1=value; keyword2=value;
  
关键字不区分大小写。 但是，值可能区分大小写，具体取决于数据源。 关键字和值可能包含[空白字符](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)，尽管在关键字中忽略和不带引号的前导和尾随空格的值。

如果值包含分号[Unicode 控制字符](https://en.wikipedia.org/wiki/Unicode_control_characters)、 前导空格或尾随的空格，则必须用单引号或双引号括起来，例如：

    Keyword=" whitespace  ";
    Keyword='special;character';

它包含的值中可能不是封闭字符。 因此，仅在两个双引号，反之亦然，则可以包含一个值，包含单引号引起来：

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

引号本身，以及等号，不需要转义，因此以下连接字符串有效：

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

由于直到下一步分号或字符串的末尾读取每个值，后者的示例中的值是`a=b=c`，并最终分号是可选的。

有效的连接字符串语法因提供程序而异，从早期的 API（如 ODBC）开始，已经过了多年的发展演变。 适用于 SQL Server 的 .NET Framework 数据提供程序 (SqlClient) 并入了早期语法中的许多元素，并且在使用通常的连接字符串语法时更具灵活性。 连接字符串语法元素经常会出现一些同等有效的同义词，但有些语法和拼写错误可能会导致出现问题。 例如，“`Integrated Security=true`”是有效的，而“`IntegratedSecurity=true`”则会导致出错。 另外，在运行时从未验证的用户输入构造的连接字符串可能导致字符串注入式攻击，从而危害数据源的安全。
  
为了解决这些问题，ADO.NET 2.0 为每个 .NET Framework 数据提供程序引入了新的连接字符串生成器。 关键字作为属性公开，以便在将连接字符串提交到数据源之前，能够对连接字符串语法进行验证。
  
## <a name="in-this-section"></a>本节内容  
 [连接字符串生成器](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 演示如何使用 `ConnectionStringBuilder` 类在运行时构造有效的连接字符串。
  
 [连接字符串和配置文件](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 演示如何在配置文件中存储和检索连接字符串。
  
 [连接字符串语法](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 描述如何为 `SqlClient`、`OracleClient`、`OleDb` 和 `Odbc` 配置提供程序专用的连接字符串。
  
 [保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 演示保护用于连接到数据源的信息的各项技术。
  
## <a name="see-also"></a>请参阅  
 [连接到数据源](/cpp/data/odbc/connecting-to-a-data-source)  
 [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)

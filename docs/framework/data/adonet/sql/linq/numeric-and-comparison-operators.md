---
title: 数值和比较运算符
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: a7a455730860e2b11a5ceff5a70934502b312e19
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515061"
---
# <a name="numeric-and-comparison-operators"></a>数值和比较运算符
算术运算符和比较运算符在公共语言运行库 (CLR) 中按预期方式工作，但有以下几点例外：  
  
-   SQL 不支持对浮点数字使用取模运算符。  
  
-   SQL 不支持未校验的算法。  
  
-   在无法复制到 SQL 中的表达式中使用增量和减量运算符时会产生副作用，因而不支持此类运算符。  
  
## <a name="supported-operators"></a>支持的运算符  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 支持以下运算符。  
  
-   基本算术运算符：  
  
    -   `+`  
  
    -   `-`（减号）  
  
    -   `*`  
  
    -   `/`  
  
    -   Visual Basic 整除 (`\`)  
  
    -   `%` (Visual Basic `Mod`)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-`（一元求反）  
  
-   基本比较运算符：  
  
    -   Visual Basic `=` 和 C# `==`  
  
    -   Visual Basic `<>` 和 C# `!=`  
  
    -   Visual Basic `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a>请参阅  
 [数据类型和函数](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [C# 运算符](https://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [运算符](../../../../../visual-basic/language-reference/operators/index.md)

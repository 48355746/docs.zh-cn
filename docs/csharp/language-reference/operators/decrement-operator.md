---
title: -- 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 615b100447233856ab3740d075d69e3ae19285fd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45648777"
---
# <a name="---operator-c-reference"></a>-- 运算符（C# 参考）
减量运算符 (`--`) 按 1 递减其操作数。 减量运算符可以在其操作数之前或之后出现：`--variable` 和 `variable--`。 第一种形式是前缀递减操作。 操作的结果是操作数递减“后”的值。 第二种形式是后缀递减操作。 操作的结果是操作数递减“前”的值。  
  
## <a name="remarks"></a>备注  
 数值和枚举类型具有预定义的减量运算符。  
  
 用户定义的类型可以重载 `--` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 对整数类型的操作通常可用于枚举。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)

---
title: static（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: db12ef80752bba913e6792ccb38f598a664efb0b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508280"
---
# <a name="static-c-reference"></a>static（C# 参考）
使用 `static` 修饰符可声明属于类型本身而不是属于特定对象的静态成员。 `static` 修饰符可用于类、字段、方法、属性、运算符、事件和构造函数，但不能用于索引器、终结器或类以外的类型。 有关详细信息，请参阅[静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。  
  
## <a name="example"></a>示例  
 下面的类声明为 `static` 并且只含 `static` 方法：  
  
 [!code-csharp[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 常量或类型声明是隐式的静态成员。  
  
 不能通过实例引用静态成员。 然而，可以通过类型名称引用它。 例如，请考虑以下类：  
  
 [!code-csharp[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 若要引用静态成员 `x`，除非可从相同范围访问该成员，否则请使用完全限定的名称 `MyBaseC.MyStruct.x`：  
  
```csharp  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 尽管类的实例包含该类的所有实例字段的单独副本，但每个静态字段只有一个副本。  
  
 不可以使用 [this](../../../csharp/language-reference/keywords/this.md) 引用静态方法或属性访问器。  
  
 如果 `static` 关键字应用于类，则类的所有成员都必须是静态的。  
  
 类和静态类可以包含静态构造函数。 在程序开始和实例化类之间的某个时刻调用静态构造函数。  
  
> [!NOTE]
>  `static` 关键字比用于 C++ 中时受到的限制更多。 若要与 C++ 关键字进行比较，请参阅 [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static)（存储类 (C++)）。
  
 若要演示静态成员，请考虑表示公司员工的类。 假定此类包含计数员工的方法和存储员工人数的字段。 方法和字段均不属于任何实例员工。 而属于公司类。 因此，它们应声明为类的静态成员。  
  
## <a name="example"></a>示例  
 此示例读取新员工的姓名和 ID，员工计数器按 1 递增，并显示新员工信息和新员工人数。 为简单起见，此程序从键盘读取员工的当前人数。 在实际应用程序中，应从文件读取该信息。  
  
 [!code-csharp[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## <a name="example"></a>示例  
 此示例显示，尽管可以使用尚未声明的其他静态字段来初始化某个静态字段，但除非向该静态字段显式分配值，否则不会定义该结果。  
  
 [!code-csharp[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
- [修饰符](../../../csharp/language-reference/keywords/modifiers.md)  
- [静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

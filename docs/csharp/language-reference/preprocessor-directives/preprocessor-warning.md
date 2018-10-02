---
title: '#warning（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 59ca63d5089e377627a9116f24f9a0a1681bb4b2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506342"
---
# <a name="warning-c-reference"></a>#warning（C# 参考）
`#warning` 允许你从代码中的特定位置生成 [ CS1030](../../misc/cs1030.md) 第一级编译器警告。 例如:  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a>备注
 `#warning` 常用于条件指令中。 还可使用 [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) 生成用户定义错误。  
  
## <a name="example"></a>示例  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md)

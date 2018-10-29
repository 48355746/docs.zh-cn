---
title: ++ 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: a52f614ce1bbfb8e9d9be686b277c1e69f6f9d35
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48030458"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d57b2-102">++ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d57b2-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="d57b2-103">递增运算符 (`++`) 按 1 递增其操作数。</span><span class="sxs-lookup"><span data-stu-id="d57b2-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="d57b2-104">递增运算符可以在其操作数之前或之后出现： `++variable` 和 `variable++`。</span><span class="sxs-lookup"><span data-stu-id="d57b2-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d57b2-105">备注</span><span class="sxs-lookup"><span data-stu-id="d57b2-105">Remarks</span></span>  
 <span data-ttu-id="d57b2-106">第一个窗体是前缀递增操作。</span><span class="sxs-lookup"><span data-stu-id="d57b2-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="d57b2-107">操作的结果是操作数递增后的值。</span><span class="sxs-lookup"><span data-stu-id="d57b2-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="d57b2-108">第二个窗体是后缀递增操作。</span><span class="sxs-lookup"><span data-stu-id="d57b2-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="d57b2-109">操作的结果是操作数递增前的值。</span><span class="sxs-lookup"><span data-stu-id="d57b2-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="d57b2-110">数值和枚举类型具有预定义的递增运算符。</span><span class="sxs-lookup"><span data-stu-id="d57b2-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="d57b2-111">用户定义的类型可以重载 `++` 运算符。</span><span class="sxs-lookup"><span data-stu-id="d57b2-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="d57b2-112">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="d57b2-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d57b2-113">示例</span><span class="sxs-lookup"><span data-stu-id="d57b2-113">Example</span></span>  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d57b2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d57b2-114">See Also</span></span>

- [<span data-ttu-id="d57b2-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d57b2-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d57b2-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d57b2-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d57b2-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="d57b2-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

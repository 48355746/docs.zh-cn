---
title: 互锁操作
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f96286da84e41e79fb0b6253d6f20eea89da21a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201345"
---
# <a name="interlocked-operations"></a><span data-ttu-id="860fd-102">互锁操作</span><span class="sxs-lookup"><span data-stu-id="860fd-102">Interlocked operations</span></span>

<span data-ttu-id="860fd-103"><xref:System.Threading.Interlocked?displayProperty=nameWithType> 类中的方法可用于同步对多个线程共享的变量的访问。</span><span class="sxs-lookup"><span data-stu-id="860fd-103">The <xref:System.Threading.Interlocked?displayProperty=nameWithType> class provides methods that synchronize access to a variable that is shared by multiple threads.</span></span> <span data-ttu-id="860fd-104">如果该变量位于共享内存中，则不同进程的线程都可以使用此机制。</span><span class="sxs-lookup"><span data-stu-id="860fd-104">The threads of different processes can use this mechanism if the variable is in shared memory.</span></span> <span data-ttu-id="860fd-105">互锁操作属于原子操作 - 即整个操作是一个单元，不能由针对同一变量的其他操作中断。</span><span class="sxs-lookup"><span data-stu-id="860fd-105">Interlocked operations are atomic — that is, the entire operation is a unit that cannot be interrupted by another operation on the same variable.</span></span> <span data-ttu-id="860fd-106">这在抢占式多线程处理操作系统中非常重要，在此类操作系统中，可在从内存地址加载值之后但有机会更改和存储该值之前将线程挂起。</span><span class="sxs-lookup"><span data-stu-id="860fd-106">This is important in operating systems with preemptive multithreading, where a thread can be suspended after loading a value from a memory address, but before having the chance to alter it and store it.</span></span>  
  
 <span data-ttu-id="860fd-107"><xref:System.Threading.Interlocked> 类提供以下操作：</span><span class="sxs-lookup"><span data-stu-id="860fd-107">The <xref:System.Threading.Interlocked> class provides the following operations:</span></span>  
  
-   <span data-ttu-id="860fd-108"><xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> 方法会向变量添加整数值，并返回此变量的新值。</span><span class="sxs-lookup"><span data-stu-id="860fd-108">The <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> method adds an integer value to a variable and returns the new value of the variable.</span></span>  
  
-   <span data-ttu-id="860fd-109"><xref:System.Threading.Interlocked.Read%2A?displayProperty=nameWithType> 方法以原子操作的形式读取 64 位整数值。</span><span class="sxs-lookup"><span data-stu-id="860fd-109">The <xref:System.Threading.Interlocked.Read%2A?displayProperty=nameWithType> method reads a 64-bit integer value as an atomic operation.</span></span> <span data-ttu-id="860fd-110">这在 32 位操作系统上很有用，在此类操作系统上，读取一个 64 位整数通常不是原子操作。</span><span class="sxs-lookup"><span data-stu-id="860fd-110">This is useful on 32-bit operating systems, where reading a 64-bit integer is not ordinarily an atomic operation.</span></span>  
  
-   <span data-ttu-id="860fd-111"><xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType> 和 <xref:System.Threading.Interlocked.Decrement%2A?displayProperty=nameWithType> 方法递增或递减变量，并返回生成值。</span><span class="sxs-lookup"><span data-stu-id="860fd-111">The <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType> and <xref:System.Threading.Interlocked.Decrement%2A?displayProperty=nameWithType> methods increment or decrement a variable and return the resulting value.</span></span>  
  
-   <span data-ttu-id="860fd-112"><xref:System.Threading.Interlocked.Exchange%2A?displayProperty=nameWithType> 方法在指定变量中以原子操作的形式交换值，同时返回此值并将它替换为新值。</span><span class="sxs-lookup"><span data-stu-id="860fd-112">The <xref:System.Threading.Interlocked.Exchange%2A?displayProperty=nameWithType> method performs an atomic exchange of the value in a specified variable, returning that value and replacing it with a new value.</span></span> <span data-ttu-id="860fd-113">使用此方法的泛型 <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29> 重载在任何引用类型的变量上执行此交换。</span><span class="sxs-lookup"><span data-stu-id="860fd-113">Use a generic <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29> overload of this method to perform the exchange on a variable of any reference type.</span></span>  
  
-   <span data-ttu-id="860fd-114"><xref:System.Threading.Interlocked.CompareExchange%2A?displayProperty=nameWithType> 方法也交换两个值，但具体视比较结果而定。</span><span class="sxs-lookup"><span data-stu-id="860fd-114">The <xref:System.Threading.Interlocked.CompareExchange%2A?displayProperty=nameWithType> method also exchanges two values, but contingent on the result of a comparison.</span></span> <span data-ttu-id="860fd-115">使用此方法的泛型 <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> 重载在任何引用类型的变量上执行此交换。</span><span class="sxs-lookup"><span data-stu-id="860fd-115">Use a generic <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> overload of this method to perform the exchange on a variable of any reference type.</span></span>  
  
 <span data-ttu-id="860fd-116">在新式处理器中，通常使用一个指令即可实现 <xref:System.Threading.Interlocked> 类的方法。</span><span class="sxs-lookup"><span data-stu-id="860fd-116">On modern processors, the methods of the <xref:System.Threading.Interlocked> class can often be implemented by a single instruction.</span></span> <span data-ttu-id="860fd-117">因此，它们提供性能非常高的同步，并且可用于生成更高级的同步机制，例如自旋锁。</span><span class="sxs-lookup"><span data-stu-id="860fd-117">Thus, they provide very high-performance synchronization and can be used to build higher-level synchronization mechanisms, like spin locks.</span></span>  
  
 <span data-ttu-id="860fd-118">有关组合使用 <xref:System.Threading.Monitor> 和 <xref:System.Threading.Interlocked> 类的示例，请参阅 <xref:System.Threading.Monitor>。</span><span class="sxs-lookup"><span data-stu-id="860fd-118">For an example that uses the <xref:System.Threading.Monitor> and <xref:System.Threading.Interlocked> classes in combination, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="compareexchange-example"></a><span data-ttu-id="860fd-119">CompareExchange 示例</span><span class="sxs-lookup"><span data-stu-id="860fd-119">CompareExchange example</span></span>

 <span data-ttu-id="860fd-120"><xref:System.Threading.Interlocked.CompareExchange%2A> 方法可用于保护比简单的递增和递减更为复杂的计算。</span><span class="sxs-lookup"><span data-stu-id="860fd-120">The <xref:System.Threading.Interlocked.CompareExchange%2A> method can be used to protect computations that are more complicated than simple increment and decrement.</span></span> <span data-ttu-id="860fd-121">以下示例演示一个线程安全的方法，该方法向存储为浮点数的累计值执行加运算。</span><span class="sxs-lookup"><span data-stu-id="860fd-121">The following example demonstrates a thread-safe method that adds to a running total stored as a floating point number.</span></span> <span data-ttu-id="860fd-122">（对于整数，<xref:System.Threading.Interlocked.Add%2A> 方法是更简单的解决方案。）有关完整的代码示例，请参阅需要使用单精度和双精度浮点参数的 <xref:System.Threading.Interlocked.CompareExchange%2A> 重载（<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> 和 <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>）。</span><span class="sxs-lookup"><span data-stu-id="860fd-122">(For integers, the <xref:System.Threading.Interlocked.Add%2A> method is a simpler solution.) For complete code examples, see the overloads of <xref:System.Threading.Interlocked.CompareExchange%2A> that take single-precision and double-precision floating-point arguments (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> and <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).</span></span>  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a><span data-ttu-id="860fd-123">Exchange 和 CompareExchange 的非类型化重载</span><span class="sxs-lookup"><span data-stu-id="860fd-123">Untyped overloads of Exchange and CompareExchange</span></span>

 <span data-ttu-id="860fd-124"><xref:System.Threading.Interlocked.Exchange%2A> 和 <xref:System.Threading.Interlocked.CompareExchange%2A> 方法包含需要使用 <xref:System.Object> 类型参数的重载。</span><span class="sxs-lookup"><span data-stu-id="860fd-124">The <xref:System.Threading.Interlocked.Exchange%2A> and <xref:System.Threading.Interlocked.CompareExchange%2A> methods have overloads that take arguments of type <xref:System.Object>.</span></span> <span data-ttu-id="860fd-125">其中每个重载的第一个参数都是 `ref Object`（Visual Basic 中的 `ByRef … As Object`），根据类型安全性要求，必须将传递给此参数的变量严格类型化为 <xref:System.Object>；不能在调用这些方法时，直接将第一个参数强制转换为 <xref:System.Object> 类型。</span><span class="sxs-lookup"><span data-stu-id="860fd-125">The first argument of each of these overloads is `ref Object` (`ByRef … As Object` in Visual Basic), and type safety requires the variable passed to this argument to be typed strictly as <xref:System.Object>; you cannot simply cast the first argument to type <xref:System.Object> when calling these methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="860fd-126">在 .NET Framework 版本 2.0 及更高版本中，使用 <xref:System.Threading.Interlocked.Exchange%2A> 和 <xref:System.Threading.Interlocked.CompareExchange%2A> 方法的泛型重载来交换强类型变量。</span><span class="sxs-lookup"><span data-stu-id="860fd-126">In the .NET Framework version 2.0 and later, use the generic overloads of the <xref:System.Threading.Interlocked.Exchange%2A> and <xref:System.Threading.Interlocked.CompareExchange%2A> methods to exchange strongly typed variables.</span></span>  
  
 <span data-ttu-id="860fd-127">以下代码示例演示只能设置一次的 `ClassA` 类型的属性，正如它在 .NET Framework 1.0 或 1.1 版中实现的那样。</span><span class="sxs-lookup"><span data-stu-id="860fd-127">The following code example shows a property of type `ClassA` that can be set only once, as it might be implemented in the .NET Framework version 1.0 or 1.1.</span></span>  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="860fd-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="860fd-128">See also</span></span>

- <xref:System.Threading.Interlocked?displayProperty=nameWithType>  
- <xref:System.Threading.Monitor?displayProperty=nameWithType>  
- [<span data-ttu-id="860fd-129">线程处理</span><span class="sxs-lookup"><span data-stu-id="860fd-129">Threading</span></span>](index.md)  
- [<span data-ttu-id="860fd-130">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="860fd-130">Threading objects and features</span></span>](threading-objects-and-features.md)

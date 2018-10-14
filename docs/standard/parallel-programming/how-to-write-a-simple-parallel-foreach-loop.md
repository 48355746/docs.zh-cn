---
title: 使用 Parallel.ForEach 编写简单的并行程序
ms.date: 09/12/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cdf4aeb6de027e26687d41d6311b6d7da49e7948
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562211"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>如何：编写简单的 Parallel.ForEach 循环

此示例展示了如何使用 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 循环，对任何 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 数据源启用数据并行。

> [!NOTE]
> 本文档使用 lambda 表达式在 PLINQ 中定义委托。 如果不熟悉 C# 或 Visual Basic 中的 lambda 表达式，请参阅 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)。

## <a name="example"></a>示例

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

<xref:System.Threading.Tasks.Parallel.ForEach%2A> 循环的工作原理类似 <xref:System.Threading.Tasks.Parallel.For%2A> 循环。 对源集合进行分区，并根据系统环境在多个线程上安排工作。 系统上的处理器越多，并行方法的运行速度就越快。 对于一些源集合，顺序循环可能会更快，具体视源大小以及要执行的工作类型而定。 若要详细了解性能，请参阅[数据并行和任务并行的潜在问题](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)

若要详细了解并行循环，请参阅[如何：编写简单的 Parallel.For 循环](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)。

若要将 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 与非泛型集合结合使用，可以使用 <xref:System.Linq.Enumerable.Cast%2A> 扩展方法，将集合转换为泛型集合，如下面的示例所示：

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

还可以使用并行 LINQ (PLINQ) 并行处理 <xref:System.Collections.Generic.IEnumerable%601> 数据源。 借助 PLINQ，可以使用声明性查询语法来表达循环行为。 有关详细信息，请参阅[并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)。

## <a name="compile-and-run-the-code"></a>编译并运行代码

- 将此代码复制并粘贴到 Visual Studio 控制台应用程序项目中。

- 添加对 System.Drawing.dll 的引用

- 按 **F5**

## <a name="see-also"></a>请参阅

- [数据并行](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [并行编程](../../../docs/standard/parallel-programming/index.md)
- [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)

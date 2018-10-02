---
title: 屏障 (.NET Framework)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 385e370f205851630f809b285a93c2609220efeb
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45647546"
---
# <a name="barrier-net-framework"></a>屏障 (.NET Framework)
屏障是用户定义的同步基元，以便于多个线程（称为“参与者”）可以分阶段同时处理算法。 达到代码中的屏障点之前，每个参与者将继续执行。 屏障表示工作阶段的末尾。 单个参与者到达屏障后将被阻止，直至所有参与者都已达到同一障碍。 所有参与者都已达到屏障后，你可以选择调用阶段后操作。 此阶段后操作可由单线程用于执行操作，而所有其他线程仍被阻止。 执行此操作后，所有参与者将不受阻止。  
  
 以下代码片段演示了基本屏障模式。  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 有关完整示例，请参阅[如何：使用屏障同步并发操作](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)。  
  
## <a name="adding-and-removing-participants"></a>添加和删除参与者  
 创建 <xref:System.Threading.Barrier> 时，需指定参与者数量。 还可以随时动态添加或删除参与者。 例如，如果其中一个参与者解决了问题的一部分，可以存储结果，停止执行相应线程，并调用 <xref:System.Threading.Barrier.RemoveParticipant%2A> 以减少屏障中的参与者数量。 当通过调用 <xref:System.Threading.Barrier.AddParticipant%2A> 添加参与者时，返回值将指定当前阶段的数量，这在初始化新的参与者的工作时很有用。  
  
## <a name="broken-barriers"></a>断开的屏障  
 如果一个参与者无法到达屏障，则可能发生死锁。 若要避免这些死锁，请使用 <xref:System.Threading.Barrier.SignalAndWait%2A> 方法的重载来指定超时期限和取消标记。 这些重载将返回一个布尔值，每个参与者均可在继续到下一阶段前进行检查。  
  
## <a name="post-phase-exceptions"></a>阶段后异常  
 如果阶段后委托引发异常，则它将包装在 <xref:System.Threading.BarrierPostPhaseException> 对象中，然后传播到所有参与者。  
  
## <a name="barrier-versus-continuewhenall"></a>屏障与 ContinueWhenAll  
 当线程执行循环中的多个阶段时，屏障特别有用。 如果你的代码仅需一个或多个工作阶段，则应考虑是否配合使用 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 对象与任何类型的隐式联接，其中包括：  
  
-   <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.Invoke%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.ForEach%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.For%2A>  
  
 有关详细信息，请参阅[使用延续任务链接任务](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md)。  
  
## <a name="see-also"></a>请参阅

- [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)  
- [如何：使用 Barrier 同步并发操作](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)

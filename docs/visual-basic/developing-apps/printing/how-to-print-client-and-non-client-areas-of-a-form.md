---
title: 如何：打印窗体的工作区和非工作区 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- title bar [Visual Basic], printing
- printing
- borders [Visual Basic], printing
- entire form
- non-client area [Visual Basic], printing
ms.assetid: 856bb0e4-dbc3-47e2-81cd-4b376cf07757
ms.openlocfilehash: 5109993146a8d53d5cbeebcc52c018a6f0f57ed5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856733"
---
# <a name="how-to-print-client-and-non-client-areas-of-a-form-visual-basic"></a>如何：打印窗体的工作区和非工作区 (Visual Basic)
通过 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件，可以在不使用 <xref:System.Drawing.Printing.PrintDocument> 组件的情况下如实快速打印窗体的图像。 下面的过程演示如何打印窗体，包括工作区和非工作区。 非工作区包括标题栏、边框和滚动条。  
  
 在 Visual Studio 中，不再包含 PowerPack 控件，但您可以下载它们从[下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=25169)。  
  
### <a name="to-print-both-the-client-and-the-non-client-areas-of-a-form"></a>同时打印窗体的工作区和非工作区  
  
1.  在“工具箱” 中，单击“Visual Basic PowerPacks”  选项卡，然后将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件拖动到窗体上。  
  
     <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件被添加到组件栏。  
  
2.  在“属性”  窗口中，将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 属性设置为 <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>。  
  
3.  在相应的事件处理程序中（例如在“打印” `Click` 的 `Button`事件处理程序中）添加以下代码。  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.FullWindow)  
    ```  
  
    > [!NOTE]
    >  在某些操作系统上，通过 <xref:System.Drawing.Graphics> 方法绘制的文本或图形可能无法正确打印。 在这种情况下，请使用兼容的打印方法： `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`)。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [PrintForm 组件](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [如何：打印可滚动的窗体](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)

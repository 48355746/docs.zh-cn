---
title: 如何： 使用两个 DataRepeater 控件 (Visual Studio) 创建母版-详细信息窗体
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245516"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>如何：使用两个 DataRepeater 控件创建主/详细信息窗体 (Visual Studio)
可以使用两个或多个显示相关的数据<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件创建大纲/细节窗体。 例如，你可能想要一个中显示客户列表<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，并当用户选择某个客户，在一秒内显示该客户的订单列表的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>。  
  
 可以通过将共享中的相同主表节点的详细信息项显示相关的数据**数据源**窗口拖到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 例如，如果必须具有对 Customers 表和相关的 Orders 表的数据源，你看到这两个表为中的树视图中的顶级节点**数据源**窗口。 展开的客户节点，以便您可以看到的列。 请注意，在列表中的最后一列表示订单表的可展开节点。 此节点表示客户的相关的订单。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>若要在两个 DataRepeater 控件中显示相关的数据  
  
1.  将两个<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  拖动调整大小和位置图柄以调整控件大小，并将它们置于由并行。  
  
3.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
    > [!NOTE]
    >  如果**数据源**窗口为空，则向其添加数据源。 有关详细信息，请参阅[添加新数据源](/visualstudio/data-tools/add-new-data-sources)。  
  
4.  在中**数据源**窗口中，选择主表的顶级节点。  
  
5.  通过单击主表的拖放类型更改为详细信息**详细信息**表节点上的下拉列表中。  
  
6.  主表节点拖到第一个项模板区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
7.  展开主表节点并选择相关表的详细信息节点。  
  
8.  通过单击详细信息表的拖放类型更改为详细信息**详细信息**表节点上的下拉列表中。  
  
9. 选择此表节点，然后将其拖到第二个项模板区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [如何：在 Windows 窗体应用程序中显示相关数据](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)

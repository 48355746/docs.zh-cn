---
title: 自定义跟踪记录
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: ef3c20890f33f3ffd07a9c88de863e1ebe24851f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520180"
---
# <a name="custom-tracking-records"></a>自定义跟踪记录
本主题演示如何创建自定义跟踪记录并在这些记录中填入将与其一起发出的数据。  
  
## <a name="emitting-custom-tracking-records"></a>发出自定义跟踪记录  
 可以从代码活动中发出自定义跟踪记录，如下面的示例所示。  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 通过对 <xref:System.Activities.Tracking.CustomTrackingRecord> 调用 <xref:System.Activities.NativeActivityContext.Track%2A> 方法，在代码活动中发出 `ActvityContext`。  
  
## <a name="see-also"></a>请参阅  
 [Windows Server App Fabric 监视](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [使用 App Fabric 监视应用程序](https://go.microsoft.com/fwlink/?LinkId=201275)

---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
ms.openlocfilehash: 63af1c9a607cb9f81e2c0abf795ee2b3432cbf9c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397353"
---
# <a name="asymmetricsecuritybindingelement"></a>AsymmetricSecurityBindingElement
AsymmetricSecurityBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>方法  
 AsymmetricSecurityBindingElement 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 AsymmetricSecurityBindingElement 类具有下列属性：  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  
 数据类型：String  
  
 访问类型：只读  
  
 此绑定的消息加密和签名的顺序。  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 数据类型：Boolean  
  
 访问类型：只读  
  
 此绑定是否需要签名确认。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

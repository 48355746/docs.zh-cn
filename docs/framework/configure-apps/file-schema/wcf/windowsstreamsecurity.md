---
title: '&lt;windowsstreamsecurity 正在&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: e117c30ba2583158ee21fd11ff4a38b094c18fd9
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2018
ms.locfileid: "50045923"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="d5d81-102">&lt;windowsstreamsecurity 正在&gt;</span><span class="sxs-lookup"><span data-stu-id="d5d81-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="d5d81-103">指定自定义绑定的 Windows 流安全设置。</span><span class="sxs-lookup"><span data-stu-id="d5d81-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="d5d81-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d5d81-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d5d81-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d5d81-105">\<bindings></span></span>  
<span data-ttu-id="d5d81-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d5d81-106">\<customBinding></span></span>  
<span data-ttu-id="d5d81-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d5d81-107">\<binding></span></span>  
<span data-ttu-id="d5d81-108">\<windowsstreamsecurity 正在 ></span><span class="sxs-lookup"><span data-stu-id="d5d81-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d81-109">语法</span><span class="sxs-lookup"><span data-stu-id="d5d81-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5d81-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d5d81-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d5d81-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d5d81-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5d81-112">特性</span><span class="sxs-lookup"><span data-stu-id="d5d81-112">Attributes</span></span>  
  
|<span data-ttu-id="d5d81-113">特性</span><span class="sxs-lookup"><span data-stu-id="d5d81-113">Attribute</span></span>|<span data-ttu-id="d5d81-114">描述</span><span class="sxs-lookup"><span data-stu-id="d5d81-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5d81-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="d5d81-115">protectionLevel</span></span>|<span data-ttu-id="d5d81-116">定义消息级安全性。</span><span class="sxs-lookup"><span data-stu-id="d5d81-116">Defines message-level security.</span></span> <span data-ttu-id="d5d81-117">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="d5d81-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="d5d81-118">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="d5d81-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="d5d81-119">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="d5d81-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d5d81-120">-None： 无保护。</span><span class="sxs-lookup"><span data-stu-id="d5d81-120">-   None: No protection.</span></span><br /><span data-ttu-id="d5d81-121">登录： 对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="d5d81-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="d5d81-122">-EncryptAndSign： 消息签名并加密。</span><span class="sxs-lookup"><span data-stu-id="d5d81-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="d5d81-123">默认值为 EncryptAndSign。</span><span class="sxs-lookup"><span data-stu-id="d5d81-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="d5d81-124">此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。</span><span class="sxs-lookup"><span data-stu-id="d5d81-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5d81-125">子元素</span><span class="sxs-lookup"><span data-stu-id="d5d81-125">Child Elements</span></span>  
 <span data-ttu-id="d5d81-126">无</span><span class="sxs-lookup"><span data-stu-id="d5d81-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5d81-127">父元素</span><span class="sxs-lookup"><span data-stu-id="d5d81-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d5d81-128">元素</span><span class="sxs-lookup"><span data-stu-id="d5d81-128">Element</span></span>|<span data-ttu-id="d5d81-129">描述</span><span class="sxs-lookup"><span data-stu-id="d5d81-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5d81-130">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d5d81-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d5d81-131">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="d5d81-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5d81-132">备注</span><span class="sxs-lookup"><span data-stu-id="d5d81-132">Remarks</span></span>  
 <span data-ttu-id="d5d81-133">使用面向流协议（如 TCP 和命名管道）的传输支持基于流的传输升级。</span><span class="sxs-lookup"><span data-stu-id="d5d81-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="d5d81-134">特别是 WCF 提供了安全升级。</span><span class="sxs-lookup"><span data-stu-id="d5d81-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="d5d81-135">此传输安全的配置以及通过封装此配置元素[ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)，其中可以配置，并添加到自定义绑定</span><span class="sxs-lookup"><span data-stu-id="d5d81-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d81-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5d81-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="d5d81-137">绑定</span><span class="sxs-lookup"><span data-stu-id="d5d81-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d5d81-138">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="d5d81-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d5d81-139">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="d5d81-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d5d81-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d5d81-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

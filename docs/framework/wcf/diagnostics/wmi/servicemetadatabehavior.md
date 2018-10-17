---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 19a04b6432f1ecc38a3b906b7e677175863134db
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374815"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="d93b6-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="d93b6-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="d93b6-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="d93b6-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d93b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="d93b6-104">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d93b6-105">方法</span><span class="sxs-lookup"><span data-stu-id="d93b6-105">Methods</span></span>  
 <span data-ttu-id="d93b6-106">ServiceMetadataBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="d93b6-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d93b6-107">属性</span><span class="sxs-lookup"><span data-stu-id="d93b6-107">Properties</span></span>  
 <span data-ttu-id="d93b6-108">ServiceMetadataBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="d93b6-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="d93b6-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="d93b6-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="d93b6-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d93b6-110">Data type: string</span></span>  
  
 <span data-ttu-id="d93b6-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d93b6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d93b6-112">设置服务重定向元数据请求的位置。</span><span class="sxs-lookup"><span data-stu-id="d93b6-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="d93b6-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="d93b6-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="d93b6-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="d93b6-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="d93b6-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d93b6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d93b6-116">控制服务是否在 `HttpGetUrl` 属性控制的地址上发布其 WSDL。</span><span class="sxs-lookup"><span data-stu-id="d93b6-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="d93b6-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="d93b6-117">HttpGetUrl</span></span>  
 <span data-ttu-id="d93b6-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d93b6-118">Data type: string</span></span>  
  
 <span data-ttu-id="d93b6-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d93b6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d93b6-120">设置位置，在该位置发布服务 WSDL 以便使用 HTTP 进行检索。</span><span class="sxs-lookup"><span data-stu-id="d93b6-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="d93b6-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="d93b6-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="d93b6-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="d93b6-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="d93b6-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d93b6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d93b6-124">控制服务是否在 `HttpsGetUrl` 属性控制的地址上通过 HTTPS 发布其 WSDL。</span><span class="sxs-lookup"><span data-stu-id="d93b6-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="d93b6-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="d93b6-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="d93b6-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d93b6-126">Data type: string</span></span>  
  
 <span data-ttu-id="d93b6-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d93b6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d93b6-128">设置位置，在该位置发布服务 WSDL 以便使用 HTTPS 进行检索。</span><span class="sxs-lookup"><span data-stu-id="d93b6-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d93b6-129">要求</span><span class="sxs-lookup"><span data-stu-id="d93b6-129">Requirements</span></span>  
  
|<span data-ttu-id="d93b6-130">MOF</span><span class="sxs-lookup"><span data-stu-id="d93b6-130">MOF</span></span>|<span data-ttu-id="d93b6-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="d93b6-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d93b6-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="d93b6-132">Namespace</span></span>|<span data-ttu-id="d93b6-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="d93b6-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d93b6-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d93b6-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>

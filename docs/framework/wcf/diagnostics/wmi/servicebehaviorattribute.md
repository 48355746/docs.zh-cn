---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: c2915c636aec26cfb1f58d12da49151915c52c05
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182952"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="be383-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="be383-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="be383-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="be383-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be383-104">语法</span><span class="sxs-lookup"><span data-stu-id="be383-104">Syntax</span></span>  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="be383-105">方法</span><span class="sxs-lookup"><span data-stu-id="be383-105">Methods</span></span>  
 <span data-ttu-id="be383-106">ServiceBehaviorAttribute 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="be383-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="be383-107">属性</span><span class="sxs-lookup"><span data-stu-id="be383-107">Properties</span></span>  
 <span data-ttu-id="be383-108">ServiceBehaviorAttribute 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="be383-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="be383-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="be383-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="be383-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="be383-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="be383-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-112">指示在客户端关闭输出会话时是否自动关闭会话。</span><span class="sxs-lookup"><span data-stu-id="be383-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="be383-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="be383-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="be383-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="be383-114">Data type: string</span></span>  
<span data-ttu-id="be383-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-116">指示服务是支持单线程、多线程还是支持可重入调用。</span><span class="sxs-lookup"><span data-stu-id="be383-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="be383-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="be383-117">ConfigurationName</span></span>  
 <span data-ttu-id="be383-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="be383-118">Data type: string</span></span>  
  
 <span data-ttu-id="be383-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-120">服务配置的名称。</span><span class="sxs-lookup"><span data-stu-id="be383-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="be383-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="be383-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="be383-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="be383-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="be383-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-124">指定是否要将未知序列化数据发送到网络上。</span><span class="sxs-lookup"><span data-stu-id="be383-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="be383-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="be383-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="be383-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="be383-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="be383-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-128">指定是否在返回给客户端的 SOAP 错误详细信息中包含托管异常信息以供调试。</span><span class="sxs-lookup"><span data-stu-id="be383-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="be383-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="be383-129">InstanceContextMode</span></span>  
 <span data-ttu-id="be383-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="be383-130">Data type: string</span></span>  
  
 <span data-ttu-id="be383-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-132">指定何时创建新服务对象。</span><span class="sxs-lookup"><span data-stu-id="be383-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="be383-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="be383-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="be383-134">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="be383-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="be383-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-136">序列化对象中允许的最大项数。</span><span class="sxs-lookup"><span data-stu-id="be383-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="be383-137">name</span><span class="sxs-lookup"><span data-stu-id="be383-137">Name</span></span>  
 <span data-ttu-id="be383-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="be383-138">Data type: string</span></span>  
  
 <span data-ttu-id="be383-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-140">WSDL 中服务的名称属性。</span><span class="sxs-lookup"><span data-stu-id="be383-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="be383-141">命名空间</span><span class="sxs-lookup"><span data-stu-id="be383-141">Namespace</span></span>  
 <span data-ttu-id="be383-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="be383-142">Data type: string</span></span>  
  
 <span data-ttu-id="be383-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-144">WSDL 中服务的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="be383-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="be383-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="be383-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="be383-146">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="be383-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="be383-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-148">指定当前事务完成后，是否回收服务对象。</span><span class="sxs-lookup"><span data-stu-id="be383-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="be383-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="be383-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="be383-150">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="be383-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="be383-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-152">指定当前会话关闭时，挂起的事务是否已完成。</span><span class="sxs-lookup"><span data-stu-id="be383-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="be383-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="be383-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="be383-154">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="be383-154">Data type: string</span></span>  
  
 <span data-ttu-id="be383-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-156">指定事务的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="be383-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="be383-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="be383-157">TransactionTimeout</span></span>  
 <span data-ttu-id="be383-158">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="be383-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="be383-159">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-160">事务必须在此期间完成的时间段。</span><span class="sxs-lookup"><span data-stu-id="be383-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="be383-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="be383-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="be383-162">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="be383-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="be383-163">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-164">指定是否使用当前同步上下文来选择线程执行。</span><span class="sxs-lookup"><span data-stu-id="be383-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="be383-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="be383-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="be383-166">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="be383-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="be383-167">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="be383-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be383-168">指定系统或应用程序是否强制执行 SOAP MustUnderstand 标头处理。</span><span class="sxs-lookup"><span data-stu-id="be383-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be383-169">要求</span><span class="sxs-lookup"><span data-stu-id="be383-169">Requirements</span></span>  
  
|<span data-ttu-id="be383-170">MOF</span><span class="sxs-lookup"><span data-stu-id="be383-170">MOF</span></span>|<span data-ttu-id="be383-171">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="be383-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="be383-172">命名空间</span><span class="sxs-lookup"><span data-stu-id="be383-172">Namespace</span></span>|<span data-ttu-id="be383-173">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="be383-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be383-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="be383-174">See Also</span></span>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>

---
title: ICLRStrongName::GetHashFromFile 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33aab5ee23a1f0d30d1f9f3079856ca30d46d2ec
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862076"
---
# <a name="iclrstrongnamegethashfromfile-method"></a>ICLRStrongName::GetHashFromFile 方法
生成指定文件内容的哈希。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szFilePath`  
 [in]哈希的文件的名称。  
  
 `piHashAlg`  
 [in、 out]要生成哈希时使用的算法。 有效的算法是定义的 Win32 CryptoAPI。 如果`piHashAlg`设置为 0，使用 CALG_SHA 1 的默认算法。  
  
 `pbHash`  
 [out]包含生成的哈希的字节数组。  
  
 `cchHash`  
 [in]缓冲区的最大大小的`pbHash`指向。  
  
 `pchHash`  
 [out]大小 （字节），则返回的`pbHash`。  
  
## <a name="return-value"></a>返回值  
 `S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。  
  
## <a name="remarks"></a>备注  
 此方法等同于[iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)方法，不同之处在于的文件的名称规范是 ANSI 而不是 Unicode。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [GetHashFromFileW 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

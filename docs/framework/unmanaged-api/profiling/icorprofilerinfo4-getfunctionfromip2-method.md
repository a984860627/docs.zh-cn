---
title: "ICorProfilerInfo4::GetFunctionFromIP2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetFunctionFromIP2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f354bdc198a8060c7241a2b9bdb472bee5ed7b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a>ICorProfilerInfo4::GetFunctionFromIP2 方法
将托管的代码指令指针映射到函数的 JIT 重新编译版本。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
#### <a name="parameters"></a>参数  
 `ip`  
 [in]托管代码中的指令指针。  
  
 `pFunctionId`  
 [out]函数 id。  
  
 `pReJitId`  
 [out]函数的 JIT 重新编译版本的标识。  
  
## <a name="remarks"></a>备注  
 `GetFunctionFromIP2`类似于`GetFunctionFromIP`，只不过它获取而不是包含指定的 IP 地址的函数的函数 ID 的 JIT 重新编译的 ID。  
  
> [!NOTE]
>  `GetFunctionFromIP2`可以触发垃圾回收，而`GetFunctionFromIP`将不会。  有关详细信息，请参阅[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

---
title: "ICorDebugRegisterSet 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet
helpviewer_keywords: ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 714f3d7839ce1d8b65405b6cb3c91d43f1db6642
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset-interface"></a>ICorDebugRegisterSet 接口
表示当前正在执行代码的计算机上可用的寄存器组。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetRegisters 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|（在计算机上当前正在执行代码） 中获取的每个寄存器的值指定的位掩码。|  
|[GetRegistersAvailable 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|获取的位掩码，该值指示用于在此注册`ICorDebugRegisterSet`当前可用。|  
|[GetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|获取当前线程的上下文。|  
|[SetRegisters 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|尚未实现对.NET Framework 2.0 版。|  
|[SetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|尚未实现对.NET Framework 2.0。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugRegisterSet`接口支持仅 32 位寄存器。 使用[ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)在需要其他寄存器例如 ia-64 的平台上的接口。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ICorDebugRegisterSet2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)

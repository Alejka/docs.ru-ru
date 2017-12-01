---
title: "Метод ICLRTask::SetTaskIdentifier"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SetTaskIdentifier
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 916f4638ad8206352f3b5973bb6c8b5dab39cda4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="8a3b2-102">Метод ICLRTask::SetTaskIdentifier</span><span class="sxs-lookup"><span data-stu-id="8a3b2-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="8a3b2-103">Указывает, что общеязыковая среда выполнения (CLR), чтобы связать заданное значение идентификатора с задачей, представленный текущим [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a3b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a3b2-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a3b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a3b2-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="8a3b2-106">[in] Уникальный идентификатор для CLR, необходимо связать с задачей, представленный текущим `ICLRTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a3b2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8a3b2-107">Return Value</span></span>  
  
|<span data-ttu-id="8a3b2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a3b2-108">HRESULT</span></span>|<span data-ttu-id="8a3b2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8a3b2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a3b2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a3b2-110">S_OK</span></span>|<span data-ttu-id="8a3b2-111">`SetTaskIdentifier`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="8a3b2-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a3b2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a3b2-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a3b2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a3b2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a3b2-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-115">The call timed out.</span></span>|  
|<span data-ttu-id="8a3b2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a3b2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a3b2-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a3b2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a3b2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a3b2-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a3b2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a3b2-120">E_FAIL</span></span>|<span data-ttu-id="8a3b2-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a3b2-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a3b2-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a3b2-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a3b2-124">Remarks</span></span>  
 <span data-ttu-id="8a3b2-125">Узел может связать идентификатор с задачей для содействия интеграции среды CLR и узлов в среде отладки.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="8a3b2-126">Идентификатор не имеет смысла для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="8a3b2-127">Среда CLR передает его вместе с отладчиком.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="8a3b2-128">Отладчик можно использовать этот идентификатор для связи стека вызовов среды CLR с основного приложения и включить их, сведения трассировки, соответствующих единой, при просмотре в пользовательском интерфейсе отладчика.</span><span class="sxs-lookup"><span data-stu-id="8a3b2-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3b2-129">Требования</span><span class="sxs-lookup"><span data-stu-id="8a3b2-129">Requirements</span></span>  
 <span data-ttu-id="8a3b2-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a3b2-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3b2-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a3b2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a3b2-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a3b2-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a3b2-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3b2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3b2-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8a3b2-134">See Also</span></span>  
 [<span data-ttu-id="8a3b2-135">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8a3b2-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="8a3b2-136">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8a3b2-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="8a3b2-137">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8a3b2-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="8a3b2-138">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8a3b2-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
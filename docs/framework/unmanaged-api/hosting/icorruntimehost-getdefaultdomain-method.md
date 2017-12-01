---
title: "Метод ICorRuntimeHost::GetDefaultDomain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.GetDefaultDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c482247a0a227c202bb81db09d13ad9af71e60f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="976de-102">Метод ICorRuntimeHost::GetDefaultDomain</span><span class="sxs-lookup"><span data-stu-id="976de-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="976de-103">Получает указатель интерфейса типа <xref:System._AppDomain?displayProperty=nameWithType> , представляющий домен по умолчанию для текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="976de-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="976de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="976de-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="976de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="976de-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="976de-106">[out] Указатель на интерфейс типа <xref:System._AppDomain?displayProperty=nameWithType> для <xref:System.AppDomain> экземпляр, который представляет домен приложения по умолчанию для процесса.</span><span class="sxs-lookup"><span data-stu-id="976de-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="976de-107">Этот указатель является типизированным `IUnknown`, поэтому обычно следует вызывать вызывающим объектам `QueryInterface` для получения указателя на интерфейс типа <xref:System._AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="976de-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="976de-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="976de-108">Return Value</span></span>  
  
|<span data-ttu-id="976de-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="976de-109">HRESULT</span></span>|<span data-ttu-id="976de-110">Описание</span><span class="sxs-lookup"><span data-stu-id="976de-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="976de-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="976de-111">S_OK</span></span>|<span data-ttu-id="976de-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="976de-112">The operation was successful.</span></span>|  
|<span data-ttu-id="976de-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="976de-113">S_FALSE</span></span>|<span data-ttu-id="976de-114">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="976de-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="976de-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="976de-115">E_FAIL</span></span>|<span data-ttu-id="976de-116">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="976de-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="976de-117">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="976de-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="976de-118">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="976de-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="976de-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="976de-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="976de-120">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="976de-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="976de-121">Требования</span><span class="sxs-lookup"><span data-stu-id="976de-121">Requirements</span></span>  
 <span data-ttu-id="976de-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="976de-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="976de-123">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="976de-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="976de-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="976de-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="976de-125">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="976de-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="976de-126">См. также</span><span class="sxs-lookup"><span data-stu-id="976de-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="976de-127">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="976de-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
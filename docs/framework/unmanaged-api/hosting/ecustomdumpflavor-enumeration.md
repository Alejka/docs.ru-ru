---
title: "Перечисление ECustomDumpFlavor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ECustomDumpFlavor
api_location: mscoree.dll
api_type: COM
f1_keywords: ECustomDumpFlavor
helpviewer_keywords: ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a7317a3a12acef2a16deebab9a1e1b10205ebf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="facca-102">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="facca-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="facca-103">Содержит значения, указывающие, какие элементы будут включены в пользовательское подмножество кучи дампа при сообщении об ошибках.</span><span class="sxs-lookup"><span data-stu-id="facca-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="facca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="facca-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="facca-105">Члены</span><span class="sxs-lookup"><span data-stu-id="facca-105">Members</span></span>  
  
|<span data-ttu-id="facca-106">Член</span><span class="sxs-lookup"><span data-stu-id="facca-106">Member</span></span>|<span data-ttu-id="facca-107">Описание</span><span class="sxs-lookup"><span data-stu-id="facca-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="facca-108">Указывает, что дамп пользовательской кучи должен запустить как мини-дамп и содержать дополнительные данные, заданные любой [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) экземпляров, переданный в одном методе.</span><span class="sxs-lookup"><span data-stu-id="facca-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="facca-109">Указывает, что дамп пользовательской кучи необходимо собрать все данные состояния среды выполнения, которые не были выделены динамично.</span><span class="sxs-lookup"><span data-stu-id="facca-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="facca-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="facca-110">Remarks</span></span>  
 <span data-ttu-id="facca-111">Тип параметра `ECustomDumpFlavor` передается [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="facca-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="facca-112">Требования</span><span class="sxs-lookup"><span data-stu-id="facca-112">Requirements</span></span>  
 <span data-ttu-id="facca-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="facca-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="facca-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="facca-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="facca-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="facca-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="facca-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="facca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facca-117">См. также</span><span class="sxs-lookup"><span data-stu-id="facca-117">See Also</span></span>  
 [<span data-ttu-id="facca-118">Ecustomdumpitemkind-перечисление</span><span class="sxs-lookup"><span data-stu-id="facca-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="facca-119">Iclrerrorreportingmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="facca-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="facca-120">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="facca-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
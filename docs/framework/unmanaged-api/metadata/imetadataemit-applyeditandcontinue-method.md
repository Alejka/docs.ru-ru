---
title: "Метод IMetaDataEmit::ApplyEditAndContinue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.ApplyEditAndContinue
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6d7744051bca9aeec677803f8b6c0bbbd0cdd1fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="01fde-102">Метод IMetaDataEmit::ApplyEditAndContinue</span><span class="sxs-lookup"><span data-stu-id="01fde-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="01fde-103">Обновляет текущую область сборки с изменениями, сделанными в указанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="01fde-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01fde-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01fde-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01fde-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01fde-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="01fde-106">[in] Указатель на <<!--zzxref:IUnknown --> `IUnknown`>, представляющий дельта метаданных из переносимого исполняемого (PE) файла.</span><span class="sxs-lookup"><span data-stu-id="01fde-106">[in] Pointer to an <<!--zzxref:IUnknown --> `IUnknown`> object that represents the delta metadata from the portable executable (PE) file.</span></span>  
  
 <span data-ttu-id="01fde-107">Разностные метаданные — это блок метаданных, содержащих изменения, внесенные в копию фактических метаданных модуля.</span><span class="sxs-lookup"><span data-stu-id="01fde-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01fde-108">Требования</span><span class="sxs-lookup"><span data-stu-id="01fde-108">Requirements</span></span>  
 <span data-ttu-id="01fde-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01fde-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01fde-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="01fde-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01fde-111">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01fde-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01fde-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01fde-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01fde-113">См. также</span><span class="sxs-lookup"><span data-stu-id="01fde-113">See Also</span></span>  
 [<span data-ttu-id="01fde-114">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="01fde-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="01fde-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="01fde-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
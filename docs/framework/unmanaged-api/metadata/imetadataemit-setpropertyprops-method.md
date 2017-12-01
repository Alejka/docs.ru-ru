---
title: "Метод IMetaDataEmit::SetPropertyProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fe79846b9fd576941c706b48a7aed0667c264a3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="225c5-102">Метод IMetaDataEmit::SetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="225c5-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="225c5-103">Задает функции сохранения в метаданных для свойства, определенные во время предыдущего вызова для [метод DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="225c5-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="225c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="225c5-104">Syntax</span></span>  
  
```  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="225c5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="225c5-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="225c5-106">[in] Маркер для изменения свойства</span><span class="sxs-lookup"><span data-stu-id="225c5-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="225c5-107">[in] Флаги свойства.</span><span class="sxs-lookup"><span data-stu-id="225c5-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="225c5-108">[in] Тип значения по умолчанию этого свойства.</span><span class="sxs-lookup"><span data-stu-id="225c5-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="225c5-109">[in] Значение по умолчанию для свойства.</span><span class="sxs-lookup"><span data-stu-id="225c5-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="225c5-110">[in] Количество (Юникод) символы в `pValue`.</span><span class="sxs-lookup"><span data-stu-id="225c5-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="225c5-111">[in] Метод, который задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="225c5-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="225c5-112">[in] Метод, который возвращает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="225c5-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="225c5-113">[in] Массив из других методов, связанное со свойством.</span><span class="sxs-lookup"><span data-stu-id="225c5-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="225c5-114">Этот массив `mdTokenNil` токена.</span><span class="sxs-lookup"><span data-stu-id="225c5-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="225c5-115">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-115">Requirements</span></span>  
 <span data-ttu-id="225c5-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="225c5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="225c5-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="225c5-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="225c5-118">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="225c5-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="225c5-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="225c5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="225c5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="225c5-120">See Also</span></span>  
 [<span data-ttu-id="225c5-121">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="225c5-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="225c5-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="225c5-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
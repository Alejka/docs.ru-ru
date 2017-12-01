---
title: "Метод IMetaDataDispenserEx::SetOption"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.SetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a58ac4379522c13125f98df058cd67bceb7cdbd1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexsetoption-method"></a><span data-ttu-id="081e6-102">Метод IMetaDataDispenserEx::SetOption</span><span class="sxs-lookup"><span data-stu-id="081e6-102">IMetaDataDispenserEx::SetOption Method</span></span>
<span data-ttu-id="081e6-103">Устанавливает для указанного параметра заданное значение для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="081e6-103">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="081e6-104">Параметр определяет способ обработки вызовов текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="081e6-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="081e6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="081e6-105">Syntax</span></span>  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="081e6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="081e6-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="081e6-107">[in] Указатель на идентификатор GUID, который указывает параметр должен иметь значение.</span><span class="sxs-lookup"><span data-stu-id="081e6-107">[in] A pointer to a GUID that specifies the option to be set.</span></span>  
  
 `pValue`  
 <span data-ttu-id="081e6-108">[in] Значение, используемое для задания параметра.</span><span class="sxs-lookup"><span data-stu-id="081e6-108">[in] The value to use to set the option.</span></span> <span data-ttu-id="081e6-109">Тип этого значения должен быть разновидностью указанного параметра.</span><span class="sxs-lookup"><span data-stu-id="081e6-109">The type of this value must be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="081e6-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="081e6-110">Remarks</span></span>  
 <span data-ttu-id="081e6-111">В следующей таблице перечислены доступные идентификаторы GUID, `optionId` может указывать параметр и соответствующие допустимые значения для `pValue` параметра.</span><span class="sxs-lookup"><span data-stu-id="081e6-111">The following table lists the available GUIDs that the `optionId` parameter can point to and the corresponding valid values for the `pValue` parameter.</span></span>  
  
|<span data-ttu-id="081e6-112">GUID</span><span class="sxs-lookup"><span data-stu-id="081e6-112">GUID</span></span>|<span data-ttu-id="081e6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="081e6-113">Description</span></span>|<span data-ttu-id="081e6-114">`pValue`Параметр</span><span class="sxs-lookup"><span data-stu-id="081e6-114">`pValue` Parameter</span></span>|  
|----------|-----------------|------------------------|  
|<span data-ttu-id="081e6-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="081e6-115">MetaDataCheckDuplicatesFor</span></span>|<span data-ttu-id="081e6-116">Определяет, какие элементы проверяются на наличие дубликатов.</span><span class="sxs-lookup"><span data-stu-id="081e6-116">Controls which items are checked for duplicates.</span></span> <span data-ttu-id="081e6-117">Каждый раз при вызове [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) метод, который создает новый элемент, вы можете запросить метод для проверки, является ли элемент уже существует в текущей области.</span><span class="sxs-lookup"><span data-stu-id="081e6-117">Each time you call an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) method that creates a new item, you can ask the method to check whether the item already exists in the current scope.</span></span> <span data-ttu-id="081e6-118">Например, можно проверить наличие `mdMethodDef` элементы; в этом случае при вызове [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), она проверяет, что метод уже существует в текущей области.</span><span class="sxs-lookup"><span data-stu-id="081e6-118">For example, you can check for the existence of `mdMethodDef` items; in this case, when you call [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), it will check that the method does not already exist in the current scope.</span></span> <span data-ttu-id="081e6-119">Эта проверка используется ключ, который однозначно определяет данный метод: родительский тип, имя и подпись.</span><span class="sxs-lookup"><span data-stu-id="081e6-119">This check uses the key that uniquely identifies a given method: parent type, name, and signature.</span></span>|<span data-ttu-id="081e6-120">Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="081e6-120">Must be a variant of type UI4, and must contain a combination of the values of the [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="081e6-121">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="081e6-121">MetaDataRefToDefCheck</span></span>|<span data-ttu-id="081e6-122">Элементы управления, которые ссылки на элементы, преобразуемые в определения.</span><span class="sxs-lookup"><span data-stu-id="081e6-122">Controls which referenced items are converted to definitions.</span></span> <span data-ttu-id="081e6-123">По умолчанию ядро метаданных будет оптимизировать код, преобразование ссылочного элемента его определение, если указанный элемент, фактически определенных в текущей области.</span><span class="sxs-lookup"><span data-stu-id="081e6-123">By default, the metadata engine will optimize the code by converting a referenced item to its definition if the referenced item is actually defined in the current scope.</span></span>|<span data-ttu-id="081e6-124">Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="081e6-124">Must be a variant of type UI4, and must contain a combination of the values of the [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="081e6-125">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="081e6-125">MetaDataNotificationForTokenMovement</span></span>|<span data-ttu-id="081e6-126">Задает, какой токен, происходящее при слиянии метаданных создает обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="081e6-126">Controls which token remaps occurring during a metadata merge generate callbacks.</span></span> <span data-ttu-id="081e6-127">Используйте [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) метод, чтобы установить вашей [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="081e6-127">Use the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method to establish your [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface.</span></span>|<span data-ttu-id="081e6-128">Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="081e6-128">Must be a variant of type UI4, and must contain a combination of the values of the [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="081e6-129">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="081e6-129">MetaDataSetENC</span></span>|<span data-ttu-id="081e6-130">Управляет поведением edit and continue (ENC).</span><span class="sxs-lookup"><span data-stu-id="081e6-130">Controls the behavior of edit-and-continue (ENC).</span></span> <span data-ttu-id="081e6-131">Одновременно можно задать только один режим работы.</span><span class="sxs-lookup"><span data-stu-id="081e6-131">Only one mode of behavior can be set at a time.</span></span>|<span data-ttu-id="081e6-132">Должен быть разновидностью UI4 и должен содержать значение [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="081e6-132">Must be a variant of type UI4, and must contain a value of the [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) enumeration.</span></span> <span data-ttu-id="081e6-133">Значение не является битовой маской.</span><span class="sxs-lookup"><span data-stu-id="081e6-133">The value is not a bitmask.</span></span>|  
|<span data-ttu-id="081e6-134">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="081e6-134">MetaDataErrorIfEmitOutOfOrder</span></span>|<span data-ttu-id="081e6-135">Элементы управления, какие ошибки создается out порядок создания обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="081e6-135">Controls which emitted-out-of-order errors generate callbacks.</span></span> <span data-ttu-id="081e6-136">Выдача метаданных по порядку не является неустранимой; Однако если вы предоставлять метаданные в порядке их предпочитаемую ядром метаданных, метаданные является более компактным и таким образом можно повысить эффективность поиска.</span><span class="sxs-lookup"><span data-stu-id="081e6-136">Emitting metadata out of order is not fatal; however, if you emit metadata in an order that is favored by the metadata engine, the metadata is more compact and therefore can be more efficiently searched.</span></span> <span data-ttu-id="081e6-137">Используйте `IMetaDataEmit::SetHandler` метод, чтобы установить вашей [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="081e6-137">Use the `IMetaDataEmit::SetHandler` method to establish your [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) interface.</span></span>|<span data-ttu-id="081e6-138">Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="081e6-138">Must be a variant of type UI4, and must contain a combination of the values of the [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="081e6-139">MetaDataImportOption</span><span class="sxs-lookup"><span data-stu-id="081e6-139">MetaDataImportOption</span></span>|<span data-ttu-id="081e6-140">Определяет, какие типы элементов, которые были удалены в процессе ENC извлекаются при помощи перечислителя.</span><span class="sxs-lookup"><span data-stu-id="081e6-140">Controls which kinds of items that were deleted during an ENC are retrieved by an enumerator.</span></span>|<span data-ttu-id="081e6-141">Должен быть разновидностью UI4 и должен состоять из комбинации значений [перечисление CorImportOptions](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="081e6-141">Must be a variant of type UI4, and must contain a combination of the values of the [CorImportOptions Enumeration](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="081e6-142">MetaDataThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="081e6-142">MetaDataThreadSafetyOptions</span></span>|<span data-ttu-id="081e6-143">Управляет ли ядро метаданных получает модулей чтения/записи блокировки, обеспечивая безопасность потоков.</span><span class="sxs-lookup"><span data-stu-id="081e6-143">Controls whether the metadata engine obtains reader/writer locks, thereby ensuring thread safety.</span></span> <span data-ttu-id="081e6-144">По умолчанию в ядре предполагается, что доступа является однопоточным вызывающим объектом, поэтому блокировки не создаются.</span><span class="sxs-lookup"><span data-stu-id="081e6-144">By default, the engine assumes that access is single-threaded by the caller, so no locks are obtained.</span></span> <span data-ttu-id="081e6-145">Клиенты отвечают за обслуживание надлежащего выполнения синхронизации потока при использовании API метаданных.</span><span class="sxs-lookup"><span data-stu-id="081e6-145">Clients are responsible for maintaining proper thread synchronization when using the metadata API.</span></span>|<span data-ttu-id="081e6-146">Должен быть разновидностью UI4 и должен содержать значение [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="081e6-146">Must be a variant of type UI4, and must contain a value of the [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) enumeration.</span></span> <span data-ttu-id="081e6-147">Значение не является битовой маской.</span><span class="sxs-lookup"><span data-stu-id="081e6-147">The value is not a bitmask.</span></span>|  
|<span data-ttu-id="081e6-148">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="081e6-148">MetaDataGenerateTCEAdapters</span></span>|<span data-ttu-id="081e6-149">Определяет, должна ли программа импорта библиотек типов создавать адаптеры тесно связанных событий (TCE) для контейнеров точек подключения COM.</span><span class="sxs-lookup"><span data-stu-id="081e6-149">Controls whether the type library importer should generate the tightly coupled event (TCE) adapters for COM connection point containers.</span></span>|<span data-ttu-id="081e6-150">Должен быть разновидностью типа BOOL.</span><span class="sxs-lookup"><span data-stu-id="081e6-150">Must be a variant of type BOOL.</span></span> <span data-ttu-id="081e6-151">Если `pValue` равно `true`, программа импорта библиотек типов создает адаптеры TCE.</span><span class="sxs-lookup"><span data-stu-id="081e6-151">If `pValue` is set to `true`, the type library importer generates the TCE adapters.</span></span>|  
|<span data-ttu-id="081e6-152">MetaDataTypeLibImportNamespace</span><span class="sxs-lookup"><span data-stu-id="081e6-152">MetaDataTypeLibImportNamespace</span></span>|<span data-ttu-id="081e6-153">Задает другие пространства имен для библиотеки типов, импортируемой.</span><span class="sxs-lookup"><span data-stu-id="081e6-153">Specifies a non-default namespace for the type library that is being imported.</span></span>|<span data-ttu-id="081e6-154">Необходимо значение null или является разновидностью типа BSTR.</span><span class="sxs-lookup"><span data-stu-id="081e6-154">Must be either a null value or a variant of type BSTR.</span></span> <span data-ttu-id="081e6-155">Если `pValue` имеет значение null, текущее пространство имен имеет значение null; в противном случае, текущего пространства имен имеет значение в строку, которая хранится в разновидности типа BSTR.</span><span class="sxs-lookup"><span data-stu-id="081e6-155">If `pValue` is a null value, the current namespace is set to null; otherwise, the current namespace is set to the string that is held in the variant's BSTR type.</span></span>|  
|<span data-ttu-id="081e6-156">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="081e6-156">MetaDataLinkerOptions</span></span>|<span data-ttu-id="081e6-157">Определяет, должен ли компоновщик создать сборку или файл модуля .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="081e6-157">Controls whether the linker should generate an assembly or a .NET Framework module file.</span></span>|<span data-ttu-id="081e6-158">Должен быть разновидностью UI4 и должен состоять из комбинации значений [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="081e6-158">Must be a variant of type UI4, and must contain a combination of the values of the [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) enumeration.</span></span>|  
|<span data-ttu-id="081e6-159">MetaDataRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="081e6-159">MetaDataRuntimeVersion</span></span>|<span data-ttu-id="081e6-160">Указывает версию среды CLR, для которого был создан этот образ.</span><span class="sxs-lookup"><span data-stu-id="081e6-160">Specifies the version of the common language runtime against which this image was built.</span></span> <span data-ttu-id="081e6-161">Версия сохраняется в виде строки, например «v1.0.3705».</span><span class="sxs-lookup"><span data-stu-id="081e6-161">The version is stored as a string, such as "v1.0.3705".</span></span>|<span data-ttu-id="081e6-162">Должно быть значение null, значение VT_EMPTY или разновидностью BSTR.</span><span class="sxs-lookup"><span data-stu-id="081e6-162">Must be a null value, a VT_EMPTY value, or a variant of type BSTR.</span></span> <span data-ttu-id="081e6-163">Если `pValue` является null, для версии среды выполнения устанавливается значение null.</span><span class="sxs-lookup"><span data-stu-id="081e6-163">If `pValue` is null, the runtime version is set to null.</span></span> <span data-ttu-id="081e6-164">Если `pValue` равно VT_EMPTY, версия устанавливается в значение по умолчанию, которое выводится из версии Mscorwks.dll, в течение которого выполняется код метаданных.</span><span class="sxs-lookup"><span data-stu-id="081e6-164">If `pValue` is VT_EMPTY, the version is set to a default value, which is drawn from the version of Mscorwks.dll within which the metadata code is running.</span></span> <span data-ttu-id="081e6-165">В противном случае — версия среды выполнения имеет значение в строку, которая хранится в разновидности типа BSTR.</span><span class="sxs-lookup"><span data-stu-id="081e6-165">Otherwise, the runtime version is set to the string that is held in the variant's BSTR type.</span></span>|  
|<span data-ttu-id="081e6-166">MetaDataMergerOptions</span><span class="sxs-lookup"><span data-stu-id="081e6-166">MetaDataMergerOptions</span></span>|<span data-ttu-id="081e6-167">Задает параметры для слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="081e6-167">Specifies options for merging metadata.</span></span>|<span data-ttu-id="081e6-168">Должен быть разновидностью UI4 и должен состоять из комбинации значений `MergeFlags` перечисления, который описан в файле CorHdr.h.</span><span class="sxs-lookup"><span data-stu-id="081e6-168">Must be a variant of type UI4, and must contain a combination of the values of the `MergeFlags` enumeration, which is described in the CorHdr.h file.</span></span>|  
|<span data-ttu-id="081e6-169">MetaDataPreserveLocalRefs</span><span class="sxs-lookup"><span data-stu-id="081e6-169">MetaDataPreserveLocalRefs</span></span>|<span data-ttu-id="081e6-170">Отключение оптимизации локальных ссылок в определения.</span><span class="sxs-lookup"><span data-stu-id="081e6-170">Disables optimizing local references into definitions.</span></span>|<span data-ttu-id="081e6-171">Должен состоять из комбинации значений [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="081e6-171">Must contain a combination of the values of the [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="081e6-172">Требования</span><span class="sxs-lookup"><span data-stu-id="081e6-172">Requirements</span></span>  
 <span data-ttu-id="081e6-173">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="081e6-173">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="081e6-174">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="081e6-174">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="081e6-175">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="081e6-175">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="081e6-176">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="081e6-176">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081e6-177">См. также</span><span class="sxs-lookup"><span data-stu-id="081e6-177">See Also</span></span>  
 [<span data-ttu-id="081e6-178">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="081e6-178">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="081e6-179">IMetaDataDispenser-интерфейс</span><span class="sxs-lookup"><span data-stu-id="081e6-179">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
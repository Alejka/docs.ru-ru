---
title: "Метод StrongNameGetPublicKeyEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameGetPublicKeyEx
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f39c5c948d43fd0e9387c1cc0319a46d25ec86ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="253c5-102">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="253c5-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="253c5-103">Возвращает открытый ключ из пары открытого и закрытого ключей и указывает хэш-алгоритм и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="253c5-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="253c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="253c5-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="253c5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="253c5-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="253c5-106">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="253c5-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="253c5-107">Если `pbKeyBlob` имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="253c5-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="253c5-108">В этом случае `StrongNameGetPublicKeyEx` метод извлекает открытый ключ из пары ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="253c5-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="253c5-109">Если `pbKeyBlob` не равно null, предполагается пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="253c5-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="253c5-110">Ключи должны быть 1024-разрядный Rivest шифрования RSA--Adleman () ключей подписывания.</span><span class="sxs-lookup"><span data-stu-id="253c5-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="253c5-111">Другие типы ключей не поддерживаются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="253c5-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="253c5-112">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="253c5-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="253c5-113">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="253c5-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="253c5-114">Если `pbKeyBlob` равен null, контейнер ключей, заданные `szKeyContainer` должна содержать пары ключей.</span><span class="sxs-lookup"><span data-stu-id="253c5-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="253c5-115">[in] Размер в байтах для `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="253c5-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="253c5-116">[out] Возвращаемый открытый ключ большого двоичного ОБЪЕКТА.</span><span class="sxs-lookup"><span data-stu-id="253c5-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="253c5-117">`ppbPublicKeyBlob` Параметра выделяется средой CLR и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="253c5-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="253c5-118">Вызывающий объект должен освободить память с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="253c5-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="253c5-119">[out] Размер возвращаемого BLOB-объект открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="253c5-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="253c5-120">[in] Хэш-алгоритм сборки.</span><span class="sxs-lookup"><span data-stu-id="253c5-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="253c5-121">Список допустимых значений см.</span><span class="sxs-lookup"><span data-stu-id="253c5-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="253c5-122">[in] Зарезервировано для будущего использования; значение по умолчанию null.</span><span class="sxs-lookup"><span data-stu-id="253c5-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="253c5-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="253c5-123">Return Value</span></span>  
 <span data-ttu-id="253c5-124">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="253c5-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="253c5-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="253c5-125">Remarks</span></span>  
 <span data-ttu-id="253c5-126">Открытый ключ содержится в [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="253c5-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="253c5-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="253c5-127">Remarks</span></span>  
 <span data-ttu-id="253c5-128">В следующей таблице показаны набор допустимых значений для `uHashAlgId` параметра.</span><span class="sxs-lookup"><span data-stu-id="253c5-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="253c5-129">Имя</span><span class="sxs-lookup"><span data-stu-id="253c5-129">Name</span></span>|<span data-ttu-id="253c5-130">Значение</span><span class="sxs-lookup"><span data-stu-id="253c5-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="253c5-131">Нет</span><span class="sxs-lookup"><span data-stu-id="253c5-131">None</span></span>|<span data-ttu-id="253c5-132">0</span><span class="sxs-lookup"><span data-stu-id="253c5-132">0</span></span>|  
|<span data-ttu-id="253c5-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="253c5-133">SHA-1</span></span>|<span data-ttu-id="253c5-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="253c5-134">0x8004</span></span>|  
|<span data-ttu-id="253c5-135">АЛГОРИТМ SHA-256</span><span class="sxs-lookup"><span data-stu-id="253c5-135">SHA-256</span></span>|<span data-ttu-id="253c5-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="253c5-136">0x800c</span></span>|  
|<span data-ttu-id="253c5-137">SHA-384.</span><span class="sxs-lookup"><span data-stu-id="253c5-137">SHA-384</span></span>|<span data-ttu-id="253c5-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="253c5-138">0x800d</span></span>|  
|<span data-ttu-id="253c5-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="253c5-139">SHA-512</span></span>|<span data-ttu-id="253c5-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="253c5-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="253c5-141">Требования</span><span class="sxs-lookup"><span data-stu-id="253c5-141">Requirements</span></span>  
 <span data-ttu-id="253c5-142">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="253c5-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="253c5-143">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="253c5-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="253c5-144">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="253c5-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="253c5-145">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="253c5-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="253c5-146">См. также</span><span class="sxs-lookup"><span data-stu-id="253c5-146">See Also</span></span>  
 [<span data-ttu-id="253c5-147">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="253c5-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="253c5-148">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="253c5-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="253c5-149">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="253c5-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="253c5-150">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="253c5-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
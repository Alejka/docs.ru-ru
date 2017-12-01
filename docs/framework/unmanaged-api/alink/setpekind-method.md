---
title: "Метод SetPEKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetPEKind
api_location: alink.dll
api_type: COM
f1_keywords: SetPEKind
helpviewer_keywords: SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d511bcda2ab4e879c123d866b3f6c887173c1d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="setpekind-method"></a><span data-ttu-id="a65d4-102">Метод SetPEKind</span><span class="sxs-lookup"><span data-stu-id="a65d4-102">SetPEKind Method</span></span>
<span data-ttu-id="a65d4-103">Определяет переносимый исполняемый тип, зависящий от компьютера или конкретного компьютера.</span><span class="sxs-lookup"><span data-stu-id="a65d4-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a65d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a65d4-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="a65d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a65d4-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a65d4-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="a65d4-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a65d4-107">Маркер файла, для которого требуется задать тип PE.</span><span class="sxs-lookup"><span data-stu-id="a65d4-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="a65d4-108">Может иметь значение NULL, если `AssemblyID` не указывает на несвязанный NETMODULE-файл.</span><span class="sxs-lookup"><span data-stu-id="a65d4-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="a65d4-109">Тип среды предустановки, как указано в [перечисление CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="a65d4-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="a65d4-110">Архитектуры конечного компьютера, как указано в заголовке NT.</span><span class="sxs-lookup"><span data-stu-id="a65d4-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a65d4-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a65d4-111">Return Value</span></span>  
 <span data-ttu-id="a65d4-112">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="a65d4-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a65d4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a65d4-113">Requirements</span></span>  
 <span data-ttu-id="a65d4-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="a65d4-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65d4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a65d4-115">See Also</span></span>  
 [<span data-ttu-id="a65d4-116">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="a65d4-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [<span data-ttu-id="a65d4-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="a65d4-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a65d4-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="a65d4-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a65d4-119">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="a65d4-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
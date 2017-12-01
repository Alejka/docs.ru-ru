---
title: "Метод ICorDebugThread::CreateEval"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateEval
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aebabf12e6dcf12f0e1e1f24ec2ad69ea55ec86c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="cf80c-102">Метод ICorDebugThread::CreateEval</span><span class="sxs-lookup"><span data-stu-id="cf80c-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="cf80c-103">Создает объект ICorDebugEval, который собирает и предоставляет функциональные возможности ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="cf80c-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf80c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf80c-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf80c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf80c-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="cf80c-106">[out] Указатель на адрес `ICorDebugEval` объект, который собирает и предоставляет функциональные возможности для данного потока.</span><span class="sxs-lookup"><span data-stu-id="cf80c-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf80c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf80c-107">Remarks</span></span>  
 <span data-ttu-id="cf80c-108">Объект выполнения будет передавать новую цепочку в потоке перед выполнением этого вычисления.</span><span class="sxs-lookup"><span data-stu-id="cf80c-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="cf80c-109">Это прервет вычисления, в данный момент выполняется в потоке до завершения оценки.</span><span class="sxs-lookup"><span data-stu-id="cf80c-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf80c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cf80c-110">Requirements</span></span>  
 <span data-ttu-id="cf80c-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf80c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf80c-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf80c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf80c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf80c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf80c-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf80c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
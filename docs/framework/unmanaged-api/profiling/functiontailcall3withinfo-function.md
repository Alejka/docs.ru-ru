---
title: "Функция FunctionTailcall3WithInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall3WithInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall3WithInfo
helpviewer_keywords: FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c22f00678f707df04a69104fedef87aa6d5e3d7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="6bdd8-102">Функция FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6bdd8-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="6bdd8-103">Уведомляет профилировщик, который должен выполнить вызов с префиксом tail в другую функцию текущей выполняемой функции и предоставляет маркер, который может быть передан [метод ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) для извлечения кадр стека.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bdd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bdd8-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bdd8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6bdd8-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="6bdd8-106">[in] Идентификатор текущей выполняемой функции, внесет с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="6bdd8-107">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="6bdd8-108">Этот дескриптор допустим только во время обратного вызова, в которую передается.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bdd8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6bdd8-109">Remarks</span></span>  
 <span data-ttu-id="6bdd8-110">`FunctionTailcall3WithInfo` Метод обратного вызова Уведомляет профилировщик, как функции вызываются, а также позволяет профилировщику использовать [метод ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) проверки кадра стека.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="6bdd8-111">Для доступа к сведениям кадра стека, `COR_PRF_ENABLE_FRAME_INFO` должно иметь значение флага.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="6bdd8-112">Можно использовать профилировщик [метод ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) установить флаги событий, а затем использовать [метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации вашего Реализация этой функции.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="6bdd8-113">`FunctionTailcall3WithInfo` Функция является обратным вызовом, необходимо произвести его.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="6bdd8-114">В реализации должен использоваться `__declspec(naked)` атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="6bdd8-115">Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="6bdd8-116">При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="6bdd8-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="6bdd8-117">При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="6bdd8-118">Реализация `FunctionTailcall3WithInfo` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="6bdd8-119">Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="6bdd8-120">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionTailcall3WithInfo` возвращает.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="6bdd8-121">Кроме того функция FunctionTailcall3WithInfo не должна вызывать управляемый код или вызвать распределения управляемой памяти каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bdd8-122">Требования</span><span class="sxs-lookup"><span data-stu-id="6bdd8-122">Requirements</span></span>  
 <span data-ttu-id="6bdd8-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bdd8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bdd8-124">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="6bdd8-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6bdd8-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bdd8-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bdd8-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bdd8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bdd8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6bdd8-127">See Also</span></span>  
 [<span data-ttu-id="6bdd8-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="6bdd8-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="6bdd8-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="6bdd8-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="6bdd8-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="6bdd8-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="6bdd8-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6bdd8-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="6bdd8-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6bdd8-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="6bdd8-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="6bdd8-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="6bdd8-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6bdd8-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="6bdd8-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="6bdd8-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="6bdd8-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="6bdd8-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="6bdd8-137">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="6bdd8-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
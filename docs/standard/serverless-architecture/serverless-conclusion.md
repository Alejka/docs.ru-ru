---
title: Главные выводы - Бессерверных приложений
description: Независимая предоставляет множество преимуществ и представляет свои сложности. Сводка главные выводы из этого руководства.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 055facf7ef46c18f8cda518da9a9f3e114dec1a2
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "49370086"
---
# <a name="conclusion"></a><span data-ttu-id="f1034-104">Заключение</span><span class="sxs-lookup"><span data-stu-id="f1034-104">Conclusion</span></span>

<span data-ttu-id="f1034-105">Следующие главные выводы являются наиболее важных выводов из этого руководства.</span><span class="sxs-lookup"><span data-stu-id="f1034-105">The following key takeaways are the most important conclusions from this guide.</span></span>

<span data-ttu-id="f1034-106">**Преимущества использования без сервера.**</span><span class="sxs-lookup"><span data-stu-id="f1034-106">**Benefits of using serverless.**</span></span> <span data-ttu-id="f1034-107">Бессерверные решения предоставляют важные преимущества экономии, так как без сервера реализуется в модели оплаты по мере использования.</span><span class="sxs-lookup"><span data-stu-id="f1034-107">Serverless solutions provide the important benefit of cost savings because serverless is implemented in a pay-per-use model.</span></span> <span data-ttu-id="f1034-108">Без использования сервера позволяет независимо масштабировать, тестировать и развертывать отдельные компоненты приложения.</span><span class="sxs-lookup"><span data-stu-id="f1034-108">Serverless makes it possible to independently scale, test, and deploy individual components of your application.</span></span> <span data-ttu-id="f1034-109">Без использования сервера наилучшим образом подходят для реализации архитектуры микрослужб и полностью интегрируется в конвейер DevOps.</span><span class="sxs-lookup"><span data-stu-id="f1034-109">Serverless is uniquely suited to implement microservices architectures and integrates fully into a DevOps pipeline.</span></span>

<span data-ttu-id="f1034-110">**Код как единица развертывания.**</span><span class="sxs-lookup"><span data-stu-id="f1034-110">**Code as a unit of deployment.**</span></span> <span data-ttu-id="f1034-111">Независимая абстрагирует оборудованию, операционной системы и среды выполнения, работу с приложением.</span><span class="sxs-lookup"><span data-stu-id="f1034-111">Serverless abstracts the hardware, OS, and runtime away from the application.</span></span> <span data-ttu-id="f1034-112">Без использования сервера позволяет сосредоточиться на бизнес-логику в коде как единицей развертывания.</span><span class="sxs-lookup"><span data-stu-id="f1034-112">Serverless enables focusing on business logic in code as the unit of deployment.</span></span>

<span data-ttu-id="f1034-113">**Триггеры и привязки.**</span><span class="sxs-lookup"><span data-stu-id="f1034-113">**Triggers and bindings.**</span></span> <span data-ttu-id="f1034-114">Независимая облегчает интеграцию с хранилищем, API-интерфейсы и другие облачные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="f1034-114">Serverless eases integration with storage, APIs, and other cloud resources.</span></span> <span data-ttu-id="f1034-115">Функции Azure предоставляют триггеры для выполнения кода и привязки для взаимодействия с ресурсами.</span><span class="sxs-lookup"><span data-stu-id="f1034-115">Azure Functions provides triggers to execute code and bindings to interact with resources.</span></span>

<span data-ttu-id="f1034-116">**Микрослужбы.**</span><span class="sxs-lookup"><span data-stu-id="f1034-116">**Microservices.**</span></span> <span data-ttu-id="f1034-117">Архитектура микрослужб становится предпочтительным подходом для распределенных и крупных или сложных критически важных приложений, основанных на нескольких независимых подсистемах в виде автономных служб.</span><span class="sxs-lookup"><span data-stu-id="f1034-117">The microservices architecture is becoming the preferred approach for distributed and large or complex mission-critical applications that are based on multiple independent subsystems in the form of autonomous services.</span></span> <span data-ttu-id="f1034-118">В архитектуре на базе микрослужб приложения на базе коллекции служб, которые можно разрабатывать, тестировать, обновлять, развертывать и масштабировать независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="f1034-118">In a microservice-based architecture, the application is built as a collection of services that can be developed, tested, versioned, deployed, and scaled independently.</span></span> <span data-ttu-id="f1034-119">Без сервера — это архитектура, хорошо подходит для создания этих служб.</span><span class="sxs-lookup"><span data-stu-id="f1034-119">Serverless is an architecture well-suited for building these services.</span></span>

<span data-ttu-id="f1034-120">**Бессерверные платформы.**</span><span class="sxs-lookup"><span data-stu-id="f1034-120">**Serverless platforms.**</span></span> <span data-ttu-id="f1034-121">Без сервера не ограничивается только кодом.</span><span class="sxs-lookup"><span data-stu-id="f1034-121">Serverless isn't just about the code.</span></span> <span data-ttu-id="f1034-122">Платформы, которые поддерживают бессерверной архитектуры включают бессерверные рабочие процессы и оркестрации бессерверных обмена сообщениями и событий и службы без сервера баз данных.</span><span class="sxs-lookup"><span data-stu-id="f1034-122">Platforms that support serverless architectures include serverless workflows and orchestration, serverless messaging and event services, and serverless databases.</span></span>

<span data-ttu-id="f1034-123">**Проблем.**</span><span class="sxs-lookup"><span data-stu-id="f1034-123">**Serverless challenges.**</span></span> <span data-ttu-id="f1034-124">Независимая представлены проблемы, связанные с разработки распределенных приложений, таких как фрагментированный и независимыми моделями данных, устойчивость, управление версиями и службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f1034-124">Serverless introduces challenges related to distributed application development, such as fragmented and independent data models, resiliency, versioning, and service discovery.</span></span> <span data-ttu-id="f1034-125">Без использования сервера может не подходить в идеале для долго выполняющихся процессов или компоненты, которые выигрывают от более тесную связь.</span><span class="sxs-lookup"><span data-stu-id="f1034-125">Serverless may not be ideally suited to long running processes or components that benefit from tighter coupling.</span></span>

<span data-ttu-id="f1034-126">**Без сервера, как средство, а не на панели элементов.**</span><span class="sxs-lookup"><span data-stu-id="f1034-126">**Serverless as a tool, not the toolbox.**</span></span> <span data-ttu-id="f1034-127">Без сервера не эксклюзивные решение для архитектуры приложения.</span><span class="sxs-lookup"><span data-stu-id="f1034-127">Serverless is not the exclusive solution to application architecture.</span></span> <span data-ttu-id="f1034-128">Это средство, которое можно использовать как часть гибридного приложения, которое может содержать традиционных уровней, серверные части монолитного приложения и контейнеры.</span><span class="sxs-lookup"><span data-stu-id="f1034-128">It is a tool that can be leveraged as part of a hybrid application that may contain traditional tiers, monolith back ends, and containers.</span></span> <span data-ttu-id="f1034-129">Независимая позволяют улучшить существующие решения и не отдельных подход к разработке приложений.</span><span class="sxs-lookup"><span data-stu-id="f1034-129">Serverless can be used to enhance existing solutions and is not an all-or-nothing approach to application development.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="f1034-130">Назад</span><span class="sxs-lookup"><span data-stu-id="f1034-130">Previous</span></span>](serverless-business-scenarios.md)
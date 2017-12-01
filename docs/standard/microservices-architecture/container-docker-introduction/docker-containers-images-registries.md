---
title: "Контейнеры docker, изображения и реестров"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Контейнеры docker, изображения и реестров"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 224fed34f06d10760b14aa9ecbae6c0e912915cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="0a77a-104">Контейнеры docker, изображения и реестров</span><span class="sxs-lookup"><span data-stu-id="0a77a-104">Docker containers, images, and registries</span></span>

<span data-ttu-id="0a77a-105">При использовании Docker, разработчик создает приложение или служба и пакеты его и его зависимости в образ контейнера.</span><span class="sxs-lookup"><span data-stu-id="0a77a-105">When using Docker, a developer creates an app or service and packages it and its dependencies into a container image.</span></span> <span data-ttu-id="0a77a-106">Образ — это статическое представление приложения или службы и его конфигурации и зависимостей.</span><span class="sxs-lookup"><span data-stu-id="0a77a-106">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="0a77a-107">Для выполнения приложения или службы, чтобы создать контейнер, в котором будут выполняться на узле Docker создается образ приложения.</span><span class="sxs-lookup"><span data-stu-id="0a77a-107">To run the app or service, the app’s image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="0a77a-108">Контейнеров, изначально проверены в среде разработки или ПК.</span><span class="sxs-lookup"><span data-stu-id="0a77a-108">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="0a77a-109">Разработчикам следует хранить изображения в реестре, который выступает в качестве библиотеки изображений и требуются при развертывании в рабочей среде orchestrators.</span><span class="sxs-lookup"><span data-stu-id="0a77a-109">Developers should store images in a registry, which acts as a library of images and is needed when deploying to production orchestrators.</span></span> <span data-ttu-id="0a77a-110">Docker обслуживает открытого реестра через [Docker Hub](https://hub.docker.com/); другие поставщики предлагают реестров для различных коллекций изображений.</span><span class="sxs-lookup"><span data-stu-id="0a77a-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="0a77a-111">Кроме того, предприятия могут иметь частного реестра локальными для своих собственных образов Docker.</span><span class="sxs-lookup"><span data-stu-id="0a77a-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="0a77a-112">На рисунке 2 – 4 показано, как изображения и реестров в Docker связаны с другими компонентами.</span><span class="sxs-lookup"><span data-stu-id="0a77a-112">Figure 2-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="0a77a-113">Он также содержит несколько предложений реестра от поставщиков.</span><span class="sxs-lookup"><span data-stu-id="0a77a-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image5.PNG)

<span data-ttu-id="0a77a-114">**На рисунке 2 – 4**.</span><span class="sxs-lookup"><span data-stu-id="0a77a-114">**Figure 2-4**.</span></span> <span data-ttu-id="0a77a-115">Классификация Docker термины и основные понятия</span><span class="sxs-lookup"><span data-stu-id="0a77a-115">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="0a77a-116">Размещение изображений в реестре позволяет хранить разряды статические и неизменяемый приложения, включая все их зависимости на уровне framework.</span><span class="sxs-lookup"><span data-stu-id="0a77a-116">Putting images in a registry lets you store static and immutable application bits, including all their dependencies at a framework level.</span></span> <span data-ttu-id="0a77a-117">Эти образы можно затем числовые версии и развертываются в нескольких средах и таким образом предоставляют единицу развертывания.</span><span class="sxs-lookup"><span data-stu-id="0a77a-117">Those images can then be versioned and deployed in multiple environments and therefore provide a consistent deployment unit.</span></span>

<span data-ttu-id="0a77a-118">Реестры частный образ либо размещенной в локальной или в облаке, рекомендуется использовать при:</span><span class="sxs-lookup"><span data-stu-id="0a77a-118">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

-   <span data-ttu-id="0a77a-119">Изображения не должен быть общим открыто из-за конфиденциальность.</span><span class="sxs-lookup"><span data-stu-id="0a77a-119">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="0a77a-120">Требуется минимальная сетевая задержка между образов и среды выбранного развертывания.</span><span class="sxs-lookup"><span data-stu-id="0a77a-120">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="0a77a-121">Например если облако Azure рабочей среды, может потребоваться хранения рисунков в реестре контейнера Azure, чтобы сетевая задержка будет минимальной.</span><span class="sxs-lookup"><span data-stu-id="0a77a-121">For example, if your production environment is Azure cloud, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="0a77a-122">Аналогичным образом Если в локальной рабочей среды может потребоваться иметь локальные доверенный реестр Docker в той же локальной сети.</span><span class="sxs-lookup"><span data-stu-id="0a77a-122">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="0a77a-123">[Предыдущие] docker (terminology.md) [Далее] (.. /NET-Core-NET-Framework-Containers/index.MD)</span><span class="sxs-lookup"><span data-stu-id="0a77a-123">[Previous] (docker-terminology.md) [Next] (../net-core-net-framework-containers/index.md)</span></span>
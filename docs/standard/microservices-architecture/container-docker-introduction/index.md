---
title: Общие сведения о контейнерах и Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Общие сведения о контейнерах и Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 08/31/2018
ms.openlocfilehash: bc99bbfc3adee4cdc7008a91f42659ebcaa7a1b1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45658435"
---
# <a name="introduction-to-containers-and-docker"></a>Общие сведения о контейнерах и Docker

Контейнеризация — это подход к разработке программного обеспечения, при котором приложение или служба, их зависимости и конфигурация (абстрактные файлы манифеста развертывания) упаковываются вместе в образ контейнера. Контейнерное приложение может тестироваться как единое целое и развертываться как экземпляр образа контейнера в операционной системе (ОС) узла.

Так же как обычные контейнеры позволяют перевозить любые грузы на корабле, поезде или грузовике, программные контейнеры выступают в качестве стандартных модулей для развертывания программного обеспечения, которые могут содержать различный код и зависимости. Контейнеризация программного обеспечения позволяет разработчикам и ИТ-специалистам развертывать его в разных средах без каких-либо изменений или с минимальными изменениями.

Контейнеры также изолируют приложения друг от друга в общей операционной системе. Контейнерные приложения выполняются на основе узла контейнеров, который в свою очередь работает в операционной системе (Linux или Windows). Поэтому контейнеры требуют гораздо меньше ресурсов, чем образы виртуальных машин.

Каждый контейнер может вмещать целое веб-приложение или службу, как показано на рис. 2-1. В этом примере узел Docker — это узел контейнеров, а App1, App2, Svc 1 и Svc 2 — контейнерные приложения или службы.

![Два приложения и две службы, работающие в операционной системе на виртуальной машине или физическом сервере](./media/image1.png)

**Рис. 2-1**. Несколько контейнеров на одном узле

Еще одним преимуществом контейнеризации является масштабируемость. Вы можете быстро осуществлять горизонтальное масштабирование, создавая контейнеры для краткосрочных задач. С точки зрения приложения, создание экземпляра образа (контейнера) аналогично созданию экземпляра процесса, например для службы или веб-приложения. Но для обеспечения надежности при запуске нескольких экземпляров одного образа на нескольких серверах обычно желательно, чтобы контейнеры (экземпляры образа) выполнялись на разных серверах или виртуальных машинах в разных доменах сбоя.

Иными словами, контейнеры предоставляют такие преимущества, как изоляция, переносимость, гибкость, масштабируемость и контроль, на протяжении всего жизненного цикла приложения. Самым важным преимуществом является изоляция среды разработки от рабочей среды.


>[!div class="step-by-step"]
[Назад](../index.md)
[Вперед](docker-defined.md)

---
title: События безопасности (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e02274b63ddf7df42d26621791de0286df9655b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395516"
---
# <a name="security-etw-events"></a>События безопасности (трассировка событий Windows)
<a name="top"></a> События безопасности создаются при проверке строгого имени и проверке Authenticode.  
  
 Эта категория состоит из следующих событий:  
  
-   [События StrongNameVerificationStart_V1 и StrongNameVerificationStop_V1](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [События AuthenticodeVerificationStart_V1 и AuthenticodeVerificationStop_V1](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a>События StrongNameVerificationStart_V1 и StrongNameVerificationStop_V1  
 В таблице ниже показаны ключевое слово и уровень. (Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|Информационный (4)|  
  
 В таблице ниже представлены сведения о событии.  
  
|Событие|Идентификатор события|Условие вызова|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|Начало проверки строгого имени.|  
|`StrongNameVerificationStop_V1`|182|Окончание проверки строгого имени.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Флаги проверки.|  
|ErrorCode|win:UInt32|Код ошибки HResult.|  
|FullyQualifiedAssemblyName|win:UnicodeString|Полное имя сборки.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
 [К началу](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a>События AuthenticodeVerificationStart_V1 и AuthenticodeVerificationStop_V1  
 В таблице ниже показаны ключевое слово и уровень.  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|Информационный (4)|  
  
 В таблице ниже представлены сведения о событии.  
  
|Событие|Идентификатор события|Условие вызова|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|Начало проверки Authenticode.|  
|`AuthenticodeVerificationStop_V1`|184|Окончание проверки Authenticode.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Флаги проверки.|  
|ErrorCode|win:UInt32|Код ошибки HResult.|  
|ModulePath|win:UnicodeString|Путь к модулю.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
## <a name="see-also"></a>См. также  
 [События трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-events.md)

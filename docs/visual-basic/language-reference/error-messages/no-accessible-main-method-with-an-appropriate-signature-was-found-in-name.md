---
title: Ни один из доступных &#39;Main&#39; найден метод с соответствующей сигнатурой в &#39; &lt;имя&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6a60e26a2bd0e31c0f92dbbfb2518c75f304d9f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593224"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>Ни один из доступных &#39;Main&#39; найден метод с соответствующей сигнатурой в &#39; &lt;имя&gt;&#39;
Приложения командной строки должны иметь `Sub Main` определен. `Main` должен быть объявлен как `Public Shared` , если оно определено в классе или как `Public` , если определено в модуле.  
  
 **Идентификатор ошибки:** BC30737  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Определение `Public Sub Main` процедуры для вашего проекта. Он объявляется как `Shared` только в том случае, если она определяется внутри класса.  
  
## <a name="see-also"></a>См. также  
 [Структура программы Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)

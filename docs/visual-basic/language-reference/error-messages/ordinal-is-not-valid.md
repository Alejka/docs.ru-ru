---
title: Недопустимый порядковый номер
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 12d73b33e3c025b40c98d84e3507af7be1e1e91a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593607"
---
# <a name="ordinal-is-not-valid"></a>Недопустимый порядковый номер
При вызове в библиотеке динамической компоновки (DLL) использовался использовать номер, а не имя процедуры, с помощью `#num` синтаксиса. Эта ошибка имеет следующие возможные причины:  
  
-   Попытка преобразовать `#num` выражение в порядковый.  
  
-   `#num` Указанного не соответствует ни одной функции в DLL.  
  
-   Библиотека типов имеет недопустимое объявление причиной внутреннего использования недопустимого порядкового номера.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что выражение представляет допустимый номер или вызовите процедуру по имени.  
  
2.  Убедитесь, что `#num` определяет допустимую функцию в DLL.  
  
3.  Изолируйте вызов процедуры, вызывающей ошибку код комментарием. Запись `Declare` инструкции для процедуры и сообщите об ошибке разработчику библиотеки типов.  
  
## <a name="see-also"></a>См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

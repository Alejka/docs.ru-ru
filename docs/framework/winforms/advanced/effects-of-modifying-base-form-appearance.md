---
title: Влияние изменения внешнего вида базовой формы
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: adaf9224fd340c6ea4342e2591806a7c877e83ff
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084413"
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a>Влияние изменения внешнего вида базовой формы
В процессе разработки приложения часто может потребоваться изменить внешний вид базовой формы, от которой наследуются другие формы проекта (или других проектов).  
  
 Во время разработки изменения внешнего вида базовой формы (будь то значения свойств либо добавление и удаление элементов управления) отражаются на наследуемых формах при построении проекта, содержащего базовую форму. Просто сохранить изменения в базовой форме будет недостаточно. Для сборки проекта выберите в меню **Сборка** пункт **Собрать**.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
 Изменения, внесенные в базовую форму во время выполнения, не влияют на наследуемые формы, экземпляры которых уже созданы.  
  
## <a name="see-also"></a>См. также  
 [base](~/docs/csharp/language-reference/keywords/base.md)  
 [Практическое руководство. Наследование форм Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [Визуальное наследование в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)

---
title: Практическое руководство. Привязка элемента ListBox к данным
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 186d25750c5ce196a5e46c02f0f56e2440ea3a25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552835"
---
# <a name="how-to-bind-a-listbox-to-data"></a>Практическое руководство. Привязка элемента ListBox к данным
Разработчик приложения можно создать <xref:System.Windows.Controls.ListBox> элементов управления без указания содержимого каждого <xref:System.Windows.Controls.ListBoxItem> отдельно. Привязка данных можно использовать для привязки данных к отдельным элементам.  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.ListBox> , заполняющий <xref:System.Windows.Controls.ListBoxItem> элементов с помощью привязки данных в источник данных с именем *цветов*. В этом случае необязательно использовать <xref:System.Windows.Controls.ListBoxItem> теги для указания содержимого каждого элемента.  
  
## <a name="example"></a>Пример  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)

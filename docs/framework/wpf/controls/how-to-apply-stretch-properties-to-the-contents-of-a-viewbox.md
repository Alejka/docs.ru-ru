---
title: Практическое руководство. Применение свойства Stretch к содержимому элемента Viewbox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: 3e81ec9fd045bb3fcf359943e455d2cce94aec55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552809"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a>Практическое руководство. Применение свойства Stretch к содержимому элемента Viewbox
## <a name="example"></a>Пример  
 В этом примере показано, как изменить значение <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> и <xref:System.Windows.Controls.Viewbox.Stretch%2A> свойства <xref:System.Windows.Controls.Viewbox>.  
  
 В первом примере используется [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения <xref:System.Windows.Controls.Viewbox> элемента. Он назначает <xref:System.Windows.FrameworkElement.MaxWidth%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A> 400. В примере операторы <xref:System.Windows.Controls.Image> элемент в пределах <xref:System.Windows.Controls.Viewbox>. <xref:System.Windows.Controls.Button> элементы, которые соответствуют значениям свойств для <xref:System.Windows.Controls.Viewbox.Stretch%2A> и <xref:System.Windows.Controls.StretchDirection> перечисления управляют растяжением вложенного <xref:System.Windows.Controls.Image>.  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 Дескрипторы файлов, в следующем кода <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события, предыдущий [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] примере определяется.  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Viewbox>  
 <xref:System.Windows.Media.Stretch>  
 <xref:System.Windows.Controls.StretchDirection>

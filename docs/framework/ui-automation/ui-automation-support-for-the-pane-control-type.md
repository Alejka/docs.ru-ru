---
title: "UI Automation Support for the Pane Control Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI Automation, Pane control type"
  - "Pane control type"
  - "control types, Pane"
ms.assetid: 79761191-4449-4630-899c-9cbdb8867d3f
caps.latest.revision: 25
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 25
---
# UI Automation Support for the Pane Control Type
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления Pane. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>. Эти условия включают определенные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], шаблонов элементов управления и значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 Тип элемента управления Pane используется для представления объекта в рамке или в окне документа. Пользователи могут выполнять навигацию по элементам управления "Панель" и по содержимому текущей панели, но не могут переходить между элементами в разных панелях. Таким образом, элемент управления "Панель" представляют уровень группирования ниже, чем окна или документы, но выше, чем отдельные элементы управления. Пользователь переходит между панелями, нажимая клавишу TAB, F6 или CTRL\+TAB, в зависимости от контекста. Типу элемента управления Pane не требуется специальная навигация с помощью клавиатуры.  
  
 В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], свойства, шаблоны элементов управления и события для типа элемента управления Pane. Требования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "Список", будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] или [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], относящиеся к элементам управления "Панель", и показывается, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление содержимого|  
|---------------------------------------|-------------------------------|  
|Панель|Панель|  
  
<a name="Required_UI_Automation_Properties"></a>   
## Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], значения или определения которых особенно актуальны для элементов управления "Панель". Дополнительные сведения о свойствах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|Свойство [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|Значение|Примечания|  
|-------------------------------------------------------------------------------------|--------------|----------------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Значение этого свойства всегда должно быть четким, кратким и понятным заголовком.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Это свойство предоставляет активную точку элемента управления "Панель", при щелчке в которой эта панель получает фокус.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|См. примечания.|Элементы управления "Панель" обычно не имеют статических меток. Если метка со статическим текстом присутствует, она должна предоставляться через это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Панель|Это значение является одинаковым для всех инфраструктур [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"панель"|Локализованная строка, соответствующая типу элемента управления Pane.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Элементы управления "Панель" всегда включаются в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Элементы управления "Панель" всегда включаются в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|""|Текст справки для элементов управления "Панель" должен объяснять назначение этой рамки и ее связь с другими рамками. Описание необходимо, если назначение и взаимосвязь рамок не ясны из значения свойства `NameProperty`. "|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>|См. примечания.|Если определенное сочетание клавиш переводит фокус в конкретную панель, сведения об этом должны предоставляться через данное свойство.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], которые должны поддерживаться всеми элементами управления "Панель". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|--------------------------------|---------------|----------------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider>|Зависит от обстоятельств|Реализуйте этот шаблон элемента управления, если элемент управления "Панель" можно перемещать, изменять его размер или поворачивать на экране.|  
|<xref:System.Windows.Automation.Provider.IWindowProvider>|Никогда|Если необходимо реализовать этот шаблон элемента управления, элемент управления должен быть основан на типе <xref:System.Windows.Automation.ControlType.Window>.|  
|<xref:System.Windows.Automation.Provider.IDockProvider>|Зависит от обстоятельств|Реализуйте этот шаблон элемента управления, если панель управления можно закреплять.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Зависит от обстоятельств|Реализуйте этот шаблон элемента управления, если панель управления можно прокручивать.|  
  
<a name="Required_UI_Automation_Events"></a>   
## Необходимые события модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], которые должны поддерживаться всеми элементами управления "Панель". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|Событие [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка\/значение|Примечания|  
|-----------------------------------------------------------------------------------|-------------------------|----------------|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent>|Никогда|Нет|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent>|Никогда|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AsyncContentLoadedEvent>|Обязательный|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательно|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательно|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательно|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty>|Зависит от обстоятельств|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty>|Зависит от обстоятельств|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty>|Зависит от обстоятельств|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty>|Зависит от обстоятельств|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty>|Зависит от обстоятельств|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty>|Зависит от обстоятельств|Нет|  
|Событие изменения свойства <xref:System.Windows.Automation.WindowPatternIdentifiers.WindowVisualStateProperty>|Никогда|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательный|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательный|Нет|  
  
<a name="Pane_Control_Type_Example"></a>   
## Пример типа элемента управления Pane  
 На следующем рисунке показан элемент управления, реализующий тип элемента управления Pane.  
  
 ![Снимок экрана окна апплета с двумя панелями](../../../docs/framework/ui-automation/media/uiauto-pane.png "uiauto\_pane")  
  
|Дерево [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — представление элемента управления|Дерево [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — представление содержимого|  
|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|  
|<ul><li>Панель</li><li>Tree \(шаблон Scroll\)<br /><br /> <ul><li>TreeItem</li><li>Панель</li><li>Edit \(шаблон Scroll\)</li></ul></li></ul>|-   Панель<br />-   Tree \(шаблон Scroll\)<br />-   TreeItem<br />-   …Pane<br />-   Правка<br />-   \(шаблон Scroll\)|  
  
## См. также  
 <xref:System.Windows.Automation.ControlType.Pane>   
 [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)   
 [UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-overview.md)
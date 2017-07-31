---
title: "Практическое руководство. Создание и инициализация источников трассировки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "источники трассировки"
  - "инициализация источников трассировки"
  - "файлы конфигурации [платформа .NET Framework], источники трассировки"
ms.assetid: f88dda6f-5fda-45be-9b3c-745a9b708c4d
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Создание и инициализация источников трассировки
Класс <xref:System.Diagnostics.TraceSource> используется приложениями для создания трассировок, которые могут быть связаны с приложением.  <xref:System.Diagnostics.TraceSource> предоставляет методы трассировки, позволяющие легко трассировать события, трассировать данные и выпускать информационные трассировки.  Выходные данные трассировки из объектов <xref:System.Diagnostics.TraceSource> можно создавать и инициализировать с использованием или без использования файлов конфигурации.  В этом разделе содержатся инструкции для обоих вариантов.  Однако рекомендуется использовать файлы конфигурации для упрощения повторной настройки трассировки, создаваемой источниками трассировки во время выполнения.  
  
### Создание и инициализация источника трассировки с помощью файла конфигурации  
  
1.  Создайте проект консольного приложения Visual Studio и замените предоставленный код следующим кодом.  Этот код регистрирует ошибки и предупреждения, выводит некоторые из них на консоль, а некоторые в файл myListener, созданный записями в файле конфигурации.  
  
     [!code-csharp[TraceSourceExample1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample1/cs/program.cs#1)]
     [!code-vb[TraceSourceExample1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample1/vb/program.vb#1)]  
  
2.  Добавьте в проект файл конфигурации приложения \(если его еще нет\), чтобы инициализировать источник трассировки с именем `TraceSourceApp` в примере кода из шага 1.  
  
3.  Замените содержимое файла конфигурации по умолчанию приведенными ниже параметрами, чтобы инициализировать прослушиватель трассировки с выводом данных на консоль и прослушиватель трассировки с записью в текстовый файл для источника трассировки, созданного на шаге 1.  
  
    ```  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"   
            switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"   
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"   
                  initializeData="Error"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Error"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"   
            type="System.Diagnostics.TextWriterTraceListener"   
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
     Помимо настройки прослушивателей трассировки, файл конфигурации также создает фильтры для обоих типов прослушивателей и создает переключатель источника для источника трассировки.  Демонстрируются два приема для добавления прослушивателей трассировки: добавление прослушивателя непосредственно в источник трассировки, и добавление прослушивателя к общей коллекции прослушивателей, а затем добавление его по имени в источник трассировки.  Фильтры, определенные для этих двух прослушивателей, инициализируются с различными уровнями источника.  Это приводит к тому, что некоторые сообщения записываются только одним из двух прослушивателей.  
  
     Файл конфигурации инициализирует настройки для источника трассировки во время инициализации приложения.  Приложение может динамически изменить набор свойств с помощью файла конфигурации, чтобы переопределить любые настройки, заданные пользователем.  Например, может потребоваться, чтобы важные сообщения всегда отправлялись в текстовый файл, независимо от текущих настроек конфигурации.  В примере кода показано, как переопределить параметры файла конфигурации таким образом, чтобы обеспечить вывод важных сообщений в прослушиватели трассировки.  
  
     При изменении настроек файла конфигурации во время работы приложения начальные настройки не изменяются.  Чтобы изменить эти параметры, необходимо либо перезапустить приложение, либо обновить приложение программными средствами с помощью метода <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=fullName>.  
  
### Инициализация источников трассировки, прослушивателей и фильтров без файла конфигурации  
  
-   Используйте следующий пример кода, чтобы разрешить трассировку через источник трассировки с помощью файла конфигурации.  Как правило, использование этого приема не рекомендовано, однако в некоторых обстоятельствах требуется инициализация трассировки независимо от файла конфигурации.  
  
     [!code-csharp[TraceSourceExample2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample2/cs/program.cs#1)]
     [!code-vb[TraceSourceExample2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample2/vb/program.vb#1)]  
  
## См. также  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.EventTypeFilter>   
 [Tracing and Instrumenting Applications](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
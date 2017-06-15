---
title: "DbConnection, DbCommand и DbException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 58aab611-7e6f-4749-b983-28ab7ae87dbe
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DbConnection, DbCommand и DbException
После создания <xref:System.Data.Common.DbProviderFactory> и <xref:System.Data.Common.DbConnection> можно будет пользоваться командами и модулями чтения данных, чтобы получать данные из источника данных.  
  
## Пример извлечения данных  
 В этом примере в качестве аргумента указывается объект `DbConnection`.  Объект <xref:System.Data.Common.DbCommand> создается для выбора данных из таблицы Categories путем задания <xref:System.Data.Common.DbCommand.CommandText%2A> инструкции SQL SELECT.  Предполагается, что в источнике данных существует таблица Categories.  Открывается соединение, и данные получаются при помощи объекта <xref:System.Data.Common.DbDataReader>.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/VB/source.vb#1)]  
  
## Пример выполнения команды  
 В этом примере в качестве аргумента указывается объект `DbConnection`.  Если объект `DbConnection` является допустимым, то открывается соединение, создается и выполняется команда <xref:System.Data.Common.DbCommand>.  <xref:System.Data.Common.DbCommand.CommandText%2A> задается инструкции SQL INSERT, которая выполняет вставку в таблицу Categories в базе данных Northwind.  Предполагается, что база данных Northwind существует в источнике данных, а также что используемый в инструкции INSERT синтаксис SQL является допустимым для указанного поставщика.  Ошибки в источнике данных обрабатываются блоком кода <xref:System.Data.Common.DbException>, а все остальные исключения \- в блоке <xref:System.Exception>.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/VB/source.vb#1)]  
  
## Обработка ошибок данных при помощи DbException  
 Класс <xref:System.Data.Common.DbException> является базовым классом для всех исключений, формируемых от имени источника данных.  В коде обработки исключений его можно использовать для обработки исключений, формируемых разными поставщиками, при этом нет необходимости ссылаться на определенный класс исключений.  Следующий фрагмент кода демонстрирует, как использовать класс <xref:System.Data.Common.DbException> для отображения сведений об ошибке, возвращаемых источником данных, при помощи свойств <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A> и <xref:System.Exception.Message%2A>.  В выходных сведениях приводится тип ошибки, источник, указывающий имя поставщика, код ошибки и связанное с ошибкой сообщение.  
  
```vb  
Try  
    ' Do work here.  
Catch ex As DbException  
    ' Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType())  
    Console.WriteLine("Source: {0}", ex.Source)  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode)  
    Console.WriteLine("Message: {0}", ex.Message)  
Finally  
    ' Perform cleanup here.  
End Try  
```  
  
```csharp  
try  
{  
    // Do work here.  
}  
catch (DbException ex)  
{  
    // Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType());  
    Console.WriteLine("Source: {0}", ex.Source);  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode);  
    Console.WriteLine("Message: {0}", ex.Message);  
}  
finally  
{  
    // Perform cleanup here.  
}  
```  
  
## См. также  
 [Объекты DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)   
 [Получение DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)   
 [Изменение данных с помощью DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)
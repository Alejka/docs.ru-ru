---
title: "Пошаговое руководство. Создание типов F# из файла схемы DBML (F#)"
description: "Узнайте, как создание типов F # для данных из базы данных в F # 3.0 при наличии сведений о схеме, закодированные в DBML-файла."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: 50e0a2bb6378c82b5c6425589da8a982b5fc496a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a><span data-ttu-id="6f1f4-104">Пошаговое руководство. Создание типов F# из файла схемы DBML</span><span class="sxs-lookup"><span data-stu-id="6f1f4-104">Walkthrough: Generating F# Types from a DBML File</span></span>

> [!NOTE]
<span data-ttu-id="6f1f4-105">В этом руководстве, была написана для F # 3.0 и будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="6f1f4-106">Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](http://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="6f1f4-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="6f1f4-107">Справочные ссылки API, вы перейдете MSDN.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="6f1f4-108">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="6f1f4-109">В этом пошаговом руководстве для F # 3.0 описывается создание типов для данных из базы данных, при наличии сведений о схеме, закодированные в DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-109">This walkthrough for F# 3.0 describes how to create types for data from a database when you have schema information encoded in a .dbml file.</span></span> <span data-ttu-id="6f1f4-110">LINQ to SQL используется этот формат для представления схемы базы данных.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-110">LINQ to SQL uses this file format to represent database schema.</span></span> <span data-ttu-id="6f1f4-111">LINQ to SQL-файл схемы в Visual Studio можно создать с помощью конструктора реляционных объектов (O/R).</span><span class="sxs-lookup"><span data-stu-id="6f1f4-111">You can generate a LINQ to SQL schema file in Visual Studio by using the Object Relational (O/R) Designer.</span></span> <span data-ttu-id="6f1f4-112">Дополнительные сведения см. в разделе [Общие сведения о конструкторе O/R](https://msdn.microsoft.com/library/bb384511.aspx) и [создание кода в LINQ to SQL](https://msdn.microsoft.com/library/bb386976).</span><span class="sxs-lookup"><span data-stu-id="6f1f4-112">For more information, see [O/R Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) and [Code Generation in LINQ to SQL](https://msdn.microsoft.com/library/bb386976).</span></span>

<span data-ttu-id="6f1f4-113">Поставщик типов языка разметки баз данных (DBML) можно написать код, который использует типы в зависимости от схемы базы данных без необходимости указания статической строки соединения во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-113">The Database Markup Language (DBML) type provider allows you to write code that uses types based on a database schema without requiring you to specify a static connection string at compile time.</span></span> <span data-ttu-id="6f1f4-114">Который может быть полезным, если требуется возможность того, что конечного приложения будет использовать другую базу данных, другие учетные данные или другую строку соединения чем тот, который используется для разработки приложения.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-114">That can be useful if you need to allow for the possibility that the final application will use a different database, different credentials, or a different connection string than the one you use to develop the application.</span></span> <span data-ttu-id="6f1f4-115">При наличии подключения прямых базы данных, можно использовать во время компиляции, и это же базы данных и учетные данные, которые будут занимать построения приложения, также можно использовать поставщика типов SQLDataConnection.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-115">If you have a direct database connection that you can use at compile time and this is the same database and credentials that you will eventually use in your built application, you can also use the SQLDataConnection type provider.</span></span> <span data-ttu-id="6f1f4-116">Дополнительные сведения см. в разделе [Пошаговое руководство: доступ к базе данных SQL с помощью поставщиков типов](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="6f1f4-116">For more information, see [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>

<span data-ttu-id="6f1f4-117">В данном пошаговом руководстве рассмотрены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-117">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="6f1f4-118">Они должны выполнить в указанном порядке для данного пошагового руководства для успешного выполнения:</span><span class="sxs-lookup"><span data-stu-id="6f1f4-118">They should be completed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="6f1f4-119">Создание DBML-файла</span><span class="sxs-lookup"><span data-stu-id="6f1f4-119">Creating a .dbml file</span></span>
<br />

- <span data-ttu-id="6f1f4-120">Создание и настройка проекта F #</span><span class="sxs-lookup"><span data-stu-id="6f1f4-120">Creating and setting up an F# project</span></span>
<br />

- <span data-ttu-id="6f1f4-121">Настройка поставщика типов и Создание типов</span><span class="sxs-lookup"><span data-stu-id="6f1f4-121">Configuring the type provider and generating the types</span></span>
<br />

- <span data-ttu-id="6f1f4-122">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="6f1f4-122">Querying the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="6f1f4-123">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6f1f4-123">Prerequisites</span></span>

## <a name="creating-a-dbml-file"></a><span data-ttu-id="6f1f4-124">Создание DBML-файла</span><span class="sxs-lookup"><span data-stu-id="6f1f4-124">Creating a .dbml file</span></span>
<span data-ttu-id="6f1f4-125">Если базы данных для проверки на нет, создайте его в соответствии с инструкциями в нижней части [Пошаговое руководство: доступ к базе данных SQL с помощью поставщиков типов](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="6f1f4-125">If you do not have a database to test on, create one by following the instructions at the bottom of [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span> <span data-ttu-id="6f1f4-126">Если вы выполните следующие действия, вы создадите базу данных с именем MyDatabase, который содержит несколько простых таблиц и хранимых процедур в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-126">If you follow these instructions, you will create a database called MyDatabase that contains a few simple tables and stored procedures on your SQL Server.</span></span>

<span data-ttu-id="6f1f4-127">Если уже имеется DBML-файла, можно перейти к разделе **создать и установить копию проекта F #**.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-127">If you already have a .dbml file, you can skip to the section, **Create and Set Up an F# Project**.</span></span> <span data-ttu-id="6f1f4-128">В противном случае можно создать DBML-файла, заданному существующей базы данных SQL и с помощью командной строки программу SqlMetal.exe.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-128">Otherwise, you can create a .dbml file given an existing SQL database and by using the command-line tool SqlMetal.exe.</span></span>


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a><span data-ttu-id="6f1f4-129">Создание DBML-файла с помощью SqlMetal.exe</span><span class="sxs-lookup"><span data-stu-id="6f1f4-129">To create a .dbml file by using SqlMetal.exe</span></span>

1. <span data-ttu-id="6f1f4-130">Откройте **Командная строка разработчика**.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-130">Open a **Developer Command Prompt**.</span></span>
<br />

2. <span data-ttu-id="6f1f4-131">Убедитесь, что доступ к SqlMetal.exe, введя `SqlMetal.exe /?` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-131">Ensure that you have access to SqlMetal.exe by entering `SqlMetal.exe /?` at the command prompt.</span></span> <span data-ttu-id="6f1f4-132">SqlMetal.exe обычно устанавливается в **пакеты SDK** папки в **Program Files** или **Program Files (x86)**.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-132">SqlMetal.exe is typically installed under the **Microsoft SDKs** folder in **Program Files** or **Program Files (x86)**.</span></span>
<br />

3. <span data-ttu-id="6f1f4-133">Запустите SqlMetal.exe со следующими параметрами командной строки.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-133">Run SqlMetal.exe with the following command-line options.</span></span> <span data-ttu-id="6f1f4-134">Подставьте вместо правильный путь `c:\destpath` создать DBML-файла и вставить соответствующие значения для сервера базы данных, имя экземпляра и имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-134">Substitute an appropriate path in place of `c:\destpath` to create the .dbml file, and insert appropriate values for the database server, instance name, and database name.</span></span>
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
<span data-ttu-id="6f1f4-135">Если SqlMetal.exe проблемы при создании файла из-за проблем с разрешениями, сменить текущий каталог, в папку, которая имеет доступ на запись к.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-135">If SqlMetal.exe has trouble creating the file due to permissions issues, change the current directory to a folder that you have write access to.</span></span>


4. <span data-ttu-id="6f1f4-136">Вы также можете изучить другие доступные параметры командной строки.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-136">You can also look at the other available command-line options.</span></span> <span data-ttu-id="6f1f4-137">Например существуют параметры, которые можно использовать, если требуется, представления и функции SQL, включенные в создаваемых типов.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-137">For example, there are options you can use if you want views and SQL functions included in the generated types.</span></span> <span data-ttu-id="6f1f4-138">Дополнительные сведения см. в разделе [SqlMetal.exe &#40; Средство создания кода &#41; ](https://msdn.microsoft.com/library/bb386987).</span><span class="sxs-lookup"><span data-stu-id="6f1f4-138">For more information, see [SqlMetal.exe &#40;Code Generation Tool&#41;](https://msdn.microsoft.com/library/bb386987).</span></span>
<br />


## <a name="creating-and-setting-up-an-f-project"></a><span data-ttu-id="6f1f4-139">Создание и настройка проекта F #</span><span class="sxs-lookup"><span data-stu-id="6f1f4-139">Creating and setting up an F# project</span></span>
<span data-ttu-id="6f1f4-140">На этом шаге создайте проект и добавляются необходимые ссылки на использование поставщика типов DBML.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-140">In this step, you create a project and add appropriate references to use the DBML type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="6f1f4-141">Действия для создания и настройки проекта F#</span><span class="sxs-lookup"><span data-stu-id="6f1f4-141">To create and set up an F# project</span></span>

1. <span data-ttu-id="6f1f4-142">Добавьте новый проект консольного приложения F # в решение.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-142">Add a new F# Console Application project to your solution.</span></span>
<br />

2. <span data-ttu-id="6f1f4-143">В **обозревателе решений**, откройте контекстное меню для **ссылки**и нажмите кнопку **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-143">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="6f1f4-144">В **сборки** области, выберите **Framework** узел и выберите в списке доступных сборок **System.Data** и **System.Data.Linq**  сборки.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-144">In the **Assemblies** area, choose the **Framework** node, and then, in the list of available assemblies, choose the **System.Data** and **System.Data.Linq** assemblies.</span></span>
<br />

4. <span data-ttu-id="6f1f4-145">В **сборки** области, выберите **расширения**и выберите в списке доступных сборок **FSharp.Data.TypeProviders**.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-145">In the **Assemblies** area, choose **Extensions**, and then, in the list of available assemblies, choose **FSharp.Data.TypeProviders**.</span></span>
<br />

5. <span data-ttu-id="6f1f4-146">Выберите **ОК** кнопку, чтобы добавить ссылки на следующие сборки в проект.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-146">Choose the **OK** button to add references to these assemblies to your project.</span></span>
<br />

6. <span data-ttu-id="6f1f4-147">(Необязательно).</span><span class="sxs-lookup"><span data-stu-id="6f1f4-147">(Optional).</span></span> <span data-ttu-id="6f1f4-148">Скопируйте DBML-файл, созданный на предыдущем шаге и вставьте файл в главной папке проекта.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-148">Copy the .dbml file that you created in the previous step, and paste the file in the main folder for your project.</span></span> <span data-ttu-id="6f1f4-149">Эта папка содержит файл проекта (.fsproj) и файлы кода.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-149">This folder contains the project file (.fsproj) and code files.</span></span> <span data-ttu-id="6f1f4-150">В строке меню выберите **проекта**, **Добавление существующего элемента**, а затем укажите DBML-файл, чтобы добавить его в проект.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-150">On the menu bar, choose **Project**, **Add Existing Item**, and then specify the .dbml file to add it to your project.</span></span> <span data-ttu-id="6f1f4-151">Если вы выполните следующие действия, можно опустить параметр static ResolutionFolder на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-151">If you complete these steps, you can omit the ResolutionFolder static parameter in the next step.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="6f1f4-152">Настройка поставщика типов</span><span class="sxs-lookup"><span data-stu-id="6f1f4-152">Configuring the type provider</span></span>
<span data-ttu-id="6f1f4-153">В этом разделе вы создать поставщик типов и Создание типов в схеме, описанной в DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-153">In this section, you create a type provider and generate types from the schema that’s described in the .dbml file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a><span data-ttu-id="6f1f4-154">Настройка поставщика типов и Создание типов</span><span class="sxs-lookup"><span data-stu-id="6f1f4-154">To configure the type provider and generate the types</span></span>

- <span data-ttu-id="6f1f4-155">Добавьте код, который открывает **TypeProviders** пространства имен и создает экземпляр поставщика типов для DBML-файла, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-155">Add code that opens the **TypeProviders** namespace and instantiates the type provider for the .dbml file that you want to use.</span></span> <span data-ttu-id="6f1f4-156">Если вы добавили DBML-файл в проект, можно опустить параметр static ResolutionFolder.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-156">If you added the .dbml file to your project, you can omit the ResolutionFolder static parameter.</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

<span data-ttu-id="6f1f4-157">Предоставляет доступ к созданным типам тип DataContext и наследует от `System.Data.Linq.DataContext`.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-157">The DataContext type provides access to all the generated types and inherits from `System.Data.Linq.DataContext`.</span></span> <span data-ttu-id="6f1f4-158">Поставщик типов DbmlFile имеет различные статических параметров, задаваемых пользователем.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-158">The DbmlFile type provider has various static parameters that you can set.</span></span> <span data-ttu-id="6f1f4-159">Например, можно использовать другое имя для типа DataContext, указав `DataContext=MyDataContext`.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-159">For example, you can use a different name for the DataContext type by specifying `DataContext=MyDataContext`.</span></span> <span data-ttu-id="6f1f4-160">В этом случае ваш код напоминает приведенный ниже:</span><span class="sxs-lookup"><span data-stu-id="6f1f4-160">In that case, your code resembles the following example:</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a><span data-ttu-id="6f1f4-161">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="6f1f4-161">Querying the database</span></span>
<span data-ttu-id="6f1f4-162">В этом разделе используются выражения запросов F # запросов к базе данных.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-162">In this section, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="6f1f4-163">Действия для запроса данных</span><span class="sxs-lookup"><span data-stu-id="6f1f4-163">To query the data</span></span>

- <span data-ttu-id="6f1f4-164">Добавьте код для запроса к базе данных.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-164">Add code to query the database.</span></span>
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a><span data-ttu-id="6f1f4-165">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="6f1f4-165">Next Steps</span></span>
<span data-ttu-id="6f1f4-166">Можно продолжить использовать другие выражения запроса, или получить из контекста данных подключения к базе данных и выполнения обычных операций с данными ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="6f1f4-166">You can proceed to use other query expressions, or get a database connection from the data context and perform normal ADO.NET data operations.</span></span> <span data-ttu-id="6f1f4-167">Для выполнения дополнительных действий см. в разделах после «Запроса данных» в [Пошаговое руководство: доступ к базе данных SQL с помощью поставщиков типов](accessing-a-sql-database.md).</span><span class="sxs-lookup"><span data-stu-id="6f1f4-167">For additional steps, see the sections after "Query the Data" in [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="6f1f4-168">См. также</span><span class="sxs-lookup"><span data-stu-id="6f1f4-168">See Also</span></span>
[<span data-ttu-id="6f1f4-169">Поставщик типов DbmlFile</span><span class="sxs-lookup"><span data-stu-id="6f1f4-169">DbmlFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="6f1f4-170">Поставщики типов</span><span class="sxs-lookup"><span data-stu-id="6f1f4-170">Type Providers</span></span>](index.md)

[<span data-ttu-id="6f1f4-171">Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="6f1f4-171">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>](accessing-a-sql-database.md)

[<span data-ttu-id="6f1f4-172">SqlMetal.exe &#40; Средство создания кода &#41;</span><span class="sxs-lookup"><span data-stu-id="6f1f4-172">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)

[<span data-ttu-id="6f1f4-173">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="6f1f4-173">Query Expressions</span></span>](../../language-reference/query-expressions.md)
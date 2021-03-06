---
title: Параметры компилятора (F#)
description: Используйте F# параметрах компилятора командной строки для управления компиляцией вашей F# приложений и библиотек.
ms.date: 05/16/2016
ms.openlocfilehash: f4a596d0dede6f66faa34374f7f73a89323f1620
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "33566448"
---
# <a name="compiler-options"></a>Параметры компилятора

В этом разделе описываются параметры командной строки компилятора для F# компилятора, fsc.exe. Среда может также контролироваться настройкой свойств проекта.


## <a name="compiler-options-listed-alphabetically"></a>Параметры компилятора в алфавитном порядке
Ниже приведены параметры компилятора в алфавитном порядке. Некоторые из F# параметры компилятора, аналогичны C# параметры компилятора. Если это так, ссылку на C# предоставляется тему по параметрам компилятора.



|Параметр компилятора|Описание|
|---------------|-----------|
|**-***&lt;имя выходного файла&gt;**|Создает библиотеку и задает ее имя файла. Этот параметр является краткой формой **--target:библиотека****&lt;filename&gt;**.|
|**-baseaddress:&lt;строка&gt;**|Задает базовый адрес библиотеки для построения.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;baseaddress &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/2fdbz5xd.aspx).|
|**--кодовая страница:&lt;int&gt;**|Указывает кодовую страницу для чтения файлов исходного кода.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;кодовая страница &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/w0kyekyh.aspx).|
|**--consolecolors**|Указывает, что ошибки и предупреждения используют кодированный цветом текст на консоли.|
|**--crossoptimize**[**+**&#124;**-**]|Включает или отключает межмодульные оптимизации.|
|**-delaysign**[**+**&#124;**-**]|Отложенная подпись сборки, используя только открытую часть ключа строгого имени.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;delaysign &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/ta1sxwy8.aspx).|
|**--проверить**[**+**&#124;**-**]|Включает или отключает формирование проверок переполнения.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;проверяется &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/h25wtyxf.aspx).|
|**--debug**[**+**&#124;**-**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**--debug**: [**полный**&#124;**pdbonly**]<br /><br />**-g:** [**полный**&#124;**pdbonly**]|Включает или отключает формирование сведений по отладке или указывает тип отладочной информации для создания. Значение по умолчанию полное, что разрешает присоединение к выполняющейся программе. Выберите **pdbonly** для получения ограниченного отладочной информации, хранимой в файле pdb (база данных программы).<br /><br />Эквивалентно C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе .<br /><br />[&#47;Отладка &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/8cw0bt21.aspx).|
|**--определить:&lt;строка&gt;**<br /><br />**-d:&lt;строки&gt;**|Определяет символ для использования в условной компиляции.|
|**--детерминированным**[**+**&#124;**-**]|Создания детерминированной сборки (включая идентификатор GUID версии модуля и метка времени).  Это не может использоваться с подстановочным знаком номера версий и поддерживает только внедренные и переносимых отладки|
|**--doc:&lt;xmldoc файла&gt;**|Предписывает компилятору создавать комментарии XML-документации в указанный файл. Дополнительные сведения см. в разделе [XML Documentation](xml-documentation.md).<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;doc &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/3260k4x7.aspx).|
|**--fullpaths**|Предписывает компилятору создавать полные пути.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;fullpaths &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/d315xc66.aspx).|
|**--справки**<br /><br />**-?**|Отображает сведения об использовании, включая краткое описание всех параметров компилятора.|
|**-highentropyva**[**+**&#124;**-**]|Включение или отключение высокой энтропией технологию address space макета randomization (ASLR), функцию усиленной безопасности. Операционная система случайный выбор из своего местоположения в памяти, в котором загружаются инфраструктуры для приложений (например, стек и куча). Если включить этот параметр, операционные системы могут использовать такая рандомизация для использования полного 64-разрядного адресного пространства на 64-разрядном компьютере.|
|**-keycontainer:&lt;строка&gt;**|Задает контейнер ключа для строгого имени.|
|**-keyfile:&lt;имя файла&gt;**|Указывает имя файла открытого ключа для подписи созданной сборки.|
|**--lib:&lt;имя папки&gt;**<br /><br />**-I:&lt;имя папки&gt;**|Указывает каталог для поиска указанных сборок.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;lib &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/s5bac5fx.aspx).|
|**-linkresource**:**&lt;сведения о ресурсе&gt;**|Связывает указанный ресурс в сборку. Сведения о ресурсе имеет *filename*[,*имя*[,*открытый*&#124;*частного*]]<br /><br />Связывание единичного ресурса при помощи этого параметра является альтернативой к внедрению целого файла ресурсов с помощью **--resource** параметр.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;linkresource &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/xawyf94k.aspx).|
|**--mlcompatibility**|Игнорирует предупреждения, которые отображаются при использовании функций, предназначенных для совместимости с другими версиями языка ML.|
|**--noframework**|Отключает ссылку по умолчанию для сборки .NET Framework.|
|**--nointerfacedata**|Указывает компилятору на необходимость пропустить ресурс, который он обычно добавляет к сборке, которая включает F#-определенных метаданных.|
|**-nologo**|Не показывает текст баннера при запуске компилятора.|
|**--nooptimizationdata**|Предписывает компилятору включать только оптимизацию, которая необходима для выполнения встроенных конструктов. Этот параметр запрещает межмодульную, но улучшает совместимость двоичных данных.|
|**-nowin32manifest**|Указывает компилятору, чтобы пропустить манифест Win32 по умолчанию.|
|**-nowarn:&lt;int-list&gt;**|Отключает определенные предупреждения, перечисленные по номеру. Выделяет каждый номер предупреждения с помощью символа запятой. Можно найти номер предупреждения для любого предупреждения из компиляционного вывода.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;nowarn &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/7f28x9z3.aspx).|
|**--оптимизировать**[**+**&#124;**-**]**[&lt;список строк&gt;]**<br /><br />**-O [+&#124;-] [&lt;список строк&gt;]**|Включает или отключает оптимизацию. Некоторые параметры оптимизации может быть отключены или включены выборочно при помощи их перечисления. Ниже приведены: **nojitoptimize**, **nojittracking**, **nolocaloptimize**, **nocrossoptimize**, **notailcalls**.|
|**--out:&lt;output-filename&gt;**<br /><br />**-o:&lt;имя выходного файла&gt;**|Задает имя скомпилированной сборки или модуля.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;out &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/bw3t50f3.aspx).|
|**--pdb:&lt;pdb-filename&gt;**|Имена файла PDB (база данных программы) отладки вывода. Этот параметр применяется, только когда **--debug** включена.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;pdb &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/ms228625.aspx).|
|**--платформы:&lt;имя платформы&gt;**|Указывает, что созданный код запускается только на указанной платформе (**x86**, **Itanium**, или **x64**), или, если имя платформы **anycpu**выбирается, указывает, что созданный код может запускаться на любой платформе.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;платформы &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/zekwfyz4.aspx).|
|**-preferreduilang:&lt;lang&gt;**| Указывает имя предпочтительного языка вывода языка и региональных параметров (например, es-ES, ja-JP). |
|**--quotations-debug**|Указывает, что Дополнительные сведения об отладке должны выдаваться для выражений, которые являются производными от F# литералов цитат и отраженных определений. Отладочная информация добавляется к настраиваемым атрибутам из F# узел дерева выражения. См. в разделе [кавычки кода](code-quotations.md) и [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--reference:&lt;assembly-filename&gt;**<br /><br />**-r** &lt; **имя файла сборки&gt;**|Позволяет выполнять код из F# или сборки .NET Framework, доступным для компилируемого кода.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;ссылку &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/yabyz3h4.aspx).|
|**--resource:&lt;имя файла ресурсов&gt;**|Внедряет файл управляемых ресурсов в созданную сборку.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;ресурсов &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/c0tyye07.aspx).|
|**--sig**:&lt;**имя файла подписи&gt;**|Создает файл сигнатуры, в зависимости от созданной сборки. Дополнительные сведения о файлах сигнатур см. в разделе [подписи](signatures.md).|
|**--simpleresolution**|Указывает, что ссылки на сборки должны разрешаться с помощью правил Mono на основе каталогов, а не разрешения MSBuild. Значение по умолчанию — используется разрешение MSBuild, кроме запуска в Mono.|
|**— автономный**|Определяет значение для создания сборки, содержащей все его зависимости, чтобы она выполнялась самостоятельно без необходимости дополнительных сборок, таких как F# библиотеки.|
|**--staticlink:&lt;имя сборки**&gt;|Статически связывает данную сборку и все указанные библиотеки DLL, которые зависят от этой сборки. Используйте имя сборки, а не имя библиотеки DLL.|
|**-subsystemversion**|Указывает версию подсистемы операционной системы, который будет использоваться создаваемый исполняемый файл. Используйте 6.02 для Windows 8.1, 6.01 для Windows 7, 6.00 для Windows Vista. Этот параметр применяется только к исполняемым файлам, а не к библиотекам DLL и требуется использовать, только если приложение зависит от функции безопасности, доступные только в некоторых версиях операционной системы. Если этот параметр используется, и пользователь пытается выполнить приложения в более ранней версии операционной системы, он завершится ошибкой с сообщением об ошибке.|
|**--tailcalls**[**+**&#124;**-**]|Включает или отключает использование конечной части IL инструкции, что кадр стека для конечных рекурсивных функций. Этот параметр по умолчанию включен.|
|**--целевой**: [**exe** &#124; **winexe** &#124; **библиотеки** &#124; **модуль** ]  **&lt;имя выходного файла&gt;**|Указывает тип и имя созданного скомпилированного кода.<ul><li>**exe** означает консольное приложение.<br /></li><li>**winexe** означает приложение Windows, которое отличается от консольного приложения тем, что он не имеет определенных стандартных потоков ввода вывода (stdin, stdout и stderr).<br /></li><li>**Библиотека** является сборкой без точки входа.<br /></li><li>**модуль** является модулем .NET Framework (.netmodule), который может позже быть соединен с другими модулями в сборку.<br /></li><ul/>Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;целевой &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/6h25dztx.aspx).|
|**--раз**|Отображает информацию о времени для компиляции.|
|**--utf8output**|Включает печать вывода компилятора в кодировке UTF-8.|
|**--предупредить:&lt;уровня предупреждения&gt;**|Задает уровень предупреждений (0 – 5). По умолчанию — 3. Каждому предупреждению приписывается уровень на основе его серьезности. Уровень 5 дает дополнительные, но менее серьезны, предупреждения, чем уровень 1.<br /><br />Предупреждения уровня 5: 21 (проверка рекурсивного использования во время выполнения), 22 (**let rec** оценка произвольного порядка), 45 (полная абстракция) и 52 (защитительное копирование). Все другие предупреждения — это уровень 2.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;предупреждать &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/13b90fz7.aspx).|
|**--warnon:&lt;int-list&gt;**|Включение конкретных предупреждений, которые могут быть отключены по умолчанию или отключены другим параметром командной строки. В F# 3.0, только предупреждение 1182 (неиспользуемые переменные) по умолчанию отключены.|
|**-warnaserror**[**+**&#124;**-**] [**&lt;int-list&gt;**]|Включает или отключает параметр, позволяющий сообщать о предупреждениях как ошибки. Вы можете предоставить специальные номера предупреждений, чтобы отключать или включать. Параметры позже в командной строке переопределяют параметры в командной строке. Например, чтобы указать предупреждений, которые вы не хотите выводятся как ошибки, укажите **--warnaserror +--warnaserror-:&lt;int-list&gt;**.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;warnaserror &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/406xhdz3.aspx).|
|**--win32manifest:manifest-filename**|Добавляет файл манифеста Win32 в компиляцию. Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;win32manifest &#40;C&#35; параметры компилятора&#41;](https://msdn.microsoft.com/library/bb545961.aspx).|
|**--win32res:resource-filename**|Добавляет файл ресурсов Win32 в компиляцию.<br /><br />Этот параметр эквивалентен C# параметр компилятора с тем же именем. Дополнительные сведения см. в разделе [ &#47;win32res (&#40;C & #35); Параметры компилятора&#41;](https://msdn.microsoft.com/library/8f2f5x2e.aspx).|

## <a name="related-topics"></a>См. также


|Заголовок|Описание|
|-----|-----------|
|[Параметры окна "Интерактивный F#"](fsharp-interactive-options.md)|Описываются параметры командной строки, поддерживаемые F# интерпретатор, fsi.exe.|
|[Справочник по свойствам проектов](/visualstudio/ide/reference/project-properties-reference)|Описывает пользовательский Интерфейс для проектов, включая страницы свойств проекта, которые обеспечивают параметры построения.|

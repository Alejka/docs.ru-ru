---
title: Практическое руководство. Запись текста в двоичные файлы в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: 59edf84c1addd287eb1d1615c46258f329b1c7e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587206"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a>Практическое руководство. Запись текста в двоичные файлы в Visual Basic
Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> записывает данные в двоичный файл. Если параметр `append` имеет значение `True`, данные будут добавляться в файл; в противном случае данные в файле перезаписываются.  
  
 Если указанный путь без имени файла является недопустимым, возникает исключение <xref:System.IO.DirectoryNotFoundException>. Если путь является допустимым, но файл не существует, файл будет создан.  
  
### <a name="to-write-to-a-binary-file"></a>Запись в двоичный файл  
  
-   Используйте метод `WriteAllBytes`, указав путь к файлу, имя файла и байты, которые требуется записать. В этом примере массив данных `CustomerData` добавляется в файл `CollectedData.dat`.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Исключение может возникнуть при следующих условиях:  
  
-   Путь является недопустимым по одной из следующих причин: это строка нулевой длины; она содержит только пробелы; она содержит недопустимые знаки. (<xref:System.ArgumentException>).  
  
-   Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `File` указывает на путь, который не существует (<xref:System.IO.FileNotFoundException> или <xref:System.IO.DirectoryNotFoundException>).  
  
-   Файл уже используется другим процессом или возникла ошибка ввода-вывода (<xref:System.IO.IOException>).  
  
-   Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).  
  
-   Имя файла или каталога в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).  
  
-   У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>  
 [Практическое руководство. Запись текста в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)

---
title: -resource (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: e02eda66ab9fadbc7b5b042c8940096c70ef6a03
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45746131"
---
# <a name="-resource-c-compiler-options"></a>-resource (параметры компилятора C#)
Внедряет указанный ресурс в выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Файл ресурсов платформы .NET Framework, который требуется внедрить в выходной файл.  
  
 `identifier` (необязательно)  
 Логическое имя ресурса, используемое для его загрузки. По умолчанию используется имя файла.  
  
 `accessibility-modifier` (необязательно)  
 Доступность ресурса: "public" (открытый) или "private" (закрытый). Значение по умолчанию — "public" (открытый).  
  
## <a name="remarks"></a>Примечания  
 Используйте [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md), чтобы связать ресурс со сборкой и не добавлять файл ресурсов в выходной файл.  
  
 По умолчанию ресурсы в сборке открыты, если они создавались с помощью компилятора C#. Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступа. Уровни доступности, отличные от `public` или `private`, не допускаются.  
  
 Если `filename` является файлом ресурсов .NET Framework, созданным, например, с помощью [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, то к нему можно обращаться с помощью членов пространства имен <xref:System.Resources>. Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы `GetManifestResource` в классе <xref:System.Reflection.Assembly>.  
  
 **-res** является краткой формой **-resource**.  
  
 Порядок расположения ресурсов в выходном файле будет определяться порядком, указанным в командной строке.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Добавьте файл ресурсов в проект.  
  
2.  Выберите файл, который требуется внедрить, в **обозревателе решений**.  
  
3.  Выберите **Действие сборки** для файла в окне **Свойства**.  
  
4.  Присвойте параметру **Действие сборки** значение **Внедренный ресурс**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.FileProperties2.BuildAction%2A>.  
  
## <a name="example"></a>Пример  
 Компиляция `in.cs` и привязка файла ресурсов `rf.resource`:  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a>См. также  

- [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

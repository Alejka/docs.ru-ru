---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b22fb9ae24a04d9fe530811bf764352199c31813
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200814"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

**- Refonly** параметр указывает, что основные выходные файлы компиляции ссылочную сборку, а не сборка реализации. Параметр `-refonly` автоматически отключает вывод файлов PDB, так как базовые сборки не могут выполняться.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Синтаксис

```console
-refonly
```

## <a name="remarks"></a>Примечания

Visual Basic поддерживает `-refout` переключения, начиная с версии 15.3.

Ссылка сборки являются только метаданные, которые содержат метаданные, но без реализации их кода. Они включают сведения о типе и члене для всем, кроме анонимных типов. Тело `throw null` используется для того, чтобы могло выполняться средство PEVerify для проверки полноты метаданных, что было бы невозможно при отсутствии тела.

Базовые сборки содержат уровня сборки [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) атрибута. Этот атрибут может быть задан в исходном коде (в этом случае компилятору не требуется его синтезировать). Из-за этого атрибута среды выполнения не будут загружать базовые сборки для выполнения (но по-прежнему могут быть загружены в контекст только для отражения). Средства, выполняющие отражение сборок необходимо убедиться, что они загружать базовые сборки как предназначенный только для отражения; в противном случае среда выполнения создает <xref:System.BadImageFormatException>.

Параметры `-refonly` и [`-refout`](refout-compiler-option.md) являются взаимоисключающими.

## <a name="see-also"></a>См. также
[-refout](refout-compiler-option.md)   
[Компилятор Visual Basic с интерфейсом командной строки](index.md)  
[Примеры командных строк компиляции](sample-compilation-command-lines.md)   

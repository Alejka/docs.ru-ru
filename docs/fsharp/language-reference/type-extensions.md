---
title: "Расширения типов (F#)"
description: "Узнайте, как расширения типов F # позволяют добавить новые элементы в ранее определенный тип объекта."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c9d7ce27-f5ad-4766-b9e9-34187da5bc24
ms.openlocfilehash: f78f8689e95fc1547f1a2b17c615592c00051f7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="type-extensions"></a><span data-ttu-id="528f7-104">Расширения типов</span><span class="sxs-lookup"><span data-stu-id="528f7-104">Type Extensions</span></span>

<span data-ttu-id="528f7-105">Расширения типов позволяют добавлять новые элементы на ранее определенный тип объекта.</span><span class="sxs-lookup"><span data-stu-id="528f7-105">Type extensions let you add new members to a previously defined object type.</span></span>

## <a name="syntax"></a><span data-ttu-id="528f7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="528f7-106">Syntax</span></span>

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a><span data-ttu-id="528f7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="528f7-107">Remarks</span></span>
<span data-ttu-id="528f7-108">Существует два вида типов расширений, которые имеют различный синтаксис и поведение.</span><span class="sxs-lookup"><span data-stu-id="528f7-108">There are two forms of type extensions that have slightly different syntax and behavior.</span></span> <span data-ttu-id="528f7-109">*Встроенное расширение* — это расширение, отображается в том же пространстве имен или модуль, в том же исходном файле и в той же сборки (DLL или исполняемом файле) как расширяемый тип.</span><span class="sxs-lookup"><span data-stu-id="528f7-109">An *intrinsic extension* is an extension that appears in the same namespace or module, in the same source file, and in the same assembly (DLL or executable file) as the type being extended.</span></span> <span data-ttu-id="528f7-110">*Дополнительное расширение* — это расширение, которое находится за пределами исходного модуля, пространства имен или сборке расширяемого типа.</span><span class="sxs-lookup"><span data-stu-id="528f7-110">An *optional extension* is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span> <span data-ttu-id="528f7-111">Встроенные расширения отображаются на тип, при проверке этого типа с помощью отражения, но дополнительные не.</span><span class="sxs-lookup"><span data-stu-id="528f7-111">Intrinsic extensions appear on the type when the type is examined by reflection, but optional extensions do not.</span></span> <span data-ttu-id="528f7-112">Дополнительное расширение должно содержаться в модулях и они содержат только в области, если модуль, содержащий его модуль открыт.</span><span class="sxs-lookup"><span data-stu-id="528f7-112">Optional extensions must be in modules, and they are only in scope when the module that contains the extension is open.</span></span>

<span data-ttu-id="528f7-113">В предыдущем синтаксисе *typename* представляет тип, который расширяется.</span><span class="sxs-lookup"><span data-stu-id="528f7-113">In the previous syntax, *typename* represents the type that is being extended.</span></span> <span data-ttu-id="528f7-114">Любой тип, который может осуществляться могут быть расширены, но имя типа должно быть фактическое имя типа, не сокращенная форма типа.</span><span class="sxs-lookup"><span data-stu-id="528f7-114">Any type that can be accessed can be extended, but the type name must be an actual type name, not a type abbreviation.</span></span> <span data-ttu-id="528f7-115">Можно определить несколько элементов в один тип расширения.</span><span class="sxs-lookup"><span data-stu-id="528f7-115">You can define multiple members in one type extension.</span></span> <span data-ttu-id="528f7-116">*Собственный идентификатор* представляет экземпляр вызываемого объекта, как и обычные элементы.</span><span class="sxs-lookup"><span data-stu-id="528f7-116">The *self-identifier* represents the instance of the object being invoked, just as in ordinary members.</span></span>

<span data-ttu-id="528f7-117">`end` Ключевое слово является обязательным в упрощенный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="528f7-117">The `end` keyword is optional in lightweight syntax.</span></span>

<span data-ttu-id="528f7-118">Члены, определенные в расширениях типов можно использовать так же, как и других членов в типе класса.</span><span class="sxs-lookup"><span data-stu-id="528f7-118">Members defined in type extensions can be used just like other members on a class type.</span></span> <span data-ttu-id="528f7-119">Как и другие члены они быть статическим или члены экземпляров.</span><span class="sxs-lookup"><span data-stu-id="528f7-119">Like other members, they can be static or instance members.</span></span> <span data-ttu-id="528f7-120">Эти методы также называются *методы расширения*; свойства называются *свойства расширения*, и т. д.</span><span class="sxs-lookup"><span data-stu-id="528f7-120">These methods are also known as *extension methods*; properties are known as *extension properties*, and so on.</span></span> <span data-ttu-id="528f7-121">Члены дополнительных расширений компилируются на статические члены, для которых экземпляр объекта неявно передается как первый параметр.</span><span class="sxs-lookup"><span data-stu-id="528f7-121">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="528f7-122">Тем не менее они работать, как если бы они были экземпляра и статических членов в соответствии с каким образом они объявлены.</span><span class="sxs-lookup"><span data-stu-id="528f7-122">However, they act as if they were instance members or static members according to how they are declared.</span></span> <span data-ttu-id="528f7-123">Неявное расширением элементы включены в качестве членов типа и может использоваться без ограничений.</span><span class="sxs-lookup"><span data-stu-id="528f7-123">Implicit extension members are included as members of the type and can be used without restriction.</span></span>

<span data-ttu-id="528f7-124">Методы расширения не может быть виртуальным или абстрактным методам.</span><span class="sxs-lookup"><span data-stu-id="528f7-124">Extension methods cannot be virtual or abstract methods.</span></span> <span data-ttu-id="528f7-125">Они могут перегружать другие методы с тем же именем, но компилятор отдает предпочтение методам без расширения, в случае возникнет Неоднозначный вызов.</span><span class="sxs-lookup"><span data-stu-id="528f7-125">They can overload other methods of the same name, but the compiler gives preference to non-extension methods in the case of an ambiguous call.</span></span>

<span data-ttu-id="528f7-126">Если для одного типа имеется несколько встроенных расширений типа, все члены должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="528f7-126">If multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="528f7-127">Для дополнительных расширениях члены различных расширений того же типа могут иметь одинаковые имена.</span><span class="sxs-lookup"><span data-stu-id="528f7-127">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="528f7-128">Неоднозначность происходят только в том случае, если код клиента открывает две различные области, определяющие одинаковые имена членов.</span><span class="sxs-lookup"><span data-stu-id="528f7-128">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

<span data-ttu-id="528f7-129">В следующем примере тип в модуле с расширением внутреннего типа.</span><span class="sxs-lookup"><span data-stu-id="528f7-129">In the following example, a type in a module has an intrinsic type extension.</span></span> <span data-ttu-id="528f7-130">Клиентскому коду за пределами модуля расширение типа выглядит как обычный член типа во всех отношениях.</span><span class="sxs-lookup"><span data-stu-id="528f7-130">To client code outside the module, the type extension appears as a regular member of the type in all respects.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

<span data-ttu-id="528f7-131">Можно использовать встроенных расширений типа можно разделить определение типа на несколько разделов.</span><span class="sxs-lookup"><span data-stu-id="528f7-131">You can use intrinsic type extensions to separate the definition of a type into sections.</span></span> <span data-ttu-id="528f7-132">Это может быть полезно при управлении большими определениями типов, например, для отделения кода, созданного компилятором и разрабатываемого кода или сгруппировать код, созданный разными людьми или связанные с различные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="528f7-132">This can be useful in managing large type definitions, for example, to keep compiler-generated code and authored code separate or to group together code created by different people or associated with different functionality.</span></span>

<span data-ttu-id="528f7-133">В следующем примере дополнительное расширение типа `System.Int32` типа с методом расширения `FromString` статический член, которая вызывает `Parse`.</span><span class="sxs-lookup"><span data-stu-id="528f7-133">In the following example, an optional type extension extends the `System.Int32` type with an extension method `FromString` that calls the static member `Parse`.</span></span> <span data-ttu-id="528f7-134">`testFromString` Метод показывает, что новый член вызывается так же, как и любой другой член экземпляра.</span><span class="sxs-lookup"><span data-stu-id="528f7-134">The `testFromString` method demonstrates that the new member is called just like any instance member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

<span data-ttu-id="528f7-135">Новый член экземпляра будет отображаться как любой другой метод `Int32` типа в IntelliSense, но только в том случае, если модуль, содержащий расширение находится в открытом или в противном случае в области видимости.</span><span class="sxs-lookup"><span data-stu-id="528f7-135">The new instance member will appear like any other method of the `Int32` type in IntelliSense, but only when the module that contains the extension is open or otherwise in scope.</span></span>

## <a name="generic-extension-methods"></a><span data-ttu-id="528f7-136">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="528f7-136">Generic Extension Methods</span></span>
<span data-ttu-id="528f7-137">Прежде чем F # 3.1, компилятор F # не поддерживает использование C#-стиля методы расширения с переменной универсального типа, тип массива, тип кортежа или тип функции F #, как параметр «this».</span><span class="sxs-lookup"><span data-stu-id="528f7-137">Before F# 3.1, the F# compiler didn't support the use of C#-style extension methods with a generic type variable, array type, tuple type, or an F# function type as the "this" parameter.</span></span> <span data-ttu-id="528f7-138">3.1 языка F # поддерживает использование этих элементов расширения.</span><span class="sxs-lookup"><span data-stu-id="528f7-138">F# 3.1 supports the use of these extension members.</span></span>

<span data-ttu-id="528f7-139">Например в коде F # 3.1, можно использовать методы расширения с подписями, похожим на следующий синтаксис в C#:</span><span class="sxs-lookup"><span data-stu-id="528f7-139">For example, in F# 3.1 code, you can use extension methods with signatures that resemble the following syntax in C#:</span></span>

```csharp
static member Method<T>(this T input, T other)
```

<span data-ttu-id="528f7-140">Этот подход особенно полезен, если параметр универсального типа ограничен.</span><span class="sxs-lookup"><span data-stu-id="528f7-140">This approach is particularly useful when the generic type parameter is constrained.</span></span> <span data-ttu-id="528f7-141">Кроме того теперь можно объявить члены расширений следующим образом в коде F # и определяют дополнительные, семантически широкий набор методов расширения.</span><span class="sxs-lookup"><span data-stu-id="528f7-141">Further, you can now declare extension members like this in F# code and define an additional, semantically rich set of extension methods.</span></span> <span data-ttu-id="528f7-142">В языке F # обычно определяются элементы расширения как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="528f7-142">In F#, you usually define extension members as the following example shows:</span></span>

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

<span data-ttu-id="528f7-143">Тем не менее для универсального типа, переменная типа может не быть ограничен.</span><span class="sxs-lookup"><span data-stu-id="528f7-143">However, for a generic type, the type variable may not be constrained.</span></span> <span data-ttu-id="528f7-144">Можно объявить C#-расширение элементу стиля в F #, чтобы обойти это ограничение.</span><span class="sxs-lookup"><span data-stu-id="528f7-144">You can now declare a C#-style extension member in F# to work around this limitation.</span></span> <span data-ttu-id="528f7-145">При объединении этого типа объявления с встроенное средство F # универсальные алгоритмы можно представить как члены расширений.</span><span class="sxs-lookup"><span data-stu-id="528f7-145">When you combine this kind of declaration with the inline feature of F#, you can present generic algorithms as extension members.</span></span>

<span data-ttu-id="528f7-146">Рассмотрим следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="528f7-146">Consider the following declaration:</span></span>

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="528f7-147">Используя это объявление, можно написать код, подобный приведенному в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="528f7-147">By using this declaration, you can write code that resembles the following sample.</span></span>

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

<span data-ttu-id="528f7-148">В этом коде тот же универсальный код арифметические применяется к спискам два типа без перегрузки, определяя элемент одно расширение.</span><span class="sxs-lookup"><span data-stu-id="528f7-148">In this code, the same generic arithmetic code is applied to lists of two types without overloading, by defining a single extension member.</span></span>


## <a name="see-also"></a><span data-ttu-id="528f7-149">См. также</span><span class="sxs-lookup"><span data-stu-id="528f7-149">See Also</span></span>
[<span data-ttu-id="528f7-150">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="528f7-150">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="528f7-151">Члены</span><span class="sxs-lookup"><span data-stu-id="528f7-151">Members</span></span>](members/index.md)
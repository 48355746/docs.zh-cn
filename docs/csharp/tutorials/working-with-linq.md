---
title: 使用 LINQ
description: 此教程将介绍如何使用 LINQ 生成序列、编写用于 LINQ 查询的方法，以及如何区分及早计算和惰性计算。
ms.date: 03/28/2017
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: dc5f6cc4fd38b32f54a576a3947187cbed4e70e8
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086747"
---
# <a name="working-with-linq"></a><span data-ttu-id="59a34-103">使用 LINQ</span><span class="sxs-lookup"><span data-stu-id="59a34-103">Working with LINQ</span></span>

## <a name="introduction"></a><span data-ttu-id="59a34-104">介绍</span><span class="sxs-lookup"><span data-stu-id="59a34-104">Introduction</span></span>

<span data-ttu-id="59a34-105">此教程将介绍 .NET Core 和 C# 语言的许多功能。</span><span class="sxs-lookup"><span data-stu-id="59a34-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="59a34-106">你将了解：</span><span class="sxs-lookup"><span data-stu-id="59a34-106">You’ll learn:</span></span>

*   <span data-ttu-id="59a34-107">如何使用 LINQ 生成序列</span><span class="sxs-lookup"><span data-stu-id="59a34-107">How to generate sequences with LINQ</span></span>
*   <span data-ttu-id="59a34-108">如何编写可轻松用于 LINQ 查询的方法。</span><span class="sxs-lookup"><span data-stu-id="59a34-108">How to write methods that can be easily used in LINQ queries.</span></span>
*   <span data-ttu-id="59a34-109">如何区分及早计算和惰性计算。</span><span class="sxs-lookup"><span data-stu-id="59a34-109">How to distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="59a34-110">你将通过生成应用程序来了解如何执行这些操作，应用程序体现了所有魔术师都具备的一项基本技能，即[完美洗牌](https://en.wikipedia.org/wiki/Faro_shuffle)。</span><span class="sxs-lookup"><span data-stu-id="59a34-110">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="59a34-111">简而言之，完美洗牌这项技能是指，将一副纸牌分成两半，然后两手各拿一半交错洗牌（一张隔一张），以便重新生成原来的一副纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-111">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="59a34-112">魔术师之所以要掌握这项技能是因为，每次洗牌后每张纸牌的位置已知，且顺序为重复模式。</span><span class="sxs-lookup"><span data-stu-id="59a34-112">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span> 

<span data-ttu-id="59a34-113">考虑到我们的目的，数据序列控制起来就会非常轻松。</span><span class="sxs-lookup"><span data-stu-id="59a34-113">For our purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="59a34-114">生成的应用程序会构造一副纸牌，然后执行一系列洗牌操作，每次都会输出序列。</span><span class="sxs-lookup"><span data-stu-id="59a34-114">The application you'll build will construct a card deck, and then perform a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="59a34-115">还可以将更新后的顺序与原始顺序进行比较。</span><span class="sxs-lookup"><span data-stu-id="59a34-115">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="59a34-116">在此教程中，将执行多步操作。</span><span class="sxs-lookup"><span data-stu-id="59a34-116">This tutorial has multiple steps.</span></span> <span data-ttu-id="59a34-117">执行每步操作后，都可以运行应用程序，并查看进度。</span><span class="sxs-lookup"><span data-stu-id="59a34-117">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="59a34-118">还可参阅 dotnet/samples GitHub 存储库中的[完整示例](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq)。</span><span class="sxs-lookup"><span data-stu-id="59a34-118">You can also see the [completed sample](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="59a34-119">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="59a34-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59a34-120">系统必备</span><span class="sxs-lookup"><span data-stu-id="59a34-120">Prerequisites</span></span>

<span data-ttu-id="59a34-121">必须将计算机设置为运行 .Net Core。</span><span class="sxs-lookup"><span data-stu-id="59a34-121">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="59a34-122">有关安装说明，请访问 [.NET Core](https://www.microsoft.com/net/core) 页。</span><span class="sxs-lookup"><span data-stu-id="59a34-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="59a34-123">可以在 Windows、Ubuntu Linux、OS X 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="59a34-123">You can run this application on Windows, Ubuntu Linux, OS X or in a Docker container.</span></span> <span data-ttu-id="59a34-124">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="59a34-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="59a34-125">在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="59a34-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="59a34-126">不过，你可以使用习惯使用的任意工具。</span><span class="sxs-lookup"><span data-stu-id="59a34-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="59a34-127">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="59a34-127">Create the Application</span></span>

<span data-ttu-id="59a34-128">第一步是新建应用程序。</span><span class="sxs-lookup"><span data-stu-id="59a34-128">The first step is to create a new application.</span></span> <span data-ttu-id="59a34-129">打开命令提示符，然后新建应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="59a34-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="59a34-130">将新建的目录设为当前目录。</span><span class="sxs-lookup"><span data-stu-id="59a34-130">Make that the current directory.</span></span> <span data-ttu-id="59a34-131">在命令提示符处，键入命令 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="59a34-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="59a34-132">这将为基本的“Hello World”应用程序创建起始文件。</span><span class="sxs-lookup"><span data-stu-id="59a34-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="59a34-133">如果之前从未用过 C#，请参阅[这篇教程](console-teleprompter.md)，其中介绍了 C# 程序的结构。</span><span class="sxs-lookup"><span data-stu-id="59a34-133">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="59a34-134">可以阅读相应的内容，然后回到此教程详细了解 LINQ。</span><span class="sxs-lookup"><span data-stu-id="59a34-134">You can read that and then return here to learn more about LINQ.</span></span> 

## <a name="creating-the-data-set"></a><span data-ttu-id="59a34-135">创建数据集</span><span class="sxs-lookup"><span data-stu-id="59a34-135">Creating the Data Set</span></span>

<span data-ttu-id="59a34-136">首先，我们要创建一副纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-136">Let's start by creating a deck of cards.</span></span> <span data-ttu-id="59a34-137">为此，请使用包含两个源（一个用于四套花色，另一个用于十三个值）的 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="59a34-137">You'll do this using a LINQ query that has two sources (one for the four suits, one for the thirteen values).</span></span> <span data-ttu-id="59a34-138">将这些源合并成一副纸牌（52 张）。</span><span class="sxs-lookup"><span data-stu-id="59a34-138">You'll combine those sources into a 52 card deck.</span></span> <span data-ttu-id="59a34-139">`foreach` 循环内的 `Console.WriteLine` 语句会显示纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-139">A `Console.WriteLine` statement inside a `foreach` loop displays the cards.</span></span>

<span data-ttu-id="59a34-140">查询如下：</span><span class="sxs-lookup"><span data-stu-id="59a34-140">Here's the query:</span></span>

```csharp
var startingDeck = from s in Suits()
                   from r in Ranks()
                   select new { Suit = s, Rank = r };

foreach (var c in startingDeck)
{
    Console.WriteLine(c);
}
```

<span data-ttu-id="59a34-141">多个 `from` 子句生成 `SelectMany`，用于将第一个和第二个序列中的所有元素合并成一个序列。</span><span class="sxs-lookup"><span data-stu-id="59a34-141">The multiple `from` clauses produce a `SelectMany`, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="59a34-142">考虑到我们的目的，顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="59a34-142">The order is important for our purposes.</span></span> <span data-ttu-id="59a34-143">第一个源序列（花色）中的首个元素与第二个序列（值）中的每个元素合并。</span><span class="sxs-lookup"><span data-stu-id="59a34-143">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Values).</span></span> <span data-ttu-id="59a34-144">这就生成了第一个花色的所有十三张纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-144">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="59a34-145">对第一个序列（花色）中的每个元素重复此过程。</span><span class="sxs-lookup"><span data-stu-id="59a34-145">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="59a34-146">最后生成按花色排序（后跟值）的一副纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-146">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="59a34-147">接下来，需要生成 Suits() 和 Ranks() 方法。</span><span class="sxs-lookup"><span data-stu-id="59a34-147">Next, you'll need to build the Suits() and Ranks() methods.</span></span> <span data-ttu-id="59a34-148">让我们从一组非常简单的*迭代器方法*入手，这些方法将一个序列生成为可枚举的各个字符串：</span><span class="sxs-lookup"><span data-stu-id="59a34-148">Let's start with a really simple set of *iterator methods* that generate the sequence as an enumerable of strings:</span></span>

```csharp
static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

<span data-ttu-id="59a34-149">这两种方法都利用 `yield return` 语法在运行时生成序列。</span><span class="sxs-lookup"><span data-stu-id="59a34-149">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="59a34-150">编译器会生成对象来实现 `IEnumerable<T>`，并在有请求时生成字符串序列。</span><span class="sxs-lookup"><span data-stu-id="59a34-150">The compiler builds an object that implements `IEnumerable<T>` and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="59a34-151">为了让编译能够顺利进行，需要在文件的最上面添加以下两行代码：</span><span class="sxs-lookup"><span data-stu-id="59a34-151">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
```

<span data-ttu-id="59a34-152">此时，运行已生成的示例。</span><span class="sxs-lookup"><span data-stu-id="59a34-152">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="59a34-153">将显示一副纸牌中的所有 52 张纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-153">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="59a34-154">在调试器模式下运行此示例来观察 `Suits()` 和 `Values()` 方法的执行情况，你可能会觉得非常有用。</span><span class="sxs-lookup"><span data-stu-id="59a34-154">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Values()` methods execute.</span></span> <span data-ttu-id="59a34-155">可以清楚地看到，每个序列中的所有字符串仅在需要时生成。</span><span class="sxs-lookup"><span data-stu-id="59a34-155">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![显示应用输出 52 张纸牌的控制台窗口](./media/working-with-linq/console.png)

## <a name="manipulating-the-order"></a><span data-ttu-id="59a34-157">控制顺序</span><span class="sxs-lookup"><span data-stu-id="59a34-157">Manipulating the Order</span></span>

<span data-ttu-id="59a34-158">接下来，让我们来生成一个可执行洗牌操作的实用工具方法。</span><span class="sxs-lookup"><span data-stu-id="59a34-158">Next, let's build a utility method that can perform the shuffle.</span></span> <span data-ttu-id="59a34-159">第一步是将一副纸牌分成两半。</span><span class="sxs-lookup"><span data-stu-id="59a34-159">The first step is to split the deck in two.</span></span> <span data-ttu-id="59a34-160">LINQ API 包含的 `Take()` 和 `Skip()` 方法提供了这种功能：</span><span class="sxs-lookup"><span data-stu-id="59a34-160">The `Take()` and `Skip()` methods that are part of the LINQ APIs provide that feature for us:</span></span>

```csharp
var top = startingDeck.Take(26);
var bottom = startingDeck.Skip(26);
```

<span data-ttu-id="59a34-161">由于标准库中没有洗牌方法，因此必须自行编写。</span><span class="sxs-lookup"><span data-stu-id="59a34-161">The shuffle method doesn't exist in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="59a34-162">这个新方法体现了要对基于 LINQ 的程序执行的几种操作，我们将逐步介绍此方法的每个部分。</span><span class="sxs-lookup"><span data-stu-id="59a34-162">This new method illustrates several techniques that you'll use with LINQ-based programs, so let's explain each part of the method in steps.</span></span>

<span data-ttu-id="59a34-163">此方法的签名可创建*扩展方法*：</span><span class="sxs-lookup"><span data-stu-id="59a34-163">The signature for the method creates an *extension method*:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T>
    (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="59a34-164">扩展方法是一种具有特殊用途的*静态方法*。</span><span class="sxs-lookup"><span data-stu-id="59a34-164">An extension method is a special purpose *static method.*</span></span> <span data-ttu-id="59a34-165">可以发现，在扩展方法的第一个自变量中添加了 `this` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="59a34-165">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="59a34-166">也就是说，调用扩展方法，就像是第一个自变量类型的成员方法一样。</span><span class="sxs-lookup"><span data-stu-id="59a34-166">That means you call the method as though it were a member method of the type of the first argument.</span></span>

<span data-ttu-id="59a34-167">扩展方法只能在 `static` 类中声明，那么让我们新建一个 `extensions` 静态类来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="59a34-167">Extension methods can be declared only inside `static` classes, so let's create a new static class called `extensions` for this functionality.</span></span> <span data-ttu-id="59a34-168">在此教程接下来的部分中，你将会添加更多扩展方法，这些方法都位于同一类中。</span><span class="sxs-lookup"><span data-stu-id="59a34-168">You'll add more extension methods as you continue this tutorial, and those will be placed in the same class.</span></span>

<span data-ttu-id="59a34-169">此方法声明还遵循标准惯用做法，其中输入和输出类型为 `IEnumerable<T>`。</span><span class="sxs-lookup"><span data-stu-id="59a34-169">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="59a34-170">遵循这种做法，可以将 LINQ 方法链在一起，从而执行更复杂的查询。</span><span class="sxs-lookup"><span data-stu-id="59a34-170">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

```csharp
using System.Collections.Generic;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>
            (this IEnumerable<T> first, IEnumerable<T> second)
        {
            // implementation coming.
        }
    }
}
```

<span data-ttu-id="59a34-171">将同时枚举两个序列，交错各个元素，然后创建一个对象。</span><span class="sxs-lookup"><span data-stu-id="59a34-171">You will be enumerating both sequences at once, interleaving the elements, and creating one object.</span></span>  <span data-ttu-id="59a34-172">必须了解 `IEnumerable` 的工作原理，才能编写处理两个序列的 LINQ 方法。</span><span class="sxs-lookup"><span data-stu-id="59a34-172">Writing a LINQ method that works with two sequences requires that you understand how `IEnumerable` works.</span></span>

<span data-ttu-id="59a34-173">`IEnumerable` 接口有一个方法 (`GetEnumerator()`)。</span><span class="sxs-lookup"><span data-stu-id="59a34-173">The `IEnumerable` interface has one method: `GetEnumerator()`.</span></span> <span data-ttu-id="59a34-174">`GetEnumerator()` 返回的对象包含用于移动到下一个元素的方法，以及用于检索序列中当前元素的属性。</span><span class="sxs-lookup"><span data-stu-id="59a34-174">The object returned by `GetEnumerator()` has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="59a34-175">将使用这两个成员来枚举集合并返回元素。</span><span class="sxs-lookup"><span data-stu-id="59a34-175">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="59a34-176">由于此交错方法是迭代器方法，因此将使用上面的 `yield return` 语法，而不用生成并返回集合。</span><span class="sxs-lookup"><span data-stu-id="59a34-176">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span> 

<span data-ttu-id="59a34-177">下面是此方法的实现代码：</span><span class="sxs-lookup"><span data-stu-id="59a34-177">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="59a34-178">至此，你已编写好这个方法，请回到 `Main` 方法，并进行一次洗牌：</span><span class="sxs-lookup"><span data-stu-id="59a34-178">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }
        
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a><span data-ttu-id="59a34-179">比较</span><span class="sxs-lookup"><span data-stu-id="59a34-179">Comparisons</span></span>

<span data-ttu-id="59a34-180">让我们来看看进行多少次洗牌才能恢复一副纸牌的原始顺序。</span><span class="sxs-lookup"><span data-stu-id="59a34-180">Let's see how many shuffles it takes to set the deck back to its original order.</span></span> <span data-ttu-id="59a34-181">需要编写用于确定两个序列是否相等的方法。</span><span class="sxs-lookup"><span data-stu-id="59a34-181">You'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="59a34-182">编写好此方法后，需要循环执行用于洗牌的代码，看看一副纸牌何时才能恢复原始顺序。</span><span class="sxs-lookup"><span data-stu-id="59a34-182">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="59a34-183">编写用于确定两个序列是否相等的方法应该很简单。</span><span class="sxs-lookup"><span data-stu-id="59a34-183">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="59a34-184">此方法的结构与你编写的洗牌方法类似。</span><span class="sxs-lookup"><span data-stu-id="59a34-184">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="59a34-185">不同之处在于，这一次将比较每个序列的匹配元素，而不是生成每个返回元素。</span><span class="sxs-lookup"><span data-stu-id="59a34-185">Only this time, instead of yield returning each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="59a34-186">枚举整个序列后，如果每个元素都一致，那么序列就是相同的：</span><span class="sxs-lookup"><span data-stu-id="59a34-186">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="59a34-187">这反映了另一种 LINQ 惯用做法，即终端方法。</span><span class="sxs-lookup"><span data-stu-id="59a34-187">This shows a second Linq idiom: terminal methods.</span></span> <span data-ttu-id="59a34-188">此类方法需要将序列（或在此示例中，为两个序列）用作输入，并返回一个标量值。</span><span class="sxs-lookup"><span data-stu-id="59a34-188">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="59a34-189">若使用，此类方法始终是查询的最终方法</span><span class="sxs-lookup"><span data-stu-id="59a34-189">These methods, when they are used, are always the final method of a query.</span></span> <span data-ttu-id="59a34-190">（由此而得名）。</span><span class="sxs-lookup"><span data-stu-id="59a34-190">(Hence the name).</span></span> 

<span data-ttu-id="59a34-191">使用此类方法来确定一副纸牌何时恢复原始顺序时，就可以了解实际效果。</span><span class="sxs-lookup"><span data-stu-id="59a34-191">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="59a34-192">循环执行洗牌代码，通过应用 `SequenceEquals()` 方法确定序列已恢复原始顺序时停止执行。</span><span class="sxs-lookup"><span data-stu-id="59a34-192">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="59a34-193">你会发现，此类方法始终是任何查询中的最后一个方法，因为返回的是一个值，而不是一个序列：</span><span class="sxs-lookup"><span data-stu-id="59a34-193">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
var times = 0;
var shuffle = startingDeck;

do
{
    shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    times++;
} while (!startingDeck.SequenceEquals(shuffle));

Console.WriteLine(times);
```

<span data-ttu-id="59a34-194">运行此示例，看看一副纸牌在每次洗牌时是如何重新排列的（纸牌在进行 8 次迭代后恢复原始配置）。</span><span class="sxs-lookup"><span data-stu-id="59a34-194">Run the sample, and see how the deck rearranges on each shuffle, until it returns to its original configuration after 8 iterations.</span></span>

## <a name="optimizations"></a><span data-ttu-id="59a34-195">优化</span><span class="sxs-lookup"><span data-stu-id="59a34-195">Optimizations</span></span>

<span data-ttu-id="59a34-196">到目前为止，你已生成的示例执行的是向外洗牌，即每次洗牌时第一张和最后一张纸牌保持不变。</span><span class="sxs-lookup"><span data-stu-id="59a34-196">The sample you've built so far executes an *out shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="59a34-197">让我们来做一点改变，执行向内洗牌，改变全部 52 张纸牌的位置。</span><span class="sxs-lookup"><span data-stu-id="59a34-197">Let's make one change, and run an *in shuffle*, where all 52 cards change position.</span></span> <span data-ttu-id="59a34-198">向内洗牌是指，交错一副纸牌时，将后一半中的第一张纸牌变成一副纸牌中的第一张纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-198">For an in shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="59a34-199">也就是说，上半部分中的最后一张纸牌变成一副纸牌中的最后一张纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-199">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="59a34-200">只需更改一行代码即可。</span><span class="sxs-lookup"><span data-stu-id="59a34-200">That's just a one line change.</span></span> <span data-ttu-id="59a34-201">将对 shuffle 的调用更新为，更改一副纸牌的上半部分和下半部分的顺序：</span><span class="sxs-lookup"><span data-stu-id="59a34-201">Update the call to shuffle to change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="59a34-202">再次运行程序，你会发现需要进行 52 次迭代才能恢复一副纸牌的原始顺序。</span><span class="sxs-lookup"><span data-stu-id="59a34-202">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="59a34-203">随着程序的继续运行，你还会开始注意到一些非常严重的性能下降问题发生。</span><span class="sxs-lookup"><span data-stu-id="59a34-203">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="59a34-204">导致这种情况出现的原因有很多。</span><span class="sxs-lookup"><span data-stu-id="59a34-204">There are a number of reasons for this.</span></span> <span data-ttu-id="59a34-205">让我们来看看其中一个主要原因：*惰性计算*的使用效率低下。</span><span class="sxs-lookup"><span data-stu-id="59a34-205">Let's tackle one of the major causes: inefficient use of *lazy evaluation*.</span></span>

<span data-ttu-id="59a34-206">LINQ 查询执行的是惰性计算。</span><span class="sxs-lookup"><span data-stu-id="59a34-206">LINQ queries are evaluated lazily.</span></span> <span data-ttu-id="59a34-207">仅当有元素请求时才生成序列。</span><span class="sxs-lookup"><span data-stu-id="59a34-207">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="59a34-208">通常情况下，这是 LINQ 的主要优势所在。</span><span class="sxs-lookup"><span data-stu-id="59a34-208">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="59a34-209">不过，在诸如此程序之类的用例中，这就会导致执行时间指数式增长。</span><span class="sxs-lookup"><span data-stu-id="59a34-209">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="59a34-210">原来的一副纸牌是使用 LINQ 查询生成。</span><span class="sxs-lookup"><span data-stu-id="59a34-210">The original deck was generated using a LINQ query.</span></span> <span data-ttu-id="59a34-211">每次洗牌操作是通过对上一副纸牌执行三次 LINQ 查询进行。</span><span class="sxs-lookup"><span data-stu-id="59a34-211">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="59a34-212">所有这些操作均采用惰性执行方式。</span><span class="sxs-lookup"><span data-stu-id="59a34-212">All these are performed lazily.</span></span> <span data-ttu-id="59a34-213">也就是说，每当有序列请求时，才会再次执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="59a34-213">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="59a34-214">执行到第 52 次迭代时，就已经重新生成很多很多次原来的一副纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-214">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="59a34-215">让我们来编写一个日志方法来阐明此行为。</span><span class="sxs-lookup"><span data-stu-id="59a34-215">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="59a34-216">然后，你就可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="59a34-216">Then, you'll fix it.</span></span>

<span data-ttu-id="59a34-217">下面展示了日志方法，可以将其追加到任何查询中，以标记查询已执行。</span><span class="sxs-lookup"><span data-stu-id="59a34-217">Here's a log method that can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="59a34-218">接下来，使用日志消息来检测每个查询的定义：</span><span class="sxs-lookup"><span data-stu-id="59a34-218">Next, instrument the definition of each query with a log message:</span></span>

```csharp
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }
        
    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        shuffle = shuffle.Skip(26)
            .LogQuery("Bottom Half")
            .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
            .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="59a34-219">请注意，不是每次访问查询都会生成日志。</span><span class="sxs-lookup"><span data-stu-id="59a34-219">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="59a34-220">只有在创建原始查询时，才会生成日志。</span><span class="sxs-lookup"><span data-stu-id="59a34-220">You log only when you create the original query.</span></span> <span data-ttu-id="59a34-221">程序的运行时间仍然很长，但现在知道原因了。</span><span class="sxs-lookup"><span data-stu-id="59a34-221">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="59a34-222">如果对在启用日志记录的情况下运行向内洗牌失去了耐心，请切换回向外洗牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-222">If you run out of patience running the inner shuffle with logging turned on, switch back to the outer shuffle.</span></span> <span data-ttu-id="59a34-223">但仍会看到惰性计算效果。</span><span class="sxs-lookup"><span data-stu-id="59a34-223">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="59a34-224">在一次运行中，共执行 2592 次查询，包括生成所有值和花色。</span><span class="sxs-lookup"><span data-stu-id="59a34-224">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="59a34-225">可使用一种简单的方法来更新此程序，以省去所有这些执行。</span><span class="sxs-lookup"><span data-stu-id="59a34-225">There is an easy way to update this program to avoid all those executions.</span></span> <span data-ttu-id="59a34-226">LINQ 方法 `ToArray()` 和 `ToList()` 用于运行查询，并将结果分别存储在数组或列表中。</span><span class="sxs-lookup"><span data-stu-id="59a34-226">There are LINQ methods `ToArray()` and `ToList()` that cause the query to run, and store the results in an array or a list, respectively.</span></span> <span data-ttu-id="59a34-227">可以使用这些方法来缓存查询的数据结果，而不用再次执行源查询。</span><span class="sxs-lookup"><span data-stu-id="59a34-227">You use these methods to cache the data results of a query rather than execute the source query again.</span></span>  <span data-ttu-id="59a34-228">追加查询以通过调用 `ToArray()` 生成一副纸牌，然后再次运行查询：</span><span class="sxs-lookup"><span data-stu-id="59a34-228">Append the queries that generate the card decks with a call to `ToArray()` and run the query again:</span></span>

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="59a34-229">再次运行程序，向外洗牌下降到 30 次查询。</span><span class="sxs-lookup"><span data-stu-id="59a34-229">Run again, and the outer shuffle is down to 30 queries.</span></span> <span data-ttu-id="59a34-230">再次运行向内洗牌程序，改善情况类似。</span><span class="sxs-lookup"><span data-stu-id="59a34-230">Run again with the inner shuffle and you'll see similar improvements.</span></span> <span data-ttu-id="59a34-231">（现在执行 162 次查询）。</span><span class="sxs-lookup"><span data-stu-id="59a34-231">(It now executes 162 queries).</span></span>

<span data-ttu-id="59a34-232">不要将此示例误认为，所有查询都应及早运行。</span><span class="sxs-lookup"><span data-stu-id="59a34-232">Don't misinterpret this example by thinking that all queries should run eagerly.</span></span> <span data-ttu-id="59a34-233">此示例旨在突出显示惰性计算可能会导致性能下降的用例。</span><span class="sxs-lookup"><span data-stu-id="59a34-233">This example is designed to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="59a34-234">这是因为每次重新排列一副纸牌都要以先前的排列为依据。</span><span class="sxs-lookup"><span data-stu-id="59a34-234">That's because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="59a34-235">使用惰性计算意味着一副纸牌的每个新配置都以原来的一副纸牌为依据，甚至在执行生成 `startingDeck` 的代码时，也不例外。</span><span class="sxs-lookup"><span data-stu-id="59a34-235">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="59a34-236">这会导致大量额外的工作。</span><span class="sxs-lookup"><span data-stu-id="59a34-236">That causes a large amount of extra work.</span></span> 

<span data-ttu-id="59a34-237">在实践中，一些算法的效果优于使用及早计算，另一些算法的效果优于使用惰性计算。</span><span class="sxs-lookup"><span data-stu-id="59a34-237">In practice, some algorithms run much better using eager evaluation, and others run much better using lazy evaluation.</span></span> <span data-ttu-id="59a34-238">（通常情况下，如果数据源为单独进程（如数据库引擎），更好的选择是使用惰性计算。</span><span class="sxs-lookup"><span data-stu-id="59a34-238">(In general, lazy evaluation is a much better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="59a34-239">在这种情况下，使用惰性计算，更复杂的查询可以只对数据库进程执行一次往返。）LINQ 支持同时使用惰性计算和及早计算。</span><span class="sxs-lookup"><span data-stu-id="59a34-239">In those cases, lazy evaluation enables more complex queries to execute only one round trip to the database process.) LINQ enables both lazy and eager evaluation.</span></span> <span data-ttu-id="59a34-240">请进行衡量，做出最佳选择。</span><span class="sxs-lookup"><span data-stu-id="59a34-240">Measure, and pick the best choice.</span></span>

## <a name="preparing-for-new-features"></a><span data-ttu-id="59a34-241">为添加新功能做好准备</span><span class="sxs-lookup"><span data-stu-id="59a34-241">Preparing for New Features</span></span>

<span data-ttu-id="59a34-242">为此示例编写的代码展示了如何创建简单的有效原型。</span><span class="sxs-lookup"><span data-stu-id="59a34-242">The code you've written for this sample is an example of creating a simple prototype that does the job.</span></span> <span data-ttu-id="59a34-243">这样可以很好地探索问题空间；对于许多功能来说，这可能是最佳永久性解决方案。</span><span class="sxs-lookup"><span data-stu-id="59a34-243">This is a great way to explore a problem space, and for many features, it may be the best permanent solution.</span></span> <span data-ttu-id="59a34-244">已将*匿名类型*用于纸牌，每张纸牌均由字符串表示。</span><span class="sxs-lookup"><span data-stu-id="59a34-244">You've leveraged *anonymous types* for the cards, and each card is represented by strings.</span></span>

<span data-ttu-id="59a34-245">*匿名类型*在高效工作方面具有许多优势。</span><span class="sxs-lookup"><span data-stu-id="59a34-245">*Anonymous Types* have many productivity advantages.</span></span> <span data-ttu-id="59a34-246">无需自行定义表示存储的类。</span><span class="sxs-lookup"><span data-stu-id="59a34-246">You don't need to define a class yourself to represent the storage.</span></span> <span data-ttu-id="59a34-247">编译器会为你生成类型。</span><span class="sxs-lookup"><span data-stu-id="59a34-247">The compiler generates the type for you.</span></span> <span data-ttu-id="59a34-248">编译器生成的类型遵循多种关于简单数据对象的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="59a34-248">The compiler generated type utilizes many of the best practices for simple data objects.</span></span> <span data-ttu-id="59a34-249">此类型*不可变*，也就是说，在构造之后所有属性都不能更改。</span><span class="sxs-lookup"><span data-stu-id="59a34-249">It's *immutable*, meaning that none of its properties can be changed after it has been constructed.</span></span> <span data-ttu-id="59a34-250">由于匿名类型位于程序集内部，因此不视为属于相应程序集的公共 API。</span><span class="sxs-lookup"><span data-stu-id="59a34-250">Anonymous types are internal to an assembly, so they aren't seen as part of the public API for that assembly.</span></span> <span data-ttu-id="59a34-251">匿名类型还包含 `ToString()` 方法（用于随每个值一起返回格式化字符串）的重写方法。</span><span class="sxs-lookup"><span data-stu-id="59a34-251">Anonymous types also contain an override of the `ToString()` method that returns a formatted string with each of the values.</span></span>

<span data-ttu-id="59a34-252">匿名类型也有缺点。</span><span class="sxs-lookup"><span data-stu-id="59a34-252">Anonymous types also have disadvantages.</span></span> <span data-ttu-id="59a34-253">由于没有可访问的名称，因此无法用作返回值或自变量。</span><span class="sxs-lookup"><span data-stu-id="59a34-253">They don't have accessible names, so you can't use them as return values or arguments.</span></span> <span data-ttu-id="59a34-254">你会注意到，使用这些匿名类型的上述所有方法都是泛型方法。</span><span class="sxs-lookup"><span data-stu-id="59a34-254">You'll notice that any methods above that used these anonymous types are generic methods.</span></span> <span data-ttu-id="59a34-255">`ToString()` 的重写方法可能无法满足你的需求，因为应用程序的功能越来越多。</span><span class="sxs-lookup"><span data-stu-id="59a34-255">The override of `ToString()` may not be what you want as the application grows more features.</span></span> 

<span data-ttu-id="59a34-256">此示例还将字符串用于每张纸牌的花色和级别。</span><span class="sxs-lookup"><span data-stu-id="59a34-256">The sample also uses strings for the suit and the rank of each card.</span></span> <span data-ttu-id="59a34-257">这是相当开放的。</span><span class="sxs-lookup"><span data-stu-id="59a34-257">That's quite open ended.</span></span> <span data-ttu-id="59a34-258">借助 C# 类型系统，我们可以将 `enum` 类型用于这些值，从而编写更优质的代码。</span><span class="sxs-lookup"><span data-stu-id="59a34-258">The C# type system can help us make better code, by leveraging `enum` types for those values.</span></span>

<span data-ttu-id="59a34-259">从花色开始。</span><span class="sxs-lookup"><span data-stu-id="59a34-259">Start with the suits.</span></span> <span data-ttu-id="59a34-260">这是使用 `enum` 的大好时机：</span><span class="sxs-lookup"><span data-stu-id="59a34-260">This is a perfect time to use an `enum`:</span></span>

[!CODE-csharp[Suit enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet2)]

<span data-ttu-id="59a34-261">`Suits()` 方法也更改了类型和实现代码：</span><span class="sxs-lookup"><span data-stu-id="59a34-261">The `Suits()` method also changes type and implementation:</span></span>

[!CODE-csharp[Suit IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet4)]

<span data-ttu-id="59a34-262">接下来，对纸牌的级别进行同样的更改：</span><span class="sxs-lookup"><span data-stu-id="59a34-262">Next, do the same change with the Rank of the cards:</span></span>

[!CODE-csharp[Rank enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet3)]

<span data-ttu-id="59a34-263">以及用于生成级别的方法：</span><span class="sxs-lookup"><span data-stu-id="59a34-263">And the method that generates them:</span></span>

[!CODE-csharp[Rank IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet5)]

<span data-ttu-id="59a34-264">作为最后一项清理工作，让我们使用一个类型来表示纸牌，而不是依赖于匿名类型。</span><span class="sxs-lookup"><span data-stu-id="59a34-264">As one final cleanup, let's make a type to represent the card, instead of relying on an anonymous type.</span></span> <span data-ttu-id="59a34-265">匿名类型非常适合轻量级的局部类型，但在此示例中，扑克牌是主要概念之一。</span><span class="sxs-lookup"><span data-stu-id="59a34-265">Anonymous types are great for lightweight, local types, but in this example, the playing card is one of the main concepts.</span></span> <span data-ttu-id="59a34-266">它应为具体类型。</span><span class="sxs-lookup"><span data-stu-id="59a34-266">It should be a concrete type.</span></span>

[!CODE-csharp[PlayingCard](../../../samples/csharp/getting-started/console-linq/playingcard.cs?name=snippet1)]

<span data-ttu-id="59a34-267">此类型使用在构造函数中设置的*自动实现的只读属性*，而且无法修改。</span><span class="sxs-lookup"><span data-stu-id="59a34-267">This type uses *auto-implemented read-only properties* which are set in the constructor, and then cannot be modified.</span></span> <span data-ttu-id="59a34-268">它还使用[字符串内插](../language-reference/tokens/interpolated.md)功能，简化了字符串输出格式设置。</span><span class="sxs-lookup"><span data-stu-id="59a34-268">It also makes use of the [string interpolation](../language-reference/tokens/interpolated.md) feature that makes it easier to format string output.</span></span>

<span data-ttu-id="59a34-269">将生成初始的一副纸牌的查询更新为使用新类型：</span><span class="sxs-lookup"><span data-stu-id="59a34-269">Update the query that generates the starting deck to use the new type:</span></span>

```csharp
var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                    from r in Ranks().LogQuery("Value Generation")
                    select new PlayingCard(s, r))
                    .LogQuery("Starting Deck")
                    .ToArray();
```

<span data-ttu-id="59a34-270">编译并再次运行。</span><span class="sxs-lookup"><span data-stu-id="59a34-270">Compile and run again.</span></span> <span data-ttu-id="59a34-271">输出更加清晰，代码更加清楚，扩展起来也更加容易。</span><span class="sxs-lookup"><span data-stu-id="59a34-271">The output is a little cleaner, and the code is a bit more clear and can be extended more easily.</span></span>

## <a name="conclusion"></a><span data-ttu-id="59a34-272">结束语</span><span class="sxs-lookup"><span data-stu-id="59a34-272">Conclusion</span></span>

<span data-ttu-id="59a34-273">此示例展示了在 LINQ 中使用的一些方法，以及如何创建你自己的方法与支持 LINQ 的代码轻松结合使用。</span><span class="sxs-lookup"><span data-stu-id="59a34-273">This sample showed you some of the methods used in LINQ, how to create your own methods that will be easily used with LINQ enabled code.</span></span> <span data-ttu-id="59a34-274">还介绍了惰性求值和及早求值的区别，以及决定使用哪种求值对性能产生的影响。</span><span class="sxs-lookup"><span data-stu-id="59a34-274">It also showed you the differences between lazy and eager evaluation, and the effect that decision can have on performance.</span></span>

<span data-ttu-id="59a34-275">而且，你也了解了一点魔术师掌握的一项技能。</span><span class="sxs-lookup"><span data-stu-id="59a34-275">You learned a bit about one magician's technique.</span></span> <span data-ttu-id="59a34-276">魔术师之所以采用完美洗牌是因为，可以控制每张纸牌在一副纸牌中的移动。</span><span class="sxs-lookup"><span data-stu-id="59a34-276">Magicians use the faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="59a34-277">在一些戏法中，魔术师会让一位观众将一张纸牌放在一副纸牌的最上面，然后进行几次洗牌，指出观众所放那张纸牌的具体位置。</span><span class="sxs-lookup"><span data-stu-id="59a34-277">In some tricks, the magician has an audience member place a card on top of the deck, and shuffles a few times, knowing where that card goes.</span></span> <span data-ttu-id="59a34-278">在另一些戏法中，则需要按特定方式设置一副纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-278">Other illusions require the deck set a certain way.</span></span> <span data-ttu-id="59a34-279">魔术师会在变戏法前设置一副纸牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-279">A magician will set the deck prior to performing the trick.</span></span> <span data-ttu-id="59a34-280">然后，她会对一副纸牌进行 5 次向外洗牌。</span><span class="sxs-lookup"><span data-stu-id="59a34-280">Then she will shuffle the deck 5 times using an outer shuffle.</span></span> <span data-ttu-id="59a34-281">在舞台上，她可以向观众展示看似杂乱无章的一副纸牌，然后再进行 3 次洗牌，这样刚好就可以得到她想要的一副纸牌了。</span><span class="sxs-lookup"><span data-stu-id="59a34-281">On stage, she can show what looks like a random deck, shuffle it 3 more times, and have the deck set exactly how she wants.</span></span>

---
description: 条件テストの結果に基づいてコマンドブロックを実行するために使用できる言語ステートメントについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_while?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_While
ms.openlocfilehash: d53077ba54e0680eea6addc87f4e9aeb3eafc4fe
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223179"
---
# <a name="about-while"></a><span data-ttu-id="4b93b-104">しばらく</span><span class="sxs-lookup"><span data-stu-id="4b93b-104">About While</span></span>

## <a name="short-description"></a><span data-ttu-id="4b93b-105">概要</span><span class="sxs-lookup"><span data-stu-id="4b93b-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="4b93b-106">条件テストの結果に基づいてコマンドブロックを実行するために使用できる言語ステートメントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4b93b-106">Describes a language statement that you can use to run a command block based on the results of a conditional test.</span></span>

## <a name="long-description"></a><span data-ttu-id="4b93b-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="4b93b-107">LONG DESCRIPTION</span></span>
<span data-ttu-id="4b93b-108">While ステートメント (While ループとも呼ばれます) は、条件テストが true と評価されている限り、コマンドブロックでコマンドを実行するループを作成するための言語構成要素です。</span><span class="sxs-lookup"><span data-stu-id="4b93b-108">The While statement (also known as a While loop) is a language construct for creating a loop that runs commands in a command block as long as a conditional test evaluates to true.</span></span> <span data-ttu-id="4b93b-109">While ステートメントは、構文が複雑になるので、For ステートメントよりも簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="4b93b-109">The While statement is easier to construct than a For statement because its syntax is less complicated.</span></span> <span data-ttu-id="4b93b-110">さらに、While ステートメントで条件テストを指定すると、ループの実行回数を制御できるため、Foreach ステートメントよりも柔軟です。</span><span class="sxs-lookup"><span data-stu-id="4b93b-110">In addition, it is more flexible than the Foreach statement because you specify a conditional test in the While statement to control how many times the loop runs.</span></span>

<span data-ttu-id="4b93b-111">While ステートメントの構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b93b-111">The following shows the While statement syntax:</span></span>

```powershell
while (<condition>){<statement list>}
```

<span data-ttu-id="4b93b-112">While ステートメントを実行すると、 `<condition>` セクションに入る前に、PowerShell によってステートメントのセクションが評価され `<statement list>` ます。</span><span class="sxs-lookup"><span data-stu-id="4b93b-112">When you run a While statement, PowerShell evaluates the `<condition>` section of the statement before entering the `<statement list>` section.</span></span> <span data-ttu-id="4b93b-113">ステートメントの条件部分は、true または false のいずれかに解決されます。</span><span class="sxs-lookup"><span data-stu-id="4b93b-113">The condition portion of the statement resolves to either true or false.</span></span> <span data-ttu-id="4b93b-114">条件が true のままである限り、PowerShell はセクションを再適用し `<statement list>` ます。</span><span class="sxs-lookup"><span data-stu-id="4b93b-114">As long as the condition remains true, PowerShell reruns the `<statement list>` section.</span></span>

<span data-ttu-id="4b93b-115">`<statement list>`ステートメントのセクションには、ループが入力または繰り返されるたびに実行される1つ以上のコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b93b-115">The `<statement list>` section of the statement contains one or more commands that are run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="4b93b-116">たとえば、次の While ステートメントでは、$val 変数が作成されていない場合、または $val 変数が作成されて0に初期化された場合に、1 ~ 3 の数値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b93b-116">For example, the following While statement displays the numbers 1 through 3 if the $val variable has not been created or if the $val variable has been created and initialized to 0.</span></span>

```powershell
while($val -ne 3)
{
    $val++
    Write-Host $val
}
```

<span data-ttu-id="4b93b-117">この例では、$val \= 0、1、2の場合、条件 ($val は3と等しくありません) は true です。</span><span class="sxs-lookup"><span data-stu-id="4b93b-117">In this example, the condition ($val is not equal to 3) is true while $val \= 0, 1, 2.</span></span> <span data-ttu-id="4b93b-118">ループを実行するたびに、 \+ \+ 単項インクリメント演算子 ($val) を使用して $val が1ずつインクリメントされ \+ \+ ます。</span><span class="sxs-lookup"><span data-stu-id="4b93b-118">Each time through the loop, $val is incremented by 1 using the \+\+ unary increment operator ($val\+\+).</span></span> <span data-ttu-id="4b93b-119">最後にループを実行したときは、$val \= 3 です。</span><span class="sxs-lookup"><span data-stu-id="4b93b-119">The last time through the loop, $val \= 3.</span></span> <span data-ttu-id="4b93b-120">$Val が3の場合、condition ステートメントは false と評価され、ループが終了します。</span><span class="sxs-lookup"><span data-stu-id="4b93b-120">When $val equals 3, the condition statement evaluates to false, and the loop exits.</span></span>

<span data-ttu-id="4b93b-121">PowerShell コマンドプロンプトでこのコマンドを簡単に記述するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4b93b-121">To conveniently write this command at the PowerShell command prompt, you can enter it in the following way:</span></span>

```powershell
while($val -ne 3){$val++; Write-Host $val}
```

<span data-ttu-id="4b93b-122">$Val の値をコンソールに書き込む2番目のコマンドから $val に1を追加する最初のコマンドがセミコロンで区切られていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b93b-122">Notice that the semicolon separates the first command that adds 1 to $val from the second command that writes the value of $val to the console.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b93b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b93b-123">SEE ALSO</span></span>

[<span data-ttu-id="4b93b-124">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="4b93b-124">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="4b93b-125">about_Do</span><span class="sxs-lookup"><span data-stu-id="4b93b-125">about_Do</span></span>](about_Do.md)

[<span data-ttu-id="4b93b-126">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="4b93b-126">about_Foreach</span></span>](about_Foreach.md)

[<span data-ttu-id="4b93b-127">about_For</span><span class="sxs-lookup"><span data-stu-id="4b93b-127">about_For</span></span>](about_For.md)

[<span data-ttu-id="4b93b-128">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="4b93b-128">about_Language_Keywords</span></span>](about_Language_Keywords.md)

---
title: ShouldProcess について知りたかったことのすべて
description: ShouldProcess は、見過ごされることがよくある重要な機能です。 WhatIf と Confirm パラメーターを使用すると、関数に簡単に追加できます。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 1d9110302a191b90bd11bdf742f77704a8c9d6f0
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149485"
---
# <a name="everything-you-wanted-to-know-about-shouldprocess"></a><span data-ttu-id="52554-104">ShouldProcess について知りたかったことのすべて</span><span class="sxs-lookup"><span data-stu-id="52554-104">Everything you wanted to know about ShouldProcess</span></span>

<span data-ttu-id="52554-105">PowerShell 関数には、ユーザーとの対話方法を大幅に向上させる機能がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="52554-105">PowerShell functions have several features that greatly improve the way users interact with them.</span></span>
<span data-ttu-id="52554-106">見過ごされることがよくある重要な機能の 1 つが、`-WhatIf` と `-Confirm` のサポートであり、簡単に関数に追加できます。</span><span class="sxs-lookup"><span data-stu-id="52554-106">One important feature that is often overlooked is `-WhatIf` and `-Confirm` support and it's easy to add to your functions.</span></span> <span data-ttu-id="52554-107">この記事では、この機能を実装する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="52554-107">In this article, we dive deep into how to implement this feature.</span></span>

> [!NOTE]
> <span data-ttu-id="52554-108">この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログ記事です。</span><span class="sxs-lookup"><span data-stu-id="52554-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="52554-109">このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="52554-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="52554-110">[PowerShellExplained.com][] のブログをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="52554-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

<span data-ttu-id="52554-111">これは、セーフティ ネットを必要とするユーザーに対してそれを提供するために、関数で有効にできる単純な機能です。</span><span class="sxs-lookup"><span data-stu-id="52554-111">This is a simple feature you can enable in your functions to provide a safety net for the users that need it.</span></span> <span data-ttu-id="52554-112">危険な可能性があることがわかっているコマンドを初めて実行するときほど怖いことはありません。</span><span class="sxs-lookup"><span data-stu-id="52554-112">There's nothing scarier than running a command that you know can be dangerous for the first time.</span></span> <span data-ttu-id="52554-113">これを `-WhatIf` で実行するオプションを使用すると、大きな違いが生まれます。</span><span class="sxs-lookup"><span data-stu-id="52554-113">The option to run it with `-WhatIf` can make a big difference.</span></span>

## <a name="commonparameters"></a><span data-ttu-id="52554-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="52554-114">CommonParameters</span></span>

<span data-ttu-id="52554-115">これらの[共通パラメーター][]の実装について説明する前に、その使用方法を簡単に見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="52554-115">Before we look at implementing these [common parameters][], I want to take a quick look at how they're used.</span></span>

## <a name="using--whatif"></a><span data-ttu-id="52554-116">-WhatIf を使用する</span><span class="sxs-lookup"><span data-stu-id="52554-116">Using -WhatIf</span></span>

<span data-ttu-id="52554-117">コマンドで `-WhatIf` パラメーターがサポートされている場合、コマンドがどのように実行されるかを、実際の変更を行わずに確認できます。</span><span class="sxs-lookup"><span data-stu-id="52554-117">When a command supports the `-WhatIf` parameter, it allows you to see what the command would have done instead of making changes.</span></span> <span data-ttu-id="52554-118">特に破壊的な操作を行う前には、この方法でコマンドの影響をテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="52554-118">it's a good way to test out the impact of a command, especially before you do something destructive.</span></span>

```powershell
PS C:\temp> Remove-Item -Path .\myfile1.txt -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

<span data-ttu-id="52554-119">コマンドによって `ShouldProcess` が正しく実装されている場合は、実行することになるすべての変更が表示されます。</span><span class="sxs-lookup"><span data-stu-id="52554-119">If the command correctly implements `ShouldProcess`, it should show you all the changes that it would have made.</span></span> <span data-ttu-id="52554-120">ワイルドカードを使用して複数のファイルを削除する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="52554-120">Here is an example using a wildcard to delete multiple files.</span></span>

```powershell
PS C:\temp> Remove-Item -Path * -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\myfile2.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\importantfile.txt".
```

## <a name="using--confirm"></a><span data-ttu-id="52554-121">-Confirm を使用する</span><span class="sxs-lookup"><span data-stu-id="52554-121">Using -Confirm</span></span>

<span data-ttu-id="52554-122">`-WhatIf` をサポートするコマンドは、`-Confirm` もサポートします。</span><span class="sxs-lookup"><span data-stu-id="52554-122">Commands that support `-WhatIf` also support `-Confirm`.</span></span> <span data-ttu-id="52554-123">これにより、実行前にアクションを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="52554-123">This gives you a chance confirm an action before performing it.</span></span>

```powershell
PS C:\temp> Remove-Item .\myfile1.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="52554-124">この場合、続行、変更のスキップ、またはスクリプトの停止を行う複数のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="52554-124">In this case, you have multiple options that allow you to continue, skip a change, or stop the script.</span></span> <span data-ttu-id="52554-125">ヘルプ プロンプトでは、これらの各オプションが次のように説明されます。</span><span class="sxs-lookup"><span data-stu-id="52554-125">The help prompt describes each of those options like this.</span></span>

```Output
Y - Continue with only the next step of the operation.
A - Continue with all the steps of the operation.
N - Skip this operation and proceed with the next operation.
L - Skip this operation and all subsequent operations.
S - Pause the current pipeline and return to the command prompt. Type "exit" to resume the pipeline.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

### <a name="localization"></a><span data-ttu-id="52554-126">ローカリゼーション</span><span class="sxs-lookup"><span data-stu-id="52554-126">Localization</span></span>

<span data-ttu-id="52554-127">このプロンプトは PowerShell にローカライズされているので、お使いのオペレーティング システムの言語に基づいて言語が変化します。</span><span class="sxs-lookup"><span data-stu-id="52554-127">This prompt is localized in PowerShell so the language changes based on the language of your operating system.</span></span> <span data-ttu-id="52554-128">これも、PowerShell によって管理されるものの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="52554-128">This is one more thing that PowerShell manages for you.</span></span>

### <a name="switch-parameters"></a><span data-ttu-id="52554-129">スイッチ パラメーター</span><span class="sxs-lookup"><span data-stu-id="52554-129">Switch parameters</span></span>

<span data-ttu-id="52554-130">スイッチ パラメーターに値を渡す方法を簡単に見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="52554-130">Let's take quick moment to look at ways to pass a value to a switch parameter.</span></span> <span data-ttu-id="52554-131">これを呼び出す主な理由は、呼び出す関数にパラメーター値を渡すことが多いためです。</span><span class="sxs-lookup"><span data-stu-id="52554-131">The main reason I call this out is that you often want to pass parameter values to functions you call.</span></span>

<span data-ttu-id="52554-132">最初の方法は、すべてのパラメーターに使用できる特定のパラメーター構文ですが、ほとんどの場合、スイッチ パラメーターに使用されています。</span><span class="sxs-lookup"><span data-stu-id="52554-132">The first approach is a specific parameter syntax that can be used for all parameters but you mostly see it used for switch parameters.</span></span> <span data-ttu-id="52554-133">パラメーターに値を付加するには、コロンを指定します。</span><span class="sxs-lookup"><span data-stu-id="52554-133">You specify a colon to attach a value to the parameter.</span></span>

```powershell
Remove-Item -Path:* -WhatIf:$true
```

<span data-ttu-id="52554-134">変数でも同じ操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="52554-134">You can do the same with a variable.</span></span>

```powershell
$DoWhatIf = $true
Remove-Item -Path * -WhatIf:$DoWhatIf
```

<span data-ttu-id="52554-135">2 つ目の方法では、ハッシュテーブルを使用して値をスプラッティングします。</span><span class="sxs-lookup"><span data-stu-id="52554-135">The second approach is to use a hashtable to splat the value.</span></span>

```powershell
$RemoveSplat = @{
    Path = '*'
    WhatIf = $true
}
Remove-Item @RemoveSplat
```

<span data-ttu-id="52554-136">ハッシュテーブルまたはスプラッティングを初めて使用する場合は、「[ハッシュテーブルについて知りたかったことのすべて][]」という別の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52554-136">If you're new to hashtables or splatting, I have another article on that covers [everything you wanted to know about hashtables][].</span></span>

## <a name="supportsshouldprocess"></a><span data-ttu-id="52554-137">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="52554-137">SupportsShouldProcess</span></span>

<span data-ttu-id="52554-138">`-WhatIf` と `-Confirm` のサポートを有効にするための最初の手順は、関数の `CmdletBinding` で `SupportsShouldProcess` を指定することです。</span><span class="sxs-lookup"><span data-stu-id="52554-138">The first step to enable `-WhatIf` and `-Confirm` support is to specify `SupportsShouldProcess` in the `CmdletBinding` of your function.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt
}
```

<span data-ttu-id="52554-139">この方法で `SupportsShouldProcess` を指定することで、`-WhatIf` (または `-Confirm`) を使用して関数を呼び出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="52554-139">By specifying `SupportsShouldProcess` in this way, we can now call our function with `-WhatIf` (or `-Confirm`).</span></span>

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

<span data-ttu-id="52554-140">`-WhatIf` という名前のパラメーターを作成しなかったことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="52554-140">Notice that I did not create a parameter called `-WhatIf`.</span></span> <span data-ttu-id="52554-141">`SupportsShouldProcess` を指定すると、自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="52554-141">Specifying `SupportsShouldProcess` automatically creates it for us.</span></span> <span data-ttu-id="52554-142">`Test-ShouldProcess` で `-WhatIf` パラメーターを指定すると、その他の呼び出しのいくつかでも `-WhatIf` 処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="52554-142">When we specify the `-WhatIf` parameter on `Test-ShouldProcess`, some things we call also perform `-WhatIf` processing.</span></span>

### <a name="trust-but-verify"></a><span data-ttu-id="52554-143">信頼するが検証する</span><span class="sxs-lookup"><span data-stu-id="52554-143">Trust but verify</span></span>

<span data-ttu-id="52554-144">呼び出すものすべてが `-WhatIf` の値を継承すると信頼することは危険です。</span><span class="sxs-lookup"><span data-stu-id="52554-144">There's some danger here trusting that everything you call inherits `-WhatIf` values.</span></span> <span data-ttu-id="52554-145">例の残りでは、これは動作しないという前提に立ち、他のコマンドを呼び出す場合には明示的に行うようにします。</span><span class="sxs-lookup"><span data-stu-id="52554-145">For the rest of the examples, I'm going to assume that it doesn't work and be very explicit when making calls to other commands.</span></span> <span data-ttu-id="52554-146">同じようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="52554-146">I recommend that you do the same.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt -WhatIf:$WhatIf
}
```

<span data-ttu-id="52554-147">この微妙な違いについては、全体像をつかんだ後に、詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="52554-147">I will revisit the nuances much later once you have a better understanding of all the pieces in play.</span></span>

## <a name="pscmdletshouldprocess"></a><span data-ttu-id="52554-148">$PSCmdlet.ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="52554-148">$PSCmdlet.ShouldProcess</span></span>

<span data-ttu-id="52554-149">`SupportsShouldProcess` の実装を可能にするメソッドは `$PSCmdlet.ShouldProcess` です。</span><span class="sxs-lookup"><span data-stu-id="52554-149">The method that allows you to implement `SupportsShouldProcess` is `$PSCmdlet.ShouldProcess`.</span></span> <span data-ttu-id="52554-150">`$PSCmdlet.ShouldProcess(...)` を呼び出して、ロジックを処理する必要があるかどうかを確認すると、残りは PowerShell によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="52554-150">You call `$PSCmdlet.ShouldProcess(...)` to see if you should process some logic and PowerShell takes care of the rest.</span></span> <span data-ttu-id="52554-151">例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="52554-151">Let's start with an example:</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        $file.Delete()
    }
}
```

<span data-ttu-id="52554-152">`$PSCmdlet.ShouldProcess($file.name)` を呼び出すと、`-WhatIf` (および `-Confirm` パラメーター) がチェックされ、それに応じて処理されます。</span><span class="sxs-lookup"><span data-stu-id="52554-152">The call to `$PSCmdlet.ShouldProcess($file.name)` checks for the `-WhatIf` (and `-Confirm` parameter) then handles it accordingly.</span></span> <span data-ttu-id="52554-153">`-WhatIf` によって、`ShouldProcess` は変更の説明を出力し、`$false` を返します。</span><span class="sxs-lookup"><span data-stu-id="52554-153">The `-WhatIf` causes `ShouldProcess` to output a description of the change and return `$false`:</span></span>

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

<span data-ttu-id="52554-154">`-Confirm` を使用した呼び出しでは、スクリプトが一時停止され、ユーザーに続行するオプションを示すプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52554-154">A call using `-Confirm` pauses the script and prompts the user with the option to continue.</span></span> <span data-ttu-id="52554-155">ユーザーが `Y` を選択した場合は `$true` が返されます。</span><span class="sxs-lookup"><span data-stu-id="52554-155">It returns `$true` if the user selected `Y`.</span></span>

```powershell
PS> Test-ShouldProcess -Confirm
Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="52554-156">`$PSCmdlet.ShouldProcess` の優れた機能は、詳細出力として 2 倍になることです。</span><span class="sxs-lookup"><span data-stu-id="52554-156">An awesome feature of `$PSCmdlet.ShouldProcess` is that it doubles as verbose output.</span></span> <span data-ttu-id="52554-157">`ShouldProcess` を実装するときは、これを頻繁に行います。</span><span class="sxs-lookup"><span data-stu-id="52554-157">I depend on this often when implementing `ShouldProcess`.</span></span>

```powershell
PS> Test-ShouldProcess -Verbose
VERBOSE: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

### <a name="overloads"></a><span data-ttu-id="52554-158">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="52554-158">Overloads</span></span>

<span data-ttu-id="52554-159">`$PSCmdlet.ShouldProcess` には、メッセージングをカスタマイズするためのさまざまなパラメーターを持ついくつかのオーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="52554-159">There are a few different overloads for `$PSCmdlet.ShouldProcess` with different parameters for customizing the messaging.</span></span> <span data-ttu-id="52554-160">既に前の例で、最初のものを紹介しました。</span><span class="sxs-lookup"><span data-stu-id="52554-160">We already saw the first one in the example above.</span></span> <span data-ttu-id="52554-161">詳しく見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="52554-161">Let's take a closer look at it.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    if($PSCmdlet.ShouldProcess('TARGET')){
        # ...
    }
}
```

<span data-ttu-id="52554-162">これにより、関数名とターゲット (パラメーターの値) の両方を含む出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="52554-162">This produces output that includes both the function name and the target (value of the parameter).</span></span>

```powershell
What if: Performing the operation "Test-ShouldProcess" on target "TARGET".
```

<span data-ttu-id="52554-163">2 番目のパラメーターを操作として指定すると、メッセージ内で関数名の代わりに操作値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="52554-163">Specifying a second parameter as the operation uses the operation value instead of the function name in the message.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".
```

<span data-ttu-id="52554-164">次のオプションでは、メッセージを完全にカスタマイズするために 3 つのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="52554-164">The next option is to specify three parameters to fully customize the message.</span></span> <span data-ttu-id="52554-165">3 つのパラメーターを使用する場合、最初のパラメーターはメッセージ全体を示します。</span><span class="sxs-lookup"><span data-stu-id="52554-165">When three parameters are used, the first one is the entire message.</span></span> <span data-ttu-id="52554-166">2 番目の 2 つのパラメーターは、`-Confirm` メッセージ出力でも引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="52554-166">The second two parameters are still used in the `-Confirm` message output.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

### <a name="quick-parameter-reference"></a><span data-ttu-id="52554-167">クイック パラメーター リファレンス</span><span class="sxs-lookup"><span data-stu-id="52554-167">Quick parameter reference</span></span>

<span data-ttu-id="52554-168">使用する必要があるパラメーターを確認するだけにこの記事を参照してくる場合は、さまざまな `-WhatIf` シナリオでパラメーターがどのようにメッセージを変更するかを示すクイック リファレンスをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="52554-168">Just in case you came here only to figure out what parameters you should use, here is a quick reference showing how the parameters change the message in the different `-WhatIf` scenarios.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('TARGET')
What if: Performing the operation "FUNCTION_NAME" on target "TARGET".

## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".

## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

<span data-ttu-id="52554-169">2 つのパラメーターを持つものが使用される傾向があります。</span><span class="sxs-lookup"><span data-stu-id="52554-169">I tend to use the one with two parameters.</span></span>

### <a name="shouldprocessreason"></a><span data-ttu-id="52554-170">ShouldProcessReason</span><span class="sxs-lookup"><span data-stu-id="52554-170">ShouldProcessReason</span></span>

<span data-ttu-id="52554-171">他よりも高度な 4 番目のオーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="52554-171">We have a fourth overload that's more advanced than the others.</span></span> <span data-ttu-id="52554-172">これにより、`ShouldProcess` が実行された理由を取得できます。</span><span class="sxs-lookup"><span data-stu-id="52554-172">It allows you to get the reason `ShouldProcess` was executed.</span></span> <span data-ttu-id="52554-173">これは単に網羅するために追加しています。代わりに `$WhatIf` が `$true` かどうかを確認できるためです。</span><span class="sxs-lookup"><span data-stu-id="52554-173">I'm only adding this here for completeness because we can just check if `$WhatIf` is `$true` instead.</span></span>

```powershell
$reason = ''
if($PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION',[ref]$reason)){
    Write-Output "Some Action"
}
$reason
```

<span data-ttu-id="52554-174">`[ref]` を持つ参照変数として、`$reason` 変数を 4 番目のパラメーターに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="52554-174">We have to pass the `$reason` variable into the fourth parameter as a reference variable with `[ref]`.</span></span> <span data-ttu-id="52554-175">`ShouldProcess` によって、値 `None` または `WhatIf` を使用して `$reason` が設定されます。</span><span class="sxs-lookup"><span data-stu-id="52554-175">`ShouldProcess` populates `$reason` with the value `None` or `WhatIf`.</span></span> <span data-ttu-id="52554-176">これは特に便利なわけではなく、使用する理由もありません。</span><span class="sxs-lookup"><span data-stu-id="52554-176">I didn't say this was useful and I have had no reason to ever use it.</span></span>

### <a name="where-to-place-it"></a><span data-ttu-id="52554-177">どこに配置するか</span><span class="sxs-lookup"><span data-stu-id="52554-177">Where to place it</span></span>

<span data-ttu-id="52554-178">`ShouldProcess` を使用するのは、スクリプトの安全性を高めるためです。</span><span class="sxs-lookup"><span data-stu-id="52554-178">You use `ShouldProcess` to make your scripts safer.</span></span> <span data-ttu-id="52554-179">そのため、スクリプトで変更を行うときに使用します。</span><span class="sxs-lookup"><span data-stu-id="52554-179">So you use it when your scripts are making changes.</span></span> <span data-ttu-id="52554-180">`$PSCmdlet.ShouldProcess` の呼び出しをできるだけ変更の近くに配置するのが良いでしょう。</span><span class="sxs-lookup"><span data-stu-id="52554-180">I like to place the `$PSCmdlet.ShouldProcess` call as close to the change as possible.</span></span>

```powershell
## general logic and variable work
if ($PSCmdlet.ShouldProcess('TARGET','OPERATION')){
    # Change goes here
}
```

<span data-ttu-id="52554-181">項目のコレクションを処理する場合は、項目ごとに呼び出します。</span><span class="sxs-lookup"><span data-stu-id="52554-181">If I'm processing a collection of items, I call it for each item.</span></span> <span data-ttu-id="52554-182">そのため、この呼び出しは foreach ループ内に配置されます。</span><span class="sxs-lookup"><span data-stu-id="52554-182">So the call gets placed inside the foreach loop.</span></span>

```powershell
foreach ($node in $collection){
    # general logic and variable work
    if ($PSCmdlet.ShouldProcess($node,'OPERATION')){
        # Change goes here
    }
}
```

<span data-ttu-id="52554-183">`ShouldProcess` を変更のなるべく近くに配置する理由は、`-WhatIf` が指定されたときに、可能な限り多くのコードを実行したいためです。</span><span class="sxs-lookup"><span data-stu-id="52554-183">The reason why I place `ShouldProcess` tightly around the change, is that I want as much code to execute as possible when `-WhatIf` is specified.</span></span> <span data-ttu-id="52554-184">可能であればセットアップと検証を実行して、ユーザーがこれらのエラーを確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="52554-184">I want the setup and validation to run if possible so the user gets to see those errors.</span></span>

<span data-ttu-id="52554-185">また、プロジェクトを検証する Pester テストでこれを使用することもお勧めです。</span><span class="sxs-lookup"><span data-stu-id="52554-185">I also like to use this in my Pester tests that validate my projects.</span></span> <span data-ttu-id="52554-186">Pester でモックを作成するのが難しいロジックがある場合、多くの場合、それを `ShouldProcess` にラップして、テストで `-WhatIf` を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="52554-186">If I have a piece of logic that is hard to mock in pester, I can often wrap it in `ShouldProcess` and call it with `-WhatIf` in my tests.</span></span> <span data-ttu-id="52554-187">少なくともコードの一部をテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="52554-187">It's better to test some of your code than none of it.</span></span>

### <a name="whatifpreference"></a><span data-ttu-id="52554-188">$WhatIfPreference</span><span class="sxs-lookup"><span data-stu-id="52554-188">$WhatIfPreference</span></span>

<span data-ttu-id="52554-189">最初のユーザー設定変数は `$WhatIfPreference` です。</span><span class="sxs-lookup"><span data-stu-id="52554-189">The first preference variable we have is `$WhatIfPreference`.</span></span> <span data-ttu-id="52554-190">これは既定では `$false` です。</span><span class="sxs-lookup"><span data-stu-id="52554-190">This is `$false` by default.</span></span> <span data-ttu-id="52554-191">`$true` に設定した場合は、`-WhatIf` を指定したかのように関数が実行されます。</span><span class="sxs-lookup"><span data-stu-id="52554-191">If you set it to `$true` then your function executes as if you specified `-WhatIf`.</span></span> <span data-ttu-id="52554-192">セッションでこれを設定した場合、すべてのコマンドで `-WhatIf` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="52554-192">If you set this in your session, all commands perform `-WhatIf` execution.</span></span>

<span data-ttu-id="52554-193">`-WhatIf` を指定して関数を呼び出すと、関数のスコープ内で `$WhatIfPreference` の値が `$true` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="52554-193">When you call a function with `-WhatIf`, the value of `$WhatIfPreference` gets set to `$true` inside the scope of your function.</span></span>

## <a name="confirmimpact"></a><span data-ttu-id="52554-194">ConfirmImpact</span><span class="sxs-lookup"><span data-stu-id="52554-194">ConfirmImpact</span></span>

<span data-ttu-id="52554-195">この例のほとんどは `-WhatIf` を対象としていますが、これまでのすべての例は `-Confirm` でも機能し、ユーザーにメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="52554-195">Most of my examples are for `-WhatIf` but everything so far also works with `-Confirm` to prompt the user.</span></span> <span data-ttu-id="52554-196">関数の `ConfirmImpact` を High に設定すると、`-Confirm` で呼び出されたかのようにユーザーにプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52554-196">You can set the `ConfirmImpact` of the function to high and it prompts the user as if it was called with `-Confirm`.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param()

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="52554-197">この `Test-ShouldProcess` の呼び出しでは、`High` の影響によって `-Confirm` アクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="52554-197">This call to `Test-ShouldProcess` is performing the `-Confirm` action because of the `High` impact.</span></span>

```powershell
PS> Test-ShouldProcess

Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "TARGET".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
Some Action
```

<span data-ttu-id="52554-198">明らかな問題は、ユーザーにプロンプトを表示することなく他のスクリプトで使用するのが困難になることです。</span><span class="sxs-lookup"><span data-stu-id="52554-198">The obvious issue is that now it's harder to use in other scripts without prompting the user.</span></span> <span data-ttu-id="52554-199">この場合は、`-Confirm` に `$false` を渡して、プロンプトを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="52554-199">In this case, we can pass a `$false` to `-Confirm` to suppress the prompt.</span></span>

```powershell
PS> Test-ShouldProcess -Confirm:$false
Some Action
```

<span data-ttu-id="52554-200">`-Force` サポートを追加する方法については、後のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="52554-200">I'll cover how to add `-Force` support in a later section.</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="52554-201">$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="52554-201">$ConfirmPreference</span></span>

<span data-ttu-id="52554-202">`$ConfirmPreference` は、`ConfirmImpact` によりユーザーにいつ実行の確認を求めるかを制御する自動変数です。</span><span class="sxs-lookup"><span data-stu-id="52554-202">`$ConfirmPreference` is an automatic variable that controls when `ConfirmImpact` asks you to confirm execution.</span></span> <span data-ttu-id="52554-203">`$ConfirmPreference` と `ConfirmImpact` の両方で使用可能な値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="52554-203">Here are the possible values for both `$ConfirmPreference` and `ConfirmImpact`.</span></span>

- `High`
- `Medium`
- `Low`
- `None`

<span data-ttu-id="52554-204">これらの値を使用すると、関数ごとに異なるレベルの影響を指定できます。</span><span class="sxs-lookup"><span data-stu-id="52554-204">With these values, you can specify different levels of impact for each function.</span></span> <span data-ttu-id="52554-205">`$ConfirmPreference` を `ConfirmImpact` よりも高い値に設定した場合、実行の確認を求めるプロンプトが表示されません。</span><span class="sxs-lookup"><span data-stu-id="52554-205">If you have `$ConfirmPreference` set to a value higher than `ConfirmImpact`, then you aren't prompted to confirm execution.</span></span>

<span data-ttu-id="52554-206">既定では、`$ConfirmPreference` は `High` に、`ConfirmImpact` は `Medium` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="52554-206">By default, `$ConfirmPreference` is set to `High` and `ConfirmImpact` is `Medium`.</span></span> <span data-ttu-id="52554-207">関数でユーザーに自動的にプロンプトが表示されるようにするには、`ConfirmImpact` を `High` に設定します。</span><span class="sxs-lookup"><span data-stu-id="52554-207">If you want your function to automatically prompt the user, set your `ConfirmImpact` to `High`.</span></span> <span data-ttu-id="52554-208">それ以外の場合、破壊的な場合は `Medium` に設定し、コマンドが常に運用環境で安全に実行されている場合は `Low` に設定します。</span><span class="sxs-lookup"><span data-stu-id="52554-208">Otherwise set it to `Medium` if its destructive and use `Low` if the command is always safe run in production.</span></span> <span data-ttu-id="52554-209">`none` に設定すると、`-Confirm` が指定されている場合でもプロンプトは表示されません (ただし、`-WhatIf` は引き続きサポートされます)。</span><span class="sxs-lookup"><span data-stu-id="52554-209">If you set it to `none`, it doesn't prompt even if `-Confirm` was specified (but it still gives you `-WhatIf` support).</span></span>

<span data-ttu-id="52554-210">`-Confirm` を指定して関数を呼び出すと、関数のスコープ内で `$ConfirmPreference` の値が `Low` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="52554-210">When calling a function with `-Confirm`, the value of `$ConfirmPreference` gets set to `Low` inside the scope of your function.</span></span>

### <a name="suppressing-nested-confirm-prompts"></a><span data-ttu-id="52554-211">入れ子になった確認プロンプトの抑制</span><span class="sxs-lookup"><span data-stu-id="52554-211">Suppressing nested confirm prompts</span></span>

<span data-ttu-id="52554-212">`$ConfirmPreference` は、呼び出す関数によって取得できます。</span><span class="sxs-lookup"><span data-stu-id="52554-212">The `$ConfirmPreference` can get picked up by functions that you call.</span></span> <span data-ttu-id="52554-213">これにより、確認プロンプトを追加したときに、呼び出した関数によってもユーザーにプロンプトが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="52554-213">This can create scenarios where you add a confirm prompt and the function you call also prompts the user.</span></span>

<span data-ttu-id="52554-214">よくある手法としては、プロンプトを既に処理しているときに呼び出すコマンドに `-Confirm:$false` を指定します。</span><span class="sxs-lookup"><span data-stu-id="52554-214">What I tend to do is specify `-Confirm:$false` on the commands that I call when I have already handled the prompting.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        Remove-Item -Path $file.FullName -Confirm:$false
    }
}
```

<span data-ttu-id="52554-215">ここで、前に説明した警告に戻ります。`-WhatIf` が関数に渡されない場合と、`-Confirm` が関数に渡される場合には、微妙な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="52554-215">This brings us back to an earlier warning: There are nuances as to when `-WhatIf` is not passed to a function and when `-Confirm` passes to a function.</span></span> <span data-ttu-id="52554-216">これについては後で説明します。</span><span class="sxs-lookup"><span data-stu-id="52554-216">I promise I'll get back to this later.</span></span>

## <a name="pscmdletshouldcontinue"></a><span data-ttu-id="52554-217">$PSCmdlet.ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="52554-217">$PSCmdlet.ShouldContinue</span></span>

<span data-ttu-id="52554-218">`ShouldProcess` よりも多くの制御が必要な場合は、`ShouldContinue` を使用してプロンプトを直接トリガーできます。</span><span class="sxs-lookup"><span data-stu-id="52554-218">If you need more control than `ShouldProcess` provides, you can trigger the prompt directly with `ShouldContinue`.</span></span> <span data-ttu-id="52554-219">`ShouldContinue` では、実行されるたびにプロンプトが表示されるので、`$ConfirmPreference`、`ConfirmImpact`、`-Confirm`、`$WhatIfPreference`、および `-WhatIf` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="52554-219">`ShouldContinue` ignores `$ConfirmPreference`, `ConfirmImpact`, `-Confirm`, `$WhatIfPreference`, and `-WhatIf` because it prompts every time it's executed.</span></span>

<span data-ttu-id="52554-220">一見すると、`ShouldProcess` と `ShouldContinue` は混同しがちです。</span><span class="sxs-lookup"><span data-stu-id="52554-220">At a quick glance, it's easy to confuse `ShouldProcess` and `ShouldContinue`.</span></span> <span data-ttu-id="52554-221">パラメーター名は `CmdletBinding` で `SupportsShouldProcess` であるため、`ShouldProcess` を使用するように記憶する傾向があります。</span><span class="sxs-lookup"><span data-stu-id="52554-221">I tend to remember to use `ShouldProcess` because the parameter is called `SupportsShouldProcess` in the `CmdletBinding`.</span></span>
<span data-ttu-id="52554-222">ほとんどすべてのシナリオでは `ShouldProcess` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52554-222">You should use `ShouldProcess` in almost every scenario.</span></span> <span data-ttu-id="52554-223">そのため、最初にその方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="52554-223">That is why I covered that method first.</span></span>

<span data-ttu-id="52554-224">`ShouldContinue` の動作について見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="52554-224">Let's take a look at `ShouldContinue` in action.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    if($PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="52554-225">これは、より少ないオプションの簡単なプロンプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="52554-225">This provides us a simpler prompt with fewer options.</span></span>

```powershell
Test-ShouldContinue

Second
TARGET
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="52554-226">`ShouldContinue` の最大の問題は、常にユーザーにプロンプトが表示されるため、ユーザーが対話形式で実行する必要があることです。</span><span class="sxs-lookup"><span data-stu-id="52554-226">The biggest issue with `ShouldContinue` is that it requires the user to run it interactively because it always prompts the user.</span></span> <span data-ttu-id="52554-227">他のスクリプトで使用できるツールを常に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="52554-227">You should always be building tools that can be used by other scripts.</span></span> <span data-ttu-id="52554-228">その方法は、`-Force` を実装することです。</span><span class="sxs-lookup"><span data-stu-id="52554-228">The way you do this is by implementing `-Force`.</span></span> <span data-ttu-id="52554-229">このアイデアについては後で説明します。</span><span class="sxs-lookup"><span data-stu-id="52554-229">I'll revisit this idea later.</span></span>

### <a name="yes-to-all"></a><span data-ttu-id="52554-230">すべてはい</span><span class="sxs-lookup"><span data-stu-id="52554-230">Yes to all</span></span>

<span data-ttu-id="52554-231">これは `ShouldProcess` では自動的に処理されますが、`ShouldContinue` については多少の処理が必要になります。</span><span class="sxs-lookup"><span data-stu-id="52554-231">This is automatically handled with `ShouldProcess` but we have to do a little more work for `ShouldContinue`.</span></span> <span data-ttu-id="52554-232">ロジックを制御するために参照渡しによっていくつかの値を渡す必要がある 2 番目のメソッド オーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="52554-232">There's a second method overload where we have to pass in a few values by reference to control the logic.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    $collection = 1..5
    $yesToAll = $false
    $noToAll = $false

    foreach($target in $collection) {

        $continue = $PSCmdlet.ShouldContinue(
                "TARGET_$target",
                'OPERATION',
                [ref]$yesToAll,
                [ref]$noToAll
            )

        if ($continue){
            Write-Output "Some Action [$target]"
        }
    }
}
```

<span data-ttu-id="52554-233">`foreach` ループとコレクションを追加して、その動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="52554-233">I added a `foreach` loop and a collection to show it in action.</span></span> <span data-ttu-id="52554-234">読みやすくするために、`if` ステートメントから `ShouldContinue` 呼び出しを抜き出してあります。</span><span class="sxs-lookup"><span data-stu-id="52554-234">I pulled the `ShouldContinue` call out of the `if` statement to make it easier to read.</span></span> <span data-ttu-id="52554-235">4 つのパラメーターを使用してメソッドを呼び出すと、少し見にくくなりますが、できる限り見やすい状態にしてあります。</span><span class="sxs-lookup"><span data-stu-id="52554-235">Calling a method with four parameters starts to get a little ugly, but I tried to make it look as clean as I could.</span></span>

## <a name="implementing--force"></a><span data-ttu-id="52554-236">-Force の実装</span><span class="sxs-lookup"><span data-stu-id="52554-236">Implementing -Force</span></span>

<span data-ttu-id="52554-237">`ShouldProcess` と `ShouldContinue` では、`-Force` を異なる方法で実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52554-237">`ShouldProcess` and `ShouldContinue` need to implement `-Force` in different ways.</span></span> <span data-ttu-id="52554-238">これらの実装に対する注意点として、`ShouldProcess` は常に実行される必要がありますが、`-Force` が指定されている場合 `ShouldContinue` は実行してはなりません。</span><span class="sxs-lookup"><span data-stu-id="52554-238">The trick to these implementations is that `ShouldProcess` should always get executed, but `ShouldContinue` should not get executed if `-Force` is specified.</span></span>

### <a name="shouldprocess--force"></a><span data-ttu-id="52554-239">ShouldProcess -Force</span><span class="sxs-lookup"><span data-stu-id="52554-239">ShouldProcess -Force</span></span>

<span data-ttu-id="52554-240">`ConfirmImpact` を `high` に設定した場合、ユーザーが最初に試みるのは、`-Force` を使用してそれを抑制することです。</span><span class="sxs-lookup"><span data-stu-id="52554-240">If you set your `ConfirmImpact` to `high`, the first thing your users are going to try is to suppress it with `-Force`.</span></span> <span data-ttu-id="52554-241">まずはそれを実行してみましょう。</span><span class="sxs-lookup"><span data-stu-id="52554-241">That's the first thing I do anyway.</span></span>

```powershell
Test-ShouldProcess -Force
Error: Test-ShouldProcess: A parameter cannot be found that matches parameter name 'force'.
```

<span data-ttu-id="52554-242">`ConfirmImpact` のセクションで説明したように、実際には次のように呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="52554-242">If you recall from the `ConfirmImpact` section, they actually need to call it like this:</span></span>

```powershell
Test-ShouldProcess -Confirm:$false
```

<span data-ttu-id="52554-243">これを行う必要があることに気が付かない人もおり、また `-Confirm:$false` により `ShouldContinue` は抑制されません。</span><span class="sxs-lookup"><span data-stu-id="52554-243">Not everyone realizes they need to do that and `-Confirm:$false` doesn't suppress `ShouldContinue`.</span></span>
<span data-ttu-id="52554-244">そのため、ユーザーのために `-Force` を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52554-244">So we should implement `-Force` for the sanity of our users.</span></span> <span data-ttu-id="52554-245">次の完全な例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="52554-245">Take a look at this full example here:</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param(
        [Switch]$Force
    )

    if ($Force -and -not $Confirm){
        $ConfirmPreference = 'None'
    }

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="52554-246">独自の `-Force` スイッチをパラメーターとして追加し、`CmdletBinding` に `SupportsShouldProcess` を追加するときに使用できる `$Confirm` 自動パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="52554-246">We add our own `-Force` switch as a parameter and use the `$Confirm` automatic parameter that is available when adding `SupportsShouldProcess` in the `CmdletBinding`.</span></span>

```powershell
[CmdletBinding(
    SupportsShouldProcess,
    ConfirmImpact = 'High'
)]
param(
    [Switch]$Force
)
```

<span data-ttu-id="52554-247">ここでは、`-Force` ロジックに焦点を絞っています。</span><span class="sxs-lookup"><span data-stu-id="52554-247">Focusing in on the `-Force` logic here:</span></span>

```powershell
if ($Force -and -not $Confirm){
    $ConfirmPreference = 'None'
}
```

<span data-ttu-id="52554-248">ユーザーが `-Force` を指定した場合は、`-Confirm` も指定されていない限り、確認プロンプトを抑制します。</span><span class="sxs-lookup"><span data-stu-id="52554-248">If the user specifies `-Force`, we want to suppress the confirm prompt unless they also specify `-Confirm`.</span></span> <span data-ttu-id="52554-249">これにより、ユーザーは変更を強制することができますが、引き続き変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="52554-249">This allows a user to force a change but still confirm the change.</span></span> <span data-ttu-id="52554-250">次に、ローカル スコープで `$ConfirmPreference` を設定します。これにより、`ShouldProcess` の呼び出しでこれが検出されます。</span><span class="sxs-lookup"><span data-stu-id="52554-250">Then we set `$ConfirmPreference` in the local scope where our call to `ShouldProcess` discoverers it.</span></span>

```powershell
if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
```

<span data-ttu-id="52554-251">`-Force` と `-WhatIf` の両方が指定されている場合は、`-WhatIf` を優先する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52554-251">If someone specifies both `-Force` and `-WhatIf`, then `-WhatIf` needs to take priority.</span></span> <span data-ttu-id="52554-252">この方法では、`ShouldProcess` が常に実行されるため、`-WhatIf` の処理が保持されます。</span><span class="sxs-lookup"><span data-stu-id="52554-252">This approach preserves `-WhatIf` processing because `ShouldProcess` always gets executed.</span></span>

<span data-ttu-id="52554-253">`ShouldProcess` を含む if ステートメントの中に `$Force` 値のチェックを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="52554-253">Do not add a check for the `$Force` value inside the if statement with the `ShouldProcess`.</span></span> <span data-ttu-id="52554-254">これは、この特定のシナリオの場合のアンチパターンですが、次のセクションの `ShouldContinue` でこれについて説明します。</span><span class="sxs-lookup"><span data-stu-id="52554-254">That is an anti-pattern for this specific scenario even though that's what I show you in the next section for `ShouldContinue`.</span></span>

### <a name="shouldcontinue--force"></a><span data-ttu-id="52554-255">ShouldContinue -Force</span><span class="sxs-lookup"><span data-stu-id="52554-255">ShouldContinue -Force</span></span>

<span data-ttu-id="52554-256">これは、`ShouldContinue` で `-Force` を実装するための正しい方法です。</span><span class="sxs-lookup"><span data-stu-id="52554-256">This is the correct way to implement `-Force` with `ShouldContinue`.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param(
        [Switch]$Force
    )

    if($Force -or $PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="52554-257">`-or` 演算子の左側に `$Force` を配置することで、最初に評価が行われます。</span><span class="sxs-lookup"><span data-stu-id="52554-257">By placing the `$Force` to the left of the `-or` operator, it gets evaluated first.</span></span> <span data-ttu-id="52554-258">このように記述すると、`if` ステートメントの実行を省くことができます。</span><span class="sxs-lookup"><span data-stu-id="52554-258">Writing it this way short circuits the execution of the `if` statement.</span></span> <span data-ttu-id="52554-259">`$force` が `$true` の場合、`ShouldContinue` は実行されません。</span><span class="sxs-lookup"><span data-stu-id="52554-259">If `$force` is `$true`, then the `ShouldContinue` is not executed.</span></span>

```powershell
PS> Test-ShouldContinue -Force
Some Action
```

<span data-ttu-id="52554-260">このシナリオでは `-Confirm` や `-WhatIf` について考慮する必要はありません。なぜなら、これらは `ShouldContinue` でサポートされていないためです。</span><span class="sxs-lookup"><span data-stu-id="52554-260">We don't have to worry about `-Confirm` or `-WhatIf` in this scenario because they're not supported by `ShouldContinue`.</span></span> <span data-ttu-id="52554-261">このため、`ShouldProcess` とは異なる方法で処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52554-261">This is why it needs to be handled differently than `ShouldProcess`.</span></span>

## <a name="scope-issues"></a><span data-ttu-id="52554-262">スコープの問題</span><span class="sxs-lookup"><span data-stu-id="52554-262">Scope issues</span></span>

<span data-ttu-id="52554-263">`-WhatIf` と `-Confirm` の使用は、関数内のすべて、およびそれらが呼び出すすべてに適用することが想定されています。</span><span class="sxs-lookup"><span data-stu-id="52554-263">Using `-WhatIf` and `-Confirm` are supposed to apply to everything inside your functions and everything they call.</span></span> <span data-ttu-id="52554-264">これを行うには、関数のローカル スコープ内で `$WhatIfPreference` を `$true` に、または `$ConfirmPreference` を`Low` に設定します。</span><span class="sxs-lookup"><span data-stu-id="52554-264">They do this by setting `$WhatIfPreference` to `$true` or setting `$ConfirmPreference` to `Low` in the local scope of the function.</span></span> <span data-ttu-id="52554-265">別の関数を呼び出すと、`ShouldProcess` の呼び出しでそれらの値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="52554-265">When you call another function, calls to `ShouldProcess` use those values.</span></span>

<span data-ttu-id="52554-266">これは、ほとんどの場合、実際に正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="52554-266">This actually works correctly most of the time.</span></span> <span data-ttu-id="52554-267">組み込みのコマンドレットまたは関数を同じスコープ内で呼び出すときは、いつでも機能します。</span><span class="sxs-lookup"><span data-stu-id="52554-267">Anytime you call built-in cmdlet or a function in your same scope, it works.</span></span> <span data-ttu-id="52554-268">また、コンソールからスクリプト モジュール内のスクリプトまたは関数を呼び出す場合にも機能します。</span><span class="sxs-lookup"><span data-stu-id="52554-268">It also works when you call a script or a function in a script module from the console.</span></span>

<span data-ttu-id="52554-269">これが動作しない特定の場合は、スクリプトまたはスクリプト モジュールが別のスクリプト モジュールの関数を呼び出す場合です。</span><span class="sxs-lookup"><span data-stu-id="52554-269">The one specific place where it doesn't work is when a script or a script module calls a function in another script module.</span></span> <span data-ttu-id="52554-270">これは大きな問題でないように感じるかもしれませんが、PSGallery から作成したりプルしたりするモジュールのほとんどは、スクリプト モジュールです。</span><span class="sxs-lookup"><span data-stu-id="52554-270">This may not sound like a big problem, but most of the modules you create or pull from the PSGallery are script modules.</span></span>

<span data-ttu-id="52554-271">主な問題は、スクリプト モジュールは、他のスクリプト モジュールの関数から呼び出されたときに、`$WhatIfPreference` および `$ConfirmPreference` (またその他いくつか) の値を継承しないことです。</span><span class="sxs-lookup"><span data-stu-id="52554-271">The core issue is that script modules do not inherit the values for `$WhatIfPreference` or `$ConfirmPreference` (and several others) when called from functions in other script modules.</span></span>

<span data-ttu-id="52554-272">これを一般的な規則としてうまくまとめると、バイナリ モジュールに対しては正しく機能するが、スクリプト モジュールの場合は決して信頼しないことです。</span><span class="sxs-lookup"><span data-stu-id="52554-272">The best way to summarize this as a general rule is that this works correctly for binary modules and never trust it to work for script modules.</span></span> <span data-ttu-id="52554-273">確信がない場合は、テストするか、正しく動作しないと想定してください。</span><span class="sxs-lookup"><span data-stu-id="52554-273">If you aren't sure, either test it or just assume it doesn't work correctly.</span></span>

<span data-ttu-id="52554-274">これは、分離されていると正しく動作する複数のモジュールに `-WhatIf` サポートを追加し、これらが互いを呼び出すと正しく機能しないというシナリオが発生するため、非常に危険です。</span><span class="sxs-lookup"><span data-stu-id="52554-274">I personally feel this is very dangerous because it creates scenarios where you add `-WhatIf` support to multiple modules that work correctly in isolation, but fail to work correctly when they call each other.</span></span>

<span data-ttu-id="52554-275">この問題を解決するために、GitHub の RFC が存在します。</span><span class="sxs-lookup"><span data-stu-id="52554-275">We do have a GitHub RFC working to get this issue fixed.</span></span> <span data-ttu-id="52554-276">詳細については、[スクリプト モジュールのスコープを超えた実行設定の伝達][RFC]に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52554-276">See [Propagate execution preferences beyond script module scope][RFC] for more details.</span></span>

## <a name="in-closing"></a><span data-ttu-id="52554-277">最後に</span><span class="sxs-lookup"><span data-stu-id="52554-277">In closing</span></span>

<span data-ttu-id="52554-278">`ShouldProcess` 使用する必要があるたびに、その使用方法を確認する必要あります。</span><span class="sxs-lookup"><span data-stu-id="52554-278">I have to look up how to use `ShouldProcess` every time I need to use it.</span></span> <span data-ttu-id="52554-279">`ShouldProcess` と `ShouldContinue` を区別するために長い時間がかかりました。</span><span class="sxs-lookup"><span data-stu-id="52554-279">It took me a long time to distinguish `ShouldProcess` from `ShouldContinue`.</span></span> <span data-ttu-id="52554-280">ほとんどの場合、使用するパラメーターを調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="52554-280">I almost always need to look up what parameters to use.</span></span> <span data-ttu-id="52554-281">混乱することがあってもあまり気にしないでください。</span><span class="sxs-lookup"><span data-stu-id="52554-281">So don't worry if you still get confused from time to time.</span></span> <span data-ttu-id="52554-282">必要なときには、この記事がここにあります。</span><span class="sxs-lookup"><span data-stu-id="52554-282">This article will be here when you need it.</span></span> <span data-ttu-id="52554-283">私自身も頻繁にこれを参照することになるでしょう。</span><span class="sxs-lookup"><span data-stu-id="52554-283">I'm sure I will reference it often myself.</span></span>

<span data-ttu-id="52554-284">この投稿を気にっていただけた場合は、以下のリンクを使用して、Twitter でご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="52554-284">If you liked this post, please share your thoughts with me on Twitter using the link below.</span></span> <span data-ttu-id="52554-285">コンテンツの価値を評価していただける方からのご意見は常に歓迎いたします。</span><span class="sxs-lookup"><span data-stu-id="52554-285">I always like hearing from people that get value from my content.</span></span>

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[original version]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[共通パラメーター]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[common parameters]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[ハッシュテーブルについて知りたかったことのすべて]: everything-about-hashtable.md
[everything you wanted to know about hashtables]: everything-about-hashtable.md
[RFC]: https://github.com/PowerShell/PowerShell-RFC/pull/221#issuecomment-592954839

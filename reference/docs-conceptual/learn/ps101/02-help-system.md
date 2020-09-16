---
title: ヘルプ システム
description: ヘルプ システムを使いこなすことは、PowerShell を使って成功するための鍵です。
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 8325a32ad8ec137781300e9d46cab52705f0805a
ms.sourcegitcommit: eaac7af89171379df2e20464ebee9fc7e7d7674a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89493659"
---
# <a name="chapter-2---the-help-system"></a><span data-ttu-id="51662-103">第 2 章 - ヘルプ システム</span><span class="sxs-lookup"><span data-stu-id="51662-103">Chapter 2 - The Help System</span></span>

<span data-ttu-id="51662-104">IT プロフェッショナルの 2 つのグループを対象に、PowerShell のスキル レベルを判断するための筆記テストを実施しました。このテストは、コンピューターは使用せずに行われ、</span><span class="sxs-lookup"><span data-stu-id="51662-104">Two groups of IT pros were given a written test without access to a computer to determine their skill level with PowerShell.</span></span> <span data-ttu-id="51662-105">対象グループの一方は PowerShell 初心者、もう一方はエキスパートで構成されていました。</span><span class="sxs-lookup"><span data-stu-id="51662-105">PowerShell beginners were placed in one group and experts in another.</span></span>
<span data-ttu-id="51662-106">このテスト結果では、2 つのグループのスキル レベルに大きな違いはないように見えました。</span><span class="sxs-lookup"><span data-stu-id="51662-106">Based on the results of the test, there didn't seem to be much difference in the skill level between the two groups.</span></span> <span data-ttu-id="51662-107">その後、両方のグループに 2 回目のテストを実施しました。前回のテストと内容は似ていますが、</span><span class="sxs-lookup"><span data-stu-id="51662-107">Both groups were given a second test similar to the first one.</span></span> <span data-ttu-id="51662-108">今回はテスト中に、インターネットにアクセスできない PowerShell が搭載されたコンピューターを使うことができました。</span><span class="sxs-lookup"><span data-stu-id="51662-108">This time they were given access to a computer with PowerShell that didn't have access to the internet.</span></span> <span data-ttu-id="51662-109">2 回目のテストの結果では、2 つのグループのスキル レベルの差は歴然としていました。</span><span class="sxs-lookup"><span data-stu-id="51662-109">The results of the second test showed a huge difference in the skill level between the two groups.</span></span> <span data-ttu-id="51662-110">エキスパートは必ずしも答えを知っているわけではありません。しかし、答えを導き出す手段がわかっているのです。</span><span class="sxs-lookup"><span data-stu-id="51662-110">Experts don't always know the answers, but they know how to figure out the answers.</span></span>

<span data-ttu-id="51662-111">2 つのグループの最初のテストと 2 番目のテストの結果の違いは何だったのでしょう。</span><span class="sxs-lookup"><span data-stu-id="51662-111">What was the difference in the results of the first and second test between these two groups?</span></span>

<span data-ttu-id="51662-112">2 つのテストの結果に違いが出た原因は、エキスパートが、PowerShell で何千ものコマンドを使用する方法を丸暗記していないからです。</span><span class="sxs-lookup"><span data-stu-id="51662-112">The differences observed in these two tests were because experts don't memorize how to use thousands of commands in PowerShell.</span></span> <span data-ttu-id="51662-113">エキスパートは、PowerShell のヘルプ システムを使用する方法について、よくわかっています。</span><span class="sxs-lookup"><span data-stu-id="51662-113">They learn how to use the help system within PowerShell extremely well.</span></span>
<span data-ttu-id="51662-114">だから、必要なときに必要なコマンドを見つけ、コマンドが見つかったら、そのコマンドの使用方法を見つけることができるのです。</span><span class="sxs-lookup"><span data-stu-id="51662-114">This allows them to find the necessary commands when needed and how to use those commands once they've found them.</span></span>

<span data-ttu-id="51662-115">PowerShell の発明者 Jeffrey Snover が同じようなことを話しているのを、私は幾度となく聞いています。</span><span class="sxs-lookup"><span data-stu-id="51662-115">I've heard Jeffrey Snover, the inventor of PowerShell, tell a similar story a number of times.</span></span>

<span data-ttu-id="51662-116">ヘルプ システムを使いこなすことは、PowerShell を使って成功するための鍵です。</span><span class="sxs-lookup"><span data-stu-id="51662-116">Mastering the help system is the key to being successful with PowerShell.</span></span>

## <a name="discoverability"></a><span data-ttu-id="51662-117">Discoverability (探索可能性)</span><span class="sxs-lookup"><span data-stu-id="51662-117">Discoverability</span></span>

<span data-ttu-id="51662-118">PowerShell のコンパイルされたコマンドはコマンドレットと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="51662-118">Compiled commands in PowerShell are called cmdlets.</span></span> <span data-ttu-id="51662-119">コマンドレットは、"command-let" と発音します (CMD let ではありません)。</span><span class="sxs-lookup"><span data-stu-id="51662-119">Cmdlet is pronounced "command-let" (not CMD-let).</span></span> <span data-ttu-id="51662-120">コマンドレット名は、検出しやすいように、単数形の "動詞-名詞" コマンドの形式になっています。</span><span class="sxs-lookup"><span data-stu-id="51662-120">Cmdlets names have the form of singular "Verb-Noun" commands to make them easily discoverable.</span></span> <span data-ttu-id="51662-121">たとえば、実行中のプロセスを確認するためのコマンドレットは `Get-Process`、サービスの一覧とその状態を取得するためのコマンドレットは `Get-Service` です。</span><span class="sxs-lookup"><span data-stu-id="51662-121">For example, the cmdlet for determining what processes are running is `Get-Process` and the cmdlet for retrieving a list of services and their statuses is `Get-Service`.</span></span> <span data-ttu-id="51662-122">本書で後述しますが、PowerShell には、エイリアス、関数など、他の種類のコマンドもあります。</span><span class="sxs-lookup"><span data-stu-id="51662-122">There are other types of commands in PowerShell such as aliases and functions that will be covered later in this book.</span></span> <span data-ttu-id="51662-123">PowerShell コマンドという用語は、それがコマンドレット、関数、エイリアスかどうかに関係なく、PowerShell のすべての種類のコマンドを意味する一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="51662-123">The term PowerShell command is a generic term that's often used to refer to any type of command in PowerShell, regardless of whether or not it's a cmdlet, function, or alias.</span></span>

## <a name="the-three-core-cmdlets-in-powershell"></a><span data-ttu-id="51662-124">PowerShell の 3 つのコア コマンドレット</span><span class="sxs-lookup"><span data-stu-id="51662-124">The Three Core Cmdlets in PowerShell</span></span>

- `Get-Command`
- `Get-Help`
- <span data-ttu-id="51662-125">`Get-Member` (第 3 章で説明)</span><span class="sxs-lookup"><span data-stu-id="51662-125">`Get-Member` (covered in chapter 3)</span></span>

<span data-ttu-id="51662-126">よく聞かれるのが、PowerShell で使用するコマンドを判断する方法です。</span><span class="sxs-lookup"><span data-stu-id="51662-126">One question I'm often asked is how do you figure out what the commands are in PowerShell?</span></span> <span data-ttu-id="51662-127">コマンドの決定には、`Get-Command` と `Get-Help` の両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="51662-127">Both `Get-Command` and `Get-Help` can be used to determine the commands.</span></span>

## <a name="get-help"></a><span data-ttu-id="51662-128">Get-Help</span><span class="sxs-lookup"><span data-stu-id="51662-128">Get-Help</span></span>

<span data-ttu-id="51662-129">`Get-Help` は多目的コマンドです。</span><span class="sxs-lookup"><span data-stu-id="51662-129">`Get-Help` is a multipurpose command.</span></span> <span data-ttu-id="51662-130">`Get-Help` は、コマンドを見つけた後に、そのコマンドの使用方法を確認するうえで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51662-130">`Get-Help` helps you learn how to use commands once you find them.</span></span> <span data-ttu-id="51662-131">`Get-Help` を使ってコマンドを特定することもできますが、`Get-Command` とは異なり、このコマンドと比べるとより間接的です。</span><span class="sxs-lookup"><span data-stu-id="51662-131">`Get-Help` can also be used to help locate commands, but in a different and more indirect way when compared to `Get-Command`.</span></span>

<span data-ttu-id="51662-132">`Get-Help` を使用してコマンドを検索すると、まず入力内容に基づいて、コマンド名のワイルドカード一致が検索されます。</span><span class="sxs-lookup"><span data-stu-id="51662-132">When `Get-Help` is used to locate commands, it first searches for wildcard matches of command names based on the provided input.</span></span> <span data-ttu-id="51662-133">一致するものが見つからないと、ヘルプ トピックが検索され、そこで一致するものが見つからないと、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="51662-133">If it doesn't find a match, it searches through the help topics themselves, and if no match is found an error is returned.</span></span> <span data-ttu-id="51662-134">一般的な考えに反して、`Get-Help` を使って、ヘルプ トピックのないコマンドを見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="51662-134">Contrary to popular belief, `Get-Help` can be used to find commands that don't have help topics.</span></span>

<span data-ttu-id="51662-135">PowerShell のヘルプ システムでまず知っておく必要があるのが、`Get-Help` コマンドレットを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="51662-135">The first thing you need to know about the help system in PowerShell is how to use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="51662-136">次のコマンドを使用すると、`Get-Help` のヘルプ トピックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51662-136">The following command is used to display the help topic for `Get-Help`.</span></span>

```powershell
Get-Help -Name Get-Help
```

```Output
Do you want to run Update-Help?
The Update-Help cmdlet downloads the most current Help files for Windows PowerShell
modules, and installs them on your computer. For more information about the Update-Help
cmdlet, see http://go.microsoft.com/fwlink/?LinkId=210614.
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="51662-137">PowerShell バージョン 3 以降、PowerShell ヘルプはオペレーティング システムに付属していません。</span><span class="sxs-lookup"><span data-stu-id="51662-137">Beginning with PowerShell version 3, PowerShell help doesn't ship with the operating system.</span></span> <span data-ttu-id="51662-138">コマンドに対して初めて `Get-Help` を実行すると、このメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51662-138">The first time `Get-Help` is run for a command, the previous message is displayed.</span></span> <span data-ttu-id="51662-139">`Get-Help` コマンドレットではなく `help` 関数または `man` エイリアスを使用すると、このプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="51662-139">If the `help` function or `man` alias is used instead of the `Get-Help` cmdlet, you don't receive this prompt.</span></span>

<span data-ttu-id="51662-140"><kbd>Y</kbd> 押して [はい] を選択すると、`Update-Help` コマンドレットが実行されます。既定では、このコマンドレットにはインターネット アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="51662-140">Answering yes by pressing <kbd>Y</kbd> runs the `Update-Help` cmdlet, which requires internet access by default.</span></span> <span data-ttu-id="51662-141">`Y` は、大文字と小文字のどちらでも指定できます。</span><span class="sxs-lookup"><span data-stu-id="51662-141">`Y` can be specified in either upper or lower case.</span></span>

<span data-ttu-id="51662-142">ヘルプがダウンロードされ、更新が完了すると、指定したコマンドのヘルプ トピックが返されます。</span><span class="sxs-lookup"><span data-stu-id="51662-142">Once the help is downloaded and the update is complete, the help topic is returned for the specified command:</span></span>

```powershell
Get-Help -Name Get-Help
```

<span data-ttu-id="51662-143">ここでコンピューターでこの例を実行し、出力を確認して、情報がどのようにグループ化されているかをメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="51662-143">Take a moment to run that example on your computer, review the output, and take note of how the information is grouped:</span></span>

- <span data-ttu-id="51662-144">NAME</span><span class="sxs-lookup"><span data-stu-id="51662-144">NAME</span></span>
- <span data-ttu-id="51662-145">概要</span><span class="sxs-lookup"><span data-stu-id="51662-145">SYNOPSIS</span></span>
- <span data-ttu-id="51662-146">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="51662-146">SYNTAX</span></span>
- <span data-ttu-id="51662-147">Description</span><span class="sxs-lookup"><span data-stu-id="51662-147">DESCRIPTION</span></span>
- <span data-ttu-id="51662-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="51662-148">RELATED LINKS</span></span>
- <span data-ttu-id="51662-149">REMARKS</span><span class="sxs-lookup"><span data-stu-id="51662-149">REMARKS</span></span>

<span data-ttu-id="51662-150">ご覧のように、ヘルプ トピックには膨大な情報を含めることができますが、これでもヘルプ トピック全体ではありません。</span><span class="sxs-lookup"><span data-stu-id="51662-150">As you can see, help topics can contain an enormous amount of information and this isn't even the entire help topic.</span></span>

<span data-ttu-id="51662-151">PowerShell に限ったことではりませんが、パラメーターは、コマンドに入力を提供する手段です。</span><span class="sxs-lookup"><span data-stu-id="51662-151">While not specific to PowerShell, a parameter is a way to provide input to a command.</span></span> <span data-ttu-id="51662-152">`Get-Help` には、ヘルプ トピック全体またはヘルプ トピックのサブセットを取得するためのパラメーターが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="51662-152">`Get-Help` has many parameters that can be specified in order to return the entire help topic or a subset of it.</span></span>

<span data-ttu-id="51662-153">前の結果セットに示されているヘルプ トピックの構文セクションには、`Get-Help` のパラメーターの一覧が表示されています。</span><span class="sxs-lookup"><span data-stu-id="51662-153">The syntax section of the help topic shown in the previous set of results lists all of the parameters for `Get-Help`.</span></span> <span data-ttu-id="51662-154">一見すると、同じパラメーターが 6 つの異なる時刻に表示されているようですが、</span><span class="sxs-lookup"><span data-stu-id="51662-154">At first glance, it appears the same parameters are listed six different times.</span></span> <span data-ttu-id="51662-155">構文セクションのそれぞれのブロックが、パラメーター セットです。</span><span class="sxs-lookup"><span data-stu-id="51662-155">Each of those different blocks in the syntax section is a parameter set.</span></span> <span data-ttu-id="51662-156">つまり、`Get-Help` コマンドレットには 6 つの異なるパラメーター セットがあります。</span><span class="sxs-lookup"><span data-stu-id="51662-156">This means the `Get-Help` cmdlet has six different parameter sets.</span></span> <span data-ttu-id="51662-157">さらに詳しく見ると、各パラメーター セットで、少なくとも 1 つのパラメーターが違っていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="51662-157">If you take a closer look, you'll notice that at least one parameter is different in each of the parameter sets.</span></span>

<span data-ttu-id="51662-158">パラメーター セットを同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="51662-158">Parameter sets are mutually exclusive.</span></span> <span data-ttu-id="51662-159">1 つのパラメーター セットにのみ存在する一意のパラメーターが使用されている場合、使用できるのは、そのパラメーター セットに含まれるパラメーターだけです。</span><span class="sxs-lookup"><span data-stu-id="51662-159">Once a unique parameter that only exists in one of the parameter sets is used, only parameters contained within that parameter set can be used.</span></span> <span data-ttu-id="51662-160">たとえば、**Full** パラメーターと **Detailed** パラメーターは、それぞれ異なるパラメーター セットに含まれているため、両方を同時に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="51662-160">For example, both the **Full** and **Detailed** parameters couldn't be specified at the same time because they are in different parameter sets.</span></span>

<span data-ttu-id="51662-161">次のパラメーターはそれぞれ、異なるパラメーター セットに含まれています。</span><span class="sxs-lookup"><span data-stu-id="51662-161">Each of the following parameters are in different parameter sets:</span></span>

- <span data-ttu-id="51662-162">[完全]</span><span class="sxs-lookup"><span data-stu-id="51662-162">Full</span></span>
- <span data-ttu-id="51662-163">詳細</span><span class="sxs-lookup"><span data-stu-id="51662-163">Detailed</span></span>
- <span data-ttu-id="51662-164">例</span><span class="sxs-lookup"><span data-stu-id="51662-164">Examples</span></span>
- <span data-ttu-id="51662-165">オンライン</span><span class="sxs-lookup"><span data-stu-id="51662-165">Online</span></span>
- <span data-ttu-id="51662-166">パラメーター</span><span class="sxs-lookup"><span data-stu-id="51662-166">Parameter</span></span>
- <span data-ttu-id="51662-167">ShowWindow</span><span class="sxs-lookup"><span data-stu-id="51662-167">ShowWindow</span></span>

<span data-ttu-id="51662-168">構文セクションに示されている、角かっこや山かっこなどのわかりにくい構文すべてに意味がありますが、これについては、本書の付録 A で説明します。</span><span class="sxs-lookup"><span data-stu-id="51662-168">All of the cryptic syntax such as square and angle brackets in the syntax section means something but will be covered in Appendix A of this book.</span></span> <span data-ttu-id="51662-169">重要ではありますが、PowerShell を初めて使うユーザーや、毎日使っているわけではないユーザーにとって、わかりにくい構文が何であるかを把握するのが難しいことは少なくありません。</span><span class="sxs-lookup"><span data-stu-id="51662-169">While important, learning what the cryptic syntax is often difficult to retain for someone who is new to PowerShell and may not use it everyday.</span></span>

<span data-ttu-id="51662-170">わかりにくい構文の詳細については、[付録 A:][] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51662-170">For more information to better understand the cryptic syntax, see [Appendix A][].</span></span>

<span data-ttu-id="51662-171">初心者を対象とした、より簡単な方法で同じ情報を確認する方法があります (簡単な言語を除く)。</span><span class="sxs-lookup"><span data-stu-id="51662-171">For beginners, there's an easier way to figure out the same information except in plain language.</span></span>

<span data-ttu-id="51662-172">`Get-Help` の **Full** パラメーター を指定すると、ヘルプ トピック全体が返されます。</span><span class="sxs-lookup"><span data-stu-id="51662-172">When the **Full** parameter of `Get-Help` is specified, the entire help topic is returned.</span></span>

```powershell
Get-Help -Name Get-Help -Full
```

<span data-ttu-id="51662-173">ここでコンピューターでこの例を実行し、出力を確認して、情報がどのようにグループ化されているかをメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="51662-173">Take a moment to run that example on your computer, review the output, and take note of how the information is grouped:</span></span>

- <span data-ttu-id="51662-174">NAME</span><span class="sxs-lookup"><span data-stu-id="51662-174">NAME</span></span>
- <span data-ttu-id="51662-175">概要</span><span class="sxs-lookup"><span data-stu-id="51662-175">SYNOPSIS</span></span>
- <span data-ttu-id="51662-176">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="51662-176">SYNTAX</span></span>
- <span data-ttu-id="51662-177">Description</span><span class="sxs-lookup"><span data-stu-id="51662-177">DESCRIPTION</span></span>
- <span data-ttu-id="51662-178">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="51662-178">PARAMETERS</span></span>
- <span data-ttu-id="51662-179">入力</span><span class="sxs-lookup"><span data-stu-id="51662-179">INPUTS</span></span>
- <span data-ttu-id="51662-180">出力</span><span class="sxs-lookup"><span data-stu-id="51662-180">OUTPUTS</span></span>
- <span data-ttu-id="51662-181">注</span><span class="sxs-lookup"><span data-stu-id="51662-181">NOTES</span></span>
- <span data-ttu-id="51662-182">例</span><span class="sxs-lookup"><span data-stu-id="51662-182">EXAMPLES</span></span>
- <span data-ttu-id="51662-183">関連リンク</span><span class="sxs-lookup"><span data-stu-id="51662-183">RELATED LINKS</span></span>

<span data-ttu-id="51662-184">**Full** パラメーターを使用すると、追加セクションがいくつか返されます。そのうちの 1 つがパラメーター セクションで、このセクションには、わかりにくい構文セクションよりも多くの情報が示されています。</span><span class="sxs-lookup"><span data-stu-id="51662-184">Notice that using the **Full** parameter returned several additional sections, one of which is the PARAMETERS section that provides more information than the cryptic SYNTAX section.</span></span>

<span data-ttu-id="51662-185">**Full** パラメーターはスイッチ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="51662-185">The **Full** parameter is a switch parameter.</span></span> <span data-ttu-id="51662-186">値を必要としないパラメーターが、スイッチ パラメーターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="51662-186">A parameter that doesn't require a value is called a switch parameter.</span></span> <span data-ttu-id="51662-187">スイッチ パラメーターが指定されている場合、その値は true であり、そうでない場合、値は false です。</span><span class="sxs-lookup"><span data-stu-id="51662-187">When a switch parameter is specified, it's value is true and when it's not, it's value is false.</span></span>

<span data-ttu-id="51662-188">この章の PowerShell コンソールでの作業では、`Get-Help` のヘルプ トピック全体を表示するための前のコマンドはあっという間に過ぎてしまい、読む時間がありませんでした。</span><span class="sxs-lookup"><span data-stu-id="51662-188">If you've been working through this chapter in the PowerShell console, you noticed that the previous command to display the full help topic for `Get-Help` flew by on the screen without giving you a chance to read it.</span></span> <span data-ttu-id="51662-189">もっと良い方法があります。</span><span class="sxs-lookup"><span data-stu-id="51662-189">There's a better way.</span></span>

<span data-ttu-id="51662-190">`Help` は、`more` という名前の関数に対して `Get-Help` をパイプ処理する関数で、これは Windows の `more.com` 実行可能ファイルのラッパーです。</span><span class="sxs-lookup"><span data-stu-id="51662-190">`Help` is a function that pipes `Get-Help` to a function named `more`, which is a wrapper for the `more.com` executable file in Windows.</span></span> <span data-ttu-id="51662-191">PowerShell コンソールでは、`help` は 1 ページずつヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="51662-191">In the PowerShell console, `help` provides one page of help at a time.</span></span> <span data-ttu-id="51662-192">ISE では、`Get-Help` と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="51662-192">In the ISE, it works the same way as `Get-Help`.</span></span> <span data-ttu-id="51662-193">操作性に優れ、入力も少なくて済むため、`Get-Help` コマンドレットではなく `help` 関数を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51662-193">My recommendation is to use the `help` function instead of the `Get-Help` cmdlet since it provides a better experience and it's less to type.</span></span>

<span data-ttu-id="51662-194">ただし、入力が少ないことが必ずしも良いとは限りません。</span><span class="sxs-lookup"><span data-stu-id="51662-194">Less typing isn't always a good thing, however.</span></span> <span data-ttu-id="51662-195">コマンドをスクリプトとして保存したり、他のユーザーと共有したりする場合は、必ず完全なコマンドレットとパラメーター名を使用してください。</span><span class="sxs-lookup"><span data-stu-id="51662-195">If you're going to save your commands as a script or share them with someone else, be sure to use full cmdlet and parameter names.</span></span> <span data-ttu-id="51662-196">完全な名前は自己文書化されるため、理解しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="51662-196">The full names are self-documenting, which makes them easier to understand.</span></span> <span data-ttu-id="51662-197">ご自身のコマンドを次に読んで理解する必要があるユーザーのことを考えてください。</span><span class="sxs-lookup"><span data-stu-id="51662-197">Think about the next person that has to read and understand your commands.</span></span> <span data-ttu-id="51662-198">それは自分自身かもしれません。</span><span class="sxs-lookup"><span data-stu-id="51662-198">It could be you.</span></span> <span data-ttu-id="51662-199">同僚そして未来の自分が、ありがたいと思うでしょう。</span><span class="sxs-lookup"><span data-stu-id="51662-199">Your coworkers and future self will thank you.</span></span>

<span data-ttu-id="51662-200">Windows 10 ラボ環境のコンピューターの PowerShell コンソールで、次のコマンドを実行してみます。</span><span class="sxs-lookup"><span data-stu-id="51662-200">Try running the following commands in the PowerShell console on your Windows 10 lab environment computer.</span></span>

```powershell
Get-Help -Name Get-Help -Full
help -Name Get-Help -Full
help Get-Help -Full
```

<span data-ttu-id="51662-201">Windows 10 ラボ環境のコンピューターで実行したとき、前に示したコマンドの出力と違いがあることに気が付きましたか。</span><span class="sxs-lookup"><span data-stu-id="51662-201">Did you notice any differences in the output from the previously listed commands when you ran them on your Windows 10 lab environment computer?</span></span>

<span data-ttu-id="51662-202">最後の 2 つのオプションが 1 ページずつ結果を返すこと以外、違いはありません。</span><span class="sxs-lookup"><span data-stu-id="51662-202">There aren't any differences other than the last two options return the results one page at a time.</span></span>
<span data-ttu-id="51662-203">`Help` 関数を使用している場合、<kbd>スペース</kbd> キーを使用すると、コンテンツの次のページが表示されます。また、<kbd>Ctrl </kbd> + <kbd> C </kbd> キーを押すと、PowerShell コンソールで実行されているコマンドがキャンセルされます。</span><span class="sxs-lookup"><span data-stu-id="51662-203">The <kbd>spacebar</kbd> is used to display the next page of content when using the `Help` function and <kbd>Ctrl</kbd>+<kbd>C</kbd> cancels commands that are running in the PowerShell console.</span></span>

<span data-ttu-id="51662-204">最初の例では `Get-Help` コマンドレットが使用され、2 番目の例では `Help` 関数が使用されます。3 番目の例では、`Help` 関数が使用され、**Name** パラメーターが省略されています。</span><span class="sxs-lookup"><span data-stu-id="51662-204">The first example uses the `Get-Help` cmdlet, the second uses the `Help` function, and the third omits the **Name** parameter when using the `Help` function.</span></span> <span data-ttu-id="51662-205">**Name** は位置指定パラメーターであり、この例では位置指定に使用されています。</span><span class="sxs-lookup"><span data-stu-id="51662-205">**Name** is a positional parameter and it's being used positionally in that example.</span></span> <span data-ttu-id="51662-206">つまり、値自体が正しい位置で指定されていれば、パラメーター名を指定しなくても値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="51662-206">This means the value can be specified without specifying the parameter name, as long as the value itself is specified in the correct position.</span></span> <span data-ttu-id="51662-207">値を指定する位置はどのようにわかったのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="51662-207">How did I know what position to specify the value in?</span></span> <span data-ttu-id="51662-208">次の例に示すヘルプを読めばわかります。</span><span class="sxs-lookup"><span data-stu-id="51662-208">By reading the help as shown in the following example.</span></span>

```powershell
help Get-Help -Parameter Name
```

```Output
-Name <String>
    Gets help about the specified command or concept. Enter the name of a cmdlet, function,
    provider, script, or workflow, such as Get-Member, a conceptual article name, such as
    about_Objects, or an alias, such as ls. Wildcard characters are permitted in cmdlet and
    provider names, but you can't use wildcard characters to find the names of function help and
    script help articles.

    To get help for a script that isn't located in a path that's listed in the $env:Path
    environment variable, type the script's path and file name.

    If you enter the exact name of a help article, Get-Help displays the article contents.

    If you enter a word or word pattern that appears in several help article titles, Get-Help
    displays a list of the matching titles.

    If you enter a word that doesn't match any help article titles, Get-Help displays a list of
    articles that include that word in their contents.

    The names of conceptual articles, such as about_Objects, must be entered in English, even in
    non-English versions of PowerShell.

    Required?                    false
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  true
```

<span data-ttu-id="51662-209">この例では、**Parameter** パラメーターが Help 関数と共に使用され、**Name** パラメーターのヘルプ トピックの情報だけが返されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="51662-209">Notice that in the previous example, the **Parameter** parameter was used with the Help function to only return information from the help topic for the **Name** parameter.</span></span> <span data-ttu-id="51662-210">これは、100 ページにも見えることがあるヘルプ トピックを手作業で詳しく調べようとするよりも、はるかに簡潔です。</span><span class="sxs-lookup"><span data-stu-id="51662-210">This is much more concise than trying to manually sift through what sometimes seems like a hundred page help topic.</span></span>

<span data-ttu-id="51662-211">これらの結果から、**Name** パラメーターが位置指定パラメーターで、位置指定に使用する場合は、位置 0 (最初の位置) で指定する必要があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="51662-211">Based on those results, you can see that the **Name** parameter is positional and must be specified in position zero (the first position) when used positionally.</span></span> <span data-ttu-id="51662-212">パラメーター名が指定されている場合、パラメーターを指定する順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="51662-212">The order that parameters are specified in doesn't matter if the parameter name is specified.</span></span>

<span data-ttu-id="51662-213">もう 1 つ重要なのは、**Name** パラメーターでは、その値のデータ型が、`<String>` によって示される 1 つの文字列であることが想定されることです。</span><span class="sxs-lookup"><span data-stu-id="51662-213">One other important piece of information is that the **Name** parameter expects the datatype for its value to be a single string, which is denoted by `<String>`.</span></span> <span data-ttu-id="51662-214">複数の文字列が受け入れられると、データ型は `<String[]>` として表示されます。</span><span class="sxs-lookup"><span data-stu-id="51662-214">If it accepted multiple strings, the datatype would be listed as `<String[]>`.</span></span>

<span data-ttu-id="51662-215">場合によっては、コマンドのヘルプ トピック全体を単に表示したくないこともあります。</span><span class="sxs-lookup"><span data-stu-id="51662-215">Sometimes you simply don't want to display the entire help topic for a command.</span></span> <span data-ttu-id="51662-216">`Get-Help` や `Help`で指定できる **Full** 以外にもパラメーターは多数あります。</span><span class="sxs-lookup"><span data-stu-id="51662-216">There are a number of other parameters besides **Full** that can be specified with `Get-Help` or `Help`.</span></span> <span data-ttu-id="51662-217">Windows 10 ラボ環境のコンピューターで、次のコマンドを実行してみます。</span><span class="sxs-lookup"><span data-stu-id="51662-217">Try running the following commands on your Windows 10 lab environment computer:</span></span>

```powershell
Get-Help -Name Get-Command -Full
Get-Help -Name Get-Command -Detailed
Get-Help -Name Get-Command -Examples
Get-Help -Name Get-Command -Online
Get-Help -Name Get-Command -Parameter Noun
Get-Help -Name Get-Command -ShowWindow
```

<span data-ttu-id="51662-218">私はいつも、`help <command name>` は、**Full** パラメーターまたは **Online** パラメーターと一緒に使用します。</span><span class="sxs-lookup"><span data-stu-id="51662-218">I typically use `help <command name>` with the **Full** or **Online** parameter.</span></span> <span data-ttu-id="51662-219">例だけに関心がある場合は、**Examples** パラメーターを、特定のパラメーターにのみ関心がある場合は、**Parameter** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="51662-219">If I'm only interested in the examples, I'll use the **Examples** parameter and if I'm only interested in a specific parameter, I'll use the **Parameter** parameter.</span></span> <span data-ttu-id="51662-220">**ShowWindow** パラメーターを使用すると、別の検索可能なウィンドウでヘルプ トピックが開きます。複数のモニターがある場合は、それを別のモニターに配置できます。</span><span class="sxs-lookup"><span data-stu-id="51662-220">The **ShowWindow** parameter opens the help topic in a separate searchable window that can be placed on a different monitor if you have multiple monitors.</span></span> <span data-ttu-id="51662-221">この **ShowWindow** パラメーターには、ヘルプ トピック全体が表示されないという既知のバグがあるため、私は避けました。</span><span class="sxs-lookup"><span data-stu-id="51662-221">I've avoided the **ShowWindow** parameter because there's a known bug where it doesn't display the entire help topic.</span></span>

<span data-ttu-id="51662-222">別のウィンドウでヘルプを確認したい場合は、次の例に示すように、**Online** パラメーターを使用するか、**Full** パラメーターを使用して、結果を `Out-GridView` にパイプ処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51662-222">If you want help in a separate window, my recommendation is to either use the **Online** parameter or use the **Full** parameter and pipe the results to `Out-GridView`, as shown in the following example.</span></span>

```powershell
help Get-Command -Full | Out-GridView
```

<span data-ttu-id="51662-223">`Out-GridView` コマンドレットと、`Get-Help` コマンドレットの **ShowWindow** パラメーターの両方に、GUI (グラフィカル ユーザー インターフェイス) を備えたオペレーティング システムが必要です。</span><span class="sxs-lookup"><span data-stu-id="51662-223">Both the `Out-GridView` cmdlet and the **ShowWindow** parameter of the `Get-Help` cmdlet require an operating system with a GUI (Graphical User Interface).</span></span> <span data-ttu-id="51662-224">サーバー コア (GUI なし) インストール オプションを使用してインストールされた Windows Server 上で、いずれか一方を使おうとすると、エラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="51662-224">They will generate an error message if you attempt to use either of them on Windows Server that's been installed using the server core (no-GUI) installation option.</span></span>

<span data-ttu-id="51662-225">`Get-Help` を使用してコマンドを検索するには、アスタリスク (`*`) ワイルドカード文字を **Name** パラメーターで使用します。</span><span class="sxs-lookup"><span data-stu-id="51662-225">To use `Get-Help` to find commands, use the asterisk (`*`) wildcard character with the **Name** parameter.</span></span> <span data-ttu-id="51662-226">次の例に示すように、**Name** パラメーターの値として、コマンドに対する検索用語を指定します。</span><span class="sxs-lookup"><span data-stu-id="51662-226">Specify a term that you're searching for commands on as the value for the **Name** parameter as shown in the following example.</span></span>

```powershell
help *process*
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
Exit-PSHostProcess                Cmdlet    Microsoft.PowerShell.Core Closes an intera...
Get-PSHostProcessInfo             Cmdlet    Microsoft.PowerShell.Core
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-AppvVirtualProcess            Function  AppvClient                ...
Start-AppvVirtualProcess          Function  AppvClient                ...
```

<span data-ttu-id="51662-227">この例では、`*` ワイルドカード文字は不要で、省略しても、同じ結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="51662-227">In the previous example, the `*` wildcard characters are not required and omitting them produces the same result.</span></span> <span data-ttu-id="51662-228">`Get-Help` では、ワイルドカード文字がバックグラウンドで自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="51662-228">`Get-Help` automatically adds the wildcard characters behind the scenes.</span></span>

```powershell
help process
```

<span data-ttu-id="51662-229">このコマンドでは、プロセスが終了するたびに、`*` ワイルドカード文字を指定した場合と同じ結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="51662-229">The previous command produces the same results as specifying the `*` wildcard character on each end of process.</span></span>

<span data-ttu-id="51662-230">このオプションの動作はいつも一貫しているため、私は好んで追加しますが、</span><span class="sxs-lookup"><span data-stu-id="51662-230">I prefer to add them since that's the option that always works consistently.</span></span> <span data-ttu-id="51662-231">これが必要なのは特定のシナリオだけで、他では不要です。</span><span class="sxs-lookup"><span data-stu-id="51662-231">Otherwise, they are required in certain scenarios and not others.</span></span> <span data-ttu-id="51662-232">値の途中にワイルドカード文字を追加するとすぐに、指定した値に自動的に追加されることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="51662-232">As soon as you add a wildcard character in the middle of the value, they're no longer automatically added behind the scenes to the value you specified.</span></span>

```powershell
help pr*cess
```

<span data-ttu-id="51662-233">`pr*cess` の先頭または末尾、あるいはその両方に `*` ワイルドカード文字が追加されない限り、そのコマンドによって結果が返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="51662-233">No results are returned by that command unless the `*` wildcard character is added to the beginning, end, or both the beginning and end of `pr*cess`.</span></span>

<span data-ttu-id="51662-234">指定した値がダッシュで始まると、PowerShell ではそれがパラメーター名として解釈され、そのようなパラメーター名は `Get-Help` コマンドレットに対しては存在しないため、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="51662-234">If the value you specified begins with a dash, then an error is generated because PowerShell interprets it as a parameter name and no such parameter name exists for the `Get-Help` cmdlet.</span></span>

```powershell
help -process
```

<span data-ttu-id="51662-235">検索対象が `-process` で終わるコマンドの場合は、その値の先頭に `*` のワイルドカード文字を追加するだけです。</span><span class="sxs-lookup"><span data-stu-id="51662-235">If what you're attempting to look for are commands that end with `-process`, you only need to add the `*` wildcard character to the beginning of the value.</span></span>

```powershell
help *-process
```

<span data-ttu-id="51662-236">`Get-Help` で PowerShell コマンドを検索する場合は、検索対象に限定するのではなく、少しあいまいにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51662-236">When searching for PowerShell commands with `Get-Help`, you want to be a little more vague instead of being too specific with what you're searching for.</span></span>

<span data-ttu-id="51662-237">前に `process` を検索したときは、コマンドの名前に `process` が含まれているコマンドのみが見つかり、その結果のみが返されました。</span><span class="sxs-lookup"><span data-stu-id="51662-237">Searching for `process` earlier found only commands that contained `process` in the name of the command and returned only those results.</span></span> <span data-ttu-id="51662-238">`Get-Help` を使用して `processes` を検索すると、コマンド名に一致するものが見つからないため、システム上の PowerShell のすべてのヘルプ トピックに対して検索が実行され、見つかった一致がすべて返されます。</span><span class="sxs-lookup"><span data-stu-id="51662-238">When `Get-Help` is used to search for `processes`, it doesn't find any matches for command names, so it performs a search of every help topic in PowerShell on your system and returns any matches it finds.</span></span> <span data-ttu-id="51662-239">このため返される結果の数が膨大になります。</span><span class="sxs-lookup"><span data-stu-id="51662-239">This causes it to return an enormous number of results.</span></span>

```powershell
Get-Help processes
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Disconnect-PSSession              Cmdlet    Microsoft.PowerShell.Core Disconnects from...
Enter-PSHostProcess               Cmdlet    Microsoft.PowerShell.Core Connects to and ...
ForEach-Object                    Cmdlet    Microsoft.PowerShell.Core Performs an oper...
Get-PSSessionConfiguration        Cmdlet    Microsoft.PowerShell.Core Gets the registe...
New-PSTransportOption             Cmdlet    Microsoft.PowerShell.Core Creates an objec...
Out-Host                          Cmdlet    Microsoft.PowerShell.Core Sends output to ...
Where-Object                      Cmdlet    Microsoft.PowerShell.Core Selects objects ...
Clear-Variable                    Cmdlet    Microsoft.PowerShell.U... Deletes the valu...
Compare-Object                    Cmdlet    Microsoft.PowerShell.U... Compares two set...
Convert-String                    Cmdlet    Microsoft.PowerShell.U... Formats a string...
ConvertFrom-Csv                   Cmdlet    Microsoft.PowerShell.U... Converts object ...
ConvertTo-Html                    Cmdlet    Microsoft.PowerShell.U... Converts Microso...
ConvertTo-Xml                     Cmdlet    Microsoft.PowerShell.U... Creates an XML-b...
Debug-Runspace                    Cmdlet    Microsoft.PowerShell.U... Starts an intera...
Export-Csv                        Cmdlet    Microsoft.PowerShell.U... Converts objects...
Export-FormatData                 Cmdlet    Microsoft.PowerShell.U... Saves formatting...
Format-List                       Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Format-Table                      Cmdlet    Microsoft.PowerShell.U... Formats the outp...
Get-Random                        Cmdlet    Microsoft.PowerShell.U... Gets a random nu...
Get-Unique                        Cmdlet    Microsoft.PowerShell.U... Returns unique i...
Group-Object                      Cmdlet    Microsoft.PowerShell.U... Groups objects t...
Import-Clixml                     Cmdlet    Microsoft.PowerShell.U... Imports a CLIXML...
Import-Csv                        Cmdlet    Microsoft.PowerShell.U... Creates table-li...
Measure-Object                    Cmdlet    Microsoft.PowerShell.U... Calculates the n...
Out-File                          Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Out-GridView                      Cmdlet    Microsoft.PowerShell.U... Sends output to ...
Select-Object                     Cmdlet    Microsoft.PowerShell.U... Selects objects ...
Set-Variable                      Cmdlet    Microsoft.PowerShell.U... Sets the value o...
Sort-Object                       Cmdlet    Microsoft.PowerShell.U... Sorts objects by...
Tee-Object                        Cmdlet    Microsoft.PowerShell.U... Saves command ou...
Trace-Command                     Cmdlet    Microsoft.PowerShell.U... Configures and s...
Write-Output                      Cmdlet    Microsoft.PowerShell.U... Sends the specif...
Debug-Process                     Cmdlet    Microsoft.PowerShell.M... Debugs one or mo...
Get-Process                       Cmdlet    Microsoft.PowerShell.M... Gets the process...
Get-WmiObject                     Cmdlet    Microsoft.PowerShell.M... Gets instances o...
Start-Process                     Cmdlet    Microsoft.PowerShell.M... Starts one or mo...
Stop-Process                      Cmdlet    Microsoft.PowerShell.M... Stops one or mor...
Wait-Process                      Cmdlet    Microsoft.PowerShell.M... Waits for the pr...
Get-Counter                       Cmdlet    Microsoft.PowerShell.D... Gets performance...
Invoke-WSManAction                Cmdlet    Microsoft.WSMan.Manage... Invokes an actio...
Remove-WSManInstance              Cmdlet    Microsoft.WSMan.Manage... Deletes a manage...
Get-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Displays managem...
New-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Creates a new in...
Set-WSManInstance                 Cmdlet    Microsoft.WSMan.Manage... Modifies the man...
about_Arithmetic_Operators        HelpFile                            Describes the op...
about_Arrays                      HelpFile                            Describes arrays...
about_Debuggers                   HelpFile                            Describes the Wi...
about_Execution_Policies          HelpFile                            Describes the Wi...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Foreach                     HelpFile                            Describes a lang...
about_Functions                   HelpFile                            Describes how to...
about_Language_Keywords           HelpFile                            Describes the ke...
about_Methods                     HelpFile                            Describes how to...
about_Objects                     HelpFile                            Provides essenti...
about_Parallel                    HelpFile                            Describes the Pa...
about_Pipelines                   HelpFile                            Combining comman...
about_Preference_Variables        HelpFile                            Variables that c...
about_Remote                      HelpFile                            Describes how to...
about_Remote_Output               HelpFile                            Describes how to...
about_Sequence                    HelpFile                            Describes the Se...
about_Session_Configuration_Files HelpFile                            Describes sessio...
about_Variables                   HelpFile                            Describes how va...
about_Windows_PowerShell_5.0      HelpFile                            Describes new fe...
about_WQL                         HelpFile                            Describes WMI Qu...
about_WS-Management_Cmdlets       HelpFile                            Provides an over...
about_ForEach-Parallel            HelpFile                            Describes the Fo...
about_Parallel                    HelpFile                            Describes the Pa...
about_Sequence                    HelpFile                            Describes the Se...
```

<span data-ttu-id="51662-240">`Help` を使用して `process` を検索すると 10 件の結果が返されます。また、`processes` を検索すると 68 件の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="51662-240">Using `Help` to search for `process` returned 10 results and using it to search for `processes` returned 68 results.</span></span> <span data-ttu-id="51662-241">見つかった結果が 1 つだけの場合は、コマンドの一覧ではなく、ヘルプ トピック自体が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51662-241">If only one result is found, the help topic itself will be displayed instead of a list of commands.</span></span>

```powershell
get-help *hotfix*
```

```Output
NAME
    Get-HotFix

SYNOPSIS
    Gets the hotfixes that have been applied to the local and remote computers.


SYNTAX
    Get-HotFix [-ComputerName <String[]>] [-Credential <PSCredential>] [-Description
    <String[]>] [<CommonParameters>]

    Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential
    <PSCredential>] [<CommonParameters>]


DESCRIPTION
    The Get-Hotfix cmdlet gets hotfixes (also called updates) that have been installed
    on either the local computer (or on specified remote computers) by Windows Update,
    Microsoft Update, or Windows Server Update Services; the cmdlet also gets hotfixes
    or updates that have been installed manually by users.


RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821586
    Win32_QuickFixEngineering http://go.microsoft.com/fwlink/?LinkID=145071
    Get-ComputerRestorePoint
    Add-Content

REMARKS
    To see the examples, type: "get-help Get-HotFix -examples".
    For more information, type: "get-help Get-HotFix -detailed".
    For technical information, type: "get-help Get-HotFix -full".
    For online help, type: "get-help Get-HotFix -online"
```

<span data-ttu-id="51662-242">ここで、PowerShell の `Help` では、ヘルプ トピックが含まれているコマンドしか見つけることができないという説が嘘であることを証明します。</span><span class="sxs-lookup"><span data-stu-id="51662-242">Now to debunk the myth that `Help` in PowerShell can only find commands that have help topics.</span></span>

```powershell
help *more*
```

```Output
NAME
    more

SYNTAX
    more [[-paths] <string[]>]


ALIASES
    None


REMARKS
    None
```

<span data-ttu-id="51662-243">この例の `more` にはヘルプ トピックがありませんが、PowerShell の `Help` システムはこれを見つけることができました。</span><span class="sxs-lookup"><span data-stu-id="51662-243">Notice in the previous example that `more` doesn't have a help topic, yet the `Help` system in PowerShell was able to find it.</span></span> <span data-ttu-id="51662-244">このシステムは一致を 1 つだけ見つけて、コマンドにヘルプ トピックがないときに表示される基本的な構文情報を返しました。</span><span class="sxs-lookup"><span data-stu-id="51662-244">It only found one match and returned the basic syntax information that you'll see when a command doesn't have a help topic.</span></span>

<span data-ttu-id="51662-245">PowerShell には、さまざまな概念 (About) ヘルプ トピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="51662-245">PowerShell contains numerous conceptual (About) help topics.</span></span> <span data-ttu-id="51662-246">次のコマンドを使用すると、システム上の **About** ヘルプ トピックの一覧を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="51662-246">The following command can be used to return a list of all **About** help topics on your system.</span></span>

```powershell
help About_*
```

<span data-ttu-id="51662-247">結果を単一の About ヘルプ トピック 1 つに制限すると、リストではなく実際のヘルプ トピックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51662-247">Limiting the results to one single About help topic displays the actual help topic instead of returning a list.</span></span>

```powershell
help about_Updatable_Help
```

<span data-ttu-id="51662-248">**About** ヘルプ トピックを表示するには、PowerShell のヘルプ システムを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51662-248">The help system in PowerShell has to be updated in order for the **About** help topics to be present.</span></span> <span data-ttu-id="51662-249">何らかの理由でコンピューター上のヘルプ システムの初期更新が失敗した場合、`Update-Help` コマンドレットが正常に実行されるまで、ファイルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="51662-249">If for some reason the initial update of the help system failed on your computer, the files will not be available until the `Update-Help` cmdlet has been run successfully.</span></span>

## <a name="get-command"></a><span data-ttu-id="51662-250">Get-Command</span><span class="sxs-lookup"><span data-stu-id="51662-250">Get-Command</span></span>

<span data-ttu-id="51662-251">`Get-Command` は、コマンドを見つけやすくすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="51662-251">`Get-Command` is designed to help you locate commands.</span></span> <span data-ttu-id="51662-252">パラメーターを指定せずに `Get-Command` を実行すると、システム上のコマンドの一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="51662-252">Running `Get-Command` without any parameters returns a list of all the commands on your system.</span></span> <span data-ttu-id="51662-253">次の例は、`Get-Command` コマンドレットを使用して、プロセスを操作するためのコマンドを確認しています。</span><span class="sxs-lookup"><span data-stu-id="51662-253">The following example demonstrates using the `Get-Command` cmdlet to determine what commands exist for working with processes:</span></span>

```powershell
Get-Command -Noun Process
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Debug-Process                                      3.1.0.0    Microsof...
Cmdlet          Get-Process                                        3.1.0.0    Microsof...
Cmdlet          Start-Process                                      3.1.0.0    Microsof...
Cmdlet          Stop-Process                                       3.1.0.0    Microsof...
Cmdlet          Wait-Process                                       3.1.0.0    Microsof...
```

<span data-ttu-id="51662-254">この例の `Get-Command` の実行例では、**Noun** パラメーターが使用され、`Process` が **Noun** パラメーターの値として指定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="51662-254">Notice in the previous example where `Get-Command` was run, the **Noun** parameter is used and `Process` is specified as the value for the **Noun** parameter.</span></span> <span data-ttu-id="51662-255">`Get-Command` コマンドレットの使用方法がわからない場合は、</span><span class="sxs-lookup"><span data-stu-id="51662-255">What if you didn't know how to use the `Get-Command` cmdlet?</span></span> <span data-ttu-id="51662-256">`Get-Help` を使えば、`Get-Command` のヘルプ トピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="51662-256">You could use `Get-Help` to display the help topic for `Get-Command`.</span></span>

<span data-ttu-id="51662-257">**Name**、**Noun**、**Verb** の各パラメーターで、ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="51662-257">The **Name**, **Noun**, and **Verb** parameters accept wildcards.</span></span> <span data-ttu-id="51662-258">次の例では、**Name** パラメーターでワイルドカード文字が使用されています。</span><span class="sxs-lookup"><span data-stu-id="51662-258">The following example shows wildcards being used with the **Name** parameter:</span></span>

```Output
Get-Command -Name *service*
```

```powershell
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Function        Set-NetFirewallServiceFilter                       2.0.0.0    NetSecurity
Cmdlet          Get-Service                                        3.1.0.0    Microsof...
Cmdlet          New-Service                                        3.1.0.0    Microsof...
Cmdlet          New-WebServiceProxy                                3.1.0.0    Microsof...
Cmdlet          Restart-Service                                    3.1.0.0    Microsof...
Cmdlet          Resume-Service                                     3.1.0.0    Microsof...
Cmdlet          Set-Service                                        3.1.0.0    Microsof...
Cmdlet          Start-Service                                      3.1.0.0    Microsof...
Cmdlet          Stop-Service                                       3.1.0.0    Microsof...
Cmdlet          Suspend-Service                                    3.1.0.0    Microsof...
Application     AgentService.exe                                   10.0.14... C:\Windo...
Application     SensorDataService.exe                              10.0.14... C:\Windo...
Application     services.exe                                       10.0.14... C:\Windo...
Application     services.msc                                       0.0.0.0    C:\Windo...
Application     TieringEngineService.exe                           10.0.14... C:\Windo...
```

<span data-ttu-id="51662-259">`Get-Command` の **Name** パラメーターでワイルドカード文字を使用することは、あまり好きではありません。ネイティブの PowerShell コマンドではない実行可能ファイルも返されるためです。</span><span class="sxs-lookup"><span data-stu-id="51662-259">I'm not a fan of using wildcards with the **Name** parameter of `Get-Command` since it also returns executable files that are not native PowerShell commands.</span></span>

<span data-ttu-id="51662-260">**Name** パラメーターと共にワイルドカード文字を使用する場合は、**CommandType** パラメーターを使って結果を制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51662-260">If you are going to use wildcard characters with the **Name** parameter, I recommend limiting the results with the **CommandType** parameter.</span></span>

```powershell
Get-Command -Name *service* -CommandType Cmdlet, Function, Alias
```

<span data-ttu-id="51662-261">それよりも良いのは、**Verb** パラメーターまたは **Noun** パラメーターのいずれか、または両方を使用することでしょう。動詞と名詞の両方が含まれるのは、PowerShell コマンドだけだからです。</span><span class="sxs-lookup"><span data-stu-id="51662-261">A better option is to use either the **Verb** or **Noun** parameter or both of them since only PowerShell commands have both verbs and nouns.</span></span>

<span data-ttu-id="51662-262">ヘルプ トピックで問題が見つかっても大丈夫です。</span><span class="sxs-lookup"><span data-stu-id="51662-262">Found something wrong with a help topic?</span></span> <span data-ttu-id="51662-263">PowerShell のヘルプ トピックはオープンソースなので、GitHub の [PowerShell-Docs][] リポジトリから入手できます。</span><span class="sxs-lookup"><span data-stu-id="51662-263">The good news is the help topics for PowerShell have been open-sourced and available in the [PowerShell-Docs][] repository on GitHub.</span></span> <span data-ttu-id="51662-264">誤っている情報は、自分だけでなく他のユーザー全員が修正し、皆で協力し合うことができます。</span><span class="sxs-lookup"><span data-stu-id="51662-264">Pay it forward by not only fixing the incorrect information for yourself, but everyone else as well.</span></span> <span data-ttu-id="51662-265">ただ GitHub での PowerShell ドキュメント リポジトリのフォーク、ヘルプ トピック更新、pull request の送信のみを行ってください。</span><span class="sxs-lookup"><span data-stu-id="51662-265">Simply fork the PowerShell documentation repository on GitHub, update the help topic, and submit a pull request.</span></span>
<span data-ttu-id="51662-266">pull request が受け入れられたら、修正されたドキュメントは全員が利用できます。</span><span class="sxs-lookup"><span data-stu-id="51662-266">Once the pull request is accepted, the corrected documentation is available for everyone.</span></span>

## <a name="updating-help"></a><span data-ttu-id="51662-267">ヘルプの更新</span><span class="sxs-lookup"><span data-stu-id="51662-267">Updating Help</span></span>

<span data-ttu-id="51662-268">PowerShell ヘルプ トピックのローカル コピーは、コマンドの最初のヘルプが要求されたときに更新されました。</span><span class="sxs-lookup"><span data-stu-id="51662-268">The local copy of the PowerShell help topics was previously updated the first-time help on a command was requested.</span></span> <span data-ttu-id="51662-269">ヘルプ コンテンツは不定期で更新されることがあるため、ヘルプ システムは定期的に更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51662-269">It's recommended to periodically update the help system because there can be updates to the help content from time to time.</span></span> <span data-ttu-id="51662-270">`Update-Help` コマンドレットは、ヘルプ トピックの更新に使用されます。</span><span class="sxs-lookup"><span data-stu-id="51662-270">The `Update-Help` cmdlet is used to update the help topics.</span></span>
<span data-ttu-id="51662-271">管理者として昇格された PowerShell を実行するには、既定でインターネット アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="51662-271">It requires internet access by default and for you to be running PowerShell elevated as an administrator.</span></span>

```powershell
Update-Help
```

```Output
Update-Help : Failed to update Help for the module(s) 'BitsTransfer' with UI culture(s)
{en-US} : The value of the HelpInfoUri key in the module manifest must resolve to a
container or root URL on a website where the help files are stored. The HelpInfoUri
'https://technet.microsoft.com/en-us/library/dd819413.aspx' does not resolve to a
container.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : InvalidOperation: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : InvalidHelpInfoUri,Microsoft.PowerShell.Commands.UpdateHel
   pCommand

Update-Help : Failed to update Help for the module(s) 'NetworkControllerDiagnostics,
StorageReplica' with UI culture(s) {en-US} : Unable to retrieve the HelpInfo XML file
for UI culture en-US. Make sure the HelpInfoUri property in the module manifest is valid
or check your network connection and then try the command again.
At line:1 char:1
+ Update-Help
+
    + CategoryInfo          : ResourceUnavailable: (:) [Update-Help], Exception
    + FullyQualifiedErrorId : UnableToRetrieveHelpInfoXml,Microsoft.PowerShell.Commands.
   UpdateHelpCommand
```

<span data-ttu-id="51662-272">いくつかのモジュールによってエラーが返されましたが、これは珍しいことではありません。</span><span class="sxs-lookup"><span data-stu-id="51662-272">A couple of the modules returned errors, which is not uncommon.</span></span> <span data-ttu-id="51662-273">コンピューターがインターネットにアクセスできない場合は、インターネットにアクセスできる別のマシンで `Save-Help` コマンドレットを使用して、更新されたヘルプ情報をネットワーク上のファイル共有に保存してから、`Update-Help` の **SourcePath** パラメーターを使用し、ヘルプ トピックに対してこのネットワークの場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="51662-273">If the machine didn't have internet access, you could use the `Save-Help` cmdlet on another machine that does have internet access to first save the updated help information to a file share on your network and then use the **SourcePath** parameter of `Update-Help` to specify this network location for the help topics.</span></span>

<span data-ttu-id="51662-274">コンピューターのヘルプ コンテンツを定期的に更新するために、スケジュールされたタスクを設定するか、PowerShell でプロファイル スクリプトにロジックを追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="51662-274">Consider setting up a scheduled task or adding some logic to your profile script in PowerShell to periodically update the help content on your computer.</span></span> <span data-ttu-id="51662-275">プロファイル スクリプトについては、以降の章で説明します。</span><span class="sxs-lookup"><span data-stu-id="51662-275">Profile scripts will be discussed in an upcoming chapter.</span></span>

## <a name="summary"></a><span data-ttu-id="51662-276">まとめ</span><span class="sxs-lookup"><span data-stu-id="51662-276">Summary</span></span>

<span data-ttu-id="51662-277">この章では、`Get-Help` と `Get-Command` の両方を使ってコマンドを見つける方法と、</span><span class="sxs-lookup"><span data-stu-id="51662-277">In this chapter you've learned how to find commands with both `Get-Help` and `Get-Command`.</span></span> <span data-ttu-id="51662-278">コマンドを見つけたら、ヘルプ システムを使ってどのようにそのコマンドの使用方法を確認するかを学習しました。</span><span class="sxs-lookup"><span data-stu-id="51662-278">You've learned how to use the help system to figure out how to use commands once you find them.</span></span> <span data-ttu-id="51662-279">また、更新プログラムが利用可能になったときにヘルプ トピックのコンテンツを更新する方法についても学習しました。</span><span class="sxs-lookup"><span data-stu-id="51662-279">You've also learned how to update the content of the help topics when updates are available.</span></span>

<span data-ttu-id="51662-280">私があなたに言いたいのは、ぜひ 1 日 1 つの PowerShell コマンドを覚えてほしい、ということです。</span><span class="sxs-lookup"><span data-stu-id="51662-280">My challenge to you is to learn a PowerShell command a day.</span></span>

```powershell
Get-Command | Get-Random | Get-Help -Full
```

## <a name="review"></a><span data-ttu-id="51662-281">確認</span><span class="sxs-lookup"><span data-stu-id="51662-281">Review</span></span>

1. <span data-ttu-id="51662-282">`Get-Service` の **DisplayName** パラメーターは、位置指定のパラメーターですか。</span><span class="sxs-lookup"><span data-stu-id="51662-282">Is the **DisplayName** parameter of `Get-Service` positional?</span></span>
1. <span data-ttu-id="51662-283">`Get-Process` コマンドレットにはパラメーター セットの数がいくつありますか。</span><span class="sxs-lookup"><span data-stu-id="51662-283">How many parameter sets does the `Get-Process` cmdlet have?</span></span>
1. <span data-ttu-id="51662-284">イベント ログを操作するための PowerShell コマンドは何ですか。</span><span class="sxs-lookup"><span data-stu-id="51662-284">What PowerShell commands exist for working with event logs?</span></span>
1. <span data-ttu-id="51662-285">コンピューターで実行されている PowerShell プロセス リストを返すための PowerShell コマンドは何ですか。</span><span class="sxs-lookup"><span data-stu-id="51662-285">What is the PowerShell command for returning a list of PowerShell processes running on your computer?</span></span>
1. <span data-ttu-id="51662-286">コンピューターに格納されている PowerShell ヘルプ コンテンツを更新するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="51662-286">How do you update the PowerShell help content that's stored on your computer?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="51662-287">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="51662-287">Recommended Reading</span></span>

<span data-ttu-id="51662-288">この章で説明しているトピックについてもっと詳しく知りたい方は、次の PowerShell のヘルプ トピックを読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51662-288">If you want to know more information about the topics covered in this chapter, I recommend reading the following PowerShell help topics.</span></span>

- <span data-ttu-id="51662-289">[Get-Help][]</span><span class="sxs-lookup"><span data-stu-id="51662-289">[Get-Help][]</span></span>
- <span data-ttu-id="51662-290">[Get-Command][]</span><span class="sxs-lookup"><span data-stu-id="51662-290">[Get-Command][]</span></span>
- <span data-ttu-id="51662-291">[Update-Help][]</span><span class="sxs-lookup"><span data-stu-id="51662-291">[Update-Help][]</span></span>
- <span data-ttu-id="51662-292">[Save-Help][]</span><span class="sxs-lookup"><span data-stu-id="51662-292">[Save-Help][]</span></span>
- <span data-ttu-id="51662-293">[about_Updatable_Help][]</span><span class="sxs-lookup"><span data-stu-id="51662-293">[about_Updatable_Help][]</span></span>
- <span data-ttu-id="51662-294">[about_Command_Syntax][]</span><span class="sxs-lookup"><span data-stu-id="51662-294">[about_Command_Syntax][]</span></span>

<span data-ttu-id="51662-295">次の章では、`Get-Member` コマンドレットと、オブジェクト、プロパティ、およびメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="51662-295">In the next chapter, you'll learn about the `Get-Member` cmdlet as well as objects, properties, and methods.</span></span>

<!-- link references -->
[Get-Help]: /powershell/module/microsoft.powershell.core/get-help
[Get-Command]: /powershell/module/microsoft.powershell.core/get-command
[Update-Help]: /powershell/module/microsoft.powershell.core/update-help
[Save-Help]: /powershell/module/microsoft.powershell.core/save-help
[about_Updatable_Help]: /powershell/module/microsoft.powershell.core/about/about_updatable_help
[about_Command_Syntax]: /powershell/module/microsoft.powershell.core/about/about_command_syntax
[PowerShell-Docs]: https://github.com/powershell/powershell
[付録 A:]: appendix-a.md
[Appendix A]: appendix-a.md

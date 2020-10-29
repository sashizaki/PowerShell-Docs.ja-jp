---
ms.date: 05/22/2020
keywords: powershell,コマンドレット
title: PowerShell とは
description: この記事では、PowerShell のスクリプト環境とその機能の概要について説明します。
ms.openlocfilehash: 91fc580af9a3adf43a24c40b4aaf3f1843882705
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500778"
---
# <a name="what-is-powershell"></a><span data-ttu-id="7a178-104">PowerShell とは</span><span class="sxs-lookup"><span data-stu-id="7a178-104">What is PowerShell?</span></span>

<span data-ttu-id="7a178-105">PowerShell は、コマンドライン シェルとスクリプト言語で構成される、クロスプラットフォームのタスク自動化および構成管理フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="7a178-105">PowerShell is a cross-platform task automation and configuration management framework, consisting of a command-line shell and scripting language.</span></span> <span data-ttu-id="7a178-106">.NET の共通言語ランタイム (CLR) を基に構築されている PowerShell は、テキストを受け取ってテキストを返す多くのシェルとは異なり、.NET オブジェクトを受け取って返します。</span><span class="sxs-lookup"><span data-stu-id="7a178-106">Unlike most shells, which accept and return text, PowerShell is built on top of the .NET Common Language Runtime (CLR), and accepts and returns .NET objects.</span></span> <span data-ttu-id="7a178-107">この根本的な変更により、自動化のためのまったく新しいツールと方法になっています。</span><span class="sxs-lookup"><span data-stu-id="7a178-107">This fundamental change brings entirely new tools and methods for automation.</span></span>

<!-- removing images until we can get replacements
:::row:::
   :::column span="":::
      Windows
      [![PowerShell on Windows](media/overview/windows-desktop-660.gif)](media/overview/windows-desktop.gif#lightbox)
      [Install on Windows](install/installing-powershell-core-on-windows.md)
   :::column-end:::
   :::column span="":::
      Linux
      [![PowerShell on Linux](media/overview/linux-desktop-660.gif)](media/overview/linux-desktop.gif#lightbox)
      [Install on Linux](install/installing-powershell-core-on-linux.md)
   :::column-end:::
   :::column span="":::
      macOS
      [![PowerShell on macOS](media/overview/macos-desktop-660.gif)](media/overview/macos-desktop.gif#lightbox)
      [Install on macOS](install/installing-powershell-core-on-macos.md)
   :::column-end:::
:::row-end:::
-->

## <a name="output-is-object-based"></a><span data-ttu-id="7a178-108">オブジェクト ベースの出力</span><span class="sxs-lookup"><span data-stu-id="7a178-108">Output is object-based</span></span>

<span data-ttu-id="7a178-109">従来のコマンドライン インターフェイスとは異なり、 PowerShell コマンドレットは、オブジェクトを扱うように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7a178-109">Unlike traditional command-line interfaces, PowerShell cmdlets are designed to deal with objects.</span></span>
<span data-ttu-id="7a178-110">オブジェクトは、画面上に表示される文字による単なる文字列ではない、より詳細な構造化された情報です。</span><span class="sxs-lookup"><span data-stu-id="7a178-110">An object is structured information that is more than just the string of characters appearing on the screen.</span></span> <span data-ttu-id="7a178-111">コマンドの実行結果は、常に補足的な情報と共に出力され、必要に応じてこの情報を活用できます。</span><span class="sxs-lookup"><span data-stu-id="7a178-111">Command output always carries extra information that you can use if you need it.</span></span>

<span data-ttu-id="7a178-112">テキスト処理ツールを使用して過去のデータを処理すると、PowerShell で使用された場合とは異なる動作になることがわかるでしょう。</span><span class="sxs-lookup"><span data-stu-id="7a178-112">If you've used text-processing tools to process data in the past, you'll find that they behave differently when used in PowerShell.</span></span> <span data-ttu-id="7a178-113">ほとんどの場合、テキスト処理ツールを使用して特定の情報を抽出する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7a178-113">In most cases, you don't need text-processing tools to extract specific information.</span></span> <span data-ttu-id="7a178-114">標準の PowerShell オブジェクト構文を使用して、データの一部に直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="7a178-114">You directly access portions of the data using standard PowerShell object syntax.</span></span>

## <a name="the-command-family-is-extensible"></a><span data-ttu-id="7a178-115">拡張可能なコマンド ファミリ</span><span class="sxs-lookup"><span data-stu-id="7a178-115">The command family is extensible</span></span>

<span data-ttu-id="7a178-116">`cmd.exe` などのインターフェイスには、組み込みのコマンド セットを直接拡張する手段がありません。</span><span class="sxs-lookup"><span data-stu-id="7a178-116">Interfaces such as `cmd.exe` don't provide a way for you to directly extend the built-in command set.</span></span> <span data-ttu-id="7a178-117">`cmd.exe` 内で実行される外部のコマンドライン ツールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a178-117">You can create external command-line tools that run in `cmd.exe`.</span></span> <span data-ttu-id="7a178-118">しかし、これらの外部ツールには、ヘルプの統合などのサービスがありません。</span><span class="sxs-lookup"><span data-stu-id="7a178-118">But these external tools don't have services, such as Help integration.</span></span> <span data-ttu-id="7a178-119">`cmd.exe` は、これらの外部ツールが有効なコマンドであることを自動認識しません。</span><span class="sxs-lookup"><span data-stu-id="7a178-119">`cmd.exe` doesn't automatically know that these external tools are valid commands.</span></span>

<span data-ttu-id="7a178-120">PowerShell のコマンドは _コマンドレット_ と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="7a178-120">The commands in PowerShell are known as _cmdlets_ .</span></span> <span data-ttu-id="7a178-121">各コマンドレットは個別に使用することもできますが、組み合わせて使い複雑なタスクを実行すると、その力を実感できます。</span><span class="sxs-lookup"><span data-stu-id="7a178-121">You can use each cmdlet separately, but their power is realized when you combine them to perform complex tasks.</span></span> <span data-ttu-id="7a178-122">多くのシェルと同じように、PowerShell ではコンピューター上のファイル システムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7a178-122">Like many shells, PowerShell gives you access to the file system on the computer.</span></span> <span data-ttu-id="7a178-123">PowerShell の _プロバイダー_ を使うと、レジストリや証明書ストアなどのその他のデータ ストアに、ファイル システムとほぼ同様に簡単にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7a178-123">PowerShell _providers_ enable you to access other data stores, such as the registry and the certificate stores, as easily as you access the file system.</span></span>

<span data-ttu-id="7a178-124">コンパイル済みのコードまたはスクリプトを使用すると、あなた独自のコマンドレットや関数モジュールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7a178-124">You can create your own cmdlet and function modules using compiled code or scripts.</span></span> <span data-ttu-id="7a178-125">モジュールは、シェルにコマンドレットとプロバイダーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="7a178-125">Modules can add cmdlets and providers to the shell.</span></span> <span data-ttu-id="7a178-126">また、PowerShell では、UNIX のシェル スクリプトや `cmd.exe` のバッチ ファイルに似たスクリプトもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7a178-126">PowerShell also supports scripts that are analogous to UNIX shell scripts and `cmd.exe` batch files.</span></span>

## <a name="support-for-command-aliases"></a><span data-ttu-id="7a178-127">コマンドのエイリアスをサポートします</span><span class="sxs-lookup"><span data-stu-id="7a178-127">Support for command aliases</span></span>

<span data-ttu-id="7a178-128">PowerShell では、代替名でコマンドを参照するエイリアスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7a178-128">PowerShell supports aliases to refer to commands by alternate names.</span></span> <span data-ttu-id="7a178-129">エイリアスがあることで、他のシェルの経験があるユーザーは、既に知っている一般的なコマンド名を PowerShell のほぼ同じ操作に利用できます。</span><span class="sxs-lookup"><span data-stu-id="7a178-129">Aliasing allows users with experience in other shells to use common command names that they already know for similar operations in PowerShell.</span></span>

<span data-ttu-id="7a178-130">エイリアスは、新しい名前を別のコマンドに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="7a178-130">Aliasing associates a new name with another command.</span></span> <span data-ttu-id="7a178-131">たとえば、PowerShell には、出力ウィンドウをクリアする `Clear-Host` という内部関数があります。</span><span class="sxs-lookup"><span data-stu-id="7a178-131">For example, PowerShell has an internal function named `Clear-Host` that clears the output window.</span></span> <span data-ttu-id="7a178-132">コマンド プロンプトに `cls` または `clear` エイリアスのどちらかを入力できます。</span><span class="sxs-lookup"><span data-stu-id="7a178-132">You can type either the `cls` or `clear` alias at a command prompt.</span></span> <span data-ttu-id="7a178-133">PowerShell はこれらのエイリアスを解釈して、`Clear-Host` 関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a178-133">PowerShell interprets these aliases and runs the `Clear-Host` function.</span></span>

<span data-ttu-id="7a178-134">この機能は、ユーザーが PowerShell を習得するうえで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7a178-134">This feature helps users to learn PowerShell.</span></span> <span data-ttu-id="7a178-135">まず、ほとんどの `cmd.exe` および Unix ユーザーは、既に名前は知っている多数のコマンドのレパートリーを持っています。</span><span class="sxs-lookup"><span data-stu-id="7a178-135">First, most `cmd.exe` and Unix users have a large repertoire of commands that users already know by name.</span></span> <span data-ttu-id="7a178-136">同等の PowerShell のコマンドでは、同一の結果が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a178-136">The PowerShell equivalents may not produce identical results.</span></span> <span data-ttu-id="7a178-137">しかし、十分に近い結果になるので、PowerShell のコマンド名を知らなくてもユーザーが既知のコマンドを利用することは可能です。</span><span class="sxs-lookup"><span data-stu-id="7a178-137">However, the results are close enough that users can do work without knowing the PowerShell command name.</span></span> <span data-ttu-id="7a178-138">新しいコマンド シェルを習得する上でのもう 1 つの主なストレス要因は、"身体が覚えている" ことです。</span><span class="sxs-lookup"><span data-stu-id="7a178-138">"Muscle memory" is another major source of frustration when learning a new command shell.</span></span> <span data-ttu-id="7a178-139">長年にわたって `cmd.exe` を使用してきた場合、画面をクリアするのに、反射的に `cls` コマンドを入力してしまうでしょう。</span><span class="sxs-lookup"><span data-stu-id="7a178-139">If you have used `cmd.exe` for years, you might reflexively type the `cls` command to clear the screen.</span></span> <span data-ttu-id="7a178-140">`Clear-Host` のエイリアスがなければ、エラー メッセージを受け取ってしまい、出力をクリアするにはどうすればいいかわからないでしょう。</span><span class="sxs-lookup"><span data-stu-id="7a178-140">Without the alias for `Clear-Host`, you receive an error message and won't know what to do to clear the output.</span></span>

## <a name="powershell-handles-console-input-and-display"></a><span data-ttu-id="7a178-141">PowerShell によってコンソールの入力と表示が処理される</span><span class="sxs-lookup"><span data-stu-id="7a178-141">PowerShell handles console input and display</span></span>

<span data-ttu-id="7a178-142">コマンドを入力すると、常に、コマンドラインの入力が PowerShell によって直接処理されます。</span><span class="sxs-lookup"><span data-stu-id="7a178-142">When you type a command, PowerShell always processes the command-line input directly.</span></span> <span data-ttu-id="7a178-143">また、PowerShell では、出力を画面上で確認できるように書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7a178-143">PowerShell also formats the output that you see on the screen.</span></span> <span data-ttu-id="7a178-144">各コマンドレットで必要な作業が減るため、これは大きな差になります。</span><span class="sxs-lookup"><span data-stu-id="7a178-144">This difference is significant because it reduces the work required of each cmdlet.</span></span> <span data-ttu-id="7a178-145">どのコマンドレットでも常に同じように作業できることが、保証されます。</span><span class="sxs-lookup"><span data-stu-id="7a178-145">It ensures that you can always do things the same way with any cmdlet.</span></span> <span data-ttu-id="7a178-146">コマンドレットの開発者は、コマンドライン引数の解析や出力形式の設定のために、コードを記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7a178-146">Cmdlet developers don't need to write code to parse the command-line arguments or format the output.</span></span>

<span data-ttu-id="7a178-147">従来のコマンドライン ツールでは、ヘルプの要求と表示に独自の体系が採用されていました。</span><span class="sxs-lookup"><span data-stu-id="7a178-147">Traditional command-line tools have their own schemes for requesting and displaying Help.</span></span> <span data-ttu-id="7a178-148">一部のコマンドライン ツールでは、`/?` を使用してヘルプを表示します。他では、`-?`、`/H`、または `//` を使用します。</span><span class="sxs-lookup"><span data-stu-id="7a178-148">Some command-line tools use `/?` to trigger the Help display; others use `-?`, `/H`, or even `//`.</span></span> <span data-ttu-id="7a178-149">ヘルプがコンソール画面に表示される代わりに、GUI のウィンドウに表示されるものもあります。</span><span class="sxs-lookup"><span data-stu-id="7a178-149">Some will display Help in a GUI window, rather than in the console display.</span></span> <span data-ttu-id="7a178-150">間違ったパラメーターを使用すると、入力内容が無視され、タスクの実行が自動的に開始される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7a178-150">If you use the wrong parameter, the tool might ignore what you typed and begin executing a task automatically.</span></span>
<span data-ttu-id="7a178-151">PowerShell はコマンドラインを自動的に解析して処理するため、`-?` パラメーターは常に "このコマンドのヘルプを表示する" ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7a178-151">Since PowerShell automatically parses and processes the command line, the `-?` parameter always means "show me Help for this command".</span></span>

> [!NOTE]
> <span data-ttu-id="7a178-152">PowerShell でグラフィック アプリケーションを実行した場合は、そのアプリケーションのウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="7a178-152">If you run a graphic application in PowerShell, the window for the application opens.</span></span>
> <span data-ttu-id="7a178-153">PowerShell が介在するのは、ユーザーによって指定されたコマンドライン入力を処理するときと、コンソール ウィンドウに返されたアプリケーション出力を処理するときだけです。</span><span class="sxs-lookup"><span data-stu-id="7a178-153">PowerShell intervenes only when processing the command-line input you supply or the application output returned to the console window.</span></span> <span data-ttu-id="7a178-154">アプリケーション内部の動作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="7a178-154">It does not affect how the application works internally.</span></span>

## <a name="powershell-has-a-pipeline"></a><span data-ttu-id="7a178-155">PowerShell にはパイプラインがある</span><span class="sxs-lookup"><span data-stu-id="7a178-155">PowerShell has a pipeline</span></span>

<span data-ttu-id="7a178-156">パイプラインは、コマンドライン インターフェイスで使用される最も重要な概念と言っても過言ではありません。</span><span class="sxs-lookup"><span data-stu-id="7a178-156">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="7a178-157">パイプラインは、適切に利用すれば、複雑なコマンドを使用する負荷を軽減し、より簡単に作業フローを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7a178-157">When used properly, pipelines reduce the effort of using complex commands and make it easier to see the flow of work.</span></span> <span data-ttu-id="7a178-158">パイプライン内の各コマンドは、項目ごとに次のコマンドに出力を渡します。</span><span class="sxs-lookup"><span data-stu-id="7a178-158">Each command in a pipeline passes its output, item by item, to the next command.</span></span> <span data-ttu-id="7a178-159">コマンドでは、一度に複数の項目を処理する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="7a178-159">Commands don't have to handle more than one item at a time.</span></span> <span data-ttu-id="7a178-160">結果として、リソース使用量が減り、出力をすぐに取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7a178-160">The result is reduced resource consumption and the ability to get output immediately.</span></span>

<span data-ttu-id="7a178-161">パイプラインで使用される表記は、他のシェルで使用される表記とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="7a178-161">The notation used for pipelines is similar to the notation used in other shells.</span></span> <span data-ttu-id="7a178-162">PowerShell でのパイプラインの違いは、一目見ただけではわかりにくいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="7a178-162">At first glance, it may not be apparent how pipelines are different in PowerShell.</span></span> <span data-ttu-id="7a178-163">画面にはテキストが表示されますが、PowerShell は、コマンド間ではテキストではなくオブジェクトを受け渡します。</span><span class="sxs-lookup"><span data-stu-id="7a178-163">Although you see text on the screen, PowerShell pipes objects, not text, between commands.</span></span>

<span data-ttu-id="7a178-164">たとえば、`Out-Host` コマンドレットを使用して、別のコマンドからの出力をページ単位で表示させると、通常のテキストがページごとに分割されて画面上に表示されているだけのように見えます。</span><span class="sxs-lookup"><span data-stu-id="7a178-164">For example, if you use the `Out-Host` cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```powershell
Get-ChildItem | Out-Host -Paging
```

```Output
    Directory: /mnt/c/Git/PS-Docs/PowerShell-Docs/reference/7.0/Microsoft.PowerShell.Core

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          05/22/2020    08:30                About
-----          05/20/2020    14:36           9044 Add-History.md
-----          05/20/2020    14:36          12227 Clear-History.md
-----          05/20/2020    14:36           3566 Clear-Host.md
-----          05/20/2020    14:36          29087 Connect-PSSession.md
-----          05/20/2020    14:36           5705 Debug-Job.md
-----          05/20/2020    14:36           3515 Disable-ExperimentalFeature.md
-----          05/20/2020    14:36          25531 Disable-PSRemoting.md
-----          05/20/2020    14:36           7852 Disable-PSSessionConfiguration.md
-----          05/20/2020    14:36          25355 Disconnect-PSSession.md
-----          05/20/2020    14:36           3491 Enable-ExperimentalFeature.md
-----          05/20/2020    14:36          13310 Enable-PSRemoting.md
-----          05/20/2020    14:36           8401 Enable-PSSessionConfiguration.md
-----          05/20/2020    14:36           9531 Enter-PSHostProcess.md
...
<SPACE> next page; <CR> next line; Q quit
```

<span data-ttu-id="7a178-165">また、表示する完全なページが準備できると、`Out-Host` コマンドレットに処理が転送されるため、ページングによって CPU 使用率が低下します。</span><span class="sxs-lookup"><span data-stu-id="7a178-165">Paging also reduces CPU utilization because processing transfers to the `Out-Host` cmdlet when it has a complete page ready to display.</span></span> <span data-ttu-id="7a178-166">パイプライン内で先行するコマンドレットは、次のページの出力が利用可能になるまで、実行を一時停止します。</span><span class="sxs-lookup"><span data-stu-id="7a178-166">The cmdlets that precede it in the pipeline pause execution until the next page of output is available.</span></span>

### <a name="objects-in-the-pipeline"></a><span data-ttu-id="7a178-167">パイプライン内のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="7a178-167">Objects in the pipeline</span></span>

<span data-ttu-id="7a178-168">PowerShell でコマンドレットを実行した場合、コンソール ウィンドウではオブジェクトをテキストで表す必要があるため、テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a178-168">When you run a cmdlet in PowerShell, you see text output because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="7a178-169">テキスト出力では、出力されるオブジェクトのすべてのプロパティが必ず表示されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="7a178-169">The text output may not display all of the properties of the object being output.</span></span>

<span data-ttu-id="7a178-170">たとえば、`Get-Location` コマンドレットについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="7a178-170">For example, consider the `Get-Location` cmdlet.</span></span> <span data-ttu-id="7a178-171">テキストの出力は情報の要約であり、`Get-Location` から返されたオブジェクトの完全な表現ではありません。</span><span class="sxs-lookup"><span data-stu-id="7a178-171">The text output is a summary of information, not a complete representation of the object returned by `Get-Location`.</span></span> <span data-ttu-id="7a178-172">出力の見出しは、画面の表示用にデータを書式設定する処理によって、追加されます。</span><span class="sxs-lookup"><span data-stu-id="7a178-172">The heading in the output is added by the process that formats the data for onscreen display.</span></span>

```powershell
Get-Location
```

```Output
Path
----
C:\
```

<span data-ttu-id="7a178-173">出力を `Get-Member` コマンドレットにパイプ処理すると、`Get-Location` から返されたオブジェクトに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a178-173">Piping the output to the `Get-Member` cmdlet displays information about the object returned by `Get-Location`.</span></span>

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

<span data-ttu-id="7a178-174">`Get-Location` は、現在のパスとその他の情報を含む **PathInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7a178-174">`Get-Location` returns a **PathInfo** object that contains the current path and other information.</span></span>

## <a name="built-in-help-system"></a><span data-ttu-id="7a178-175">組み込みのヘルプ システム</span><span class="sxs-lookup"><span data-stu-id="7a178-175">Built-in help system</span></span>

<span data-ttu-id="7a178-176">PowerShell には、Unix の `man` ページと似た PowerShell の概念とコマンド構文を詳細に説明するヘルプ記事があります。</span><span class="sxs-lookup"><span data-stu-id="7a178-176">Similar to Unix `man` pages, PowerShell includes detailed help articles that explain PowerShell concepts and command syntax.</span></span> <span data-ttu-id="7a178-177">[Get-Help][] コマンドレットを使用すると、これらの記事をコマンド プロンプトで表示できます。PowerShell ドキュメント オンラインでは、これらの記事の最新版を参照できます。</span><span class="sxs-lookup"><span data-stu-id="7a178-177">Use the [Get-Help][] cmdlet to display these articles at the command prompt or view the most recently updated versions of these articles in the PowerShell documentation online.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7a178-178">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7a178-178">Next steps</span></span>

<span data-ttu-id="7a178-179">PowerShell の詳細については、このサイトの「 **PowerShell の習得** 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a178-179">To learn more about PowerShell, see the **Learning PowerShell** section of this site.</span></span>

<!-- link references -->

[Get-Help]: /powershell/module/microsoft.powershell.core/Get-Help

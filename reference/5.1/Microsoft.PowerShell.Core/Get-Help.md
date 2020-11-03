---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Help
ms.openlocfilehash: a9a7aa7730d920bb78e0ae64daa50e5a28921163
ms.sourcegitcommit: b7ff031a12afd04910aeb98345ebee92f5845b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "93219003"
---
# <span data-ttu-id="a21da-103">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a21da-103">Get-Help</span></span>

## <span data-ttu-id="a21da-104">概要</span><span class="sxs-lookup"><span data-stu-id="a21da-104">SYNOPSIS</span></span>
<span data-ttu-id="a21da-105">PowerShell コマンドと概念に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-105">Displays information about PowerShell commands and concepts.</span></span>

## <span data-ttu-id="a21da-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a21da-106">SYNTAX</span></span>

### <span data-ttu-id="a21da-107">AllUsersView (既定値)</span><span class="sxs-lookup"><span data-stu-id="a21da-107">AllUsersView (Default)</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [-Full] [<CommonParameters>]
```

### <span data-ttu-id="a21da-108">DetailedView</span><span class="sxs-lookup"><span data-stu-id="a21da-108">DetailedView</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Detailed [<CommonParameters>]
```

### <span data-ttu-id="a21da-109">例</span><span class="sxs-lookup"><span data-stu-id="a21da-109">Examples</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Examples [<CommonParameters>]
```

### <span data-ttu-id="a21da-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a21da-110">Parameters</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Parameter <String> [<CommonParameters>]
```

### <span data-ttu-id="a21da-111">オンライン</span><span class="sxs-lookup"><span data-stu-id="a21da-111">Online</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Online [<CommonParameters>]
```

### <span data-ttu-id="a21da-112">ShowWindow</span><span class="sxs-lookup"><span data-stu-id="a21da-112">ShowWindow</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -ShowWindow [<CommonParameters>]
```

## <span data-ttu-id="a21da-113">Description</span><span class="sxs-lookup"><span data-stu-id="a21da-113">DESCRIPTION</span></span>

<span data-ttu-id="a21da-114">コマンド `Get-Help` レットでは、コマンドレット、関数、Common Information Model (CIM) コマンド、ワークフロー、プロバイダー、エイリアス、スクリプトなど、PowerShell の概念とコマンドに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-114">The `Get-Help` cmdlet displays information about PowerShell concepts and commands, including cmdlets, functions, Common Information Model (CIM) commands, workflows, providers, aliases, and scripts.</span></span>

<span data-ttu-id="a21da-115">PowerShell コマンドレットのヘルプを表示するには、「」のように、 `Get-Help` コマンドレット名の後に「」と入力し `Get-Help Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-115">To get help for a PowerShell cmdlet, type `Get-Help` followed by the cmdlet name, such as: `Get-Help Get-Process`.</span></span>

<span data-ttu-id="a21da-116">PowerShell の概念説明ヘルプ記事は、 **about_Comparison_Operators** などの **about_** から始まります。</span><span class="sxs-lookup"><span data-stu-id="a21da-116">Conceptual help articles in PowerShell begin with **about_** , such as **about_Comparison_Operators**.</span></span> <span data-ttu-id="a21da-117">すべての **about_** 記事を表示するには、「」と入力 `Get-Help about_*` します。</span><span class="sxs-lookup"><span data-stu-id="a21da-117">To see all **about_** articles, type `Get-Help about_*`.</span></span> <span data-ttu-id="a21da-118">特定の記事を表示するには、のように「 `Get-Help about_<article-name>` 」と入力し `Get-Help about_Comparison_Operators` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-118">To see a particular article, type `Get-Help about_<article-name>`, such as `Get-Help about_Comparison_Operators`.</span></span>

<span data-ttu-id="a21da-119">PowerShell プロバイダーのヘルプを表示するには、 `Get-Help` プロバイダー名の後に「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a21da-119">To get help for a PowerShell provider, type `Get-Help` followed by the provider name.</span></span> <span data-ttu-id="a21da-120">たとえば、証明書プロバイダーのヘルプを表示するには、「」と入力 `Get-Help Certificate` します。</span><span class="sxs-lookup"><span data-stu-id="a21da-120">For example, to get help for the Certificate provider, type `Get-Help Certificate`.</span></span>

<span data-ttu-id="a21da-121">`help`または `man` を入力して、一度に1つのテキスト画面を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="a21da-121">You can also type `help` or `man`, which displays one screen of text at a time.</span></span> <span data-ttu-id="a21da-122">または、はと `<cmdlet-name> -?` 同じです `Get-Help` が、コマンドレットに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a21da-122">Or, `<cmdlet-name> -?`, that is identical to `Get-Help`, but only works for cmdlets.</span></span>

<span data-ttu-id="a21da-123">`Get-Help` コンピューター上のヘルプファイルから表示されるヘルプコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21da-123">`Get-Help` gets the help content that it displays from help files on your computer.</span></span> <span data-ttu-id="a21da-124">ヘルプファイルがない場合は、 `Get-Help` コマンドレットに関する基本的な情報のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-124">Without the help files, `Get-Help` displays only basic information about cmdlets.</span></span> <span data-ttu-id="a21da-125">一部の PowerShell モジュールには、ヘルプファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a21da-125">Some PowerShell modules include help files.</span></span> <span data-ttu-id="a21da-126">PowerShell 3.0 以降では、Windows オペレーティングシステムに付属のモジュールにヘルプファイルは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="a21da-126">Beginning in PowerShell 3.0, the modules that come with the Windows operating system don't include help files.</span></span> <span data-ttu-id="a21da-127">PowerShell 3.0 でモジュールのヘルプファイルをダウンロードまたは更新するには、 `Update-Help` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a21da-127">To download or update the help files for a module in PowerShell 3.0, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="a21da-128">Microsoft Docs で PowerShell のヘルプドキュメントをオンラインで表示することもできます。ヘルプファイルのオンラインバージョンを取得するには、のように、 **online** パラメーターを使用し `Get-Help Get-Process -Online` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-128">You can also view the PowerShell help documents online in the Microsoft Docs. To get the online version of a help file, use the **Online** parameter, such as: `Get-Help Get-Process -Online`.</span></span> <span data-ttu-id="a21da-129">PowerShell のドキュメントをすべて読み取るには、Microsoft Docs [powershell のドキュメント](/powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-129">To read all the PowerShell documentation, see the Microsoft Docs [PowerShell Documentation](/powershell).</span></span>

<span data-ttu-id="a21da-130">`Get-Help`ヘルプ記事の正確な名前、またはヘルプ記事に固有の単語を入力すると、によって `Get-Help` その記事の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-130">If you type `Get-Help` followed by the exact name of a help article, or by a word unique to a help article, `Get-Help` displays the article's content.</span></span> <span data-ttu-id="a21da-131">コマンドエイリアスの正確な名前を指定すると、によって `Get-Help` 元のコマンドのヘルプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-131">If you specify the exact name of a command alias, `Get-Help` displays the help for the original command.</span></span> <span data-ttu-id="a21da-132">複数のヘルプ記事のタイトルに表示される単語または単語のパターンを入力すると、 `Get-Help` 一致するタイトルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-132">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span> <span data-ttu-id="a21da-133">ヘルプ記事のタイトルに表示されていないテキストを入力すると、 `Get-Help` そのテキストを内容に含む記事の一覧がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-133">If you enter any text that doesn't appear in any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="a21da-134">`Get-Help` サポートされているすべての言語およびロケールのヘルプ記事を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-134">`Get-Help` can get help articles for all supported languages and locales.</span></span> <span data-ttu-id="a21da-135">`Get-Help` は、最初に、Windows に設定されているロケールでヘルプファイルを検索し、次に、親ロケール (たとえば、pt の **pt** **-BR** ) で、次にフォールバックロケールでヘルプファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="a21da-135">`Get-Help` first looks for help files in the locale set for Windows, then in the parent locale, such as **pt** for **pt-BR** , and then in a fallback locale.</span></span> <span data-ttu-id="a21da-136">PowerShell 3.0 以降では、フォールバックロケールでヘルプが見つからない場合、では、 `Get-Help` エラーメッセージを返すか、自動生成されたヘルプを表示する前に、英語 ( **en-us** ) のヘルプ記事が検索されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-136">Beginning in PowerShell 3.0, if `Get-Help` doesn't find help in the fallback locale, it looks for help articles in English, **en-US** , before it returns an error message or displaying autogenerated help.</span></span>

<span data-ttu-id="a21da-137">コマンド構文ダイアグラムに表示されるシンボルの詳細については `Get-Help` 、「 [about_Command_Syntax](./About/about_Command_Syntax.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-137">For information about the symbols that `Get-Help` displays in the command syntax diagram, see [about_Command_Syntax](./About/about_Command_Syntax.md).</span></span>
<span data-ttu-id="a21da-138">**Required** や **Position** などのパラメーター属性の詳細については、「 [about_Parameters](./About/about_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-138">For information about parameter attributes, such as **Required** and **Position** , see [about_Parameters](./About/about_Parameters.md).</span></span>

>[!NOTE]
> <span data-ttu-id="a21da-139">PowerShell 3.0 および PowerShell 4.0 では、 `Get-Help` モジュールが現在のセッションにインポートされ **て** いない限り、はモジュール内の記事を見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="a21da-139">In PowerShell 3.0 and PowerShell 4.0, `Get-Help` can't find **About** articles in modules unless the module is imported into the current session.</span></span> <span data-ttu-id="a21da-140">これは既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="a21da-140">This is a known issue.</span></span> <span data-ttu-id="a21da-141">モジュール内の記事 **に関する情報** を取得するには、コマンドレットを使用するか、 `Import-Module` モジュールに含まれているコマンドレットを実行して、モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a21da-141">To get **About** articles in a module, import the module, either by using the `Import-Module` cmdlet or by running a cmdlet that's included in the module.</span></span>

## <span data-ttu-id="a21da-142">例</span><span class="sxs-lookup"><span data-stu-id="a21da-142">EXAMPLES</span></span>

### <span data-ttu-id="a21da-143">例 1: コマンドレットに関する基本的なヘルプ情報を表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-143">Example 1: Display basic help information about a cmdlet</span></span>

<span data-ttu-id="a21da-144">これらの例では、コマンドレットに関する基本的なヘルプ情報が表示さ `Format-Table` れます。</span><span class="sxs-lookup"><span data-stu-id="a21da-144">These examples display basic help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table
Get-Help -Name Format-Table
Format-Table -?
```

<span data-ttu-id="a21da-145">`Get-Help <cmdlet-name>` は、コマンドレットの最も簡単な既定の構文です `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="a21da-145">`Get-Help <cmdlet-name>` is the simplest and default syntax of `Get-Help` cmdlet.</span></span> <span data-ttu-id="a21da-146">**Name** パラメーターは省略できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-146">You can omit the **Name** parameter.</span></span>

<span data-ttu-id="a21da-147">構文は `<cmdlet-name> -?` コマンドレットに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a21da-147">The syntax `<cmdlet-name> -?` works only for cmdlets.</span></span>

### <span data-ttu-id="a21da-148">例 2: 基本的な情報を1ページずつ表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-148">Example 2: Display basic information one page at a time</span></span>

<span data-ttu-id="a21da-149">これらの例では、コマンドレットの基本的なヘルプ情報 `Format-Table` が1ページずつ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-149">These examples display basic help information about the `Format-Table` cmdlet one page at a time.</span></span>

```powershell
help Format-Table
man Format-Table
Get-Help Format-Table | Out-Host -Paging
```

<span data-ttu-id="a21da-150">`help` は、 `Get-Help` コマンドレットを内部的に実行し、結果を1ページずつ表示する関数です。</span><span class="sxs-lookup"><span data-stu-id="a21da-150">`help` is a function that runs `Get-Help` cmdlet internally and displays the result one page at a time.</span></span>

<span data-ttu-id="a21da-151">`man` 関数のエイリアスです `help` 。</span><span class="sxs-lookup"><span data-stu-id="a21da-151">`man` is an alias for the `help` function.</span></span>

<span data-ttu-id="a21da-152">`Get-Help Format-Table` オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="a21da-152">`Get-Help Format-Table` sends the object down the pipeline.</span></span> <span data-ttu-id="a21da-153">`Out-Host -Paging` パイプラインからの出力を受け取り、一度に1ページずつ表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-153">`Out-Host -Paging` receives the output from the pipeline and displays it one page at a time.</span></span> <span data-ttu-id="a21da-154">詳細については、「 [Out Host](Out-Host.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-154">For more information, see [Out-Host](Out-Host.md).</span></span>

### <span data-ttu-id="a21da-155">例 3: コマンドレットの詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-155">Example 3: Display more information for a cmdlet</span></span>

<span data-ttu-id="a21da-156">これらの例では、コマンドレットの詳細なヘルプ情報が表示さ `Format-Table` れます。</span><span class="sxs-lookup"><span data-stu-id="a21da-156">These examples display more detailed help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table -Detailed
Get-Help Format-Table -Full
```

<span data-ttu-id="a21da-157">**詳細** パラメーターには、パラメーターの説明と例を含むヘルプ記事の詳細ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-157">The **Detailed** parameter displays the help article's detailed view that includes parameter descriptions and examples.</span></span>

<span data-ttu-id="a21da-158">**Full** パラメーターは、パラメーターの説明、例、入力オブジェクトと出力オブジェクトの種類、および追加のメモを含むヘルプ記事の完全なビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-158">The **Full** parameter displays the help article's full view that includes parameter descriptions, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="a21da-159">**詳細** パラメーターと **完全** パラメーターは、コンピューターにヘルプファイルがインストールされているコマンドに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a21da-159">The **Detailed** and **Full** parameters are effective only for the commands that have help files installed on the computer.</span></span> <span data-ttu-id="a21da-160">これらのパラメーターは、概念 ( **about_** ) のヘルプ記事には有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a21da-160">The parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="a21da-161">例 4: パラメーターを使用して、コマンドレットの選択した部分を表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-161">Example 4: Display selected parts of a cmdlet by using parameters</span></span>

<span data-ttu-id="a21da-162">これらの例では、コマンドレットのヘルプの選択部分を表示し `Format-Table` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-162">These examples display selected portions of the `Format-Table` cmdlet help.</span></span>

```powershell
Get-Help Format-Table -Examples
Get-Help Format-Table -Parameter *
Get-Help Format-Table -Parameter GroupBy
```

<span data-ttu-id="a21da-163">**例** のパラメーターには、ヘルプファイルの **名前** と **概要** 、およびすべての例が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-163">The **Examples** parameter displays the help file's **NAME** and **SYNOPSIS** sections, and all the Examples.</span></span> <span data-ttu-id="a21da-164">**例のパラメーターは** スイッチパラメーターであるため、例の番号を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a21da-164">You can't specify an Example number because the **Examples** parameter is a switch parameter.</span></span>

<span data-ttu-id="a21da-165">**Parameter** パラメーターには、指定されたパラメーターの説明だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-165">The **Parameter** parameter displays only the descriptions of the specified parameters.</span></span> <span data-ttu-id="a21da-166">アスタリスク () のワイルドカード文字のみを指定すると `*` 、すべてのパラメーターの説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-166">If you specify only the asterisk (`*`) wildcard character, it displays the descriptions of all parameters.</span></span>
<span data-ttu-id="a21da-167">**パラメーター** で **GroupBy** などのパラメーター名を指定すると、そのパラメーターに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-167">When **Parameter** specifies a parameter name such as **GroupBy** , information about that parameter is shown.</span></span>

<span data-ttu-id="a21da-168">これらのパラメーターは、概念 ( **about_** ) のヘルプ記事には有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a21da-168">These parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="a21da-169">例 5: オンラインバージョンのヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-169">Example 5: Display online version of help</span></span>

<span data-ttu-id="a21da-170">この例では、 `Format-Table` 既定の web ブラウザーでコマンドレットのヘルプ記事のオンラインバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-170">This example displays the online version of the help article for the `Format-Table` cmdlet in your default web browser.</span></span>

```powershell
Get-Help Format-Table -Online
```

### <span data-ttu-id="a21da-171">例 6: ヘルプシステムに関するヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-171">Example 6: Display help about the help system</span></span>

<span data-ttu-id="a21da-172">パラメーターを指定せずにコマンドレットを実行すると、 `Get-Help` PowerShell ヘルプシステムに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-172">The `Get-Help` cmdlet without parameters displays information about the PowerShell help system.</span></span>

```powershell
Get-Help
```

### <span data-ttu-id="a21da-173">例 7: 使用可能なヘルプ記事を表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-173">Example 7: Display available help articles</span></span>

<span data-ttu-id="a21da-174">この例では、お使いのコンピューターで利用可能なすべてのヘルプ記事の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-174">This example displays a list of all help articles available on your computer.</span></span>

```powershell
Get-Help *
```

### <span data-ttu-id="a21da-175">例 8: 概念説明の記事の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-175">Example 8: Display a list of conceptual articles</span></span>

<span data-ttu-id="a21da-176">この例では、PowerShell ヘルプに含まれる概念説明の記事の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-176">This example displays a list of the conceptual articles included in PowerShell help.</span></span> <span data-ttu-id="a21da-177">これらの記事はすべて **about_** 文字で始まります。</span><span class="sxs-lookup"><span data-stu-id="a21da-177">All these articles begin with the characters **about_**.</span></span> <span data-ttu-id="a21da-178">特定のヘルプファイルを表示するには、たとえば「」と入力 `Get-Help \<about_article-name\>` `Get-Help about_Signing` します。</span><span class="sxs-lookup"><span data-stu-id="a21da-178">To display a particular help file, type `Get-Help \<about_article-name\>`, for example, `Get-Help about_Signing`.</span></span>

<span data-ttu-id="a21da-179">コンピューターにヘルプファイルがインストールされている概念説明の記事のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-179">Only the conceptual articles that have help files installed on your computer are displayed.</span></span> <span data-ttu-id="a21da-180">PowerShell 3.0 でヘルプファイルをダウンロードしてインストールする方法の詳細については、「 [update-help](Update-Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-180">For information about downloading and installing help files in PowerShell 3.0, see [Update-Help](Update-Help.md).</span></span>

```powershell
Get-Help about_*
```

### <span data-ttu-id="a21da-181">例 9: コマンドレットのヘルプで単語を検索する</span><span class="sxs-lookup"><span data-stu-id="a21da-181">Example 9: Search for a word in cmdlet help</span></span>

<span data-ttu-id="a21da-182">この例は、コマンドレットのヘルプ記事で単語を検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a21da-182">This example shows how to search for a word in a cmdlet help article.</span></span>

```powershell
Get-Help Add-Member -Full | Out-String -Stream | Select-String -Pattern Clixml
```

```Output
the Export-Clixml cmdlet to save the instance of the object, including the additional members...
can use the Import-Clixml cmdlet to re-create the instance of the object from the information...
Export-Clixml
Import-Clixml
```

<span data-ttu-id="a21da-183">`Get-Help` は、 **完全な** パラメーターを使用してのヘルプ情報を取得し `Add-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-183">`Get-Help` uses the **Full** parameter to get help information for `Add-Member`.</span></span> <span data-ttu-id="a21da-184">**MamlCommandHelpInfo** オブジェクトは、パイプラインを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-184">The **MamlCommandHelpInfo** object is sent down the pipeline.</span></span> <span data-ttu-id="a21da-185">`Out-String`**Stream** パラメーターを使用して、オブジェクトを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="a21da-185">`Out-String` uses the **Stream** parameter to convert the object into a string.</span></span> <span data-ttu-id="a21da-186">`Select-String`**Pattern** パラメーターを使用して、 **export-clixml** 文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="a21da-186">`Select-String` uses the **Pattern** parameter to search the string for **Clixml**.</span></span>

### <span data-ttu-id="a21da-187">例 10: 単語を含む記事の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-187">Example 10: Display a list of articles that include a word</span></span>

<span data-ttu-id="a21da-188">この例では、 **リモート処理** という単語を含む記事の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-188">This example displays a list of articles that include the word **remoting**.</span></span>

<span data-ttu-id="a21da-189">どの記事のタイトルにも表示されない単語を入力すると、 `Get-Help` その単語を含む記事の一覧がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-189">When you enter a word that doesn't appear in any article title, `Get-Help` displays a list of articles that include that word.</span></span>

```powershell
Get-Help -Name remoting
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Install-PowerShellRemoting.ps1    External                            Install-PowerShellRemoting.ps1
Disable-PSRemoting                Cmdlet    Microsoft.PowerShell.Core Prevents remote users...
Enable-PSRemoting                 Cmdlet    Microsoft.PowerShell.Core Configures the computer...
```

### <span data-ttu-id="a21da-190">例 11: プロバイダー固有のヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-190">Example 11: Display provider-specific help</span></span>

<span data-ttu-id="a21da-191">この例では、のプロバイダー固有のヘルプを取得する2つの方法を示し `Get-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-191">This example shows two ways of getting the provider-specific help for `Get-Item`.</span></span> <span data-ttu-id="a21da-192">これらのコマンドは、 `Get-Item` PowerShell SQL Server プロバイダーの **DataCollection** ノードでコマンドレットを使用する方法を説明するヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-192">These commands get help that explains how to use the `Get-Item` cmdlet in the PowerShell SQL Server provider's **DataCollection** node.</span></span>

<span data-ttu-id="a21da-193">最初の例では、path パラメーターを使用して `Get-Help` **Path** 、SQL Server プロバイダーのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a21da-193">The first example uses the `Get-Help` **Path** parameter to specify the SQL Server provider's path.</span></span>
<span data-ttu-id="a21da-194">プロバイダーのパスが指定されているため、任意のパスの場所からコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-194">Because the provider's path is specified, you can run the command from any path location.</span></span>

<span data-ttu-id="a21da-195">2番目の例では、を使用し `Set-Location` て、SQL Server プロバイダーのパスに移動します。</span><span class="sxs-lookup"><span data-stu-id="a21da-195">The second example uses `Set-Location` to navigate to the SQL Server provider's path.</span></span> <span data-ttu-id="a21da-196">この場所から、プロバイダー固有のヘルプを取得するために、 **Path** パラメーターは必要ありません `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="a21da-196">From that location, the **Path** parameter isn't needed for `Get-Help` to get the provider-specific help.</span></span>

```powershell
Get-Help Get-Item -Path SQLSERVER:\DataCollection
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

```powershell
Set-Location SQLSERVER:\DataCollection
SQLSERVER:\DataCollection> Get-Help Get-Item
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

### <span data-ttu-id="a21da-197">例 12: スクリプトのヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-197">Example 12: Display help for a script</span></span>

<span data-ttu-id="a21da-198">この例では、のヘルプを取得し `MyScript.ps1 script` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-198">This example gets help for the `MyScript.ps1 script`.</span></span> <span data-ttu-id="a21da-199">関数とスクリプトのヘルプを記述する方法の詳細については、「 [about_Comment_Based_Help](./About/about_Comment_Based_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-199">For information about how to write help for your functions and scripts, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span></span>

```powershell
Get-Help -Name C:\PS-Test\MyScript.ps1
```

## <span data-ttu-id="a21da-200">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a21da-200">PARAMETERS</span></span>

### <span data-ttu-id="a21da-201">-カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a21da-201">-Category</span></span>

<span data-ttu-id="a21da-202">指定したカテゴリの項目とそのエイリアスに対してのみヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-202">Displays help only for items in the specified category and their aliases.</span></span> <span data-ttu-id="a21da-203">概念説明の記事は、 **HelpFile** カテゴリに含まれています。</span><span class="sxs-lookup"><span data-stu-id="a21da-203">Conceptual articles are in the **HelpFile** category.</span></span>

<span data-ttu-id="a21da-204">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a21da-204">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a21da-205">エイリアス</span><span class="sxs-lookup"><span data-stu-id="a21da-205">Alias</span></span>
- <span data-ttu-id="a21da-206">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a21da-206">Cmdlet</span></span>
- <span data-ttu-id="a21da-207">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="a21da-207">Provider</span></span>
- <span data-ttu-id="a21da-208">全般</span><span class="sxs-lookup"><span data-stu-id="a21da-208">General</span></span>
- <span data-ttu-id="a21da-209">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="a21da-209">FAQ</span></span>
- <span data-ttu-id="a21da-210">用語集</span><span class="sxs-lookup"><span data-stu-id="a21da-210">Glossary</span></span>
- <span data-ttu-id="a21da-211">HelpFile</span><span class="sxs-lookup"><span data-stu-id="a21da-211">HelpFile</span></span>
- <span data-ttu-id="a21da-212">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="a21da-212">ScriptCommand</span></span>
- <span data-ttu-id="a21da-213">機能</span><span class="sxs-lookup"><span data-stu-id="a21da-213">Function</span></span>
- <span data-ttu-id="a21da-214">Assert</span><span class="sxs-lookup"><span data-stu-id="a21da-214">Filter</span></span>
- <span data-ttu-id="a21da-215">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="a21da-215">ExternalScript</span></span>
- <span data-ttu-id="a21da-216">All</span><span class="sxs-lookup"><span data-stu-id="a21da-216">All</span></span>
- <span data-ttu-id="a21da-217">DefaultHelp</span><span class="sxs-lookup"><span data-stu-id="a21da-217">DefaultHelp</span></span>
- <span data-ttu-id="a21da-218">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="a21da-218">Workflow</span></span>
- <span data-ttu-id="a21da-219">DscResource</span><span class="sxs-lookup"><span data-stu-id="a21da-219">DscResource</span></span>
- <span data-ttu-id="a21da-220">クラス</span><span class="sxs-lookup"><span data-stu-id="a21da-220">Class</span></span>
- <span data-ttu-id="a21da-221">構成</span><span class="sxs-lookup"><span data-stu-id="a21da-221">Configuration</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Alias, Cmdlet, Provider, General, FAQ, Glossary, HelpFile, ScriptCommand, Function, Filter, ExternalScript, All, DefaultHelp, Workflow, DscResource, Class, Configuration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21da-222">-コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a21da-222">-Component</span></span>

<span data-ttu-id="a21da-223">**Exchange** など、指定されたコンポーネント値を持つコマンドを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-223">Displays commands with the specified component value, such as **Exchange**.</span></span> <span data-ttu-id="a21da-224">コンポーネント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a21da-224">Enter a component name.</span></span>
<span data-ttu-id="a21da-225">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-225">Wildcard characters are permitted.</span></span> <span data-ttu-id="a21da-226">このパラメーターは、概念 ( **About_** ) ヘルプの表示には影響しません。</span><span class="sxs-lookup"><span data-stu-id="a21da-226">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a21da-227">-Detailed</span><span class="sxs-lookup"><span data-stu-id="a21da-227">-Detailed</span></span>

<span data-ttu-id="a21da-228">基本的なヘルプの表示に加えてパラメーターの説明と例を表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-228">Adds parameter descriptions and examples to the basic help display.</span></span> <span data-ttu-id="a21da-229">このパラメーターは、ヘルプファイルがコンピューターにインストールされている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a21da-229">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="a21da-230">概念 ( **About_** ) のヘルプの表示には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="a21da-230">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetailedView
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21da-231">-Examples</span><span class="sxs-lookup"><span data-stu-id="a21da-231">-Examples</span></span>

<span data-ttu-id="a21da-232">名前、概要、例のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-232">Displays only the name, synopsis, and examples.</span></span> <span data-ttu-id="a21da-233">例のみを表示するには、「」と入力 `(Get-Help \<cmdlet-name\>).Examples` します。</span><span class="sxs-lookup"><span data-stu-id="a21da-233">To display only the examples, type `(Get-Help \<cmdlet-name\>).Examples`.</span></span>

<span data-ttu-id="a21da-234">このパラメーターは、ヘルプファイルがコンピューターにインストールされている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a21da-234">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="a21da-235">概念 ( **About_** ) のヘルプの表示には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="a21da-235">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Examples
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21da-236">-Full</span><span class="sxs-lookup"><span data-stu-id="a21da-236">-Full</span></span>

<span data-ttu-id="a21da-237">コマンドレットのヘルプ記事全体を表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-237">Displays the entire help article for a cmdlet.</span></span> <span data-ttu-id="a21da-238">**完全** には、パラメーターの説明と属性、例、入力オブジェクトと出力オブジェクトの種類、および追加のメモが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a21da-238">**Full** includes parameter descriptions and attributes, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="a21da-239">このパラメーターは、ヘルプファイルがコンピューターにインストールされている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a21da-239">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="a21da-240">概念 ( **About_** ) のヘルプの表示には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="a21da-240">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllUsersView
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21da-241">-機能</span><span class="sxs-lookup"><span data-stu-id="a21da-241">-Functionality</span></span>

<span data-ttu-id="a21da-242">指定した機能を持つ項目のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-242">Displays help for items with the specified functionality.</span></span> <span data-ttu-id="a21da-243">機能を入力します。</span><span class="sxs-lookup"><span data-stu-id="a21da-243">Enter the functionality.</span></span> <span data-ttu-id="a21da-244">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-244">Wildcard characters are permitted.</span></span> <span data-ttu-id="a21da-245">このパラメーターは、概念 ( **About_** ) ヘルプの表示には影響しません。</span><span class="sxs-lookup"><span data-stu-id="a21da-245">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a21da-246">-Name</span><span class="sxs-lookup"><span data-stu-id="a21da-246">-Name</span></span>

<span data-ttu-id="a21da-247">指定したコマンドまたは概念に関するヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21da-247">Gets help about the specified command or concept.</span></span> <span data-ttu-id="a21da-248">コマンドレット、関数、プロバイダー、スクリプト、またはワークフローの名前 (など)、またはのような概念記事の名前 (など)、 `Get-Member` またはエイリアス (など) を入力し `about_Objects` `ls` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-248">Enter the name of a cmdlet, function, provider, script, or workflow, such as `Get-Member`, a conceptual article name, such as `about_Objects`, or an alias, such as `ls`.</span></span> <span data-ttu-id="a21da-249">コマンドレットとプロバイダー名にはワイルドカード文字を使用できますが、ワイルドカード文字を使用して関数のヘルプおよびスクリプトのヘルプ記事の名前を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="a21da-249">Wildcard characters are permitted in cmdlet and provider names, but you can't use wildcard characters to find the names of function help and script help articles.</span></span>

<span data-ttu-id="a21da-250">環境変数に示されているパスにないスクリプトのヘルプを表示するには `$env:Path` 、スクリプトのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a21da-250">To get help for a script that isn't located in a path that's listed in the `$env:Path` environment variable, type the script's path and file name.</span></span>

<span data-ttu-id="a21da-251">ヘルプ記事の正確な名前を入力すると、に `Get-Help` その記事の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-251">If you enter the exact name of a help article, `Get-Help` displays the article contents.</span></span>

<span data-ttu-id="a21da-252">複数のヘルプ記事のタイトルに表示される単語または単語のパターンを入力すると、 `Get-Help` 一致するタイトルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-252">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span>

<span data-ttu-id="a21da-253">ヘルプ記事のタイトルに一致しないテキストを入力すると、 `Get-Help` そのテキストを内容に含む記事の一覧がに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-253">If you enter any text that doesn't match any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="a21da-254">などの概念記事の名前は、 `about_Objects` 英語以外のバージョンの PowerShell でも英語で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21da-254">The names of conceptual articles, such as `about_Objects`, must be entered in English, even in non-English versions of PowerShell.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="a21da-255">-Online</span><span class="sxs-lookup"><span data-stu-id="a21da-255">-Online</span></span>

<span data-ttu-id="a21da-256">ヘルプ記事のオンラインバージョンを既定のブラウザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-256">Displays the online version of a help article in the default browser.</span></span> <span data-ttu-id="a21da-257">このパラメーターは、コマンドレット、関数、ワークフロー、およびスクリプトのヘルプ記事に対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a21da-257">This parameter is valid only for cmdlet, function, workflow, and script help articles.</span></span> <span data-ttu-id="a21da-258">リモートセッションでは、 **Online** パラメーターをと共に使用することはできません `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="a21da-258">You can't use the **Online** parameter with `Get-Help` in a remote session.</span></span>

<span data-ttu-id="a21da-259">記述するヘルプ記事でこの機能をサポートする方法の詳細については、「 [about_Comment_Based_Help](./About/about_Comment_Based_Help.md)」、「 [オンラインヘルプのサポート](/powershell/scripting/developer/module/supporting-online-help)」、および「 [PowerShell コマンドレットのヘルプの作成](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-259">For information about supporting this feature in help articles that you write, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md), and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help), and [Writing Help for PowerShell Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Online
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21da-260">-Parameter</span><span class="sxs-lookup"><span data-stu-id="a21da-260">-Parameter</span></span>

<span data-ttu-id="a21da-261">指定したパラメーターの詳しい説明のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-261">Displays only the detailed descriptions of the specified parameters.</span></span> <span data-ttu-id="a21da-262">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-262">Wildcards are permitted.</span></span> <span data-ttu-id="a21da-263">このパラメーターは、概念 ( **About_** ) ヘルプの表示には影響しません。</span><span class="sxs-lookup"><span data-stu-id="a21da-263">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String
Parameter Sets: Parameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a21da-264">-Path</span><span class="sxs-lookup"><span data-stu-id="a21da-264">-Path</span></span>

<span data-ttu-id="a21da-265">指定されたプロバイダー パスでのコマンドレットの動作を説明するヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21da-265">Gets help that explains how the cmdlet works in the specified provider path.</span></span> <span data-ttu-id="a21da-266">PowerShell プロバイダーのパスを入力してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-266">Enter a PowerShell provider path.</span></span>

<span data-ttu-id="a21da-267">このパラメーターは、コマンドレットヘルプ記事のカスタマイズバージョンを取得します。このコマンドレットは、指定された PowerShell プロバイダーパスでのコマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="a21da-267">This parameter gets a customized version of a cmdlet help article that explains how the cmdlet works in the specified PowerShell provider path.</span></span> <span data-ttu-id="a21da-268">このパラメーターは、プロバイダーコマンドレットに関するヘルプに対してのみ有効です。プロバイダーがヘルプファイルにプロバイダーコマンドレットのヘルプ記事のカスタムバージョンを含める場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a21da-268">This parameter is effective only for help about a provider cmdlet and only when the provider includes a custom version of the provider cmdlet help article in its help file.</span></span> <span data-ttu-id="a21da-269">このパラメーターを使用するには、プロバイダーが含まれるモジュールのヘルプ ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a21da-269">To use this parameter, install the help file for the module that includes the provider.</span></span>

<span data-ttu-id="a21da-270">プロバイダーパスのカスタムコマンドレットのヘルプを表示するには、プロバイダーのパスの場所に移動し、コマンドを入力する `Get-Help` か、任意のパスの場所からの **path** パラメーターを使用して `Get-Help` プロバイダーのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a21da-270">To see the custom cmdlet help for a provider path, go to the provider path location and enter a `Get-Help` command or, from any path location, use the **Path** parameter of `Get-Help` to specify the provider path.</span></span> <span data-ttu-id="a21da-271">ヘルプ記事のプロバイダヘルプセクションで、カスタムコマンドレットのヘルプをオンラインで検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="a21da-271">You can also find custom cmdlet help online in the provider help section of the help articles.</span></span>

<span data-ttu-id="a21da-272">PowerShell プロバイダーの詳細については、「 [about_Providers](./About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-272">For more information about PowerShell providers, see [about_Providers](./About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a21da-273">-ロール</span><span class="sxs-lookup"><span data-stu-id="a21da-273">-Role</span></span>

<span data-ttu-id="a21da-274">指定したユーザー ロール向けにカスタマイズされたヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-274">Displays help customized for the specified user role.</span></span> <span data-ttu-id="a21da-275">ロールを入力します。</span><span class="sxs-lookup"><span data-stu-id="a21da-275">Enter a role.</span></span> <span data-ttu-id="a21da-276">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-276">Wildcard characters are permitted.</span></span>

<span data-ttu-id="a21da-277">組織においてユーザーが果たすロールを入力します。</span><span class="sxs-lookup"><span data-stu-id="a21da-277">Enter the role that the user plays in an organization.</span></span> <span data-ttu-id="a21da-278">一部のコマンドレットでは、このパラメーターの値に基づいて、ヘルプ ファイルに異なるテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-278">Some cmdlets display different text in their help files based on the value of this parameter.</span></span> <span data-ttu-id="a21da-279">このパラメーターは、コア コマンドレットのヘルプには効果を持ちません。</span><span class="sxs-lookup"><span data-stu-id="a21da-279">This parameter has no effect on help for the core cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a21da-280">-ShowWindow</span><span class="sxs-lookup"><span data-stu-id="a21da-280">-ShowWindow</span></span>

<span data-ttu-id="a21da-281">読みやすくするために、ウィンドウにヘルプ トピックを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-281">Displays the help topic in a window for easier reading.</span></span> <span data-ttu-id="a21da-282">このウィンドウには **、検索の検索機能** と、ヘルプトピックの選択したセクションのみを表示するオプションを含む、表示のオプションを設定できる **設定** ボックスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a21da-282">The window includes a **Find** search feature and a **Settings** box that lets you set options for the display, including options to display only selected sections of a help topic.</span></span>

<span data-ttu-id="a21da-283">**ShowWindow** パラメーターは、コマンド (コマンドレット、関数、CIM コマンド、ワークフロー、スクリプト) のヘルプトピックと、記事 **に関する** 概念をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a21da-283">The **ShowWindow** parameter supports help topics for commands (cmdlets, functions, CIM commands, workflows, scripts) and conceptual **About** articles.</span></span> <span data-ttu-id="a21da-284">プロバイダー ヘルプはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a21da-284">It does not support provider help.</span></span>

<span data-ttu-id="a21da-285">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a21da-285">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShowWindow
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21da-286">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a21da-286">CommonParameters</span></span>

<span data-ttu-id="a21da-287">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a21da-287">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a21da-288">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-288">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a21da-289">入力</span><span class="sxs-lookup"><span data-stu-id="a21da-289">INPUTS</span></span>

### <span data-ttu-id="a21da-290">なし</span><span class="sxs-lookup"><span data-stu-id="a21da-290">None</span></span>

<span data-ttu-id="a21da-291">オブジェクトをパイプラインからに送信することはできません `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="a21da-291">You can't send objects down the pipeline to `Get-Help`.</span></span>

## <span data-ttu-id="a21da-292">出力</span><span class="sxs-lookup"><span data-stu-id="a21da-292">OUTPUTS</span></span>

### <span data-ttu-id="a21da-293">ExtendedCmdletHelpInfo</span><span class="sxs-lookup"><span data-stu-id="a21da-293">ExtendedCmdletHelpInfo</span></span>

<span data-ttu-id="a21da-294">`Get-Help`ヘルプファイルのないコマンドでを実行すると、は `Get-Help` 自動生成されたヘルプを表す **ExtendedCmdletHelpInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a21da-294">If you run `Get-Help` on a command that doesn't have a help file, `Get-Help` returns an **ExtendedCmdletHelpInfo** object that represents autogenerated help.</span></span>

### <span data-ttu-id="a21da-295">System.String</span><span class="sxs-lookup"><span data-stu-id="a21da-295">System.String</span></span>

<span data-ttu-id="a21da-296">概念説明のヘルプ記事が表示された場合は、 `Get-Help` それを文字列として返します。</span><span class="sxs-lookup"><span data-stu-id="a21da-296">If you get a conceptual help article, `Get-Help` returns it as a string.</span></span>

### <span data-ttu-id="a21da-297">MamlCommandHelpInfo</span><span class="sxs-lookup"><span data-stu-id="a21da-297">MamlCommandHelpInfo</span></span>

<span data-ttu-id="a21da-298">ヘルプファイルを含むコマンドを取得すると、は `Get-Help` **MamlCommandHelpInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a21da-298">If you get a command that has a help file, `Get-Help` returns a **MamlCommandHelpInfo** object.</span></span>

## <span data-ttu-id="a21da-299">注</span><span class="sxs-lookup"><span data-stu-id="a21da-299">NOTES</span></span>

<span data-ttu-id="a21da-300">PowerShell 3.0 にはヘルプファイルが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="a21da-300">PowerShell 3.0 doesn't include help files.</span></span> <span data-ttu-id="a21da-301">が読み込まれたヘルプファイルをダウンロードしてインストールするには `Get-Help` 、コマンドレットを使用し `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-301">To download and install the help files that `Get-Help` reads, use the `Update-Help` cmdlet.</span></span> <span data-ttu-id="a21da-302">コマンドレットを使用して、 `Update-Help` PowerShell およびインストールするモジュールに付属するコアコマンドのヘルプファイルをダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a21da-302">You can use the `Update-Help` cmdlet to download and install help files for the core commands that come with PowerShell and for any modules that you install.</span></span> <span data-ttu-id="a21da-303">また、このコマンドレットを使用してヘルプ ファイルを更新して、コンピューター上のヘルプを最新に保つこともできます。</span><span class="sxs-lookup"><span data-stu-id="a21da-303">You can also use it to update the help files so that the help on your computer is never outdated.</span></span>

<span data-ttu-id="a21da-304">PowerShell online に付属するコマンドに関するヘルプ記事は、 [Windows powershell を使用](/powershell/scripting/getting-started/getting-started-with-windows-powershell)したはじめにから開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="a21da-304">You can also read the help articles about the commands that come with PowerShell online starting at [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

<span data-ttu-id="a21da-305">`Get-Help` Windows オペレーティングシステムに対して設定されたロケール、またはそのロケールのフォールバック言語でヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-305">`Get-Help` displays help in the locale set for the Windows operating system or in the fallback language for that locale.</span></span> <span data-ttu-id="a21da-306">プライマリまたはフォールバックロケールのヘルプファイルがない場合、は `Get-Help` コンピューターにヘルプファイルがないかのように動作します。</span><span class="sxs-lookup"><span data-stu-id="a21da-306">If you don't have help files for the primary or fallback locale, `Get-Help` behaves as if there are no help files on the computer.</span></span> <span data-ttu-id="a21da-307">別のロケールのヘルプを表示するには、コントロールパネルの [ **地域** と **言語** ] を使用して設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="a21da-307">To get help for a different locale, use **Region** and **Language** in Control Panel to change the settings.</span></span> <span data-ttu-id="a21da-308">Windows 10 の場合、 **設定** 、 **時刻 & 言語** 。</span><span class="sxs-lookup"><span data-stu-id="a21da-308">On Windows 10, **Settings** , **Time & Language**.</span></span>

<span data-ttu-id="a21da-309">ヘルプの完全なビューには、パラメーターに関する情報の表が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a21da-309">The full view of help includes a table of information about the parameters.</span></span> <span data-ttu-id="a21da-310">この表には、次のフィールドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a21da-310">The table includes the following fields:</span></span>

- <span data-ttu-id="a21da-311">**[必須]** 。</span><span class="sxs-lookup"><span data-stu-id="a21da-311">**Required**.</span></span> <span data-ttu-id="a21da-312">パラメーターが必須 (true) であるか省略可能 (false) であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-312">Indicates whether the parameter is required (true) or optional (false).</span></span>

- <span data-ttu-id="a21da-313">**位置** 。</span><span class="sxs-lookup"><span data-stu-id="a21da-313">**Position**.</span></span> <span data-ttu-id="a21da-314">パラメーターの名前が付けられているか、位置 (numeric) であるかを示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-314">Indicates whether the parameter is named or positional (numeric).</span></span> <span data-ttu-id="a21da-315">位置指定パラメーターは、コマンド内の特定の場所に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21da-315">Positional parameters must appear in a specified place in the command.</span></span>

- <span data-ttu-id="a21da-316">**名前付き** では、パラメーター名が必須であることを示しますが、パラメーターはコマンド内の任意の場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-316">**Named** indicates that the parameter name is required, but that the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="a21da-317">**数値** は、パラメーター名が省略可能であることを示します。ただし、名前を省略した場合、パラメーターは数値で指定された場所にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21da-317">**Numeric** indicates that the parameter name is optional, but when the name is omitted, the parameter must be in the place specified by the number.</span></span> <span data-ttu-id="a21da-318">たとえば、は、パラメーター名を省略した場合に、 `2` パラメーターが2番目または名前のないパラメーターである必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-318">For example, `2` indicates that when the parameter name is omitted, the parameter must be the second or only unnamed parameter in the command.</span></span> <span data-ttu-id="a21da-319">パラメーター名を使用する場合は、コマンド内の任意の場所にパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-319">When the parameter name is used, the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="a21da-320">**既定値** 。</span><span class="sxs-lookup"><span data-stu-id="a21da-320">**Default value**.</span></span> <span data-ttu-id="a21da-321">コマンドにパラメーターを含めない場合に PowerShell が使用するパラメーター値または既定の動作。</span><span class="sxs-lookup"><span data-stu-id="a21da-321">The parameter value or default behavior that PowerShell uses if you don't include the parameter in the command.</span></span>

- <span data-ttu-id="a21da-322">パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="a21da-322">Accepts pipeline input.</span></span> <span data-ttu-id="a21da-323">パイプラインを介してオブジェクトをパラメーターに送信できるかどうか (true)、またはできない (false) かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a21da-323">Indicates whether you can (true) or can't (false) send objects to the parameter through a pipeline.</span></span> <span data-ttu-id="a21da-324">**プロパティ名を** 指定すると、パイプラインオブジェクトには、パラメーター名と同じ名前のプロパティが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a21da-324">**By Property Name** means that the pipelined object must have a property that has the same name as the parameter name.</span></span>

- <span data-ttu-id="a21da-325">**ワイルドカード文字を受け入れ** ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-325">**Accepts wildcard characters**.</span></span> <span data-ttu-id="a21da-326">パラメーターの値にアスタリスク ( `*` ) や疑問符 () などのワイルドカード文字を含めることができるかどうかを示し `?` ます。</span><span class="sxs-lookup"><span data-stu-id="a21da-326">Indicates whether the value of a parameter can include wildcard characters, such as an asterisk (`*`) or question mark (`?`).</span></span>

## <span data-ttu-id="a21da-327">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a21da-327">RELATED LINKS</span></span>

[<span data-ttu-id="a21da-328">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="a21da-328">about_Command_Syntax</span></span>](About/about_Command_Syntax.md)

[<span data-ttu-id="a21da-329">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="a21da-329">about_Comment_Based_Help</span></span>](./About/about_Comment_Based_Help.md)

[<span data-ttu-id="a21da-330">Get-Command</span><span class="sxs-lookup"><span data-stu-id="a21da-330">Get-Command</span></span>](Get-Command.md)

[<span data-ttu-id="a21da-331">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="a21da-331">Supporting Updatable Help</span></span>](/powershell/scripting/developer/module/supporting-updatable-help)

[<span data-ttu-id="a21da-332">Update-Help</span><span class="sxs-lookup"><span data-stu-id="a21da-332">Update-Help</span></span>](Update-Help.md)

[<span data-ttu-id="a21da-333">コメントベースのヘルプ トピックを記述する</span><span class="sxs-lookup"><span data-stu-id="a21da-333">Writing Comment-Based Help Topics</span></span>](/powershell/scripting/developer/help/writing-comment-based-help-topics)

[<span data-ttu-id="a21da-334">PowerShell コマンドレットのヘルプの記述</span><span class="sxs-lookup"><span data-stu-id="a21da-334">Writing Help for PowerShell Cmdlets</span></span>](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)

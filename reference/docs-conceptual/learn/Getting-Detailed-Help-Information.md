---
ms.date: 08/27/2018
keywords: PowerShell, コマンドレット
title: 詳しいヘルプ情報の取得
ms.assetid: 6fb4daf7-8607-4a3e-b692-f77631adc1b9
ms.openlocfilehash: e58814f512aa2c5914f92f942cf2a4a76956ee20
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086529"
---
# <a name="getting-detailed-help-information"></a><span data-ttu-id="aa644-103">詳しいヘルプ情報の取得</span><span class="sxs-lookup"><span data-stu-id="aa644-103">Getting detailed help information</span></span>

<span data-ttu-id="aa644-104">PowerShell には、PowerShell の概念と言語について説明した詳しいヘルプ記事があります。</span><span class="sxs-lookup"><span data-stu-id="aa644-104">PowerShell includes detailed Help articles that explain PowerShell concepts and the PowerShell language.</span></span> <span data-ttu-id="aa644-105">また、各コマンドレットおよびプロバイダーに関するヘルプ記事や、多くの関数およびスクリプトに関するヘルプ記事もあります。</span><span class="sxs-lookup"><span data-stu-id="aa644-105">There are also Help articles for each cmdlet and provider and for many functions and scripts.</span></span>

<span data-ttu-id="aa644-106">これらのヘルプ記事はコマンド プロンプトで表示でき、[PowerShell](/powershell/scripting/overview) ドキュメント オンラインでこれらの記事の最新版を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="aa644-106">You can display these Help articles at the command prompt or view the most recently updated versions of these articles in the [PowerShell](/powershell/scripting/overview) documentation online.</span></span>

## <a name="getting-help-for-cmdlets"></a><span data-ttu-id="aa644-107">コマンドレットのヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="aa644-107">Getting help for cmdlets</span></span>

<span data-ttu-id="aa644-108">PowerShell のコマンドレットに関するヘルプを表示するには、[Get-Help](/powershell/module/microsoft.powershell.core/Get-Help) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa644-108">To get Help about PowerShell cmdlets, use the [Get-Help](/powershell/module/microsoft.powershell.core/Get-Help) cmdlet.</span></span> <span data-ttu-id="aa644-109">たとえば、`Get-ChildItem` コマンドレットのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-109">For example, to get Help for the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem
```

<span data-ttu-id="aa644-110">または</span><span class="sxs-lookup"><span data-stu-id="aa644-110">or</span></span>

```powershell
Get-ChildItem -?
```

<span data-ttu-id="aa644-111">Get-Help コマンドレットに関するヘルプも表示できます。</span><span class="sxs-lookup"><span data-stu-id="aa644-111">You can even get Help about the Get-Help cmdlet.</span></span> <span data-ttu-id="aa644-112">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-112">For example:</span></span>

```powershell
Get-Help Get-Help
```

<span data-ttu-id="aa644-113">セッションのすべてのコマンドレットのヘルプ記事の一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-113">To get a list of all the cmdlet Help articles in your session, type:</span></span>

```powershell
Get-Help -Category Cmdlet
```

<span data-ttu-id="aa644-114">各ヘルプ記事を 1 ページずつ表示するには、`help` 関数またはそのエイリアスである `man` を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa644-114">To display one page of each Help article at a time, use the `help` function or its alias `man`.</span></span>
<span data-ttu-id="aa644-115">たとえば、`Get-ChildItem` コマンドレットのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-115">For example, to display Help for the `Get-ChildItem` cmdlet, type</span></span>

```powershell
man Get-ChildItem
```

<span data-ttu-id="aa644-116">または</span><span class="sxs-lookup"><span data-stu-id="aa644-116">or</span></span>

```powershell
help Get-ChildItem
```

<span data-ttu-id="aa644-117">詳細な情報を表示するには、`Get-Help` コマンドレットの **Detailed** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa644-117">To display detailed information, use the **Detailed** parameter of the `Get-Help` cmdlet.</span></span> <span data-ttu-id="aa644-118">たとえば、`Get-ChildItem` コマンドレットに関する詳細情報を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-118">For example, to get detailed information about the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Detailed
```

<span data-ttu-id="aa644-119">ヘルプ記事のすべての内容を表示するには、`Get-Help` コマンドレットの **Full** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa644-119">To display all content in the Help article, use the **Full** parameter of the `Get-Help` cmdlet.</span></span> <span data-ttu-id="aa644-120">たとえば、`Get-ChildItem` コマンドレットのヘルプ記事の内容をすべて表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-120">For example, to display all content in the Help article for the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Full
```

<span data-ttu-id="aa644-121">コマンドレットのパラメーターに関する詳しいヘルプを表示するには、`Get-Help` コマンドレットの **Parameter** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa644-121">To get detailed Help about the parameters of a cmdlet, use the **Parameter** parameter of the `Get-Help` cmdlet.</span></span> <span data-ttu-id="aa644-122">たとえば、`Get-ChildItem` コマンドレットのすべてのパラメーターの詳しいヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-122">For example, to get detailed Help for all of the parameters of the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Parameter *
```

<span data-ttu-id="aa644-123">ヘルプ記事内の例だけを表示するには、`Get-Help` の **Example** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa644-123">To display only the examples in a Help article, use the **Examples** parameter of the `Get-Help`.</span></span>
<span data-ttu-id="aa644-124">たとえば、`Get-ChildItem` コマンドレットのヘルプ記事の例だけを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-124">For example, to display only the examples in the Help article for the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Examples
```

<span data-ttu-id="aa644-125">作成したコマンドレットに関するヘルプ記事を記述する方法については、「[How to Write Cmdlet Help](/powershell/developer/help/writing-help-for-windows-powershell-cmdlets)」(コマンドレット ヘルプの記述方法) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa644-125">For information about how to write Help articles for the cmdlets that you write, see [How to Write Cmdlet Help](/powershell/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

## <a name="getting-conceptual-help"></a><span data-ttu-id="aa644-126">概念説明のヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="aa644-126">Getting conceptual help</span></span>

<span data-ttu-id="aa644-127">`Get-Help` コマンドレットでは、PowerShell 言語に関する記事など、PowerShell の概念説明の記事の情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa644-127">The `Get-Help` cmdlet also displays information about conceptual articles in PowerShell, including articles about the PowerShell language.</span></span> <span data-ttu-id="aa644-128">概念説明のヘルプ記事には、"about_" というプレフィックスが付きます (about_line_editing など)。</span><span class="sxs-lookup"><span data-stu-id="aa644-128">Conceptual Help articles begin with the "about_" prefix, such as about_line_editing.</span></span> <span data-ttu-id="aa644-129">概念説明の記事の名前は、英語バージョン以外の PowerShell でも英語で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa644-129">(The name of the conceptual article must be entered in English even on non-English versions of PowerShell.)</span></span>

<span data-ttu-id="aa644-130">概念説明の記事を一覧表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-130">To display a list of conceptual articles, type:</span></span>

```powershell
Get-Help about_*
```

<span data-ttu-id="aa644-131">特定のヘルプ記事を表示するには、次のように記事の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-131">To display a particular Help article, type the article name, for example:</span></span>

```powershell
Get-Help about_command_syntax
```

<span data-ttu-id="aa644-132">**Detailed**、**Parameter**、**Examples** などの `Get-Help` のパラメーターは、概念説明のヘルプ記事の表示には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="aa644-132">The parameters of `Get-Help`, such as **Detailed**, **Parameter**, and **Examples**, have no effect on the display of conceptual Help articles.</span></span>

## <a name="getting-help-about-providers"></a><span data-ttu-id="aa644-133">プロバイダーに関するヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="aa644-133">Getting help about providers</span></span>

<span data-ttu-id="aa644-134">`Get-Help` コマンドレットでは、PowerShell プロバイダーに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="aa644-134">The `Get-Help` cmdlet displays information about PowerShell providers.</span></span> <span data-ttu-id="aa644-135">プロバイダーのヘルプを取得するには、`Get-Help` に続けてプロバイダー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-135">To get Help for a provider, type `Get-Help` followed by the provider name.</span></span> <span data-ttu-id="aa644-136">たとえば、Registry プロバイダーのヘルプを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-136">For example, to get Help for the Registry provider, type:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="aa644-137">セッションのすべてのプロバイダーのヘルプ記事の一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-137">To get a list of all the provider Help articles in your session, type</span></span>

```powershell
Get-Help -Category provider
```

<span data-ttu-id="aa644-138">**Detailed**、**Parameter**、**Examples** などの `Get-Help` のパラメーターは、プロバイダー ヘルプ記事の表示には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="aa644-138">The parameters of `Get-Help`, such as **Detailed**, **Parameter**, and **Examples**, have no effect on the display of provider Help articles.</span></span>

## <a name="getting-help-about-scripts-and-functions"></a><span data-ttu-id="aa644-139">スクリプトおよび関数に関するヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="aa644-139">Getting help about scripts and functions</span></span>

<span data-ttu-id="aa644-140">PowerShell の多くのスクリプトおよび関数には、ヘルプ記事が用意されています。</span><span class="sxs-lookup"><span data-stu-id="aa644-140">Many scripts and functions in PowerShell have Help articles.</span></span> <span data-ttu-id="aa644-141">`Get-Help` コマンドレットを使用して、スクリプトや関数のヘルプ記事を表示します。</span><span class="sxs-lookup"><span data-stu-id="aa644-141">Use the `Get-Help` cmdlet to display the Help articles for scripts and functions.</span></span>

<span data-ttu-id="aa644-142">関数のヘルプを表示するには、`Get-Help` に続けて関数名を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-142">To display the Help for a function, type `Get-Help` followed by the function name.</span></span> <span data-ttu-id="aa644-143">たとえば、`Disable-PSRemoting` 関数のヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-143">For example, to get Help for the `Disable-PSRemoting` function, type:</span></span>

```powershell
Get-Help Disable-PSRemoting
```

<span data-ttu-id="aa644-144">スクリプトのヘルプを表示するには、スクリプト ファイルへのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-144">To display the Help for a script, type the path to the script file.</span></span> <span data-ttu-id="aa644-145">スクリプトが Path 環境変数に一覧表示されたパスにない場合は、完全修飾パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa644-145">If the script is not in a path listed in the Path environment variable, you must use the fully qualified path.</span></span>

<span data-ttu-id="aa644-146">たとえば、"TestScript.ps1" という名前のスクリプトが C:\\PS-Test ディレクトリに格納されている場合、このスクリプトのヘルプ記事を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-146">For example, if you have a script called "TestScript.ps1" in your C:\\PS-Test directory, to display the Help article for the script, type:</span></span>

```powershell
Get-Help c:\ps-test\TestScript.ps1
```

<span data-ttu-id="aa644-147">コマンドレットのヘルプを表示するように設計されたパラメーターは、スクリプトと関数のヘルプにも有効です。</span><span class="sxs-lookup"><span data-stu-id="aa644-147">The parameters that are designed for displaying cmdlet Help work for script and function Help, too.</span></span> <span data-ttu-id="aa644-148">ただし、`Get-Help *` を実行している場合、スクリプトと関数のヘルプは表示されません。</span><span class="sxs-lookup"><span data-stu-id="aa644-148">However, help for functions and scripts is not shown when you run `Get-Help *`.</span></span>

<span data-ttu-id="aa644-149">関数とスクリプトのヘルプ記事の記述については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa644-149">For information about writing Help articles for your functions and scripts, see the following articles:</span></span>

- [<span data-ttu-id="aa644-150">about_Functions</span><span class="sxs-lookup"><span data-stu-id="aa644-150">about_Functions</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions)
- [<span data-ttu-id="aa644-151">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="aa644-151">about_Scripts</span></span>](/powershell/module/microsoft.powershell.core/about/about_scripts)
- [<span data-ttu-id="aa644-152">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="aa644-152">about_Comment_Based_Help</span></span>](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)

## <a name="getting-help-online"></a><span data-ttu-id="aa644-153">オンラインでのヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="aa644-153">Getting help online</span></span>

<span data-ttu-id="aa644-154">オンラインでのヘルプ記事の表示は、ヘルプを表示するための最善の方法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="aa644-154">Viewing the Help articles online is one of the best ways to get help.</span></span> <span data-ttu-id="aa644-155">オンラインの記事は、より簡単に最新のコンテンツに更新して提供できます。</span><span class="sxs-lookup"><span data-stu-id="aa644-155">Online articles are easier to update and provide the most current content.</span></span>

<span data-ttu-id="aa644-156">オンライン ヘルプを表示するには、`Get-Help` コマンドレットの **Online** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa644-156">To get Help online, use the **Online** parameter of the `Get-Help` cmdlet.</span></span> <span data-ttu-id="aa644-157">プロバイダー ヘルプや概念説明 (About) のヘルプ記事など、PowerShell に付属しているすべてのヘルプ記事は、[PowerShell](/powershell/scripting/powershell-scripting) ドキュメントでオンラインから利用できます。</span><span class="sxs-lookup"><span data-stu-id="aa644-157">All the Help articles that come with PowerShell, including provider Help and conceptual (About) Help articles, are available online in the [PowerShell](/powershell/scripting/powershell-scripting) documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="aa644-158">概念説明の記事 (about_\*) やプロバイダー ヘルプの記事では、**Online** パラメーターを使用できません。</span><span class="sxs-lookup"><span data-stu-id="aa644-158">You can't use the **Online** parameter with conceptual (about_\*) or provider Help articles.</span></span>
> <span data-ttu-id="aa644-159">オンライン ヘルプはオプションであるため、すべてのコマンドレット、関数、またはスクリプトで有効なわけではありません。</span><span class="sxs-lookup"><span data-stu-id="aa644-159">Online help is optional, so it does not work for every cmdlet, function, or script.</span></span>

<span data-ttu-id="aa644-160">たとえば、`Get-ChildItem` コマンドレットのヘルプ記事のオンライン バージョンを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-160">For example, to get the online version of the Help article about the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem -Online
```

<span data-ttu-id="aa644-161">PowerShell では、既定のブラウザーで記事を開きます。</span><span class="sxs-lookup"><span data-stu-id="aa644-161">PowerShell opens the article in your default browser.</span></span> <span data-ttu-id="aa644-162">あるへルプ記事のオンライン ヘルプがサポートされている場合は、そのヘルプ記事の URL を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="aa644-162">If online Help is supported for a Help article, you can also view the URL of the Help article.</span></span> <span data-ttu-id="aa644-163">URL は、ヘルプ記事の「関連リンク」セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa644-163">The URL appears in the Related Links section of a Help article.</span></span>

<span data-ttu-id="aa644-164">たとえば、Add-Computer コマンドレットのオンライン ヘルプ トピックの URL を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa644-164">For example, to see the URL for the online version of the Add-Computer cmdlet, type:</span></span>

```powershell
Get-Help Add-Computer
```

<span data-ttu-id="aa644-165">記事の「関連リンク」セクションの最初の行を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aa644-165">The first line in the Related Links section of the article is shown below.</span></span>

```Output
Online version: http://go.microsoft.com/fwlink/?LinkId=821564
```

<span data-ttu-id="aa644-166">ヘルプ記事のオンライン サポートを提供する方法については、[about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa644-166">For information about how to provide online support for your Help articles, see [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help).</span></span>

## <a name="see-also"></a><span data-ttu-id="aa644-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa644-167">See also</span></span>

- [<span data-ttu-id="aa644-168">about_Functions</span><span class="sxs-lookup"><span data-stu-id="aa644-168">about_Functions</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions)
- [<span data-ttu-id="aa644-169">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="aa644-169">about_Scripts</span></span>](/powershell/module/microsoft.powershell.core/about/about_scripts)
- [<span data-ttu-id="aa644-170">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="aa644-170">about_Comment_Based_Help</span></span>](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)
- [<span data-ttu-id="aa644-171">Get-Help</span><span class="sxs-lookup"><span data-stu-id="aa644-171">Get-Help</span></span>](/powershell/module/microsoft.powershell.core/get-help)

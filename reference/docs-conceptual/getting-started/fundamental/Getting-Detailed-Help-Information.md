---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "詳しいヘルプ情報の取得"
ms.assetid: 6fb4daf7-8607-4a3e-b692-f77631adc1b9
ms.openlocfilehash: c786ce089073abccdf186dc1d9e8ee383f83655d
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
# <a name="getting-detailed-help-information"></a><span data-ttu-id="32fb6-103">詳しいヘルプ情報の取得</span><span class="sxs-lookup"><span data-stu-id="32fb6-103">Getting Detailed Help Information</span></span>
<span data-ttu-id="32fb6-104">Windows PowerShell には、Windows PowerShell の概念と言語について説明した詳しいヘルプ トピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="32fb6-104">Windows PowerShell includes detailed Help topics that explain Windows PowerShell concepts and the Windows PowerShell language.</span></span> <span data-ttu-id="32fb6-105">また、各コマンドレットおよびプロバイダーに関するヘルプ トピックや、多くの関数およびスクリプトに関するヘルプ トピックもあります。</span><span class="sxs-lookup"><span data-stu-id="32fb6-105">There are also Help topics for each cmdlet and provider and Help topics for many functions and scripts.</span></span>

<span data-ttu-id="32fb6-106">これらのヘルプ トピックはコマンド プロンプトで表示でき、Microsoft TechNet ライブラリで最新版のトピックを見ることもできます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-106">You can display these Help topics at the command prompt or view the most recently updated versions of these topics in the Microsoft TechNet Library.</span></span> <span data-ttu-id="32fb6-107">Windows PowerShell Integrated Scripting Environment など、Windows PowerShell をホストする多くのプログラムでは、状況依存のヘルプやコンパイル済みヘルプ ファイル (.chm) などの追加のヘルプ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="32fb6-107">Many programs that host Windows PowerShell, such as Windows PowerShell Integrated Scripting Environment, provide additional Help features, such as context-sensitive Help and compiled Help file (.chm).</span></span>

## <a name="getting-help-for-cmdlets"></a><span data-ttu-id="32fb6-108">コマンドレットのヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="32fb6-108">Getting Help for Cmdlets</span></span>
<span data-ttu-id="32fb6-109">Windows PowerShell のコマンドレットに関するヘルプを表示するには、[Get-Help [m2]](https://technet.microsoft.com/en-us/library/2d7fe1b4-0025-4580-a911-d81922dd6cd2) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-109">To get Help about Windows PowerShell cmdlets, use the [Get-Help [m2]](https://technet.microsoft.com/en-us/library/2d7fe1b4-0025-4580-a911-d81922dd6cd2) cmdlet.</span></span> <span data-ttu-id="32fb6-110">たとえば、[Get-ChildItem [m2]](https://technet.microsoft.com/en-us/library/4b270d63-c995-45b8-b5b4-3f8887efbfcc) コマンドレットのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-110">For example, to get Help for the [Get-ChildItem [m2]](https://technet.microsoft.com/en-us/library/4b270d63-c995-45b8-b5b4-3f8887efbfcc) cmdlet, type:</span></span>

```
get-help get-childitem
```

<span data-ttu-id="32fb6-111">または</span><span class="sxs-lookup"><span data-stu-id="32fb6-111">or</span></span>

```
get-childitem -?
```

<span data-ttu-id="32fb6-112">Get-Help コマンドレットに関するヘルプも表示できます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-112">You can even get Help about the Get-Help cmdlet.</span></span> <span data-ttu-id="32fb6-113">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-113">For example:</span></span>

```
get-help get-help
```

<span data-ttu-id="32fb6-114">セッションのすべてのコマンドレットのヘルプ トピックの一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-114">To get a list of all the cmdlet Help topics in your session, type:</span></span>

```
get-help -category cmdlet
```

<span data-ttu-id="32fb6-115">各ヘルプ トピックを 1 ページずつ表示するには、**help** 関数、またはそのエイリアスである **man** を使用します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-115">To display one page of each Help topic at a time, use the **help** function or its alias **man**.</span></span> <span data-ttu-id="32fb6-116">たとえば、Get-ChildItem コマンドレットのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-116">For example, to display Help for the Get-ChildItem cmdlet, type</span></span>

```
man get-childitem
```

<span data-ttu-id="32fb6-117">または</span><span class="sxs-lookup"><span data-stu-id="32fb6-117">or</span></span>

```
help get-childitem
```

<span data-ttu-id="32fb6-118">パラメーターの説明や使用例など、コマンドレット、関数、またはスクリプトに関する詳細情報を表示するには、Get-Help コマンドレットの *Detailed* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-118">To display detailed information about a cmdlet, function, or script, including descriptions of its parameters and examples of its use, use the *Detailed* parameter of the Get-Help cmdlet.</span></span> <span data-ttu-id="32fb6-119">たとえば、Get-ChildItem コマンドレットに関する詳細情報を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-119">For example, to get detailed information about the Get-ChildItem cmdlet, type:</span></span>

```
get-help get-childitem -detailed
```

<span data-ttu-id="32fb6-120">ヘルプ トピックのすべての内容を表示するには、Get-Help コマンドレットの *Full* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-120">To display all content in the Help topic, use the *Full* parameter of the Get-Help cmdlet.</span></span> <span data-ttu-id="32fb6-121">たとえば、Get-ChildItem コマンドレットのヘルプ トピックの内容をすべて表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-121">For example, to display all content in the Help topic for the Get-ChildItem cmdlet, type:</span></span>

```
get-help get-childitem -full
```

<span data-ttu-id="32fb6-122">コマンドレットのパラメーターに関する詳しいヘルプを表示するには、Get-Help コマンドレットの *Parameter* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-122">To get detailed Help about the parameters of a cmdlet, use the *Parameter* parameter of the Get-Help cmdlet.</span></span> <span data-ttu-id="32fb6-123">たとえば、Get-ChildItem コマンドレットのすべてのパラメーターの詳しいヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-123">For example, to get detailed Help for all of the parameters of the Get-ChildItem cmdlet, type:</span></span>

```
get-help get-childitem -parameter *
```

<span data-ttu-id="32fb6-124">ヘルプ トピック内の例だけを表示するには、Get-Help の *Example* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-124">To display only the examples in a Help topic, use the *Example* parameter of the Get-Help.</span></span> <span data-ttu-id="32fb6-125">たとえば、Get-ChildItem コマンドレットのヘルプ トピック内の例のみを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-125">For example, to display only the examples in the Help topic for the Get-ChildItem cmdlet, type:</span></span>

```
get-help get-childitem -examples
```

<span data-ttu-id="32fb6-126">作成したコマンドレットに関するヘルプ トピックを記述する方法については、MSDN ライブラリの「[How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415)」 (コマンドレット ヘルプの記述方法) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32fb6-126">For information about how to write Help topics for the cmdlets that you write, see [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415) in the MSDN library.</span></span>

## <a name="getting-conceptual-help"></a><span data-ttu-id="32fb6-127">概念説明のヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="32fb6-127">Getting Conceptual Help</span></span>
<span data-ttu-id="32fb6-128">Get-Help コマンドレットでは、Windows PowerShell 言語に関するトピックなど、Windows PowerShell の概念説明トピックの情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-128">The Get-Help cmdlet also displays information about conceptual topics in Windows PowerShell, including topics about the Windows PowerShell language.</span></span> <span data-ttu-id="32fb6-129">概念説明のヘルプ トピックには、"about_" というプレフィックスが付きます (about_line_editing など)。</span><span class="sxs-lookup"><span data-stu-id="32fb6-129">Conceptual Help topics begin with the "about_" prefix, such as about_line_editing.</span></span> <span data-ttu-id="32fb6-130">概念説明のトピックの名前は、英語バージョン以外の Windows PowerShell でも英語で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32fb6-130">(The name of the conceptual topic must be entered in English even on non-English versions of Windows PowerShell.)</span></span>

<span data-ttu-id="32fb6-131">概念説明のトピックを一覧表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-131">To display a list of conceptual topics, type:</span></span>

```
get-help about_*
```

<span data-ttu-id="32fb6-132">特定のヘルプ トピックを表示するには、次のように、トピック名を入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-132">To display a particular Help topic, type the topic name, for example:</span></span>

```
get-help about_command_syntax
```

<span data-ttu-id="32fb6-133">Get-Help の *Detailed*、*Parameter*、*Examples* などのパラメーターは、概念説明ヘルプ トピックの表示には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="32fb6-133">The parameters of Get-Help, such as *Detailed*, *Parameter*, and *Examples*, have no effect on the display of conceptual Help topics.</span></span>

## <a name="getting-help-about-providers"></a><span data-ttu-id="32fb6-134">プロバイダーに関するヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="32fb6-134">Getting Help About Providers</span></span>
<span data-ttu-id="32fb6-135">Get-Help コマンドレットでは、Windows PowerShell プロバイダーに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-135">The Get-Help cmdlet displays information about Windows PowerShell providers.</span></span> <span data-ttu-id="32fb6-136">プロバイダーのヘルプを取得するには、"Get-Help" に続けてプロバイダー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-136">To get Help for a provider, type "Get-Help" followed by the provider name.</span></span> <span data-ttu-id="32fb6-137">たとえば、Registry プロバイダーのヘルプを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-137">For example, to get Help for the Registry provider, type:</span></span>

```
get-help registry
```

<span data-ttu-id="32fb6-138">セッションのすべてのプロバイダーのヘルプ トピックの一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-138">To get a list of all the provider Help topics in your session, type</span></span>

```
get-help -category provider
```

<span data-ttu-id="32fb6-139">Get-Help の *Detailed*、*Parameter*、*Examples* などのパラメーターは、プロバイダーに関するヘルプ トピックの表示には効果がありません。</span><span class="sxs-lookup"><span data-stu-id="32fb6-139">The parameters of Get-Help, such as *Detailed*, *Parameter*, and *Examples*, have no effect on the display of provider Help topics.</span></span>

## <a name="getting-help-about-scripts-and-functions"></a><span data-ttu-id="32fb6-140">スクリプトおよび関数に関するヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="32fb6-140">Getting Help About Scripts and Functions</span></span>
<span data-ttu-id="32fb6-141">Windows PowerShell の多くのスクリプトおよび関数には、ヘルプ トピックが用意されています。</span><span class="sxs-lookup"><span data-stu-id="32fb6-141">Many scripts and functions in Windows PowerShell have Help topics.</span></span> <span data-ttu-id="32fb6-142">Get-Help コマンドレットを使用して、スクリプトや関数のヘルプ トピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-142">Use the Get-Help cmdlet to display the Help topics for scripts and functions.</span></span>

<span data-ttu-id="32fb6-143">関数のヘルプを表示するには、"get-help" に続けて関数名を入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-143">To display the Help for a function, type "get-help" followed by the function name.</span></span> <span data-ttu-id="32fb6-144">たとえば、Disable-PSRemoting 関数のヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-144">For example, to get Help for the Disable-PSRemoting function, type:</span></span>

```
get-help disable-psremoting
```

<span data-ttu-id="32fb6-145">スクリプトのヘルプを表示するには、スクリプト ファイルへの完全修飾パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-145">To display the Help for a script, type the fully qualified path to the script file.</span></span> <span data-ttu-id="32fb6-146">スクリプトのパスが Path 環境変数に含まれている場合は、コマンドからパスを省略できます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-146">If the script is in a path that is listed in the Path environment variable, you can omit the path from the command.</span></span>

<span data-ttu-id="32fb6-147">たとえば、"TestScript.ps1" という名前のスクリプトが C:\\PS-Test ディレクトリに格納されている場合、このスクリプトのヘルプ トピックを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-147">For example, if you have a script called "TestScript.ps1" in your C:\\PS-Test directory, to display the Help topic for the script, type:</span></span>

```
get-help c:\ps-test\TestScript.ps1
```

<span data-ttu-id="32fb6-148">*Detailed*、*Full*、*Examples*、*Parameter* など、コマンドレットのヘルプを表示するためにデザインされているパラメーターは、スクリプトのヘルプや関数のヘルプにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-148">The parameters that were designed for displaying cmdlet Help, such as *Detailed*, *Full*, *Examples*, and *Parameter*, work for script Help and function Help, too.</span></span> <span data-ttu-id="32fb6-149">ただし、"get-help \*" を入力してすべてのヘルプを表示した場合、関数およびスクリプトのヘルプは表示されません。</span><span class="sxs-lookup"><span data-stu-id="32fb6-149">However, when you display all Help, by typing "get-help \*", Help for functions and scripts does not appear.</span></span>

<span data-ttu-id="32fb6-150">関数およびスクリプトに関するヘルプ トピックを記述する方法については、「[about_Functions [m2]](https://technet.microsoft.com/en-us/library/61d40692-5300-4de9-a9b5-bae31815e105)」、「[about_Scripts](https://technet.microsoft.com/en-us/library/7dc08334-dcfe-450b-b949-0554855623af)」、「[about_Comment_Based_Help](https://technet.microsoft.com/en-us/library/99a81ccc-21a0-49ec-a1b3-9efe2b4c0bbf)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32fb6-150">For information about writing Help topics for your functions and scripts, see [about_Functions [m2]](https://technet.microsoft.com/en-us/library/61d40692-5300-4de9-a9b5-bae31815e105), [about_Scripts](https://technet.microsoft.com/en-us/library/7dc08334-dcfe-450b-b949-0554855623af), and [about_Comment_Based_Help](https://technet.microsoft.com/en-us/library/99a81ccc-21a0-49ec-a1b3-9efe2b4c0bbf).</span></span>

## <a name="getting-help-online"></a><span data-ttu-id="32fb6-151">オンライン ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="32fb6-151">Getting Help Online</span></span>
<span data-ttu-id="32fb6-152">インターネットに接続している場合、ヘルプを見るための最も良い方法の 1 つは、ヘルプ トピックをオンラインで表示することです。</span><span class="sxs-lookup"><span data-stu-id="32fb6-152">If you are connected to the Internet, one of the best ways to get Help is to view the Help topics online.</span></span> <span data-ttu-id="32fb6-153">オンライン トピックは簡単に更新できるため、最新の情報が得られる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="32fb6-153">Because online topics are easy to update, they are likely to provide the most current content.</span></span>

<span data-ttu-id="32fb6-154">オンライン ヘルプを表示するには、Get-Help コマンドレットの *Online* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-154">To get Help online, try the *Online* parameter of the Get-Help cmdlet.</span></span> <span data-ttu-id="32fb6-155">Get-Help コマンドレットの *Online* パラメーターは、コマンドレットのヘルプ、関数のヘルプ、スクリプトのヘルプに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-155">The *Online* parameter of the Get-Help cmdlet works only for cmdlet Help, function Help, and script Help.</span></span> <span data-ttu-id="32fb6-156">概念説明のトピック ("about" ヘルプ) やプロバイダーに関するヘルプ トピックに対しては、*Online* パラメーターを使用できません。</span><span class="sxs-lookup"><span data-stu-id="32fb6-156">You cannot use the *Online* parameter with conceptual (About) topics or provider Help topics.</span></span> <span data-ttu-id="32fb6-157">また、この機能はオプションであるため、すべてのコマンドレット、関数、スクリプトのヘルプ トピックに有効なわけではありません。</span><span class="sxs-lookup"><span data-stu-id="32fb6-157">Also, because this feature is optional, it does not work for every cmdlet, function, or script Help topic.</span></span>

<span data-ttu-id="32fb6-158">ただし、プロバイダーのヘルプ トピックや概念説明 ("about" ヘルプ) トピックも含め、Windows PowerShell に付属するすべてのヘルプ トピックが、Microsoft TechNet ライブラリの [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkID=107116) セクションからオンラインで参照できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="32fb6-158">However, all the Help topics that come with Windows PowerShell, including provider Help and conceptual (About) Help topics, are available online in the [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkID=107116) section of the Microsoft TechNet Library.</span></span>

<span data-ttu-id="32fb6-159">Get-Help コマンドレットの *Online* パラメーターを使用するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-159">To use the *Online* parameter of the Get-Help cmdlet, use the following command format.</span></span>

```
get-help <command-name> -online
```

<span data-ttu-id="32fb6-160">たとえば、Get-ChildItem コマンドレットのヘルプ トピックのオンライン バージョンを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-160">For example, to get the online version of the Help topic about the Get-ChildItem cmdlet, type:</span></span>

```
get-help get-childitem -online
```

<span data-ttu-id="32fb6-161">ヘルプ トピックのオンライン バージョンが存在する場合には、既定のブラウザーにそのトピックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-161">If an online version of the Help topic is available, it will open in your default browser.</span></span>

<span data-ttu-id="32fb6-162">あるへルプ トピックに対してオンライン ヘルプがサポートされている場合、そのヘルプ トピックのインターネット アドレス (URL) を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-162">If online Help is supported for a Help topic, you can also view the Internet address (URL) of the Help topic.</span></span> <span data-ttu-id="32fb6-163">インターネット アドレスは、ヘルプ トピックの「関連リンク」セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="32fb6-163">The Internet address appears in the Related Links section of a Help topic.</span></span>

<span data-ttu-id="32fb6-164">たとえば、Add-Computer コマンドレットのオンライン ヘルプ トピックの URL を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-164">For example, to see the URL for the online version of the Add-Computer cmdlet, type:</span></span>

```
get-help add-computer
```

<span data-ttu-id="32fb6-165">トピックの「関連リンク」セクションの最初の行を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32fb6-165">The first line in the Related Links section of the topic is shown below.</span></span>

```
Online version: http://go.microsoft.com/fwlink/?LinkID=135194
```

<span data-ttu-id="32fb6-166">ヘルプ トピックのオンライン サポートを提供する方法については、「[about_Comment_Based_Help](https://technet.microsoft.com/en-us/library/99a81ccc-21a0-49ec-a1b3-9efe2b4c0bbf)」と MSDN ライブラリの [「How to Write Cmdlet Help」](https://go.microsoft.com/fwlink/?LinkID=123415) (コマンドレット ヘルプの記述方法) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32fb6-166">For information about how to provide online support for your Help topics, see [about_Comment_Based_Help](https://technet.microsoft.com/en-us/library/99a81ccc-21a0-49ec-a1b3-9efe2b4c0bbf), and see [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415) in the MSDN library.</span></span>

## <a name="see-also"></a><span data-ttu-id="32fb6-167">参照</span><span class="sxs-lookup"><span data-stu-id="32fb6-167">See Also</span></span>
- <span data-ttu-id="32fb6-168">[about_Functions [m2]](https://technet.microsoft.com/en-us/library/61d40692-5300-4de9-a9b5-bae31815e105)</span><span class="sxs-lookup"><span data-stu-id="32fb6-168">[about_Functions [m2]](https://technet.microsoft.com/en-us/library/61d40692-5300-4de9-a9b5-bae31815e105)</span></span>
- [<span data-ttu-id="32fb6-169">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="32fb6-169">about_Scripts</span></span>](https://technet.microsoft.com/en-us/library/7dc08334-dcfe-450b-b949-0554855623af)
- [<span data-ttu-id="32fb6-170">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="32fb6-170">about_Comment_Based_Help</span></span>](https://technet.microsoft.com/en-us/library/99a81ccc-21a0-49ec-a1b3-9efe2b4c0bbf)
- <span data-ttu-id="32fb6-171">[Get-Help [m2]](https://technet.microsoft.com/en-us/library/2d7fe1b4-0025-4580-a911-d81922dd6cd2)</span><span class="sxs-lookup"><span data-stu-id="32fb6-171">[Get-Help [m2]](https://technet.microsoft.com/en-us/library/2d7fe1b4-0025-4580-a911-d81922dd6cd2)</span></span>


---
description: 関数とスクリプトのコメントベースのヘルプトピックを記述する方法について説明します。
keywords: powershell,コマンドレット
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comment_based_help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comment_Based_Help
ms.openlocfilehash: cb7ac6e7b4ec3afb95c9864665490633fdad6c5c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223128"
---
# <a name="about-comment-based-help"></a><span data-ttu-id="85de2-104">コメントベースのヘルプについて</span><span class="sxs-lookup"><span data-stu-id="85de2-104">About Comment-based Help</span></span>

## <a name="short-description"></a><span data-ttu-id="85de2-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="85de2-105">Short description</span></span>
<span data-ttu-id="85de2-106">関数とスクリプトのコメントベースのヘルプトピックを記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85de2-106">Describes how to write comment-based help topics for functions and scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="85de2-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="85de2-107">Long description</span></span>

<span data-ttu-id="85de2-108">特別なヘルプコメントキーワードを使用して、関数およびスクリプトのコメントベースのヘルプトピックを記述できます。</span><span class="sxs-lookup"><span data-stu-id="85de2-108">You can write comment-based help topics for functions and scripts by using special help comment keywords.</span></span>

<span data-ttu-id="85de2-109">[Get-help](xref:Microsoft.PowerShell.Core.Get-Help)コマンドレットは、XML ファイルから生成されたコマンドレットヘルプトピックを表示するのと同じ形式で、コメントベースのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="85de2-109">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) cmdlet displays comment-based help in the same format in which it displays the cmdlet help topics that are generated from XML files.</span></span> <span data-ttu-id="85de2-110">ユーザーは、 `Get-Help` **詳細** 、 **完全** 、 **例** 、 **オンライン** など、のすべてのパラメーターを使用して、コメントベースのヘルプの内容を表示できます。</span><span class="sxs-lookup"><span data-stu-id="85de2-110">Users can use all of the parameters of `Get-Help`, such as **Detailed** , **Full** , **Examples** , and **Online** , to display the contents of comment-based help.</span></span>

<span data-ttu-id="85de2-111">関数とスクリプトの XML ベースのヘルプファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="85de2-111">You can also write XML-based help files for functions and scripts.</span></span> <span data-ttu-id="85de2-112">`Get-Help`コマンドレットで関数またはスクリプトの XML ベースのヘルプファイルを検索できるようにするには、キーワードを使用し `.ExternalHelp` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-112">To enable the `Get-Help` cmdlet to find the XML-based help file for a function or script, use the `.ExternalHelp` keyword.</span></span> <span data-ttu-id="85de2-113">このキーワードがない場合、で `Get-Help` は、関数またはスクリプトの XML ベースのヘルプトピックを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="85de2-113">Without this keyword, `Get-Help` cannot find XML-based help topics for functions or scripts.</span></span>

<span data-ttu-id="85de2-114">このトピックでは、関数とスクリプトのヘルプトピックを記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85de2-114">This topic explains how to write help topics for functions and scripts.</span></span> <span data-ttu-id="85de2-115">関数とスクリプトのヘルプトピックを表示する方法の詳細については、「 [get-help](xref:Microsoft.PowerShell.Core.Get-Help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85de2-115">For information about how to display help topics for functions and scripts, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).</span></span>

<span data-ttu-id="85de2-116">[Update-help](xref:Microsoft.PowerShell.Core.Update-Help)および update-help コマンドレットは、XML ファイルでのみ[機能します](xref:Microsoft.PowerShell.Core.Save-Help)。</span><span class="sxs-lookup"><span data-stu-id="85de2-116">The [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) and [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) cmdlets work only on XML files.</span></span> <span data-ttu-id="85de2-117">更新可能なヘルプでは、コメントベースのヘルプトピックはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="85de2-117">Updatable Help does not support comment-based help topics.</span></span>

## <a name="syntax-for-comment-based-help"></a><span data-ttu-id="85de2-118">コメントベースのヘルプの構文</span><span class="sxs-lookup"><span data-stu-id="85de2-118">Syntax for comment-based help</span></span>

<span data-ttu-id="85de2-119">コメントベースのヘルプの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85de2-119">The syntax for comment-based help is as follows:</span></span>

```
# .<help keyword>
# <help content>
```

<span data-ttu-id="85de2-120">or</span><span class="sxs-lookup"><span data-stu-id="85de2-120">or</span></span>

```
<#
.<help keyword>
<help content>
#>
```

<span data-ttu-id="85de2-121">コメントベースのヘルプは、一連のコメントとして書かれています。</span><span class="sxs-lookup"><span data-stu-id="85de2-121">Comment-based help is written as a series of comments.</span></span> <span data-ttu-id="85de2-122">コメントの各行の前にコメント記号を入力する `#` か、および記号を使用し `<#` て `#>` コメントブロックを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="85de2-122">You can type a comment symbol `#` before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="85de2-123">コメントブロック内のすべての行は、コメントとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-123">All the lines within the comment block are interpreted as comments.</span></span>

<span data-ttu-id="85de2-124">コメントベースのヘルプトピック内のすべての行は、連続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="85de2-124">All of the lines in a comment-based help topic must be contiguous.</span></span> <span data-ttu-id="85de2-125">コメントベースのヘルプトピックがヘルプトピックに含まれていないコメントの後に続く場合は、ヘルプ以外の最後のコメント行とコメントベースのヘルプの先頭の間に、少なくとも1つの空白行がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="85de2-125">If a comment-based help topic follows a comment that is not part of the help topic, there must be at least one blank line between the last non-help comment line and the beginning of the comment-based help.</span></span>

<span data-ttu-id="85de2-126">キーワードは、コメントベースのヘルプの各セクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="85de2-126">Keywords define each section of comment-based help.</span></span> <span data-ttu-id="85de2-127">各コメントベースのヘルプキーワードの前には、ドットが付き `.` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-127">Each comment-based help keyword is preceded by a dot `.`.</span></span> <span data-ttu-id="85de2-128">キーワードは任意の順序で表示できます。</span><span class="sxs-lookup"><span data-stu-id="85de2-128">The keywords can appear in any order.</span></span> <span data-ttu-id="85de2-129">キーワード名の大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="85de2-129">The keyword names are not case-sensitive.</span></span>

<span data-ttu-id="85de2-130">たとえば、キーワードは、 `.Description` 関数またはスクリプトの説明の前にあります。</span><span class="sxs-lookup"><span data-stu-id="85de2-130">For example, the `.Description` keyword precedes a description of a function or script.</span></span>

```
<#
.Description
Get-Function displays the name and syntax of all functions in the session.
#>
```

<span data-ttu-id="85de2-131">コメントブロックには少なくとも1つのキーワードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="85de2-131">The comment block must contain at least one keyword.</span></span> <span data-ttu-id="85de2-132">などのキーワードの中には、 `.EXAMPLE` 同じコメントブロックに何度も出現するものがあります。</span><span class="sxs-lookup"><span data-stu-id="85de2-132">Some of the keywords, such as `.EXAMPLE`, can appear many times in the same comment block.</span></span> <span data-ttu-id="85de2-133">各キーワードのヘルプコンテンツは、キーワードの後の行から開始され、複数の行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="85de2-133">The help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

## <a name="syntax-for-comment-based-help-in-functions"></a><span data-ttu-id="85de2-134">関数のコメントベースのヘルプの構文</span><span class="sxs-lookup"><span data-stu-id="85de2-134">Syntax for comment-based help in functions</span></span>

<span data-ttu-id="85de2-135">関数のコメントベースのヘルプは、次の3つの場所のいずれかに表示されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-135">Comment-based help for a function can appear in one of three locations:</span></span>

- <span data-ttu-id="85de2-136">関数本体の先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="85de2-136">At the beginning of the function body.</span></span>
- <span data-ttu-id="85de2-137">関数本体の末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="85de2-137">At the end of the function body.</span></span>
- <span data-ttu-id="85de2-138">キーワードの前 `function` 。</span><span class="sxs-lookup"><span data-stu-id="85de2-138">Before the `function` keyword.</span></span> <span data-ttu-id="85de2-139">関数のヘルプとキーワードの最後の行の間に、複数の空白行を指定することはできません `function` 。</span><span class="sxs-lookup"><span data-stu-id="85de2-139">There cannot be more than one blank line between the last line of the function help and the `function` keyword.</span></span>

<span data-ttu-id="85de2-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="85de2-140">For example:</span></span>

```powershell
function Get-Function
{
<#
.<help keyword>
<help content>
#>

  # function logic
}
```

<span data-ttu-id="85de2-141">or</span><span class="sxs-lookup"><span data-stu-id="85de2-141">or</span></span>

```powershell
function Get-Function
{
   # function logic

<#
.<help keyword>
<help content>
#>
}
```

<span data-ttu-id="85de2-142">or</span><span class="sxs-lookup"><span data-stu-id="85de2-142">or</span></span>

```powershell
<#
.<help keyword>
<help content>
#>
function Get-Function { }
```

## <a name="syntax-for-comment-based-help-in-scripts"></a><span data-ttu-id="85de2-143">スクリプトのコメントベースのヘルプの構文</span><span class="sxs-lookup"><span data-stu-id="85de2-143">Syntax for comment-based help in scripts</span></span>

<span data-ttu-id="85de2-144">スクリプトのコメントベースのヘルプは、スクリプト内の次の2つの場所のいずれかに表示されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-144">Comment-based help for a script can appear in one of the following two locations in the script.</span></span>

- <span data-ttu-id="85de2-145">スクリプトファイルの先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="85de2-145">At the beginning of the script file.</span></span> <span data-ttu-id="85de2-146">スクリプトのヘルプは、コメントと空白行によってのみスクリプトの先頭に配置できます。</span><span class="sxs-lookup"><span data-stu-id="85de2-146">Script help can be preceded in the script only by comments and blank lines.</span></span>

  <span data-ttu-id="85de2-147">スクリプト本体の最初の項目 (ヘルプの後) が関数宣言の場合、スクリプトヘルプの末尾と関数宣言の間には、少なくとも2つの空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="85de2-147">If the first item in the script body (after the help) is a function declaration, there must be at least two blank lines between the end of the script help and the function declaration.</span></span> <span data-ttu-id="85de2-148">それ以外の場合、ヘルプは、スクリプトのヘルプではなく、関数のヘルプとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-148">Otherwise, the help is interpreted as being help for the function, not help for the script.</span></span>

- <span data-ttu-id="85de2-149">スクリプトファイルの末尾にあります。</span><span class="sxs-lookup"><span data-stu-id="85de2-149">At the end of the script file.</span></span> <span data-ttu-id="85de2-150">ただし、スクリプトが署名されている場合は、スクリプトファイルの先頭にコメントベースのヘルプを配置します。</span><span class="sxs-lookup"><span data-stu-id="85de2-150">However, if the script is signed, place Comment-based help at the beginning of the script file.</span></span> <span data-ttu-id="85de2-151">スクリプトの末尾は、signature ブロックによって占有されています。</span><span class="sxs-lookup"><span data-stu-id="85de2-151">The end of the script is occupied by the signature block.</span></span>

<span data-ttu-id="85de2-152">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="85de2-152">For example:</span></span>

```powershell
<#
.<help keyword>
<help content>
#>


function Get-Function { }
```

<span data-ttu-id="85de2-153">or</span><span class="sxs-lookup"><span data-stu-id="85de2-153">or</span></span>

```powershell
function Get-Function { }

<#
.<help keyword>
<help content>
#>
```

## <a name="syntax-for-comment-based-help-in-script-modules"></a><span data-ttu-id="85de2-154">スクリプトモジュールのコメントベースのヘルプの構文</span><span class="sxs-lookup"><span data-stu-id="85de2-154">Syntax for comment-based help in script modules</span></span>

<span data-ttu-id="85de2-155">スクリプトモジュールでは、 `.psm1` コメントベースのヘルプは、スクリプトの構文ではなく、関数の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="85de2-155">In a script module `.psm1`, comment-based help uses the syntax for functions, not the syntax for scripts.</span></span> <span data-ttu-id="85de2-156">スクリプトの構文を使用して、スクリプトモジュールで定義されているすべての関数のヘルプを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="85de2-156">You cannot use the script syntax to provide help for all functions defined in a script module.</span></span>

<span data-ttu-id="85de2-157">たとえば、キーワードを使用して、 `.ExternalHelp` スクリプトモジュール内の関数の XML ベースのヘルプファイルを識別する場合は、各関数にコメントを追加する必要があり `.ExternalHelp` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-157">For example, if you are using the `.ExternalHelp` keyword to identify the XML-based help files for the functions in a script module, you must add an `.ExternalHelp` comment to each function.</span></span>

```powershell
# .ExternalHelp <XML-file-name>
function <function-name>
{
  ...
}
```

## <a name="comment-based-help-keywords"></a><span data-ttu-id="85de2-158">コメントベースのヘルプキーワード</span><span class="sxs-lookup"><span data-stu-id="85de2-158">Comment-based help keywords</span></span>

<span data-ttu-id="85de2-159">有効なコメントベースのヘルプキーワードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="85de2-159">The following are valid comment-based help keywords.</span></span> <span data-ttu-id="85de2-160">これらの一覧は、通常、ヘルプトピックに表示される順序で、使用目的と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-160">They are listed in the order in which they typically appear in a help topic along with their intended use.</span></span> <span data-ttu-id="85de2-161">これらのキーワードは、コメントベースのヘルプ内で任意の順序で表示でき、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="85de2-161">These keywords can appear in any order in the comment-based help, and they are not case-sensitive.</span></span>

### <a name="synopsis"></a><span data-ttu-id="85de2-162">.概要</span><span class="sxs-lookup"><span data-stu-id="85de2-162">.SYNOPSIS</span></span>

<span data-ttu-id="85de2-163">関数またはスクリプトの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="85de2-163">A brief description of the function or script.</span></span> <span data-ttu-id="85de2-164">このキーワードは、各トピックで1回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="85de2-164">This keyword can be used only once in each topic.</span></span>

### <a name="description"></a><span data-ttu-id="85de2-165">.記述</span><span class="sxs-lookup"><span data-stu-id="85de2-165">.DESCRIPTION</span></span>

<span data-ttu-id="85de2-166">関数またはスクリプトの詳細な説明。</span><span class="sxs-lookup"><span data-stu-id="85de2-166">A detailed description of the function or script.</span></span> <span data-ttu-id="85de2-167">このキーワードは、各トピックで1回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="85de2-167">This keyword can be used only once in each topic.</span></span>

### <a name="parameter"></a><span data-ttu-id="85de2-168">.引き</span><span class="sxs-lookup"><span data-stu-id="85de2-168">.PARAMETER</span></span>

<span data-ttu-id="85de2-169">パラメーターの説明。</span><span class="sxs-lookup"><span data-stu-id="85de2-169">The description of a parameter.</span></span> <span data-ttu-id="85de2-170">`.PARAMETER`関数またはスクリプトの構文で、各パラメーターにキーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85de2-170">Add a `.PARAMETER` keyword for each parameter in the function or script syntax.</span></span>

<span data-ttu-id="85de2-171">キーワードと同じ行にパラメーター名を入力し `.PARAMETER` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-171">Type the parameter name on the same line as the `.PARAMETER` keyword.</span></span> <span data-ttu-id="85de2-172">キーワードの後の行にパラメーターの説明を入力し `.PARAMETER` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-172">Type the parameter description on the lines following the `.PARAMETER` keyword.</span></span> <span data-ttu-id="85de2-173">Windows PowerShell `.PARAMETER` は、パラメーターの説明の一部として、行と次のキーワード、またはコメントブロックの末尾の間のすべてのテキストを解釈します。</span><span class="sxs-lookup"><span data-stu-id="85de2-173">Windows PowerShell interprets all text between the `.PARAMETER` line and the next keyword or the end of the comment block as part of the parameter description.</span></span>
<span data-ttu-id="85de2-174">説明には、段落区切りを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="85de2-174">The description can include paragraph breaks.</span></span>

```
.PARAMETER  <Parameter-Name>
```

<span data-ttu-id="85de2-175">パラメーターキーワードは、コメントブロック内の任意の順序で指定できますが、関数またはスクリプトの構文によって、パラメーター (およびその説明) がヘルプトピックに表示される順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-175">The Parameter keywords can appear in any order in the comment block, but the function or script syntax determines the order in which the parameters (and their descriptions) appear in help topic.</span></span> <span data-ttu-id="85de2-176">順序を変更するには、構文を変更します。</span><span class="sxs-lookup"><span data-stu-id="85de2-176">To change the order, change the syntax.</span></span>

<span data-ttu-id="85de2-177">関数またはスクリプト構文のパラメーター変数名の直前にコメントを配置することで、パラメーターの説明を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="85de2-177">You can also specify a parameter description by placing a comment in the function or script syntax immediately before the parameter variable name.</span></span> <span data-ttu-id="85de2-178">これを機能させるには、少なくとも1つのキーワードを含むコメントブロックが必要です。</span><span class="sxs-lookup"><span data-stu-id="85de2-178">For this to work, you must also have a comment block with at least one keyword.</span></span>

<span data-ttu-id="85de2-179">構文コメントとキーワードの両方を使用する場合 `.PARAMETER` は、キーワードに関連付けられている説明 `.PARAMETER` が使用され、構文のコメントは無視されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-179">If you use both a syntax comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the syntax comment is ignored.</span></span>

```powershell
<#
.SYNOPSIS
    Short description here
#>
function Verb-Noun {
    [CmdletBinding()]
    param (
        # This is the same as .Parameter
        [string]$Computername
    )
    # Verb the Noun on the computer
}
```

### <a name="example"></a><span data-ttu-id="85de2-180">.よう</span><span class="sxs-lookup"><span data-stu-id="85de2-180">.EXAMPLE</span></span>

<span data-ttu-id="85de2-181">関数またはスクリプトを使用するサンプルコマンド。必要に応じて、サンプル出力と説明が続きます。</span><span class="sxs-lookup"><span data-stu-id="85de2-181">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="85de2-182">各例について、このキーワードを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="85de2-182">Repeat this keyword for each example.</span></span>

### <a name="inputs"></a><span data-ttu-id="85de2-183">.INPUTACCEL</span><span class="sxs-lookup"><span data-stu-id="85de2-183">.INPUTS</span></span>

<span data-ttu-id="85de2-184">関数またはスクリプトにパイプすることができるオブジェクトの .NET 型。</span><span class="sxs-lookup"><span data-stu-id="85de2-184">The .NET types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="85de2-185">入力オブジェクトの説明を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="85de2-185">You can also include a description of the input objects.</span></span>

### <a name="outputs"></a><span data-ttu-id="85de2-186">.出力</span><span class="sxs-lookup"><span data-stu-id="85de2-186">.OUTPUTS</span></span>

<span data-ttu-id="85de2-187">コマンドレットが返すオブジェクトの .NET 型。</span><span class="sxs-lookup"><span data-stu-id="85de2-187">The .NET type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="85de2-188">返されたオブジェクトの説明を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="85de2-188">You can also include a description of the returned objects.</span></span>

### <a name="notes"></a><span data-ttu-id="85de2-189">.注記</span><span class="sxs-lookup"><span data-stu-id="85de2-189">.NOTES</span></span>

<span data-ttu-id="85de2-190">関数またはスクリプトに関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="85de2-190">Additional information about the function or script.</span></span>

### <a name="link"></a><span data-ttu-id="85de2-191">.リンク</span><span class="sxs-lookup"><span data-stu-id="85de2-191">.LINK</span></span>

<span data-ttu-id="85de2-192">関連するトピックの名前。</span><span class="sxs-lookup"><span data-stu-id="85de2-192">The name of a related topic.</span></span> <span data-ttu-id="85de2-193">値は、"の下の行に表示されます。LINK "キーワードの前にはコメント記号を付ける `#` か、コメントブロックに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="85de2-193">The value appears on the line below the ".LINK" keyword and must be preceded by a comment symbol `#` or included in the comment block.</span></span>

<span data-ttu-id="85de2-194">`.LINK`関連する各トピックについて、キーワードを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="85de2-194">Repeat the `.LINK` keyword for each related topic.</span></span>

<span data-ttu-id="85de2-195">このコンテンツは、ヘルプトピックの「関連リンク」セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-195">This content appears in the Related Links section of the help topic.</span></span>

<span data-ttu-id="85de2-196">キーワードの内容には、 `.Link` 同じヘルプトピックのオンラインバージョンの Uniform Resource Identifier (URI) を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="85de2-196">The `.Link` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same help topic.</span></span> <span data-ttu-id="85de2-197">の **online** パラメーターを使用すると、オンラインバージョンが開き `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-197">The online version opens when you use the **Online** parameter of `Get-Help`.</span></span> <span data-ttu-id="85de2-198">URI は "http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85de2-198">The URI must begin with "http" or "https".</span></span>

### <a name="component"></a><span data-ttu-id="85de2-199">.成分</span><span class="sxs-lookup"><span data-stu-id="85de2-199">.COMPONENT</span></span>

<span data-ttu-id="85de2-200">関数またはスクリプトが使用する、またはそれに関連するテクノロジまたは機能の名前。</span><span class="sxs-lookup"><span data-stu-id="85de2-200">The name of the technology or feature that the function or script uses, or to which it is related.</span></span> <span data-ttu-id="85de2-201">の **Component** パラメーターで `Get-Help` は、この値を使用して、によって返される検索結果をフィルター処理し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-201">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="role"></a><span data-ttu-id="85de2-202">.果たす</span><span class="sxs-lookup"><span data-stu-id="85de2-202">.ROLE</span></span>

<span data-ttu-id="85de2-203">ヘルプトピックのユーザーロールの名前です。</span><span class="sxs-lookup"><span data-stu-id="85de2-203">The name of the user role for the help topic.</span></span> <span data-ttu-id="85de2-204">の **Role** パラメーターで `Get-Help` は、この値を使用して、によって返される検索結果をフィルター処理し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-204">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="functionality"></a><span data-ttu-id="85de2-205">.機</span><span class="sxs-lookup"><span data-stu-id="85de2-205">.FUNCTIONALITY</span></span>

<span data-ttu-id="85de2-206">関数の使用目的を説明するキーワード。</span><span class="sxs-lookup"><span data-stu-id="85de2-206">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="85de2-207">の **機能** パラメーターは、 `Get-Help` この値を使用して、によって返される検索結果をフィルター処理し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-207">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="forwardhelptargetname"></a><span data-ttu-id="85de2-208">.FORWARDHELPTARGETNAME</span><span class="sxs-lookup"><span data-stu-id="85de2-208">.FORWARDHELPTARGETNAME</span></span>

<span data-ttu-id="85de2-209">指定されたコマンドのヘルプトピックにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="85de2-209">Redirects to the help topic for the specified command.</span></span> <span data-ttu-id="85de2-210">関数、スクリプト、コマンドレット、またはプロバイダーのヘルプトピックを含む、任意のヘルプトピックにユーザーをリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="85de2-210">You can redirect users to any help topic, including help topics for a function, script, cmdlet, or provider.</span></span>

```powershell
# .FORWARDHELPTARGETNAME <Command-Name>
```

### <a name="forwardhelpcategory"></a><span data-ttu-id="85de2-211">.FORWARDHELPCATEGORY</span><span class="sxs-lookup"><span data-stu-id="85de2-211">.FORWARDHELPCATEGORY</span></span>

<span data-ttu-id="85de2-212">の項目のヘルプカテゴリを指定し `.ForwardHelpTargetName` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-212">Specifies the help category of the item in `.ForwardHelpTargetName`.</span></span> <span data-ttu-id="85de2-213">有効な値は、、、、、、、、、、、、 `Alias` `Cmdlet` `HelpFile` `Function` `Provider` `General` `FAQ` `Glossary` `ScriptCommand` `ExternalScript` `Filter` または `All` です。</span><span class="sxs-lookup"><span data-stu-id="85de2-213">Valid values are `Alias`, `Cmdlet`, `HelpFile`, `Function`, `Provider`, `General`, `FAQ`, `Glossary`, `ScriptCommand`, `ExternalScript`, `Filter`, or `All`.</span></span> <span data-ttu-id="85de2-214">同じ名前のコマンドが存在する場合に競合を回避するには、このキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="85de2-214">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

```powershell
# .FORWARDHELPCATEGORY <Category>
```

### <a name="remotehelprunspace"></a><span data-ttu-id="85de2-215">.REMOTEHELPRUNSPACE 空間</span><span class="sxs-lookup"><span data-stu-id="85de2-215">.REMOTEHELPRUNSPACE</span></span>

<span data-ttu-id="85de2-216">ヘルプトピックを含むセッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="85de2-216">Specifies a session that contains the help topic.</span></span> <span data-ttu-id="85de2-217">**PSSession** オブジェクトを含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="85de2-217">Enter a variable that contains a **PSSession** object.</span></span> <span data-ttu-id="85de2-218">このキーワードは、 [エクスポート](xref:Microsoft.PowerShell.Utility.Export-PSSession) コマンドレットによって使用され、エクスポートされたコマンドのヘルプトピックを検索します。</span><span class="sxs-lookup"><span data-stu-id="85de2-218">This keyword is used by the [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) cmdlet to find the help topics for the exported commands.</span></span>

```powershell
# .REMOTEHELPRUNSPACE <PSSession-variable>
```

### <a name="externalhelp"></a><span data-ttu-id="85de2-219">..EXTERNALHELP</span><span class="sxs-lookup"><span data-stu-id="85de2-219">.EXTERNALHELP</span></span>

<span data-ttu-id="85de2-220">スクリプトまたは関数の XML ベースのヘルプファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="85de2-220">Specifies an XML-based help file for the script or function.</span></span>

```powershell
# .EXTERNALHELP <XML Help File>
```

<span data-ttu-id="85de2-221">キーワードは、 `.ExternalHelp` 関数またはスクリプトが XML ファイルに記述されている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="85de2-221">The `.ExternalHelp` keyword is required when a function or script is documented in XML files.</span></span> <span data-ttu-id="85de2-222">このキーワードがない場合、は `Get-Help` 関数またはスクリプトの XML ベースのヘルプファイルを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="85de2-222">Without this keyword, `Get-Help` cannot find the XML-based help file for the function or script.</span></span>

<span data-ttu-id="85de2-223">キーワードは、 `.ExternalHelp` 他のコメントベースのヘルプキーワードよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-223">The `.ExternalHelp` keyword takes precedence over other comment-based help keywords.</span></span> <span data-ttu-id="85de2-224">`.ExternalHelp`が存在する場合、 `Get-Help` キーワードの値に一致するヘルプトピックが見つからない場合でも、にはコメントベースのヘルプは表示されません `.ExternalHelp` 。</span><span class="sxs-lookup"><span data-stu-id="85de2-224">If `.ExternalHelp` is present, `Get-Help` does not display comment-based help, even if it cannot find a help topic that matches the value of the `.ExternalHelp` keyword.</span></span>

<span data-ttu-id="85de2-225">関数がモジュールによってエクスポートされる場合は、キーワードの値 `.ExternalHelp` をパスを含まないファイル名に設定します。</span><span class="sxs-lookup"><span data-stu-id="85de2-225">If the function is exported by a module, set the value of the `.ExternalHelp` keyword to a filename without a path.</span></span> <span data-ttu-id="85de2-226">`Get-Help` モジュールディレクトリの言語固有のサブディレクトリで、指定されたファイル名を検索します。</span><span class="sxs-lookup"><span data-stu-id="85de2-226">`Get-Help` looks for the specified file name in a language-specific subdirectory of the module directory.</span></span> <span data-ttu-id="85de2-227">関数の XML ベースのヘルプファイルの名前には要件はありませんが、次の形式を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85de2-227">There are no requirements for the name of the XML-based help file for a function, but a best practice is to use the following format:</span></span>

```
<ScriptModule.psm1>-help.xml
```

<span data-ttu-id="85de2-228">関数がモジュールに含まれていない場合は、XML ベースのヘルプファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="85de2-228">If the function is not included in a module, include a path to the XML-based help file.</span></span> <span data-ttu-id="85de2-229">値にパスが含まれていて、パスに UI カルチャ固有のサブディレクトリが含まれている場合、は、 `Get-Help` モジュールディレクトリの場合と同様に、Windows 用に設定された言語フォールバック標準に従って、スクリプトまたは関数の名前を持つ XML ファイルを再帰的に検索します。</span><span class="sxs-lookup"><span data-stu-id="85de2-229">If the value includes a path and the path contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does in a module directory.</span></span>

<span data-ttu-id="85de2-230">コマンドレットヘルプの XML ベースのヘルプファイル形式の詳細については、MSDN ライブラリの「 [How To Write Cmdlet help (コマンドレットヘルプの記述方法](https://go.microsoft.com/fwlink/?LinkID=123415) )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85de2-230">For more information about the cmdlet help XML-based help file format, see [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415) in the MSDN library.</span></span>

## <a name="autogenerated-content"></a><span data-ttu-id="85de2-231">自動生成コンテンツ</span><span class="sxs-lookup"><span data-stu-id="85de2-231">Autogenerated content</span></span>

<span data-ttu-id="85de2-232">名前、構文、パラメーターリスト、パラメーター属性テーブル、共通パラメーター、および解説は、コマンドレットによって自動的に生成され `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-232">The name, syntax, parameter list, parameter attribute table, common parameters, and remarks are automatically generated by the `Get-Help` cmdlet.</span></span>

### <a name="name"></a><span data-ttu-id="85de2-233">Name</span><span class="sxs-lookup"><span data-stu-id="85de2-233">Name</span></span>

<span data-ttu-id="85de2-234">関数のヘルプトピックの **名前** セクションは、関数の構文の関数名から取得されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-234">The **Name** section of a function help topic is taken from the function name in the function syntax.</span></span> <span data-ttu-id="85de2-235">スクリプトのヘルプトピックの **名前** は、スクリプトファイル名から取得されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-235">The **Name** of a script help topic is taken from the script filename.</span></span> <span data-ttu-id="85de2-236">名前または大文字と小文字の区別を変更するには、関数の構文またはスクリプトのファイル名を変更します。</span><span class="sxs-lookup"><span data-stu-id="85de2-236">To change the name or its capitalization, change the function syntax or the script filename.</span></span>

### <a name="syntax"></a><span data-ttu-id="85de2-237">構文</span><span class="sxs-lookup"><span data-stu-id="85de2-237">Syntax</span></span>

<span data-ttu-id="85de2-238">ヘルプトピックの **構文** セクションは、関数またはスクリプトの構文から生成されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-238">The **Syntax** section of the help topic is generated from the function or script syntax.</span></span> <span data-ttu-id="85de2-239">パラメーターの .NET 型など、ヘルプトピックの構文に詳細を追加するには、構文に詳細を追加します。</span><span class="sxs-lookup"><span data-stu-id="85de2-239">To add detail to the help topic syntax, such as the .NET type of a parameter, add the detail to the syntax.</span></span> <span data-ttu-id="85de2-240">パラメーターの型を指定しない場合、 **オブジェクト** の種類が既定値として挿入されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-240">If you do not specify a parameter type, the **Object** type is inserted as the default value.</span></span>

### <a name="parameter-list"></a><span data-ttu-id="85de2-241">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="85de2-241">Parameter List</span></span>

<span data-ttu-id="85de2-242">ヘルプトピックのパラメーターリストは、関数またはスクリプトの構文、およびキーワードを使用して追加する説明から生成され `.Parameter` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-242">The parameter list in the help topic is generated from the function or script syntax and from the descriptions that you add by using the `.Parameter` keyword.</span></span> <span data-ttu-id="85de2-243">関数のパラメーターは、関数またはスクリプトの構文に表示されるのと同じ順序で、ヘルプトピックの **パラメーター** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-243">The function parameters appear in the **Parameters** section of the help topic in the same order that they appear in the function or script syntax.</span></span> <span data-ttu-id="85de2-244">パラメーター名のスペルと大文字小文字の区別も構文から取得されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-244">The spelling and capitalization of parameter names is also taken from the syntax.</span></span> <span data-ttu-id="85de2-245">キーワードによって指定されたパラメーター名の影響を受けません `.Parameter` 。</span><span class="sxs-lookup"><span data-stu-id="85de2-245">It is not affected by the parameter name specified by the `.Parameter` keyword.</span></span>

### <a name="common-parameters"></a><span data-ttu-id="85de2-246">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="85de2-246">Common Parameters</span></span>

<span data-ttu-id="85de2-247">**一般的なパラメーター** は、ヘルプトピックの構文とパラメーターリストに、何の効果もない場合でも追加されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-247">The **Common parameters** are added to the syntax and parameter list of the help topic, even if they have no effect.</span></span> <span data-ttu-id="85de2-248">共通パラメーターの詳細については、「 [about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85de2-248">For more information about the common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="85de2-249">パラメーター属性テーブル</span><span class="sxs-lookup"><span data-stu-id="85de2-249">Parameter Attribute Table</span></span>

<span data-ttu-id="85de2-250">`Get-Help` の **Full** パラメーターまたは **parameter** パラメーターを使用するときに表示されるパラメーター属性のテーブルを生成し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="85de2-250">`Get-Help` generates the table of parameter attributes that appears when you use the **Full** or **Parameter** parameter of `Get-Help`.</span></span> <span data-ttu-id="85de2-251">**必須** 、 **位置** 、および **既定** 値の属性の値は、関数またはスクリプトの構文から取得されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-251">The value of the **Required** , **Position** , and **Default** value attributes is taken from the function or script syntax.</span></span>

<span data-ttu-id="85de2-252">既定値および **Accept ワイルドカード文字** の値は、関数またはスクリプトで定義されている場合でも、parameter 属性テーブルには表示されません。</span><span class="sxs-lookup"><span data-stu-id="85de2-252">Default values and a value for **Accept Wildcard characters** do not appear in the parameter attribute table even when they are defined in the function or script.</span></span> <span data-ttu-id="85de2-253">ユーザーを支援するために、この情報をパラメーターの説明に入力してください。</span><span class="sxs-lookup"><span data-stu-id="85de2-253">To help users, provide this information in the parameter description.</span></span>

### <a name="remarks"></a><span data-ttu-id="85de2-254">解説</span><span class="sxs-lookup"><span data-stu-id="85de2-254">Remarks</span></span>

<span data-ttu-id="85de2-255">ヘルプトピックの「 **解説** 」セクションは、関数またはスクリプトの名前から自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="85de2-255">The **Remarks** section of the help topic is automatically generated from the function or script name.</span></span> <span data-ttu-id="85de2-256">コンテンツを変更または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="85de2-256">You cannot change or affect its content.</span></span>

## <a name="examples"></a><span data-ttu-id="85de2-257">例</span><span class="sxs-lookup"><span data-stu-id="85de2-257">Examples</span></span>

### <a name="comment-based-help-for-a-function"></a><span data-ttu-id="85de2-258">関数のコメントベースのヘルプ</span><span class="sxs-lookup"><span data-stu-id="85de2-258">Comment-based Help for a Function</span></span>

<span data-ttu-id="85de2-259">次のサンプル関数には、コメントベースのヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85de2-259">The following sample function includes comment-based help:</span></span>

```powershell
function Add-Extension
{
param ([string]$Name,[string]$Extension = "txt")
$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name.
Takes any strings for the file name or extension.

.PARAMETER Name
Specifies the file name.

.PARAMETER Extension
Specifies the extension. "Txt" is the default.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension
or file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

<span data-ttu-id="85de2-260">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85de2-260">The results are as follows:</span></span>

```powershell
Get-Help -Name "Add-Extension" -Full
```

```Output
NAME

Add-Extension

SYNOPSIS

Adds a file name extension to a supplied name.

SYNTAX

Add-Extension [[-Name] <String>] [[-Extension] <String>]
[<CommonParameters>]

DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

PARAMETERS

-Name
Specifies the file name.

Required?                    false
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-Extension
Specifies the extension. "Txt" is the default.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type
"get-help about_commonparameters".

INPUTS
None. You cannot pipe objects to Add-Extension.

OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

Example 1

PS> extension -name "File"
File.txt

Example 2

PS> extension -name "File" -extension "doc"
File.doc

Example 3

PS> extension "File" "doc"
File.doc

RELATED LINKS

http://www.fabrikam.com/extension.html
Set-Item
```

### <a name="parameter-descriptions-in-function-syntax"></a><span data-ttu-id="85de2-261">関数の構文におけるパラメーターの説明</span><span class="sxs-lookup"><span data-stu-id="85de2-261">Parameter Descriptions in Function Syntax</span></span>

<span data-ttu-id="85de2-262">この例は前の例と同じですが、パラメーターの説明が関数の構文に挿入される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="85de2-262">This example is the same as the previous one, except that the parameter descriptions are inserted in the function syntax.</span></span> <span data-ttu-id="85de2-263">この形式は、説明が brief の場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85de2-263">This format is most useful when the descriptions are brief.</span></span>

```powershell
function Add-Extension
{
param
(

[string]
#Specifies the file name.
$name,

[string]
#Specifies the file name extension. "Txt" is the default.
$extension = "txt"
)

$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

### <a name="comment-based-help-for-a-script"></a><span data-ttu-id="85de2-264">スクリプトのコメントベースのヘルプ</span><span class="sxs-lookup"><span data-stu-id="85de2-264">Comment-based Help for a Script</span></span>

<span data-ttu-id="85de2-265">次のサンプルスクリプトには、コメントベースのヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85de2-265">The following sample script includes comment-based help.</span></span> <span data-ttu-id="85de2-266">終了とステートメントの間に空白行があることに注意して `#>` `Param` ください。</span><span class="sxs-lookup"><span data-stu-id="85de2-266">Notice the blank lines between the closing `#>` and the `Param` statement.</span></span> <span data-ttu-id="85de2-267">ステートメントが含まれていないスクリプトでは、 `Param` ヘルプトピックの最後のコメントと最初の関数宣言の間に、少なくとも2つの空白行が必要です。</span><span class="sxs-lookup"><span data-stu-id="85de2-267">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the help topic and the first function declaration.</span></span> <span data-ttu-id="85de2-268">これらの空白行がない場合、では `Get-Help` ヘルプトピックがスクリプトではなく関数に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="85de2-268">Without these blank lines, `Get-Help` associates the help topic with the function, not the script.</span></span>

```powershell
<#
.SYNOPSIS

Performs monthly data updates.

.DESCRIPTION

The Update-Month.ps1 script updates the registry with new data generated
during the past month and generates a report.

.PARAMETER InputPath
Specifies the path to the CSV-based input file.

.PARAMETER OutputPath
Specifies the name and path for the CSV-based output file. By default,
MonthlyUpdates.ps1 generates a name from the date and time it runs, and
saves the output in the local directory.

.INPUTS

None. You cannot pipe objects to Update-Month.ps1.

.OUTPUTS

None. Update-Month.ps1 does not generate any output.

.EXAMPLE

PS> .\Update-Month.ps1

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath `
C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
...
```

<span data-ttu-id="85de2-269">次のコマンドは、スクリプトのヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="85de2-269">The following command gets the script help.</span></span> <span data-ttu-id="85de2-270">スクリプトは環境変数に示されているディレクトリにないため `$env:Path` 、スクリプトヘルプを `Get-Help` 取得するコマンドではスクリプトパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85de2-270">Because the script is not in a directory that is listed in the `$env:Path` environment variable, the `Get-Help` command that gets the script help must specify the script path.</span></span>

```powershell
Get-Help -Path .\update-month.ps1 -Full
```

```Output
# NAME

C:\ps-test\Update-Month.ps1

# SYNOPSIS

Performs monthly data updates.

# SYNTAX

C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
<String>] [<CommonParameters>]

# DESCRIPTION

The Update-Month.ps1 script updates the registry with new data
generated during the past month and generates a report.

# PARAMETERS

-InputPath
Specifies the path to the CSV-based input file.

Required?                    true
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-OutputPath
Specifies the name and path for the CSV-based output file. By
default, MonthlyUpdates.ps1 generates a name from the date
and time it runs, and saves the output in the local directory.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type,
"get-help about_commonparameters".

# INPUTS

None. You cannot pipe objects to Update-Month.ps1.

# OUTPUTS

None. Update-Month.ps1 does not generate any output.

Example 1

PS> .\Update-Month.ps1

Example 2

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

Example 3

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
C:\Reports\2009\January.csv

# RELATED LINKS
```

### <a name="redirecting-to-an-xml-file"></a><span data-ttu-id="85de2-271">XML ファイルへのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="85de2-271">Redirecting to an XML File</span></span>

<span data-ttu-id="85de2-272">関数とスクリプトの XML ベースのヘルプトピックを記述できます。</span><span class="sxs-lookup"><span data-stu-id="85de2-272">You can write XML-based help topics for functions and scripts.</span></span> <span data-ttu-id="85de2-273">コメントベースのヘルプは実装が簡単ですが、更新可能なヘルプには XML ベースのヘルプが必要で、複数の言語ではヘルプトピックを提供します。</span><span class="sxs-lookup"><span data-stu-id="85de2-273">Although comment-based help is easier to implement, XML-based help is required for Updatable Help and to provide help topics in multiple languages.</span></span>

<span data-ttu-id="85de2-274">次の例は、Update-Month.ps1 スクリプトの最初の数行を示しています。</span><span class="sxs-lookup"><span data-stu-id="85de2-274">The following example shows the first few lines of the Update-Month.ps1 script.</span></span>
<span data-ttu-id="85de2-275">スクリプトでは、キーワードを使用して、 `.ExternalHelp` スクリプトの XML ベースのヘルプトピックへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="85de2-275">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based help topic for the script.</span></span>

<span data-ttu-id="85de2-276">キーワードの値は、 `.ExternalHelp` キーワードと同じ行に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="85de2-276">Note that the value of the `.ExternalHelp` keyword appears on the same line as the keyword.</span></span> <span data-ttu-id="85de2-277">その他の配置は無効になります。</span><span class="sxs-lookup"><span data-stu-id="85de2-277">Any other placement is ineffective.</span></span>

```powershell
# .ExternalHelp C:\MyScripts\Update-Month-Help.xml

param ([string]$InputPath, [string]$OutPutPath)
function Get-Data { }
...
```

<span data-ttu-id="85de2-278">次の例は、関数内でのキーワードの有効な3つの配置を示して `.ExternalHelp` います。</span><span class="sxs-lookup"><span data-stu-id="85de2-278">The following examples show three valid placements of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
# .ExternalHelp C:\ps-test\Add-Extension.xml

param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

```powershell
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name

# .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

```powershell
# .ExternalHelp C:\ps-test\Add-Extension.xml
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

### <a name="redirecting-to-a-different-help-topic"></a><span data-ttu-id="85de2-279">別のヘルプトピックへのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="85de2-279">Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="85de2-280">次のコードは、PowerShell の組み込みヘルプ関数の先頭から抜粋したもので、一度に1画面のヘルプテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="85de2-280">The following code is an excerpt from the beginning of the built-in help function in PowerShell, which displays one screen of help text at a time.</span></span>
<span data-ttu-id="85de2-281">コマンドレットのヘルプトピックでは `Get-Help` help 関数について説明しているので、help 関数はキーワードとキーワードを使用して `.ForwardHelpTargetName` ユーザーを `.ForwardHelpCategory` `Get-Help` コマンドレットのヘルプトピックにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="85de2-281">Because the help topic for the `Get-Help` cmdlet describes the help function, the help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the `Get-Help` cmdlet help topic.</span></span>

```powershell
function help
{

<#
.FORWARDHELPTARGETNAME Get-Help
.FORWARDHELPCATEGORY Cmdlet
#>
[CmdletBinding(DefaultParameterSetName='AllUsersView')]
param(
[Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
[System.String]
${Name},
...
```

<span data-ttu-id="85de2-282">次のコマンドは、この機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="85de2-282">The following command uses this feature:</span></span>

```powershell
Get-Help -Name help
```

```Output
NAME

Get-Help

SYNOPSIS

Displays information about PowerShell cmdlets and concepts.
...
```

## <a name="see-also"></a><span data-ttu-id="85de2-283">関連項目</span><span class="sxs-lookup"><span data-stu-id="85de2-283">See also</span></span>

[<span data-ttu-id="85de2-284">about_Functions</span><span class="sxs-lookup"><span data-stu-id="85de2-284">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="85de2-285">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="85de2-285">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="85de2-286">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="85de2-286">about_Scripts</span></span>](about_Scripts.md)

[<span data-ttu-id="85de2-287">コマンドレットヘルプの記述方法</span><span class="sxs-lookup"><span data-stu-id="85de2-287">How to Write Cmdlet Help</span></span>](https://go.microsoft.com/fwlink/?LinkID=123415)
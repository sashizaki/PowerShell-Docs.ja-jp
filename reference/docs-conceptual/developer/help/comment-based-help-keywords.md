---
ms.date: 06/09/2020
ms.topic: reference
title: コメント ベースのヘルプのキーワード
description: コメント ベースのヘルプのキーワード
ms.openlocfilehash: d87dde8700813767f6c09cfce70ed06c7964ebc7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645474"
---
# <a name="comment-based-help-keywords"></a><span data-ttu-id="0eea5-103">コメント ベースのヘルプのキーワード</span><span class="sxs-lookup"><span data-stu-id="0eea5-103">Comment-Based Help Keywords</span></span>

<span data-ttu-id="0eea5-104">このトピックでは、コメントベースのヘルプのキーワードの一覧とその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-104">This topic lists and describes the keywords in comment-based help.</span></span>

## <a name="keywords-in-comment-based-help"></a><span data-ttu-id="0eea5-105">Comment-Based ヘルプのキーワード</span><span class="sxs-lookup"><span data-stu-id="0eea5-105">Keywords in Comment-Based Help</span></span>

<span data-ttu-id="0eea5-106">有効なコメントベースのヘルプキーワードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-106">The following are valid comment-based Help keywords.</span></span> <span data-ttu-id="0eea5-107">これらの一覧は、通常、ヘルプトピックに表示される順序で、使用目的と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-107">They are listed in the order in which they typically appear in a Help topic along with their intended use.</span></span> <span data-ttu-id="0eea5-108">これらのキーワードは、コメントベースのヘルプ内で任意の順序で表示でき、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="0eea5-108">These keywords can appear in any order in the comment-based Help, and they are not case-sensitive.</span></span>

<span data-ttu-id="0eea5-109">キーワードは、 `.EXTERNALHELP` 他のすべてのコメントベースのヘルプキーワードよりも優先されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0eea5-109">Note that the `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span>
<span data-ttu-id="0eea5-110">が指定されている場合、 `.EXTERNALHELP` キーワードの値に一致するヘルプファイルが見つからない場合でも、このコマンドレット [では](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) 、コメントベースのヘルプは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0eea5-110">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0eea5-111">.概要</span><span class="sxs-lookup"><span data-stu-id="0eea5-111">.SYNOPSIS</span></span>

<span data-ttu-id="0eea5-112">関数またはスクリプトの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="0eea5-112">A brief description of the function or script.</span></span> <span data-ttu-id="0eea5-113">このキーワードは、各トピックで1回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-113">This keyword can be used only once in each topic.</span></span>

## <a name="description"></a><span data-ttu-id="0eea5-114">.記述</span><span class="sxs-lookup"><span data-stu-id="0eea5-114">.DESCRIPTION</span></span>

<span data-ttu-id="0eea5-115">関数またはスクリプトの詳細な説明。</span><span class="sxs-lookup"><span data-stu-id="0eea5-115">A detailed description of the function or script.</span></span> <span data-ttu-id="0eea5-116">このキーワードは、各トピックで1回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-116">This keyword can be used only once in each topic.</span></span>

## <a name="parameter-parameter-name"></a><span data-ttu-id="0eea5-117">.引き \<Parameter-Name></span><span class="sxs-lookup"><span data-stu-id="0eea5-117">.PARAMETER \<Parameter-Name></span></span>

<span data-ttu-id="0eea5-118">パラメーターの説明。</span><span class="sxs-lookup"><span data-stu-id="0eea5-118">The description of a parameter.</span></span> <span data-ttu-id="0eea5-119">`.PARAMETER`関数またはスクリプトの各パラメーターにキーワードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-119">You can include a `.PARAMETER` keyword for each parameter in the function or script.</span></span>

<span data-ttu-id="0eea5-120">キーワードは、 `.PARAMETER` コメントブロック内で任意の順序で表示できますが、パラメーターがステートメントまたは関数の宣言に表示される順序によって、 `Param` ヘルプトピックでパラメーターが表示される順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="0eea5-120">The `.PARAMETER` keywords can appear in any order in the comment block, but the order in which the parameters appear in the `Param` statement or function declaration determines the order in which the parameters appear in Help topic.</span></span> <span data-ttu-id="0eea5-121">ヘルプトピックのパラメーターの順序を変更するに `Param` は、ステートメントまたは関数の宣言でパラメーターの順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-121">To change the order of parameters in the Help topic, change the order of the parameters in the `Param` statement or function declaration.</span></span>

<span data-ttu-id="0eea5-122">パラメーターの説明を指定するには、パラメーター変数名の直前のステートメントにコメントを配置し `Param` ます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-122">You can also specify a parameter description by placing a comment in the `Param` statement immediately before the parameter variable name.</span></span> <span data-ttu-id="0eea5-123">ステートメントコメントとキーワードの両方を使用する場合 `Param` `.PARAMETER` は、キーワードに関連付けられている説明 `.PARAMETER` が使用され、 `Param` ステートメントコメントは無視されます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-123">If you use both a `Param` statement comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the `Param` statement comment is ignored.</span></span>

## <a name="example"></a><span data-ttu-id="0eea5-124">.よう</span><span class="sxs-lookup"><span data-stu-id="0eea5-124">.EXAMPLE</span></span>

<span data-ttu-id="0eea5-125">関数またはスクリプトを使用するサンプルコマンド。必要に応じて、サンプル出力と説明が続きます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-125">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="0eea5-126">各例について、このキーワードを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-126">Repeat this keyword for each example.</span></span>

## <a name="inputs"></a><span data-ttu-id="0eea5-127">.INPUTACCEL</span><span class="sxs-lookup"><span data-stu-id="0eea5-127">.INPUTS</span></span>

<span data-ttu-id="0eea5-128">関数またはスクリプトにパイプできるオブジェクトの Microsoft .NET Framework 型。</span><span class="sxs-lookup"><span data-stu-id="0eea5-128">The Microsoft .NET Framework types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="0eea5-129">入力オブジェクトの説明を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-129">You can also include a description of the input objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="0eea5-130">.出力</span><span class="sxs-lookup"><span data-stu-id="0eea5-130">.OUTPUTS</span></span>

<span data-ttu-id="0eea5-131">コマンドレットが返すオブジェクトの .NET Framework 型。</span><span class="sxs-lookup"><span data-stu-id="0eea5-131">The .NET Framework type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="0eea5-132">返されたオブジェクトの説明を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-132">You can also include a description of the returned objects.</span></span>

## <a name="notes"></a><span data-ttu-id="0eea5-133">.注記</span><span class="sxs-lookup"><span data-stu-id="0eea5-133">.NOTES</span></span>

<span data-ttu-id="0eea5-134">関数またはスクリプトに関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="0eea5-134">Additional information about the function or script.</span></span>

## <a name="link"></a><span data-ttu-id="0eea5-135">.リンク</span><span class="sxs-lookup"><span data-stu-id="0eea5-135">.LINK</span></span>

<span data-ttu-id="0eea5-136">関連するトピックの名前。</span><span class="sxs-lookup"><span data-stu-id="0eea5-136">The name of a related topic.</span></span> <span data-ttu-id="0eea5-137">関連する各トピックについて、このキーワードを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-137">Repeat this keyword for each related topic.</span></span> <span data-ttu-id="0eea5-138">このコンテンツは、ヘルプトピックの「関連リンク」セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-138">This content appears in the Related Links section of the Help topic.</span></span>

<span data-ttu-id="0eea5-139">キーワードの内容には、 `.LINK` 同じヘルプトピックのオンラインバージョンの Uniform Resource Identifier (URI) を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-139">The `.LINK` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same Help topic.</span></span> <span data-ttu-id="0eea5-140">のパラメーターを使用すると、オンラインバージョンが開き `Online` `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-140">The online version opens when you use the `Online` parameter of `Get-Help`.</span></span> <span data-ttu-id="0eea5-141">URI は "http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0eea5-141">The URI must begin with "http" or "https".</span></span>

## <a name="component"></a><span data-ttu-id="0eea5-142">.成分</span><span class="sxs-lookup"><span data-stu-id="0eea5-142">.COMPONENT</span></span>

<span data-ttu-id="0eea5-143">関数またはスクリプトが使用する、またはそれに関連するテクノロジまたは機能の名前。</span><span class="sxs-lookup"><span data-stu-id="0eea5-143">The name of the technology or feature that the function or script uses, or to which it is related.</span></span>
<span data-ttu-id="0eea5-144">の **Component** パラメーターで `Get-Help` は、この値を使用して、によって返される検索結果をフィルター処理し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-144">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="role"></a><span data-ttu-id="0eea5-145">.果たす</span><span class="sxs-lookup"><span data-stu-id="0eea5-145">.Role</span></span>

<span data-ttu-id="0eea5-146">ヘルプトピックのユーザーロールの名前です。</span><span class="sxs-lookup"><span data-stu-id="0eea5-146">The name of the user role for the help topic.</span></span> <span data-ttu-id="0eea5-147">の **Role** パラメーターで `Get-Help` は、この値を使用して、によって返される検索結果をフィルター処理し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-147">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="functionality"></a><span data-ttu-id="0eea5-148">.機</span><span class="sxs-lookup"><span data-stu-id="0eea5-148">.FUNCTIONALITY</span></span>

<span data-ttu-id="0eea5-149">関数の使用目的を説明するキーワード。</span><span class="sxs-lookup"><span data-stu-id="0eea5-149">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="0eea5-150">の **機能** パラメーターは、 `Get-Help` この値を使用して、によって返される検索結果をフィルター処理し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-150">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="forwardhelptargetname-command-name"></a><span data-ttu-id="0eea5-151">.FORWARDHELPTARGETNAME \<Command-Name></span><span class="sxs-lookup"><span data-stu-id="0eea5-151">.FORWARDHELPTARGETNAME \<Command-Name></span></span>

<span data-ttu-id="0eea5-152">指定されたコマンドのヘルプトピックにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="0eea5-152">Redirects to the Help topic for the specified command.</span></span> <span data-ttu-id="0eea5-153">関数、スクリプト、コマンドレット、またはプロバイダーのヘルプトピックを含む、任意のヘルプトピックにユーザーをリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-153">You can redirect users to any Help topic, including Help topics for a function, script, cmdlet, or provider.</span></span>

## <a name="forwardhelpcategory-category"></a><span data-ttu-id="0eea5-154">.FORWARDHELPCATEGORY \<Category></span><span class="sxs-lookup"><span data-stu-id="0eea5-154">.FORWARDHELPCATEGORY \<Category></span></span>

<span data-ttu-id="0eea5-155">の項目のヘルプカテゴリを指定し `.FORWARDHELPTARGETNAME` ます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-155">Specifies the Help category of the item in `.FORWARDHELPTARGETNAME`.</span></span> <span data-ttu-id="0eea5-156">同じ名前のコマンドが存在する場合に競合を回避するには、このキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-156">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

<span data-ttu-id="0eea5-157">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0eea5-157">Valid values are:</span></span>

- <span data-ttu-id="0eea5-158">エイリアス</span><span class="sxs-lookup"><span data-stu-id="0eea5-158">Alias</span></span>
- <span data-ttu-id="0eea5-159">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="0eea5-159">Cmdlet</span></span>
- <span data-ttu-id="0eea5-160">HelpFile</span><span class="sxs-lookup"><span data-stu-id="0eea5-160">HelpFile</span></span>
- <span data-ttu-id="0eea5-161">機能</span><span class="sxs-lookup"><span data-stu-id="0eea5-161">Function</span></span>
- <span data-ttu-id="0eea5-162">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="0eea5-162">Provider</span></span>
- <span data-ttu-id="0eea5-163">全般</span><span class="sxs-lookup"><span data-stu-id="0eea5-163">General</span></span>
- <span data-ttu-id="0eea5-164">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="0eea5-164">FAQ</span></span>
- <span data-ttu-id="0eea5-165">用語集</span><span class="sxs-lookup"><span data-stu-id="0eea5-165">Glossary</span></span>
- <span data-ttu-id="0eea5-166">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="0eea5-166">ScriptCommand</span></span>
- <span data-ttu-id="0eea5-167">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="0eea5-167">ExternalScript</span></span>
- <span data-ttu-id="0eea5-168">フィルター</span><span class="sxs-lookup"><span data-stu-id="0eea5-168">Filter</span></span>
- <span data-ttu-id="0eea5-169">すべて</span><span class="sxs-lookup"><span data-stu-id="0eea5-169">All</span></span>

## <a name="remotehelprunspace-pssession-variable"></a><span data-ttu-id="0eea5-170">.REMOTEHELPRUNSPACE 空間 \<PSSession-variable></span><span class="sxs-lookup"><span data-stu-id="0eea5-170">.REMOTEHELPRUNSPACE \<PSSession-variable></span></span>

<span data-ttu-id="0eea5-171">ヘルプトピックを含むセッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-171">Specifies a session that contains the Help topic.</span></span> <span data-ttu-id="0eea5-172">PSSession を含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-172">Enter a variable that contains a PSSession.</span></span> <span data-ttu-id="0eea5-173">このキーワードは、エクスポートされ `Export-PSSession` たコマンドのヘルプトピックを検索するために、コマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-173">This keyword is used by the `Export-PSSession` cmdlet to find the Help topics for the exported commands.</span></span>

## <a name="externalhelp-xml-help-file"></a><span data-ttu-id="0eea5-174">..EXTERNALHELP \<XML Help File></span><span class="sxs-lookup"><span data-stu-id="0eea5-174">.EXTERNALHELP \<XML Help File></span></span>

<span data-ttu-id="0eea5-175">スクリプトまたは関数の XML ベースのヘルプファイルのパスと名前の両方またはいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-175">Specifies the path and/or name of an XML-based Help file for the script or function.</span></span>

<span data-ttu-id="0eea5-176">キーワードは、 `.EXTERNALHELP` XML ベースのファイル内のスクリプトまたは関数のヘルプを取得するように [、コマンド](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) レットに指示します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-176">The `.EXTERNALHELP` keyword tells the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet to get help for the script or function in an XML-based file.</span></span> <span data-ttu-id="0eea5-177">キーワードは、 `.EXTERNALHELP` スクリプトまたは関数に XML ベースのヘルプファイルを使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="0eea5-177">The `.EXTERNALHELP` keyword is required when using an XML-based help file for a script or function.</span></span> <span data-ttu-id="0eea5-178">使用しない場合、 `Get-Help` 関数またはスクリプトのヘルプファイルは検索されません。</span><span class="sxs-lookup"><span data-stu-id="0eea5-178">Without it, `Get-Help` will not find a help file for the function or script.</span></span>

<span data-ttu-id="0eea5-179">キーワードは、 `.EXTERNALHELP` 他のすべてのコメントベースのヘルプキーワードよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-179">The `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span> <span data-ttu-id="0eea5-180">が指定されている場合、 `.EXTERNALHELP` キーワードの値に一致するヘルプファイルが見つからない場合でも、このコマンドレット [では](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) 、コメントベースのヘルプは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0eea5-180">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

<span data-ttu-id="0eea5-181">関数がスクリプトモジュールによってエクスポートされる場合、の値は `.EXTERNALHELP` パスを含まないファイル名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0eea5-181">When the function is exported by a script module, the value of `.EXTERNALHELP` should be a filename without a path.</span></span> <span data-ttu-id="0eea5-182">`Get-Help` は、モジュールディレクトリのロケール固有のサブディレクトリでファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-182">`Get-Help` looks for the file in a locale-specific subdirectory of the module directory.</span></span> <span data-ttu-id="0eea5-183">ファイル名には要件はありませんが、ファイル名の形式としてを使用することをお勧め `<ScriptModule>.psm1-help.xml` します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-183">There are no requirements for the filename, but a best practice is to use the following filename format: `<ScriptModule>.psm1-help.xml`.</span></span>

<span data-ttu-id="0eea5-184">関数がモジュールに関連付けられていない場合は、キーワードの値にパスとファイル名を含め `.EXTERNALHELP` ます。</span><span class="sxs-lookup"><span data-stu-id="0eea5-184">When the function is not associated with a module, include a path and filename in the value of the `.EXTERNALHELP` keyword.</span></span> <span data-ttu-id="0eea5-185">XML ファイルへの指定したパスに UI カルチャ固有のサブディレクトリが含まれている場合、は、 `Get-Help` すべての xml ベースのヘルプトピックと同様に、Windows 用に設定された言語フォールバック標準に従って、スクリプトまたは関数の名前を持つ xml ファイルを再帰的に検索します。</span><span class="sxs-lookup"><span data-stu-id="0eea5-185">If the specified path to the XML file contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does for all XML-based Help topics.</span></span>

<span data-ttu-id="0eea5-186">コマンドレットヘルプの XML ベースのヘルプファイル形式の詳細については、「 [Windows PowerShell コマンドレットヘルプの記述](./writing-help-for-windows-powershell-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0eea5-186">For more information about the cmdlet Help XML-based Help file format, see [Writing Windows PowerShell Cmdlet Help](./writing-help-for-windows-powershell-cmdlets.md).</span></span>

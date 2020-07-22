---
title: コメント ベースのヘルプのキーワード
ms.date: 06/09/2020
ms.openlocfilehash: fb737c19d7b7f4d003af3ba36bb396bac52d94e7
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893154"
---
# <a name="comment-based-help-keywords"></a><span data-ttu-id="5d0c9-102">コメント ベースのヘルプのキーワード</span><span class="sxs-lookup"><span data-stu-id="5d0c9-102">Comment-Based Help Keywords</span></span>

<span data-ttu-id="5d0c9-103">このトピックでは、コメントベースのヘルプのキーワードの一覧とその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-103">This topic lists and describes the keywords in comment-based help.</span></span>

## <a name="keywords-in-comment-based-help"></a><span data-ttu-id="5d0c9-104">コメントベースのヘルプのキーワード</span><span class="sxs-lookup"><span data-stu-id="5d0c9-104">Keywords in Comment-Based Help</span></span>

<span data-ttu-id="5d0c9-105">有効なコメントベースのヘルプキーワードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-105">The following are valid comment-based Help keywords.</span></span> <span data-ttu-id="5d0c9-106">これらの一覧は、通常、ヘルプトピックに表示される順序で、使用目的と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-106">They are listed in the order in which they typically appear in a Help topic along with their intended use.</span></span> <span data-ttu-id="5d0c9-107">これらのキーワードは、コメントベースのヘルプ内で任意の順序で表示でき、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-107">These keywords can appear in any order in the comment-based Help, and they are not case-sensitive.</span></span>

<span data-ttu-id="5d0c9-108">キーワードは、 `.EXTERNALHELP` 他のすべてのコメントベースのヘルプキーワードよりも優先されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-108">Note that the `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span>
<span data-ttu-id="5d0c9-109">が指定されている場合、 `.EXTERNALHELP` キーワードの値に一致するヘルプファイルが見つからない場合でも、このコマンドレット[では](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand)、コメントベースのヘルプは表示されません。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-109">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5d0c9-110">.概要</span><span class="sxs-lookup"><span data-stu-id="5d0c9-110">.SYNOPSIS</span></span>

<span data-ttu-id="5d0c9-111">関数またはスクリプトの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-111">A brief description of the function or script.</span></span> <span data-ttu-id="5d0c9-112">このキーワードは、各トピックで1回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-112">This keyword can be used only once in each topic.</span></span>

## <a name="description"></a><span data-ttu-id="5d0c9-113">.記述</span><span class="sxs-lookup"><span data-stu-id="5d0c9-113">.DESCRIPTION</span></span>

<span data-ttu-id="5d0c9-114">関数またはスクリプトの詳細な説明。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-114">A detailed description of the function or script.</span></span> <span data-ttu-id="5d0c9-115">このキーワードは、各トピックで1回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-115">This keyword can be used only once in each topic.</span></span>

## <a name="parameter-parameter-name"></a><span data-ttu-id="5d0c9-116">.引き\<Parameter-Name></span><span class="sxs-lookup"><span data-stu-id="5d0c9-116">.PARAMETER \<Parameter-Name></span></span>

<span data-ttu-id="5d0c9-117">パラメーターの説明。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-117">The description of a parameter.</span></span> <span data-ttu-id="5d0c9-118">`.PARAMETER`関数またはスクリプトの各パラメーターにキーワードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-118">You can include a `.PARAMETER` keyword for each parameter in the function or script.</span></span>

<span data-ttu-id="5d0c9-119">キーワードは、 `.PARAMETER` コメントブロック内で任意の順序で表示できますが、パラメーターがステートメントまたは関数の宣言に表示される順序によって、 `Param` ヘルプトピックでパラメーターが表示される順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-119">The `.PARAMETER` keywords can appear in any order in the comment block, but the order in which the parameters appear in the `Param` statement or function declaration determines the order in which the parameters appear in Help topic.</span></span> <span data-ttu-id="5d0c9-120">ヘルプトピックのパラメーターの順序を変更するに `Param` は、ステートメントまたは関数の宣言でパラメーターの順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-120">To change the order of parameters in the Help topic, change the order of the parameters in the `Param` statement or function declaration.</span></span>

<span data-ttu-id="5d0c9-121">パラメーターの説明を指定するには、パラメーター変数名の直前のステートメントにコメントを配置し `Param` ます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-121">You can also specify a parameter description by placing a comment in the `Param` statement immediately before the parameter variable name.</span></span> <span data-ttu-id="5d0c9-122">ステートメントコメントとキーワードの両方を使用する場合 `Param` `.PARAMETER` は、キーワードに関連付けられている説明 `.PARAMETER` が使用され、 `Param` ステートメントコメントは無視されます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-122">If you use both a `Param` statement comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the `Param` statement comment is ignored.</span></span>

## <a name="example"></a><span data-ttu-id="5d0c9-123">.よう</span><span class="sxs-lookup"><span data-stu-id="5d0c9-123">.EXAMPLE</span></span>

<span data-ttu-id="5d0c9-124">関数またはスクリプトを使用するサンプルコマンド。必要に応じて、サンプル出力と説明が続きます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-124">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="5d0c9-125">各例について、このキーワードを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-125">Repeat this keyword for each example.</span></span>

## <a name="inputs"></a><span data-ttu-id="5d0c9-126">.INPUTACCEL</span><span class="sxs-lookup"><span data-stu-id="5d0c9-126">.INPUTS</span></span>

<span data-ttu-id="5d0c9-127">関数またはスクリプトにパイプできるオブジェクトの Microsoft .NET Framework 型。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-127">The Microsoft .NET Framework types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="5d0c9-128">入力オブジェクトの説明を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-128">You can also include a description of the input objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="5d0c9-129">.出力</span><span class="sxs-lookup"><span data-stu-id="5d0c9-129">.OUTPUTS</span></span>

<span data-ttu-id="5d0c9-130">コマンドレットが返すオブジェクトの .NET Framework 型。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-130">The .NET Framework type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="5d0c9-131">返されたオブジェクトの説明を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-131">You can also include a description of the returned objects.</span></span>

## <a name="notes"></a><span data-ttu-id="5d0c9-132">.注記</span><span class="sxs-lookup"><span data-stu-id="5d0c9-132">.NOTES</span></span>

<span data-ttu-id="5d0c9-133">関数またはスクリプトに関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-133">Additional information about the function or script.</span></span>

## <a name="link"></a><span data-ttu-id="5d0c9-134">.リンク</span><span class="sxs-lookup"><span data-stu-id="5d0c9-134">.LINK</span></span>

<span data-ttu-id="5d0c9-135">関連するトピックの名前。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-135">The name of a related topic.</span></span> <span data-ttu-id="5d0c9-136">関連する各トピックについて、このキーワードを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-136">Repeat this keyword for each related topic.</span></span> <span data-ttu-id="5d0c9-137">このコンテンツは、ヘルプトピックの「関連リンク」セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-137">This content appears in the Related Links section of the Help topic.</span></span>

<span data-ttu-id="5d0c9-138">キーワードの内容には、 `.LINK` 同じヘルプトピックのオンラインバージョンの Uniform Resource Identifier (URI) を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-138">The `.LINK` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same Help topic.</span></span> <span data-ttu-id="5d0c9-139">のパラメーターを使用すると、オンラインバージョンが開き `Online` `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-139">The online version opens when you use the `Online` parameter of `Get-Help`.</span></span> <span data-ttu-id="5d0c9-140">URI は "http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-140">The URI must begin with "http" or "https".</span></span>

## <a name="component"></a><span data-ttu-id="5d0c9-141">.成分</span><span class="sxs-lookup"><span data-stu-id="5d0c9-141">.COMPONENT</span></span>

<span data-ttu-id="5d0c9-142">関数またはスクリプトが使用する、またはそれに関連するテクノロジまたは機能の名前。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-142">The name of the technology or feature that the function or script uses, or to which it is related.</span></span>
<span data-ttu-id="5d0c9-143">の**Component**パラメーターで `Get-Help` は、この値を使用して、によって返される検索結果をフィルター処理し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-143">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="role"></a><span data-ttu-id="5d0c9-144">.果たす</span><span class="sxs-lookup"><span data-stu-id="5d0c9-144">.Role</span></span>

<span data-ttu-id="5d0c9-145">ヘルプトピックのユーザーロールの名前です。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-145">The name of the user role for the help topic.</span></span> <span data-ttu-id="5d0c9-146">の**Role**パラメーターで `Get-Help` は、この値を使用して、によって返される検索結果をフィルター処理し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-146">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="functionality"></a><span data-ttu-id="5d0c9-147">.機</span><span class="sxs-lookup"><span data-stu-id="5d0c9-147">.FUNCTIONALITY</span></span>

<span data-ttu-id="5d0c9-148">関数の使用目的を説明するキーワード。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-148">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="5d0c9-149">の**機能**パラメーターは、 `Get-Help` この値を使用して、によって返される検索結果をフィルター処理し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-149">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="forwardhelptargetname-command-name"></a><span data-ttu-id="5d0c9-150">.FORWARDHELPTARGETNAME\<Command-Name></span><span class="sxs-lookup"><span data-stu-id="5d0c9-150">.FORWARDHELPTARGETNAME \<Command-Name></span></span>

<span data-ttu-id="5d0c9-151">指定されたコマンドのヘルプトピックにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-151">Redirects to the Help topic for the specified command.</span></span> <span data-ttu-id="5d0c9-152">関数、スクリプト、コマンドレット、またはプロバイダーのヘルプトピックを含む、任意のヘルプトピックにユーザーをリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-152">You can redirect users to any Help topic, including Help topics for a function, script, cmdlet, or provider.</span></span>

## <a name="forwardhelpcategory-category"></a><span data-ttu-id="5d0c9-153">.FORWARDHELPCATEGORY\<Category></span><span class="sxs-lookup"><span data-stu-id="5d0c9-153">.FORWARDHELPCATEGORY \<Category></span></span>

<span data-ttu-id="5d0c9-154">の項目のヘルプカテゴリを指定し `.FORWARDHELPTARGETNAME` ます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-154">Specifies the Help category of the item in `.FORWARDHELPTARGETNAME`.</span></span> <span data-ttu-id="5d0c9-155">同じ名前のコマンドが存在する場合に競合を回避するには、このキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-155">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

<span data-ttu-id="5d0c9-156">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-156">Valid values are:</span></span>

- <span data-ttu-id="5d0c9-157">エイリアス</span><span class="sxs-lookup"><span data-stu-id="5d0c9-157">Alias</span></span>
- <span data-ttu-id="5d0c9-158">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5d0c9-158">Cmdlet</span></span>
- <span data-ttu-id="5d0c9-159">HelpFile</span><span class="sxs-lookup"><span data-stu-id="5d0c9-159">HelpFile</span></span>
- <span data-ttu-id="5d0c9-160">関数</span><span class="sxs-lookup"><span data-stu-id="5d0c9-160">Function</span></span>
- <span data-ttu-id="5d0c9-161">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="5d0c9-161">Provider</span></span>
- <span data-ttu-id="5d0c9-162">全般</span><span class="sxs-lookup"><span data-stu-id="5d0c9-162">General</span></span>
- <span data-ttu-id="5d0c9-163">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="5d0c9-163">FAQ</span></span>
- <span data-ttu-id="5d0c9-164">用語集</span><span class="sxs-lookup"><span data-stu-id="5d0c9-164">Glossary</span></span>
- <span data-ttu-id="5d0c9-165">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="5d0c9-165">ScriptCommand</span></span>
- <span data-ttu-id="5d0c9-166">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="5d0c9-166">ExternalScript</span></span>
- <span data-ttu-id="5d0c9-167">フィルター</span><span class="sxs-lookup"><span data-stu-id="5d0c9-167">Filter</span></span>
- <span data-ttu-id="5d0c9-168">All</span><span class="sxs-lookup"><span data-stu-id="5d0c9-168">All</span></span>

## <a name="remotehelprunspace-pssession-variable"></a><span data-ttu-id="5d0c9-169">.REMOTEHELPRUNSPACE 空間\<PSSession-variable></span><span class="sxs-lookup"><span data-stu-id="5d0c9-169">.REMOTEHELPRUNSPACE \<PSSession-variable></span></span>

<span data-ttu-id="5d0c9-170">ヘルプトピックを含むセッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-170">Specifies a session that contains the Help topic.</span></span> <span data-ttu-id="5d0c9-171">PSSession を含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-171">Enter a variable that contains a PSSession.</span></span> <span data-ttu-id="5d0c9-172">このキーワードは、エクスポートされ `Export-PSSession` たコマンドのヘルプトピックを検索するために、コマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-172">This keyword is used by the `Export-PSSession` cmdlet to find the Help topics for the exported commands.</span></span>

## <a name="externalhelp-xml-help-file"></a><span data-ttu-id="5d0c9-173">..EXTERNALHELP\<XML Help File></span><span class="sxs-lookup"><span data-stu-id="5d0c9-173">.EXTERNALHELP \<XML Help File></span></span>

<span data-ttu-id="5d0c9-174">スクリプトまたは関数の XML ベースのヘルプファイルのパスと名前の両方またはいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-174">Specifies the path and/or name of an XML-based Help file for the script or function.</span></span>

<span data-ttu-id="5d0c9-175">キーワードは、 `.EXTERNALHELP` XML ベースのファイル内のスクリプトまたは関数のヘルプを取得するように[、コマンド](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand)レットに指示します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-175">The `.EXTERNALHELP` keyword tells the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet to get help for the script or function in an XML-based file.</span></span> <span data-ttu-id="5d0c9-176">キーワードは、 `.EXTERNALHELP` スクリプトまたは関数に XML ベースのヘルプファイルを使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-176">The `.EXTERNALHELP` keyword is required when using an XML-based help file for a script or function.</span></span> <span data-ttu-id="5d0c9-177">使用しない場合、 `Get-Help` 関数またはスクリプトのヘルプファイルは検索されません。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-177">Without it, `Get-Help` will not find a help file for the function or script.</span></span>

<span data-ttu-id="5d0c9-178">キーワードは、 `.EXTERNALHELP` 他のすべてのコメントベースのヘルプキーワードよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-178">The `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span> <span data-ttu-id="5d0c9-179">が指定されている場合、 `.EXTERNALHELP` キーワードの値に一致するヘルプファイルが見つからない場合でも、このコマンドレット[では](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand)、コメントベースのヘルプは表示されません。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-179">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

<span data-ttu-id="5d0c9-180">関数がスクリプトモジュールによってエクスポートされる場合、の値は `.EXTERNALHELP` パスを含まないファイル名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-180">When the function is exported by a script module, the value of `.EXTERNALHELP` should be a filename without a path.</span></span> <span data-ttu-id="5d0c9-181">`Get-Help`は、モジュールディレクトリのロケール固有のサブディレクトリでファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-181">`Get-Help` looks for the file in a locale-specific subdirectory of the module directory.</span></span> <span data-ttu-id="5d0c9-182">ファイル名には要件はありませんが、ファイル名の形式としてを使用することをお勧め `<ScriptModule>.psm1-help.xml` します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-182">There are no requirements for the filename, but a best practice is to use the following filename format: `<ScriptModule>.psm1-help.xml`.</span></span>

<span data-ttu-id="5d0c9-183">関数がモジュールに関連付けられていない場合は、キーワードの値にパスとファイル名を含め `.EXTERNALHELP` ます。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-183">When the function is not associated with a module, include a path and filename in the value of the `.EXTERNALHELP` keyword.</span></span> <span data-ttu-id="5d0c9-184">XML ファイルへの指定したパスに UI カルチャ固有のサブディレクトリが含まれている場合、は、 `Get-Help` すべての xml ベースのヘルプトピックと同様に、Windows 用に設定された言語フォールバック標準に従って、スクリプトまたは関数の名前を持つ xml ファイルを再帰的に検索します。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-184">If the specified path to the XML file contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does for all XML-based Help topics.</span></span>

<span data-ttu-id="5d0c9-185">コマンドレットヘルプの XML ベースのヘルプファイル形式の詳細については、「 [Windows PowerShell コマンドレットヘルプの記述](./writing-help-for-windows-powershell-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d0c9-185">For more information about the cmdlet Help XML-based Help file format, see [Writing Windows PowerShell Cmdlet Help](./writing-help-for-windows-powershell-cmdlets.md).</span></span>

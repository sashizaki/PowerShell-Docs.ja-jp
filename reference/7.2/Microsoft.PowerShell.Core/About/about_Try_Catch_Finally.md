---
description: 、、およびブロックを使用して、終了エラーを処理する方法について説明し `Try` `Catch` `Finally` ます。
Locale: en-US
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_try_catch_finally?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Try_Catch_Finally
ms.openlocfilehash: c93fa69e3badd7777950a850dfe81b79f9197f68
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602000"
---
# <a name="about-try-catch-finally"></a><span data-ttu-id="d9f46-103">Try Catch Finally について</span><span class="sxs-lookup"><span data-stu-id="d9f46-103">About Try Catch Finally</span></span>

## <a name="short-description"></a><span data-ttu-id="d9f46-104">概要</span><span class="sxs-lookup"><span data-stu-id="d9f46-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="d9f46-105">、、およびブロックを使用して、終了エラーを処理する方法について説明し `Try` `Catch` `Finally` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-105">Describes how to use the `Try`, `Catch`, and `Finally` blocks to handle terminating errors.</span></span>

## <a name="long-description"></a><span data-ttu-id="d9f46-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="d9f46-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="d9f46-107">`Try`、 `Catch` 、およびブロックを使用して、 `Finally` スクリプトの終了エラーに応答したり、終了エラーを処理したりします。</span><span class="sxs-lookup"><span data-stu-id="d9f46-107">Use `Try`, `Catch`, and `Finally` blocks to respond to or handle terminating errors in scripts.</span></span> <span data-ttu-id="d9f46-108">ステートメントを使用して、 `Trap` スクリプトの終了エラーを処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-108">The `Trap` statement can also be used to handle terminating errors in scripts.</span></span> <span data-ttu-id="d9f46-109">詳細については、「 [about_Trap](about_Trap.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9f46-109">For more information, see [about_Trap](about_Trap.md).</span></span>

<span data-ttu-id="d9f46-110">終了エラーにより、ステートメントの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-110">A terminating error stops a statement from running.</span></span> <span data-ttu-id="d9f46-111">PowerShell が何らかの方法で終了エラーを処理しない場合、PowerShell は、現在のパイプラインを使用した関数またはスクリプトの実行も停止します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-111">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script using the current pipeline.</span></span> <span data-ttu-id="d9f46-112">C などの他の言語では、 \# 終了エラーは例外と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-112">In other languages, such as C\#, terminating errors are referred to as exceptions.</span></span>

<span data-ttu-id="d9f46-113">ブロックを使用して、 `Try` PowerShell でエラーを監視するスクリプトのセクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-113">Use the `Try` block to define a section of a script in which you want PowerShell to monitor for errors.</span></span> <span data-ttu-id="d9f46-114">ブロック内でエラーが発生すると、 `Try` エラーが最初に自動変数に保存され `$Error` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-114">When an error occurs within the `Try` block, the error is first saved to the `$Error` automatic variable.</span></span> <span data-ttu-id="d9f46-115">次に、PowerShell は、 `Catch` エラーを処理するブロックを検索します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-115">PowerShell then searches for a `Catch` block to handle the error.</span></span> <span data-ttu-id="d9f46-116">ステートメントに `Try` 一致するブロックがない場合 `Catch` 、PowerShell は引き続き、 `Catch` 親スコープ内の適切なブロックまたはステートメントを検索し `Trap` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-116">If the `Try` statement does not have a matching `Catch` block, PowerShell continues to search for an appropriate `Catch` block or `Trap` statement in the parent scopes.</span></span> <span data-ttu-id="d9f46-117">`Catch`ブロックが完了するか、適切な `Catch` ブロックまたは `Trap` ステートメントが見つからない場合は、 `Finally` ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-117">After a `Catch` block is completed or if no appropriate `Catch` block or `Trap` statement is found, the `Finally` block is run.</span></span> <span data-ttu-id="d9f46-118">エラーを処理できない場合は、エラーストリームにエラーが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-118">If the error cannot be handled, the error is written to the error stream.</span></span>

<span data-ttu-id="d9f46-119">ブロックには `Catch` 、エラーを追跡するコマンドや、想定されるスクリプトのフローを回復するためのコマンドを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-119">A `Catch` block can include commands for tracking the error or for recovering the expected flow of the script.</span></span> <span data-ttu-id="d9f46-120">ブロックは、 `Catch` キャッチするエラーの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-120">A `Catch` block can specify which error types it catches.</span></span> <span data-ttu-id="d9f46-121">ステートメントには、 `Try` `Catch` さまざまな種類のエラーに対応する複数のブロックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-121">A `Try` statement can include multiple `Catch` blocks for different kinds of errors.</span></span>

<span data-ttu-id="d9f46-122">ブロックは、スクリプトで不要になっ `Finally` たリソースを解放するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-122">A `Finally` block can be used to free any resources that are no longer needed by your script.</span></span>

<span data-ttu-id="d9f46-123">`Try`、、およびは、 `Catch` `Finally` `Try` `Catch` `Finally` C プログラミング言語で使用される、、およびの各キーワードに似て \# います。</span><span class="sxs-lookup"><span data-stu-id="d9f46-123">`Try`, `Catch`, and `Finally` resemble the `Try`, `Catch`, and `Finally` keywords used in the C\# programming language.</span></span>

### <a name="syntax"></a><span data-ttu-id="d9f46-124">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d9f46-124">SYNTAX</span></span>

<span data-ttu-id="d9f46-125">ステートメントには、 `Try` `Try` ブロック、0個以上 `Catch` のブロック、および0個または1個のブロックが含まれてい `Finally` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-125">A `Try` statement contains a `Try` block, zero or more `Catch` blocks, and zero or one `Finally` block.</span></span> <span data-ttu-id="d9f46-126">`Try`ステートメントには、少なくとも1つの `Catch` ブロックまたは1つのブロックが必要 `Finally` です。</span><span class="sxs-lookup"><span data-stu-id="d9f46-126">A `Try` statement must have at least one `Catch` block or one `Finally` block.</span></span>

<span data-ttu-id="d9f46-127">ブロックの構文を次に示し `Try` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-127">The following shows the `Try` block syntax:</span></span>

```powershell
try {<statement list>}
```

<span data-ttu-id="d9f46-128">`Try`キーワードの後には、中かっこで囲まれたステートメントリストが続きます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-128">The `Try` keyword is followed by a statement list in braces.</span></span> <span data-ttu-id="d9f46-129">ステートメントリスト内のステートメントの実行中に終了エラーが発生した場合、スクリプトは `Try` ブロックから適切なブロックにエラーオブジェクトを渡し `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-129">If a terminating error occurs while the statements in the statement list are being run, the script passes the error object from the `Try` block to an appropriate `Catch` block.</span></span>

<span data-ttu-id="d9f46-130">ブロックの構文を次に示し `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-130">The following shows the `Catch` block syntax:</span></span>

```powershell
catch [[<error type>][',' <error type>]*] {<statement list>}
```

<span data-ttu-id="d9f46-131">エラーの種類は角かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="d9f46-131">Error types appear in brackets.</span></span> <span data-ttu-id="d9f46-132">最も外側の角かっこは、要素が省略可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-132">The outermost brackets indicate the element is optional.</span></span>

<span data-ttu-id="d9f46-133">`Catch`キーワードの後に、オプションのエラーの種類の指定リストとステートメントリストが続きます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-133">The `Catch` keyword is followed by an optional list of error type specifications and a statement list.</span></span> <span data-ttu-id="d9f46-134">ブロックで終了エラーが発生した場合 `Try` 、PowerShell は適切なブロックを検索し `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-134">If a terminating error occurs in the `Try` block, PowerShell searches for an appropriate `Catch` block.</span></span> <span data-ttu-id="d9f46-135">見つかった場合は、ブロック内のステートメント `Catch` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-135">If one is found, the statements in the `Catch` block are executed.</span></span>

<span data-ttu-id="d9f46-136">`Catch`ブロックでは、1つまたは複数のエラーの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-136">The `Catch` block can specify one or more error types.</span></span> <span data-ttu-id="d9f46-137">エラーの種類は、Microsoft .NET Framework の例外、または .NET Framework の例外から派生した例外です。</span><span class="sxs-lookup"><span data-stu-id="d9f46-137">An error type is a Microsoft .NET Framework exception or an exception that is derived from a .NET Framework exception.</span></span> <span data-ttu-id="d9f46-138">ブロックは、 `Catch` 指定された .NET Framework exception クラス、または指定されたクラスから派生した任意のクラスのエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-138">A `Catch` block handles errors of the specified .NET Framework exception class or of any class that derives from the specified class.</span></span>

<span data-ttu-id="d9f46-139">ブロックで `Catch` エラーの種類が指定されている場合、その `Catch` ブロックはエラーの種類を処理します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-139">If a `Catch` block specifies an error type, that `Catch` block handles that type of error.</span></span> <span data-ttu-id="d9f46-140">`Catch`ブロックでエラーの種類が指定されていない場合、ブロック `Catch` で発生したエラーがブロックによって処理さ `Try` れます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-140">If a `Catch` block does not specify an error type, that `Catch` block handles any error encountered in the `Try` block.</span></span> <span data-ttu-id="d9f46-141">ステートメントには `Try` `Catch` 、指定されたさまざまなエラーの種類に対して複数のブロックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-141">A `Try` statement can include multiple `Catch` blocks for the different specified error types.</span></span>

<span data-ttu-id="d9f46-142">ブロックの構文を次に示し `Finally` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-142">The following shows the `Finally` block syntax:</span></span>

```powershell
finally {<statement list>}
```

<span data-ttu-id="d9f46-143">キーワードの後には、ステートメントがエラーなしで実行された `Finally` 場合 `Try` や、ステートメントでエラーがキャッチされた場合でも、スクリプトが実行されるたびに実行されるステートメントリストが続き `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-143">The `Finally` keyword is followed by a statement list that runs every time the script is run, even if the `Try` statement ran without error or an error was caught in a `Catch` statement.</span></span>

<span data-ttu-id="d9f46-144"><kbd>CTRL</kbd>C キーを押すと + <kbd></kbd> 、パイプラインが停止することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d9f46-144">Note that pressing <kbd>CTRL</kbd>+<kbd>C</kbd> stops the pipeline.</span></span> <span data-ttu-id="d9f46-145">パイプラインに送信されたオブジェクトは出力として表示されません。</span><span class="sxs-lookup"><span data-stu-id="d9f46-145">Objects that are sent to the pipeline will not be displayed as output.</span></span> <span data-ttu-id="d9f46-146">したがって、表示するステートメント ("Finally ブロックが実行されている" など) を含めると、ブロックが実行され<kbd></kbd>た + 場合でも、CTRL<kbd>C</kbd>キーを押しても表示されません `Finally` 。</span><span class="sxs-lookup"><span data-stu-id="d9f46-146">Therefore, if you include a statement to be displayed, such as "Finally block has run", it will not be displayed after you press <kbd>CTRL</kbd>+<kbd>C</kbd>, even if the `Finally` block ran.</span></span>

### <a name="catching-errors"></a><span data-ttu-id="d9f46-147">キャッチ (エラーを)</span><span class="sxs-lookup"><span data-stu-id="d9f46-147">CATCHING ERRORS</span></span>

<span data-ttu-id="d9f46-148">次のサンプルスクリプトは、ブロックを含むブロックを示してい `Try` `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-148">The following sample script shows a `Try` block with a `Catch` block:</span></span>

```powershell
try { NonsenseString }
catch { "An error occurred." }
```

<span data-ttu-id="d9f46-149">キーワードは、 `Catch` ブロックまたは別のブロックの直後にある必要があり `Try` `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-149">The `Catch` keyword must immediately follow the `Try` block or another `Catch` block.</span></span>

<span data-ttu-id="d9f46-150">PowerShell では、コマンドレットまたはその他の項目として "NonsenseString" は認識されません。</span><span class="sxs-lookup"><span data-stu-id="d9f46-150">PowerShell does not recognize "NonsenseString" as a cmdlet or other item.</span></span>
<span data-ttu-id="d9f46-151">このスクリプトを実行すると、次の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-151">Running this script returns the following result:</span></span>

```powershell
An error occurred.
```

<span data-ttu-id="d9f46-152">スクリプトが "NonsenseString" を検出すると、終了エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-152">When the script encounters "NonsenseString", it causes a terminating error.</span></span> <span data-ttu-id="d9f46-153">ブロックは、 `Catch` ブロック内のステートメントリストを実行してエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-153">The `Catch` block handles the error by running the statement list inside the block.</span></span>

### <a name="using-multiple-catch-statements"></a><span data-ttu-id="d9f46-154">複数の CATCH ステートメントの使用</span><span class="sxs-lookup"><span data-stu-id="d9f46-154">USING MULTIPLE CATCH STATEMENTS</span></span>

<span data-ttu-id="d9f46-155">ステートメントには `Try` 、任意の数のブロックを含めることができ `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-155">A `Try` statement can have any number of `Catch` blocks.</span></span> <span data-ttu-id="d9f46-156">たとえば、次のスクリプトにはを `Try` ダウンロードするブロックがあり、 `MyDoc.doc` 2 つのブロックが含まれてい `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-156">For example, the following script has a `Try` block that downloads `MyDoc.doc`, and it contains two `Catch` blocks:</span></span>

```powershell
try {
   $wc = new-object System.Net.WebClient
   $wc.DownloadFile("http://www.contoso.com/MyDoc.doc","c:\temp\MyDoc.doc")
}
catch [System.Net.WebException],[System.IO.IOException] {
    "Unable to download MyDoc.doc from http://www.contoso.com."
}
catch {
    "An error occurred that could not be resolved."
}

```

<span data-ttu-id="d9f46-157">最初の `Catch` ブロックは、 **WebException** 型と **IOException** 型のエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-157">The first `Catch` block handles errors of the **System.Net.WebException** and **System.IO.IOException** types.</span></span> <span data-ttu-id="d9f46-158">2番目の `Catch` ブロックでは、エラーの種類が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="d9f46-158">The second `Catch` block does not specify an error type.</span></span> <span data-ttu-id="d9f46-159">2つ目のブロックは、 `Catch` 発生した他のすべての終了エラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-159">The second `Catch` block handles any other terminating errors that occur.</span></span>

<span data-ttu-id="d9f46-160">PowerShell は、継承によってエラーの種類と一致します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-160">PowerShell matches error types by inheritance.</span></span> <span data-ttu-id="d9f46-161">ブロックは、 `Catch` 指定された .NET Framework exception クラス、または指定されたクラスから派生した任意のクラスのエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-161">A `Catch` block handles errors of the specified .NET Framework exception class or of any class that derives from the specified class.</span></span> <span data-ttu-id="d9f46-162">次の例には、 `Catch` "コマンドが見つかりません" というエラーをキャッチするブロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d9f46-162">The following example contains a `Catch` block that catches a "Command Not Found" error:</span></span>

```powershell
catch [System.Management.Automation.CommandNotFoundException]
{"Inherited Exception" }
```

<span data-ttu-id="d9f46-163">指定したエラーの種類 **CommandNotFoundException** は、 **System.Systemexception** 型から継承されます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-163">The specified error type, **CommandNotFoundException**, inherits from the **System.SystemException** type.</span></span> <span data-ttu-id="d9f46-164">次の例では、コマンドが見つからないというエラーもキャッチします。</span><span class="sxs-lookup"><span data-stu-id="d9f46-164">The following example also catches a Command Not Found error:</span></span>

```powershell
catch [System.SystemException] {"Base Exception" }
```

<span data-ttu-id="d9f46-165">この `Catch` ブロックは、"コマンドが見つかりません" エラーと、 **systemexception** 型から継承する他のエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-165">This `Catch` block handles the "Command Not Found" error and other errors that inherit from the **SystemException** type.</span></span>

<span data-ttu-id="d9f46-166">エラークラスとその派生クラスの1つを指定する場合は、 `Catch` 派生クラスのブロックを汎用クラスのブロックの前に配置し `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-166">If you specify an error class and one of its derived classes, place the `Catch` block for the derived class before the `Catch` block for the general class.</span></span>

### <a name="using-traps-in-a-try-catch"></a><span data-ttu-id="d9f46-167">Try Catch でのトラップの使用</span><span class="sxs-lookup"><span data-stu-id="d9f46-167">Using Traps in a Try Catch</span></span>

<span data-ttu-id="d9f46-168">ブロック内で定義されたを持つブロックで終了エラーが発生した場合 `Try` `Trap` `Try` 、一致するブロックがある場合でも、 `Catch` `Trap` ステートメントは制御を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d9f46-168">When a terminating error occurs in a `Try` block with a `Trap` defined within the `Try` block, even if there is a matching `Catch` block, the `Trap` statement takes control.</span></span>

<span data-ttu-id="d9f46-169">が `Trap` より大きいブロックに存在 `Try` し、現在のスコープ内に一致するブロックがない場合、 `Catch` `Trap` 親スコープに一致するブロックがある場合でも、は制御を受け取ります `Catch` 。</span><span class="sxs-lookup"><span data-stu-id="d9f46-169">If a `Trap` exists at a higher block than the `Try`, and there is no matching `Catch` block within the current scope, the `Trap` will take control, even if any parent scope has a matching `Catch` block.</span></span>

### <a name="accessing-exception-information"></a><span data-ttu-id="d9f46-170">例外情報へのアクセス</span><span class="sxs-lookup"><span data-stu-id="d9f46-170">ACCESSING EXCEPTION INFORMATION</span></span>

<span data-ttu-id="d9f46-171">ブロック内で `Catch` は、現在のエラーに `$_` はとも呼ばれるを使用してアクセスできます `$PSItem` 。</span><span class="sxs-lookup"><span data-stu-id="d9f46-171">Within a `Catch` block, the current error can be accessed using `$_`, which is also known as `$PSItem`.</span></span> <span data-ttu-id="d9f46-172">オブジェクトの型は **Errorrecord** です。</span><span class="sxs-lookup"><span data-stu-id="d9f46-172">The object is of type **ErrorRecord**.</span></span>

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_
}
```

<span data-ttu-id="d9f46-173">このスクリプトを実行すると、次の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-173">Running this script returns the following result:</span></span>

```Output
An Error occurred:
The term 'NonsenseString' is not recognized as the name of a cmdlet, function,
script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
```

<span data-ttu-id="d9f46-174">**ScriptStackTrace**、 **Exception**、 **errordetails** など、アクセスできるプロパティが追加されています。</span><span class="sxs-lookup"><span data-stu-id="d9f46-174">There are additional properties that can be accessed, such as **ScriptStackTrace**, **Exception**, and **ErrorDetails**.</span></span>  <span data-ttu-id="d9f46-175">たとえば、スクリプトを次のように変更したとします。</span><span class="sxs-lookup"><span data-stu-id="d9f46-175">For example, if we change the script to the following:</span></span>

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_.ScriptStackTrace
}
```

<span data-ttu-id="d9f46-176">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d9f46-176">The result will be similar to:</span></span>

```
An Error occurred:
at <ScriptBlock>, <No file>: line 2
```

### <a name="freeing-resources-by-using-finally"></a><span data-ttu-id="d9f46-177">FINALLY を使用したリソースの解放</span><span class="sxs-lookup"><span data-stu-id="d9f46-177">FREEING RESOURCES BY USING FINALLY</span></span>

<span data-ttu-id="d9f46-178">スクリプトで使用されるリソースを解放するには、 `Finally` ブロックとブロックの後にブロックを追加し `Try` `Catch` ます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-178">To free resources used by a script, add a `Finally` block after the `Try` and `Catch` blocks.</span></span> <span data-ttu-id="d9f46-179">ブロック `Finally` ステートメントは、 `Try` ブロックで終了エラーが発生したかどうかに関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-179">The `Finally` block statements run regardless of whether the `Try` block encounters a terminating error.</span></span> <span data-ttu-id="d9f46-180">PowerShell は、 `Finally` スクリプトが終了する前、または現在のブロックがスコープ外になる前に、ブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9f46-180">PowerShell runs the `Finally` block before the script terminates or before the current block goes out of scope.</span></span>

<span data-ttu-id="d9f46-181">`Finally` <kbd>CTRL</kbd>C を使用してスクリプトを停止した場合でも、ブロックは実行さ + <kbd></kbd>れます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-181">A `Finally` block runs even if you use <kbd>CTRL</kbd>+<kbd>C</kbd> to stop the script.</span></span> <span data-ttu-id="d9f46-182">ブロックは、 `Finally` Exit キーワードがブロック内からスクリプトを停止した場合にも実行さ `Catch` れます。</span><span class="sxs-lookup"><span data-stu-id="d9f46-182">A `Finally` block also runs if an Exit keyword stops the script from within a `Catch` block.</span></span>

### <a name="see-also"></a><span data-ttu-id="d9f46-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9f46-183">SEE ALSO</span></span>

[<span data-ttu-id="d9f46-184">about_Break</span><span class="sxs-lookup"><span data-stu-id="d9f46-184">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="d9f46-185">about_Continue</span><span class="sxs-lookup"><span data-stu-id="d9f46-185">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="d9f46-186">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="d9f46-186">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="d9f46-187">about_Throw</span><span class="sxs-lookup"><span data-stu-id="d9f46-187">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="d9f46-188">about_Trap</span><span class="sxs-lookup"><span data-stu-id="d9f46-188">about_Trap</span></span>](about_Trap.md)


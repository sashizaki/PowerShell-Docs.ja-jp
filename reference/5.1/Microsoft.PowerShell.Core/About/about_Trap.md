---
description: 終了エラーを処理するキーワードについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_trap?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Trap
ms.openlocfilehash: 9627c632769cb87e790cc421c09d1103b90acf1d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222472"
---
# <a name="about-trap"></a><span data-ttu-id="024cb-104">トラップについて</span><span class="sxs-lookup"><span data-stu-id="024cb-104">About Trap</span></span>

## <a name="short-description"></a><span data-ttu-id="024cb-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="024cb-105">Short description</span></span>

<span data-ttu-id="024cb-106">終了エラーを処理するキーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="024cb-106">Describes a keyword that handles a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="024cb-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="024cb-107">Long description</span></span>

<span data-ttu-id="024cb-108">終了エラーにより、ステートメントの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="024cb-108">A terminating error stops a statement from running.</span></span> <span data-ttu-id="024cb-109">PowerShell が何らかの方法で終了エラーを処理しない場合、PowerShell は現在のパイプラインでの関数またはスクリプトの実行も停止します。</span><span class="sxs-lookup"><span data-stu-id="024cb-109">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script in the current pipeline.</span></span> <span data-ttu-id="024cb-110">C# などの他の言語では、終了エラーは例外として知られています。</span><span class="sxs-lookup"><span data-stu-id="024cb-110">In other languages, such as C#, terminating errors are known as exceptions.</span></span>

<span data-ttu-id="024cb-111">キーワードは、 `trap` 終了エラーが発生したときに実行するステートメントのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="024cb-111">The `trap` keyword specifies a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="024cb-112">`trap` ステートメントは、次の方法で終了エラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="024cb-112">`trap` statements handle the terminating errors in the following ways:</span></span>

- <span data-ttu-id="024cb-113">ステートメントブロックを処理し、を `trap` 含むスクリプトまたは関数の実行を続行した後に、エラーを表示し `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-113">Display the error after processing the `trap` statement block and continuing execution of the script or function containing the `trap`.</span></span> <span data-ttu-id="024cb-114">これは既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="024cb-114">This is the default behavior.</span></span>

- <span data-ttu-id="024cb-115">ステートメントでを使用して、エラーを表示し、を含むスクリプトまたは関数の実行を中止し `trap` `break` `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-115">Display the error and abort execution of the script or function containing the `trap` using `break` in the `trap` statement.</span></span>

- <span data-ttu-id="024cb-116">エラーを無音にしますが、 `trap` ステートメントでを使用して、を含むスクリプトまたは関数の実行を続行し `continue` `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-116">Silence the error, but continue execution of the script or function containing the `trap` by using `continue` in the `trap` statement.</span></span>

<span data-ttu-id="024cb-117">のステートメントの一覧には、 `trap` 複数の条件または関数呼び出しを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="024cb-117">The statement list of the `trap` can include multiple conditions or function calls.</span></span> <span data-ttu-id="024cb-118">では、 `trap` ログやテスト条件を書き込んだり、別のプログラムを実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="024cb-118">A `trap` can write logs, test conditions, or even run another program.</span></span>

### <a name="syntax"></a><span data-ttu-id="024cb-119">構文</span><span class="sxs-lookup"><span data-stu-id="024cb-119">Syntax</span></span>

<span data-ttu-id="024cb-120">`trap` ステートメントの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="024cb-120">The `trap` statement has the following syntax:</span></span>

```powershell
trap [[<error type>]] {<statement list>}
```

<span data-ttu-id="024cb-121">ステートメントには、 `trap` 終了エラーが発生したときに実行するステートメントのリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="024cb-121">The `trap` statement includes a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="024cb-122">ステートメントは、 `trap` キーワード、 `trap` オプションで型式、およびエラーがトラップされたときに実行するステートメントのリストを含むステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-122">A `trap` statement consists of the `trap` keyword, optionally followed by a type expression, and the statement block containing the list of statements to run when an error is trapped.</span></span> <span data-ttu-id="024cb-123">型式は、キャッチするエラーの種類を指定し `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-123">The type expression refines the types of errors the `trap` catches.</span></span>

<span data-ttu-id="024cb-124">スクリプトまたはコマンドには、複数のステートメントを含めることができ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-124">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="024cb-125">`trap` ステートメントは、スクリプトまたはコマンド内の任意の場所に置くことができます。</span><span class="sxs-lookup"><span data-stu-id="024cb-125">`trap` statements can appear anywhere in the script or command.</span></span>

### <a name="trapping-all-terminating-errors"></a><span data-ttu-id="024cb-126">すべての終了エラーのトラップ</span><span class="sxs-lookup"><span data-stu-id="024cb-126">Trapping all terminating errors</span></span>

<span data-ttu-id="024cb-127">スクリプトまたはコマンドで別の方法で処理されない終了エラーが発生した場合、PowerShell は `trap` エラーを処理するステートメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="024cb-127">When a terminating error occurs that is not handled in another way in a script or command, PowerShell checks for a `trap` statement that handles the error.</span></span> <span data-ttu-id="024cb-128">`trap`ステートメントが存在する場合、PowerShell はステートメントでスクリプトまたはコマンドの実行を続行し `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-128">If a `trap` statement is present, PowerShell continues running the script or command in the `trap` statement.</span></span>

<span data-ttu-id="024cb-129">次の例は、非常に単純な `trap` ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="024cb-129">The following example is a very simple `trap` statement:</span></span>

```powershell
trap {"Error found."}
```

<span data-ttu-id="024cb-130">この `trap` ステートメントは、終了エラーをトラップします。</span><span class="sxs-lookup"><span data-stu-id="024cb-130">This `trap` statement traps any terminating error.</span></span>

<span data-ttu-id="024cb-131">次の例では、関数に、実行時エラーの原因となる文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="024cb-131">In the following example, the function includes a nonsense string that causes a runtime error.</span></span>

```powershell
function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="024cb-132">この関数を実行すると、次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-132">Running this function returns the following:</span></span>

```Output
Error found.
nonsenseString : The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:3 char:5
+     nonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (nonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="024cb-133">次の例には、 `trap` 自動変数を使用してエラーを表示するステートメントが含まれてい `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-133">The following example includes a `trap` statement that displays the error by using the `$_` automatic variable:</span></span>

```powershell
function TrapTest {
    trap {"Error found: $_"}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="024cb-134">このバージョンの関数を実行すると、次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-134">Running this version of the function returns the following:</span></span>

```Output
Error found: The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
nonsenseString : The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:3 char:5
+     nonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (nonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

> [!IMPORTANT]
> <span data-ttu-id="024cb-135">`trap` ステートメントは、特定のスコープ内の任意の場所で定義できますが、常にそのスコープ内のすべてのステートメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-135">`trap` statements may be defined anywhere within a given scope, but always apply to all statements in that scope.</span></span> <span data-ttu-id="024cb-136">実行時に、 `trap` ブロック内のステートメントは、他のステートメントが実行される前に定義されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-136">At runtime, `trap` statements in a block are defined before any other statements are executed.</span></span> <span data-ttu-id="024cb-137">JavaScript では、これは [hoisting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting)と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="024cb-137">In JavaScript, this is known as [hoisting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span></span> <span data-ttu-id="024cb-138">つまり、ステートメントは、 `trap` 定義された時点を超えて実行が進んでいない場合でも、そのブロック内のすべてのステートメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-138">This means that `trap` statements apply to all statements in that block even if execution has not advanced past the point at which they are defined.</span></span> <span data-ttu-id="024cb-139">たとえば、 `trap` スクリプトの末尾にを定義し、最初のステートメントでエラーをスローした場合でも、そのがトリガーさ `trap` れます。</span><span class="sxs-lookup"><span data-stu-id="024cb-139">For example, defining a `trap` at the end of a script and throwing an error in the first statement still triggers that `trap`.</span></span>

### <a name="trapping-specific-errors"></a><span data-ttu-id="024cb-140">特定のエラーのトラップ</span><span class="sxs-lookup"><span data-stu-id="024cb-140">Trapping specific errors</span></span>

<span data-ttu-id="024cb-141">スクリプトまたはコマンドには、複数のステートメントを含めることができ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-141">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="024cb-142">は、 `trap` 特定のエラーを処理するように定義できます。</span><span class="sxs-lookup"><span data-stu-id="024cb-142">A `trap` can be defined to handle specific errors.</span></span>

<span data-ttu-id="024cb-143">次の例は、 `trap` 特定のエラー **CommandNotFoundException** をトラップするステートメントです。</span><span class="sxs-lookup"><span data-stu-id="024cb-143">The following example is a `trap` statement that traps the specific error **CommandNotFoundException** :</span></span>

```powershell
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
```

<span data-ttu-id="024cb-144">関数またはスクリプトで、既知のコマンドと一致しない文字列が検出されると、この `trap` ステートメントは "command error トラップ" という文字列を表示します。</span><span class="sxs-lookup"><span data-stu-id="024cb-144">When a function or script encounters a string that does not match a known command, this `trap` statement displays the "Command error trapped" string.</span></span>
<span data-ttu-id="024cb-145">ステートメントの一覧を実行 `trap` すると、PowerShell によってエラーオブジェクトがエラーストリームに書き込まれ、スクリプトが続行されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-145">After running the `trap` statement list, PowerShell writes the error object to the error stream and then continues the script.</span></span>

<span data-ttu-id="024cb-146">PowerShell は .NET の例外の種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="024cb-146">PowerShell uses .NET exception types.</span></span> <span data-ttu-id="024cb-147">次の例では、 **system.exception** エラーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="024cb-147">The following example specifies the **System.Exception** error type:</span></span>

```powershell
trap [System.Exception] {"An error trapped"}
```

<span data-ttu-id="024cb-148">**CommandNotFoundException** エラーの種類は、 **system.exception** 型から継承されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-148">The **CommandNotFoundException** error type inherits from the **System.Exception** type.</span></span> <span data-ttu-id="024cb-149">このステートメントは、不明なコマンドによって作成されたエラーをトラップします。</span><span class="sxs-lookup"><span data-stu-id="024cb-149">This statement traps an error that is created by an unknown command.</span></span> <span data-ttu-id="024cb-150">また、他のエラーの種類をトラップします。</span><span class="sxs-lookup"><span data-stu-id="024cb-150">It also traps other error types.</span></span>

<span data-ttu-id="024cb-151">1つのスクリプトに複数のステートメントを含めることができ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-151">You can have more than one `trap` statement in a script.</span></span> <span data-ttu-id="024cb-152">各エラーの種類は、1つのステートメントでのみトラップでき `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-152">Each error type can be trapped by only one `trap` statement.</span></span> <span data-ttu-id="024cb-153">終了エラーが発生すると、PowerShell は、 `trap` 現在の実行スコープを開始位置として、最も限定的な一致を持つを検索します。</span><span class="sxs-lookup"><span data-stu-id="024cb-153">When a terminating error occurs, PowerShell searches for the `trap` with the most specific match, starting in the current scope of execution.</span></span>

<span data-ttu-id="024cb-154">次のスクリプトの例には、エラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="024cb-154">The following script example contains an error.</span></span> <span data-ttu-id="024cb-155">このスクリプトには、 `trap` 終了エラーをトラップする一般的なステートメントと、 `trap` **CommandNotFoundException** 型を指定する特定のステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="024cb-155">The script includes a general `trap` statement that traps any terminating error and a specific `trap` statement that specifies the **CommandNotFoundException** type.</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException] {
  "Command error trapped"
}
nonsenseString
```

<span data-ttu-id="024cb-156">このスクリプトを実行すると、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-156">Running this script produces the following result:</span></span>

```Output
Command error trapped
nonsenseString : The term 'nonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At C:\Temp\traptest.ps1:5 char:1
+ nonsenseString
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (nonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="024cb-157">PowerShell はコマンドレットまたはその他の項目として "nonsenseString" を認識しないため、 **CommandNotFoundException** エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-157">Because PowerShell does not recognize "nonsenseString" as a cmdlet or other item, it returns a **CommandNotFoundException** error.</span></span> <span data-ttu-id="024cb-158">この終了エラーは、特定のステートメントによってトラップされ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-158">This terminating error is trapped by the specific `trap` statement.</span></span>

<span data-ttu-id="024cb-159">次のスクリプトの例では、同じステートメントに別のエラーが含まれてい `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-159">The following script example contains the same `trap` statements with a different error:</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
1/$null
```

<span data-ttu-id="024cb-160">このスクリプトを実行すると、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-160">Running this script produces the following result:</span></span>

```Output
Attempted to divide by zero.
At C:\temp\traptest.ps1:4 char:1
+ 1/$null
+ ~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], RuntimeException
    + FullyQualifiedErrorId : RuntimeException
```

<span data-ttu-id="024cb-161">0で除算しようとしても、 **CommandNotFoundException** エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="024cb-161">The attempt to divide by zero does not create a **CommandNotFoundException** error.</span></span> <span data-ttu-id="024cb-162">代わりに、そのエラーは、終了エラーをトラップするもう1つのステートメントによってトラップされ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-162">Instead, that error is trapped by the other `trap` statement, which traps any terminating error.</span></span>

### <a name="trapping-errors-and-scope"></a><span data-ttu-id="024cb-163">エラーとスコープのトラップ</span><span class="sxs-lookup"><span data-stu-id="024cb-163">Trapping errors and scope</span></span>

<span data-ttu-id="024cb-164">ステートメントと同じスコープ内で終了エラーが発生した場合 `trap` 、PowerShell はによって定義されたステートメントの一覧を実行 `trap` します。</span><span class="sxs-lookup"><span data-stu-id="024cb-164">If a terminating error occurs in the same scope as the `trap` statement, PowerShell runs the list of statements defined by the `trap`.</span></span> <span data-ttu-id="024cb-165">実行は、エラーの後のステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-165">Execution continues at the statement after the error.</span></span> <span data-ttu-id="024cb-166">`trap`ステートメントがエラーとは別のスコープにある場合、ステートメントと同じスコープ内にある次のステートメントから実行が続行され `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-166">If the `trap` statement is in a different scope from the error, execution continues at the next statement that is in the same scope as the `trap` statement.</span></span>

<span data-ttu-id="024cb-167">たとえば、関数でエラーが発生し、 `trap` ステートメントが関数内にある場合、スクリプトは次のステートメントで続行されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-167">For example, if an error occurs in a function, and the `trap` statement is in the function, the script continues at the next statement.</span></span> <span data-ttu-id="024cb-168">次のスクリプトには、エラーとステートメントが含まれてい `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-168">The following script contains an error and a `trap` statement:</span></span>

```powershell
function function1 {
    trap { "An error: " }
    NonsenseString
    "function1 was completed"
}

function1
```

<span data-ttu-id="024cb-169">このスクリプトを実行すると、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-169">Running this script produces the following result:</span></span>

```Output
An error:
NonsenseString : The term 'NonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:3 char:5
+     NonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (NonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

function1 was completed
```

<span data-ttu-id="024cb-170">`trap`関数内のステートメントは、エラーをトラップします。</span><span class="sxs-lookup"><span data-stu-id="024cb-170">The `trap` statement in the function traps the error.</span></span> <span data-ttu-id="024cb-171">メッセージを表示すると、PowerShell によって関数の実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-171">After displaying the message, PowerShell resumes running the function.</span></span> <span data-ttu-id="024cb-172">が完了したことに注意 `Function1` してください。</span><span class="sxs-lookup"><span data-stu-id="024cb-172">Note that `Function1` was completed.</span></span>

<span data-ttu-id="024cb-173">これを次の例と比較します。この例では、同じエラーとステートメントが使用されてい `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-173">Compare this with the following example, which has the same error and `trap` statement.</span></span> <span data-ttu-id="024cb-174">この例では、 `trap` ステートメントが関数の外側にあります。</span><span class="sxs-lookup"><span data-stu-id="024cb-174">In this example, the `trap` statement occurs outside the function:</span></span>

```powershell
function function2 {
    NonsenseString
    "function2 was completed"
}

trap { "An error: " }

function2
```

<span data-ttu-id="024cb-175">関数を実行する `Function2` と、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-175">Running the `Function2` function produces the following result:</span></span>

```Output
An error:
NonsenseString : The term 'NonsenseString' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At C:\temp\traptest.ps1:2 char:5
+     NonsenseString
+     ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (NonsenseString:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="024cb-176">この例では、"function2 was completed" コマンドは実行されませんでした。</span><span class="sxs-lookup"><span data-stu-id="024cb-176">In this example, the "function2 was completed" command was not run.</span></span> <span data-ttu-id="024cb-177">どちらの例でも、関数内で終了エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="024cb-177">In both examples, the terminating error occurs within the function.</span></span> <span data-ttu-id="024cb-178">ただし、この例では、 `trap` ステートメントは関数の外にあります。</span><span class="sxs-lookup"><span data-stu-id="024cb-178">In this example, however, the `trap` statement is outside the function.</span></span> <span data-ttu-id="024cb-179">PowerShell は、ステートメントの実行後に関数に戻りません `trap` 。</span><span class="sxs-lookup"><span data-stu-id="024cb-179">PowerShell does not go back into the function after the `trap` statement runs.</span></span>

> [!CAUTION]
> <span data-ttu-id="024cb-180">同じエラー条件に対して複数のトラップが定義されている場合、最初に `trap` 定義された構文 (スコープ内で最も高いもの) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-180">When multiple traps are defined for the same error condition, the first `trap` defined lexically (highest in the scope) is used.</span></span>

<span data-ttu-id="024cb-181">次の例では、"そのよう `trap` な ops 1" を持つのみが実行されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-181">In the following example, only the `trap` with "whoops 1" is run.</span></span>

```powershell
Remove-Item -ErrorAction Stop ThisFileDoesNotExist
trap { "whoops 1"; continue }
trap { "whoops 2"; continue }
```

> [!IMPORTANT]
> <span data-ttu-id="024cb-182">トラップステートメントは、コンパイルされる場所にスコープが設定されています。</span><span class="sxs-lookup"><span data-stu-id="024cb-182">A Trap statement is scoped to where it compiles.</span></span> <span data-ttu-id="024cb-183">関数またはドットのソース化されたスクリプト内にステートメントがある場合 `trap` 、関数またはドットのソース化されたスクリプトが終了すると、内のすべての `trap` ステートメントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-183">If you have a `trap` statement inside a function or dot sourced script, when the function or dot sourced script exits, all `trap` statements inside are removed.</span></span>

### <a name="using-the-break-and-continue-keywords"></a><span data-ttu-id="024cb-184">Break および continue キーワードの使用</span><span class="sxs-lookup"><span data-stu-id="024cb-184">Using the break and continue keywords</span></span>

<span data-ttu-id="024cb-185">`break`ステートメントでキーワードとキーワードを使用すると、 `continue` `trap` 終了エラー後もスクリプトまたはコマンドを実行し続けるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="024cb-185">You can use the `break` and `continue` keywords in a `trap` statement to determine whether a script or command continues to run after a terminating error.</span></span>

<span data-ttu-id="024cb-186">ステートメントを `break` ステートメントリストに含めた場合 `trap` 、PowerShell は関数またはスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="024cb-186">If you include a `break` statement in a `trap` statement list, PowerShell stops the function or script.</span></span> <span data-ttu-id="024cb-187">次のサンプル関数では、ステートメントでキーワードを使用してい `break` `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-187">The following sample function uses the `break` keyword in a `trap` statement:</span></span>

```powershell
function break_example {
    trap {
        "Error trapped"
        break
    }
    1/$null
    "Function completed."
}

break_example
```

```Output
Error trapped
Attempted to divide by zero.
At line:6 char:5
+     1/$null
+     ~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : RuntimeException
```

<span data-ttu-id="024cb-188">ステートメントに `trap` キーワードが含まれているため、 `break` 関数は実行を続行せず、"関数は完了しました" 行は実行されません。</span><span class="sxs-lookup"><span data-stu-id="024cb-188">Because the `trap` statement included the `break` keyword, the function does not continue to run, and the "Function completed" line is not run.</span></span>

<span data-ttu-id="024cb-189">`continue`ステートメントにキーワードを含めると `trap` 、またはを使用しない場合と同様に、エラーの原因となったステートメントの後に PowerShell が再開され `break` `continue` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-189">If you include a `continue` keyword in a `trap` statement, PowerShell resumes after the statement that caused the error, just as it would without `break` or `continue`.</span></span> <span data-ttu-id="024cb-190">ただし、キーワードを使用すると、エラー `continue` ストリームにエラーが書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="024cb-190">With the `continue` keyword, however, PowerShell does not write an error to the error stream.</span></span>

<span data-ttu-id="024cb-191">次のサンプル関数では、ステートメントでキーワードを使用してい `continue` `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-191">The following sample function uses the `continue` keyword in a `trap` statement:</span></span>

```powershell
function continue_example {
    trap {
        "Error trapped"
        continue
    }
    1/$null
    "Function completed."
}

continue_example
```

```Output
Error trapped
Function completed.
```

<span data-ttu-id="024cb-192">関数は、エラーがトラップされ、"関数が完了しました" ステートメントが実行された後に再開されます。</span><span class="sxs-lookup"><span data-stu-id="024cb-192">The function resumes after the error is trapped, and the "Function completed" statement runs.</span></span> <span data-ttu-id="024cb-193">エラーストリームにはエラーが書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="024cb-193">No error is written to the error stream.</span></span>

## <a name="notes"></a><span data-ttu-id="024cb-194">メモ</span><span class="sxs-lookup"><span data-stu-id="024cb-194">Notes</span></span>

<span data-ttu-id="024cb-195">`trap` ステートメントを使用すると、スコープ内のすべての終了エラーを広範囲に処理することができます。</span><span class="sxs-lookup"><span data-stu-id="024cb-195">`trap` statements provide a simple way to broadly ensure all terminating errors within a scope are handled.</span></span> <span data-ttu-id="024cb-196">より詳細なエラー処理を行うには、 `try` / `catch` ステートメントを使用してトラップが定義されているブロックを使用し `catch` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-196">For more finer-grained error handling, use `try`/`catch` blocks where traps are defined using `catch` statements.</span></span> <span data-ttu-id="024cb-197">ステートメントは、 `catch` 関連付けられているステートメント内のコードにのみ適用され `try` ます。</span><span class="sxs-lookup"><span data-stu-id="024cb-197">The `catch` statements only apply to the code inside the associated `try` statement.</span></span> <span data-ttu-id="024cb-198">詳細については、「 [about_Try_Catch_Finally](about_Try_Catch_Finally.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="024cb-198">For more information, see [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="024cb-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="024cb-199">See also</span></span>

[<span data-ttu-id="024cb-200">about_Break</span><span class="sxs-lookup"><span data-stu-id="024cb-200">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="024cb-201">about_Continue</span><span class="sxs-lookup"><span data-stu-id="024cb-201">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="024cb-202">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="024cb-202">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="024cb-203">about_Throw</span><span class="sxs-lookup"><span data-stu-id="024cb-203">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="024cb-204">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="024cb-204">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

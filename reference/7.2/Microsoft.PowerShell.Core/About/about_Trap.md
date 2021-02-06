---
description: 終了エラーを処理するキーワードについて説明します。
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_trap?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Trap
ms.openlocfilehash: 30b03235cbc2338de3786e37416d1c1ce1d660e3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602186"
---
# <a name="about-trap"></a><span data-ttu-id="91f23-103">トラップについて</span><span class="sxs-lookup"><span data-stu-id="91f23-103">About Trap</span></span>

## <a name="short-description"></a><span data-ttu-id="91f23-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="91f23-104">Short description</span></span>

<span data-ttu-id="91f23-105">終了エラーを処理するキーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="91f23-105">Describes a keyword that handles a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="91f23-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="91f23-106">Long description</span></span>

<span data-ttu-id="91f23-107">終了エラーにより、ステートメントの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="91f23-107">A terminating error stops a statement from running.</span></span> <span data-ttu-id="91f23-108">PowerShell が何らかの方法で終了エラーを処理しない場合、PowerShell は現在のパイプラインでの関数またはスクリプトの実行も停止します。</span><span class="sxs-lookup"><span data-stu-id="91f23-108">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script in the current pipeline.</span></span> <span data-ttu-id="91f23-109">C# などの他の言語では、終了エラーは例外として知られています。</span><span class="sxs-lookup"><span data-stu-id="91f23-109">In other languages, such as C#, terminating errors are known as exceptions.</span></span>

<span data-ttu-id="91f23-110">キーワードは、 `trap` 終了エラーが発生したときに実行するステートメントのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="91f23-110">The `trap` keyword specifies a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="91f23-111">`trap` ステートメントは、次の方法で終了エラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="91f23-111">`trap` statements handle the terminating errors in the following ways:</span></span>

- <span data-ttu-id="91f23-112">ステートメントブロックを処理し、を `trap` 含むスクリプトまたは関数の実行を続行した後に、エラーを表示し `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-112">Display the error after processing the `trap` statement block and continuing execution of the script or function containing the `trap`.</span></span> <span data-ttu-id="91f23-113">これが既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="91f23-113">This is the default behavior.</span></span>

- <span data-ttu-id="91f23-114">ステートメントでを使用して、エラーを表示し、を含むスクリプトまたは関数の実行を中止し `trap` `break` `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-114">Display the error and abort execution of the script or function containing the `trap` using `break` in the `trap` statement.</span></span>

- <span data-ttu-id="91f23-115">エラーを無音にしますが、 `trap` ステートメントでを使用して、を含むスクリプトまたは関数の実行を続行し `continue` `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-115">Silence the error, but continue execution of the script or function containing the `trap` by using `continue` in the `trap` statement.</span></span>

<span data-ttu-id="91f23-116">のステートメントの一覧には、 `trap` 複数の条件または関数呼び出しを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="91f23-116">The statement list of the `trap` can include multiple conditions or function calls.</span></span> <span data-ttu-id="91f23-117">では、 `trap` ログやテスト条件を書き込んだり、別のプログラムを実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="91f23-117">A `trap` can write logs, test conditions, or even run another program.</span></span>

### <a name="syntax"></a><span data-ttu-id="91f23-118">構文</span><span class="sxs-lookup"><span data-stu-id="91f23-118">Syntax</span></span>

<span data-ttu-id="91f23-119">`trap` ステートメントの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="91f23-119">The `trap` statement has the following syntax:</span></span>

```powershell
trap [[<error type>]] {<statement list>}
```

<span data-ttu-id="91f23-120">ステートメントには、 `trap` 終了エラーが発生したときに実行するステートメントのリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91f23-120">The `trap` statement includes a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="91f23-121">ステートメントは、 `trap` キーワード、 `trap` オプションで型式、およびエラーがトラップされたときに実行するステートメントのリストを含むステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-121">A `trap` statement consists of the `trap` keyword, optionally followed by a type expression, and the statement block containing the list of statements to run when an error is trapped.</span></span> <span data-ttu-id="91f23-122">型式は、キャッチするエラーの種類を指定し `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-122">The type expression refines the types of errors the `trap` catches.</span></span>

<span data-ttu-id="91f23-123">スクリプトまたはコマンドには、複数のステートメントを含めることができ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-123">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="91f23-124">`trap` ステートメントは、スクリプトまたはコマンド内の任意の場所に置くことができます。</span><span class="sxs-lookup"><span data-stu-id="91f23-124">`trap` statements can appear anywhere in the script or command.</span></span>

### <a name="trapping-all-terminating-errors"></a><span data-ttu-id="91f23-125">すべての終了エラーのトラップ</span><span class="sxs-lookup"><span data-stu-id="91f23-125">Trapping all terminating errors</span></span>

<span data-ttu-id="91f23-126">スクリプトまたはコマンドで別の方法で処理されない終了エラーが発生した場合、PowerShell は `trap` エラーを処理するステートメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="91f23-126">When a terminating error occurs that is not handled in another way in a script or command, PowerShell checks for a `trap` statement that handles the error.</span></span> <span data-ttu-id="91f23-127">`trap`ステートメントが存在する場合、PowerShell はステートメントでスクリプトまたはコマンドの実行を続行し `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-127">If a `trap` statement is present, PowerShell continues running the script or command in the `trap` statement.</span></span>

<span data-ttu-id="91f23-128">次の例は、非常に単純な `trap` ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="91f23-128">The following example is a very simple `trap` statement:</span></span>

```powershell
trap {"Error found."}
```

<span data-ttu-id="91f23-129">この `trap` ステートメントは、終了エラーをトラップします。</span><span class="sxs-lookup"><span data-stu-id="91f23-129">This `trap` statement traps any terminating error.</span></span>

<span data-ttu-id="91f23-130">次の例では、関数に、実行時エラーの原因となる文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="91f23-130">In the following example, the function includes a nonsense string that causes a runtime error.</span></span>

```powershell
function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="91f23-131">この関数を実行すると、次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-131">Running this function returns the following:</span></span>

```Output
Error found.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="91f23-132">次の例には、 `trap` 自動変数を使用してエラーを表示するステートメントが含まれてい `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-132">The following example includes a `trap` statement that displays the error by using the `$_` automatic variable:</span></span>

```powershell
function TrapTest {
    trap {"Error found: $_"}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="91f23-133">このバージョンの関数を実行すると、次の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-133">Running this version of the function returns the following:</span></span>

```Output
Error found: The term 'nonsenseString' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the
name, or if a path was included, verify that the path is correct and try again.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

> [!IMPORTANT]
> <span data-ttu-id="91f23-134">`trap` ステートメントは、特定のスコープ内の任意の場所で定義できますが、常にそのスコープ内のすべてのステートメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-134">`trap` statements may be defined anywhere within a given scope, but always apply to all statements in that scope.</span></span> <span data-ttu-id="91f23-135">実行時に、 `trap` ブロック内のステートメントは、他のステートメントが実行される前に定義されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-135">At runtime, `trap` statements in a block are defined before any other statements are executed.</span></span> <span data-ttu-id="91f23-136">JavaScript では、これは [hoisting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting)と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="91f23-136">In JavaScript, this is known as [hoisting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span></span> <span data-ttu-id="91f23-137">つまり、ステートメントは、 `trap` 定義された時点を超えて実行が進んでいない場合でも、そのブロック内のすべてのステートメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-137">This means that `trap` statements apply to all statements in that block even if execution has not advanced past the point at which they are defined.</span></span> <span data-ttu-id="91f23-138">たとえば、 `trap` スクリプトの末尾にを定義し、最初のステートメントでエラーをスローした場合でも、そのがトリガーさ `trap` れます。</span><span class="sxs-lookup"><span data-stu-id="91f23-138">For example, defining a `trap` at the end of a script and throwing an error in the first statement still triggers that `trap`.</span></span>

### <a name="trapping-specific-errors"></a><span data-ttu-id="91f23-139">特定のエラーのトラップ</span><span class="sxs-lookup"><span data-stu-id="91f23-139">Trapping specific errors</span></span>

<span data-ttu-id="91f23-140">スクリプトまたはコマンドには、複数のステートメントを含めることができ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-140">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="91f23-141">は、 `trap` 特定のエラーを処理するように定義できます。</span><span class="sxs-lookup"><span data-stu-id="91f23-141">A `trap` can be defined to handle specific errors.</span></span>

<span data-ttu-id="91f23-142">次の例は、 `trap` 特定のエラー **CommandNotFoundException** をトラップするステートメントです。</span><span class="sxs-lookup"><span data-stu-id="91f23-142">The following example is a `trap` statement that traps the specific error **CommandNotFoundException**:</span></span>

```powershell
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
```

<span data-ttu-id="91f23-143">関数またはスクリプトで、既知のコマンドと一致しない文字列が検出されると、この `trap` ステートメントは "command error トラップ" という文字列を表示します。</span><span class="sxs-lookup"><span data-stu-id="91f23-143">When a function or script encounters a string that does not match a known command, this `trap` statement displays the "Command error trapped" string.</span></span>
<span data-ttu-id="91f23-144">ステートメントの一覧を実行 `trap` すると、PowerShell によってエラーオブジェクトがエラーストリームに書き込まれ、スクリプトが続行されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-144">After running the `trap` statement list, PowerShell writes the error object to the error stream and then continues the script.</span></span>

<span data-ttu-id="91f23-145">PowerShell は .NET の例外の種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="91f23-145">PowerShell uses .NET exception types.</span></span> <span data-ttu-id="91f23-146">次の例では、 **system.exception** エラーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="91f23-146">The following example specifies the **System.Exception** error type:</span></span>

```powershell
trap [System.Exception] {"An error trapped"}
```

<span data-ttu-id="91f23-147">**CommandNotFoundException** エラーの種類は、 **system.exception** 型から継承されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-147">The **CommandNotFoundException** error type inherits from the **System.Exception** type.</span></span> <span data-ttu-id="91f23-148">このステートメントは、不明なコマンドによって作成されたエラーをトラップします。</span><span class="sxs-lookup"><span data-stu-id="91f23-148">This statement traps an error that is created by an unknown command.</span></span> <span data-ttu-id="91f23-149">また、他のエラーの種類をトラップします。</span><span class="sxs-lookup"><span data-stu-id="91f23-149">It also traps other error types.</span></span>

<span data-ttu-id="91f23-150">1つのスクリプトに複数のステートメントを含めることができ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-150">You can have more than one `trap` statement in a script.</span></span> <span data-ttu-id="91f23-151">各エラーの種類は、1つのステートメントでのみトラップでき `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-151">Each error type can be trapped by only one `trap` statement.</span></span> <span data-ttu-id="91f23-152">終了エラーが発生すると、PowerShell は、 `trap` 現在の実行スコープを開始位置として、最も限定的な一致を持つを検索します。</span><span class="sxs-lookup"><span data-stu-id="91f23-152">When a terminating error occurs, PowerShell searches for the `trap` with the most specific match, starting in the current scope of execution.</span></span>

<span data-ttu-id="91f23-153">次のスクリプトの例には、エラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91f23-153">The following script example contains an error.</span></span> <span data-ttu-id="91f23-154">このスクリプトには、 `trap` 終了エラーをトラップする一般的なステートメントと、 `trap` **CommandNotFoundException** 型を指定する特定のステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91f23-154">The script includes a general `trap` statement that traps any terminating error and a specific `trap` statement that specifies the **CommandNotFoundException** type.</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException] {
  "Command error trapped"
}
nonsenseString
```

<span data-ttu-id="91f23-155">このスクリプトを実行すると、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-155">Running this script produces the following result:</span></span>

```Output
Command error trapped
nonsenseString:
Line |
   5 |  nonsenseString
     |  ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="91f23-156">PowerShell はコマンドレットまたはその他の項目として "nonsenseString" を認識しないため、 **CommandNotFoundException** エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-156">Because PowerShell does not recognize "nonsenseString" as a cmdlet or other item, it returns a **CommandNotFoundException** error.</span></span> <span data-ttu-id="91f23-157">この終了エラーは、特定のステートメントによってトラップされ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-157">This terminating error is trapped by the specific `trap` statement.</span></span>

<span data-ttu-id="91f23-158">次のスクリプトの例では、同じステートメントに別のエラーが含まれてい `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-158">The following script example contains the same `trap` statements with a different error:</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
1/$null
```

<span data-ttu-id="91f23-159">このスクリプトを実行すると、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-159">Running this script produces the following result:</span></span>

```Output
Other terminating error trapped
RuntimeException:
Line |
   4 |  1/$null
     |  ~~~~~~~
     | Attempted to divide by zero.
```

<span data-ttu-id="91f23-160">0で除算しようとしても、 **CommandNotFoundException** エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="91f23-160">The attempt to divide by zero does not create a **CommandNotFoundException** error.</span></span> <span data-ttu-id="91f23-161">代わりに、そのエラーは、終了エラーをトラップするもう1つのステートメントによってトラップされ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-161">Instead, that error is trapped by the other `trap` statement, which traps any terminating error.</span></span>

### <a name="trapping-errors-and-scope"></a><span data-ttu-id="91f23-162">エラーとスコープのトラップ</span><span class="sxs-lookup"><span data-stu-id="91f23-162">Trapping errors and scope</span></span>

<span data-ttu-id="91f23-163">ステートメントと同じスコープ内で終了エラーが発生した場合 `trap` 、PowerShell はによって定義されたステートメントの一覧を実行 `trap` します。</span><span class="sxs-lookup"><span data-stu-id="91f23-163">If a terminating error occurs in the same scope as the `trap` statement, PowerShell runs the list of statements defined by the `trap`.</span></span> <span data-ttu-id="91f23-164">実行は、エラーの後のステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-164">Execution continues at the statement after the error.</span></span> <span data-ttu-id="91f23-165">`trap`ステートメントがエラーとは別のスコープにある場合、ステートメントと同じスコープ内にある次のステートメントから実行が続行され `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-165">If the `trap` statement is in a different scope from the error, execution continues at the next statement that is in the same scope as the `trap` statement.</span></span>

<span data-ttu-id="91f23-166">たとえば、関数でエラーが発生し、 `trap` ステートメントが関数内にある場合、スクリプトは次のステートメントで続行されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-166">For example, if an error occurs in a function, and the `trap` statement is in the function, the script continues at the next statement.</span></span> <span data-ttu-id="91f23-167">次のスクリプトには、エラーとステートメントが含まれてい `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-167">The following script contains an error and a `trap` statement:</span></span>

```powershell
function function1 {
    trap { "An error: " }
    NonsenseString
    "function1 was completed"
}

function1
```

<span data-ttu-id="91f23-168">このスクリプトを実行すると、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-168">Running this script produces the following result:</span></span>

```Output
An error:
NonsenseString:
Line |
   3 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
function1 was completed
```

<span data-ttu-id="91f23-169">`trap`関数内のステートメントは、エラーをトラップします。</span><span class="sxs-lookup"><span data-stu-id="91f23-169">The `trap` statement in the function traps the error.</span></span> <span data-ttu-id="91f23-170">メッセージを表示すると、PowerShell によって関数の実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-170">After displaying the message, PowerShell resumes running the function.</span></span> <span data-ttu-id="91f23-171">が完了したことに注意 `Function1` してください。</span><span class="sxs-lookup"><span data-stu-id="91f23-171">Note that `Function1` was completed.</span></span>

<span data-ttu-id="91f23-172">これを次の例と比較します。この例では、同じエラーとステートメントが使用されてい `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-172">Compare this with the following example, which has the same error and `trap` statement.</span></span> <span data-ttu-id="91f23-173">この例では、 `trap` ステートメントが関数の外側にあります。</span><span class="sxs-lookup"><span data-stu-id="91f23-173">In this example, the `trap` statement occurs outside the function:</span></span>

```powershell
function function2 {
    NonsenseString
    "function2 was completed"
}

trap { "An error: " }

function2
```

<span data-ttu-id="91f23-174">関数を実行する `Function2` と、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-174">Running the `Function2` function produces the following result:</span></span>

```Output
An error:
NonsenseString:
Line |
   2 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="91f23-175">この例では、"function2 was completed" コマンドは実行されませんでした。</span><span class="sxs-lookup"><span data-stu-id="91f23-175">In this example, the "function2 was completed" command was not run.</span></span> <span data-ttu-id="91f23-176">どちらの例でも、関数内で終了エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="91f23-176">In both examples, the terminating error occurs within the function.</span></span> <span data-ttu-id="91f23-177">ただし、この例では、 `trap` ステートメントは関数の外にあります。</span><span class="sxs-lookup"><span data-stu-id="91f23-177">In this example, however, the `trap` statement is outside the function.</span></span> <span data-ttu-id="91f23-178">PowerShell は、ステートメントの実行後に関数に戻りません `trap` 。</span><span class="sxs-lookup"><span data-stu-id="91f23-178">PowerShell does not go back into the function after the `trap` statement runs.</span></span>

> [!CAUTION]
> <span data-ttu-id="91f23-179">同じエラー条件に対して複数のトラップが定義されている場合、最初に `trap` 定義された構文 (スコープ内で最も高いもの) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-179">When multiple traps are defined for the same error condition, the first `trap` defined lexically (highest in the scope) is used.</span></span>

<span data-ttu-id="91f23-180">次の例では、"そのよう `trap` な ops 1" を持つのみが実行されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-180">In the following example, only the `trap` with "whoops 1" is run.</span></span>

```powershell
Remove-Item -ErrorAction Stop ThisFileDoesNotExist
trap { "whoops 1"; continue }
trap { "whoops 2"; continue }
```

> [!IMPORTANT]
> <span data-ttu-id="91f23-181">トラップステートメントは、コンパイルされる場所にスコープが設定されています。</span><span class="sxs-lookup"><span data-stu-id="91f23-181">A Trap statement is scoped to where it compiles.</span></span> <span data-ttu-id="91f23-182">関数またはドットのソース化されたスクリプト内にステートメントがある場合 `trap` 、関数またはドットのソース化されたスクリプトが終了すると、内のすべての `trap` ステートメントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-182">If you have a `trap` statement inside a function or dot sourced script, when the function or dot sourced script exits, all `trap` statements inside are removed.</span></span>

### <a name="using-the-break-and-continue-keywords"></a><span data-ttu-id="91f23-183">Break および continue キーワードの使用</span><span class="sxs-lookup"><span data-stu-id="91f23-183">Using the break and continue keywords</span></span>

<span data-ttu-id="91f23-184">`break`ステートメントでキーワードとキーワードを使用すると、 `continue` `trap` 終了エラー後もスクリプトまたはコマンドを実行し続けるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="91f23-184">You can use the `break` and `continue` keywords in a `trap` statement to determine whether a script or command continues to run after a terminating error.</span></span>

<span data-ttu-id="91f23-185">ステートメントを `break` ステートメントリストに含めた場合 `trap` 、PowerShell は関数またはスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="91f23-185">If you include a `break` statement in a `trap` statement list, PowerShell stops the function or script.</span></span> <span data-ttu-id="91f23-186">次のサンプル関数では、ステートメントでキーワードを使用してい `break` `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-186">The following sample function uses the `break` keyword in a `trap` statement:</span></span>

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
ParentContainsErrorRecordException:
Line |
   6 |      1/$null
     |      ~~~~~~~
     | Attempted to divide by zero.
```

<span data-ttu-id="91f23-187">ステートメントに `trap` キーワードが含まれているため、 `break` 関数は実行を続行せず、"関数は完了しました" 行は実行されません。</span><span class="sxs-lookup"><span data-stu-id="91f23-187">Because the `trap` statement included the `break` keyword, the function does not continue to run, and the "Function completed" line is not run.</span></span>

<span data-ttu-id="91f23-188">`continue`ステートメントにキーワードを含めると `trap` 、またはを使用しない場合と同様に、エラーの原因となったステートメントの後に PowerShell が再開され `break` `continue` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-188">If you include a `continue` keyword in a `trap` statement, PowerShell resumes after the statement that caused the error, just as it would without `break` or `continue`.</span></span> <span data-ttu-id="91f23-189">ただし、キーワードを使用すると、エラー `continue` ストリームにエラーが書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="91f23-189">With the `continue` keyword, however, PowerShell does not write an error to the error stream.</span></span>

<span data-ttu-id="91f23-190">次のサンプル関数では、ステートメントでキーワードを使用してい `continue` `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-190">The following sample function uses the `continue` keyword in a `trap` statement:</span></span>

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

<span data-ttu-id="91f23-191">関数は、エラーがトラップされ、"関数が完了しました" ステートメントが実行された後に再開されます。</span><span class="sxs-lookup"><span data-stu-id="91f23-191">The function resumes after the error is trapped, and the "Function completed" statement runs.</span></span> <span data-ttu-id="91f23-192">エラーストリームにはエラーが書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="91f23-192">No error is written to the error stream.</span></span>

## <a name="notes"></a><span data-ttu-id="91f23-193">メモ</span><span class="sxs-lookup"><span data-stu-id="91f23-193">Notes</span></span>

<span data-ttu-id="91f23-194">`trap` ステートメントを使用すると、スコープ内のすべての終了エラーを広範囲に処理することができます。</span><span class="sxs-lookup"><span data-stu-id="91f23-194">`trap` statements provide a simple way to broadly ensure all terminating errors within a scope are handled.</span></span> <span data-ttu-id="91f23-195">より詳細なエラー処理を行うには、 `try` / `catch` ステートメントを使用してトラップが定義されているブロックを使用し `catch` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-195">For more finer-grained error handling, use `try`/`catch` blocks where traps are defined using `catch` statements.</span></span> <span data-ttu-id="91f23-196">ステートメントは、 `catch` 関連付けられているステートメント内のコードにのみ適用され `try` ます。</span><span class="sxs-lookup"><span data-stu-id="91f23-196">The `catch` statements only apply to the code inside the associated `try` statement.</span></span> <span data-ttu-id="91f23-197">詳細については、「 [about_Try_Catch_Finally](about_Try_Catch_Finally.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91f23-197">For more information, see [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="91f23-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="91f23-198">See also</span></span>

[<span data-ttu-id="91f23-199">about_Break</span><span class="sxs-lookup"><span data-stu-id="91f23-199">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="91f23-200">about_Continue</span><span class="sxs-lookup"><span data-stu-id="91f23-200">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="91f23-201">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="91f23-201">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="91f23-202">about_Throw</span><span class="sxs-lookup"><span data-stu-id="91f23-202">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="91f23-203">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="91f23-203">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

---
description: 終了エラーを生成する Throw キーワードについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: dce019e9dc77d24843f254f978224cf5820d31aa
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221104"
---
# <a name="about-throw"></a><span data-ttu-id="d0e24-104">Throw の概要</span><span class="sxs-lookup"><span data-stu-id="d0e24-104">About Throw</span></span>

## <a name="short-description"></a><span data-ttu-id="d0e24-105">概要</span><span class="sxs-lookup"><span data-stu-id="d0e24-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="d0e24-106">終了エラーを生成する Throw キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d0e24-106">Describes the Throw keyword, which generates a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="d0e24-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="d0e24-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="d0e24-108">Throw キーワードを使うと、終了エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d0e24-108">The Throw keyword causes a terminating error.</span></span> <span data-ttu-id="d0e24-109">Throw キーワードを使用すると、コマンド、関数、またはスクリプトの処理を停止できます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-109">You can use the Throw keyword to stop the processing of a command, function, or script.</span></span>

<span data-ttu-id="d0e24-110">たとえば、If ステートメントのスクリプトブロックで Throw キーワードを使用して、条件に応答したり、try-catch ステートメントの Catch ブロックで Throw キーワードを使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-110">For example, you can use the Throw keyword in the script block of an If statement to respond to a condition or in the Catch block of a Try-Catch-Finally statement.</span></span> <span data-ttu-id="d0e24-111">また、パラメーター宣言で Throw キーワードを使用して、関数パラメーターを必須にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-111">You can also use the Throw keyword in a parameter declaration to make a function parameter mandatory.</span></span>

<span data-ttu-id="d0e24-112">Throw キーワードを使用すると、ユーザーメッセージ文字列や、エラーの原因となったオブジェクトなど、任意のオブジェクトをスローできます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-112">The Throw keyword can throw any object, such as a user message string or the object that caused the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0e24-113">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d0e24-113">SYNTAX</span></span>

<span data-ttu-id="d0e24-114">Throw キーワードの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d0e24-114">The syntax of the Throw keyword is as follows:</span></span>

```powershell
throw [<expression>]
```

<span data-ttu-id="d0e24-115">Throw 構文の式は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d0e24-115">The expression in the Throw syntax is optional.</span></span> <span data-ttu-id="d0e24-116">Throw ステートメントが Catch ブロックに出現せず、式も含まれていない場合、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-116">When the Throw statement does not appear in a Catch block, and it does not include an expression, it generates a ScriptHalted error.</span></span>

```powershell
C:\PS> throw

ScriptHalted
At line:1 char:6
+ throw <<<<
+ CategoryInfo          : OperationStopped: (:) [], RuntimeException
+ FullyQualifiedErrorId : ScriptHalted
```

<span data-ttu-id="d0e24-117">Throw キーワードが式のない Catch ブロックで使用されている場合は、現在の RuntimeException を再度スローします。</span><span class="sxs-lookup"><span data-stu-id="d0e24-117">If the Throw keyword is used in a Catch block without an expression, it throws the current RuntimeException again.</span></span> <span data-ttu-id="d0e24-118">詳細については、「about_Try_Catch_Finally」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0e24-118">For more information, see about_Try_Catch_Finally.</span></span>

## <a name="throwing-a-string"></a><span data-ttu-id="d0e24-119">文字列をスローする</span><span class="sxs-lookup"><span data-stu-id="d0e24-119">THROWING A STRING</span></span>

<span data-ttu-id="d0e24-120">Throw ステートメント内の省略可能な式は、次の例に示すように文字列にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-120">The optional expression in a Throw statement can be a string, as shown in the following example:</span></span>

```powershell
C:\PS> throw "This is an error."

This is an error.
At line:1 char:6
+ throw <<<<  "This is an error."
+ CategoryInfo          : OperationStopped: (This is an error.:String) [], R
untimeException
+ FullyQualifiedErrorId : This is an error.
```

## <a name="throwing-other-objects"></a><span data-ttu-id="d0e24-121">他のオブジェクトのスロー</span><span class="sxs-lookup"><span data-stu-id="d0e24-121">THROWING OTHER OBJECTS</span></span>

<span data-ttu-id="d0e24-122">式は、次の例に示すように、PowerShell プロセスを表すオブジェクトをスローするオブジェクトにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-122">The expression can also be an object that throws the object that represents the PowerShell process, as shown in the following example:</span></span>

```powershell
C:\PS> throw (get-process PowerShell)

System.Diagnostics.Process (PowerShell)
At line:1 char:6
+ throw <<<<  (get-process PowerShell)
+ CategoryInfo          : OperationStopped: (System.Diagnostics.Process (Pow
erShell):Process) [],
RuntimeException
+ FullyQualifiedErrorId : System.Diagnostics.Process (PowerShell)
```

<span data-ttu-id="d0e24-123">$Error 自動変数の ErrorRecord オブジェクトの TargetObject プロパティを使用して、エラーを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-123">You can use the TargetObject property of the ErrorRecord object in the $error automatic variable to examine the error.</span></span>

```powershell
C:\PS> $error[0].targetobject

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
319      26    61016      70864   568     3.28   5548 PowerShell
```

<span data-ttu-id="d0e24-124">ErrorRecord オブジェクトまたは Microsoft .NET Framework 例外をスローすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-124">You can also throw an ErrorRecord object or a Microsoft .NET Framework exception.</span></span> <span data-ttu-id="d0e24-125">Throw キーワードを使用して FormatException オブジェクトをスローする例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d0e24-125">The following example uses the Throw keyword to throw a System.FormatException object.</span></span>

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

One of the identified items was in an invalid format.
At line:1 char:6
+ throw <<<<  $formatError
+ CategoryInfo          : OperationStopped: (:) [], FormatException
+ FullyQualifiedErrorId : One of the identified items was in an invalid
format.
```

## <a name="resulting-error"></a><span data-ttu-id="d0e24-126">結果のエラー</span><span class="sxs-lookup"><span data-stu-id="d0e24-126">RESULTING ERROR</span></span>

<span data-ttu-id="d0e24-127">Throw キーワードを使用すると、ErrorRecord オブジェクトを生成できます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-127">The Throw keyword can generate an ErrorRecord object.</span></span> <span data-ttu-id="d0e24-128">ErrorRecord オブジェクトの Exception プロパティには、RuntimeException オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d0e24-128">The Exception property of the ErrorRecord object contains a RuntimeException object.</span></span> <span data-ttu-id="d0e24-129">ErrorRecord オブジェクトと RuntimeException オブジェクトの残りの部分は、Throw キーワードによってスローされるオブジェクトによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d0e24-129">The remainder of the ErrorRecord object and the RuntimeException object vary with the object that the Throw keyword throws.</span></span>

<span data-ttu-id="d0e24-130">RunTimeException オブジェクトは ErrorRecord オブジェクトにラップされ、ErrorRecord オブジェクトは $Error 自動変数に自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-130">The RunTimeException object is wrapped in an ErrorRecord object, and the ErrorRecord object is automatically saved in the $Error automatic variable.</span></span>

## <a name="using-throw-to-create-a-mandatory-parameter"></a><span data-ttu-id="d0e24-131">THROW を使用して必須パラメーターを作成する</span><span class="sxs-lookup"><span data-stu-id="d0e24-131">USING THROW TO CREATE A MANDATORY PARAMETER</span></span>

<span data-ttu-id="d0e24-132">Throw キーワードを使用すると、関数パラメーターを必須にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-132">You can use the Throw keyword to make a function parameter mandatory.</span></span>

<span data-ttu-id="d0e24-133">これは、Parameter キーワードの必須パラメーターを使用する代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="d0e24-133">This is an alternative to using the Mandatory parameter of the Parameter keyword.</span></span> <span data-ttu-id="d0e24-134">必須パラメーターを使用すると、ユーザーに対して必要なパラメーター値の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-134">When you use the Mandatory parameter, the system prompts the user for the required parameter value.</span></span> <span data-ttu-id="d0e24-135">Throw キーワードを使用すると、コマンドが停止し、エラーレコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0e24-135">When you use the Throw keyword, the command stops and displays the error record.</span></span>

<span data-ttu-id="d0e24-136">たとえば、parameter 部分式の Throw キーワードを使用すると、Path パラメーターが関数の必須パラメーターになります。</span><span class="sxs-lookup"><span data-stu-id="d0e24-136">For example, the Throw keyword in the parameter subexpression makes the Path parameter a required parameter in the function.</span></span>

<span data-ttu-id="d0e24-137">この場合、Throw キーワードはメッセージ文字列をスローしますが、Path パラメーターが指定されていない場合、終了エラーを生成する Throw キーワードが存在することになります。</span><span class="sxs-lookup"><span data-stu-id="d0e24-137">In this case, the Throw keyword throws a message string, but it is the presence of the Throw keyword that generates the terminating error if the Path parameter is not specified.</span></span> <span data-ttu-id="d0e24-138">Throw の後の式は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d0e24-138">The expression that follows Throw is optional.</span></span>

```powershell
function Get-XMLFiles
{
  param ($path = $(throw "The Path parameter is required."))
  dir -path $path\*.xml -recurse |
    sort lastwritetime |
      ft lastwritetime, attributes, name  -auto
}
```

## <a name="see-also"></a><span data-ttu-id="d0e24-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0e24-139">SEE ALSO</span></span>

[<span data-ttu-id="d0e24-140">about_Break</span><span class="sxs-lookup"><span data-stu-id="d0e24-140">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="d0e24-141">about_Continue</span><span class="sxs-lookup"><span data-stu-id="d0e24-141">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="d0e24-142">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="d0e24-142">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="d0e24-143">about_Trap</span><span class="sxs-lookup"><span data-stu-id="d0e24-143">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="d0e24-144">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="d0e24-144">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

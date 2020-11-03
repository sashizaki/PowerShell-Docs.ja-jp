---
description: 終了エラーを生成する Throw キーワードについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: d4bf0ea00145c03522d4db952be201c877c9d50c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220523"
---
# <a name="about-throw"></a><span data-ttu-id="15a65-104">Throw の概要</span><span class="sxs-lookup"><span data-stu-id="15a65-104">About Throw</span></span>

## <a name="short-description"></a><span data-ttu-id="15a65-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="15a65-105">Short description</span></span>
<span data-ttu-id="15a65-106">終了エラーを生成する Throw キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="15a65-106">Describes the Throw keyword, which generates a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="15a65-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="15a65-107">Long description</span></span>

<span data-ttu-id="15a65-108">Throw キーワードを使うと、終了エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="15a65-108">The Throw keyword causes a terminating error.</span></span> <span data-ttu-id="15a65-109">Throw キーワードを使用すると、コマンド、関数、またはスクリプトの処理を停止できます。</span><span class="sxs-lookup"><span data-stu-id="15a65-109">You can use the Throw keyword to stop the processing of a command, function, or script.</span></span>

<span data-ttu-id="15a65-110">たとえば、If ステートメントのスクリプトブロックで Throw キーワードを使用して、条件に応答したり、try-catch ステートメントの Catch ブロックで Throw キーワードを使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="15a65-110">For example, you can use the Throw keyword in the script block of an If statement to respond to a condition or in the Catch block of a Try-Catch-Finally statement.</span></span> <span data-ttu-id="15a65-111">また、パラメーター宣言で Throw キーワードを使用して、関数パラメーターを必須にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="15a65-111">You can also use the Throw keyword in a parameter declaration to make a function parameter mandatory.</span></span>

<span data-ttu-id="15a65-112">Throw キーワードを使用すると、ユーザーメッセージ文字列や、エラーの原因となったオブジェクトなど、任意のオブジェクトをスローできます。</span><span class="sxs-lookup"><span data-stu-id="15a65-112">The Throw keyword can throw any object, such as a user message string or the object that caused the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="15a65-113">構文</span><span class="sxs-lookup"><span data-stu-id="15a65-113">Syntax</span></span>

<span data-ttu-id="15a65-114">Throw キーワードの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15a65-114">The syntax of the Throw keyword is as follows:</span></span>

```powershell
throw [<expression>]
```

<span data-ttu-id="15a65-115">Throw 構文の式は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="15a65-115">The expression in the Throw syntax is optional.</span></span> <span data-ttu-id="15a65-116">Throw ステートメントが Catch ブロックに出現せず、式も含まれていない場合、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="15a65-116">When the Throw statement does not appear in a Catch block, and it does not include an expression, it generates a ScriptHalted error.</span></span>

```powershell
C:\PS> throw

Exception: ScriptHalted
```

<span data-ttu-id="15a65-117">Throw キーワードが式のない Catch ブロックで使用されている場合は、現在の RuntimeException を再度スローします。</span><span class="sxs-lookup"><span data-stu-id="15a65-117">If the Throw keyword is used in a Catch block without an expression, it throws the current RuntimeException again.</span></span> <span data-ttu-id="15a65-118">詳細については、「about_Try_Catch_Finally」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15a65-118">For more information, see about_Try_Catch_Finally.</span></span>

## <a name="throwing-a-string"></a><span data-ttu-id="15a65-119">文字列をスローする</span><span class="sxs-lookup"><span data-stu-id="15a65-119">Throwing a string</span></span>

<span data-ttu-id="15a65-120">Throw ステートメント内の省略可能な式は、次の例に示すように文字列にすることができます。</span><span class="sxs-lookup"><span data-stu-id="15a65-120">The optional expression in a Throw statement can be a string, as shown in the following example:</span></span>

```powershell
C:\PS> throw "This is an error."

Exception: This is an error.
```

## <a name="throwing-other-objects"></a><span data-ttu-id="15a65-121">他のオブジェクトのスロー</span><span class="sxs-lookup"><span data-stu-id="15a65-121">Throwing other objects</span></span>

<span data-ttu-id="15a65-122">式は、次の例に示すように、PowerShell プロセスを表すオブジェクトをスローするオブジェクトにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="15a65-122">The expression can also be an object that throws the object that represents the PowerShell process, as shown in the following example:</span></span>

```powershell
C:\PS> throw (get-process Pwsh)

Exception: System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh)
```

<span data-ttu-id="15a65-123">$Error 自動変数の ErrorRecord オブジェクトの TargetObject プロパティを使用して、エラーを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="15a65-123">You can use the TargetObject property of the ErrorRecord object in the $error automatic variable to examine the error.</span></span>

```powershell
C:\PS> $error[0].targetobject

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    125   174.44     229.57      23.61    1548   2 pwsh
     63    44.07      81.95       1.75    1732   2 pwsh
     63    43.32      77.65       1.48    9092   2 pwsh
```

<span data-ttu-id="15a65-124">ErrorRecord オブジェクトまたは .NET 例外をスローすることもできます。</span><span class="sxs-lookup"><span data-stu-id="15a65-124">You can also throw an ErrorRecord object or a .NET exception.</span></span> <span data-ttu-id="15a65-125">Throw キーワードを使用して FormatException オブジェクトをスローする例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="15a65-125">The following example uses the Throw keyword to throw a System.FormatException object.</span></span>

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

OperationStopped: One of the identified items was in an invalid format.
```

## <a name="the-resulting-error"></a><span data-ttu-id="15a65-126">生成されたエラー</span><span class="sxs-lookup"><span data-stu-id="15a65-126">The resulting error</span></span>

<span data-ttu-id="15a65-127">Throw キーワードを使用すると、ErrorRecord オブジェクトを生成できます。</span><span class="sxs-lookup"><span data-stu-id="15a65-127">The Throw keyword can generate an ErrorRecord object.</span></span> <span data-ttu-id="15a65-128">ErrorRecord オブジェクトの Exception プロパティには、RuntimeException オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="15a65-128">The Exception property of the ErrorRecord object contains a RuntimeException object.</span></span> <span data-ttu-id="15a65-129">ErrorRecord オブジェクトと RuntimeException オブジェクトの残りの部分は、Throw キーワードによってスローされるオブジェクトによって異なります。</span><span class="sxs-lookup"><span data-stu-id="15a65-129">The remainder of the ErrorRecord object and the RuntimeException object vary with the object that the Throw keyword throws.</span></span>

<span data-ttu-id="15a65-130">RunTimeException オブジェクトは ErrorRecord オブジェクトにラップされ、ErrorRecord オブジェクトは $Error 自動変数に自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="15a65-130">The RunTimeException object is wrapped in an ErrorRecord object, and the ErrorRecord object is automatically saved in the $Error automatic variable.</span></span>

## <a name="using-throw-to-create-a-mandatory-parameter"></a><span data-ttu-id="15a65-131">Throw を使用して必須パラメーターを作成する</span><span class="sxs-lookup"><span data-stu-id="15a65-131">Using Throw to create a mandatory parameter</span></span>

<span data-ttu-id="15a65-132">以前のバージョンの PowerShell とは異なり、パラメーターの検証に Throw キーワードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="15a65-132">Unlike past versions of PowerShell, do not use the Throw keyword for parameter validation.</span></span> <span data-ttu-id="15a65-133">正しい方法については [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15a65-133">See [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) for the correct way.</span></span>

## <a name="see-also"></a><span data-ttu-id="15a65-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="15a65-134">See also</span></span>

- [<span data-ttu-id="15a65-135">about_Break</span><span class="sxs-lookup"><span data-stu-id="15a65-135">about_Break</span></span>](about_Break.md)
- [<span data-ttu-id="15a65-136">about_Continue</span><span class="sxs-lookup"><span data-stu-id="15a65-136">about_Continue</span></span>](about_Continue.md)
- [<span data-ttu-id="15a65-137">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="15a65-137">about_Scopes</span></span>](about_Scopes.md)
- [<span data-ttu-id="15a65-138">about_Trap</span><span class="sxs-lookup"><span data-stu-id="15a65-138">about_Trap</span></span>](about_Trap.md)
- [<span data-ttu-id="15a65-139">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="15a65-139">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

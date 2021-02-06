---
description: 関数について説明 `Prompt` し、カスタム関数を作成する方法を示し `Prompt` ます。
Locale: en-US
ms.date: 04/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_prompts?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Prompts
ms.openlocfilehash: 3887df636c3ad486a4dbe72fffdc8acd92d2b3e9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599287"
---
# <a name="about-prompts"></a><span data-ttu-id="58c2c-103">プロンプトについて</span><span class="sxs-lookup"><span data-stu-id="58c2c-103">About Prompts</span></span>

## <a name="short-description"></a><span data-ttu-id="58c2c-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="58c2c-104">Short description</span></span>
<span data-ttu-id="58c2c-105">関数について説明 `Prompt` し、カスタム関数を作成する方法を示し `Prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-105">Describes the `Prompt` function and demonstrates how to create a custom `Prompt` function.</span></span>

## <a name="long-description"></a><span data-ttu-id="58c2c-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="58c2c-106">Long description</span></span>

<span data-ttu-id="58c2c-107">Powershell コマンドプロンプトで、PowerShell でコマンドを実行する準備ができたことが示されます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-107">The PowerShell command prompt indicates that PowerShell is ready to run a command:</span></span>

```
PS C:\>
```

<span data-ttu-id="58c2c-108">PowerShell プロンプトは、組み込み関数によって決定され `Prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-108">The PowerShell prompt is determined by the built-in `Prompt` function.</span></span> <span data-ttu-id="58c2c-109">独自の関数を作成 `Prompt` して PowerShell プロファイルに保存することで、プロンプトをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-109">You can customize the prompt by creating your own `Prompt` function and saving it in your PowerShell profile.</span></span>

## <a name="about-the-prompt-function"></a><span data-ttu-id="58c2c-110">Prompt 関数について</span><span class="sxs-lookup"><span data-stu-id="58c2c-110">About the Prompt function</span></span>

<span data-ttu-id="58c2c-111">関数は、 `Prompt` PowerShell プロンプトの外観を決定します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-111">The `Prompt` function determines the appearance of the PowerShell prompt.</span></span>
<span data-ttu-id="58c2c-112">PowerShell には組み込み関数が用意さ `Prompt` れていますが、独自の関数を定義することでオーバーライドでき `Prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-112">PowerShell comes with a built-in `Prompt` function, but you can override it by defining your own `Prompt` function.</span></span>

<span data-ttu-id="58c2c-113">`Prompt`関数の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="58c2c-113">The `Prompt` function has the following syntax:</span></span>

```powershell
function Prompt { <function-body> }
```

<span data-ttu-id="58c2c-114">関数は、 `Prompt` オブジェクトを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="58c2c-114">The `Prompt` function must return an object.</span></span> <span data-ttu-id="58c2c-115">文字列として書式設定された文字列またはオブジェクトを返すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58c2c-115">As a best practice, return a string or an object that is formatted as a string.</span></span> <span data-ttu-id="58c2c-116">推奨される最大長は80文字です。</span><span class="sxs-lookup"><span data-stu-id="58c2c-116">The maximum recommended length is 80 characters.</span></span>

<span data-ttu-id="58c2c-117">たとえば、次の関数は、 `Prompt` "Hello, World" という文字列と、その後に右山かっこ () を返し `>` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-117">For example, the following `Prompt` function returns a "Hello, World" string followed by a  right angle bracket (`>`).</span></span>

```powershell
PS C:\> function prompt {"Hello, World > "}
Hello, World >
```

### <a name="getting-the-prompt-function"></a><span data-ttu-id="58c2c-118">Prompt 関数を取得する</span><span class="sxs-lookup"><span data-stu-id="58c2c-118">Getting the Prompt function</span></span>

<span data-ttu-id="58c2c-119">関数を取得するに `Prompt` は、 `Get-Command` コマンドレットを使用するか、 `Get-Item` 関数ドライブのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-119">To get the `Prompt` function, use the `Get-Command` cmdlet or use the `Get-Item` cmdlet in the Function drive.</span></span>

<span data-ttu-id="58c2c-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-120">For example:</span></span>

```powershell
PS C:\> Get-Command Prompt

CommandType     Name      ModuleName
-----------     ----      ----------
Function        prompt
```

<span data-ttu-id="58c2c-121">プロンプトの値を設定するスクリプトを取得するには、ドットメソッドを使用して関数の **ScriptBlock** プロパティを取得し `Prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-121">To get the script that sets the value of the prompt, use the dot method to get the **ScriptBlock** property of the `Prompt` function.</span></span>

<span data-ttu-id="58c2c-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-122">For example:</span></span>

```powershell
(Get-Command Prompt).ScriptBlock
```

```Output
"PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) "
# .Link
# https://go.microsoft.com/fwlink/?LinkID=225750
# .ExternalHelp System.Management.Automation.dll-help.xml
```

<span data-ttu-id="58c2c-123">すべての関数と同様に、 `Prompt` 関数はドライブに格納され `Function:` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-123">Like all functions, the `Prompt` function is stored in the `Function:` drive.</span></span>
<span data-ttu-id="58c2c-124">現在の関数を作成するスクリプトを表示するには `Prompt` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-124">To display the script that creates the current `Prompt` function, type:</span></span>

```powershell
(Get-Item function:prompt).ScriptBlock
```

### <a name="the-default-prompt"></a><span data-ttu-id="58c2c-125">既定のプロンプト</span><span class="sxs-lookup"><span data-stu-id="58c2c-125">The default prompt</span></span>

<span data-ttu-id="58c2c-126">既定のプロンプトは、関数が `Prompt` エラーを生成した場合、またはオブジェクトを返さない場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-126">The default prompt appears only when the `Prompt` function generates an error or does not return an object.</span></span>

<span data-ttu-id="58c2c-127">既定の PowerShell プロンプトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="58c2c-127">The default PowerShell prompt is:</span></span>

```
PS>
```

<span data-ttu-id="58c2c-128">たとえば、次のコマンドは関数を `Prompt` に設定し `$null` ますが、これは無効です。</span><span class="sxs-lookup"><span data-stu-id="58c2c-128">For example, the following command sets the `Prompt` function to `$null`, which is invalid.</span></span> <span data-ttu-id="58c2c-129">その結果、既定のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-129">As a result, the default prompt appears.</span></span>

```powershell
PS C:\> function prompt {$null}
PS>
```

<span data-ttu-id="58c2c-130">PowerShell には組み込みのプロンプトが付属しているため、通常、既定のプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="58c2c-130">Because PowerShell comes with a built-in prompt, you usually do not see the default prompt.</span></span>

### <a name="built-in-prompt"></a><span data-ttu-id="58c2c-131">組み込みのプロンプト</span><span class="sxs-lookup"><span data-stu-id="58c2c-131">Built-in prompt</span></span>

<span data-ttu-id="58c2c-132">PowerShell には組み込み関数が含まれてい `Prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-132">PowerShell includes a built-in `Prompt` function.</span></span>

```powershell
function prompt {
    $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
      else { '' }) + 'PS ' + $(Get-Location) +
        $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="58c2c-133">関数は、コマンドレットを使用して、 `Test-Path` `$PSDebugContext` 自動変数が設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-133">The function uses the `Test-Path` cmdlet to determine whether the `$PSDebugContext` automatic variable is populated.</span></span> <span data-ttu-id="58c2c-134">が設定されている場合は、デバッグモードになり、次のように `$PSDebugContext` `[DBG]:` プロンプトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-134">If `$PSDebugContext` is populated, you are in debugging mode, and `[DBG]:` is added to the prompt, as follows:</span></span>

```Output
[DBG]: PS C:\ps-test>
```

<span data-ttu-id="58c2c-135">`$PSDebugContext`が設定されていない場合、関数は `PS` プロンプトにを追加します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-135">If `$PSDebugContext` is not populated, the function adds `PS` to the prompt.</span></span>
<span data-ttu-id="58c2c-136">また、関数は、コマンドレットを使用して、 `Get-Location` 現在のファイルシステムのディレクトリの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-136">And, the function uses the `Get-Location` cmdlet to get the current file system directory location.</span></span> <span data-ttu-id="58c2c-137">次に、右山かっこ () を追加し `>` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-137">Then, it adds a right angle bracket (`>`).</span></span>

<span data-ttu-id="58c2c-138">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-138">For example:</span></span>

```Output
PS C:\ps-test>
```

<span data-ttu-id="58c2c-139">入れ子になったプロンプトでは、関数によって2つの山かっこ () がプロンプトに追加され `>>` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-139">If you are in a nested prompt, the function adds two angle brackets (`>>`) to the prompt.</span></span> <span data-ttu-id="58c2c-140">(自動変数の値が1より大きい場合は、入れ子になったプロンプトが表示され `$NestedPromptLevel` ます)。</span><span class="sxs-lookup"><span data-stu-id="58c2c-140">(You are in a nested prompt if the value of the `$NestedPromptLevel` automatic variable is greater than 1.)</span></span>

<span data-ttu-id="58c2c-141">たとえば、入れ子になったプロンプトでデバッグする場合、プロンプトは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-141">For example, when you are debugging in a nested prompt, the prompt resembles the following prompt:</span></span>

```Output
[DBG] PS C:\ps-test>>>
```

### <a name="changes-to-the-prompt"></a><span data-ttu-id="58c2c-142">プロンプトの変更</span><span class="sxs-lookup"><span data-stu-id="58c2c-142">Changes to the prompt</span></span>

<span data-ttu-id="58c2c-143">`Enter-PSSession`コマンドレットは、リモートコンピューターの名前を現在の関数に付加し `Prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-143">The `Enter-PSSession` cmdlet prepends the name of the remote computer to the current `Prompt` function.</span></span> <span data-ttu-id="58c2c-144">コマンドレットを使用し `Enter-PSSession` てリモートコンピューターとのセッションを開始すると、コマンドプロンプトが変更され、リモートコンピューターの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-144">When you use the `Enter-PSSession` cmdlet to start a session with a remote computer, the command prompt changes to include the name of the remote computer.</span></span> <span data-ttu-id="58c2c-145">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-145">For example:</span></span>

```Output
PS Hello, World> Enter-PSSession Server01
[Server01]: PS Hello, World>
```

<span data-ttu-id="58c2c-146">その他の PowerShell ホストアプリケーションと代替シェルには、独自のカスタムコマンドプロンプトが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="58c2c-146">Other PowerShell host applications and alternate shells might have their own custom command prompts.</span></span>

<span data-ttu-id="58c2c-147">と自動変数の詳細については `$PSDebugContext` `$NestedPromptLevel` 、「 [about_Automatic_Variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58c2c-147">For more information about the `$PSDebugContext` and `$NestedPromptLevel` automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

### <a name="how-to-customize-the-prompt"></a><span data-ttu-id="58c2c-148">プロンプトをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="58c2c-148">How to customize the prompt</span></span>

<span data-ttu-id="58c2c-149">プロンプトをカスタマイズするには、新しい関数を記述し `Prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-149">To customize the prompt, write a new `Prompt` function.</span></span> <span data-ttu-id="58c2c-150">関数は保護されていないため、上書きできます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-150">The function is not protected, so you can overwrite it.</span></span>

<span data-ttu-id="58c2c-151">関数を記述するに `Prompt` は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-151">To write a `Prompt` function, type the following:</span></span>

```powershell
function prompt { }
```

<span data-ttu-id="58c2c-152">次に、中かっこの間に、プロンプトを作成するコマンドまたは文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-152">Then, between the braces, enter the commands or the string that creates your prompt.</span></span>

<span data-ttu-id="58c2c-153">たとえば、次のプロンプトにはコンピューター名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="58c2c-153">For example, the following prompt includes your computer name:</span></span>

```powershell
function prompt {"PS [$env:COMPUTERNAME]> "}
```

<span data-ttu-id="58c2c-154">Server01 コンピューターでは、プロンプトは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="58c2c-154">On the Server01 computer, the prompt resembles the following prompt:</span></span>

```Output
PS [Server01] >
```

<span data-ttu-id="58c2c-155">次の `Prompt` 関数には、現在の日付と時刻が含まれています。</span><span class="sxs-lookup"><span data-stu-id="58c2c-155">The following `Prompt` function includes the current date and time:</span></span>

```powershell
function prompt {"$(Get-Date)> "}
```

<span data-ttu-id="58c2c-156">プロンプトは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="58c2c-156">The prompt resembles the following prompt:</span></span>

```Output
03/15/2012 17:49:47>
```

<span data-ttu-id="58c2c-157">既定の関数を変更することもでき `Prompt` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-157">You can also change the default `Prompt` function:</span></span>

<span data-ttu-id="58c2c-158">たとえば、次の変更された関数は、 `Prompt` `[ADMIN]:` [ **管理者として実行** ] オプションを使用して powershell を開いたときに、組み込みの powershell プロンプトにを追加します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-158">For example, the following modified `Prompt` function adds `[ADMIN]:` to the built-in PowerShell prompt when PowerShell is opened by using the **Run as administrator** option:</span></span>

```powershell
function prompt {
  $identity = [Security.Principal.WindowsIdentity]::GetCurrent()
  $principal = [Security.Principal.WindowsPrincipal] $identity
  $adminRole = [Security.Principal.WindowsBuiltInRole]::Administrator

  $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
    elseif($principal.IsInRole($adminRole)) { "[ADMIN]: " }
    else { '' }
  ) + 'PS ' + $(Get-Location) +
    $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="58c2c-159">[ **管理者として実行** ] オプションを使用して PowerShell を起動すると、次のようなプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-159">When you start PowerShell by using the **Run as administrator** option, a prompt that resembles the following prompt appears:</span></span>

```Output
[ADMIN]: PS C:\ps-test>
```

<span data-ttu-id="58c2c-160">次の関数は、次の `Prompt` コマンドの履歴 ID を表示します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-160">The following `Prompt` function displays the history ID of the next command.</span></span> <span data-ttu-id="58c2c-161">コマンドの履歴を表示するには、コマンドレットを使用し `Get-History` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-161">To view the command history, use the `Get-History` cmdlet.</span></span>

```powershell
function prompt {
   # The at sign creates an array in case only one history item exists.
   $history = @(Get-History)
   if($history.Count -gt 0)
   {
      $lastItem = $history[$history.Count - 1]
      $lastId = $lastItem.Id
   }

   $nextCommand = $lastId + 1
   $currentDirectory = Get-Location
   "PS: $nextCommand $currentDirectory >"
}
```

<span data-ttu-id="58c2c-162">次のプロンプトでは、 `Write-Host` コマンドレットとコマンドレットを使用して、 `Get-Random` 色をランダムに変更するプロンプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-162">The following prompt uses the `Write-Host` and `Get-Random` cmdlets to create a prompt that changes color randomly.</span></span> <span data-ttu-id="58c2c-163">`Write-Host`は現在のホストアプリケーションに書き込みますが、オブジェクトを返しません。この関数には、ステートメントが含まれてい `Return` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-163">Because `Write-Host` writes to the current host application but does not return an object, this function includes a `Return` statement.</span></span> <span data-ttu-id="58c2c-164">使用しない場合、PowerShell では既定のプロンプトであるを使用し `PS>` ます。</span><span class="sxs-lookup"><span data-stu-id="58c2c-164">Without it, PowerShell uses the default prompt, `PS>`.</span></span>

```powershell
function prompt {
    $color = Get-Random -Min 1 -Max 16
    Write-Host ("PS " + $(Get-Location) +">") -NoNewLine `
     -ForegroundColor $Color
    return " "
}
```

### <a name="saving-the-prompt-function"></a><span data-ttu-id="58c2c-165">Prompt 関数を保存しています</span><span class="sxs-lookup"><span data-stu-id="58c2c-165">Saving the Prompt function</span></span>

<span data-ttu-id="58c2c-166">任意の関数と同様に、 `Prompt` 関数は現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-166">Like any function, the `Prompt` function exists only in the current session.</span></span> <span data-ttu-id="58c2c-167">`Prompt`今後のセッションのために関数を保存するには、PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="58c2c-167">To save the `Prompt` function for future sessions, add it to your PowerShell profiles.</span></span> <span data-ttu-id="58c2c-168">プロファイルの詳細については、「[about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58c2c-168">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="58c2c-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="58c2c-169">See also</span></span>

[<span data-ttu-id="58c2c-170">Get-Location</span><span class="sxs-lookup"><span data-stu-id="58c2c-170">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)

[<span data-ttu-id="58c2c-171">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="58c2c-171">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="58c2c-172">Get-History</span><span class="sxs-lookup"><span data-stu-id="58c2c-172">Get-History</span></span>](xref:Microsoft.PowerShell.Core.Get-History)

[<span data-ttu-id="58c2c-173">Get-Random</span><span class="sxs-lookup"><span data-stu-id="58c2c-173">Get-Random</span></span>](xref:Microsoft.PowerShell.Utility.Get-Random)

[<span data-ttu-id="58c2c-174">Write-Host</span><span class="sxs-lookup"><span data-stu-id="58c2c-174">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)

[<span data-ttu-id="58c2c-175">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="58c2c-175">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="58c2c-176">about_Functions</span><span class="sxs-lookup"><span data-stu-id="58c2c-176">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="58c2c-177">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="58c2c-177">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="58c2c-178">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="58c2c-178">about_Debuggers</span></span>](about_Debuggers.md)

[<span data-ttu-id="58c2c-179">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="58c2c-179">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)


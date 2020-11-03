---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 7e622367f1753fc15bed26fe083e9f343fd82b85
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224347"
---
# <span data-ttu-id="7977b-103">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="7977b-103">Write-Debug</span></span>

## <span data-ttu-id="7977b-104">概要</span><span class="sxs-lookup"><span data-stu-id="7977b-104">SYNOPSIS</span></span>
<span data-ttu-id="7977b-105">デバッグ メッセージをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="7977b-105">Writes a debug message to the console.</span></span>

## <span data-ttu-id="7977b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7977b-106">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="7977b-107">Description</span><span class="sxs-lookup"><span data-stu-id="7977b-107">DESCRIPTION</span></span>

<span data-ttu-id="7977b-108">`Write-Debug`コマンドレットは、スクリプトまたはコマンドからデバッグメッセージをホストに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7977b-108">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="7977b-109">既定では、デバッグメッセージはコンソールに表示されませんが、 **debug** パラメーターまたは変数を使用して表示でき `$DebugPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="7977b-109">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="7977b-110">例</span><span class="sxs-lookup"><span data-stu-id="7977b-110">EXAMPLES</span></span>

### <span data-ttu-id="7977b-111">例 1: $DebugPreference を理解する</span><span class="sxs-lookup"><span data-stu-id="7977b-111">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="7977b-112">この例では、デバッグメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7977b-112">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="7977b-113">の既定値 `$DebugPreference` は **SilentlyContinue** です。</span><span class="sxs-lookup"><span data-stu-id="7977b-113">The default value of `$DebugPreference` is **SilentlyContinue** .</span></span> <span data-ttu-id="7977b-114">このため、メッセージはコンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="7977b-114">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="7977b-115">例 2: $DebugPreference の値を変更する</span><span class="sxs-lookup"><span data-stu-id="7977b-115">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="7977b-116">この例では、変数の値を変更した場合の影響を示し `$DebugPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="7977b-116">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="7977b-117">まず、の現在の値を表示 `$DebugPreference` し、デバッグメッセージの書き込みを試みます。</span><span class="sxs-lookup"><span data-stu-id="7977b-117">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="7977b-118">次に、の値を `$DebugPreference` [ **続行** ] に変更します。これにより、デバッグメッセージを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7977b-118">Then we change the value of `$DebugPreference` to **Continue** , which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="7977b-119">の詳細について `$DebugPreference` は、「 [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7977b-119">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="7977b-120">例 3: Debug パラメーターを使用して $DebugPreference をオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="7977b-120">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="7977b-121">関数は、 `Test-Debug` 変数の値を `$DebugPreference` PowerShell ホストおよびデバッグストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7977b-121">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="7977b-122">この例では、 **Debug** パラメーターを使用して値をオーバーライドし `$DebugPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="7977b-122">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

```powershell
function Test-Debug {
    [CmdletBinding()]
    param()
    Write-Debug ('$DebugPreference is ' + $DebugPreference)
    Write-Host ('$DebugPreference is ' + $DebugPreference)
}
```

```
PS> Test-Debug
$DebugPreference is SilentlyContinue

PS> Test-Debug -Debug
DEBUG: $DebugPreference is Inquire

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
$DebugPreference is Inquire
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="7977b-123">`$DebugPreference` **Debug** パラメーターを使用すると、の値が変更されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7977b-123">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="7977b-124">この変更は、関数のスコープにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="7977b-124">This change only affects the scope of the function.</span></span> <span data-ttu-id="7977b-125">値は関数の外部には影響しません。</span><span class="sxs-lookup"><span data-stu-id="7977b-125">The value is not affected outside the function.</span></span>

> [!NOTE]
> <span data-ttu-id="7977b-126">の値 `$DebugPreference` が **Inquire** の場合、PowerShell は実行を停止して実行を続行するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7977b-126">When the value of `$DebugPreference` is **Inquire** , PowerShell halts execution to ask if execution should continue.</span></span>

<span data-ttu-id="7977b-127">**Debug** 共通パラメーターの詳細については、「 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7977b-127">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7977b-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7977b-128">PARAMETERS</span></span>

### <span data-ttu-id="7977b-129">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="7977b-129">-Message</span></span>

<span data-ttu-id="7977b-130">コンソールに出力するデバッグ メッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="7977b-130">Specifies the debug message to send to the console.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7977b-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7977b-131">CommonParameters</span></span>

<span data-ttu-id="7977b-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7977b-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7977b-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7977b-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7977b-134">入力</span><span class="sxs-lookup"><span data-stu-id="7977b-134">INPUTS</span></span>

### <span data-ttu-id="7977b-135">System.String</span><span class="sxs-lookup"><span data-stu-id="7977b-135">System.String</span></span>

<span data-ttu-id="7977b-136">パイプを使用して、デバッグメッセージを含む文字列をにパイプすることができ `Write-Debug` ます。</span><span class="sxs-lookup"><span data-stu-id="7977b-136">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="7977b-137">出力</span><span class="sxs-lookup"><span data-stu-id="7977b-137">OUTPUTS</span></span>

### <span data-ttu-id="7977b-138">なし</span><span class="sxs-lookup"><span data-stu-id="7977b-138">None</span></span>

<span data-ttu-id="7977b-139">`Write-Debug` は、デバッグストリームにのみ書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7977b-139">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="7977b-140">パイプラインにオブジェクトを書き込むことはありません。</span><span class="sxs-lookup"><span data-stu-id="7977b-140">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="7977b-141">注</span><span class="sxs-lookup"><span data-stu-id="7977b-141">NOTES</span></span>

## <span data-ttu-id="7977b-142">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7977b-142">RELATED LINKS</span></span>

[<span data-ttu-id="7977b-143">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="7977b-143">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="7977b-144">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="7977b-144">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="7977b-145">書き込み-エラー</span><span class="sxs-lookup"><span data-stu-id="7977b-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="7977b-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="7977b-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="7977b-147">Write-Output</span><span class="sxs-lookup"><span data-stu-id="7977b-147">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="7977b-148">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="7977b-148">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="7977b-149">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="7977b-149">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="7977b-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="7977b-150">Write-Warning</span></span>](Write-Warning.md)

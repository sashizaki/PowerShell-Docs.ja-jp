---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 3d23f76dbf8e1c9a21805a4914038c8c4f319852
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602784"
---
# <span data-ttu-id="a047c-102">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="a047c-102">Write-Debug</span></span>

## <span data-ttu-id="a047c-103">概要</span><span class="sxs-lookup"><span data-stu-id="a047c-103">SYNOPSIS</span></span>
<span data-ttu-id="a047c-104">デバッグ メッセージをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="a047c-104">Writes a debug message to the console.</span></span>

## <span data-ttu-id="a047c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a047c-105">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="a047c-106">Description</span><span class="sxs-lookup"><span data-stu-id="a047c-106">DESCRIPTION</span></span>

<span data-ttu-id="a047c-107">`Write-Debug`コマンドレットは、スクリプトまたはコマンドからデバッグメッセージをホストに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a047c-107">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="a047c-108">既定では、デバッグメッセージはコンソールに表示されませんが、 **debug** パラメーターまたは変数を使用して表示でき `$DebugPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="a047c-108">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="a047c-109">例</span><span class="sxs-lookup"><span data-stu-id="a047c-109">EXAMPLES</span></span>

### <span data-ttu-id="a047c-110">例 1: $DebugPreference を理解する</span><span class="sxs-lookup"><span data-stu-id="a047c-110">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="a047c-111">この例では、デバッグメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a047c-111">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="a047c-112">の既定値 `$DebugPreference` は **SilentlyContinue** です。</span><span class="sxs-lookup"><span data-stu-id="a047c-112">The default value of `$DebugPreference` is **SilentlyContinue**.</span></span> <span data-ttu-id="a047c-113">このため、メッセージはコンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="a047c-113">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="a047c-114">例 2: $DebugPreference の値を変更する</span><span class="sxs-lookup"><span data-stu-id="a047c-114">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="a047c-115">この例では、変数の値を変更した場合の影響を示し `$DebugPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="a047c-115">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="a047c-116">まず、の現在の値を表示 `$DebugPreference` し、デバッグメッセージの書き込みを試みます。</span><span class="sxs-lookup"><span data-stu-id="a047c-116">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="a047c-117">次に、の値を `$DebugPreference` [ **続行**] に変更します。これにより、デバッグメッセージを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a047c-117">Then we change the value of `$DebugPreference` to **Continue**, which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="a047c-118">の詳細について `$DebugPreference` は、「 [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a047c-118">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="a047c-119">例 3: Debug パラメーターを使用して $DebugPreference をオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="a047c-119">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="a047c-120">関数は、 `Test-Debug` 変数の値を `$DebugPreference` PowerShell ホストおよびデバッグストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a047c-120">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="a047c-121">この例では、 **Debug** パラメーターを使用して値をオーバーライドし `$DebugPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="a047c-121">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

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
DEBUG: $DebugPreference is Continue
$DebugPreference is Continue
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="a047c-122">`$DebugPreference` **Debug** パラメーターを使用すると、の値が変更されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a047c-122">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="a047c-123">この変更は、関数のスコープにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="a047c-123">This change only affects the scope of the function.</span></span> <span data-ttu-id="a047c-124">値は関数の外部には影響しません。</span><span class="sxs-lookup"><span data-stu-id="a047c-124">The value is not affected outside the function.</span></span>

<span data-ttu-id="a047c-125">**Debug** 共通パラメーターの詳細については、「 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a047c-125">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a047c-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a047c-126">PARAMETERS</span></span>

### <span data-ttu-id="a047c-127">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="a047c-127">-Message</span></span>

<span data-ttu-id="a047c-128">コンソールに出力するデバッグ メッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="a047c-128">Specifies the debug message to send to the console.</span></span>

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

### <span data-ttu-id="a047c-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a047c-129">CommonParameters</span></span>

<span data-ttu-id="a047c-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a047c-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a047c-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a047c-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a047c-132">入力</span><span class="sxs-lookup"><span data-stu-id="a047c-132">INPUTS</span></span>

### <span data-ttu-id="a047c-133">System.String</span><span class="sxs-lookup"><span data-stu-id="a047c-133">System.String</span></span>

<span data-ttu-id="a047c-134">パイプを使用して、デバッグメッセージを含む文字列をにパイプすることができ `Write-Debug` ます。</span><span class="sxs-lookup"><span data-stu-id="a047c-134">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="a047c-135">出力</span><span class="sxs-lookup"><span data-stu-id="a047c-135">OUTPUTS</span></span>

### <span data-ttu-id="a047c-136">なし</span><span class="sxs-lookup"><span data-stu-id="a047c-136">None</span></span>

<span data-ttu-id="a047c-137">`Write-Debug` は、デバッグストリームにのみ書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a047c-137">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="a047c-138">パイプラインにオブジェクトを書き込むことはありません。</span><span class="sxs-lookup"><span data-stu-id="a047c-138">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="a047c-139">注</span><span class="sxs-lookup"><span data-stu-id="a047c-139">NOTES</span></span>

## <span data-ttu-id="a047c-140">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a047c-140">RELATED LINKS</span></span>

[<span data-ttu-id="a047c-141">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="a047c-141">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="a047c-142">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="a047c-142">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="a047c-143">Write-Error</span><span class="sxs-lookup"><span data-stu-id="a047c-143">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="a047c-144">Write-Host</span><span class="sxs-lookup"><span data-stu-id="a047c-144">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="a047c-145">Write-Output</span><span class="sxs-lookup"><span data-stu-id="a047c-145">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="a047c-146">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="a047c-146">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="a047c-147">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="a047c-147">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="a047c-148">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="a047c-148">Write-Warning</span></span>](Write-Warning.md)

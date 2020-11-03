---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-warning?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Warning
ms.openlocfilehash: 7e74e53bd056a452917d2f2380b817fc6925f0fe
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224360"
---
# <span data-ttu-id="c5d2a-103">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="c5d2a-103">Write-Warning</span></span>

## <span data-ttu-id="c5d2a-104">概要</span><span class="sxs-lookup"><span data-stu-id="c5d2a-104">SYNOPSIS</span></span>
<span data-ttu-id="c5d2a-105">警告メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-105">Writes a warning message.</span></span>

## <span data-ttu-id="c5d2a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5d2a-106">SYNTAX</span></span>

```
Write-Warning [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="c5d2a-107">Description</span><span class="sxs-lookup"><span data-stu-id="c5d2a-107">DESCRIPTION</span></span>

<span data-ttu-id="c5d2a-108">コマンドレットでは、 `Write-Warning` 警告メッセージを PowerShell ホストに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-108">The `Write-Warning` cmdlet writes a warning message to the PowerShell host.</span></span> <span data-ttu-id="c5d2a-109">警告への応答は、ユーザーの変数の値と、 `$WarningPreference` **warnings action** 共通パラメーターの使用によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-109">The response to the warning depends on the value of the user's `$WarningPreference` variable and the use of the **WarningAction** common parameter.</span></span>

## <span data-ttu-id="c5d2a-110">例</span><span class="sxs-lookup"><span data-stu-id="c5d2a-110">EXAMPLES</span></span>

### <span data-ttu-id="c5d2a-111">例 1: 警告メッセージを記述する</span><span class="sxs-lookup"><span data-stu-id="c5d2a-111">Example 1: Write a warning message</span></span>

<span data-ttu-id="c5d2a-112">このコマンドは、"WARNING: This is only a test warning." というメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-112">This command displays the message "WARNING: This is only a test warning."</span></span>

```powershell
Write-Warning "This is only a test warning."
```

### <span data-ttu-id="c5d2a-113">例 2: Write-Warning に文字列を渡す</span><span class="sxs-lookup"><span data-stu-id="c5d2a-113">Example 2: Pass a string to Write-Warning</span></span>

<span data-ttu-id="c5d2a-114">このコマンドは、パイプライン演算子 () を使用してに文字列を送信できることを示して `|` `Write-Warning` います。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-114">This command shows that you can use a pipeline operator (`|`) to send a string to `Write-Warning`.</span></span>
<span data-ttu-id="c5d2a-115">このコマンドに示すように、変数に文字列を保存することも、文字列を直接にパイプすることもでき `Write-Warning` ます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-115">You can save the string in a variable, as shown in this command, or pipe the string directly to `Write-Warning`.</span></span>

```powershell
$w = "This is only a test warning."
$w | Write-Warning
```

### <span data-ttu-id="c5d2a-116">例 3: $WarningPreference 変数を設定し、警告を記述する</span><span class="sxs-lookup"><span data-stu-id="c5d2a-116">Example 3: Set the $WarningPreference variable and write a warning</span></span>

<span data-ttu-id="c5d2a-117">この例は、コマンドの変数の値の効果を示して `$WarningPreference` `Write-Warning` います。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-117">This example shows the effect of the value of the `$WarningPreference` variable on a `Write-Warning` command.</span></span>

```powershell
PS> $WarningPreference
Continue
PS> Write-Warning "This is only a test warning."
This is only a test warning.
PS> $WarningPreference = "SilentlyContinue"
PS> Write-Warning "This is only a test warning."
PS> $WarningPreference = "Stop"
PS> Write-Warning "This is only a test warning."
WARNING: This is only a test message.
Write-Warning : Command execution stopped because the shell variable "WarningPreference" is set to Stop.
At line:1 char:14
     + Write-Warning <<<<  "This is only a test message."
```

<span data-ttu-id="c5d2a-118">最初のコマンドは、変数の既定値であるを表示し `$WarningPreference` `Continue` ます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-118">The first command displays the default value of the `$WarningPreference` variable, which is `Continue`.</span></span> <span data-ttu-id="c5d2a-119">この結果、警告メッセージが表示された後も実行が継続されます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-119">As a result, when you write a warning, the warning message is displayed and execution continues.</span></span>

<span data-ttu-id="c5d2a-120">変数の値を変更すると、 `$WarningPreference` コマンドの効果が `Write-Warning` 再度変更されます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-120">When you change the value of the `$WarningPreference` variable, the effect of the `Write-Warning` command changes again.</span></span> <span data-ttu-id="c5d2a-121">値がの場合、 `SilentlyContinue` 警告は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-121">A value of `SilentlyContinue` suppresses the warning.</span></span> <span data-ttu-id="c5d2a-122">値がの場合、 `Stop` 警告が表示され、コマンドの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-122">A value of `Stop` displays the warning and then stops execution of the command.</span></span>

<span data-ttu-id="c5d2a-123">変数の詳細については `$WarningPreference` 、「 [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-123">For more information about the `$WarningPreference` variable, see [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="c5d2a-124">例 4: Warnings アクションパラメーターを設定し、警告を書き込む</span><span class="sxs-lookup"><span data-stu-id="c5d2a-124">Example 4: Set the WarningAction parameter and write a warning</span></span>

<span data-ttu-id="c5d2a-125">この例は、コマンドに対する **Warnings action** 共通パラメーターの効果を示して `Write-Warning` います。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-125">This example shows the effect of the **WarningAction** common parameter on a `Write-Warning` command.</span></span> <span data-ttu-id="c5d2a-126">任意のコマンドレットと共に **Warnings action** 共通パラメーターを使用して、そのコマンドによって生成された警告に対して PowerShell がどのように応答するかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-126">You can use the **WarningAction** common parameter with any cmdlet to determine how PowerShell responds to warnings resulting from that command.</span></span> <span data-ttu-id="c5d2a-127">**Warnings action** 共通パラメーターは、その特定のコマンドのの値のみをオーバーライドし `$WarningPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-127">The **WarningAction** common parameter overrides the value of the `$WarningPreference` only for that particular command.</span></span>

```powershell
PS> Write-Warning "This is only a test warning." -WarningAction Inquire
WARNING: This is only a test warning.
Confirm
Continue with this operation?
 [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="c5d2a-128">このコマンドは、 `Write-Warning` コマンドレットを使用して警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-128">This command uses the `Write-Warning` cmdlet to display a warning.</span></span> <span data-ttu-id="c5d2a-129">値が Inquire の **Warnings action** 共通パラメーターは、コマンドで警告が表示されたときにユーザーにプロンプトを表示するようシステムに指示します。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-129">The **WarningAction** common parameter with a value of Inquire directs the system to prompt the user when the command displays a warning.</span></span>

<span data-ttu-id="c5d2a-130">**Warnings action** 共通パラメーターの詳細については、「 [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-130">For more information about the **WarningAction** common parameter, see [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c5d2a-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5d2a-131">PARAMETERS</span></span>

### <span data-ttu-id="c5d2a-132">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="c5d2a-132">-Message</span></span>
<span data-ttu-id="c5d2a-133">警告メッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-133">Specifies the warning message.</span></span>

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

### <span data-ttu-id="c5d2a-134">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5d2a-134">CommonParameters</span></span>

<span data-ttu-id="c5d2a-135">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5d2a-136">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5d2a-137">入力</span><span class="sxs-lookup"><span data-stu-id="c5d2a-137">INPUTS</span></span>

### <span data-ttu-id="c5d2a-138">System.String</span><span class="sxs-lookup"><span data-stu-id="c5d2a-138">System.String</span></span>

<span data-ttu-id="c5d2a-139">パイプを使用して、警告を含む文字列をにパイプすることができ `Write-Warning` ます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-139">You can pipe a string that contains the warning to `Write-Warning`.</span></span>

## <span data-ttu-id="c5d2a-140">出力</span><span class="sxs-lookup"><span data-stu-id="c5d2a-140">OUTPUTS</span></span>

### <span data-ttu-id="c5d2a-141">なし</span><span class="sxs-lookup"><span data-stu-id="c5d2a-141">None</span></span>

<span data-ttu-id="c5d2a-142">`Write-Warning` 警告ストリームにのみ書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-142">`Write-Warning` writes only to the warning stream.</span></span> <span data-ttu-id="c5d2a-143">その他の出力は生成しません。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-143">It does not generate any other output.</span></span>

## <span data-ttu-id="c5d2a-144">注</span><span class="sxs-lookup"><span data-stu-id="c5d2a-144">NOTES</span></span>

<span data-ttu-id="c5d2a-145">変数の既定値 `$WarningPreference` はです `Continue` 。これにより、警告が表示され、コマンドの実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-145">The default value for the `$WarningPreference` variable is `Continue`, which displays the warning and then continues executing the command.</span></span> <span data-ttu-id="c5d2a-146">などのユーザー設定変数の有効な値を確認するには、 `$WarningPreference` "abc" などのランダムな文字の文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-146">To determine valid values for a preference variable such as `$WarningPreference`, set it to a string of random characters, such as "abc".</span></span> <span data-ttu-id="c5d2a-147">結果として得られるエラーメッセージには、有効な値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5d2a-147">The resulting error message lists the valid values.</span></span>

## <span data-ttu-id="c5d2a-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c5d2a-148">RELATED LINKS</span></span>

[<span data-ttu-id="c5d2a-149">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="c5d2a-149">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="c5d2a-150">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="c5d2a-150">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="c5d2a-151">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="c5d2a-151">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="c5d2a-152">書き込み-エラー</span><span class="sxs-lookup"><span data-stu-id="c5d2a-152">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="c5d2a-153">Write-Host</span><span class="sxs-lookup"><span data-stu-id="c5d2a-153">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="c5d2a-154">Write-Information</span><span class="sxs-lookup"><span data-stu-id="c5d2a-154">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="c5d2a-155">Write-Output</span><span class="sxs-lookup"><span data-stu-id="c5d2a-155">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="c5d2a-156">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="c5d2a-156">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="c5d2a-157">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="c5d2a-157">Write-Verbose</span></span>](Write-Verbose.md)

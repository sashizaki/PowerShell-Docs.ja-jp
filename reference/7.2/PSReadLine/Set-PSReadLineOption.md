---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: cac2c2bb8ce1f3a28c0d91c7503b3ac4d038ccad
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "99601800"
---
# <span data-ttu-id="e4f2b-102">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="e4f2b-102">Set-PSReadLineOption</span></span>

## <span data-ttu-id="e4f2b-103">構文</span><span class="sxs-lookup"><span data-stu-id="e4f2b-103">Synopsis</span></span>
<span data-ttu-id="e4f2b-104">**Psreadline** でのコマンドライン編集の動作をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-104">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

## <span data-ttu-id="e4f2b-105">構文</span><span class="sxs-lookup"><span data-stu-id="e4f2b-105">Syntax</span></span>

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func`2[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action`1[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-PredictionSource <PredictionSource>]
 [-PredictionViewStyle <PredictionViewStyle>] [-Colors <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="e4f2b-106">説明</span><span class="sxs-lookup"><span data-stu-id="e4f2b-106">Description</span></span>

<span data-ttu-id="e4f2b-107">コマンドラインを編集しているときに、コマンドレットによって `Set-PSReadLineOption` **psreadline** モジュールの動作がカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-107">The `Set-PSReadLineOption` cmdlet customizes the behavior of the **PSReadLine** module when you're editing the command line.</span></span> <span data-ttu-id="e4f2b-108">**Psreadline** の設定を表示するには、を使用し `Get-PSReadLineOption` ます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-108">To view the **PSReadLine** settings, use `Get-PSReadLineOption`.</span></span>

## <span data-ttu-id="e4f2b-109">例</span><span class="sxs-lookup"><span data-stu-id="e4f2b-109">Examples</span></span>

### <span data-ttu-id="e4f2b-110">例 1: 前景色と背景色を設定する</span><span class="sxs-lookup"><span data-stu-id="e4f2b-110">Example 1: Set foreground and background colors</span></span>

<span data-ttu-id="e4f2b-111">この例では、 **Psreadline** を設定して、 **コメント** トークンを緑色の前景テキストがグレーの背景に表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-111">This example sets **PSReadLine** to display the **Comment** token with green foreground text on a gray background.</span></span> <span data-ttu-id="e4f2b-112">この例で使用されているエスケープシーケンスでは、 **32** は前景色を表し、 **47** は背景色を表します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-112">In the escape sequence used in the example, **32** represents the foreground color and **47** represents the background color.</span></span>

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

<span data-ttu-id="e4f2b-113">前景テキストの色のみを設定するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-113">You can choose to set only a foreground text color.</span></span> <span data-ttu-id="e4f2b-114">たとえば、 **コメント** トークンの背景色が明るい緑で表示さ ``"Comment"="`e[92m"`` れます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-114">For example, a bright green foreground text color for the **Comment** token: ``"Comment"="`e[92m"``.</span></span>

### <span data-ttu-id="e4f2b-115">例 2: ベルのスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="e4f2b-115">Example 2: Set bell style</span></span>

<span data-ttu-id="e4f2b-116">この例では、 **Psreadline** は、ユーザーに注意する必要があるエラーまたは条件に応答します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-116">In this example, **PSReadLine** will respond to errors or conditions that require user attention.</span></span>
<span data-ttu-id="e4f2b-117">**ベル Lstyle** は、1221 Hz の60ミリ秒で可聴ビープ音を発するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-117">The **BellStyle** is set to emit an audible beep at 1221 Hz for 60 ms.</span></span>

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> <span data-ttu-id="e4f2b-118">この機能は、プラットフォーム上のすべてのホストで動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-118">This feature may not work in all hosts on platforms.</span></span>

### <span data-ttu-id="e4f2b-119">例 3: 複数のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="e4f2b-119">Example 3: Set multiple options</span></span>

<span data-ttu-id="e4f2b-120">`Set-PSReadLineOption` ハッシュテーブルを使用して複数のオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-120">`Set-PSReadLineOption` can set multiple options with a hash table.</span></span>

```powershell
$PSReadLineOptions = @{
    EditMode = "Emacs"
    HistoryNoDuplicates = $true
    HistorySearchCursorMovesToEnd = $true
    Colors = @{
        "Command" = "#8181f7"
    }
}
Set-PSReadLineOption @PSReadLineOptions
```

<span data-ttu-id="e4f2b-121">ハッシュテーブルによって `$PSReadLineOptions` 、キーと値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-121">The `$PSReadLineOptions` hash table sets the keys and values.</span></span> <span data-ttu-id="e4f2b-122">`Set-PSReadLineOption` では、キーと値を使用して `@PSReadLineOptions` **psreadline** オプションを更新します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-122">`Set-PSReadLineOption` uses the keys and values with `@PSReadLineOptions` to update the **PSReadLine** options.</span></span>

<span data-ttu-id="e4f2b-123">ハッシュテーブル名を入力したキーと値は、 `$PSReadLineOptions` PowerShell コマンドラインで表示できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-123">You can view the keys and values entering the hash table name, `$PSReadLineOptions` on the PowerShell command line.</span></span>

### <span data-ttu-id="e4f2b-124">例 4: 複数の色のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="e4f2b-124">Example 4: Set multiple color options</span></span>

<span data-ttu-id="e4f2b-125">この例では、1つのコマンドで複数の color 値を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-125">This example shows how to set more than one color value in a single command.</span></span>

```powershell
Set-PSReadLineOption -Colors @{
  Command            = 'Magenta'
  Number             = 'DarkGray'
  Member             = 'DarkGray'
  Operator           = 'DarkGray'
  Type               = 'DarkGray'
  Variable           = 'DarkGreen'
  Parameter          = 'DarkGreen'
  ContinuationPrompt = 'DarkGray'
  Default            = 'DarkGray'
}
```

### <span data-ttu-id="e4f2b-126">例 5: 複数の型の色の値を設定する</span><span class="sxs-lookup"><span data-stu-id="e4f2b-126">Example 5: Set color values for multiple types</span></span>

<span data-ttu-id="e4f2b-127">この例では、 **Psreadline** に表示されるトークンの色を設定する方法について、3種類の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-127">This example shows three different methods for how to set the color of tokens displayed in **PSReadLine**.</span></span>

```powershell
Set-PSReadLineOption -Colors @{
 # Use a ConsoleColor enum
 "Error" = [ConsoleColor]::DarkRed

 # 24 bit color escape sequence
 "String" = "$([char]0x1b)[38;5;100m"

 # RGB value
 "Command" = "#8181f7"
}
```

### <span data-ttu-id="e4f2b-128">例 6: ViModeChangeHandler を使用して Vi モードの変更を表示する</span><span class="sxs-lookup"><span data-stu-id="e4f2b-128">Example 6: Use ViModeChangeHandler to display Vi mode changes</span></span>

<span data-ttu-id="e4f2b-129">この例では、 **Vi** モードの変更に応じて、VT escape のカーソル変更を出力します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-129">This example emits a cursor change VT escape in response to a **Vi** mode change.</span></span>

```powershell
function OnViModeChange {
    if ($args[0] -eq 'Command') {
        # Set the cursor to a blinking block.
        Write-Host -NoNewLine "`e[1 q"
    } else {
        # Set the cursor to a blinking line.
        Write-Host -NoNewLine "`e[5 q"
    }
}
Set-PSReadLineOption -ViModeIndicator Script -ViModeChangeHandler $Function:OnViModeChange
```

<span data-ttu-id="e4f2b-130">**Onvimodechange** 関数は、 **Vi** モード (insert および command) のカーソルオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-130">The **OnViModeChange** function sets the cursor options for the **Vi** modes: insert and command.</span></span>
<span data-ttu-id="e4f2b-131">**ViModeChangeHandler** は、プロバイダーを使用し `Function:` て、スクリプトブロックオブジェクトとして **onvimodechange** を参照します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-131">**ViModeChangeHandler** uses the `Function:` provider to reference **OnViModeChange** as a script block object.</span></span>

<span data-ttu-id="e4f2b-132">詳細については、「[about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-132">For more information, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <span data-ttu-id="e4f2b-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4f2b-133">Parameters</span></span>

### <span data-ttu-id="e4f2b-134">-Addtohistory ハンドラー</span><span class="sxs-lookup"><span data-stu-id="e4f2b-134">-AddToHistoryHandler</span></span>

<span data-ttu-id="e4f2b-135">**Psreadline** 履歴に追加するコマンドを制御する **ScriptBlock** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-135">Specifies a **ScriptBlock** that controls which commands get added to **PSReadLine** history.</span></span>

<span data-ttu-id="e4f2b-136">**ScriptBlock** は、コマンドラインを入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-136">The **ScriptBlock** receives the command line as input.</span></span> <span data-ttu-id="e4f2b-137">**ScriptBlock** がを返した場合は、 `$True` コマンドラインが履歴に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-137">If the **ScriptBlock** returns `$True`, the command line is added to the history.</span></span>

```yaml
Type: System.Func`2[System.String,System.Object]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-138">-AnsiEscapeTimeout</span><span class="sxs-lookup"><span data-stu-id="e4f2b-138">-AnsiEscapeTimeout</span></span>

<span data-ttu-id="e4f2b-139">このオプションは、入力がリダイレクトされるときのウィンドウに固有です。たとえば、またはで実行されている場合です `tmux` `screen` 。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-139">This option is specific to Windows when input is redirected, for example, when running under `tmux` or `screen`.</span></span>

<span data-ttu-id="e4f2b-140">Windows でのリダイレクト入力では、多くのキーがエスケープ文字で始まる文字のシーケンスとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-140">With redirected input on Windows, many keys are sent as a sequence of characters starting with the escape character.</span></span> <span data-ttu-id="e4f2b-141">1つのエスケープ文字の後により多くの文字と有効なエスケープシーケンスを区別することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-141">It's impossible to distinguish between a single escape character followed by more characters and a valid escape sequence.</span></span>

<span data-ttu-id="e4f2b-142">ターミナルは、ユーザーの種類よりも高速に文字を送信できることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-142">The assumption is that the terminal can send the characters faster than a user types.</span></span> <span data-ttu-id="e4f2b-143">**Psreadline** は、このタイムアウトを待機してから、完全なエスケープシーケンスを受け取っています。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-143">**PSReadLine** waits for this timeout before concluding that it has received a complete escape sequence.</span></span>

<span data-ttu-id="e4f2b-144">入力時にランダムまたは予期しない文字が表示する場合は、このタイムアウトを調整できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-144">If you see random or unexpected characters when you type, you can adjust this timeout.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-145">-ベル Lstyle</span><span class="sxs-lookup"><span data-stu-id="e4f2b-145">-BellStyle</span></span>

<span data-ttu-id="e4f2b-146">**Psreadline** がさまざまなエラーやあいまいな状況にどのように応答するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-146">Specifies how **PSReadLine** responds to various error and ambiguous conditions.</span></span>

<span data-ttu-id="e4f2b-147">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-147">The valid values are as follows:</span></span>

- <span data-ttu-id="e4f2b-148">**可聴**: 短いビープ音。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-148">**Audible**: A short beep.</span></span>
- <span data-ttu-id="e4f2b-149">**ビジュアル**: テキストが短時間点滅します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-149">**Visual**: Text flashes briefly.</span></span>
- <span data-ttu-id="e4f2b-150">**None**: フィードバックがありません。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-150">**None**: No feedback.</span></span>

```yaml
Type: Microsoft.PowerShell.BellStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Audible
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-151">-色</span><span class="sxs-lookup"><span data-stu-id="e4f2b-151">-Colors</span></span>

<span data-ttu-id="e4f2b-152">**Colors** パラメーターは、 **psreadline** によって使用されるさまざまな色を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-152">The **Colors** parameter specifies various colors used by **PSReadLine**.</span></span>

<span data-ttu-id="e4f2b-153">引数は、キーが色を指定する要素と値を指定するハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-153">The argument is a hash table where the keys specify which element and the values specify the color.</span></span>
<span data-ttu-id="e4f2b-154">詳細については、「 [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-154">For more information, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="e4f2b-155">色には、 **ConsoleColor** の値か、 `[ConsoleColor]::Red` 有効な ANSI エスケープシーケンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-155">Colors can be either a value from **ConsoleColor**, for example `[ConsoleColor]::Red`, or a valid ANSI escape sequence.</span></span> <span data-ttu-id="e4f2b-156">有効なエスケープシーケンスは、ターミナルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-156">Valid escape sequences depend on your terminal.</span></span> <span data-ttu-id="e4f2b-157">PowerShell 5.0 では、赤いテキストのエスケープシーケンスの例はです `$([char]0x1b)[91m` 。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-157">In PowerShell 5.0, an example escape sequence for red text is `$([char]0x1b)[91m`.</span></span> <span data-ttu-id="e4f2b-158">PowerShell 6 以降では、同じエスケープシーケンスは `` `e[91m`` です。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-158">In PowerShell 6 and above, the same escape sequence is `` `e[91m``.</span></span> <span data-ttu-id="e4f2b-159">次の型を含むその他のエスケープシーケンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-159">You can specify other escape sequences including the following types:</span></span>

<span data-ttu-id="e4f2b-160">PSReadLine 2.2.0 でののカスタマイズをサポートするために、2色の設定が追加されました `ListView` 。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-160">Two color settings were added to support customization of the `ListView` in PSReadLine 2.2.0:</span></span>

- <span data-ttu-id="e4f2b-161">**ListPredictionColor** -先頭の `>` 文字と末尾のソース名 (など) の色を設定し `[History]` ます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-161">**ListPredictionColor** - set color for the leading `>` character and the trailing source name, e.g. `[History]`.</span></span> <span data-ttu-id="e4f2b-162">既定では、が `DarkYellow` 前景色として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-162">By default, it uses `DarkYellow` as the foreground color.</span></span>
- <span data-ttu-id="e4f2b-163">**ListPredictionSelectedColor** -リスト項目が選択されていることを示す色を設定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-163">**ListPredictionSelectedColor** - set color for indicating a list item is selected.</span></span> <span data-ttu-id="e4f2b-164">既定では、は `DarkBlack` 背景色としてを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-164">By default, it uses `DarkBlack` as the background color.</span></span>

- <span data-ttu-id="e4f2b-165">256色</span><span class="sxs-lookup"><span data-stu-id="e4f2b-165">256 color</span></span>
- <span data-ttu-id="e4f2b-166">24ビットカラー</span><span class="sxs-lookup"><span data-stu-id="e4f2b-166">24-bit color</span></span>
- <span data-ttu-id="e4f2b-167">前景、背景、または両方</span><span class="sxs-lookup"><span data-stu-id="e4f2b-167">Foreground, background, or both</span></span>
- <span data-ttu-id="e4f2b-168">反転、太字</span><span class="sxs-lookup"><span data-stu-id="e4f2b-168">Inverse, bold</span></span>

<span data-ttu-id="e4f2b-169">ANSI カラーコードの詳細については、Wikipedia の「 [ansi escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-169">For more information about ANSI color codes, see [ANSI escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span></span>

<span data-ttu-id="e4f2b-170">有効なキーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-170">The valid keys include:</span></span>

- <span data-ttu-id="e4f2b-171">**続行 ationprompt**: 継続プロンプトの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-171">**ContinuationPrompt**: The color of the continuation prompt.</span></span>
- <span data-ttu-id="e4f2b-172">**強調**: 強調色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-172">**Emphasis**: The emphasis color.</span></span> <span data-ttu-id="e4f2b-173">たとえば、履歴を検索するときに一致するテキストです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-173">For example, the matching text when searching history.</span></span>
- <span data-ttu-id="e4f2b-174">**エラー**: エラーの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-174">**Error**: The error color.</span></span> <span data-ttu-id="e4f2b-175">たとえば、プロンプトでを入力します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-175">For example, in the prompt.</span></span>
- <span data-ttu-id="e4f2b-176">**Selection**: メニューの選択または選択されたテキストを強調表示する色です。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-176">**Selection**: The color to highlight the menu selection or selected text.</span></span>
- <span data-ttu-id="e4f2b-177">**既定** 値: 既定のトークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-177">**Default**: The default token color.</span></span>
- <span data-ttu-id="e4f2b-178">**Comment**: コメントトークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-178">**Comment**: The comment token color.</span></span>
- <span data-ttu-id="e4f2b-179">**キーワード**: キーワードトークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-179">**Keyword**: The keyword token color.</span></span>
- <span data-ttu-id="e4f2b-180">**String**: 文字列トークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-180">**String**: The string token color.</span></span>
- <span data-ttu-id="e4f2b-181">**Operator**: 演算子のトークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-181">**Operator**: The operator token color.</span></span>
- <span data-ttu-id="e4f2b-182">**Variable**: 変数のトークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-182">**Variable**: The variable token color.</span></span>
- <span data-ttu-id="e4f2b-183">**Command**: コマンドトークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-183">**Command**: The command token color.</span></span>
- <span data-ttu-id="e4f2b-184">**パラメーター**: パラメーターのトークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-184">**Parameter**: The parameter token color.</span></span>
- <span data-ttu-id="e4f2b-185">**Type**: 型トークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-185">**Type**: The type token color.</span></span>
- <span data-ttu-id="e4f2b-186">**Number**: 数値トークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-186">**Number**: The number token color.</span></span>
- <span data-ttu-id="e4f2b-187">**メンバー**: メンバー名トークンの色。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-187">**Member**: The member name token color.</span></span>
- <span data-ttu-id="e4f2b-188">**InlinePrediction**: 予測提案のインラインビューの色です。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-188">**InlinePrediction**: The color for the inline view of the predictive suggestion.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-189">-CommandValidationHandler</span><span class="sxs-lookup"><span data-stu-id="e4f2b-189">-CommandValidationHandler</span></span>

<span data-ttu-id="e4f2b-190">**Validateandacceptline** から呼び出される **ScriptBlock** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-190">Specifies a **ScriptBlock** that is called from **ValidateAndAcceptLine**.</span></span> <span data-ttu-id="e4f2b-191">例外がスローされた場合、検証は失敗し、エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-191">If an exception is thrown, validation fails and the error is reported.</span></span>

<span data-ttu-id="e4f2b-192">例外をスローする前に、検証ハンドラーはエラーの発生時にカーソルを置いて、簡単に修正できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-192">Before throwing an exception, the validation handler can place the cursor at the point of the error to make it easier to fix.</span></span> <span data-ttu-id="e4f2b-193">検証ハンドラーは、などのコマンドラインを変更して、一般的な入力ミスを修正することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-193">A validation handler can also change the command line, such as to correct common typographical errors.</span></span>

<span data-ttu-id="e4f2b-194">**Validateandacceptline** を使用すると、動作しないコマンドで履歴が乱雑にならないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-194">**ValidateAndAcceptLine** is used to avoid cluttering your history with commands that can't work.</span></span>

```yaml
Type: System.Action`1[System.Management.Automation.Language.CommandAst]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-195">-補完 Queryitems</span><span class="sxs-lookup"><span data-stu-id="e4f2b-195">-CompletionQueryItems</span></span>

<span data-ttu-id="e4f2b-196">プロンプトを表示せずに表示される完了項目の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-196">Specifies the maximum number of completion items that are shown without prompting.</span></span>

<span data-ttu-id="e4f2b-197">表示する項目の数がこの値よりも大きい場合、 **Psreadline** は、完了項目を表示する前に、 **[はい/いいえ]** を表示します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-197">If the number of items to show is greater than this value, **PSReadLine** prompts **yes/no** before displaying the completion items.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-198">-続行 Ationprompt</span><span class="sxs-lookup"><span data-stu-id="e4f2b-198">-ContinuationPrompt</span></span>

<span data-ttu-id="e4f2b-199">複数行の入力が入力された場合に、後続の行の先頭に表示される文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-199">Specifies the string displayed at the beginning of the subsequent lines when multi-line input is entered.</span></span> <span data-ttu-id="e4f2b-200">既定値は2倍大きい記号 ( `>>` ) です。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-200">The default is double greater-than signs (`>>`).</span></span> <span data-ttu-id="e4f2b-201">空の文字列は有効です。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-201">An empty string is valid.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-202">-有効期間</span><span class="sxs-lookup"><span data-stu-id="e4f2b-202">-DingDuration</span></span>

<span data-ttu-id="e4f2b-203">**ベル Lstyle** が **可聴** に設定されている場合のビープ音の期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-203">Specifies the duration of the beep when **BellStyle** is set to **Audible**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50ms
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-204">-外調</span><span class="sxs-lookup"><span data-stu-id="e4f2b-204">-DingTone</span></span>

<span data-ttu-id="e4f2b-205">**ベル Lstyle** が **可聴** に設定されている場合のビープ音のトーンをヘルツ (hz) で指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-205">Specifies the tone in Hertz (Hz) of the beep when **BellStyle** is set to **Audible**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1221
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-206">-EditMode</span><span class="sxs-lookup"><span data-stu-id="e4f2b-206">-EditMode</span></span>

<span data-ttu-id="e4f2b-207">コマンドライン編集モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-207">Specifies the command line editing mode.</span></span> <span data-ttu-id="e4f2b-208">このパラメーターを使用すると、によって設定されたキーバインドがリセットさ `Set-PSReadLineKeyHandler` れます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-208">Using this parameter resets any key bindings set by `Set-PSReadLineKeyHandler`.</span></span>

<span data-ttu-id="e4f2b-209">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-209">The valid values are as follows:</span></span>

- <span data-ttu-id="e4f2b-210">**Windows**: キーバインドは、PowerShell、cmd、および Visual Studio をエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-210">**Windows**: Key bindings emulate PowerShell, cmd, and Visual Studio.</span></span>
- <span data-ttu-id="e4f2b-211">**Emacs**: キーバインドは Bash または Emacs をエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-211">**Emacs**: Key bindings emulate Bash or Emacs.</span></span>
- <span data-ttu-id="e4f2b-212">**Vi**: キーバインドは vi をエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-212">**Vi**: Key bindings emulate Vi.</span></span>

<span data-ttu-id="e4f2b-213">`Get-PSReadLineKeyHandler`現在構成されている **EditMode** のキーバインドを表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-213">Use `Get-PSReadLineKeyHandler` to see the key bindings for the currently configured **EditMode**.</span></span>

```yaml
Type: Microsoft.PowerShell.EditMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-214">-ExtraPromptLineCount</span><span class="sxs-lookup"><span data-stu-id="e4f2b-214">-ExtraPromptLineCount</span></span>

<span data-ttu-id="e4f2b-215">余分な行の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-215">Specifies the number of extra lines.</span></span>

<span data-ttu-id="e4f2b-216">プロンプトが複数行にわたっている場合は、このパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-216">If your prompt spans more than one line, specify a value for this parameter.</span></span> <span data-ttu-id="e4f2b-217">このオプションは、出力を表示した後に **Psreadline** がプロンプトを表示するときに余分な行を使用できるようにする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-217">Use this option when you want extra lines to be available when **PSReadLine** displays the prompt after showing some output.</span></span> <span data-ttu-id="e4f2b-218">たとえば、 **Psreadline** は入力候補の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-218">For example, **PSReadLine** returns a list of completions.</span></span>

<span data-ttu-id="e4f2b-219">このオプションは、以前のバージョンの **Psreadline** の場合よりも小さくする必要がありますが、関数を使用するときに便利です `InvokePrompt` 。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-219">This option is needed less than in previous versions of **PSReadLine**, but is useful when the `InvokePrompt` function is used.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-220">-履歴の重複</span><span class="sxs-lookup"><span data-stu-id="e4f2b-220">-HistoryNoDuplicates</span></span>

<span data-ttu-id="e4f2b-221">このオプションは、再呼び出しの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-221">This option controls the recall behavior.</span></span> <span data-ttu-id="e4f2b-222">重複するコマンドは、履歴ファイルにまだ追加されています。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-222">Duplicate commands are still added to the history file.</span></span>
<span data-ttu-id="e4f2b-223">このオプションを設定すると、コマンドの呼び出し時に最新の呼び出しのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-223">When this option is set, only the most recent invocation appears when recalling commands.</span></span> <span data-ttu-id="e4f2b-224">再呼び出し中に順序を維持するために、繰り返しコマンドが履歴に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-224">Repeated commands are added to history to preserve ordering during recall.</span></span> <span data-ttu-id="e4f2b-225">ただし、通常は、履歴をリコールまたは検索するときにコマンドを複数回表示したくはありません。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-225">However, you typically don't want to see the command multiple times when recalling or searching the history.</span></span>

<span data-ttu-id="e4f2b-226">既定では、グローバル **PSConsoleReadLineOptions** オブジェクトの **履歴の no重複** プロパティはに設定され `True` ます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-226">By default, the **HistoryNoDuplicates** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="e4f2b-227">この **Switchparameter** を使用して、プロパティ値をに設定し `True` ます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-227">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="e4f2b-228">プロパティ値を変更するには、次のように **Switchparameter** の値を指定する必要があります `-HistoryNoDuplicates:$False` 。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-228">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-HistoryNoDuplicates:$False`.</span></span>

<span data-ttu-id="e4f2b-229">次のコマンドを使用して、プロパティ値を直接設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-229">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).HistoryNoDuplicates = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-230">-履歴の Savepath</span><span class="sxs-lookup"><span data-stu-id="e4f2b-230">-HistorySavePath</span></span>

<span data-ttu-id="e4f2b-231">履歴を保存するファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-231">Specifies the path to the file where history is saved.</span></span> <span data-ttu-id="e4f2b-232">Windows または Windows 以外のプラットフォームを実行しているコンピューターでは、別の場所にファイルが保存されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-232">Computers running Windows or non-Windows platforms store the file in different locations.</span></span> <span data-ttu-id="e4f2b-233">ファイル名は変数に格納され `$($host.Name)_history.txt` ます。たとえば、のように `ConsoleHost_history.txt` なります。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-233">The filename is stored in a variable `$($host.Name)_history.txt`, for example `ConsoleHost_history.txt`.</span></span>

<span data-ttu-id="e4f2b-234">このパラメーターを使用しない場合、既定のパスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-234">If you don't use this parameter, the default path is as follows:</span></span>

<span data-ttu-id="e4f2b-235">**Windows**</span><span class="sxs-lookup"><span data-stu-id="e4f2b-235">**Windows**</span></span>

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

<span data-ttu-id="e4f2b-236">**Windows 以外**</span><span class="sxs-lookup"><span data-stu-id="e4f2b-236">**non-Windows**</span></span>

`$env:XDG_DATA_HOME/powershell/PSReadLine\$($host.Name)_history.txt`

`$env:HOME/.local/share/powershell/PSReadLine\$($host.Name)_history.txt`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A file named $($host.Name)_history.txt in $env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine on Windows and $env:XDG_DATA_HOME/powershell/PSReadLine or $env:HOME/.local/share/powershell/PSReadLine on non-Windows platforms
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-237">-履歴の Savestyle</span><span class="sxs-lookup"><span data-stu-id="e4f2b-237">-HistorySaveStyle</span></span>

<span data-ttu-id="e4f2b-238">**Psreadline** が履歴を保存する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-238">Specifies how **PSReadLine** saves history.</span></span>

<span data-ttu-id="e4f2b-239">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-239">Valid values are as follows:</span></span>

- <span data-ttu-id="e4f2b-240">**Saveincrementally**: 各コマンドが実行された後に履歴を保存し、PowerShell の複数のインスタンス間で共有します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-240">**SaveIncrementally**: Save history after each command is executed and share across multiple instances of PowerShell.</span></span>
- <span data-ttu-id="e4f2b-241">**Saveatexit**: PowerShell の終了時に履歴ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-241">**SaveAtExit**: Append history file when PowerShell exits.</span></span>
- <span data-ttu-id="e4f2b-242">**Savは**、履歴ファイルを使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-242">**SaveNothing**: Don't use a history file.</span></span>

```yaml
Type: Microsoft.PowerShell.HistorySaveStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SaveIncrementally
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-243">-HistorySearchCaseSensitive</span><span class="sxs-lookup"><span data-stu-id="e4f2b-243">-HistorySearchCaseSensitive</span></span>

<span data-ttu-id="e4f2b-244">**ReverseSearchHistory** や **history search後方** などの関数で、履歴検索で大文字と小文字を区別することを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-244">Specifies that history searching is case-sensitive in functions like **ReverseSearchHistory** or **HistorySearchBackward**.</span></span>

<span data-ttu-id="e4f2b-245">既定では、global **PSConsoleReadLineOptions** オブジェクトの **HistorySearchCaseSensitive** プロパティはに設定されて `False` います。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-245">By default, the **HistorySearchCaseSensitive** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="e4f2b-246">この **Switchparameter** を使用して、プロパティ値をに設定し `True` ます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-246">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="e4f2b-247">プロパティの値を変更するには、次のように **Switchparameter** の値を指定する必要があります `-HistorySearchCaseSensitive:$False` 。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-247">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCaseSensitive:$False`.</span></span>

<span data-ttu-id="e4f2b-248">次のコマンドを使用して、プロパティ値を直接設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-248">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).HistorySearchCaseSensitive = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-249">-HistorySearchCursorMovesToEnd</span><span class="sxs-lookup"><span data-stu-id="e4f2b-249">-HistorySearchCursorMovesToEnd</span></span>

<span data-ttu-id="e4f2b-250">は、検索を使用して、履歴から読み込まれたコマンドの最後までカーソルが移動することを示します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-250">Indicates that the cursor moves to the end of commands that you load from history by using a search.</span></span>
<span data-ttu-id="e4f2b-251">このパラメーターをに設定すると `$False` 、上矢印または下矢印を押したときの位置にカーソルが置かれたままになります。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-251">When this parameter is set to `$False`, the cursor remains at the position it was when you pressed the up or down arrows.</span></span>

<span data-ttu-id="e4f2b-252">既定では、global **PSConsoleReadLineOptions** オブジェクトの **HistorySearchCursorMovesToEnd** プロパティはに設定されて `False` います。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-252">By default, the **HistorySearchCursorMovesToEnd** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="e4f2b-253">この **Switchparameter** を使用して、プロパティ値をに設定し `True` ます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-253">Using this **SwitchParameter** set the property value to `True`.</span></span> <span data-ttu-id="e4f2b-254">プロパティの値を変更するには、次のように **Switchparameter** の値を指定する必要があります `-HistorySearchCursorMovesToEnd:$False` 。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-254">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCursorMovesToEnd:$False`.</span></span>

<span data-ttu-id="e4f2b-255">次のコマンドを使用して、プロパティ値を直接設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-255">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).HistorySearchCursorMovesToEnd = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-256">-Maximumhistory Count</span><span class="sxs-lookup"><span data-stu-id="e4f2b-256">-MaximumHistoryCount</span></span>

<span data-ttu-id="e4f2b-257">**Psreadline** 履歴に保存するコマンドの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-257">Specifies the maximum number of commands to save in **PSReadLine** history.</span></span>

<span data-ttu-id="e4f2b-258">**Psreadline** 履歴は、PowerShell 履歴とは別のものです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-258">**PSReadLine** history is separate from PowerShell history.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-259">-MaximumKillRingCount</span><span class="sxs-lookup"><span data-stu-id="e4f2b-259">-MaximumKillRingCount</span></span>

<span data-ttu-id="e4f2b-260">Kill ring に格納される項目の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-260">Specifies the maximum number of items stored in the kill ring.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-261">-PromptText</span><span class="sxs-lookup"><span data-stu-id="e4f2b-261">-PromptText</span></span>

<span data-ttu-id="e4f2b-262">解析エラーが発生した場合、 **Psreadline** はプロンプトの一部を赤で変更します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-262">When there's a parse error, **PSReadLine** changes a part of the prompt red.</span></span> <span data-ttu-id="e4f2b-263">**Psreadline** は、プロンプトの一部の色だけを変更する方法を決定するために、prompt 関数を分析します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-263">**PSReadLine** analyzes your prompt function to determine how to change only the color of part of your prompt.</span></span> <span data-ttu-id="e4f2b-264">この分析は100% の信頼度ではありません。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-264">This analysis isn't 100% reliable.</span></span>

<span data-ttu-id="e4f2b-265">**Psreadline** が予期しない方法でプロンプトを変更する場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-265">Use this option if **PSReadLine** is changing your prompt in unexpected ways.</span></span> <span data-ttu-id="e4f2b-266">末尾の空白を含めます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-266">Include any trailing whitespace.</span></span>

<span data-ttu-id="e4f2b-267">たとえば、プロンプト関数が次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-267">For example, if your prompt function looked like the following example:</span></span>

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

<span data-ttu-id="e4f2b-268">その後、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-268">Then set:</span></span>

`Set-PSReadLineOption -PromptText "# "`

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-269">-ShowToolTips ヒント</span><span class="sxs-lookup"><span data-stu-id="e4f2b-269">-ShowToolTips</span></span>

<span data-ttu-id="e4f2b-270">候補の候補を表示すると、入力候補の一覧にツールヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-270">When displaying possible completions, tooltips are shown in the list of completions.</span></span>

<span data-ttu-id="e4f2b-271">既定では、このオプションは有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-271">This option is enabled by default.</span></span> <span data-ttu-id="e4f2b-272">以前のバージョンの **Psreadline** では、このオプションは既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-272">This option wasn't enabled by default in prior versions of **PSReadLine**.</span></span> <span data-ttu-id="e4f2b-273">無効にするには、このオプションをに設定 `$False` します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-273">To disable, set this option to `$False`.</span></span>

<span data-ttu-id="e4f2b-274">既定では、グローバル **PSConsoleReadLineOptions** オブジェクトの **showtooltips ヒント** プロパティはに設定されてい `True` ます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-274">By default, the **ShowToolTips** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="e4f2b-275">この **Switchparameter** を使用して、プロパティ値をに設定し `True` ます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-275">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="e4f2b-276">プロパティ値を変更するには、次のように **Switchparameter** の値を指定する必要があります `-ShowToolTips:$False` 。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-276">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-ShowToolTips:$False`.</span></span>

<span data-ttu-id="e4f2b-277">次のコマンドを使用して、プロパティ値を直接設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-277">Using the following command, you can set the property value directly:</span></span>

`(Get-PSReadLineOption).ShowToolTips = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-278">-ViModeChangeHandler</span><span class="sxs-lookup"><span data-stu-id="e4f2b-278">-ViModeChangeHandler</span></span>

<span data-ttu-id="e4f2b-279">**Vimodeindicator** がに設定されている場合、指定されたスクリプトブロックは、モードが変更されるたびに `Script` 呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-279">When the **ViModeIndicator** is set to `Script`, the script block provided will be invoked every time the mode changes.</span></span> <span data-ttu-id="e4f2b-280">スクリプトブロックには、型の引数が1つ用意されてい `ViMode` ます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-280">The script block is provided one argument of type `ViMode`.</span></span>

<span data-ttu-id="e4f2b-281">このパラメーターは、PowerShell 7 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-281">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-282">-ViModeIndicator</span><span class="sxs-lookup"><span data-stu-id="e4f2b-282">-ViModeIndicator</span></span>

<span data-ttu-id="e4f2b-283">このオプションは、現在の **Vi** モードの視覚的な表示を設定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-283">This option sets the visual indication for the current **Vi** mode.</span></span> <span data-ttu-id="e4f2b-284">挿入モードまたはコマンドモード。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-284">Either insert mode or command mode.</span></span>

<span data-ttu-id="e4f2b-285">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-285">The valid values are as follows:</span></span>

- <span data-ttu-id="e4f2b-286">**None**: 何も表示されません。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-286">**None**: There's no indication.</span></span>
- <span data-ttu-id="e4f2b-287">**プロンプト**: プロンプトの色が変更されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-287">**Prompt**: The prompt changes color.</span></span>
- <span data-ttu-id="e4f2b-288">**カーソル**: カーソルのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-288">**Cursor**: The cursor changes size.</span></span>
- <span data-ttu-id="e4f2b-289">**スクリプト**: ユーザーが指定したテキストが印刷されます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-289">**Script**: User-specified text is printed.</span></span>

```yaml
Type: Microsoft.PowerShell.ViModeStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-290">-WordDelimiters</span><span class="sxs-lookup"><span data-stu-id="e4f2b-290">-WordDelimiters</span></span>

<span data-ttu-id="e4f2b-291">**Forwardword** や、入力 **候補** などの関数の単語を区切る文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-291">Specifies the characters that delimit words for functions like **ForwardWord** or **KillWord**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: ;:,.[]{}()/\|^&*-=+'"---
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-292">-PredictionSource</span><span class="sxs-lookup"><span data-stu-id="e4f2b-292">-PredictionSource</span></span>

<span data-ttu-id="e4f2b-293">予測候補を取得するための PSReadLine のソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-293">Specifies the source for PSReadLine to get predictive suggestions.</span></span>

<span data-ttu-id="e4f2b-294">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-294">Valid values are:</span></span>

- <span data-ttu-id="e4f2b-295">**None** -予測 IntelliSense 機能を無効にします (既定)。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-295">**None** - disable the predictive IntelliSense feature (default).</span></span>
<span data-ttu-id="e4f2b-296">-\`**履歴** -予測 IntelliSense 機能を有効にし、唯一のソースとして psreadline 履歴を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-296">-\`**History** - enable the predictive IntelliSense feature and use the PSReadLine history as the only source.</span></span>
- <span data-ttu-id="e4f2b-297">**プラグイン** -予測 IntelliSense 機能を有効にし、唯一の `CommandPrediction` ソースとしてプラグイン () を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-297">**Plugin** - enable the predictive IntelliSense feature and use the plugins (`CommandPrediction`) as the only source.</span></span> <span data-ttu-id="e4f2b-298">この値は PSReadLine 2.2.0 で追加されました</span><span class="sxs-lookup"><span data-stu-id="e4f2b-298">This value was added in PSReadLine 2.2.0</span></span>
- <span data-ttu-id="e4f2b-299">履歴と **プラグイン**-予測 IntelliSense 機能を有効にし、ソースとして履歴とプラグインの両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-299">**HistoryAndPlugin** - enable the predictive IntelliSense feature and use both history and plugin as the sources.</span></span> <span data-ttu-id="e4f2b-300">この値は PSReadLine 2.2.0 で追加されました</span><span class="sxs-lookup"><span data-stu-id="e4f2b-300">This value was added in PSReadLine 2.2.0</span></span>

```yaml
Type: Microsoft.PowerShell.PredictionSource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-301">-PredictionViewStyle</span><span class="sxs-lookup"><span data-stu-id="e4f2b-301">-PredictionViewStyle</span></span>

<span data-ttu-id="e4f2b-302">予測テキストの表示スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-302">Sets the style for the display of the predictive text.</span></span> <span data-ttu-id="e4f2b-303">既定値は **InlineView** です。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-303">The default is **InlineView**.</span></span>

- <span data-ttu-id="e4f2b-304">**InlineView** -魚と zsh のような、今日の既存のスタイルです。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-304">**InlineView** - the style as existing today, similar as in fish shell and zsh.</span></span> <span data-ttu-id="e4f2b-305">(既定値)。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-305">(default)</span></span>
- <span data-ttu-id="e4f2b-306">**ListView** -提案はドロップダウンリストに表示され、ユーザーは <kbd>Uparrow</kbd> と <kbd>downarrow</kbd>を使用して選択できます。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-306">**ListView** - suggestions are rendered in a drop down list, and users can select using <kbd>UpArrow</kbd> and <kbd>DownArrow</kbd>.</span></span>

<span data-ttu-id="e4f2b-307">このパラメーターは PSReadLine 2.2.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-307">This parameter was added in PSReadLine 2.2.0</span></span>

```yaml
Type: Microsoft.PowerShell.PredictionViewStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineView
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4f2b-308">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4f2b-308">CommonParameters</span></span>

<span data-ttu-id="e4f2b-309">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-309">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4f2b-310">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-310">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4f2b-311">入力</span><span class="sxs-lookup"><span data-stu-id="e4f2b-311">Inputs</span></span>

### <span data-ttu-id="e4f2b-312">なし</span><span class="sxs-lookup"><span data-stu-id="e4f2b-312">None</span></span>

<span data-ttu-id="e4f2b-313">パイプを使用してオブジェクトを `Set-PSReadLineOption.`</span><span class="sxs-lookup"><span data-stu-id="e4f2b-313">You cannot pipe objects to `Set-PSReadLineOption.`</span></span>

## <span data-ttu-id="e4f2b-314">出力</span><span class="sxs-lookup"><span data-stu-id="e4f2b-314">Outputs</span></span>

### <span data-ttu-id="e4f2b-315">なし</span><span class="sxs-lookup"><span data-stu-id="e4f2b-315">None</span></span>

<span data-ttu-id="e4f2b-316">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-316">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e4f2b-317">メモ</span><span class="sxs-lookup"><span data-stu-id="e4f2b-317">Notes</span></span>

## <span data-ttu-id="e4f2b-318">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e4f2b-318">Related links</span></span>

[<span data-ttu-id="e4f2b-319">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="e4f2b-319">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

[<span data-ttu-id="e4f2b-320">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="e4f2b-320">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="e4f2b-321">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="e4f2b-321">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="e4f2b-322">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="e4f2b-322">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="e4f2b-323">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="e4f2b-323">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

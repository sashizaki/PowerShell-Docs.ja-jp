---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: d3e3ee1dcde36ac09f8441aff7ce48797cf48b5f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214896"
---
# <span data-ttu-id="8ed3e-103">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="8ed3e-103">Set-PSReadLineOption</span></span>

## <span data-ttu-id="8ed3e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8ed3e-104">Synopsis</span></span>
<span data-ttu-id="8ed3e-105">**Psreadline** でのコマンドライン編集の動作をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-105">Customizes the behavior of command line editing in **PSReadLine** .</span></span>

## <span data-ttu-id="8ed3e-106">構文</span><span class="sxs-lookup"><span data-stu-id="8ed3e-106">Syntax</span></span>

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-Colors <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="8ed3e-107">説明</span><span class="sxs-lookup"><span data-stu-id="8ed3e-107">Description</span></span>

<span data-ttu-id="8ed3e-108">コマンドラインを編集しているときに、コマンドレットによって `Set-PSReadLineOption` **psreadline** モジュールの動作がカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-108">The `Set-PSReadLineOption` cmdlet customizes the behavior of the **PSReadLine** module when you're editing the command line.</span></span> <span data-ttu-id="8ed3e-109">**Psreadline** の設定を表示するには、を使用し `Get-PSReadLineOption` ます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-109">To view the **PSReadLine** settings, use `Get-PSReadLineOption`.</span></span>

## <span data-ttu-id="8ed3e-110">例</span><span class="sxs-lookup"><span data-stu-id="8ed3e-110">Examples</span></span>

### <span data-ttu-id="8ed3e-111">例 1: 前景色と背景色を設定する</span><span class="sxs-lookup"><span data-stu-id="8ed3e-111">Example 1: Set foreground and background colors</span></span>

<span data-ttu-id="8ed3e-112">この例では、 **Psreadline** を設定して、 **コメント** トークンを緑色の前景テキストがグレーの背景に表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-112">This example sets **PSReadLine** to display the **Comment** token with green foreground text on a gray background.</span></span> <span data-ttu-id="8ed3e-113">この例で使用されているエスケープシーケンスでは、 **32** は前景色を表し、 **47** は背景色を表します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-113">In the escape sequence used in the example, **32** represents the foreground color and **47** represents the background color.</span></span>

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

<span data-ttu-id="8ed3e-114">前景テキストの色のみを設定するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-114">You can choose to set only a foreground text color.</span></span> <span data-ttu-id="8ed3e-115">たとえば、 **コメント** トークンの背景色が明るい緑で表示さ ``"Comment"="`e[92m"`` れます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-115">For example, a bright green foreground text color for the **Comment** token: ``"Comment"="`e[92m"``.</span></span>

### <span data-ttu-id="8ed3e-116">例 2: ベルのスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="8ed3e-116">Example 2: Set bell style</span></span>

<span data-ttu-id="8ed3e-117">この例では、 **Psreadline** は、ユーザーに注意する必要があるエラーまたは条件に応答します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-117">In this example, **PSReadLine** will respond to errors or conditions that require user attention.</span></span>
<span data-ttu-id="8ed3e-118">**ベル Lstyle** は、1221 Hz の60ミリ秒で可聴ビープ音を発するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-118">The **BellStyle** is set to emit an audible beep at 1221 Hz for 60 ms.</span></span>

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> <span data-ttu-id="8ed3e-119">この機能は、プラットフォーム上のすべてのホストで動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-119">This feature may not work in all hosts on platforms.</span></span>

### <span data-ttu-id="8ed3e-120">例 3: 複数のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="8ed3e-120">Example 3: Set multiple options</span></span>

<span data-ttu-id="8ed3e-121">`Set-PSReadLineOption` ハッシュテーブルを使用して複数のオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-121">`Set-PSReadLineOption` can set multiple options with a hash table.</span></span>

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

<span data-ttu-id="8ed3e-122">ハッシュテーブルによって `$PSReadLineOptions` 、キーと値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-122">The `$PSReadLineOptions` hash table sets the keys and values.</span></span> <span data-ttu-id="8ed3e-123">`Set-PSReadLineOption` では、キーと値を使用して `@PSReadLineOptions` **psreadline** オプションを更新します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-123">`Set-PSReadLineOption` uses the keys and values with `@PSReadLineOptions` to update the **PSReadLine** options.</span></span>

<span data-ttu-id="8ed3e-124">ハッシュテーブル名を入力したキーと値は、 `$PSReadLineOptions` PowerShell コマンドラインで表示できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-124">You can view the keys and values entering the hash table name, `$PSReadLineOptions` on the PowerShell command line.</span></span>

### <span data-ttu-id="8ed3e-125">例 4: 複数の色のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="8ed3e-125">Example 4: Set multiple color options</span></span>

<span data-ttu-id="8ed3e-126">この例では、1つのコマンドで複数の color 値を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-126">This example shows how to set more than one color value in a single command.</span></span>

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

### <span data-ttu-id="8ed3e-127">例 5: 複数の型の色の値を設定する</span><span class="sxs-lookup"><span data-stu-id="8ed3e-127">Example 5: Set color values for multiple types</span></span>

<span data-ttu-id="8ed3e-128">この例では、 **Psreadline** に表示されるトークンの色を設定する方法について、3種類の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-128">This example shows three different methods for how to set the color of tokens displayed in **PSReadLine** .</span></span>

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

### <span data-ttu-id="8ed3e-129">例 6: ViModeChangeHandler を使用して Vi モードの変更を表示する</span><span class="sxs-lookup"><span data-stu-id="8ed3e-129">Example 6: Use ViModeChangeHandler to display Vi mode changes</span></span>

<span data-ttu-id="8ed3e-130">この例では、 **Vi** モードの変更に応じて、VT escape のカーソル変更を出力します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-130">This example emits a cursor change VT escape in response to a **Vi** mode change.</span></span>

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

<span data-ttu-id="8ed3e-131">**Onvimodechange** 関数は、 **Vi** モード (insert および command) のカーソルオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-131">The **OnViModeChange** function sets the cursor options for the **Vi** modes: insert and command.</span></span>
<span data-ttu-id="8ed3e-132">**ViModeChangeHandler** は、プロバイダーを使用し `Function:` て、スクリプトブロックオブジェクトとして **onvimodechange** を参照します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-132">**ViModeChangeHandler** uses the `Function:` provider to reference **OnViModeChange** as a script block object.</span></span>

<span data-ttu-id="8ed3e-133">詳細については、「[about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-133">For more information, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <span data-ttu-id="8ed3e-134">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ed3e-134">Parameters</span></span>

### <span data-ttu-id="8ed3e-135">-Addtohistory ハンドラー</span><span class="sxs-lookup"><span data-stu-id="8ed3e-135">-AddToHistoryHandler</span></span>

<span data-ttu-id="8ed3e-136">**Psreadline** 履歴に追加するコマンドを制御する **ScriptBlock** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-136">Specifies a **ScriptBlock** that controls which commands get added to **PSReadLine** history.</span></span>

<span data-ttu-id="8ed3e-137">**ScriptBlock** は、コマンドラインを入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-137">The **ScriptBlock** receives the command line as input.</span></span> <span data-ttu-id="8ed3e-138">**ScriptBlock** がを返した場合は、 `$True` コマンドラインが履歴に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-138">If the **ScriptBlock** returns `$True`, the command line is added to the history.</span></span>

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

### <span data-ttu-id="8ed3e-139">-AnsiEscapeTimeout</span><span class="sxs-lookup"><span data-stu-id="8ed3e-139">-AnsiEscapeTimeout</span></span>

<span data-ttu-id="8ed3e-140">このオプションは、入力がリダイレクトされるときのウィンドウに固有です。たとえば、またはで実行されている場合です `tmux` `screen` 。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-140">This option is specific to Windows when input is redirected, for example, when running under `tmux` or `screen`.</span></span>

<span data-ttu-id="8ed3e-141">Windows でのリダイレクト入力では、多くのキーがエスケープ文字で始まる文字のシーケンスとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-141">With redirected input on Windows, many keys are sent as a sequence of characters starting with the escape character.</span></span> <span data-ttu-id="8ed3e-142">1つのエスケープ文字の後により多くの文字と有効なエスケープシーケンスを区別することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-142">It's impossible to distinguish between a single escape character followed by more characters and a valid escape sequence.</span></span>

<span data-ttu-id="8ed3e-143">ターミナルは、ユーザーの種類よりも高速に文字を送信できることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-143">The assumption is that the terminal can send the characters faster than a user types.</span></span> <span data-ttu-id="8ed3e-144">**Psreadline** は、このタイムアウトを待機してから、完全なエスケープシーケンスを受け取っています。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-144">**PSReadLine** waits for this timeout before concluding that it has received a complete escape sequence.</span></span>

<span data-ttu-id="8ed3e-145">入力時にランダムまたは予期しない文字が表示する場合は、このタイムアウトを調整できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-145">If you see random or unexpected characters when you type, you can adjust this timeout.</span></span>

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

### <span data-ttu-id="8ed3e-146">-ベル Lstyle</span><span class="sxs-lookup"><span data-stu-id="8ed3e-146">-BellStyle</span></span>

<span data-ttu-id="8ed3e-147">**Psreadline** がさまざまなエラーやあいまいな状況にどのように応答するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-147">Specifies how **PSReadLine** responds to various error and ambiguous conditions.</span></span>

<span data-ttu-id="8ed3e-148">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-148">The valid values are as follows:</span></span>

- <span data-ttu-id="8ed3e-149">**可聴** : 短いビープ音。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-149">**Audible** : A short beep.</span></span>
- <span data-ttu-id="8ed3e-150">**ビジュアル** : テキストが短時間点滅します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-150">**Visual** : Text flashes briefly.</span></span>
- <span data-ttu-id="8ed3e-151">**None** : フィードバックがありません。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-151">**None** : No feedback.</span></span>

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

### <span data-ttu-id="8ed3e-152">-色</span><span class="sxs-lookup"><span data-stu-id="8ed3e-152">-Colors</span></span>

<span data-ttu-id="8ed3e-153">**Colors** パラメーターは、 **psreadline** によって使用されるさまざまな色を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-153">The **Colors** parameter specifies various colors used by **PSReadLine** .</span></span>

<span data-ttu-id="8ed3e-154">引数は、キーが色を指定する要素と値を指定するハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-154">The argument is a hash table where the keys specify which element and the values specify the color.</span></span>
<span data-ttu-id="8ed3e-155">詳細については、「 [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-155">For more information, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="8ed3e-156">色には、 **ConsoleColor** の値か、 `[ConsoleColor]::Red` 有効な ANSI エスケープシーケンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-156">Colors can be either a value from **ConsoleColor** , for example `[ConsoleColor]::Red`, or a valid ANSI escape sequence.</span></span> <span data-ttu-id="8ed3e-157">有効なエスケープシーケンスは、ターミナルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-157">Valid escape sequences depend on your terminal.</span></span> <span data-ttu-id="8ed3e-158">PowerShell 5.0 では、赤いテキストのエスケープシーケンスの例はです `$([char]0x1b)[91m` 。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-158">In PowerShell 5.0, an example escape sequence for red text is `$([char]0x1b)[91m`.</span></span> <span data-ttu-id="8ed3e-159">PowerShell 6 以降では、同じエスケープシーケンスは `` `e[91m`` です。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-159">In PowerShell 6 and above, the same escape sequence is `` `e[91m``.</span></span> <span data-ttu-id="8ed3e-160">次の型を含むその他のエスケープシーケンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-160">You can specify other escape sequences including the following types:</span></span>

- <span data-ttu-id="8ed3e-161">256色</span><span class="sxs-lookup"><span data-stu-id="8ed3e-161">256 color</span></span>
- <span data-ttu-id="8ed3e-162">24ビットカラー</span><span class="sxs-lookup"><span data-stu-id="8ed3e-162">24-bit color</span></span>
- <span data-ttu-id="8ed3e-163">前景、背景、または両方</span><span class="sxs-lookup"><span data-stu-id="8ed3e-163">Foreground, background, or both</span></span>
- <span data-ttu-id="8ed3e-164">反転、太字</span><span class="sxs-lookup"><span data-stu-id="8ed3e-164">Inverse, bold</span></span>

<span data-ttu-id="8ed3e-165">ANSI カラーコードの詳細については、Wikipedia の「 [ansi escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-165">For more information about ANSI color codes, see [ANSI escape code](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.</span></span>

<span data-ttu-id="8ed3e-166">有効なキーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-166">The valid keys include:</span></span>

- <span data-ttu-id="8ed3e-167">**続行 ationprompt** : 継続プロンプトの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-167">**ContinuationPrompt** : The color of the continuation prompt.</span></span>
- <span data-ttu-id="8ed3e-168">**強調** : 強調色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-168">**Emphasis** : The emphasis color.</span></span> <span data-ttu-id="8ed3e-169">たとえば、履歴を検索するときに一致するテキストです。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-169">For example, the matching text when searching history.</span></span>
- <span data-ttu-id="8ed3e-170">**エラー** : エラーの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-170">**Error** : The error color.</span></span> <span data-ttu-id="8ed3e-171">たとえば、プロンプトでを入力します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-171">For example, in the prompt.</span></span>
- <span data-ttu-id="8ed3e-172">**Selection** : メニューの選択または選択されたテキストを強調表示する色です。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-172">**Selection** : The color to highlight the menu selection or selected text.</span></span>
- <span data-ttu-id="8ed3e-173">**既定** 値: 既定のトークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-173">**Default** : The default token color.</span></span>
- <span data-ttu-id="8ed3e-174">**Comment** : コメントトークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-174">**Comment** : The comment token color.</span></span>
- <span data-ttu-id="8ed3e-175">**キーワード** : キーワードトークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-175">**Keyword** : The keyword token color.</span></span>
- <span data-ttu-id="8ed3e-176">**String** : 文字列トークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-176">**String** : The string token color.</span></span>
- <span data-ttu-id="8ed3e-177">**Operator** : 演算子のトークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-177">**Operator** : The operator token color.</span></span>
- <span data-ttu-id="8ed3e-178">**Variable** : 変数のトークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-178">**Variable** : The variable token color.</span></span>
- <span data-ttu-id="8ed3e-179">**Command** : コマンドトークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-179">**Command** : The command token color.</span></span>
- <span data-ttu-id="8ed3e-180">**パラメーター** : パラメーターのトークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-180">**Parameter** : The parameter token color.</span></span>
- <span data-ttu-id="8ed3e-181">**Type** : 型トークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-181">**Type** : The type token color.</span></span>
- <span data-ttu-id="8ed3e-182">**Number** : 数値トークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-182">**Number** : The number token color.</span></span>
- <span data-ttu-id="8ed3e-183">**メンバー** : メンバー名トークンの色。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-183">**Member** : The member name token color.</span></span>

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

### <span data-ttu-id="8ed3e-184">-CommandValidationHandler</span><span class="sxs-lookup"><span data-stu-id="8ed3e-184">-CommandValidationHandler</span></span>

<span data-ttu-id="8ed3e-185">**Validateandacceptline** から呼び出される **ScriptBlock** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-185">Specifies a **ScriptBlock** that is called from **ValidateAndAcceptLine** .</span></span> <span data-ttu-id="8ed3e-186">例外がスローされた場合、検証は失敗し、エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-186">If an exception is thrown, validation fails and the error is reported.</span></span>

<span data-ttu-id="8ed3e-187">例外をスローする前に、検証ハンドラーはエラーの発生時にカーソルを置いて、簡単に修正できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-187">Before throwing an exception, the validation handler can place the cursor at the point of the error to make it easier to fix.</span></span> <span data-ttu-id="8ed3e-188">検証ハンドラーは、などのコマンドラインを変更して、一般的な入力ミスを修正することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-188">A validation handler can also change the command line, such as to correct common typographical errors.</span></span>

<span data-ttu-id="8ed3e-189">**Validateandacceptline** を使用すると、動作しないコマンドで履歴が乱雑にならないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-189">**ValidateAndAcceptLine** is used to avoid cluttering your history with commands that can't work.</span></span>

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

### <span data-ttu-id="8ed3e-190">-補完 Queryitems</span><span class="sxs-lookup"><span data-stu-id="8ed3e-190">-CompletionQueryItems</span></span>

<span data-ttu-id="8ed3e-191">プロンプトを表示せずに表示される完了項目の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-191">Specifies the maximum number of completion items that are shown without prompting.</span></span>

<span data-ttu-id="8ed3e-192">表示する項目の数がこの値よりも大きい場合、 **Psreadline** は、完了項目を表示する前に、 **[はい/いいえ]** を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-192">If the number of items to show is greater than this value, **PSReadLine** prompts **yes/no** before displaying the completion items.</span></span>

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

### <span data-ttu-id="8ed3e-193">-続行 Ationprompt</span><span class="sxs-lookup"><span data-stu-id="8ed3e-193">-ContinuationPrompt</span></span>

<span data-ttu-id="8ed3e-194">複数行の入力が入力された場合に、後続の行の先頭に表示される文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-194">Specifies the string displayed at the beginning of the subsequent lines when multi-line input is entered.</span></span> <span data-ttu-id="8ed3e-195">既定値は2倍大きい記号 ( `>>` ) です。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-195">The default is double greater-than signs (`>>`).</span></span> <span data-ttu-id="8ed3e-196">空の文字列は有効です。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-196">An empty string is valid.</span></span>

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

### <span data-ttu-id="8ed3e-197">-有効期間</span><span class="sxs-lookup"><span data-stu-id="8ed3e-197">-DingDuration</span></span>

<span data-ttu-id="8ed3e-198">**ベル Lstyle** が **可聴** に設定されている場合のビープ音の期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-198">Specifies the duration of the beep when **BellStyle** is set to **Audible** .</span></span>

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

### <span data-ttu-id="8ed3e-199">-外調</span><span class="sxs-lookup"><span data-stu-id="8ed3e-199">-DingTone</span></span>

<span data-ttu-id="8ed3e-200">**ベル Lstyle** が **可聴** に設定されている場合のビープ音のトーンをヘルツ (hz) で指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-200">Specifies the tone in Hertz (Hz) of the beep when **BellStyle** is set to **Audible** .</span></span>

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

### <span data-ttu-id="8ed3e-201">-EditMode</span><span class="sxs-lookup"><span data-stu-id="8ed3e-201">-EditMode</span></span>

<span data-ttu-id="8ed3e-202">コマンドライン編集モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-202">Specifies the command line editing mode.</span></span> <span data-ttu-id="8ed3e-203">このパラメーターを使用すると、によって設定されたキーバインドがリセットさ `Set-PSReadLineKeyHandler` れます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-203">Using this parameter resets any key bindings set by `Set-PSReadLineKeyHandler`.</span></span>

<span data-ttu-id="8ed3e-204">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-204">The valid values are as follows:</span></span>

- <span data-ttu-id="8ed3e-205">**Windows** : キーバインドは、PowerShell、cmd、および Visual Studio をエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-205">**Windows** : Key bindings emulate PowerShell, cmd, and Visual Studio.</span></span>
- <span data-ttu-id="8ed3e-206">**Emacs** : キーバインドは Bash または Emacs をエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-206">**Emacs** : Key bindings emulate Bash or Emacs.</span></span>
- <span data-ttu-id="8ed3e-207">**Vi** : キーバインドは vi をエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-207">**Vi** : Key bindings emulate Vi.</span></span>

<span data-ttu-id="8ed3e-208">`Get-PSReadLineKeyHandler`現在構成されている **EditMode** のキーバインドを表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-208">Use `Get-PSReadLineKeyHandler` to see the key bindings for the currently configured **EditMode** .</span></span>

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

### <span data-ttu-id="8ed3e-209">-ExtraPromptLineCount</span><span class="sxs-lookup"><span data-stu-id="8ed3e-209">-ExtraPromptLineCount</span></span>

<span data-ttu-id="8ed3e-210">余分な行の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-210">Specifies the number of extra lines.</span></span>

<span data-ttu-id="8ed3e-211">プロンプトが複数行にわたっている場合は、このパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-211">If your prompt spans more than one line, specify a value for this parameter.</span></span> <span data-ttu-id="8ed3e-212">このオプションは、出力を表示した後に **Psreadline** がプロンプトを表示するときに余分な行を使用できるようにする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-212">Use this option when you want extra lines to be available when **PSReadLine** displays the prompt after showing some output.</span></span> <span data-ttu-id="8ed3e-213">たとえば、 **Psreadline** は入力候補の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-213">For example, **PSReadLine** returns a list of completions.</span></span>

<span data-ttu-id="8ed3e-214">このオプションは、以前のバージョンの **Psreadline** の場合よりも小さくする必要がありますが、関数を使用するときに便利です `InvokePrompt` 。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-214">This option is needed less than in previous versions of **PSReadLine** , but is useful when the `InvokePrompt` function is used.</span></span>

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

### <span data-ttu-id="8ed3e-215">-履歴の重複</span><span class="sxs-lookup"><span data-stu-id="8ed3e-215">-HistoryNoDuplicates</span></span>

<span data-ttu-id="8ed3e-216">このオプションは、再呼び出しの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-216">This option controls the recall behavior.</span></span> <span data-ttu-id="8ed3e-217">重複するコマンドは、履歴ファイルにまだ追加されています。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-217">Duplicate commands are still added to the history file.</span></span>
<span data-ttu-id="8ed3e-218">このオプションを設定すると、コマンドの呼び出し時に最新の呼び出しのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-218">When this option is set, only the most recent invocation appears when recalling commands.</span></span> <span data-ttu-id="8ed3e-219">再呼び出し中に順序を維持するために、繰り返しコマンドが履歴に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-219">Repeated commands are added to history to preserve ordering during recall.</span></span> <span data-ttu-id="8ed3e-220">ただし、通常は、履歴をリコールまたは検索するときにコマンドを複数回表示したくはありません。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-220">However, you typically don't want to see the command multiple times when recalling or searching the history.</span></span>

<span data-ttu-id="8ed3e-221">既定では、グローバル **PSConsoleReadLineOptions** オブジェクトの **履歴の no重複** プロパティはに設定され `True` ます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-221">By default, the **HistoryNoDuplicates** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="8ed3e-222">この **Switchparameter** を使用して、プロパティ値をに設定し `True` ます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-222">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="8ed3e-223">プロパティ値を変更するには、次のように **Switchparameter** の値を指定する必要があります `-HistoryNoDuplicates:$False` 。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-223">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-HistoryNoDuplicates:$False`.</span></span>

<span data-ttu-id="8ed3e-224">次のコマンドを使用して、プロパティ値を直接設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-224">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="8ed3e-225">-履歴の Savepath</span><span class="sxs-lookup"><span data-stu-id="8ed3e-225">-HistorySavePath</span></span>

<span data-ttu-id="8ed3e-226">履歴を保存するファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-226">Specifies the path to the file where history is saved.</span></span> <span data-ttu-id="8ed3e-227">Windows または Windows 以外のプラットフォームを実行しているコンピューターでは、別の場所にファイルが保存されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-227">Computers running Windows or non-Windows platforms store the file in different locations.</span></span> <span data-ttu-id="8ed3e-228">ファイル名は変数に格納され `$($host.Name)_history.txt` ます。たとえば、のように `ConsoleHost_history.txt` なります。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-228">The filename is stored in a variable `$($host.Name)_history.txt`, for example `ConsoleHost_history.txt`.</span></span>

<span data-ttu-id="8ed3e-229">このパラメーターを使用しない場合、既定のパスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-229">If you don't use this parameter, the default path is as follows:</span></span>

<span data-ttu-id="8ed3e-230">**Windows**</span><span class="sxs-lookup"><span data-stu-id="8ed3e-230">**Windows**</span></span>

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

<span data-ttu-id="8ed3e-231">**Windows 以外**</span><span class="sxs-lookup"><span data-stu-id="8ed3e-231">**non-Windows**</span></span>

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

### <span data-ttu-id="8ed3e-232">-履歴の Savestyle</span><span class="sxs-lookup"><span data-stu-id="8ed3e-232">-HistorySaveStyle</span></span>

<span data-ttu-id="8ed3e-233">**Psreadline** が履歴を保存する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-233">Specifies how **PSReadLine** saves history.</span></span>

<span data-ttu-id="8ed3e-234">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-234">Valid values are as follows:</span></span>

- <span data-ttu-id="8ed3e-235">**Saveincrementally** : 各コマンドが実行された後に履歴を保存し、PowerShell の複数のインスタンス間で共有します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-235">**SaveIncrementally** : Save history after each command is executed and share across multiple instances of PowerShell.</span></span>
- <span data-ttu-id="8ed3e-236">**Saveatexit** : PowerShell の終了時に履歴ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-236">**SaveAtExit** : Append history file when PowerShell exits.</span></span>
- <span data-ttu-id="8ed3e-237">**Savは** 、履歴ファイルを使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-237">**SaveNothing** : Don't use a history file.</span></span>

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

### <span data-ttu-id="8ed3e-238">-HistorySearchCaseSensitive</span><span class="sxs-lookup"><span data-stu-id="8ed3e-238">-HistorySearchCaseSensitive</span></span>

<span data-ttu-id="8ed3e-239">**ReverseSearchHistory** や **history search後方** などの関数で、履歴検索で大文字と小文字を区別することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-239">Specifies that history searching is case-sensitive in functions like **ReverseSearchHistory** or **HistorySearchBackward** .</span></span>

<span data-ttu-id="8ed3e-240">既定では、global **PSConsoleReadLineOptions** オブジェクトの **HistorySearchCaseSensitive** プロパティはに設定されて `False` います。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-240">By default, the **HistorySearchCaseSensitive** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="8ed3e-241">この **Switchparameter** を使用して、プロパティ値をに設定し `True` ます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-241">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="8ed3e-242">プロパティの値を変更するには、次のように **Switchparameter** の値を指定する必要があります `-HistorySearchCaseSensitive:$False` 。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-242">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCaseSensitive:$False`.</span></span>

<span data-ttu-id="8ed3e-243">次のコマンドを使用して、プロパティ値を直接設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-243">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="8ed3e-244">-HistorySearchCursorMovesToEnd</span><span class="sxs-lookup"><span data-stu-id="8ed3e-244">-HistorySearchCursorMovesToEnd</span></span>

<span data-ttu-id="8ed3e-245">は、検索を使用して、履歴から読み込まれたコマンドの最後までカーソルが移動することを示します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-245">Indicates that the cursor moves to the end of commands that you load from history by using a search.</span></span>
<span data-ttu-id="8ed3e-246">このパラメーターをに設定すると `$False` 、上矢印または下矢印を押したときの位置にカーソルが置かれたままになります。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-246">When this parameter is set to `$False`, the cursor remains at the position it was when you pressed the up or down arrows.</span></span>

<span data-ttu-id="8ed3e-247">既定では、global **PSConsoleReadLineOptions** オブジェクトの **HistorySearchCursorMovesToEnd** プロパティはに設定されて `False` います。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-247">By default, the **HistorySearchCursorMovesToEnd** property of the global **PSConsoleReadLineOptions** object is set to `False`.</span></span> <span data-ttu-id="8ed3e-248">この **Switchparameter** を使用して、プロパティ値をに設定し `True` ます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-248">Using this **SwitchParameter** set the property value to `True`.</span></span> <span data-ttu-id="8ed3e-249">プロパティの値を変更するには、次のように **Switchparameter** の値を指定する必要があります `-HistorySearchCursorMovesToEnd:$False` 。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-249">To change the property value back, you must specify the value of the **SwitchParameter** as follows: `-HistorySearchCursorMovesToEnd:$False`.</span></span>

<span data-ttu-id="8ed3e-250">次のコマンドを使用して、プロパティ値を直接設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-250">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="8ed3e-251">-Maximumhistory Count</span><span class="sxs-lookup"><span data-stu-id="8ed3e-251">-MaximumHistoryCount</span></span>

<span data-ttu-id="8ed3e-252">**Psreadline** 履歴に保存するコマンドの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-252">Specifies the maximum number of commands to save in **PSReadLine** history.</span></span>

<span data-ttu-id="8ed3e-253">**Psreadline** 履歴は、PowerShell 履歴とは別のものです。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-253">**PSReadLine** history is separate from PowerShell history.</span></span>

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

### <span data-ttu-id="8ed3e-254">-MaximumKillRingCount</span><span class="sxs-lookup"><span data-stu-id="8ed3e-254">-MaximumKillRingCount</span></span>

<span data-ttu-id="8ed3e-255">Kill ring に格納される項目の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-255">Specifies the maximum number of items stored in the kill ring.</span></span>

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

### <span data-ttu-id="8ed3e-256">-PromptText</span><span class="sxs-lookup"><span data-stu-id="8ed3e-256">-PromptText</span></span>

<span data-ttu-id="8ed3e-257">解析エラーが発生した場合、 **Psreadline** はプロンプトの一部を赤で変更します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-257">When there's a parse error, **PSReadLine** changes a part of the prompt red.</span></span> <span data-ttu-id="8ed3e-258">**Psreadline** は、プロンプトの一部の色だけを変更する方法を決定するために、prompt 関数を分析します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-258">**PSReadLine** analyzes your prompt function to determine how to change only the color of part of your prompt.</span></span> <span data-ttu-id="8ed3e-259">この分析は100% の信頼度ではありません。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-259">This analysis isn't 100% reliable.</span></span>

<span data-ttu-id="8ed3e-260">**Psreadline** が予期しない方法でプロンプトを変更する場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-260">Use this option if **PSReadLine** is changing your prompt in unexpected ways.</span></span> <span data-ttu-id="8ed3e-261">末尾の空白を含めます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-261">Include any trailing whitespace.</span></span>

<span data-ttu-id="8ed3e-262">たとえば、プロンプト関数が次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-262">For example, if your prompt function looked like the following example:</span></span>

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

<span data-ttu-id="8ed3e-263">その後、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-263">Then set:</span></span>

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

### <span data-ttu-id="8ed3e-264">-ShowToolTips ヒント</span><span class="sxs-lookup"><span data-stu-id="8ed3e-264">-ShowToolTips</span></span>

<span data-ttu-id="8ed3e-265">候補の候補を表示すると、入力候補の一覧にツールヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-265">When displaying possible completions, tooltips are shown in the list of completions.</span></span>

<span data-ttu-id="8ed3e-266">このオプションは、既定で有効です。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-266">This option is enabled by default.</span></span> <span data-ttu-id="8ed3e-267">以前のバージョンの **Psreadline** では、このオプションは既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-267">This option wasn't enabled by default in prior versions of **PSReadLine** .</span></span> <span data-ttu-id="8ed3e-268">無効にするには、このオプションをに設定 `$False` します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-268">To disable, set this option to `$False`.</span></span>

<span data-ttu-id="8ed3e-269">既定では、グローバル **PSConsoleReadLineOptions** オブジェクトの **showtooltips ヒント** プロパティはに設定されてい `True` ます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-269">By default, the **ShowToolTips** property of the global **PSConsoleReadLineOptions** object is set to `True`.</span></span> <span data-ttu-id="8ed3e-270">この **Switchparameter** を使用して、プロパティ値をに設定し `True` ます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-270">Using this **SwitchParameter** sets the property value to `True`.</span></span> <span data-ttu-id="8ed3e-271">プロパティ値を変更するには、次のように **Switchparameter** の値を指定する必要があります `-ShowToolTips:$False` 。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-271">To change the property value, you must specify the value of the **SwitchParameter** as follows: `-ShowToolTips:$False`.</span></span>

<span data-ttu-id="8ed3e-272">次のコマンドを使用して、プロパティ値を直接設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-272">Using the following command, you can set the property value directly:</span></span>

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

### <span data-ttu-id="8ed3e-273">-ViModeChangeHandler</span><span class="sxs-lookup"><span data-stu-id="8ed3e-273">-ViModeChangeHandler</span></span>

<span data-ttu-id="8ed3e-274">**Vimodeindicator** がに設定されている場合、指定されたスクリプトブロックは、モードが変更されるたびに `Script` 呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-274">When the **ViModeIndicator** is set to `Script`, the script block provided will be invoked every time the mode changes.</span></span> <span data-ttu-id="8ed3e-275">スクリプトブロックには、型の引数が1つ用意されてい `ViMode` ます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-275">The script block is provided one argument of type `ViMode`.</span></span>

<span data-ttu-id="8ed3e-276">このパラメーターは、PowerShell 7 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-276">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="8ed3e-277">-ViModeIndicator</span><span class="sxs-lookup"><span data-stu-id="8ed3e-277">-ViModeIndicator</span></span>

<span data-ttu-id="8ed3e-278">このオプションは、現在の **Vi** モードの視覚的な表示を設定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-278">This option sets the visual indication for the current **Vi** mode.</span></span> <span data-ttu-id="8ed3e-279">挿入モードまたはコマンドモード。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-279">Either insert mode or command mode.</span></span>

<span data-ttu-id="8ed3e-280">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-280">The valid values are as follows:</span></span>

- <span data-ttu-id="8ed3e-281">**None** : 何も表示されません。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-281">**None** : There's no indication.</span></span>
- <span data-ttu-id="8ed3e-282">**プロンプト** : プロンプトの色が変更されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-282">**Prompt** : The prompt changes color.</span></span>
- <span data-ttu-id="8ed3e-283">**カーソル** : カーソルのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-283">**Cursor** : The cursor changes size.</span></span>
- <span data-ttu-id="8ed3e-284">**スクリプト** : ユーザーが指定したテキストが印刷されます。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-284">**Script** : User-specified text is printed.</span></span>

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

### <span data-ttu-id="8ed3e-285">-WordDelimiters</span><span class="sxs-lookup"><span data-stu-id="8ed3e-285">-WordDelimiters</span></span>

<span data-ttu-id="8ed3e-286">**Forwardword** や、入力 **候補** などの関数の単語を区切る文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-286">Specifies the characters that delimit words for functions like **ForwardWord** or **KillWord** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: ;:,.[]{}()/\|^&*-=+'"–—―
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8ed3e-287">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ed3e-287">CommonParameters</span></span>

<span data-ttu-id="8ed3e-288">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-288">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8ed3e-289">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-289">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8ed3e-290">入力</span><span class="sxs-lookup"><span data-stu-id="8ed3e-290">Inputs</span></span>

### <span data-ttu-id="8ed3e-291">なし</span><span class="sxs-lookup"><span data-stu-id="8ed3e-291">None</span></span>

<span data-ttu-id="8ed3e-292">パイプを使用してオブジェクトを `Set-PSReadLineOption.`</span><span class="sxs-lookup"><span data-stu-id="8ed3e-292">You cannot pipe objects to `Set-PSReadLineOption.`</span></span>

## <span data-ttu-id="8ed3e-293">出力</span><span class="sxs-lookup"><span data-stu-id="8ed3e-293">Outputs</span></span>

### <span data-ttu-id="8ed3e-294">なし</span><span class="sxs-lookup"><span data-stu-id="8ed3e-294">None</span></span>

<span data-ttu-id="8ed3e-295">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-295">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="8ed3e-296">メモ</span><span class="sxs-lookup"><span data-stu-id="8ed3e-296">Notes</span></span>

## <span data-ttu-id="8ed3e-297">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8ed3e-297">Related links</span></span>

[<span data-ttu-id="8ed3e-298">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="8ed3e-298">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

[<span data-ttu-id="8ed3e-299">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="8ed3e-299">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="8ed3e-300">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="8ed3e-300">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="8ed3e-301">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="8ed3e-301">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="8ed3e-302">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="8ed3e-302">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

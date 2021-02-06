---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-progress?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Progress
ms.openlocfilehash: 2e2bd5474198745d72ad2b87c3c305695a198f22
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601000"
---
# <span data-ttu-id="6e916-102">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="6e916-102">Write-Progress</span></span>

## <span data-ttu-id="6e916-103">概要</span><span class="sxs-lookup"><span data-stu-id="6e916-103">SYNOPSIS</span></span>
<span data-ttu-id="6e916-104">PowerShell コマンドウィンドウ内の進行状況バーを表示します。</span><span class="sxs-lookup"><span data-stu-id="6e916-104">Displays a progress bar within a PowerShell command window.</span></span>

## <span data-ttu-id="6e916-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e916-105">SYNTAX</span></span>

```
Write-Progress [-Activity] <String> [[-Status] <String>] [[-Id] <Int32>] [-PercentComplete <Int32>]
 [-SecondsRemaining <Int32>] [-CurrentOperation <String>] [-ParentId <Int32>] [-Completed] [-SourceId <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="6e916-106">Description</span><span class="sxs-lookup"><span data-stu-id="6e916-106">DESCRIPTION</span></span>

<span data-ttu-id="6e916-107">コマンド `Write-Progress` レットは、実行中のコマンドまたはスクリプトの状態を示す進行状況バーを PowerShell コマンドウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="6e916-107">The `Write-Progress` cmdlet displays a progress bar in a PowerShell command window that depicts the status of a running command or script.</span></span> <span data-ttu-id="6e916-108">バーに示されるインジケーターと、進行状況バーの上部および下部に表示されるテキストを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6e916-108">You can select the indicators that the bar reflects and the text that appears above and below the progress bar.</span></span>

## <span data-ttu-id="6e916-109">例</span><span class="sxs-lookup"><span data-stu-id="6e916-109">EXAMPLES</span></span>

### <span data-ttu-id="6e916-110">例 1: For ループの進行状況を表示する</span><span class="sxs-lookup"><span data-stu-id="6e916-110">Example 1: Display the progress of a For loop</span></span>

```powershell
for ($i = 1; $i -le 100; $i++ )
{
    Write-Progress -Activity "Search in Progress" -Status "$i% Complete:" -PercentComplete $i;
}
```

<span data-ttu-id="6e916-111">このコマンドは、1 から 100 をカウントする For ループの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="6e916-111">This command displays the progress of a For loop that counts from 1 to 100.</span></span>

<span data-ttu-id="6e916-112">コマンドレットには、 `Write-Progress` ステータスバーの見出し `Activity` 、ステータス行、および `$i` タスクの相対的な完全性を示す変数 (for ループのカウンター) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e916-112">The `Write-Progress` cmdlet includes a status bar heading `Activity`, a status line, and the variable `$i` (the counter in the For loop), which indicates the relative completeness of the task.</span></span>

### <span data-ttu-id="6e916-113">例 2: 入れ子になった For ループの進行状況を表示する</span><span class="sxs-lookup"><span data-stu-id="6e916-113">Example 2: Display the progress of nested For loops</span></span>

```powershell
for($I = 1; $I -lt 101; $I++ )
{
    Write-Progress -Activity Updating -Status 'Progress->' -PercentComplete $I -CurrentOperation OuterLoop
    for($j = 1; $j -lt 101; $j++ )
    {
        Write-Progress -Id 1 -Activity Updating -Status 'Progress' -PercentComplete $j -CurrentOperation InnerLoop
    }
}
```

```Output
Updating
Progress ->
 [ooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo]
OuterLoop
Updating
Progress
 [oooooooooooooooooo                                                   ]
InnerLoop
```

<span data-ttu-id="6e916-114">この例は、2 つの入れ子になった For ループの進行状況をそれぞれ対応する進行状況バーに表示します。</span><span class="sxs-lookup"><span data-stu-id="6e916-114">This example displays the progress of two nested For loops, each of which is represented by a progress bar.</span></span>

<span data-ttu-id="6e916-115">`Write-Progress`2 番目の進行状況バーのコマンドには、最初の進行状況バーと区別する **Id** パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e916-115">The `Write-Progress` command for the second progress bar includes the **Id** parameter that distinguishes it from the first progress bar.</span></span>

<span data-ttu-id="6e916-116">**Id** パラメーターを指定しない場合、進行状況バーは、もう一方の下に表示されるのではなく、互いに重ねて表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e916-116">Without the **Id** parameter, the progress bars would be superimposed on each other instead of being displayed one below the other.</span></span>

### <span data-ttu-id="6e916-117">例 3: 文字列の検索中に進行状況を表示する</span><span class="sxs-lookup"><span data-stu-id="6e916-117">Example 3: Display the progress while searching for a string</span></span>

```powershell
# Use Get-EventLog to get the events in the System log and store them in the $Events variable.
$Events = Get-EventLog -LogName system
# Pipe the events to the ForEach-Object cmdlet.
$Events | ForEach-Object -Begin {
    # In the Begin block, use Clear-Host to clear the screen.
    Clear-Host
    # Set the $i counter variable to zero.
    $i = 0
    # Set the $out variable to a empty string.
    $out = ""
} -Process {
    # In the Process script block search the message property of each incoming object for "bios".
    if($_.message -like "*bios*")
    {
        # Append the matching message to the out variable.
        $out=$out + $_.Message
    }
    # Increment the $i counter variable which is used to create the progress bar.
    $i = $i+1
    # Use Write-Progress to output a progress bar.
    # The Activity and Status parameters create the first and second lines of the progress bar heading, respectively.
    Write-Progress -Activity "Searching Events" -Status "Progress:" -PercentComplete ($i/$Events.count*100)
} -End {
    # Display the matching messages using the out variable.
    $out
}
```

<span data-ttu-id="6e916-118">このコマンドは、System イベント ログ内で "bios" という文字列を検索するコマンドの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="6e916-118">This command displays the progress of a command to find the string "bios" in the System event log.</span></span>

<span data-ttu-id="6e916-119">**達成** 率パラメーター値は、取得されたイベントの合計数によって処理されたイベントの数を割って、その `$I` `$Events.count` 結果を100で乗算することによって計算されます。</span><span class="sxs-lookup"><span data-stu-id="6e916-119">The **PercentComplete** parameter value is calculated by dividing the number of events that have been processed `$I` by the total number of events retrieved `$Events.count` and then multiplying that result by 100.</span></span>

### <span data-ttu-id="6e916-120">例 4: 入れ子になったプロセスの各レベルの進行状況を表示する</span><span class="sxs-lookup"><span data-stu-id="6e916-120">Example 4: Display progress for each level of a nested process</span></span>

```powershell
foreach ( $i in 1..10 ) {
  Write-Progress -Id 0 "Step $i"
  foreach ( $j in 1..10 ) {
    Write-Progress -Id 1 -ParentId 0 "Step $i - Substep $j"
    foreach ( $k in 1..10 ) {
      Write-Progress -Id 2  -ParentId 1 "Step $i - Substep $j - iteration $k"; start-sleep -m 150
    }
  }
}
```

```Output
Step 1
     Processing
    Step 1 - Substep 2
         Processing
        Step 1 - Substep 2 - Iteration 3
             Processing
```

<span data-ttu-id="6e916-121">この例では、 **ParentId** パラメーターを使用して、各ステップの進行中に親/子のリレーションシップを表示するようにインデントされた出力を設定できます。</span><span class="sxs-lookup"><span data-stu-id="6e916-121">In this example you can use the **ParentId** parameter to have indented output to show parent/child relationships in the progress of each step.</span></span>

## <span data-ttu-id="6e916-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e916-122">PARAMETERS</span></span>

### <span data-ttu-id="6e916-123">-アクティビティ</span><span class="sxs-lookup"><span data-stu-id="6e916-123">-Activity</span></span>

<span data-ttu-id="6e916-124">ステータス バーの上の見出しのテキストの 1 行目を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e916-124">Specifies the first line of text in the heading above the status bar.</span></span>
<span data-ttu-id="6e916-125">このテキストは、進行状況が表示されているアクティビティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6e916-125">This text describes the activity whose progress is being reported.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e916-126">-完了</span><span class="sxs-lookup"><span data-stu-id="6e916-126">-Completed</span></span>

<span data-ttu-id="6e916-127">進行状況バーを表示するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6e916-127">Indicates whether the progress bar is visible.</span></span>
<span data-ttu-id="6e916-128">このパラメーターを省略した場合は、 `Write-Progress` 進行状況の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e916-128">If this parameter is omitted, `Write-Progress` displays progress information.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e916-129">-CurrentOperation</span><span class="sxs-lookup"><span data-stu-id="6e916-129">-CurrentOperation</span></span>

<span data-ttu-id="6e916-130">進行状況バーの下のテキスト行を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e916-130">Specifies the line of text below the progress bar.</span></span>
<span data-ttu-id="6e916-131">このテキストでは、現在実行されている操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e916-131">This text describes the operation that is currently taking place.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e916-132">-Id</span><span class="sxs-lookup"><span data-stu-id="6e916-132">-Id</span></span>

<span data-ttu-id="6e916-133">それぞれの進行状況バーを区別するための ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e916-133">Specifies an ID that distinguishes each progress bar from the others.</span></span> <span data-ttu-id="6e916-134">1 つのコマンドで複数の進行状況バーを作成する場合は、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e916-134">Use this parameter when you are creating more than one progress bar in a single command.</span></span> <span data-ttu-id="6e916-135">進行状況バーに異なる ID を付けなかった場合、進行状況バーは、順に表示される代わりに重なり合って表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e916-135">If the progress bars do not have different IDs, they are superimposed instead of being displayed in a series.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e916-136">-ParentId</span><span class="sxs-lookup"><span data-stu-id="6e916-136">-ParentId</span></span>

<span data-ttu-id="6e916-137">現在のアクティビティの親アクティビティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e916-137">Specifies the parent activity of the current activity.</span></span>
<span data-ttu-id="6e916-138">現在のアクティビティが親アクティビティを持たない場合は、値 -1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e916-138">Use the value -1 if the current activity has no parent activity.</span></span>

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

### <span data-ttu-id="6e916-139">-達成率</span><span class="sxs-lookup"><span data-stu-id="6e916-139">-PercentComplete</span></span>

<span data-ttu-id="6e916-140">完了したアクティビティの割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e916-140">Specifies the percentage of the activity that is completed.</span></span>
<span data-ttu-id="6e916-141">完了した割合が不明な場合や該当しない場合は、値 -1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e916-141">Use the value -1 if the percentage complete is unknown or not applicable.</span></span>

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

### <span data-ttu-id="6e916-142">-SecondsRemaining</span><span class="sxs-lookup"><span data-stu-id="6e916-142">-SecondsRemaining</span></span>

<span data-ttu-id="6e916-143">アクティビティが完了するまでの推定残り秒数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e916-143">Specifies the projected number of seconds remaining until the activity is completed.</span></span>
<span data-ttu-id="6e916-144">残り秒数が不明な場合や該当しない場合は、値 -1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e916-144">Use the value -1 if the number of seconds remaining is unknown or not applicable.</span></span>

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

### <span data-ttu-id="6e916-145">-SourceId</span><span class="sxs-lookup"><span data-stu-id="6e916-145">-SourceId</span></span>

<span data-ttu-id="6e916-146">レコードのソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e916-146">Specifies the source of the record.</span></span> <span data-ttu-id="6e916-147">これは **Id** の代わりに使用できますが、 **ParentId** などの他のパラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e916-147">You can use this in place of **Id** but cannot be used with other parameters like **ParentId**.</span></span>

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

### <span data-ttu-id="6e916-148">-状態</span><span class="sxs-lookup"><span data-stu-id="6e916-148">-Status</span></span>

<span data-ttu-id="6e916-149">ステータス バーの上の見出しのテキストの 2 行目を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e916-149">Specifies the second line of text in the heading above the status bar.</span></span>
<span data-ttu-id="6e916-150">このテキストは、アクティビティの現在の状態を記述します。</span><span class="sxs-lookup"><span data-stu-id="6e916-150">This text describes current state of the activity.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e916-151">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e916-151">CommonParameters</span></span>

<span data-ttu-id="6e916-152">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6e916-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e916-153">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e916-153">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="6e916-154">入力</span><span class="sxs-lookup"><span data-stu-id="6e916-154">INPUTS</span></span>

### <span data-ttu-id="6e916-155">なし</span><span class="sxs-lookup"><span data-stu-id="6e916-155">None</span></span>

<span data-ttu-id="6e916-156">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="6e916-156">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="6e916-157">出力</span><span class="sxs-lookup"><span data-stu-id="6e916-157">OUTPUTS</span></span>

### <span data-ttu-id="6e916-158">なし</span><span class="sxs-lookup"><span data-stu-id="6e916-158">None</span></span>

<span data-ttu-id="6e916-159">`Write-Progress` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="6e916-159">`Write-Progress` does not generate any output.</span></span>

## <span data-ttu-id="6e916-160">注</span><span class="sxs-lookup"><span data-stu-id="6e916-160">NOTES</span></span>

<span data-ttu-id="6e916-161">進行状況バーが表示されない場合は、変数の値を確認し `$ProgressPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="6e916-161">If the progress bar does not appear, check the value of the `$ProgressPreference` variable.</span></span> <span data-ttu-id="6e916-162">値が SilentlyContinue に設定されている場合、進行状況バーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6e916-162">If the value is set to SilentlyContinue, the progress bar is not displayed.</span></span> <span data-ttu-id="6e916-163">PowerShell の設定の詳細については、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e916-163">For more information about PowerShell preferences, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="6e916-164">コマンドレットのパラメーターは、system.servicemodel **レコード** クラスのプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="6e916-164">The parameters of the cmdlet correspond to the properties of the **System.Management.Automation.ProgressRecord** class.</span></span> <span data-ttu-id="6e916-165">詳細については、「 [進捗記録クラス](/dotnet/api/system.management.automation.progressrecord)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e916-165">For more information, see [ProgressRecord Class](/dotnet/api/system.management.automation.progressrecord).</span></span>

## <span data-ttu-id="6e916-166">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6e916-166">RELATED LINKS</span></span>

[<span data-ttu-id="6e916-167">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="6e916-167">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="6e916-168">Write-Error</span><span class="sxs-lookup"><span data-stu-id="6e916-168">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="6e916-169">Write-Host</span><span class="sxs-lookup"><span data-stu-id="6e916-169">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="6e916-170">Write-Output</span><span class="sxs-lookup"><span data-stu-id="6e916-170">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="6e916-171">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="6e916-171">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="6e916-172">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="6e916-172">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="6e916-173">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="6e916-173">Write-Warning</span></span>](Write-Warning.md)

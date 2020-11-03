---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214664"
---
# <span data-ttu-id="85f88-103">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="85f88-103">Limit-EventLog</span></span>

## <span data-ttu-id="85f88-104">概要</span><span class="sxs-lookup"><span data-stu-id="85f88-104">SYNOPSIS</span></span>
<span data-ttu-id="85f88-105">イベント ログのサイズおよびエントリの期間を制限するイベント ログ プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-105">Sets the event log properties that limit the size of the event log and the age of its entries.</span></span>

## <span data-ttu-id="85f88-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85f88-106">SYNTAX</span></span>

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="85f88-107">Description</span><span class="sxs-lookup"><span data-stu-id="85f88-107">DESCRIPTION</span></span>
<span data-ttu-id="85f88-108">**Limit-EventLog** コマンドレットは、従来のイベントログの最大サイズ、各イベントを保持する必要がある期間、およびログが最大サイズに達したときの動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-108">The **Limit-EventLog** cmdlet sets the maximum size of a classic event log, how long each event must be retained, and what happens when the log reaches its maximum size.</span></span>
<span data-ttu-id="85f88-109">このコマンドレットを使用して、ローカル コンピューターまたはリモート コンピューター上のイベント ログを制限できます。</span><span class="sxs-lookup"><span data-stu-id="85f88-109">You can use it to limit the event logs on local or remote computers.</span></span>

<span data-ttu-id="85f88-110">EventLog という名詞を含むコマンドレット (EventLog コマンドレット) は、従来のイベント ログでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="85f88-110">The cmdlets that contain the EventLog noun (the EventLog cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="85f88-111">Windows Vista 以降のバージョンで Windows イベント ログ技術を使用しているログからイベントを取得するには、Get-WinEvent を使用します。</span><span class="sxs-lookup"><span data-stu-id="85f88-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use Get-WinEvent.</span></span>

## <span data-ttu-id="85f88-112">例</span><span class="sxs-lookup"><span data-stu-id="85f88-112">EXAMPLES</span></span>

### <span data-ttu-id="85f88-113">例 1: イベントログのサイズを大きくする</span><span class="sxs-lookup"><span data-stu-id="85f88-113">Example 1: Increase the size of an event log</span></span>

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

<span data-ttu-id="85f88-114">このコマンドは、ローカル コンピューター上の Windows PowerShell イベント ログの最大サイズを 20,480 バイト (20 KB) に増やします。</span><span class="sxs-lookup"><span data-stu-id="85f88-114">This command increases the maximum size of the Windows PowerShell event log on the local computer to 20480 bytes (20 KB).</span></span>

### <span data-ttu-id="85f88-115">例 2: 指定した期間のイベントログを保持する</span><span class="sxs-lookup"><span data-stu-id="85f88-115">Example 2: Retain an event log for a specified duration</span></span>

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

<span data-ttu-id="85f88-116">このコマンドは、Server01 コンピューターと Server02 コンピューター上のセキュリティ ログのイベントを少なくとも 7 日間確実に保持します。</span><span class="sxs-lookup"><span data-stu-id="85f88-116">This command ensures that events in the Security log on the Server01 and Server02 computers are retained for at least 7 days.</span></span>

### <span data-ttu-id="85f88-117">例 3: すべてのイベントログのオーバーフローアクションを変更する</span><span class="sxs-lookup"><span data-stu-id="85f88-117">Example 3: Change the overflow action of all event logs</span></span>

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

<span data-ttu-id="85f88-118">この例では、ローカルコンピューター上のすべてのイベントログのオーバーフローアクションを OverwriteOlder に変更します。</span><span class="sxs-lookup"><span data-stu-id="85f88-118">This example changes the overflow action of all event logs on the local computer to OverwriteOlder.</span></span>

<span data-ttu-id="85f88-119">最初のコマンドは、ローカル コンピューター上のすべてのログのログ名を取得します。</span><span class="sxs-lookup"><span data-stu-id="85f88-119">The first command gets the log names of all of the logs on the local computer.</span></span>
<span data-ttu-id="85f88-120">2 番目のコマンドはオーバーフロー アクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-120">The second command sets the overflow action.</span></span>
<span data-ttu-id="85f88-121">3 番目のコマンドは結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="85f88-121">The third command displays the results.</span></span>

## <span data-ttu-id="85f88-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85f88-122">PARAMETERS</span></span>

### <span data-ttu-id="85f88-123">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="85f88-123">-ComputerName</span></span>
<span data-ttu-id="85f88-124">リモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-124">Specifies remote computers.</span></span>
<span data-ttu-id="85f88-125">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="85f88-125">The default is the local computer.</span></span>

<span data-ttu-id="85f88-126">リモートコンピューターの NetBIOS 名、インターネットプロトコル (IP) アドレス、または完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="85f88-126">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="85f88-127">ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="85f88-127">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="85f88-128">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="85f88-128">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="85f88-129">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **Limit-EventLog** の *ComputerName* パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="85f88-129">You can use the *ComputerName* parameter of **Limit-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85f88-130">-LogName</span><span class="sxs-lookup"><span data-stu-id="85f88-130">-LogName</span></span>
<span data-ttu-id="85f88-131">イベント ログを指定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-131">Specifies the event logs.</span></span>
<span data-ttu-id="85f88-132">1 つ以上のイベント ログのログ名 (LogDisplayName ではなく Log プロパティの値) をコンマ区切りで入力します。</span><span class="sxs-lookup"><span data-stu-id="85f88-132">Enter the log name (the value of the Log property; not the LogDisplayName) of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="85f88-133">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="85f88-133">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="85f88-134">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="85f88-134">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85f88-135">-MaximumSize</span><span class="sxs-lookup"><span data-stu-id="85f88-135">-MaximumSize</span></span>
<span data-ttu-id="85f88-136">イベント ログの最大サイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-136">Specifies the maximum size of the event logs in bytes.</span></span>
<span data-ttu-id="85f88-137">64 キロバイト (KB) ～ 4 ギガバイト (GB) の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="85f88-137">Enter a value between 64 kilobytes (KB) and 4 gigabytes (GB).</span></span>
<span data-ttu-id="85f88-138">値は 64 KB (65536) で割り切れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85f88-138">The value must be divisible by 64 KB (65536).</span></span>

<span data-ttu-id="85f88-139">このパラメーター **は、従来** のイベントログを表す system.string オブジェクトの **maximumkilobytes** プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-139">This parameter specifies the value of the **MaximumKilobytes** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85f88-140">-OverflowAction</span><span class="sxs-lookup"><span data-stu-id="85f88-140">-OverflowAction</span></span>
<span data-ttu-id="85f88-141">イベント ログが最大サイズに達したときのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-141">Specifies what happens when the event log reaches its maximum size.</span></span>

<span data-ttu-id="85f88-142">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85f88-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85f88-143">DoNotOverwrite: 既存のエントリは保持され、新しいエントリは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="85f88-143">DoNotOverwrite:  Existing entries are retained and new entries are discarded.</span></span>
- <span data-ttu-id="85f88-144">OverwriteAsNeeded: 新しいエントリごとに、最も古いエントリが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="85f88-144">OverwriteAsNeeded:  Each new entry overwrites the oldest entry.</span></span>
- <span data-ttu-id="85f88-145">OverwriteOlder: 新しいイベントは、 **MinimumRetentionDays** プロパティで指定された値よりも古いイベントを上書きします。</span><span class="sxs-lookup"><span data-stu-id="85f88-145">OverwriteOlder:  New events overwrite events older than the value specified by the **MinimumRetentionDays** property.</span></span> <span data-ttu-id="85f88-146">**MinimumRetentionDays** プロパティ値によって指定されたよりも古いイベントがない場合、新しいイベントは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="85f88-146">If there are no events older than specified by the **MinimumRetentionDays** property value, new events are discarded.</span></span>

<span data-ttu-id="85f88-147">このパラメーターは、従来のイベントログを表す OverflowAction **オブジェクトの** **OverflowAction** プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-147">This parameter specifies the value of the **OverflowAction** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85f88-148">-RetentionDays</span><span class="sxs-lookup"><span data-stu-id="85f88-148">-RetentionDays</span></span>
<span data-ttu-id="85f88-149">イベントをイベント ログに残す必要がある最小日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-149">Specifies the minimum number of days that an event must remain in the event log.</span></span>

<span data-ttu-id="85f88-150">このパラメーターは、従来のイベントログを表す MinimumRetentionDays **オブジェクトの** **MinimumRetentionDays** プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="85f88-150">This parameter specifies the value of the **MinimumRetentionDays** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85f88-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="85f88-151">-Confirm</span></span>
<span data-ttu-id="85f88-152">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="85f88-152">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85f88-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="85f88-153">-WhatIf</span></span>
<span data-ttu-id="85f88-154">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="85f88-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="85f88-155">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="85f88-155">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85f88-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="85f88-156">CommonParameters</span></span>
<span data-ttu-id="85f88-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="85f88-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85f88-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85f88-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85f88-159">入力</span><span class="sxs-lookup"><span data-stu-id="85f88-159">INPUTS</span></span>

### <span data-ttu-id="85f88-160">なし</span><span class="sxs-lookup"><span data-stu-id="85f88-160">None</span></span>
<span data-ttu-id="85f88-161">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="85f88-161">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="85f88-162">出力</span><span class="sxs-lookup"><span data-stu-id="85f88-162">OUTPUTS</span></span>

### <span data-ttu-id="85f88-163">なし</span><span class="sxs-lookup"><span data-stu-id="85f88-163">None</span></span>
<span data-ttu-id="85f88-164">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="85f88-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="85f88-165">注</span><span class="sxs-lookup"><span data-stu-id="85f88-165">NOTES</span></span>

* <span data-ttu-id="85f88-166">Windows Vista 以降のバージョンの Windows でこのコマンドレットを使用するには、[管理者として実行] オプションを使用して Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="85f88-166">To use this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="85f88-167">このコマンドレットは、従来のイベントログを表す **system.string オブジェクトの** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="85f88-167">This cmdlet changes the properties of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>
<span data-ttu-id="85f88-168">イベントログのプロパティの現在の設定を表示するには、「」と入力 `Get-EventLog -List` します。</span><span class="sxs-lookup"><span data-stu-id="85f88-168">To see the current settings of the event log properties, type `Get-EventLog -List`.</span></span>

*

## <span data-ttu-id="85f88-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="85f88-169">RELATED LINKS</span></span>

[<span data-ttu-id="85f88-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="85f88-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="85f88-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="85f88-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="85f88-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="85f88-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="85f88-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="85f88-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="85f88-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="85f88-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="85f88-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="85f88-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="85f88-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="85f88-176">Write-EventLog</span></span>](Write-EventLog.md)

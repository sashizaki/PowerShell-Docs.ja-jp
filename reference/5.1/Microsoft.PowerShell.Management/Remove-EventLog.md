---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214555"
---
# <span data-ttu-id="1f876-103">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="1f876-103">Remove-EventLog</span></span>

## <span data-ttu-id="1f876-104">概要</span><span class="sxs-lookup"><span data-stu-id="1f876-104">SYNOPSIS</span></span>
<span data-ttu-id="1f876-105">イベント ログを削除またはイベント ソースの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="1f876-105">Deletes an event log or unregisters an event source.</span></span>

## <span data-ttu-id="1f876-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1f876-106">SYNTAX</span></span>

### <span data-ttu-id="1f876-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="1f876-107">Default (Default)</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1f876-108">source</span><span class="sxs-lookup"><span data-stu-id="1f876-108">Source</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1f876-109">Description</span><span class="sxs-lookup"><span data-stu-id="1f876-109">DESCRIPTION</span></span>
<span data-ttu-id="1f876-110">EventLog コマンドレットは、ローカルまたはリモートのコンピューターからイベントログファイルを削除し、ログのすべてのイベントソースの登録を **解除** します。</span><span class="sxs-lookup"><span data-stu-id="1f876-110">The **Remove-EventLog** cmdlet deletes an event log file from a local or remote computer and unregisters all its event sources for the log.</span></span>
<span data-ttu-id="1f876-111">このコマンドレットを使用して、イベント ログを削除せずにイベント ソースの登録を解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f876-111">You can also use this cmdlet to unregister event sources without deleting any event logs.</span></span>

<span data-ttu-id="1f876-112">**Eventlog** 名詞を含むコマンドレット ( **eventlog** コマンドレット) は、従来のイベントログでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="1f876-112">The cmdlets that contain the **EventLog** noun, the **EventLog** cmdlets, work only on classic event logs.</span></span>
<span data-ttu-id="1f876-113">Windows Vista 以降のバージョンの Windows オペレーティングシステムで Windows イベントログテクノロジを使用するログからイベントを取得するには、Get-WinEvent を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f876-113">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use Get-WinEvent.</span></span>

<span data-ttu-id="1f876-114">注意: このコマンドレットでは、オペレーティングシステムのイベントログを削除できます。これにより、アプリケーションのエラーや予期しないシステムの動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f876-114">CAUTION: This cmdlet can delete operating system event logs, which might cause application failures and unexpected system behavior.</span></span>

## <span data-ttu-id="1f876-115">例</span><span class="sxs-lookup"><span data-stu-id="1f876-115">EXAMPLES</span></span>

### <span data-ttu-id="1f876-116">例 1: ローカルコンピューターからイベントログを削除する</span><span class="sxs-lookup"><span data-stu-id="1f876-116">Example 1: Remove an event log from the local computer</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

<span data-ttu-id="1f876-117">このコマンドは、ローカル コンピューターから MyLog イベント ログを削除し、そのイベント ソースの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="1f876-117">This command deletes the MyLog event log from the local computer and unregisters its event sources.</span></span>

### <span data-ttu-id="1f876-118">例 2: 複数のコンピューターからイベントログを削除する</span><span class="sxs-lookup"><span data-stu-id="1f876-118">Example 2: Remove an event log from several computers</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="1f876-119">このコマンドは、ローカルコンピューターと Server01 および Server02 リモートコンピューターから MyLog イベントログと TestLog イベントログを削除します。</span><span class="sxs-lookup"><span data-stu-id="1f876-119">This command deletes the MyLog and TestLog event logs from the local computer and the Server01 and Server02 remote computers.</span></span>
<span data-ttu-id="1f876-120">コマンドは、これらのログのイベント ソースの登録も解除します。</span><span class="sxs-lookup"><span data-stu-id="1f876-120">The command also unregisters the event sources for these logs.</span></span>

### <span data-ttu-id="1f876-121">例 3: イベントソースを削除する</span><span class="sxs-lookup"><span data-stu-id="1f876-121">Example 3: Delete an event source</span></span>

```
PS C:\> Remove-EventLog -Source "MyApp"
```

<span data-ttu-id="1f876-122">このコマンドを実行すると、ローカル コンピューター上のログから MyApp イベント ソースが削除されます。</span><span class="sxs-lookup"><span data-stu-id="1f876-122">This command deletes the MyApp event source from the logs on the local computer.</span></span>
<span data-ttu-id="1f876-123">コマンドが完了すると、MyApp プログラムはイベントログに書き込むことができません。</span><span class="sxs-lookup"><span data-stu-id="1f876-123">When the command finishes, the MyApp program cannot write to any event logs.</span></span>

### <span data-ttu-id="1f876-124">例 4: イベントログを削除してアクションを確認する</span><span class="sxs-lookup"><span data-stu-id="1f876-124">Example 4: Remove an event log and confirm the action</span></span>

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

<span data-ttu-id="1f876-125">これらのコマンドは、コンピューター上のイベントログの一覧を表示し、イベント **削除** コマンドが正常に実行されたことを確認する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1f876-125">These commands show how to list the event logs on a computer and verify that a **Remove-EventLog** command was successful.</span></span>

### <span data-ttu-id="1f876-126">例 5: イベントソースを削除してアクションを確認する</span><span class="sxs-lookup"><span data-stu-id="1f876-126">Example 5: Remove an event source and confirm the action</span></span>

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

<span data-ttu-id="1f876-127">これらのコマンドは、Get-WmiObject コマンドレットを使用して、ローカル コンピューター上のイベント ソースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f876-127">These commands use the Get-WmiObject cmdlet to list the event sources on the local computer.</span></span>
<span data-ttu-id="1f876-128">これらのコマンドを実行して、コマンドの成功を確認したり、イベント ソースを削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f876-128">You can these commands to verify the success of a command or to delete an event source.</span></span>

<span data-ttu-id="1f876-129">最初のコマンドは、ローカル コンピューター上の TestLog イベント ログのイベント ソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f876-129">The first command gets the event sources of the TestLog event log on the local computer.</span></span>
<span data-ttu-id="1f876-130">MyApp はソースの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="1f876-130">MyApp is one of the sources.</span></span>

<span data-ttu-id="1f876-131">2番目のコマンドは、 **削除** イベントの *source* パラメーターを使用して、MyApp イベントソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="1f876-131">The second command uses the *Source* parameter of **Remove-EventLog** to delete the MyApp event source.</span></span>

<span data-ttu-id="1f876-132">3 番目のコマンドは、最初のコマンドと同一です。</span><span class="sxs-lookup"><span data-stu-id="1f876-132">The third command is identical to the first.</span></span>
<span data-ttu-id="1f876-133">MyApp イベント ソースが削除されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="1f876-133">It shows that the MyApp event source was deleted.</span></span>

## <span data-ttu-id="1f876-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1f876-134">PARAMETERS</span></span>

### <span data-ttu-id="1f876-135">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="1f876-135">-ComputerName</span></span>
<span data-ttu-id="1f876-136">リモート コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f876-136">Specifies a remote computer.</span></span>
<span data-ttu-id="1f876-137">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="1f876-137">The default is the local computer.</span></span>

<span data-ttu-id="1f876-138">リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f876-138">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="1f876-139">ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f876-139">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="1f876-140">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="1f876-140">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="1f876-141">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **削除イベントログ** の *ComputerName* パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f876-141">You can use the *ComputerName* parameter of **Remove-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f876-142">-LogName</span><span class="sxs-lookup"><span data-stu-id="1f876-142">-LogName</span></span>
<span data-ttu-id="1f876-143">イベント ログを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f876-143">Specifies the event logs.</span></span>
<span data-ttu-id="1f876-144">1つ以上のイベントログのログ名をコンマで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="1f876-144">Enter the log name of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="1f876-145">ログ名は *Logdisplayname* ではなく **log** プロパティの値であり、ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="1f876-145">The log name is the value of the **Log** property, not the *LogDisplayName* , Wildcard characters are not permitted.</span></span>
<span data-ttu-id="1f876-146">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="1f876-146">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f876-147">-Source</span><span class="sxs-lookup"><span data-stu-id="1f876-147">-Source</span></span>
<span data-ttu-id="1f876-148">このコマンドレットが登録を解除するイベントソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f876-148">Specifies the event sources that this cmdlet unregisters.</span></span>
<span data-ttu-id="1f876-149">実行可能ファイル名ではなく、ソース名をコンマで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="1f876-149">Enter the source names, not the executable name, separated by commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f876-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1f876-150">-Confirm</span></span>
<span data-ttu-id="1f876-151">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f876-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1f876-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1f876-152">-WhatIf</span></span>
<span data-ttu-id="1f876-153">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="1f876-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1f876-154">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1f876-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1f876-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f876-155">CommonParameters</span></span>
<span data-ttu-id="1f876-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1f876-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1f876-157">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f876-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1f876-158">入力</span><span class="sxs-lookup"><span data-stu-id="1f876-158">INPUTS</span></span>

### <span data-ttu-id="1f876-159">なし</span><span class="sxs-lookup"><span data-stu-id="1f876-159">None</span></span>
<span data-ttu-id="1f876-160">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1f876-160">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1f876-161">出力</span><span class="sxs-lookup"><span data-stu-id="1f876-161">OUTPUTS</span></span>

### <span data-ttu-id="1f876-162">なし</span><span class="sxs-lookup"><span data-stu-id="1f876-162">None</span></span>
<span data-ttu-id="1f876-163">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="1f876-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="1f876-164">注</span><span class="sxs-lookup"><span data-stu-id="1f876-164">NOTES</span></span>

* <span data-ttu-id="1f876-165">Windows Vista 以降のバージョンの Windows オペレーティングシステムで **削除イベントログ** を使用するには、[管理者として実行] オプションを使用して windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="1f876-165">To use **Remove-EventLog** on Windows Vista and later versions of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

  <span data-ttu-id="1f876-166">イベント ログを削除した後、ログを再作成する場合、同じイベント ソースを登録することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f876-166">If you remove an event log and then re-create the log, you will not be able to register the same event sources.</span></span>
<span data-ttu-id="1f876-167">エントリを元のログに書き込むためにイベント ソースを使用したアプリケーションは、新しいログに書き込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="1f876-167">Applications that used the events sources to write entries to the original log will not be able to write to the new log.</span></span>

* <span data-ttu-id="1f876-168">特定ログのイベント ソースの登録を解除すると、エントリの他のイベント ログへの書き込みが防止されます。</span><span class="sxs-lookup"><span data-stu-id="1f876-168">When you unregister an event source for a particular log, the event source might be prevented from writing entries in other event logs.</span></span>

## <span data-ttu-id="1f876-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1f876-169">RELATED LINKS</span></span>

[<span data-ttu-id="1f876-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="1f876-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="1f876-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="1f876-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="1f876-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="1f876-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="1f876-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="1f876-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="1f876-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="1f876-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="1f876-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="1f876-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="1f876-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="1f876-176">Write-EventLog</span></span>](Write-EventLog.md)

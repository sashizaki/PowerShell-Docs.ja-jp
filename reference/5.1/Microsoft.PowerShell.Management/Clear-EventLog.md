---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-EventLog
ms.openlocfilehash: 695a13d4fbbf60caadeed994c1aa9c36432be917
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215563"
---
# <span data-ttu-id="63f34-103">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="63f34-103">Clear-EventLog</span></span>

## <span data-ttu-id="63f34-104">概要</span><span class="sxs-lookup"><span data-stu-id="63f34-104">SYNOPSIS</span></span>
<span data-ttu-id="63f34-105">ローカルコンピューターまたはリモートコンピューター上の指定されたイベントログからすべてのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="63f34-105">Clears all entries from specified event logs on the local or remote computers.</span></span>

## <span data-ttu-id="63f34-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="63f34-106">SYNTAX</span></span>

```
Clear-EventLog [-LogName] <String[]> [[-ComputerName] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="63f34-107">Description</span><span class="sxs-lookup"><span data-stu-id="63f34-107">DESCRIPTION</span></span>

<span data-ttu-id="63f34-108">`Clear-EventLog`コマンドレットは、ローカルコンピューターまたはリモートコンピューター上の指定されたイベントログからすべてのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="63f34-108">The `Clear-EventLog` cmdlet deletes all of the entries from the specified event logs on the local computer or on remote computers.</span></span>
<span data-ttu-id="63f34-109">を使用するには `Clear-EventLog` 、影響を受けるコンピューターの Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="63f34-109">To use `Clear-EventLog`, you must be a member of the Administrators group on the affected computer.</span></span>

<span data-ttu-id="63f34-110">**Eventlog** 名詞を含むコマンドレット (eventlog コマンドレット) は、従来のイベントログでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="63f34-110">The cmdlets that contain the **EventLog** noun (the EventLog cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="63f34-111">Windows Vista 以降のバージョンの windows で windows イベントログテクノロジを使用するログからイベントを取得するには、Get-WinEvent コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="63f34-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="63f34-112">例</span><span class="sxs-lookup"><span data-stu-id="63f34-112">EXAMPLES</span></span>

### <span data-ttu-id="63f34-113">例 1: ローカルコンピューターから特定のイベントログの種類をクリアする</span><span class="sxs-lookup"><span data-stu-id="63f34-113">Example 1: Clear specific event log types from the local computer</span></span>

```powershell
Clear-EventLog "Windows PowerShell"
```

<span data-ttu-id="63f34-114">このコマンドは、ローカルコンピューター上の Windows PowerShell イベントログからエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="63f34-114">This command clears the entries from the Windows PowerShell event log on the local computer.</span></span>

### <span data-ttu-id="63f34-115">例 2: ローカルコンピューターとリモートコンピューターから特定の複数のログの種類を消去する</span><span class="sxs-lookup"><span data-stu-id="63f34-115">Example 2: Clear specific multiple log types from the local and remote computers</span></span>

```powershell
Clear-EventLog -LogName ODiag, OSession -ComputerName localhost, Server02
```

<span data-ttu-id="63f34-116">このコマンドは、ローカルコンピューターおよび Server02 リモートコンピューター上の Microsoft Office Diagnostics (ODiag) および Microsoft Office Sessions (Odiag) ログに含まれるすべてのエントリをクリアします。</span><span class="sxs-lookup"><span data-stu-id="63f34-116">This command clears all of the entries in the Microsoft Office Diagnostics (ODiag) and Microsoft Office Sessions (OSession) logs on the local computer and the Server02 remote computer.</span></span>

### <span data-ttu-id="63f34-117">例 3: 指定されたコンピューター上のすべてのログを消去し、イベントログの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="63f34-117">Example 3: Clear all logs on the specified computers then display the event log list</span></span>

```powershell
Clear-EventLog -LogName application, system -confirm
```

<span data-ttu-id="63f34-118">このコマンドでは、指定したイベント ログのエントリを削除する前に確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="63f34-118">This command prompts you for confirmation before deleting the entries in the specified event logs.</span></span>

### <span data-ttu-id="63f34-119">例 4: 指定したコンピューター上のすべてのログを消去し、イベントログの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="63f34-119">Example 4: Clear all logs on the specified computers then display the event log list</span></span>

```powershell
function clear-all-event-logs ($computerName="localhost")
{
   $logs = Get-EventLog -ComputerName $computername -List | ForEach-Object {$_.Log}
   $logs | ForEach-Object {Clear-EventLog -ComputerName $computername -LogName $_ }
   Get-EventLog -ComputerName $computername -list
}

clear-all-event-logs -ComputerName Server01
```

```Output
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded           0 Application
15,168      0 OverwriteAsNeeded           0 DFS Replication
512         7 OverwriteOlder              0 DxStudio
20,480      0 OverwriteAsNeeded           0 Hardware Events
512         7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
16,384      0 OverwriteAsNeeded           0 Microsoft Office Diagnostics
16,384      0 OverwriteAsNeeded           0 Microsoft Office Sessions
30,016      0 OverwriteAsNeeded           1 Security
15,168      0 OverwriteAsNeeded           2 System
15,360      0 OverwriteAsNeeded           0 Windows PowerShell
```

<span data-ttu-id="63f34-120">この関数は指定されたコンピューター上のすべてのイベント ログをクリアし、その結果のイベント ログの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="63f34-120">This function clears all event logs on the specified computers and then displays the resulting event log list.</span></span>

<span data-ttu-id="63f34-121">クリアした後で表示される前にシステム ログやセキュリティ ログに追加されたエントリがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="63f34-121">Notice that a few entries were added to the System and Security logs after the logs were cleared but before they were displayed.</span></span>

## <span data-ttu-id="63f34-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="63f34-122">PARAMETERS</span></span>

### <span data-ttu-id="63f34-123">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="63f34-123">-ComputerName</span></span>

<span data-ttu-id="63f34-124">リモート コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="63f34-124">Specifies a remote computer.</span></span>
<span data-ttu-id="63f34-125">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="63f34-125">The default is the local computer.</span></span>

<span data-ttu-id="63f34-126">リモート コンピューターの NetBIOS 名、インターネット プロトコル (IP) アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="63f34-126">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="63f34-127">ローカル コンピューターを指定するには、コンピューター名、ドット (.)、または「localhost」を入力します。</span><span class="sxs-lookup"><span data-stu-id="63f34-127">To specify the local computer, type the computer name, a dot (.), or "localhost".</span></span>

<span data-ttu-id="63f34-128">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="63f34-128">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="63f34-129">**ComputerName** `Get-EventLog` コンピューターがリモートコマンドを実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63f34-129">You can use the **ComputerName** parameter of `Get-EventLog` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 1
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="63f34-130">-LogName</span><span class="sxs-lookup"><span data-stu-id="63f34-130">-LogName</span></span>

<span data-ttu-id="63f34-131">イベント ログを指定します。</span><span class="sxs-lookup"><span data-stu-id="63f34-131">Specifies the event logs.</span></span>
<span data-ttu-id="63f34-132">1 つ以上のイベント ログのログ名 (LogDisplayName ではなく Log プロパティの値) をコンマ区切りで入力します。</span><span class="sxs-lookup"><span data-stu-id="63f34-132">Enter the log name (the value of the Log property; not the LogDisplayName) of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="63f34-133">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="63f34-133">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="63f34-134">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="63f34-134">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="63f34-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="63f34-135">-Confirm</span></span>

<span data-ttu-id="63f34-136">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63f34-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="63f34-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="63f34-137">-WhatIf</span></span>

<span data-ttu-id="63f34-138">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="63f34-138">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="63f34-139">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="63f34-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="63f34-140">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="63f34-140">CommonParameters</span></span>

<span data-ttu-id="63f34-141">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="63f34-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="63f34-142">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f34-142">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="63f34-143">入力</span><span class="sxs-lookup"><span data-stu-id="63f34-143">INPUTS</span></span>

### <span data-ttu-id="63f34-144">なし</span><span class="sxs-lookup"><span data-stu-id="63f34-144">None</span></span>

<span data-ttu-id="63f34-145">パイプを使用してオブジェクトをにパイプすることはできません `Clear-EventLog` 。</span><span class="sxs-lookup"><span data-stu-id="63f34-145">You cannot pipe objects to `Clear-EventLog`.</span></span>

## <span data-ttu-id="63f34-146">出力</span><span class="sxs-lookup"><span data-stu-id="63f34-146">OUTPUTS</span></span>

### <span data-ttu-id="63f34-147">なし</span><span class="sxs-lookup"><span data-stu-id="63f34-147">None</span></span>

<span data-ttu-id="63f34-148">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="63f34-148">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="63f34-149">注</span><span class="sxs-lookup"><span data-stu-id="63f34-149">NOTES</span></span>

- <span data-ttu-id="63f34-150">Windows Vista 以降のバージョンの Windows でを使用するには `Clear-EventLog` 、[管理者として実行] オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="63f34-150">To use `Clear-EventLog` on Windows Vista and later versions of Windows, start Windows PowerShell with the "Run as administrator" option.</span></span>

## <span data-ttu-id="63f34-151">関連リンク</span><span class="sxs-lookup"><span data-stu-id="63f34-151">RELATED LINKS</span></span>

[<span data-ttu-id="63f34-152">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="63f34-152">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="63f34-153">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="63f34-153">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="63f34-154">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="63f34-154">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="63f34-155">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="63f34-155">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="63f34-156">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="63f34-156">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="63f34-157">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="63f34-157">Write-EventLog</span></span>](Write-EventLog.md)

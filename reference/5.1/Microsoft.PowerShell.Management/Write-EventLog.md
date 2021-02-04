---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: 051f02b00144805569d5130686a51a0f42b64b00
ms.sourcegitcommit: f5986121386c81acddcf324eb0526d7d092bcc8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "98584632"
---
# <span data-ttu-id="34c88-103">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="34c88-103">Write-EventLog</span></span>

## <span data-ttu-id="34c88-104">概要</span><span class="sxs-lookup"><span data-stu-id="34c88-104">SYNOPSIS</span></span>
<span data-ttu-id="34c88-105">イベントをイベント ログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="34c88-105">Writes an event to an event log.</span></span>

## <span data-ttu-id="34c88-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="34c88-106">SYNTAX</span></span>

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## <span data-ttu-id="34c88-107">Description</span><span class="sxs-lookup"><span data-stu-id="34c88-107">DESCRIPTION</span></span>

<span data-ttu-id="34c88-108">コマンドレットでは、イベントを `Write-EventLog` イベントログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="34c88-108">The `Write-EventLog` cmdlet writes an event to an event log.</span></span>

<span data-ttu-id="34c88-109">イベントをイベント ログに書き込むには、イベント ログがコンピューター上に存在し、イベント ソースがイベント ログに登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c88-109">To write an event to an event log, the event log must exist on the computer and the source must be registered for the event log.</span></span>

<span data-ttu-id="34c88-110">**Eventlog** 名詞を含むコマンドレット ( **eventlog** コマンドレット) は、従来のイベントログでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="34c88-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span> <span data-ttu-id="34c88-111">Windows Vista 以降のバージョンの Windows オペレーティングシステムで Windows イベントログテクノロジを使用するログからイベントを取得するには、 `Get-WinEvent` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="34c88-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the `Get-WinEvent` cmdlet.</span></span>

## <span data-ttu-id="34c88-112">例</span><span class="sxs-lookup"><span data-stu-id="34c88-112">EXAMPLES</span></span>

### <span data-ttu-id="34c88-113">例 1: アプリケーションイベントログにイベントを書き込む</span><span class="sxs-lookup"><span data-stu-id="34c88-113">Example 1: Write an event to the Application event log</span></span>

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

<span data-ttu-id="34c88-114">このコマンドは、MyApp ソースのイベントをアプリケーション イベント ログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="34c88-114">This command writes an event from the MyApp source to the Application event log.</span></span>

### <span data-ttu-id="34c88-115">例 2: リモートコンピューターのアプリケーションイベントログにイベントを書き込む</span><span class="sxs-lookup"><span data-stu-id="34c88-115">Example 2: Write an event to the Application event log of a remote computer</span></span>

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

<span data-ttu-id="34c88-116">このコマンドは、MyApp ソースのイベントを Server01 リモート コンピューター上のアプリケーション イベント ログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="34c88-116">This command writes an event from the MyApp source to the Application event log on the Server01 remote computer.</span></span>

## <span data-ttu-id="34c88-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="34c88-117">PARAMETERS</span></span>

### <span data-ttu-id="34c88-118">-カテゴリ</span><span class="sxs-lookup"><span data-stu-id="34c88-118">-Category</span></span>

<span data-ttu-id="34c88-119">イベントのタスク カテゴリを指定します。</span><span class="sxs-lookup"><span data-stu-id="34c88-119">Specifies a task category for the event.</span></span> <span data-ttu-id="34c88-120">イベント ログのカテゴリ メッセージ ファイルに記載された文字列に関連付けられた整数を入力します。</span><span class="sxs-lookup"><span data-stu-id="34c88-120">Enter an integer that is associated with the strings in the category message file for the event log.</span></span>

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34c88-121">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="34c88-121">-ComputerName</span></span>

<span data-ttu-id="34c88-122">リモート コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="34c88-122">Specifies a remote computer.</span></span> <span data-ttu-id="34c88-123">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="34c88-123">The default is the local computer.</span></span>

<span data-ttu-id="34c88-124">リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="34c88-124">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="34c88-125">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="34c88-125">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="34c88-126"> `Get-EventLog` コンピューターがリモートコマンドを実行するように構成されていない場合でも、コマンドレットの ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34c88-126">You can use the **ComputerName** parameter of the `Get-EventLog` cmdlet even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34c88-127">-EntryType</span><span class="sxs-lookup"><span data-stu-id="34c88-127">-EntryType</span></span>

<span data-ttu-id="34c88-128">イベントのエントリの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="34c88-128">Specifies the entry type of the event.</span></span> <span data-ttu-id="34c88-129">このパラメーターに指定できる値は、Error、Warning、Information、SuccessAudit、および FailureAudit です。</span><span class="sxs-lookup"><span data-stu-id="34c88-129">The acceptable values for this parameter are: Error, Warning, Information, SuccessAudit, and FailureAudit.</span></span> <span data-ttu-id="34c88-130">既定値は Information です。</span><span class="sxs-lookup"><span data-stu-id="34c88-130">The default value is Information.</span></span>

<span data-ttu-id="34c88-131">値の説明については、「 [詳細 Enumeration](/dotnet/api/system.diagnostics.eventlogentrytype)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34c88-131">For a description of the values, see [EventLogEntryType Enumeration](/dotnet/api/system.diagnostics.eventlogentrytype).</span></span>

```yaml
Type: System.Diagnostics.EventLogEntryType
Parameter Sets: (All)
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34c88-132">-EventId</span><span class="sxs-lookup"><span data-stu-id="34c88-132">-EventId</span></span>

<span data-ttu-id="34c88-133">イベント識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="34c88-133">Specifies the event identifier.</span></span> <span data-ttu-id="34c88-134">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="34c88-134">This parameter is required.</span></span> <span data-ttu-id="34c88-135">**EventId** パラメーターの最大値は65535です。</span><span class="sxs-lookup"><span data-stu-id="34c88-135">The maximum value for the **EventId** parameter is 65535.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ID, EID

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34c88-136">-LogName</span><span class="sxs-lookup"><span data-stu-id="34c88-136">-LogName</span></span>

<span data-ttu-id="34c88-137">イベントを書き込むログの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="34c88-137">Specifies the name of the log to which the event is written.</span></span> <span data-ttu-id="34c88-138">ログ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="34c88-138">Enter the log name.</span></span> <span data-ttu-id="34c88-139">ログ名は **Logdisplayname** ではなく **log** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="34c88-139">The log name is the value of the **Log** property, not the **LogDisplayName**.</span></span> <span data-ttu-id="34c88-140">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="34c88-140">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="34c88-141">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="34c88-141">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34c88-142">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="34c88-142">-Message</span></span>

<span data-ttu-id="34c88-143">イベント メッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="34c88-143">Specifies the event message.</span></span> <span data-ttu-id="34c88-144">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="34c88-144">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MSG

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34c88-145">-RawData</span><span class="sxs-lookup"><span data-stu-id="34c88-145">-RawData</span></span>

<span data-ttu-id="34c88-146">イベントに関連付けるバイナリ データをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="34c88-146">Specifies the binary data that is associated with the event, in bytes.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: (All)
Aliases: RD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34c88-147">-Source</span><span class="sxs-lookup"><span data-stu-id="34c88-147">-Source</span></span>

<span data-ttu-id="34c88-148">イベント ソースを指定します。通常は、イベントをログに書き込むアプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="34c88-148">Specifies the event source, which is typically the name of the application that is writing the event to the log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="34c88-149">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="34c88-149">CommonParameters</span></span>

<span data-ttu-id="34c88-150">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="34c88-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="34c88-151">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34c88-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="34c88-152">入力</span><span class="sxs-lookup"><span data-stu-id="34c88-152">INPUTS</span></span>

### <span data-ttu-id="34c88-153">なし</span><span class="sxs-lookup"><span data-stu-id="34c88-153">None</span></span>

<span data-ttu-id="34c88-154">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="34c88-154">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="34c88-155">出力</span><span class="sxs-lookup"><span data-stu-id="34c88-155">OUTPUTS</span></span>

### <span data-ttu-id="34c88-156">EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="34c88-156">System.Diagnostics.EventLogEntry</span></span>

<span data-ttu-id="34c88-157">このコマンドレットは、ログ内のイベントを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="34c88-157">This cmdlet returns objects that represents the events in the logs.</span></span>

## <span data-ttu-id="34c88-158">注</span><span class="sxs-lookup"><span data-stu-id="34c88-158">NOTES</span></span>

<span data-ttu-id="34c88-159">一部の Windows イベントログでは、イベントの書き込みに管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="34c88-159">For some Windows event logs, writing events requires administrator rights.</span></span> <span data-ttu-id="34c88-160">[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34c88-160">You must start PowerShell using the **Run as Administrator** option.</span></span>

## <span data-ttu-id="34c88-161">関連リンク</span><span class="sxs-lookup"><span data-stu-id="34c88-161">RELATED LINKS</span></span>

[<span data-ttu-id="34c88-162">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="34c88-162">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="34c88-163">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="34c88-163">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="34c88-164">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="34c88-164">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="34c88-165">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="34c88-165">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="34c88-166">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="34c88-166">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="34c88-167">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="34c88-167">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="34c88-168">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="34c88-168">Write-EventLog</span></span>](Write-EventLog.md)

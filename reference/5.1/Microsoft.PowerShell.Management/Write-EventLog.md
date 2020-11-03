---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: cae34c4cf942d9aa4abb9a2d716ef9854f70de2e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214296"
---
# <span data-ttu-id="51fa1-103">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="51fa1-103">Write-EventLog</span></span>

## <span data-ttu-id="51fa1-104">概要</span><span class="sxs-lookup"><span data-stu-id="51fa1-104">SYNOPSIS</span></span>
<span data-ttu-id="51fa1-105">イベントをイベント ログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="51fa1-105">Writes an event to an event log.</span></span>

## <span data-ttu-id="51fa1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="51fa1-106">SYNTAX</span></span>

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## <span data-ttu-id="51fa1-107">Description</span><span class="sxs-lookup"><span data-stu-id="51fa1-107">DESCRIPTION</span></span>
<span data-ttu-id="51fa1-108">**書き込み** イベントレットは、イベントをイベントログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="51fa1-108">The **Write-EventLog** cmdlet writes an event to an event log.</span></span>

<span data-ttu-id="51fa1-109">イベントをイベント ログに書き込むには、イベント ログがコンピューター上に存在し、イベント ソースがイベント ログに登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="51fa1-109">To write an event to an event log, the event log must exist on the computer and the source must be registered for the event log.</span></span>

<span data-ttu-id="51fa1-110">**Eventlog** 名詞を含むコマンドレット ( **eventlog** コマンドレット) は、従来のイベントログでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="51fa1-111">Windows Vista 以降のバージョンの windows オペレーティングシステムで Windows イベントログテクノロジを使用するログからイベントを取得するには、Get-WinEvent コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="51fa1-112">例</span><span class="sxs-lookup"><span data-stu-id="51fa1-112">EXAMPLES</span></span>

### <span data-ttu-id="51fa1-113">例 1: アプリケーションイベントログにイベントを書き込む</span><span class="sxs-lookup"><span data-stu-id="51fa1-113">Example 1: Write an event to the Application event log</span></span>

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

<span data-ttu-id="51fa1-114">このコマンドは、MyApp ソースのイベントをアプリケーション イベント ログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="51fa1-114">This command writes an event from the MyApp source to the Application event log.</span></span>

### <span data-ttu-id="51fa1-115">例 2: リモートコンピューターのアプリケーションイベントログにイベントを書き込む</span><span class="sxs-lookup"><span data-stu-id="51fa1-115">Example 2: Write an event to the Application event log of a remote computer</span></span>

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

<span data-ttu-id="51fa1-116">このコマンドは、MyApp ソースのイベントを Server01 リモート コンピューター上のアプリケーション イベント ログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="51fa1-116">This command writes an event from the MyApp source to the Application event log on the Server01 remote computer.</span></span>

## <span data-ttu-id="51fa1-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="51fa1-117">PARAMETERS</span></span>

### <span data-ttu-id="51fa1-118">-カテゴリ</span><span class="sxs-lookup"><span data-stu-id="51fa1-118">-Category</span></span>
<span data-ttu-id="51fa1-119">イベントのタスク カテゴリを指定します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-119">Specifies a task category for the event.</span></span>
<span data-ttu-id="51fa1-120">イベント ログのカテゴリ メッセージ ファイルに記載された文字列に関連付けられた整数を入力します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-120">Enter an integer that is associated with the strings in the category message file for the event log.</span></span>

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

### <span data-ttu-id="51fa1-121">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="51fa1-121">-ComputerName</span></span>
<span data-ttu-id="51fa1-122">リモート コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-122">Specifies a remote computer.</span></span>
<span data-ttu-id="51fa1-123">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="51fa1-123">The default is the local computer.</span></span>

<span data-ttu-id="51fa1-124">リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-124">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="51fa1-125">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="51fa1-125">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="51fa1-126">コンピューターがリモートコマンドを実行するように構成されていない場合でも、Get-EventLog コマンドレットの *ComputerName* パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="51fa1-126">You can use the *ComputerName* parameter of the Get-EventLog cmdlet even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="51fa1-127">-EntryType</span><span class="sxs-lookup"><span data-stu-id="51fa1-127">-EntryType</span></span>
<span data-ttu-id="51fa1-128">イベントのエントリの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-128">Specifies the entry type of the event.</span></span>
<span data-ttu-id="51fa1-129">このパラメーターに指定できる値は、Error、Warning、Information、SuccessAudit、および FailureAudit です。</span><span class="sxs-lookup"><span data-stu-id="51fa1-129">The acceptable values for this parameter are: Error, Warning, Information, SuccessAudit, and FailureAudit.</span></span>
<span data-ttu-id="51fa1-130">既定値は Information です。</span><span class="sxs-lookup"><span data-stu-id="51fa1-130">The default value is Information.</span></span>

<span data-ttu-id="51fa1-131">値の説明については、MSDN ライブラリの「 [詳細列挙体](https://go.microsoft.com/fwlink/?LinkId=143599) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51fa1-131">For a description of the values, see [EventLogEntryType Enumeration](https://go.microsoft.com/fwlink/?LinkId=143599) in the MSDN library.</span></span>

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

### <span data-ttu-id="51fa1-132">-EventId</span><span class="sxs-lookup"><span data-stu-id="51fa1-132">-EventId</span></span>
<span data-ttu-id="51fa1-133">イベント識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-133">Specifies the event identifier.</span></span>
<span data-ttu-id="51fa1-134">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="51fa1-134">This parameter is required.</span></span>
<span data-ttu-id="51fa1-135">*EventId* パラメーターの最大値は65535です。</span><span class="sxs-lookup"><span data-stu-id="51fa1-135">The maximum value for the *EventId* parameter is 65535.</span></span>

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

### <span data-ttu-id="51fa1-136">-LogName</span><span class="sxs-lookup"><span data-stu-id="51fa1-136">-LogName</span></span>
<span data-ttu-id="51fa1-137">イベントを書き込むログの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-137">Specifies the name of the log to which the event is written.</span></span>
<span data-ttu-id="51fa1-138">ログ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-138">Enter the log name.</span></span>
<span data-ttu-id="51fa1-139">ログ名は **Logdisplayname** ではなく **log** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="51fa1-139">The log name is the value of the **Log** property, not the **LogDisplayName** .</span></span>
<span data-ttu-id="51fa1-140">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="51fa1-140">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="51fa1-141">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="51fa1-141">This parameter is required.</span></span>

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

### <span data-ttu-id="51fa1-142">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="51fa1-142">-Message</span></span>
<span data-ttu-id="51fa1-143">イベント メッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-143">Specifies the event message.</span></span>
<span data-ttu-id="51fa1-144">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="51fa1-144">This parameter is required.</span></span>

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

### <span data-ttu-id="51fa1-145">-RawData</span><span class="sxs-lookup"><span data-stu-id="51fa1-145">-RawData</span></span>
<span data-ttu-id="51fa1-146">イベントに関連付けるバイナリ データをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-146">Specifies the binary data that is associated with the event, in bytes.</span></span>

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

### <span data-ttu-id="51fa1-147">-Source</span><span class="sxs-lookup"><span data-stu-id="51fa1-147">-Source</span></span>
<span data-ttu-id="51fa1-148">イベント ソースを指定します。通常は、イベントをログに書き込むアプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="51fa1-148">Specifies the event source, which is typically the name of the application that is writing the event to the log.</span></span>

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

### <span data-ttu-id="51fa1-149">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="51fa1-149">CommonParameters</span></span>
<span data-ttu-id="51fa1-150">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="51fa1-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="51fa1-151">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51fa1-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="51fa1-152">入力</span><span class="sxs-lookup"><span data-stu-id="51fa1-152">INPUTS</span></span>

### <span data-ttu-id="51fa1-153">なし</span><span class="sxs-lookup"><span data-stu-id="51fa1-153">None</span></span>
<span data-ttu-id="51fa1-154">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="51fa1-154">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="51fa1-155">出力</span><span class="sxs-lookup"><span data-stu-id="51fa1-155">OUTPUTS</span></span>

### <span data-ttu-id="51fa1-156">EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="51fa1-156">System.Diagnostics.EventLogEntry</span></span>
<span data-ttu-id="51fa1-157">このコマンドレットは、ログ内のイベントを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-157">This cmdlet returns objects that represents the events in the logs.</span></span>

## <span data-ttu-id="51fa1-158">注</span><span class="sxs-lookup"><span data-stu-id="51fa1-158">NOTES</span></span>

* <span data-ttu-id="51fa1-159">**書き込みイベントログ** を使用するには、[管理者として実行] オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="51fa1-159">To use **Write-EventLog** , start Windows PowerShell by using the Run as administrator option.</span></span>

*

## <span data-ttu-id="51fa1-160">関連リンク</span><span class="sxs-lookup"><span data-stu-id="51fa1-160">RELATED LINKS</span></span>

[<span data-ttu-id="51fa1-161">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="51fa1-161">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="51fa1-162">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="51fa1-162">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="51fa1-163">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="51fa1-163">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="51fa1-164">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="51fa1-164">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="51fa1-165">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="51fa1-165">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="51fa1-166">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="51fa1-166">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="51fa1-167">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="51fa1-167">Write-EventLog</span></span>](Write-EventLog.md)

---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: f9f4edca0fce4633daeac9ac11a3ccfb09feb98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213992"
---
# <span data-ttu-id="4b07c-103">Get-Event</span><span class="sxs-lookup"><span data-stu-id="4b07c-103">Get-Event</span></span>

## <span data-ttu-id="4b07c-104">概要</span><span class="sxs-lookup"><span data-stu-id="4b07c-104">SYNOPSIS</span></span>
<span data-ttu-id="4b07c-105">イベント キュー内のイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-105">Gets the events in the event queue.</span></span>

## <span data-ttu-id="4b07c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b07c-106">SYNTAX</span></span>

### <span data-ttu-id="4b07c-107">BySource (既定値)</span><span class="sxs-lookup"><span data-stu-id="4b07c-107">BySource (Default)</span></span>

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### <span data-ttu-id="4b07c-108">ById</span><span class="sxs-lookup"><span data-stu-id="4b07c-108">ById</span></span>

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## <span data-ttu-id="4b07c-109">Description</span><span class="sxs-lookup"><span data-stu-id="4b07c-109">DESCRIPTION</span></span>
<span data-ttu-id="4b07c-110">**Get イベント** コマンドレットは、現在のセッションの Windows PowerShell イベントキューにあるイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-110">The **Get-Event** cmdlet gets events in the Windows PowerShell event queue for the current session.</span></span>
<span data-ttu-id="4b07c-111">すべてのイベントを取得するか、 *EventIdentifier* パラメーターまたは *SourceIdentifier* パラメーターを使用してイベントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4b07c-111">You can get all events or use the *EventIdentifier* or *SourceIdentifier* parameter to specify the events.</span></span>

<span data-ttu-id="4b07c-112">イベントは、発生時に、イベント キューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4b07c-112">When an event occurs, it is added to the event queue.</span></span>
<span data-ttu-id="4b07c-113">イベント キューには、登録したイベント、New-Event コマンドレットを使用して作成されたイベント、および Windows PowerShell の終了時に発生するイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b07c-113">The event queue includes events for which you have registered, events created by using the New-Event cmdlet, and the event that is raised when Windows PowerShell exits.</span></span>
<span data-ttu-id="4b07c-114">イベントを取得するには、 **Get イベント** または Wait-Event を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-114">You can use **Get-Event** or Wait-Event to get the events.</span></span>

<span data-ttu-id="4b07c-115">このコマンドレットは、イベント ビューアーのログからイベントを取得しません。</span><span class="sxs-lookup"><span data-stu-id="4b07c-115">This cmdlet does not get events from the Event Viewer logs.</span></span>
<span data-ttu-id="4b07c-116">これらのイベントを取得するには、Get-WinEvent または Get-EventLog を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-116">To get those events, use Get-WinEvent or Get-EventLog.</span></span>

## <span data-ttu-id="4b07c-117">例</span><span class="sxs-lookup"><span data-stu-id="4b07c-117">EXAMPLES</span></span>

### <span data-ttu-id="4b07c-118">例 1: すべてのイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="4b07c-118">Example 1: Get all events</span></span>

```
PS C:\> Get-Event
```

<span data-ttu-id="4b07c-119">このコマンドは、イベント キュー内のすべてのイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-119">This command gets all events in the event queue.</span></span>

### <span data-ttu-id="4b07c-120">例 2: ソース識別子でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="4b07c-120">Example 2: Get events by source identifier</span></span>

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

<span data-ttu-id="4b07c-121">このコマンドは、SourceIdentifier プロパティの値が PowerShell. ProcessCreated であるイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-121">This command gets events in which the value of the SourceIdentifier property is PowerShell.ProcessCreated.</span></span>

### <span data-ttu-id="4b07c-122">例 3: 生成された時刻に基づいてイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="4b07c-122">Example 3: Get an event based on the time it was generated</span></span>

```
PS C:\> $Events = Get-Event
PS C:\> $Events[0] | Format-List -Property *
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b805917d1b7b
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:09:32 PM
MessageData      : PS C:\> Get-Event | Where {$_.TimeGenerated -ge "11/13/2008 12:15:00 PM"}
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b8059325d1a0
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:15:00 PM
MessageData      :
```

<span data-ttu-id="4b07c-123">この例では SourceIdentifier 以外のプロパティを使用してイベントを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-123">This example shows how to get events by using properties other than SourceIdentifier.</span></span>

<span data-ttu-id="4b07c-124">最初のコマンドは、イベントキュー内のすべてのイベントを取得し、$Events 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-124">The first command gets all events in the event queue and saves them in the $Events variable.</span></span>

<span data-ttu-id="4b07c-125">2番目のコマンドは、配列表記を使用して、$Events 変数内の配列内の最初の (0 インデックス) イベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-125">The second command uses array notation to get the first (0-index) event in the array in the $Events variable.</span></span>
<span data-ttu-id="4b07c-126">コマンドは、パイプライン演算子 (|) を使用して Format-List コマンドにイベントを送信します。Format-List コマンドは、一覧内のイベントのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-126">The command uses a pipeline operator (|) to send the event to the Format-List command, which displays all properties of the event in a list.</span></span>
<span data-ttu-id="4b07c-127">これによって、イベント オブジェクトのプロパティを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="4b07c-127">This allows you to examine the properties of the event object.</span></span>

<span data-ttu-id="4b07c-128">3番目のコマンドは、Where-Object コマンドレットを使用して、生成された時刻に基づいてイベントを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b07c-128">The third command shows how to use the Where-Object cmdlet to get an event based on the time that it was generated.</span></span>

### <span data-ttu-id="4b07c-129">例 4: 識別子を使用してイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="4b07c-129">Example 4: Get an event by its identifier</span></span>

```
PS C:\> Get-Event -EventIdentifier 2
```

<span data-ttu-id="4b07c-130">このコマンドは、イベント識別子が 2 のイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-130">This command gets the event with an event identifier of 2.</span></span>

## <span data-ttu-id="4b07c-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b07c-131">PARAMETERS</span></span>

### <span data-ttu-id="4b07c-132">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="4b07c-132">-EventIdentifier</span></span>
<span data-ttu-id="4b07c-133">このコマンドレットがイベントを取得するイベント識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-133">Specifies the event identifiers for which this cmdlet gets events.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b07c-134">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="4b07c-134">-SourceIdentifier</span></span>
<span data-ttu-id="4b07c-135">このコマンドレットがイベントを取得するソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-135">Specifies source identifiers for which this cmdlet gets events.</span></span>
<span data-ttu-id="4b07c-136">既定では、イベント キュー内のすべてのイベントです。</span><span class="sxs-lookup"><span data-stu-id="4b07c-136">The default is all events in the event queue.</span></span>
<span data-ttu-id="4b07c-137">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4b07c-137">Wildcards are not permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b07c-138">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b07c-138">CommonParameters</span></span>
<span data-ttu-id="4b07c-139">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4b07c-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b07c-140">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b07c-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b07c-141">入力</span><span class="sxs-lookup"><span data-stu-id="4b07c-141">INPUTS</span></span>

### <span data-ttu-id="4b07c-142">なし</span><span class="sxs-lookup"><span data-stu-id="4b07c-142">None</span></span>
<span data-ttu-id="4b07c-143">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="4b07c-143">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4b07c-144">出力</span><span class="sxs-lookup"><span data-stu-id="4b07c-144">OUTPUTS</span></span>

### <span data-ttu-id="4b07c-145">PSEventArgs (システム管理)</span><span class="sxs-lookup"><span data-stu-id="4b07c-145">System.Management.Automation.PSEventArgs</span></span>
<span data-ttu-id="4b07c-146">**PSEventArgs** は、イベントごとに1つのオブジェクト **を返します** 。</span><span class="sxs-lookup"><span data-stu-id="4b07c-146">**Get-Event** returns a **PSEventArgs** object for each event.</span></span>
<span data-ttu-id="4b07c-147">このオブジェクトの説明を表示するには、「」 `Get-Help Get-Event -Full` と入力し、ヘルプトピックの「メモ」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b07c-147">To see a description of this object, type `Get-Help Get-Event -Full` and see the Notes section of the help topic.</span></span>

## <span data-ttu-id="4b07c-148">注</span><span class="sxs-lookup"><span data-stu-id="4b07c-148">NOTES</span></span>

* <span data-ttu-id="4b07c-149">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-149">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="4b07c-150">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="4b07c-150">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

  <span data-ttu-id="4b07c-151">**Get Event** コマンドレットは、次のプロパティを持つ **PSEventArgs** オブジェクト ( **PSEventArgs** ) を返します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-151">The **Get-Event** cmdlet returns a **PSEventArgs** object ( **System.Management.Automation.PSEventArgs** ) with the following properties:</span></span>

  - <span data-ttu-id="4b07c-152">ComputerName。</span><span class="sxs-lookup"><span data-stu-id="4b07c-152">ComputerName.</span></span>
<span data-ttu-id="4b07c-153">イベントが発生したコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="4b07c-153">The name of the computer on which the event occurred.</span></span>
<span data-ttu-id="4b07c-154">このプロパティ値は、リモート コンピューターからイベントが転送された場合にのみ入力されます。</span><span class="sxs-lookup"><span data-stu-id="4b07c-154">This property value is populated only when the event is forwarded from a remote computer.</span></span>

  - <span data-ttu-id="4b07c-155">RunspaceId.</span><span class="sxs-lookup"><span data-stu-id="4b07c-155">RunspaceId.</span></span>
<span data-ttu-id="4b07c-156">イベントが発生したセッションを一意に識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="4b07c-156">A GUID that uniquely identifies the session in which the event occurred.</span></span>
<span data-ttu-id="4b07c-157">このプロパティ値は、リモート コンピューターからイベントが転送された場合にのみ入力されます。</span><span class="sxs-lookup"><span data-stu-id="4b07c-157">This property value is populated only when the event is forwarded from a remote computer.</span></span>

  - <span data-ttu-id="4b07c-158">EventIdentifier.</span><span class="sxs-lookup"><span data-stu-id="4b07c-158">EventIdentifier.</span></span>
<span data-ttu-id="4b07c-159">現在のセッションにおけるイベント通知を一意に識別する整数 (Int32)。</span><span class="sxs-lookup"><span data-stu-id="4b07c-159">An integer (Int32) that uniquely identifies the event notification in the current session.</span></span>

  - <span data-ttu-id="4b07c-160">センダー.</span><span class="sxs-lookup"><span data-stu-id="4b07c-160">Sender.</span></span>
<span data-ttu-id="4b07c-161">イベントを生成したオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4b07c-161">The object that generated the event.</span></span>
<span data-ttu-id="4b07c-162">*Action* パラメーターの値では、$Sender の自動変数に Sender オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b07c-162">In the value of the *Action* parameter, the $Sender automatic variable contains the sender object.</span></span>

  - <span data-ttu-id="4b07c-163">SourceEventArgs.</span><span class="sxs-lookup"><span data-stu-id="4b07c-163">SourceEventArgs.</span></span>
<span data-ttu-id="4b07c-164">存在する場合は、EventArgs から派生した最初のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4b07c-164">The first parameter that derives from EventArgs, if it exists.</span></span>
<span data-ttu-id="4b07c-165">たとえば、署名に "オブジェクト送信者, ElapsedEventArgs e" という形式の timer elapsed イベントがある場合、SourceEventArgs プロパティには ElapsedEventArgs が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b07c-165">For example, in a timer elapsed event in which the signature has the form Object sender, Timers.ElapsedEventArgs e, the SourceEventArgs property would contain the Timers.ElapsedEventArgs.</span></span>
<span data-ttu-id="4b07c-166">*Action* パラメーターの値には、$EventArgs の自動変数にこの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b07c-166">In the value of the *Action* parameter, the $EventArgs automatic variable contains this value.</span></span>

  - <span data-ttu-id="4b07c-167">SourceArgs。</span><span class="sxs-lookup"><span data-stu-id="4b07c-167">SourceArgs.</span></span>
<span data-ttu-id="4b07c-168">元のイベント署名のすべてのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4b07c-168">All parameters of the original event signature.</span></span>
<span data-ttu-id="4b07c-169">標準イベントシグネチャの場合、$Args \[ 0 は \] 送信者を表し、$Args \[ 1 \] は sourceeventargs を表します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-169">For a standard event signature, $Args\[0\] represents the sender, and $Args\[1\] represents the SourceEventArgs.</span></span>
<span data-ttu-id="4b07c-170">*Action* パラメーターの値には、$Args の自動変数にこの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b07c-170">In the value of the *Action* parameter, the $Args automatic variable contains this value.</span></span>

  - <span data-ttu-id="4b07c-171">SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="4b07c-171">SourceIdentifier.</span></span>
<span data-ttu-id="4b07c-172">イベント サブスクリプションを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="4b07c-172">A string that identifies the event subscription.</span></span>
<span data-ttu-id="4b07c-173">*Action* パラメーターの値では、$Event の自動変数の SourceIdentifier プロパティにこの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b07c-173">In the value of the *Action* parameter, the SourceIdentifier property of the $Event automatic variable contains this value.</span></span>

  - <span data-ttu-id="4b07c-174">TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="4b07c-174">TimeGenerated.</span></span>
<span data-ttu-id="4b07c-175">イベントが生成された時刻を表す **DateTime** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4b07c-175">A **DateTime** object that represents the time at which the event was generated.</span></span>
<span data-ttu-id="4b07c-176">*Action* パラメーターの値では、$Event 自動変数の timegenerated プロパティにこの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b07c-176">In the value of the *Action* parameter, the TimeGenerated property of the $Event automatic variable contains this value.</span></span>

  <span data-ttu-id="4b07c-177">--MessageData。</span><span class="sxs-lookup"><span data-stu-id="4b07c-177">--MessageData.</span></span>
<span data-ttu-id="4b07c-178">イベント サブスクリプションに関連付けられているデータ。</span><span class="sxs-lookup"><span data-stu-id="4b07c-178">Data associated with the event subscription.</span></span>
<span data-ttu-id="4b07c-179">ユーザーは、イベントを登録するときに、このデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b07c-179">Users specify this data when they register an event.</span></span>
<span data-ttu-id="4b07c-180">*Action* パラメーターの値では、$Event 自動変数の messagedata プロパティにこの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b07c-180">In the value of the *Action* parameter, the MessageData property of the $Event automatic variable contains this value.</span></span>

*

## <span data-ttu-id="4b07c-181">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4b07c-181">RELATED LINKS</span></span>

[<span data-ttu-id="4b07c-182">New-Event</span><span class="sxs-lookup"><span data-stu-id="4b07c-182">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="4b07c-183">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="4b07c-183">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="4b07c-184">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="4b07c-184">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="4b07c-185">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="4b07c-185">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="4b07c-186">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4b07c-186">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="4b07c-187">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="4b07c-187">Wait-Event</span></span>](Wait-Event.md)

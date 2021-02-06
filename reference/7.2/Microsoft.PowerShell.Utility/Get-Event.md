---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: 4b275d489984f85aea401b781e38c80fbc4b2177
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601404"
---
# <span data-ttu-id="83648-102">Get-Event</span><span class="sxs-lookup"><span data-stu-id="83648-102">Get-Event</span></span>

## <span data-ttu-id="83648-103">概要</span><span class="sxs-lookup"><span data-stu-id="83648-103">SYNOPSIS</span></span>
<span data-ttu-id="83648-104">イベント キュー内のイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="83648-104">Gets the events in the event queue.</span></span>

## <span data-ttu-id="83648-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="83648-105">SYNTAX</span></span>

### <span data-ttu-id="83648-106">BySource (既定値)</span><span class="sxs-lookup"><span data-stu-id="83648-106">BySource (Default)</span></span>

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### <span data-ttu-id="83648-107">ById</span><span class="sxs-lookup"><span data-stu-id="83648-107">ById</span></span>

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## <span data-ttu-id="83648-108">Description</span><span class="sxs-lookup"><span data-stu-id="83648-108">DESCRIPTION</span></span>

<span data-ttu-id="83648-109">`Get-Event`コマンドレットは、現在のセッションの PowerShell イベントキューにあるイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="83648-109">The `Get-Event` cmdlet gets events in the PowerShell event queue for the current session.</span></span> <span data-ttu-id="83648-110">すべてのイベントを取得するか、 **EventIdentifier** パラメーターまたは **SourceIdentifier** パラメーターを使用してイベントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="83648-110">You can get all events or use the **EventIdentifier** or **SourceIdentifier** parameter to specify the events.</span></span>

<span data-ttu-id="83648-111">イベントは、発生時に、イベント キューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="83648-111">When an event occurs, it is added to the event queue.</span></span> <span data-ttu-id="83648-112">イベントキューには、登録したイベント、コマンドレットを使用して作成されたイベント、 `New-Event` および PowerShell の終了時に発生するイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="83648-112">The event queue includes events for which you have registered, events created by using the `New-Event` cmdlet, and the event that is raised when PowerShell exits.</span></span> <span data-ttu-id="83648-113">またはを使用し `Get-Event` `Wait-Event` て、イベントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="83648-113">You can use `Get-Event` or `Wait-Event` to get the events.</span></span>

<span data-ttu-id="83648-114">このコマンドレットは、イベント ビューアーのログからイベントを取得しません。</span><span class="sxs-lookup"><span data-stu-id="83648-114">This cmdlet does not get events from the Event Viewer logs.</span></span> <span data-ttu-id="83648-115">これらのイベントを取得するには、またはを使用し `Get-WinEvent` `Get-EventLog` ます。</span><span class="sxs-lookup"><span data-stu-id="83648-115">To get those events, use `Get-WinEvent` or `Get-EventLog`.</span></span>

## <span data-ttu-id="83648-116">例</span><span class="sxs-lookup"><span data-stu-id="83648-116">EXAMPLES</span></span>

### <span data-ttu-id="83648-117">例 1: すべてのイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="83648-117">Example 1: Get all events</span></span>

```
PS C:\> Get-Event
```

<span data-ttu-id="83648-118">このコマンドは、イベント キュー内のすべてのイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="83648-118">This command gets all events in the event queue.</span></span>

### <span data-ttu-id="83648-119">例 2: ソース識別子でイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="83648-119">Example 2: Get events by source identifier</span></span>

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

<span data-ttu-id="83648-120">このコマンドは、SourceIdentifier プロパティの値が PowerShell. ProcessCreated であるイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="83648-120">This command gets events in which the value of the SourceIdentifier property is PowerShell.ProcessCreated.</span></span>

### <span data-ttu-id="83648-121">例 3: 生成された時刻に基づいてイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="83648-121">Example 3: Get an event based on the time it was generated</span></span>

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

<span data-ttu-id="83648-122">この例では SourceIdentifier 以外のプロパティを使用してイベントを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="83648-122">This example shows how to get events by using properties other than SourceIdentifier.</span></span>

<span data-ttu-id="83648-123">最初のコマンドは、イベントキュー内のすべてのイベントを取得し、変数に保存し `$Events` ます。</span><span class="sxs-lookup"><span data-stu-id="83648-123">The first command gets all events in the event queue and saves them in the `$Events` variable.</span></span>

<span data-ttu-id="83648-124">2番目のコマンドは、配列表記を使用して、変数内の配列内の最初の (0 インデックス) イベントを取得し `$Events` ます。</span><span class="sxs-lookup"><span data-stu-id="83648-124">The second command uses array notation to get the first (0-index) event in the array in the `$Events` variable.</span></span> <span data-ttu-id="83648-125">このコマンドは、パイプライン演算子 () を使用して `|` コマンドにイベントを送信し `Format-List` ます。これにより、イベントのすべてのプロパティが一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="83648-125">The command uses a pipeline operator (`|`) to send the event to the `Format-List` command, which displays all properties of the event in a list.</span></span> <span data-ttu-id="83648-126">これによって、イベント オブジェクトのプロパティを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="83648-126">This allows you to examine the properties of the event object.</span></span>

<span data-ttu-id="83648-127">3番目のコマンドは、コマンドレットを使用して、生成された時刻に基づいてイベントを取得する方法を示して `Where-Object` います。</span><span class="sxs-lookup"><span data-stu-id="83648-127">The third command shows how to use the `Where-Object` cmdlet to get an event based on the time that it was generated.</span></span>

### <span data-ttu-id="83648-128">例 4: 識別子を使用してイベントを取得する</span><span class="sxs-lookup"><span data-stu-id="83648-128">Example 4: Get an event by its identifier</span></span>

```
PS C:\> Get-Event -EventIdentifier 2
```

<span data-ttu-id="83648-129">このコマンドは、イベント識別子が 2 のイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="83648-129">This command gets the event with an event identifier of 2.</span></span>

## <span data-ttu-id="83648-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="83648-130">PARAMETERS</span></span>

### <span data-ttu-id="83648-131">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="83648-131">-EventIdentifier</span></span>

<span data-ttu-id="83648-132">このコマンドレットがイベントを取得するイベント識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="83648-132">Specifies the event identifiers for which this cmdlet gets events.</span></span>

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

### <span data-ttu-id="83648-133">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="83648-133">-SourceIdentifier</span></span>

<span data-ttu-id="83648-134">このコマンドレットがイベントを取得するソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="83648-134">Specifies source identifiers for which this cmdlet gets events.</span></span> <span data-ttu-id="83648-135">既定では、イベント キュー内のすべてのイベントです。</span><span class="sxs-lookup"><span data-stu-id="83648-135">The default is all events in the event queue.</span></span> <span data-ttu-id="83648-136">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="83648-136">Wildcards are not permitted.</span></span>

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

### <span data-ttu-id="83648-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="83648-137">CommonParameters</span></span>

<span data-ttu-id="83648-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="83648-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="83648-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83648-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="83648-140">入力</span><span class="sxs-lookup"><span data-stu-id="83648-140">INPUTS</span></span>

### <span data-ttu-id="83648-141">なし</span><span class="sxs-lookup"><span data-stu-id="83648-141">None</span></span>

<span data-ttu-id="83648-142">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="83648-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="83648-143">出力</span><span class="sxs-lookup"><span data-stu-id="83648-143">OUTPUTS</span></span>

### <span data-ttu-id="83648-144">PSEventArgs (システム管理)</span><span class="sxs-lookup"><span data-stu-id="83648-144">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="83648-145">`Get-Event` 各イベントの **PSEventArgs** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="83648-145">`Get-Event` returns a **PSEventArgs** object for each event.</span></span> <span data-ttu-id="83648-146">このオブジェクトの説明を表示するには、「」 `Get-Help Get-Event -Full` と入力し、ヘルプトピックの「メモ」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="83648-146">To see a description of this object, type `Get-Help Get-Event -Full` and see the Notes section of the help topic.</span></span>

## <span data-ttu-id="83648-147">注</span><span class="sxs-lookup"><span data-stu-id="83648-147">NOTES</span></span>

<span data-ttu-id="83648-148">Linux または macOS プラットフォームで使用できるイベントソースがありません。</span><span class="sxs-lookup"><span data-stu-id="83648-148">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="83648-149">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="83648-149">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="83648-150">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="83648-150">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="83648-151">`Get-Event`コマンドレットは、次のプロパティを持つ **PSEventArgs** オブジェクト (**PSEventArgs**) を返します。</span><span class="sxs-lookup"><span data-stu-id="83648-151">The `Get-Event` cmdlet returns a **PSEventArgs** object (**System.Management.Automation.PSEventArgs**) with the following properties:</span></span>

- <span data-ttu-id="83648-152">ComputerName。</span><span class="sxs-lookup"><span data-stu-id="83648-152">ComputerName.</span></span> <span data-ttu-id="83648-153">イベントが発生したコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="83648-153">The name of the computer on which the event occurred.</span></span> <span data-ttu-id="83648-154">このプロパティ値は、リモート コンピューターからイベントが転送された場合にのみ入力されます。</span><span class="sxs-lookup"><span data-stu-id="83648-154">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="83648-155">RunspaceId.</span><span class="sxs-lookup"><span data-stu-id="83648-155">RunspaceId.</span></span> <span data-ttu-id="83648-156">イベントが発生したセッションを一意に識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="83648-156">A GUID that uniquely identifies the session in which the event occurred.</span></span> <span data-ttu-id="83648-157">このプロパティ値は、リモート コンピューターからイベントが転送された場合にのみ入力されます。</span><span class="sxs-lookup"><span data-stu-id="83648-157">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="83648-158">EventIdentifier.</span><span class="sxs-lookup"><span data-stu-id="83648-158">EventIdentifier.</span></span> <span data-ttu-id="83648-159">現在のセッションにおけるイベント通知を一意に識別する整数 (Int32)。</span><span class="sxs-lookup"><span data-stu-id="83648-159">An integer (Int32) that uniquely identifies the event notification in the current session.</span></span>

- <span data-ttu-id="83648-160">センダー.</span><span class="sxs-lookup"><span data-stu-id="83648-160">Sender.</span></span> <span data-ttu-id="83648-161">イベントを生成したオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="83648-161">The object that generated the event.</span></span> <span data-ttu-id="83648-162">**Action** パラメーターの値では、 `$Sender` 自動変数に sender オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="83648-162">In the value of the **Action** parameter, the `$Sender` automatic variable contains the sender object.</span></span>

- <span data-ttu-id="83648-163">SourceEventArgs.</span><span class="sxs-lookup"><span data-stu-id="83648-163">SourceEventArgs.</span></span> <span data-ttu-id="83648-164">存在する場合は、EventArgs から派生した最初のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="83648-164">The first parameter that derives from EventArgs, if it exists.</span></span> <span data-ttu-id="83648-165">たとえば、署名に "オブジェクト送信者, **ElapsedEventArgs** e" という形式の timer elapsed イベントがある場合、 **sourceeventargs** プロパティには **ElapsedEventArgs** が含まれます。</span><span class="sxs-lookup"><span data-stu-id="83648-165">For example, in a timer elapsed event in which the signature has the form Object sender, **Timers.ElapsedEventArgs** e, the **SourceEventArgs** property would contain the **Timers.ElapsedEventArgs**.</span></span> <span data-ttu-id="83648-166">**Action** パラメーターの値では、 `$EventArgs` 自動変数にこの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83648-166">In the value of the **Action** parameter, the `$EventArgs` automatic variable contains this value.</span></span>

- <span data-ttu-id="83648-167">SourceArgs。</span><span class="sxs-lookup"><span data-stu-id="83648-167">SourceArgs.</span></span> <span data-ttu-id="83648-168">元のイベント署名のすべてのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="83648-168">All parameters of the original event signature.</span></span> <span data-ttu-id="83648-169">標準イベントシグネチャの場合、は `$Args[0]` 送信者を表し、 `$Args[1]` **sourceeventargs** を表します。</span><span class="sxs-lookup"><span data-stu-id="83648-169">For a standard event signature, `$Args[0]` represents the sender, and `$Args[1]` represents the **SourceEventArgs**.</span></span> <span data-ttu-id="83648-170">**Action** パラメーターの値では、 `$Args` 自動変数にこの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83648-170">In the value of the **Action** parameter, the `$Args` automatic variable contains this value.</span></span>

- <span data-ttu-id="83648-171">SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="83648-171">SourceIdentifier.</span></span> <span data-ttu-id="83648-172">イベント サブスクリプションを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="83648-172">A string that identifies the event subscription.</span></span> <span data-ttu-id="83648-173">**Action** パラメーターの値では、自動変数の **SourceIdentifier** プロパティに `$Event` この値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83648-173">In the value of the **Action** parameter, the **SourceIdentifier** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="83648-174">TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="83648-174">TimeGenerated.</span></span> <span data-ttu-id="83648-175">イベントが生成された時刻を表す **DateTime** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="83648-175">A **DateTime** object that represents the time at which the event was generated.</span></span>
  <span data-ttu-id="83648-176">**Action** パラメーターの値では、自動変数の **timegenerated** プロパティに `$Event` この値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83648-176">In the value of the **Action** parameter, the **TimeGenerated** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="83648-177">MessageData.</span><span class="sxs-lookup"><span data-stu-id="83648-177">MessageData.</span></span> <span data-ttu-id="83648-178">イベント サブスクリプションに関連付けられているデータ。</span><span class="sxs-lookup"><span data-stu-id="83648-178">Data associated with the event subscription.</span></span> <span data-ttu-id="83648-179">ユーザーは、イベントを登録するときに、このデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="83648-179">Users specify this data when they register an event.</span></span> <span data-ttu-id="83648-180">**Action** パラメーターの値では、自動変数の **messagedata** プロパティに `$Event` この値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83648-180">In the value of the **Action** parameter, the **MessageData** property of the `$Event` automatic variable contains this value.</span></span>

## <span data-ttu-id="83648-181">関連リンク</span><span class="sxs-lookup"><span data-stu-id="83648-181">RELATED LINKS</span></span>

[<span data-ttu-id="83648-182">New-Event</span><span class="sxs-lookup"><span data-stu-id="83648-182">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="83648-183">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="83648-183">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="83648-184">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="83648-184">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="83648-185">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="83648-185">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="83648-186">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="83648-186">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="83648-187">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="83648-187">Wait-Event</span></span>](Wait-Event.md)

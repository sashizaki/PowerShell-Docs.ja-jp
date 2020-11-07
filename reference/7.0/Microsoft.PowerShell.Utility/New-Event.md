---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: e842aca53947b4dc9e606f2f6b17532c7c9e0cb4
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346651"
---
# <span data-ttu-id="cdf79-103">New-Event</span><span class="sxs-lookup"><span data-stu-id="cdf79-103">New-Event</span></span>

## <span data-ttu-id="cdf79-104">概要</span><span class="sxs-lookup"><span data-stu-id="cdf79-104">SYNOPSIS</span></span>
<span data-ttu-id="cdf79-105">新しいイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cdf79-105">Creates a new event.</span></span>

## <span data-ttu-id="cdf79-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cdf79-106">SYNTAX</span></span>

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="cdf79-107">Description</span><span class="sxs-lookup"><span data-stu-id="cdf79-107">DESCRIPTION</span></span>

<span data-ttu-id="cdf79-108">コマンドレットにより、 `New-Event` 新しいカスタムイベントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cdf79-108">The `New-Event` cmdlet creates a new custom event.</span></span>

<span data-ttu-id="cdf79-109">カスタム イベントを使用して、プログラム内の状態の変更やプログラムが検出した変更 (ハードウェアまたはシステムの状態、アプリケーションの状態、ディスクの状態、ネットワークの状態、バック グラウンド ジョブの完了など) についてユーザーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="cdf79-109">You can use custom events to notify users about state changes in your program and any change that your program can detect, including hardware or system conditions, application status, disk status, network status, or the completion of a background job.</span></span>

<span data-ttu-id="cdf79-110">カスタム イベントは、セッションで発生するたびにイベント キューに自動的に追加されます。それらをサブスクライブする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cdf79-110">Custom events are automatically added to the event queue in your session whenever they are raised; you do not need to subscribe to them.</span></span> <span data-ttu-id="cdf79-111">ただし、イベントをローカルセッションに転送したり、イベントに応答するアクションを指定したりする場合は、コマンドレットを使用して `Register-EngineEvent` カスタムイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="cdf79-111">However, if you want to forward an event to the local session or specify an action to respond to the event, use the `Register-EngineEvent` cmdlet to subscribe to the custom event.</span></span>

<span data-ttu-id="cdf79-112">カスタム イベントをサブスクライブすると、イベント サブスクライバーがセッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cdf79-112">When you subscribe to a custom event, the event subscriber is added to your session.</span></span> <span data-ttu-id="cdf79-113">コマンドレットを使用してイベントサブスクリプションをキャンセルすると、 `Unregister-Event` イベントサブスクライバーとカスタムイベントがセッションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="cdf79-113">If you cancel the event subscription by using the `Unregister-Event` cmdlet, the event subscriber and custom event are deleted from the session.</span></span> <span data-ttu-id="cdf79-114">カスタムイベントをサブスクライブしていない場合は、イベントを削除するために、プログラムの状態を変更するか、PowerShell セッションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf79-114">If you do not subscribe to the custom event, to delete the event, you must change the program conditions or close the PowerShell session.</span></span>

## <span data-ttu-id="cdf79-115">例</span><span class="sxs-lookup"><span data-stu-id="cdf79-115">EXAMPLES</span></span>

### <span data-ttu-id="cdf79-116">例 1: イベントキューに新しいイベントを作成する</span><span class="sxs-lookup"><span data-stu-id="cdf79-116">Example 1: Create a new event in the event queue</span></span>

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

<span data-ttu-id="cdf79-117">このコマンドは、PowerShell イベントキューに新しいイベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cdf79-117">This command creates a new event in the PowerShell event queue.</span></span> <span data-ttu-id="cdf79-118">このメソッドは、 **Windows の Timer** オブジェクトを使用してイベントを送信します。</span><span class="sxs-lookup"><span data-stu-id="cdf79-118">It uses a **Windows.Timer** object to send the event.</span></span>

### <span data-ttu-id="cdf79-119">例 2: 別のイベントに応答してイベントを発生させる</span><span class="sxs-lookup"><span data-stu-id="cdf79-119">Example 2: Raise an event in response to another event</span></span>

```
PS C:\> function Enable-ProcessCreationEvent
{
   $Query = New-Object System.Management.WqlEventQuery "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1), "TargetInstance isa 'Win32_Process'"
   $ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
   $Identifier = "WMI.ProcessCreated"
   Register-ObjectEvent $ProcessWatcher "EventArrived" -SupportEvent $Identifier -Action
   {
      [void] (New-Event -SourceID "PowerShell.ProcessCreated" -Sender $Args[0] -EventArguments $Args[1].SourceEventArgs.NewEvent.TargetInstance)
   }
}
```

<span data-ttu-id="cdf79-120">このサンプル関数では、コマンドレットを使用して、 `New-Event` 別のイベントに応答してイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="cdf79-120">This sample function uses the `New-Event` cmdlet to raise an event in response to another event.</span></span> <span data-ttu-id="cdf79-121">このコマンドは、コマンドレットを使用して、 `Register-ObjectEvent` 新しいプロセスが作成されたときに発生する Windows Management Instrumentation (WMI) イベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="cdf79-121">The command uses the `Register-ObjectEvent` cmdlet to subscribe to the Windows Management Instrumentation (WMI) event that is raised when a new process is created.</span></span> <span data-ttu-id="cdf79-122">このコマンドは、コマンドレットの **Action** パラメーターを使用して、新しいイベントを作成するコマンドレットを呼び出し `New-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="cdf79-122">The command uses the **Action** parameter of the cmdlet to call the `New-Event` cmdlet, which creates the new event.</span></span>

<span data-ttu-id="cdf79-123">が発生するイベント `New-Event` は PowerShell イベントキューに自動的に追加されるため、そのイベントに登録する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cdf79-123">Because the events that `New-Event` raises are automatically added to the PowerShell event queue, you do not need to register for that event.</span></span>

## <span data-ttu-id="cdf79-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cdf79-124">PARAMETERS</span></span>

### <span data-ttu-id="cdf79-125">-EventArguments</span><span class="sxs-lookup"><span data-stu-id="cdf79-125">-EventArguments</span></span>

<span data-ttu-id="cdf79-126">イベントのオプションを格納しているオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdf79-126">Specifies an object that contains options for the event.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cdf79-127">-MessageData</span><span class="sxs-lookup"><span data-stu-id="cdf79-127">-MessageData</span></span>

<span data-ttu-id="cdf79-128">イベントに関連付けられている追加のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdf79-128">Specifies additional data associated with the event.</span></span> <span data-ttu-id="cdf79-129">このパラメーターの値は、イベント オブジェクトの **MessageData** プロパティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdf79-129">The value of this parameter appears in the **MessageData** property of the event object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cdf79-130">-送信者</span><span class="sxs-lookup"><span data-stu-id="cdf79-130">-Sender</span></span>

<span data-ttu-id="cdf79-131">イベントを発生させるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdf79-131">Specifies the object that raises the event.</span></span> <span data-ttu-id="cdf79-132">既定値は PowerShell エンジンです。</span><span class="sxs-lookup"><span data-stu-id="cdf79-132">The default is the PowerShell engine.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cdf79-133">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="cdf79-133">-SourceIdentifier</span></span>

<span data-ttu-id="cdf79-134">新しいイベントの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cdf79-134">Specifies a name for the new event.</span></span> <span data-ttu-id="cdf79-135">このパラメーターは必須であり、セッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdf79-135">This parameter is required, and it must be unique in the session.</span></span>

<span data-ttu-id="cdf79-136">このパラメーターの値は、イベントの **SourceIdentifier** プロパティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdf79-136">The value of this parameter appears in the **SourceIdentifier** property of the events.</span></span>

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

### <span data-ttu-id="cdf79-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cdf79-137">CommonParameters</span></span>

<span data-ttu-id="cdf79-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cdf79-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cdf79-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdf79-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cdf79-140">入力</span><span class="sxs-lookup"><span data-stu-id="cdf79-140">INPUTS</span></span>

### <span data-ttu-id="cdf79-141">なし</span><span class="sxs-lookup"><span data-stu-id="cdf79-141">None</span></span>

<span data-ttu-id="cdf79-142">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="cdf79-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="cdf79-143">出力</span><span class="sxs-lookup"><span data-stu-id="cdf79-143">OUTPUTS</span></span>

### <span data-ttu-id="cdf79-144">PSEventArgs (システム管理)</span><span class="sxs-lookup"><span data-stu-id="cdf79-144">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="cdf79-145">注</span><span class="sxs-lookup"><span data-stu-id="cdf79-145">NOTES</span></span>

<span data-ttu-id="cdf79-146">Linux または macOS プラットフォームで使用できるイベントソースがありません。</span><span class="sxs-lookup"><span data-stu-id="cdf79-146">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="cdf79-147">新しいカスタム イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="cdf79-147">The new custom event, the event subscription, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="cdf79-148">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="cdf79-148">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="cdf79-149">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cdf79-149">RELATED LINKS</span></span>

[<span data-ttu-id="cdf79-150">Get-Event</span><span class="sxs-lookup"><span data-stu-id="cdf79-150">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="cdf79-151">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="cdf79-151">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="cdf79-152">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="cdf79-152">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="cdf79-153">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="cdf79-153">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="cdf79-154">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="cdf79-154">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="cdf79-155">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="cdf79-155">Wait-Event</span></span>](Wait-Event.md)

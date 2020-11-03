---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Event
ms.openlocfilehash: ee613dd78cbb30dce37c07297411c2d8bf9d832d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214728"
---
# <span data-ttu-id="1fbab-103">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="1fbab-103">Wait-Event</span></span>

## <span data-ttu-id="1fbab-104">概要</span><span class="sxs-lookup"><span data-stu-id="1fbab-104">SYNOPSIS</span></span>
<span data-ttu-id="1fbab-105">特定のイベントが発生するまで待機してから、実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-105">Waits until a particular event is raised before continuing to run.</span></span>

## <span data-ttu-id="1fbab-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1fbab-106">SYNTAX</span></span>

```
Wait-Event [[-SourceIdentifier] <String>] [-Timeout <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="1fbab-107">Description</span><span class="sxs-lookup"><span data-stu-id="1fbab-107">DESCRIPTION</span></span>

<span data-ttu-id="1fbab-108">`Wait-Event`コマンドレットは、特定のイベントが発生するまで、スクリプトまたは関数の実行を中断します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-108">The `Wait-Event` cmdlet suspends execution of a script or function until a particular event is raised.</span></span> <span data-ttu-id="1fbab-109">イベントが検出されると、実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="1fbab-109">Execution resumes when the event is detected.</span></span> <span data-ttu-id="1fbab-110">待機を取り消すには、 <kbd>ctrl</kbd> + <kbd>C</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-110">To cancel the wait, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="1fbab-111">この機能によって、イベントのポーリングに代わる別の方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1fbab-111">This feature provides an alternative to polling for an event.</span></span> <span data-ttu-id="1fbab-112">また、2つの異なる方法でイベントへの応答を決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fbab-112">It also allows you to determine the response to an event in two different ways:</span></span>

- <span data-ttu-id="1fbab-113">イベントサブスクリプションの **Action** パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="1fbab-113">using the **Action** parameter of the event subscription</span></span>
- <span data-ttu-id="1fbab-114">イベントが返され、アクションで応答するまで待機しています</span><span class="sxs-lookup"><span data-stu-id="1fbab-114">waiting for an event to return and then respond with an action</span></span>

## <span data-ttu-id="1fbab-115">例</span><span class="sxs-lookup"><span data-stu-id="1fbab-115">EXAMPLES</span></span>

### <span data-ttu-id="1fbab-116">例 1: 次のイベントを待機する</span><span class="sxs-lookup"><span data-stu-id="1fbab-116">Example 1: Wait for the next event</span></span>

<span data-ttu-id="1fbab-117">この例では、次のイベントが発生するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-117">This example waits for the next event that is raised.</span></span>

```powershell
Wait-Event
```

### <span data-ttu-id="1fbab-118">例 2: 指定したソース識別子を持つイベントを待機する</span><span class="sxs-lookup"><span data-stu-id="1fbab-118">Example 2: Wait for an event with a specified source identifier</span></span>

<span data-ttu-id="1fbab-119">この例では、次のイベントが発生し、ソース識別子が ProcessStarted であることを待機します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-119">This example waits for the next event that is raised and that has a source identifier of ProcessStarted.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="1fbab-120">例 3: timer elapsed イベントを待機する</span><span class="sxs-lookup"><span data-stu-id="1fbab-120">Example 3: Wait for a timer elapsed event</span></span>

<span data-ttu-id="1fbab-121">この例では、コマンドレットを使用して、 `Wait-Event` 2000 ミリ秒に設定されているタイマーのタイマーイベントを待機します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-121">This example uses the `Wait-Event` cmdlet to wait for a timer event on a timer that is set for 2000 milliseconds.</span></span>

```powershell
$Timer = New-Object Timers.Timer
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Elapsed'
}
Register-ObjectEvent @objectEventArgs
$Timer.Interval = 2000
$Timer.Autoreset = $False
$Timer.Enabled = $True
Wait-Event Timer.Elapsed
```

```Output
ComputerName     :
RunspaceId       : bb560b14-ff43-48d4-b801-5adc31bbc6fb
EventIdentifier  : 1
Sender           : System.Timers.Timer
SourceEventArgs  : System.Timers.ElapsedEventArgs
SourceArgs       : {System.Timers.Timer, System.Timers.ElapsedEventArgs}
SourceIdentifier : Timer.Elapsed
TimeGenerated    : 4/23/2020 2:30:37 PM
MessageData      :
```

### <span data-ttu-id="1fbab-122">例 4: 指定したタイムアウト後にイベントを待機する</span><span class="sxs-lookup"><span data-stu-id="1fbab-122">Example 4: Wait for an event after a specified timeout</span></span>

<span data-ttu-id="1fbab-123">この例では、次のイベントが発生し、ソース識別子が **Processstarted** であることを、最大90秒間待機します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-123">This example waits up to 90 seconds for the next event that is raised and that has a source identifier of **ProcessStarted** .</span></span> <span data-ttu-id="1fbab-124">指定された時間が経過すると、待機は終了します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-124">If the specified time expires, the wait ends.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted" -Timeout 90
```

## <span data-ttu-id="1fbab-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1fbab-125">PARAMETERS</span></span>

### <span data-ttu-id="1fbab-126">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="1fbab-126">-SourceIdentifier</span></span>

<span data-ttu-id="1fbab-127">このコマンドレットがイベントを待機するソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-127">Specifies the source identifier that this cmdlet waits for events.</span></span>
<span data-ttu-id="1fbab-128">既定では、は、 `Wait-Event` 任意のイベントを待機します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-128">By default, `Wait-Event` waits for any event.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1fbab-129">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="1fbab-129">-Timeout</span></span>

<span data-ttu-id="1fbab-130">イベントが発生するまで待機する最大時間を秒単位で指定し `Wait-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="1fbab-130">Specifies the maximum time, in seconds, that `Wait-Event` waits for the event to occur.</span></span> <span data-ttu-id="1fbab-131">既定値は、無期限に待機することを示す -1 です。</span><span class="sxs-lookup"><span data-stu-id="1fbab-131">The default, -1, waits indefinitely.</span></span> <span data-ttu-id="1fbab-132">コマンドを送信すると、タイミングが開始され `Wait-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="1fbab-132">The timing starts when you submit the `Wait-Event` command.</span></span>

<span data-ttu-id="1fbab-133">指定された時間を超えた場合、イベントが発生していない場合でも、待機が終了し、コマンド プロンプトが返されます。</span><span class="sxs-lookup"><span data-stu-id="1fbab-133">If the specified time is exceeded, the wait ends and the command prompt returns, even if the event has not been raised.</span></span> <span data-ttu-id="1fbab-134">エラー メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1fbab-134">No error message is displayed.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1fbab-135">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fbab-135">CommonParameters</span></span>

<span data-ttu-id="1fbab-136">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1fbab-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1fbab-137">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fbab-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1fbab-138">入力</span><span class="sxs-lookup"><span data-stu-id="1fbab-138">INPUTS</span></span>

### <span data-ttu-id="1fbab-139">System.String</span><span class="sxs-lookup"><span data-stu-id="1fbab-139">System.String</span></span>

## <span data-ttu-id="1fbab-140">出力</span><span class="sxs-lookup"><span data-stu-id="1fbab-140">OUTPUTS</span></span>

### <span data-ttu-id="1fbab-141">PSEventArgs (システム管理)</span><span class="sxs-lookup"><span data-stu-id="1fbab-141">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="1fbab-142">注</span><span class="sxs-lookup"><span data-stu-id="1fbab-142">NOTES</span></span>

<span data-ttu-id="1fbab-143">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="1fbab-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="1fbab-144">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="1fbab-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="1fbab-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1fbab-145">RELATED LINKS</span></span>

[<span data-ttu-id="1fbab-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="1fbab-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="1fbab-147">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="1fbab-147">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="1fbab-148">New-Event</span><span class="sxs-lookup"><span data-stu-id="1fbab-148">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="1fbab-149">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="1fbab-149">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="1fbab-150">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="1fbab-150">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="1fbab-151">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="1fbab-151">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="1fbab-152">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="1fbab-152">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="1fbab-153">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="1fbab-153">Wait-Event</span></span>](Wait-Event.md)


---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 9373cb1c5080b95317925937ccf04baa3d335bea
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344152"
---
# <span data-ttu-id="6e597-103">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="6e597-103">Unregister-Event</span></span>

## <span data-ttu-id="6e597-104">概要</span><span class="sxs-lookup"><span data-stu-id="6e597-104">SYNOPSIS</span></span>
<span data-ttu-id="6e597-105">イベントのサブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="6e597-105">Cancels an event subscription.</span></span>

## <span data-ttu-id="6e597-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e597-106">SYNTAX</span></span>

### <span data-ttu-id="6e597-107">BySource (既定値)</span><span class="sxs-lookup"><span data-stu-id="6e597-107">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6e597-108">ById</span><span class="sxs-lookup"><span data-stu-id="6e597-108">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6e597-109">Description</span><span class="sxs-lookup"><span data-stu-id="6e597-109">DESCRIPTION</span></span>

<span data-ttu-id="6e597-110">`Unregister-Event`コマンドレットでは `Register-EngineEvent` 、、 `Register-ObjectEvent` 、またはコマンドレットを使用して作成されたイベントサブスクリプションをキャンセルし `Register-WmiEvent` ます。</span><span class="sxs-lookup"><span data-stu-id="6e597-110">The `Unregister-Event` cmdlet cancels an event subscription that was created by using the `Register-EngineEvent`, `Register-ObjectEvent`, or `Register-WmiEvent` cmdlet.</span></span>

<span data-ttu-id="6e597-111">イベント サブスクリプションが取り消されると、セッションからイベント サブスクライバーが削除され、サブスクライブされたイベントはイベント キューに追加されません。</span><span class="sxs-lookup"><span data-stu-id="6e597-111">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span> <span data-ttu-id="6e597-112">コマンドレットを使用して作成されたイベントへのサブスクリプションをキャンセルすると、 `New-Event` 新しいイベントもセッションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="6e597-112">When you cancel a subscription to an event created by using the `New-Event` cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="6e597-113">`Unregister-Event` イベントキューからイベントを削除しません。</span><span class="sxs-lookup"><span data-stu-id="6e597-113">`Unregister-Event` does not delete events from the event queue.</span></span> <span data-ttu-id="6e597-114">イベントを削除するには、コマンドレットを使用し `Remove-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="6e597-114">To delete events, use the `Remove-Event` cmdlet.</span></span>

## <span data-ttu-id="6e597-115">例</span><span class="sxs-lookup"><span data-stu-id="6e597-115">EXAMPLES</span></span>

### <span data-ttu-id="6e597-116">例 1: ソース id によってイベントサブスクリプションを取り消す</span><span class="sxs-lookup"><span data-stu-id="6e597-116">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="6e597-117">このコマンドは、ソース識別子が ProcessStarted ているイベントサブスクリプションをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="6e597-117">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="6e597-118">イベントのソース識別子を検索するには、コマンドレットを使用し `Get-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="6e597-118">To find the source identifier of an event, use the `Get-Event` cmdlet.</span></span> <span data-ttu-id="6e597-119">イベントサブスクリプションのソース識別子を検索するには、コマンドレットを使用し `Get-EventSubscriber` ます。</span><span class="sxs-lookup"><span data-stu-id="6e597-119">To find the source identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="6e597-120">例 2: サブスクリプション id によってイベントサブスクリプションを取り消す</span><span class="sxs-lookup"><span data-stu-id="6e597-120">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="6e597-121">このコマンドは、サブスクリプション識別子が 2 のイベント サブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="6e597-121">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="6e597-122">イベントサブスクリプションのサブスクリプション識別子を検索するには、コマンドレットを使用し `Get-EventSubscriber` ます。</span><span class="sxs-lookup"><span data-stu-id="6e597-122">To find the subscription identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="6e597-123">例 3: すべてのイベントサブスクリプションを取り消す</span><span class="sxs-lookup"><span data-stu-id="6e597-123">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="6e597-124">このコマンドは、セッション内のすべてのイベント サブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="6e597-124">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="6e597-125">このコマンドは、コマンドレットを使用して、 `Get-EventSubscriber` セッション内のすべてのイベントサブスクライバーオブジェクトを取得します。これには、イベント登録コマンドレットの **supportevent** パラメーターを使用して非表示になっているサブスクライバーも含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e597-125">The command uses the `Get-EventSubscriber` cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the **SupportEvent** parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="6e597-126">パイプライン演算子 () を使用して `|` 、サブスクライバーオブジェクトをに送信します。これにより `Unregister-Event` 、セッションからサブスクライバーオブジェクトが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6e597-126">It uses a pipeline operator (`|`) to send the subscriber objects to `Unregister-Event`, which deletes them from the session.</span></span> <span data-ttu-id="6e597-127">タスクを完了するには、で **Force** パラメーターも必要です `Unregister-Event` 。</span><span class="sxs-lookup"><span data-stu-id="6e597-127">To complete the task, the **Force** parameter is also required on `Unregister-Event`.</span></span>

## <span data-ttu-id="6e597-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e597-128">PARAMETERS</span></span>

### <span data-ttu-id="6e597-129">-Force</span><span class="sxs-lookup"><span data-stu-id="6e597-129">-Force</span></span>

<span data-ttu-id="6e597-130">、、およびの **Supportevent** パラメーターを使用して非表示にされたサブスクリプションも含め、すべてのイベントサブスクリプションをキャンセルし `Register-ObjectEvent` `Register-WmiEvent` `Register-EngineEvent` ます。</span><span class="sxs-lookup"><span data-stu-id="6e597-130">Cancels all event subscriptions, including subscriptions that were hidden by using the **SupportEvent** parameter of `Register-ObjectEvent`, `Register-WmiEvent`, and `Register-EngineEvent`.</span></span>

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

### <span data-ttu-id="6e597-131">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="6e597-131">-SourceIdentifier</span></span>

<span data-ttu-id="6e597-132">このコマンドレットでイベントサブスクリプションをキャンセルするソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e597-132">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="6e597-133">各コマンドには、 **SourceIdentifier** パラメーターまたは **SubscriptionId** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e597-133">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e597-134">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="6e597-134">-SubscriptionId</span></span>

<span data-ttu-id="6e597-135">このコマンドレットによってイベントサブスクリプションが取り消されるソース識別子 ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e597-135">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="6e597-136">各コマンドには、 **SourceIdentifier** パラメーターまたは **SubscriptionId** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e597-136">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e597-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6e597-137">-Confirm</span></span>

<span data-ttu-id="6e597-138">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e597-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6e597-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6e597-139">-WhatIf</span></span>

<span data-ttu-id="6e597-140">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="6e597-140">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6e597-141">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="6e597-141">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6e597-142">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e597-142">CommonParameters</span></span>

<span data-ttu-id="6e597-143">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6e597-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e597-144">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e597-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e597-145">入力</span><span class="sxs-lookup"><span data-stu-id="6e597-145">INPUTS</span></span>

### <span data-ttu-id="6e597-146">PSEventSubscriber (システム管理)</span><span class="sxs-lookup"><span data-stu-id="6e597-146">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="6e597-147">パイプを使用して、出力をからにパイプすることができ `Get-EventSubscriber` `Unregister-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="6e597-147">You can pipe the output from `Get-EventSubscriber` to `Unregister-Event`.</span></span>

## <span data-ttu-id="6e597-148">出力</span><span class="sxs-lookup"><span data-stu-id="6e597-148">OUTPUTS</span></span>

### <span data-ttu-id="6e597-149">なし</span><span class="sxs-lookup"><span data-stu-id="6e597-149">None</span></span>

<span data-ttu-id="6e597-150">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="6e597-150">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="6e597-151">注</span><span class="sxs-lookup"><span data-stu-id="6e597-151">NOTES</span></span>

<span data-ttu-id="6e597-152">Linux または macOS プラットフォームで使用できるイベントソースがありません。</span><span class="sxs-lookup"><span data-stu-id="6e597-152">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="6e597-153">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="6e597-153">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="6e597-154">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="6e597-154">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="6e597-155">`Unregister-Event` コマンドレットを使用して `New-Event` イベントをサブスクライブしていない限り、コマンドレットを使用して作成されたイベントを削除することはできません `Register-EngineEvent` 。</span><span class="sxs-lookup"><span data-stu-id="6e597-155">`Unregister-Event` cannot delete events created by using the `New-Event` cmdlet unless you have subscribed to the event by using the `Register-EngineEvent` cmdlet.</span></span> <span data-ttu-id="6e597-156">セッションからカスタム イベントを削除するには、プログラムを使用してそれを削除するか、セッションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e597-156">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

## <span data-ttu-id="6e597-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6e597-157">RELATED LINKS</span></span>

[<span data-ttu-id="6e597-158">Get-Event</span><span class="sxs-lookup"><span data-stu-id="6e597-158">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="6e597-159">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="6e597-159">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="6e597-160">New-Event</span><span class="sxs-lookup"><span data-stu-id="6e597-160">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="6e597-161">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="6e597-161">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="6e597-162">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="6e597-162">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="6e597-163">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="6e597-163">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="6e597-164">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="6e597-164">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="6e597-165">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="6e597-165">Wait-Event</span></span>](Wait-Event.md)

---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 863dbba4c106f1f57c9396823692620bb358b646
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600803"
---
# <span data-ttu-id="b36e2-102">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="b36e2-102">Unregister-Event</span></span>

## <span data-ttu-id="b36e2-103">概要</span><span class="sxs-lookup"><span data-stu-id="b36e2-103">SYNOPSIS</span></span>
<span data-ttu-id="b36e2-104">イベントのサブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="b36e2-104">Cancels an event subscription.</span></span>

## <span data-ttu-id="b36e2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b36e2-105">SYNTAX</span></span>

### <span data-ttu-id="b36e2-106">BySource (既定値)</span><span class="sxs-lookup"><span data-stu-id="b36e2-106">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b36e2-107">ById</span><span class="sxs-lookup"><span data-stu-id="b36e2-107">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b36e2-108">Description</span><span class="sxs-lookup"><span data-stu-id="b36e2-108">DESCRIPTION</span></span>

<span data-ttu-id="b36e2-109">`Unregister-Event`コマンドレットでは `Register-EngineEvent` 、、 `Register-ObjectEvent` 、またはコマンドレットを使用して作成されたイベントサブスクリプションをキャンセルし `Register-WmiEvent` ます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-109">The `Unregister-Event` cmdlet cancels an event subscription that was created by using the `Register-EngineEvent`, `Register-ObjectEvent`, or `Register-WmiEvent` cmdlet.</span></span>

<span data-ttu-id="b36e2-110">イベント サブスクリプションが取り消されると、セッションからイベント サブスクライバーが削除され、サブスクライブされたイベントはイベント キューに追加されません。</span><span class="sxs-lookup"><span data-stu-id="b36e2-110">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span> <span data-ttu-id="b36e2-111">コマンドレットを使用して作成されたイベントへのサブスクリプションをキャンセルすると、 `New-Event` 新しいイベントもセッションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-111">When you cancel a subscription to an event created by using the `New-Event` cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="b36e2-112">`Unregister-Event` イベントキューからイベントを削除しません。</span><span class="sxs-lookup"><span data-stu-id="b36e2-112">`Unregister-Event` does not delete events from the event queue.</span></span> <span data-ttu-id="b36e2-113">イベントを削除するには、コマンドレットを使用し `Remove-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-113">To delete events, use the `Remove-Event` cmdlet.</span></span>

## <span data-ttu-id="b36e2-114">例</span><span class="sxs-lookup"><span data-stu-id="b36e2-114">EXAMPLES</span></span>

### <span data-ttu-id="b36e2-115">例 1: ソース id によってイベントサブスクリプションを取り消す</span><span class="sxs-lookup"><span data-stu-id="b36e2-115">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="b36e2-116">このコマンドは、ソース識別子が ProcessStarted ているイベントサブスクリプションをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="b36e2-116">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="b36e2-117">イベントのソース識別子を検索するには、コマンドレットを使用し `Get-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-117">To find the source identifier of an event, use the `Get-Event` cmdlet.</span></span> <span data-ttu-id="b36e2-118">イベントサブスクリプションのソース識別子を検索するには、コマンドレットを使用し `Get-EventSubscriber` ます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-118">To find the source identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="b36e2-119">例 2: サブスクリプション id によってイベントサブスクリプションを取り消す</span><span class="sxs-lookup"><span data-stu-id="b36e2-119">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="b36e2-120">このコマンドは、サブスクリプション識別子が 2 のイベント サブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="b36e2-120">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="b36e2-121">イベントサブスクリプションのサブスクリプション識別子を検索するには、コマンドレットを使用し `Get-EventSubscriber` ます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-121">To find the subscription identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="b36e2-122">例 3: すべてのイベントサブスクリプションを取り消す</span><span class="sxs-lookup"><span data-stu-id="b36e2-122">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="b36e2-123">このコマンドは、セッション内のすべてのイベント サブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="b36e2-123">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="b36e2-124">このコマンドは、コマンドレットを使用して、 `Get-EventSubscriber` セッション内のすべてのイベントサブスクライバーオブジェクトを取得します。これには、イベント登録コマンドレットの **supportevent** パラメーターを使用して非表示になっているサブスクライバーも含まれます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-124">The command uses the `Get-EventSubscriber` cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the **SupportEvent** parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="b36e2-125">パイプライン演算子 () を使用して `|` 、サブスクライバーオブジェクトをに送信します。これにより `Unregister-Event` 、セッションからサブスクライバーオブジェクトが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-125">It uses a pipeline operator (`|`) to send the subscriber objects to `Unregister-Event`, which deletes them from the session.</span></span> <span data-ttu-id="b36e2-126">タスクを完了するには、で **Force** パラメーターも必要です `Unregister-Event` 。</span><span class="sxs-lookup"><span data-stu-id="b36e2-126">To complete the task, the **Force** parameter is also required on `Unregister-Event`.</span></span>

## <span data-ttu-id="b36e2-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b36e2-127">PARAMETERS</span></span>

### <span data-ttu-id="b36e2-128">-Force</span><span class="sxs-lookup"><span data-stu-id="b36e2-128">-Force</span></span>

<span data-ttu-id="b36e2-129">、、およびの **Supportevent** パラメーターを使用して非表示にされたサブスクリプションも含め、すべてのイベントサブスクリプションをキャンセルし `Register-ObjectEvent` `Register-WmiEvent` `Register-EngineEvent` ます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-129">Cancels all event subscriptions, including subscriptions that were hidden by using the **SupportEvent** parameter of `Register-ObjectEvent`, `Register-WmiEvent`, and `Register-EngineEvent`.</span></span>

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

### <span data-ttu-id="b36e2-130">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="b36e2-130">-SourceIdentifier</span></span>

<span data-ttu-id="b36e2-131">このコマンドレットでイベントサブスクリプションをキャンセルするソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="b36e2-131">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="b36e2-132">各コマンドには、 **SourceIdentifier** パラメーターまたは **SubscriptionId** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36e2-132">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

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

### <span data-ttu-id="b36e2-133">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="b36e2-133">-SubscriptionId</span></span>

<span data-ttu-id="b36e2-134">このコマンドレットによってイベントサブスクリプションが取り消されるソース識別子 ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="b36e2-134">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="b36e2-135">各コマンドには、 **SourceIdentifier** パラメーターまたは **SubscriptionId** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36e2-135">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

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

### <span data-ttu-id="b36e2-136">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b36e2-136">-Confirm</span></span>

<span data-ttu-id="b36e2-137">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-137">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b36e2-138">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b36e2-138">-WhatIf</span></span>

<span data-ttu-id="b36e2-139">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="b36e2-139">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b36e2-140">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="b36e2-140">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b36e2-141">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b36e2-141">CommonParameters</span></span>

<span data-ttu-id="b36e2-142">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b36e2-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b36e2-143">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b36e2-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b36e2-144">入力</span><span class="sxs-lookup"><span data-stu-id="b36e2-144">INPUTS</span></span>

### <span data-ttu-id="b36e2-145">PSEventSubscriber (システム管理)</span><span class="sxs-lookup"><span data-stu-id="b36e2-145">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="b36e2-146">パイプを使用して、出力をからにパイプすることができ `Get-EventSubscriber` `Unregister-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-146">You can pipe the output from `Get-EventSubscriber` to `Unregister-Event`.</span></span>

## <span data-ttu-id="b36e2-147">出力</span><span class="sxs-lookup"><span data-stu-id="b36e2-147">OUTPUTS</span></span>

### <span data-ttu-id="b36e2-148">なし</span><span class="sxs-lookup"><span data-stu-id="b36e2-148">None</span></span>

<span data-ttu-id="b36e2-149">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="b36e2-149">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="b36e2-150">注</span><span class="sxs-lookup"><span data-stu-id="b36e2-150">NOTES</span></span>

<span data-ttu-id="b36e2-151">Linux または macOS プラットフォームで使用できるイベントソースがありません。</span><span class="sxs-lookup"><span data-stu-id="b36e2-151">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="b36e2-152">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="b36e2-152">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="b36e2-153">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="b36e2-153">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="b36e2-154">`Unregister-Event` コマンドレットを使用して `New-Event` イベントをサブスクライブしていない限り、コマンドレットを使用して作成されたイベントを削除することはできません `Register-EngineEvent` 。</span><span class="sxs-lookup"><span data-stu-id="b36e2-154">`Unregister-Event` cannot delete events created by using the `New-Event` cmdlet unless you have subscribed to the event by using the `Register-EngineEvent` cmdlet.</span></span> <span data-ttu-id="b36e2-155">セッションからカスタム イベントを削除するには、プログラムを使用してそれを削除するか、セッションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36e2-155">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

## <span data-ttu-id="b36e2-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b36e2-156">RELATED LINKS</span></span>

[<span data-ttu-id="b36e2-157">Get-Event</span><span class="sxs-lookup"><span data-stu-id="b36e2-157">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="b36e2-158">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="b36e2-158">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="b36e2-159">New-Event</span><span class="sxs-lookup"><span data-stu-id="b36e2-159">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="b36e2-160">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="b36e2-160">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="b36e2-161">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="b36e2-161">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="b36e2-162">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="b36e2-162">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="b36e2-163">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="b36e2-163">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="b36e2-164">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="b36e2-164">Wait-Event</span></span>](Wait-Event.md)

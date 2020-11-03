---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 748ef22203f59090be6f5491ea76b50d54930a95
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217563"
---
# <span data-ttu-id="4f595-103">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4f595-103">Unregister-Event</span></span>

## <span data-ttu-id="4f595-104">概要</span><span class="sxs-lookup"><span data-stu-id="4f595-104">SYNOPSIS</span></span>
<span data-ttu-id="4f595-105">イベントのサブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="4f595-105">Cancels an event subscription.</span></span>

## <span data-ttu-id="4f595-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4f595-106">SYNTAX</span></span>

### <span data-ttu-id="4f595-107">BySource (既定値)</span><span class="sxs-lookup"><span data-stu-id="4f595-107">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4f595-108">ById</span><span class="sxs-lookup"><span data-stu-id="4f595-108">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4f595-109">Description</span><span class="sxs-lookup"><span data-stu-id="4f595-109">DESCRIPTION</span></span>
<span data-ttu-id="4f595-110">イベントの登録 **解除** コマンドレットは、Register-engineevent、Register/objectevent、または Register-WmiEvent コマンドレットを使用して作成されたイベントサブスクリプションをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="4f595-110">The **Unregister-Event** cmdlet cancels an event subscription that was created by using the Register-EngineEvent, Register-ObjectEvent, or Register-WmiEvent cmdlet.</span></span>

<span data-ttu-id="4f595-111">イベント サブスクリプションが取り消されると、セッションからイベント サブスクライバーが削除され、サブスクライブされたイベントはイベント キューに追加されません。</span><span class="sxs-lookup"><span data-stu-id="4f595-111">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span>
<span data-ttu-id="4f595-112">New-Event コマンドレットを使用して作成されたイベントのサブスクリプションを取り消すと、新しいイベントはセッションからも削除されます。</span><span class="sxs-lookup"><span data-stu-id="4f595-112">When you cancel a subscription to an event created by using the New-Event cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="4f595-113">**登録解除-** イベントはイベントキューからイベントを削除しません。</span><span class="sxs-lookup"><span data-stu-id="4f595-113">**Unregister-Event** does not delete events from the event queue.</span></span>
<span data-ttu-id="4f595-114">イベントを削除するには、Remove-Event コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f595-114">To delete events, use the Remove-Event cmdlet.</span></span>

## <span data-ttu-id="4f595-115">例</span><span class="sxs-lookup"><span data-stu-id="4f595-115">EXAMPLES</span></span>

### <span data-ttu-id="4f595-116">例 1: ソース id によってイベントサブスクリプションを取り消す</span><span class="sxs-lookup"><span data-stu-id="4f595-116">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="4f595-117">このコマンドは、ソース識別子が ProcessStarted ているイベントサブスクリプションをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="4f595-117">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="4f595-118">イベントのソース識別子を調べるには、Get-Event コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f595-118">To find the source identifier of an event, use the Get-Event cmdlet.</span></span>
<span data-ttu-id="4f595-119">イベントサブスクリプションのソース識別子を検索するには、 **Get EventSubscriber** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f595-119">To find the source identifier of an event subscription, use the **Get-EventSubscriber** cmdlet.</span></span>

### <span data-ttu-id="4f595-120">例 2: サブスクリプション id によってイベントサブスクリプションを取り消す</span><span class="sxs-lookup"><span data-stu-id="4f595-120">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="4f595-121">このコマンドは、サブスクリプション識別子が 2 のイベント サブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="4f595-121">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="4f595-122">イベントサブスクリプションのサブスクリプション識別子を検索するには、 **Get EventSubscriber** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f595-122">To find the subscription identifier of an event subscription, use the **Get-EventSubscriber** cmdlet.</span></span>

### <span data-ttu-id="4f595-123">例 3: すべてのイベントサブスクリプションを取り消す</span><span class="sxs-lookup"><span data-stu-id="4f595-123">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="4f595-124">このコマンドは、セッション内のすべてのイベント サブスクリプションを取り消します。</span><span class="sxs-lookup"><span data-stu-id="4f595-124">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="4f595-125">このコマンドは、 **Get EventSubscriber** コマンドレットを使用して、セッション内のすべてのイベントサブスクライバーオブジェクトを取得します。これには、イベント登録コマンドレットの *supportevent* パラメーターを使用して非表示になっているサブスクライバーも含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f595-125">The command uses the **Get-EventSubscriber** cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the *SupportEvent* parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="4f595-126">パイプライン演算子 (|) を使用して、サブスクライバーオブジェクトを **登録解除イベント** に送信します。このオブジェクトは、セッションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="4f595-126">It uses a pipeline operator (|) to send the subscriber objects to **Unregister-Event** , which deletes them from the session.</span></span>
<span data-ttu-id="4f595-127">タスクを完了するには、 **イベントの登録解除** で *Force* パラメーターも必要です。</span><span class="sxs-lookup"><span data-stu-id="4f595-127">To complete the task, the *Force* parameter is also required on **Unregister-Event**.</span></span>

## <span data-ttu-id="4f595-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4f595-128">PARAMETERS</span></span>

### <span data-ttu-id="4f595-129">-Force</span><span class="sxs-lookup"><span data-stu-id="4f595-129">-Force</span></span>
<span data-ttu-id="4f595-130">**Register-engineevent** の *supportevent* **パラメーターを使用** して非表示になっていたサブスクリプションを **含め、すべて** のイベントサブスクリプションをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="4f595-130">Cancels all event subscriptions, including subscriptions that were hidden by using the *SupportEvent* parameter of **Register-ObjectEvent** , **Register-WmiEvent** , and **Register-EngineEvent**.</span></span>

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

### <span data-ttu-id="4f595-131">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="4f595-131">-SourceIdentifier</span></span>
<span data-ttu-id="4f595-132">このコマンドレットでイベントサブスクリプションをキャンセルするソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f595-132">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="4f595-133">各コマンドには、 *SourceIdentifier* パラメーターまたは *SubscriptionId* パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f595-133">A *SourceIdentifier* or *SubscriptionId* parameter must be included in every command.</span></span>

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

### <span data-ttu-id="4f595-134">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="4f595-134">-SubscriptionId</span></span>
<span data-ttu-id="4f595-135">このコマンドレットによってイベントサブスクリプションが取り消されるソース識別子 ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f595-135">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="4f595-136">各コマンドには、 *SourceIdentifier* パラメーターまたは *SubscriptionId* パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f595-136">A *SourceIdentifier* or *SubscriptionId* parameter must be included in every command.</span></span>

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

### <span data-ttu-id="4f595-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4f595-137">-Confirm</span></span>
<span data-ttu-id="4f595-138">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f595-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4f595-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4f595-139">-WhatIf</span></span>
<span data-ttu-id="4f595-140">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4f595-140">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4f595-141">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4f595-141">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4f595-142">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f595-142">CommonParameters</span></span>
<span data-ttu-id="4f595-143">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4f595-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4f595-144">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f595-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4f595-145">入力</span><span class="sxs-lookup"><span data-stu-id="4f595-145">INPUTS</span></span>

### <span data-ttu-id="4f595-146">PSEventSubscriber (システム管理)</span><span class="sxs-lookup"><span data-stu-id="4f595-146">System.Management.Automation.PSEventSubscriber</span></span>
<span data-ttu-id="4f595-147">パイプを使用して、出力を Get-EventSubscriber から **登録解除** することができます。</span><span class="sxs-lookup"><span data-stu-id="4f595-147">You can pipe the output from Get-EventSubscriber to **Unregister-Event**.</span></span>

## <span data-ttu-id="4f595-148">出力</span><span class="sxs-lookup"><span data-stu-id="4f595-148">OUTPUTS</span></span>

### <span data-ttu-id="4f595-149">なし</span><span class="sxs-lookup"><span data-stu-id="4f595-149">None</span></span>
<span data-ttu-id="4f595-150">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="4f595-150">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="4f595-151">注</span><span class="sxs-lookup"><span data-stu-id="4f595-151">NOTES</span></span>

* <span data-ttu-id="4f595-152">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="4f595-152">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="4f595-153">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="4f595-153">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

  <span data-ttu-id="4f595-154">**Register-engineevent** コマンドレットを使用してイベントをサブスクライブしている場合を除き、New-Event コマンドレットを使用して作成されたイベントを削除することは **できません** 。</span><span class="sxs-lookup"><span data-stu-id="4f595-154">**Unregister-Event** cannot delete events created by using the New-Event cmdlet unless you have subscribed to the event by using the **Register-EngineEvent** cmdlet.</span></span>
<span data-ttu-id="4f595-155">セッションからカスタム イベントを削除するには、プログラムを使用してそれを削除するか、セッションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f595-155">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

*

## <span data-ttu-id="4f595-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4f595-156">RELATED LINKS</span></span>

[<span data-ttu-id="4f595-157">Get-Event</span><span class="sxs-lookup"><span data-stu-id="4f595-157">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="4f595-158">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="4f595-158">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="4f595-159">New-Event</span><span class="sxs-lookup"><span data-stu-id="4f595-159">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="4f595-160">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="4f595-160">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="4f595-161">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="4f595-161">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="4f595-162">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="4f595-162">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="4f595-163">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4f595-163">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="4f595-164">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="4f595-164">Wait-Event</span></span>](Wait-Event.md)


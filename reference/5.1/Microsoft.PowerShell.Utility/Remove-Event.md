---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 19841624e836f7cf8080487c977f11b88dd3174e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213752"
---
# <span data-ttu-id="4f42e-103">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="4f42e-103">Remove-Event</span></span>

## <span data-ttu-id="4f42e-104">概要</span><span class="sxs-lookup"><span data-stu-id="4f42e-104">SYNOPSIS</span></span>
<span data-ttu-id="4f42e-105">イベントをイベント キューから削除します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-105">Deletes events from the event queue.</span></span>

## <span data-ttu-id="4f42e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4f42e-106">SYNTAX</span></span>

### <span data-ttu-id="4f42e-107">BySource (既定値)</span><span class="sxs-lookup"><span data-stu-id="4f42e-107">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4f42e-108">ByIdentifier</span><span class="sxs-lookup"><span data-stu-id="4f42e-108">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4f42e-109">Description</span><span class="sxs-lookup"><span data-stu-id="4f42e-109">DESCRIPTION</span></span>
<span data-ttu-id="4f42e-110">**イベントの削除** コマンドレットは、現在のセッションのイベントキューからイベントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-110">The **Remove-Event** cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="4f42e-111">このコマンドレットは、現在キューにあるイベントのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-111">This cmdlet deletes only the events currently in the queue.</span></span>
<span data-ttu-id="4f42e-112">イベントの登録の取り消しまたはサブスクリプションの解除を行うには、Unregister-Event コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-112">To cancel event registrations or unsubscribe, use the Unregister-Event cmdlet.</span></span>

## <span data-ttu-id="4f42e-113">例</span><span class="sxs-lookup"><span data-stu-id="4f42e-113">EXAMPLES</span></span>

### <span data-ttu-id="4f42e-114">例 1: ソース識別子を使用してイベントを削除する</span><span class="sxs-lookup"><span data-stu-id="4f42e-114">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="4f42e-115">このコマンドは、イベントキューからプロセスのソース識別子が開始されたイベントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-115">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="4f42e-116">例 2: イベント識別子でイベントを削除する</span><span class="sxs-lookup"><span data-stu-id="4f42e-116">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="4f42e-117">このコマンドは、イベント ID が 30 のイベントをイベント キューから削除します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-117">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="4f42e-118">例 3: すべてのイベントを削除する</span><span class="sxs-lookup"><span data-stu-id="4f42e-118">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="4f42e-119">このコマンドは、イベント キューからすべてのイベントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-119">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="4f42e-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4f42e-120">PARAMETERS</span></span>

### <span data-ttu-id="4f42e-121">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="4f42e-121">-EventIdentifier</span></span>
<span data-ttu-id="4f42e-122">コマンドレットが削除するイベント識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-122">Specifies the event identifier for which the cmdlet deletes.</span></span>
<span data-ttu-id="4f42e-123">すべてのコマンドには、 *EventIdentifier* パラメーターまたは *SourceIdentifier* パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="4f42e-123">An *EventIdentifier* or *SourceIdentifier* parameter is required in every command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ByIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4f42e-124">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="4f42e-124">-SourceIdentifier</span></span>
<span data-ttu-id="4f42e-125">このコマンドレットによってイベントが削除されるソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-125">Specifies the source identifier for which this cmdlet deletes events from.</span></span>
<span data-ttu-id="4f42e-126">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4f42e-126">Wildcards are not permitted.</span></span>
<span data-ttu-id="4f42e-127">すべてのコマンドには、 *EventIdentifier* パラメーターまたは *SourceIdentifier* パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="4f42e-127">An *EventIdentifier* or *SourceIdentifier* parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f42e-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4f42e-128">-Confirm</span></span>
<span data-ttu-id="4f42e-129">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f42e-129">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4f42e-130">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4f42e-130">-WhatIf</span></span>
<span data-ttu-id="4f42e-131">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-131">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4f42e-132">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4f42e-132">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4f42e-133">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f42e-133">CommonParameters</span></span>
<span data-ttu-id="4f42e-134">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4f42e-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4f42e-135">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f42e-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4f42e-136">入力</span><span class="sxs-lookup"><span data-stu-id="4f42e-136">INPUTS</span></span>

### <span data-ttu-id="4f42e-137">PSEventArgs (システム管理)</span><span class="sxs-lookup"><span data-stu-id="4f42e-137">System.Management.Automation.PSEventArgs</span></span>
<span data-ttu-id="4f42e-138">パイプを使用して Get-Event からイベントを **削除** できます。</span><span class="sxs-lookup"><span data-stu-id="4f42e-138">You can pipe events from Get-Event to **Remove-Event** .</span></span>

## <span data-ttu-id="4f42e-139">出力</span><span class="sxs-lookup"><span data-stu-id="4f42e-139">OUTPUTS</span></span>

### <span data-ttu-id="4f42e-140">なし</span><span class="sxs-lookup"><span data-stu-id="4f42e-140">None</span></span>
<span data-ttu-id="4f42e-141">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="4f42e-141">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4f42e-142">注</span><span class="sxs-lookup"><span data-stu-id="4f42e-142">NOTES</span></span>

* <span data-ttu-id="4f42e-143">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="4f42e-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="4f42e-144">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="4f42e-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

*

## <span data-ttu-id="4f42e-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4f42e-145">RELATED LINKS</span></span>

[<span data-ttu-id="4f42e-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="4f42e-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="4f42e-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="4f42e-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="4f42e-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="4f42e-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="4f42e-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="4f42e-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="4f42e-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="4f42e-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="4f42e-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4f42e-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="4f42e-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="4f42e-152">Wait-Event</span></span>](Wait-Event.md)
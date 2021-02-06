---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 3193de9020f2f54795bde9d5cce1bb86c4431ef9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601192"
---
# <span data-ttu-id="03410-102">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="03410-102">Remove-Event</span></span>

## <span data-ttu-id="03410-103">概要</span><span class="sxs-lookup"><span data-stu-id="03410-103">SYNOPSIS</span></span>
<span data-ttu-id="03410-104">イベントをイベント キューから削除します。</span><span class="sxs-lookup"><span data-stu-id="03410-104">Deletes events from the event queue.</span></span>

## <span data-ttu-id="03410-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="03410-105">SYNTAX</span></span>

### <span data-ttu-id="03410-106">BySource (既定値)</span><span class="sxs-lookup"><span data-stu-id="03410-106">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="03410-107">ByIdentifier</span><span class="sxs-lookup"><span data-stu-id="03410-107">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="03410-108">Description</span><span class="sxs-lookup"><span data-stu-id="03410-108">DESCRIPTION</span></span>

<span data-ttu-id="03410-109">`Remove-Event`コマンドレットは、現在のセッションのイベントキューからイベントを削除します。</span><span class="sxs-lookup"><span data-stu-id="03410-109">The `Remove-Event` cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="03410-110">このコマンドレットは、現在キューにあるイベントのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="03410-110">This cmdlet deletes only the events currently in the queue.</span></span> <span data-ttu-id="03410-111">イベントの登録またはサブスクライブ解除を取り消すには、コマンドレットを使用し `Unregister-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="03410-111">To cancel event registrations or unsubscribe, use the `Unregister-Event` cmdlet.</span></span>

## <span data-ttu-id="03410-112">例</span><span class="sxs-lookup"><span data-stu-id="03410-112">EXAMPLES</span></span>

### <span data-ttu-id="03410-113">例 1: ソース識別子を使用してイベントを削除する</span><span class="sxs-lookup"><span data-stu-id="03410-113">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="03410-114">このコマンドは、イベントキューからプロセスのソース識別子が開始されたイベントを削除します。</span><span class="sxs-lookup"><span data-stu-id="03410-114">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="03410-115">例 2: イベント識別子でイベントを削除する</span><span class="sxs-lookup"><span data-stu-id="03410-115">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="03410-116">このコマンドは、イベント ID が 30 のイベントをイベント キューから削除します。</span><span class="sxs-lookup"><span data-stu-id="03410-116">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="03410-117">例 3: すべてのイベントを削除する</span><span class="sxs-lookup"><span data-stu-id="03410-117">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="03410-118">このコマンドは、イベント キューからすべてのイベントを削除します。</span><span class="sxs-lookup"><span data-stu-id="03410-118">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="03410-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="03410-119">PARAMETERS</span></span>

### <span data-ttu-id="03410-120">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="03410-120">-EventIdentifier</span></span>

<span data-ttu-id="03410-121">コマンドレットが削除するイベント識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="03410-121">Specifies the event identifier for which the cmdlet deletes.</span></span> <span data-ttu-id="03410-122">すべてのコマンドには、 **EventIdentifier** パラメーターまたは **SourceIdentifier** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="03410-122">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="03410-123">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="03410-123">-SourceIdentifier</span></span>

<span data-ttu-id="03410-124">このコマンドレットによってイベントが削除されるソース識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="03410-124">Specifies the source identifier for which this cmdlet deletes events from.</span></span> <span data-ttu-id="03410-125">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="03410-125">Wildcards are not permitted.</span></span> <span data-ttu-id="03410-126">すべてのコマンドには、 **EventIdentifier** パラメーターまたは **SourceIdentifier** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="03410-126">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="03410-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="03410-127">-Confirm</span></span>

<span data-ttu-id="03410-128">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03410-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="03410-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="03410-129">-WhatIf</span></span>

<span data-ttu-id="03410-130">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="03410-130">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="03410-131">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="03410-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="03410-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="03410-132">CommonParameters</span></span>

<span data-ttu-id="03410-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="03410-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="03410-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03410-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="03410-135">入力</span><span class="sxs-lookup"><span data-stu-id="03410-135">INPUTS</span></span>

### <span data-ttu-id="03410-136">PSEventArgs (システム管理)</span><span class="sxs-lookup"><span data-stu-id="03410-136">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="03410-137">パイプを使用して、イベントをからにパイプすることができ `Get-Event` `Remove-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="03410-137">You can pipe events from `Get-Event` to `Remove-Event`.</span></span>

## <span data-ttu-id="03410-138">出力</span><span class="sxs-lookup"><span data-stu-id="03410-138">OUTPUTS</span></span>

### <span data-ttu-id="03410-139">なし</span><span class="sxs-lookup"><span data-stu-id="03410-139">None</span></span>

<span data-ttu-id="03410-140">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="03410-140">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="03410-141">注</span><span class="sxs-lookup"><span data-stu-id="03410-141">NOTES</span></span>

<span data-ttu-id="03410-142">Linux または macOS プラットフォームで使用できるイベントソースがありません。</span><span class="sxs-lookup"><span data-stu-id="03410-142">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="03410-143">イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="03410-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="03410-144">現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="03410-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="03410-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="03410-145">RELATED LINKS</span></span>

[<span data-ttu-id="03410-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="03410-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="03410-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="03410-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="03410-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="03410-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="03410-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="03410-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="03410-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="03410-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="03410-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="03410-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="03410-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="03410-152">Wait-Event</span></span>](Wait-Event.md)

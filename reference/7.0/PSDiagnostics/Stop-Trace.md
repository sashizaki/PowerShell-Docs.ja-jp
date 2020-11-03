---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 2629ae1beb722282065e76600174b511bfe5fbc9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211115"
---
# <span data-ttu-id="4a46f-103">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="4a46f-103">Stop-Trace</span></span>

## <span data-ttu-id="4a46f-104">概要</span><span class="sxs-lookup"><span data-stu-id="4a46f-104">SYNOPSIS</span></span>
<span data-ttu-id="4a46f-105">イベントトレースログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="4a46f-105">Stop an Event Trace logging session.</span></span>

## <span data-ttu-id="4a46f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4a46f-106">SYNTAX</span></span>

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## <span data-ttu-id="4a46f-107">Description</span><span class="sxs-lookup"><span data-stu-id="4a46f-107">DESCRIPTION</span></span>

<span data-ttu-id="4a46f-108">このコマンドレットは、Windows イベントトレースのログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="4a46f-108">This cmdlet stops a Windows Event Trace logging session.</span></span>

<span data-ttu-id="4a46f-109">このコマンドレットは、次のコマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a46f-109">This cmdlet is used by the following cmdlets:</span></span>

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

<span data-ttu-id="4a46f-110">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a46f-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4a46f-111">例</span><span class="sxs-lookup"><span data-stu-id="4a46f-111">EXAMPLES</span></span>

### <span data-ttu-id="4a46f-112">例 1: WSMan トレースログセッションを停止する</span><span class="sxs-lookup"><span data-stu-id="4a46f-112">Example 1: Stop a WSMan Trace logging session</span></span>

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## <span data-ttu-id="4a46f-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4a46f-113">PARAMETERS</span></span>

### <span data-ttu-id="4a46f-114">-/</span><span class="sxs-lookup"><span data-stu-id="4a46f-114">-ETS</span></span>
<span data-ttu-id="4a46f-115">イベントを保存またはスケジュールせずに直接イベントトレースセッションに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a46f-115">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="4a46f-116">-セッション名</span><span class="sxs-lookup"><span data-stu-id="4a46f-116">-SessionName</span></span>
<span data-ttu-id="4a46f-117">停止するイベントトレースセッションの名前。</span><span class="sxs-lookup"><span data-stu-id="4a46f-117">The name of the Event Trace session to be stopped.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4a46f-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a46f-118">CommonParameters</span></span>
<span data-ttu-id="4a46f-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4a46f-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4a46f-120">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a46f-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4a46f-121">入力</span><span class="sxs-lookup"><span data-stu-id="4a46f-121">INPUTS</span></span>

### <span data-ttu-id="4a46f-122">なし</span><span class="sxs-lookup"><span data-stu-id="4a46f-122">None</span></span>

## <span data-ttu-id="4a46f-123">出力</span><span class="sxs-lookup"><span data-stu-id="4a46f-123">OUTPUTS</span></span>

### <span data-ttu-id="4a46f-124">なし</span><span class="sxs-lookup"><span data-stu-id="4a46f-124">None</span></span>

## <span data-ttu-id="4a46f-125">注</span><span class="sxs-lookup"><span data-stu-id="4a46f-125">NOTES</span></span>

## <span data-ttu-id="4a46f-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4a46f-126">RELATED LINKS</span></span>

[<span data-ttu-id="4a46f-127">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="4a46f-127">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="4a46f-128">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="4a46f-128">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="4a46f-129">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="4a46f-129">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="4a46f-130">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4a46f-130">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="4a46f-131">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="4a46f-131">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="4a46f-132">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4a46f-132">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

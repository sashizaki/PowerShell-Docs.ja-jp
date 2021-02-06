---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 5727ae52326830fa16012722d0b801b7d43e50dd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605170"
---
# <span data-ttu-id="04562-102">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="04562-102">Stop-Trace</span></span>

## <span data-ttu-id="04562-103">概要</span><span class="sxs-lookup"><span data-stu-id="04562-103">SYNOPSIS</span></span>
<span data-ttu-id="04562-104">イベントトレースログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="04562-104">Stop an Event Trace logging session.</span></span>

## <span data-ttu-id="04562-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04562-105">SYNTAX</span></span>

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## <span data-ttu-id="04562-106">Description</span><span class="sxs-lookup"><span data-stu-id="04562-106">DESCRIPTION</span></span>

<span data-ttu-id="04562-107">このコマンドレットは、Windows イベントトレースのログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="04562-107">This cmdlet stops a Windows Event Trace logging session.</span></span>

<span data-ttu-id="04562-108">このコマンドレットは、次のコマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="04562-108">This cmdlet is used by the following cmdlets:</span></span>

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

<span data-ttu-id="04562-109">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04562-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="04562-110">例</span><span class="sxs-lookup"><span data-stu-id="04562-110">EXAMPLES</span></span>

### <span data-ttu-id="04562-111">例 1: WSMan トレースログセッションを停止する</span><span class="sxs-lookup"><span data-stu-id="04562-111">Example 1: Stop a WSMan Trace logging session</span></span>

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## <span data-ttu-id="04562-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04562-112">PARAMETERS</span></span>

### <span data-ttu-id="04562-113">-/</span><span class="sxs-lookup"><span data-stu-id="04562-113">-ETS</span></span>
<span data-ttu-id="04562-114">イベントを保存またはスケジュールせずに直接イベントトレースセッションに送信します。</span><span class="sxs-lookup"><span data-stu-id="04562-114">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="04562-115">-セッション名</span><span class="sxs-lookup"><span data-stu-id="04562-115">-SessionName</span></span>
<span data-ttu-id="04562-116">停止するイベントトレースセッションの名前。</span><span class="sxs-lookup"><span data-stu-id="04562-116">The name of the Event Trace session to be stopped.</span></span>

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

### <span data-ttu-id="04562-117">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="04562-117">CommonParameters</span></span>
<span data-ttu-id="04562-118">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="04562-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="04562-119">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04562-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="04562-120">入力</span><span class="sxs-lookup"><span data-stu-id="04562-120">INPUTS</span></span>

### <span data-ttu-id="04562-121">なし</span><span class="sxs-lookup"><span data-stu-id="04562-121">None</span></span>

## <span data-ttu-id="04562-122">出力</span><span class="sxs-lookup"><span data-stu-id="04562-122">OUTPUTS</span></span>

### <span data-ttu-id="04562-123">なし</span><span class="sxs-lookup"><span data-stu-id="04562-123">None</span></span>

## <span data-ttu-id="04562-124">注</span><span class="sxs-lookup"><span data-stu-id="04562-124">NOTES</span></span>

## <span data-ttu-id="04562-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="04562-125">RELATED LINKS</span></span>

[<span data-ttu-id="04562-126">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="04562-126">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="04562-127">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="04562-127">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="04562-128">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="04562-128">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="04562-129">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="04562-129">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="04562-130">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="04562-130">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="04562-131">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="04562-131">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)


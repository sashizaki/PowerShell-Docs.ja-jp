---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 5e91477cd840e895c25207bd5355686e0c24d473
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209362"
---
# <span data-ttu-id="2e46d-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="2e46d-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="2e46d-104">概要</span><span class="sxs-lookup"><span data-stu-id="2e46d-104">SYNOPSIS</span></span>
<span data-ttu-id="2e46d-105">有効にする-WSManTrace によって開始された WSMan ログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="2e46d-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="2e46d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e46d-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="2e46d-107">Description</span><span class="sxs-lookup"><span data-stu-id="2e46d-107">DESCRIPTION</span></span>
<span data-ttu-id="2e46d-108">このコマンドレットは、Enable-WSManTrace によって開始された WSMan ログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="2e46d-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="2e46d-109">このコマンドレットは、コマンドレットを使用し `Stop-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="2e46d-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="2e46d-110">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e46d-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="2e46d-111">例</span><span class="sxs-lookup"><span data-stu-id="2e46d-111">EXAMPLES</span></span>

### <span data-ttu-id="2e46d-112">例 1: WSMan トレースを停止する</span><span class="sxs-lookup"><span data-stu-id="2e46d-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="2e46d-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e46d-113">PARAMETERS</span></span>

### <span data-ttu-id="2e46d-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e46d-114">CommonParameters</span></span>

<span data-ttu-id="2e46d-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2e46d-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e46d-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e46d-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e46d-117">入力</span><span class="sxs-lookup"><span data-stu-id="2e46d-117">INPUTS</span></span>

### <span data-ttu-id="2e46d-118">なし</span><span class="sxs-lookup"><span data-stu-id="2e46d-118">None</span></span>

## <span data-ttu-id="2e46d-119">出力</span><span class="sxs-lookup"><span data-stu-id="2e46d-119">OUTPUTS</span></span>

### <span data-ttu-id="2e46d-120">なし</span><span class="sxs-lookup"><span data-stu-id="2e46d-120">None</span></span>

## <span data-ttu-id="2e46d-121">注</span><span class="sxs-lookup"><span data-stu-id="2e46d-121">NOTES</span></span>

## <span data-ttu-id="2e46d-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2e46d-122">RELATED LINKS</span></span>

[<span data-ttu-id="2e46d-123">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="2e46d-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="2e46d-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="2e46d-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="2e46d-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="2e46d-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

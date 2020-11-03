---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: f7ec371e0d9826dc095fbf71c4785cae2856875b
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209071"
---
# <span data-ttu-id="4da3c-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4da3c-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="4da3c-104">概要</span><span class="sxs-lookup"><span data-stu-id="4da3c-104">SYNOPSIS</span></span>
<span data-ttu-id="4da3c-105">有効にする-WSManTrace によって開始された WSMan ログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="4da3c-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="4da3c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4da3c-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="4da3c-107">Description</span><span class="sxs-lookup"><span data-stu-id="4da3c-107">DESCRIPTION</span></span>
<span data-ttu-id="4da3c-108">このコマンドレットは、Enable-WSManTrace によって開始された WSMan ログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="4da3c-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="4da3c-109">このコマンドレットは、コマンドレットを使用し `Stop-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="4da3c-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="4da3c-110">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4da3c-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4da3c-111">例</span><span class="sxs-lookup"><span data-stu-id="4da3c-111">EXAMPLES</span></span>

### <span data-ttu-id="4da3c-112">例 1: WSMan トレースを停止する</span><span class="sxs-lookup"><span data-stu-id="4da3c-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="4da3c-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4da3c-113">PARAMETERS</span></span>

### <span data-ttu-id="4da3c-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4da3c-114">CommonParameters</span></span>

<span data-ttu-id="4da3c-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4da3c-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4da3c-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4da3c-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4da3c-117">入力</span><span class="sxs-lookup"><span data-stu-id="4da3c-117">INPUTS</span></span>

### <span data-ttu-id="4da3c-118">なし</span><span class="sxs-lookup"><span data-stu-id="4da3c-118">None</span></span>

## <span data-ttu-id="4da3c-119">出力</span><span class="sxs-lookup"><span data-stu-id="4da3c-119">OUTPUTS</span></span>

### <span data-ttu-id="4da3c-120">なし</span><span class="sxs-lookup"><span data-stu-id="4da3c-120">None</span></span>

## <span data-ttu-id="4da3c-121">注</span><span class="sxs-lookup"><span data-stu-id="4da3c-121">NOTES</span></span>

## <span data-ttu-id="4da3c-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4da3c-122">RELATED LINKS</span></span>

[<span data-ttu-id="4da3c-123">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="4da3c-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="4da3c-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="4da3c-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="4da3c-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4da3c-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

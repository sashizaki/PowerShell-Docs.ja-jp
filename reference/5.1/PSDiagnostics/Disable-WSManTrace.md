---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 90cb571f93243e6fbc59970e5602911e17e25ec7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213547"
---
# <span data-ttu-id="66546-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="66546-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="66546-104">概要</span><span class="sxs-lookup"><span data-stu-id="66546-104">SYNOPSIS</span></span>
<span data-ttu-id="66546-105">有効にする-WSManTrace によって開始された WSMan ログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="66546-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="66546-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66546-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="66546-107">Description</span><span class="sxs-lookup"><span data-stu-id="66546-107">DESCRIPTION</span></span>
<span data-ttu-id="66546-108">このコマンドレットは、Enable-WSManTrace によって開始された WSMan ログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="66546-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="66546-109">このコマンドレットは、コマンドレットを使用し `Stop-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="66546-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="66546-110">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66546-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="66546-111">例</span><span class="sxs-lookup"><span data-stu-id="66546-111">EXAMPLES</span></span>

### <span data-ttu-id="66546-112">例 1: WSMan トレースを停止する</span><span class="sxs-lookup"><span data-stu-id="66546-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="66546-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66546-113">PARAMETERS</span></span>

### <span data-ttu-id="66546-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="66546-114">CommonParameters</span></span>

<span data-ttu-id="66546-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="66546-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66546-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66546-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66546-117">入力</span><span class="sxs-lookup"><span data-stu-id="66546-117">INPUTS</span></span>

### <span data-ttu-id="66546-118">なし</span><span class="sxs-lookup"><span data-stu-id="66546-118">None</span></span>

## <span data-ttu-id="66546-119">出力</span><span class="sxs-lookup"><span data-stu-id="66546-119">OUTPUTS</span></span>

### <span data-ttu-id="66546-120">System.Object</span><span class="sxs-lookup"><span data-stu-id="66546-120">System.Object</span></span>

## <span data-ttu-id="66546-121">注</span><span class="sxs-lookup"><span data-stu-id="66546-121">NOTES</span></span>

## <span data-ttu-id="66546-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="66546-122">RELATED LINKS</span></span>

[<span data-ttu-id="66546-123">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="66546-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="66546-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="66546-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="66546-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="66546-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 647a7676eddf2175bf29e02b3482cc9c7c4d8ebe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603025"
---
# <span data-ttu-id="018cb-102">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="018cb-102">Disable-WSManTrace</span></span>

## <span data-ttu-id="018cb-103">概要</span><span class="sxs-lookup"><span data-stu-id="018cb-103">SYNOPSIS</span></span>
<span data-ttu-id="018cb-104">有効にする-WSManTrace によって開始された WSMan ログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="018cb-104">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="018cb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="018cb-105">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="018cb-106">Description</span><span class="sxs-lookup"><span data-stu-id="018cb-106">DESCRIPTION</span></span>
<span data-ttu-id="018cb-107">このコマンドレットは、Enable-WSManTrace によって開始された WSMan ログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="018cb-107">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="018cb-108">このコマンドレットは、コマンドレットを使用し `Stop-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="018cb-108">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="018cb-109">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="018cb-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="018cb-110">例</span><span class="sxs-lookup"><span data-stu-id="018cb-110">EXAMPLES</span></span>

### <span data-ttu-id="018cb-111">例 1: WSMan トレースを停止する</span><span class="sxs-lookup"><span data-stu-id="018cb-111">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="018cb-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="018cb-112">PARAMETERS</span></span>

### <span data-ttu-id="018cb-113">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="018cb-113">CommonParameters</span></span>

<span data-ttu-id="018cb-114">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="018cb-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="018cb-115">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="018cb-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="018cb-116">入力</span><span class="sxs-lookup"><span data-stu-id="018cb-116">INPUTS</span></span>

### <span data-ttu-id="018cb-117">なし</span><span class="sxs-lookup"><span data-stu-id="018cb-117">None</span></span>

## <span data-ttu-id="018cb-118">出力</span><span class="sxs-lookup"><span data-stu-id="018cb-118">OUTPUTS</span></span>

### <span data-ttu-id="018cb-119">なし</span><span class="sxs-lookup"><span data-stu-id="018cb-119">None</span></span>

## <span data-ttu-id="018cb-120">注</span><span class="sxs-lookup"><span data-stu-id="018cb-120">NOTES</span></span>

## <span data-ttu-id="018cb-121">関連リンク</span><span class="sxs-lookup"><span data-stu-id="018cb-121">RELATED LINKS</span></span>

[<span data-ttu-id="018cb-122">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="018cb-122">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="018cb-123">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="018cb-123">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="018cb-124">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="018cb-124">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)


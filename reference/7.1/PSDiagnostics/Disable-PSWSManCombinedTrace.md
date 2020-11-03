---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 854769bea9c1b3c104f87d99909f6201a39cac42
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209175"
---
# <span data-ttu-id="a74d2-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="a74d2-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="a74d2-104">概要</span><span class="sxs-lookup"><span data-stu-id="a74d2-104">SYNOPSIS</span></span>
<span data-ttu-id="a74d2-105">-Pswsman結合 Edtrace を有効にして、ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a74d2-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="a74d2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a74d2-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="a74d2-107">Description</span><span class="sxs-lookup"><span data-stu-id="a74d2-107">DESCRIPTION</span></span>

<span data-ttu-id="a74d2-108">このコマンドレットは、によって開始されたログセッションを停止 `Enable-PSWSManCombinedTrace` します。</span><span class="sxs-lookup"><span data-stu-id="a74d2-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="a74d2-109">このコマンドレットは、コマンドレットを使用し `Stop-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="a74d2-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="a74d2-110">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a74d2-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a74d2-111">例</span><span class="sxs-lookup"><span data-stu-id="a74d2-111">EXAMPLES</span></span>

### <span data-ttu-id="a74d2-112">例 1: 結合されたログセッションを無効にする</span><span class="sxs-lookup"><span data-stu-id="a74d2-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="a74d2-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a74d2-113">PARAMETERS</span></span>

### <span data-ttu-id="a74d2-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a74d2-114">CommonParameters</span></span>

<span data-ttu-id="a74d2-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a74d2-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a74d2-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a74d2-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a74d2-117">入力</span><span class="sxs-lookup"><span data-stu-id="a74d2-117">INPUTS</span></span>

### <span data-ttu-id="a74d2-118">なし</span><span class="sxs-lookup"><span data-stu-id="a74d2-118">None</span></span>

## <span data-ttu-id="a74d2-119">出力</span><span class="sxs-lookup"><span data-stu-id="a74d2-119">OUTPUTS</span></span>

### <span data-ttu-id="a74d2-120">なし</span><span class="sxs-lookup"><span data-stu-id="a74d2-120">None</span></span>

## <span data-ttu-id="a74d2-121">注</span><span class="sxs-lookup"><span data-stu-id="a74d2-121">NOTES</span></span>

## <span data-ttu-id="a74d2-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a74d2-122">RELATED LINKS</span></span>

[<span data-ttu-id="a74d2-123">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="a74d2-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="a74d2-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="a74d2-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="a74d2-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="a74d2-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)


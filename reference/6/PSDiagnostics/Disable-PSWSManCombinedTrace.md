---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: dc817a2f8629744ce4bdcf428530713e76c3d044
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209079"
---
# <span data-ttu-id="39e5b-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="39e5b-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="39e5b-104">概要</span><span class="sxs-lookup"><span data-stu-id="39e5b-104">SYNOPSIS</span></span>
<span data-ttu-id="39e5b-105">-Pswsman結合 Edtrace を有効にして、ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="39e5b-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="39e5b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39e5b-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="39e5b-107">Description</span><span class="sxs-lookup"><span data-stu-id="39e5b-107">DESCRIPTION</span></span>

<span data-ttu-id="39e5b-108">このコマンドレットは、によって開始されたログセッションを停止 `Enable-PSWSManCombinedTrace` します。</span><span class="sxs-lookup"><span data-stu-id="39e5b-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="39e5b-109">このコマンドレットは、コマンドレットを使用し `Stop-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="39e5b-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="39e5b-110">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39e5b-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="39e5b-111">例</span><span class="sxs-lookup"><span data-stu-id="39e5b-111">EXAMPLES</span></span>

### <span data-ttu-id="39e5b-112">例 1: 結合されたログセッションを無効にする</span><span class="sxs-lookup"><span data-stu-id="39e5b-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="39e5b-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39e5b-113">PARAMETERS</span></span>

### <span data-ttu-id="39e5b-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="39e5b-114">CommonParameters</span></span>

<span data-ttu-id="39e5b-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="39e5b-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39e5b-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39e5b-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="39e5b-117">入力</span><span class="sxs-lookup"><span data-stu-id="39e5b-117">INPUTS</span></span>

### <span data-ttu-id="39e5b-118">なし</span><span class="sxs-lookup"><span data-stu-id="39e5b-118">None</span></span>

## <span data-ttu-id="39e5b-119">出力</span><span class="sxs-lookup"><span data-stu-id="39e5b-119">OUTPUTS</span></span>

### <span data-ttu-id="39e5b-120">なし</span><span class="sxs-lookup"><span data-stu-id="39e5b-120">None</span></span>

## <span data-ttu-id="39e5b-121">注</span><span class="sxs-lookup"><span data-stu-id="39e5b-121">NOTES</span></span>

## <span data-ttu-id="39e5b-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="39e5b-122">RELATED LINKS</span></span>

[<span data-ttu-id="39e5b-123">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="39e5b-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="39e5b-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="39e5b-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="39e5b-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="39e5b-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

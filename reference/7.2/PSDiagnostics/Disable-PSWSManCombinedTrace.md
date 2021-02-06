---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 690a8b050fd0e16033a585df210db340f41a83a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600781"
---
# <span data-ttu-id="c9386-102">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="c9386-102">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="c9386-103">概要</span><span class="sxs-lookup"><span data-stu-id="c9386-103">SYNOPSIS</span></span>
<span data-ttu-id="c9386-104">-Pswsman結合 Edtrace を有効にして、ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c9386-104">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="c9386-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c9386-105">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="c9386-106">Description</span><span class="sxs-lookup"><span data-stu-id="c9386-106">DESCRIPTION</span></span>

<span data-ttu-id="c9386-107">このコマンドレットは、によって開始されたログセッションを停止 `Enable-PSWSManCombinedTrace` します。</span><span class="sxs-lookup"><span data-stu-id="c9386-107">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="c9386-108">このコマンドレットは、コマンドレットを使用し `Stop-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="c9386-108">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="c9386-109">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9386-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="c9386-110">例</span><span class="sxs-lookup"><span data-stu-id="c9386-110">EXAMPLES</span></span>

### <span data-ttu-id="c9386-111">例 1: 結合されたログセッションを無効にする</span><span class="sxs-lookup"><span data-stu-id="c9386-111">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="c9386-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c9386-112">PARAMETERS</span></span>

### <span data-ttu-id="c9386-113">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9386-113">CommonParameters</span></span>

<span data-ttu-id="c9386-114">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c9386-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c9386-115">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9386-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c9386-116">入力</span><span class="sxs-lookup"><span data-stu-id="c9386-116">INPUTS</span></span>

### <span data-ttu-id="c9386-117">なし</span><span class="sxs-lookup"><span data-stu-id="c9386-117">None</span></span>

## <span data-ttu-id="c9386-118">出力</span><span class="sxs-lookup"><span data-stu-id="c9386-118">OUTPUTS</span></span>

### <span data-ttu-id="c9386-119">なし</span><span class="sxs-lookup"><span data-stu-id="c9386-119">None</span></span>

## <span data-ttu-id="c9386-120">注</span><span class="sxs-lookup"><span data-stu-id="c9386-120">NOTES</span></span>

## <span data-ttu-id="c9386-121">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c9386-121">RELATED LINKS</span></span>

[<span data-ttu-id="c9386-122">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="c9386-122">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="c9386-123">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="c9386-123">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="c9386-124">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="c9386-124">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)


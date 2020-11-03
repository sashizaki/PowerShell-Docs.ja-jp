---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 70ce4849e78262fc3553502d307e1df4e9ecfcf3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209076"
---
# <span data-ttu-id="ef226-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="ef226-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="ef226-104">概要</span><span class="sxs-lookup"><span data-stu-id="ef226-104">SYNOPSIS</span></span>
<span data-ttu-id="ef226-105">WSMan プロバイダーが有効になっているログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="ef226-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="ef226-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ef226-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="ef226-107">Description</span><span class="sxs-lookup"><span data-stu-id="ef226-107">DESCRIPTION</span></span>
<span data-ttu-id="ef226-108">このコマンドレットは、WSMan プロバイダーが有効になっているログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="ef226-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="ef226-109">次のイベントプロバイダーが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ef226-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="ef226-110">イベント転送</span><span class="sxs-lookup"><span data-stu-id="ef226-110">Event Forwarding</span></span>
- <span data-ttu-id="ef226-111">IpmiDrv</span><span class="sxs-lookup"><span data-stu-id="ef226-111">IpmiDrv</span></span>
- <span data-ttu-id="ef226-112">IPMIPrv</span><span class="sxs-lookup"><span data-stu-id="ef226-112">IPMIPrv</span></span>
- <span data-ttu-id="ef226-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="ef226-113">WinRM</span></span>
- <span data-ttu-id="ef226-114">WinrsCmd</span><span class="sxs-lookup"><span data-stu-id="ef226-114">WinrsCmd</span></span>
- <span data-ttu-id="ef226-115">WinrsExe</span><span class="sxs-lookup"><span data-stu-id="ef226-115">WinrsExe</span></span>
- <span data-ttu-id="ef226-116">WinrsMgr</span><span class="sxs-lookup"><span data-stu-id="ef226-116">WinrsMgr</span></span>
- <span data-ttu-id="ef226-117">WSManProvHost</span><span class="sxs-lookup"><span data-stu-id="ef226-117">WSManProvHost</span></span>

<span data-ttu-id="ef226-118">セッションの名前は ' wsmlog ' です。</span><span class="sxs-lookup"><span data-stu-id="ef226-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="ef226-119">このコマンドレットは、コマンドレットを使用し `Start-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="ef226-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="ef226-120">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef226-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="ef226-121">例</span><span class="sxs-lookup"><span data-stu-id="ef226-121">EXAMPLES</span></span>

### <span data-ttu-id="ef226-122">例 1: WSMan ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="ef226-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="ef226-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ef226-123">PARAMETERS</span></span>

### <span data-ttu-id="ef226-124">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef226-124">CommonParameters</span></span>

<span data-ttu-id="ef226-125">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ef226-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ef226-126">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef226-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ef226-127">入力</span><span class="sxs-lookup"><span data-stu-id="ef226-127">INPUTS</span></span>

### <span data-ttu-id="ef226-128">なし</span><span class="sxs-lookup"><span data-stu-id="ef226-128">None</span></span>

## <span data-ttu-id="ef226-129">出力</span><span class="sxs-lookup"><span data-stu-id="ef226-129">OUTPUTS</span></span>

### <span data-ttu-id="ef226-130">なし</span><span class="sxs-lookup"><span data-stu-id="ef226-130">None</span></span>

## <span data-ttu-id="ef226-131">注</span><span class="sxs-lookup"><span data-stu-id="ef226-131">NOTES</span></span>

## <span data-ttu-id="ef226-132">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ef226-132">RELATED LINKS</span></span>

[<span data-ttu-id="ef226-133">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="ef226-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="ef226-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="ef226-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="ef226-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="ef226-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

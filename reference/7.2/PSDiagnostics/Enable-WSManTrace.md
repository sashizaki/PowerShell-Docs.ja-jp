---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: a9d91eab94666186c13f8d5c928d83055f6dbefa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600801"
---
# <span data-ttu-id="bf929-102">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="bf929-102">Enable-WSManTrace</span></span>

## <span data-ttu-id="bf929-103">概要</span><span class="sxs-lookup"><span data-stu-id="bf929-103">SYNOPSIS</span></span>
<span data-ttu-id="bf929-104">WSMan プロバイダーが有効になっているログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="bf929-104">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="bf929-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bf929-105">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="bf929-106">Description</span><span class="sxs-lookup"><span data-stu-id="bf929-106">DESCRIPTION</span></span>
<span data-ttu-id="bf929-107">このコマンドレットは、WSMan プロバイダーが有効になっているログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="bf929-107">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="bf929-108">次のイベントプロバイダーが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="bf929-108">The following event providers are enabled:</span></span>

- <span data-ttu-id="bf929-109">イベント転送</span><span class="sxs-lookup"><span data-stu-id="bf929-109">Event Forwarding</span></span>
- <span data-ttu-id="bf929-110">IpmiDrv</span><span class="sxs-lookup"><span data-stu-id="bf929-110">IpmiDrv</span></span>
- <span data-ttu-id="bf929-111">IPMIPrv</span><span class="sxs-lookup"><span data-stu-id="bf929-111">IPMIPrv</span></span>
- <span data-ttu-id="bf929-112">WinRM</span><span class="sxs-lookup"><span data-stu-id="bf929-112">WinRM</span></span>
- <span data-ttu-id="bf929-113">WinrsCmd</span><span class="sxs-lookup"><span data-stu-id="bf929-113">WinrsCmd</span></span>
- <span data-ttu-id="bf929-114">WinrsExe</span><span class="sxs-lookup"><span data-stu-id="bf929-114">WinrsExe</span></span>
- <span data-ttu-id="bf929-115">WinrsMgr</span><span class="sxs-lookup"><span data-stu-id="bf929-115">WinrsMgr</span></span>
- <span data-ttu-id="bf929-116">WSManProvHost</span><span class="sxs-lookup"><span data-stu-id="bf929-116">WSManProvHost</span></span>

<span data-ttu-id="bf929-117">セッションの名前は ' wsmlog ' です。</span><span class="sxs-lookup"><span data-stu-id="bf929-117">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="bf929-118">このコマンドレットは、コマンドレットを使用し `Start-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="bf929-118">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="bf929-119">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf929-119">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="bf929-120">例</span><span class="sxs-lookup"><span data-stu-id="bf929-120">EXAMPLES</span></span>

### <span data-ttu-id="bf929-121">例 1: WSMan ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="bf929-121">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="bf929-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bf929-122">PARAMETERS</span></span>

### <span data-ttu-id="bf929-123">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf929-123">CommonParameters</span></span>

<span data-ttu-id="bf929-124">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bf929-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bf929-125">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf929-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bf929-126">入力</span><span class="sxs-lookup"><span data-stu-id="bf929-126">INPUTS</span></span>

### <span data-ttu-id="bf929-127">なし</span><span class="sxs-lookup"><span data-stu-id="bf929-127">None</span></span>

## <span data-ttu-id="bf929-128">出力</span><span class="sxs-lookup"><span data-stu-id="bf929-128">OUTPUTS</span></span>

### <span data-ttu-id="bf929-129">なし</span><span class="sxs-lookup"><span data-stu-id="bf929-129">None</span></span>

## <span data-ttu-id="bf929-130">注</span><span class="sxs-lookup"><span data-stu-id="bf929-130">NOTES</span></span>

## <span data-ttu-id="bf929-131">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bf929-131">RELATED LINKS</span></span>

[<span data-ttu-id="bf929-132">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="bf929-132">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="bf929-133">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="bf929-133">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="bf929-134">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="bf929-134">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)


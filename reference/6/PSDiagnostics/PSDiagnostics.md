---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=855965
Help Version: 6.2.5.0
keywords: powershell,コマンドレット
Locale: en-US
Module Guid: c61d6278-02a3-4618-ae37-a524d40a7f44
Module Name: PSDiagnostics
ms.date: 11/27/2018
schema: 2.0.0
title: PSDiagnostics モジュール
ms.openlocfilehash: 10bd2d740ce4b21b7e0867c870a55a01a94ee499
ms.sourcegitcommit: 3571b9e87e8881adbf7984cda46a63891039a987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "93209437"
---
# <span data-ttu-id="6b415-103">PSDiagnostics モジュール</span><span class="sxs-lookup"><span data-stu-id="6b415-103">PSDiagnostics Module</span></span>

## <span data-ttu-id="6b415-104">説明</span><span class="sxs-lookup"><span data-stu-id="6b415-104">Description</span></span>

<span data-ttu-id="6b415-105">PowerShell 診断モジュールには、Windows 上の PowerShell で ETW トレースを使用できるようにするコマンドレットのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b415-105">The PowerShell Diagnostics Module contains a set of cmdlets that enables the use of ETW tracing in PowerShell on Windows.</span></span>

## <span data-ttu-id="6b415-106">PSDiagnostics コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6b415-106">PSDiagnostics Cmdlets</span></span>

### [<span data-ttu-id="6b415-107">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="6b415-107">Disable-PSTrace</span></span>](Disable-PSTrace.md)
<span data-ttu-id="6b415-108">Microsoft Windows PowerShell イベントプロバイダーのログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6b415-108">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="6b415-109">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="6b415-109">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
<span data-ttu-id="6b415-110">-Pswsman結合 Edtrace を有効にして、ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6b415-110">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

### [<span data-ttu-id="6b415-111">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="6b415-111">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
<span data-ttu-id="6b415-112">有効にする-WSManTrace によって開始された WSMan ログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="6b415-112">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

### [<span data-ttu-id="6b415-113">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="6b415-113">Enable-PSTrace</span></span>](Enable-PSTrace.md)
<span data-ttu-id="6b415-114">Microsoft Windows PowerShell イベントプロバイダーのログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6b415-114">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="6b415-115">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="6b415-115">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
<span data-ttu-id="6b415-116">WSMan プロバイダーと PowerShell プロバイダーが有効になっている状態で、ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6b415-116">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

### [<span data-ttu-id="6b415-117">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="6b415-117">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
<span data-ttu-id="6b415-118">WSMan プロバイダーが有効になっているログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6b415-118">Start a logging session with the WSMan providers enabled.</span></span>

### [<span data-ttu-id="6b415-119">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="6b415-119">Get-LogProperties</span></span>](Get-LogProperties.md)
<span data-ttu-id="6b415-120">Windows イベントログのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b415-120">Retrieves the properties of a Windows event log.</span></span>

### [<span data-ttu-id="6b415-121">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="6b415-121">Set-LogProperties</span></span>](Set-LogProperties.md)
<span data-ttu-id="6b415-122">Windows イベントログのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="6b415-122">Changes the properties of a Windows event log.</span></span>

### [<span data-ttu-id="6b415-123">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="6b415-123">Start-Trace</span></span>](Start-Trace.md)
<span data-ttu-id="6b415-124">イベントトレースログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6b415-124">Start an Event Trace logging session.</span></span>

### [<span data-ttu-id="6b415-125">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="6b415-125">Stop-Trace</span></span>](Stop-Trace.md)
<span data-ttu-id="6b415-126">イベントトレースログセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="6b415-126">Stop an Event Trace logging session.</span></span>

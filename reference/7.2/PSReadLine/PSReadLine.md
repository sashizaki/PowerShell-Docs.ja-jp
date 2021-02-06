---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: da71d4ef896befaadd7ed64f9a013dc19508a54c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599710"
---
# <span data-ttu-id="e2488-102">PSReadLine モジュール</span><span class="sxs-lookup"><span data-stu-id="e2488-102">PSReadLine Module</span></span>

## <span data-ttu-id="e2488-103">説明</span><span class="sxs-lookup"><span data-stu-id="e2488-103">Description</span></span>

<span data-ttu-id="e2488-104">PSReadLine モジュールには、PowerShell でコマンドライン編集環境をカスタマイズできるコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e2488-104">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="e2488-105">これらの記事では、PSReadLine v2.0 について説明しています。</span><span class="sxs-lookup"><span data-stu-id="e2488-105">These articles documents PSReadLine v2.0.</span></span> <span data-ttu-id="e2488-106">このバージョンは、PowerShell v6 と Windows 10 10 月2018更新プログラム (ビルド 1809) に付属しています。</span><span class="sxs-lookup"><span data-stu-id="e2488-106">This version ships in PowerShell v6 and the Windows 10 October 2018 Update (Build 1809).</span></span>

> [!NOTE]
> <span data-ttu-id="e2488-107">PowerShell 7.0 以降では、スクリーンリーダープログラムが検出されると、PowerShell は Windows で PSReadLine の自動読み込みをスキップします。</span><span class="sxs-lookup"><span data-stu-id="e2488-107">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="e2488-108">現在、PSReadLine は、スクリーンリーダーではうまく機能しません。</span><span class="sxs-lookup"><span data-stu-id="e2488-108">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="e2488-109">Windows での PowerShell 7.0 の既定の表示と書式設定は正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="e2488-109">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="e2488-110">必要に応じて、モジュールを手動で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e2488-110">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="e2488-111">PSReadLine コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e2488-111">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="e2488-112">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="e2488-112">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="e2488-113">PSReadLine のメインエントリポイント。</span><span class="sxs-lookup"><span data-stu-id="e2488-113">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="e2488-114">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="e2488-114">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="e2488-115">PSReadLine モジュールのバインドされたキー関数を取得します。</span><span class="sxs-lookup"><span data-stu-id="e2488-115">Gets the bound key functions for the PSReadLine module.</span></span>

### [<span data-ttu-id="e2488-116">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="e2488-116">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="e2488-117">構成可能なオプションの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e2488-117">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="e2488-118">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="e2488-118">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="e2488-119">この関数は、PSReadLine のメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="e2488-119">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="e2488-120">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="e2488-120">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="e2488-121">キーバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="e2488-121">Removes a key binding.</span></span>

### [<span data-ttu-id="e2488-122">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="e2488-122">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="e2488-123">ユーザー定義キーまたは PSReadLine キーハンドラー関数にキーをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e2488-123">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="e2488-124">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="e2488-124">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="e2488-125">**Psreadline** でのコマンドライン編集の動作をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="e2488-125">Customizes the behavior of command line editing in **PSReadLine**.</span></span>


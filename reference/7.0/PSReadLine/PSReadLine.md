---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=2113630
Help Version: 7.0.1.0
keywords: powershell
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: e14d322fb2f964f06c064c1f9878dc3033947520
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "93220400"
---
# <span data-ttu-id="47d84-103">PSReadLine モジュール</span><span class="sxs-lookup"><span data-stu-id="47d84-103">PSReadLine Module</span></span>

## <span data-ttu-id="47d84-104">説明</span><span class="sxs-lookup"><span data-stu-id="47d84-104">Description</span></span>

<span data-ttu-id="47d84-105">PSReadLine モジュールには、PowerShell でコマンドライン編集環境をカスタマイズできるコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="47d84-105">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="47d84-106">これらの記事では、PSReadLine v2.0 について説明しています。</span><span class="sxs-lookup"><span data-stu-id="47d84-106">These articles documents PSReadLine v2.0.</span></span> <span data-ttu-id="47d84-107">このバージョンは、PowerShell v6 と Windows 10 10 月2018更新プログラム (ビルド 1809) に付属しています。</span><span class="sxs-lookup"><span data-stu-id="47d84-107">This version ships in PowerShell v6 and the Windows 10 October 2018 Update (Build 1809).</span></span>

> [!NOTE]
> <span data-ttu-id="47d84-108">PowerShell 7.0 以降では、スクリーンリーダープログラムが検出されると、PowerShell は Windows で PSReadLine の自動読み込みをスキップします。</span><span class="sxs-lookup"><span data-stu-id="47d84-108">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="47d84-109">現在、PSReadLine は、スクリーンリーダーではうまく機能しません。</span><span class="sxs-lookup"><span data-stu-id="47d84-109">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="47d84-110">Windows での PowerShell 7.0 の既定の表示と書式設定は正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="47d84-110">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="47d84-111">必要に応じて、モジュールを手動で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="47d84-111">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="47d84-112">PSReadLine コマンドレット</span><span class="sxs-lookup"><span data-stu-id="47d84-112">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="47d84-113">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="47d84-113">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="47d84-114">PSReadLine のメインエントリポイント。</span><span class="sxs-lookup"><span data-stu-id="47d84-114">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="47d84-115">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="47d84-115">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="47d84-116">PSReadLine モジュールのキーバインドを取得します。</span><span class="sxs-lookup"><span data-stu-id="47d84-116">Gets the key bindings for the PSReadLine module.</span></span>

### [<span data-ttu-id="47d84-117">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="47d84-117">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="47d84-118">構成可能なオプションの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="47d84-118">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="47d84-119">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="47d84-119">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="47d84-120">この関数は、PSReadLine のメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="47d84-120">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="47d84-121">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="47d84-121">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="47d84-122">キーバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="47d84-122">Removes a key binding.</span></span>

### [<span data-ttu-id="47d84-123">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="47d84-123">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="47d84-124">ユーザー定義キーまたは PSReadLine キーハンドラー関数にキーをバインドします。</span><span class="sxs-lookup"><span data-stu-id="47d84-124">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="47d84-125">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="47d84-125">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="47d84-126">**Psreadline** でのコマンドライン編集の動作をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="47d84-126">Customizes the behavior of command line editing in **PSReadLine**.</span></span>


---
external help file: PSReadLine-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSConsoleHostReadLine
ms.openlocfilehash: 47d97fd50294a0dda1064bad123dc17931f8a470
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93225067"
---
# <span data-ttu-id="08618-103">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="08618-103">PSConsoleHostReadLine</span></span>

## <span data-ttu-id="08618-104">概要</span><span class="sxs-lookup"><span data-stu-id="08618-104">SYNOPSIS</span></span>
<span data-ttu-id="08618-105">この関数は、PSReadLine のメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="08618-105">This function is the main entry point for PSReadLine.</span></span>

## <span data-ttu-id="08618-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08618-106">SYNTAX</span></span>

```
PSConsoleHostReadLine
```

## <span data-ttu-id="08618-107">Description</span><span class="sxs-lookup"><span data-stu-id="08618-107">DESCRIPTION</span></span>

<span data-ttu-id="08618-108">`PSConsoleHostReadLine` は、PSReadLine モジュールのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="08618-108">`PSConsoleHostReadLine` is the main entry point for the PSReadLine module.</span></span> <span data-ttu-id="08618-109">PowerShell コンソールホストは、PSReadLine モジュールを自動的に読み込み、この関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="08618-109">The PowerShell console host automatically loads the PSReadLine module and calls this function.</span></span> <span data-ttu-id="08618-110">通常の動作状況では、この関数はコマンドラインから使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="08618-110">Under normal operating conditions, this function is not intended to be used from the command line.</span></span>

<span data-ttu-id="08618-111">拡張ポイント `PSConsoleHostReadLine` は、コンソールホストに特別な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="08618-111">The extension point `PSConsoleHostReadLine` is special to the console host.</span></span> <span data-ttu-id="08618-112">ホストは、この名前を持つ任意のエイリアス、関数、またはスクリプトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="08618-112">The host calls any alias, function, or script with this name.</span></span> <span data-ttu-id="08618-113">PSReadLine は、コンソールホストから呼び出されるように、この関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="08618-113">PSReadLine defines this function so that it is called from the console host.</span></span>

## <span data-ttu-id="08618-114">例</span><span class="sxs-lookup"><span data-stu-id="08618-114">EXAMPLES</span></span>

### <span data-ttu-id="08618-115">例 1</span><span class="sxs-lookup"><span data-stu-id="08618-115">Example 1</span></span>

<span data-ttu-id="08618-116">この関数は、コマンドラインから使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="08618-116">This function is not intended to be used from the command line.</span></span>

## <span data-ttu-id="08618-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08618-117">PARAMETERS</span></span>

## <span data-ttu-id="08618-118">入力</span><span class="sxs-lookup"><span data-stu-id="08618-118">INPUTS</span></span>

### <span data-ttu-id="08618-119">なし</span><span class="sxs-lookup"><span data-stu-id="08618-119">None</span></span>

## <span data-ttu-id="08618-120">出力</span><span class="sxs-lookup"><span data-stu-id="08618-120">OUTPUTS</span></span>

### <span data-ttu-id="08618-121">なし</span><span class="sxs-lookup"><span data-stu-id="08618-121">None</span></span>

## <span data-ttu-id="08618-122">注</span><span class="sxs-lookup"><span data-stu-id="08618-122">NOTES</span></span>

## <span data-ttu-id="08618-123">関連リンク</span><span class="sxs-lookup"><span data-stu-id="08618-123">RELATED LINKS</span></span>

[<span data-ttu-id="08618-124">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="08618-124">about_PSReadLine</span></span>](./About/about_PSReadLine.md)

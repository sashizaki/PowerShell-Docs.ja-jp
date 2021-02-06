---
external help file: PSReadLine-help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSConsoleHostReadLine
ms.openlocfilehash: e02f06137395e187cfe86eb1aeb4b30dbb3f09f1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600795"
---
# <span data-ttu-id="dde8b-102">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="dde8b-102">PSConsoleHostReadLine</span></span>

## <span data-ttu-id="dde8b-103">概要</span><span class="sxs-lookup"><span data-stu-id="dde8b-103">SYNOPSIS</span></span>
<span data-ttu-id="dde8b-104">この関数は、PSReadLine のメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="dde8b-104">This function is the main entry point for PSReadLine.</span></span>

## <span data-ttu-id="dde8b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dde8b-105">SYNTAX</span></span>

```
PSConsoleHostReadLine
```

## <span data-ttu-id="dde8b-106">Description</span><span class="sxs-lookup"><span data-stu-id="dde8b-106">DESCRIPTION</span></span>

<span data-ttu-id="dde8b-107">`PSConsoleHostReadLine` は、PSReadLine モジュールのメインエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="dde8b-107">`PSConsoleHostReadLine` is the main entry point for the PSReadLine module.</span></span> <span data-ttu-id="dde8b-108">PowerShell コンソールホストは、PSReadLine モジュールを自動的に読み込み、この関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dde8b-108">The PowerShell console host automatically loads the PSReadLine module and calls this function.</span></span> <span data-ttu-id="dde8b-109">通常の動作状況では、この関数はコマンドラインから使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="dde8b-109">Under normal operating conditions, this function is not intended to be used from the command line.</span></span>

<span data-ttu-id="dde8b-110">拡張ポイント `PSConsoleHostReadLine` は、コンソールホストに特別な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="dde8b-110">The extension point `PSConsoleHostReadLine` is special to the console host.</span></span> <span data-ttu-id="dde8b-111">ホストは、この名前を持つ任意のエイリアス、関数、またはスクリプトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dde8b-111">The host calls any alias, function, or script with this name.</span></span> <span data-ttu-id="dde8b-112">PSReadLine は、コンソールホストから呼び出されるように、この関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="dde8b-112">PSReadLine defines this function so that it is called from the console host.</span></span>

## <span data-ttu-id="dde8b-113">例</span><span class="sxs-lookup"><span data-stu-id="dde8b-113">EXAMPLES</span></span>

### <span data-ttu-id="dde8b-114">例 1</span><span class="sxs-lookup"><span data-stu-id="dde8b-114">Example 1</span></span>

<span data-ttu-id="dde8b-115">この関数は、コマンドラインから使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="dde8b-115">This function is not intended to be used from the command line.</span></span>

## <span data-ttu-id="dde8b-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dde8b-116">PARAMETERS</span></span>

## <span data-ttu-id="dde8b-117">入力</span><span class="sxs-lookup"><span data-stu-id="dde8b-117">INPUTS</span></span>

### <span data-ttu-id="dde8b-118">なし</span><span class="sxs-lookup"><span data-stu-id="dde8b-118">None</span></span>

## <span data-ttu-id="dde8b-119">出力</span><span class="sxs-lookup"><span data-stu-id="dde8b-119">OUTPUTS</span></span>

### <span data-ttu-id="dde8b-120">なし</span><span class="sxs-lookup"><span data-stu-id="dde8b-120">None</span></span>

## <span data-ttu-id="dde8b-121">注</span><span class="sxs-lookup"><span data-stu-id="dde8b-121">NOTES</span></span>

## <span data-ttu-id="dde8b-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="dde8b-122">RELATED LINKS</span></span>

[<span data-ttu-id="dde8b-123">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="dde8b-123">about_PSReadLine</span></span>](./About/about_PSReadLine.md)


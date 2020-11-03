---
description: PowerShell で収集されたテレメトリと、オプトアウトする方法について説明します。
keywords: powershell
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: 4aeab828d66d1f015946051419facd81ce2b78c1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220531"
---
# <a name="about-telemetry"></a><span data-ttu-id="f2cd5-104">テレメトリについて</span><span class="sxs-lookup"><span data-stu-id="f2cd5-104">About Telemetry</span></span>

## <a name="short-description"></a><span data-ttu-id="f2cd5-105">概要</span><span class="sxs-lookup"><span data-stu-id="f2cd5-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="f2cd5-106">PowerShell で収集されたテレメトリと、オプトアウトする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2cd5-106">Describes the telemetry collected in PowerShell and how to opt-out.</span></span>

## <a name="long-description"></a><span data-ttu-id="f2cd5-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="f2cd5-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f2cd5-108">PowerShell は、基本的なテレメトリデータを Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="f2cd5-108">PowerShell sends basic telemetry data to Microsoft.</span></span>
<span data-ttu-id="f2cd5-109">このデータにより、PowerShell が使用されている環境をより深く理解し、新機能と修正の優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="f2cd5-109">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>
<span data-ttu-id="f2cd5-110">次のテレメトリポイントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="f2cd5-110">The following telemetry points are recorded:</span></span>

- <span data-ttu-id="f2cd5-111">PowerShell の種類で開始 (API vs コンソール)</span><span class="sxs-lookup"><span data-stu-id="f2cd5-111">Count of PowerShell Starts by type (API vs console)</span></span>
- <span data-ttu-id="f2cd5-112">一意の PowerShell 使用状況のカウント</span><span class="sxs-lookup"><span data-stu-id="f2cd5-112">Count of unique PowerShell usage</span></span>
- <span data-ttu-id="f2cd5-113">次の実行の種類の数。</span><span class="sxs-lookup"><span data-stu-id="f2cd5-113">Count of the following execution types:</span></span>
  - <span data-ttu-id="f2cd5-114">アプリケーション (ネイティブコマンド)</span><span class="sxs-lookup"><span data-stu-id="f2cd5-114">Application (native commands)</span></span>
  - <span data-ttu-id="f2cd5-115">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="f2cd5-115">ExternalScript</span></span>
  - <span data-ttu-id="f2cd5-116">スクリプト</span><span class="sxs-lookup"><span data-stu-id="f2cd5-116">Script</span></span>
  - <span data-ttu-id="f2cd5-117">機能</span><span class="sxs-lookup"><span data-stu-id="f2cd5-117">Function</span></span>
  - <span data-ttu-id="f2cd5-118">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f2cd5-118">Cmdlet</span></span>
- <span data-ttu-id="f2cd5-119">PowerShell に付属している、Microsoft が所有する試験的な機能または試験的な機能の数</span><span class="sxs-lookup"><span data-stu-id="f2cd5-119">Count of enabled Microsoft owned experimental features or experimental features shipped with PowerShell</span></span>
- <span data-ttu-id="f2cd5-120">ホストされているセッションの数</span><span class="sxs-lookup"><span data-stu-id="f2cd5-120">Count of hosted sessions</span></span>
- <span data-ttu-id="f2cd5-121">Microsoft 所有のモジュールが読み込まれた回数</span><span class="sxs-lookup"><span data-stu-id="f2cd5-121">Count of Microsoft owned modules loaded</span></span>

<span data-ttu-id="f2cd5-122">このデータには、OS 名、OS バージョン、PowerShell のバージョン、および配布チャネルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2cd5-122">This data includes the OS name, OS version, the PowerShell version, and the distribution channel.</span></span>

<span data-ttu-id="f2cd5-123">このテレメトリをオプトアウトするには、環境変数 POWERSHELL_TELEMETRY_OPTOUT を true、yes、または1に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2cd5-123">To opt-out of this telemetry, set the environment variable POWERSHELL_TELEMETRY_OPTOUT to true, yes, or 1.</span></span>

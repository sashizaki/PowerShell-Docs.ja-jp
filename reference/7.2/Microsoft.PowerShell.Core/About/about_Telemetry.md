---
description: PowerShell で収集されたテレメトリと、オプトアウトする方法について説明します。
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: 677d43b405fdc92e6b68d6e903847b11cb671a2c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602412"
---
# <a name="about-telemetry"></a><span data-ttu-id="ca72d-103">テレメトリについて</span><span class="sxs-lookup"><span data-stu-id="ca72d-103">About Telemetry</span></span>

## <a name="short-description"></a><span data-ttu-id="ca72d-104">概要</span><span class="sxs-lookup"><span data-stu-id="ca72d-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="ca72d-105">PowerShell で収集されたテレメトリと、オプトアウトする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca72d-105">Describes the telemetry collected in PowerShell and how to opt-out.</span></span>

## <a name="long-description"></a><span data-ttu-id="ca72d-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="ca72d-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="ca72d-107">PowerShell は、基本的なテレメトリデータを Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="ca72d-107">PowerShell sends basic telemetry data to Microsoft.</span></span>
<span data-ttu-id="ca72d-108">このデータにより、PowerShell が使用されている環境をより深く理解し、新機能と修正の優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ca72d-108">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>
<span data-ttu-id="ca72d-109">次のテレメトリポイントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="ca72d-109">The following telemetry points are recorded:</span></span>

- <span data-ttu-id="ca72d-110">PowerShell の種類で開始 (API vs コンソール)</span><span class="sxs-lookup"><span data-stu-id="ca72d-110">Count of PowerShell Starts by type (API vs console)</span></span>
- <span data-ttu-id="ca72d-111">一意の PowerShell 使用状況のカウント</span><span class="sxs-lookup"><span data-stu-id="ca72d-111">Count of unique PowerShell usage</span></span>
- <span data-ttu-id="ca72d-112">次の実行の種類の数。</span><span class="sxs-lookup"><span data-stu-id="ca72d-112">Count of the following execution types:</span></span>
  - <span data-ttu-id="ca72d-113">アプリケーション (ネイティブコマンド)</span><span class="sxs-lookup"><span data-stu-id="ca72d-113">Application (native commands)</span></span>
  - <span data-ttu-id="ca72d-114">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="ca72d-114">ExternalScript</span></span>
  - <span data-ttu-id="ca72d-115">スクリプト</span><span class="sxs-lookup"><span data-stu-id="ca72d-115">Script</span></span>
  - <span data-ttu-id="ca72d-116">Function</span><span class="sxs-lookup"><span data-stu-id="ca72d-116">Function</span></span>
  - <span data-ttu-id="ca72d-117">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="ca72d-117">Cmdlet</span></span>
- <span data-ttu-id="ca72d-118">PowerShell に付属している、Microsoft が所有する試験的な機能または試験的な機能の数</span><span class="sxs-lookup"><span data-stu-id="ca72d-118">Count of enabled Microsoft owned experimental features or experimental features shipped with PowerShell</span></span>
- <span data-ttu-id="ca72d-119">ホストされているセッションの数</span><span class="sxs-lookup"><span data-stu-id="ca72d-119">Count of hosted sessions</span></span>
- <span data-ttu-id="ca72d-120">Microsoft 所有のモジュールが読み込まれた回数</span><span class="sxs-lookup"><span data-stu-id="ca72d-120">Count of Microsoft owned modules loaded</span></span>

<span data-ttu-id="ca72d-121">このデータには、OS 名、OS バージョン、PowerShell のバージョン、および配布チャネルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca72d-121">This data includes the OS name, OS version, the PowerShell version, and the distribution channel.</span></span>

<span data-ttu-id="ca72d-122">このテレメトリをオプトアウトするには、環境変数 POWERSHELL_TELEMETRY_OPTOUT を true、yes、または1に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca72d-122">To opt-out of this telemetry, set the environment variable POWERSHELL_TELEMETRY_OPTOUT to true, yes, or 1.</span></span>


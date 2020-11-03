---
description: Powershell の新しいバージョンがリリースされたことをユーザーに通知します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Update_Notifications
ms.openlocfilehash: 258eb9316ba063069d032bc115bdeb4614666f37
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224179"
---
# <a name="about-update-notifications"></a><span data-ttu-id="2caf1-104">更新通知について</span><span class="sxs-lookup"><span data-stu-id="2caf1-104">About Update Notifications</span></span>

## <a name="short-description"></a><span data-ttu-id="2caf1-105">概要</span><span class="sxs-lookup"><span data-stu-id="2caf1-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="2caf1-106">Powershell の新しいバージョンがリリースされたことをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2caf1-106">Notifies users on startup of PowerShell that a new version of PowerShell has been released.</span></span>

## <a name="long-description"></a><span data-ttu-id="2caf1-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="2caf1-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="2caf1-108">Powershell 7.0 以降では、powershell は更新通知を使用して、PowerShell への更新が存在することをユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="2caf1-108">Beginning with PowerShell 7.0, PowerShell uses update notifications to alert users to the existence of updates to PowerShell.</span></span> <span data-ttu-id="2caf1-109">PowerShell は、新しいバージョンが利用可能かどうかを、1 日に 1 回オンライン サービスに問い合わせます。</span><span class="sxs-lookup"><span data-stu-id="2caf1-109">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="2caf1-110">特定の24時間の期間に最初のセッション中に更新チェックが行われますが、パフォーマンス上の理由から、通知は後続のセッションの開始時にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="2caf1-110">While the update check happens during the first session in a given 24-hour period, for performance reasons, the notification will only be shown on the start of subsequent sessions.</span></span> <span data-ttu-id="2caf1-111">また、パフォーマンス上の理由から、セッションが開始されてから少なくとも3秒が経過するまでチェックは開始されません。</span><span class="sxs-lookup"><span data-stu-id="2caf1-111">Also for performance reasons, the check will not start until at least 3 seconds after the session begins.</span></span>

<span data-ttu-id="2caf1-112">既定では、PowerShell は、そのバージョン/分岐に応じて、2 つの異なる通知チャネルのいずれかをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="2caf1-112">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="2caf1-113">サポートされている一般公開 (GA) バージョンの PowerShell では、更新された GA リリースの通知のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="2caf1-113">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="2caf1-114">プレビューおよびリリース候補 (RC) リリースでは、プレビュー、RC、GA リリースに対する更新プログラムが通知されます。</span><span class="sxs-lookup"><span data-stu-id="2caf1-114">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="2caf1-115">更新通知動作は、`POWERSHELL_UPDATECHECK` 環境変数を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="2caf1-115">The update notification behavior can be changed using the `POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="2caf1-116">サポートされている値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2caf1-116">The following values are supported:</span></span>

- <span data-ttu-id="2caf1-117">`Off` 更新通知機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="2caf1-117">`Off` turns off the update notification feature</span></span>
- <span data-ttu-id="2caf1-118">`Default` が次のように定義されていません `POWERSHELL_UPDATECHECK` 。</span><span class="sxs-lookup"><span data-stu-id="2caf1-118">`Default` is the same as not defining `POWERSHELL_UPDATECHECK`:</span></span>
  - <span data-ttu-id="2caf1-119">GA リリースでは、GA リリースに対する更新プログラムが通知されます</span><span class="sxs-lookup"><span data-stu-id="2caf1-119">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="2caf1-120">プレビュー/RC リリースでは、GA およびプレビュー リリースに対する更新プログラムが通知されます</span><span class="sxs-lookup"><span data-stu-id="2caf1-120">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="2caf1-121">`LTS` 長期的なサービス (LTS) GA リリースの更新についてのみ通知します</span><span class="sxs-lookup"><span data-stu-id="2caf1-121">`LTS` only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

<span data-ttu-id="2caf1-122">次のエンドポイントは、各チャネルの最新バージョンを決定するために現在使用されています。</span><span class="sxs-lookup"><span data-stu-id="2caf1-122">The following endpoints are currently used for determining the latest version of each channel:</span></span>

- <span data-ttu-id="2caf1-123">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span><span class="sxs-lookup"><span data-stu-id="2caf1-123">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span></span>
- <span data-ttu-id="2caf1-124">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span><span class="sxs-lookup"><span data-stu-id="2caf1-124">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span></span>
- <span data-ttu-id="2caf1-125">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span><span class="sxs-lookup"><span data-stu-id="2caf1-125">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span></span>

<span data-ttu-id="2caf1-126">更新通知には、PowerShell を自動的に更新する方法は用意されていません。</span><span class="sxs-lookup"><span data-stu-id="2caf1-126">The update notification doesn't provide any way to automatically update PowerShell.</span></span> <span data-ttu-id="2caf1-127">今後、PowerShell 内から更新するための手順や機能が増えている場合がありますが、現在は PowerShell のインストールに使用したのと同じインストールメカニズムを使用して更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2caf1-127">In the future, there may be more instructions or capabilities to update from within PowerShell, but today, you should use the same install mechanism you used to install PowerShell to update it.</span></span>


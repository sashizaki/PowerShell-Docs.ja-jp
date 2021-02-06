---
description: Powershell の新しいバージョンがリリースされたことをユーザーに通知します。
Locale: en-US
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Update_Notifications
ms.openlocfilehash: 1a9f8cfec15f83566fdb77175dcc1aed6d9e8c34
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605435"
---
# <a name="about-update-notifications"></a><span data-ttu-id="3ded5-103">更新通知について</span><span class="sxs-lookup"><span data-stu-id="3ded5-103">About Update Notifications</span></span>

## <a name="short-description"></a><span data-ttu-id="3ded5-104">概要</span><span class="sxs-lookup"><span data-stu-id="3ded5-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="3ded5-105">Powershell の新しいバージョンがリリースされたことをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3ded5-105">Notifies users on startup of PowerShell that a new version of PowerShell has been released.</span></span>

## <a name="long-description"></a><span data-ttu-id="3ded5-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="3ded5-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="3ded5-107">Powershell 7.0 以降では、powershell は更新通知を使用して、PowerShell への更新が存在することをユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="3ded5-107">Beginning with PowerShell 7.0, PowerShell uses update notifications to alert users to the existence of updates to PowerShell.</span></span> <span data-ttu-id="3ded5-108">PowerShell は、新しいバージョンが利用可能かどうかを、1 日に 1 回オンライン サービスに問い合わせます。</span><span class="sxs-lookup"><span data-stu-id="3ded5-108">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="3ded5-109">特定の24時間の期間に最初のセッション中に更新チェックが行われますが、パフォーマンス上の理由から、通知は後続のセッションの開始時にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ded5-109">While the update check happens during the first session in a given 24-hour period, for performance reasons, the notification will only be shown on the start of subsequent sessions.</span></span> <span data-ttu-id="3ded5-110">また、パフォーマンス上の理由から、セッションが開始されてから少なくとも3秒が経過するまでチェックは開始されません。</span><span class="sxs-lookup"><span data-stu-id="3ded5-110">Also for performance reasons, the check will not start until at least 3 seconds after the session begins.</span></span>

<span data-ttu-id="3ded5-111">既定では、PowerShell は、そのバージョン/分岐に応じて、2 つの異なる通知チャネルのいずれかをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="3ded5-111">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="3ded5-112">サポートされている一般公開 (GA) バージョンの PowerShell では、更新された GA リリースの通知のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="3ded5-112">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="3ded5-113">プレビューおよびリリース候補 (RC) リリースでは、プレビュー、RC、GA リリースに対する更新プログラムが通知されます。</span><span class="sxs-lookup"><span data-stu-id="3ded5-113">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="3ded5-114">更新通知動作は、`POWERSHELL_UPDATECHECK` 環境変数を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="3ded5-114">The update notification behavior can be changed using the `POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="3ded5-115">サポートされている値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3ded5-115">The following values are supported:</span></span>

- <span data-ttu-id="3ded5-116">`Off` 更新通知機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="3ded5-116">`Off` turns off the update notification feature</span></span>
- <span data-ttu-id="3ded5-117">`Default` が次のように定義されていません `POWERSHELL_UPDATECHECK` 。</span><span class="sxs-lookup"><span data-stu-id="3ded5-117">`Default` is the same as not defining `POWERSHELL_UPDATECHECK`:</span></span>
  - <span data-ttu-id="3ded5-118">GA リリースでは、GA リリースに対する更新プログラムが通知されます</span><span class="sxs-lookup"><span data-stu-id="3ded5-118">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="3ded5-119">プレビュー/RC リリースでは、GA およびプレビュー リリースに対する更新プログラムが通知されます</span><span class="sxs-lookup"><span data-stu-id="3ded5-119">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="3ded5-120">`LTS` 長期的なサービス (LTS) GA リリースの更新についてのみ通知します</span><span class="sxs-lookup"><span data-stu-id="3ded5-120">`LTS` only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

<span data-ttu-id="3ded5-121">次のエンドポイントは、各チャネルの最新バージョンを決定するために現在使用されています。</span><span class="sxs-lookup"><span data-stu-id="3ded5-121">The following endpoints are currently used for determining the latest version of each channel:</span></span>

- <span data-ttu-id="3ded5-122">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span><span class="sxs-lookup"><span data-stu-id="3ded5-122">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span></span>
- <span data-ttu-id="3ded5-123">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span><span class="sxs-lookup"><span data-stu-id="3ded5-123">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span></span>
- <span data-ttu-id="3ded5-124">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span><span class="sxs-lookup"><span data-stu-id="3ded5-124">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span></span>

<span data-ttu-id="3ded5-125">更新通知には、PowerShell を自動的に更新する方法は用意されていません。</span><span class="sxs-lookup"><span data-stu-id="3ded5-125">The update notification doesn't provide any way to automatically update PowerShell.</span></span> <span data-ttu-id="3ded5-126">今後、PowerShell 内から更新するための手順や機能が増えている場合がありますが、現在は PowerShell のインストールに使用したのと同じインストールメカニズムを使用して更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ded5-126">In the future, there may be more instructions or capabilities to update from within PowerShell, but today, you should use the same install mechanism you used to install PowerShell to update it.</span></span>


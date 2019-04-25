---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 57152e9f62c34600df63a2db8e9683928e825d93
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085798"
---
# <a name="detailed-information-about-lcm-state"></a><span data-ttu-id="2a778-102">LCM 状態に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="2a778-102">Detailed information about LCM state</span></span>

<span data-ttu-id="2a778-103">LCM 状態に関する詳細情報を公開する機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="2a778-103">We have made improvements in exposing details about the LCM state.</span></span> <span data-ttu-id="2a778-104">Get-DscLocalConfigurationManager によって返される LCMState には、次の値が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2a778-104">The LCMState that is returned by Get-DscLocalConfigurationManager can now contain the following values:</span></span>

* <span data-ttu-id="2a778-105">**Idle**</span><span class="sxs-lookup"><span data-stu-id="2a778-105">**Idle**</span></span>
* <span data-ttu-id="2a778-106">**Busy**</span><span class="sxs-lookup"><span data-stu-id="2a778-106">**Busy**</span></span>
* <span data-ttu-id="2a778-107">**PendingReboot**</span><span class="sxs-lookup"><span data-stu-id="2a778-107">**PendingReboot**</span></span>
* <span data-ttu-id="2a778-108">**PendingConfiguration**</span><span class="sxs-lookup"><span data-stu-id="2a778-108">**PendingConfiguration**</span></span>

<span data-ttu-id="2a778-109">また、状態に関するさらに詳細な情報を含む LCMStateDetail プロパティも追加されました。</span><span class="sxs-lookup"><span data-stu-id="2a778-109">We have also added an LCMStateDetail property that contains more information about the state.</span></span>

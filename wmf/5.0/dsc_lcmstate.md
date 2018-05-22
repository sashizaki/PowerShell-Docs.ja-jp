---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: db9b48c188b3bfe2e20c06875606a285922f55a6
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="detailed-information-about-lcm-state"></a><span data-ttu-id="fe378-102">LCM 状態に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="fe378-102">Detailed information about LCM state</span></span>

<span data-ttu-id="fe378-103">LCM 状態に関する詳細情報を公開する機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="fe378-103">We have made improvements in exposing details about the LCM state.</span></span> <span data-ttu-id="fe378-104">Get-DscLocalConfigurationManager によって返される LCMState には、次の値が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fe378-104">The LCMState that is returned by Get-DscLocalConfigurationManager can now contain the following values:</span></span>

* <span data-ttu-id="fe378-105">**Idle**</span><span class="sxs-lookup"><span data-stu-id="fe378-105">**Idle**</span></span>
* <span data-ttu-id="fe378-106">**Busy**</span><span class="sxs-lookup"><span data-stu-id="fe378-106">**Busy**</span></span>
* <span data-ttu-id="fe378-107">**PendingReboot**</span><span class="sxs-lookup"><span data-stu-id="fe378-107">**PendingReboot**</span></span>
* <span data-ttu-id="fe378-108">**PendingConfiguration**</span><span class="sxs-lookup"><span data-stu-id="fe378-108">**PendingConfiguration**</span></span>

<span data-ttu-id="fe378-109">また、状態に関するさらに詳細な情報を含む LCMStateDetail プロパティも追加されました。</span><span class="sxs-lookup"><span data-stu-id="fe378-109">We have also added an LCMStateDetail property that contains more information about the state.</span></span>

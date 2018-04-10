---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: baa35e9acd24d6f6155acf617a0d2c2210742af7
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="detailed-information-about-lcm-state"></a><span data-ttu-id="71947-102">LCM 状態に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="71947-102">Detailed information about LCM state</span></span>

<span data-ttu-id="71947-103">LCM 状態に関する詳細情報を公開する機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="71947-103">We have made improvements in exposing details about the LCM state.</span></span> <span data-ttu-id="71947-104">Get-DscLocalConfigurationManager によって返される LCMState には、次の値が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="71947-104">The LCMState that is returned by Get-DscLocalConfigurationManager can now contain the following values:</span></span>

* <span data-ttu-id="71947-105">**Idle**</span><span class="sxs-lookup"><span data-stu-id="71947-105">**Idle**</span></span>
* <span data-ttu-id="71947-106">**Busy**</span><span class="sxs-lookup"><span data-stu-id="71947-106">**Busy**</span></span>
* <span data-ttu-id="71947-107">**PendingReboot**</span><span class="sxs-lookup"><span data-stu-id="71947-107">**PendingReboot**</span></span>
* <span data-ttu-id="71947-108">**PendingConfiguration**</span><span class="sxs-lookup"><span data-stu-id="71947-108">**PendingConfiguration**</span></span>

<span data-ttu-id="71947-109">また、状態に関するさらに詳細な情報を含む LCMStateDetail プロパティも追加されました。</span><span class="sxs-lookup"><span data-stu-id="71947-109">We have also added an LCMStateDetail property that contains more information about the state.</span></span>
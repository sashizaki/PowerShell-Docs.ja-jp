---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 4fc146f84588d368ac3eb819e3acb4cb8c5d8793
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="detailed-information-about-lcm-state"></a><span data-ttu-id="0a3ce-102">LCM 状態に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="0a3ce-102">Detailed information about LCM state</span></span>

<span data-ttu-id="0a3ce-103">LCM 状態に関する詳細情報を公開する機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="0a3ce-103">We have made improvements in exposing details about the LCM state.</span></span> <span data-ttu-id="0a3ce-104">Get-DscLocalConfigurationManager によって返される LCMState には、次の値が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0a3ce-104">The LCMState that is returned by Get-DscLocalConfigurationManager can now contain the following values:</span></span>

* <span data-ttu-id="0a3ce-105">**Idle**</span><span class="sxs-lookup"><span data-stu-id="0a3ce-105">**Idle**</span></span>
* <span data-ttu-id="0a3ce-106">**Busy**</span><span class="sxs-lookup"><span data-stu-id="0a3ce-106">**Busy**</span></span>
* <span data-ttu-id="0a3ce-107">**PendingReboot**</span><span class="sxs-lookup"><span data-stu-id="0a3ce-107">**PendingReboot**</span></span>
* <span data-ttu-id="0a3ce-108">**PendingConfiguration**</span><span class="sxs-lookup"><span data-stu-id="0a3ce-108">**PendingConfiguration**</span></span>

<span data-ttu-id="0a3ce-109">また、状態に関するさらに詳細な情報を含む LCMStateDetail プロパティも追加されました。</span><span class="sxs-lookup"><span data-stu-id="0a3ce-109">We have also added an LCMStateDetail property that contains more information about the state.</span></span>


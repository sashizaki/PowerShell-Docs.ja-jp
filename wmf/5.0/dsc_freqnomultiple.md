---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: e1faf71436c8ba0ae02a166ce06d03de9f66f094
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="frequencies-for-refreshmode-and-configurationmode-dont-need-to-be-multiples-of-each-other"></a><span data-ttu-id="83cc1-102">RefreshMode と ConfigurationMode の出現頻度は互いの倍数である必要はありません</span><span class="sxs-lookup"><span data-stu-id="83cc1-102">Frequencies for RefreshMode and ConfigurationMode don't need to be multiples of each other</span></span>

<span data-ttu-id="83cc1-103">以前のバージョンの DSC では、LCM は `RefreshFrequencyMins` と `ConfigurationModeFrequencyMins` を互いの倍数として処理します。</span><span class="sxs-lookup"><span data-stu-id="83cc1-103">In the previous version of DSC, the LCM would treat `RefreshFrequencyMins` and `ConfigurationModeFrequencyMins` as multiples of each other.</span></span> <span data-ttu-id="83cc1-104">WMF 5.0 RTM では、これらのプロパティは互いに独立して処理されます。</span><span class="sxs-lookup"><span data-stu-id="83cc1-104">In WMF 5.0 RTM, these properties are processed independent of each other.</span></span>

<span data-ttu-id="83cc1-105">詳細については、「[ローカル構成マネージャーの構成](https://msdn.microsoft.com/powershell/dsc/metaconfig)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83cc1-105">For more information, see [Configuring the Local Configuration Manager](https://msdn.microsoft.com/powershell/dsc/metaconfig).</span></span>
---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 23a5c8832f7c2888880a1ee846d75feaa95ebe47
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058405"
---
# <a name="frequencies-for-refreshmode-and-configurationmode-dont-need-to-be-multiples-of-each-other"></a><span data-ttu-id="f1f83-102">RefreshMode と ConfigurationMode の出現頻度は互いの倍数である必要はありません</span><span class="sxs-lookup"><span data-stu-id="f1f83-102">Frequencies for RefreshMode and ConfigurationMode don't need to be multiples of each other</span></span>

<span data-ttu-id="f1f83-103">以前のバージョンの DSC では、LCM は `RefreshFrequencyMins` と `ConfigurationModeFrequencyMins` を互いの倍数として処理します。</span><span class="sxs-lookup"><span data-stu-id="f1f83-103">In the previous version of DSC, the LCM would treat `RefreshFrequencyMins` and `ConfigurationModeFrequencyMins` as multiples of each other.</span></span> <span data-ttu-id="f1f83-104">WMF 5.0 RTM では、これらのプロパティは互いに独立して処理されます。</span><span class="sxs-lookup"><span data-stu-id="f1f83-104">In WMF 5.0 RTM, these properties are processed independent of each other.</span></span>

<span data-ttu-id="f1f83-105">詳細については、「[ローカル構成マネージャーの構成](https://msdn.microsoft.com/powershell/dsc/metaconfig)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1f83-105">For more information, see [Configuring the Local Configuration Manager](https://msdn.microsoft.com/powershell/dsc/metaconfig).</span></span>

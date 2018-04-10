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
# <a name="frequencies-for-refreshmode-and-configurationmode-dont-need-to-be-multiples-of-each-other"></a>RefreshMode と ConfigurationMode の出現頻度は互いの倍数である必要はありません

以前のバージョンの DSC では、LCM は `RefreshFrequencyMins` と `ConfigurationModeFrequencyMins` を互いの倍数として処理します。 WMF 5.0 RTM では、これらのプロパティは互いに独立して処理されます。

詳細については、「[ローカル構成マネージャーの構成](https://msdn.microsoft.com/powershell/dsc/metaconfig)」を参照してください。
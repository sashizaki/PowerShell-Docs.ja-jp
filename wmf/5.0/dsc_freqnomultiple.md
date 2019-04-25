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
# <a name="frequencies-for-refreshmode-and-configurationmode-dont-need-to-be-multiples-of-each-other"></a>RefreshMode と ConfigurationMode の出現頻度は互いの倍数である必要はありません

以前のバージョンの DSC では、LCM は `RefreshFrequencyMins` と `ConfigurationModeFrequencyMins` を互いの倍数として処理します。 WMF 5.0 RTM では、これらのプロパティは互いに独立して処理されます。

詳細については、「[ローカル構成マネージャーの構成](https://msdn.microsoft.com/powershell/dsc/metaconfig)」を参照してください。

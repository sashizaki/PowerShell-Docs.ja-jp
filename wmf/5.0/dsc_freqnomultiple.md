---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: a3ac215396206fba62bce303733429d60722ee6b
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34218384"
---
# <a name="frequencies-for-refreshmode-and-configurationmode-dont-need-to-be-multiples-of-each-other"></a>RefreshMode と ConfigurationMode の出現頻度は互いの倍数である必要はありません

以前のバージョンの DSC では、LCM は `RefreshFrequencyMins` と `ConfigurationModeFrequencyMins` を互いの倍数として処理します。 WMF 5.0 RTM では、これらのプロパティは互いに独立して処理されます。

詳細については、「[ローカル構成マネージャーの構成](https://msdn.microsoft.com/powershell/dsc/metaconfig)」を参照してください。

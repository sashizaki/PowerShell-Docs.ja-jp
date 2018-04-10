---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 91c115c7f0553cd5edf7fecf04e6a5c71c0a1aa2
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="new-guid"></a>New-Guid
スクリプトを記述しているときには (または、おそらく DSC リソースを記述しているときにも)、多くの場合、一意の識別子が必要になることがあります。 GUID はこの用途に適しており、.NET Framework の Guid クラスを呼び出せば、簡単に生成できます。しかし、これを実行するコマンドレットがあれば、.NET Framework クラスをまだ使い慣れていないエンド ユーザーに使ってもらえます。

PS C:\\&gt; New-Guid

GUID

----

e19d6ea5-3cc2-4db9-8095-0cdaed5a703d
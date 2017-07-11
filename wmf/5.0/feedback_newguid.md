---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: bb2e7b99d14c790bdd3df2f5c729275b96a659fc
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="new-guid" class="xliff"></a>

# New-Guid
スクリプトを記述しているときには (または、おそらく DSC リソースを記述しているときにも)、多くの場合、一意の識別子が必要になることがあります。 GUID はこの用途に適しており、.NET Framework の Guid クラスを呼び出せば、簡単に生成できます。しかし、これを実行するコマンドレットがあれば、.NET Framework クラスをまだ使い慣れていないエンド ユーザーに使ってもらえます。

PS C:\\&gt; New-Guid

GUID

----

e19d6ea5-3cc2-4db9-8095-0cdaed5a703d


---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 410fa4b6c6d3e2708da78414cbb9b80dd3ca1387
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="on-demand-pull-of-dsc-configurations" class="xliff"></a>

# DSC 構成のオンデマンド プル

新しい Update-DscConfiguration コマンドレットは、メタ構成で定義されているプル サーバーからのプルをトリガーします。 この動作のことを、よく '今すぐプル' と呼びます。 


トリガーされたプルは、通常の頻度でトリガーされるプルとまったく同様に動作します。

1. 現在の構成のチェックサムが、プル サーバー上の構成のチェックサムと比較されます。 
2. この 2 つが同一の場合は、構成を適用せずに、正常に終了します。 
3. この 2 つが異なる場合は、構成がプル サーバーからダウンロードされ、適用されます。

**注:** メタ構成で RefreshMode = 'Push' の場合は、コマンドレットからエラーが返されます。そのため、ターゲット ノードが 'Push' モードの場合は常に、このコマンドレットは何も実行しません。

```PowerShell
Update-DscConfiguration     [[-ComputerName] <string[]>] 
                            [-Wait]
                            [-Force] 
                            [-JobName <string>] 
                            [-Credential<pscredential>] 
                            [-ThrottleLimit <int>] 
                            [-WhatIf] 
                            [-Confirm] 
                            [<CommonParameters>]

Update-DscConfiguration     -CimSession <CimSession[]> 
                            [-Wait] 
                            [-Force] 
                            [-JobName <string>] 
                            [-ThrottleLimit <int>]
                            [-WhatIf] 
                            [-Confirm] 
                            [<CommonParameters>]
```


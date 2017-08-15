---
ms.date: 2017-06-12T00:00:00.000Z
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: f2ddde78f436e6f03f521a9a8246dbda93e7a57a
ms.sourcegitcommit: a5c0795ca6ec9332967bff9c151a8572feb1a53a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2017
---
# <a name="on-demand-pull-of-dsc-configurations"></a>DSC 構成のオンデマンド プル

新しい Update-DscConfiguration コマンドレットは、メタ構成で定義されているプル サーバーからのプルをトリガーします。 この動作のことを、よく '今すぐプル' と呼びます。 


トリガーされたプルは、通常の頻度でトリガーされるプルとまったく同様に動作します。

1. 現在の構成のチェックサムが、プル サーバー上の構成のチェックサムと比較されます。 
2. この 2 つが同一の場合は、構成を適用せずに、正常に終了します。 
3. この 2 つが異なる場合は、構成がプル サーバーからダウンロードされ、適用されます。

**注:** メタ構成で RefreshMode = 'Push' の場合は、コマンドレットからエラーが返されます。そのため、ターゲット ノードが 'Push' モードの場合は常に、このコマンドレットは何も実行しません。

```powershell
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


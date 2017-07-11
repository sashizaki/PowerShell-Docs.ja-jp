---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 2d629d98b59c455011f4a5d955ef666218ae2f3f
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="test-dscconfiguration-cmdlet-supports-reference-configurations" class="xliff"></a>

# Test-DscConfiguration コマンドレットでの参照構成のサポート

Test-DscConfiguration コマンドレットが更新されて、参照構成ドキュメントを指定することにより、1 つ以上のターゲット ノードを必要な構成の状態と比較してテストできるようになりました。

次の新しいパラメーター セットでは、指定されたパスにある DSC 構成をテストのみに使い、指定されたターゲット ノード上の各構成に適用することはしません。 Start-DscConfiguration や他の DSC コマンドレットと同様、各 MOF の名前を使って、構成をテストするターゲット ノードが決まります。 

```PowerShell
Test-DscConfiguration   [-Path] <string> 
                        [[-ComputerName] <string[]>] 
                        [-Credential <pscredential>] 
                        [-ThrottleLimit <int>] 
                        [-AsJob] 
                        [<CommonParameters>]

Test-DscConfiguration   [-Path] <string> 
                        -CimSession <CimSession[]> 
                        [-ThrottleLimit <int>] 
                        [-AsJob] 
                        [<CommonParameters>]
```

次の新しいパラメーター セットでは、1 つの DSC 構成をテストのみに使い、指定されたターゲット ノード上の構成に適用することはしません。 

```PowerShell
Test-DscConfiguration   -ReferenceConfiguration <string> 
                        [[-ComputerName] <string[]>]
                        [-Credential <pscredential>] 
                        [-ThrottleLimit <int>] 
                        [-AsJob] 
                        [<CommonParameters>]

Test-DscConfiguration   -ReferenceConfiguration <string> 
                        -CimSession <CimSession[]> 
                        [-ThrottleLimit <int>] 
                        [-AsJob] 
                        [<CommonParameters>]
```


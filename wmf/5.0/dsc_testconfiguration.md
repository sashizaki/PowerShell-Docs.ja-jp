---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 4008a7f91af41150f26c4147135b30aa8835281c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058745"
---
# <a name="test-dscconfiguration-cmdlet-supports-reference-configurations"></a>Test-DscConfiguration コマンドレットでの参照構成のサポート

Test-DscConfiguration コマンドレットが更新されて、参照構成ドキュメントを指定することにより、1 つ以上のターゲット ノードを必要な構成の状態と比較してテストできるようになりました。

次の新しいパラメーター セットでは、指定されたパスにある DSC 構成をテストのみに使い、指定されたターゲット ノード上の各構成に適用することはしません。 Start-DscConfiguration や他の DSC コマンドレットと同様、各 MOF の名前を使って、構成をテストするターゲット ノードが決まります。

```powershell
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

```powershell
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

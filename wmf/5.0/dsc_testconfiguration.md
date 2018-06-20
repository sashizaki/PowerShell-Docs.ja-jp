---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 10f8dd0f5097260eb4a8516f9662df3d219bdfe5
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "34187563"
---
# <a name="test-dscconfiguration-cmdlet-supports-reference-configurations"></a><span data-ttu-id="e43f9-102">Test-DscConfiguration コマンドレットでの参照構成のサポート</span><span class="sxs-lookup"><span data-stu-id="e43f9-102">Test-DscConfiguration cmdlet supports Reference Configurations</span></span>

<span data-ttu-id="e43f9-103">Test-DscConfiguration コマンドレットが更新されて、参照構成ドキュメントを指定することにより、1 つ以上のターゲット ノードを必要な構成の状態と比較してテストできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e43f9-103">The Test-DscConfiguration cmdlet has been updated to allow testing of desired configuration state of one or more target nodes by specifying a reference configuration document to compare against.</span></span>

<span data-ttu-id="e43f9-104">次の新しいパラメーター セットでは、指定されたパスにある DSC 構成をテストのみに使い、指定されたターゲット ノード上の各構成に適用することはしません。</span><span class="sxs-lookup"><span data-stu-id="e43f9-104">The following new parameter sets use DSC configurations in the path specified to only test and never apply each configuration on the specified target node(s).</span></span> <span data-ttu-id="e43f9-105">Start-DscConfiguration や他の DSC コマンドレットと同様、各 MOF の名前を使って、構成をテストするターゲット ノードが決まります。</span><span class="sxs-lookup"><span data-stu-id="e43f9-105">As with Start-DscConfiguration and other DSC cmdlets, the name of each MOF is used to determine which target node to test the configuration on.</span></span>

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

<span data-ttu-id="e43f9-106">次の新しいパラメーター セットでは、1 つの DSC 構成をテストのみに使い、指定されたターゲット ノード上の構成に適用することはしません。</span><span class="sxs-lookup"><span data-stu-id="e43f9-106">The following new parameter sets use a single DSC configuration to only test and never apply the configuration on the specified target node(s).</span></span>

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

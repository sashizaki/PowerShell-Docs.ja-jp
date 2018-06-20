---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 6d37fbc5091d69925d60349f3acbdecc92da1b95
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34220344"
---
# <a name="on-demand-pull-of-dsc-configurations"></a><span data-ttu-id="f4ca9-102">DSC 構成のオンデマンド プル</span><span class="sxs-lookup"><span data-stu-id="f4ca9-102">On-demand PULL of DSC Configurations</span></span>

<span data-ttu-id="f4ca9-103">新しい Update-DscConfiguration コマンドレットは、メタ構成で定義されているプル サーバーからのプルをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="f4ca9-103">The new Update-DscConfiguration cmdlet triggers a pull from the pull server(s) defined in the meta-configuration.</span></span> <span data-ttu-id="f4ca9-104">この動作のことを、よく '今すぐプル' と呼びます。</span><span class="sxs-lookup"><span data-stu-id="f4ca9-104">The behavior is often referred to as 'Pull Now'.</span></span>


<span data-ttu-id="f4ca9-105">トリガーされたプルは、通常の頻度でトリガーされるプルとまったく同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="f4ca9-105">Once triggered, the pull behaves exactly the same as it would have when triggered during the regular frequency:</span></span>

1. <span data-ttu-id="f4ca9-106">現在の構成のチェックサムが、プル サーバー上の構成のチェックサムと比較されます。</span><span class="sxs-lookup"><span data-stu-id="f4ca9-106">The checksum for current configuration is compared to the checksum for the configuration on the pull server.</span></span>
2. <span data-ttu-id="f4ca9-107">この 2 つが同一の場合は、構成を適用せずに、正常に終了します。</span><span class="sxs-lookup"><span data-stu-id="f4ca9-107">If they are the same, it completes successfully without applying the configuration.</span></span>
3. <span data-ttu-id="f4ca9-108">この 2 つが異なる場合は、構成がプル サーバーからダウンロードされ、適用されます。</span><span class="sxs-lookup"><span data-stu-id="f4ca9-108">If they are different, the configuration is pulled down from the pull server and applied.</span></span>

<span data-ttu-id="f4ca9-109">**注:** メタ構成で RefreshMode = 'Push' の場合は、コマンドレットからエラーが返されます。そのため、ターゲット ノードが 'Push' モードの場合は常に、このコマンドレットは何も実行しません。</span><span class="sxs-lookup"><span data-stu-id="f4ca9-109">**Note:** If the Meta-Configuration RefreshMode = 'Push' an error is returned by this cmdlet so this cmdlet will always do nothing when a target node is in 'Push' Mode.</span></span>

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

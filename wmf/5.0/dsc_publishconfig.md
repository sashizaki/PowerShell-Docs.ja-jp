---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: f929ce4684bb53c3039238ecd465f1c0e432f741
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="deliver-a-configuration-document-without-applying"></a><span data-ttu-id="ef8d7-102">適用することなく構成ドキュメントを提供する</span><span class="sxs-lookup"><span data-stu-id="ef8d7-102">Deliver a configuration document without applying</span></span>

<span data-ttu-id="ef8d7-103">[Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) コマンドレットでは、構成の MOF ファイルをターゲット ノードにコピーしますが、その構成は適用されません。</span><span class="sxs-lookup"><span data-stu-id="ef8d7-103">The [Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) cmdlet copies a configuration MOF file to a target node, but does not apply the configuration.</span></span>
<span data-ttu-id="ef8d7-104">この構成が適用されるは、次の一貫性パス中、または [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx) コマンドレットの実行時です。</span><span class="sxs-lookup"><span data-stu-id="ef8d7-104">This configuration is applied during the next consistency pass, or when you run the [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx) cmdlet.</span></span>

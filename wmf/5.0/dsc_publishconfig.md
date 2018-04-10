---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 136e16ae74e54f3bc9d0623178257df1e9104aac
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="deliver-a-configuration-document-without-applying"></a><span data-ttu-id="97e6d-102">適用することなく構成ドキュメントを提供する</span><span class="sxs-lookup"><span data-stu-id="97e6d-102">Deliver a configuration document without applying</span></span>

<span data-ttu-id="97e6d-103">[Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) コマンドレットでは、構成の MOF ファイルをターゲット ノードにコピーしますが、その構成は適用されません。</span><span class="sxs-lookup"><span data-stu-id="97e6d-103">The [Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) cmdlet copies a configuration MOF file to a target node, but does not apply the configuration.</span></span>
<span data-ttu-id="97e6d-104">この構成が適用されるは、次の一貫性パス中、または [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx) コマンドレットの実行時です。</span><span class="sxs-lookup"><span data-stu-id="97e6d-104">This configuration is applied during the next consistency pass, or when you run the [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx) cmdlet.</span></span>
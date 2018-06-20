---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: プル サーバーからノード情報を照会するための DSC 関数
ms.openlocfilehash: 069fc79a79fbd5f75bcce27f7f0bd95af0d7b1ad
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34225625"
---
# <a name="dsc-function-to-query-node-information-from-pull-server"></a><span data-ttu-id="43504-103">プル サーバーからノード情報を照会するための DSC 関数</span><span class="sxs-lookup"><span data-stu-id="43504-103">DSC function to query node information from pull server.</span></span>

```powershell
function QueryNodeInformation
{
Param (
       [string] $Uri =
"http://localhost:7070/PSDSCComplianceServer.svc/Status",
       [string] $ContentType = "application/json"
     )

  Write-Host "Querying node information from pull server URI  = $Uri" -ForegroundColor Green

  Write-Host "Querying node status in content type  = $ContentType " -ForegroundColor Green

   $response = Invoke-WebRequest -Uri $Uri -Method Get -ContentType $ContentType -UseDefaultCredentials -Headers
    @{Accept = $ContentType}

   if($response.StatusCode -ne 200)
 {
     Write-Host "node information was not retrieved." -ForegroundColor Red
 }

 $jsonResponse = ConvertFrom-Json $response.Content

  return $jsonResponse
}
```

<span data-ttu-id="43504-104">`Uri` パラメーターをプル サーバーの URI に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="43504-104">Replace the `Uri` parameter with the URI for your pull server.</span></span> <span data-ttu-id="43504-105">ノードの情報を XML 形式にする場合は、`ContentType` を `application/xml` に設定します。</span><span class="sxs-lookup"><span data-stu-id="43504-105">If you want the node information in XML format, set `ContentType` to `application/xml`.</span></span>

<span data-ttu-id="43504-106">`$json` パラメーターからノード情報を取得するには、以下を使用します。</span><span class="sxs-lookup"><span data-stu-id="43504-106">To retrieve the node information from the `$json` parameter, use the following:</span></span>

```powershell
$json = QueryNodeInformation –Uri http://localhost:7070/PSDSCComplianceServer.svc/Status

$json.value | Format-Table TargetName, ConfigurationId, ServerChecksum, NodeCompliant, LastComplianceTime, StatusCode
```
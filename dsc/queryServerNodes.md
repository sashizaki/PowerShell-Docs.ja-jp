---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: プル サーバーからノード情報を照会するための DSC 関数
ms.openlocfilehash: 5c10eefe9ded4fe6339c4e6252cc189bcd793978
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="dsc-function-to-query-node-information-from-pull-server"></a>プル サーバーからノード情報を照会するための DSC 関数

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

`Uri` パラメーターをプル サーバーの URI に置き換えます。 ノードの情報を XML 形式にする場合は、`ContentType` を `application/xml` に設定します。

`$json` パラメーターからノード情報を取得するには、以下を使用します。

```powershell
$json = QueryNodeInformation –Uri http://localhost:7070/PSDSCComplianceServer.svc/Status

$json.value | Format-Table TargetName, ConfigurationId, ServerChecksum, NodeCompliant, LastComplianceTime, StatusCode
```
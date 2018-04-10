---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: a8947844df0da167961c64e1e09d5075960c95de
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="generate-powershell-cmdlets-based-on-odata-endpoint"></a><span data-ttu-id="a4ef1-102">OData エンドポイントに基づく PowerShell コマンドレットの生成</span><span class="sxs-lookup"><span data-stu-id="a4ef1-102">Generate PowerShell Cmdlets based on OData Endpoint</span></span>
<a name="generate-windows-powershell-cmdlets-based-on-an-odata-endpoint"></a><span data-ttu-id="a4ef1-103">OData エンドポイントに基づく Windows PowerShell コマンドレットの生成</span><span class="sxs-lookup"><span data-stu-id="a4ef1-103">Generate Windows PowerShell cmdlets based on an OData endpoint</span></span>
--------------------------------------------------------------

<span data-ttu-id="a4ef1-104">**Export-ODataEndpointProxy** は、特定の OData エンドポイントによって公開される機能に基づいて、一連の Windows PowerShell コマンドレットを生成するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-104">**Export-ODataEndpointProxy** is a cmdlet that generates a set of Windows PowerShell cmdlets based on the functionality exposed by a given OData endpoint.</span></span>

<span data-ttu-id="a4ef1-105">次の例では、この新しいコマンドレットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-105">The following example shows how to use this new cmdlet:</span></span>

<span data-ttu-id="a4ef1-106">\# Export-ODataEndpointProxy の基本ユース ケース</span><span class="sxs-lookup"><span data-stu-id="a4ef1-106">\# Basic use case of Export-ODataEndpointProxy</span></span>

```powershell
Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -OutputModule C:\Users\user\Generated.psd1

ipmo 'C:\Users\user\Generated.psd1'
# Cmdlets are created based on the following heuristics
# New-<EntityType> -<Key> [-<Other Attributes>]
#
# Get-<EntityType> [-<Key> -Top –Skip –Filter -OrderBy]
# # If there is a complex key, the keys will actually be -<Key1> -<Key2>…
# # Note this rule applies to any other instances of the key
#
# Set-<EntityType> -<Key> [-<Other Attributes>]
#
# Remove-<EntityType> -<Key>
#
# Invoke-<EntityType><Action> [-<Key> -<Other Parameters>]
#
#
# Cmdlets from associations (Note: Get and Remove get additional parameter sets)
# Get-<EntityType> -<AssociatedEntity>
# New-<EntityType> -<AssociatedEntity> -<Key>
# Remove-<EntityType> -<AssociatedEntity> -<Key>
#
#
# Note: Every cmdlet has the –ConnectionURI parameter for explicitly setting the URI of the endpoint. This normally uses the same address that you gave the Export-ODataEndpointProxy cmdlet, but can be overridden in this fashion for the sake of similar endpoints.
#
```

<span data-ttu-id="a4ef1-107">この機能の開発に関して、次に示すものを含め、主なユース ケースがまだあります。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-107">There are still parts of key use cases in development for this functionality, including, but not limited to:</span></span>
-   <span data-ttu-id="a4ef1-108">関連付け</span><span class="sxs-lookup"><span data-stu-id="a4ef1-108">Associations</span></span>
-   <span data-ttu-id="a4ef1-109">ストリームの引き渡し</span><span class="sxs-lookup"><span data-stu-id="a4ef1-109">Passing streams</span></span>

<a name="generate-windows-powershell-cmdlets-based-on-an-odata-endpoint-with-odatautils"></a><span data-ttu-id="a4ef1-110">ODataUtils を使用した OData エンドポイントに基づく Windows PowerShell コマンドレットの生成</span><span class="sxs-lookup"><span data-stu-id="a4ef1-110">Generate Windows PowerShell cmdlets based on an OData endpoint with ODataUtils</span></span>
------------------------------------------------------------------------------
<span data-ttu-id="a4ef1-111">ODataUtils モジュールにより、OData をサポートする REST エンドポイントから Windows PowerShell コマンドレットを生成できます。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-111">The ODataUtils module allows generation of Windows PowerShell cmdlets from REST endpoints that support OData.</span></span> <span data-ttu-id="a4ef1-112">Microsoft.PowerShell.ODataUtils Windows PowerShell モジュールには次の増分拡張があります。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-112">The following incremental enhancements are in the Microsoft.PowerShell.ODataUtils Windows PowerShell module.</span></span>
-   <span data-ttu-id="a4ef1-113">サーバー側エンドポイントからクライアント側への追加情報のチャネル。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-113">Channel additional information from server-side endpoint to client side.</span></span>
-   <span data-ttu-id="a4ef1-114">クライアント側ページング サポート</span><span class="sxs-lookup"><span data-stu-id="a4ef1-114">Client-side paging support</span></span>
-   <span data-ttu-id="a4ef1-115">-Select パラメーターを使用したサーバー側フィルタリング</span><span class="sxs-lookup"><span data-stu-id="a4ef1-115">Server-side filtering by using the -Select parameter</span></span>
-   <span data-ttu-id="a4ef1-116">Web 要求のヘッダーのサポート</span><span class="sxs-lookup"><span data-stu-id="a4ef1-116">Support for web request headers</span></span>

<span data-ttu-id="a4ef1-117">Export-ODataEndPointProxy コマンドレットによって生成されたプロキシ コマンドレットは、情報ストリーム (新しい Windows PowerShell 5.0 の機能) 上のサーバー側 OData エンドポイントから (クライアント側プロキシの生成中に使用される $metadata には含まれない) 追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-117">The proxy cmdlets generated by the Export-ODataEndPointProxy cmdlet provide additional information (not mentioned in the $metadata used during the client-side proxy generation) from the server side OData endpoint on the Information stream (a new Windows PowerShell 5.0 feature).</span></span> <span data-ttu-id="a4ef1-118">次に、その情報を取得する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-118">Here is an example of how to get that information.</span></span>
```powershell
Import-Module Microsoft.PowerShell.ODataUtils -Force
$generatedProxyModuleDir = Join-Path -Path $env:SystemDrive -ChildPath 'ODataDemoProxy'
$uri = "http://services.odata.org/V3/(S(fhleiief23wrm5a5nhf542q5))/OData/OData.svc/"
Export-ODataEndpointProxy -Uri $uri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -AllowClobber
Import-Module $generatedProxyModuleDir -Force

# In the below command, we are retrieving top 1 product.
# By specifying -IncludeTotalResponseCount parameter,
# we are getting the total count of all the Product records
# available on the server side. This information
# is surfaced on the client side through the Information stream.
$product = Get-Product -Top 1 -AllowUnsecureConnection -AllowAdditionalData -IncludeTotalResponseCount -InformationVariable infoStream
# The Information stream contains the additional
# information sent from the server side.
$additionalInfo = $infoStream.GetEnumerator() | % MessageData
# 'Odata.Count' indicates the total product records
# available on the server side Odata endpoint.
$additionalInfo['odata.count']
```

<span data-ttu-id="a4ef1-119">クライアント側ページング サポートを使用して、サーバー側からバッチのレコードを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-119">You can get the records from the server side in batches by using client-side paging support.</span></span> <span data-ttu-id="a4ef1-120">これは、ネットワーク経由でサーバーから大量のデータを取得する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-120">This is useful when you must get a large amount of data from the server over the network.</span></span>
```powershell
$skipCount = 0
$batchSize = 3
# Client-Side Paging Support: The records from the server side
# are retrieved in batches of $batchSize
while($skipCount -le $additionalInfo['odata.count'])
{
Get-Product -AllowUnsecureConnection -AllowAdditionalData -Top $batchSize -Skip $skipCount
$skipCount += $batchSize
}
```

<span data-ttu-id="a4ef1-121">生成されたプロキシ コマンドレットは、クライアントが必要なレコード プロパティのみを受信するためのフィルターとして使用できる -Select パラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-121">The generated proxy cmdlets support the –Select parameter which you can use as a filter to receive only the record properties that the client needs.</span></span> <span data-ttu-id="a4ef1-122">フィルター処理はサーバー側で行われるため、ネットワーク経由で転送されるデータの量が削減されます。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-122">This reduces the amount of data that is transferred over the network, because the filtering occurs on the server side.</span></span>
```powershell
# In the below example only the Name property of the
# Product record is retrieved from the server side.
Get-Product -Top 2 -AllowUnsecureConnection -AllowAdditionalData -Select Name
```

<span data-ttu-id="a4ef1-123">Export-ODataEndpointProxy コマンドレットと、これによって生成されたプロキシ コマンドレットは、ヘッダー パラメーター (ハッシュ テーブルとして値を指定する) をサポートします。ヘッダー パラメーターは、サーバー側 OData エンドポイントで想定される追加情報をチャネルするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-123">The Export-ODataEndpointProxy cmdlet, and the proxy cmdlets generated by it, now support the Headers parameter (supply values as a hash table), which you can use to channel any additional information that is expected by the server-side OData endpoint.</span></span> <span data-ttu-id="a4ef1-124">次の例では、認証用のサブスクリプション キーを想定するサービスのヘッダーによってサブスクリプション キーをチャネルすることができます。</span><span class="sxs-lookup"><span data-stu-id="a4ef1-124">In the following example, you can channel a Subscription key through Headers for services that are expecting a Subscription key for authentication.</span></span>
```powershell
# As an example, in the below command 'XXXX' is the authentication used by the
# Export-ODataEndpointProxy cmdlet to interact with the server-side
# OData endpoint accessed through $endPointUri.

Export-ODataEndpointProxy -Uri $endPointUri -OutputModule $generatedProxyModuleDir -Force -AllowUnSecureConnection -Verbose -Headers @{'subscription-key'='XXXX'}
```
---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: aab7ae73d223f349fc0c103332331710a3eb2efe
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210019"
---
# <span data-ttu-id="fbc8e-103">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="fbc8e-103">Invoke-RestMethod</span></span>

## <span data-ttu-id="fbc8e-104">概要</span><span class="sxs-lookup"><span data-stu-id="fbc8e-104">SYNOPSIS</span></span>
<span data-ttu-id="fbc8e-105">RESTful Web サービスに HTTP または HTTPS 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-105">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="fbc8e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbc8e-106">SYNTAX</span></span>

### <span data-ttu-id="fbc8e-107">StandardMethod (既定値)</span><span class="sxs-lookup"><span data-stu-id="fbc8e-107">StandardMethod (Default)</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="fbc8e-108">StandardMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="fbc8e-108">StandardMethodNoProxy</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="fbc8e-109">CustomMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="fbc8e-109">CustomMethodNoProxy</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="fbc8e-110">CustomMethod</span><span class="sxs-lookup"><span data-stu-id="fbc8e-110">CustomMethod</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="fbc8e-111">説明</span><span class="sxs-lookup"><span data-stu-id="fbc8e-111">Description</span></span>

<span data-ttu-id="fbc8e-112">コマンドレットは、高度 `Invoke-RestMethod` に構造化されたデータを返す HTTP 要求と HTTPS 要求を、表現された状態転送 (REST) web サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-112">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that return richly structured data.</span></span>

<span data-ttu-id="fbc8e-113">PowerShell は、データ型に基づいて応答を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-113">PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="fbc8e-114">RSS フィードまたは ATOM フィードの場合、PowerShell は Item または Entry XML ノードを返します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-114">For an RSS or ATOM feed, PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="fbc8e-115">JavaScript Object Notation (JSON) または XML の場合、PowerShell はコンテンツをオブジェクトに変換または逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-115">For JavaScript Object Notation (JSON) or XML, PowerShell converts, or deserializes, the content into objects.</span></span>

<span data-ttu-id="fbc8e-116">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-116">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="fbc8e-117">PowerShell 7.0 以降では、は `Invoke-RestMethod` 環境変数によって定義されたプロキシ構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-117">Beginning in PowerShell 7.0, `Invoke-RestMethod` supports proxy configuration defined by environment variables.</span></span> <span data-ttu-id="fbc8e-118">この記事の「 [メモ](#notes) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-118">See the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="fbc8e-119">例</span><span class="sxs-lookup"><span data-stu-id="fbc8e-119">EXAMPLES</span></span>

### <span data-ttu-id="fbc8e-120">例 1: PowerShell RSS フィードを取得する</span><span class="sxs-lookup"><span data-stu-id="fbc8e-120">Example 1: Get the PowerShell RSS feed</span></span>

<span data-ttu-id="fbc8e-121">この例では、 `Invoke-RestMethod` コマンドレットを使用して、PowerShell ブログの RSS フィードから情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-121">This example uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="fbc8e-122">このコマンドは、コマンドレットを使用して、 `Format-Table` テーブル内の各ブログの **Title** プロパティと **pubDate** プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-122">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

```powershell
Invoke-RestMethod -Uri https://blogs.msdn.microsoft.com/powershell/feed/ |
  Format-Table -Property Title, pubDate
```

```Output
Title                                                                pubDate
-----                                                                -------
Join the PowerShell 10th Anniversary Celebration!                    Tue, 08 Nov 2016 23:00:04 +0000
DSC Resource Kit November 2016 Release                               Thu, 03 Nov 2016 00:19:07 +0000
PSScriptAnalyzer Community Call - Oct 18, 2016                       Thu, 13 Oct 2016 17:52:35 +0000
New Home for In-Box DSC Resources                                    Sat, 08 Oct 2016 07:13:10 +0000
New Social Features on Gallery                                       Fri, 30 Sep 2016 23:04:34 +0000
PowerShellGet and PackageManagement in PowerShell Gallery and GitHub Thu, 29 Sep 2016 22:21:42 +0000
PowerShell Security at DerbyCon                                      Wed, 28 Sep 2016 01:13:19 +0000
DSC Resource Kit September Release                                   Thu, 22 Sep 2016 00:25:37 +0000
PowerShell DSC and implicit remoting broken in KB3176934             Tue, 23 Aug 2016 15:07:50 +0000
PowerShell on Linux and Open Source!                                 Thu, 18 Aug 2016 15:32:02 +0000
```

### <span data-ttu-id="fbc8e-123">例 2: POST 要求を実行する</span><span class="sxs-lookup"><span data-stu-id="fbc8e-123">Example 2: Run a POST request</span></span>

<span data-ttu-id="fbc8e-124">この例では、ユーザーがを実行して、 `Invoke-RestMethod` ユーザーの組織のイントラネット web サイトで POST 要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-124">In this example, a user runs `Invoke-RestMethod` to do a POST request on an intranet website in the user's organization.</span></span>

```powershell
$Cred = Get-Credential
$Url = "https://server.contoso.com:8089/services/search/jobs/export"
$Body = @{
    search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}
Invoke-RestMethod -Method 'Post' -Uri $url -Credential $Cred -Body $body -OutFile output.csv
```

<span data-ttu-id="fbc8e-125">資格情報の入力が求められ、に格納され `$Cred` ます。また、には、アクセスする URL が定義されてい `$Url` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-125">The credentials are prompted for and then stored in `$Cred` and the URL that will be access is defined in `$Url`.</span></span>

<span data-ttu-id="fbc8e-126">変数は、 `$Body` 検索条件を記述し、CSV を出力モードとして指定します。また、返されるデータの期間を指定します。この時間を経過すると、2日前の日前に終了します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-126">The `$Body` variable describes the search criteria, specifies CSV as the output mode, and specifies a time period for returned data that starts two days ago and ends one day ago.</span></span> <span data-ttu-id="fbc8e-127">Body 変数は、が通信する特定の REST API に適用されるパラメーターの値を指定し `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-127">The body variable specifies values for parameters that apply to the particular REST API with which `Invoke-RestMethod` is communicating.</span></span>

<span data-ttu-id="fbc8e-128">`Invoke-RestMethod`コマンドは、すべての変数を使用して実行され、結果として得られる CSV 出力ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-128">The `Invoke-RestMethod` command is run with all variables in place, specifying a path and file name for the resulting CSV output file.</span></span>

### <span data-ttu-id="fbc8e-129">例 3: リレーションリンクに従う</span><span class="sxs-lookup"><span data-stu-id="fbc8e-129">Example 3: Follow relation links</span></span>

<span data-ttu-id="fbc8e-130">一部の REST Api では、 [RFC5988](https://tools.ietf.org/html/rfc5988#page-6)ごとの関係リンクを使用した改ページがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-130">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="fbc8e-131">ヘッダーを解析して次のページの URL を取得する代わりに、コマンドレットでこの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-131">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="fbc8e-132">この例では、PowerShell GitHub リポジトリから、問題の最初の2ページが返されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-132">This example returns the first two pages of issues from the PowerShell GitHub repository.</span></span>

```powershell
$url = 'https://api.github.com/repos/powershell/powershell/issues'
Invoke-RestMethod $url -FollowRelLink -MaximumFollowRelLink 2
```

### <span data-ttu-id="fbc8e-133">例 4: 単純化されたマルチパート/フォーム-データ送信</span><span class="sxs-lookup"><span data-stu-id="fbc8e-133">Example 4: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="fbc8e-134">一部の Api `multipart/form-data` では、ファイルのアップロードと混合コンテンツの送信が必要です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-134">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="fbc8e-135">この例では、ユーザーのプロファイルを更新する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-135">This example demonstrates how to update a user's profile.</span></span>

```powershell
$Uri = 'https://api.contoso.com/v2/profile'
$Form = @{
    firstName  = 'John'
    lastName   = 'Doe'
    email      = 'john.doe@contoso.com'
    avatar     = Get-Item -Path 'c:\Pictures\jdoe.png'
    birthday   = '1980-10-15'
    hobbies    = 'Hiking','Fishing','Jogging'
}
$Result = Invoke-RestMethod -Uri $Uri -Method Post -Form $Form
```

<span data-ttu-id="fbc8e-136">プロファイルフォームには、、、 `firstName` 、、、 `lastName` `email` `avatar` `birthday` および `hobbies` の各フィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-136">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="fbc8e-137">API では、ユーザープロファイル pic をフィールドに指定するイメージが必要です `avatar` 。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-137">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="fbc8e-138">API は、 `hobbies` 同じ形式で複数のエントリを送信することも許可します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-138">The API will also accept multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="fbc8e-139">`$Form`ハッシュテーブルを作成する場合、キー名はフォームフィールド名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-139">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="fbc8e-140">既定では、ハッシュテーブルの値は文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-140">By default, the values of the HashTable will be converted to strings.</span></span> <span data-ttu-id="fbc8e-141">値が存在する場合は、 `System.IO.FileInfo` ファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-141">If a `System.IO.FileInfo` value is present, the file contents will be submitted.</span></span> <span data-ttu-id="fbc8e-142">配列やリストなどのコレクションが存在する場合、フォームフィールドは複数回送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-142">If a collection such as arrays or lists are present, the form field will be submitted multiple times.</span></span>

<span data-ttu-id="fbc8e-143">キーでを使用する `Get-Item` `avatar` と、 `FileInfo` オブジェクトが値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-143">By using `Get-Item` on the `avatar` key, the `FileInfo` object will be set as the value.</span></span> <span data-ttu-id="fbc8e-144">結果として、のイメージデータが `jdoe.png` 送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-144">The result is that the image data for `jdoe.png` will be submitted.</span></span>

<span data-ttu-id="fbc8e-145">キーにリストを指定すると、 `hobbies` フィールドは、 `hobbies` リスト項目ごとに1回送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-145">By supplying a list to the `hobbies` key, the `hobbies` field will be present in the submissions once for each list item.</span></span>

### <span data-ttu-id="fbc8e-146">例 5: 複数のヘッダーを渡す</span><span class="sxs-lookup"><span data-stu-id="fbc8e-146">Example 5: Pass multiple headers</span></span>

<span data-ttu-id="fbc8e-147">多くの場合、Api は認証または検証のために渡されたヘッダーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-147">APIs often require passed headers for authentication or validation.</span></span> <span data-ttu-id="fbc8e-148">この例では、から複数のヘッダーを REST API に渡す方法について説明し `hash-table` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-148">This example demonstrates, how to pass multiple headers from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

## <span data-ttu-id="fbc8e-149">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbc8e-149">Parameters</span></span>

### <span data-ttu-id="fbc8e-150">-AllowUnencryptedAuthentication</span><span class="sxs-lookup"><span data-stu-id="fbc8e-150">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="fbc8e-151">暗号化されていない接続を介した資格情報とシークレットの送信を許可します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-151">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="fbc8e-152">既定では、で始まらない **Uri** を指定した **資格情報** または任意の **認証** オプションを指定すると、エラーが発生します。この要求は、暗号化されていない接続を `https://` 介してプレーンテキストで誤ってシークレットを通信するのを防ぐために中止されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-152">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` will result in an error and the request will abort to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="fbc8e-153">独自のリスクでこの動作をオーバーライドするには、 **Allowunencryptedauthentication** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-153">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="fbc8e-154">このパラメーターの使用はセキュリティで保護されていないため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-154">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="fbc8e-155">これは、暗号化された接続を提供できないレガシシステムとの互換性のためだけに用意されています。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-155">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="fbc8e-156">ご自身の責任でをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-156">Use at your own risk.</span></span>

<span data-ttu-id="fbc8e-157">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-157">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-158">-認証</span><span class="sxs-lookup"><span data-stu-id="fbc8e-158">-Authentication</span></span>

<span data-ttu-id="fbc8e-159">要求に使用する明示的な認証の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-159">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="fbc8e-160">既定値は **[None]\(なし\)** です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-160">The default is **None** .</span></span>
<span data-ttu-id="fbc8e-161">**UseDefaultCredentials** で **認証** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-161">**Authentication** can't be used with **UseDefaultCredentials** .</span></span>

<span data-ttu-id="fbc8e-162">使用可能な認証オプション:</span><span class="sxs-lookup"><span data-stu-id="fbc8e-162">Available Authentication Options:</span></span>

- <span data-ttu-id="fbc8e-163">**None** : **認証** が指定されていない場合の既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-163">**None** : This is the default option when **Authentication** is not supplied.</span></span> <span data-ttu-id="fbc8e-164">明示的な認証は使用されません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-164">No explicit authentication will be used.</span></span>
- <span data-ttu-id="fbc8e-165">**基本** : **資格情報** が必要です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-165">**Basic** : Requires **Credential** .</span></span> <span data-ttu-id="fbc8e-166">資格情報は、RFC 7617 の基本認証ヘッダーを形式で送信するために使用され `Authorization: Basic` `base64(user:password)` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-166">The credentials will be used to send an RFC 7617 Basic Authentication `Authorization: Basic` header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="fbc8e-167">**ベアラー** : **トークン** が必要です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-167">**Bearer** : Requires **Token** .</span></span> <span data-ttu-id="fbc8e-168">は、指定されたトークンを使用して、および RFC 6750 ヘッダーを送信し `Authorization: Bearer` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-168">Will send and RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="fbc8e-169">これは **OAuth** のエイリアスです</span><span class="sxs-lookup"><span data-stu-id="fbc8e-169">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="fbc8e-170">**OAuth** : **トークン** が必要です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-170">**OAuth** : Requires **Token** .</span></span> <span data-ttu-id="fbc8e-171">は、指定された `Authorization: Bearer` トークンを使用して RFC 6750 ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-171">Will send an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="fbc8e-172">これは **ベアラー** のエイリアスです</span><span class="sxs-lookup"><span data-stu-id="fbc8e-172">This is an alias for **Bearer**</span></span>

<span data-ttu-id="fbc8e-173">**認証** を指定すると、 `Authorization` **ヘッダー** に指定されたヘッダーまたは **web セッション** に含まれるヘッダーが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-173">Supplying **Authentication** will override any `Authorization` headers supplied to **Headers** or included in **WebSession** .</span></span>

<span data-ttu-id="fbc8e-174">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-174">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebAuthenticationType
Parameter Sets: (All)
Aliases:
Accepted values: None, Basic, Bearer, OAuth

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-175">-本文</span><span class="sxs-lookup"><span data-stu-id="fbc8e-175">-Body</span></span>

<span data-ttu-id="fbc8e-176">要求の本文を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-176">Specifies the body of the request.</span></span> <span data-ttu-id="fbc8e-177">本文は、ヘッダーに続く要求の内容です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-177">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="fbc8e-178">パイプを使用して、本文の値をにパイプすることもでき `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-178">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="fbc8e-179">**Body** パラメーターを使用すると、クエリ パラメーターのリストを指定したり、応答の内容を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-179">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="fbc8e-180">入力が GET 要求で、本文が `IDictionary` (通常はハッシュテーブル) の場合、本文はクエリパラメーターとして Uniform Resource Identifier (URI) に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-180">When the input is a GET request, and the body is an `IDictionary` (typically, a hash table), the body is added to the Uniform Resource Identifier (URI) as query parameters.</span></span> <span data-ttu-id="fbc8e-181">その他の要求の種類 (POST など) の場合、本文は標準的な "名前=値" の形式で要求本文の値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-181">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

<span data-ttu-id="fbc8e-182">本文がフォームである場合、または別の呼び出しの出力である場合 `Invoke-WebRequest` 、PowerShell は要求の内容をフォームフィールドに設定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-182">When the body is a form, or it's the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="fbc8e-183">**Body** パラメーターは、 **MultipartFormDataContent** オブジェクトを受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-183">The **Body** parameter may also accept a **System.Net.Http.MultipartFormDataContent** object.</span></span> <span data-ttu-id="fbc8e-184">これにより、要求が容易になり `multipart/form-data` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-184">This will facilitate `multipart/form-data` requests.</span></span> <span data-ttu-id="fbc8e-185">**MultipartFormDataContent** オブジェクトが **本文** に指定されている場合、 **ContentType** 、 **headers** 、または **websession** パラメーターに指定されたコンテンツに関連するヘッダーは、オブジェクトのコンテンツヘッダーによってオーバーライドされ `MultipartFormDataContent` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-185">When a **MultipartFormDataContent** object is supplied for **Body** , any content related headers supplied to the **ContentType** , **Headers** , or **WebSession** parameters will be overridden by the content headers of the `MultipartFormDataContent` object.</span></span> <span data-ttu-id="fbc8e-186">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-186">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-187">-証明書</span><span class="sxs-lookup"><span data-stu-id="fbc8e-187">-Certificate</span></span>

<span data-ttu-id="fbc8e-188">セキュリティで保護された Web 要求に使用するクライアント証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-188">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="fbc8e-189">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-189">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="fbc8e-190">証明書を検索するには、を使用する `Get-PfxCertificate` か、 `Get-ChildItem` 証明書 () ドライブのコマンドレットを使用し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-190">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="fbc8e-191">証明書が有効でないか、十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-191">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-192">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="fbc8e-192">-CertificateThumbprint</span></span>

<span data-ttu-id="fbc8e-193">要求を送信するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-193">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="fbc8e-194">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-194">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="fbc8e-195">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-195">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="fbc8e-196">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-196">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="fbc8e-197">証明書の拇印を取得するに `Get-Item` は、PowerShell ドライブでまたはコマンドを使用し `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-197">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="fbc8e-198">この機能は現在、Windows OS プラットフォームでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-198">This feature is currently only supported on Windows OS platforms.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-199">-ContentType</span><span class="sxs-lookup"><span data-stu-id="fbc8e-199">-ContentType</span></span>

<span data-ttu-id="fbc8e-200">Web 要求のコンテンツ タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-200">Specifies the content type of the web request.</span></span>

<span data-ttu-id="fbc8e-201">このパラメーターを省略して、要求メソッドが POST の場合は、 `Invoke-RestMethod` コンテンツの種類をに設定し `application/x-www-form-urlencoded` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-201">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="fbc8e-202">それ以外の場合は、の呼び出しでコンテンツの種類が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-202">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="fbc8e-203">**ContentType** `MultipartFormDataContent` オブジェクトが **本文** に対して指定されると、ContentType はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-203">**ContentType** will be overridden when a `MultipartFormDataContent` object is supplied for **Body** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-204">-Credential</span><span class="sxs-lookup"><span data-stu-id="fbc8e-204">-Credential</span></span>

<span data-ttu-id="fbc8e-205">要求を送信するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-205">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="fbc8e-206">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-206">The default is the current user.</span></span>

<span data-ttu-id="fbc8e-207">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-207">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="fbc8e-208">**資格情報** は、単独で使用することも、特定の **認証** パラメーターオプションと組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-208">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="fbc8e-209">リモートサーバーが認証チャレンジ要求を送信した場合にのみ、リモートサーバーに資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-209">When used alone, it will only supply credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="fbc8e-210">**認証** オプションと共に使用すると、資格情報が明示的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-210">When used with **Authentication** options, the credentials will be explicitly sent.</span></span>

<span data-ttu-id="fbc8e-211">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-211">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="fbc8e-212">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-212">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-213">-CustomMethod</span><span class="sxs-lookup"><span data-stu-id="fbc8e-213">-CustomMethod</span></span>

<span data-ttu-id="fbc8e-214">Web 要求に使用するカスタムメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-214">Specifies custom method used for the web request.</span></span> <span data-ttu-id="fbc8e-215">これは、エンドポイントで必要とされる要求メソッドで使用できますが、 **メソッド** では使用できません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-215">This can be used with the Request Method required by the endpoint is not an available option on the **Method** .</span></span> <span data-ttu-id="fbc8e-216">**メソッド** と **custommethod** を一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-216">**Method** and **CustomMethod** cannot be used together.</span></span>

<span data-ttu-id="fbc8e-217">例:</span><span class="sxs-lookup"><span data-stu-id="fbc8e-217">Example:</span></span>

`Invoke-RestMethod -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="fbc8e-218">これにより `TEST` 、API に HTTP 要求が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-218">This makes a `TEST` HTTP request to the API.</span></span>

<span data-ttu-id="fbc8e-219">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-219">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CustomMethodNoProxy, CustomMethod
Aliases: CM

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-220">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="fbc8e-220">-DisableKeepAlive</span></span>

<span data-ttu-id="fbc8e-221">コマンドレットが HTTP ヘッダーの **KeepAlive** 値を False に設定することを示します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-221">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="fbc8e-222">既定では、 **KeepAlive** は True です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-222">By default, **KeepAlive** is True.</span></span> <span data-ttu-id="fbc8e-223">**KeepAlive** は、後続の要求を容易にするために、サーバーへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-223">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-224">-リンク</span><span class="sxs-lookup"><span data-stu-id="fbc8e-224">-FollowRelLink</span></span>

<span data-ttu-id="fbc8e-225">コマンドレットが関係リンクに従う必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-225">Indicates the cmdlet should follow relation links.</span></span>

<span data-ttu-id="fbc8e-226">一部の REST Api では、 [RFC5988](https://tools.ietf.org/html/rfc5988#page-6)ごとの関係リンクを使用した改ページがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-226">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="fbc8e-227">ヘッダーを解析して次のページの URL を取得する代わりに、コマンドレットでこの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-227">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="fbc8e-228">リレーションリンクに従う回数を設定するには、 **Maximumの Rellink** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-228">To set how many times to follow relation links, use the **MaximumFollowRelLink** parameter.</span></span>

<span data-ttu-id="fbc8e-229">このスイッチを使用すると、コマンドレットは結果のページのコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-229">When using this switch, the cmdlet returns a collection of pages of results.</span></span> <span data-ttu-id="fbc8e-230">結果の各ページには、複数の結果項目が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-230">Each page of results may contain multiple result items.</span></span>

<span data-ttu-id="fbc8e-231">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-231">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: FL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-232">-フォーム</span><span class="sxs-lookup"><span data-stu-id="fbc8e-232">-Form</span></span>

<span data-ttu-id="fbc8e-233">辞書を送信に変換 `multipart/form-data` します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-233">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="fbc8e-234">**フォーム** を **本文** と共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-234">**Form** may not be used with **Body** .</span></span>
<span data-ttu-id="fbc8e-235">**ContentType** が無視される場合は。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-235">If **ContentType** will be ignored.</span></span>

<span data-ttu-id="fbc8e-236">ディクショナリのキーは、フォームフィールド名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-236">The keys of the dictionary will be used as the form field names.</span></span> <span data-ttu-id="fbc8e-237">既定では、フォーム値は文字列値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-237">By default, form values will be converted to string values.</span></span>

<span data-ttu-id="fbc8e-238">値が **system.servicemodel オブジェクトの** 場合は、バイナリファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-238">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span>
<span data-ttu-id="fbc8e-239">ファイルの名前は、として送信され `filename` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-239">The name of the file will be submitted as the `filename`.</span></span> <span data-ttu-id="fbc8e-240">MIME はとして設定され `application/octet-stream` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-240">The MIME will be set as `application/octet-stream`.</span></span> <span data-ttu-id="fbc8e-241">`Get-Item` を使用 **すると、system.object オブジェクト** を簡単に指定できます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-241">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="fbc8e-242">値が配列やリストなどのコレクション型である場合、for フィールドは複数回送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-242">If the value is a collection type, such as an Array or List, the for field will be submitted multiple times.</span></span> <span data-ttu-id="fbc8e-243">既定では、リストの値は文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-243">The values of the list will be treated as strings by default.</span></span> <span data-ttu-id="fbc8e-244">値が **system.servicemodel オブジェクトの** 場合は、バイナリファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-244">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span> <span data-ttu-id="fbc8e-245">入れ子になったコレクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-245">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="fbc8e-246">上の例では、 `tags` フィールドは、、、およびの各につき1回、フォームで3回指定され `Vacation` `Italy` `2017` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-246">In the above example, the `tags` field will be supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="fbc8e-247">この `pictures` フィールドは、フォルダー内のファイルごとに1回送信され `2017-Italy` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-247">The `pictures` field will also be submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="fbc8e-248">そのフォルダー内のファイルのバイナリコンテンツは、値として送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-248">The binary contents of the files in that folder will be submitted as the values.</span></span>

<span data-ttu-id="fbc8e-249">この機能は、PowerShell 6.1.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-249">This feature was added in PowerShell 6.1.0.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-250">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="fbc8e-250">-Headers</span></span>

<span data-ttu-id="fbc8e-251">Web 要求のヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-251">Specifies the headers of the web request.</span></span> <span data-ttu-id="fbc8e-252">ハッシュ テーブルまたは辞書を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-252">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="fbc8e-253">UserAgent ヘッダーを設定するには、 **UserAgent** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-253">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="fbc8e-254">このパラメーターを使用して `User-Agent` 、またはクッキーヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-254">You cannot use this parameter to specify `User-Agent` or cookie headers.</span></span>

<span data-ttu-id="fbc8e-255">などのコンテンツ関連ヘッダーは、 `Content-Type` `MultipartFormDataContent` オブジェクトが **本文** に指定されたときにオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-255">Content related headers, such as `Content-Type` will be overridden when a `MultipartFormDataContent` object is supplied for **Body** .</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-256">-InFile</span><span class="sxs-lookup"><span data-stu-id="fbc8e-256">-InFile</span></span>

<span data-ttu-id="fbc8e-257">ファイルから Web 要求の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-257">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="fbc8e-258">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-258">Enter a path and file name.</span></span> <span data-ttu-id="fbc8e-259">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-259">If you omit the path, the default is the current location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-260">-MaximumFollowRelLink</span><span class="sxs-lookup"><span data-stu-id="fbc8e-260">-MaximumFollowRelLink</span></span>

<span data-ttu-id="fbc8e-261">**リンク** が使用されている場合に、関係リンクに従う回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-261">Specifies how many times to follow relation links if **FollowRelLink** is used.</span></span> <span data-ttu-id="fbc8e-262">要求が多すぎることが原因で REST api が調整された場合は、小さい値が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-262">A smaller value may be needed if the REST api throttles due to too many requests.</span></span> <span data-ttu-id="fbc8e-263">既定値は `[Int32]::MaxValue` です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-263">The default value is `[Int32]::MaxValue`.</span></span> <span data-ttu-id="fbc8e-264">値を 0 (ゼロ) にすると、次の関係リンクが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-264">A value of 0 (zero) prevents following relation links.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ML

Required: False
Position: Named
Default value: Int32.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-265">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="fbc8e-265">-MaximumRedirection</span></span>

<span data-ttu-id="fbc8e-266">接続に失敗する前に PowerShell が代替 Uniform Resource Identifier (URI) に接続をリダイレクトする回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-266">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="fbc8e-267">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-267">The default value is 5.</span></span> <span data-ttu-id="fbc8e-268">値 0 (ゼロ) を指定した場合、リダイレクトはまったく行われません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-268">A value of 0 (zero) prevents all redirection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-269">-MaximumRetryCount</span><span class="sxs-lookup"><span data-stu-id="fbc8e-269">-MaximumRetryCount</span></span>

<span data-ttu-id="fbc8e-270">400と599の間のエラーコード (包括的または 304) を受信したときに PowerShell が接続を再試行する回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-270">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="fbc8e-271">再試行回数を指定する場合は、 **Retryintervalsec** パラメーターも参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-271">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-272">-メソッド</span><span class="sxs-lookup"><span data-stu-id="fbc8e-272">-Method</span></span>

<span data-ttu-id="fbc8e-273">Web 要求に使用するメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-273">Specifies the method used for the web request.</span></span> <span data-ttu-id="fbc8e-274">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-274">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fbc8e-275">Default</span><span class="sxs-lookup"><span data-stu-id="fbc8e-275">Default</span></span>
- <span data-ttu-id="fbc8e-276">削除</span><span class="sxs-lookup"><span data-stu-id="fbc8e-276">Delete</span></span>
- <span data-ttu-id="fbc8e-277">取得</span><span class="sxs-lookup"><span data-stu-id="fbc8e-277">Get</span></span>
- <span data-ttu-id="fbc8e-278">Head</span><span class="sxs-lookup"><span data-stu-id="fbc8e-278">Head</span></span>
- <span data-ttu-id="fbc8e-279">Merge</span><span class="sxs-lookup"><span data-stu-id="fbc8e-279">Merge</span></span>
- <span data-ttu-id="fbc8e-280">オプション</span><span class="sxs-lookup"><span data-stu-id="fbc8e-280">Options</span></span>
- <span data-ttu-id="fbc8e-281">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="fbc8e-281">Patch</span></span>
- <span data-ttu-id="fbc8e-282">投稿</span><span class="sxs-lookup"><span data-stu-id="fbc8e-282">Post</span></span>
- <span data-ttu-id="fbc8e-283">Put</span><span class="sxs-lookup"><span data-stu-id="fbc8e-283">Put</span></span>
- <span data-ttu-id="fbc8e-284">Trace</span><span class="sxs-lookup"><span data-stu-id="fbc8e-284">Trace</span></span>

<span data-ttu-id="fbc8e-285">**Custommethod** パラメーターは、上に一覧表示されていない要求メソッドに使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-285">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: StandardMethod, StandardMethodNoProxy
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-286">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="fbc8e-286">-NoProxy</span></span>

<span data-ttu-id="fbc8e-287">コマンドレットが宛先に接続するためにプロキシを使用しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-287">Indicates that the cmdlet will not use a proxy to reach the destination.</span></span>

<span data-ttu-id="fbc8e-288">Internet Explorer で構成されているプロキシ、または環境に指定されているプロキシをバイパスする必要がある場合は、このスイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-288">When you need to bypass the proxy configured in Internet Explorer, or a proxy specified in the environment, use this switch.</span></span>

<span data-ttu-id="fbc8e-289">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-289">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethodNoProxy, CustomMethodNoProxy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-290">-出力</span><span class="sxs-lookup"><span data-stu-id="fbc8e-290">-OutFile</span></span>

<span data-ttu-id="fbc8e-291">指定した出力ファイルに応答本文を保存します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-291">Saves the response body in the specified output file.</span></span> <span data-ttu-id="fbc8e-292">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-292">Enter a path and file name.</span></span> <span data-ttu-id="fbc8e-293">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-293">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="fbc8e-294">既定では、は `Invoke-RestMethod` パイプラインに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-294">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="fbc8e-295">結果をファイルとパイプラインに送信するには、 **Passthru** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-295">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-296">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fbc8e-296">-PassThru</span></span>

<span data-ttu-id="fbc8e-297">結果を返す一方でファイルにも書き込みます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-297">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="fbc8e-298">このパラメーターは、同時に **OutFile** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-298">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No output
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-299">-PreserveAuthorizationOnRedirect</span><span class="sxs-lookup"><span data-stu-id="fbc8e-299">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="fbc8e-300">コマンドレットで、リダイレクト全体でヘッダーを保持する必要があることを示し `Authorization` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-300">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="fbc8e-301">既定では、コマンドレットは、 `Authorization` リダイレクトの前にヘッダーを除去します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-301">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="fbc8e-302">このパラメーターを指定すると、ヘッダーがリダイレクト場所に送信される必要がある場合に、このロジックが無効になります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-302">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="fbc8e-303">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-303">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-304">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="fbc8e-304">-Proxy</span></span>

<span data-ttu-id="fbc8e-305">は、インターネットリソースに直接接続するのではなく、要求にプロキシサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-305">Uses a proxy server for the request, rather than connecting directly to the internet resource.</span></span> <span data-ttu-id="fbc8e-306">ネットワークプロキシサーバーの Uniform Resource Identifier (URI) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-306">Enter the Uniform Resource Identifier (URI) of a network proxy server.</span></span>

<span data-ttu-id="fbc8e-307">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-307">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-308">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="fbc8e-308">-ProxyCredential</span></span>

<span data-ttu-id="fbc8e-309">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-309">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="fbc8e-310">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-310">The default is the current user.</span></span>

<span data-ttu-id="fbc8e-311">**User01** や **domain01\user01」** などのユーザー名を入力する **User@Domain.Com** か、 `PSCredential` コマンドレットによって生成されたオブジェクトなどのオブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-311">Type a user name, such as **User01** or **Domain01\User01** , **User@Domain.Com** , or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="fbc8e-312">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-312">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="fbc8e-313">**Proxycredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-313">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-314">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="fbc8e-314">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="fbc8e-315">コマンドレットが、 **プロキシ** パラメーターで指定されたプロキシサーバーにアクセスするために、現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-315">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="fbc8e-316">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-316">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="fbc8e-317">**Proxycredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-317">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-318">-ResponseHeadersVariable</span><span class="sxs-lookup"><span data-stu-id="fbc8e-318">-ResponseHeadersVariable</span></span>

<span data-ttu-id="fbc8e-319">応答ヘッダーディクショナリを作成し、指定した変数の値に保存します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-319">Creates a Response Headers Dictionary and saves it in the value of the specified variable.</span></span> <span data-ttu-id="fbc8e-320">ディクショナリのキーには、web サーバーから返された応答ヘッダーのフィールド名が含まれ、値はそれぞれのフィールド値になります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-320">The keys of the dictionary will contain the field names of the Response Header returned by the web server and the values will be the respective field values.</span></span>

<span data-ttu-id="fbc8e-321">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-321">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RHV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-322">-再開</span><span class="sxs-lookup"><span data-stu-id="fbc8e-322">-Resume</span></span>

<span data-ttu-id="fbc8e-323">部分ファイルのダウンロードを再開するのに最適な試行を実行します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-323">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="fbc8e-324">**Resume** パラメーター **には、出力パラメーターが** 必要です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-324">The **Resume** parameter requires the **OutFile** parameter.</span></span>

<span data-ttu-id="fbc8e-325">**Resume** はローカルファイルとリモートファイルのサイズでのみ動作し、ローカルファイルとリモートファイルが同じであることを検証しません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-325">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="fbc8e-326">ローカルファイルのサイズがリモートファイルのサイズよりも小さい場合、コマンドレットはファイルのダウンロードを再開し、残りのバイトをファイルの末尾に追加しようとします。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-326">If the local file size is smaller than the remote file size, then the cmdlet will attempt to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="fbc8e-327">ローカルファイルのサイズがリモートファイルのサイズと同じ場合、アクションは実行されず、コマンドレットはダウンロードが既に完了しているものと想定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-327">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already completed.</span></span>

<span data-ttu-id="fbc8e-328">ローカルファイルのサイズがリモートファイルのサイズよりも大きい場合、ローカルファイルは上書きされ、リモートファイル全体が完全に再ダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-328">If the local file size is larger than the remote file size, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="fbc8e-329">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-329">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="fbc8e-330">リモートサーバーがダウンロードの再開をサポートしていない場合、ローカルファイルは上書きされ、リモートファイル全体が完全に再ダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-330">If the remote server does not support download resuming, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="fbc8e-331">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-331">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="fbc8e-332">ローカルファイルが存在しない場合は、ローカルファイルが作成され、リモートファイル全体が完全にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-332">If the local file doesn't exist, then the local file will be created and the entire remote file will be completely downloaded.</span></span> <span data-ttu-id="fbc8e-333">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-333">This behavior is the same as using **OutFile** without **Resume** .</span></span>

<span data-ttu-id="fbc8e-334">この機能は、PowerShell 6.1.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-334">This feature was added in PowerShell 6.1.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-335">-RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="fbc8e-335">-RetryIntervalSec</span></span>

<span data-ttu-id="fbc8e-336">400と 304 599 の間のエラーコードを受信したときの、接続の再試行の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-336">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="fbc8e-337">再試行回数を指定するには、 **Maximumretrycount** パラメーターも参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-337">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-338">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="fbc8e-338">-SessionVariable</span></span>

<span data-ttu-id="fbc8e-339">このコマンドレットによって web 要求セッションが作成され、値に保存される変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-339">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="fbc8e-340">ドル記号 () を付けずに変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-340">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="fbc8e-341">セッション変数を指定すると、は `Invoke-RestMethod` web 要求セッションオブジェクトを作成し、PowerShell セッション内の指定された名前の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-341">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="fbc8e-342">コマンドが完了すると、すぐに変数をセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-342">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="fbc8e-343">リモートセッションとは異なり、web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-343">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="fbc8e-344">これは、cookie、資格情報、リダイレクトの最大値、ユーザーエージェント文字列など、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-344">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="fbc8e-345">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-345">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="fbc8e-346">後続の Web 要求で Web 要求セッションを使用するには、 **WebSession** パラメーターの値にセッション変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-346">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="fbc8e-347">PowerShell は、新しい接続を確立するときに、web 要求セッションオブジェクトのデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-347">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="fbc8e-348">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-348">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="fbc8e-349">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-349">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="fbc8e-350">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-350">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-351">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="fbc8e-351">-SkipCertificateCheck</span></span>

<span data-ttu-id="fbc8e-352">有効期限、失効、信頼されたルート証明機関などのすべての検証を含む証明書検証チェックをスキップします。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-352">Skips certificate validation checks that include all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="fbc8e-353">このパラメーターの使用はセキュリティで保護されていないため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-353">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="fbc8e-354">このスイッチは、テスト目的で自己署名証明書を使用する既知のホストに対してのみ使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-354">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="fbc8e-355">ご自身の責任でをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-355">Use at your own risk.</span></span>

<span data-ttu-id="fbc8e-356">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-356">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-357">-SkipHeaderValidation</span><span class="sxs-lookup"><span data-stu-id="fbc8e-357">-SkipHeaderValidation</span></span>

<span data-ttu-id="fbc8e-358">コマンドレットが検証なしで要求にヘッダーを追加する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-358">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="fbc8e-359">標準に準拠していないヘッダー値が必要なサイトには、このスイッチを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-359">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="fbc8e-360">このスイッチを指定すると、値をオフにするための検証が無効になります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-360">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="fbc8e-361">指定した場合、すべてのヘッダーが検証なしで追加されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-361">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="fbc8e-362">これにより、 **ContentType** 、 **Headers** 、および **UserAgent** パラメーターに渡された値の検証が無効になります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-362">This will disable validation for values passed to the **ContentType** , **Headers** , and **UserAgent** parameters.</span></span>

<span data-ttu-id="fbc8e-363">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-363">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-364">-SkipHttpErrorCheck</span><span class="sxs-lookup"><span data-stu-id="fbc8e-364">-SkipHttpErrorCheck</span></span>

<span data-ttu-id="fbc8e-365">このパラメーターを指定すると、コマンドレットは HTTP エラー状態を無視し、応答の処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-365">This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses.</span></span>
<span data-ttu-id="fbc8e-366">エラー応答は、成功したかのようにパイプラインに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-366">The error responses are written to the pipeline just as if they were successful.</span></span>

<span data-ttu-id="fbc8e-367">このパラメーターは、PowerShell 7 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-367">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-368">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="fbc8e-368">-SslProtocol</span></span>

<span data-ttu-id="fbc8e-369">Web 要求に対して許可されている SSL/TLS プロトコルを設定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-369">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="fbc8e-370">既定では、システムでサポートされているすべての SSL/TLS プロトコルが許可されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-370">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="fbc8e-371">**Sslprotocol** では、コンプライアンスのために特定のプロトコルを制限できます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-371">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="fbc8e-372">**Sslprotocol** では、 `WebSslProtocol` フラグ列挙型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-372">**SslProtocol** uses the `WebSslProtocol` Flag Enum.</span></span> <span data-ttu-id="fbc8e-373">フラグ表記を使用して複数のプロトコルを指定したり、複数のオプションをと組み合わせたりすることはでき `WebSslProtocol` `-bor` ますが、複数のプロトコルを指定することは、すべてのプラットフォームでサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-373">It is possible to supply more than one protocol using flag notation or combining multiple `WebSslProtocol` options with `-bor`, however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="fbc8e-374">Windows 以外のプラットフォームでは、を `'Tls, Tls12'` オプションとして指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-374">On non-Windows platforms it may not be possible to supply `'Tls, Tls12'` as an option.</span></span>

<span data-ttu-id="fbc8e-375">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-375">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-376">-StatusCodeVariable</span><span class="sxs-lookup"><span data-stu-id="fbc8e-376">-StatusCodeVariable</span></span>

<span data-ttu-id="fbc8e-377">このパラメーターは、ステータスコードの整数値が割り当てられている変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-377">This parameter specifies a variable that's assigned a status code's integer value.</span></span> <span data-ttu-id="fbc8e-378">パラメーターでは、 **SkipHttpErrorCheck** パラメーターと共に使用すると、成功メッセージまたはエラーメッセージを識別できます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-378">The parameter can identify success messages or failure messages when used with the **SkipHttpErrorCheck** parameter.</span></span>

<span data-ttu-id="fbc8e-379">パラメーターの変数名をなどの文字列として入力し `-StatusCodeVariable "scv"` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-379">Input the parameter's variable name as a string such as `-StatusCodeVariable "scv"`.</span></span>

<span data-ttu-id="fbc8e-380">このパラメーターは、PowerShell 7 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-380">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-381">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="fbc8e-381">-TimeoutSec</span></span>

<span data-ttu-id="fbc8e-382">要求がタイムアウトになるまでの待機時間を指定します。値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-382">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="fbc8e-383">既定値は 0 で、無制限のタイムアウトを意味しています。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-383">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="fbc8e-384">ドメインネームシステム (DNS) クエリは、返されるまで最大15秒かかることがあります。要求に解決を必要とするホスト名が含まれていて、 **Timeoutsec** を0より大きく15秒未満に設定した場合、WebException がスローされる前に15秒以上かかることがあり、要求はタイムアウトになります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-384">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-385">-トークン</span><span class="sxs-lookup"><span data-stu-id="fbc8e-385">-Token</span></span>

<span data-ttu-id="fbc8e-386">要求に含める OAuth またはベアラートークン。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-386">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="fbc8e-387">**トークン** は、特定の **認証** オプションに必要です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-387">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="fbc8e-388">個別に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-388">It can't be used independently.</span></span>

<span data-ttu-id="fbc8e-389">**トークンは** 、 `SecureString` トークンを含むを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-389">**Token** takes a `SecureString` that contains the token.</span></span> <span data-ttu-id="fbc8e-390">トークンを指定するには、次のように手動で使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-390">To supply the token, manually use the following:</span></span>

`Invoke-RestMethod -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="fbc8e-391">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-391">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-392">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="fbc8e-392">-TransferEncoding</span></span>

<span data-ttu-id="fbc8e-393">転送エンコード HTTP 応答ヘッダーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-393">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="fbc8e-394">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-394">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fbc8e-395">まとめ</span><span class="sxs-lookup"><span data-stu-id="fbc8e-395">Chunked</span></span>
- <span data-ttu-id="fbc8e-396">圧縮</span><span class="sxs-lookup"><span data-stu-id="fbc8e-396">Compress</span></span>
- <span data-ttu-id="fbc8e-397">Deflate</span><span class="sxs-lookup"><span data-stu-id="fbc8e-397">Deflate</span></span>
- <span data-ttu-id="fbc8e-398">GZip</span><span class="sxs-lookup"><span data-stu-id="fbc8e-398">GZip</span></span>
- <span data-ttu-id="fbc8e-399">ID</span><span class="sxs-lookup"><span data-stu-id="fbc8e-399">Identity</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: chunked, compress, deflate, gzip, identity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-400">-Uri</span><span class="sxs-lookup"><span data-stu-id="fbc8e-400">-Uri</span></span>

<span data-ttu-id="fbc8e-401">Web 要求の送信先となるインターネットリソースの Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-401">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="fbc8e-402">このパラメーターは、HTTP、HTTPS、FTP、FILE の値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-402">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="fbc8e-403">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-403">This parameter is required.</span></span> <span data-ttu-id="fbc8e-404">パラメーター名 ( **Uri** ) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-404">The parameter name ( **Uri** ) is optional.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-405">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="fbc8e-405">-UseBasicParsing</span></span>

<span data-ttu-id="fbc8e-406">このパラメーターは非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-406">This parameter has been deprecated.</span></span> <span data-ttu-id="fbc8e-407">PowerShell 6.0.0 以降では、すべての Web 要求で基本的な解析のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-407">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="fbc8e-408">このパラメーターは下位互換性のためだけに含まれています。このパラメーターを使用しても、コマンドレットの操作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-408">This parameter is included for backwards compatibility only and any use of it will have no effect on the operation of the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-409">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="fbc8e-409">-UseDefaultCredentials</span></span>

<span data-ttu-id="fbc8e-410">コマンドレットが、web 要求を送信するために現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-410">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="fbc8e-411">**認証** または **資格情報** と共に使用することはできません。また、すべてのプラットフォームでサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-411">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-412">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="fbc8e-412">-UserAgent</span></span>

<span data-ttu-id="fbc8e-413">Web 要求のユーザー エージェント文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-413">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="fbc8e-414">既定のユーザーエージェントは、 `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` オペレーティングシステムとプラットフォームによって微妙な違いがあるに似ています。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-414">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="fbc8e-415">ほとんどのインターネットブラウザーで使用される標準のユーザーエージェント文字列を使用して web サイトをテストするには、Chrome、FireFox、InternetExplorer、Opera、Safari などの [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) クラスのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-415">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-416">-WebSession</span><span class="sxs-lookup"><span data-stu-id="fbc8e-416">-WebSession</span></span>

<span data-ttu-id="fbc8e-417">Web 要求セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-417">Specifies a web request session.</span></span> <span data-ttu-id="fbc8e-418">ドル記号 () を含む変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-418">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="fbc8e-419">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-419">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="fbc8e-420">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-420">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="fbc8e-421">`Content-Type`**本文** に **MultipartFormDataContent** オブジェクトが指定されている場合、などのコンテンツ関連ヘッダーもオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-421">Content related headers, such as `Content-Type`, will be also be overridden when a **MultipartFormDataContent** object is supplied for **Body** .</span></span>

<span data-ttu-id="fbc8e-422">リモートセッションとは異なり、web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-422">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="fbc8e-423">これは、cookie、資格情報、リダイレクトの最大値、ユーザーエージェント文字列など、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-423">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="fbc8e-424">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-424">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="fbc8e-425">Web 要求セッションを作成するには、コマンドの **sessionvariable** パラメーターの値にドル記号を付けずに変数名を入力し `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-425">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="fbc8e-426">`Invoke-RestMethod` セッションを作成し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-426">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="fbc8e-427">後続のコマンドで、この変数を **WebSession** パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-427">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="fbc8e-428">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-428">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbc8e-429">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbc8e-429">CommonParameters</span></span>

<span data-ttu-id="fbc8e-430">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-430">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbc8e-431">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-431">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbc8e-432">入力</span><span class="sxs-lookup"><span data-stu-id="fbc8e-432">INPUTS</span></span>

### <span data-ttu-id="fbc8e-433">System.Object</span><span class="sxs-lookup"><span data-stu-id="fbc8e-433">System.Object</span></span>

<span data-ttu-id="fbc8e-434">パイプを使用して、web 要求の本文をにパイプすることができ `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-434">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="fbc8e-435">出力</span><span class="sxs-lookup"><span data-stu-id="fbc8e-435">OUTPUTS</span></span>

### <span data-ttu-id="fbc8e-436">Int64、System.string、System.Xml.Xmlドキュメント</span><span class="sxs-lookup"><span data-stu-id="fbc8e-436">System.Int64, System.String, System.Xml.XmlDocument</span></span>

<span data-ttu-id="fbc8e-437">このコマンドレットの出力は、取得するコンテンツの書式によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-437">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="fbc8e-438">PSObject</span><span class="sxs-lookup"><span data-stu-id="fbc8e-438">PSObject</span></span>

<span data-ttu-id="fbc8e-439">要求が JSON 文字列を返す場合、は `Invoke-RestMethod` 文字列を表す **PSObject** を返します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-439">If the request returns JSON strings, `Invoke-RestMethod` returns a **PSObject** that represents the strings.</span></span>

## <span data-ttu-id="fbc8e-440">注</span><span class="sxs-lookup"><span data-stu-id="fbc8e-440">NOTES</span></span>

<span data-ttu-id="fbc8e-441">一部の機能は、一部のプラットフォームでは使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-441">Some features may not be available on all platforms.</span></span>

<span data-ttu-id="fbc8e-442">.NET Core 3.1 の変更のため、PowerShell 7.0 以降では、 [Httpclient. defaultproxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) プロパティを使用してプロキシの構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-442">Because of changes in .NET Core 3.1, PowerShell 7.0 and higher use the [HttpClient.DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) property to determine the proxy configuration.</span></span>

<span data-ttu-id="fbc8e-443">このプロパティの値は、プラットフォームによって決まります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-443">The value of this property is determined by your platform:</span></span>

- <span data-ttu-id="fbc8e-444">**Windows の場合** : 環境変数からプロキシ構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-444">**For Windows** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="fbc8e-445">これらの変数が定義されていない場合、プロパティはユーザーのプロキシ設定から派生します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-445">If those variables are not defined the property is derived from the user's proxy settings.</span></span>
- <span data-ttu-id="fbc8e-446">**MacOS の場合** : 環境変数からプロキシ構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-446">**For macOS** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="fbc8e-447">これらの変数が定義されていない場合、プロパティはシステムのプロキシ設定から派生します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-447">If those variables are not defined the property is derived from the system's proxy settings.</span></span>
- <span data-ttu-id="fbc8e-448">**Linux の場合** : 環境変数からプロキシ構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-448">**For Linux** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="fbc8e-449">これらの変数が定義されていない場合、プロパティは、すべてのアドレスをバイパスするように構成されていないインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-449">If those variables are not defined the property initializes a non-configured instance that bypasses all addresses.</span></span>

<span data-ttu-id="fbc8e-450">Windows および Unix ベースのプラットフォームでの初期化に使用される環境変数 `DefaultProxy` は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-450">The environment variables used for `DefaultProxy` initialization on Windows and Unix-based platforms are:</span></span>

- <span data-ttu-id="fbc8e-451">` HTTP_PROXY`: HTTP 要求で使用されるプロキシサーバーのホスト名または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-451">` HTTP_PROXY`: the hostname or IP address of the proxy server used on HTTP requests.</span></span>
- <span data-ttu-id="fbc8e-452">`HTTPS_PROXY`: HTTPS 要求で使用されるプロキシサーバーのホスト名または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-452">`HTTPS_PROXY`: the hostname or IP address of the proxy server used on HTTPS requests.</span></span>
- <span data-ttu-id="fbc8e-453">`ALL_PROXY`: HTTP および HTTPS 要求で使用されるプロキシサーバーのホスト名または IP アドレス `HTTP_PROXY` (またはが定義されて `HTTPS_PROXY` いない場合)。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-453">`ALL_PROXY`: the hostname or IP address of the proxy server used on HTTP and HTTPS requests in case `HTTP_PROXY` or `HTTPS_PROXY` are not defined.</span></span>
- <span data-ttu-id="fbc8e-454">`NO_PROXY`: プロキシから除外する必要があるホスト名のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="fbc8e-454">`NO_PROXY`: a comma-separated list of hostnames that should be excluded from proxying.</span></span>

## <span data-ttu-id="fbc8e-455">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fbc8e-455">RELATED LINKS</span></span>

[<span data-ttu-id="fbc8e-456">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="fbc8e-456">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="fbc8e-457">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="fbc8e-457">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="fbc8e-458">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="fbc8e-458">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

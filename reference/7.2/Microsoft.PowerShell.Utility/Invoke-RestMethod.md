---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: 91cd2dda912d6e79177e8a961012a1604d9460ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599290"
---
# <span data-ttu-id="de4eb-102">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="de4eb-102">Invoke-RestMethod</span></span>

## <span data-ttu-id="de4eb-103">概要</span><span class="sxs-lookup"><span data-stu-id="de4eb-103">SYNOPSIS</span></span>
<span data-ttu-id="de4eb-104">RESTful Web サービスに HTTP または HTTPS 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-104">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="de4eb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de4eb-105">SYNTAX</span></span>

### <span data-ttu-id="de4eb-106">StandardMethod (既定値)</span><span class="sxs-lookup"><span data-stu-id="de4eb-106">StandardMethod (Default)</span></span>

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

### <span data-ttu-id="de4eb-107">StandardMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="de4eb-107">StandardMethodNoProxy</span></span>

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

### <span data-ttu-id="de4eb-108">CustomMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="de4eb-108">CustomMethodNoProxy</span></span>

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

### <span data-ttu-id="de4eb-109">CustomMethod</span><span class="sxs-lookup"><span data-stu-id="de4eb-109">CustomMethod</span></span>

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

## <span data-ttu-id="de4eb-110">説明</span><span class="sxs-lookup"><span data-stu-id="de4eb-110">Description</span></span>

<span data-ttu-id="de4eb-111">コマンドレットは、高度 `Invoke-RestMethod` に構造化されたデータを返す HTTP 要求と HTTPS 要求を、表現された状態転送 (REST) web サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-111">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that return richly structured data.</span></span>

<span data-ttu-id="de4eb-112">PowerShell は、データ型に基づいて応答を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-112">PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="de4eb-113">RSS フィードまたは ATOM フィードの場合、PowerShell は Item または Entry XML ノードを返します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-113">For an RSS or ATOM feed, PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="de4eb-114">JavaScript Object Notation (JSON) または XML の場合、PowerShell はコンテンツをオブジェクトに変換または逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-114">For JavaScript Object Notation (JSON) or XML, PowerShell converts, or deserializes, the content into objects.</span></span>

<span data-ttu-id="de4eb-115">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-115">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="de4eb-116">PowerShell 7.0 以降では、は `Invoke-RestMethod` 環境変数によって定義されたプロキシ構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="de4eb-116">Beginning in PowerShell 7.0, `Invoke-RestMethod` supports proxy configuration defined by environment variables.</span></span> <span data-ttu-id="de4eb-117">この記事の「 [メモ](#notes) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4eb-117">See the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="de4eb-118">例</span><span class="sxs-lookup"><span data-stu-id="de4eb-118">EXAMPLES</span></span>

### <span data-ttu-id="de4eb-119">例 1: PowerShell RSS フィードを取得する</span><span class="sxs-lookup"><span data-stu-id="de4eb-119">Example 1: Get the PowerShell RSS feed</span></span>

<span data-ttu-id="de4eb-120">この例では、 `Invoke-RestMethod` コマンドレットを使用して、PowerShell ブログの RSS フィードから情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-120">This example uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="de4eb-121">このコマンドは、コマンドレットを使用して、 `Format-Table` テーブル内の各ブログの **Title** プロパティと **pubDate** プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-121">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

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

### <span data-ttu-id="de4eb-122">例 2: POST 要求を実行する</span><span class="sxs-lookup"><span data-stu-id="de4eb-122">Example 2: Run a POST request</span></span>

<span data-ttu-id="de4eb-123">この例では、ユーザーがを実行して、 `Invoke-RestMethod` ユーザーの組織のイントラネット web サイトで POST 要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-123">In this example, a user runs `Invoke-RestMethod` to do a POST request on an intranet website in the user's organization.</span></span>

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

<span data-ttu-id="de4eb-124">資格情報の入力が求められ、に格納され `$Cred` ます。また、には、アクセスする URL が定義されてい `$Url` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-124">The credentials are prompted for and then stored in `$Cred` and the URL that will be access is defined in `$Url`.</span></span>

<span data-ttu-id="de4eb-125">変数は、 `$Body` 検索条件を記述し、CSV を出力モードとして指定します。また、返されるデータの期間を指定します。この時間を経過すると、2日前の日前に終了します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-125">The `$Body` variable describes the search criteria, specifies CSV as the output mode, and specifies a time period for returned data that starts two days ago and ends one day ago.</span></span> <span data-ttu-id="de4eb-126">Body 変数は、が通信する特定の REST API に適用されるパラメーターの値を指定し `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-126">The body variable specifies values for parameters that apply to the particular REST API with which `Invoke-RestMethod` is communicating.</span></span>

<span data-ttu-id="de4eb-127">`Invoke-RestMethod`コマンドは、すべての変数を使用して実行され、結果として得られる CSV 出力ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-127">The `Invoke-RestMethod` command is run with all variables in place, specifying a path and file name for the resulting CSV output file.</span></span>

### <span data-ttu-id="de4eb-128">例 3: リレーションリンクに従う</span><span class="sxs-lookup"><span data-stu-id="de4eb-128">Example 3: Follow relation links</span></span>

<span data-ttu-id="de4eb-129">一部の REST Api では、 [RFC5988](https://tools.ietf.org/html/rfc5988#page-6)ごとの関係リンクを使用した改ページがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="de4eb-129">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="de4eb-130">ヘッダーを解析して次のページの URL を取得する代わりに、コマンドレットでこの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-130">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="de4eb-131">この例では、PowerShell GitHub リポジトリから、問題の最初の2ページが返されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-131">This example returns the first two pages of issues from the PowerShell GitHub repository.</span></span>

```powershell
$url = 'https://api.github.com/repos/powershell/powershell/issues'
Invoke-RestMethod $url -FollowRelLink -MaximumFollowRelLink 2
```

### <span data-ttu-id="de4eb-132">例 4: 単純化されたマルチパート/フォーム-データ送信</span><span class="sxs-lookup"><span data-stu-id="de4eb-132">Example 4: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="de4eb-133">一部の Api `multipart/form-data` では、ファイルのアップロードと混合コンテンツの送信が必要です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-133">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="de4eb-134">この例では、ユーザーのプロファイルを更新する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-134">This example demonstrates how to update a user's profile.</span></span>

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

<span data-ttu-id="de4eb-135">プロファイルフォームには、、、 `firstName` 、、、 `lastName` `email` `avatar` `birthday` および `hobbies` の各フィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-135">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="de4eb-136">API では、ユーザープロファイル pic をフィールドに指定するイメージが必要です `avatar` 。</span><span class="sxs-lookup"><span data-stu-id="de4eb-136">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="de4eb-137">API は、 `hobbies` 同じ形式で複数のエントリを送信することも許可します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-137">The API will also accept multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="de4eb-138">`$Form`ハッシュテーブルを作成する場合、キー名はフォームフィールド名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-138">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="de4eb-139">既定では、ハッシュテーブルの値は文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-139">By default, the values of the HashTable will be converted to strings.</span></span> <span data-ttu-id="de4eb-140">値が存在する場合は、 `System.IO.FileInfo` ファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-140">If a `System.IO.FileInfo` value is present, the file contents will be submitted.</span></span> <span data-ttu-id="de4eb-141">配列やリストなどのコレクションが存在する場合、フォームフィールドは複数回送信されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-141">If a collection such as arrays or lists are present, the form field will be submitted multiple times.</span></span>

<span data-ttu-id="de4eb-142">キーでを使用する `Get-Item` `avatar` と、 `FileInfo` オブジェクトが値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-142">By using `Get-Item` on the `avatar` key, the `FileInfo` object will be set as the value.</span></span> <span data-ttu-id="de4eb-143">結果として、のイメージデータが `jdoe.png` 送信されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-143">The result is that the image data for `jdoe.png` will be submitted.</span></span>

<span data-ttu-id="de4eb-144">キーにリストを指定すると、 `hobbies` フィールドは、 `hobbies` リスト項目ごとに1回送信されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-144">By supplying a list to the `hobbies` key, the `hobbies` field will be present in the submissions once for each list item.</span></span>

### <span data-ttu-id="de4eb-145">例 5: 複数のヘッダーを渡す</span><span class="sxs-lookup"><span data-stu-id="de4eb-145">Example 5: Pass multiple headers</span></span>

<span data-ttu-id="de4eb-146">多くの場合、Api は認証または検証のために渡されたヘッダーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="de4eb-146">APIs often require passed headers for authentication or validation.</span></span> <span data-ttu-id="de4eb-147">この例では、から複数のヘッダーを REST API に渡す方法について説明し `hash-table` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-147">This example demonstrates, how to pass multiple headers from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

## <span data-ttu-id="de4eb-148">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de4eb-148">Parameters</span></span>

### <span data-ttu-id="de4eb-149">-AllowUnencryptedAuthentication</span><span class="sxs-lookup"><span data-stu-id="de4eb-149">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="de4eb-150">暗号化されていない接続を介した資格情報とシークレットの送信を許可します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-150">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="de4eb-151">既定では、で始まらない **Uri** を指定した **資格情報** または任意の **認証** オプションを指定すると、エラーが発生します。この要求は、暗号化されていない接続を `https://` 介してプレーンテキストで誤ってシークレットを通信するのを防ぐために中止されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-151">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` will result in an error and the request will abort to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="de4eb-152">独自のリスクでこの動作をオーバーライドするには、 **Allowunencryptedauthentication** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-152">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="de4eb-153">このパラメーターの使用はセキュリティで保護されていないため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-153">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="de4eb-154">これは、暗号化された接続を提供できないレガシシステムとの互換性のためだけに用意されています。</span><span class="sxs-lookup"><span data-stu-id="de4eb-154">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="de4eb-155">ご自身の責任でをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="de4eb-155">Use at your own risk.</span></span>

<span data-ttu-id="de4eb-156">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-156">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-157">-認証</span><span class="sxs-lookup"><span data-stu-id="de4eb-157">-Authentication</span></span>

<span data-ttu-id="de4eb-158">要求に使用する明示的な認証の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-158">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="de4eb-159">既定値は **[None]\(なし\)** です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-159">The default is **None**.</span></span>
<span data-ttu-id="de4eb-160">**UseDefaultCredentials** で **認証** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-160">**Authentication** can't be used with **UseDefaultCredentials**.</span></span>

<span data-ttu-id="de4eb-161">使用可能な認証オプション:</span><span class="sxs-lookup"><span data-stu-id="de4eb-161">Available Authentication Options:</span></span>

- <span data-ttu-id="de4eb-162">**None**: **認証** が指定されていない場合の既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-162">**None**: This is the default option when **Authentication** is not supplied.</span></span> <span data-ttu-id="de4eb-163">明示的な認証は使用されません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-163">No explicit authentication will be used.</span></span>
- <span data-ttu-id="de4eb-164">**基本**: **資格情報** が必要です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-164">**Basic**: Requires **Credential**.</span></span> <span data-ttu-id="de4eb-165">資格情報は、RFC 7617 の基本認証ヘッダーを形式で送信するために使用され `Authorization: Basic` `base64(user:password)` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-165">The credentials will be used to send an RFC 7617 Basic Authentication `Authorization: Basic` header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="de4eb-166">**ベアラー**: **トークン** が必要です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-166">**Bearer**: Requires **Token**.</span></span> <span data-ttu-id="de4eb-167">は、指定されたトークンを使用して、および RFC 6750 ヘッダーを送信し `Authorization: Bearer` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-167">Will send and RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="de4eb-168">これは **OAuth** のエイリアスです</span><span class="sxs-lookup"><span data-stu-id="de4eb-168">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="de4eb-169">**OAuth**: **トークン** が必要です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-169">**OAuth**: Requires **Token**.</span></span> <span data-ttu-id="de4eb-170">は、指定された `Authorization: Bearer` トークンを使用して RFC 6750 ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-170">Will send an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="de4eb-171">これは **ベアラー** のエイリアスです</span><span class="sxs-lookup"><span data-stu-id="de4eb-171">This is an alias for **Bearer**</span></span>

<span data-ttu-id="de4eb-172">**認証** を指定すると、 `Authorization` **ヘッダー** に指定されたヘッダーまたは **web セッション** に含まれるヘッダーが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-172">Supplying **Authentication** will override any `Authorization` headers supplied to **Headers** or included in **WebSession**.</span></span>

<span data-ttu-id="de4eb-173">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-173">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-174">-本文</span><span class="sxs-lookup"><span data-stu-id="de4eb-174">-Body</span></span>

<span data-ttu-id="de4eb-175">要求の本文を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-175">Specifies the body of the request.</span></span> <span data-ttu-id="de4eb-176">本文は、ヘッダーに続く要求の内容です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-176">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="de4eb-177">パイプを使用して、本文の値をにパイプすることもでき `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-177">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="de4eb-178">**Body** パラメーターを使用すると、クエリ パラメーターのリストを指定したり、応答の内容を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-178">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="de4eb-179">入力が GET 要求で、本文が `IDictionary` (通常はハッシュテーブル) の場合、本文はクエリパラメーターとして Uniform Resource Identifier (URI) に追加されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-179">When the input is a GET request, and the body is an `IDictionary` (typically, a hash table), the body is added to the Uniform Resource Identifier (URI) as query parameters.</span></span> <span data-ttu-id="de4eb-180">その他の要求の種類 (POST など) の場合、本文は標準的な "名前=値" の形式で要求本文の値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-180">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

<span data-ttu-id="de4eb-181">本文がフォームである場合、または別の呼び出しの出力である場合 `Invoke-WebRequest` 、PowerShell は要求の内容をフォームフィールドに設定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-181">When the body is a form, or it's the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="de4eb-182">**Body** パラメーターは、 **MultipartFormDataContent** オブジェクトを受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-182">The **Body** parameter may also accept a **System.Net.Http.MultipartFormDataContent** object.</span></span> <span data-ttu-id="de4eb-183">これにより、要求が容易になり `multipart/form-data` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-183">This will facilitate `multipart/form-data` requests.</span></span> <span data-ttu-id="de4eb-184">**MultipartFormDataContent** オブジェクトが **本文** に指定されている場合、 **ContentType**、 **headers**、または **websession** パラメーターに指定されたコンテンツに関連するヘッダーは、オブジェクトのコンテンツヘッダーによってオーバーライドされ `MultipartFormDataContent` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-184">When a **MultipartFormDataContent** object is supplied for **Body**, any content related headers supplied to the **ContentType**, **Headers**, or **WebSession** parameters will be overridden by the content headers of the `MultipartFormDataContent` object.</span></span> <span data-ttu-id="de4eb-185">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-185">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-186">-証明書</span><span class="sxs-lookup"><span data-stu-id="de4eb-186">-Certificate</span></span>

<span data-ttu-id="de4eb-187">セキュリティで保護された Web 要求に使用するクライアント証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-187">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="de4eb-188">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-188">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="de4eb-189">証明書を検索するには、を使用する `Get-PfxCertificate` か、 `Get-ChildItem` 証明書 () ドライブのコマンドレットを使用し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-189">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="de4eb-190">証明書が有効でないか、十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-190">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="de4eb-191">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="de4eb-191">-CertificateThumbprint</span></span>

<span data-ttu-id="de4eb-192">要求を送信するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-192">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="de4eb-193">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-193">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="de4eb-194">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-194">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="de4eb-195">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-195">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="de4eb-196">証明書の拇印を取得するに `Get-Item` は、PowerShell ドライブでまたはコマンドを使用し `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-196">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="de4eb-197">この機能は現在、Windows OS プラットフォームでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de4eb-197">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="de4eb-198">-ContentType</span><span class="sxs-lookup"><span data-stu-id="de4eb-198">-ContentType</span></span>

<span data-ttu-id="de4eb-199">Web 要求のコンテンツ タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-199">Specifies the content type of the web request.</span></span>

<span data-ttu-id="de4eb-200">このパラメーターを省略して、要求メソッドが POST の場合は、 `Invoke-RestMethod` コンテンツの種類をに設定し `application/x-www-form-urlencoded` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-200">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="de4eb-201">それ以外の場合は、の呼び出しでコンテンツの種類が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-201">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="de4eb-202"> `MultipartFormDataContent` オブジェクトが **本文** に対して指定されると、ContentType はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-202">**ContentType** will be overridden when a `MultipartFormDataContent` object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="de4eb-203">-Credential</span><span class="sxs-lookup"><span data-stu-id="de4eb-203">-Credential</span></span>

<span data-ttu-id="de4eb-204">要求を送信するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-204">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="de4eb-205">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-205">The default is the current user.</span></span>

<span data-ttu-id="de4eb-206">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-206">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="de4eb-207">**資格情報** は、単独で使用することも、特定の **認証** パラメーターオプションと組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-207">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="de4eb-208">リモートサーバーが認証チャレンジ要求を送信した場合にのみ、リモートサーバーに資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-208">When used alone, it will only supply credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="de4eb-209">**認証** オプションと共に使用すると、資格情報が明示的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-209">When used with **Authentication** options, the credentials will be explicitly sent.</span></span>

<span data-ttu-id="de4eb-210">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-210">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="de4eb-211">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4eb-211">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="de4eb-212">-CustomMethod</span><span class="sxs-lookup"><span data-stu-id="de4eb-212">-CustomMethod</span></span>

<span data-ttu-id="de4eb-213">Web 要求に使用するカスタムメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-213">Specifies custom method used for the web request.</span></span> <span data-ttu-id="de4eb-214">これは、エンドポイントで必要とされる要求メソッドで使用できますが、 **メソッド** では使用できません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-214">This can be used with the Request Method required by the endpoint is not an available option on the **Method**.</span></span> <span data-ttu-id="de4eb-215">**メソッド** と **custommethod** を一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-215">**Method** and **CustomMethod** cannot be used together.</span></span>

<span data-ttu-id="de4eb-216">例:</span><span class="sxs-lookup"><span data-stu-id="de4eb-216">Example:</span></span>

`Invoke-RestMethod -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="de4eb-217">これにより `TEST` 、API に HTTP 要求が作成されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-217">This makes a `TEST` HTTP request to the API.</span></span>

<span data-ttu-id="de4eb-218">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-218">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-219">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="de4eb-219">-DisableKeepAlive</span></span>

<span data-ttu-id="de4eb-220">コマンドレットが HTTP ヘッダーの **KeepAlive** 値を False に設定することを示します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-220">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="de4eb-221">既定では、**KeepAlive** は True です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-221">By default, **KeepAlive** is True.</span></span> <span data-ttu-id="de4eb-222">**KeepAlive** は、後続の要求を容易にするために、サーバーへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-222">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="de4eb-223">-リンク</span><span class="sxs-lookup"><span data-stu-id="de4eb-223">-FollowRelLink</span></span>

<span data-ttu-id="de4eb-224">コマンドレットが関係リンクに従う必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-224">Indicates the cmdlet should follow relation links.</span></span>

<span data-ttu-id="de4eb-225">一部の REST Api では、 [RFC5988](https://tools.ietf.org/html/rfc5988#page-6)ごとの関係リンクを使用した改ページがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="de4eb-225">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="de4eb-226">ヘッダーを解析して次のページの URL を取得する代わりに、コマンドレットでこの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-226">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="de4eb-227">リレーションリンクに従う回数を設定するには、 **Maximumの Rellink** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-227">To set how many times to follow relation links, use the **MaximumFollowRelLink** parameter.</span></span>

<span data-ttu-id="de4eb-228">このスイッチを使用すると、コマンドレットは結果のページのコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-228">When using this switch, the cmdlet returns a collection of pages of results.</span></span> <span data-ttu-id="de4eb-229">結果の各ページには、複数の結果項目が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-229">Each page of results may contain multiple result items.</span></span>

<span data-ttu-id="de4eb-230">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-230">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-231">-フォーム</span><span class="sxs-lookup"><span data-stu-id="de4eb-231">-Form</span></span>

<span data-ttu-id="de4eb-232">辞書を送信に変換 `multipart/form-data` します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-232">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="de4eb-233">**フォーム** を **本文** と共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-233">**Form** may not be used with **Body**.</span></span>
<span data-ttu-id="de4eb-234">**ContentType** が無視される場合は。</span><span class="sxs-lookup"><span data-stu-id="de4eb-234">If **ContentType** will be ignored.</span></span>

<span data-ttu-id="de4eb-235">ディクショナリのキーは、フォームフィールド名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-235">The keys of the dictionary will be used as the form field names.</span></span> <span data-ttu-id="de4eb-236">既定では、フォーム値は文字列値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-236">By default, form values will be converted to string values.</span></span>

<span data-ttu-id="de4eb-237">値が **system.servicemodel オブジェクトの** 場合は、バイナリファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-237">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span>
<span data-ttu-id="de4eb-238">ファイルの名前は、として送信され `filename` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-238">The name of the file will be submitted as the `filename`.</span></span> <span data-ttu-id="de4eb-239">MIME はとして設定され `application/octet-stream` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-239">The MIME will be set as `application/octet-stream`.</span></span> <span data-ttu-id="de4eb-240">`Get-Item` を使用 **すると、system.object オブジェクト** を簡単に指定できます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-240">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="de4eb-241">値が配列やリストなどのコレクション型である場合、for フィールドは複数回送信されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-241">If the value is a collection type, such as an Array or List, the for field will be submitted multiple times.</span></span> <span data-ttu-id="de4eb-242">既定では、リストの値は文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-242">The values of the list will be treated as strings by default.</span></span> <span data-ttu-id="de4eb-243">値が **system.servicemodel オブジェクトの** 場合は、バイナリファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-243">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span> <span data-ttu-id="de4eb-244">入れ子になったコレクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-244">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="de4eb-245">上の例では、 `tags` フィールドは、、、およびの各につき1回、フォームで3回指定され `Vacation` `Italy` `2017` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-245">In the above example, the `tags` field will be supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="de4eb-246">この `pictures` フィールドは、フォルダー内のファイルごとに1回送信され `2017-Italy` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-246">The `pictures` field will also be submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="de4eb-247">そのフォルダー内のファイルのバイナリコンテンツは、値として送信されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-247">The binary contents of the files in that folder will be submitted as the values.</span></span>

<span data-ttu-id="de4eb-248">この機能は、PowerShell 6.1.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-248">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="de4eb-249">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="de4eb-249">-Headers</span></span>

<span data-ttu-id="de4eb-250">Web 要求のヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-250">Specifies the headers of the web request.</span></span> <span data-ttu-id="de4eb-251">ハッシュ テーブルまたは辞書を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-251">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="de4eb-252">UserAgent ヘッダーを設定するには、**UserAgent** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-252">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="de4eb-253">このパラメーターを使用して `User-Agent` 、またはクッキーヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-253">You cannot use this parameter to specify `User-Agent` or cookie headers.</span></span>

<span data-ttu-id="de4eb-254">などのコンテンツ関連ヘッダーは、 `Content-Type` `MultipartFormDataContent` オブジェクトが **本文** に指定されたときにオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-254">Content related headers, such as `Content-Type` will be overridden when a `MultipartFormDataContent` object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="de4eb-255">-InFile</span><span class="sxs-lookup"><span data-stu-id="de4eb-255">-InFile</span></span>

<span data-ttu-id="de4eb-256">ファイルから Web 要求の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-256">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="de4eb-257">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-257">Enter a path and file name.</span></span> <span data-ttu-id="de4eb-258">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-258">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="de4eb-259">-MaximumFollowRelLink</span><span class="sxs-lookup"><span data-stu-id="de4eb-259">-MaximumFollowRelLink</span></span>

<span data-ttu-id="de4eb-260">**リンク** が使用されている場合に、関係リンクに従う回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-260">Specifies how many times to follow relation links if **FollowRelLink** is used.</span></span> <span data-ttu-id="de4eb-261">要求が多すぎることが原因で REST api が調整された場合は、小さい値が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-261">A smaller value may be needed if the REST api throttles due to too many requests.</span></span> <span data-ttu-id="de4eb-262">既定値は `[Int32]::MaxValue` です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-262">The default value is `[Int32]::MaxValue`.</span></span> <span data-ttu-id="de4eb-263">値を 0 (ゼロ) にすると、次の関係リンクが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-263">A value of 0 (zero) prevents following relation links.</span></span>

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

### <span data-ttu-id="de4eb-264">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="de4eb-264">-MaximumRedirection</span></span>

<span data-ttu-id="de4eb-265">接続に失敗する前に PowerShell が代替 Uniform Resource Identifier (URI) に接続をリダイレクトする回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-265">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="de4eb-266">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-266">The default value is 5.</span></span> <span data-ttu-id="de4eb-267">値 0 (ゼロ) を指定した場合、リダイレクトはまったく行われません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-267">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="de4eb-268">-MaximumRetryCount</span><span class="sxs-lookup"><span data-stu-id="de4eb-268">-MaximumRetryCount</span></span>

<span data-ttu-id="de4eb-269">400と599の間のエラーコード (包括的または 304) を受信したときに PowerShell が接続を再試行する回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-269">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="de4eb-270">再試行回数を指定する場合は、 **Retryintervalsec** パラメーターも参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4eb-270">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="de4eb-271">-メソッド</span><span class="sxs-lookup"><span data-stu-id="de4eb-271">-Method</span></span>

<span data-ttu-id="de4eb-272">Web 要求に使用するメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-272">Specifies the method used for the web request.</span></span> <span data-ttu-id="de4eb-273">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-273">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="de4eb-274">Default</span><span class="sxs-lookup"><span data-stu-id="de4eb-274">Default</span></span>
- <span data-ttu-id="de4eb-275">削除</span><span class="sxs-lookup"><span data-stu-id="de4eb-275">Delete</span></span>
- <span data-ttu-id="de4eb-276">取得</span><span class="sxs-lookup"><span data-stu-id="de4eb-276">Get</span></span>
- <span data-ttu-id="de4eb-277">Head</span><span class="sxs-lookup"><span data-stu-id="de4eb-277">Head</span></span>
- <span data-ttu-id="de4eb-278">マージする</span><span class="sxs-lookup"><span data-stu-id="de4eb-278">Merge</span></span>
- <span data-ttu-id="de4eb-279">オプション</span><span class="sxs-lookup"><span data-stu-id="de4eb-279">Options</span></span>
- <span data-ttu-id="de4eb-280">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="de4eb-280">Patch</span></span>
- <span data-ttu-id="de4eb-281">投稿</span><span class="sxs-lookup"><span data-stu-id="de4eb-281">Post</span></span>
- <span data-ttu-id="de4eb-282">Put</span><span class="sxs-lookup"><span data-stu-id="de4eb-282">Put</span></span>
- <span data-ttu-id="de4eb-283">Trace</span><span class="sxs-lookup"><span data-stu-id="de4eb-283">Trace</span></span>

<span data-ttu-id="de4eb-284">**Custommethod** パラメーターは、上に一覧表示されていない要求メソッドに使用できます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-284">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

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

### <span data-ttu-id="de4eb-285">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="de4eb-285">-NoProxy</span></span>

<span data-ttu-id="de4eb-286">コマンドレットが宛先に接続するためにプロキシを使用しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-286">Indicates that the cmdlet will not use a proxy to reach the destination.</span></span>

<span data-ttu-id="de4eb-287">Internet Explorer で構成されているプロキシ、または環境に指定されているプロキシをバイパスする必要がある場合は、このスイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-287">When you need to bypass the proxy configured in Internet Explorer, or a proxy specified in the environment, use this switch.</span></span>

<span data-ttu-id="de4eb-288">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-288">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="de4eb-289">-出力</span><span class="sxs-lookup"><span data-stu-id="de4eb-289">-OutFile</span></span>

<span data-ttu-id="de4eb-290">指定した出力ファイルに応答本文を保存します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-290">Saves the response body in the specified output file.</span></span> <span data-ttu-id="de4eb-291">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-291">Enter a path and file name.</span></span> <span data-ttu-id="de4eb-292">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-292">If you omit the path, the default is the current location.</span></span> <span data-ttu-id="de4eb-293">名前はリテラルパスとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-293">The name is treated as a literal path.</span></span> <span data-ttu-id="de4eb-294">角かっこ () を含む名前 `[]` は、単一引用符 () で囲む必要があり `'` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-294">Names that contain brackets (`[]`) must be enclosed in single quotes (`'`).</span></span>

<span data-ttu-id="de4eb-295">既定では、は `Invoke-RestMethod` パイプラインに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-295">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="de4eb-296">結果をファイルとパイプラインに送信するには、**Passthru** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-296">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="de4eb-297">-PassThru</span><span class="sxs-lookup"><span data-stu-id="de4eb-297">-PassThru</span></span>

<span data-ttu-id="de4eb-298">結果を返す一方でファイルにも書き込みます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-298">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="de4eb-299">このパラメーターは、同時に **OutFile** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-299">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="de4eb-300">-PreserveAuthorizationOnRedirect</span><span class="sxs-lookup"><span data-stu-id="de4eb-300">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="de4eb-301">コマンドレットで、リダイレクト全体でヘッダーを保持する必要があることを示し `Authorization` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-301">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="de4eb-302">既定では、コマンドレットは、 `Authorization` リダイレクトの前にヘッダーを除去します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-302">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="de4eb-303">このパラメーターを指定すると、ヘッダーがリダイレクト場所に送信される必要がある場合に、このロジックが無効になります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-303">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="de4eb-304">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-304">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-305">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="de4eb-305">-Proxy</span></span>

<span data-ttu-id="de4eb-306">は、インターネットリソースに直接接続するのではなく、要求にプロキシサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-306">Uses a proxy server for the request, rather than connecting directly to the internet resource.</span></span> <span data-ttu-id="de4eb-307">ネットワークプロキシサーバーの Uniform Resource Identifier (URI) を入力します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-307">Enter the Uniform Resource Identifier (URI) of a network proxy server.</span></span>

<span data-ttu-id="de4eb-308">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-308">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-309">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="de4eb-309">-ProxyCredential</span></span>

<span data-ttu-id="de4eb-310">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-310">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="de4eb-311">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-311">The default is the current user.</span></span>

<span data-ttu-id="de4eb-312">**User01** や **domain01\user01」** などのユーザー名を入力する **User@Domain.Com** か、 `PSCredential` コマンドレットによって生成されたオブジェクトなどのオブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-312">Type a user name, such as **User01** or **Domain01\User01**, **User@Domain.Com**, or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="de4eb-313">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-313">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="de4eb-314">**Proxycredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-314">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="de4eb-315">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="de4eb-315">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="de4eb-316">コマンドレットが、 **プロキシ** パラメーターで指定されたプロキシサーバーにアクセスするために、現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-316">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="de4eb-317">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-317">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="de4eb-318">**Proxycredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-318">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="de4eb-319">-ResponseHeadersVariable</span><span class="sxs-lookup"><span data-stu-id="de4eb-319">-ResponseHeadersVariable</span></span>

<span data-ttu-id="de4eb-320">応答ヘッダーディクショナリを作成し、指定した変数の値に保存します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-320">Creates a Response Headers Dictionary and saves it in the value of the specified variable.</span></span> <span data-ttu-id="de4eb-321">ディクショナリのキーには、web サーバーから返された応答ヘッダーのフィールド名が含まれ、値はそれぞれのフィールド値になります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-321">The keys of the dictionary will contain the field names of the Response Header returned by the web server and the values will be the respective field values.</span></span>

<span data-ttu-id="de4eb-322">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-322">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-323">-再開</span><span class="sxs-lookup"><span data-stu-id="de4eb-323">-Resume</span></span>

<span data-ttu-id="de4eb-324">部分ファイルのダウンロードを再開するのに最適な試行を実行します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-324">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="de4eb-325">**Resume** パラメーター **には、出力パラメーターが** 必要です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-325">The **Resume** parameter requires the **OutFile** parameter.</span></span>

<span data-ttu-id="de4eb-326">**Resume** はローカルファイルとリモートファイルのサイズでのみ動作し、ローカルファイルとリモートファイルが同じであることを検証しません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-326">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="de4eb-327">ローカルファイルのサイズがリモートファイルのサイズよりも小さい場合、コマンドレットはファイルのダウンロードを再開し、残りのバイトをファイルの末尾に追加しようとします。</span><span class="sxs-lookup"><span data-stu-id="de4eb-327">If the local file size is smaller than the remote file size, then the cmdlet will attempt to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="de4eb-328">ローカルファイルのサイズがリモートファイルのサイズと同じ場合、アクションは実行されず、コマンドレットはダウンロードが既に完了しているものと想定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-328">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already completed.</span></span>

<span data-ttu-id="de4eb-329">ローカルファイルのサイズがリモートファイルのサイズよりも大きい場合、ローカルファイルは上書きされ、リモートファイル全体が完全に再ダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-329">If the local file size is larger than the remote file size, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="de4eb-330">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-330">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="de4eb-331">リモートサーバーがダウンロードの再開をサポートしていない場合、ローカルファイルは上書きされ、リモートファイル全体が完全に再ダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-331">If the remote server does not support download resuming, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="de4eb-332">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-332">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="de4eb-333">ローカルファイルが存在しない場合は、ローカルファイルが作成され、リモートファイル全体が完全にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-333">If the local file doesn't exist, then the local file will be created and the entire remote file will be completely downloaded.</span></span> <span data-ttu-id="de4eb-334">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-334">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="de4eb-335">この機能は、PowerShell 6.1.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-335">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="de4eb-336">-RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="de4eb-336">-RetryIntervalSec</span></span>

<span data-ttu-id="de4eb-337">400と 304 599 の間のエラーコードを受信したときの、接続の再試行の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-337">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="de4eb-338">再試行回数を指定するには、 **Maximumretrycount** パラメーターも参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4eb-338">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="de4eb-339">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="de4eb-339">-SessionVariable</span></span>

<span data-ttu-id="de4eb-340">このコマンドレットによって web 要求セッションが作成され、値に保存される変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-340">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="de4eb-341">ドル記号 () を付けずに変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-341">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="de4eb-342">セッション変数を指定すると、は `Invoke-RestMethod` web 要求セッションオブジェクトを作成し、PowerShell セッション内の指定された名前の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-342">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="de4eb-343">コマンドが完了すると、すぐに変数をセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-343">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="de4eb-344">リモートセッションとは異なり、web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-344">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="de4eb-345">これは、cookie、資格情報、リダイレクトの最大値、ユーザーエージェント文字列など、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-345">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="de4eb-346">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-346">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="de4eb-347">後続の Web 要求で Web 要求セッションを使用するには、**WebSession** パラメーターの値にセッション変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-347">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="de4eb-348">PowerShell は、新しい接続を確立するときに、web 要求セッションオブジェクトのデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-348">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="de4eb-349">Web 要求セッションの値をオーバーライドするには、**UserAgent**、**Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-349">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="de4eb-350">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-350">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="de4eb-351">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-351">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="de4eb-352">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="de4eb-352">-SkipCertificateCheck</span></span>

<span data-ttu-id="de4eb-353">有効期限、失効、信頼されたルート証明機関などのすべての検証を含む証明書検証チェックをスキップします。</span><span class="sxs-lookup"><span data-stu-id="de4eb-353">Skips certificate validation checks that include all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="de4eb-354">このパラメーターの使用はセキュリティで保護されていないため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-354">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="de4eb-355">このスイッチは、テスト目的で自己署名証明書を使用する既知のホストに対してのみ使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="de4eb-355">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="de4eb-356">ご自身の責任でをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="de4eb-356">Use at your own risk.</span></span>

<span data-ttu-id="de4eb-357">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-357">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-358">-SkipHeaderValidation</span><span class="sxs-lookup"><span data-stu-id="de4eb-358">-SkipHeaderValidation</span></span>

<span data-ttu-id="de4eb-359">コマンドレットが検証なしで要求にヘッダーを追加する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-359">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="de4eb-360">標準に準拠していないヘッダー値が必要なサイトには、このスイッチを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-360">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="de4eb-361">このスイッチを指定すると、値をオフにするための検証が無効になります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-361">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="de4eb-362">指定した場合、すべてのヘッダーが検証なしで追加されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-362">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="de4eb-363">これにより、 **ContentType**、 **Headers**、および **UserAgent** パラメーターに渡された値の検証が無効になります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-363">This will disable validation for values passed to the **ContentType**, **Headers**, and **UserAgent** parameters.</span></span>

<span data-ttu-id="de4eb-364">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-364">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="de4eb-365">-SkipHttpErrorCheck</span><span class="sxs-lookup"><span data-stu-id="de4eb-365">-SkipHttpErrorCheck</span></span>

<span data-ttu-id="de4eb-366">このパラメーターを指定すると、コマンドレットは HTTP エラー状態を無視し、応答の処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-366">This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses.</span></span>
<span data-ttu-id="de4eb-367">エラー応答は、成功したかのようにパイプラインに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-367">The error responses are written to the pipeline just as if they were successful.</span></span>

<span data-ttu-id="de4eb-368">このパラメーターは、PowerShell 7 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-368">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="de4eb-369">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="de4eb-369">-SslProtocol</span></span>

<span data-ttu-id="de4eb-370">Web 要求に対して許可されている SSL/TLS プロトコルを設定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-370">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="de4eb-371">既定では、システムでサポートされているすべての SSL/TLS プロトコルが許可されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-371">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="de4eb-372">**Sslprotocol** では、コンプライアンスのために特定のプロトコルを制限できます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-372">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="de4eb-373">**Sslprotocol** では、 `WebSslProtocol` フラグ列挙型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-373">**SslProtocol** uses the `WebSslProtocol` Flag Enum.</span></span> <span data-ttu-id="de4eb-374">フラグ表記を使用して複数のプロトコルを指定したり、複数のオプションをと組み合わせたりすることはでき `WebSslProtocol` `-bor` ますが、複数のプロトコルを指定することは、すべてのプラットフォームでサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-374">It is possible to supply more than one protocol using flag notation or combining multiple `WebSslProtocol` options with `-bor`, however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="de4eb-375">Windows 以外のプラットフォームで `Tls` は、 `Tls12` オプションとしてまたはを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-375">On non-Windows platforms it may not be possible to supply `Tls` or `Tls12` as an option.</span></span> <span data-ttu-id="de4eb-376">のサポート `Tls13` は、すべてのオペレーティングシステムで使用できるわけではなく、オペレーティングシステムごとに検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-376">Support for `Tls13` is not available on all operating systems and will need to be verified on a per operating system basis.</span></span>

<span data-ttu-id="de4eb-377">この機能は PowerShell 6.0.0 で追加され、 `Tls13` powershell 7.1 でがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-377">This feature was added in PowerShell 6.0.0 and support for `Tls13` was added in PowerShell 7.1.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12, Tls13

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de4eb-378">-StatusCodeVariable</span><span class="sxs-lookup"><span data-stu-id="de4eb-378">-StatusCodeVariable</span></span>

<span data-ttu-id="de4eb-379">このパラメーターは、ステータスコードの整数値が割り当てられている変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-379">This parameter specifies a variable that's assigned a status code's integer value.</span></span> <span data-ttu-id="de4eb-380">パラメーターでは、 **SkipHttpErrorCheck** パラメーターと共に使用すると、成功メッセージまたはエラーメッセージを識別できます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-380">The parameter can identify success messages or failure messages when used with the **SkipHttpErrorCheck** parameter.</span></span>

<span data-ttu-id="de4eb-381">パラメーターの変数名をなどの文字列として入力し `-StatusCodeVariable "scv"` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-381">Input the parameter's variable name as a string such as `-StatusCodeVariable "scv"`.</span></span>

<span data-ttu-id="de4eb-382">このパラメーターは、PowerShell 7 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-382">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="de4eb-383">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="de4eb-383">-TimeoutSec</span></span>

<span data-ttu-id="de4eb-384">要求がタイムアウトになるまでの待機時間を指定します。値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-384">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="de4eb-385">既定値は 0 で、無制限のタイムアウトを意味しています。</span><span class="sxs-lookup"><span data-stu-id="de4eb-385">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="de4eb-386">ドメインネームシステム (DNS) クエリは、返されるまで最大15秒かかることがあります。要求に解決を必要とするホスト名が含まれていて、 **Timeoutsec** を0より大きく15秒未満に設定した場合、WebException がスローされる前に15秒以上かかることがあり、要求はタイムアウトになります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-386">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="de4eb-387">-トークン</span><span class="sxs-lookup"><span data-stu-id="de4eb-387">-Token</span></span>

<span data-ttu-id="de4eb-388">要求に含める OAuth またはベアラートークン。</span><span class="sxs-lookup"><span data-stu-id="de4eb-388">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="de4eb-389">**トークン** は、特定の **認証** オプションに必要です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-389">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="de4eb-390">個別に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-390">It can't be used independently.</span></span>

<span data-ttu-id="de4eb-391">**トークンは** 、 `SecureString` トークンを含むを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-391">**Token** takes a `SecureString` that contains the token.</span></span> <span data-ttu-id="de4eb-392">トークンを指定するには、次のように手動で使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-392">To supply the token, manually use the following:</span></span>

`Invoke-RestMethod -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="de4eb-393">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-393">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="de4eb-394">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="de4eb-394">-TransferEncoding</span></span>

<span data-ttu-id="de4eb-395">転送エンコード HTTP 応答ヘッダーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-395">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="de4eb-396">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-396">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="de4eb-397">まとめ</span><span class="sxs-lookup"><span data-stu-id="de4eb-397">Chunked</span></span>
- <span data-ttu-id="de4eb-398">圧縮</span><span class="sxs-lookup"><span data-stu-id="de4eb-398">Compress</span></span>
- <span data-ttu-id="de4eb-399">Deflate</span><span class="sxs-lookup"><span data-stu-id="de4eb-399">Deflate</span></span>
- <span data-ttu-id="de4eb-400">GZip</span><span class="sxs-lookup"><span data-stu-id="de4eb-400">GZip</span></span>
- <span data-ttu-id="de4eb-401">ID</span><span class="sxs-lookup"><span data-stu-id="de4eb-401">Identity</span></span>

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

### <span data-ttu-id="de4eb-402">-Uri</span><span class="sxs-lookup"><span data-stu-id="de4eb-402">-Uri</span></span>

<span data-ttu-id="de4eb-403">Web 要求の送信先となるインターネットリソースの Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-403">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="de4eb-404">このパラメーターは、HTTP、HTTPS、FTP、FILE の値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="de4eb-404">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="de4eb-405">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-405">This parameter is required.</span></span> <span data-ttu-id="de4eb-406">パラメーター名 (**Uri**) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-406">The parameter name (**Uri**) is optional.</span></span>

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

### <span data-ttu-id="de4eb-407">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="de4eb-407">-UseBasicParsing</span></span>

<span data-ttu-id="de4eb-408">このパラメーターは非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="de4eb-408">This parameter has been deprecated.</span></span> <span data-ttu-id="de4eb-409">PowerShell 6.0.0 以降では、すべての Web 要求で基本的な解析のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-409">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="de4eb-410">このパラメーターは下位互換性のためだけに含まれています。このパラメーターを使用しても、コマンドレットの操作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-410">This parameter is included for backwards compatibility only and any use of it will have no effect on the operation of the cmdlet.</span></span>

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

### <span data-ttu-id="de4eb-411">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="de4eb-411">-UseDefaultCredentials</span></span>

<span data-ttu-id="de4eb-412">コマンドレットが、web 要求を送信するために現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-412">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="de4eb-413">**認証** または **資格情報** と共に使用することはできません。また、すべてのプラットフォームでサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-413">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

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

### <span data-ttu-id="de4eb-414">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="de4eb-414">-UserAgent</span></span>

<span data-ttu-id="de4eb-415">Web 要求のユーザー エージェント文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-415">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="de4eb-416">既定のユーザーエージェントは、 `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` オペレーティングシステムとプラットフォームによって微妙な違いがあるに似ています。</span><span class="sxs-lookup"><span data-stu-id="de4eb-416">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="de4eb-417">ほとんどのインターネットブラウザーで使用される標準のユーザーエージェント文字列を使用して web サイトをテストするには、Chrome、FireFox、InternetExplorer、Opera、Safari などの [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) クラスのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-417">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

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

### <span data-ttu-id="de4eb-418">-WebSession</span><span class="sxs-lookup"><span data-stu-id="de4eb-418">-WebSession</span></span>

<span data-ttu-id="de4eb-419">Web 要求セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-419">Specifies a web request session.</span></span> <span data-ttu-id="de4eb-420">ドル記号 () を含む変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-420">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="de4eb-421">Web 要求セッションの値をオーバーライドするには、**UserAgent**、**Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-421">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="de4eb-422">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-422">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="de4eb-423">`Content-Type`**本文** に **MultipartFormDataContent** オブジェクトが指定されている場合、などのコンテンツ関連ヘッダーもオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-423">Content related headers, such as `Content-Type`, will be also be overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

<span data-ttu-id="de4eb-424">リモートセッションとは異なり、web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-424">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="de4eb-425">これは、cookie、資格情報、リダイレクトの最大値、ユーザーエージェント文字列など、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-425">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="de4eb-426">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-426">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="de4eb-427">Web 要求セッションを作成するには、コマンドの **sessionvariable** パラメーターの値にドル記号を付けずに変数名を入力し `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-427">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="de4eb-428">`Invoke-RestMethod` セッションを作成し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-428">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="de4eb-429">後続のコマンドで、この変数を **WebSession** パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-429">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="de4eb-430">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de4eb-430">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="de4eb-431">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="de4eb-431">CommonParameters</span></span>

<span data-ttu-id="de4eb-432">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="de4eb-432">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de4eb-433">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de4eb-433">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de4eb-434">入力</span><span class="sxs-lookup"><span data-stu-id="de4eb-434">INPUTS</span></span>

### <span data-ttu-id="de4eb-435">System.Object</span><span class="sxs-lookup"><span data-stu-id="de4eb-435">System.Object</span></span>

<span data-ttu-id="de4eb-436">パイプを使用して、web 要求の本文をにパイプすることができ `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="de4eb-436">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="de4eb-437">出力</span><span class="sxs-lookup"><span data-stu-id="de4eb-437">OUTPUTS</span></span>

### <span data-ttu-id="de4eb-438">Int64、System.string、System.Xml.Xmlドキュメント</span><span class="sxs-lookup"><span data-stu-id="de4eb-438">System.Int64, System.String, System.Xml.XmlDocument</span></span>

<span data-ttu-id="de4eb-439">このコマンドレットの出力は、取得するコンテンツの書式によって異なります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-439">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="de4eb-440">PSObject</span><span class="sxs-lookup"><span data-stu-id="de4eb-440">PSObject</span></span>

<span data-ttu-id="de4eb-441">要求が JSON 文字列を返す場合、は `Invoke-RestMethod` 文字列を表す **PSObject** を返します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-441">If the request returns JSON strings, `Invoke-RestMethod` returns a **PSObject** that represents the strings.</span></span>

## <span data-ttu-id="de4eb-442">注</span><span class="sxs-lookup"><span data-stu-id="de4eb-442">NOTES</span></span>

<span data-ttu-id="de4eb-443">一部の機能は、一部のプラットフォームでは使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-443">Some features may not be available on all platforms.</span></span>

<span data-ttu-id="de4eb-444">.NET Core 3.1 の変更のため、PowerShell 7.0 以降では、 [Httpclient. defaultproxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) プロパティを使用してプロキシの構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-444">Because of changes in .NET Core 3.1, PowerShell 7.0 and higher use the [HttpClient.DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) Property to determine the proxy configuration.</span></span>

<span data-ttu-id="de4eb-445">このプロパティの値は、プラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-445">The value of this property is different rules depending on your platform:</span></span>

- <span data-ttu-id="de4eb-446">**Windows の場合**: 環境変数から、または定義されていない場合は、ユーザーのプロキシ設定からプロキシ構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-446">**For Windows**: Reads proxy configuration from environment variables or, if those are not defined, from the user's proxy settings.</span></span>
- <span data-ttu-id="de4eb-447">**MacOS の** 場合: 環境変数から、またはシステムのプロキシ設定からプロキシ構成が定義されていない場合は、その構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="de4eb-447">**For macOS**: Reads proxy configuration from environment variables or, if those are not defined, from the system's proxy settings.</span></span>
- <span data-ttu-id="de4eb-448">**Linux の場合**: 環境変数からプロキシ構成を読み取ります。これらが定義されていない場合、このプロパティは、すべてのアドレスをバイパスする構成されていないインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="de4eb-448">**For Linux**: Reads proxy configuration from environment variables or, in case those are not defined, this property initializes a non-configured instance that bypasses all addresses.</span></span>

<span data-ttu-id="de4eb-449">Windows および Unix ベースのプラットフォームでの初期化に使用される環境変数 `DefaultProxy` は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="de4eb-449">The environment variables used for `DefaultProxy` initialization on Windows and Unix-based platforms are:</span></span>

- <span data-ttu-id="de4eb-450">` HTTP_PROXY`: HTTP 要求で使用されるプロキシサーバーのホスト名または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="de4eb-450">` HTTP_PROXY`: the hostname or IP address of the proxy server used on HTTP requests.</span></span>
- <span data-ttu-id="de4eb-451">`HTTPS_PROXY`: HTTPS 要求で使用されるプロキシサーバーのホスト名または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="de4eb-451">`HTTPS_PROXY`: the hostname or IP address of the proxy server used on HTTPS requests.</span></span>
- <span data-ttu-id="de4eb-452">`ALL_PROXY`: HTTP および HTTPS 要求で使用されるプロキシサーバーのホスト名または IP アドレス `HTTP_PROXY` (またはが定義されて `HTTPS_PROXY` いない場合)。</span><span class="sxs-lookup"><span data-stu-id="de4eb-452">`ALL_PROXY`: the hostname or IP address of the proxy server used on HTTP and HTTPS requests in case `HTTP_PROXY` or `HTTPS_PROXY` are not defined.</span></span>
- <span data-ttu-id="de4eb-453">`NO_PROXY`: プロキシから除外する必要があるホスト名のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="de4eb-453">`NO_PROXY`: a comma-separated list of hostnames that should be excluded from proxying.</span></span>

## <span data-ttu-id="de4eb-454">関連リンク</span><span class="sxs-lookup"><span data-stu-id="de4eb-454">RELATED LINKS</span></span>

[<span data-ttu-id="de4eb-455">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="de4eb-455">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="de4eb-456">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="de4eb-456">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="de4eb-457">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="de4eb-457">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

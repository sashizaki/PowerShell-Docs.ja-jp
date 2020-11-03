---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: bb23f2ed01573a3f67c19f45db495cd86ecefe0c
ms.sourcegitcommit: 69b08b28ee2ef3168065672a23b9b6f0c578c95b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "93219867"
---
# <span data-ttu-id="76b98-103">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="76b98-103">Invoke-WebRequest</span></span>

## <span data-ttu-id="76b98-104">概要</span><span class="sxs-lookup"><span data-stu-id="76b98-104">SYNOPSIS</span></span>
<span data-ttu-id="76b98-105">インターネット上の web ページからコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="76b98-105">Gets content from a web page on the internet.</span></span>

## <span data-ttu-id="76b98-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="76b98-106">SYNTAX</span></span>

### <span data-ttu-id="76b98-107">StandardMethod (既定値)</span><span class="sxs-lookup"><span data-stu-id="76b98-107">StandardMethod (Default)</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Method <WebRequestMethod>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="76b98-108">StandardMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="76b98-108">StandardMethodNoProxy</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Method <WebRequestMethod>] -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck]
 [-PreserveAuthorizationOnRedirect] [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="76b98-109">CustomMethod</span><span class="sxs-lookup"><span data-stu-id="76b98-109">CustomMethod</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -CustomMethod <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="76b98-110">CustomMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="76b98-110">CustomMethodNoProxy</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -CustomMethod <String> -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck]
 [-PreserveAuthorizationOnRedirect] [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="76b98-111">Description</span><span class="sxs-lookup"><span data-stu-id="76b98-111">DESCRIPTION</span></span>

<span data-ttu-id="76b98-112">`Invoke-WebRequest`コマンドレットは、HTTP 要求と HTTPS 要求を web ページまたは web サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="76b98-112">The `Invoke-WebRequest` cmdlet sends HTTP and HTTPS requests to a web page or web service.</span></span> <span data-ttu-id="76b98-113">応答を解析し、リンク、画像、およびその他の重要な HTML 要素のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="76b98-113">It parses the response and returns collections of links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="76b98-114">このコマンドレットは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="76b98-115">PowerShell 7.0 以降では、は `Invoke-WebRequest` 環境変数によって定義されたプロキシ構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="76b98-115">Beginning in PowerShell 7.0, `Invoke-WebRequest` supports proxy configuration defined by environment variables.</span></span> <span data-ttu-id="76b98-116">この記事の「 [メモ](#notes) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b98-116">See the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="76b98-117">例</span><span class="sxs-lookup"><span data-stu-id="76b98-117">EXAMPLES</span></span>

### <span data-ttu-id="76b98-118">例 1: web 要求を送信する</span><span class="sxs-lookup"><span data-stu-id="76b98-118">Example 1: Send a web request</span></span>

<span data-ttu-id="76b98-119">この例では、コマンドレットを使用して、 `Invoke-WebRequest` Bing.com サイトに web 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="76b98-119">This example uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

```powershell
$Response = Invoke-WebRequest -URI https://www.bing.com/search?q=how+many+feet+in+a+mile
$Response.InputFields | Where-Object {
    $_.name -like "* Value*"
} | Select-Object Name, Value
```

```Output
name       value
----       -----
From Value 1
To Value   5280
```

<span data-ttu-id="76b98-120">最初のコマンドは、要求を発行し、その応答を変数に保存し `$Response` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-120">The first command issues the request and saves the response in the `$Response` variable.</span></span>

<span data-ttu-id="76b98-121">2番目のコマンドは、 **Name** プロパティがのような **inputfield** を取得し `"* Value"` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-121">The second command gets any **InputField** where the **Name** property is like `"* Value"`.</span></span> <span data-ttu-id="76b98-122">フィルター処理された結果は、 `Select-Object` **名前** と **値** のプロパティを選択するためにパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-122">The filtered results are piped to `Select-Object` to select the **Name** and **Value** properties.</span></span>

### <span data-ttu-id="76b98-123">例 2: ステートフルな web サービスを使用する</span><span class="sxs-lookup"><span data-stu-id="76b98-123">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="76b98-124">この例は、 `Invoke-WebRequest` コマンドレットをステートフル web サービスと共に使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="76b98-124">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service.</span></span>

```powershell
$Body = @{
    User = 'jdoe'
    password = 'P@S$w0rd!'
}
$LoginResponse = Invoke-WebRequest 'https://www.contoso.com/login/' -SessionVariable 'Session' -Body $Body -Method 'POST'

$Session

$ProfileResponse = Invoke-WebRequest 'https://www.contoso.com/profile/' -WebSession $Session

$ProfileResponse
```

<span data-ttu-id="76b98-125">への最初の呼び出しでは、 `Invoke-WebRequest` サインイン要求が送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-125">The first call to `Invoke-WebRequest` sends a sign-in request.</span></span> <span data-ttu-id="76b98-126">このコマンドは、 **-sessionvariable** パラメーターの値に "Session" という値を指定し、結果を変数に保存し `$LoginResponse` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-126">The command specifies a value of "Session" for the value of the **-SessionVariable** parameter, and saves the result in the `$LoginResponse` variable.</span></span> <span data-ttu-id="76b98-127">コマンドが完了すると、 `$LoginResponse` 変数にはが含まれ、 `BasicHtmlWebResponseObject` 変数には `$Session` オブジェクトが含まれ `WebRequestSession` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-127">When the command completes, the `$LoginResponse` variable contains an `BasicHtmlWebResponseObject` and the `$Session` variable contains a `WebRequestSession` object.</span></span> <span data-ttu-id="76b98-128">これにより、ユーザーがサイトに記録されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-128">This logs the user into the site.</span></span>

<span data-ttu-id="76b98-129">を呼び出す `$Session` ことによって、変数内のオブジェクトが表示され `WebRequestSession` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-129">The call to `$Session` by itself shows the `WebRequestSession` object in the variable.</span></span>

<span data-ttu-id="76b98-130">への2回目の呼び出しでは、ユーザーが `Invoke-WebRequest` サイトにログインする必要があるユーザーのプロファイルがフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-130">The second call to `Invoke-WebRequest` fetches the user's profile which requires that the user be logged into the site.</span></span> <span data-ttu-id="76b98-131">変数に格納されているセッションデータ `$Session` は、ログイン中に作成されたサイトにセッション cookie を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-131">The session data stored in the `$Session` variable is used to provide session cookies to the site created during the login.</span></span> <span data-ttu-id="76b98-132">結果は変数に保存され `$ProfileResponse` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-132">The result is saved in the `$ProfileResponse` variable.</span></span>

<span data-ttu-id="76b98-133">によるの呼び出しは、 `$ProfileResponse` 変数内のを表示し `BasicHtmlWebResponseObject` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-133">The call to `$ProfileResponse` by itself shows the `BasicHtmlWebResponseObject` in the variable.</span></span>

### <span data-ttu-id="76b98-134">例 3: web ページからリンクを取得する</span><span class="sxs-lookup"><span data-stu-id="76b98-134">Example 3: Get links from a web page</span></span>

<span data-ttu-id="76b98-135">この例では、web ページ内のリンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="76b98-135">This example gets the links in a web page.</span></span> <span data-ttu-id="76b98-136">コマンドレットを使用して、 `Invoke-WebRequest` web ページのコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="76b98-136">It uses the `Invoke-WebRequest` cmdlet to get the web page content.</span></span> <span data-ttu-id="76b98-137">次に、を返すの **Links** プロパティ `BasicHtmlWebResponseObject` `Invoke-WebRequest` と、各リンクの **Href** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-137">Then it uses the **Links** property of the `BasicHtmlWebResponseObject` that `Invoke-WebRequest` returns, and the **Href** property of each link.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs").Links.Href
```

### <span data-ttu-id="76b98-138">例 4: 要求されたページで定義されているエンコーディングを使用して、応答の内容をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="76b98-138">Example 4: Writes the response content to a file using the encoding defined in the requested page.</span></span>

<span data-ttu-id="76b98-139">この例では、コマンドレットを使用して、 `Invoke-WebRequest` PowerShell ドキュメントページの web ページの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="76b98-139">This example uses the `Invoke-WebRequest` cmdlet to retrieve the web page content of a PowerShell documentation page.</span></span>

```powershell
$Response = Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs"
$Stream = [System.IO.StreamWriter]::new('.\docspage.html', $false, $Response.Encoding)
try {
    $Stream.Write($Response.Content)
}
finally {
    $Stream.Dispose()
}
```

<span data-ttu-id="76b98-140">最初のコマンドは、ページを取得し、その応答オブジェクトを変数に保存し `$Response` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-140">The first command retrieves the page and saves the response object in the `$Response` variable.</span></span>

<span data-ttu-id="76b98-141">2番目のコマンドは、 `StreamWriter` 応答の内容をファイルに書き込むために使用するを作成します。</span><span class="sxs-lookup"><span data-stu-id="76b98-141">The second command creates a `StreamWriter` to use to write the response content to a file.</span></span> <span data-ttu-id="76b98-142">応答オブジェクトの **encoding** プロパティは、ファイルのエンコーディングを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-142">The **Encoding** property of the response object is used to set the encoding for the file.</span></span>

<span data-ttu-id="76b98-143">最後のいくつかのコマンドは、 **コンテンツ** プロパティをファイルに書き込んだ後、を破棄し `StreamWriter` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-143">The final few commands write the **Content** property to the file then disposes the `StreamWriter`.</span></span>

<span data-ttu-id="76b98-144">Web 要求がテキストコンテンツを返さない場合、 **Encoding** プロパティは null になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="76b98-144">Note that the **Encoding** property is null if the web request doesn't return text content.</span></span>

### <span data-ttu-id="76b98-145">例 5: マルチパート/フォームデータファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="76b98-145">Example 5: Submit a multipart/form-data file</span></span>

<span data-ttu-id="76b98-146">この例では、コマンドレットを使用し `Invoke-WebRequest` て、送信としてファイルをアップロードし `multipart/form-data` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-146">This example uses the `Invoke-WebRequest` cmdlet upload a file as a `multipart/form-data` submission.</span></span> <span data-ttu-id="76b98-147">ファイル `c:\document.txt` は、のを含むフォームフィールドとして送信され `document` `Content-Type` `text/plain` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-147">The file `c:\document.txt` is submitted as the form field `document` with the `Content-Type` of `text/plain`.</span></span>

```powershell
$FilePath = 'c:\document.txt'
$FieldName = 'document'
$ContentType = 'text/plain'

$FileStream = [System.IO.FileStream]::new($filePath, [System.IO.FileMode]::Open)
$FileHeader = [System.Net.Http.Headers.ContentDispositionHeaderValue]::new('form-data')
$FileHeader.Name = $FieldName
$FileHeader.FileName = Split-Path -leaf $FilePath
$FileContent = [System.Net.Http.StreamContent]::new($FileStream)
$FileContent.Headers.ContentDisposition = $FileHeader
$FileContent.Headers.ContentType = [System.Net.Http.Headers.MediaTypeHeaderValue]::Parse($ContentType)

$MultipartContent = [System.Net.Http.MultipartFormDataContent]::new()
$MultipartContent.Add($FileContent)

$Response = Invoke-WebRequest -Body $MultipartContent -Method 'POST' -Uri 'https://api.contoso.com/upload'
```

### <span data-ttu-id="76b98-148">例 6: 単純化されたマルチパート/フォーム-データ送信</span><span class="sxs-lookup"><span data-stu-id="76b98-148">Example 6: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="76b98-149">一部の Api `multipart/form-data` では、ファイルのアップロードと混合コンテンツの送信が必要です。</span><span class="sxs-lookup"><span data-stu-id="76b98-149">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="76b98-150">この例では、ユーザープロファイルの更新を示します。</span><span class="sxs-lookup"><span data-stu-id="76b98-150">This example demonstrates updating a user profile.</span></span>

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
$Result = Invoke-WebRequest -Uri $Uri -Method Post -Form $Form
```

<span data-ttu-id="76b98-151">プロファイルフォームには、、、 `firstName` 、、、 `lastName` `email` `avatar` `birthday` および `hobbies` の各フィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="76b98-151">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="76b98-152">API では、ユーザープロファイル pic をフィールドに指定するイメージが必要です `avatar` 。</span><span class="sxs-lookup"><span data-stu-id="76b98-152">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="76b98-153">この API は、 `hobbies` 同じ形式で複数のエントリを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="76b98-153">The API also accepts multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="76b98-154">`$Form`ハッシュテーブルを作成する場合、キー名はフォームフィールド名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-154">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="76b98-155">既定では、ハッシュテーブルの値は文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-155">By default, the values of the HashTable are converted to strings.</span></span> <span data-ttu-id="76b98-156">System.servicemodel の **値が** 存在する場合は、ファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-156">If a **System.IO.FileInfo** value is present, the file contents are submitted.</span></span> <span data-ttu-id="76b98-157">配列やリストなどのコレクションが存在する場合、フォームフィールドは複数回送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-157">If a collection such as arrays or lists are present, the form field is submitted multiple times.</span></span>

<span data-ttu-id="76b98-158">キーでを使用する `Get-Item` `avatar` と、 `FileInfo` オブジェクトが値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-158">By using `Get-Item` on the `avatar` key, the `FileInfo` object is set as the value.</span></span> <span data-ttu-id="76b98-159">その結果、のイメージデータが送信され `jdoe.png` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-159">The result is that the image data for `jdoe.png` is submitted.</span></span>

<span data-ttu-id="76b98-160">キーにリストを指定することによって、 `hobbies` `hobbies` フィールドはリスト項目ごとに1回送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-160">By supplying a list to the `hobbies` key, the `hobbies` field is present in the submissions once for each list item.</span></span>

### <span data-ttu-id="76b98-161">例 7: Invoke-WebRequest からの失敗したメッセージをキャッチする</span><span class="sxs-lookup"><span data-stu-id="76b98-161">Example 7: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="76b98-162">が `Invoke-WebRequest` 成功以外の HTTP メッセージ (404、500など) を検出すると、出力は返されず、終了エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="76b98-162">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="76b98-163">エラーをキャッチして **StatusCode** を表示するには、ブロックで実行を囲むことができ `try/catch` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-163">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span>

```powershell
try
{
    $Response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost" -ErrorAction Stop
    # This will only execute if the Invoke-WebRequest is successful.
    $StatusCode = $Response.StatusCode
}
catch
{
    $StatusCode = $_.Exception.Response.StatusCode.value__
}
$StatusCode
```

```Output
404
```

<span data-ttu-id="76b98-164">コマンドは `Invoke-WebRequest` **Stop** という **erroraction** を使用してを呼び出します。これにより、は、 `Invoke-WebRequest` 失敗した要求に対して強制的に終了エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="76b98-164">The command calls `Invoke-WebRequest` with an **ErrorAction** of **Stop** , which forces `Invoke-WebRequest` to throw a terminating error on any failed requests.</span></span> <span data-ttu-id="76b98-165">終了エラーは、 `catch` **例外** オブジェクトから **StatusCode** を取得するブロックによってキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-165">The terminating error is caught by the `catch` block which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="76b98-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="76b98-166">PARAMETERS</span></span>

### <span data-ttu-id="76b98-167">-AllowUnencryptedAuthentication</span><span class="sxs-lookup"><span data-stu-id="76b98-167">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="76b98-168">暗号化されていない接続を介した資格情報とシークレットの送信を許可します。</span><span class="sxs-lookup"><span data-stu-id="76b98-168">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="76b98-169">既定では、で開始されていない **Uri** を持つ **資格情報** または任意の **認証** オプションを指定 `https://` すると、エラーが発生し、要求は中止されます。これにより、暗号化されていない接続を介してプレーンテキストでシークレットが誤って通信されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="76b98-169">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` results in an error and the request is aborted to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="76b98-170">独自のリスクでこの動作をオーバーライドするには、 **Allowunencryptedauthentication** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-170">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="76b98-171">このパラメーターの使用はセキュリティで保護されていないため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="76b98-171">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="76b98-172">これは、暗号化された接続を提供できないレガシシステムとの互換性のためだけに用意されています。</span><span class="sxs-lookup"><span data-stu-id="76b98-172">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="76b98-173">ご自身の責任でをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="76b98-173">Use at your own risk.</span></span>

<span data-ttu-id="76b98-174">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-174">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="76b98-175">-認証</span><span class="sxs-lookup"><span data-stu-id="76b98-175">-Authentication</span></span>

<span data-ttu-id="76b98-176">要求に使用する明示的な認証の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-176">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="76b98-177">既定値は **[None]\(なし\)** です。</span><span class="sxs-lookup"><span data-stu-id="76b98-177">The default is **None**.</span></span>
<span data-ttu-id="76b98-178">**UseDefaultCredentials** で **認証** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-178">**Authentication** cannot be used with **UseDefaultCredentials**.</span></span>

<span data-ttu-id="76b98-179">使用可能な認証オプション:</span><span class="sxs-lookup"><span data-stu-id="76b98-179">Available Authentication Options:</span></span>

- <span data-ttu-id="76b98-180">**None** : **認証** が指定されていない場合の既定のオプションです。明示的な認証は使用されません。</span><span class="sxs-lookup"><span data-stu-id="76b98-180">**None** : This is the default option when **Authentication** isn't supplied; no explicit authentication is used.</span></span>
- <span data-ttu-id="76b98-181">**基本** : **資格情報** が必要です。</span><span class="sxs-lookup"><span data-stu-id="76b98-181">**Basic** : Requires **Credential**.</span></span> <span data-ttu-id="76b98-182">資格情報は、RFC 7617 の基本認証ヘッダーでという形式で送信され `base64(user:password)` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-182">The credentials are sent in an RFC 7617 Basic Authentication header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="76b98-183">**ベアラー** : **トークン** が必要です。</span><span class="sxs-lookup"><span data-stu-id="76b98-183">**Bearer** : Requires **Token**.</span></span> <span data-ttu-id="76b98-184">指定された `Authorization: Bearer` トークンを使用して RFC 6750 ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="76b98-184">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="76b98-185">これは **OAuth** のエイリアスです</span><span class="sxs-lookup"><span data-stu-id="76b98-185">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="76b98-186">**OAuth** : **トークン** が必要です。</span><span class="sxs-lookup"><span data-stu-id="76b98-186">**OAuth** : Requires **Token**.</span></span> <span data-ttu-id="76b98-187">指定された `Authorization: Bearer` トークンを使用して RFC 6750 ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="76b98-187">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="76b98-188">これは **ベアラー** のエイリアスです</span><span class="sxs-lookup"><span data-stu-id="76b98-188">This is an alias for **Bearer**</span></span>

<span data-ttu-id="76b98-189">**認証** `Authorization` を指定すると、 **ヘッダー** に指定されたヘッダーまたは **web セッション** に含まれるヘッダーが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-189">Supplying **Authentication** overrides any `Authorization` headers supplied to **Headers** or included in **WebSession**.</span></span>

<span data-ttu-id="76b98-190">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-190">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="76b98-191">-本文</span><span class="sxs-lookup"><span data-stu-id="76b98-191">-Body</span></span>

<span data-ttu-id="76b98-192">要求の本文を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-192">Specifies the body of the request.</span></span> <span data-ttu-id="76b98-193">本文は、ヘッダーに続く要求の内容です。</span><span class="sxs-lookup"><span data-stu-id="76b98-193">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="76b98-194">パイプを使用して、本文の値をにパイプすることもでき `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-194">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="76b98-195">**Body** パラメーターを使用すると、クエリ パラメーターのリストを指定したり、応答の内容を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="76b98-195">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="76b98-196">入力が GET 要求で、本文が `IDictionary` (通常はハッシュテーブル) の場合、本文はクエリパラメーターとして URI に追加されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-196">When the input is a GET request and the body is an `IDictionary` (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="76b98-197">他の要求の種類 (POST など) の場合、本文は標準形式の要求本文の値として設定され `name=value` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-197">For other request types (such as POST), the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="76b98-198">**Body** パラメーターは、オブジェクトを受け取ることもでき `System.Net.Http.MultipartFormDataContent` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-198">The **Body** parameter may also accept a `System.Net.Http.MultipartFormDataContent` object.</span></span> <span data-ttu-id="76b98-199">これにより、要求が容易に `multipart/form-data` なります。</span><span class="sxs-lookup"><span data-stu-id="76b98-199">This facilitates `multipart/form-data` requests.</span></span> <span data-ttu-id="76b98-200">**MultipartFormDataContent** オブジェクトが **Body** に指定されている場合、 **ContentType** 、 **headers** 、または **websession** パラメーターに指定されたコンテンツに関連するヘッダーは、 **MultipartFormDataContent** オブジェクトのコンテンツヘッダーによってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-200">When a **MultipartFormDataContent** object is supplied for **Body** , any Content related headers supplied to the **ContentType** , **Headers** , or **WebSession** parameters is overridden by the Content headers of the **MultipartFormDataContent** object.</span></span> <span data-ttu-id="76b98-201">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-201">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="76b98-202">-証明書</span><span class="sxs-lookup"><span data-stu-id="76b98-202">-Certificate</span></span>

<span data-ttu-id="76b98-203">セキュリティで保護された web 要求に使用されるクライアント証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-203">Specifies the client certificate that's used for a secure web request.</span></span> <span data-ttu-id="76b98-204">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="76b98-204">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="76b98-205">証明書を検索するには、を使用する `Get-PfxCertificate` か、 `Get-ChildItem` 証明書 () ドライブのコマンドレットを使用し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-205">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="76b98-206">証明書が有効でないか、十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="76b98-206">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="76b98-207">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="76b98-207">-CertificateThumbprint</span></span>

<span data-ttu-id="76b98-208">要求を送信するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-208">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="76b98-209">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="76b98-209">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="76b98-210">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-210">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="76b98-211">ローカルユーザーアカウントにのみマップできます。ドメインアカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="76b98-211">They can be mapped only to local user accounts; they don't work with domain accounts.</span></span>

<span data-ttu-id="76b98-212">証明書の拇印を取得するに `Get-Item` は、PowerShell ドライブでまたはコマンドを使用し `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-212">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="76b98-213">この機能は現在、Windows OS プラットフォームでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="76b98-213">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="76b98-214">-ContentType</span><span class="sxs-lookup"><span data-stu-id="76b98-214">-ContentType</span></span>

<span data-ttu-id="76b98-215">Web 要求のコンテンツ タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-215">Specifies the content type of the web request.</span></span>

<span data-ttu-id="76b98-216">このパラメーターを省略して、要求メソッドが POST の場合は、 `Invoke-WebRequest` コンテンツの種類をに設定し `application/x-www-form-urlencoded` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-216">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="76b98-217">それ以外の場合は、の呼び出しでコンテンツの種類が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="76b98-217">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="76b98-218">**MultipartFormDataContent** オブジェクトが **本文** に指定されている場合、 **ContentType** はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-218">**ContentType** is overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="76b98-219">-Credential</span><span class="sxs-lookup"><span data-stu-id="76b98-219">-Credential</span></span>

<span data-ttu-id="76b98-220">要求を送信するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-220">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="76b98-221">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="76b98-221">The default is the current user.</span></span>

<span data-ttu-id="76b98-222">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-222">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="76b98-223">**資格情報** は、単独で使用することも、特定の **認証** パラメーターオプションと組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="76b98-223">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="76b98-224">リモートサーバーが認証チャレンジ要求を送信した場合にのみ、リモートサーバーに資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="76b98-224">When used alone, it only supplies credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="76b98-225">**認証** オプションと共に使用すると、資格情報が明示的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-225">When used with **Authentication** options, the credentials are explicitly sent.</span></span>

<span data-ttu-id="76b98-226">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-226">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="76b98-227">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b98-227">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="76b98-228">-CustomMethod</span><span class="sxs-lookup"><span data-stu-id="76b98-228">-CustomMethod</span></span>

<span data-ttu-id="76b98-229">Web 要求に使用するカスタムメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-229">Specifies a custom method used for the web request.</span></span> <span data-ttu-id="76b98-230">これは、エンドポイントに必要な要求メソッドが、 **メソッド** で使用可能なオプションではない場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="76b98-230">This can be used if the Request Method required by the endpoint isn't an available option on the **Method**.</span></span> <span data-ttu-id="76b98-231">**メソッド** と **custommethod** を一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-231">**Method** and **CustomMethod** can't be used together.</span></span>

<span data-ttu-id="76b98-232">この例では `TEST` 、API に対して HTTP 要求を行います。</span><span class="sxs-lookup"><span data-stu-id="76b98-232">This example makes a `TEST` HTTP request to the API:</span></span>

`Invoke-WebRequest -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="76b98-233">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-233">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CustomMethod, CustomMethodNoProxy
Aliases: CM

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76b98-234">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="76b98-234">-DisableKeepAlive</span></span>

<span data-ttu-id="76b98-235">コマンドレットが HTTP ヘッダーの **KeepAlive** 値を **False** に設定することを示します。</span><span class="sxs-lookup"><span data-stu-id="76b98-235">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False**.</span></span> <span data-ttu-id="76b98-236">既定では、 **KeepAlive** は **True** です。</span><span class="sxs-lookup"><span data-stu-id="76b98-236">By default, **KeepAlive** is **True**.</span></span> <span data-ttu-id="76b98-237">**KeepAlive** は、後続の要求を容易にするために、サーバーへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="76b98-237">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="76b98-238">-フォーム</span><span class="sxs-lookup"><span data-stu-id="76b98-238">-Form</span></span>

<span data-ttu-id="76b98-239">辞書を送信に変換 `multipart/form-data` します。</span><span class="sxs-lookup"><span data-stu-id="76b98-239">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="76b98-240">**フォーム** を **本文** と共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-240">**Form** may not be used with **Body**.</span></span>
<span data-ttu-id="76b98-241">**ContentType** が使用されている場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-241">If **ContentType** is used, it's ignored.</span></span>

<span data-ttu-id="76b98-242">ディクショナリのキーは、フォームフィールド名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-242">The keys of the dictionary are used as the form field names.</span></span> <span data-ttu-id="76b98-243">既定では、フォーム値は文字列値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-243">By default, form values are converted to string values.</span></span>

<span data-ttu-id="76b98-244">値が **system.servicemodel オブジェクトの** 場合は、バイナリファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-244">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="76b98-245">ファイル名は **filename** プロパティとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-245">The name of the file is submitted as the **filename** property.</span></span> <span data-ttu-id="76b98-246">MIME の種類はとして設定され `application/octet-stream` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-246">The MIME type is set as `application/octet-stream`.</span></span> <span data-ttu-id="76b98-247">`Get-Item` を使用 **すると、system.object オブジェクト** を簡単に指定できます。</span><span class="sxs-lookup"><span data-stu-id="76b98-247">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="76b98-248">値がコレクション型 (配列やリストなど) の場合、for フィールドは複数回送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-248">If the value is a collection type, such Arrays or Lists, the for field are submitted multiple times.</span></span>
<span data-ttu-id="76b98-249">既定では、リストの値は文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="76b98-249">The values of the list are treated as strings by default.</span></span> <span data-ttu-id="76b98-250">値が **system.servicemodel オブジェクトの** 場合は、バイナリファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-250">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="76b98-251">入れ子になったコレクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="76b98-251">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="76b98-252">上の例では `tags` 、フィールドは、、、およびの各につき1回、フォームに3回指定されてい `Vacation` `Italy` `2017` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-252">In the above example the `tags` field are supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="76b98-253">また、フィールドは、 `pictures` フォルダー内のファイルごとに1回送信され `2017-Italy` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-253">The `pictures` field is also submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="76b98-254">そのフォルダー内のファイルのバイナリコンテンツは、値として送信されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-254">The binary contents of the files in that folder are submitted as the values.</span></span>

<span data-ttu-id="76b98-255">この機能は、PowerShell 6.1.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-255">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="76b98-256">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="76b98-256">-Headers</span></span>

<span data-ttu-id="76b98-257">Web 要求のヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-257">Specifies the headers of the web request.</span></span> <span data-ttu-id="76b98-258">ハッシュ テーブルまたは辞書を入力します。</span><span class="sxs-lookup"><span data-stu-id="76b98-258">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="76b98-259">UserAgent ヘッダーを設定するには、 **UserAgent** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-259">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="76b98-260">このパラメーターを使用して **、ユーザーエージェント** または cookie のヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-260">You can't use this parameter to specify **User-Agent** or cookie headers.</span></span>

<span data-ttu-id="76b98-261">などのコンテンツ関連ヘッダー `Content-Type` は、 **MultipartFormDataContent** オブジェクトが **本文** に指定されたときにオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-261">Content related headers, such as `Content-Type` is overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="76b98-262">-InFile</span><span class="sxs-lookup"><span data-stu-id="76b98-262">-InFile</span></span>

<span data-ttu-id="76b98-263">ファイルから Web 要求の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="76b98-263">Gets the content of the web request from a file.</span></span> <span data-ttu-id="76b98-264">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="76b98-264">Enter a path and file name.</span></span> <span data-ttu-id="76b98-265">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="76b98-265">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="76b98-266">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="76b98-266">-MaximumRedirection</span></span>

<span data-ttu-id="76b98-267">接続に失敗する前に PowerShell が代替 Uniform Resource Identifier (URI) に接続をリダイレクトする回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-267">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="76b98-268">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="76b98-268">The default value is 5.</span></span> <span data-ttu-id="76b98-269">値 0 (ゼロ) を指定した場合、リダイレクトはまったく行われません。</span><span class="sxs-lookup"><span data-stu-id="76b98-269">A value of 0 (zero) prevents all redirection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76b98-270">-MaximumRetryCount</span><span class="sxs-lookup"><span data-stu-id="76b98-270">-MaximumRetryCount</span></span>

<span data-ttu-id="76b98-271">400と599の間のエラーコード (包括的または 304) を受信したときに PowerShell が接続を再試行する回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-271">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="76b98-272">再試行回数を指定する場合は、 **Retryintervalsec** パラメーターも参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b98-272">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="76b98-273">-メソッド</span><span class="sxs-lookup"><span data-stu-id="76b98-273">-Method</span></span>

<span data-ttu-id="76b98-274">Web 要求に使用するメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-274">Specifies the method used for the web request.</span></span> <span data-ttu-id="76b98-275">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76b98-275">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="76b98-276">Default</span><span class="sxs-lookup"><span data-stu-id="76b98-276">Default</span></span>
- <span data-ttu-id="76b98-277">削除</span><span class="sxs-lookup"><span data-stu-id="76b98-277">Delete</span></span>
- <span data-ttu-id="76b98-278">取得</span><span class="sxs-lookup"><span data-stu-id="76b98-278">Get</span></span>
- <span data-ttu-id="76b98-279">Head</span><span class="sxs-lookup"><span data-stu-id="76b98-279">Head</span></span>
- <span data-ttu-id="76b98-280">Merge</span><span class="sxs-lookup"><span data-stu-id="76b98-280">Merge</span></span>
- <span data-ttu-id="76b98-281">オプション</span><span class="sxs-lookup"><span data-stu-id="76b98-281">Options</span></span>
- <span data-ttu-id="76b98-282">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="76b98-282">Patch</span></span>
- <span data-ttu-id="76b98-283">投稿</span><span class="sxs-lookup"><span data-stu-id="76b98-283">Post</span></span>
- <span data-ttu-id="76b98-284">Put</span><span class="sxs-lookup"><span data-stu-id="76b98-284">Put</span></span>
- <span data-ttu-id="76b98-285">Trace</span><span class="sxs-lookup"><span data-stu-id="76b98-285">Trace</span></span>

<span data-ttu-id="76b98-286">**Custommethod** パラメーターは、上に一覧表示されていない要求メソッドに使用できます。</span><span class="sxs-lookup"><span data-stu-id="76b98-286">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

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

### <span data-ttu-id="76b98-287">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="76b98-287">-NoProxy</span></span>

<span data-ttu-id="76b98-288">コマンドレットが送信先に接続するためにプロキシを使用しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="76b98-288">Indicates that the cmdlet shouldn't use a proxy to reach the destination.</span></span> <span data-ttu-id="76b98-289">環境で構成されているプロキシをバイパスする必要がある場合は、このスイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-289">When you need to bypass the proxy configured in the environment, use this switch.</span></span> <span data-ttu-id="76b98-290">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-290">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="76b98-291">-出力</span><span class="sxs-lookup"><span data-stu-id="76b98-291">-OutFile</span></span>

<span data-ttu-id="76b98-292">このコマンドレットが応答本文を保存する出力ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-292">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="76b98-293">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="76b98-293">Enter a path and file name.</span></span>
<span data-ttu-id="76b98-294">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="76b98-294">If you omit the path, the default is the current location.</span></span> <span data-ttu-id="76b98-295">名前はリテラルパスとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="76b98-295">The name is treated as a literal path.</span></span>
<span data-ttu-id="76b98-296">角かっこ () を含む名前 `[]` は、単一引用符 () で囲む必要があり `'` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-296">Names that contain brackets (`[]`) must be enclosed in single quotes (`'`).</span></span>

<span data-ttu-id="76b98-297">既定では、は `Invoke-WebRequest` パイプラインに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="76b98-297">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="76b98-298">結果をファイルとパイプラインに送信するには、 **Passthru** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-298">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="76b98-299">-PassThru</span><span class="sxs-lookup"><span data-stu-id="76b98-299">-PassThru</span></span>

<span data-ttu-id="76b98-300">コマンドレットがファイルに書き込むだけでなく、結果を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="76b98-300">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="76b98-301">このパラメーターは、同時に **OutFile** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="76b98-301">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="76b98-302">-PreserveAuthorizationOnRedirect</span><span class="sxs-lookup"><span data-stu-id="76b98-302">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="76b98-303">コマンドレットで、リダイレクト全体でヘッダーを保持する必要があることを示し `Authorization` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-303">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="76b98-304">既定では、コマンドレットは、 `Authorization` リダイレクトの前にヘッダーを除去します。</span><span class="sxs-lookup"><span data-stu-id="76b98-304">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="76b98-305">このパラメーターを指定すると、ヘッダーがリダイレクト場所に送信される必要がある場合に、このロジックが無効になります。</span><span class="sxs-lookup"><span data-stu-id="76b98-305">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="76b98-306">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-306">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="76b98-307">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="76b98-307">-Proxy</span></span>

<span data-ttu-id="76b98-308">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-308">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>
<span data-ttu-id="76b98-309">ネットワーク プロキシ サーバーの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="76b98-309">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="76b98-310">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="76b98-310">-ProxyCredential</span></span>

<span data-ttu-id="76b98-311">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-311">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="76b98-312">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="76b98-312">The default is the current user.</span></span>

<span data-ttu-id="76b98-313">**User01** や **domain01\user01」** などのユーザー名を入力する **User@Domain.Com** か、 `PSCredential` コマンドレットによって生成されたオブジェクトなどのオブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-313">Type a user name, such as **User01** or **Domain01\User01** , **User@Domain.Com** , or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="76b98-314">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="76b98-314">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="76b98-315">**Proxycredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-315">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76b98-316">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="76b98-316">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="76b98-317">コマンドレットが、 **プロキシ** パラメーターで指定されたプロキシサーバーにアクセスするために、現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="76b98-317">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="76b98-318">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="76b98-318">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="76b98-319">**Proxycredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-319">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="76b98-320">-再開</span><span class="sxs-lookup"><span data-stu-id="76b98-320">-Resume</span></span>

<span data-ttu-id="76b98-321">部分ファイルのダウンロードを再開するのに最適な試行を実行します。</span><span class="sxs-lookup"><span data-stu-id="76b98-321">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="76b98-322">**再開** に **は、出力** 出力が必要です。</span><span class="sxs-lookup"><span data-stu-id="76b98-322">**Resume** requires **OutFile**.</span></span>

<span data-ttu-id="76b98-323">**Resume** はローカルファイルとリモートファイルのサイズでのみ動作し、ローカルファイルとリモートファイルが同じであることを検証しません。</span><span class="sxs-lookup"><span data-stu-id="76b98-323">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="76b98-324">ローカルファイルのサイズがリモートファイルのサイズよりも小さい場合、コマンドレットはファイルのダウンロードを再開し、残りのバイトをファイルの末尾に追加しようとします。</span><span class="sxs-lookup"><span data-stu-id="76b98-324">If the local file size is smaller than the remote file size, then the cmdlet attempts to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="76b98-325">ローカルファイルのサイズがリモートファイルのサイズと同じ場合、アクションは実行されず、コマンドレットはダウンロードが既に完了していると想定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-325">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already complete.</span></span>

<span data-ttu-id="76b98-326">ローカルファイルのサイズがリモートファイルのサイズより大きい場合は、ローカルファイルが上書きされ、リモートファイル全体が再ダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-326">If the local file size is larger than the remote file size, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="76b98-327">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="76b98-327">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="76b98-328">リモートサーバーがダウンロードの再開をサポートしていない場合は、ローカルファイルが上書きされ、リモートファイル全体が再ダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-328">If the remote server does not support download resuming, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="76b98-329">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="76b98-329">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="76b98-330">ローカルファイルが存在しない場合は、ローカルファイルが作成され、リモートファイル全体がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-330">If the local file does not exist, then the local file is created and the entire remote file is downloaded.</span></span> <span data-ttu-id="76b98-331">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="76b98-331">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="76b98-332">この機能は、PowerShell 6.1.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-332">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="76b98-333">-RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="76b98-333">-RetryIntervalSec</span></span>

<span data-ttu-id="76b98-334">400と 304 599 の間のエラーコードを受信したときの、接続の再試行の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-334">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="76b98-335">再試行回数を指定するには、 **Maximumretrycount** パラメーターも参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b98-335">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="76b98-336">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="76b98-336">-SessionVariable</span></span>

<span data-ttu-id="76b98-337">このコマンドレットによって web 要求セッションが作成され、値に保存される変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-337">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="76b98-338">ドル記号 () を付けずに変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-338">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="76b98-339">セッション変数を指定すると、は `Invoke-WebRequest` web 要求セッションオブジェクトを作成し、PowerShell セッション内の指定された名前の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="76b98-339">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="76b98-340">コマンドが完了すると、すぐに変数をセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="76b98-340">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="76b98-341">リモート セッションとは異なり、Web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="76b98-341">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="76b98-342">これは、cookie、資格情報、リダイレクトの最大値、ユーザーエージェント文字列など、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="76b98-342">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="76b98-343">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="76b98-343">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="76b98-344">後続の Web 要求で Web 要求セッションを使用するには、 **WebSession** パラメーターの値にセッション変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-344">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="76b98-345">PowerShell は、新しい接続を確立するときに、web 要求セッションオブジェクトのデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-345">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="76b98-346">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-346">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="76b98-347">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-347">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="76b98-348">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-348">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="76b98-349">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="76b98-349">-SkipCertificateCheck</span></span>

<span data-ttu-id="76b98-350">証明書の検証チェックをスキップします。</span><span class="sxs-lookup"><span data-stu-id="76b98-350">Skips certificate validation checks.</span></span> <span data-ttu-id="76b98-351">これには、有効期限、失効、信頼されたルート証明機関などのすべての検証が含まれます。</span><span class="sxs-lookup"><span data-stu-id="76b98-351">This includes all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="76b98-352">このパラメーターの使用はセキュリティで保護されていないため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="76b98-352">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="76b98-353">このスイッチは、テスト目的で自己署名証明書を使用する既知のホストに対してのみ使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="76b98-353">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="76b98-354">ご自身の責任でをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="76b98-354">Use at your own risk.</span></span>

<span data-ttu-id="76b98-355">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-355">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="76b98-356">-SkipHeaderValidation</span><span class="sxs-lookup"><span data-stu-id="76b98-356">-SkipHeaderValidation</span></span>

<span data-ttu-id="76b98-357">コマンドレットが検証なしで要求にヘッダーを追加する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="76b98-357">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="76b98-358">標準に準拠していないヘッダー値が必要なサイトには、このスイッチを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76b98-358">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="76b98-359">このスイッチを指定すると、値をオフにするための検証が無効になります。</span><span class="sxs-lookup"><span data-stu-id="76b98-359">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="76b98-360">指定した場合、すべてのヘッダーが検証なしで追加されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-360">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="76b98-361">このスイッチは、 **ContentType** 、 **Headers** 、および **UserAgent** パラメーターに渡される値の検証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="76b98-361">This switch disables validation for values passed to the **ContentType** , **Headers** and **UserAgent** parameters.</span></span>

<span data-ttu-id="76b98-362">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-362">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="76b98-363">-SkipHttpErrorCheck</span><span class="sxs-lookup"><span data-stu-id="76b98-363">-SkipHttpErrorCheck</span></span>

<span data-ttu-id="76b98-364">このパラメーターを指定すると、コマンドレットは HTTP エラー状態を無視し、応答の処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="76b98-364">This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses.</span></span>
<span data-ttu-id="76b98-365">エラー応答は、成功したかのようにパイプラインに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="76b98-365">The error responses are written to the pipeline just as if they were successful.</span></span>

<span data-ttu-id="76b98-366">このパラメーターは、PowerShell 7 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-366">This parameter was introduced in PowerShell 7.</span></span>

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

### <span data-ttu-id="76b98-367">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="76b98-367">-SslProtocol</span></span>

<span data-ttu-id="76b98-368">Web 要求に対して許可されている SSL/TLS プロトコルを設定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-368">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="76b98-369">既定では、システムでサポートされているすべての SSL/TLS プロトコルが許可されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-369">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="76b98-370">**Sslprotocol** では、コンプライアンスのために特定のプロトコルを制限できます。</span><span class="sxs-lookup"><span data-stu-id="76b98-370">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="76b98-371">**Sslprotocol** では **websslprotocol** フラグ列挙型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-371">**SslProtocol** uses the **WebSslProtocol** Flag Enum.</span></span> <span data-ttu-id="76b98-372">フラグ表記を使用して複数のプロトコルを指定したり、複数の **Websslprotocol** オプションを **bor** と組み合わせたりすることはできますが、複数のプロトコルを指定することは、すべてのプラットフォームでサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="76b98-372">It is possible to supply more than one protocol using flag notation or combining multiple **WebSslProtocol** options with **bor** , however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="76b98-373">Windows 以外のプラットフォームで `Tls` は、 `Tls12` オプションとしてまたはを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-373">On non-Windows platforms it may not be possible to supply `Tls` or `Tls12` as an option.</span></span> <span data-ttu-id="76b98-374">のサポート `Tls13` は、すべてのオペレーティングシステムで使用できるわけではなく、オペレーティングシステムごとに検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76b98-374">Support for `Tls13` is not available on all operating systems and will need to be verified on a per operating system basis.</span></span>

<span data-ttu-id="76b98-375">この機能は PowerShell 6.0.0 で追加され、 `Tls13` powershell 7.1 でがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="76b98-375">This feature was added in PowerShell 6.0.0 and support for `Tls13` was added in PowerShell 7.1.</span></span>

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

### <span data-ttu-id="76b98-376">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="76b98-376">-TimeoutSec</span></span>

<span data-ttu-id="76b98-377">要求がタイムアウトになるまでの待機時間を指定します。値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="76b98-377">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="76b98-378">既定値は 0 で、無制限のタイムアウトを意味しています。</span><span class="sxs-lookup"><span data-stu-id="76b98-378">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="76b98-379">ドメインネームシステム (DNS) クエリは、返されるまで最大15秒かかることがあります。要求に解決を必要とするホスト名が含まれていて、 **Timeoutsec** を0より大きく15秒未満に設定した場合、WebException がスローされる前に15秒以上かかることがあり、要求はタイムアウトになります。</span><span class="sxs-lookup"><span data-stu-id="76b98-379">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76b98-380">-トークン</span><span class="sxs-lookup"><span data-stu-id="76b98-380">-Token</span></span>

<span data-ttu-id="76b98-381">要求に含める OAuth またはベアラートークン。</span><span class="sxs-lookup"><span data-stu-id="76b98-381">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="76b98-382">**トークン** は、特定の **認証** オプションに必要です。</span><span class="sxs-lookup"><span data-stu-id="76b98-382">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="76b98-383">個別に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-383">It cannot be used independently.</span></span>

<span data-ttu-id="76b98-384">**トークン** は、 `SecureString` トークンを含むを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="76b98-384">**Token** takes a `SecureString` containing the token.</span></span> <span data-ttu-id="76b98-385">トークンを手動で指定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="76b98-385">To supply the token manually use the following:</span></span>

`Invoke-WebRequest -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="76b98-386">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="76b98-386">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="76b98-387">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="76b98-387">-TransferEncoding</span></span>

<span data-ttu-id="76b98-388">転送エンコード HTTP 応答ヘッダーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-388">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="76b98-389">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76b98-389">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="76b98-390">まとめ</span><span class="sxs-lookup"><span data-stu-id="76b98-390">Chunked</span></span>
- <span data-ttu-id="76b98-391">圧縮</span><span class="sxs-lookup"><span data-stu-id="76b98-391">Compress</span></span>
- <span data-ttu-id="76b98-392">Deflate</span><span class="sxs-lookup"><span data-stu-id="76b98-392">Deflate</span></span>
- <span data-ttu-id="76b98-393">GZip</span><span class="sxs-lookup"><span data-stu-id="76b98-393">GZip</span></span>
- <span data-ttu-id="76b98-394">ID</span><span class="sxs-lookup"><span data-stu-id="76b98-394">Identity</span></span>

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

### <span data-ttu-id="76b98-395">-Uri</span><span class="sxs-lookup"><span data-stu-id="76b98-395">-Uri</span></span>

<span data-ttu-id="76b98-396">Web 要求の送信先となるインターネットリソースの Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-396">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="76b98-397">URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="76b98-397">Enter a URI.</span></span> <span data-ttu-id="76b98-398">このパラメーターは、HTTP または HTTPS のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="76b98-398">This parameter supports HTTP or HTTPS only.</span></span>

<span data-ttu-id="76b98-399">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="76b98-399">This parameter is required.</span></span> <span data-ttu-id="76b98-400">パラメーター名 **Uri** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="76b98-400">The parameter name **Uri** is optional.</span></span>

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

### <span data-ttu-id="76b98-401">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="76b98-401">-UseBasicParsing</span></span>

<span data-ttu-id="76b98-402">このパラメーターは非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="76b98-402">This parameter has been deprecated.</span></span> <span data-ttu-id="76b98-403">PowerShell 6.0.0 以降では、すべての Web 要求で基本的な解析のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-403">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="76b98-404">このパラメーターは下位互換性のためだけに含まれています。このパラメーターを使用しても、コマンドレットの操作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="76b98-404">This parameter is included for backwards compatibility only and any use of it has no effect on the operation of the cmdlet.</span></span>

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

### <span data-ttu-id="76b98-405">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="76b98-405">-UseDefaultCredentials</span></span>

<span data-ttu-id="76b98-406">コマンドレットが、web 要求を送信するために現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="76b98-406">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="76b98-407">**認証** または **資格情報** と共に使用することはできません。また、すべてのプラットフォームでサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76b98-407">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

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

### <span data-ttu-id="76b98-408">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="76b98-408">-UserAgent</span></span>

<span data-ttu-id="76b98-409">Web 要求のユーザー エージェント文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-409">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="76b98-410">既定のユーザーエージェントは、 `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` オペレーティングシステムとプラットフォームによって微妙な違いがあるに似ています。</span><span class="sxs-lookup"><span data-stu-id="76b98-410">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="76b98-411">ほとんどのインターネットブラウザーで使用される標準のユーザーエージェント文字列を使用して web サイトをテストするには、Chrome、FireFox、InternetExplorer、Opera、Safari などの [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) クラスのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-411">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

<span data-ttu-id="76b98-412">たとえば、次のコマンドは、Internet Explorer のユーザーエージェント文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-412">For example, the following command uses the user agent string for Internet Explorer:</span></span>

```powershell
Invoke-WebRequest -Uri https://website.com/ -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer)
```

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

### <span data-ttu-id="76b98-413">-WebSession</span><span class="sxs-lookup"><span data-stu-id="76b98-413">-WebSession</span></span>

<span data-ttu-id="76b98-414">Web 要求セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-414">Specifies a web request session.</span></span> <span data-ttu-id="76b98-415">ドル記号 () を含む変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-415">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="76b98-416">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-416">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="76b98-417">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="76b98-417">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="76b98-418">`Content-Type`**本文** に **MultipartFormDataContent** オブジェクトが指定されている場合、などのコンテンツ関連ヘッダーもオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-418">Content related headers, such as `Content-Type`, are also be overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

<span data-ttu-id="76b98-419">リモートセッションとは異なり、web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="76b98-419">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="76b98-420">これは、cookie、資格情報、リダイレクトの最大値、ユーザーエージェント文字列など、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="76b98-420">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="76b98-421">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="76b98-421">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="76b98-422">Web 要求セッションを作成するには、コマンドの **sessionvariable** パラメーターの値にドル記号を付けずに変数名を入力し `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-422">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="76b98-423">`Invoke-WebRequest` セッションを作成し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="76b98-423">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="76b98-424">後続のコマンドで、この変数を **WebSession** パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="76b98-424">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="76b98-425">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="76b98-425">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="76b98-426">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="76b98-426">CommonParameters</span></span>

<span data-ttu-id="76b98-427">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="76b98-427">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="76b98-428">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b98-428">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="76b98-429">入力</span><span class="sxs-lookup"><span data-stu-id="76b98-429">INPUTS</span></span>

### <span data-ttu-id="76b98-430">System.Object</span><span class="sxs-lookup"><span data-stu-id="76b98-430">System.Object</span></span>

<span data-ttu-id="76b98-431">パイプを使用して、web 要求の本文をにパイプすることができ `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="76b98-431">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="76b98-432">出力</span><span class="sxs-lookup"><span data-stu-id="76b98-432">OUTPUTS</span></span>

### <span data-ttu-id="76b98-433">Microsoft. PowerShell. BasicHtmlWebResponseObject</span><span class="sxs-lookup"><span data-stu-id="76b98-433">Microsoft.PowerShell.Commands.BasicHtmlWebResponseObject</span></span>

## <span data-ttu-id="76b98-434">注</span><span class="sxs-lookup"><span data-stu-id="76b98-434">NOTES</span></span>

<span data-ttu-id="76b98-435">PowerShell 6.0.0 以降で `Invoke-WebRequest` は、基本的な解析のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="76b98-435">Beginning with PowerShell 6.0.0 `Invoke-WebRequest` supports basic parsing only.</span></span>

<span data-ttu-id="76b98-436">詳細については、「 [Basichtmlwebresponseobject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b98-436">For more information, see [BasicHtmlWebResponseObject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).</span></span>

<span data-ttu-id="76b98-437">.NET Core 3.1 の変更のため、PowerShell 7.0 以降では、 [Httpclient. defaultproxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) プロパティを使用してプロキシの構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="76b98-437">Because of changes in .NET Core 3.1, PowerShell 7.0 and higher use the [HttpClient.DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) Property to determine the proxy configuration.</span></span>

<span data-ttu-id="76b98-438">このプロパティの値は、プラットフォームによって決まります。</span><span class="sxs-lookup"><span data-stu-id="76b98-438">The value of this property is determined by your platform:</span></span>

- <span data-ttu-id="76b98-439">**Windows の場合** : 環境変数からプロキシ構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="76b98-439">**For Windows** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="76b98-440">これらの変数が定義されていない場合、プロパティはユーザーのプロキシ設定から派生します。</span><span class="sxs-lookup"><span data-stu-id="76b98-440">If those variables are not defined the property is derived from the user's proxy settings.</span></span>
- <span data-ttu-id="76b98-441">**MacOS の場合** : 環境変数からプロキシ構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="76b98-441">**For macOS** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="76b98-442">これらの変数が定義されていない場合、プロパティはシステムのプロキシ設定から派生します。</span><span class="sxs-lookup"><span data-stu-id="76b98-442">If those variables are not defined the property is derived from the system's proxy settings.</span></span>
- <span data-ttu-id="76b98-443">**Linux の場合** : 環境変数からプロキシ構成を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="76b98-443">**For Linux** : Reads proxy configuration from environment variables.</span></span> <span data-ttu-id="76b98-444">これらの変数が定義されていない場合、プロパティは、すべてのアドレスをバイパスするように構成されていないインスタンスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="76b98-444">If those variables are not defined the property initializes a non-configured instance that bypasses all addresses.</span></span>

<span data-ttu-id="76b98-445">Windows および Unix ベースのプラットフォームでの初期化に使用される環境変数 `DefaultProxy` は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76b98-445">The environment variables used for `DefaultProxy` initialization on Windows and Unix-based platforms are:</span></span>

- <span data-ttu-id="76b98-446">` HTTP_PROXY`: HTTP 要求で使用されるプロキシサーバーのホスト名または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="76b98-446">` HTTP_PROXY`: the hostname or IP address of the proxy server used on HTTP requests.</span></span>
- <span data-ttu-id="76b98-447">`HTTPS_PROXY`: HTTPS 要求で使用されるプロキシサーバーのホスト名または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="76b98-447">`HTTPS_PROXY`: the hostname or IP address of the proxy server used on HTTPS requests.</span></span>
- <span data-ttu-id="76b98-448">`ALL_PROXY`: HTTP および HTTPS 要求で使用されるプロキシサーバーのホスト名または IP アドレス `HTTP_PROXY` (またはが定義されて `HTTPS_PROXY` いない場合)。</span><span class="sxs-lookup"><span data-stu-id="76b98-448">`ALL_PROXY`: the hostname or IP address of the proxy server used on HTTP and HTTPS requests in case `HTTP_PROXY` or `HTTPS_PROXY` are not defined.</span></span>
- <span data-ttu-id="76b98-449">`NO_PROXY`: プロキシから除外する必要があるホスト名のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="76b98-449">`NO_PROXY`: a comma-separated list of hostnames that should be excluded from proxying.</span></span>

## <span data-ttu-id="76b98-450">関連リンク</span><span class="sxs-lookup"><span data-stu-id="76b98-450">RELATED LINKS</span></span>

[<span data-ttu-id="76b98-451">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="76b98-451">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="76b98-452">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="76b98-452">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="76b98-453">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="76b98-453">ConvertTo-Json</span></span>](ConvertTo-Json.md)
---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 09270fd74fd256858faacaae399e05b40985ddb5
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219432"
---
# <span data-ttu-id="65714-103">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="65714-103">Invoke-WebRequest</span></span>

## <span data-ttu-id="65714-104">概要</span><span class="sxs-lookup"><span data-stu-id="65714-104">SYNOPSIS</span></span>
<span data-ttu-id="65714-105">インターネット上の web ページからコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="65714-105">Gets content from a web page on the internet.</span></span>

## <span data-ttu-id="65714-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65714-106">SYNTAX</span></span>

### <span data-ttu-id="65714-107">StandardMethod (既定値)</span><span class="sxs-lookup"><span data-stu-id="65714-107">StandardMethod (Default)</span></span>

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
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="65714-108">StandardMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="65714-108">StandardMethodNoProxy</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Method <WebRequestMethod>] -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="65714-109">CustomMethod</span><span class="sxs-lookup"><span data-stu-id="65714-109">CustomMethod</span></span>

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
 [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="65714-110">CustomMethodNoProxy</span><span class="sxs-lookup"><span data-stu-id="65714-110">CustomMethodNoProxy</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>]
 [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -CustomMethod <String> -NoProxy
 [-Body <Object>] [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>]
 [-InFile <String>] [-OutFile <String>] [-PassThru] [-Resume] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="65714-111">Description</span><span class="sxs-lookup"><span data-stu-id="65714-111">DESCRIPTION</span></span>

<span data-ttu-id="65714-112">`Invoke-WebRequest`コマンドレットは、HTTP 要求と HTTPS 要求を web ページまたは web サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="65714-112">The `Invoke-WebRequest` cmdlet sends HTTP and HTTPS requests to a web page or web service.</span></span> <span data-ttu-id="65714-113">応答を解析し、リンク、画像、およびその他の重要な HTML 要素のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="65714-113">It parses the response and returns collections of links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="65714-114">このコマンドレットは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="65714-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="65714-115">例</span><span class="sxs-lookup"><span data-stu-id="65714-115">EXAMPLES</span></span>

### <span data-ttu-id="65714-116">例 1: web 要求を送信する</span><span class="sxs-lookup"><span data-stu-id="65714-116">Example 1: Send a web request</span></span>

<span data-ttu-id="65714-117">この例では、コマンドレットを使用して、 `Invoke-WebRequest` Bing.com サイトに web 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="65714-117">This example uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

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

<span data-ttu-id="65714-118">最初のコマンドは、要求を発行し、その応答を変数に保存し `$Response` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-118">The first command issues the request and saves the response in the `$Response` variable.</span></span>

<span data-ttu-id="65714-119">2番目のコマンドは、 **Name** プロパティがのような **inputfield** を取得し `"* Value"` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-119">The second command gets any **InputField** where the **Name** property is like `"* Value"`.</span></span> <span data-ttu-id="65714-120">フィルター処理された結果は、 `Select-Object` **名前** と **値** のプロパティを選択するためにパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="65714-120">The filtered results are piped to `Select-Object` to select the **Name** and **Value** properties.</span></span>

### <span data-ttu-id="65714-121">例 2: ステートフルな web サービスを使用する</span><span class="sxs-lookup"><span data-stu-id="65714-121">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="65714-122">この例は、 `Invoke-WebRequest` コマンドレットをステートフル web サービスと共に使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="65714-122">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service.</span></span>

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

<span data-ttu-id="65714-123">への最初の呼び出しでは、 `Invoke-WebRequest` サインイン要求が送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-123">The first call to `Invoke-WebRequest` sends a sign-in request.</span></span> <span data-ttu-id="65714-124">このコマンドは、 **-sessionvariable** パラメーターの値に "Session" という値を指定し、結果を変数に保存し `$LoginResponse` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-124">The command specifies a value of "Session" for the value of the **-SessionVariable** parameter, and saves the result in the `$LoginResponse` variable.</span></span> <span data-ttu-id="65714-125">コマンドが完了すると、 `$LoginResponse` 変数にはが含まれ、 `BasicHtmlWebResponseObject` 変数には `$Session` オブジェクトが含まれ `WebRequestSession` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-125">When the command completes, the `$LoginResponse` variable contains an `BasicHtmlWebResponseObject` and the `$Session` variable contains a `WebRequestSession` object.</span></span> <span data-ttu-id="65714-126">これにより、ユーザーがサイトに記録されます。</span><span class="sxs-lookup"><span data-stu-id="65714-126">This logs the user into the site.</span></span>

<span data-ttu-id="65714-127">を呼び出す `$Session` ことによって、変数内のオブジェクトが表示され `WebRequestSession` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-127">The call to `$Session` by itself shows the `WebRequestSession` object in the variable.</span></span>

<span data-ttu-id="65714-128">への2回目の呼び出しでは、ユーザーが `Invoke-WebRequest` サイトにログインする必要があるユーザーのプロファイルがフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="65714-128">The second call to `Invoke-WebRequest` fetches the user's profile which requires that the user be logged into the site.</span></span> <span data-ttu-id="65714-129">変数に格納されているセッションデータ `$Session` は、ログイン中に作成されたサイトにセッション cookie を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="65714-129">The session data stored in the `$Session` variable is used to provide session cookies to the site created during the login.</span></span> <span data-ttu-id="65714-130">結果は変数に保存され `$ProfileResponse` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-130">The result is saved in the `$ProfileResponse` variable.</span></span>

<span data-ttu-id="65714-131">によるの呼び出しは、 `$ProfileResponse` 変数内のを表示し `BasicHtmlWebResponseObject` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-131">The call to `$ProfileResponse` by itself shows the `BasicHtmlWebResponseObject` in the variable.</span></span>

### <span data-ttu-id="65714-132">例 3: web ページからリンクを取得する</span><span class="sxs-lookup"><span data-stu-id="65714-132">Example 3: Get links from a web page</span></span>

<span data-ttu-id="65714-133">この例では、web ページ内のリンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="65714-133">This example gets the links in a web page.</span></span> <span data-ttu-id="65714-134">コマンドレットを使用して、 `Invoke-WebRequest` web ページのコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="65714-134">It uses the `Invoke-WebRequest` cmdlet to get the web page content.</span></span> <span data-ttu-id="65714-135">次に、を返すの **Links** プロパティ `BasicHtmlWebResponseObject` `Invoke-WebRequest` と、各リンクの **Href** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-135">Then it uses the **Links** property of the `BasicHtmlWebResponseObject` that `Invoke-WebRequest` returns, and the **Href** property of each link.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://aka.ms/pscore6-docs").Links.Href
```

### <span data-ttu-id="65714-136">例 4: 要求されたページで定義されているエンコーディングを使用して、応答の内容をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="65714-136">Example 4: Writes the response content to a file using the encoding defined in the requested page.</span></span>

<span data-ttu-id="65714-137">この例では、コマンドレットを使用して、 `Invoke-WebRequest` PowerShell ドキュメントページの web ページの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="65714-137">This example uses the `Invoke-WebRequest` cmdlet to retrieve the web page content of a PowerShell documentation page.</span></span>

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

<span data-ttu-id="65714-138">最初のコマンドは、ページを取得し、その応答オブジェクトを変数に保存し `$Response` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-138">The first command retrieves the page and saves the response object in the `$Response` variable.</span></span>

<span data-ttu-id="65714-139">2番目のコマンドは、 `StreamWriter` 応答の内容をファイルに書き込むために使用するを作成します。</span><span class="sxs-lookup"><span data-stu-id="65714-139">The second command creates a `StreamWriter` to use to write the response content to a file.</span></span> <span data-ttu-id="65714-140">応答オブジェクトの **encoding** プロパティは、ファイルのエンコーディングを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="65714-140">The **Encoding** property of the response object is used to set the encoding for the file.</span></span>

<span data-ttu-id="65714-141">最後のいくつかのコマンドは、 **コンテンツ** プロパティをファイルに書き込んだ後、を破棄し `StreamWriter` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-141">The final few commands write the **Content** property to the file then disposes the `StreamWriter`.</span></span>

<span data-ttu-id="65714-142">Web 要求がテキストコンテンツを返さない場合、 **Encoding** プロパティは null になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="65714-142">Note that the **Encoding** property is null if the web request doesn't return text content.</span></span>

### <span data-ttu-id="65714-143">例 5: マルチパート/フォームデータファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="65714-143">Example 5: Submit a multipart/form-data file</span></span>

<span data-ttu-id="65714-144">この例では、コマンドレットを使用し `Invoke-WebRequest` て、送信としてファイルをアップロードし `multipart/form-data` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-144">This example uses the `Invoke-WebRequest` cmdlet upload a file as a `multipart/form-data` submission.</span></span> <span data-ttu-id="65714-145">ファイル `c:\document.txt` は、のを含むフォームフィールドとして送信され `document` `Content-Type` `text/plain` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-145">The file `c:\document.txt` is submitted as the form field `document` with the `Content-Type` of `text/plain`.</span></span>

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

### <span data-ttu-id="65714-146">例 6: 単純化されたマルチパート/フォーム-データ送信</span><span class="sxs-lookup"><span data-stu-id="65714-146">Example 6: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="65714-147">一部の Api `multipart/form-data` では、ファイルのアップロードと混合コンテンツの送信が必要です。</span><span class="sxs-lookup"><span data-stu-id="65714-147">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="65714-148">この例では、ユーザープロファイルの更新を示します。</span><span class="sxs-lookup"><span data-stu-id="65714-148">This example demonstrates updating a user profile.</span></span>

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

<span data-ttu-id="65714-149">プロファイルフォームには、、、 `firstName` 、、、 `lastName` `email` `avatar` `birthday` および `hobbies` の各フィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="65714-149">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="65714-150">API では、ユーザープロファイル pic をフィールドに指定するイメージが必要です `avatar` 。</span><span class="sxs-lookup"><span data-stu-id="65714-150">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="65714-151">この API は、 `hobbies` 同じ形式で複数のエントリを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="65714-151">The API also accepts multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="65714-152">`$Form`ハッシュテーブルを作成する場合、キー名はフォームフィールド名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="65714-152">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="65714-153">既定では、ハッシュテーブルの値は文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="65714-153">By default, the values of the HashTable are converted to strings.</span></span> <span data-ttu-id="65714-154">System.servicemodel の **値が** 存在する場合は、ファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-154">If a **System.IO.FileInfo** value is present, the file contents are submitted.</span></span> <span data-ttu-id="65714-155">配列やリストなどのコレクションが存在する場合、フォームフィールドは複数回送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-155">If a collection such as arrays or lists are present, the form field is submitted multiple times.</span></span>

<span data-ttu-id="65714-156">キーでを使用する `Get-Item` `avatar` と、 `FileInfo` オブジェクトが値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="65714-156">By using `Get-Item` on the `avatar` key, the `FileInfo` object is set as the value.</span></span> <span data-ttu-id="65714-157">その結果、のイメージデータが送信され `jdoe.png` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-157">The result is that the image data for `jdoe.png` is submitted.</span></span>

<span data-ttu-id="65714-158">キーにリストを指定することによって、 `hobbies` `hobbies` フィールドはリスト項目ごとに1回送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-158">By supplying a list to the `hobbies` key, the `hobbies` field is present in the submissions once for each list item.</span></span>

### <span data-ttu-id="65714-159">例 7: Invoke-WebRequest からの失敗したメッセージをキャッチする</span><span class="sxs-lookup"><span data-stu-id="65714-159">Example 7: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="65714-160">が `Invoke-WebRequest` 成功以外の HTTP メッセージ (404、500など) を検出すると、出力は返されず、終了エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="65714-160">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="65714-161">エラーをキャッチして **StatusCode** を表示するには、ブロックで実行を囲むことができ `try/catch` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-161">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span>

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

<span data-ttu-id="65714-162">コマンドは `Invoke-WebRequest` **Stop** という **erroraction** を使用してを呼び出します。これにより、は、 `Invoke-WebRequest` 失敗した要求に対して強制的に終了エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="65714-162">The command calls `Invoke-WebRequest` with an **ErrorAction** of **Stop** , which forces `Invoke-WebRequest` to throw a terminating error on any failed requests.</span></span> <span data-ttu-id="65714-163">終了エラーは、 `catch` **例外** オブジェクトから **StatusCode** を取得するブロックによってキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="65714-163">The terminating error is caught by the `catch` block which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="65714-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65714-164">PARAMETERS</span></span>

### <span data-ttu-id="65714-165">-AllowUnencryptedAuthentication</span><span class="sxs-lookup"><span data-stu-id="65714-165">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="65714-166">暗号化されていない接続を介した資格情報とシークレットの送信を許可します。</span><span class="sxs-lookup"><span data-stu-id="65714-166">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="65714-167">既定では、で開始されていない **Uri** を持つ **資格情報** または任意の **認証** オプションを指定 `https://` すると、エラーが発生し、要求は中止されます。これにより、暗号化されていない接続を介してプレーンテキストでシークレットが誤って通信されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="65714-167">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` results in an error and the request is aborted to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="65714-168">独自のリスクでこの動作をオーバーライドするには、 **Allowunencryptedauthentication** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-168">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="65714-169">このパラメーターの使用はセキュリティで保護されていないため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="65714-169">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="65714-170">これは、暗号化された接続を提供できないレガシシステムとの互換性のためだけに用意されています。</span><span class="sxs-lookup"><span data-stu-id="65714-170">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="65714-171">ご自身の責任でをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="65714-171">Use at your own risk.</span></span>

<span data-ttu-id="65714-172">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-172">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="65714-173">-認証</span><span class="sxs-lookup"><span data-stu-id="65714-173">-Authentication</span></span>

<span data-ttu-id="65714-174">要求に使用する明示的な認証の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-174">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="65714-175">既定値は **[None]\(なし\)** です。</span><span class="sxs-lookup"><span data-stu-id="65714-175">The default is **None**.</span></span>
<span data-ttu-id="65714-176">**UseDefaultCredentials** で **認証** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-176">**Authentication** cannot be used with **UseDefaultCredentials**.</span></span>

<span data-ttu-id="65714-177">使用可能な認証オプション:</span><span class="sxs-lookup"><span data-stu-id="65714-177">Available Authentication Options:</span></span>

- <span data-ttu-id="65714-178">**None** : **認証** が指定されていない場合の既定のオプションです。明示的な認証は使用されません。</span><span class="sxs-lookup"><span data-stu-id="65714-178">**None** : This is the default option when **Authentication** isn't supplied; no explicit authentication is used.</span></span>
- <span data-ttu-id="65714-179">**基本** : **資格情報** が必要です。</span><span class="sxs-lookup"><span data-stu-id="65714-179">**Basic** : Requires **Credential**.</span></span> <span data-ttu-id="65714-180">資格情報は、RFC 7617 の基本認証ヘッダーでという形式で送信され `base64(user:password)` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-180">The credentials are sent in an RFC 7617 Basic Authentication header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="65714-181">**ベアラー** : **トークン** が必要です。</span><span class="sxs-lookup"><span data-stu-id="65714-181">**Bearer** : Requires **Token**.</span></span> <span data-ttu-id="65714-182">指定された `Authorization: Bearer` トークンを使用して RFC 6750 ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="65714-182">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="65714-183">これは **OAuth** のエイリアスです</span><span class="sxs-lookup"><span data-stu-id="65714-183">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="65714-184">**OAuth** : **トークン** が必要です。</span><span class="sxs-lookup"><span data-stu-id="65714-184">**OAuth** : Requires **Token**.</span></span> <span data-ttu-id="65714-185">指定された `Authorization: Bearer` トークンを使用して RFC 6750 ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="65714-185">Sends an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="65714-186">これは **ベアラー** のエイリアスです</span><span class="sxs-lookup"><span data-stu-id="65714-186">This is an alias for **Bearer**</span></span>

<span data-ttu-id="65714-187">**認証** `Authorization` を指定すると、 **ヘッダー** に指定されたヘッダーまたは **web セッション** に含まれるヘッダーが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="65714-187">Supplying **Authentication** overrides any `Authorization` headers supplied to **Headers** or included in **WebSession**.</span></span>

<span data-ttu-id="65714-188">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-188">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="65714-189">-本文</span><span class="sxs-lookup"><span data-stu-id="65714-189">-Body</span></span>

<span data-ttu-id="65714-190">要求の本文を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-190">Specifies the body of the request.</span></span> <span data-ttu-id="65714-191">本文は、ヘッダーに続く要求の内容です。</span><span class="sxs-lookup"><span data-stu-id="65714-191">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="65714-192">パイプを使用して、本文の値をにパイプすることもでき `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-192">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="65714-193">**Body** パラメーターを使用すると、クエリ パラメーターのリストを指定したり、応答の内容を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="65714-193">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="65714-194">入力が GET 要求で、本文が `IDictionary` (通常はハッシュテーブル) の場合、本文はクエリパラメーターとして URI に追加されます。</span><span class="sxs-lookup"><span data-stu-id="65714-194">When the input is a GET request and the body is an `IDictionary` (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="65714-195">他の要求の種類 (POST など) の場合、本文は標準形式の要求本文の値として設定され `name=value` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-195">For other request types (such as POST), the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="65714-196">**Body** パラメーターは、オブジェクトを受け取ることもでき `System.Net.Http.MultipartFormDataContent` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-196">The **Body** parameter may also accept a `System.Net.Http.MultipartFormDataContent` object.</span></span> <span data-ttu-id="65714-197">これにより、要求が容易に `multipart/form-data` なります。</span><span class="sxs-lookup"><span data-stu-id="65714-197">This facilitates `multipart/form-data` requests.</span></span> <span data-ttu-id="65714-198">**MultipartFormDataContent** オブジェクトが **Body** に指定されている場合、 **ContentType** 、 **headers** 、または **websession** パラメーターに指定されたコンテンツに関連するヘッダーは、 **MultipartFormDataContent** オブジェクトのコンテンツヘッダーによってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="65714-198">When a **MultipartFormDataContent** object is supplied for **Body** , any Content related headers supplied to the **ContentType** , **Headers** , or **WebSession** parameters is overridden by the Content headers of the **MultipartFormDataContent** object.</span></span> <span data-ttu-id="65714-199">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-199">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="65714-200">-証明書</span><span class="sxs-lookup"><span data-stu-id="65714-200">-Certificate</span></span>

<span data-ttu-id="65714-201">セキュリティで保護された web 要求に使用されるクライアント証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-201">Specifies the client certificate that's used for a secure web request.</span></span> <span data-ttu-id="65714-202">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="65714-202">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="65714-203">証明書を検索するには、を使用する `Get-PfxCertificate` か、 `Get-ChildItem` 証明書 () ドライブのコマンドレットを使用し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-203">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="65714-204">証明書が有効でないか、十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="65714-204">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="65714-205">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="65714-205">-CertificateThumbprint</span></span>

<span data-ttu-id="65714-206">要求を送信するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-206">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="65714-207">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="65714-207">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="65714-208">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="65714-208">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="65714-209">ローカルユーザーアカウントにのみマップできます。ドメインアカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="65714-209">They can be mapped only to local user accounts; they don't work with domain accounts.</span></span>

<span data-ttu-id="65714-210">証明書の拇印を取得するに `Get-Item` は、PowerShell ドライブでまたはコマンドを使用し `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-210">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="65714-211">この機能は現在、Windows OS プラットフォームでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="65714-211">This feature is currently only supported on Windows OS platforms.</span></span>

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

### <span data-ttu-id="65714-212">-ContentType</span><span class="sxs-lookup"><span data-stu-id="65714-212">-ContentType</span></span>

<span data-ttu-id="65714-213">Web 要求のコンテンツ タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-213">Specifies the content type of the web request.</span></span>

<span data-ttu-id="65714-214">このパラメーターを省略して、要求メソッドが POST の場合は、 `Invoke-WebRequest` コンテンツの種類をに設定し `application/x-www-form-urlencoded` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-214">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="65714-215">それ以外の場合は、の呼び出しでコンテンツの種類が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="65714-215">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="65714-216">**MultipartFormDataContent** オブジェクトが **本文** に指定されている場合、 **ContentType** はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="65714-216">**ContentType** is overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="65714-217">-Credential</span><span class="sxs-lookup"><span data-stu-id="65714-217">-Credential</span></span>

<span data-ttu-id="65714-218">要求を送信するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-218">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="65714-219">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="65714-219">The default is the current user.</span></span>

<span data-ttu-id="65714-220">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-220">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="65714-221">**資格情報** は、単独で使用することも、特定の **認証** パラメーターオプションと組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="65714-221">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="65714-222">リモートサーバーが認証チャレンジ要求を送信した場合にのみ、リモートサーバーに資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="65714-222">When used alone, it only supplies credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="65714-223">**認証** オプションと共に使用すると、資格情報が明示的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-223">When used with **Authentication** options, the credentials are explicitly sent.</span></span>

<span data-ttu-id="65714-224">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="65714-224">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="65714-225">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65714-225">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="65714-226">-CustomMethod</span><span class="sxs-lookup"><span data-stu-id="65714-226">-CustomMethod</span></span>

<span data-ttu-id="65714-227">Web 要求に使用するカスタムメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-227">Specifies a custom method used for the web request.</span></span> <span data-ttu-id="65714-228">これは、エンドポイントに必要な要求メソッドが、 **メソッド** で使用可能なオプションではない場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="65714-228">This can be used if the Request Method required by the endpoint isn't an available option on the **Method**.</span></span> <span data-ttu-id="65714-229">**メソッド** と **custommethod** を一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-229">**Method** and **CustomMethod** can't be used together.</span></span>

<span data-ttu-id="65714-230">この例では `TEST` 、API に対して HTTP 要求を行います。</span><span class="sxs-lookup"><span data-stu-id="65714-230">This example makes a `TEST` HTTP request to the API:</span></span>

`Invoke-WebRequest -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="65714-231">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-231">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="65714-232">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="65714-232">-DisableKeepAlive</span></span>

<span data-ttu-id="65714-233">コマンドレットが HTTP ヘッダーの **KeepAlive** 値を **False** に設定することを示します。</span><span class="sxs-lookup"><span data-stu-id="65714-233">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False**.</span></span> <span data-ttu-id="65714-234">既定では、 **KeepAlive** は **True** です。</span><span class="sxs-lookup"><span data-stu-id="65714-234">By default, **KeepAlive** is **True**.</span></span> <span data-ttu-id="65714-235">**KeepAlive** は、後続の要求を容易にするために、サーバーへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="65714-235">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="65714-236">-フォーム</span><span class="sxs-lookup"><span data-stu-id="65714-236">-Form</span></span>

<span data-ttu-id="65714-237">辞書を送信に変換 `multipart/form-data` します。</span><span class="sxs-lookup"><span data-stu-id="65714-237">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="65714-238">**フォーム** を **本文** と共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-238">**Form** may not be used with **Body**.</span></span>
<span data-ttu-id="65714-239">**ContentType** が使用されている場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="65714-239">If **ContentType** is used, it's ignored.</span></span>

<span data-ttu-id="65714-240">ディクショナリのキーは、フォームフィールド名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="65714-240">The keys of the dictionary are used as the form field names.</span></span> <span data-ttu-id="65714-241">既定では、フォーム値は文字列値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="65714-241">By default, form values are converted to string values.</span></span>

<span data-ttu-id="65714-242">値が **system.servicemodel オブジェクトの** 場合は、バイナリファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-242">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="65714-243">ファイル名は **filename** プロパティとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-243">The name of the file is submitted as the **filename** property.</span></span> <span data-ttu-id="65714-244">MIME の種類はとして設定され `application/octet-stream` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-244">The MIME type is set as `application/octet-stream`.</span></span> <span data-ttu-id="65714-245">`Get-Item` を使用 **すると、system.object オブジェクト** を簡単に指定できます。</span><span class="sxs-lookup"><span data-stu-id="65714-245">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="65714-246">値がコレクション型 (配列やリストなど) の場合、for フィールドは複数回送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-246">If the value is a collection type, such Arrays or Lists, the for field are submitted multiple times.</span></span>
<span data-ttu-id="65714-247">既定では、リストの値は文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="65714-247">The values of the list are treated as strings by default.</span></span> <span data-ttu-id="65714-248">値が **system.servicemodel オブジェクトの** 場合は、バイナリファイルの内容が送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-248">If the value is a **System.IO.FileInfo** object, then the binary file contents are submitted.</span></span> <span data-ttu-id="65714-249">入れ子になったコレクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65714-249">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="65714-250">上の例では `tags` 、フィールドは、、、およびの各につき1回、フォームに3回指定されてい `Vacation` `Italy` `2017` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-250">In the above example the `tags` field are supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="65714-251">また、フィールドは、 `pictures` フォルダー内のファイルごとに1回送信され `2017-Italy` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-251">The `pictures` field is also submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="65714-252">そのフォルダー内のファイルのバイナリコンテンツは、値として送信されます。</span><span class="sxs-lookup"><span data-stu-id="65714-252">The binary contents of the files in that folder are submitted as the values.</span></span>

<span data-ttu-id="65714-253">この機能は、PowerShell 6.1.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-253">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="65714-254">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="65714-254">-Headers</span></span>

<span data-ttu-id="65714-255">Web 要求のヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-255">Specifies the headers of the web request.</span></span> <span data-ttu-id="65714-256">ハッシュ テーブルまたは辞書を入力します。</span><span class="sxs-lookup"><span data-stu-id="65714-256">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="65714-257">UserAgent ヘッダーを設定するには、 **UserAgent** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-257">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="65714-258">このパラメーターを使用して **、ユーザーエージェント** または cookie のヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-258">You can't use this parameter to specify **User-Agent** or cookie headers.</span></span>

<span data-ttu-id="65714-259">などのコンテンツ関連ヘッダー `Content-Type` は、 **MultipartFormDataContent** オブジェクトが **本文** に指定されたときにオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="65714-259">Content related headers, such as `Content-Type` is overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

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

### <span data-ttu-id="65714-260">-InFile</span><span class="sxs-lookup"><span data-stu-id="65714-260">-InFile</span></span>

<span data-ttu-id="65714-261">ファイルから Web 要求の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="65714-261">Gets the content of the web request from a file.</span></span> <span data-ttu-id="65714-262">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="65714-262">Enter a path and file name.</span></span> <span data-ttu-id="65714-263">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="65714-263">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="65714-264">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="65714-264">-MaximumRedirection</span></span>

<span data-ttu-id="65714-265">接続に失敗する前に PowerShell が代替 Uniform Resource Identifier (URI) に接続をリダイレクトする回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-265">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="65714-266">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="65714-266">The default value is 5.</span></span> <span data-ttu-id="65714-267">値 0 (ゼロ) を指定した場合、リダイレクトはまったく行われません。</span><span class="sxs-lookup"><span data-stu-id="65714-267">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="65714-268">-MaximumRetryCount</span><span class="sxs-lookup"><span data-stu-id="65714-268">-MaximumRetryCount</span></span>

<span data-ttu-id="65714-269">400と599の間のエラーコード (包括的または 304) を受信したときに PowerShell が接続を再試行する回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-269">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="65714-270">再試行回数を指定する場合は、 **Retryintervalsec** パラメーターも参照してください。</span><span class="sxs-lookup"><span data-stu-id="65714-270">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="65714-271">-メソッド</span><span class="sxs-lookup"><span data-stu-id="65714-271">-Method</span></span>

<span data-ttu-id="65714-272">Web 要求に使用するメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-272">Specifies the method used for the web request.</span></span> <span data-ttu-id="65714-273">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="65714-273">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="65714-274">Default</span><span class="sxs-lookup"><span data-stu-id="65714-274">Default</span></span>
- <span data-ttu-id="65714-275">削除</span><span class="sxs-lookup"><span data-stu-id="65714-275">Delete</span></span>
- <span data-ttu-id="65714-276">取得</span><span class="sxs-lookup"><span data-stu-id="65714-276">Get</span></span>
- <span data-ttu-id="65714-277">Head</span><span class="sxs-lookup"><span data-stu-id="65714-277">Head</span></span>
- <span data-ttu-id="65714-278">Merge</span><span class="sxs-lookup"><span data-stu-id="65714-278">Merge</span></span>
- <span data-ttu-id="65714-279">オプション</span><span class="sxs-lookup"><span data-stu-id="65714-279">Options</span></span>
- <span data-ttu-id="65714-280">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="65714-280">Patch</span></span>
- <span data-ttu-id="65714-281">投稿</span><span class="sxs-lookup"><span data-stu-id="65714-281">Post</span></span>
- <span data-ttu-id="65714-282">Put</span><span class="sxs-lookup"><span data-stu-id="65714-282">Put</span></span>
- <span data-ttu-id="65714-283">Trace</span><span class="sxs-lookup"><span data-stu-id="65714-283">Trace</span></span>

<span data-ttu-id="65714-284">**Custommethod** パラメーターは、上に一覧表示されていない要求メソッドに使用できます。</span><span class="sxs-lookup"><span data-stu-id="65714-284">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

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

### <span data-ttu-id="65714-285">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="65714-285">-NoProxy</span></span>

<span data-ttu-id="65714-286">コマンドレットが送信先に接続するためにプロキシを使用しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="65714-286">Indicates that the cmdlet shouldn't use a proxy to reach the destination.</span></span> <span data-ttu-id="65714-287">環境で構成されているプロキシをバイパスする必要がある場合は、このスイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-287">When you need to bypass the proxy configured in the environment, use this switch.</span></span> <span data-ttu-id="65714-288">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-288">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="65714-289">-出力</span><span class="sxs-lookup"><span data-stu-id="65714-289">-OutFile</span></span>

<span data-ttu-id="65714-290">このコマンドレットが応答本文を保存する出力ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-290">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="65714-291">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="65714-291">Enter a path and file name.</span></span>
<span data-ttu-id="65714-292">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="65714-292">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="65714-293">既定では、は `Invoke-WebRequest` パイプラインに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="65714-293">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="65714-294">結果をファイルとパイプラインに送信するには、 **Passthru** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-294">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="65714-295">-PassThru</span><span class="sxs-lookup"><span data-stu-id="65714-295">-PassThru</span></span>

<span data-ttu-id="65714-296">コマンドレットがファイルに書き込むだけでなく、結果を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="65714-296">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="65714-297">このパラメーターは、同時に **OutFile** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="65714-297">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="65714-298">-PreserveAuthorizationOnRedirect</span><span class="sxs-lookup"><span data-stu-id="65714-298">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="65714-299">コマンドレットで、リダイレクト全体でヘッダーを保持する必要があることを示し `Authorization` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-299">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="65714-300">既定では、コマンドレットは、 `Authorization` リダイレクトの前にヘッダーを除去します。</span><span class="sxs-lookup"><span data-stu-id="65714-300">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="65714-301">このパラメーターを指定すると、ヘッダーがリダイレクト場所に送信される必要がある場合に、このロジックが無効になります。</span><span class="sxs-lookup"><span data-stu-id="65714-301">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="65714-302">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-302">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="65714-303">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="65714-303">-Proxy</span></span>

<span data-ttu-id="65714-304">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-304">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>
<span data-ttu-id="65714-305">ネットワーク プロキシ サーバーの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="65714-305">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="65714-306">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="65714-306">-ProxyCredential</span></span>

<span data-ttu-id="65714-307">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-307">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="65714-308">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="65714-308">The default is the current user.</span></span>

<span data-ttu-id="65714-309">**User01** や **domain01\user01」** などのユーザー名を入力する **User@Domain.Com** か、 `PSCredential` コマンドレットによって生成されたオブジェクトなどのオブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-309">Type a user name, such as **User01** or **Domain01\User01** , **User@Domain.Com** , or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="65714-310">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="65714-310">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="65714-311">**Proxycredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-311">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="65714-312">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="65714-312">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="65714-313">コマンドレットが、 **プロキシ** パラメーターで指定されたプロキシサーバーにアクセスするために、現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="65714-313">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="65714-314">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="65714-314">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="65714-315">**Proxycredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-315">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="65714-316">-再開</span><span class="sxs-lookup"><span data-stu-id="65714-316">-Resume</span></span>

<span data-ttu-id="65714-317">部分ファイルのダウンロードを再開するのに最適な試行を実行します。</span><span class="sxs-lookup"><span data-stu-id="65714-317">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="65714-318">**再開** に **は、出力** 出力が必要です。</span><span class="sxs-lookup"><span data-stu-id="65714-318">**Resume** requires **OutFile**.</span></span>

<span data-ttu-id="65714-319">**Resume** はローカルファイルとリモートファイルのサイズでのみ動作し、ローカルファイルとリモートファイルが同じであることを検証しません。</span><span class="sxs-lookup"><span data-stu-id="65714-319">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="65714-320">ローカルファイルのサイズがリモートファイルのサイズよりも小さい場合、コマンドレットはファイルのダウンロードを再開し、残りのバイトをファイルの末尾に追加しようとします。</span><span class="sxs-lookup"><span data-stu-id="65714-320">If the local file size is smaller than the remote file size, then the cmdlet attempts to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="65714-321">ローカルファイルのサイズがリモートファイルのサイズと同じ場合、アクションは実行されず、コマンドレットはダウンロードが既に完了していると想定します。</span><span class="sxs-lookup"><span data-stu-id="65714-321">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already complete.</span></span>

<span data-ttu-id="65714-322">ローカルファイルのサイズがリモートファイルのサイズより大きい場合は、ローカルファイルが上書きされ、リモートファイル全体が再ダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="65714-322">If the local file size is larger than the remote file size, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="65714-323">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="65714-323">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="65714-324">リモートサーバーがダウンロードの再開をサポートしていない場合は、ローカルファイルが上書きされ、リモートファイル全体が再ダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="65714-324">If the remote server does not support download resuming, then the local file is overwritten and the entire remote file is re-downloaded.</span></span> <span data-ttu-id="65714-325">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="65714-325">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="65714-326">ローカルファイルが存在しない場合は、ローカルファイルが作成され、リモートファイル全体がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="65714-326">If the local file does not exist, then the local file is created and the entire remote file is downloaded.</span></span> <span data-ttu-id="65714-327">この動作は、 **Resume\*\*\*\*を使用しない場合** と同じです。</span><span class="sxs-lookup"><span data-stu-id="65714-327">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="65714-328">この機能は、PowerShell 6.1.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-328">This feature was added in PowerShell 6.1.0.</span></span>

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

### <span data-ttu-id="65714-329">-RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="65714-329">-RetryIntervalSec</span></span>

<span data-ttu-id="65714-330">400と 304 599 の間のエラーコードを受信したときの、接続の再試行の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-330">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="65714-331">再試行回数を指定するには、 **Maximumretrycount** パラメーターも参照してください。</span><span class="sxs-lookup"><span data-stu-id="65714-331">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

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

### <span data-ttu-id="65714-332">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="65714-332">-SessionVariable</span></span>

<span data-ttu-id="65714-333">このコマンドレットによって web 要求セッションが作成され、値に保存される変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-333">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="65714-334">ドル記号 () を付けずに変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-334">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="65714-335">セッション変数を指定すると、は `Invoke-WebRequest` web 要求セッションオブジェクトを作成し、PowerShell セッション内の指定された名前の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="65714-335">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="65714-336">コマンドが完了すると、すぐに変数をセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="65714-336">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="65714-337">リモート セッションとは異なり、Web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="65714-337">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="65714-338">これは、cookie、資格情報、リダイレクトの最大値、ユーザーエージェント文字列など、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="65714-338">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="65714-339">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="65714-339">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="65714-340">後続の Web 要求で Web 要求セッションを使用するには、 **WebSession** パラメーターの値にセッション変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-340">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="65714-341">PowerShell は、新しい接続を確立するときに、web 要求セッションオブジェクトのデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-341">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="65714-342">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-342">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="65714-343">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="65714-343">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="65714-344">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-344">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="65714-345">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="65714-345">-SkipCertificateCheck</span></span>

<span data-ttu-id="65714-346">証明書の検証チェックをスキップします。</span><span class="sxs-lookup"><span data-stu-id="65714-346">Skips certificate validation checks.</span></span> <span data-ttu-id="65714-347">これには、有効期限、失効、信頼されたルート証明機関などのすべての検証が含まれます。</span><span class="sxs-lookup"><span data-stu-id="65714-347">This includes all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="65714-348">このパラメーターの使用はセキュリティで保護されていないため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="65714-348">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="65714-349">このスイッチは、テスト目的で自己署名証明書を使用する既知のホストに対してのみ使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="65714-349">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="65714-350">ご自身の責任でをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="65714-350">Use at your own risk.</span></span>

<span data-ttu-id="65714-351">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-351">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="65714-352">-SkipHeaderValidation</span><span class="sxs-lookup"><span data-stu-id="65714-352">-SkipHeaderValidation</span></span>

<span data-ttu-id="65714-353">コマンドレットが検証なしで要求にヘッダーを追加する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="65714-353">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="65714-354">標準に準拠していないヘッダー値が必要なサイトには、このスイッチを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65714-354">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="65714-355">このスイッチを指定すると、値をオフにするための検証が無効になります。</span><span class="sxs-lookup"><span data-stu-id="65714-355">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="65714-356">指定した場合、すべてのヘッダーが検証なしで追加されます。</span><span class="sxs-lookup"><span data-stu-id="65714-356">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="65714-357">このスイッチは、 **ContentType** 、 **Headers** 、および **UserAgent** パラメーターに渡される値の検証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="65714-357">This switch disables validation for values passed to the **ContentType** , **Headers** and **UserAgent** parameters.</span></span>

<span data-ttu-id="65714-358">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-358">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="65714-359">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="65714-359">-SslProtocol</span></span>

<span data-ttu-id="65714-360">Web 要求に対して許可されている SSL/TLS プロトコルを設定します。</span><span class="sxs-lookup"><span data-stu-id="65714-360">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="65714-361">既定では、システムでサポートされているすべての SSL/TLS プロトコルが許可されます。</span><span class="sxs-lookup"><span data-stu-id="65714-361">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="65714-362">**Sslprotocol** では、コンプライアンスのために特定のプロトコルを制限できます。</span><span class="sxs-lookup"><span data-stu-id="65714-362">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="65714-363">**Sslprotocol** では **websslprotocol** フラグ列挙型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="65714-363">**SslProtocol** uses the **WebSslProtocol** Flag Enum.</span></span> <span data-ttu-id="65714-364">フラグ表記を使用して複数のプロトコルを指定したり、複数の **Websslprotocol** オプションを **bor** と組み合わせたりすることはできますが、複数のプロトコルを指定することは、すべてのプラットフォームでサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="65714-364">It is possible to supply more than one protocol using flag notation or combining multiple **WebSslProtocol** options with **bor** , however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="65714-365">Windows 以外のプラットフォームでは、を `'Tls, Tls12'` オプションとして指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-365">On non-Windows platforms it may not be possible to supply `'Tls, Tls12'` as an option.</span></span>

<span data-ttu-id="65714-366">この機能は、PowerShell 6.0.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="65714-366">This feature was added in PowerShell 6.0.0.</span></span>

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

### <span data-ttu-id="65714-367">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="65714-367">-TimeoutSec</span></span>

<span data-ttu-id="65714-368">要求がタイムアウトになるまでの待機時間を指定します。値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="65714-368">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="65714-369">既定値は 0 で、無制限のタイムアウトを意味しています。</span><span class="sxs-lookup"><span data-stu-id="65714-369">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="65714-370">ドメインネームシステム (DNS) クエリは、返されるまで最大15秒かかることがあります。要求に解決を必要とするホスト名が含まれていて、 **Timeoutsec** を0より大きく15秒未満に設定した場合、WebException がスローされる前に15秒以上かかることがあり、要求はタイムアウトになります。</span><span class="sxs-lookup"><span data-stu-id="65714-370">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="65714-371">-トークン</span><span class="sxs-lookup"><span data-stu-id="65714-371">-Token</span></span>

<span data-ttu-id="65714-372">要求に含める OAuth またはベアラートークン。</span><span class="sxs-lookup"><span data-stu-id="65714-372">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="65714-373">**トークン** は、特定の **認証** オプションに必要です。</span><span class="sxs-lookup"><span data-stu-id="65714-373">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="65714-374">個別に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-374">It cannot be used independently.</span></span>

<span data-ttu-id="65714-375">**トークン** は、 `SecureString` トークンを含むを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="65714-375">**Token** takes a `SecureString` containing the token.</span></span> <span data-ttu-id="65714-376">トークンを手動で指定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="65714-376">To supply the token manually use the following:</span></span>

`Invoke-WebRequest -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="65714-377">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="65714-377">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="65714-378">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="65714-378">-TransferEncoding</span></span>

<span data-ttu-id="65714-379">転送エンコード HTTP 応答ヘッダーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-379">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="65714-380">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="65714-380">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="65714-381">まとめ</span><span class="sxs-lookup"><span data-stu-id="65714-381">Chunked</span></span>
- <span data-ttu-id="65714-382">圧縮</span><span class="sxs-lookup"><span data-stu-id="65714-382">Compress</span></span>
- <span data-ttu-id="65714-383">Deflate</span><span class="sxs-lookup"><span data-stu-id="65714-383">Deflate</span></span>
- <span data-ttu-id="65714-384">GZip</span><span class="sxs-lookup"><span data-stu-id="65714-384">GZip</span></span>
- <span data-ttu-id="65714-385">ID</span><span class="sxs-lookup"><span data-stu-id="65714-385">Identity</span></span>

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

### <span data-ttu-id="65714-386">-Uri</span><span class="sxs-lookup"><span data-stu-id="65714-386">-Uri</span></span>

<span data-ttu-id="65714-387">Web 要求の送信先となるインターネットリソースの Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-387">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="65714-388">URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="65714-388">Enter a URI.</span></span> <span data-ttu-id="65714-389">このパラメーターは、HTTP または HTTPS のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="65714-389">This parameter supports HTTP or HTTPS only.</span></span>

<span data-ttu-id="65714-390">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="65714-390">This parameter is required.</span></span> <span data-ttu-id="65714-391">パラメーター名 **Uri** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="65714-391">The parameter name **Uri** is optional.</span></span>

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

### <span data-ttu-id="65714-392">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="65714-392">-UseBasicParsing</span></span>

<span data-ttu-id="65714-393">このパラメーターは非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="65714-393">This parameter has been deprecated.</span></span> <span data-ttu-id="65714-394">PowerShell 6.0.0 以降では、すべての Web 要求で基本的な解析のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="65714-394">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="65714-395">このパラメーターは下位互換性のためだけに含まれています。このパラメーターを使用しても、コマンドレットの操作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="65714-395">This parameter is included for backwards compatibility only and any use of it has no effect on the operation of the cmdlet.</span></span>

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

### <span data-ttu-id="65714-396">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="65714-396">-UseDefaultCredentials</span></span>

<span data-ttu-id="65714-397">コマンドレットが、web 要求を送信するために現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="65714-397">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="65714-398">**認証** または **資格情報** と共に使用することはできません。また、すべてのプラットフォームでサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65714-398">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

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

### <span data-ttu-id="65714-399">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="65714-399">-UserAgent</span></span>

<span data-ttu-id="65714-400">Web 要求のユーザー エージェント文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-400">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="65714-401">既定のユーザーエージェントは、 `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` オペレーティングシステムとプラットフォームによって微妙な違いがあるに似ています。</span><span class="sxs-lookup"><span data-stu-id="65714-401">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="65714-402">ほとんどのインターネットブラウザーで使用される標準のユーザーエージェント文字列を使用して web サイトをテストするには、Chrome、FireFox、InternetExplorer、Opera、Safari などの [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) クラスのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-402">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

<span data-ttu-id="65714-403">たとえば、次のコマンドは、Internet Explorer のユーザーエージェント文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-403">For example, the following command uses the user agent string for Internet Explorer:</span></span>

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

### <span data-ttu-id="65714-404">-WebSession</span><span class="sxs-lookup"><span data-stu-id="65714-404">-WebSession</span></span>

<span data-ttu-id="65714-405">Web 要求セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="65714-405">Specifies a web request session.</span></span> <span data-ttu-id="65714-406">ドル記号 () を含む変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-406">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="65714-407">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-407">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="65714-408">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="65714-408">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="65714-409">`Content-Type`**本文** に **MultipartFormDataContent** オブジェクトが指定されている場合、などのコンテンツ関連ヘッダーもオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="65714-409">Content related headers, such as `Content-Type`, are also be overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

<span data-ttu-id="65714-410">リモートセッションとは異なり、web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="65714-410">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="65714-411">これは、cookie、資格情報、リダイレクトの最大値、ユーザーエージェント文字列など、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="65714-411">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="65714-412">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="65714-412">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="65714-413">Web 要求セッションを作成するには、コマンドの **sessionvariable** パラメーターの値にドル記号を付けずに変数名を入力し `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-413">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="65714-414">`Invoke-WebRequest` セッションを作成し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="65714-414">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="65714-415">後続のコマンドで、この変数を **WebSession** パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="65714-415">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="65714-416">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="65714-416">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="65714-417">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="65714-417">CommonParameters</span></span>

<span data-ttu-id="65714-418">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="65714-418">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65714-419">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65714-419">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65714-420">入力</span><span class="sxs-lookup"><span data-stu-id="65714-420">INPUTS</span></span>

### <span data-ttu-id="65714-421">System.Object</span><span class="sxs-lookup"><span data-stu-id="65714-421">System.Object</span></span>

<span data-ttu-id="65714-422">パイプを使用して、web 要求の本文をにパイプすることができ `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="65714-422">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="65714-423">出力</span><span class="sxs-lookup"><span data-stu-id="65714-423">OUTPUTS</span></span>

### <span data-ttu-id="65714-424">Microsoft. PowerShell. BasicHtmlWebResponseObject</span><span class="sxs-lookup"><span data-stu-id="65714-424">Microsoft.PowerShell.Commands.BasicHtmlWebResponseObject</span></span>

## <span data-ttu-id="65714-425">注</span><span class="sxs-lookup"><span data-stu-id="65714-425">NOTES</span></span>

<span data-ttu-id="65714-426">PowerShell 6.0.0 以降で `Invoke-WebRequest` は、基本的な解析のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="65714-426">Beginning with PowerShell 6.0.0 `Invoke-WebRequest` supports basic parsing only.</span></span>

<span data-ttu-id="65714-427">オブジェクトの種類の詳細につい **ては、** 「 [basichtmlwebresponseobject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65714-427">For more information about the **Microsoft.PowerShell.Commands.BasicHtmlWebResponseObject** object type, see [BasicHtmlWebResponseObject](/dotnet/api/microsoft.powershell.commands.basichtmlwebresponseobject).</span></span>

<span data-ttu-id="65714-428">.NET が PowerShell にプロキシサービスを提供する方法の詳細については、「 [プロキシ経由でインターネットにアクセス](/dotnet/framework/network-programming/accessing-the-internet-through-a-proxy)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65714-428">For more information about how .NET provides proxy services to PowerShell, see [Accessing the Internet Through a Proxy](/dotnet/framework/network-programming/accessing-the-internet-through-a-proxy).</span></span>

## <span data-ttu-id="65714-429">関連リンク</span><span class="sxs-lookup"><span data-stu-id="65714-429">RELATED LINKS</span></span>

[<span data-ttu-id="65714-430">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="65714-430">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="65714-431">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="65714-431">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="65714-432">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="65714-432">ConvertTo-Json</span></span>](ConvertTo-Json.md)

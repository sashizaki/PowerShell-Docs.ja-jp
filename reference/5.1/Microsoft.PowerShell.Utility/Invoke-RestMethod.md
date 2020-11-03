---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/13/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: c89f7351e9c874cea2cc0cd5e0912e3ca0d8b0bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213843"
---
# <span data-ttu-id="4a99c-103">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="4a99c-103">Invoke-RestMethod</span></span>

## <span data-ttu-id="4a99c-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a99c-104">Synopsis</span></span>
<span data-ttu-id="4a99c-105">RESTful Web サービスに HTTP または HTTPS 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-105">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="4a99c-106">構文</span><span class="sxs-lookup"><span data-stu-id="4a99c-106">Syntax</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-CertificateThumbprint <String>] [-Certificate <X509Certificate>]
 [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>] [-Headers <IDictionary>]
 [-MaximumRedirection <Int32>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials]
 [-Body <Object>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>]
 [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="4a99c-107">説明</span><span class="sxs-lookup"><span data-stu-id="4a99c-107">Description</span></span>

<span data-ttu-id="4a99c-108">コマンドレットは、高度 `Invoke-RestMethod` に構造化されたデータを返す HTTP 要求と HTTPS 要求を、表現された状態転送 (REST) web サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-108">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that returns richly structured data.</span></span>

<span data-ttu-id="4a99c-109">応答は、データ型に応じて書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-109">Windows PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="4a99c-110">RSS または ATOM フィードの場合は、Item または Entry XML ノードが返されます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-110">For an RSS or ATOM feed, Windows PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="4a99c-111">JavaScript Object Notation (JSON) または XML の場合は、コンテンツがオブジェクトに変換 (または逆シリアル化) されます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-111">For JavaScript Object Notation (JSON) or XML, Windows PowerShell converts (or deserializes) the content into objects.</span></span>

<span data-ttu-id="4a99c-112">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4a99c-112">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="4a99c-113">既定では、プロパティを設定するためにページを解析するときに、web ページ内のスクリプトコードが実行される場合があり `ParsedHtml` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-113">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span> <span data-ttu-id="4a99c-114">これを抑制するには、 **Usebasicparsing** スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-114">Use the **UseBasicParsing** switch to suppress this.</span></span>

## <span data-ttu-id="4a99c-115">例</span><span class="sxs-lookup"><span data-stu-id="4a99c-115">Examples</span></span>

### <span data-ttu-id="4a99c-116">例 1: PowerShell RSS フィードを取得する</span><span class="sxs-lookup"><span data-stu-id="4a99c-116">Example 1: Get the PowerShell RSS feed</span></span>

```powershell
Invoke-RestMethod -Uri https://devblogs.microsoft.com/powershell/feed/ |
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

<span data-ttu-id="4a99c-117">このコマンドは、 `Invoke-RestMethod` コマンドレットを使用して、PowerShell ブログの RSS フィードから情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-117">This command uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="4a99c-118">このコマンドは、コマンドレットを使用して、 `Format-Table` テーブル内の各ブログの **Title** プロパティと **pubDate** プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-118">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

### <span data-ttu-id="4a99c-119">例 2</span><span class="sxs-lookup"><span data-stu-id="4a99c-119">Example 2</span></span>

<span data-ttu-id="4a99c-120">次の例では、ユーザーがを実行して、 `Invoke-RestMethod` ユーザーの組織のイントラネット web サイトで POST 要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-120">In the following example, a user runs `Invoke-RestMethod` to perform a POST request on an intranet website in the user's organization.</span></span>

```powershell
$Cred = Get-Credential

# Next, allow the use of self-signed SSL certificates.

[System.Net.ServicePointManager]::ServerCertificateValidationCallback = { $True }

# Create variables to store the values consumed by the Invoke-RestMethod command.
# The search variable contents are later embedded in the body variable.

$Server = 'server.contoso.com'
$Url = "https://${server}:8089/services/search/jobs/export"
$Search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"

# The cmdlet handles URL encoding. The body variable describes the search criteria, specifies CSV as
# the output mode, and specifies a time period for returned data that starts two days ago and ends
# one day ago. The body variable specifies values for parameters that apply to the particular REST
# API with which Invoke-RestMethod is communicating.

$Body = @{
    search = $Search
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}

# Now, run the Invoke-RestMethod command with all variables in place, specifying a path and file
# name for the resulting CSV output file.

Invoke-RestMethod -Method Post -Uri $url -Credential $Cred -Body $body -OutFile output.csv

{"preview":true,"offset":0,"result":{"sourcetype":"contoso1","count":"9624"}}

{"preview":true,"offset":1,"result":{"sourcetype":"contoso2","count":"152"}}

{"preview":true,"offset":2,"result":{"sourcetype":"contoso3","count":"88494"}}

{"preview":true,"offset":3,"result":{"sourcetype":"contoso4","count":"15277"}}
```

### <span data-ttu-id="4a99c-121">例 3: 複数のヘッダーを渡す</span><span class="sxs-lookup"><span data-stu-id="4a99c-121">Example 3: Pass multiple headers</span></span>

<span data-ttu-id="4a99c-122">この例では、の複数のヘッダーを REST API に渡す方法について説明し `hash-table` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-122">This example demonstrates, how to pass multiple headers in from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

<span data-ttu-id="4a99c-123">多くの場合、Api は認証や検証などのためにヘッダーを渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a99c-123">APIs often require passed headers for authentication, validation etc.</span></span>

### <span data-ttu-id="4a99c-124">例 3: フォームデータを送信する</span><span class="sxs-lookup"><span data-stu-id="4a99c-124">Example 3: Submitting form data</span></span>

<span data-ttu-id="4a99c-125">本文がフォームである場合、または別の呼び出しの出力である場合 `Invoke-WebRequest` 、PowerShell は要求の内容をフォームフィールドに設定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-125">When the body is a form, or it is the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="4a99c-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-126">For example:</span></span>

```powershell
$R = Invoke-WebRequest https://website.com/login.aspx
$R.Forms[0].Name = "MyName"
$R.Forms[0].Password = "MyPassword"
Invoke-RestMethod https://website.com/service.aspx -Body $R.Forms[0]
```

## <span data-ttu-id="4a99c-127">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a99c-127">Parameters</span></span>

### <span data-ttu-id="4a99c-128">-本文</span><span class="sxs-lookup"><span data-stu-id="4a99c-128">-Body</span></span>

<span data-ttu-id="4a99c-129">要求の本文を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-129">Specifies the body of the request.</span></span> <span data-ttu-id="4a99c-130">本文は、ヘッダーに続く要求の内容です。</span><span class="sxs-lookup"><span data-stu-id="4a99c-130">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="4a99c-131">パイプを使用して、本文の値をにパイプすることもでき `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-131">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="4a99c-132">**Body** パラメーターを使用すると、クエリ パラメーターのリストを指定したり、応答の内容を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-132">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="4a99c-133">入力が GET 要求で、本文が IDictionary (通常は、ハッシュ テーブル) の場合、本文はクエリ パラメーターとして URI に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-133">When the input is a GET request, and the body is an IDictionary (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="4a99c-134">その他の要求の種類 (POST など) の場合、本文は標準的な "名前=値" の形式で要求本文の値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-134">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

> [!WARNING]
> <span data-ttu-id="4a99c-135">`with -1-byte payload`本文のサイズが既知で HTTP ヘッダーで送信されている場合でも、POST 本文の詳細出力はで終了し `Content-Length` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-135">The verbose output of a POST body will end with `with -1-byte payload`, even though the size of the body is both known and sent in the `Content-Length` HTTP header.</span></span>

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

### <span data-ttu-id="4a99c-136">-証明書</span><span class="sxs-lookup"><span data-stu-id="4a99c-136">-Certificate</span></span>

<span data-ttu-id="4a99c-137">セキュリティで保護された Web 要求に使用するクライアント証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-137">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="4a99c-138">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-138">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="4a99c-139">証明書を検索するには、を使用する `Get-PfxCertificate` か、 `Get-ChildItem` 証明書 () ドライブのコマンドレットを使用し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-139">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="4a99c-140">証明書が無効な場合、または証明書に十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-140">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="4a99c-141">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="4a99c-141">-CertificateThumbprint</span></span>

<span data-ttu-id="4a99c-142">要求を送信するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-142">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="4a99c-143">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="4a99c-144">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="4a99c-145">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="4a99c-146">証明書の拇印を取得するに `Get-Item` は、 `Get-ChildItem` Windows PowerShell () ドライブのまたはコマンドを使用し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the Windows PowerShell (`Cert:`) drive.</span></span>

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

### <span data-ttu-id="4a99c-147">-ContentType</span><span class="sxs-lookup"><span data-stu-id="4a99c-147">-ContentType</span></span>

<span data-ttu-id="4a99c-148">Web 要求のコンテンツ タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-148">Specifies the content type of the web request.</span></span>

<span data-ttu-id="4a99c-149">このパラメーターを省略して、要求メソッドが POST の場合は、 `Invoke-RestMethod` コンテンツの種類を "application/url エンコード" に設定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-149">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to "application/x-www-form-urlencoded".</span></span> <span data-ttu-id="4a99c-150">それ以外の場合、呼び出しの中でコンテンツ タイプは指定されません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-150">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="4a99c-151">-Credential</span><span class="sxs-lookup"><span data-stu-id="4a99c-151">-Credential</span></span>

<span data-ttu-id="4a99c-152">要求を送信するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-152">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="4a99c-153">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="4a99c-153">The default is the current user.</span></span>

<span data-ttu-id="4a99c-154">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-154">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="4a99c-155">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-155">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="4a99c-156">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a99c-156">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="4a99c-157">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="4a99c-157">-DisableKeepAlive</span></span>

<span data-ttu-id="4a99c-158">HTTP ヘッダーの **KeepAlive** 値を False に設定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-158">Sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="4a99c-159">既定では、 **KeepAlive** は True です。</span><span class="sxs-lookup"><span data-stu-id="4a99c-159">By default, **KeepAlive** is True.</span></span>
<span data-ttu-id="4a99c-160">**KeepAlive** は、後続の要求を容易にするために、サーバーへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-160">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: KeepAlive
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4a99c-161">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="4a99c-161">-Headers</span></span>

<span data-ttu-id="4a99c-162">Web 要求のヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-162">Specifies the headers of the web request.</span></span> <span data-ttu-id="4a99c-163">ハッシュ テーブルまたは辞書を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-163">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="4a99c-164">UserAgent ヘッダーを設定するには、 **UserAgent** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-164">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="4a99c-165">このパラメーターを使用して UserAgent または Cookie のヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-165">You cannot use this parameter to specify UserAgent or cookie headers.</span></span>

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

### <span data-ttu-id="4a99c-166">-InFile</span><span class="sxs-lookup"><span data-stu-id="4a99c-166">-InFile</span></span>

<span data-ttu-id="4a99c-167">ファイルから Web 要求の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-167">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="4a99c-168">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-168">Enter a path and file name.</span></span> <span data-ttu-id="4a99c-169">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="4a99c-169">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="4a99c-170">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="4a99c-170">-MaximumRedirection</span></span>

<span data-ttu-id="4a99c-171">接続を失敗させる前に Windows PowerShell が代替 Uniform Resource Identifier (URI) に接続をリダイレクトする回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-171">Determines how many times Windows PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="4a99c-172">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="4a99c-172">The default value is 5.</span></span> <span data-ttu-id="4a99c-173">値 0 (ゼロ) を指定した場合、リダイレクトはまったく行われません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-173">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="4a99c-174">-メソッド</span><span class="sxs-lookup"><span data-stu-id="4a99c-174">-Method</span></span>

<span data-ttu-id="4a99c-175">Web 要求に使用するメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-175">Specifies the method used for the web request.</span></span> <span data-ttu-id="4a99c-176">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4a99c-176">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4a99c-177">Default</span><span class="sxs-lookup"><span data-stu-id="4a99c-177">Default</span></span>
- <span data-ttu-id="4a99c-178">削除</span><span class="sxs-lookup"><span data-stu-id="4a99c-178">Delete</span></span>
- <span data-ttu-id="4a99c-179">取得</span><span class="sxs-lookup"><span data-stu-id="4a99c-179">Get</span></span>
- <span data-ttu-id="4a99c-180">Head</span><span class="sxs-lookup"><span data-stu-id="4a99c-180">Head</span></span>
- <span data-ttu-id="4a99c-181">Merge</span><span class="sxs-lookup"><span data-stu-id="4a99c-181">Merge</span></span>
- <span data-ttu-id="4a99c-182">オプション</span><span class="sxs-lookup"><span data-stu-id="4a99c-182">Options</span></span>
- <span data-ttu-id="4a99c-183">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="4a99c-183">Patch</span></span>
- <span data-ttu-id="4a99c-184">投稿</span><span class="sxs-lookup"><span data-stu-id="4a99c-184">Post</span></span>
- <span data-ttu-id="4a99c-185">Put</span><span class="sxs-lookup"><span data-stu-id="4a99c-185">Put</span></span>
- <span data-ttu-id="4a99c-186">Trace</span><span class="sxs-lookup"><span data-stu-id="4a99c-186">Trace</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: (All)
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4a99c-187">-出力</span><span class="sxs-lookup"><span data-stu-id="4a99c-187">-OutFile</span></span>

<span data-ttu-id="4a99c-188">指定した出力ファイルに応答本文を保存します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-188">Saves the response body in the specified output file.</span></span> <span data-ttu-id="4a99c-189">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-189">Enter a path and file name.</span></span> <span data-ttu-id="4a99c-190">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="4a99c-190">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="4a99c-191">既定では、は `Invoke-RestMethod` パイプラインに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-191">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="4a99c-192">結果をファイルとパイプラインに送信するには、 **Passthru** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-192">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="4a99c-193">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4a99c-193">-PassThru</span></span>

<span data-ttu-id="4a99c-194">結果を返す一方でファイルにも書き込みます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-194">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="4a99c-195">このパラメーターは、同時に **OutFile** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="4a99c-195">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="4a99c-196">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="4a99c-196">-Proxy</span></span>

<span data-ttu-id="4a99c-197">インターネット リソースに直接接続するのではなく、要求のプロキシ サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-197">Uses a proxy server for the request, rather than connecting directly to the Internet resource.</span></span> <span data-ttu-id="4a99c-198">ネットワーク プロキシ サーバーの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-198">Enter the URI of a network proxy server.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4a99c-199">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="4a99c-199">-ProxyCredential</span></span>

<span data-ttu-id="4a99c-200">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-200">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="4a99c-201">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="4a99c-201">The default is the current user.</span></span>

<span data-ttu-id="4a99c-202">「User01」や「Domain01\User01」のようなユーザー名を入力するか、  コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-202">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="4a99c-203">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="4a99c-203">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="4a99c-204">**ProxyCredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-204">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="4a99c-205">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="4a99c-205">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="4a99c-206">現在のユーザーの資格情報を使用して、 **Proxy** パラメーターに指定したプロキシ サーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4a99c-206">Uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="4a99c-207">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="4a99c-207">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="4a99c-208">**ProxyCredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-208">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="4a99c-209">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="4a99c-209">-SessionVariable</span></span>

<span data-ttu-id="4a99c-210">Web 要求セッションを作成して、指定した変数の値に保存します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-210">Creates a web request session and saves it in the value of the specified variable.</span></span> <span data-ttu-id="4a99c-211">ドル記号 () を付けずに変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-211">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="4a99c-212">セッション変数を指定すると、は `Invoke-RestMethod` web 要求セッションオブジェクトを作成し、PowerShell セッション内の指定された名前の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-212">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="4a99c-213">コマンドが完了すると、すぐに変数をセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-213">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="4a99c-214">リモート セッションとは異なり、Web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-214">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="4a99c-215">Web 要求セッションは、Cookie、資格情報、リダイレクトの最大値、ユーザー エージェント文字列などの、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="4a99c-215">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="4a99c-216">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-216">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="4a99c-217">後続の Web 要求で Web 要求セッションを使用するには、 **WebSession** パラメーターの値にセッション変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-217">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="4a99c-218">Windows PowerShell は、新しい接続を確立するときに、Web 要求セッション オブジェクトのデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-218">Windows PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="4a99c-219">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-219">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="4a99c-220">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-220">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="4a99c-221">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-221">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="4a99c-222">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="4a99c-222">-TimeoutSec</span></span>

<span data-ttu-id="4a99c-223">要求がタイムアウトになるまでの待機時間を指定します。値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-223">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="4a99c-224">既定値は 0 で、無制限のタイムアウトを意味しています。</span><span class="sxs-lookup"><span data-stu-id="4a99c-224">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="4a99c-225">ドメインネームシステム (DNS) クエリは、返されるまで最大15秒かかることがあります。要求に解決を必要とするホスト名が含まれていて、TimeoutSec を0より大きく15秒未満に設定した場合、WebException がスローされる前に15秒以上かかることがあり、要求はタイムアウトになります。</span><span class="sxs-lookup"><span data-stu-id="4a99c-225">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set TimeoutSec to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="4a99c-226">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="4a99c-226">-TransferEncoding</span></span>

<span data-ttu-id="4a99c-227">転送エンコード HTTP 応答ヘッダーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-227">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="4a99c-228">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4a99c-228">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4a99c-229">まとめ</span><span class="sxs-lookup"><span data-stu-id="4a99c-229">Chunked</span></span>
- <span data-ttu-id="4a99c-230">圧縮</span><span class="sxs-lookup"><span data-stu-id="4a99c-230">Compress</span></span>
- <span data-ttu-id="4a99c-231">Deflate</span><span class="sxs-lookup"><span data-stu-id="4a99c-231">Deflate</span></span>
- <span data-ttu-id="4a99c-232">GZip</span><span class="sxs-lookup"><span data-stu-id="4a99c-232">GZip</span></span>
- <span data-ttu-id="4a99c-233">ID</span><span class="sxs-lookup"><span data-stu-id="4a99c-233">Identity</span></span>

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

### <span data-ttu-id="4a99c-234">-Uri</span><span class="sxs-lookup"><span data-stu-id="4a99c-234">-Uri</span></span>

<span data-ttu-id="4a99c-235">Web 要求の送信先の Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-235">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="4a99c-236">このパラメーターは、HTTP、HTTPS、FTP、FILE の値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4a99c-236">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="4a99c-237">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="4a99c-237">This parameter is required.</span></span> <span data-ttu-id="4a99c-238">パラメーター名 ( **Uri** ) は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4a99c-238">The parameter name ( **Uri** ) is optional.</span></span>

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

### <span data-ttu-id="4a99c-239">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="4a99c-239">-UseBasicParsing</span></span>

<span data-ttu-id="4a99c-240">コマンドレットが基本的な解析を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-240">Indicates that the cmdlet uses basic parsing.</span></span> <span data-ttu-id="4a99c-241">コマンドレットは、 **文字列** オブジェクト内の生の HTML を返します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-241">The cmdlet returns the raw HTML in a **String** object.</span></span>

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

### <span data-ttu-id="4a99c-242">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="4a99c-242">-UseDefaultCredentials</span></span>

<span data-ttu-id="4a99c-243">現在のユーザーの資格情報を使用して Web 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-243">Uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="4a99c-244">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="4a99c-244">-UserAgent</span></span>

<span data-ttu-id="4a99c-245">Web 要求のユーザー エージェント文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-245">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="4a99c-246">既定のユーザー エージェントは、"Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0" のようになりますが、オペレーティング システムとプラットフォームによって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="4a99c-246">The default user agent is similar to "Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0" with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="4a99c-247">ほとんどのインターネットブラウザーで使用される標準のユーザーエージェント文字列を使用して web サイトをテストするには、Chrome、FireFox、Internet Explorer、Opera、Safari などの [PSUserAgent](/dotnet/api/microsoft.powershell.commands) クラスのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-247">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands) class, such as Chrome, FireFox, Internet Explorer, Opera, and Safari.</span></span>

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

### <span data-ttu-id="4a99c-248">-WebSession</span><span class="sxs-lookup"><span data-stu-id="4a99c-248">-WebSession</span></span>

<span data-ttu-id="4a99c-249">Web 要求セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-249">Specifies a web request session.</span></span> <span data-ttu-id="4a99c-250">ドル記号 () を含む変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-250">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="4a99c-251">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-251">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential** .</span></span> <span data-ttu-id="4a99c-252">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-252">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="4a99c-253">リモート セッションとは異なり、Web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-253">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="4a99c-254">Web 要求セッションは、Cookie、資格情報、リダイレクトの最大値、ユーザー エージェント文字列などの、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="4a99c-254">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="4a99c-255">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-255">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="4a99c-256">Web 要求セッションを作成するには、コマンドの **Sessionvariable** パラメーターの値に、(ドル記号を付けずに) 変数名を入力し `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-256">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="4a99c-257">`Invoke-RestMethod` セッションを作成し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-257">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="4a99c-258">後続のコマンドで、この変数を **WebSession** パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-258">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="4a99c-259">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a99c-259">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="4a99c-260">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a99c-260">CommonParameters</span></span>

<span data-ttu-id="4a99c-261">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4a99c-261">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4a99c-262">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a99c-262">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4a99c-263">入力</span><span class="sxs-lookup"><span data-stu-id="4a99c-263">Inputs</span></span>

### <span data-ttu-id="4a99c-264">System.Object</span><span class="sxs-lookup"><span data-stu-id="4a99c-264">System.Object</span></span>

<span data-ttu-id="4a99c-265">パイプを使用して、web 要求の本文をにパイプすることができ `Invoke-RestMethod` ます。</span><span class="sxs-lookup"><span data-stu-id="4a99c-265">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="4a99c-266">出力</span><span class="sxs-lookup"><span data-stu-id="4a99c-266">Outputs</span></span>

### <span data-ttu-id="4a99c-267">System.Xml.Xmlドキュメント、Microsoft.PowerShell.Commands.HtmlWebResponseObject、System.string</span><span class="sxs-lookup"><span data-stu-id="4a99c-267">System.Xml.XmlDocument, Microsoft.PowerShell.Commands.HtmlWebResponseObject, System.String</span></span>

<span data-ttu-id="4a99c-268">このコマンドレットの出力は、取得するコンテンツの書式によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4a99c-268">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="4a99c-269">PSObject</span><span class="sxs-lookup"><span data-stu-id="4a99c-269">PSObject</span></span>

<span data-ttu-id="4a99c-270">要求が JSON 文字列を返す場合、は `Invoke-RestMethod` 文字列を表す PSObject を返します。</span><span class="sxs-lookup"><span data-stu-id="4a99c-270">If the request returns JSON strings, `Invoke-RestMethod` returns a PSObject that represents the strings.</span></span>

## <span data-ttu-id="4a99c-271">メモ</span><span class="sxs-lookup"><span data-stu-id="4a99c-271">Notes</span></span>

## <span data-ttu-id="4a99c-272">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4a99c-272">Related Links</span></span>

[<span data-ttu-id="4a99c-273">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="4a99c-273">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="4a99c-274">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="4a99c-274">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="4a99c-275">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="4a99c-275">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

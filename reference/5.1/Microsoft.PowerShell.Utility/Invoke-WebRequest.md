---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: f3545065d4879830a5051ef687f210c7fbd1251e
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "98860663"
---
# <span data-ttu-id="143d4-102">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="143d4-102">Invoke-WebRequest</span></span>

## <span data-ttu-id="143d4-103">概要</span><span class="sxs-lookup"><span data-stu-id="143d4-103">SYNOPSIS</span></span>
<span data-ttu-id="143d4-104">インターネット上の Web ページからコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="143d4-104">Gets content from a web page on the Internet.</span></span>

## <span data-ttu-id="143d4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="143d4-105">SYNTAX</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="143d4-106">Description</span><span class="sxs-lookup"><span data-stu-id="143d4-106">DESCRIPTION</span></span>

<span data-ttu-id="143d4-107">`Invoke-WebRequest`コマンドレットは、HTTP、HTTPS、FTP、およびファイル要求を web ページまたは web サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="143d4-107">The `Invoke-WebRequest` cmdlet sends HTTP, HTTPS, FTP, and FILE requests to a web page or web service.</span></span>
<span data-ttu-id="143d4-108">さらに、応答を解析し、フォーム、リンク、画像、およびその他の重要な HTML 要素のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="143d4-108">It parses the response and returns collections of forms, links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="143d4-109">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="143d4-109">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="143d4-110">既定では、プロパティを設定するためにページを解析するときに、web ページ内のスクリプトコードが実行される場合があり `ParsedHtml` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-110">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span>
> <span data-ttu-id="143d4-111">`-UseBasicParsing`これを抑制するには、スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="143d4-111">Use the `-UseBasicParsing` switch to suppress this.</span></span>

## <span data-ttu-id="143d4-112">例</span><span class="sxs-lookup"><span data-stu-id="143d4-112">EXAMPLES</span></span>

### <span data-ttu-id="143d4-113">例 1: web 要求を送信する</span><span class="sxs-lookup"><span data-stu-id="143d4-113">Example 1: Send a web request</span></span>

<span data-ttu-id="143d4-114">このコマンドは、コマンドレットを使用して、 `Invoke-WebRequest` web 要求を Bing.com サイトに送信します。</span><span class="sxs-lookup"><span data-stu-id="143d4-114">This command uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

```powershell
$R = Invoke-WebRequest -URI https://www.bing.com?q=how+many+feet+in+a+mile
$R.AllElements | Where-Object {
    $_.name -like "* Value" -and $_.tagName -eq "INPUT"
} | Select-Object Name, Value
```

```Output
name       value
----       -----
From Value 1
To Value   5280
```

<span data-ttu-id="143d4-115">最初のコマンドは、要求を発行し、その応答を変数に保存し `$R` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-115">The first command issues the request and saves the response in the `$R` variable.</span></span>

<span data-ttu-id="143d4-116">2番目のコマンドは、 **Allelements** プロパティのオブジェクトをフィルター処理します。ここで、 **name** プロパティは "\* Value" で、 **tagName** は "INPUT" になります。</span><span class="sxs-lookup"><span data-stu-id="143d4-116">The second command filters the objects in the **AllElements** property where the **name** property is like "\* Value" and the **tagName** is "INPUT".</span></span> <span data-ttu-id="143d4-117">フィルター処理された結果は、 `Select-Object` **名前** と **値** のプロパティを選択するためにパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="143d4-117">The filtered results are piped to `Select-Object` to select the **name** and **value** properties.</span></span>

### <span data-ttu-id="143d4-118">例 2: ステートフルな web サービスを使用する</span><span class="sxs-lookup"><span data-stu-id="143d4-118">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="143d4-119">この例では、 `Invoke-WebRequest` Facebook などのステートフルな web サービスでコマンドレットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="143d4-119">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service, such as Facebook.</span></span>

```powershell
$R = Invoke-WebRequest https://www.facebook.com/login.php -SessionVariable fb
# This command stores the first form in the Forms property of the $R variable in the $Form variable.
$Form = $R.Forms[0]
# This command shows the fields available in the Form.
$Form.fields
```

```Output
Key                     Value
---                     -----
...
email
pass
...
```

```powershell
# These commands populate the username and password of the respective Form fields.
$Form.Fields["email"]="User01@Fabrikam.com"
$Form.Fields["pass"]="P@ssw0rd"
# This command creates the Uri that will be used to log in to facebook.
# The value of the Uri parameter is the value of the Action property of the form.
$Uri = "https://www.facebook.com" + $Form.Action
# Now the Invoke-WebRequest cmdlet is used to sign into the Facebook web service.
# The WebRequestSession object in the $FB variable is passed as the value of the WebSession parameter.
# The value of the Body parameter is the hash table in the Fields property of the form.
# The value of the *Method* parameter is POST. The command saves the output in the $R variable.
$R = Invoke-WebRequest -Uri $Uri -WebSession $FB -Method POST -Body $Form.Fields
$R.StatusDescription
```

<span data-ttu-id="143d4-120">最初のコマンドは、 `Invoke-WebRequest` コマンドレットを使用してサインイン要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="143d4-120">The first command uses the `Invoke-WebRequest` cmdlet to send a sign-in request.</span></span> <span data-ttu-id="143d4-121">このコマンドは、 **Sessionvariable** パラメーターの値に "FB" という値を指定し、結果を変数に保存し `$R` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-121">The command specifies a value of "FB" for the value of the **SessionVariable** parameter, and saves the result in the `$R` variable.</span></span> <span data-ttu-id="143d4-122">コマンドが完了すると、 `$R` 変数に **Htmlwebresponseobject** が含まれ、変数には `$FB` **WebRequestSession** オブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="143d4-122">When the command completes, the `$R` variable contains an **HtmlWebResponseObject** and the `$FB` variable contains a **WebRequestSession** object.</span></span>

<span data-ttu-id="143d4-123">`Invoke-WebRequest`コマンドレットが facebook にサインインすると、変数内の web 応答オブジェクトの **statusdescription** プロパティは、 `$R` ユーザーが正常にサインインしたことを示します。</span><span class="sxs-lookup"><span data-stu-id="143d4-123">After the `Invoke-WebRequest` cmdlet signs in to facebook, the **StatusDescription** property of the web response object in the `$R` variable indicates that the user is signed in successfully.</span></span>

### <span data-ttu-id="143d4-124">例 3: web ページからリンクを取得する</span><span class="sxs-lookup"><span data-stu-id="143d4-124">Example 3: Get links from a web page</span></span>

<span data-ttu-id="143d4-125">このコマンドは、Web ページ内のリンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="143d4-125">This command gets the links in a web page.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

<span data-ttu-id="143d4-126">コマンドレットでは、 `Invoke-WebRequest` web ページの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="143d4-126">The `Invoke-WebRequest` cmdlet gets the web page content.</span></span> <span data-ttu-id="143d4-127">次に、返された **Htmlwebresponseobject** の **Links** プロパティを使用して、各リンクの **Href** プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="143d4-127">Then the **Links** property of the returned **HtmlWebResponseObject** is used to display the **Href** property of each link.</span></span>

### <span data-ttu-id="143d4-128">例 4: Invoke-WebRequest からの失敗したメッセージをキャッチする</span><span class="sxs-lookup"><span data-stu-id="143d4-128">Example 4: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="143d4-129">が `Invoke-WebRequest` 成功以外の HTTP メッセージ (404、500など) を検出すると、出力は返されず、終了エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="143d4-129">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="143d4-130">エラーをキャッチして **StatusCode** を表示するには、ブロックで実行を囲むことができ `try/catch` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-130">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span> <span data-ttu-id="143d4-131">次の例は、これを実現する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="143d4-131">The following example shows how to accomplish this.</span></span>

```powershell
try
{
    $Response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost"
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

<span data-ttu-id="143d4-132">終了エラーは、 `catch` **例外** オブジェクトから **StatusCode** を取得するブロックによってキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="143d4-132">The terminating error is caught by the `catch` block, which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="143d4-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="143d4-133">PARAMETERS</span></span>

### <span data-ttu-id="143d4-134">-本文</span><span class="sxs-lookup"><span data-stu-id="143d4-134">-Body</span></span>

<span data-ttu-id="143d4-135">要求の本文を指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-135">Specifies the body of the request.</span></span>
<span data-ttu-id="143d4-136">本文は、ヘッダーに続く要求の内容です。</span><span class="sxs-lookup"><span data-stu-id="143d4-136">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="143d4-137">パイプを使用して、本文の値をにパイプすることもでき `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-137">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="143d4-138">**Body** パラメーターを使用すると、クエリ パラメーターのリストを指定したり、応答の内容を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="143d4-138">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="143d4-139">入力が GET 要求で、本文が **IDictionary** (通常はハッシュテーブル) の場合、本文はクエリパラメーターとして URI に追加されます。</span><span class="sxs-lookup"><span data-stu-id="143d4-139">When the input is a GET request and the body is an **IDictionary** (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="143d4-140">他の GET 要求の場合、本文は標準形式の要求本文の値として設定され `name=value` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-140">For other GET requests, the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="143d4-141">本文がフォームである場合、または呼び出しの出力である場合 `Invoke-WebRequest` 、PowerShell は要求の内容をフォームフィールドに設定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-141">When the body is a form, or it is the output of an `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>
<span data-ttu-id="143d4-142">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="143d4-142">For example:</span></span>

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- <span data-ttu-id="143d4-143">または</span><span class="sxs-lookup"><span data-stu-id="143d4-143">or -</span></span>

`Invoke-RestMethod https://website.com/service.aspx -Body $r.Forms\[0\]`

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

### <span data-ttu-id="143d4-144">-証明書</span><span class="sxs-lookup"><span data-stu-id="143d4-144">-Certificate</span></span>

<span data-ttu-id="143d4-145">セキュリティで保護された Web 要求に使用するクライアント証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-145">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="143d4-146">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="143d4-146">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="143d4-147">証明書を検索するには、を使用する `Get-PfxCertificate` か、 `Get-ChildItem` **証明書** () ドライブのコマンドレットを使用し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-147">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the **Certificate** (`Cert:`) drive.</span></span> <span data-ttu-id="143d4-148">証明書が無効な場合、または証明書に十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="143d4-148">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="143d4-149">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="143d4-149">-CertificateThumbprint</span></span>

<span data-ttu-id="143d4-150">要求を送信するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-150">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="143d4-151">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="143d4-151">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="143d4-152">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="143d4-152">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="143d4-153">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="143d4-153">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="143d4-154">証明書の拇印を取得するに `Get-Item` は、PowerShell ドライブでまたはコマンドを使用し `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-154">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

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

### <span data-ttu-id="143d4-155">-ContentType</span><span class="sxs-lookup"><span data-stu-id="143d4-155">-ContentType</span></span>

<span data-ttu-id="143d4-156">Web 要求のコンテンツ タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-156">Specifies the content type of the web request.</span></span>

<span data-ttu-id="143d4-157">このパラメーターを省略して、要求メソッドが POST の場合は、 `Invoke-WebRequest` コンテンツの種類を application/url エンコードに設定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-157">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to application/x-www-form-urlencoded.</span></span> <span data-ttu-id="143d4-158">それ以外の場合、呼び出しの中でコンテンツ タイプは指定されません。</span><span class="sxs-lookup"><span data-stu-id="143d4-158">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="143d4-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="143d4-159">-Credential</span></span>

<span data-ttu-id="143d4-160">要求を送信するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-160">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="143d4-161">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="143d4-161">The default is the current user.</span></span>

<span data-ttu-id="143d4-162">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-162">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="143d4-163">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="143d4-163">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="143d4-164">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="143d4-164">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="143d4-165">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="143d4-165">-DisableKeepAlive</span></span>

<span data-ttu-id="143d4-166">コマンドレットが HTTP ヘッダーの **KeepAlive** 値を **False** に設定することを示します。</span><span class="sxs-lookup"><span data-stu-id="143d4-166">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False**.</span></span> <span data-ttu-id="143d4-167">既定では、 **KeepAlive** は **True** です。</span><span class="sxs-lookup"><span data-stu-id="143d4-167">By default, **KeepAlive** is **True**.</span></span> <span data-ttu-id="143d4-168">**KeepAlive** は、後続の要求を容易にするために、サーバーへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="143d4-168">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="143d4-169">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="143d4-169">-Headers</span></span>

<span data-ttu-id="143d4-170">Web 要求のヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-170">Specifies the headers of the web request.</span></span> <span data-ttu-id="143d4-171">ハッシュ テーブルまたは辞書を入力します。</span><span class="sxs-lookup"><span data-stu-id="143d4-171">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="143d4-172">**UserAgent** ヘッダーを設定するには、 **UserAgent** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="143d4-172">To set **UserAgent** headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="143d4-173">このパラメーターを使用して、 **UserAgent** または cookie のヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="143d4-173">You cannot use this parameter to specify **UserAgent** or cookie headers.</span></span>

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

### <span data-ttu-id="143d4-174">-InFile</span><span class="sxs-lookup"><span data-stu-id="143d4-174">-InFile</span></span>

<span data-ttu-id="143d4-175">ファイルから Web 要求の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="143d4-175">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="143d4-176">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="143d4-176">Enter a path and file name.</span></span> <span data-ttu-id="143d4-177">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="143d4-177">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="143d4-178">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="143d4-178">-MaximumRedirection</span></span>

<span data-ttu-id="143d4-179">接続に失敗する前に PowerShell が代替 Uniform Resource Identifier (URI) に接続をリダイレクトする回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-179">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="143d4-180">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="143d4-180">The default value is 5.</span></span> <span data-ttu-id="143d4-181">値 0 (ゼロ) を指定した場合、リダイレクトはまったく行われません。</span><span class="sxs-lookup"><span data-stu-id="143d4-181">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="143d4-182">-メソッド</span><span class="sxs-lookup"><span data-stu-id="143d4-182">-Method</span></span>

<span data-ttu-id="143d4-183">Web 要求に使用するメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-183">Specifies the method used for the web request.</span></span> <span data-ttu-id="143d4-184">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="143d4-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="143d4-185">Default</span><span class="sxs-lookup"><span data-stu-id="143d4-185">Default</span></span>
- <span data-ttu-id="143d4-186">削除</span><span class="sxs-lookup"><span data-stu-id="143d4-186">Delete</span></span>
- <span data-ttu-id="143d4-187">取得</span><span class="sxs-lookup"><span data-stu-id="143d4-187">Get</span></span>
- <span data-ttu-id="143d4-188">Head</span><span class="sxs-lookup"><span data-stu-id="143d4-188">Head</span></span>
- <span data-ttu-id="143d4-189">Merge</span><span class="sxs-lookup"><span data-stu-id="143d4-189">Merge</span></span>
- <span data-ttu-id="143d4-190">オプション</span><span class="sxs-lookup"><span data-stu-id="143d4-190">Options</span></span>
- <span data-ttu-id="143d4-191">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="143d4-191">Patch</span></span>
- <span data-ttu-id="143d4-192">投稿</span><span class="sxs-lookup"><span data-stu-id="143d4-192">Post</span></span>
- <span data-ttu-id="143d4-193">Put</span><span class="sxs-lookup"><span data-stu-id="143d4-193">Put</span></span>
- <span data-ttu-id="143d4-194">Trace</span><span class="sxs-lookup"><span data-stu-id="143d4-194">Trace</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: (All)
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="143d4-195">-出力</span><span class="sxs-lookup"><span data-stu-id="143d4-195">-OutFile</span></span>

<span data-ttu-id="143d4-196">このコマンドレットが応答本文を保存する出力ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-196">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="143d4-197">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="143d4-197">Enter a path and file name.</span></span>
<span data-ttu-id="143d4-198">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="143d4-198">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="143d4-199">既定では、は `Invoke-WebRequest` パイプラインに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="143d4-199">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="143d4-200">結果をファイルとパイプラインに送信するには、**Passthru** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="143d4-200">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="143d4-201">-PassThru</span><span class="sxs-lookup"><span data-stu-id="143d4-201">-PassThru</span></span>

<span data-ttu-id="143d4-202">コマンドレットがファイルに書き込むだけでなく、結果を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="143d4-202">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="143d4-203">このパラメーターは、同時に **OutFile** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="143d4-203">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="143d4-204">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="143d4-204">-Proxy</span></span>

<span data-ttu-id="143d4-205">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-205">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>
<span data-ttu-id="143d4-206">ネットワーク プロキシ サーバーの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="143d4-206">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="143d4-207">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="143d4-207">-ProxyCredential</span></span>

<span data-ttu-id="143d4-208">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-208">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="143d4-209">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="143d4-209">The default is the current user.</span></span>

<span data-ttu-id="143d4-210">またはなどのユーザー名を入力する `User01` `Domain01\User01` か、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-210">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="143d4-211">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="143d4-211">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="143d4-212">**ProxyCredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="143d4-212">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="143d4-213">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="143d4-213">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="143d4-214">コマンドレットが、 **プロキシ** パラメーターで指定されたプロキシサーバーにアクセスするために、現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="143d4-214">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="143d4-215">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="143d4-215">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="143d4-216">**ProxyCredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="143d4-216">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="143d4-217">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="143d4-217">-SessionVariable</span></span>

<span data-ttu-id="143d4-218">このコマンドレットによって web 要求セッションが作成され、値に保存される変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-218">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="143d4-219">ドル記号 () を付けずに変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-219">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="143d4-220">セッション変数を指定すると、は `Invoke-WebRequest` web 要求セッションオブジェクトを作成し、PowerShell セッション内の指定された名前の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="143d4-220">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="143d4-221">コマンドが完了すると、すぐに変数をセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="143d4-221">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="143d4-222">リモート セッションとは異なり、Web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="143d4-222">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="143d4-223">Web 要求セッションは、Cookie、資格情報、リダイレクトの最大値、ユーザー エージェント文字列などの、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="143d4-223">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="143d4-224">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="143d4-224">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="143d4-225">後続の Web 要求で Web 要求セッションを使用するには、**WebSession** パラメーターの値にセッション変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-225">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="143d4-226">PowerShell は、新しい接続を確立するときに、web 要求セッションオブジェクトのデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="143d4-226">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="143d4-227">Web 要求セッションの値をオーバーライドするには、**UserAgent**、**Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="143d4-227">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="143d4-228">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="143d4-228">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="143d4-229">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="143d4-229">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="143d4-230">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="143d4-230">-TimeoutSec</span></span>

<span data-ttu-id="143d4-231">要求がタイムアウトになるまでの待機時間を指定します。値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="143d4-231">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="143d4-232">既定値は 0 で、無制限のタイムアウトを意味しています。</span><span class="sxs-lookup"><span data-stu-id="143d4-232">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="143d4-233">ドメインネームシステム (DNS) クエリは、返されるまで最大15秒かかることがあります。要求に解決を必要とするホスト名が含まれていて、 **Timeoutsec** を0より大きく15秒未満に設定した場合、 **WebException** がスローされる前に15秒以上かかることがあり、要求はタイムアウトになります。</span><span class="sxs-lookup"><span data-stu-id="143d4-233">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a **WebException** is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="143d4-234">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="143d4-234">-TransferEncoding</span></span>

<span data-ttu-id="143d4-235">転送エンコード HTTP 応答ヘッダーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-235">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="143d4-236">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="143d4-236">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="143d4-237">まとめ</span><span class="sxs-lookup"><span data-stu-id="143d4-237">Chunked</span></span>
- <span data-ttu-id="143d4-238">圧縮</span><span class="sxs-lookup"><span data-stu-id="143d4-238">Compress</span></span>
- <span data-ttu-id="143d4-239">Deflate</span><span class="sxs-lookup"><span data-stu-id="143d4-239">Deflate</span></span>
- <span data-ttu-id="143d4-240">GZip</span><span class="sxs-lookup"><span data-stu-id="143d4-240">GZip</span></span>
- <span data-ttu-id="143d4-241">ID</span><span class="sxs-lookup"><span data-stu-id="143d4-241">Identity</span></span>

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

### <span data-ttu-id="143d4-242">-Uri</span><span class="sxs-lookup"><span data-stu-id="143d4-242">-Uri</span></span>

<span data-ttu-id="143d4-243">Web 要求の送信先の Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-243">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="143d4-244">URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="143d4-244">Enter a URI.</span></span> <span data-ttu-id="143d4-245">このパラメーターは、HTTP、HTTPS、FTP、FILE の値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="143d4-245">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="143d4-246">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="143d4-246">This parameter is required.</span></span>

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

### <span data-ttu-id="143d4-247">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="143d4-247">-UseBasicParsing</span></span>

<span data-ttu-id="143d4-248">コマンドレットがドキュメントオブジェクトモデル (DOM) 解析を行わずに、HTML コンテンツの応答オブジェクトを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="143d4-248">Indicates that the cmdlet uses the response object for HTML content without Document Object Model (DOM) parsing.</span></span> <span data-ttu-id="143d4-249">このパラメーターは、Windows Server オペレーティング システムの Server Core インストールなど、コンピューターに Internet Explorer がインストールされていない場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="143d4-249">This parameter is required when Internet Explorer is not installed on the computers, such as on a Server Core installation of a Windows Server operating system.</span></span>

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

### <span data-ttu-id="143d4-250">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="143d4-250">-UseDefaultCredentials</span></span>

<span data-ttu-id="143d4-251">Cmdet が、web 要求を送信するために現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="143d4-251">Indicates that the cmdet uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="143d4-252">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="143d4-252">-UserAgent</span></span>

<span data-ttu-id="143d4-253">Web 要求のユーザー エージェント文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-253">Specifies a user agent string for the web request.</span></span> <span data-ttu-id="143d4-254">既定のユーザーエージェントは、 `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` オペレーティングシステムとプラットフォームによって微妙な違いがあるに似ています。</span><span class="sxs-lookup"><span data-stu-id="143d4-254">The default user agent is similar to `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="143d4-255">ほとんどのインターネットブラウザーで使用される標準のユーザーエージェント文字列を使用して web サイトをテストするには、Chrome、FireFox、InternetExplorer、Opera、Safari などの [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) クラスのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="143d4-255">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span> <span data-ttu-id="143d4-256">たとえば、次のコマンドは、Internet Explorer のユーザーエージェント文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="143d4-256">For example, the following command uses the user agent string for Internet Explorer</span></span>

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

### <span data-ttu-id="143d4-257">-WebSession</span><span class="sxs-lookup"><span data-stu-id="143d4-257">-WebSession</span></span>

<span data-ttu-id="143d4-258">Web 要求セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="143d4-258">Specifies a web request session.</span></span> <span data-ttu-id="143d4-259">ドル記号 () を含む変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-259">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="143d4-260">Web 要求セッションの値をオーバーライドするには、**UserAgent**、**Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="143d4-260">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="143d4-261">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="143d4-261">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="143d4-262">リモート セッションとは異なり、Web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="143d4-262">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="143d4-263">Web 要求セッションは、Cookie、資格情報、リダイレクトの最大値、ユーザー エージェント文字列などの、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="143d4-263">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="143d4-264">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="143d4-264">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="143d4-265">Web 要求セッションを作成するには、コマンドの **Sessionvariable** パラメーターの値に、(ドル記号を付けずに) 変数名を入力し `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-265">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="143d4-266">`Invoke-WebRequest` セッションを作成し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="143d4-266">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="143d4-267">後続のコマンドで、この変数を **WebSession** パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="143d4-267">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="143d4-268">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="143d4-268">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="143d4-269">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="143d4-269">CommonParameters</span></span>

<span data-ttu-id="143d4-270">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-270">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="143d4-271">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="143d4-271">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="143d4-272">入力</span><span class="sxs-lookup"><span data-stu-id="143d4-272">INPUTS</span></span>

### <span data-ttu-id="143d4-273">System.Object</span><span class="sxs-lookup"><span data-stu-id="143d4-273">System.Object</span></span>

<span data-ttu-id="143d4-274">パイプを使用して、web 要求の本文をにパイプすることができ `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="143d4-274">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="143d4-275">出力</span><span class="sxs-lookup"><span data-stu-id="143d4-275">OUTPUTS</span></span>

### <span data-ttu-id="143d4-276">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span><span class="sxs-lookup"><span data-stu-id="143d4-276">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span></span>

## <span data-ttu-id="143d4-277">注</span><span class="sxs-lookup"><span data-stu-id="143d4-277">NOTES</span></span>

## <span data-ttu-id="143d4-278">関連リンク</span><span class="sxs-lookup"><span data-stu-id="143d4-278">RELATED LINKS</span></span>

[<span data-ttu-id="143d4-279">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="143d4-279">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="143d4-280">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="143d4-280">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="143d4-281">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="143d4-281">ConvertTo-Json</span></span>](ConvertTo-Json.md)

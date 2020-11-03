---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WebRequest
ms.openlocfilehash: 25da6262e93be3e3749aabaf4950e2fbcd91ff5c
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219227"
---
# <span data-ttu-id="f61ff-103">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="f61ff-103">Invoke-WebRequest</span></span>

## <span data-ttu-id="f61ff-104">概要</span><span class="sxs-lookup"><span data-stu-id="f61ff-104">SYNOPSIS</span></span>
<span data-ttu-id="f61ff-105">インターネット上の Web ページからコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-105">Gets content from a web page on the Internet.</span></span>

## <span data-ttu-id="f61ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f61ff-106">SYNTAX</span></span>

```
Invoke-WebRequest [-UseBasicParsing] [-Uri] <Uri> [-WebSession <WebRequestSession>] [-SessionVariable <String>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-CertificateThumbprint <String>]
 [-Certificate <X509Certificate>] [-UserAgent <String>] [-DisableKeepAlive] [-TimeoutSec <Int32>]
 [-Headers <IDictionary>] [-MaximumRedirection <Int32>] [-Method <WebRequestMethod>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>] [-ContentType <String>]
 [-TransferEncoding <String>] [-InFile <String>] [-OutFile <String>] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="f61ff-107">Description</span><span class="sxs-lookup"><span data-stu-id="f61ff-107">DESCRIPTION</span></span>

<span data-ttu-id="f61ff-108">`Invoke-WebRequest`コマンドレットは、HTTP、HTTPS、FTP、およびファイル要求を web ページまたは web サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-108">The `Invoke-WebRequest` cmdlet sends HTTP, HTTPS, FTP, and FILE requests to a web page or web service.</span></span>
<span data-ttu-id="f61ff-109">さらに、応答を解析し、フォーム、リンク、画像、およびその他の重要な HTML 要素のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-109">It parses the response and returns collections of forms, links, images, and other significant HTML elements.</span></span>

<span data-ttu-id="f61ff-110">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f61ff-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="f61ff-111">既定では、プロパティを設定するためにページを解析するときに、web ページ内のスクリプトコードが実行される場合があり `ParsedHtml` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-111">By default, script code in the web page may be run when the page is being parsed to populate the `ParsedHtml` property.</span></span>
> <span data-ttu-id="f61ff-112">`-UseBasicParsing`これを抑制するには、スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-112">Use the `-UseBasicParsing` switch to suppress this.</span></span>

## <span data-ttu-id="f61ff-113">例</span><span class="sxs-lookup"><span data-stu-id="f61ff-113">EXAMPLES</span></span>

### <span data-ttu-id="f61ff-114">例 1: web 要求を送信する</span><span class="sxs-lookup"><span data-stu-id="f61ff-114">Example 1: Send a web request</span></span>

<span data-ttu-id="f61ff-115">このコマンドは、コマンドレットを使用して、 `Invoke-WebRequest` web 要求を Bing.com サイトに送信します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-115">This command uses the `Invoke-WebRequest` cmdlet to send a web request to the Bing.com site.</span></span>

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

<span data-ttu-id="f61ff-116">最初のコマンドは、要求を発行し、その応答を変数に保存し `$R` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-116">The first command issues the request and saves the response in the `$R` variable.</span></span>

<span data-ttu-id="f61ff-117">2番目のコマンドは、 **Allelements** プロパティのオブジェクトをフィルター処理します。ここで、 **name** プロパティは "\* Value" で、 **tagName** は "INPUT" になります。</span><span class="sxs-lookup"><span data-stu-id="f61ff-117">The second command filters the objects in the **AllElements** property where the **name** property is like "\* Value" and the **tagName** is "INPUT".</span></span> <span data-ttu-id="f61ff-118">フィルター処理された結果は、 `Select-Object` **名前** と **値** のプロパティを選択するためにパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-118">The filtered results are piped to `Select-Object` to select the **name** and **value** properties.</span></span>

### <span data-ttu-id="f61ff-119">例 2: ステートフルな web サービスを使用する</span><span class="sxs-lookup"><span data-stu-id="f61ff-119">Example 2: Use a stateful web service</span></span>

<span data-ttu-id="f61ff-120">この例では、 `Invoke-WebRequest` Facebook などのステートフルな web サービスでコマンドレットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-120">This example shows how to use the `Invoke-WebRequest` cmdlet with a stateful web service, such as Facebook.</span></span>

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

<span data-ttu-id="f61ff-121">最初のコマンドは、 `Invoke-WebRequest` コマンドレットを使用してサインイン要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-121">The first command uses the `Invoke-WebRequest` cmdlet to send a sign-in request.</span></span> <span data-ttu-id="f61ff-122">このコマンドは、 **Sessionvariable** パラメーターの値に "FB" という値を指定し、結果を変数に保存し `$R` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-122">The command specifies a value of "FB" for the value of the **SessionVariable** parameter, and saves the result in the `$R` variable.</span></span> <span data-ttu-id="f61ff-123">コマンドが完了すると、 `$R` 変数に **Htmlwebresponseobject** が含まれ、変数には `$FB` **WebRequestSession** オブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-123">When the command completes, the `$R` variable contains an **HtmlWebResponseObject** and the `$FB` variable contains a **WebRequestSession** object.</span></span>

<span data-ttu-id="f61ff-124">`Invoke-WebRequest`コマンドレットが facebook にサインインすると、変数内の web 応答オブジェクトの **statusdescription** プロパティは、 `$R` ユーザーが正常にサインインしたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-124">After the `Invoke-WebRequest` cmdlet signs in to facebook, the **StatusDescription** property of the web response object in the `$R` variable indicates that the user is signed in successfully.</span></span>

### <span data-ttu-id="f61ff-125">例 3: web ページからリンクを取得する</span><span class="sxs-lookup"><span data-stu-id="f61ff-125">Example 3: Get links from a web page</span></span>

<span data-ttu-id="f61ff-126">このコマンドは、Web ページ内のリンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-126">This command gets the links in a web page.</span></span>

```powershell
(Invoke-WebRequest -Uri "https://devblogs.microsoft.com/powershell/").Links.Href
```

<span data-ttu-id="f61ff-127">コマンドレットでは、 `Invoke-WebRequest` web ページの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-127">The `Invoke-WebRequest` cmdlet gets the web page content.</span></span> <span data-ttu-id="f61ff-128">次に、返された **Htmlwebresponseobject** の **Links** プロパティを使用して、各リンクの **Href** プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-128">Then the **Links** property of the returned **HtmlWebResponseObject** is used to display the **Href** property of each link.</span></span>

### <span data-ttu-id="f61ff-129">例 4: Invoke-WebRequest からの失敗したメッセージをキャッチする</span><span class="sxs-lookup"><span data-stu-id="f61ff-129">Example 4: Catch non success messages from Invoke-WebRequest</span></span>

<span data-ttu-id="f61ff-130">が `Invoke-WebRequest` 成功以外の HTTP メッセージ (404、500など) を検出すると、出力は返されず、終了エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="f61ff-130">When `Invoke-WebRequest` encounters a non-success HTTP message (404, 500, etc.), it returns no output and throws a terminating error.</span></span> <span data-ttu-id="f61ff-131">エラーをキャッチして **StatusCode** を表示するには、ブロックで実行を囲むことができ `try/catch` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-131">To catch the error and view the **StatusCode** you can enclose execution in a `try/catch` block.</span></span> <span data-ttu-id="f61ff-132">次の例は、これを実現する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f61ff-132">The following example shows how to accomplish this.</span></span>

```powershell
try
{
    $response = Invoke-WebRequest -Uri "www.microsoft.com/unkownhost" -ErrorAction Stop
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

<span data-ttu-id="f61ff-133">最初のコマンドは、 `Invoke-WebRequest` **Stop** の **erroraction** を使用してを呼び出します。これにより、 `Invoke-WebRequest` は、失敗した要求に対して強制的に終了エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="f61ff-133">The first command calls `Invoke-WebRequest` with an **ErrorAction** of **Stop** , which forces `Invoke-WebRequest` to throw a terminating error on any failed requests.</span></span> <span data-ttu-id="f61ff-134">終了エラーは、 `catch` **例外** オブジェクトから **StatusCode** を取得するブロックによってキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-134">The terminating error is caught by the `catch` block which retrieves the **StatusCode** from the **Exception** object.</span></span>

## <span data-ttu-id="f61ff-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f61ff-135">PARAMETERS</span></span>

### <span data-ttu-id="f61ff-136">-本文</span><span class="sxs-lookup"><span data-stu-id="f61ff-136">-Body</span></span>

<span data-ttu-id="f61ff-137">要求の本文を指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-137">Specifies the body of the request.</span></span>
<span data-ttu-id="f61ff-138">本文は、ヘッダーに続く要求の内容です。</span><span class="sxs-lookup"><span data-stu-id="f61ff-138">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="f61ff-139">パイプを使用して、本文の値をにパイプすることもでき `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-139">You can also pipe a body value to `Invoke-WebRequest`.</span></span>

<span data-ttu-id="f61ff-140">**Body** パラメーターを使用すると、クエリ パラメーターのリストを指定したり、応答の内容を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-140">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="f61ff-141">入力が GET 要求で、本文が **IDictionary** (通常はハッシュテーブル) の場合、本文はクエリパラメーターとして URI に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-141">When the input is a GET request and the body is an **IDictionary** (typically, a hash table), the body is added to the URI as query parameters.</span></span> <span data-ttu-id="f61ff-142">他の GET 要求の場合、本文は標準形式の要求本文の値として設定され `name=value` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-142">For other GET requests, the body is set as the value of the request body in the standard `name=value` format.</span></span>

<span data-ttu-id="f61ff-143">本文がフォームである場合、または呼び出しの出力である場合 `Invoke-WebRequest` 、PowerShell は要求の内容をフォームフィールドに設定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-143">When the body is a form, or it is the output of an `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>
<span data-ttu-id="f61ff-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-144">For example:</span></span>

`$r = Invoke-WebRequest https://website.com/login.aspx`
`$r.Forms\[0\].Name = "MyName"`
`$r.Forms\[0\].Password = "MyPassword"`
`Invoke-RestMethod https://website.com/service.aspx -Body $r`

- <span data-ttu-id="f61ff-145">または</span><span class="sxs-lookup"><span data-stu-id="f61ff-145">or -</span></span>

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

### <span data-ttu-id="f61ff-146">-証明書</span><span class="sxs-lookup"><span data-stu-id="f61ff-146">-Certificate</span></span>

<span data-ttu-id="f61ff-147">セキュリティで保護された Web 要求に使用するクライアント証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-147">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="f61ff-148">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-148">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="f61ff-149">証明書を検索するには、を使用する `Get-PfxCertificate` か、 `Get-ChildItem` **証明書** () ドライブのコマンドレットを使用し `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-149">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the **Certificate** (`Cert:`) drive.</span></span> <span data-ttu-id="f61ff-150">証明書が無効な場合、または証明書に十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-150">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="f61ff-151">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="f61ff-151">-CertificateThumbprint</span></span>

<span data-ttu-id="f61ff-152">要求を送信するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-152">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="f61ff-153">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-153">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="f61ff-154">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-154">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="f61ff-155">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-155">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="f61ff-156">証明書の拇印を取得するに `Get-Item` は、PowerShell ドライブでまたはコマンドを使用し `Get-ChildItem` `Cert:` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-156">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

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

### <span data-ttu-id="f61ff-157">-ContentType</span><span class="sxs-lookup"><span data-stu-id="f61ff-157">-ContentType</span></span>

<span data-ttu-id="f61ff-158">Web 要求のコンテンツ タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-158">Specifies the content type of the web request.</span></span>

<span data-ttu-id="f61ff-159">このパラメーターを省略して、要求メソッドが POST の場合は、 `Invoke-WebRequest` コンテンツの種類を application/url エンコードに設定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-159">If this parameter is omitted and the request method is POST, `Invoke-WebRequest` sets the content type to application/x-www-form-urlencoded.</span></span> <span data-ttu-id="f61ff-160">それ以外の場合、呼び出しの中でコンテンツ タイプは指定されません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-160">Otherwise, the content type is not specified in the call.</span></span>

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

### <span data-ttu-id="f61ff-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="f61ff-161">-Credential</span></span>

<span data-ttu-id="f61ff-162">要求を送信するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-162">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="f61ff-163">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="f61ff-163">The default is the current user.</span></span>

<span data-ttu-id="f61ff-164">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-164">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="f61ff-165">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-165">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="f61ff-166">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61ff-166">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="f61ff-167">-DisableKeepAlive</span><span class="sxs-lookup"><span data-stu-id="f61ff-167">-DisableKeepAlive</span></span>

<span data-ttu-id="f61ff-168">コマンドレットが HTTP ヘッダーの **KeepAlive** 値を **False** に設定することを示します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-168">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False**.</span></span> <span data-ttu-id="f61ff-169">既定では、 **KeepAlive** は **True** です。</span><span class="sxs-lookup"><span data-stu-id="f61ff-169">By default, **KeepAlive** is **True**.</span></span> <span data-ttu-id="f61ff-170">**KeepAlive** は、後続の要求を容易にするために、サーバーへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-170">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

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

### <span data-ttu-id="f61ff-171">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f61ff-171">-Headers</span></span>

<span data-ttu-id="f61ff-172">Web 要求のヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-172">Specifies the headers of the web request.</span></span> <span data-ttu-id="f61ff-173">ハッシュ テーブルまたは辞書を入力します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-173">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="f61ff-174">**UserAgent** ヘッダーを設定するには、 **UserAgent** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-174">To set **UserAgent** headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="f61ff-175">このパラメーターを使用して、 **UserAgent** または cookie のヘッダーを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-175">You cannot use this parameter to specify **UserAgent** or cookie headers.</span></span>

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

### <span data-ttu-id="f61ff-176">-InFile</span><span class="sxs-lookup"><span data-stu-id="f61ff-176">-InFile</span></span>

<span data-ttu-id="f61ff-177">ファイルから Web 要求の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-177">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="f61ff-178">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-178">Enter a path and file name.</span></span> <span data-ttu-id="f61ff-179">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="f61ff-179">If you omit the path, the default is the current location.</span></span>

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

### <span data-ttu-id="f61ff-180">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="f61ff-180">-MaximumRedirection</span></span>

<span data-ttu-id="f61ff-181">接続に失敗する前に PowerShell が代替 Uniform Resource Identifier (URI) に接続をリダイレクトする回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-181">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="f61ff-182">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="f61ff-182">The default value is 5.</span></span> <span data-ttu-id="f61ff-183">値 0 (ゼロ) を指定した場合、リダイレクトはまったく行われません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-183">A value of 0 (zero) prevents all redirection.</span></span>

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

### <span data-ttu-id="f61ff-184">-メソッド</span><span class="sxs-lookup"><span data-stu-id="f61ff-184">-Method</span></span>

<span data-ttu-id="f61ff-185">Web 要求に使用するメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-185">Specifies the method used for the web request.</span></span> <span data-ttu-id="f61ff-186">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f61ff-186">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f61ff-187">Default</span><span class="sxs-lookup"><span data-stu-id="f61ff-187">Default</span></span>
- <span data-ttu-id="f61ff-188">削除</span><span class="sxs-lookup"><span data-stu-id="f61ff-188">Delete</span></span>
- <span data-ttu-id="f61ff-189">取得</span><span class="sxs-lookup"><span data-stu-id="f61ff-189">Get</span></span>
- <span data-ttu-id="f61ff-190">Head</span><span class="sxs-lookup"><span data-stu-id="f61ff-190">Head</span></span>
- <span data-ttu-id="f61ff-191">Merge</span><span class="sxs-lookup"><span data-stu-id="f61ff-191">Merge</span></span>
- <span data-ttu-id="f61ff-192">オプション</span><span class="sxs-lookup"><span data-stu-id="f61ff-192">Options</span></span>
- <span data-ttu-id="f61ff-193">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="f61ff-193">Patch</span></span>
- <span data-ttu-id="f61ff-194">投稿</span><span class="sxs-lookup"><span data-stu-id="f61ff-194">Post</span></span>
- <span data-ttu-id="f61ff-195">Put</span><span class="sxs-lookup"><span data-stu-id="f61ff-195">Put</span></span>
- <span data-ttu-id="f61ff-196">Trace</span><span class="sxs-lookup"><span data-stu-id="f61ff-196">Trace</span></span>

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

### <span data-ttu-id="f61ff-197">-出力</span><span class="sxs-lookup"><span data-stu-id="f61ff-197">-OutFile</span></span>

<span data-ttu-id="f61ff-198">このコマンドレットが応答本文を保存する出力ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-198">Specifies the output file for which this cmdlet saves the response body.</span></span> <span data-ttu-id="f61ff-199">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-199">Enter a path and file name.</span></span>
<span data-ttu-id="f61ff-200">パスを省略した場合、既定値は現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="f61ff-200">If you omit the path, the default is the current location.</span></span>

<span data-ttu-id="f61ff-201">既定では、は `Invoke-WebRequest` パイプラインに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-201">By default, `Invoke-WebRequest` returns the results to the pipeline.</span></span> <span data-ttu-id="f61ff-202">結果をファイルとパイプラインに送信するには、 **Passthru** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-202">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="f61ff-203">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f61ff-203">-PassThru</span></span>

<span data-ttu-id="f61ff-204">コマンドレットがファイルに書き込むだけでなく、結果を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-204">Indicates that the cmdlet returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="f61ff-205">このパラメーターは、同時に **OutFile** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="f61ff-205">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

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

### <span data-ttu-id="f61ff-206">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="f61ff-206">-Proxy</span></span>

<span data-ttu-id="f61ff-207">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-207">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>
<span data-ttu-id="f61ff-208">ネットワーク プロキシ サーバーの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-208">Enter the URI of a network proxy server.</span></span>

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

### <span data-ttu-id="f61ff-209">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="f61ff-209">-ProxyCredential</span></span>

<span data-ttu-id="f61ff-210">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-210">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="f61ff-211">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="f61ff-211">The default is the current user.</span></span>

<span data-ttu-id="f61ff-212">またはなどのユーザー名を入力する `User01` `Domain01\User01` か、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-212">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="f61ff-213">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="f61ff-213">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="f61ff-214">**ProxyCredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-214">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="f61ff-215">-ProxyUseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="f61ff-215">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="f61ff-216">コマンドレットが、 **プロキシ** パラメーターで指定されたプロキシサーバーにアクセスするために、現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-216">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="f61ff-217">このパラメーターは、 **プロキシ** パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="f61ff-217">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="f61ff-218">**ProxyCredential** パラメーターと **ProxyUseDefaultCredentials** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-218">You cannot use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

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

### <span data-ttu-id="f61ff-219">-SessionVariable</span><span class="sxs-lookup"><span data-stu-id="f61ff-219">-SessionVariable</span></span>

<span data-ttu-id="f61ff-220">このコマンドレットによって web 要求セッションが作成され、値に保存される変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-220">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="f61ff-221">ドル記号 () を付けずに変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-221">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="f61ff-222">セッション変数を指定すると、は `Invoke-WebRequest` web 要求セッションオブジェクトを作成し、PowerShell セッション内の指定された名前の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-222">When you specify a session variable, `Invoke-WebRequest` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="f61ff-223">コマンドが完了すると、すぐに変数をセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-223">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="f61ff-224">リモート セッションとは異なり、Web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-224">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="f61ff-225">Web 要求セッションは、Cookie、資格情報、リダイレクトの最大値、ユーザー エージェント文字列などの、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f61ff-225">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="f61ff-226">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-226">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="f61ff-227">後続の Web 要求で Web 要求セッションを使用するには、 **WebSession** パラメーターの値にセッション変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-227">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="f61ff-228">PowerShell は、新しい接続を確立するときに、web 要求セッションオブジェクトのデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-228">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="f61ff-229">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-229">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="f61ff-230">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-230">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="f61ff-231">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-231">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="f61ff-232">-TimeoutSec</span><span class="sxs-lookup"><span data-stu-id="f61ff-232">-TimeoutSec</span></span>

<span data-ttu-id="f61ff-233">要求がタイムアウトになるまでの待機時間を指定します。値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-233">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="f61ff-234">既定値は 0 で、無制限のタイムアウトを意味しています。</span><span class="sxs-lookup"><span data-stu-id="f61ff-234">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="f61ff-235">ドメインネームシステム (DNS) クエリは、返されるまで最大15秒かかることがあります。要求に解決を必要とするホスト名が含まれていて、 **Timeoutsec** を0より大きく15秒未満に設定した場合、 **WebException** がスローされる前に15秒以上かかることがあり、要求はタイムアウトになります。</span><span class="sxs-lookup"><span data-stu-id="f61ff-235">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a **WebException** is thrown, and your request times out.</span></span>

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

### <span data-ttu-id="f61ff-236">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="f61ff-236">-TransferEncoding</span></span>

<span data-ttu-id="f61ff-237">転送エンコード HTTP 応答ヘッダーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-237">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="f61ff-238">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f61ff-238">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f61ff-239">まとめ</span><span class="sxs-lookup"><span data-stu-id="f61ff-239">Chunked</span></span>
- <span data-ttu-id="f61ff-240">圧縮</span><span class="sxs-lookup"><span data-stu-id="f61ff-240">Compress</span></span>
- <span data-ttu-id="f61ff-241">Deflate</span><span class="sxs-lookup"><span data-stu-id="f61ff-241">Deflate</span></span>
- <span data-ttu-id="f61ff-242">GZip</span><span class="sxs-lookup"><span data-stu-id="f61ff-242">GZip</span></span>
- <span data-ttu-id="f61ff-243">ID</span><span class="sxs-lookup"><span data-stu-id="f61ff-243">Identity</span></span>

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

### <span data-ttu-id="f61ff-244">-Uri</span><span class="sxs-lookup"><span data-stu-id="f61ff-244">-Uri</span></span>

<span data-ttu-id="f61ff-245">Web 要求の送信先の Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-245">Specifies the Uniform Resource Identifier (URI) of the Internet resource to which the web request is sent.</span></span> <span data-ttu-id="f61ff-246">URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-246">Enter a URI.</span></span> <span data-ttu-id="f61ff-247">このパラメーターは、HTTP、HTTPS、FTP、FILE の値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f61ff-247">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="f61ff-248">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="f61ff-248">This parameter is required.</span></span>

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

### <span data-ttu-id="f61ff-249">-UseBasicParsing</span><span class="sxs-lookup"><span data-stu-id="f61ff-249">-UseBasicParsing</span></span>

<span data-ttu-id="f61ff-250">コマンドレットがドキュメントオブジェクトモデル (DOM) 解析を行わずに、HTML コンテンツの応答オブジェクトを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-250">Indicates that the cmdlet uses the response object for HTML content without Document Object Model (DOM) parsing.</span></span> <span data-ttu-id="f61ff-251">このパラメーターは、Windows Server オペレーティング システムの Server Core インストールなど、コンピューターに Internet Explorer がインストールされていない場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="f61ff-251">This parameter is required when Internet Explorer is not installed on the computers, such as on a Server Core installation of a Windows Server operating system.</span></span>

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

### <span data-ttu-id="f61ff-252">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="f61ff-252">-UseDefaultCredentials</span></span>

<span data-ttu-id="f61ff-253">Cmdet が、web 要求を送信するために現在のユーザーの資格情報を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-253">Indicates that the cmdet uses the credentials of the current user to send the web request.</span></span>

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

### <span data-ttu-id="f61ff-254">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="f61ff-254">-UserAgent</span></span>

<span data-ttu-id="f61ff-255">Web 要求のユーザー エージェント文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-255">Specifies a user agent string for the web request.</span></span> <span data-ttu-id="f61ff-256">既定のユーザーエージェントは、 `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` オペレーティングシステムとプラットフォームによって微妙な違いがあるに似ています。</span><span class="sxs-lookup"><span data-stu-id="f61ff-256">The default user agent is similar to `Mozilla/5.0 (Windows NT; Windows NT 6.1; en-US) WindowsPowerShell/3.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="f61ff-257">ほとんどのインターネットブラウザーで使用される標準のユーザーエージェント文字列を使用して web サイトをテストするには、Chrome、FireFox、InternetExplorer、Opera、Safari などの [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) クラスのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-257">To test a website with the standard user agent string that is used by most Internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span> <span data-ttu-id="f61ff-258">たとえば、次のコマンドは、Internet Explorer のユーザーエージェント文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-258">For example, the following command uses the user agent string for Internet Explorer</span></span>

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

### <span data-ttu-id="f61ff-259">-WebSession</span><span class="sxs-lookup"><span data-stu-id="f61ff-259">-WebSession</span></span>

<span data-ttu-id="f61ff-260">Web 要求セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-260">Specifies a web request session.</span></span> <span data-ttu-id="f61ff-261">ドル記号 () を含む変数名を入力し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-261">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="f61ff-262">Web 要求セッションの値をオーバーライドするには、 **UserAgent** 、 **Credential** などのコマンドレット パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-262">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="f61ff-263">パラメーターの値は、Web 要求セッションの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-263">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="f61ff-264">リモート セッションとは異なり、Web 要求セッションは永続的な接続ではありません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-264">Unlike a remote session, the web request session is not a persistent connection.</span></span> <span data-ttu-id="f61ff-265">Web 要求セッションは、Cookie、資格情報、リダイレクトの最大値、ユーザー エージェント文字列などの、接続と要求に関する情報を含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f61ff-265">It is an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="f61ff-266">Web 要求セッションを使用して、Web 要求の間で状態とデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-266">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="f61ff-267">Web 要求セッションを作成するには、コマンドの **Sessionvariable** パラメーターの値に、(ドル記号を付けずに) 変数名を入力し `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-267">To create a web request session, enter a variable name (without a dollar sign) in the value of the **SessionVariable** parameter of an `Invoke-WebRequest` command.</span></span> <span data-ttu-id="f61ff-268">`Invoke-WebRequest` セッションを作成し、変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-268">`Invoke-WebRequest` creates the session and saves it in the variable.</span></span> <span data-ttu-id="f61ff-269">後続のコマンドで、この変数を **WebSession** パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="f61ff-269">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="f61ff-270">**Sessionvariable** と **websession** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f61ff-270">You cannot use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

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

### <span data-ttu-id="f61ff-271">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f61ff-271">CommonParameters</span></span>

<span data-ttu-id="f61ff-272">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-272">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="f61ff-273">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61ff-273">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f61ff-274">入力</span><span class="sxs-lookup"><span data-stu-id="f61ff-274">INPUTS</span></span>

### <span data-ttu-id="f61ff-275">System.Object</span><span class="sxs-lookup"><span data-stu-id="f61ff-275">System.Object</span></span>

<span data-ttu-id="f61ff-276">パイプを使用して、web 要求の本文をにパイプすることができ `Invoke-WebRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="f61ff-276">You can pipe the body of a web request to `Invoke-WebRequest`.</span></span>

## <span data-ttu-id="f61ff-277">出力</span><span class="sxs-lookup"><span data-stu-id="f61ff-277">OUTPUTS</span></span>

### <span data-ttu-id="f61ff-278">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span><span class="sxs-lookup"><span data-stu-id="f61ff-278">Microsoft.PowerShell.Commands.HtmlWebResponseObject</span></span>

## <span data-ttu-id="f61ff-279">注</span><span class="sxs-lookup"><span data-stu-id="f61ff-279">NOTES</span></span>

## <span data-ttu-id="f61ff-280">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f61ff-280">RELATED LINKS</span></span>

[<span data-ttu-id="f61ff-281">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="f61ff-281">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="f61ff-282">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="f61ff-282">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="f61ff-283">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="f61ff-283">ConvertTo-Json</span></span>](ConvertTo-Json.md)

---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 03/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmaninstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManInstance
ms.openlocfilehash: cab18c513be5427f06165ae0558ad87653d23e35
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218576"
---
# <span data-ttu-id="9fc9b-103">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9fc9b-103">New-WSManInstance</span></span>

## <span data-ttu-id="9fc9b-104">概要</span><span class="sxs-lookup"><span data-stu-id="9fc9b-104">SYNOPSIS</span></span>
<span data-ttu-id="9fc9b-105">管理リソースの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-105">Creates a new instance of a management resource.</span></span>

## <span data-ttu-id="9fc9b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9fc9b-106">SYNTAX</span></span>

### <span data-ttu-id="9fc9b-107">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="9fc9b-107">ComputerName (Default)</span></span>

```
New-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable>
 [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="9fc9b-108">URI</span><span class="sxs-lookup"><span data-stu-id="9fc9b-108">URI</span></span>

```
New-WSManInstance [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="9fc9b-109">Description</span><span class="sxs-lookup"><span data-stu-id="9fc9b-109">DESCRIPTION</span></span>

<span data-ttu-id="9fc9b-110">コマンドレットでは、 `New-WSManInstance` 管理リソースの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-110">The `New-WSManInstance` cmdlet creates a new instance of a management resource.</span></span> <span data-ttu-id="9fc9b-111">リソース URI と値セットまたは入力ファイルを使用して、管理リソースの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-111">It uses a resource URI and a value set or input file to create the new instance of the management resource.</span></span>

<span data-ttu-id="9fc9b-112">このコマンドレットは、WinRM の接続/トランスポート層を使用して、管理リソースのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-112">This cmdlet uses the WinRM connection/transport layer to create the management resource instance.</span></span>

## <span data-ttu-id="9fc9b-113">例</span><span class="sxs-lookup"><span data-stu-id="9fc9b-113">EXAMPLES</span></span>

### <span data-ttu-id="9fc9b-114">例 1: HTTPS リスナーを作成する</span><span class="sxs-lookup"><span data-stu-id="9fc9b-114">Example 1: Create a HTTPS listener</span></span>

<span data-ttu-id="9fc9b-115">このコマンドは、すべての IP アドレスの WS-Management HTTPS リスナーのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-115">This command creates an instance of a WS-Management HTTPS listener on all IP addresses.</span></span>

```powershell
New-WSManInstance winrm/config/Listener -SelectorSet @{Transport='HTTPS'; Address='*'} -ValueSet @{Hostname="HOST";CertificateThumbprint="XXXXXXXXXX"}
```

## <span data-ttu-id="9fc9b-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9fc9b-116">PARAMETERS</span></span>

### <span data-ttu-id="9fc9b-117">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="9fc9b-117">-ApplicationName</span></span>

<span data-ttu-id="9fc9b-118">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-118">Specifies the application name in the connection.</span></span> <span data-ttu-id="9fc9b-119">**ApplicationName** パラメーターの既定値は **WSMAN** です。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-119">The default value of the **ApplicationName** parameter is **WSMAN**.</span></span> <span data-ttu-id="9fc9b-120">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-120">The complete identifier for the remote endpoint is in the following format:</span></span>

`<transport>://<server>:<port>/<ApplicationName>`

<span data-ttu-id="9fc9b-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-121">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="9fc9b-122">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span> <span data-ttu-id="9fc9b-123">この **WSMAN** の既定の設定は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-123">This default setting of **WSMAN** is appropriate for most uses.</span></span> <span data-ttu-id="9fc9b-124">このパラメーターは、Windows PowerShell を実行している 1 台のコンピューターに多数のコンピューターからリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-124">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span> <span data-ttu-id="9fc9b-125">この場合、IIS は効率を上げるために Web Services for Management (WS-MANAGEMENT) をホストします。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: Wsman
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-126">-認証</span><span class="sxs-lookup"><span data-stu-id="9fc9b-126">-Authentication</span></span>

<span data-ttu-id="9fc9b-127">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-127">Specifies the authentication mechanism to be used at the server.</span></span> <span data-ttu-id="9fc9b-128">次のいずれかの値になります。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-128">Possible values are:</span></span>

- <span data-ttu-id="9fc9b-129">Basic: Basic は、ユーザー名とパスワードがクリアテキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-129">Basic: Basic is a scheme in which the username and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="9fc9b-130">既定値: WS-Management プロトコルによって実装される認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-130">Default: Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="9fc9b-131">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-131">This is the default.</span></span>
- <span data-ttu-id="9fc9b-132">ダイジェスト: ダイジェストは、サーバーで指定されたデータ文字列をチャレンジに使用するチャレンジ/レスポンススキームです。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-132">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="9fc9b-133">Kerberos: クライアントコンピューターとサーバーは、Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-133">Kerberos: The client computer and the server mutually authenticate using Kerberos certificates.</span></span>
- <span data-ttu-id="9fc9b-134">Negotiate: Negotiate は、認証に使用するスキームを決定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンススキームです。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-134">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="9fc9b-135">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されるかを特定するネゴシエーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-135">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="9fc9b-136">CredSSP: Credential Security Support Provider (CredSSP) 認証を使用します。これにより、ユーザーは資格情報を委任できます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-136">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="9fc9b-137">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-137">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

> [!CAUTION]
> <span data-ttu-id="9fc9b-138">CredSSP では、ユーザーの資格情報がローカル コンピューターからリモート コンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-138">CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="9fc9b-139">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-139">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="9fc9b-140">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-140">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-141">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="9fc9b-141">-CertificateThumbprint</span></span>

<span data-ttu-id="9fc9b-142">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-142">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="9fc9b-143">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="9fc9b-144">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="9fc9b-145">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="9fc9b-146">証明書の拇印を取得するに `Get-Item` は、PowerShell Cert: ドライブのまたはコマンドを使用し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="9fc9b-147">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9fc9b-147">-ComputerName</span></span>

<span data-ttu-id="9fc9b-148">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-148">Specifies the computer against which you want to run the management operation.</span></span> <span data-ttu-id="9fc9b-149">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-149">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="9fc9b-150">ローカルコンピューター名を使用するか、localhost を使用するか、ドット () を使用し `.` てローカルコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-150">Use the local computer name, use localhost, or use a dot (`.`) to specify the local computer.</span></span> <span data-ttu-id="9fc9b-151">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-151">The local computer is the default.</span></span> <span data-ttu-id="9fc9b-152">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-152">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span> <span data-ttu-id="9fc9b-153">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-153">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-154">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="9fc9b-154">-ConnectionURI</span></span>

<span data-ttu-id="9fc9b-155">接続エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-155">Specifies the connection endpoint.</span></span>
<span data-ttu-id="9fc9b-156">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-156">The format of this string is:</span></span>

`<Transport>://<Server>:<Port>/<ApplicationName>`

<span data-ttu-id="9fc9b-157">次の文字列は、このパラメーターの正しい形式の値です。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-157">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="9fc9b-158">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-158">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="9fc9b-159">-Credential</span></span>

<span data-ttu-id="9fc9b-160">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-160">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="9fc9b-161">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-161">The default is the current user.</span></span> <span data-ttu-id="9fc9b-162">"User01"、"Domain01\user01」"、"" などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-162">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span> <span data-ttu-id="9fc9b-163">または、コマンドレットによって返されるような PSCredential オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-163">Or, enter a PSCredential object, such as one returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="9fc9b-164">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-164">When you type a user name, you will be prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-165">-FilePath</span><span class="sxs-lookup"><span data-stu-id="9fc9b-165">-FilePath</span></span>

<span data-ttu-id="9fc9b-166">管理リソースの作成に使用するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-166">Specifies the path of a file that is used to create a management resource.</span></span> <span data-ttu-id="9fc9b-167">管理リソースは、 **ResourceURI** パラメーターと **SelectorSet** パラメーターを使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-167">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter .</span></span> <span data-ttu-id="9fc9b-168">たとえば、次のコマンドは、 **File** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-168">For example, the following command uses the **File** parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmi/cimv2/Win32_Service -SelectorSet @{Name="spooler"} -File c:\input.xml -Authentication Default`

<span data-ttu-id="9fc9b-169">このコマンドは、ファイルからの入力を使用してスプーラサービスの **stopservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-169">This command calls the **StopService** method on the Spooler service using input from a file.</span></span> <span data-ttu-id="9fc9b-170">ファイルには、 `Input.xml` 次のコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-170">The file, `Input.xml`, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-171">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="9fc9b-171">-OptionSet</span></span>

<span data-ttu-id="9fc9b-172">要求のオプションを変更または調整する一連のスイッチをサービスに渡します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-172">Passes a set of switches to a service to modify or refine the nature of the request.</span></span> <span data-ttu-id="9fc9b-173">これらは、サービス固有であるため、コマンド ライン シェルで使用されるスイッチに似ています。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-173">These are similar to switches used in command-line shells because they are service specific.</span></span> <span data-ttu-id="9fc9b-174">任意の数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-174">Any number of options can be specified.</span></span>

<span data-ttu-id="9fc9b-175">次の例では、a、b、および c パラメーターに値 1、2、および 3 を渡す構文を示します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-175">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-176">-Port</span><span class="sxs-lookup"><span data-stu-id="9fc9b-176">-Port</span></span>

<span data-ttu-id="9fc9b-177">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-177">Specifies the port to use when the client connects to the WinRM service.</span></span> <span data-ttu-id="9fc9b-178">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-178">When the transport is HTTP, the default port is 80.</span></span> <span data-ttu-id="9fc9b-179">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-179">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="9fc9b-180">HTTPS をトランスポートとして使用する場合は、 **ComputerName** パラメーターの値がサーバーの証明書共通名 (CN) と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-180">When you use HTTPS as the transport, the value of the **ComputerName** parameter must match the server's certificate common name (CN).</span></span> <span data-ttu-id="9fc9b-181">ただし、 **Sessionoption** パラメーターの一部として **skipcncheck** パラメーターを指定した場合、サーバーの証明書の共通名がサーバーのホスト名と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-181">However, if the **SkipCNCheck** parameter is specified as part of the **SessionOption** parameter, the certificate common name of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="9fc9b-182">**Skipcncheck** パラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-182">The **SkipCNCheck** parameter should be used only for trusted computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-183">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="9fc9b-183">-ResourceURI</span></span>

<span data-ttu-id="9fc9b-184">リソース クラスまたはインスタンスの Uniform Resource Identifier (URI) を含めます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-184">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="9fc9b-185">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-185">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="9fc9b-186">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-186">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="9fc9b-187">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-187">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-188">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="9fc9b-188">-SelectorSet</span></span>

<span data-ttu-id="9fc9b-189">特定の管理リソース インスタンスの選択に使用する値のペアのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-189">Specifies a set of value pairs that are used to select particular management resource instances.</span></span> <span data-ttu-id="9fc9b-190">**SelectorSet** パラメーターは、リソースの複数のインスタンスが存在する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-190">The **SelectorSet** parameter is used when more than one instance of the resource exists.</span></span> <span data-ttu-id="9fc9b-191">**SelectorSet** パラメーターの値は、ハッシュテーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-191">The value of the **SelectorSet** parameter must be a hash table.</span></span>

<span data-ttu-id="9fc9b-192">次の例では、このパラメーターの値を入力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-192">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-193">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="9fc9b-193">-SessionOption</span></span>

<span data-ttu-id="9fc9b-194">WS-Management セッションの一連の拡張オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-194">Defines a set of extended options for the WS-Management session.</span></span> <span data-ttu-id="9fc9b-195">コマンドレットを使用して作成する **Sessionoption** オブジェクトを入力し `New-WSManSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-195">Enter a **SessionOption** object that you create using the `New-WSManSessionOption` cmdlet.</span></span> <span data-ttu-id="9fc9b-196">使用可能なオプションの詳細については、「」を参照してください `New-WSManSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-196">For more information about the options that are available, see `New-WSManSessionOption`.</span></span>

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: so

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-197">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="9fc9b-197">-UseSSL</span></span>

<span data-ttu-id="9fc9b-198">Secure Sockets Layer (SSL) プロトコルを使用してリモート コンピューターとの接続を確立するように指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-198">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="9fc9b-199">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-199">By default, SSL is not used.</span></span>

<span data-ttu-id="9fc9b-200">WS-Management は、ネットワークを介して転送されるすべての Windows PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-200">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="9fc9b-201">**UseSSL** パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-201">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="9fc9b-202">接続に使用するポートで SSL を使用できない場合に、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-202">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-203">-ValueSet</span><span class="sxs-lookup"><span data-stu-id="9fc9b-203">-ValueSet</span></span>

<span data-ttu-id="9fc9b-204">管理リソースの変更に役立つハッシュ テーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-204">Specifies a hash table that helps modify a management resource.</span></span> <span data-ttu-id="9fc9b-205">管理リソースは、 **ResourceURI** パラメーターと **SelectorSet** パラメーターを使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-205">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter.</span></span> <span data-ttu-id="9fc9b-206">**Valueset** パラメーターの値は、ハッシュテーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-206">The value of the **ValueSet** parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fc9b-207">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9fc9b-207">CommonParameters</span></span>

<span data-ttu-id="9fc9b-208">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9fc9b-209">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-209">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9fc9b-210">入力</span><span class="sxs-lookup"><span data-stu-id="9fc9b-210">INPUTS</span></span>

### <span data-ttu-id="9fc9b-211">なし</span><span class="sxs-lookup"><span data-stu-id="9fc9b-211">None</span></span>

<span data-ttu-id="9fc9b-212">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-212">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="9fc9b-213">出力</span><span class="sxs-lookup"><span data-stu-id="9fc9b-213">OUTPUTS</span></span>

### <span data-ttu-id="9fc9b-214">なし</span><span class="sxs-lookup"><span data-stu-id="9fc9b-214">None</span></span>

<span data-ttu-id="9fc9b-215">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-215">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9fc9b-216">注</span><span class="sxs-lookup"><span data-stu-id="9fc9b-216">NOTES</span></span>

<span data-ttu-id="9fc9b-217">`Set-WmiInstance`コマンドレットである Windows Management Instrumentation (WMI) コマンドレットも似ています。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-217">The `Set-WmiInstance` cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span>
<span data-ttu-id="9fc9b-218">`Set-WmiInstance` は、DCOM 接続/トランスポート層を使用して、WMI インスタンスを作成または更新します。</span><span class="sxs-lookup"><span data-stu-id="9fc9b-218">`Set-WmiInstance` uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

## <span data-ttu-id="9fc9b-219">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9fc9b-219">RELATED LINKS</span></span>

[<span data-ttu-id="9fc9b-220">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="9fc9b-220">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="9fc9b-221">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="9fc9b-221">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="9fc9b-222">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="9fc9b-222">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="9fc9b-223">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="9fc9b-223">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="9fc9b-224">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="9fc9b-224">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="9fc9b-225">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9fc9b-225">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="9fc9b-226">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="9fc9b-226">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="9fc9b-227">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="9fc9b-227">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="9fc9b-228">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9fc9b-228">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="9fc9b-229">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9fc9b-229">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="9fc9b-230">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="9fc9b-230">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="9fc9b-231">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="9fc9b-231">Test-WSMan</span></span>](Test-WSMan.md)

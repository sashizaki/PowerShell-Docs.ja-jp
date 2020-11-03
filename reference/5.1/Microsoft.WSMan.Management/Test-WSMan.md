---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/test-wsman?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-WSMan
ms.openlocfilehash: 3178c12dbc14b9d0841f1d924a695ae2f761f579
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224739"
---
# <span data-ttu-id="8957c-103">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="8957c-103">Test-WSMan</span></span>

## <span data-ttu-id="8957c-104">概要</span><span class="sxs-lookup"><span data-stu-id="8957c-104">SYNOPSIS</span></span>
<span data-ttu-id="8957c-105">WinRM サービスがローカル コンピューターとリモート コンピューターのどちらで実行されているかをテストします。</span><span class="sxs-lookup"><span data-stu-id="8957c-105">Tests whether the WinRM service is running on a local or remote computer.</span></span>

## <span data-ttu-id="8957c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8957c-106">SYNTAX</span></span>

```
Test-WSMan [[-ComputerName] <String>] [-Authentication <AuthenticationMechanism>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-Credential <PSCredential>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="8957c-107">Description</span><span class="sxs-lookup"><span data-stu-id="8957c-107">DESCRIPTION</span></span>
<span data-ttu-id="8957c-108">**テスト WSMan** コマンドレットは、WinRM サービスがローカルコンピューターとリモートコンピューターのどちらで実行されているかを判断する識別要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="8957c-108">The **Test-WSMan** cmdlet submits an identification request that determines whether the WinRM service is running on a local or remote computer.</span></span>
<span data-ttu-id="8957c-109">テスト対象のコンピューターでサービスが実行されている場合、このコマンドレットは、WS-Management ID スキーマ、プロトコルのバージョン、製品ベンダー、およびテスト対象のサービスの製品バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="8957c-109">If the tested computer is running the service, the cmdlet displays the WS-Management identity schema, the protocol version, the product vendor, and the product version of the tested service.</span></span>

## <span data-ttu-id="8957c-110">例</span><span class="sxs-lookup"><span data-stu-id="8957c-110">EXAMPLES</span></span>

### <span data-ttu-id="8957c-111">例 1: WinRM サービスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="8957c-111">Example 1: Determine the status of the WinRM service</span></span>

```
PS C:\> Test-WSMan
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="8957c-112">このコマンドは、WinRM サービスがローカル コンピューターとリモート コンピューターのどちらで実行されているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8957c-112">This command determines whether the WinRM service is running on the local computer or on a remote computer.</span></span>

### <span data-ttu-id="8957c-113">例 2: リモートコンピューター上の WinRM サービスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="8957c-113">Example 2: Determine the status of the WinRM service on a remote computer</span></span>

```
PS C:\> Test-WSMan -ComputerName "server01"
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="8957c-114">このコマンドは、server01 コンピューターで WinRM サービスが実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8957c-114">This command determines whether the WinRM service is running on the server01 computer.</span></span>

### <span data-ttu-id="8957c-115">例 3: WinRM サービスの状態とオペレーティングシステムのバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="8957c-115">Example 3: Determine the status of the WinRM service and the operating system version</span></span>

```
PS C:\> Test-WSMan -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.0.6001 SP: 1.0 Stack: 2.0
```

<span data-ttu-id="8957c-116">このコマンドは、WS-Management (WinRM) サービスがローカルコンピューター上で認証パラメーターを使用して実行されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="8957c-116">This command tests to see whether the WS-Management (WinRM) service is running on the local computer by using the authentication parameter.</span></span>

<span data-ttu-id="8957c-117">Authentication パラメーターを使用すると、 **テスト WSMan** はオペレーティングシステムのバージョンを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8957c-117">Using the authentication parameter enables **Test-WSMan** to return the operating system version.</span></span>

### <span data-ttu-id="8957c-118">例 4: WinRM サービスの状態とリモートコンピューター上のオペレーティングシステムのバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="8957c-118">Example 4: Determine the status of the WinRM service and the operating system version on a remote computer</span></span>

```
PS C:\> Test-WSMan -ComputerName "server01" -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.1.7021 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="8957c-119">このコマンドは、認証パラメーターを使用して、WS-Management (WinRM) サービスが server01 という名前のコンピューター上で実行されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="8957c-119">This command tests to see whether the WS-Management (WinRM) service is running on the computer named server01 using the authentication parameter.</span></span>

<span data-ttu-id="8957c-120">Authentication パラメーターを使用すると、 **テスト WSMan** はオペレーティングシステムのバージョンを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8957c-120">Using the authentication parameter enables **Test-WSMan** to return the operating system version.</span></span>

## <span data-ttu-id="8957c-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8957c-121">PARAMETERS</span></span>

### <span data-ttu-id="8957c-122">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="8957c-122">-ApplicationName</span></span>
<span data-ttu-id="8957c-123">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8957c-123">Specifies the application name in the connection.</span></span>
<span data-ttu-id="8957c-124">*ApplicationName* パラメーターの既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="8957c-124">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="8957c-125">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="8957c-125">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="8957c-126">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="8957c-126">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="8957c-127">例: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="8957c-127">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="8957c-128">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="8957c-128">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="8957c-129">この WSMAN の既定の設定は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="8957c-129">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="8957c-130">このパラメーターは、多くのコンピューターが Windows PowerShell を実行している1台のコンピューターへのリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8957c-130">This parameter is designed to be used if many computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="8957c-131">この場合、IIS は効率を上げるために Web Services for Management (WS-MANAGEMENT) をホストします。</span><span class="sxs-lookup"><span data-stu-id="8957c-131">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="8957c-132">-認証</span><span class="sxs-lookup"><span data-stu-id="8957c-132">-Authentication</span></span>
<span data-ttu-id="8957c-133">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="8957c-133">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="8957c-134">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8957c-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8957c-135">基本。</span><span class="sxs-lookup"><span data-stu-id="8957c-135">Basic.</span></span>
<span data-ttu-id="8957c-136">Basic は、ユーザー名およびパスワードがクリア テキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="8957c-136">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="8957c-137">既定値。</span><span class="sxs-lookup"><span data-stu-id="8957c-137">Default.</span></span>
<span data-ttu-id="8957c-138">WS-Management プロトコルによって実装されている認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="8957c-138">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="8957c-139">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="8957c-139">This is the default.</span></span>
- <span data-ttu-id="8957c-140">ダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="8957c-140">Digest.</span></span>
<span data-ttu-id="8957c-141">Digest は、サーバーで指定されたデータ文字列をチャレンジで使用するチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="8957c-141">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="8957c-142">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="8957c-142">Kerberos.</span></span>
<span data-ttu-id="8957c-143">クライアント コンピューターとサーバーが Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="8957c-143">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="8957c-144">Negotiate</span><span class="sxs-lookup"><span data-stu-id="8957c-144">Negotiate.</span></span>
<span data-ttu-id="8957c-145">Negotiate は、認証で使用するスキームを特定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="8957c-145">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="8957c-146">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されているかをネゴシエーションで判断できます。</span><span class="sxs-lookup"><span data-stu-id="8957c-146">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="8957c-147">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="8957c-147">CredSSP.</span></span>
<span data-ttu-id="8957c-148">Credential Security Support Provider (CredSSP) 認証を使用して、ユーザーが資格情報を委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8957c-148">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="8957c-149">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="8957c-149">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="8957c-150">注意: CredSSP は、ローカルコンピューターからリモートコンピューターにユーザーの資格情報を委任します。</span><span class="sxs-lookup"><span data-stu-id="8957c-150">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="8957c-151">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="8957c-151">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="8957c-152">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8957c-152">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

<span data-ttu-id="8957c-153">重要: *認証* パラメーターを指定しない場合、認証を使用せずに、 **テスト WSMan** 要求がリモートコンピューターに匿名で送信されます。</span><span class="sxs-lookup"><span data-stu-id="8957c-153">Important: If you do not specify the *Authentication* parameter,, the **Test-WSMan** request is sent to the remote computer anonymously, without using authentication.</span></span>
<span data-ttu-id="8957c-154">要求が匿名で行われると、オペレーティングシステムのバージョンに固有の情報は返されません。</span><span class="sxs-lookup"><span data-stu-id="8957c-154">If the request is made anonymously, it returns no information that is specific to the operating-system version.</span></span>
<span data-ttu-id="8957c-155">代わりに、このコマンドレットでは、オペレーティングシステムのバージョンと Service Pack レベル (OS: 0.0.0 SP: 0.0) の null 値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8957c-155">Instead, this cmdlet displays null values for the operating system version and service pack level (OS: 0.0.0 SP: 0.0).</span></span>

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

### <span data-ttu-id="8957c-156">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="8957c-156">-CertificateThumbprint</span></span>
<span data-ttu-id="8957c-157">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8957c-157">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="8957c-158">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="8957c-158">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="8957c-159">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="8957c-159">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="8957c-160">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="8957c-160">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="8957c-161">証明書の拇印を取得するには、Windows PowerShell Cert: ドライブで Get-Item コマンドまたは Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8957c-161">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="8957c-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="8957c-162">-ComputerName</span></span>
<span data-ttu-id="8957c-163">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="8957c-163">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="8957c-164">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8957c-164">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="8957c-165">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="8957c-165">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="8957c-166">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="8957c-166">The local computer is the default.</span></span>
<span data-ttu-id="8957c-167">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8957c-167">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="8957c-168">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="8957c-168">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8957c-169">-Credential</span><span class="sxs-lookup"><span data-stu-id="8957c-169">-Credential</span></span>
<span data-ttu-id="8957c-170">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8957c-170">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="8957c-171">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="8957c-171">The default is the current user.</span></span>
<span data-ttu-id="8957c-172">User01、Domain01\user01」、などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="8957c-172">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="8957c-173">または、Get-Credential コマンドレットによって返されるような **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="8957c-173">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="8957c-174">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="8957c-174">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="8957c-175">-Port</span><span class="sxs-lookup"><span data-stu-id="8957c-175">-Port</span></span>
<span data-ttu-id="8957c-176">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="8957c-176">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="8957c-177">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="8957c-177">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="8957c-178">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="8957c-178">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="8957c-179">HTTPS をトランスポートとして使用する場合は、 *ComputerName* パラメーターの値がサーバーの証明書共通名 (CN) と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8957c-179">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>

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

### <span data-ttu-id="8957c-180">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="8957c-180">-UseSSL</span></span>
<span data-ttu-id="8957c-181">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8957c-181">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="8957c-182">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="8957c-182">By default, SSL is not used.</span></span>

<span data-ttu-id="8957c-183">WS-Management は、ネットワークを介して転送されるすべての Windows PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="8957c-183">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="8957c-184">*UseSSL* パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8957c-184">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="8957c-185">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="8957c-185">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="8957c-186">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8957c-186">CommonParameters</span></span>
<span data-ttu-id="8957c-187">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8957c-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8957c-188">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8957c-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8957c-189">入力</span><span class="sxs-lookup"><span data-stu-id="8957c-189">INPUTS</span></span>

### <span data-ttu-id="8957c-190">なし</span><span class="sxs-lookup"><span data-stu-id="8957c-190">None</span></span>
<span data-ttu-id="8957c-191">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="8957c-191">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="8957c-192">出力</span><span class="sxs-lookup"><span data-stu-id="8957c-192">OUTPUTS</span></span>

### <span data-ttu-id="8957c-193">なし</span><span class="sxs-lookup"><span data-stu-id="8957c-193">None</span></span>
<span data-ttu-id="8957c-194">このコマンドレットは出力オブジェクトを生成しません。</span><span class="sxs-lookup"><span data-stu-id="8957c-194">This cmdlet does not generate any output object.</span></span>

## <span data-ttu-id="8957c-195">注</span><span class="sxs-lookup"><span data-stu-id="8957c-195">NOTES</span></span>

* <span data-ttu-id="8957c-196">既定では、 **テスト WSMan** コマンドレットは認証を使用せずに WinRM サービスを照会し、オペレーティングシステムのバージョンに固有の情報は返しません。</span><span class="sxs-lookup"><span data-stu-id="8957c-196">By default, the **Test-WSMan** cmdlet queries the WinRM service without using authentication, and it returns no information that is specific to the operating-system version.</span></span> <span data-ttu-id="8957c-197">代わりに、オペレーティングシステムのバージョンと Service Pack レベル (OS: 0.0.0 SP: 0.0) の null 値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8957c-197">Instead, it displays null values for the operating system version and service pack level (OS: 0.0.0 SP: 0.0).</span></span>

*

## <span data-ttu-id="8957c-198">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8957c-198">RELATED LINKS</span></span>

[<span data-ttu-id="8957c-199">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="8957c-199">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="8957c-200">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="8957c-200">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="8957c-201">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="8957c-201">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="8957c-202">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="8957c-202">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="8957c-203">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="8957c-203">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="8957c-204">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8957c-204">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="8957c-205">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="8957c-205">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="8957c-206">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8957c-206">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="8957c-207">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="8957c-207">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="8957c-208">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8957c-208">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="8957c-209">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8957c-209">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="8957c-210">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="8957c-210">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

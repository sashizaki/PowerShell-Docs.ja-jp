---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/remove-wsmaninstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WSManInstance
ms.openlocfilehash: 6bd166942551671c581c04cb611c222378caeba1
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218307"
---
# <span data-ttu-id="b0cd5-103">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b0cd5-103">Remove-WSManInstance</span></span>

## <span data-ttu-id="b0cd5-104">概要</span><span class="sxs-lookup"><span data-stu-id="b0cd5-104">SYNOPSIS</span></span>
<span data-ttu-id="b0cd5-105">管理リソースのインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-105">Deletes a management resource instance.</span></span>

## <span data-ttu-id="b0cd5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b0cd5-106">SYNTAX</span></span>

### <span data-ttu-id="b0cd5-107">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="b0cd5-107">ComputerName (Default)</span></span>

```
Remove-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-UseSSL]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="b0cd5-108">URI</span><span class="sxs-lookup"><span data-stu-id="b0cd5-108">URI</span></span>

```
Remove-WSManInstance [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="b0cd5-109">Description</span><span class="sxs-lookup"><span data-stu-id="b0cd5-109">DESCRIPTION</span></span>

<span data-ttu-id="b0cd5-110">SelectorSet **コマンドレットは、** *ResourceURI* パラメーターと *SelectorSet* パラメーターで指定された管理リソースのインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-110">The **Remove-WSManInstance** cmdlet deletes an instance of a management resource that is specified in the *ResourceURI* and *SelectorSet* parameters.</span></span>

<span data-ttu-id="b0cd5-111">このコマンドレットは、WinRM の接続/トランスポート層を使用して、管理リソースのインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-111">This cmdlet uses the WinRM connection/transport layer to delete the management resource instance.</span></span>

## <span data-ttu-id="b0cd5-112">例</span><span class="sxs-lookup"><span data-stu-id="b0cd5-112">EXAMPLES</span></span>

### <span data-ttu-id="b0cd5-113">例 1: リスナーを削除する</span><span class="sxs-lookup"><span data-stu-id="b0cd5-113">Example 1: Delete a listener</span></span>

```
PS C:\> Remove-WSManInstance -ResourceUri winrm/config/Listener -SelectorSet Address=test.fabrikam.com;Transport=http
```

<span data-ttu-id="b0cd5-114">このコマンドは、コンピューター上の WS-Management HTTP リスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-114">This command deletes the WS-Management HTTP listener on a computer.</span></span>

## <span data-ttu-id="b0cd5-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b0cd5-115">PARAMETERS</span></span>

### <span data-ttu-id="b0cd5-116">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="b0cd5-116">-ApplicationName</span></span>

<span data-ttu-id="b0cd5-117">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-117">Specifies the application name in the connection.</span></span>
<span data-ttu-id="b0cd5-118">*ApplicationName* パラメーターの既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-118">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="b0cd5-119">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-119">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="b0cd5-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="b0cd5-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="b0cd5-121">例: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="b0cd5-121">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="b0cd5-122">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="b0cd5-123">この WSMAN の既定の設定は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-123">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="b0cd5-124">このパラメーターは、多くのコンピューターが PowerShell を実行する1台のコンピューターへのリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-124">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="b0cd5-125">この場合、IIS は効率を上げるために Web Services for Management (WS-MANAGEMENT) をホストします。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0cd5-126">-認証</span><span class="sxs-lookup"><span data-stu-id="b0cd5-126">-Authentication</span></span>

<span data-ttu-id="b0cd5-127">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-127">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="b0cd5-128">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-128">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b0cd5-129">基本。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-129">Basic.</span></span>
<span data-ttu-id="b0cd5-130">Basic は、ユーザー名およびパスワードがクリア テキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-130">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="b0cd5-131">既定値。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-131">Default.</span></span>
<span data-ttu-id="b0cd5-132">WS-Management プロトコルによって実装されている認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-132">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="b0cd5-133">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-133">This is the default.</span></span>
- <span data-ttu-id="b0cd5-134">ダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-134">Digest.</span></span>
<span data-ttu-id="b0cd5-135">Digest は、サーバーで指定されたデータ文字列をチャレンジで使用するチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-135">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="b0cd5-136">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-136">Kerberos.</span></span>
<span data-ttu-id="b0cd5-137">クライアント コンピューターとサーバーが Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-137">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="b0cd5-138">Negotiate</span><span class="sxs-lookup"><span data-stu-id="b0cd5-138">Negotiate.</span></span>
<span data-ttu-id="b0cd5-139">Negotiate は、認証で使用するスキームを特定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-139">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="b0cd5-140">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されているかをネゴシエーションで判断できます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-140">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="b0cd5-141">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="b0cd5-141">CredSSP.</span></span>
<span data-ttu-id="b0cd5-142">Credential Security Support Provider (CredSSP) 認証を使用して、ユーザーが資格情報を委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-142">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="b0cd5-143">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-143">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="b0cd5-144">注意: CredSSP は、ローカルコンピューターからリモートコンピューターにユーザーの資格情報を委任します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-144">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="b0cd5-145">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-145">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="b0cd5-146">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-146">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="b0cd5-147">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="b0cd5-147">-CertificateThumbprint</span></span>

<span data-ttu-id="b0cd5-148">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-148">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="b0cd5-149">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-149">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="b0cd5-150">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-150">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="b0cd5-151">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-151">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="b0cd5-152">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-152">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="b0cd5-153">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b0cd5-153">-ComputerName</span></span>

<span data-ttu-id="b0cd5-154">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-154">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="b0cd5-155">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-155">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="b0cd5-156">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-156">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="b0cd5-157">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-157">The local computer is the default.</span></span>
<span data-ttu-id="b0cd5-158">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-158">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="b0cd5-159">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-159">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0cd5-160">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="b0cd5-160">-ConnectionURI</span></span>

<span data-ttu-id="b0cd5-161">接続エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-161">Specifies the connection endpoint.</span></span>
<span data-ttu-id="b0cd5-162">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-162">The format of this string is as follows:</span></span>

<span data-ttu-id="b0cd5-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="b0cd5-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="b0cd5-164">次の文字列は、このパラメーターに対して正しく書式設定された値です。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-164">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="b0cd5-165">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-165">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0cd5-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="b0cd5-166">-Credential</span></span>

<span data-ttu-id="b0cd5-167">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-167">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="b0cd5-168">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-168">The default is the current user.</span></span>
<span data-ttu-id="b0cd5-169">User01、Domain01\user01」、などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-169">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="b0cd5-170">または、Get-Credential コマンドレットによって返されるような **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-170">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="b0cd5-171">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-171">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="b0cd5-172">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="b0cd5-172">-OptionSet</span></span>

<span data-ttu-id="b0cd5-173">要求の性質を変更または調整するための一連のスイッチをサービスに指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-173">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="b0cd5-174">これらは、サービス固有であるため、コマンドラインシェルで使用されるスイッチに似ています。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-174">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="b0cd5-175">任意の数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-175">Any number of options can be specified.</span></span>

<span data-ttu-id="b0cd5-176">次の例では、a、b、および c パラメーターに値 1、2、および 3 を渡す構文を示します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-176">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="b0cd5-177">-Port</span><span class="sxs-lookup"><span data-stu-id="b0cd5-177">-Port</span></span>

<span data-ttu-id="b0cd5-178">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-178">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="b0cd5-179">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-179">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="b0cd5-180">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-180">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="b0cd5-181">HTTPS をトランスポートとして使用する場合は、 *ComputerName* パラメーターの値がサーバーの証明書共通名 (CN) と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-181">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="b0cd5-182">ただし、 *Sessionoption* パラメーターの一部として *skipcncheck* パラメーターを指定した場合、サーバーの証明書の共通名がサーバーのホスト名と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-182">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="b0cd5-183">*Skipcncheck* パラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-183">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="b0cd5-184">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="b0cd5-184">-ResourceURI</span></span>

<span data-ttu-id="b0cd5-185">リソースクラスまたはインスタンスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-185">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="b0cd5-186">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-186">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="b0cd5-187">URI は、リソースのプレフィックスとパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-187">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="b0cd5-188">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-188">For example:</span></span>

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

### <span data-ttu-id="b0cd5-189">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="b0cd5-189">-SelectorSet</span></span>

<span data-ttu-id="b0cd5-190">特定の管理リソース インスタンスの選択に使用する値のペアのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-190">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="b0cd5-191">*SelectorSet* パラメーターは、リソースの複数のインスタンスが存在する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-191">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="b0cd5-192">*SelectorSet* の値は、ハッシュテーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-192">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="b0cd5-193">次の例では、このパラメーターの値を入力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-193">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b0cd5-194">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="b0cd5-194">-SessionOption</span></span>

<span data-ttu-id="b0cd5-195">WS-Management セッションの拡張オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-195">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="b0cd5-196">New-WSManSessionOption コマンドレットを使用して作成する **Sessionoption** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-196">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="b0cd5-197">使用可能なオプションの詳細については、「」と入力 `Get-Help New-WSManSessionOption` してください。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-197">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="b0cd5-198">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="b0cd5-198">-UseSSL</span></span>

<span data-ttu-id="b0cd5-199">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-199">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="b0cd5-200">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-200">By default, SSL is not used.</span></span>

<span data-ttu-id="b0cd5-201">WS-Management は、ネットワーク経由で転送されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-201">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="b0cd5-202">*UseSSL* パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-202">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="b0cd5-203">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-203">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases: ssl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0cd5-204">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0cd5-204">CommonParameters</span></span>

<span data-ttu-id="b0cd5-205">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-205">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b0cd5-206">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-206">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b0cd5-207">入力</span><span class="sxs-lookup"><span data-stu-id="b0cd5-207">INPUTS</span></span>

### <span data-ttu-id="b0cd5-208">なし</span><span class="sxs-lookup"><span data-stu-id="b0cd5-208">None</span></span>

<span data-ttu-id="b0cd5-209">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-209">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="b0cd5-210">出力</span><span class="sxs-lookup"><span data-stu-id="b0cd5-210">OUTPUTS</span></span>

### <span data-ttu-id="b0cd5-211">なし</span><span class="sxs-lookup"><span data-stu-id="b0cd5-211">None</span></span>

<span data-ttu-id="b0cd5-212">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-212">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b0cd5-213">注</span><span class="sxs-lookup"><span data-stu-id="b0cd5-213">NOTES</span></span>

* <span data-ttu-id="b0cd5-214">Remove-WmiObject コマンドレット (Windows Management Instrumentation (WMI) のコマンドレット) と似ています。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-214">The Remove-WmiObject cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span> <span data-ttu-id="b0cd5-215">**Get-wmiobject** は、DCOM 接続/トランスポート層を使用して、WMI インスタンスを作成または更新します。</span><span class="sxs-lookup"><span data-stu-id="b0cd5-215">**Remove-WmiObject** uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

*

## <span data-ttu-id="b0cd5-216">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b0cd5-216">RELATED LINKS</span></span>

[<span data-ttu-id="b0cd5-217">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b0cd5-217">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="b0cd5-218">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b0cd5-218">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="b0cd5-219">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b0cd5-219">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="b0cd5-220">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b0cd5-220">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="b0cd5-221">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b0cd5-221">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="b0cd5-222">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b0cd5-222">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="b0cd5-223">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="b0cd5-223">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="b0cd5-224">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b0cd5-224">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="b0cd5-225">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="b0cd5-225">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="b0cd5-226">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b0cd5-226">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="b0cd5-227">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="b0cd5-227">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="b0cd5-228">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="b0cd5-228">Test-WSMan</span></span>](Test-WSMan.md)


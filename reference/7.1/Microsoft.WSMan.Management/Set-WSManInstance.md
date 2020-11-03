---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmaninstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManInstance
ms.openlocfilehash: 9060f683372617b3a01365ceb81668c75986f46d
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218707"
---
# <span data-ttu-id="82f49-103">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="82f49-103">Set-WSManInstance</span></span>

## <span data-ttu-id="82f49-104">概要</span><span class="sxs-lookup"><span data-stu-id="82f49-104">SYNOPSIS</span></span>
<span data-ttu-id="82f49-105">リソースに関連する管理情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="82f49-105">Modifies the management information that is related to a resource.</span></span>

## <span data-ttu-id="82f49-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="82f49-106">SYNTAX</span></span>

### <span data-ttu-id="82f49-107">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="82f49-107">ComputerName (Default)</span></span>

```
Set-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-Dialect <Uri>] [-FilePath <String>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri>
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="82f49-108">URI</span><span class="sxs-lookup"><span data-stu-id="82f49-108">URI</span></span>

```
Set-WSManInstance [-ConnectionURI <Uri>] [-Dialect <Uri>] [-FilePath <String>] [-Fragment <String>]
 [-OptionSet <Hashtable>] [-ResourceURI] <Uri> [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-ValueSet <Hashtable>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="82f49-109">Description</span><span class="sxs-lookup"><span data-stu-id="82f49-109">DESCRIPTION</span></span>

<span data-ttu-id="82f49-110">Set-WSManInstance コマンドレットは、リソースに関連する管理情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="82f49-110">The Set-WSManInstance cmdlet modifies the management information that is related to a resource.</span></span>

<span data-ttu-id="82f49-111">このコマンドレットは、WinRM の接続/トランスポート層を使用して、情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="82f49-111">This cmdlet uses the WinRM connection/transport layer to modify the information.</span></span>

## <span data-ttu-id="82f49-112">例</span><span class="sxs-lookup"><span data-stu-id="82f49-112">EXAMPLES</span></span>

### <span data-ttu-id="82f49-113">例 1: ローカルコンピューター上のリスナーを無効にする</span><span class="sxs-lookup"><span data-stu-id="82f49-113">Example 1: Disable a listener on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.171, ::1, 2001:4898:0:fff:0:5efe:172.30.168.171...}
```

<span data-ttu-id="82f49-114">このコマンドは、ローカル コンピューター上の HTTPS リスナーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="82f49-114">This command disables the https listener on the local computer.</span></span>

<span data-ttu-id="82f49-115">重要: *Valueset* パラメーターは、指定されたプロパティを照合するときに大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="82f49-115">Important: The *ValueSet* parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="82f49-116">たとえば、次のコマンドでは、</span><span class="sxs-lookup"><span data-stu-id="82f49-116">For example, in this command,</span></span>

<span data-ttu-id="82f49-117">これは失敗します。 `-ValueSet @{enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="82f49-117">This fails: `-ValueSet @{enabled="False"}`</span></span>

<span data-ttu-id="82f49-118">これで成功します。 `-ValueSet @{Enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="82f49-118">This succeeds: `-ValueSet @{Enabled="False"}`</span></span>

### <span data-ttu-id="82f49-119">例 2: ローカルコンピューターの最大エンベロープサイズを設定する</span><span class="sxs-lookup"><span data-stu-id="82f49-119">Example 2: Set the maximum envelope size on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config -ValueSet @{MaxEnvelopeSizekb = "200"}
```

```Output
cfg                 : http://schemas.microsoft.com/wbem/wsman/1/config
lang                : en-US
MaxEnvelopeSizekb   : 200
MaxTimeoutms        : 60000
MaxBatchItems       : 32000
MaxProviderRequests : 4294967295
Client              : Client
Service             : Service
Winrs               : Winrs
```

<span data-ttu-id="82f49-120">このコマンドは、ローカル コンピューターで MaxEnvelopeSizekb 値を 200 に設定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-120">This command sets the MaxEnvelopeSizekb value to 200 on the local computer.</span></span>

<span data-ttu-id="82f49-121">重要: ValueSet パラメーターは、指定されたプロパティを照合するときに大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="82f49-121">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="82f49-122">たとえば、上記のコマンドを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="82f49-122">For example, using the above command.</span></span>

<span data-ttu-id="82f49-123">次のエラーが発生します:-ValueSet @ {MaxEnvelopeSizeKB = "200"}</span><span class="sxs-lookup"><span data-stu-id="82f49-123">This fails:     -ValueSet @{MaxEnvelopeSizeKB ="200"}</span></span>

<span data-ttu-id="82f49-124">成功した場合:-ValueSet @ {MaxEnvelopeSizekb = "200"}</span><span class="sxs-lookup"><span data-stu-id="82f49-124">This succeeds:  -ValueSet @{MaxEnvelopeSizekb ="200"}</span></span>

### <span data-ttu-id="82f49-125">例 3: リモートコンピューター上のリスナーを無効にする</span><span class="sxs-lookup"><span data-stu-id="82f49-125">Example 3: Disable a listener on a remote computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -ComputerName SERVER02 -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.172, ::1, 2001:4898:0:fff:0:5efe:172.30.168.172...}
```

<span data-ttu-id="82f49-126">このコマンドは、ローカル コンピューター SERVER02 上の HTTPS リスナーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="82f49-126">This command disables the https listener on the remote computer SERVER02.</span></span>

<span data-ttu-id="82f49-127">重要: ValueSet パラメーターは、指定されたプロパティを照合するときに大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="82f49-127">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="82f49-128">たとえば、上記のコマンドを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="82f49-128">For example, using the above command.</span></span>

<span data-ttu-id="82f49-129">失敗:-ValueSet @ {enabled = "False"}</span><span class="sxs-lookup"><span data-stu-id="82f49-129">This fails:     -ValueSet @{enabled="False"}</span></span>

<span data-ttu-id="82f49-130">成功した場合:-ValueSet @ {Enabled = "False"}</span><span class="sxs-lookup"><span data-stu-id="82f49-130">This succeeds:  -ValueSet @{Enabled="False"}</span></span>

## <span data-ttu-id="82f49-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="82f49-131">PARAMETERS</span></span>

### <span data-ttu-id="82f49-132">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="82f49-132">-ApplicationName</span></span>

<span data-ttu-id="82f49-133">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-133">Specifies the application name in the connection.</span></span>
<span data-ttu-id="82f49-134">ApplicationName パラメーターの既定値は "WSMAN" です。</span><span class="sxs-lookup"><span data-stu-id="82f49-134">The default value of the ApplicationName parameter is "WSMAN".</span></span>
<span data-ttu-id="82f49-135">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="82f49-135">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="82f49-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="82f49-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="82f49-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="82f49-137">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="82f49-138">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="82f49-138">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="82f49-139">既定の設定の "WSMAN" は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="82f49-139">This default setting of "WSMAN" is appropriate for most uses.</span></span>
<span data-ttu-id="82f49-140">このパラメーターは、Windows PowerShell を実行している 1 台のコンピューターに多数のコンピューターからリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="82f49-140">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="82f49-141">この場合、IIS は効率を上げるために Web Services for Management (WS-Management) をホストします。</span><span class="sxs-lookup"><span data-stu-id="82f49-141">In this case, IIS hosts Web Services for Management (WS-Management ) for efficiency.</span></span>

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

### <span data-ttu-id="82f49-142">-認証</span><span class="sxs-lookup"><span data-stu-id="82f49-142">-Authentication</span></span>

<span data-ttu-id="82f49-143">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-143">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="82f49-144">次のいずれかの値になります。</span><span class="sxs-lookup"><span data-stu-id="82f49-144">Possible values are:</span></span>

- <span data-ttu-id="82f49-145">基本: Basic は、ユーザー名とパスワードがクリアテキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="82f49-145">Basic: Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="82f49-146">既定値: WS-Management プロトコルによって実装される認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="82f49-146">Default : Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="82f49-147">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="82f49-147">This is the default.</span></span>
- <span data-ttu-id="82f49-148">ダイジェスト: ダイジェストは、サーバーで指定されたデータ文字列をチャレンジに使用するチャレンジ/レスポンススキームです。</span><span class="sxs-lookup"><span data-stu-id="82f49-148">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="82f49-149">Kerberos: クライアントコンピューターとサーバーは、Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="82f49-149">Kerberos: The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="82f49-150">Negotiate: Negotiate は、認証に使用するスキームを決定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンススキームです。</span><span class="sxs-lookup"><span data-stu-id="82f49-150">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="82f49-151">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されるかを特定するネゴシエーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="82f49-151">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="82f49-152">CredSSP: Credential Security Support Provider (CredSSP) 認証を使用します。これにより、ユーザーは資格情報を委任できます。</span><span class="sxs-lookup"><span data-stu-id="82f49-152">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="82f49-153">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="82f49-153">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="82f49-154">注意: CredSSP では、ユーザーの資格情報がローカルコンピューターからリモートコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="82f49-154">Caution: CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="82f49-155">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="82f49-155">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="82f49-156">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="82f49-156">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82f49-157">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="82f49-157">-CertificateThumbprint</span></span>

<span data-ttu-id="82f49-158">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-158">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="82f49-159">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="82f49-159">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="82f49-160">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="82f49-160">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="82f49-161">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="82f49-161">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="82f49-162">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="82f49-162">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="82f49-163">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="82f49-163">-ComputerName</span></span>

<span data-ttu-id="82f49-164">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-164">Specifies the computer against which you want to run the management operation.</span></span>
<span data-ttu-id="82f49-165">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82f49-165">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="82f49-166">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="82f49-166">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="82f49-167">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="82f49-167">The local computer is the default.</span></span>
<span data-ttu-id="82f49-168">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f49-168">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="82f49-169">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="82f49-169">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="82f49-170">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="82f49-170">-ConnectionURI</span></span>

<span data-ttu-id="82f49-171">接続エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-171">Specifies the connection endpoint.</span></span>
<span data-ttu-id="82f49-172">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82f49-172">The format of this string is:</span></span>

<span data-ttu-id="82f49-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="82f49-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="82f49-174">次の文字列は、このパラメーターの正しい形式の値です。</span><span class="sxs-lookup"><span data-stu-id="82f49-174">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="82f49-175">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f49-175">The URI must be fully qualified .</span></span>

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

### <span data-ttu-id="82f49-176">-Credential</span><span class="sxs-lookup"><span data-stu-id="82f49-176">-Credential</span></span>

<span data-ttu-id="82f49-177">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-177">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="82f49-178">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="82f49-178">The default is the current user.</span></span>
<span data-ttu-id="82f49-179">"User01"、"Domain01\user01」"、"" などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="82f49-179">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span>
<span data-ttu-id="82f49-180">または、Get-Credential コマンドレットから返されるような PSCredential オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="82f49-180">Or, enter a PSCredential object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="82f49-181">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82f49-181">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="82f49-182">-言語</span><span class="sxs-lookup"><span data-stu-id="82f49-182">-Dialect</span></span>

<span data-ttu-id="82f49-183">フィルター述語で使用する言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-183">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="82f49-184">リモート サービスでサポートされている任意の言語を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82f49-184">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="82f49-185">言語の URI には、次のエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82f49-185">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="82f49-186">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="82f49-186">WQL: `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="82f49-187">選択肢 `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="82f49-187">Selector: `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="82f49-188">づける `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="82f49-188">Association: `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: http://schemas.microsoft.com/wbem/wsman/1/WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82f49-189">-FilePath</span><span class="sxs-lookup"><span data-stu-id="82f49-189">-FilePath</span></span>

<span data-ttu-id="82f49-190">管理リソースの更新に使用するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-190">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="82f49-191">管理リソースは、ResourceURI パラメーターと SelectorSet パラメーターを使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-191">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter .</span></span>
<span data-ttu-id="82f49-192">たとえば、次のコマンドは、FilePath パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="82f49-192">For example, the following command uses the FilePath parameter:</span></span>

`Invoke-WSManAction -action StopService -resourceuri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:c:\input.xml -authentication default`

<span data-ttu-id="82f49-193">このコマンドは、ファイルからの入力を使用して、スプーラー サービスの StopService メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="82f49-193">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="82f49-194">Input.xml ファイルには、次の内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82f49-194">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="82f49-195">-Fragment</span><span class="sxs-lookup"><span data-stu-id="82f49-195">-Fragment</span></span>

<span data-ttu-id="82f49-196">指定された操作で更新または取得するインスタンス内のセクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-196">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="82f49-197">たとえば、スプーラー サービスの状態を取得するには、"-Fragment Status" を指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-197">For example, to get the status of a spooler service, specify "-Fragment Status".</span></span>

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

### <span data-ttu-id="82f49-198">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="82f49-198">-OptionSet</span></span>

<span data-ttu-id="82f49-199">要求のオプションを変更または調整する一連のスイッチをサービスに渡します。</span><span class="sxs-lookup"><span data-stu-id="82f49-199">Passes a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="82f49-200">これらは、サービス固有であるため、コマンド ライン シェルで使用されるスイッチに似ています。</span><span class="sxs-lookup"><span data-stu-id="82f49-200">These are similar to switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="82f49-201">任意の数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82f49-201">Any number of options can be specified.</span></span>

<span data-ttu-id="82f49-202">次の例では、a、b、および c パラメーターに値 1、2、および 3 を渡す構文を示します。</span><span class="sxs-lookup"><span data-stu-id="82f49-202">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

<span data-ttu-id="82f49-203">-OptionSet @{a=1;b=2;c=3}</span><span class="sxs-lookup"><span data-stu-id="82f49-203">-OptionSet @{a=1;b=2;c=3}</span></span>

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

### <span data-ttu-id="82f49-204">-Port</span><span class="sxs-lookup"><span data-stu-id="82f49-204">-Port</span></span>

<span data-ttu-id="82f49-205">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-205">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="82f49-206">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="82f49-206">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="82f49-207">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="82f49-207">When the transport is HTTPS, the default port is 443.</span></span>
<span data-ttu-id="82f49-208">HTTPS をトランスポートとして使用する場合は、ComputerName パラメーターの値がサーバーの証明書の共通名 (CN) と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f49-208">When you use HTTPS as the transport, the value of the ComputerName parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="82f49-209">ただし、SessionOption パラメーターの一部として SkipCNCheck パラメーターを指定した場合は、サーバーの証明書の共通名がサーバーのホスト名と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="82f49-209">However, if the SkipCNCheck parameter is specified as part of the SessionOption parameter, then the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="82f49-210">SkipCNCheck パラメーターは、信頼されているコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="82f49-210">The SkipCNCheck parameter should be used only for trusted machines.</span></span>

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

### <span data-ttu-id="82f49-211">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="82f49-211">-ResourceURI</span></span>

<span data-ttu-id="82f49-212">リソース クラスまたはインスタンスの Uniform Resource Identifier (URI) を含めます。</span><span class="sxs-lookup"><span data-stu-id="82f49-212">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="82f49-213">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="82f49-213">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="82f49-214">URI は、プレフィックスとリソースのパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="82f49-214">A URI consists of a prefix and a path to a resource.</span></span>
<span data-ttu-id="82f49-215">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="82f49-215">For example:</span></span>

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

### <span data-ttu-id="82f49-216">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="82f49-216">-SelectorSet</span></span>

<span data-ttu-id="82f49-217">特定の管理リソース インスタンスの選択に使用する値のペアのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-217">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="82f49-218">SelectorSet パラメーターは、リソースのインスタンスが複数存在する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="82f49-218">The SelectorSet parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="82f49-219">SelectorSet パラメーターの値は、ハッシュ テーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f49-219">The value of the SelectorSet parameter must be a hash table.</span></span>
<span data-ttu-id="82f49-220">次の例では、このパラメーターの値を入力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82f49-220">The following example shows how to enter a value for this parameter:</span></span>

<span data-ttu-id="82f49-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span><span class="sxs-lookup"><span data-stu-id="82f49-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="82f49-222">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="82f49-222">-SessionOption</span></span>

<span data-ttu-id="82f49-223">WS-Management セッションの一連の拡張オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="82f49-223">Defines a set of extended options for the WS-Management session.</span></span>
<span data-ttu-id="82f49-224">New-WSManSessionOption コマンドレットを使用して作成する SessionOption オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="82f49-224">Enter a SessionOption object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="82f49-225">使用できるオプションの詳細については、「New-WSManSessionOption」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82f49-225">For more information about the options that are available, see New-WSManSessionOption.</span></span>

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

### <span data-ttu-id="82f49-226">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="82f49-226">-UseSSL</span></span>

<span data-ttu-id="82f49-227">Secure Sockets Layer (SSL) プロトコルを使用してリモート コンピューターとの接続を確立するように指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-227">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="82f49-228">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="82f49-228">By default, SSL is not used.</span></span>

<span data-ttu-id="82f49-229">WS-Management は、ネットワークを介して転送されるすべての Windows PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="82f49-229">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="82f49-230">UseSSL パラメーターを使用すると、HTTP ではなく、HTTPS による追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82f49-230">The UseSSL parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="82f49-231">接続に使用するポートで SSL を使用できない場合に、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="82f49-231">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="82f49-232">-ValueSet</span><span class="sxs-lookup"><span data-stu-id="82f49-232">-ValueSet</span></span>

<span data-ttu-id="82f49-233">管理リソースの変更に役立つハッシュ テーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-233">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="82f49-234">管理リソースは、ResourceURI パラメーターと SelectorSet パラメーターを使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="82f49-234">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter.</span></span>
<span data-ttu-id="82f49-235">ValueSet パラメーターの値は、ハッシュ テーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f49-235">The value of the ValueSet parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="82f49-236">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="82f49-236">CommonParameters</span></span>

<span data-ttu-id="82f49-237">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="82f49-237">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="82f49-238">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82f49-238">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="82f49-239">入力</span><span class="sxs-lookup"><span data-stu-id="82f49-239">INPUTS</span></span>

### <span data-ttu-id="82f49-240">なし</span><span class="sxs-lookup"><span data-stu-id="82f49-240">None</span></span>

<span data-ttu-id="82f49-241">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="82f49-241">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="82f49-242">出力</span><span class="sxs-lookup"><span data-stu-id="82f49-242">OUTPUTS</span></span>

### <span data-ttu-id="82f49-243">なし</span><span class="sxs-lookup"><span data-stu-id="82f49-243">None</span></span>

<span data-ttu-id="82f49-244">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="82f49-244">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="82f49-245">注</span><span class="sxs-lookup"><span data-stu-id="82f49-245">NOTES</span></span>

## <span data-ttu-id="82f49-246">関連リンク</span><span class="sxs-lookup"><span data-stu-id="82f49-246">RELATED LINKS</span></span>

[<span data-ttu-id="82f49-247">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="82f49-247">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="82f49-248">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="82f49-248">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="82f49-249">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="82f49-249">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="82f49-250">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="82f49-250">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="82f49-251">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="82f49-251">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="82f49-252">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="82f49-252">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="82f49-253">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="82f49-253">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="82f49-254">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="82f49-254">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="82f49-255">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="82f49-255">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="82f49-256">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="82f49-256">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="82f49-257">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="82f49-257">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="82f49-258">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="82f49-258">Test-WSMan</span></span>](Test-WSMan.md)


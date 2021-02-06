---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: 5dfd0b355a3589bf45ea92b92ae8778023132bcd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604966"
---
# <span data-ttu-id="ddc1f-102">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="ddc1f-102">Connect-WSMan</span></span>

## <span data-ttu-id="ddc1f-103">概要</span><span class="sxs-lookup"><span data-stu-id="ddc1f-103">SYNOPSIS</span></span>
<span data-ttu-id="ddc1f-104">リモート コンピューター上の WinRM サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-104">Connects to the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="ddc1f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ddc1f-105">SYNTAX</span></span>

### <span data-ttu-id="ddc1f-106">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="ddc1f-106">ComputerName (Default)</span></span>

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="ddc1f-107">URI</span><span class="sxs-lookup"><span data-stu-id="ddc1f-107">URI</span></span>

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="ddc1f-108">Description</span><span class="sxs-lookup"><span data-stu-id="ddc1f-108">DESCRIPTION</span></span>
<span data-ttu-id="ddc1f-109">**接続 WSMan** コマンドレットは、リモートコンピューター上の WinRM サービスに接続し、リモートコンピューターへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-109">The **Connect-WSMan** cmdlet connects to the WinRM service on a remote computer, and it establishes a persistent connection to the remote computer.</span></span>
<span data-ttu-id="ddc1f-110">このコマンドレットを WSMan プロバイダーのコンテキストで使用して、リモートコンピューター上の WinRM サービスに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-110">You can use this cmdlet in the context of the WSMan provider to connect to the WinRM service on a remote computer.</span></span>
<span data-ttu-id="ddc1f-111">ただし、WSMan プロバイダーに変更する前に、このコマンドレットを使用して、リモート コンピューター上の WinRM サービスに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-111">However, you can also use this cmdlet to connect to the WinRM service on a remote computer before you change to the WSMan provider.</span></span>
<span data-ttu-id="ddc1f-112">リモートコンピューターは、WSMan プロバイダーのルートディレクトリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-112">The remote computer appears in the root directory of the WSMan provider.</span></span>

<span data-ttu-id="ddc1f-113">クライアントとサーバー コンピューターが別のドメインまたはワークグループに属している場合は、明示的な資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-113">Explicit credentials are required when the client and server computers are in different domains or workgroups.</span></span>

<span data-ttu-id="ddc1f-114">リモートコンピューター上の WinRM サービスから切断する方法の詳細については、Disconnect-WSMan コマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-114">For information about how to disconnect from the WinRM service on a remote computer, see the Disconnect-WSMan cmdlet.</span></span>

## <span data-ttu-id="ddc1f-115">例</span><span class="sxs-lookup"><span data-stu-id="ddc1f-115">EXAMPLES</span></span>

### <span data-ttu-id="ddc1f-116">例 1: リモートコンピューターに接続する</span><span class="sxs-lookup"><span data-stu-id="ddc1f-116">Example 1: Connect to a remote computer</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01"
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="ddc1f-117">このコマンドは、server01 リモート コンピューターへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-117">This command creates a connection to the remote server01 computer.</span></span>

<span data-ttu-id="ddc1f-118">**接続 wsman** コマンドレットは、通常、リモートコンピューター (この場合は server01 コンピューター) に接続するために、wsman プロバイダーのコンテキストで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-118">The **Connect-WSMan** cmdlet is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="ddc1f-119">ただし、WSMan プロバイダーに変更する前に、このコマンドレットを使用して、リモート コンピューターへの接続を確立することができます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-119">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="ddc1f-120">これらの接続は、 **ComputerName** の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-120">Those connections appear in the **ComputerName** list.</span></span>

### <span data-ttu-id="ddc1f-121">例 2: 管理者の資格情報を使用してリモートコンピューターに接続する</span><span class="sxs-lookup"><span data-stu-id="ddc1f-121">Example 2: Connect to a remote computer by using Administrator credentials</span></span>

```
PS C:\> $cred = Get-Credential Administrator
PS C:\> Connect-WSMan -ComputerName "server01" -Credential $cred
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="ddc1f-122">このコマンドは、管理者アカウントの資格情報を使用して、リモート システム server01 への接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-122">This command creates a connection to the remote system server01 using the Administrator account credentials.</span></span>

<span data-ttu-id="ddc1f-123">最初のコマンドは、Get-Credential コマンドレットを使用して、管理者の資格情報を取得し、$cred 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-123">The first command uses the Get-Credential cmdlet to get the Administrator credentials and then stores them in the $cred variable.</span></span>
<span data-ttu-id="ddc1f-124">**Get-Credential** は、システムレジストリ設定に応じて、ダイアログボックスまたはコマンドラインを使用して、ユーザー名とパスワードのパスワードを入力するように求めます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-124">**Get-Credential** prompts you for a password of username and password through a dialog box or at the command line, depending on system registry settings.</span></span>

<span data-ttu-id="ddc1f-125">2番目のコマンドは、 *Credential* パラメーターを使用して、$cred に格納されている資格情報を **接続 WSMan** に渡します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-125">The second command uses the *Credential* parameter to pass the credentials stored in $cred to **Connect-WSMan**.</span></span>
<span data-ttu-id="ddc1f-126">次に、管理者の資格情報を使用して、リモートシステム server01 に **接続** します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-126">**Connect-WSMan** then connects to the remote system server01 by using the Administrator credentials.</span></span>

### <span data-ttu-id="ddc1f-127">例 3: 指定されたポートを経由してリモートコンピューターに接続する</span><span class="sxs-lookup"><span data-stu-id="ddc1f-127">Example 3: Connect to a remote computer over a specified port</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01" -Port 80
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="ddc1f-128">このコマンドは、ポート 80 を介した server01 リモート コンピューターへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-128">This command creates a connection to the remote server01 computer over port 80.</span></span>

### <span data-ttu-id="ddc1f-129">例 4: 接続オプションを使用してリモートコンピューターに接続する</span><span class="sxs-lookup"><span data-stu-id="ddc1f-129">Example 4: Connect to a remote computer by using connection options</span></span>

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="ddc1f-130">この例で **は、server01 コマンドで** 定義されている接続オプションを使用して、リモートコンピューターへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-130">This example creates a connection to the remote server01 computer by using the connection options that are defined in the **New-WSManSessionOption** command.</span></span>

<span data-ttu-id="ddc1f-131">最初のコマンドは、 **New-WSManSessionOption** を使用して、一連の接続設定オプションを $a 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-131">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="ddc1f-132">この場合は、セッション オプションで接続のタイムアウトを 30 秒 (30,000 ミリ秒) に設定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-132">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="ddc1f-133">2番目のコマンドは、 *Sessionoption* パラメーターを使用して、$a 変数に格納されている資格情報を **接続 WSMan** に渡します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-133">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="ddc1f-134">次に、指定されたセッションオプションを使用して、リモートの server01 コンピューターに **接続** します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-134">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

## <span data-ttu-id="ddc1f-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ddc1f-135">PARAMETERS</span></span>

### <span data-ttu-id="ddc1f-136">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="ddc1f-136">-ApplicationName</span></span>
<span data-ttu-id="ddc1f-137">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-137">Specifies the application name in the connection.</span></span>
<span data-ttu-id="ddc1f-138">*ApplicationName* パラメーターの既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-138">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="ddc1f-139">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-139">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="ddc1f-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="ddc1f-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="ddc1f-141">例: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="ddc1f-141">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="ddc1f-142">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-142">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="ddc1f-143">この WSMAN の既定の設定は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-143">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="ddc1f-144">このパラメーターは、多くのコンピューターが PowerShell を実行する1台のコンピューターへのリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-144">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="ddc1f-145">この場合、IIS は効率を上げるために Web Services for Management (WS-MANAGEMENT) をホストします。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-145">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="ddc1f-146">-認証</span><span class="sxs-lookup"><span data-stu-id="ddc1f-146">-Authentication</span></span>
<span data-ttu-id="ddc1f-147">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-147">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="ddc1f-148">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ddc1f-149">基本。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-149">Basic.</span></span>
<span data-ttu-id="ddc1f-150">Basic は、ユーザー名およびパスワードがクリア テキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-150">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="ddc1f-151">既定値。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-151">Default.</span></span>
<span data-ttu-id="ddc1f-152">WS-Management プロトコルによって実装されている認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-152">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="ddc1f-153">既定値です。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-153">This is the default.</span></span>
- <span data-ttu-id="ddc1f-154">ダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-154">Digest.</span></span>
<span data-ttu-id="ddc1f-155">Digest は、サーバーで指定されたデータ文字列をチャレンジで使用するチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-155">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="ddc1f-156">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-156">Kerberos.</span></span>
<span data-ttu-id="ddc1f-157">クライアント コンピューターとサーバーが Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-157">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="ddc1f-158">Negotiate</span><span class="sxs-lookup"><span data-stu-id="ddc1f-158">Negotiate.</span></span>
<span data-ttu-id="ddc1f-159">Negotiate は、認証で使用するスキームを特定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-159">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="ddc1f-160">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されているかをネゴシエーションで判断できます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-160">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="ddc1f-161">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="ddc1f-161">CredSSP.</span></span>
<span data-ttu-id="ddc1f-162">Credential Security Support Provider (CredSSP) 認証を使用して、ユーザーが資格情報を委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-162">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="ddc1f-163">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-163">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="ddc1f-164">注意: CredSSP は、ローカルコンピューターからリモートコンピューターにユーザーの資格情報を委任します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-164">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="ddc1f-165">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-165">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="ddc1f-166">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-166">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="ddc1f-167">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="ddc1f-167">-CertificateThumbprint</span></span>
<span data-ttu-id="ddc1f-168">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-168">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="ddc1f-169">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-169">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="ddc1f-170">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-170">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="ddc1f-171">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-171">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="ddc1f-172">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-172">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="ddc1f-173">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="ddc1f-173">-ComputerName</span></span>
<span data-ttu-id="ddc1f-174">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-174">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="ddc1f-175">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-175">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="ddc1f-176">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-176">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="ddc1f-177">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-177">The local computer is the default.</span></span>
<span data-ttu-id="ddc1f-178">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-178">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="ddc1f-179">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-179">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ddc1f-180">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="ddc1f-180">-ConnectionURI</span></span>
<span data-ttu-id="ddc1f-181">接続エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-181">Specifies the connection endpoint.</span></span>
<span data-ttu-id="ddc1f-182">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-182">The format of this string is as follows:</span></span>

<span data-ttu-id="ddc1f-183">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="ddc1f-183">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="ddc1f-184">次の文字列は、このパラメーターに対して正しく書式設定された値です。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-184">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="ddc1f-185">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-185">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="ddc1f-186">-Credential</span><span class="sxs-lookup"><span data-stu-id="ddc1f-186">-Credential</span></span>
<span data-ttu-id="ddc1f-187">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-187">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="ddc1f-188">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-188">The default is the current user.</span></span>
<span data-ttu-id="ddc1f-189">User01、Domain01\user01」、などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-189">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="ddc1f-190">または、Get-Credential コマンドレットによって返されるような **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-190">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="ddc1f-191">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-191">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="ddc1f-192">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="ddc1f-192">-OptionSet</span></span>
<span data-ttu-id="ddc1f-193">要求の性質を変更または調整するための一連のスイッチをサービスに指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-193">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="ddc1f-194">これらは、サービス固有であるため、コマンドラインシェルで使用されるスイッチに似ています。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-194">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="ddc1f-195">任意の数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-195">Any number of options can be specified.</span></span>

<span data-ttu-id="ddc1f-196">次の例では、a、b、および c パラメーターに値 1、2、および 3 を渡す構文を示します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-196">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="ddc1f-197">-Port</span><span class="sxs-lookup"><span data-stu-id="ddc1f-197">-Port</span></span>
<span data-ttu-id="ddc1f-198">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-198">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="ddc1f-199">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-199">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="ddc1f-200">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-200">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="ddc1f-201">HTTPS をトランスポートとして使用する場合は、 *ComputerName* パラメーターの値がサーバーの証明書共通名 (CN) と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-201">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="ddc1f-202">ただし、 *Sessionoption* パラメーターの一部として *skipcncheck* パラメーターを指定した場合、サーバーの証明書の共通名がサーバーのホスト名と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-202">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="ddc1f-203">*Skipcncheck* パラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-203">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="ddc1f-204">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="ddc1f-204">-SessionOption</span></span>
<span data-ttu-id="ddc1f-205">WS-Management セッションの拡張オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-205">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="ddc1f-206">New-WSManSessionOption コマンドレットを使用して作成する **Sessionoption** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-206">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="ddc1f-207">使用可能なオプションの詳細については、「」と入力 `Get-Help New-WSManSessionOption` してください。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-207">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="ddc1f-208">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="ddc1f-208">-UseSSL</span></span>
<span data-ttu-id="ddc1f-209">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-209">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="ddc1f-210">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-210">By default, SSL is not used.</span></span>

<span data-ttu-id="ddc1f-211">WS-Management は、ネットワーク経由で転送されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-211">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="ddc1f-212">*UseSSL* パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-212">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="ddc1f-213">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-213">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="ddc1f-214">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ddc1f-214">CommonParameters</span></span>
<span data-ttu-id="ddc1f-215">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ddc1f-216">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ddc1f-217">入力</span><span class="sxs-lookup"><span data-stu-id="ddc1f-217">INPUTS</span></span>

### <span data-ttu-id="ddc1f-218">なし</span><span class="sxs-lookup"><span data-stu-id="ddc1f-218">None</span></span>
<span data-ttu-id="ddc1f-219">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-219">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="ddc1f-220">出力</span><span class="sxs-lookup"><span data-stu-id="ddc1f-220">OUTPUTS</span></span>

### <span data-ttu-id="ddc1f-221">なし</span><span class="sxs-lookup"><span data-stu-id="ddc1f-221">None</span></span>
<span data-ttu-id="ddc1f-222">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-222">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ddc1f-223">注</span><span class="sxs-lookup"><span data-stu-id="ddc1f-223">NOTES</span></span>

* <span data-ttu-id="ddc1f-224">WS-Management セッションを作成せずに、リモート コンピューターで管理コマンドを実行することや、管理データを照会することができます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-224">You can run management commands or query management data on a remote computer without creating a WS-Management session.</span></span> <span data-ttu-id="ddc1f-225">これを行うには、Invoke-WSManAction の *ComputerName* パラメーターと、を使用します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-225">You can do this by using the *ComputerName* parameters of Invoke-WSManAction and Get-WSManInstance.</span></span> <span data-ttu-id="ddc1f-226">*ComputerName* パラメーターを使用すると、PowerShell は、単一のコマンドに使用される一時的な接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-226">When you use the *ComputerName* parameter, PowerShell creates a temporary connection that is used for the single command.</span></span> <span data-ttu-id="ddc1f-227">コマンドの実行後、その接続は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="ddc1f-227">After the command runs, the connection is closed.</span></span>

*

## <span data-ttu-id="ddc1f-228">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ddc1f-228">RELATED LINKS</span></span>

[<span data-ttu-id="ddc1f-229">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="ddc1f-229">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="ddc1f-230">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="ddc1f-230">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="ddc1f-231">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="ddc1f-231">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="ddc1f-232">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="ddc1f-232">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="ddc1f-233">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ddc1f-233">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="ddc1f-234">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="ddc1f-234">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="ddc1f-235">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ddc1f-235">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="ddc1f-236">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="ddc1f-236">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="ddc1f-237">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ddc1f-237">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="ddc1f-238">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ddc1f-238">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="ddc1f-239">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="ddc1f-239">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="ddc1f-240">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="ddc1f-240">Test-WSMan</span></span>](Test-WSMan.md)


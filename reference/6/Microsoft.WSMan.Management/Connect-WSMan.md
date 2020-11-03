---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: d06ede0e27713b1a309aa2ed265f02881d34124e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217088"
---
# <span data-ttu-id="555b7-103">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="555b7-103">Connect-WSMan</span></span>

## <span data-ttu-id="555b7-104">概要</span><span class="sxs-lookup"><span data-stu-id="555b7-104">SYNOPSIS</span></span>
<span data-ttu-id="555b7-105">リモート コンピューター上の WinRM サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="555b7-105">Connects to the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="555b7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="555b7-106">SYNTAX</span></span>

### <span data-ttu-id="555b7-107">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="555b7-107">ComputerName (Default)</span></span>

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="555b7-108">URI</span><span class="sxs-lookup"><span data-stu-id="555b7-108">URI</span></span>

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="555b7-109">Description</span><span class="sxs-lookup"><span data-stu-id="555b7-109">DESCRIPTION</span></span>
<span data-ttu-id="555b7-110">**接続 WSMan** コマンドレットは、リモートコンピューター上の WinRM サービスに接続し、リモートコンピューターへの永続的な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="555b7-110">The **Connect-WSMan** cmdlet connects to the WinRM service on a remote computer, and it establishes a persistent connection to the remote computer.</span></span>
<span data-ttu-id="555b7-111">このコマンドレットを WSMan プロバイダーのコンテキストで使用して、リモートコンピューター上の WinRM サービスに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="555b7-111">You can use this cmdlet in the context of the WSMan provider to connect to the WinRM service on a remote computer.</span></span>
<span data-ttu-id="555b7-112">ただし、WSMan プロバイダーに変更する前に、このコマンドレットを使用して、リモート コンピューター上の WinRM サービスに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="555b7-112">However, you can also use this cmdlet to connect to the WinRM service on a remote computer before you change to the WSMan provider.</span></span>
<span data-ttu-id="555b7-113">リモートコンピューターは、WSMan プロバイダーのルートディレクトリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="555b7-113">The remote computer appears in the root directory of the WSMan provider.</span></span>

<span data-ttu-id="555b7-114">クライアントとサーバー コンピューターが別のドメインまたはワークグループに属している場合は、明示的な資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="555b7-114">Explicit credentials are required when the client and server computers are in different domains or workgroups.</span></span>

<span data-ttu-id="555b7-115">リモートコンピューター上の WinRM サービスから切断する方法の詳細については、Disconnect-WSMan コマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="555b7-115">For information about how to disconnect from the WinRM service on a remote computer, see the Disconnect-WSMan cmdlet.</span></span>

## <span data-ttu-id="555b7-116">例</span><span class="sxs-lookup"><span data-stu-id="555b7-116">EXAMPLES</span></span>

### <span data-ttu-id="555b7-117">例 1: リモートコンピューターに接続する</span><span class="sxs-lookup"><span data-stu-id="555b7-117">Example 1: Connect to a remote computer</span></span>

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

<span data-ttu-id="555b7-118">このコマンドは、server01 リモート コンピューターへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="555b7-118">This command creates a connection to the remote server01 computer.</span></span>

<span data-ttu-id="555b7-119">**接続 wsman** コマンドレットは、通常、リモートコンピューター (この場合は server01 コンピューター) に接続するために、wsman プロバイダーのコンテキストで使用されます。</span><span class="sxs-lookup"><span data-stu-id="555b7-119">The **Connect-WSMan** cmdlet is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="555b7-120">ただし、WSMan プロバイダーに変更する前に、このコマンドレットを使用して、リモート コンピューターへの接続を確立することができます。</span><span class="sxs-lookup"><span data-stu-id="555b7-120">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="555b7-121">これらの接続は、 **ComputerName** の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="555b7-121">Those connections appear in the **ComputerName** list.</span></span>

### <span data-ttu-id="555b7-122">例 2: 管理者の資格情報を使用してリモートコンピューターに接続する</span><span class="sxs-lookup"><span data-stu-id="555b7-122">Example 2: Connect to a remote computer by using Administrator credentials</span></span>

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

<span data-ttu-id="555b7-123">このコマンドは、管理者アカウントの資格情報を使用して、リモート システム server01 への接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="555b7-123">This command creates a connection to the remote system server01 using the Administrator account credentials.</span></span>

<span data-ttu-id="555b7-124">最初のコマンドは、Get-Credential コマンドレットを使用して、管理者の資格情報を取得し、$cred 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="555b7-124">The first command uses the Get-Credential cmdlet to get the Administrator credentials and then stores them in the $cred variable.</span></span>
<span data-ttu-id="555b7-125">**Get-Credential** は、システムレジストリ設定に応じて、ダイアログボックスまたはコマンドラインを使用して、ユーザー名とパスワードのパスワードを入力するように求めます。</span><span class="sxs-lookup"><span data-stu-id="555b7-125">**Get-Credential** prompts you for a password of username and password through a dialog box or at the command line, depending on system registry settings.</span></span>

<span data-ttu-id="555b7-126">2番目のコマンドは、 *Credential* パラメーターを使用して、$cred に格納されている資格情報を **接続 WSMan** に渡します。</span><span class="sxs-lookup"><span data-stu-id="555b7-126">The second command uses the *Credential* parameter to pass the credentials stored in $cred to **Connect-WSMan**.</span></span>
<span data-ttu-id="555b7-127">次に、管理者の資格情報を使用して、リモートシステム server01 に **接続** します。</span><span class="sxs-lookup"><span data-stu-id="555b7-127">**Connect-WSMan** then connects to the remote system server01 by using the Administrator credentials.</span></span>

### <span data-ttu-id="555b7-128">例 3: 指定されたポートを経由してリモートコンピューターに接続する</span><span class="sxs-lookup"><span data-stu-id="555b7-128">Example 3: Connect to a remote computer over a specified port</span></span>

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

<span data-ttu-id="555b7-129">このコマンドは、ポート 80 を介した server01 リモート コンピューターへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="555b7-129">This command creates a connection to the remote server01 computer over port 80.</span></span>

### <span data-ttu-id="555b7-130">例 4: 接続オプションを使用してリモートコンピューターに接続する</span><span class="sxs-lookup"><span data-stu-id="555b7-130">Example 4: Connect to a remote computer by using connection options</span></span>

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

<span data-ttu-id="555b7-131">この例で **は、server01 コマンドで** 定義されている接続オプションを使用して、リモートコンピューターへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="555b7-131">This example creates a connection to the remote server01 computer by using the connection options that are defined in the **New-WSManSessionOption** command.</span></span>

<span data-ttu-id="555b7-132">最初のコマンドは、 **New-WSManSessionOption** を使用して、一連の接続設定オプションを $a 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="555b7-132">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="555b7-133">この場合は、セッション オプションで接続のタイムアウトを 30 秒 (30,000 ミリ秒) に設定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-133">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="555b7-134">2番目のコマンドは、 *Sessionoption* パラメーターを使用して、$a 変数に格納されている資格情報を **接続 WSMan** に渡します。</span><span class="sxs-lookup"><span data-stu-id="555b7-134">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="555b7-135">次に、指定されたセッションオプションを使用して、リモートの server01 コンピューターに **接続** します。</span><span class="sxs-lookup"><span data-stu-id="555b7-135">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

## <span data-ttu-id="555b7-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="555b7-136">PARAMETERS</span></span>

### <span data-ttu-id="555b7-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="555b7-137">-ApplicationName</span></span>
<span data-ttu-id="555b7-138">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="555b7-139">*ApplicationName* パラメーターの既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="555b7-139">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="555b7-140">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="555b7-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="555b7-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="555b7-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="555b7-142">例: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="555b7-142">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="555b7-143">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="555b7-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="555b7-144">この WSMAN の既定の設定は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="555b7-144">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="555b7-145">このパラメーターは、多くのコンピューターが PowerShell を実行する1台のコンピューターへのリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="555b7-145">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="555b7-146">この場合、IIS は効率を上げるために Web Services for Management (WS-MANAGEMENT) をホストします。</span><span class="sxs-lookup"><span data-stu-id="555b7-146">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="555b7-147">-認証</span><span class="sxs-lookup"><span data-stu-id="555b7-147">-Authentication</span></span>
<span data-ttu-id="555b7-148">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-148">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="555b7-149">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="555b7-149">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="555b7-150">基本。</span><span class="sxs-lookup"><span data-stu-id="555b7-150">Basic.</span></span>
<span data-ttu-id="555b7-151">Basic は、ユーザー名およびパスワードがクリア テキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="555b7-151">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="555b7-152">既定値。</span><span class="sxs-lookup"><span data-stu-id="555b7-152">Default.</span></span>
<span data-ttu-id="555b7-153">WS-Management プロトコルによって実装されている認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="555b7-153">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="555b7-154">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="555b7-154">This is the default.</span></span>
- <span data-ttu-id="555b7-155">ダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="555b7-155">Digest.</span></span>
<span data-ttu-id="555b7-156">Digest は、サーバーで指定されたデータ文字列をチャレンジで使用するチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="555b7-156">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="555b7-157">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="555b7-157">Kerberos.</span></span>
<span data-ttu-id="555b7-158">クライアント コンピューターとサーバーが Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="555b7-158">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="555b7-159">Negotiate</span><span class="sxs-lookup"><span data-stu-id="555b7-159">Negotiate.</span></span>
<span data-ttu-id="555b7-160">Negotiate は、認証で使用するスキームを特定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="555b7-160">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="555b7-161">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されているかをネゴシエーションで判断できます。</span><span class="sxs-lookup"><span data-stu-id="555b7-161">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="555b7-162">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="555b7-162">CredSSP.</span></span>
<span data-ttu-id="555b7-163">Credential Security Support Provider (CredSSP) 認証を使用して、ユーザーが資格情報を委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="555b7-163">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="555b7-164">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="555b7-164">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="555b7-165">注意: CredSSP は、ローカルコンピューターからリモートコンピューターにユーザーの資格情報を委任します。</span><span class="sxs-lookup"><span data-stu-id="555b7-165">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="555b7-166">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="555b7-166">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="555b7-167">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="555b7-167">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="555b7-168">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="555b7-168">-CertificateThumbprint</span></span>
<span data-ttu-id="555b7-169">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-169">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="555b7-170">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="555b7-170">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="555b7-171">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="555b7-171">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="555b7-172">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="555b7-172">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="555b7-173">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="555b7-173">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="555b7-174">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="555b7-174">-ComputerName</span></span>
<span data-ttu-id="555b7-175">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-175">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="555b7-176">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="555b7-176">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="555b7-177">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="555b7-177">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="555b7-178">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="555b7-178">The local computer is the default.</span></span>
<span data-ttu-id="555b7-179">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="555b7-179">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="555b7-180">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="555b7-180">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="555b7-181">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="555b7-181">-ConnectionURI</span></span>
<span data-ttu-id="555b7-182">接続エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-182">Specifies the connection endpoint.</span></span>
<span data-ttu-id="555b7-183">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="555b7-183">The format of this string is as follows:</span></span>

<span data-ttu-id="555b7-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="555b7-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="555b7-185">次の文字列は、このパラメーターに対して正しく書式設定された値です。</span><span class="sxs-lookup"><span data-stu-id="555b7-185">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="555b7-186">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="555b7-186">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="555b7-187">-Credential</span><span class="sxs-lookup"><span data-stu-id="555b7-187">-Credential</span></span>
<span data-ttu-id="555b7-188">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-188">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="555b7-189">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="555b7-189">The default is the current user.</span></span>
<span data-ttu-id="555b7-190">User01、Domain01\user01」、などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="555b7-190">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="555b7-191">または、Get-Credential コマンドレットによって返されるような **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="555b7-191">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="555b7-192">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="555b7-192">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="555b7-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="555b7-193">-OptionSet</span></span>
<span data-ttu-id="555b7-194">要求の性質を変更または調整するための一連のスイッチをサービスに指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="555b7-195">これらは、サービス固有であるため、コマンドラインシェルで使用されるスイッチに似ています。</span><span class="sxs-lookup"><span data-stu-id="555b7-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="555b7-196">任意の数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="555b7-196">Any number of options can be specified.</span></span>

<span data-ttu-id="555b7-197">次の例では、a、b、および c パラメーターに値 1、2、および 3 を渡す構文を示します。</span><span class="sxs-lookup"><span data-stu-id="555b7-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="555b7-198">-Port</span><span class="sxs-lookup"><span data-stu-id="555b7-198">-Port</span></span>
<span data-ttu-id="555b7-199">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="555b7-200">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="555b7-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="555b7-201">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="555b7-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="555b7-202">HTTPS をトランスポートとして使用する場合は、 *ComputerName* パラメーターの値がサーバーの証明書共通名 (CN) と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="555b7-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="555b7-203">ただし、 *Sessionoption* パラメーターの一部として *skipcncheck* パラメーターを指定した場合、サーバーの証明書の共通名がサーバーのホスト名と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="555b7-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="555b7-204">*Skipcncheck* パラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="555b7-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="555b7-205">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="555b7-205">-SessionOption</span></span>
<span data-ttu-id="555b7-206">WS-Management セッションの拡張オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-206">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="555b7-207">New-WSManSessionOption コマンドレットを使用して作成する **Sessionoption** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="555b7-207">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="555b7-208">使用可能なオプションの詳細については、「」と入力 `Get-Help New-WSManSessionOption` してください。</span><span class="sxs-lookup"><span data-stu-id="555b7-208">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="555b7-209">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="555b7-209">-UseSSL</span></span>
<span data-ttu-id="555b7-210">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="555b7-210">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="555b7-211">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="555b7-211">By default, SSL is not used.</span></span>

<span data-ttu-id="555b7-212">WS-Management は、ネットワーク経由で転送されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="555b7-212">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="555b7-213">*UseSSL* パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="555b7-213">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="555b7-214">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="555b7-214">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="555b7-215">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="555b7-215">CommonParameters</span></span>
<span data-ttu-id="555b7-216">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="555b7-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="555b7-217">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="555b7-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="555b7-218">入力</span><span class="sxs-lookup"><span data-stu-id="555b7-218">INPUTS</span></span>

### <span data-ttu-id="555b7-219">なし</span><span class="sxs-lookup"><span data-stu-id="555b7-219">None</span></span>
<span data-ttu-id="555b7-220">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="555b7-220">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="555b7-221">出力</span><span class="sxs-lookup"><span data-stu-id="555b7-221">OUTPUTS</span></span>

### <span data-ttu-id="555b7-222">なし</span><span class="sxs-lookup"><span data-stu-id="555b7-222">None</span></span>
<span data-ttu-id="555b7-223">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="555b7-223">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="555b7-224">注</span><span class="sxs-lookup"><span data-stu-id="555b7-224">NOTES</span></span>

* <span data-ttu-id="555b7-225">WS-Management セッションを作成せずに、リモート コンピューターで管理コマンドを実行することや、管理データを照会することができます。</span><span class="sxs-lookup"><span data-stu-id="555b7-225">You can run management commands or query management data on a remote computer without creating a WS-Management session.</span></span> <span data-ttu-id="555b7-226">これを行うには、Invoke-WSManAction の *ComputerName* パラメーターと、を使用します。</span><span class="sxs-lookup"><span data-stu-id="555b7-226">You can do this by using the *ComputerName* parameters of Invoke-WSManAction and Get-WSManInstance.</span></span> <span data-ttu-id="555b7-227">*ComputerName* パラメーターを使用すると、PowerShell は、単一のコマンドに使用される一時的な接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="555b7-227">When you use the *ComputerName* parameter, PowerShell creates a temporary connection that is used for the single command.</span></span> <span data-ttu-id="555b7-228">コマンドの実行後、その接続は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="555b7-228">After the command runs, the connection is closed.</span></span>

*

## <span data-ttu-id="555b7-229">関連リンク</span><span class="sxs-lookup"><span data-stu-id="555b7-229">RELATED LINKS</span></span>

[<span data-ttu-id="555b7-230">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="555b7-230">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="555b7-231">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="555b7-231">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="555b7-232">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="555b7-232">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="555b7-233">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="555b7-233">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="555b7-234">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="555b7-234">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="555b7-235">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="555b7-235">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="555b7-236">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="555b7-236">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="555b7-237">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="555b7-237">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="555b7-238">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="555b7-238">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="555b7-239">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="555b7-239">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="555b7-240">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="555b7-240">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="555b7-241">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="555b7-241">Test-WSMan</span></span>](Test-WSMan.md)

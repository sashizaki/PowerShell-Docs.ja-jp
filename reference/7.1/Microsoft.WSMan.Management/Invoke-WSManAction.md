---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: 112b4a1e0a790c32b6a3ea2011fbc72ec86a0324
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218715"
---
# <span data-ttu-id="25c6e-103">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="25c6e-103">Invoke-WSManAction</span></span>

## <span data-ttu-id="25c6e-104">概要</span><span class="sxs-lookup"><span data-stu-id="25c6e-104">SYNOPSIS</span></span>
<span data-ttu-id="25c6e-105">リソース URI とセレクターによって指定されたオブジェクトのアクションを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-105">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="25c6e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="25c6e-106">SYNTAX</span></span>

### <span data-ttu-id="25c6e-107">URI (既定)</span><span class="sxs-lookup"><span data-stu-id="25c6e-107">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="25c6e-108">[ComputerName]</span><span class="sxs-lookup"><span data-stu-id="25c6e-108">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="25c6e-109">Description</span><span class="sxs-lookup"><span data-stu-id="25c6e-109">DESCRIPTION</span></span>
<span data-ttu-id="25c6e-110">**呼び出し WSManAction** は、RESOURCE_URI で指定されたオブジェクトに対してアクションを実行します。ここで、パラメーターはキーと値のペアによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-110">The **Invoke-WSManAction** runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="25c6e-111">このコマンドレットは、WSMan の接続/トランスポート層を使用して、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-111">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="25c6e-112">例</span><span class="sxs-lookup"><span data-stu-id="25c6e-112">EXAMPLES</span></span>

### <span data-ttu-id="25c6e-113">例 1: メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="25c6e-113">Example 1: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="25c6e-114">このコマンドは、スプーラサービスに対応する Win32_Service WMI クラスインスタンスの **startservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-114">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="25c6e-115">戻り値は、アクションが成功したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-115">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="25c6e-116">この場合、戻り値の 0 は成功を示します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-116">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="25c6e-117">戻り値の 5 は、サービスが既に開始されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-117">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="25c6e-118">例 2: メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="25c6e-118">Example 2: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action stopservice -ResourceURI wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:input.xml -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="25c6e-119">このコマンドは、ファイルからの入力を使用してスプーラサービスの **stopservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-119">This command calls the **StopService** method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="25c6e-120">Input.xml ファイルには、次の内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="25c6e-120">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### <span data-ttu-id="25c6e-121">例 3: 指定されたパラメーター値を使用してメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="25c6e-121">Example 3: Invoke a method with specified parameter values</span></span>

```powershell
Invoke-WSManAction -Action create -ResourceURI wmicimv2/win32_process -ValueSet @{commandline="notepad.exe";currentdirectory="C:\"}
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Process
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ProcessId   : 6356
ReturnValue : 0
```

<span data-ttu-id="25c6e-122">このコマンドは、Win32_Process クラスの **Create** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-122">This command calls the **Create** method of the Win32_Process class.</span></span>
<span data-ttu-id="25c6e-123">メソッドに2つのパラメーター値 Notepad.exe と C:\ を渡します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-123">It passes the method two parameter values, Notepad.exe and C:\.</span></span>
<span data-ttu-id="25c6e-124">その結果、メモ帳を実行する新しいプロセスが作成され、新しいプロセスの現在のディレクトリが C:\ に設定されます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-124">As a result, a new process is created to run Notepad, and the current directory of the new process is set to C:\.</span></span>

### <span data-ttu-id="25c6e-125">例 4: リモートコンピューターでメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="25c6e-125">Example 4: Invoke a method on a remote computer</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -ComputerName server01 -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="25c6e-126">このコマンドは、スプーラサービスに対応する Win32_Service WMI クラスインスタンスの **startservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-126">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="25c6e-127">*ComputerName* パラメーターを指定すると、リモートの server01 コンピューターに対してコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-127">Because the *ComputerName* parameter is specified, the command runs against the remote server01 computer.</span></span>

## <span data-ttu-id="25c6e-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="25c6e-128">PARAMETERS</span></span>

### <span data-ttu-id="25c6e-129">-Action</span><span class="sxs-lookup"><span data-stu-id="25c6e-129">-Action</span></span>
<span data-ttu-id="25c6e-130">ResourceURI およびセレクターによって指定された管理オブジェクトで実行するメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-130">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="25c6e-131">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="25c6e-131">-ApplicationName</span></span>
<span data-ttu-id="25c6e-132">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-132">Specifies the application name in the connection.</span></span>
<span data-ttu-id="25c6e-133">*ApplicationName* パラメーターの既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="25c6e-133">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="25c6e-134">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="25c6e-134">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="25c6e-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="25c6e-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="25c6e-136">例: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="25c6e-136">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="25c6e-137">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-137">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="25c6e-138">この WSMAN の既定の設定は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="25c6e-138">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="25c6e-139">このパラメーターは、多くのコンピューターが PowerShell を実行する1台のコンピューターへのリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="25c6e-139">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="25c6e-140">この場合、IIS は効率を上げるために Web Services for Management (WS-MANAGEMENT) をホストします。</span><span class="sxs-lookup"><span data-stu-id="25c6e-140">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="25c6e-141">-認証</span><span class="sxs-lookup"><span data-stu-id="25c6e-141">-Authentication</span></span>
<span data-ttu-id="25c6e-142">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-142">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="25c6e-143">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="25c6e-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="25c6e-144">基本。</span><span class="sxs-lookup"><span data-stu-id="25c6e-144">Basic.</span></span>
<span data-ttu-id="25c6e-145">Basic は、ユーザー名およびパスワードがクリア テキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="25c6e-145">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="25c6e-146">既定値。</span><span class="sxs-lookup"><span data-stu-id="25c6e-146">Default.</span></span>
<span data-ttu-id="25c6e-147">WS-Management プロトコルによって実装されている認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-147">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="25c6e-148">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="25c6e-148">This is the default.</span></span>
- <span data-ttu-id="25c6e-149">ダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="25c6e-149">Digest.</span></span>
<span data-ttu-id="25c6e-150">Digest は、サーバーで指定されたデータ文字列をチャレンジで使用するチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="25c6e-150">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="25c6e-151">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="25c6e-151">Kerberos.</span></span>
<span data-ttu-id="25c6e-152">クライアント コンピューターとサーバーが Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-152">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="25c6e-153">Negotiate</span><span class="sxs-lookup"><span data-stu-id="25c6e-153">Negotiate.</span></span>
<span data-ttu-id="25c6e-154">Negotiate は、認証で使用するスキームを特定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="25c6e-154">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="25c6e-155">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されているかをネゴシエーションで判断できます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-155">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="25c6e-156">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="25c6e-156">CredSSP.</span></span>
<span data-ttu-id="25c6e-157">Credential Security Support Provider (CredSSP) 認証を使用して、ユーザーが資格情報を委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="25c6e-157">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="25c6e-158">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="25c6e-158">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="25c6e-159">注意: CredSSP は、ローカルコンピューターからリモートコンピューターにユーザーの資格情報を委任します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-159">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="25c6e-160">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="25c6e-160">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="25c6e-161">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="25c6e-161">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="25c6e-162">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="25c6e-162">-CertificateThumbprint</span></span>
<span data-ttu-id="25c6e-163">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-163">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="25c6e-164">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-164">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="25c6e-165">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-165">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="25c6e-166">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="25c6e-166">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="25c6e-167">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-167">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="25c6e-168">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="25c6e-168">-ComputerName</span></span>
<span data-ttu-id="25c6e-169">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-169">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="25c6e-170">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-170">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="25c6e-171">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-171">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="25c6e-172">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="25c6e-172">The local computer is the default.</span></span>
<span data-ttu-id="25c6e-173">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25c6e-173">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="25c6e-174">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-174">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="25c6e-175">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="25c6e-175">-ConnectionURI</span></span>
<span data-ttu-id="25c6e-176">接続エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-176">Specifies the connection endpoint.</span></span>
<span data-ttu-id="25c6e-177">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="25c6e-177">The format of this string is as follows:</span></span>

<span data-ttu-id="25c6e-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="25c6e-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="25c6e-179">次の文字列は、このパラメーターに対して正しく書式設定された値です。</span><span class="sxs-lookup"><span data-stu-id="25c6e-179">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="25c6e-180">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25c6e-180">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="25c6e-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="25c6e-181">-Credential</span></span>
<span data-ttu-id="25c6e-182">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-182">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="25c6e-183">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="25c6e-183">The default is the current user.</span></span>
<span data-ttu-id="25c6e-184">User01、Domain01\user01」、などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-184">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="25c6e-185">または、Get-Credential コマンドレットによって返されるような **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-185">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="25c6e-186">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-186">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="25c6e-187">-FilePath</span><span class="sxs-lookup"><span data-stu-id="25c6e-187">-FilePath</span></span>
<span data-ttu-id="25c6e-188">管理リソースの更新に使用するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-188">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="25c6e-189">管理リソースは、 *ResourceURI* パラメーターと *SelectorSet* パラメーターを使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-189">You specify the management resource by using the *ResourceURI* parameter and the *SelectorSet* parameter.</span></span>
<span data-ttu-id="25c6e-190">たとえば、次のコマンドは、 *FilePath* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-190">For example, the following command uses the *FilePath* parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="25c6e-191">このコマンドは、ファイルからの入力を使用して **スプーラ** サービスの **stopservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-191">This command calls the **StopService** method on the **Spooler** service by using input from a file.</span></span>
<span data-ttu-id="25c6e-192">Input.xml ファイルには、次の内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="25c6e-192">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="25c6e-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="25c6e-193">-OptionSet</span></span>
<span data-ttu-id="25c6e-194">要求の性質を変更または調整するための一連のスイッチをサービスに指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="25c6e-195">これらは、サービス固有であるため、コマンドラインシェルで使用されるスイッチに似ています。</span><span class="sxs-lookup"><span data-stu-id="25c6e-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="25c6e-196">任意の数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-196">Any number of options can be specified.</span></span>

<span data-ttu-id="25c6e-197">次の例では、a、b、および c パラメーターに値 1、2、および 3 を渡す構文を示します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="25c6e-198">-Port</span><span class="sxs-lookup"><span data-stu-id="25c6e-198">-Port</span></span>
<span data-ttu-id="25c6e-199">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="25c6e-200">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="25c6e-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="25c6e-201">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="25c6e-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="25c6e-202">HTTPS をトランスポートとして使用する場合は、 *ComputerName* パラメーターの値がサーバーの証明書共通名 (CN) と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="25c6e-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="25c6e-203">ただし、 *Sessionoption* パラメーターの一部として *skipcncheck* パラメーターを指定した場合、サーバーの証明書の共通名がサーバーのホスト名と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="25c6e-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="25c6e-204">*Skipcncheck* パラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="25c6e-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="25c6e-205">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="25c6e-205">-ResourceURI</span></span>
<span data-ttu-id="25c6e-206">リソースクラスまたはインスタンスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-206">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="25c6e-207">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-207">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="25c6e-208">URI は、リソースのプレフィックスとパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-208">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="25c6e-209">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-209">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="25c6e-210">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="25c6e-210">-SelectorSet</span></span>
<span data-ttu-id="25c6e-211">特定の管理リソース インスタンスの選択に使用する値のペアのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-211">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="25c6e-212">*SelectorSet* は、リソースの複数のインスタンスが存在する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-212">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="25c6e-213">*SelectorSet* の値は、ハッシュテーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="25c6e-213">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="25c6e-214">次の例では、このパラメーターの値を入力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-214">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="25c6e-215">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="25c6e-215">-SessionOption</span></span>
<span data-ttu-id="25c6e-216">WS-Management セッションの拡張オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-216">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="25c6e-217">New-WSManSessionOption コマンドレットを使用して作成する **Sessionoption** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-217">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="25c6e-218">使用可能なオプションの詳細については、「」と入力 `Get-Help New-WSManSessionOption` してください。</span><span class="sxs-lookup"><span data-stu-id="25c6e-218">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="25c6e-219">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="25c6e-219">-UseSSL</span></span>
<span data-ttu-id="25c6e-220">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-220">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="25c6e-221">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="25c6e-221">By default, SSL is not used.</span></span>

<span data-ttu-id="25c6e-222">WS-Management は、ネットワーク経由で転送されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-222">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="25c6e-223">*UseSSL* パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="25c6e-223">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="25c6e-224">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-224">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="25c6e-225">-ValueSet</span><span class="sxs-lookup"><span data-stu-id="25c6e-225">-ValueSet</span></span>
<span data-ttu-id="25c6e-226">管理リソースの変更に役立つハッシュ テーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-226">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="25c6e-227">管理リソースは、 *ResourceURI* と *SelectorSet* を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="25c6e-227">You specify the management resource by using *ResourceURI* and *SelectorSet*.</span></span>
<span data-ttu-id="25c6e-228">*Valueset* パラメーターの値は、ハッシュテーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="25c6e-228">The value of the *ValueSet* parameter must be a hash table.</span></span>

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

### <span data-ttu-id="25c6e-229">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="25c6e-229">CommonParameters</span></span>
<span data-ttu-id="25c6e-230">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="25c6e-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="25c6e-231">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25c6e-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="25c6e-232">入力</span><span class="sxs-lookup"><span data-stu-id="25c6e-232">INPUTS</span></span>

### <span data-ttu-id="25c6e-233">なし</span><span class="sxs-lookup"><span data-stu-id="25c6e-233">None</span></span>
<span data-ttu-id="25c6e-234">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="25c6e-234">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="25c6e-235">出力</span><span class="sxs-lookup"><span data-stu-id="25c6e-235">OUTPUTS</span></span>

### <span data-ttu-id="25c6e-236">なし</span><span class="sxs-lookup"><span data-stu-id="25c6e-236">None</span></span>
<span data-ttu-id="25c6e-237">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="25c6e-237">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="25c6e-238">注</span><span class="sxs-lookup"><span data-stu-id="25c6e-238">NOTES</span></span>

## <span data-ttu-id="25c6e-239">関連リンク</span><span class="sxs-lookup"><span data-stu-id="25c6e-239">RELATED LINKS</span></span>

[<span data-ttu-id="25c6e-240">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="25c6e-240">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="25c6e-241">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="25c6e-241">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="25c6e-242">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="25c6e-242">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="25c6e-243">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="25c6e-243">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="25c6e-244">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="25c6e-244">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="25c6e-245">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="25c6e-245">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="25c6e-246">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="25c6e-246">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="25c6e-247">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="25c6e-247">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="25c6e-248">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="25c6e-248">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="25c6e-249">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="25c6e-249">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="25c6e-250">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="25c6e-250">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="25c6e-251">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="25c6e-251">Test-WSMan</span></span>](Test-WSMan.md)


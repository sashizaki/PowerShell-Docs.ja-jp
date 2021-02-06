---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: e2456e1da866929d60c36cc0e09990399b41614b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600782"
---
# <span data-ttu-id="0437d-102">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="0437d-102">Invoke-WSManAction</span></span>

## <span data-ttu-id="0437d-103">概要</span><span class="sxs-lookup"><span data-stu-id="0437d-103">SYNOPSIS</span></span>
<span data-ttu-id="0437d-104">リソース URI とセレクターによって指定されたオブジェクトのアクションを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0437d-104">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="0437d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0437d-105">SYNTAX</span></span>

### <span data-ttu-id="0437d-106">URI (既定)</span><span class="sxs-lookup"><span data-stu-id="0437d-106">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="0437d-107">[ComputerName]</span><span class="sxs-lookup"><span data-stu-id="0437d-107">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="0437d-108">Description</span><span class="sxs-lookup"><span data-stu-id="0437d-108">DESCRIPTION</span></span>
<span data-ttu-id="0437d-109">**呼び出し WSManAction** は、RESOURCE_URI で指定されたオブジェクトに対してアクションを実行します。ここで、パラメーターはキーと値のペアによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="0437d-109">The **Invoke-WSManAction** runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="0437d-110">このコマンドレットは、WSMan の接続/トランスポート層を使用して、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0437d-110">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="0437d-111">例</span><span class="sxs-lookup"><span data-stu-id="0437d-111">EXAMPLES</span></span>

### <span data-ttu-id="0437d-112">例 1: メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="0437d-112">Example 1: Invoke a method</span></span>

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

<span data-ttu-id="0437d-113">このコマンドは、スプーラサービスに対応する Win32_Service WMI クラスインスタンスの **startservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0437d-113">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="0437d-114">戻り値は、アクションが成功したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0437d-114">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="0437d-115">この場合、戻り値の 0 は成功を示します。</span><span class="sxs-lookup"><span data-stu-id="0437d-115">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="0437d-116">戻り値の 5 は、サービスが既に開始されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="0437d-116">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="0437d-117">例 2: メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="0437d-117">Example 2: Invoke a method</span></span>

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

<span data-ttu-id="0437d-118">このコマンドは、ファイルからの入力を使用してスプーラサービスの **stopservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0437d-118">This command calls the **StopService** method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="0437d-119">Input.xml ファイルには、次の内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0437d-119">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### <span data-ttu-id="0437d-120">例 3: 指定されたパラメーター値を使用してメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="0437d-120">Example 3: Invoke a method with specified parameter values</span></span>

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

<span data-ttu-id="0437d-121">このコマンドは、Win32_Process クラスの **Create** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0437d-121">This command calls the **Create** method of the Win32_Process class.</span></span>
<span data-ttu-id="0437d-122">メソッドに2つのパラメーター値 Notepad.exe と C:\ を渡します。</span><span class="sxs-lookup"><span data-stu-id="0437d-122">It passes the method two parameter values, Notepad.exe and C:\.</span></span>
<span data-ttu-id="0437d-123">その結果、メモ帳を実行する新しいプロセスが作成され、新しいプロセスの現在のディレクトリが C:\ に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0437d-123">As a result, a new process is created to run Notepad, and the current directory of the new process is set to C:\.</span></span>

### <span data-ttu-id="0437d-124">例 4: リモートコンピューターでメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="0437d-124">Example 4: Invoke a method on a remote computer</span></span>

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

<span data-ttu-id="0437d-125">このコマンドは、スプーラサービスに対応する Win32_Service WMI クラスインスタンスの **startservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0437d-125">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="0437d-126">*ComputerName* パラメーターを指定すると、リモートの server01 コンピューターに対してコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0437d-126">Because the *ComputerName* parameter is specified, the command runs against the remote server01 computer.</span></span>

## <span data-ttu-id="0437d-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0437d-127">PARAMETERS</span></span>

### <span data-ttu-id="0437d-128">-Action</span><span class="sxs-lookup"><span data-stu-id="0437d-128">-Action</span></span>
<span data-ttu-id="0437d-129">ResourceURI およびセレクターによって指定された管理オブジェクトで実行するメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-129">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

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

### <span data-ttu-id="0437d-130">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="0437d-130">-ApplicationName</span></span>
<span data-ttu-id="0437d-131">接続のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-131">Specifies the application name in the connection.</span></span>
<span data-ttu-id="0437d-132">*ApplicationName* パラメーターの既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="0437d-132">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="0437d-133">リモート エンドポイントの完全な識別子は、次の形式です。</span><span class="sxs-lookup"><span data-stu-id="0437d-133">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="0437d-134">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="0437d-134">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="0437d-135">例: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="0437d-135">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="0437d-136">セッションをホストするインターネット インフォメーション サービス (IIS) は、このエンドポイントで、指定されたアプリケーションに要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="0437d-136">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="0437d-137">この WSMAN の既定の設定は、ほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="0437d-137">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="0437d-138">このパラメーターは、多くのコンピューターが PowerShell を実行する1台のコンピューターへのリモート接続を確立する場合に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="0437d-138">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="0437d-139">この場合、IIS は効率を上げるために Web Services for Management (WS-MANAGEMENT) をホストします。</span><span class="sxs-lookup"><span data-stu-id="0437d-139">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="0437d-140">-認証</span><span class="sxs-lookup"><span data-stu-id="0437d-140">-Authentication</span></span>
<span data-ttu-id="0437d-141">サーバーで使用される認証メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-141">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="0437d-142">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0437d-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0437d-143">基本。</span><span class="sxs-lookup"><span data-stu-id="0437d-143">Basic.</span></span>
<span data-ttu-id="0437d-144">Basic は、ユーザー名およびパスワードがクリア テキストでサーバーまたはプロキシに送信されるスキームです。</span><span class="sxs-lookup"><span data-stu-id="0437d-144">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="0437d-145">既定値。</span><span class="sxs-lookup"><span data-stu-id="0437d-145">Default.</span></span>
<span data-ttu-id="0437d-146">WS-Management プロトコルによって実装されている認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="0437d-146">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="0437d-147">既定値です。</span><span class="sxs-lookup"><span data-stu-id="0437d-147">This is the default.</span></span>
- <span data-ttu-id="0437d-148">ダイジェスト。</span><span class="sxs-lookup"><span data-stu-id="0437d-148">Digest.</span></span>
<span data-ttu-id="0437d-149">Digest は、サーバーで指定されたデータ文字列をチャレンジで使用するチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="0437d-149">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="0437d-150">Kerberos。</span><span class="sxs-lookup"><span data-stu-id="0437d-150">Kerberos.</span></span>
<span data-ttu-id="0437d-151">クライアント コンピューターとサーバーが Kerberos 証明書を使用して相互に認証します。</span><span class="sxs-lookup"><span data-stu-id="0437d-151">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="0437d-152">Negotiate</span><span class="sxs-lookup"><span data-stu-id="0437d-152">Negotiate.</span></span>
<span data-ttu-id="0437d-153">Negotiate は、認証で使用するスキームを特定するために、サーバーまたはプロキシとネゴシエートするチャレンジ/レスポンス スキームです。</span><span class="sxs-lookup"><span data-stu-id="0437d-153">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="0437d-154">たとえば、このパラメーター値を指定すると、Kerberos プロトコルと NTLM のどちらが使用されているかをネゴシエーションで判断できます。</span><span class="sxs-lookup"><span data-stu-id="0437d-154">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="0437d-155">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="0437d-155">CredSSP.</span></span>
<span data-ttu-id="0437d-156">Credential Security Support Provider (CredSSP) 認証を使用して、ユーザーが資格情報を委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0437d-156">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="0437d-157">このオプションは、1 台のリモート コンピューターで実行するが、他のリモート コンピューターからデータを収集するコマンドや、他のリモート コンピューターで追加のコマンドを実行するコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="0437d-157">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="0437d-158">注意: CredSSP は、ローカルコンピューターからリモートコンピューターにユーザーの資格情報を委任します。</span><span class="sxs-lookup"><span data-stu-id="0437d-158">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="0437d-159">そのため、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="0437d-159">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="0437d-160">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡された資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0437d-160">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="0437d-161">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="0437d-161">-CertificateThumbprint</span></span>
<span data-ttu-id="0437d-162">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-162">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="0437d-163">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="0437d-163">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="0437d-164">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="0437d-164">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="0437d-165">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="0437d-165">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="0437d-166">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0437d-166">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="0437d-167">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0437d-167">-ComputerName</span></span>
<span data-ttu-id="0437d-168">管理操作を実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-168">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="0437d-169">値には、完全修飾ドメイン名、NetBIOS 名、または IP アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0437d-169">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="0437d-170">ローカル コンピューターを指定するには、ローカル コンピューター名、localhost、またはドット (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0437d-170">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="0437d-171">ローカル コンピューターは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="0437d-171">The local computer is the default.</span></span>
<span data-ttu-id="0437d-172">リモート コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0437d-172">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="0437d-173">パイプを使用して、このパラメーターの値をコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="0437d-173">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="0437d-174">-ConnectionURI</span><span class="sxs-lookup"><span data-stu-id="0437d-174">-ConnectionURI</span></span>
<span data-ttu-id="0437d-175">接続エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-175">Specifies the connection endpoint.</span></span>
<span data-ttu-id="0437d-176">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0437d-176">The format of this string is as follows:</span></span>

<span data-ttu-id="0437d-177">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="0437d-177">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="0437d-178">次の文字列は、このパラメーターに対して正しく書式設定された値です。</span><span class="sxs-lookup"><span data-stu-id="0437d-178">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="0437d-179">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0437d-179">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="0437d-180">-Credential</span><span class="sxs-lookup"><span data-stu-id="0437d-180">-Credential</span></span>
<span data-ttu-id="0437d-181">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-181">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="0437d-182">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="0437d-182">The default is the current user.</span></span>
<span data-ttu-id="0437d-183">User01、Domain01\user01」、などのユーザー名を入力し User@Domain.com ます。</span><span class="sxs-lookup"><span data-stu-id="0437d-183">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="0437d-184">または、Get-Credential コマンドレットによって返されるような **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="0437d-184">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="0437d-185">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="0437d-185">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="0437d-186">-FilePath</span><span class="sxs-lookup"><span data-stu-id="0437d-186">-FilePath</span></span>
<span data-ttu-id="0437d-187">管理リソースの更新に使用するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-187">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="0437d-188">管理リソースは、 *ResourceURI* パラメーターと *SelectorSet* パラメーターを使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-188">You specify the management resource by using the *ResourceURI* parameter and the *SelectorSet* parameter.</span></span>
<span data-ttu-id="0437d-189">たとえば、次のコマンドは、 *FilePath* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="0437d-189">For example, the following command uses the *FilePath* parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="0437d-190">このコマンドは、ファイルからの入力を使用して **スプーラ** サービスの **stopservice** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0437d-190">This command calls the **StopService** method on the **Spooler** service by using input from a file.</span></span>
<span data-ttu-id="0437d-191">Input.xml ファイルには、次の内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0437d-191">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="0437d-192">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="0437d-192">-OptionSet</span></span>
<span data-ttu-id="0437d-193">要求の性質を変更または調整するための一連のスイッチをサービスに指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-193">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="0437d-194">これらは、サービス固有であるため、コマンドラインシェルで使用されるスイッチに似ています。</span><span class="sxs-lookup"><span data-stu-id="0437d-194">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="0437d-195">任意の数のオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0437d-195">Any number of options can be specified.</span></span>

<span data-ttu-id="0437d-196">次の例では、a、b、および c パラメーターに値 1、2、および 3 を渡す構文を示します。</span><span class="sxs-lookup"><span data-stu-id="0437d-196">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="0437d-197">-Port</span><span class="sxs-lookup"><span data-stu-id="0437d-197">-Port</span></span>
<span data-ttu-id="0437d-198">クライアントが WinRM サービスに接続するときに使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-198">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="0437d-199">トランスポートが HTTP の場合、既定のポートは 80 です。</span><span class="sxs-lookup"><span data-stu-id="0437d-199">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="0437d-200">トランスポートが HTTPS の場合、既定のポートは 443 です。</span><span class="sxs-lookup"><span data-stu-id="0437d-200">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="0437d-201">HTTPS をトランスポートとして使用する場合は、 *ComputerName* パラメーターの値がサーバーの証明書共通名 (CN) と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0437d-201">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="0437d-202">ただし、 *Sessionoption* パラメーターの一部として *skipcncheck* パラメーターを指定した場合、サーバーの証明書の共通名がサーバーのホスト名と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0437d-202">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="0437d-203">*Skipcncheck* パラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="0437d-203">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="0437d-204">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="0437d-204">-ResourceURI</span></span>
<span data-ttu-id="0437d-205">リソースクラスまたはインスタンスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-205">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="0437d-206">URI は、ディスクやプロセスなど、コンピューター上の特定の種類のリソースを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0437d-206">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="0437d-207">URI は、リソースのプレフィックスとパスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="0437d-207">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="0437d-208">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0437d-208">For example:</span></span>

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

### <span data-ttu-id="0437d-209">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="0437d-209">-SelectorSet</span></span>
<span data-ttu-id="0437d-210">特定の管理リソース インスタンスの選択に使用する値のペアのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-210">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="0437d-211">*SelectorSet* は、リソースの複数のインスタンスが存在する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="0437d-211">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="0437d-212">*SelectorSet* の値は、ハッシュテーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0437d-212">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="0437d-213">次の例では、このパラメーターの値を入力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0437d-213">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="0437d-214">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="0437d-214">-SessionOption</span></span>
<span data-ttu-id="0437d-215">WS-Management セッションの拡張オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-215">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="0437d-216">New-WSManSessionOption コマンドレットを使用して作成する **Sessionoption** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="0437d-216">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="0437d-217">使用可能なオプションの詳細については、「」と入力 `Get-Help New-WSManSessionOption` してください。</span><span class="sxs-lookup"><span data-stu-id="0437d-217">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="0437d-218">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="0437d-218">-UseSSL</span></span>
<span data-ttu-id="0437d-219">リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-219">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="0437d-220">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="0437d-220">By default, SSL is not used.</span></span>

<span data-ttu-id="0437d-221">WS-Management は、ネットワーク経由で転送されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="0437d-221">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="0437d-222">*UseSSL* パラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0437d-222">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="0437d-223">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0437d-223">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="0437d-224">-ValueSet</span><span class="sxs-lookup"><span data-stu-id="0437d-224">-ValueSet</span></span>
<span data-ttu-id="0437d-225">管理リソースの変更に役立つハッシュ テーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-225">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="0437d-226">管理リソースは、 *ResourceURI* と *SelectorSet* を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="0437d-226">You specify the management resource by using *ResourceURI* and *SelectorSet*.</span></span>
<span data-ttu-id="0437d-227">*Valueset* パラメーターの値は、ハッシュテーブルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0437d-227">The value of the *ValueSet* parameter must be a hash table.</span></span>

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

### <span data-ttu-id="0437d-228">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0437d-228">CommonParameters</span></span>
<span data-ttu-id="0437d-229">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0437d-229">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0437d-230">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0437d-230">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0437d-231">入力</span><span class="sxs-lookup"><span data-stu-id="0437d-231">INPUTS</span></span>

### <span data-ttu-id="0437d-232">なし</span><span class="sxs-lookup"><span data-stu-id="0437d-232">None</span></span>
<span data-ttu-id="0437d-233">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="0437d-233">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="0437d-234">出力</span><span class="sxs-lookup"><span data-stu-id="0437d-234">OUTPUTS</span></span>

### <span data-ttu-id="0437d-235">なし</span><span class="sxs-lookup"><span data-stu-id="0437d-235">None</span></span>
<span data-ttu-id="0437d-236">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="0437d-236">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0437d-237">注</span><span class="sxs-lookup"><span data-stu-id="0437d-237">NOTES</span></span>

## <span data-ttu-id="0437d-238">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0437d-238">RELATED LINKS</span></span>

[<span data-ttu-id="0437d-239">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0437d-239">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="0437d-240">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0437d-240">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="0437d-241">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="0437d-241">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="0437d-242">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0437d-242">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="0437d-243">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="0437d-243">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="0437d-244">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0437d-244">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="0437d-245">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0437d-245">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="0437d-246">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="0437d-246">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="0437d-247">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0437d-247">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="0437d-248">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="0437d-248">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="0437d-249">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="0437d-249">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="0437d-250">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="0437d-250">Test-WSMan</span></span>](Test-WSMan.md)


---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: 6d926200ae923157c0b7d7556ef13400036b8437
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212419"
---
# <span data-ttu-id="c7d67-103">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="c7d67-103">New-CimSessionOption</span></span>

## <span data-ttu-id="c7d67-104">概要</span><span class="sxs-lookup"><span data-stu-id="c7d67-104">SYNOPSIS</span></span>
<span data-ttu-id="c7d67-105">New-CimSession コマンドレットの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-105">Specifies advanced options for the New-CimSession cmdlet.</span></span>

## <span data-ttu-id="c7d67-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c7d67-106">SYNTAX</span></span>

### <span data-ttu-id="c7d67-107">ProtocolTypeSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="c7d67-107">ProtocolTypeSet (Default)</span></span>

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### <span data-ttu-id="c7d67-108">WSManParameterSet</span><span class="sxs-lookup"><span data-stu-id="c7d67-108">WSManParameterSet</span></span>

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### <span data-ttu-id="c7d67-109">DcomParameterSet</span><span class="sxs-lookup"><span data-stu-id="c7d67-109">DcomParameterSet</span></span>

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## <span data-ttu-id="c7d67-110">Description</span><span class="sxs-lookup"><span data-stu-id="c7d67-110">DESCRIPTION</span></span>

<span data-ttu-id="c7d67-111">コマンドレットでは、 `New-CimSessionOption` CIM セッションオプションオブジェクトのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-111">The `New-CimSessionOption` cmdlet creates an instance of a CIM session options object.</span></span> <span data-ttu-id="c7d67-112">Cim セッションオプションオブジェクトをコマンドレットへの入力として使用して、 `New-CimSession` cim セッションのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-112">You use a CIM session options object as input to the `New-CimSession` cmdlet to specify the options for a CIM session.</span></span>

<span data-ttu-id="c7d67-113">このコマンドレットには2つのパラメーターセットがあります。1つは WsMan オプション用で、もう1つは分散コンポーネントオブジェクトモデル (DCOM) オプション用です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-113">This cmdlet has two parameter sets, one for WsMan options and one for Distributed Component Object Model (DCOM) options.</span></span> <span data-ttu-id="c7d67-114">コマンドレットは、使用するパラメーターに応じて、DCOM セッションオプションのインスタンスを返すか、WsMan セッションオプションを返します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-114">Depending on which parameters you use, the cmdlet returns either an instance of DCOM session options or returns WsMan session options.</span></span>

## <span data-ttu-id="c7d67-115">例</span><span class="sxs-lookup"><span data-stu-id="c7d67-115">EXAMPLES</span></span>

### <span data-ttu-id="c7d67-116">例 1: DCOM の CIM セッションオプションオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c7d67-116">Example 1: Create a CIM session options object for DCOM</span></span>

<span data-ttu-id="c7d67-117">この例では、DCOM プロトコル用の CIM セッションオプションオブジェクトを作成し、という名前の変数に格納し `$so` ます。</span><span class="sxs-lookup"><span data-stu-id="c7d67-117">This example creates a CIM session options object for the DCOM protocol and stores it in a variable named `$so`.</span></span> <span data-ttu-id="c7d67-118">次に、変数の内容がコマンドレットに渡され `New-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="c7d67-118">The contents of the variable are then passed to the `New-CimSession` cmdlet.</span></span>
<span data-ttu-id="c7d67-119">`New-CimSession` 次に、変数に定義されているオプションを使用して、Server01 というリモートサーバーを使用して新しい CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-119">`New-CimSession` then creates a new CIM session with the remote server named Server01, using the options defined in the variable.</span></span>

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### <span data-ttu-id="c7d67-120">例 2: WsMan の CIM セッションオプションオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c7d67-120">Example 2: Create a CIM session options object for WsMan</span></span>

<span data-ttu-id="c7d67-121">この例では、WsMan プロトコル用の CIM セッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-121">This example creates a CIM session options object for the WsMan protocol.</span></span> <span data-ttu-id="c7d67-122">オブジェクトには、 **Proxyauthentication** パラメーターによって指定された **Kerberos** の認証モードの構成、 **proxyauthentication** パラメーターによって指定された資格情報が含まれています。また、コマンドが CA チェックをスキップし、CN チェックをスキップし、SSL を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-122">The object contains configuration for the authentication mode of **Kerberos** specified by the **ProxyAuthentication** parameter, the credentials specified by the **ProxyCredential** parameter, and specifies that the command is to skip the CA check, skip the CN check, and use SSL.</span></span>

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### <span data-ttu-id="c7d67-123">例 3: 指定されたカルチャで CIM セッションオプションオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c7d67-123">Example 3: Create a CIM session options object with the culture specified</span></span>

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

<span data-ttu-id="c7d67-124">この例では、CIM セッションに使用するカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-124">This example specifies the culture that is used for the CIM session.</span></span> <span data-ttu-id="c7d67-125">既定では、クライアントのカルチャは、操作の実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7d67-125">By default, the culture of the client is used when performing operations.</span></span> <span data-ttu-id="c7d67-126">ただし、既定のカルチャは、 **culture** パラメーターを使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="c7d67-126">However, the default culture can be overridden using the **Culture** parameter.</span></span>

## <span data-ttu-id="c7d67-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c7d67-127">PARAMETERS</span></span>

### <span data-ttu-id="c7d67-128">-Culture</span><span class="sxs-lookup"><span data-stu-id="c7d67-128">-Culture</span></span>

<span data-ttu-id="c7d67-129">CIM セッションに使用するユーザーインターフェイスのカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-129">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="c7d67-130">次のいずれかの形式を使用して、このパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-130">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="c7d67-131">"EN-US" などの形式のカルチャ名 `<languagecode2>-<country/regioncode2>` 。</span><span class="sxs-lookup"><span data-stu-id="c7d67-131">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="c7d67-132">**CultureInfo** オブジェクトを含む変数です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-132">A variable that contains a **CultureInfo** object.</span></span>
- <span data-ttu-id="c7d67-133">**CultureInfo** オブジェクトを取得するコマンド ( [Get Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)など)</span><span class="sxs-lookup"><span data-stu-id="c7d67-133">A command that gets a **CultureInfo** object, such as [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-134">-EncodePortInServicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="c7d67-134">-EncodePortInServicePrincipalName</span></span>

<span data-ttu-id="c7d67-135">Kerberos 接続がサービスに接続しているサービスプリンシパル名 (SPN) にサービスポート番号が含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-135">Indicates that the Kerberos connection is connecting to a service whose service principal name (SPN) includes the service port number.</span></span> <span data-ttu-id="c7d67-136">この種類の接続は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="c7d67-136">This type of connection is not common.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-137">-Encoding</span><span class="sxs-lookup"><span data-stu-id="c7d67-137">-Encoding</span></span>

<span data-ttu-id="c7d67-138">WsMan プロトコルに使用されるエンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-138">Specifies the encoding used for the WsMan protocol.</span></span> <span data-ttu-id="c7d67-139">このパラメーターに指定できる値は、 **Default** 、 **Utf8** 、または **Utf16** です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-139">The acceptable values for this parameter are: **Default** , **Utf8** , or **Utf16** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PacketEncoding
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Utf8, Utf16

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-140">-HttpPrefix</span><span class="sxs-lookup"><span data-stu-id="c7d67-140">-HttpPrefix</span></span>

<span data-ttu-id="c7d67-141">コンピューター名とポート番号の後にある HTTP URL の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-141">Specifies the part of the HTTP URL after the computer name and port number.</span></span> <span data-ttu-id="c7d67-142">この変更は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="c7d67-142">Changing this is not common.</span></span> <span data-ttu-id="c7d67-143">既定では、このパラメーターの値は **/wsman** です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-143">By default, the value of this parameter is **/wsman** .</span></span>

```yaml
Type: System.Uri
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-144">-偽装</span><span class="sxs-lookup"><span data-stu-id="c7d67-144">-Impersonation</span></span>

<span data-ttu-id="c7d67-145">偽装を使用して Windows Management Instrumentation (WMI) を行う DCOM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-145">Creates a DCOM session to Windows Management Instrumentation (WMI) using impersonation.</span></span>

<span data-ttu-id="c7d67-146">このパラメーターの有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c7d67-146">Valid values for this parameter are:</span></span>

- <span data-ttu-id="c7d67-147">既定: DCOM は、通常のセキュリティネゴシエーションアルゴリズムを使用して偽装レベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c7d67-147">Default: DCOM can choose the impersonation level using its normal security negotiation algorithm.</span></span>
- <span data-ttu-id="c7d67-148">None: クライアントはサーバーに対して匿名です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-148">None: The client is anonymous to the server.</span></span> <span data-ttu-id="c7d67-149">サーバープロセスはクライアントを偽装できますが、偽装トークンには情報が含まれていないため、使用できません。</span><span class="sxs-lookup"><span data-stu-id="c7d67-149">The server process can impersonate the client, but the impersonation token does not contain any information and cannot be used.</span></span>
- <span data-ttu-id="c7d67-150">識別: オブジェクトが呼び出し元の資格情報を照会できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c7d67-150">Identify: Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="c7d67-151">Impersonate: オブジェクトが呼び出し元の資格情報を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c7d67-151">Impersonate: Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="c7d67-152">Delegate: オブジェクトが、呼び出し元の資格情報の使用を他のオブジェクトに許可できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c7d67-152">Delegate: Allows objects to permit other objects to use the credentials of the caller.</span></span>

<span data-ttu-id="c7d67-153">**権限借用** が指定されていない場合、 `New-CimSession` コマンドレットは **Impersonate** の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-153">If **Impersonation** is not specified, the `New-CimSession` cmdlet uses the value of **Impersonate** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.ImpersonationType
Parameter Sets: DcomParameterSet
Aliases:
Accepted values: Default, None, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-154">-MaxEnvelopeSizeKB</span><span class="sxs-lookup"><span data-stu-id="c7d67-154">-MaxEnvelopeSizeKB</span></span>

<span data-ttu-id="c7d67-155">どちらの方向に対しても WsMan XML メッセージのサイズ制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-155">Specifies the size limit of WsMan XML messages for either direction.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-156">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="c7d67-156">-NoEncryption</span></span>

<span data-ttu-id="c7d67-157">データの暗号化をオフにすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-157">Specifies that data encryption is turned off.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-158">-PacketIntegrity</span><span class="sxs-lookup"><span data-stu-id="c7d67-158">-PacketIntegrity</span></span>

<span data-ttu-id="c7d67-159">WMI に対して作成された DCOM セッションが、Component Object Model (COM) _Packetintegrity_ 機能を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-159">Specifies that the DCOM session created to WMI uses the Component Object Model (COM) _PacketIntegrity_ functionality.</span></span> <span data-ttu-id="c7d67-160">既定では、DCOM を使用して作成されたすべての CIM セッションで **Packetintegrity** パラメーターが **True** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c7d67-160">By default, all CIM sessions created using DCOM have the **PacketIntegrity** parameter set to **True** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-161">-PacketPrivacy</span><span class="sxs-lookup"><span data-stu-id="c7d67-161">-PacketPrivacy</span></span>

<span data-ttu-id="c7d67-162">COM _Packetprivacy_ を使用して、WMI への DCOM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-162">Creates a DCOM session to WMI using the COM _PacketPrivacy_ .</span></span> <span data-ttu-id="c7d67-163">既定では、DCOM を使用して作成されたすべての CIM セッションで、 **Packetprivacy** パラメーターが **true** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c7d67-163">By default, all CIM sessions created using DCOM have the **PacketPrivacy** parameter set to **true** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-164">-Protocol</span><span class="sxs-lookup"><span data-stu-id="c7d67-164">-Protocol</span></span>

<span data-ttu-id="c7d67-165">使用するプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-165">Specifies the protocol to use.</span></span> <span data-ttu-id="c7d67-166">このパラメーターに指定できる値は、 **DCOM** 、 **Default** 、または **Wsman** です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-166">The acceptable values for this parameter are: **DCOM** , **Default** , or **Wsman** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimCmdlets.ProtocolType
Parameter Sets: ProtocolTypeSet
Aliases:
Accepted values: Dcom, Default, Wsman

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-167">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="c7d67-167">-ProxyAuthentication</span></span>

<span data-ttu-id="c7d67-168">プロキシの解決に使用する認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-168">Specifies the authentication method to use for proxy resolution.</span></span> <span data-ttu-id="c7d67-169">このパラメーターに指定できる値は、 **Default** 、 **Digest** 、 **Negotiate** 、 **Basic** 、 **Kerberos** 、 **ntlmdomain** 、 **CredSsp** です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-169">The acceptable values for this parameter are: **Default** , **Digest** , **Negotiate** , **Basic** , **Kerberos** , **NtlmDomain** , or **CredSsp** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-170">-ProxyCertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="c7d67-170">-ProxyCertificateThumbprint</span></span>

<span data-ttu-id="c7d67-171">プロキシ認証用のユーザーアカウントの (x.509) デジタル公開キー証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-171">Specifies the (x.509) digital public key certificate of a user account for proxy authentication.</span></span>
<span data-ttu-id="c7d67-172">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-172">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="c7d67-173">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7d67-173">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="c7d67-174">ローカルユーザーアカウントにしかマップできず、ドメインアカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="c7d67-174">They can only be mapped to local user accounts and they do not work with domain accounts.</span></span>

<span data-ttu-id="c7d67-175">証明書の拇印を取得するに `Get-Item` は、 `Get-ChildItem` PowerShell Cert: ドライブのまたはコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-175">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-176">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="c7d67-176">-ProxyCredential</span></span>

<span data-ttu-id="c7d67-177">プロキシ認証に使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-177">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="c7d67-178">次のいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-178">Enter one of the following:</span></span>

- <span data-ttu-id="c7d67-179">PSCredential オブジェクトを含む変数です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-179">A variable that contains a PSCredential object.</span></span>
- <span data-ttu-id="c7d67-180">PSCredential オブジェクトを取得するコマンド (たとえば、 `Get-Credential`</span><span class="sxs-lookup"><span data-stu-id="c7d67-180">A command that gets a PSCredential object, such as `Get-Credential`</span></span>

<span data-ttu-id="c7d67-181">このオプションが設定されていない場合、資格情報を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c7d67-181">If this option is not set, then you cannot specify any credentials.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-182">-ProxyType</span><span class="sxs-lookup"><span data-stu-id="c7d67-182">-ProxyType</span></span>

<span data-ttu-id="c7d67-183">使用するホスト名解決メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-183">Specifies the host name resolution mechanism to use.</span></span> <span data-ttu-id="c7d67-184">このパラメーターに指定できる値は、 **None** 、 **WinHttp** 、 **Auto** 、または **internetexplorer** です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-184">The acceptable values for this parameter are: **None** , **WinHttp** , **Auto** , or **InternetExplorer** .</span></span>

<span data-ttu-id="c7d67-185">このパラメーターの既定値は **Internetexplorer** です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-185">The default value of this parameter is **InternetExplorer** .</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.ProxyType
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: None, WinHttp, Auto, InternetExplorer

Required: False
Position: Named
Default value: InternetExplorer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-186">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="c7d67-186">-SkipCACheck</span></span>

<span data-ttu-id="c7d67-187">HTTPS 経由で接続する場合、クライアントは、サーバー証明書が信頼された証明機関 (CA) によって署名されているかどうかを検証しません。</span><span class="sxs-lookup"><span data-stu-id="c7d67-187">Indicates that when connecting over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="c7d67-188">リモートコンピューターが物理的に安全で分離されているネットワークの一部である場合、またはリモートコンピューターが WinRM 構成で信頼されたホストとして一覧表示されている場合など、リモートコンピューターが別のメカニズムを使用して信頼されている場合にのみ、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-188">Use this parameter only when the remote computer is trusted using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated, or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-189">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="c7d67-189">-SkipCNCheck</span></span>

<span data-ttu-id="c7d67-190">サーバーの証明書の共通名 (CN) がサーバーのホスト名と一致する必要がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-190">Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.</span></span> <span data-ttu-id="c7d67-191">このパラメーターは、HTTPS プロトコルを使用する信頼されたコンピューターでのリモート操作に対してのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-191">Use this parameter for remote operations only with trusted computers that use the HTTPS protocol.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-192">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="c7d67-192">-SkipRevocationCheck</span></span>

<span data-ttu-id="c7d67-193">サーバー証明書の失効確認がスキップされることを示します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-193">Indicates that the revocation check for server certificates is skipped.</span></span> <span data-ttu-id="c7d67-194">このパラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="c7d67-194">Use this parameter only for trusted computers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-195">-UICulture</span><span class="sxs-lookup"><span data-stu-id="c7d67-195">-UICulture</span></span>

<span data-ttu-id="c7d67-196">CIM セッションに使用するユーザーインターフェイスのカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-196">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="c7d67-197">次のいずれかの形式を使用して、このパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-197">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="c7d67-198">"EN-US" などの形式のカルチャ名 `<languagecode2>-<country/regioncode2>` 。</span><span class="sxs-lookup"><span data-stu-id="c7d67-198">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="c7d67-199">CultureInfo オブジェクトを含む変数です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-199">A variable that contains a CultureInfo object.</span></span>
- <span data-ttu-id="c7d67-200">などの CultureInfo オブジェクトを取得するコマンド `Get-Culture` 。</span><span class="sxs-lookup"><span data-stu-id="c7d67-200">A command that gets a CultureInfo object, such as `Get-Culture`.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-201">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="c7d67-201">-UseSsl</span></span>

<span data-ttu-id="c7d67-202">リモートコンピューターへの接続を確立するために SSL を使用する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-202">Indicates that SSL should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="c7d67-203">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="c7d67-203">By default, SSL is not used.</span></span> <span data-ttu-id="c7d67-204">WsMan は、HTTP を使用している場合でも、ネットワーク経由で転送されるすべてのコンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-204">WsMan encrypts all content that is transmitted over the network, even when using HTTP.</span></span>

<span data-ttu-id="c7d67-205">このパラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c7d67-205">This parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="c7d67-206">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-206">If SSL is not available on the port used for the connection and you specify this parameter, then the command fails.</span></span>

<span data-ttu-id="c7d67-207">このパラメーターは、 **Packetprivacy** パラメーターが指定されていない場合にのみ使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7d67-207">It is recommended that you use this parameter only when the **PacketPrivacy** parameter is not specified.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7d67-208">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7d67-208">CommonParameters</span></span>

<span data-ttu-id="c7d67-209">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c7d67-209">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c7d67-210">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7d67-210">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c7d67-211">入力</span><span class="sxs-lookup"><span data-stu-id="c7d67-211">INPUTS</span></span>

### <span data-ttu-id="c7d67-212">なし</span><span class="sxs-lookup"><span data-stu-id="c7d67-212">None</span></span>

<span data-ttu-id="c7d67-213">このコマンドレットは、入力オブジェクトを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="c7d67-213">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="c7d67-214">出力</span><span class="sxs-lookup"><span data-stu-id="c7d67-214">OUTPUTS</span></span>

### <span data-ttu-id="c7d67-215">CIMSessionOption</span><span class="sxs-lookup"><span data-stu-id="c7d67-215">CIMSessionOption</span></span>

<span data-ttu-id="c7d67-216">このコマンドレットは、CIM セッションオプションの情報を含むオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c7d67-216">This cmdlet returns an object that contains CIM session options information.</span></span>

## <span data-ttu-id="c7d67-217">注</span><span class="sxs-lookup"><span data-stu-id="c7d67-217">NOTES</span></span>

## <span data-ttu-id="c7d67-218">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c7d67-218">RELATED LINKS</span></span>

[<span data-ttu-id="c7d67-219">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="c7d67-219">Get-ChildItem</span></span>](../microsoft.powershell.management/get-childitem.md)

[<span data-ttu-id="c7d67-220">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="c7d67-220">Get-Credential</span></span>](../microsoft.powershell.security/get-credential.md)

[<span data-ttu-id="c7d67-221">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="c7d67-221">Get-Culture</span></span>](../microsoft.powershell.utility/get-culture.md)

[<span data-ttu-id="c7d67-222">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c7d67-222">Get-Item</span></span>](../microsoft.powershell.management/get-item.md)

[<span data-ttu-id="c7d67-223">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="c7d67-223">New-CimSession</span></span>](New-CimSession.md)

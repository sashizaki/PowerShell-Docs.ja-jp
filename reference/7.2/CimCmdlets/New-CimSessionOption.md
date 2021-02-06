---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: 54a2ca8a28d54bfe1d9676acdaace4592f62620f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603210"
---
# <span data-ttu-id="438c9-102">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="438c9-102">New-CimSessionOption</span></span>

## <span data-ttu-id="438c9-103">概要</span><span class="sxs-lookup"><span data-stu-id="438c9-103">SYNOPSIS</span></span>
<span data-ttu-id="438c9-104">New-CimSession コマンドレットの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-104">Specifies advanced options for the New-CimSession cmdlet.</span></span>

## <span data-ttu-id="438c9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="438c9-105">SYNTAX</span></span>

### <span data-ttu-id="438c9-106">ProtocolTypeSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="438c9-106">ProtocolTypeSet (Default)</span></span>

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### <span data-ttu-id="438c9-107">WSManParameterSet</span><span class="sxs-lookup"><span data-stu-id="438c9-107">WSManParameterSet</span></span>

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### <span data-ttu-id="438c9-108">DcomParameterSet</span><span class="sxs-lookup"><span data-stu-id="438c9-108">DcomParameterSet</span></span>

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## <span data-ttu-id="438c9-109">Description</span><span class="sxs-lookup"><span data-stu-id="438c9-109">DESCRIPTION</span></span>

<span data-ttu-id="438c9-110">コマンドレットでは、 `New-CimSessionOption` CIM セッションオプションオブジェクトのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="438c9-110">The `New-CimSessionOption` cmdlet creates an instance of a CIM session options object.</span></span> <span data-ttu-id="438c9-111">Cim セッションオプションオブジェクトをコマンドレットへの入力として使用して、 `New-CimSession` cim セッションのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-111">You use a CIM session options object as input to the `New-CimSession` cmdlet to specify the options for a CIM session.</span></span>

<span data-ttu-id="438c9-112">このコマンドレットには2つのパラメーターセットがあります。1つは WsMan オプション用で、もう1つは分散コンポーネントオブジェクトモデル (DCOM) オプション用です。</span><span class="sxs-lookup"><span data-stu-id="438c9-112">This cmdlet has two parameter sets, one for WsMan options and one for Distributed Component Object Model (DCOM) options.</span></span> <span data-ttu-id="438c9-113">コマンドレットは、使用するパラメーターに応じて、DCOM セッションオプションのインスタンスを返すか、WsMan セッションオプションを返します。</span><span class="sxs-lookup"><span data-stu-id="438c9-113">Depending on which parameters you use, the cmdlet returns either an instance of DCOM session options or returns WsMan session options.</span></span>

## <span data-ttu-id="438c9-114">例</span><span class="sxs-lookup"><span data-stu-id="438c9-114">EXAMPLES</span></span>

### <span data-ttu-id="438c9-115">例 1: DCOM の CIM セッションオプションオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="438c9-115">Example 1: Create a CIM session options object for DCOM</span></span>

<span data-ttu-id="438c9-116">この例では、DCOM プロトコル用の CIM セッションオプションオブジェクトを作成し、という名前の変数に格納し `$so` ます。</span><span class="sxs-lookup"><span data-stu-id="438c9-116">This example creates a CIM session options object for the DCOM protocol and stores it in a variable named `$so`.</span></span> <span data-ttu-id="438c9-117">次に、変数の内容がコマンドレットに渡され `New-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="438c9-117">The contents of the variable are then passed to the `New-CimSession` cmdlet.</span></span>
<span data-ttu-id="438c9-118">`New-CimSession` 次に、変数に定義されているオプションを使用して、Server01 というリモートサーバーを使用して新しい CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="438c9-118">`New-CimSession` then creates a new CIM session with the remote server named Server01, using the options defined in the variable.</span></span>

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### <span data-ttu-id="438c9-119">例 2: WsMan の CIM セッションオプションオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="438c9-119">Example 2: Create a CIM session options object for WsMan</span></span>

<span data-ttu-id="438c9-120">この例では、WsMan プロトコル用の CIM セッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="438c9-120">This example creates a CIM session options object for the WsMan protocol.</span></span> <span data-ttu-id="438c9-121">オブジェクトには、 **Proxyauthentication** パラメーターによって指定された **Kerberos** の認証モードの構成、 **proxyauthentication** パラメーターによって指定された資格情報が含まれています。また、コマンドが CA チェックをスキップし、CN チェックをスキップし、SSL を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-121">The object contains configuration for the authentication mode of **Kerberos** specified by the **ProxyAuthentication** parameter, the credentials specified by the **ProxyCredential** parameter, and specifies that the command is to skip the CA check, skip the CN check, and use SSL.</span></span>

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### <span data-ttu-id="438c9-122">例 3: 指定されたカルチャで CIM セッションオプションオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="438c9-122">Example 3: Create a CIM session options object with the culture specified</span></span>

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

<span data-ttu-id="438c9-123">この例では、CIM セッションに使用するカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-123">This example specifies the culture that is used for the CIM session.</span></span> <span data-ttu-id="438c9-124">既定では、クライアントのカルチャは、操作の実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="438c9-124">By default, the culture of the client is used when performing operations.</span></span> <span data-ttu-id="438c9-125">ただし、既定のカルチャは、 **culture** パラメーターを使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="438c9-125">However, the default culture can be overridden using the **Culture** parameter.</span></span>

## <span data-ttu-id="438c9-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="438c9-126">PARAMETERS</span></span>

### <span data-ttu-id="438c9-127">-Culture</span><span class="sxs-lookup"><span data-stu-id="438c9-127">-Culture</span></span>

<span data-ttu-id="438c9-128">CIM セッションに使用するユーザーインターフェイスのカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-128">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="438c9-129">次のいずれかの形式を使用して、このパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-129">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="438c9-130">"EN-US" などの形式のカルチャ名 `<languagecode2>-<country/regioncode2>` 。</span><span class="sxs-lookup"><span data-stu-id="438c9-130">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="438c9-131">**CultureInfo** オブジェクトを含む変数です。</span><span class="sxs-lookup"><span data-stu-id="438c9-131">A variable that contains a **CultureInfo** object.</span></span>
- <span data-ttu-id="438c9-132">**CultureInfo** オブジェクトを取得するコマンド ( [Get Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)など)</span><span class="sxs-lookup"><span data-stu-id="438c9-132">A command that gets a **CultureInfo** object, such as [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span></span>

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

### <span data-ttu-id="438c9-133">-EncodePortInServicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="438c9-133">-EncodePortInServicePrincipalName</span></span>

<span data-ttu-id="438c9-134">Kerberos 接続がサービスに接続しているサービスプリンシパル名 (SPN) にサービスポート番号が含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="438c9-134">Indicates that the Kerberos connection is connecting to a service whose service principal name (SPN) includes the service port number.</span></span> <span data-ttu-id="438c9-135">この種類の接続は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="438c9-135">This type of connection is not common.</span></span>

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

### <span data-ttu-id="438c9-136">-Encoding</span><span class="sxs-lookup"><span data-stu-id="438c9-136">-Encoding</span></span>

<span data-ttu-id="438c9-137">WsMan プロトコルに使用されるエンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-137">Specifies the encoding used for the WsMan protocol.</span></span> <span data-ttu-id="438c9-138">このパラメーターに指定できる値は、 **Default**、 **Utf8**、または **Utf16** です。</span><span class="sxs-lookup"><span data-stu-id="438c9-138">The acceptable values for this parameter are: **Default**, **Utf8**, or **Utf16**.</span></span>

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

### <span data-ttu-id="438c9-139">-HttpPrefix</span><span class="sxs-lookup"><span data-stu-id="438c9-139">-HttpPrefix</span></span>

<span data-ttu-id="438c9-140">コンピューター名とポート番号の後にある HTTP URL の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-140">Specifies the part of the HTTP URL after the computer name and port number.</span></span> <span data-ttu-id="438c9-141">この変更は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="438c9-141">Changing this is not common.</span></span> <span data-ttu-id="438c9-142">既定では、このパラメーターの値は **/wsman** です。</span><span class="sxs-lookup"><span data-stu-id="438c9-142">By default, the value of this parameter is **/wsman**.</span></span>

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

### <span data-ttu-id="438c9-143">-偽装</span><span class="sxs-lookup"><span data-stu-id="438c9-143">-Impersonation</span></span>

<span data-ttu-id="438c9-144">偽装を使用して Windows Management Instrumentation (WMI) を行う DCOM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="438c9-144">Creates a DCOM session to Windows Management Instrumentation (WMI) using impersonation.</span></span>

<span data-ttu-id="438c9-145">このパラメーターの有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="438c9-145">Valid values for this parameter are:</span></span>

- <span data-ttu-id="438c9-146">既定: DCOM は、通常のセキュリティネゴシエーションアルゴリズムを使用して偽装レベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="438c9-146">Default: DCOM can choose the impersonation level using its normal security negotiation algorithm.</span></span>
- <span data-ttu-id="438c9-147">None: クライアントはサーバーに対して匿名です。</span><span class="sxs-lookup"><span data-stu-id="438c9-147">None: The client is anonymous to the server.</span></span> <span data-ttu-id="438c9-148">サーバープロセスはクライアントを偽装できますが、偽装トークンには情報が含まれていないため、使用できません。</span><span class="sxs-lookup"><span data-stu-id="438c9-148">The server process can impersonate the client, but the impersonation token does not contain any information and cannot be used.</span></span>
- <span data-ttu-id="438c9-149">識別: オブジェクトが呼び出し元の資格情報を照会できるようにします。</span><span class="sxs-lookup"><span data-stu-id="438c9-149">Identify: Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="438c9-150">Impersonate: オブジェクトが呼び出し元の資格情報を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="438c9-150">Impersonate: Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="438c9-151">Delegate: オブジェクトが、呼び出し元の資格情報の使用を他のオブジェクトに許可できるようにします。</span><span class="sxs-lookup"><span data-stu-id="438c9-151">Delegate: Allows objects to permit other objects to use the credentials of the caller.</span></span>

<span data-ttu-id="438c9-152">**権限借用** が指定されていない場合、 `New-CimSession` コマンドレットは **Impersonate** の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="438c9-152">If **Impersonation** is not specified, the `New-CimSession` cmdlet uses the value of **Impersonate**.</span></span>

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

### <span data-ttu-id="438c9-153">-MaxEnvelopeSizeKB</span><span class="sxs-lookup"><span data-stu-id="438c9-153">-MaxEnvelopeSizeKB</span></span>

<span data-ttu-id="438c9-154">どちらの方向に対しても WsMan XML メッセージのサイズ制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-154">Specifies the size limit of WsMan XML messages for either direction.</span></span>

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

### <span data-ttu-id="438c9-155">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="438c9-155">-NoEncryption</span></span>

<span data-ttu-id="438c9-156">データの暗号化をオフにすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-156">Specifies that data encryption is turned off.</span></span>

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

### <span data-ttu-id="438c9-157">-PacketIntegrity</span><span class="sxs-lookup"><span data-stu-id="438c9-157">-PacketIntegrity</span></span>

<span data-ttu-id="438c9-158">WMI に対して作成された DCOM セッションが、Component Object Model (COM) _Packetintegrity_ 機能を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-158">Specifies that the DCOM session created to WMI uses the Component Object Model (COM) _PacketIntegrity_ functionality.</span></span> <span data-ttu-id="438c9-159">既定では、DCOM を使用して作成されたすべての CIM セッションで **Packetintegrity** パラメーターが **True** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="438c9-159">By default, all CIM sessions created using DCOM have the **PacketIntegrity** parameter set to **True**.</span></span>

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

### <span data-ttu-id="438c9-160">-PacketPrivacy</span><span class="sxs-lookup"><span data-stu-id="438c9-160">-PacketPrivacy</span></span>

<span data-ttu-id="438c9-161">COM _Packetprivacy_ を使用して、WMI への DCOM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="438c9-161">Creates a DCOM session to WMI using the COM _PacketPrivacy_.</span></span> <span data-ttu-id="438c9-162">既定では、DCOM を使用して作成されたすべての CIM セッションで、 **Packetprivacy** パラメーターが **true** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="438c9-162">By default, all CIM sessions created using DCOM have the **PacketPrivacy** parameter set to **true**.</span></span>

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

### <span data-ttu-id="438c9-163">-Protocol</span><span class="sxs-lookup"><span data-stu-id="438c9-163">-Protocol</span></span>

<span data-ttu-id="438c9-164">使用するプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-164">Specifies the protocol to use.</span></span> <span data-ttu-id="438c9-165">このパラメーターに指定できる値は、 **DCOM**、 **Default**、または **Wsman** です。</span><span class="sxs-lookup"><span data-stu-id="438c9-165">The acceptable values for this parameter are: **DCOM**, **Default**, or **Wsman**.</span></span>

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

### <span data-ttu-id="438c9-166">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="438c9-166">-ProxyAuthentication</span></span>

<span data-ttu-id="438c9-167">プロキシの解決に使用する認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-167">Specifies the authentication method to use for proxy resolution.</span></span> <span data-ttu-id="438c9-168">このパラメーターに指定できる値は、 **Default**、 **Digest**、 **Negotiate**、 **Basic**、 **Kerberos**、 **ntlmdomain**、 **CredSsp** です。</span><span class="sxs-lookup"><span data-stu-id="438c9-168">The acceptable values for this parameter are: **Default**, **Digest**, **Negotiate**, **Basic**, **Kerberos**, **NtlmDomain**, or **CredSsp**.</span></span>

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

### <span data-ttu-id="438c9-169">-ProxyCertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="438c9-169">-ProxyCertificateThumbprint</span></span>

<span data-ttu-id="438c9-170">プロキシ認証用のユーザーアカウントの (x.509) デジタル公開キー証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-170">Specifies the (x.509) digital public key certificate of a user account for proxy authentication.</span></span>
<span data-ttu-id="438c9-171">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="438c9-171">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="438c9-172">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="438c9-172">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="438c9-173">ローカルユーザーアカウントにしかマップできず、ドメインアカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="438c9-173">They can only be mapped to local user accounts and they do not work with domain accounts.</span></span>

<span data-ttu-id="438c9-174">証明書の拇印を取得するに `Get-Item` は、 `Get-ChildItem` PowerShell Cert: ドライブのまたはコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="438c9-174">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="438c9-175">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="438c9-175">-ProxyCredential</span></span>

<span data-ttu-id="438c9-176">プロキシ認証に使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-176">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="438c9-177">次のいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="438c9-177">Enter one of the following:</span></span>

- <span data-ttu-id="438c9-178">PSCredential オブジェクトを含む変数です。</span><span class="sxs-lookup"><span data-stu-id="438c9-178">A variable that contains a PSCredential object.</span></span>
- <span data-ttu-id="438c9-179">PSCredential オブジェクトを取得するコマンド (たとえば、 `Get-Credential`</span><span class="sxs-lookup"><span data-stu-id="438c9-179">A command that gets a PSCredential object, such as `Get-Credential`</span></span>

<span data-ttu-id="438c9-180">このオプションが設定されていない場合、資格情報を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="438c9-180">If this option is not set, then you cannot specify any credentials.</span></span>

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

### <span data-ttu-id="438c9-181">-ProxyType</span><span class="sxs-lookup"><span data-stu-id="438c9-181">-ProxyType</span></span>

<span data-ttu-id="438c9-182">使用するホスト名解決メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-182">Specifies the host name resolution mechanism to use.</span></span> <span data-ttu-id="438c9-183">このパラメーターに指定できる値は、 **None**、 **WinHttp**、 **Auto**、または **internetexplorer** です。</span><span class="sxs-lookup"><span data-stu-id="438c9-183">The acceptable values for this parameter are: **None**, **WinHttp**, **Auto**, or **InternetExplorer**.</span></span>

<span data-ttu-id="438c9-184">このパラメーターの既定値は **Internetexplorer** です。</span><span class="sxs-lookup"><span data-stu-id="438c9-184">The default value of this parameter is **InternetExplorer**.</span></span>

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

### <span data-ttu-id="438c9-185">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="438c9-185">-SkipCACheck</span></span>

<span data-ttu-id="438c9-186">HTTPS 経由で接続する場合、クライアントは、サーバー証明書が信頼された証明機関 (CA) によって署名されているかどうかを検証しません。</span><span class="sxs-lookup"><span data-stu-id="438c9-186">Indicates that when connecting over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="438c9-187">リモートコンピューターが物理的に安全で分離されているネットワークの一部である場合、またはリモートコンピューターが WinRM 構成で信頼されたホストとして一覧表示されている場合など、リモートコンピューターが別のメカニズムを使用して信頼されている場合にのみ、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="438c9-187">Use this parameter only when the remote computer is trusted using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated, or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

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

### <span data-ttu-id="438c9-188">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="438c9-188">-SkipCNCheck</span></span>

<span data-ttu-id="438c9-189">サーバーの証明書の共通名 (CN) がサーバーのホスト名と一致する必要がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="438c9-189">Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.</span></span> <span data-ttu-id="438c9-190">このパラメーターは、HTTPS プロトコルを使用する信頼されたコンピューターでのリモート操作に対してのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="438c9-190">Use this parameter for remote operations only with trusted computers that use the HTTPS protocol.</span></span>

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

### <span data-ttu-id="438c9-191">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="438c9-191">-SkipRevocationCheck</span></span>

<span data-ttu-id="438c9-192">サーバー証明書の失効確認がスキップされることを示します。</span><span class="sxs-lookup"><span data-stu-id="438c9-192">Indicates that the revocation check for server certificates is skipped.</span></span> <span data-ttu-id="438c9-193">このパラメーターは、信頼されたコンピューターに対してのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="438c9-193">Use this parameter only for trusted computers.</span></span>

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

### <span data-ttu-id="438c9-194">-UICulture</span><span class="sxs-lookup"><span data-stu-id="438c9-194">-UICulture</span></span>

<span data-ttu-id="438c9-195">CIM セッションに使用するユーザーインターフェイスのカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-195">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="438c9-196">次のいずれかの形式を使用して、このパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="438c9-196">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="438c9-197">"EN-US" などの形式のカルチャ名 `<languagecode2>-<country/regioncode2>` 。</span><span class="sxs-lookup"><span data-stu-id="438c9-197">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="438c9-198">CultureInfo オブジェクトを含む変数です。</span><span class="sxs-lookup"><span data-stu-id="438c9-198">A variable that contains a CultureInfo object.</span></span>
- <span data-ttu-id="438c9-199">などの CultureInfo オブジェクトを取得するコマンド `Get-Culture` 。</span><span class="sxs-lookup"><span data-stu-id="438c9-199">A command that gets a CultureInfo object, such as `Get-Culture`.</span></span>

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

### <span data-ttu-id="438c9-200">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="438c9-200">-UseSsl</span></span>

<span data-ttu-id="438c9-201">リモートコンピューターへの接続を確立するために SSL を使用する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="438c9-201">Indicates that SSL should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="438c9-202">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="438c9-202">By default, SSL is not used.</span></span> <span data-ttu-id="438c9-203">WsMan は、HTTP を使用している場合でも、ネットワーク経由で転送されるすべてのコンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="438c9-203">WsMan encrypts all content that is transmitted over the network, even when using HTTP.</span></span>

<span data-ttu-id="438c9-204">このパラメーターを使用すると、HTTP ではなく HTTPS の追加の保護を指定できます。</span><span class="sxs-lookup"><span data-stu-id="438c9-204">This parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="438c9-205">接続に使用するポートで SSL が使用できない場合、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="438c9-205">If SSL is not available on the port used for the connection and you specify this parameter, then the command fails.</span></span>

<span data-ttu-id="438c9-206">このパラメーターは、 **Packetprivacy** パラメーターが指定されていない場合にのみ使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="438c9-206">It is recommended that you use this parameter only when the **PacketPrivacy** parameter is not specified.</span></span>

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

### <span data-ttu-id="438c9-207">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="438c9-207">CommonParameters</span></span>

<span data-ttu-id="438c9-208">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="438c9-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="438c9-209">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="438c9-209">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="438c9-210">入力</span><span class="sxs-lookup"><span data-stu-id="438c9-210">INPUTS</span></span>

### <span data-ttu-id="438c9-211">なし</span><span class="sxs-lookup"><span data-stu-id="438c9-211">None</span></span>

<span data-ttu-id="438c9-212">このコマンドレットは、入力オブジェクトを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="438c9-212">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="438c9-213">出力</span><span class="sxs-lookup"><span data-stu-id="438c9-213">OUTPUTS</span></span>

### <span data-ttu-id="438c9-214">CIMSessionOption</span><span class="sxs-lookup"><span data-stu-id="438c9-214">CIMSessionOption</span></span>

<span data-ttu-id="438c9-215">このコマンドレットは、CIM セッションオプションの情報を含むオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="438c9-215">This cmdlet returns an object that contains CIM session options information.</span></span>

## <span data-ttu-id="438c9-216">注</span><span class="sxs-lookup"><span data-stu-id="438c9-216">NOTES</span></span>

## <span data-ttu-id="438c9-217">関連リンク</span><span class="sxs-lookup"><span data-stu-id="438c9-217">RELATED LINKS</span></span>

[<span data-ttu-id="438c9-218">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="438c9-218">Get-ChildItem</span></span>](../microsoft.powershell.management/get-childitem.md)

[<span data-ttu-id="438c9-219">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="438c9-219">Get-Credential</span></span>](../microsoft.powershell.security/get-credential.md)

[<span data-ttu-id="438c9-220">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="438c9-220">Get-Culture</span></span>](../microsoft.powershell.utility/get-culture.md)

[<span data-ttu-id="438c9-221">Get-Item</span><span class="sxs-lookup"><span data-stu-id="438c9-221">Get-Item</span></span>](../microsoft.powershell.management/get-item.md)

[<span data-ttu-id="438c9-222">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="438c9-222">New-CimSession</span></span>](New-CimSession.md)


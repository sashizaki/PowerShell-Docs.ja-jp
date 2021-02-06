---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: 59e70f75ac9d822db00419d84055d92a3882c11d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603017"
---
# <span data-ttu-id="6e0ae-102">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="6e0ae-102">New-CimSession</span></span>

## <span data-ttu-id="6e0ae-103">概要</span><span class="sxs-lookup"><span data-stu-id="6e0ae-103">SYNOPSIS</span></span>

<span data-ttu-id="6e0ae-104">CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-104">Creates a CIM session.</span></span>

## <span data-ttu-id="6e0ae-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e0ae-105">SYNTAX</span></span>

### <span data-ttu-id="6e0ae-106">CredentialParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="6e0ae-106">CredentialParameterSet (Default)</span></span>

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### <span data-ttu-id="6e0ae-107">CertificateParameterSet</span><span class="sxs-lookup"><span data-stu-id="6e0ae-107">CertificateParameterSet</span></span>

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## <span data-ttu-id="6e0ae-108">Description</span><span class="sxs-lookup"><span data-stu-id="6e0ae-108">DESCRIPTION</span></span>

<span data-ttu-id="6e0ae-109">コマンドレットでは、 `New-CimSession` CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-109">The `New-CimSession` cmdlet creates a CIM session.</span></span> <span data-ttu-id="6e0ae-110">CIM セッションは、ローカルコンピューターまたはリモートコンピューターへの接続を表すクライアント側オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-110">A CIM session is a client-side object representing a connection to a local computer or a remote computer.</span></span> <span data-ttu-id="6e0ae-111">CIM セッションには、 **ComputerName**、使用されるプロトコル、さまざまな識別子など、接続に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-111">The CIM session contains information about the connection, such as **ComputerName**, the protocol used, or various identifiers.</span></span>

<span data-ttu-id="6e0ae-112">このコマンドレットは、他のすべての CIM コマンドレットで使用できる CIM セッションオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-112">This cmdlet returns a CIM session object that can be used by all other CIM cmdlets.</span></span>

## <span data-ttu-id="6e0ae-113">例</span><span class="sxs-lookup"><span data-stu-id="6e0ae-113">EXAMPLES</span></span>

### <span data-ttu-id="6e0ae-114">例 1: 既定のオプションを使用して CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="6e0ae-114">Example 1: Create a CIM session with default options</span></span>

<span data-ttu-id="6e0ae-115">この例では、既定のオプションを使用してローカル CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-115">This example creates a local CIM session with default options.</span></span> <span data-ttu-id="6e0ae-116">**ComputerName** が指定されていない場合、は `New-CimSession` ローカルコンピューターに対して DCOM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-116">If **ComputerName** is not specified, `New-CimSession` creates a DCOM session to the local computer.</span></span>

```powershell
New-CimSession
```

### <span data-ttu-id="6e0ae-117">例 2: 特定のコンピューターに対して CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="6e0ae-117">Example 2: Create a CIM session to a specific computer</span></span>

<span data-ttu-id="6e0ae-118">この例では、 **ComputerName** によって指定されたコンピューターに CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-118">This example creates a CIM session to the computer specified by **ComputerName**.</span></span>
<span data-ttu-id="6e0ae-119">既定では、 `New-CimSession` **ComputerName** が指定されている場合、は WSMan セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-119">By default, `New-CimSession` creates a WSMan session when **ComputerName** is specified.</span></span>

```powershell
New-CimSession -ComputerName Server01
```

### <span data-ttu-id="6e0ae-120">例 3: 複数のコンピューターに CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="6e0ae-120">Example 3: Create a CIM session to multiple computers</span></span>

<span data-ttu-id="6e0ae-121">この例では、 **ComputerName** によって指定された各コンピューターに、コンマ区切りの一覧で CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-121">This example creates a CIM session to each of the computers specified by **ComputerName**, in the comma separated list.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### <span data-ttu-id="6e0ae-122">例 4: フレンドリ名を使用して CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="6e0ae-122">Example 4: Create a CIM session with a friendly name</span></span>

<span data-ttu-id="6e0ae-123">この例では、 **ComputerName** によって指定された各コンピューターに対して、コンマ区切りの一覧でリモート CIM セッションを作成し、 **名前** を指定することによって、新しいセッションにフレンドリ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-123">This example creates a remote CIM session to each of the computers specified by **ComputerName**, in the comma separated list, and assigns a friendly name to the new sessions, by specifying **Name**.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

<span data-ttu-id="6e0ae-124">CIM セッションのフレンドリ名を使用して、他の CIM コマンドレットでセッションを参照することができます (たとえば、 [CimSession](Get-CimSession.md))。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-124">You can use the friendly name of a CIM session to refer to the session in other CIM cmdlets, for example, [Get-CimSession](Get-CimSession.md).</span></span>

### <span data-ttu-id="6e0ae-125">例 5: PSCredential オブジェクトを使用してコンピューターに CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="6e0ae-125">Example 5: Create a CIM session to a computer using a PSCredential object</span></span>

<span data-ttu-id="6e0ae-126">この例では、ComputerName **によって** 指定された **PSCredential** オブジェクトと、 **authentication** によって指定された認証の種類を使用して、 **ComputerName** によって指定されたコンピューターに CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-126">This example creates a CIM session to the computer specified by **ComputerName**, using the **PSCredential** object specified by **Credential**, and the authentication type specified by **Authentication**.</span></span>

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

<span data-ttu-id="6e0ae-127">コマンドレットを使用して **PSCredential** オブジェクトを作成でき [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-127">You can create a **PSCredential** object using the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

### <span data-ttu-id="6e0ae-128">例 6: 特定のポートを使用してコンピューターに CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="6e0ae-128">Example 6: Create a CIM session to a computer using a specific port</span></span>

<span data-ttu-id="6e0ae-129">この例では、**ポート** によって指定された TCP ポートを使用して、 **ComputerName** によって指定されたコンピューターに CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-129">This example creates a CIM session to the computer specified by **ComputerName** using the TCP port specified by **Port**.</span></span>

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### <span data-ttu-id="6e0ae-130">例 7: DCOM を使用して CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="6e0ae-130">Example 7: Create a CIM session using DCOM</span></span>

<span data-ttu-id="6e0ae-131">この例では、WSMan ではなく分散 COM (DCOM) プロトコルを使用して CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-131">This example creates a CIM session using the Distributed COM (DCOM) protocol instead of WSMan.</span></span>

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## <span data-ttu-id="6e0ae-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e0ae-132">PARAMETERS</span></span>

### <span data-ttu-id="6e0ae-133">-認証</span><span class="sxs-lookup"><span data-stu-id="6e0ae-133">-Authentication</span></span>

<span data-ttu-id="6e0ae-134">ユーザーの資格情報に使用される認証の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-134">Specifies the authentication type used for the user's credentials.</span></span> <span data-ttu-id="6e0ae-135">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6e0ae-136">Default</span><span class="sxs-lookup"><span data-stu-id="6e0ae-136">Default</span></span>
- <span data-ttu-id="6e0ae-137">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="6e0ae-137">Digest</span></span>
- <span data-ttu-id="6e0ae-138">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="6e0ae-138">Negotiate</span></span>
- <span data-ttu-id="6e0ae-139">Basic</span><span class="sxs-lookup"><span data-stu-id="6e0ae-139">Basic</span></span>
- <span data-ttu-id="6e0ae-140">Kerberos</span><span class="sxs-lookup"><span data-stu-id="6e0ae-140">Kerberos</span></span>
- <span data-ttu-id="6e0ae-141">NtlmDomain</span><span class="sxs-lookup"><span data-stu-id="6e0ae-141">NtlmDomain</span></span>
- <span data-ttu-id="6e0ae-142">CredSsp</span><span class="sxs-lookup"><span data-stu-id="6e0ae-142">CredSsp</span></span>

<span data-ttu-id="6e0ae-143">ローカルコンピューターへの接続に **Ntlmdomain** 認証の種類を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-143">You cannot use the **NtlmDomain** authentication type for connection to the local computer.</span></span> <span data-ttu-id="6e0ae-144">**CredSSP** 認証は、windows Vista、windows Server 2008、およびそれ以降のバージョンの windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-144">**CredSSP** authentication is available only in Windows Vista, Windows Server 2008, and later versions of Windows.</span></span>

> [!CAUTION]
> <span data-ttu-id="6e0ae-145">Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-145">Credential Security Service Provider (CredSSP) authentication is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="6e0ae-146">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-146">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="6e0ae-147">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-147">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: CredentialParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e0ae-148">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="6e0ae-148">-CertificateThumbprint</span></span>

<span data-ttu-id="6e0ae-149">この操作を実行するアクセス許可を持つユーザーアカウントのデジタル公開キー証明書 (x.509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-149">Specifies the digital public key certificate (X.509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="6e0ae-150">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-150">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="6e0ae-151">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-151">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="6e0ae-152">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-152">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="6e0ae-153">証明書の拇印を取得するに [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) は、 [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) PowerShell 証明書プロバイダーでまたはコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-153">To get a certificate thumbprint, use the [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) or [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) cmdlets in the PowerShell Certificate Provider.</span></span>

<span data-ttu-id="6e0ae-154">詳細については、「 [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-154">For more information, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

```yaml
Type: System.String
Parameter Sets: CertificateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e0ae-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="6e0ae-155">-ComputerName</span></span>

<span data-ttu-id="6e0ae-156">CIM セッションを作成するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-156">Specifies the name of the computer to which to create the CIM session.</span></span> <span data-ttu-id="6e0ae-157">1つのコンピューター名、またはコンマで区切られた複数のコンピューター名を指定してください。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-157">Specify either a single computer name, or multiple computer names separated by a comma.</span></span>

<span data-ttu-id="6e0ae-158">**ComputerName** が指定されていない場合は、ローカルコンピューターへの CIM セッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-158">If **ComputerName** is not specified, a CIM session to the local computer is created.</span></span> <span data-ttu-id="6e0ae-159">コンピューター名の値は、次のいずれかの形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-159">You can specify the value for computer name in one of the following formats:</span></span>

- <span data-ttu-id="6e0ae-160">1つまたは複数の NetBIOS 名</span><span class="sxs-lookup"><span data-stu-id="6e0ae-160">One or more NetBIOS names</span></span>
- <span data-ttu-id="6e0ae-161">1つ以上の IP アドレス</span><span class="sxs-lookup"><span data-stu-id="6e0ae-161">One or more IP addresses</span></span>
- <span data-ttu-id="6e0ae-162">1つ以上の完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-162">One or more fully qualified domain names.</span></span>

<span data-ttu-id="6e0ae-163">コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-163">If the computer is in a different domain than the user, you must specify the fully qualified domain name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e0ae-164">-Credential</span><span class="sxs-lookup"><span data-stu-id="6e0ae-164">-Credential</span></span>

<span data-ttu-id="6e0ae-165">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-165">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="6e0ae-166">**Credential** が指定されていない場合は、現在のユーザーアカウントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-166">If **Credential** is not specified, the current user account is used.</span></span>

<span data-ttu-id="6e0ae-167">次のいずれかの形式を使用して、 **Credential** の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-167">Specify the value for **Credential** using one of the following formats:</span></span>

- <span data-ttu-id="6e0ae-168">ユーザー名: "User01"</span><span class="sxs-lookup"><span data-stu-id="6e0ae-168">A user name: "User01"</span></span>
- <span data-ttu-id="6e0ae-169">ドメイン名とユーザー名: "Domain01\user01」"</span><span class="sxs-lookup"><span data-stu-id="6e0ae-169">A domain name and a user name: "Domain01\User01"</span></span>
- <span data-ttu-id="6e0ae-170">ユーザープリンシパル名: " User@Domain.com "</span><span class="sxs-lookup"><span data-stu-id="6e0ae-170">A user principal name: "User@Domain.com"</span></span>
- <span data-ttu-id="6e0ae-171">コマンドレットによって返されるような PSCredential オブジェクト [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) 。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-171">A PSCredential object, such as one returned by the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

<span data-ttu-id="6e0ae-172">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-172">When you type a user name, you are prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e0ae-173">-Name</span><span class="sxs-lookup"><span data-stu-id="6e0ae-173">-Name</span></span>

<span data-ttu-id="6e0ae-174">CIM セッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-174">Specifies a friendly name for the CIM session.</span></span>

<span data-ttu-id="6e0ae-175">名前を使用して、 [CimSession](Get-CimSession.md) コマンドレットなど、他のコマンドレットを使用するときに CIM セッションを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-175">You can use the name to refer to the CIM session when using other cmdlets, such as the [Get-CimSession](Get-CimSession.md) cmdlet.</span></span>
<span data-ttu-id="6e0ae-176">名前は、コンピューターや現在のセッションで一意である必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-176">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e0ae-177">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="6e0ae-177">-OperationTimeoutSec</span></span>

<span data-ttu-id="6e0ae-178">コマンドレットがサーバーからの応答を待機する期間。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-178">Duration for which the cmdlet waits for a response from the server.</span></span>

<span data-ttu-id="6e0ae-179">既定では、このパラメーターの値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-179">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="6e0ae-180">**Operationtimeoutsec** パラメーターが、堅牢な接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。これは、クライアントが再接続する前に、サーバー上の操作がタイムアウトになるためです。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-180">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e0ae-181">-Port</span><span class="sxs-lookup"><span data-stu-id="6e0ae-181">-Port</span></span>

<span data-ttu-id="6e0ae-182">この接続に使用するリモート コンピューター上のネットワーク ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-182">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="6e0ae-183">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-183">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="6e0ae-184">既定のポート番号は 5985 (HTTP 用の WinRM ポート) と 5986 (HTTPS 用の WinRM ポート) です。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-184">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span>

<span data-ttu-id="6e0ae-185">代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-185">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="6e0ae-186">リスナーを構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-186">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

<span data-ttu-id="6e0ae-187">必要な場合を除き、**Port** パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-187">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="6e0ae-188">コマンドのポート設定は、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-188">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="6e0ae-189">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-189">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e0ae-190">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="6e0ae-190">-SessionOption</span></span>

<span data-ttu-id="6e0ae-191">新しい CIM セッションの詳細オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-191">Sets advanced options for the new CIM session.</span></span> <span data-ttu-id="6e0ae-192">コマンドレットを使用して作成された **CimSessionOption** オブジェクトの名前を入力し [`New-CimSessionOption`](New-CimSessionOption.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-192">Enter the name of a **CimSessionOption** object created using the [`New-CimSessionOption`](New-CimSessionOption.md) cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.CimSessionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e0ae-193">-SkipTestConnection</span><span class="sxs-lookup"><span data-stu-id="6e0ae-193">-SkipTestConnection</span></span>

<span data-ttu-id="6e0ae-194">既定では、 `New-CimSession` コマンドレットは、リモートの WS-Management エンドポイントとの接続を確立します。これは、リモートサーバーが **port** パラメーターを使用して指定されたポート番号でリッスンしていることを確認し、指定されたアカウントの資格情報を検証するためです。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-194">By default, the `New-CimSession` cmdlet establishes a connection with a remote WS-Management endpoint for two reasons: to verify that the remote server is listening on the port number that is specified using the **Port** parameter, and to verify the specified account credentials.</span></span> <span data-ttu-id="6e0ae-195">検証は、標準の WS-Identity 操作を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-195">The verification is accomplished using a standard WS-Identity operation.</span></span> <span data-ttu-id="6e0ae-196">リモート WS-Management エンドポイントが WS-ADDRESSING を使用できない場合や、データ転送時間を短縮する場合は、 **Skiptestconnection** スイッチパラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-196">You can add the **SkipTestConnection** switch parameter if the remote WS-Management endpoint cannot use WS-Identify, or to reduce some data transmission time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e0ae-197">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e0ae-197">CommonParameters</span></span>

<span data-ttu-id="6e0ae-198">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-198">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e0ae-199">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-199">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="6e0ae-200">入力</span><span class="sxs-lookup"><span data-stu-id="6e0ae-200">INPUTS</span></span>

### <span data-ttu-id="6e0ae-201">なし</span><span class="sxs-lookup"><span data-stu-id="6e0ae-201">None</span></span>

<span data-ttu-id="6e0ae-202">このコマンドレットは入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="6e0ae-202">This cmdlet accepts no inputs.</span></span>

## <span data-ttu-id="6e0ae-203">出力</span><span class="sxs-lookup"><span data-stu-id="6e0ae-203">OUTPUTS</span></span>

### <span data-ttu-id="6e0ae-204">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="6e0ae-204">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="6e0ae-205">注</span><span class="sxs-lookup"><span data-stu-id="6e0ae-205">NOTES</span></span>

## <span data-ttu-id="6e0ae-206">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6e0ae-206">RELATED LINKS</span></span>

[<span data-ttu-id="6e0ae-207">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6e0ae-207">Get-ChildItem</span></span>](../Microsoft.Powershell.Management/Get-ChildItem.md)

[<span data-ttu-id="6e0ae-208">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="6e0ae-208">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="6e0ae-209">Get-Item</span><span class="sxs-lookup"><span data-stu-id="6e0ae-209">Get-Item</span></span>](../Microsoft.Powershell.Management/Get-Item.md)

[<span data-ttu-id="6e0ae-210">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="6e0ae-210">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="6e0ae-211">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="6e0ae-211">Remove-CimSession</span></span>](Remove-CimSession.md)

[<span data-ttu-id="6e0ae-212">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="6e0ae-212">New-CimSessionOption</span></span>](New-CimSessionOption.md)

[<span data-ttu-id="6e0ae-213">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="6e0ae-213">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)


---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: 85b7f62686ed5f4aef267041ef624e3d7e388038
ms.sourcegitcommit: 9a53e53e7a3ef9ac0a212c61005efff9e9902452
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "93219608"
---
# <span data-ttu-id="80deb-103">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="80deb-103">New-CimSession</span></span>

## <span data-ttu-id="80deb-104">概要</span><span class="sxs-lookup"><span data-stu-id="80deb-104">SYNOPSIS</span></span>

<span data-ttu-id="80deb-105">CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-105">Creates a CIM session.</span></span>

## <span data-ttu-id="80deb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80deb-106">SYNTAX</span></span>

### <span data-ttu-id="80deb-107">CredentialParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="80deb-107">CredentialParameterSet (Default)</span></span>

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### <span data-ttu-id="80deb-108">CertificateParameterSet</span><span class="sxs-lookup"><span data-stu-id="80deb-108">CertificateParameterSet</span></span>

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## <span data-ttu-id="80deb-109">Description</span><span class="sxs-lookup"><span data-stu-id="80deb-109">DESCRIPTION</span></span>

<span data-ttu-id="80deb-110">コマンドレットでは、 `New-CimSession` CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-110">The `New-CimSession` cmdlet creates a CIM session.</span></span> <span data-ttu-id="80deb-111">CIM セッションは、ローカルコンピューターまたはリモートコンピューターへの接続を表すクライアント側オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="80deb-111">A CIM session is a client-side object representing a connection to a local computer or a remote computer.</span></span> <span data-ttu-id="80deb-112">CIM セッションには、 **ComputerName** 、使用されるプロトコル、さまざまな識別子など、接続に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="80deb-112">The CIM session contains information about the connection, such as **ComputerName** , the protocol used, or various identifiers.</span></span>

<span data-ttu-id="80deb-113">このコマンドレットは、他のすべての CIM コマンドレットで使用できる CIM セッションオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="80deb-113">This cmdlet returns a CIM session object that can be used by all other CIM cmdlets.</span></span>

## <span data-ttu-id="80deb-114">例</span><span class="sxs-lookup"><span data-stu-id="80deb-114">EXAMPLES</span></span>

### <span data-ttu-id="80deb-115">例 1: 既定のオプションを使用して CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="80deb-115">Example 1: Create a CIM session with default options</span></span>

<span data-ttu-id="80deb-116">この例では、既定のオプションを使用してローカル CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-116">This example creates a local CIM session with default options.</span></span> <span data-ttu-id="80deb-117">**ComputerName** が指定されていない場合、は `New-CimSession` ローカルコンピューターに対して DCOM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-117">If **ComputerName** is not specified, `New-CimSession` creates a DCOM session to the local computer.</span></span>

```powershell
New-CimSession
```

### <span data-ttu-id="80deb-118">例 2: 特定のコンピューターに対して CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="80deb-118">Example 2: Create a CIM session to a specific computer</span></span>

<span data-ttu-id="80deb-119">この例では、 **ComputerName** によって指定されたコンピューターに CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-119">This example creates a CIM session to the computer specified by **ComputerName**.</span></span>
<span data-ttu-id="80deb-120">既定では、 `New-CimSession` **ComputerName** が指定されている場合、は WSMan セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-120">By default, `New-CimSession` creates a WSMan session when **ComputerName** is specified.</span></span>

```powershell
New-CimSession -ComputerName Server01
```

### <span data-ttu-id="80deb-121">例 3: 複数のコンピューターに CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="80deb-121">Example 3: Create a CIM session to multiple computers</span></span>

<span data-ttu-id="80deb-122">この例では、 **ComputerName** によって指定された各コンピューターに、コンマ区切りの一覧で CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-122">This example creates a CIM session to each of the computers specified by **ComputerName** , in the comma separated list.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### <span data-ttu-id="80deb-123">例 4: フレンドリ名を使用して CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="80deb-123">Example 4: Create a CIM session with a friendly name</span></span>

<span data-ttu-id="80deb-124">この例では、 **ComputerName** によって指定された各コンピューターに対して、コンマ区切りの一覧でリモート CIM セッションを作成し、 **名前** を指定することによって、新しいセッションにフレンドリ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="80deb-124">This example creates a remote CIM session to each of the computers specified by **ComputerName** , in the comma separated list, and assigns a friendly name to the new sessions, by specifying **Name**.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

<span data-ttu-id="80deb-125">CIM セッションのフレンドリ名を使用して、他の CIM コマンドレットでセッションを参照することができます (たとえば、 [CimSession](Get-CimSession.md))。</span><span class="sxs-lookup"><span data-stu-id="80deb-125">You can use the friendly name of a CIM session to refer to the session in other CIM cmdlets, for example, [Get-CimSession](Get-CimSession.md).</span></span>

### <span data-ttu-id="80deb-126">例 5: PSCredential オブジェクトを使用してコンピューターに CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="80deb-126">Example 5: Create a CIM session to a computer using a PSCredential object</span></span>

<span data-ttu-id="80deb-127">この例では、ComputerName **によって** 指定された **PSCredential** オブジェクトと、 **authentication** によって指定された認証の種類を使用して、 **ComputerName** によって指定されたコンピューターに CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-127">This example creates a CIM session to the computer specified by **ComputerName** , using the **PSCredential** object specified by **Credential** , and the authentication type specified by **Authentication**.</span></span>

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

<span data-ttu-id="80deb-128">コマンドレットを使用して **PSCredential** オブジェクトを作成でき [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) ます。</span><span class="sxs-lookup"><span data-stu-id="80deb-128">You can create a **PSCredential** object using the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

### <span data-ttu-id="80deb-129">例 6: 特定のポートを使用してコンピューターに CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="80deb-129">Example 6: Create a CIM session to a computer using a specific port</span></span>

<span data-ttu-id="80deb-130">この例では、 **ポート** によって指定された TCP ポートを使用して、 **ComputerName** によって指定されたコンピューターに CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-130">This example creates a CIM session to the computer specified by **ComputerName** using the TCP port specified by **Port**.</span></span>

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### <span data-ttu-id="80deb-131">例 7: DCOM を使用して CIM セッションを作成する</span><span class="sxs-lookup"><span data-stu-id="80deb-131">Example 7: Create a CIM session using DCOM</span></span>

<span data-ttu-id="80deb-132">この例では、WSMan ではなく分散 COM (DCOM) プロトコルを使用して CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80deb-132">This example creates a CIM session using the Distributed COM (DCOM) protocol instead of WSMan.</span></span>

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## <span data-ttu-id="80deb-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="80deb-133">PARAMETERS</span></span>

### <span data-ttu-id="80deb-134">-認証</span><span class="sxs-lookup"><span data-stu-id="80deb-134">-Authentication</span></span>

<span data-ttu-id="80deb-135">ユーザーの資格情報に使用される認証の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="80deb-135">Specifies the authentication type used for the user's credentials.</span></span> <span data-ttu-id="80deb-136">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80deb-136">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="80deb-137">Default</span><span class="sxs-lookup"><span data-stu-id="80deb-137">Default</span></span>
- <span data-ttu-id="80deb-138">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="80deb-138">Digest</span></span>
- <span data-ttu-id="80deb-139">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="80deb-139">Negotiate</span></span>
- <span data-ttu-id="80deb-140">Basic</span><span class="sxs-lookup"><span data-stu-id="80deb-140">Basic</span></span>
- <span data-ttu-id="80deb-141">Kerberos</span><span class="sxs-lookup"><span data-stu-id="80deb-141">Kerberos</span></span>
- <span data-ttu-id="80deb-142">NtlmDomain</span><span class="sxs-lookup"><span data-stu-id="80deb-142">NtlmDomain</span></span>
- <span data-ttu-id="80deb-143">CredSsp</span><span class="sxs-lookup"><span data-stu-id="80deb-143">CredSsp</span></span>

<span data-ttu-id="80deb-144">ローカルコンピューターへの接続に **Ntlmdomain** 認証の種類を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="80deb-144">You cannot use the **NtlmDomain** authentication type for connection to the local computer.</span></span> <span data-ttu-id="80deb-145">**CredSSP** 認証は、windows Vista、windows Server 2008、およびそれ以降のバージョンの windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="80deb-145">**CredSSP** authentication is available only in Windows Vista, Windows Server 2008, and later versions of Windows.</span></span>

> [!CAUTION]
> <span data-ttu-id="80deb-146">Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="80deb-146">Credential Security Service Provider (CredSSP) authentication is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="80deb-147">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="80deb-147">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="80deb-148">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="80deb-148">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="80deb-149">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="80deb-149">-CertificateThumbprint</span></span>

<span data-ttu-id="80deb-150">この操作を実行するアクセス許可を持つユーザーアカウントのデジタル公開キー証明書 (x.509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="80deb-150">Specifies the digital public key certificate (X.509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="80deb-151">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="80deb-151">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="80deb-152">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="80deb-152">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="80deb-153">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="80deb-153">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="80deb-154">証明書の拇印を取得するに [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) は、 [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) PowerShell 証明書プロバイダーでまたはコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="80deb-154">To get a certificate thumbprint, use the [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) or [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) cmdlets in the PowerShell Certificate Provider.</span></span>

<span data-ttu-id="80deb-155">詳細については、「 [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80deb-155">For more information, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

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

### <span data-ttu-id="80deb-156">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="80deb-156">-ComputerName</span></span>

<span data-ttu-id="80deb-157">CIM セッションを作成するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="80deb-157">Specifies the name of the computer to which to create the CIM session.</span></span> <span data-ttu-id="80deb-158">1つのコンピューター名、またはコンマで区切られた複数のコンピューター名を指定してください。</span><span class="sxs-lookup"><span data-stu-id="80deb-158">Specify either a single computer name, or multiple computer names separated by a comma.</span></span>

<span data-ttu-id="80deb-159">**ComputerName** が指定されていない場合は、ローカルコンピューターへの CIM セッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="80deb-159">If **ComputerName** is not specified, a CIM session to the local computer is created.</span></span> <span data-ttu-id="80deb-160">コンピューター名の値は、次のいずれかの形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="80deb-160">You can specify the value for computer name in one of the following formats:</span></span>

- <span data-ttu-id="80deb-161">1つまたは複数の NetBIOS 名</span><span class="sxs-lookup"><span data-stu-id="80deb-161">One or more NetBIOS names</span></span>
- <span data-ttu-id="80deb-162">1つ以上の IP アドレス</span><span class="sxs-lookup"><span data-stu-id="80deb-162">One or more IP addresses</span></span>
- <span data-ttu-id="80deb-163">1つ以上の完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="80deb-163">One or more fully qualified domain names.</span></span>

<span data-ttu-id="80deb-164">コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80deb-164">If the computer is in a different domain than the user, you must specify the fully qualified domain name.</span></span>

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

### <span data-ttu-id="80deb-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="80deb-165">-Credential</span></span>

<span data-ttu-id="80deb-166">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="80deb-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="80deb-167">**Credential** が指定されていない場合は、現在のユーザーアカウントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="80deb-167">If **Credential** is not specified, the current user account is used.</span></span>

<span data-ttu-id="80deb-168">次のいずれかの形式を使用して、 **Credential** の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="80deb-168">Specify the value for **Credential** using one of the following formats:</span></span>

- <span data-ttu-id="80deb-169">ユーザー名: "User01"</span><span class="sxs-lookup"><span data-stu-id="80deb-169">A user name: "User01"</span></span>
- <span data-ttu-id="80deb-170">ドメイン名とユーザー名: "Domain01\user01」"</span><span class="sxs-lookup"><span data-stu-id="80deb-170">A domain name and a user name: "Domain01\User01"</span></span>
- <span data-ttu-id="80deb-171">ユーザープリンシパル名: " User@Domain.com "</span><span class="sxs-lookup"><span data-stu-id="80deb-171">A user principal name: "User@Domain.com"</span></span>
- <span data-ttu-id="80deb-172">コマンドレットによって返されるような PSCredential オブジェクト [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) 。</span><span class="sxs-lookup"><span data-stu-id="80deb-172">A PSCredential object, such as one returned by the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

<span data-ttu-id="80deb-173">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80deb-173">When you type a user name, you are prompted for a password.</span></span>

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

### <span data-ttu-id="80deb-174">-Name</span><span class="sxs-lookup"><span data-stu-id="80deb-174">-Name</span></span>

<span data-ttu-id="80deb-175">CIM セッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="80deb-175">Specifies a friendly name for the CIM session.</span></span>

<span data-ttu-id="80deb-176">名前を使用して、 [CimSession](Get-CimSession.md) コマンドレットなど、他のコマンドレットを使用するときに CIM セッションを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="80deb-176">You can use the name to refer to the CIM session when using other cmdlets, such as the [Get-CimSession](Get-CimSession.md) cmdlet.</span></span>
<span data-ttu-id="80deb-177">名前は、コンピューターや現在のセッションで一意である必要ありません。</span><span class="sxs-lookup"><span data-stu-id="80deb-177">The name is not required to be unique to the computer or the current session.</span></span>

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

### <span data-ttu-id="80deb-178">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="80deb-178">-OperationTimeoutSec</span></span>

<span data-ttu-id="80deb-179">コマンドレットがサーバーからの応答を待機する期間。</span><span class="sxs-lookup"><span data-stu-id="80deb-179">Duration for which the cmdlet waits for a response from the server.</span></span>

<span data-ttu-id="80deb-180">既定では、このパラメーターの値は0です。これは、コマンドレットがサーバーの既定のタイムアウト値を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="80deb-180">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="80deb-181">**Operationtimeoutsec** パラメーターが、堅牢な接続再試行タイムアウトの3分未満の値に設定されている場合、 **operationtimeoutsec** パラメーターの値を超えるネットワークエラーは復旧できません。これは、クライアントが再接続する前に、サーバー上の操作がタイムアウトになるためです。</span><span class="sxs-lookup"><span data-stu-id="80deb-181">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="80deb-182">-Port</span><span class="sxs-lookup"><span data-stu-id="80deb-182">-Port</span></span>

<span data-ttu-id="80deb-183">この接続に使用するリモート コンピューター上のネットワーク ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="80deb-183">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="80deb-184">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="80deb-184">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="80deb-185">既定のポート番号は 5985 (HTTP 用の WinRM ポート) と 5986 (HTTPS 用の WinRM ポート) です。</span><span class="sxs-lookup"><span data-stu-id="80deb-185">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span>

<span data-ttu-id="80deb-186">代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80deb-186">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="80deb-187">リスナーを構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="80deb-187">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

<span data-ttu-id="80deb-188">必要な場合を除き、 **Port** パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="80deb-188">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="80deb-189">コマンドのポート設定は、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="80deb-189">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="80deb-190">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="80deb-190">An alternate port setting might prevent the command from running on all computers.</span></span>

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

### <span data-ttu-id="80deb-191">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="80deb-191">-SessionOption</span></span>

<span data-ttu-id="80deb-192">新しい CIM セッションの詳細オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="80deb-192">Sets advanced options for the new CIM session.</span></span> <span data-ttu-id="80deb-193">コマンドレットを使用して作成された **CimSessionOption** オブジェクトの名前を入力し [`New-CimSessionOption`](New-CimSessionOption.md) ます。</span><span class="sxs-lookup"><span data-stu-id="80deb-193">Enter the name of a **CimSessionOption** object created using the [`New-CimSessionOption`](New-CimSessionOption.md) cmdlet.</span></span>

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

### <span data-ttu-id="80deb-194">-SkipTestConnection</span><span class="sxs-lookup"><span data-stu-id="80deb-194">-SkipTestConnection</span></span>

<span data-ttu-id="80deb-195">既定では、 `New-CimSession` コマンドレットは、リモートの WS-Management エンドポイントとの接続を確立します。これは、リモートサーバーが **port** パラメーターを使用して指定されたポート番号でリッスンしていることを確認し、指定されたアカウントの資格情報を検証するためです。</span><span class="sxs-lookup"><span data-stu-id="80deb-195">By default, the `New-CimSession` cmdlet establishes a connection with a remote WS-Management endpoint for two reasons: to verify that the remote server is listening on the port number that is specified using the **Port** parameter, and to verify the specified account credentials.</span></span> <span data-ttu-id="80deb-196">検証は、標準の WS-Identity 操作を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="80deb-196">The verification is accomplished using a standard WS-Identity operation.</span></span> <span data-ttu-id="80deb-197">リモート WS-Management エンドポイントが WS-ADDRESSING を使用できない場合や、データ転送時間を短縮する場合は、 **Skiptestconnection** スイッチパラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="80deb-197">You can add the **SkipTestConnection** switch parameter if the remote WS-Management endpoint cannot use WS-Identify, or to reduce some data transmission time.</span></span>

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

### <span data-ttu-id="80deb-198">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="80deb-198">CommonParameters</span></span>

<span data-ttu-id="80deb-199">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="80deb-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="80deb-200">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80deb-200">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="80deb-201">入力</span><span class="sxs-lookup"><span data-stu-id="80deb-201">INPUTS</span></span>

### <span data-ttu-id="80deb-202">なし</span><span class="sxs-lookup"><span data-stu-id="80deb-202">None</span></span>

<span data-ttu-id="80deb-203">このコマンドレットは入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="80deb-203">This cmdlet accepts no inputs.</span></span>

## <span data-ttu-id="80deb-204">出力</span><span class="sxs-lookup"><span data-stu-id="80deb-204">OUTPUTS</span></span>

### <span data-ttu-id="80deb-205">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="80deb-205">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="80deb-206">注</span><span class="sxs-lookup"><span data-stu-id="80deb-206">NOTES</span></span>

## <span data-ttu-id="80deb-207">関連リンク</span><span class="sxs-lookup"><span data-stu-id="80deb-207">RELATED LINKS</span></span>

[<span data-ttu-id="80deb-208">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="80deb-208">Get-ChildItem</span></span>](../Microsoft.Powershell.Management/Get-ChildItem.md)

[<span data-ttu-id="80deb-209">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="80deb-209">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="80deb-210">Get-Item</span><span class="sxs-lookup"><span data-stu-id="80deb-210">Get-Item</span></span>](../Microsoft.Powershell.Management/Get-Item.md)

[<span data-ttu-id="80deb-211">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="80deb-211">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="80deb-212">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="80deb-212">Remove-CimSession</span></span>](Remove-CimSession.md)

[<span data-ttu-id="80deb-213">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="80deb-213">New-CimSessionOption</span></span>](New-CimSessionOption.md)

[<span data-ttu-id="80deb-214">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="80deb-214">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

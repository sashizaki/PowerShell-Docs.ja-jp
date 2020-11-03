---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSWorkflow
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowSession
ms.openlocfilehash: 995dd8a6df3ac8ebd7a204d2aefef3fa6aa71e14
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213363"
---
# <span data-ttu-id="9e26e-103">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="9e26e-103">New-PSWorkflowSession</span></span>

## <span data-ttu-id="9e26e-104">概要</span><span class="sxs-lookup"><span data-stu-id="9e26e-104">SYNOPSIS</span></span>
<span data-ttu-id="9e26e-105">ワークフロー セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-105">Creates a workflow session.</span></span>

## <span data-ttu-id="9e26e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e26e-106">SYNTAX</span></span>

```
New-PSWorkflowSession [[-ComputerName] <String[]>] [-Credential <Object>] [-Name <String[]>] [-Port <Int32>]
 [-UseSSL] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-EnableNetworkAccess]
 [<CommonParameters>]
```

## <span data-ttu-id="9e26e-107">Description</span><span class="sxs-lookup"><span data-stu-id="9e26e-107">DESCRIPTION</span></span>

<span data-ttu-id="9e26e-108">`New-PSWorkflowSession`コマンドレットは、Windows PowerShell ワークフローを実行するために特に設計されているユーザー管理セッション ( **PSSession** ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-108">The `New-PSWorkflowSession` cmdlet creates a user-managed session ( **PSSession** ) that is especially designed for running Windows PowerShell workflows.</span></span> <span data-ttu-id="9e26e-109">スクリプト、型と書式設定ファイル、およびワークフローに必要なオプションが含まれている Microsoft.PowerShell.Workflow セッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-109">It uses the Microsoft.PowerShell.Workflow session configuration, which includes scripts, type and formatting files, and options that are required for workflows.</span></span>

<span data-ttu-id="9e26e-110">`New-PSWorkflowSession`またはそのエイリアスであるを使用でき `nwsn` ます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-110">You can use `New-PSWorkflowSession` or its alias, `nwsn`.</span></span>

<span data-ttu-id="9e26e-111">このコマンドにワークフロー共通パラメーターを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-111">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="9e26e-112">ワークフロー共通パラメーターの詳細については、「」を参照してください [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="9e26e-112">For more information about workflow common parameters, see [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="9e26e-113">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9e26e-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="9e26e-114">例</span><span class="sxs-lookup"><span data-stu-id="9e26e-114">EXAMPLES</span></span>

### <span data-ttu-id="9e26e-115">例 1: リモートコンピューターにワークフローセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="9e26e-115">Example 1: Create a workflow session on a remote computer</span></span>

<span data-ttu-id="9e26e-116">この例では、ServerNode01 リモートコンピューターに **Workflowtests** セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-116">This example creates the **WorkflowTests** session on the ServerNode01 remote computer.</span></span>

```powershell
$params = @{
    ComputerName = "ServerNode01"
    Name = "WorkflowTests"
    SessionOption = (New-PSSessionOption -OutputBufferingMode Drop)
}
New-PSWorkflowSession @params
```

<span data-ttu-id="9e26e-117">**Sessionoption** パラメーターの値は、セッションの `New-PSSessionOption` 出力バッファーモードを **Drop** に設定するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="9e26e-117">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that sets the output buffering mode in the session to **Drop** .</span></span>

### <span data-ttu-id="9e26e-118">例 2: 複数のリモートコンピューターにワークフローセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="9e26e-118">Example 2: Create workflow sessions on multiple remote computers</span></span>

<span data-ttu-id="9e26e-119">この例では、ServerNode01 コンピューターと Server12 コンピューター上にワークフローセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-119">This example creates workflow sessions on the ServerNode01 and Server12 computers.</span></span> <span data-ttu-id="9e26e-120">このコマンドでは、 **Credential** パラメーターを使用して、ドメイン管理者のアクセス権で実行します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-120">The command uses the **Credential** parameter to run with the permissions of the domain administrator.</span></span>

```powershell
"ServerNode01", "Server12" |
    New-PSWorkflowSession -Name WorkflowSession -Credential Domain01\Admin01 -ThrottleLimit 150
```

<span data-ttu-id="9e26e-121">**ThrottleLimit** パラメーターを使用して、コマンドごとのスロットル制限を 150 に増やします。</span><span class="sxs-lookup"><span data-stu-id="9e26e-121">The command uses the **ThrottleLimit** parameter to increase the per-command throttle limit to 150.</span></span>
<span data-ttu-id="9e26e-122">この値は、 **Microsoft の PowerShell** のセッション構成で設定されている既定のスロットル制限100よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-122">This value takes precedence over the default throttle limit of 100 that is set in the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

## <span data-ttu-id="9e26e-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9e26e-123">PARAMETERS</span></span>

### <span data-ttu-id="9e26e-124">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="9e26e-124">-ApplicationName</span></span>

<span data-ttu-id="9e26e-125">接続 URI のアプリケーション名セグメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-125">Specifies the application name segment of the connection URI.</span></span>

<span data-ttu-id="9e26e-126">既定値は、 `$PSSessionApplicationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-126">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="9e26e-127">このユーザー設定変数が定義されていない場合、既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-127">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="9e26e-128">この値はほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="9e26e-128">This value is appropriate for most uses.</span></span> <span data-ttu-id="9e26e-129">詳細については、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e26e-129">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="9e26e-130">WinRM サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-130">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="9e26e-131">このパラメーターの値は、リモート コンピューター上のリスナーの **URLPrefix** プロパティの値に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e26e-131">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="9e26e-132">-認証</span><span class="sxs-lookup"><span data-stu-id="9e26e-132">-Authentication</span></span>

<span data-ttu-id="9e26e-133">ユーザー資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-133">Specifies the mechanism that is used to authenticate the user credentials.</span></span>
<span data-ttu-id="9e26e-134">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e26e-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9e26e-135">Default</span><span class="sxs-lookup"><span data-stu-id="9e26e-135">Default</span></span>
- <span data-ttu-id="9e26e-136">Basic</span><span class="sxs-lookup"><span data-stu-id="9e26e-136">Basic</span></span>
- <span data-ttu-id="9e26e-137">Credssp</span><span class="sxs-lookup"><span data-stu-id="9e26e-137">Credssp</span></span>
- <span data-ttu-id="9e26e-138">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="9e26e-138">Digest</span></span>
- <span data-ttu-id="9e26e-139">Kerberos</span><span class="sxs-lookup"><span data-stu-id="9e26e-139">Kerberos</span></span>
- <span data-ttu-id="9e26e-140">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="9e26e-140">Negotiate</span></span>
- <span data-ttu-id="9e26e-141">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="9e26e-141">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="9e26e-142">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-142">The default value is Default.</span></span>

<span data-ttu-id="9e26e-143">CredSSP 認証は、windows Vista、Windows Server 2008、およびそれ以降のバージョンの Windows オペレーティングシステムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-143">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="9e26e-144">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e26e-144">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="9e26e-145">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="9e26e-145">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="9e26e-146">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="9e26e-146">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="9e26e-147">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e26e-147">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e26e-148">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="9e26e-148">-CertificateThumbprint</span></span>

<span data-ttu-id="9e26e-149">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-149">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="9e26e-150">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-150">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="9e26e-151">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-151">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="9e26e-152">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="9e26e-152">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="9e26e-153">証明書の拇印を取得するに `Get-Item` は、コマンドレットまたは `Get-ChildItem` Windows PowerShell Cert: ドライブのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-153">To get a certificate thumbprint, use the `Get-Item` cmdlet or the `Get-ChildItem` cmdlet in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="9e26e-154">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9e26e-154">-ComputerName</span></span>

<span data-ttu-id="9e26e-155">指定されたコンピューターへの永続的な接続 ( **PSSession** ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-155">Creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="9e26e-156">複数のコンピューター名を入力すると、Windows PowerShell は、コンピューターごとに1つ **ずつ、複数の pssession を作成** します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-156">If you enter multiple computer names, Windows PowerShell creates multiple **PSSessions** , one for each computer.</span></span> <span data-ttu-id="9e26e-157">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="9e26e-157">The default is the local computer.</span></span>

<span data-ttu-id="9e26e-158">1 台または複数のリモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-158">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="9e26e-159">ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-159">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="9e26e-160">コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-160">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="9e26e-161">パイプを使用してコンピューター名をに引用符で囲むこともでき `New-PSWorkflowSession` ます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-161">You can also pipe a computer name, in quotation marks to `New-PSWorkflowSession`.</span></span>

<span data-ttu-id="9e26e-162">**ComputerName** パラメーターの値に IP アドレスを使用するには、コマンドに **Credential** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e26e-162">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="9e26e-163">また、HTTPS トランスポート用にコンピューターを構成するか、リモート コンピューターの IP アドレスをローカル コンピューター上の WinRM TrustedHosts 一覧に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e26e-163">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="9e26e-164">TrustedHosts の一覧にコンピューター名を追加する手順については、 [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)の「信頼されたホストの一覧にコンピューターを追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e26e-164">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9e26e-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="9e26e-165">-Credential</span></span>

<span data-ttu-id="9e26e-166">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="9e26e-167">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="9e26e-167">The default is the current user.</span></span> <span data-ttu-id="9e26e-168">User01、Domain01\user01」、などのユーザー名を入力する User@Domain.com か、コマンドレットによって返されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-168">Type a user name, such as User01, Domain01\User01, or User@Domain.com, or enter a **PSCredential** object, such as one returned by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="9e26e-169">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-169">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9e26e-170">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="9e26e-170">-EnableNetworkAccess</span></span>

<span data-ttu-id="9e26e-171">このコマンドレットが、ループバックセッションに対話型セキュリティトークンを追加することを示します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-171">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="9e26e-172">対話型トークンを使用すると、他のコンピューターからデータを取得するコマンドをループバック セッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-172">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="9e26e-173">たとえば、リモート コンピューターからローカル コンピューターに XML ファイルをコピーするコマンドをセッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-173">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="9e26e-174">ループバックセッションは、同じコンピューター上で発生して終了する **PSSession** です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-174">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="9e26e-175">ループバックセッションを作成するには、 **ComputerName** パラメーターを指定しないようにするか、値をドット、localhost、またはローカルコンピューターの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-175">To create a loopback session, do not specify the **ComputerName** parameter or set its value to dot, localhost, or the name of the local computer.</span></span>

<span data-ttu-id="9e26e-176">既定では、ネットワークトークンを持つループバックセッションが作成されます。これにより、リモートコンピューターに対して認証を行うための十分なアクセス許可が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e26e-176">By default, loopback sessions are created that have a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="9e26e-177">**EnableNetworkAccess** パラメーターは、ループバック セッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-177">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="9e26e-178">リモートコンピューターでセッションを作成するときに **EnableNetworkAccess** パラメーターを指定すると、コマンドは成功しますが、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-178">If you specify the **EnableNetworkAccess** parameter when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="9e26e-179">**Authentication** パラメーターの **CredSSP** 値を使用して、ループバック セッションでリモート アクセスを許可することもできます。その場合、セッションの資格情報が他のコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-179">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="9e26e-180">悪意のあるアクセスからコンピューターを保護するために、 **EnableNetworkAccess** パラメーターを使用して作成された、対話型トークンを持つ切断されたループバックセッションは、セッションが作成されたコンピューターからのみ再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-180">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="9e26e-181">CredSSP 認証を使用するセッションが切断された場合には、他のコンピューターから再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-181">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="9e26e-182">詳細については、`Disconnect-PSSession` コマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e26e-182">For more information, see the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="9e26e-183">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9e26e-183">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e26e-184">-Name</span><span class="sxs-lookup"><span data-stu-id="9e26e-184">-Name</span></span>

<span data-ttu-id="9e26e-185">ワークフロー セッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-185">Specifies a friendly name for the workflow session.</span></span> <span data-ttu-id="9e26e-186">この名前は、やなどの他のコマンドレットと共に使用でき `Get-PSSession` `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-186">You can use the name with other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="9e26e-187">名前は、コンピューターや現在のセッションで一意である必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9e26e-187">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Session#
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e26e-188">-Port</span><span class="sxs-lookup"><span data-stu-id="9e26e-188">-Port</span></span>

<span data-ttu-id="9e26e-189">この接続に使用するリモート コンピューター上のネットワーク ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-189">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="9e26e-190">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-190">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="9e26e-191">既定のポートは 5985 (HTTP の場合は WinRM ポート)、5986 (HTTPS の場合は WinRM ポート) です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-191">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="9e26e-192">別のポートを使用する前に、そのポートでリッスンするようにリモートコンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e26e-192">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="9e26e-193">リスナーを構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-193">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="9e26e-194">必要な場合を除き、 **Port** パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9e26e-194">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="9e26e-195">コマンドのポート設定は、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-195">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="9e26e-196">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e26e-196">An alternate port setting might prevent the command from running on all computers.</span></span>

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

### <span data-ttu-id="9e26e-197">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="9e26e-197">-SessionOption</span></span>

<span data-ttu-id="9e26e-198">セッションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-198">Specifies advanced options for the session.</span></span> <span data-ttu-id="9e26e-199">コマンドレットを使用して作成したものなど、 **Sessionoption** オブジェクトを入力し `New-PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-199">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet.</span></span>

<span data-ttu-id="9e26e-200">オプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-200">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="9e26e-201">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="9e26e-201">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="9e26e-202">セッションオプションの値は、ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-202">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="9e26e-203">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="9e26e-203">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="9e26e-204">セッション構成の詳細については、「 [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e26e-204">For more information about session configurations, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="9e26e-205">既定値を含む、セッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="9e26e-205">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="9e26e-206">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e26e-206">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e26e-207">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="9e26e-207">-ThrottleLimit</span></span>

<span data-ttu-id="9e26e-208">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-208">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="9e26e-209">このパラメーターを省略した場合、または値 0 (ゼロ) を入力した場合は、 **Microsoft の PowerShellWorkflow** セッション構成100の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-209">If you omit this parameter or enter a value of 0 (zero), the default value for the **Microsoft.PowerShellWorkflow** session configuration, 100, is used.</span></span>

<span data-ttu-id="9e26e-210">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="9e26e-210">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e26e-211">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="9e26e-211">-UseSSL</span></span>

<span data-ttu-id="9e26e-212">このコマンドレットが、リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-212">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="9e26e-213">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="9e26e-213">By default, SSL is not used.</span></span>

<span data-ttu-id="9e26e-214">WS-Management は、ネットワークを介して転送されるすべての Windows PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-214">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="9e26e-215">**UseSSL** パラメーターは、HTTP 接続ではなく HTTPS 接続を介してデータを送信する追加の保護です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-215">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="9e26e-216">このパラメーターを指定しても、コマンドに使用されるポートで SSL を使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9e26e-216">If you specify this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e26e-217">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e26e-217">CommonParameters</span></span>

<span data-ttu-id="9e26e-218">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9e26e-219">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e26e-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9e26e-220">入力</span><span class="sxs-lookup"><span data-stu-id="9e26e-220">INPUTS</span></span>

### <span data-ttu-id="9e26e-221">System...--[], System.string</span><span class="sxs-lookup"><span data-stu-id="9e26e-221">System.Management.Automation.Runspaces.PSSession[], System.String</span></span>

<span data-ttu-id="9e26e-222">このコマンドレットには、セッションまたはコンピューター名をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="9e26e-222">You can pipe a session or a computer name to this cmdlet.</span></span>

## <span data-ttu-id="9e26e-223">出力</span><span class="sxs-lookup"><span data-stu-id="9e26e-223">OUTPUTS</span></span>

### <span data-ttu-id="9e26e-224">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="9e26e-224">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="9e26e-225">注</span><span class="sxs-lookup"><span data-stu-id="9e26e-225">NOTES</span></span>

<span data-ttu-id="9e26e-226">`New-PSWorkflowSession`コマンドは、次のコマンドと同等です。</span><span class="sxs-lookup"><span data-stu-id="9e26e-226">A `New-PSWorkflowSession` command is equivalent to the following command:</span></span>

`New-PSSession -ConfigurationName Microsoft.PowerShell.Workflow`

## <span data-ttu-id="9e26e-227">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9e26e-227">RELATED LINKS</span></span>

[<span data-ttu-id="9e26e-228">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="9e26e-228">Disconnect-PSSession</span></span>](../Microsoft.PowerShell.Core/Disconnect-PSSession.md)

[<span data-ttu-id="9e26e-229">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="9e26e-229">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="9e26e-230">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="9e26e-230">New-PSTransportOption</span></span>](../Microsoft.PowerShell.Core/New-PSTransportOption.md)

[<span data-ttu-id="9e26e-231">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9e26e-231">Register-PSSessionConfiguration</span></span>](../Microsoft.PowerShell.Core/Register-PSSessionConfiguration.md)

[<span data-ttu-id="9e26e-232">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="9e26e-232">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="9e26e-233">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="9e26e-233">about_Session_Configurations</span></span>](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)

[<span data-ttu-id="9e26e-234">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="9e26e-234">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="9e26e-235">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="9e26e-235">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)

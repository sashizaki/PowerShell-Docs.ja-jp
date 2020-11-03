---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: a1fa09116e7069f3fc7f3d196bffd20f491a93e2
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218744"
---
# <span data-ttu-id="9c73e-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="9c73e-103">Stop-Computer</span></span>

## <span data-ttu-id="9c73e-104">概要</span><span class="sxs-lookup"><span data-stu-id="9c73e-104">SYNOPSIS</span></span>
<span data-ttu-id="9c73e-105">ローカルとリモートのコンピューターを停止 (シャットダウン) します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="9c73e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c73e-106">SYNTAX</span></span>

### <span data-ttu-id="9c73e-107">All</span><span class="sxs-lookup"><span data-stu-id="9c73e-107">All</span></span>

```
Stop-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9c73e-108">Description</span><span class="sxs-lookup"><span data-stu-id="9c73e-108">DESCRIPTION</span></span>

<span data-ttu-id="9c73e-109">この `Stop-Computer` コマンドレットは、ローカルコンピューターとリモートコンピューターをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="9c73e-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="9c73e-110">のパラメーターを使用して、 `Stop-Computer` 認証レベルと代替資格情報を指定し、即時シャットダウンを強制することができます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-110">You can use the parameters of `Stop-Computer` to specify the authentication levels and alternate credentials, and to force an immediate shut down.</span></span>

<span data-ttu-id="9c73e-111">PowerShell 7.1 で `Stop-Computer` は、Linux および macOS 用にが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9c73e-111">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="9c73e-112">これらのプラットフォームには、パラメーターは影響しません。</span><span class="sxs-lookup"><span data-stu-id="9c73e-112">The parameters have no effect on these platforms.</span></span> <span data-ttu-id="9c73e-113">コマンドレットは、ネイティブコマンドを呼び出すだけです `/sbin/shutdown` 。</span><span class="sxs-lookup"><span data-stu-id="9c73e-113">The cmdlet is just calling the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="9c73e-114">例</span><span class="sxs-lookup"><span data-stu-id="9c73e-114">EXAMPLES</span></span>

### <span data-ttu-id="9c73e-115">例 1: ローカルコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="9c73e-115">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="9c73e-116">この例では、ローカルコンピューターをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="9c73e-116">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="9c73e-117">例 2: 2 台のリモートコンピューターとローカルコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="9c73e-117">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="9c73e-118">この例では、2台のリモートコンピューターとローカルコンピューターを停止します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-118">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="9c73e-119">`Stop-Computer`**ComputerName** パラメーターを使用して、2台のリモートコンピューターとローカルコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-119">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="9c73e-120">各コンピューターがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-120">Each computer is shut down.</span></span>

### <span data-ttu-id="9c73e-121">例 3: バックグラウンドジョブとしてリモートコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="9c73e-121">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="9c73e-122">この例では、は `Stop-Computer` 2 台のリモートコンピューター上でバックグラウンドジョブとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-122">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

<span data-ttu-id="9c73e-123">バックグラウンド操作では、 `&` `Stop-Computer` バックグラウンドジョブとしてコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-123">The background operator `&` runs the `Stop-Computer` command as a background job.</span></span> <span data-ttu-id="9c73e-124">詳細については、「 [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c73e-124">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" &
$results = $j | Receive-Job
$results
```

<span data-ttu-id="9c73e-125">`Stop-Computer`**ComputerName** パラメーターを使用して、2台のリモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-125">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="9c73e-126">バックグラウンド操作では、 `&` バックグラウンドジョブとしてコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-126">The `&` background operator runs the command as a background job.</span></span> <span data-ttu-id="9c73e-127">ジョブオブジェクトは変数に格納され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-127">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="9c73e-128">変数内のジョブオブジェクト `$j` は、にパイプラインから送信され、 `Receive-Job` ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-128">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="9c73e-129">オブジェクトは変数に格納され `$results` ます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-129">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="9c73e-130">変数は、 `$results` PowerShell コンソールにジョブ情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-130">The `$results` variable displays the job information in the PowerShell console.</span></span>

### <span data-ttu-id="9c73e-131">例 4: リモートコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="9c73e-131">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="9c73e-132">この例では、指定された認証を使用してリモートコンピューターをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="9c73e-132">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -WsmanAuthentication Kerberos
```

<span data-ttu-id="9c73e-133">`Stop-Computer`**ComputerName** パラメーターを使用して、リモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-133">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="9c73e-134">**WsmanAuthentication** パラメーターは、リモート接続を確立するために Kerberos を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-134">The **WsmanAuthentication** parameter specifies to use Kerberos to establish a remote connection.</span></span>

### <span data-ttu-id="9c73e-135">例 5: ドメイン内のコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="9c73e-135">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="9c73e-136">この例では、コマンドを実行すると、指定したドメイン内のすべてのコンピューターが即座にシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-136">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -Credential $c
```

<span data-ttu-id="9c73e-137">`Get-Content`**Path** パラメーターを使用して、現在のディレクトリにあるファイルをドメインコンピューターの一覧と共に取得します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-137">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="9c73e-138">オブジェクトは変数に格納され `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-138">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="9c73e-139">`Get-Credential` は、 **Credential** パラメーターを使用して、ドメイン管理者の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-139">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="9c73e-140">資格情報は変数に格納され `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-140">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="9c73e-141">`Stop-Computer` 変数内の **ComputerName** パラメーターのコンピューターの一覧で指定されたコンピューターをシャットダウンし `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-141">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="9c73e-142">**Force** パラメーターを指定すると、即時シャットダウンが強制されます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-142">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="9c73e-143">**Credential** パラメーターは、変数に保存されている資格情報を送信し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-143">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="9c73e-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c73e-144">PARAMETERS</span></span>

### <span data-ttu-id="9c73e-145">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9c73e-145">-ComputerName</span></span>

<span data-ttu-id="9c73e-146">停止するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-146">Specifies the computers to stop.</span></span> <span data-ttu-id="9c73e-147">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="9c73e-147">The default is the local computer.</span></span>

<span data-ttu-id="9c73e-148">コンマ区切りのリストで、1 台または複数のコンピューターの NETBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-148">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="9c73e-149">ローカルコンピューターを指定するには、コンピューター名または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-149">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="9c73e-150">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="9c73e-150">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="9c73e-151">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-151">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9c73e-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9c73e-152">-Confirm</span></span>

<span data-ttu-id="9c73e-153">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-153">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c73e-154">-Credential</span><span class="sxs-lookup"><span data-stu-id="9c73e-154">-Credential</span></span>

<span data-ttu-id="9c73e-155">このアクションを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-155">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="9c73e-156">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="9c73e-156">The default is the current user.</span></span>

<span data-ttu-id="9c73e-157">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-157">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="9c73e-158">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-158">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="9c73e-159">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-159">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="9c73e-160">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c73e-160">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c73e-161">-Force</span><span class="sxs-lookup"><span data-stu-id="9c73e-161">-Force</span></span>

<span data-ttu-id="9c73e-162">コンピューターの即時シャットダウンを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-162">Forces an immediate shut down of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c73e-163">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="9c73e-163">-WsmanAuthentication</span></span>

<span data-ttu-id="9c73e-164">このコマンドレットで WSMan プロトコルを使用するときに、ユーザー資格情報の認証に使用されるメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-164">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="9c73e-165">既定値は **Default** です。</span><span class="sxs-lookup"><span data-stu-id="9c73e-165">The default value is **Default**.</span></span>

<span data-ttu-id="9c73e-166">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9c73e-166">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9c73e-167">Basic</span><span class="sxs-lookup"><span data-stu-id="9c73e-167">Basic</span></span>
- <span data-ttu-id="9c73e-168">CredSSP</span><span class="sxs-lookup"><span data-stu-id="9c73e-168">CredSSP</span></span>
- <span data-ttu-id="9c73e-169">Default</span><span class="sxs-lookup"><span data-stu-id="9c73e-169">Default</span></span>
- <span data-ttu-id="9c73e-170">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="9c73e-170">Digest</span></span>
- <span data-ttu-id="9c73e-171">Kerberos</span><span class="sxs-lookup"><span data-stu-id="9c73e-171">Kerberos</span></span>
- <span data-ttu-id="9c73e-172">Negotiate</span><span class="sxs-lookup"><span data-stu-id="9c73e-172">Negotiate.</span></span>

<span data-ttu-id="9c73e-173">このパラメーターの値の詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c73e-173">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="9c73e-174">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="9c73e-174">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="9c73e-175">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="9c73e-175">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="9c73e-176">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9c73e-176">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="9c73e-177">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9c73e-177">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c73e-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9c73e-178">-WhatIf</span></span>

<span data-ttu-id="9c73e-179">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-179">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9c73e-180">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9c73e-180">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c73e-181">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9c73e-181">CommonParameters</span></span>

<span data-ttu-id="9c73e-182">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9c73e-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9c73e-183">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c73e-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9c73e-184">入力</span><span class="sxs-lookup"><span data-stu-id="9c73e-184">INPUTS</span></span>

### <span data-ttu-id="9c73e-185">なし</span><span class="sxs-lookup"><span data-stu-id="9c73e-185">None</span></span>

<span data-ttu-id="9c73e-186">このコマンドレットに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9c73e-186">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9c73e-187">出力</span><span class="sxs-lookup"><span data-stu-id="9c73e-187">OUTPUTS</span></span>

### <span data-ttu-id="9c73e-188">なし</span><span class="sxs-lookup"><span data-stu-id="9c73e-188">None</span></span>

## <span data-ttu-id="9c73e-189">注</span><span class="sxs-lookup"><span data-stu-id="9c73e-189">NOTES</span></span>

<span data-ttu-id="9c73e-190">このコマンドレットは、 **Win32_OperatingSystem** WMI クラスの **Win32Shutdown** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c73e-190">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="9c73e-191">この方法では、コンピューターの再起動に使用するユーザーアカウントに対して、 **Seshutdownprivilege** 特権を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c73e-191">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="9c73e-192">PowerShell 7.1 で `Stop-Computer` は、Linux および macOS 用にが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9c73e-192">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="9c73e-193">これらの platorms では、コマンドレットはネイティブコマンドを呼び出し `/sbin/shutdown` ます。</span><span class="sxs-lookup"><span data-stu-id="9c73e-193">For these platorms, the cmdlet calls the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="9c73e-194">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9c73e-194">RELATED LINKS</span></span>

[<span data-ttu-id="9c73e-195">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="9c73e-195">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="9c73e-196">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="9c73e-196">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="9c73e-197">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="9c73e-197">Test-Connection</span></span>](Test-Connection.md)


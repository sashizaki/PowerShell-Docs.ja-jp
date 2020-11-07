---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8c6d70622f48183ed2f6bcd4526c305c70fe6eb2
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345087"
---
# <span data-ttu-id="30d5f-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="30d5f-103">Stop-Computer</span></span>

## <span data-ttu-id="30d5f-104">概要</span><span class="sxs-lookup"><span data-stu-id="30d5f-104">SYNOPSIS</span></span>
<span data-ttu-id="30d5f-105">ローカルとリモートのコンピューターを停止 (シャットダウン) します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="30d5f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="30d5f-106">SYNTAX</span></span>

### <span data-ttu-id="30d5f-107">すべて</span><span class="sxs-lookup"><span data-stu-id="30d5f-107">All</span></span>

```
Stop-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="30d5f-108">Description</span><span class="sxs-lookup"><span data-stu-id="30d5f-108">DESCRIPTION</span></span>

<span data-ttu-id="30d5f-109">この `Stop-Computer` コマンドレットは、ローカルコンピューターとリモートコンピューターをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="30d5f-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="30d5f-110">のパラメーターを使用して、 `Stop-Computer` 認証レベルと代替資格情報を指定し、即時シャットダウンを強制することができます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-110">You can use the parameters of `Stop-Computer` to specify the authentication levels and alternate credentials, and to force an immediate shut down.</span></span>

## <span data-ttu-id="30d5f-111">例</span><span class="sxs-lookup"><span data-stu-id="30d5f-111">EXAMPLES</span></span>

### <span data-ttu-id="30d5f-112">例 1: ローカルコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="30d5f-112">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="30d5f-113">この例では、ローカルコンピューターをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="30d5f-113">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="30d5f-114">例 2: 2 台のリモートコンピューターとローカルコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="30d5f-114">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="30d5f-115">この例では、2台のリモートコンピューターとローカルコンピューターを停止します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-115">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="30d5f-116">`Stop-Computer`**ComputerName** パラメーターを使用して、2台のリモートコンピューターとローカルコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-116">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="30d5f-117">各コンピューターがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-117">Each computer is shut down.</span></span>

### <span data-ttu-id="30d5f-118">例 3: バックグラウンドジョブとしてリモートコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="30d5f-118">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="30d5f-119">この例では、は `Stop-Computer` 2 台のリモートコンピューター上でバックグラウンドジョブとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-119">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

<span data-ttu-id="30d5f-120">バックグラウンド操作では、 `&` `Stop-Computer` バックグラウンドジョブとしてコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-120">The background operator `&` runs the `Stop-Computer` command as a background job.</span></span> <span data-ttu-id="30d5f-121">詳細については、「 [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30d5f-121">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" &
$results = $j | Receive-Job
$results
```

<span data-ttu-id="30d5f-122">`Stop-Computer`**ComputerName** パラメーターを使用して、2台のリモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-122">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="30d5f-123">バックグラウンド操作では、 `&` バックグラウンドジョブとしてコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-123">The `&` background operator runs the command as a background job.</span></span> <span data-ttu-id="30d5f-124">ジョブオブジェクトは変数に格納され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-124">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="30d5f-125">変数内のジョブオブジェクト `$j` は、にパイプラインから送信され、 `Receive-Job` ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-125">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="30d5f-126">オブジェクトは変数に格納され `$results` ます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-126">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="30d5f-127">変数は、 `$results` PowerShell コンソールにジョブ情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-127">The `$results` variable displays the job information in the PowerShell console.</span></span>

### <span data-ttu-id="30d5f-128">例 4: リモートコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="30d5f-128">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="30d5f-129">この例では、指定された認証を使用してリモートコンピューターをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="30d5f-129">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -WsmanAuthentication Kerberos
```

<span data-ttu-id="30d5f-130">`Stop-Computer`**ComputerName** パラメーターを使用して、リモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-130">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="30d5f-131">**WsmanAuthentication** パラメーターは、リモート接続を確立するために Kerberos を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-131">The **WsmanAuthentication** parameter specifies to use Kerberos to establish a remote connection.</span></span>

### <span data-ttu-id="30d5f-132">例 5: ドメイン内のコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="30d5f-132">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="30d5f-133">この例では、コマンドを実行すると、指定したドメイン内のすべてのコンピューターが即座にシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-133">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -Credential $c
```

<span data-ttu-id="30d5f-134">`Get-Content`**Path** パラメーターを使用して、現在のディレクトリにあるファイルをドメインコンピューターの一覧と共に取得します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-134">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="30d5f-135">オブジェクトは変数に格納され `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-135">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="30d5f-136">`Get-Credential` は、 **Credential** パラメーターを使用して、ドメイン管理者の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-136">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="30d5f-137">資格情報は変数に格納され `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-137">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="30d5f-138">`Stop-Computer` 変数内の **ComputerName** パラメーターのコンピューターの一覧で指定されたコンピューターをシャットダウンし `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-138">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="30d5f-139">**Force** パラメーターを指定すると、即時シャットダウンが強制されます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-139">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="30d5f-140">**Credential** パラメーターは、変数に保存されている資格情報を送信し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-140">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="30d5f-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="30d5f-141">PARAMETERS</span></span>

### <span data-ttu-id="30d5f-142">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="30d5f-142">-ComputerName</span></span>

<span data-ttu-id="30d5f-143">停止するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-143">Specifies the computers to stop.</span></span> <span data-ttu-id="30d5f-144">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="30d5f-144">The default is the local computer.</span></span>

<span data-ttu-id="30d5f-145">コンマ区切りのリストで、1 台または複数のコンピューターの NETBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-145">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="30d5f-146">ローカルコンピューターを指定するには、コンピューター名または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-146">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="30d5f-147">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="30d5f-147">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="30d5f-148">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-148">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

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

### <span data-ttu-id="30d5f-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="30d5f-149">-Confirm</span></span>

<span data-ttu-id="30d5f-150">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="30d5f-151">-Credential</span><span class="sxs-lookup"><span data-stu-id="30d5f-151">-Credential</span></span>

<span data-ttu-id="30d5f-152">このアクションを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-152">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="30d5f-153">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="30d5f-153">The default is the current user.</span></span>

<span data-ttu-id="30d5f-154">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-154">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="30d5f-155">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-155">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="30d5f-156">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-156">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="30d5f-157">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30d5f-157">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="30d5f-158">-Force</span><span class="sxs-lookup"><span data-stu-id="30d5f-158">-Force</span></span>

<span data-ttu-id="30d5f-159">コンピューターの即時シャットダウンを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-159">Forces an immediate shut down of the computer.</span></span>

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

### <span data-ttu-id="30d5f-160">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="30d5f-160">-WsmanAuthentication</span></span>

<span data-ttu-id="30d5f-161">このコマンドレットで WSMan プロトコルを使用するときに、ユーザー資格情報の認証に使用されるメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-161">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="30d5f-162">既定値は **Default** です。</span><span class="sxs-lookup"><span data-stu-id="30d5f-162">The default value is **Default**.</span></span>

<span data-ttu-id="30d5f-163">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="30d5f-163">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="30d5f-164">基本</span><span class="sxs-lookup"><span data-stu-id="30d5f-164">Basic</span></span>
- <span data-ttu-id="30d5f-165">CredSSP</span><span class="sxs-lookup"><span data-stu-id="30d5f-165">CredSSP</span></span>
- <span data-ttu-id="30d5f-166">Default</span><span class="sxs-lookup"><span data-stu-id="30d5f-166">Default</span></span>
- <span data-ttu-id="30d5f-167">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="30d5f-167">Digest</span></span>
- <span data-ttu-id="30d5f-168">Kerberos</span><span class="sxs-lookup"><span data-stu-id="30d5f-168">Kerberos</span></span>
- <span data-ttu-id="30d5f-169">Negotiate</span><span class="sxs-lookup"><span data-stu-id="30d5f-169">Negotiate.</span></span>

<span data-ttu-id="30d5f-170">このパラメーターの値の詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30d5f-170">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="30d5f-171">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="30d5f-171">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="30d5f-172">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="30d5f-172">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="30d5f-173">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="30d5f-173">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="30d5f-174">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="30d5f-174">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="30d5f-175">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="30d5f-175">-WhatIf</span></span>

<span data-ttu-id="30d5f-176">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-176">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="30d5f-177">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="30d5f-177">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="30d5f-178">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="30d5f-178">CommonParameters</span></span>

<span data-ttu-id="30d5f-179">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="30d5f-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="30d5f-180">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30d5f-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="30d5f-181">入力</span><span class="sxs-lookup"><span data-stu-id="30d5f-181">INPUTS</span></span>

### <span data-ttu-id="30d5f-182">なし</span><span class="sxs-lookup"><span data-stu-id="30d5f-182">None</span></span>

<span data-ttu-id="30d5f-183">このコマンドレットに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="30d5f-183">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="30d5f-184">出力</span><span class="sxs-lookup"><span data-stu-id="30d5f-184">OUTPUTS</span></span>

### <span data-ttu-id="30d5f-185">なし</span><span class="sxs-lookup"><span data-stu-id="30d5f-185">None</span></span>

## <span data-ttu-id="30d5f-186">注</span><span class="sxs-lookup"><span data-stu-id="30d5f-186">NOTES</span></span>

<span data-ttu-id="30d5f-187">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="30d5f-187">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="30d5f-188">このコマンドレットは、Windows でのみ機能し、 **Win32_OperatingSystem** WMI クラスの **Win32Shutdown** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="30d5f-188">This cmdlet only works on Windows and uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="30d5f-189">この方法では、コンピューターの再起動に使用するユーザーアカウントに対して、 **Seshutdownprivilege** 特権を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30d5f-189">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="30d5f-190">関連リンク</span><span class="sxs-lookup"><span data-stu-id="30d5f-190">RELATED LINKS</span></span>

[<span data-ttu-id="30d5f-191">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="30d5f-191">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="30d5f-192">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="30d5f-192">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="30d5f-193">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="30d5f-193">Test-Connection</span></span>](Test-Connection.md)

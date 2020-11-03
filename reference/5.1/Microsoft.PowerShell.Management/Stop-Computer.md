---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8062210aa94cb46d5e5557ede1bac672cae39622
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218256"
---
# <span data-ttu-id="77ff4-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="77ff4-103">Stop-Computer</span></span>

## <span data-ttu-id="77ff4-104">概要</span><span class="sxs-lookup"><span data-stu-id="77ff4-104">SYNOPSIS</span></span>
<span data-ttu-id="77ff4-105">ローカルとリモートのコンピューターを停止 (シャットダウン) します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="77ff4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77ff4-106">SYNTAX</span></span>

### <span data-ttu-id="77ff4-107">All</span><span class="sxs-lookup"><span data-stu-id="77ff4-107">All</span></span>

```
Stop-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="77ff4-108">Description</span><span class="sxs-lookup"><span data-stu-id="77ff4-108">DESCRIPTION</span></span>

<span data-ttu-id="77ff4-109">この `Stop-Computer` コマンドレットは、ローカルコンピューターとリモートコンピューターをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="77ff4-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="77ff4-110">のパラメーターを使用し `Stop-Computer` て、バックグラウンドジョブとしてのシャットダウン操作の実行、認証レベルと代替資格情報の指定、コマンドを実行するために作成される同時接続の制限、および即時シャットダウンの強制を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-110">You can use the parameters of `Stop-Computer` to run the shutdown operations as a background job, to specify the authentication levels and alternate credentials, to limit the concurrent connections that are created to run the command, and to force an immediate shut down.</span></span>

<span data-ttu-id="77ff4-111">このコマンドレットでは、 **AsJob** パラメーターを使用しない限り、PowerShell リモート処理は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="77ff4-111">This cmdlet doesn't require PowerShell remoting unless you use the **AsJob** parameter.</span></span>

## <span data-ttu-id="77ff4-112">例</span><span class="sxs-lookup"><span data-stu-id="77ff4-112">EXAMPLES</span></span>

### <span data-ttu-id="77ff4-113">例 1: ローカルコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="77ff4-113">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="77ff4-114">この例では、ローカルコンピューターをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="77ff4-114">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="77ff4-115">例 2: 2 台のリモートコンピューターとローカルコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="77ff4-115">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="77ff4-116">この例では、2台のリモートコンピューターとローカルコンピューターを停止します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-116">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="77ff4-117">`Stop-Computer`**ComputerName** パラメーターを使用して、2台のリモートコンピューターとローカルコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-117">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="77ff4-118">各コンピューターがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-118">Each computer is shut down.</span></span>

### <span data-ttu-id="77ff4-119">例 3: バックグラウンドジョブとしてリモートコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="77ff4-119">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="77ff4-120">この例では、は `Stop-Computer` 2 台のリモートコンピューター上でバックグラウンドジョブとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-120">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" -AsJob
$results = $j | Receive-Job
$results
```

<span data-ttu-id="77ff4-121">`Stop-Computer`**ComputerName** パラメーターを使用して、2台のリモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-121">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="77ff4-122">**AsJob** パラメーターは、コマンドをバックグラウンドジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-122">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="77ff4-123">ジョブオブジェクトは変数に格納され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-123">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="77ff4-124">変数内のジョブオブジェクト `$j` は、にパイプラインから送信され、 `Receive-Job` ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-124">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="77ff4-125">オブジェクトは変数に格納され `$results` ます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-125">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="77ff4-126">変数は、 `$results` PowerShell コンソールにジョブ情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-126">The `$results` variable displays the job information in the PowerShell console.</span></span>

<span data-ttu-id="77ff4-127">**AsJob** はローカルコンピューターにジョブを作成し、結果をローカルコンピューターに自動的に返すため、 `Receive-Job` ローカルコマンドとしてを実行できます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-127">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

### <span data-ttu-id="77ff4-128">例 4: リモートコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="77ff4-128">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="77ff4-129">この例では、指定された認証を使用してリモートコンピューターをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="77ff4-129">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="77ff4-130">`Stop-Computer`**ComputerName** パラメーターを使用して、リモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-130">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="77ff4-131">**Impersonation** パラメーターはカスタマイズされた偽装を指定し、 **DcomAuthentication** パラメーターは認証レベルの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-131">The **Impersonation** parameter specifies a customized impersonation and the **DcomAuthentication** parameter specifies authentication-level settings.</span></span>

### <span data-ttu-id="77ff4-132">例 5: ドメイン内のコンピューターをシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="77ff4-132">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="77ff4-133">この例では、コマンドを実行すると、指定したドメイン内のすべてのコンピューターが即座にシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-133">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -ThrottleLimit 10 -Credential $c
```

<span data-ttu-id="77ff4-134">`Get-Content`**Path** パラメーターを使用して、現在のディレクトリにあるファイルをドメインコンピューターの一覧と共に取得します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-134">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="77ff4-135">オブジェクトは変数に格納され `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-135">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="77ff4-136">`Get-Credential` は、 **Credential** パラメーターを使用して、ドメイン管理者の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-136">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="77ff4-137">資格情報は変数に格納され `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-137">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="77ff4-138">`Stop-Computer` 変数内の **ComputerName** パラメーターのコンピューターの一覧で指定されたコンピューターをシャットダウンし `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-138">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="77ff4-139">**Force** パラメーターを指定すると、即時シャットダウンが強制されます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-139">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="77ff4-140">**ThrottleLimit** パラメーターは、コマンドの同時接続数を10に制限します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-140">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span> <span data-ttu-id="77ff4-141">**Credential** パラメーターは、変数に保存されている資格情報を送信し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-141">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="77ff4-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77ff4-142">PARAMETERS</span></span>

### <span data-ttu-id="77ff4-143">-AsJob</span><span class="sxs-lookup"><span data-stu-id="77ff4-143">-AsJob</span></span>

<span data-ttu-id="77ff4-144">このコマンドレットがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-144">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="77ff4-145">このパラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。 windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[ **管理者として実行** ] オプションを使用して PowerShell を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="77ff4-145">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="77ff4-146">詳細については、「[about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ff4-146">For more information, see [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="77ff4-147">**AsJob** パラメーターを指定すると、コマンドは、バックグラウンドジョブを表すオブジェクトを直ちに返します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-147">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="77ff4-148">ジョブが完了しても、引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-148">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="77ff4-149">ジョブは、ローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-149">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="77ff4-150">ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-150">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="77ff4-151">PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) 」および「 [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ff4-151">For more information about PowerShell background jobs, see [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) and [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).</span></span>

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

### <span data-ttu-id="77ff4-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="77ff4-152">-ComputerName</span></span>

<span data-ttu-id="77ff4-153">停止するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-153">Specifies the computers to stop.</span></span> <span data-ttu-id="77ff4-154">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="77ff4-154">The default is the local computer.</span></span>

<span data-ttu-id="77ff4-155">コンマ区切りのリストで、1 台または複数のコンピューターの NETBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-155">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="77ff4-156">ローカルコンピューターを指定するには、コンピューター名または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-156">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="77ff4-157">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="77ff4-157">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="77ff4-158">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-158">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

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

### <span data-ttu-id="77ff4-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="77ff4-159">-Confirm</span></span>

<span data-ttu-id="77ff4-160">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="77ff4-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="77ff4-161">-Credential</span></span>

<span data-ttu-id="77ff4-162">このアクションを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-162">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="77ff4-163">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="77ff4-163">The default is the current user.</span></span>

<span data-ttu-id="77ff4-164">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-164">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="77ff4-165">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-165">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="77ff4-166">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="77ff4-167">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ff4-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="77ff4-168">-DcomAuthentication</span><span class="sxs-lookup"><span data-stu-id="77ff4-168">-DcomAuthentication</span></span>

<span data-ttu-id="77ff4-169">このコマンドレットが WMI で使用する認証レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-169">Specifies the authentication level that this cmdlet uses with WMI.</span></span> <span data-ttu-id="77ff4-170">`Stop-Computer` WMI を使用します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-170">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="77ff4-171">既定値は **Packet** です。</span><span class="sxs-lookup"><span data-stu-id="77ff4-171">The default value is **Packet**.</span></span>

<span data-ttu-id="77ff4-172">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="77ff4-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="77ff4-173">**既定値** は Windows 認証です。</span><span class="sxs-lookup"><span data-stu-id="77ff4-173">**Default** : Windows Authentication.</span></span>
- <span data-ttu-id="77ff4-174">**None** : COM 認証なし。</span><span class="sxs-lookup"><span data-stu-id="77ff4-174">**None** : No COM authentication.</span></span>
- <span data-ttu-id="77ff4-175">**接続** : 接続レベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="77ff4-175">**Connect** : Connect-level COM authentication.</span></span>
- <span data-ttu-id="77ff4-176">**呼び出し** : 呼び出しレベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="77ff4-176">**Call** : Call-level COM authentication.</span></span>
- <span data-ttu-id="77ff4-177">**パケット** : パケットレベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="77ff4-177">**Packet** : Packet-level COM authentication.</span></span>
- <span data-ttu-id="77ff4-178">**Packetintegrity** : パケットの整合性レベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="77ff4-178">**PacketIntegrity** : Packet Integrity-level COM authentication.</span></span>
- <span data-ttu-id="77ff4-179">**Packetprivacy** : パケットプライバシーレベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="77ff4-179">**PacketPrivacy** : Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="77ff4-180">**Unchanged** : 前のコマンドと同じです。</span><span class="sxs-lookup"><span data-stu-id="77ff4-180">**Unchanged** : Same as the previous command.</span></span>

<span data-ttu-id="77ff4-181">このパラメーターの値の詳細については、「 [Authenticationlevel](/dotnet/api/system.management.authenticationlevel)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ff4-181">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77ff4-182">-Force</span><span class="sxs-lookup"><span data-stu-id="77ff4-182">-Force</span></span>

<span data-ttu-id="77ff4-183">コンピューターの即時シャットダウンを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-183">Forces an immediate shut down of the computer.</span></span>

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

### <span data-ttu-id="77ff4-184">-偽装</span><span class="sxs-lookup"><span data-stu-id="77ff4-184">-Impersonation</span></span>

<span data-ttu-id="77ff4-185">このコマンドレットが WMI を呼び出すときに使用する偽装レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-185">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="77ff4-186">既定値は **Impersonate** です。</span><span class="sxs-lookup"><span data-stu-id="77ff4-186">The default value is **Impersonate**.</span></span>

<span data-ttu-id="77ff4-187">`Stop-Computer` WMI を使用します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-187">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="77ff4-188">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="77ff4-188">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="77ff4-189">**既定** 値: 既定の偽装。</span><span class="sxs-lookup"><span data-stu-id="77ff4-189">**Default** : Default impersonation.</span></span>
- <span data-ttu-id="77ff4-190">**Anonymous** : 呼び出し元の id を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="77ff4-190">**Anonymous** : Hides the identity of the caller.</span></span>
- <span data-ttu-id="77ff4-191">**識別** : オブジェクトが呼び出し元の資格情報を照会できるようにします。</span><span class="sxs-lookup"><span data-stu-id="77ff4-191">**Identify** : Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="77ff4-192">**Impersonate** : オブジェクトが呼び出し元の資格情報を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="77ff4-192">**Impersonate** : Allows objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77ff4-193">-Protocol</span><span class="sxs-lookup"><span data-stu-id="77ff4-193">-Protocol</span></span>

<span data-ttu-id="77ff4-194">コンピューターの再起動にどのプロトコルを使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-194">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="77ff4-195">このパラメーターに指定できる値は、 **WSMan** と **DCOM** です。</span><span class="sxs-lookup"><span data-stu-id="77ff4-195">The acceptable values for this parameter are: **WSMan** and **DCOM**.</span></span> <span data-ttu-id="77ff4-196">既定値は **DCOM** です。</span><span class="sxs-lookup"><span data-stu-id="77ff4-196">The default value is **DCOM**.</span></span>

<span data-ttu-id="77ff4-197">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="77ff4-197">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: DCOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77ff4-198">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="77ff4-198">-ThrottleLimit</span></span>

<span data-ttu-id="77ff4-199">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-199">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="77ff4-200">このパラメーターを省略した場合、または値 0 を入力した場合は、既定値の 32 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="77ff4-200">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="77ff4-201">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="77ff4-201">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="77ff4-202">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="77ff4-202">-WsmanAuthentication</span></span>

<span data-ttu-id="77ff4-203">このコマンドレットで WSMan プロトコルを使用するときに、ユーザー資格情報の認証に使用されるメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-203">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="77ff4-204">既定値は **Default** です。</span><span class="sxs-lookup"><span data-stu-id="77ff4-204">The default value is **Default**.</span></span>

<span data-ttu-id="77ff4-205">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="77ff4-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="77ff4-206">Basic</span><span class="sxs-lookup"><span data-stu-id="77ff4-206">Basic</span></span>
- <span data-ttu-id="77ff4-207">CredSSP</span><span class="sxs-lookup"><span data-stu-id="77ff4-207">CredSSP</span></span>
- <span data-ttu-id="77ff4-208">Default</span><span class="sxs-lookup"><span data-stu-id="77ff4-208">Default</span></span>
- <span data-ttu-id="77ff4-209">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="77ff4-209">Digest</span></span>
- <span data-ttu-id="77ff4-210">Kerberos</span><span class="sxs-lookup"><span data-stu-id="77ff4-210">Kerberos</span></span>
- <span data-ttu-id="77ff4-211">Negotiate</span><span class="sxs-lookup"><span data-stu-id="77ff4-211">Negotiate.</span></span>

<span data-ttu-id="77ff4-212">このパラメーターの値の詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ff4-212">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="77ff4-213">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="77ff4-213">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="77ff4-214">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="77ff4-214">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="77ff4-215">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="77ff4-215">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="77ff4-216">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="77ff4-216">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="77ff4-217">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="77ff4-217">-WhatIf</span></span>

<span data-ttu-id="77ff4-218">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-218">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="77ff4-219">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="77ff4-219">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="77ff4-220">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="77ff4-220">CommonParameters</span></span>

<span data-ttu-id="77ff4-221">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="77ff4-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="77ff4-222">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ff4-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="77ff4-223">入力</span><span class="sxs-lookup"><span data-stu-id="77ff4-223">INPUTS</span></span>

### <span data-ttu-id="77ff4-224">なし</span><span class="sxs-lookup"><span data-stu-id="77ff4-224">None</span></span>

<span data-ttu-id="77ff4-225">このコマンドレットに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="77ff4-225">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="77ff4-226">出力</span><span class="sxs-lookup"><span data-stu-id="77ff4-226">OUTPUTS</span></span>

### <span data-ttu-id="77ff4-227">None または System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="77ff4-227">None or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="77ff4-228">**AsJob** パラメーターを指定した場合、コマンドレットは、-. **Automation. remotingjob** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-228">The cmdlet returns a **System.Management.Automation.RemotingJob** object, if you specify the **AsJob** parameter.</span></span> <span data-ttu-id="77ff4-229">それ以外の場合、出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="77ff4-229">Otherwise, it doesn't generate any output.</span></span>

## <span data-ttu-id="77ff4-230">注</span><span class="sxs-lookup"><span data-stu-id="77ff4-230">NOTES</span></span>

<span data-ttu-id="77ff4-231">このコマンドレットは、 **Win32_OperatingSystem** WMI クラスの **Win32Shutdown** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="77ff4-231">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="77ff4-232">この方法では、コンピューターの再起動に使用するユーザーアカウントに対して、 **Seshutdownprivilege** 特権を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77ff4-232">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="77ff4-233">関連リンク</span><span class="sxs-lookup"><span data-stu-id="77ff4-233">RELATED LINKS</span></span>

[<span data-ttu-id="77ff4-234">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="77ff4-234">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="77ff4-235">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="77ff4-235">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="77ff4-236">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="77ff4-236">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="77ff4-237">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="77ff4-237">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="77ff4-238">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="77ff4-238">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="77ff4-239">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="77ff4-239">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="77ff4-240">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="77ff4-240">Test-Connection</span></span>](Test-Connection.md)

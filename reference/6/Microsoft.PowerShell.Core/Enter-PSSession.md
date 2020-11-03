---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: 3b087eb53fa575b2af7b18ec17823f9197e719d6
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "93218939"
---
# <span data-ttu-id="463e6-103">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="463e6-103">Enter-PSSession</span></span>

## <span data-ttu-id="463e6-104">概要</span><span class="sxs-lookup"><span data-stu-id="463e6-104">SYNOPSIS</span></span>
<span data-ttu-id="463e6-105">リモート コンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="463e6-105">Starts an interactive session with a remote computer.</span></span>

## <span data-ttu-id="463e6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="463e6-106">SYNTAX</span></span>

### <span data-ttu-id="463e6-107">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="463e6-107">ComputerName (Default)</span></span>

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="463e6-108">SSHHost</span><span class="sxs-lookup"><span data-stu-id="463e6-108">SSHHost</span></span>

```
Enter-PSSession [-HostName] <String> [-Port <Int32>] [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [<CommonParameters>]
```

### <span data-ttu-id="463e6-109">Session</span><span class="sxs-lookup"><span data-stu-id="463e6-109">Session</span></span>

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="463e6-110">Uri</span><span class="sxs-lookup"><span data-stu-id="463e6-110">Uri</span></span>

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="463e6-111">InstanceId</span><span class="sxs-lookup"><span data-stu-id="463e6-111">InstanceId</span></span>

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### <span data-ttu-id="463e6-112">Id</span><span class="sxs-lookup"><span data-stu-id="463e6-112">Id</span></span>

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="463e6-113">名前</span><span class="sxs-lookup"><span data-stu-id="463e6-113">Name</span></span>

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### <span data-ttu-id="463e6-114">VMId</span><span class="sxs-lookup"><span data-stu-id="463e6-114">VMId</span></span>

```
Enter-PSSession [-VMId] <Guid> [-Credential] <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### <span data-ttu-id="463e6-115">VMName</span><span class="sxs-lookup"><span data-stu-id="463e6-115">VMName</span></span>

```
Enter-PSSession [-VMName] <String> [-Credential] <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="463e6-116">ContainerId</span><span class="sxs-lookup"><span data-stu-id="463e6-116">ContainerId</span></span>

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## <span data-ttu-id="463e6-117">Description</span><span class="sxs-lookup"><span data-stu-id="463e6-117">DESCRIPTION</span></span>

<span data-ttu-id="463e6-118">`Enter-PSSession`コマンドレットは、1台のリモートコンピューターで対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="463e6-118">The `Enter-PSSession` cmdlet starts an interactive session with a single remote computer.</span></span>
<span data-ttu-id="463e6-119">セッション中、入力したコマンドはリモートコンピューター上で直接入力した場合と同じように、リモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-119">During the session, the commands that you type run on the remote computer, just as if you were typing directly on the remote computer.</span></span> <span data-ttu-id="463e6-120">一度に 1 つのみの対話型セッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="463e6-120">You can have only one interactive session at a time.</span></span>

<span data-ttu-id="463e6-121">通常、 **ComputerName** パラメーターを使用して、リモート コンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-121">Typically, you use the **ComputerName** parameter to specify the name of the remote computer.</span></span>
<span data-ttu-id="463e6-122">ただし、 `New-PSSession` 対話型セッションのコマンドレットを使用して作成したセッションを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="463e6-122">However, you can also use a session that you create by using the `New-PSSession` cmdlet for the interactive session.</span></span> <span data-ttu-id="463e6-123">ただし、 `Disconnect-PSSession` 、 `Connect-PSSession` 、またはコマンドレットを使用して、 `Receive-PSSession` 対話型セッションとの接続を切断したり、再接続したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="463e6-123">However, you cannot use the `Disconnect-PSSession`, `Connect-PSSession`, or `Receive-PSSession` cmdlets to disconnect from or re-connect to an interactive session.</span></span>

<span data-ttu-id="463e6-124">PowerShell 6.0 以降では、Secure Shell (SSH) を使用してリモートコンピューターへの接続を確立できます (SSH がローカルコンピューターで利用可能で、リモートコンピューターに PowerShell SSH エンドポイントが構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="463e6-124">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to a remote computer, if SSH is available on the local computer and the remote computer is configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="463e6-125">SSH ベースの PowerShell リモートセッションの利点は、複数のプラットフォーム (Windows、Linux、macOS) で動作することです。</span><span class="sxs-lookup"><span data-stu-id="463e6-125">The benefit an SSH based PowerShell remote session is that it works across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="463e6-126">SSH ベースのリモート処理では、 **HostName** パラメーターを設定して、リモートコンピューターと関連する接続情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-126">For SSH based remoting you use the **HostName** parameter set to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="463e6-127">PowerShell SSH リモート処理の設定方法の詳細については、「 [Ssh 経由の Powershell リモート](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)処理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-127">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="463e6-128">対話型セッションを終了し、リモートコンピューターから切断するには、 `Exit-PSSession` コマンドレットを使用するか、「」と入力 `exit` します。</span><span class="sxs-lookup"><span data-stu-id="463e6-128">To end the interactive session and disconnect from the remote computer, use the `Exit-PSSession` cmdlet, or type `exit`.</span></span>

## <span data-ttu-id="463e6-129">例</span><span class="sxs-lookup"><span data-stu-id="463e6-129">EXAMPLES</span></span>

### <span data-ttu-id="463e6-130">例 1: 対話型セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="463e6-130">Example 1: Start an interactive session</span></span>

```
PS> Enter-PSSession
[localhost]: PS>
```

<span data-ttu-id="463e6-131">このコマンドは、ローカル コンピューターで対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="463e6-131">This command starts an interactive session on the local computer.</span></span> <span data-ttu-id="463e6-132">コマンド プロンプトが変更され、現在、別のセッションでコマンドを実行していることを示します。</span><span class="sxs-lookup"><span data-stu-id="463e6-132">The command prompt changes to indicate that you are now running commands in a different session.</span></span>

<span data-ttu-id="463e6-133">入力したコマンドは新しいセッションで実行され、結果がテキストとして既定のセッションに返されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-133">The commands that you enter run in the new session, and the results are returned to the default session as text.</span></span>

### <span data-ttu-id="463e6-134">例 2: 対話型セッションを操作する</span><span class="sxs-lookup"><span data-stu-id="463e6-134">Example 2: Work with an interactive session</span></span>

<span data-ttu-id="463e6-135">最初のコマンドは、 `Enter-PSSession` コマンドレットを使用して、リモートコンピューター Server01 との対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="463e6-135">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with Server01, a remote computer.</span></span> <span data-ttu-id="463e6-136">セッションを開始すると、コマンド プロンプトが変更され、コンピューター名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="463e6-136">When the session starts, the command prompt changes to include the computer name.</span></span>

<span data-ttu-id="463e6-137">2 番目のコマンドは、PowerShell プロセスを取得し、Process.txt ファイルに出力をリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="463e6-137">The second command gets the PowerShell process and redirects the output to the Process.txt file.</span></span> <span data-ttu-id="463e6-138">コマンドは、リモート コンピューターに送信され、ファイルはリモート コンピューター上に保存されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-138">The command is submitted to the remote computer, and the file is saved on the remote computer.</span></span>

<span data-ttu-id="463e6-139">3番目のコマンドは、 **Exit** キーワードを使用して対話型セッションを終了し、接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="463e6-139">The third command uses the **Exit** keyword to end the interactive session and close the connection.</span></span>
<span data-ttu-id="463e6-140">4 番目のコマンドは、Process.txt ファイルがリモート コンピューター上にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="463e6-140">The fourth command confirms that the Process.txt file is on the remote computer.</span></span> <span data-ttu-id="463e6-141">`Get-ChildItem`ローカルコンピューター上の ("dir") コマンドがファイルを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="463e6-141">A `Get-ChildItem` ("dir") command on the local computer cannot find the file.</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

<span data-ttu-id="463e6-142">このコマンドは、リモート コンピューターとの対話型セッションで作業する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="463e6-142">This command shows how to work in an interactive session with a remote computer.</span></span>

### <span data-ttu-id="463e6-143">例 3: セッションパラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="463e6-143">Example 3: Use the Session parameter</span></span>

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
[Server01]: PS>
```

<span data-ttu-id="463e6-144">これらのコマンドは、の **Session** パラメーターを使用して、 `Enter-PSSession` 既存の PowerShell セッション ( **PSSession** ) で対話型セッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="463e6-144">These commands use the **Session** parameter of `Enter-PSSession` to run the interactive session in an existing PowerShell session ( **PSSession** ).</span></span>

### <span data-ttu-id="463e6-145">例 4: 対話型セッションを開始し、ポートと資格情報のパラメーターを指定する</span><span class="sxs-lookup"><span data-stu-id="463e6-145">Example 4: Start an interactive session and specify the Port and Credential parameters</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS>
```

<span data-ttu-id="463e6-146">このコマンドは、Server01 コンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="463e6-146">This command starts an interactive session with the Server01 computer.</span></span> <span data-ttu-id="463e6-147">**Port パラメーターを** 使用してポートを指定し、 **Credential** パラメーターを使用して、リモートコンピューターに接続する権限を持つユーザーのアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-147">It uses the **Port** parameter to specify the port and the **Credential** parameter to specify the account of a user who has permission to connect to the remote computer.</span></span>

### <span data-ttu-id="463e6-148">例 5: 対話型セッションを停止する</span><span class="sxs-lookup"><span data-stu-id="463e6-148">Example 5: Stop an interactive session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
[Server01]: PS> Exit-PSSession
PS>
```

<span data-ttu-id="463e6-149">この例は、対話型セッションを開始および停止する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="463e6-149">This example shows how to start and stop an interactive session.</span></span> <span data-ttu-id="463e6-150">最初のコマンドは、 `Enter-PSSession` コマンドレットを使用して、Server01 コンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="463e6-150">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

<span data-ttu-id="463e6-151">2番目のコマンドは、 `Exit-PSSession` コマンドレットを使用してセッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="463e6-151">The second command uses the `Exit-PSSession` cmdlet to end the session.</span></span> <span data-ttu-id="463e6-152">また、 **Exit** キーワードを使用して、対話型セッションを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="463e6-152">You can also use the **Exit** keyword to end the interactive session.</span></span> <span data-ttu-id="463e6-153">`Exit-PSSession` また、 **Exit** は同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="463e6-153">`Exit-PSSession` and **Exit** have the same effect.</span></span>

### <span data-ttu-id="463e6-154">例 6: SSH を使用して対話型セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="463e6-154">Example 6: Start an interactive session using SSH</span></span>

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer01
```

<span data-ttu-id="463e6-155">この例では、Secure Shell (SSH) を使用して対話型セッションを開始する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="463e6-155">This example shows how to start an interactive session using Secure Shell (SSH).</span></span> <span data-ttu-id="463e6-156">SSH がリモートコンピューターでパスワードを要求するように構成されている場合は、パスワードの入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-156">If SSH is configured on the remote computer to prompt for passwords then you will get a password prompt.</span></span>
<span data-ttu-id="463e6-157">それ以外の場合は、SSH キーベースのユーザー認証を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-157">Otherwise you will have to use SSH key based user authentication.</span></span>

### <span data-ttu-id="463e6-158">例 7: SSH を使用して対話型セッションを開始し、ポートとユーザー認証キーを指定する</span><span class="sxs-lookup"><span data-stu-id="463e6-158">Example 7: Start an interactive session using SSH and specify the Port and user authentication key</span></span>

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer02:22 -KeyFilePath c:\<path>\userAKey_rsa
```

<span data-ttu-id="463e6-159">この例では、SSH を使用して対話型セッションを開始する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="463e6-159">This example shows how to start an interactive session using SSH.</span></span> <span data-ttu-id="463e6-160">**Port** パラメーターを使用して、使用するポートを指定し、 **keyfilepath** パラメーターを使用して、リモートコンピューター上でユーザーを認証するために使用する RSA キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-160">It uses the **Port** parameter to specify the port to use and the **KeyFilePath** parameter to specify an RSA key used to authenticate the user on the remote computer.</span></span>

## <span data-ttu-id="463e6-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="463e6-161">PARAMETERS</span></span>

### <span data-ttu-id="463e6-162">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="463e6-162">-AllowRedirection</span></span>

<span data-ttu-id="463e6-163">この接続を代替 Uniform Resource Identifier (URI) にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="463e6-163">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="463e6-164">既定では、リダイレクトは許可されません。</span><span class="sxs-lookup"><span data-stu-id="463e6-164">By default, redirection is not allowed.</span></span>

<span data-ttu-id="463e6-165">**ConnectionURI** パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトするように指示を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="463e6-165">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="463e6-166">既定では、PowerShell は接続をリダイレクトしませんが、このパラメーターを使用して接続をリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="463e6-166">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="463e6-167">また、 **MaximumConnectionRedirectionCount** セッション オプション値を変更することで、接続をリダイレクトする回数を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="463e6-167">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="463e6-168">コマンドレットの **Maximumredirection** パラメーターを使用する `New-PSSessionOption` か、Preference 変数の **MaximumConnectionRedirectionCount** プロパティを設定し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-168">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="463e6-169">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="463e6-169">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-170">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="463e6-170">-ApplicationName</span></span>

<span data-ttu-id="463e6-171">接続 URI のアプリケーション名セグメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-171">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="463e6-172">このパラメーターは、このコマンドの **ConnectionURI** パラメーターを使用しないときに、アプリケーション名を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="463e6-172">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="463e6-173">既定値は、 `$PSSessionApplicationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="463e6-173">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="463e6-174">このユーザー設定変数が定義されていない場合、既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="463e6-174">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="463e6-175">この値はほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="463e6-175">This value is appropriate for most uses.</span></span> <span data-ttu-id="463e6-176">詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-176">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="463e6-177">**WinRM** サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="463e6-177">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="463e6-178">このパラメーターの値は、リモート コンピューター上のリスナーの **URLPrefix** プロパティの値に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-178">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-179">-認証</span><span class="sxs-lookup"><span data-stu-id="463e6-179">-Authentication</span></span>

<span data-ttu-id="463e6-180">ユーザーの資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-180">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="463e6-181">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="463e6-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="463e6-182">Default</span><span class="sxs-lookup"><span data-stu-id="463e6-182">Default</span></span>
- <span data-ttu-id="463e6-183">Basic</span><span class="sxs-lookup"><span data-stu-id="463e6-183">Basic</span></span>
- <span data-ttu-id="463e6-184">Credssp</span><span class="sxs-lookup"><span data-stu-id="463e6-184">Credssp</span></span>
- <span data-ttu-id="463e6-185">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="463e6-185">Digest</span></span>
- <span data-ttu-id="463e6-186">Kerberos</span><span class="sxs-lookup"><span data-stu-id="463e6-186">Kerberos</span></span>
- <span data-ttu-id="463e6-187">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="463e6-187">Negotiate</span></span>
- <span data-ttu-id="463e6-188">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="463e6-188">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="463e6-189">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="463e6-189">The default value is Default.</span></span>

<span data-ttu-id="463e6-190">CredSSP 認証は、windows Vista、Windows Server 2008、およびそれ以降のバージョンの Windows オペレーティングシステムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="463e6-190">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="463e6-191">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-191">For more information about the values of this parameter, see [AuthenticationMechanism Enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="463e6-192">注意: ユーザーの資格情報が認証対象のリモートコンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="463e6-192">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="463e6-193">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="463e6-193">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="463e6-194">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-194">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-195">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="463e6-195">-CertificateThumbprint</span></span>

<span data-ttu-id="463e6-196">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-196">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="463e6-197">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="463e6-197">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="463e6-198">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-198">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="463e6-199">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="463e6-199">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="463e6-200">証明書を取得するに `Get-Item` は、 `Get-ChildItem` PowerShell Cert: ドライブのまたはコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="463e6-200">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-201">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="463e6-201">-ComputerName</span></span>

<span data-ttu-id="463e6-202">コンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-202">Specifies a computer name.</span></span> <span data-ttu-id="463e6-203">このコマンドレットは、指定されたリモートコンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="463e6-203">This cmdlet starts an interactive session with the specified remote computer.</span></span> <span data-ttu-id="463e6-204">コンピューター名を1 つだけ入力します。</span><span class="sxs-lookup"><span data-stu-id="463e6-204">Enter only one computer name.</span></span> <span data-ttu-id="463e6-205">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="463e6-205">The default is the local computer.</span></span>

<span data-ttu-id="463e6-206">コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="463e6-206">Type the NetBIOS name, the IP address, or the fully qualified domain name of the computer.</span></span> <span data-ttu-id="463e6-207">パイプを使用してコンピューター名をにパイプすることもでき `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-207">You can also pipe a computer name to `Enter-PSSession`.</span></span>

<span data-ttu-id="463e6-208">**ComputerName** パラメーターの値に IP アドレスを使用するには、コマンドに **Credential** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-208">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="463e6-209">また、HTTPS トランスポート用にコンピューターを構成するか、リモート コンピューターの IP アドレスをローカル コンピューター上の WinRM TrustedHosts 一覧に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-209">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="463e6-210">TrustedHosts の一覧にコンピューター名を追加する手順については、 [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md)の「信頼されたホストの一覧にコンピューターを追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-210">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="463e6-211">注: windows Vista 以降のバージョンの Windows オペレーティングシステムでは、ローカルコンピューターを **ComputerName** パラメーターの値に含めるには、[管理者として実行] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-211">Note: In Windows Vista and later versions of the Windows operating system, to include the local computer in the value of the **ComputerName** parameter, you must start PowerShell with the Run as administrator option.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-212">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="463e6-212">-ConfigurationName</span></span>

<span data-ttu-id="463e6-213">対話型セッションに使用するセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-213">Specifies the session configuration that is used for the interactive session.</span></span>

<span data-ttu-id="463e6-214">セッション構成の構成名または完全修飾リソース URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="463e6-214">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="463e6-215">構成名だけを指定した場合は、次のスキーマ URI が付加され `http://schemas.microsoft.com/powershell` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-215">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="463e6-216">SSH で使用する場合は、sshd_config で定義されているターゲットで使用するサブシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-216">When used with SSH, this specifies the subsystem to use on the target as defined in sshd_config.</span></span> <span data-ttu-id="463e6-217">SSH の既定値は `powershell` サブシステムです。</span><span class="sxs-lookup"><span data-stu-id="463e6-217">The default value for SSH is the `powershell` subsystem.</span></span>

<span data-ttu-id="463e6-218">セッションのセッション構成は、リモート コンピューター上にあります。</span><span class="sxs-lookup"><span data-stu-id="463e6-218">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="463e6-219">指定したセッション構成がリモート コンピューター上に存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="463e6-219">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="463e6-220">既定値は、 `$PSSessionConfigurationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="463e6-220">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="463e6-221">このユーザー設定変数が設定されていない場合、既定値は Microsoft.PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="463e6-221">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="463e6-222">詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-222">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-223">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="463e6-223">-ConnectionUri</span></span>

<span data-ttu-id="463e6-224">セッションの接続エンドポイントを定義する URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-224">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="463e6-225">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-225">The URI must be fully qualified.</span></span> <span data-ttu-id="463e6-226">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="463e6-226">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="463e6-227">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="463e6-227">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="463e6-228">**ConnectionURI** を指定しなかった場合は、 **UseSSL** 、 **ComputerName** 、 **Port** 、および **ApplicationName** パラメーターを使用して、 **ConnectionURI** 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="463e6-228">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="463e6-229">URI のトランスポート セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="463e6-229">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="463e6-230">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合は、HTTP の場合は80、HTTPS の場合は443という標準ポートを使用してセッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-230">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created by using standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="463e6-231">PowerShell リモート処理に既定のポートを使用するには、HTTP の場合はポート5985、HTTPS の場合は5986を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-231">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="463e6-232">対象のコンピューターが接続を別の URI にリダイレクトする場合、コマンドで **Allowredirection** パラメーターを使用しない限り、PowerShell によってリダイレクトが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-232">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri
Parameter Sets: Uri
Aliases: URI, CU

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-233">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="463e6-233">-ContainerId</span></span>

<span data-ttu-id="463e6-234">コンテナーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-234">Specifies the ID of a container.</span></span>

```yaml
Type: System.String
Parameter Sets: ContainerId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-235">-Credential</span><span class="sxs-lookup"><span data-stu-id="463e6-235">-Credential</span></span>

<span data-ttu-id="463e6-236">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-236">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="463e6-237">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="463e6-237">The default is the current user.</span></span>

<span data-ttu-id="463e6-238">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-238">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="463e6-239">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="463e6-239">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="463e6-240">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-240">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="463e6-241">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-241">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: 1
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-242">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="463e6-242">-EnableNetworkAccess</span></span>

<span data-ttu-id="463e6-243">このコマンドレットが、ループバックセッションに対話型セキュリティトークンを追加することを示します。</span><span class="sxs-lookup"><span data-stu-id="463e6-243">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="463e6-244">対話型トークンを使用すると、他のコンピューターからデータを取得するコマンドをループバック セッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="463e6-244">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="463e6-245">たとえば、リモート コンピューターからローカル コンピューターに XML ファイルをコピーするコマンドをセッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="463e6-245">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="463e6-246">ループバックセッションは、同じコンピューター上で発生して終了する **PSSession** です。</span><span class="sxs-lookup"><span data-stu-id="463e6-246">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="463e6-247">ループバックセッションを作成するには、 **ComputerName** パラメーターを省略するか、値をに設定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-247">To create a loopback session, omit the **ComputerName** parameter or set its value to .</span></span> <span data-ttu-id="463e6-248">(ドット)、localhost、またはローカルコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="463e6-248">(dot), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="463e6-249">既定では、ループバックセッションはネットワークトークンを使用して作成されますが、リモートコンピューターに対して認証を行うための十分なアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-249">By default, loopback sessions are created by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="463e6-250">**EnableNetworkAccess** パラメーターは、ループバック セッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="463e6-250">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="463e6-251">リモートコンピューターでセッションを作成するときに **EnableNetworkAccess** を使用すると、コマンドは成功しますが、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-251">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="463e6-252">**Authentication** パラメーターの **CredSSP** 値を使用して、ループバック セッションでリモート アクセスを許可することもできます。その場合、セッションの資格情報が他のコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-252">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="463e6-253">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="463e6-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-254">-HostName</span><span class="sxs-lookup"><span data-stu-id="463e6-254">-HostName</span></span>

<span data-ttu-id="463e6-255">Secure Shell (SSH) ベースの接続のコンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-255">Specifies a computer name for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="463e6-256">これは **ComputerName** パラメーターと似ていますが、リモートコンピューターへの接続は Windows WinRM ではなく SSH を使用して行われる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="463e6-256">This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span> <span data-ttu-id="463e6-257">このパラメーターでは、という形式を使用して、ホスト名パラメーター値の一部としてユーザー名またはポートを指定 `user@hostname:port` できます。</span><span class="sxs-lookup"><span data-stu-id="463e6-257">This parameter supports specifying the user name and/or port as part of the host name parameter value using the form `user@hostname:port`.</span></span> <span data-ttu-id="463e6-258">ホスト名の一部として指定されたユーザー名またはポートは、 `-UserName` 指定されている場合、パラメーターおよびパラメーターよりも優先され `-Port` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-258">The user name and/or port specified as part of the host name takes precedence over the `-UserName` and `-Port` parameters, if specified.</span></span> <span data-ttu-id="463e6-259">これにより、複数のコンピューター名をこのパラメーターに渡すことができます。ここでは、特定のユーザー名やポートを持つものもあれば、パラメーターとパラメーターからユーザー名やポートを使用するものもあり `-UserName` `-Port` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-259">This allows passing multiple computer names to this parameter where some have specific user names and/or ports, while others use the user name and/or port from the `-UserName` and `-Port` parameters.</span></span>

<span data-ttu-id="463e6-260">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="463e6-260">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-261">-Id</span><span class="sxs-lookup"><span data-stu-id="463e6-261">-Id</span></span>

<span data-ttu-id="463e6-262">既存のセッションの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-262">Specifies the ID of an existing session.</span></span> <span data-ttu-id="463e6-263">`Enter-PSSession` 対話型セッションに対して指定されたセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="463e6-263">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="463e6-264">セッションの ID を検索するには、コマンドレットを使用し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-264">To find the ID of a session, use the `Get-PSSession` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-265">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="463e6-265">-InstanceId</span></span>

<span data-ttu-id="463e6-266">既存のセッションのインスタンス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-266">Specifies the instance ID of an existing session.</span></span> <span data-ttu-id="463e6-267">`Enter-PSSession` 対話型セッションに対して指定されたセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="463e6-267">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="463e6-268">インスタンス ID は GUID です。</span><span class="sxs-lookup"><span data-stu-id="463e6-268">The instance ID is a GUID.</span></span> <span data-ttu-id="463e6-269">セッションのインスタンス ID を検索するには、コマンドレットを使用し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-269">To find the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="463e6-270">**Session** 、 **Name** 、または **ID** パラメーターを使用して、既存のセッションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="463e6-270">You can also use the **Session** , **Name** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="463e6-271">または、 **ComputerName** パラメーターを使用して、一時的なセッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="463e6-271">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

```yaml
Type: System.Guid
Parameter Sets: InstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-272">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="463e6-272">-KeyFilePath</span></span>

<span data-ttu-id="463e6-273">リモートコンピューター上のユーザーを認証するために Secure Shell (SSH) によって使用されるキーファイルパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-273">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="463e6-274">SSH では、基本パスワード認証の代わりに、秘密キーまたは公開キーを使用してユーザー認証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="463e6-274">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="463e6-275">リモートコンピューターがキー認証用に構成されている場合、このパラメーターを使用して、ユーザーを識別するキーを提供できます。</span><span class="sxs-lookup"><span data-stu-id="463e6-275">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="463e6-276">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="463e6-276">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-277">-Name</span><span class="sxs-lookup"><span data-stu-id="463e6-277">-Name</span></span>

<span data-ttu-id="463e6-278">既存のセッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-278">Specifies the friendly name of an existing session.</span></span> <span data-ttu-id="463e6-279">`Enter-PSSession` 対話型セッションに対して指定されたセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="463e6-279">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="463e6-280">指定した名前が複数のセッションと一致する場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="463e6-280">If the name that you specify matches more than one session, the command fails.</span></span> <span data-ttu-id="463e6-281">**Session** 、 **InstanceID** 、または **ID** パラメーターを使用して、既存のセッションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="463e6-281">You can also use the **Session** , **InstanceID** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="463e6-282">または、 **ComputerName** パラメーターを使用して、一時的なセッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="463e6-282">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

<span data-ttu-id="463e6-283">セッションのフレンドリ名を設定するには、コマンドレットの **name** パラメーターを使用し `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-283">To establish a friendly name for a session, use the **Name** parameter of the `New-PSSession` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-284">-Port</span><span class="sxs-lookup"><span data-stu-id="463e6-284">-Port</span></span>

<span data-ttu-id="463e6-285">このコマンドに使用するリモートコンピューターのネットワークポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-285">Specifies the network port on the remote computer that is used for this command.</span></span>

<span data-ttu-id="463e6-286">PowerShell 6.0 では、このパラメーターは、Secure Shell (SSH) 接続をサポートする **HostName** パラメーターセットに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="463e6-286">In PowerShell 6.0 this parameter was inlcuded in the **HostName** parameter set which supports Secure Shell (SSH) connections.</span></span>

<span data-ttu-id="463e6-287">**WinRM (ComputerName パラメーターセット)**</span><span class="sxs-lookup"><span data-stu-id="463e6-287">**WinRM (ComputerName parameter set)**</span></span>

<span data-ttu-id="463e6-288">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="463e6-288">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="463e6-289">既定のポートは5985で、これは HTTP 用の WinRM ポート、および HTTPS 用の WinRM ポートである5986です。</span><span class="sxs-lookup"><span data-stu-id="463e6-289">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="463e6-290">代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-290">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="463e6-291">リスナーを構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="463e6-291">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="463e6-292">必要な場合を除き、 **Port** パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="463e6-292">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="463e6-293">コマンドのポート設定は、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-293">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="463e6-294">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-294">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="463e6-295">**SSH (ホスト名パラメーターセット)**</span><span class="sxs-lookup"><span data-stu-id="463e6-295">**SSH (HostName parameter set)**</span></span>

<span data-ttu-id="463e6-296">リモートコンピューターに接続するには、リモートコンピューターが SSH サービス (SSHD) を使用して構成されており、接続が使用するポートでリッスンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-296">To connect to a remote computer, the remote computer must be configured with the SSH service (SSHD) and must be listening on the port that the connection uses.</span></span> <span data-ttu-id="463e6-297">SSH の既定のポートは22です。</span><span class="sxs-lookup"><span data-stu-id="463e6-297">The default port for SSH is 22.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-298">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="463e6-298">-RunAsAdministrator</span></span>

<span data-ttu-id="463e6-299">**PSSession** が管理者として実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="463e6-299">Indicates that the **PSSession** runs as administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-300">-セッション</span><span class="sxs-lookup"><span data-stu-id="463e6-300">-Session</span></span>

<span data-ttu-id="463e6-301">対話型セッションに使用する PowerShell セッション ( **PSSession** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-301">Specifies a PowerShell session ( **PSSession** ) to use for the interactive session.</span></span> <span data-ttu-id="463e6-302">このパラメーターは、セッション オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="463e6-302">This parameter takes a session object.</span></span> <span data-ttu-id="463e6-303">また、 **Name** 、 **InstanceID** 、または **ID** パラメーターを使用して **PSSession** を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="463e6-303">You can also use the **Name** , **InstanceID** , or **ID** parameters to specify a **PSSession**.</span></span>

<span data-ttu-id="463e6-304">セッションオブジェクトを含む変数、またはやコマンドなどのセッションオブジェクトを作成または取得するコマンドを入力し `New-PSSession` `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-304">Enter a variable that contains a session object or a command that creates or gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="463e6-305">パイプを使用してセッションオブジェクトをにパイプすることもでき `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-305">You can also pipe a session object to `Enter-PSSession`.</span></span> <span data-ttu-id="463e6-306">このパラメーターを使用すると、 **PSSession** を1つだけ送信できます。</span><span class="sxs-lookup"><span data-stu-id="463e6-306">You can submit only one **PSSession** by using this parameter.</span></span> <span data-ttu-id="463e6-307">複数の **PSSession** を含む変数を入力すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="463e6-307">If you enter a variable that contains more than one **PSSession** , the command fails.</span></span>

<span data-ttu-id="463e6-308">`Exit-PSSession`または **EXIT** キーワードを使用すると、対話型セッションは終了しますが、作成した **PSSession** は開いたままになり、使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="463e6-308">When you use `Exit-PSSession` or the **EXIT** keyword, the interactive session ends, but the **PSSession** that you created remains open and available for use.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-309">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="463e6-309">-SessionOption</span></span>

<span data-ttu-id="463e6-310">セッションの詳細オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-310">Sets advanced options for the session.</span></span> <span data-ttu-id="463e6-311">コマンドレットを使用して作成する **sessionoption** オブジェクト、 `New-PSSessionOption` またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="463e6-311">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="463e6-312">オプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-312">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="463e6-313">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="463e6-313">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="463e6-314">セッションオプションの値は、ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-314">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="463e6-315">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="463e6-315">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="463e6-316">既定値を含む、セッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="463e6-316">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="463e6-317">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-317">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="463e6-318">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-318">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-319">-SSHTransport</span><span class="sxs-lookup"><span data-stu-id="463e6-319">-SSHTransport</span></span>

<span data-ttu-id="463e6-320">リモート接続が Secure Shell (SSH) を使用して確立されることを示します。</span><span class="sxs-lookup"><span data-stu-id="463e6-320">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="463e6-321">既定では、PowerShell は Windows WinRM を使用してリモートコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="463e6-321">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="463e6-322">このスイッチは、SSH ベースのリモート接続を確立するために、ホスト名パラメーターセットを使用するように PowerShell を強制します。</span><span class="sxs-lookup"><span data-stu-id="463e6-322">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="463e6-323">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="463e6-323">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-324">-サブシステム</span><span class="sxs-lookup"><span data-stu-id="463e6-324">-Subsystem</span></span>

<span data-ttu-id="463e6-325">新しい **PSSession** に使用する SSH サブシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-325">Specifies the SSH subsystem used for the new **PSSession**.</span></span>

<span data-ttu-id="463e6-326">これは sshd_config で定義されているターゲットで使用するサブシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-326">This specifies the subsystem to use on the target as defined in sshd_config.</span></span> <span data-ttu-id="463e6-327">サブシステムは、定義済みのパラメーターを使用して特定のバージョンの PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="463e6-327">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span> <span data-ttu-id="463e6-328">指定したサブシステムがリモートコンピューターに存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="463e6-328">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="463e6-329">このパラメーターを使用しない場合、既定値は ' powershell ' サブシステムになります。</span><span class="sxs-lookup"><span data-stu-id="463e6-329">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-330">-UserName</span><span class="sxs-lookup"><span data-stu-id="463e6-330">-UserName</span></span>

<span data-ttu-id="463e6-331">リモートコンピューターでセッションを作成するために使用するアカウントのユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-331">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="463e6-332">ユーザー認証方法は、リモートコンピューターで Secure Shell (SSH) がどのように構成されているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="463e6-332">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="463e6-333">SSH が基本パスワード認証用に構成されている場合は、ユーザーのパスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="463e6-333">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="463e6-334">SSH がキーベースのユーザー認証用に構成されている場合、 **Keyfilepath** パラメーターを使用してキーファイルのパスを指定することができます。パスワードプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="463e6-334">If SSH is configured for key based user authentication then a key file path can be provided via the **KeyFilePath** parameter and no password prompt will occur.</span></span> <span data-ttu-id="463e6-335">クライアントユーザーキーファイルが SSH の既知の場所にある場合、キーベースの認証に **Keyfilepath** パラメーターは必要ありません。ユーザー認証は、ユーザー名に基づいて自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-335">Note that if the client user key file is located in an SSH known location then the **KeyFilePath** parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="463e6-336">詳細については、キーベースのユーザー認証に関する SSH ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-336">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="463e6-337">これは必須のパラメーターではありません。</span><span class="sxs-lookup"><span data-stu-id="463e6-337">This is not a required parameter.</span></span> <span data-ttu-id="463e6-338">**UserName** パラメーターが指定されていない場合は、現在のログオンユーザー名が接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-338">If no **UserName** parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="463e6-339">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="463e6-339">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-340">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="463e6-340">-UseSSL</span></span>

<span data-ttu-id="463e6-341">このコマンドレットが、リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="463e6-341">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="463e6-342">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="463e6-342">By default, SSL is not used.</span></span>

<span data-ttu-id="463e6-343">WS-Management は、ネットワーク経由で送信されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="463e6-343">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="463e6-344">**UseSSL** パラメーターは、HTTP 接続ではなく HTTPS 接続を介してデータを送信する追加の保護です。</span><span class="sxs-lookup"><span data-stu-id="463e6-344">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="463e6-345">このパラメーターを使用しても、コマンドに使用されているポートで SSL を使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="463e6-345">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="463e6-346">-VMId</span><span class="sxs-lookup"><span data-stu-id="463e6-346">-VMId</span></span>

<span data-ttu-id="463e6-347">仮想マシンの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-347">Specifies the ID of a virtual machine.</span></span>

```yaml
Type: System.Guid
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-348">-VMName</span><span class="sxs-lookup"><span data-stu-id="463e6-348">-VMName</span></span>

<span data-ttu-id="463e6-349">仮想マシンの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="463e6-349">Specifies the name of a virtual machine.</span></span>

```yaml
Type: System.String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="463e6-350">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="463e6-350">CommonParameters</span></span>

<span data-ttu-id="463e6-351">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="463e6-351">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="463e6-352">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-352">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="463e6-353">入力</span><span class="sxs-lookup"><span data-stu-id="463e6-353">INPUTS</span></span>

### <span data-ttu-id="463e6-354">System.string、システムの管理.... 実行空間</span><span class="sxs-lookup"><span data-stu-id="463e6-354">System.String, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="463e6-355">パイプを使用して、コンピューター名を文字列として、またはセッションオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="463e6-355">You can pipe a computer name, as a string, or a session object to this cmdlet.</span></span>

## <span data-ttu-id="463e6-356">出力</span><span class="sxs-lookup"><span data-stu-id="463e6-356">OUTPUTS</span></span>

### <span data-ttu-id="463e6-357">なし</span><span class="sxs-lookup"><span data-stu-id="463e6-357">None</span></span>

<span data-ttu-id="463e6-358">このコマンドレットは出力を返しません。</span><span class="sxs-lookup"><span data-stu-id="463e6-358">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="463e6-359">注</span><span class="sxs-lookup"><span data-stu-id="463e6-359">NOTES</span></span>

<span data-ttu-id="463e6-360">リモート コンピューターに接続するには、リモート コンピューターの Administrators グループのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="463e6-360">To connect to a remote computer, you must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="463e6-361">ローカルコンピューターで対話型セッションを開始するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="463e6-361">To start an interactive session on the local computer, you must start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="463e6-362">を使用すると `Enter-PSSession` 、リモートコンピューターのユーザープロファイルが対話型セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-362">When you use `Enter-PSSession`, your user profile on the remote computer is used for the interactive session.</span></span> <span data-ttu-id="463e6-363">PowerShell モジュールを追加するコマンドやコマンドプロンプトを変更するコマンドなど、リモートユーザープロファイル内のコマンドは、リモートプロンプトが表示される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-363">The commands in the remote user profile, including commands to add PowerShell modules and to change the command prompt, run before the remote prompt is displayed.</span></span>

<span data-ttu-id="463e6-364">`Enter-PSSession` ローカルコンピューターの UI カルチャ設定を対話型セッションに使用します。</span><span class="sxs-lookup"><span data-stu-id="463e6-364">`Enter-PSSession` uses the UI culture setting on the local computer for the interactive session.</span></span> <span data-ttu-id="463e6-365">ローカル UI カルチャを検索するには、 `$UICulture` 自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="463e6-365">To find the local UI culture, use the `$UICulture` automatic variable.</span></span>

<span data-ttu-id="463e6-366">`Enter-PSSession` には `Get-Command` 、、 `Out-Default` 、およびの各コマンドレットが必要です `Exit-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="463e6-366">`Enter-PSSession` requires the `Get-Command`, `Out-Default`, and `Exit-PSSession` cmdlets.</span></span> <span data-ttu-id="463e6-367">これらのコマンドレットがリモートコンピューターのセッション構成に含まれていない場合、 `Enter-PSSession` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="463e6-367">If these cmdlets are not included in the session configuration on the remote computer, the `Enter-PSSession` commands fails.</span></span>

<span data-ttu-id="463e6-368">とは異なり、 `Invoke-Command` コマンドをリモートコンピューターに送信する前に解析して解釈すると、は、 `Enter-PSSession` コマンドを解釈せずにリモートコンピューターに直接送信します。</span><span class="sxs-lookup"><span data-stu-id="463e6-368">Unlike `Invoke-Command`, which parses and interprets the commands before it sends them to the remote computer, `Enter-PSSession` sends the commands directly to the remote computer without interpretation.</span></span>

<span data-ttu-id="463e6-369">入力するセッションがコマンドの処理中である場合は、PowerShell がコマンドに応答するまでに遅延が発生する可能性があり `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="463e6-369">If the session you want to enter is busy processing a command, there might be a delay before PowerShell responds to the `Enter-PSSession` command.</span></span> <span data-ttu-id="463e6-370">セッションが使用可能になるとすぐに接続されます。</span><span class="sxs-lookup"><span data-stu-id="463e6-370">You are connected as soon as the session is available.</span></span> <span data-ttu-id="463e6-371">コマンドを取り消すには `Enter-PSSession` 、 <kbd>ctrl</kbd> + <kbd>C</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="463e6-371">To cancel the `Enter-PSSession` command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="463e6-372">**ホスト名** パラメーターセットは、PowerShell 6.0 以降に含まれていました。</span><span class="sxs-lookup"><span data-stu-id="463e6-372">The **HostName** parameter set was included starting with PowerShell 6.0.</span></span> <span data-ttu-id="463e6-373">これは、Secure Shell (SSH) に基づいて PowerShell リモート処理を提供するために追加されました。</span><span class="sxs-lookup"><span data-stu-id="463e6-373">It was added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="463e6-374">複数のプラットフォーム (Windows、Linux、macOS) では SSH と PowerShell の両方がサポートされており、powershell リモート処理は PowerShell と SSH がインストールおよび構成されているこれらのプラットフォーム上で機能します。</span><span class="sxs-lookup"><span data-stu-id="463e6-374">Both SSH and PowerShell are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting will work over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="463e6-375">これは、WinRM に基づく以前の Windows のみのリモート処理とは別のものであり、WinRM 固有の機能の多くは適用されません。</span><span class="sxs-lookup"><span data-stu-id="463e6-375">This is separate from the previous Windows only remoting that is based on WinRM and much of the WinRM specific features and limitations do not apply.</span></span> <span data-ttu-id="463e6-376">たとえば、WinRM ベースのクォータ、セッションオプション、カスタムエンドポイントの構成、および切断/再接続機能は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="463e6-376">For example, WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="463e6-377">PowerShell SSH リモート処理の設定方法の詳細については、「 [Ssh 経由の Powershell リモート](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)処理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="463e6-377">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="463e6-378">PowerShell 7.1 より前では、SSH 経由のリモート処理は、次ホップのリモート セッションをサポートしていませんでした。</span><span class="sxs-lookup"><span data-stu-id="463e6-378">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="463e6-379">この機能は、WinRM を使用したセッションに限定されていました。</span><span class="sxs-lookup"><span data-stu-id="463e6-379">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="463e6-380">PowerShell 7.1 を使用すると、任意の対話型リモート セッション内で `Enter-PSSession` と `Enter-PSHostProcess` が機能します。</span><span class="sxs-lookup"><span data-stu-id="463e6-380">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="463e6-381">関連リンク</span><span class="sxs-lookup"><span data-stu-id="463e6-381">RELATED LINKS</span></span>

[<span data-ttu-id="463e6-382">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="463e6-382">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="463e6-383">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="463e6-383">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="463e6-384">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="463e6-384">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="463e6-385">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="463e6-385">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="463e6-386">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="463e6-386">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="463e6-387">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="463e6-387">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="463e6-388">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="463e6-388">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="463e6-389">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="463e6-389">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="463e6-390">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="463e6-390">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="463e6-391">about_Remote</span><span class="sxs-lookup"><span data-stu-id="463e6-391">about_Remote</span></span>](About/about_Remote.md)

---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: 40d9da7d2e7e3233608b893b026c2b89c7155ab1
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "93218936"
---
# <span data-ttu-id="a4ad6-103">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="a4ad6-103">Enter-PSSession</span></span>

## <span data-ttu-id="a4ad6-104">概要</span><span class="sxs-lookup"><span data-stu-id="a4ad6-104">SYNOPSIS</span></span>
<span data-ttu-id="a4ad6-105">リモート コンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-105">Starts an interactive session with a remote computer.</span></span>

## <span data-ttu-id="a4ad6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a4ad6-106">SYNTAX</span></span>

### <span data-ttu-id="a4ad6-107">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="a4ad6-107">ComputerName (Default)</span></span>

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [-Credential <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="a4ad6-108">Session</span><span class="sxs-lookup"><span data-stu-id="a4ad6-108">Session</span></span>

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="a4ad6-109">Uri</span><span class="sxs-lookup"><span data-stu-id="a4ad6-109">Uri</span></span>

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [-Credential <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="a4ad6-110">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a4ad6-110">InstanceId</span></span>

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### <span data-ttu-id="a4ad6-111">Id</span><span class="sxs-lookup"><span data-stu-id="a4ad6-111">Id</span></span>

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="a4ad6-112">名前</span><span class="sxs-lookup"><span data-stu-id="a4ad6-112">Name</span></span>

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### <span data-ttu-id="a4ad6-113">VMId</span><span class="sxs-lookup"><span data-stu-id="a4ad6-113">VMId</span></span>

```
Enter-PSSession [-VMId] <Guid> -Credential <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### <span data-ttu-id="a4ad6-114">VMName</span><span class="sxs-lookup"><span data-stu-id="a4ad6-114">VMName</span></span>

```
Enter-PSSession [-VMName] <String> -Credential <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="a4ad6-115">ContainerId</span><span class="sxs-lookup"><span data-stu-id="a4ad6-115">ContainerId</span></span>

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## <span data-ttu-id="a4ad6-116">Description</span><span class="sxs-lookup"><span data-stu-id="a4ad6-116">DESCRIPTION</span></span>

<span data-ttu-id="a4ad6-117">`Enter-PSSession`コマンドレットは、1台のリモートコンピューターで対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-117">The `Enter-PSSession` cmdlet starts an interactive session with a single remote computer.</span></span> <span data-ttu-id="a4ad6-118">セッション中、入力したコマンドはリモートコンピューター上で直接入力した場合と同じように、リモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-118">During the session, the commands that you type run on the remote computer, just as if you were typing directly on the remote computer.</span></span> <span data-ttu-id="a4ad6-119">一度に 1 つのみの対話型セッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-119">You can have only one interactive session at a time.</span></span>

<span data-ttu-id="a4ad6-120">通常、 **ComputerName** パラメーターを使用して、リモート コンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-120">Typically, you use the **ComputerName** parameter to specify the name of the remote computer.</span></span>
<span data-ttu-id="a4ad6-121">ただし、 `New-PSSession` 対話型セッションのコマンドレットを使用して作成したセッションを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-121">However, you can also use a session that you create by using the `New-PSSession` cmdlet for the interactive session.</span></span> <span data-ttu-id="a4ad6-122">ただし、 `Disconnect-PSSession` 、 `Connect-PSSession` 、またはコマンドレットを使用して、 `Receive-PSSession` 対話型セッションとの接続を切断したり、再接続したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-122">However, you cannot use the `Disconnect-PSSession`, `Connect-PSSession`, or `Receive-PSSession` cmdlets to disconnect from or re-connect to an interactive session.</span></span>

<span data-ttu-id="a4ad6-123">対話型セッションを終了し、リモートコンピューターから切断するには、 `Exit-PSSession` コマンドレットを使用するか、「」と入力 `exit` します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-123">To end the interactive session and disconnect from the remote computer, use the `Exit-PSSession` cmdlet, or type `exit`.</span></span>

## <span data-ttu-id="a4ad6-124">例</span><span class="sxs-lookup"><span data-stu-id="a4ad6-124">EXAMPLES</span></span>

### <span data-ttu-id="a4ad6-125">例 1: 対話型セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="a4ad6-125">Example 1: Start an interactive session</span></span>

```
PS C:\> Enter-PSSession
[localhost]: PS C:\>
```

<span data-ttu-id="a4ad6-126">このコマンドは、ローカル コンピューターで対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-126">This command starts an interactive session on the local computer.</span></span> <span data-ttu-id="a4ad6-127">コマンド プロンプトが変更され、現在、別のセッションでコマンドを実行していることを示します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-127">The command prompt changes to indicate that you are now running commands in a different session.</span></span>

<span data-ttu-id="a4ad6-128">入力したコマンドは新しいセッションで実行され、結果がテキストとして既定のセッションに返されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-128">The commands that you enter run in the new session, and the results are returned to the default session as text.</span></span>

### <span data-ttu-id="a4ad6-129">例 2: 対話型セッションを操作する</span><span class="sxs-lookup"><span data-stu-id="a4ad6-129">Example 2: Work with an interactive session</span></span>

<span data-ttu-id="a4ad6-130">最初のコマンドは、 `Enter-PSSession` コマンドレットを使用して、リモートコンピューター Server01 との対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-130">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with Server01, a remote computer.</span></span> <span data-ttu-id="a4ad6-131">セッションを開始すると、コマンド プロンプトが変更され、コンピューター名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-131">When the session starts, the command prompt changes to include the computer name.</span></span>
<span data-ttu-id="a4ad6-132">2番目のコマンドは、Windows PowerShell プロセスを取得し、Process.txt ファイルに出力をリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-132">The second command gets the Windows PowerShell process and redirects the output to the Process.txt file.</span></span> <span data-ttu-id="a4ad6-133">コマンドは、リモート コンピューターに送信され、ファイルはリモート コンピューター上に保存されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-133">The command is submitted to the remote computer, and the file is saved on the remote computer.</span></span>
<span data-ttu-id="a4ad6-134">3番目のコマンドは、 **Exit** キーワードを使用して対話型セッションを終了し、接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-134">The third command uses the **Exit** keyword to end the interactive session and close the connection.</span></span>
<span data-ttu-id="a4ad6-135">4 番目のコマンドは、Process.txt ファイルがリモート コンピューター上にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-135">The fourth command confirms that the Process.txt file is on the remote computer.</span></span> <span data-ttu-id="a4ad6-136">`Get-ChildItem`ローカルコンピューター上の ("dir") コマンドがファイルを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-136">A `Get-ChildItem` ("dir") command on the local computer cannot find the file.</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS C:\>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

<span data-ttu-id="a4ad6-137">このコマンドは、リモート コンピューターとの対話型セッションで作業する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-137">This command shows how to work in an interactive session with a remote computer.</span></span>

### <span data-ttu-id="a4ad6-138">例 3: セッションパラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="a4ad6-138">Example 3: Use the Session parameter</span></span>

```powershell
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
[Server01]: PS C:\>
```

<span data-ttu-id="a4ad6-139">これらのコマンドは、の **Session** パラメーターを使用して、 `Enter-PSSession` 既存の Windows PowerShell セッション ( **PSSession** ) で対話型セッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-139">These commands use the **Session** parameter of `Enter-PSSession` to run the interactive session in an existing Windows PowerShell session ( **PSSession** ).</span></span>

### <span data-ttu-id="a4ad6-140">例 4: 対話型セッションを開始し、ポートと資格情報のパラメーターを指定する</span><span class="sxs-lookup"><span data-stu-id="a4ad6-140">Example 4: Start an interactive session and specify the Port and Credential parameters</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS C:\>
```

<span data-ttu-id="a4ad6-141">このコマンドは、Server01 コンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-141">This command starts an interactive session with the Server01 computer.</span></span> <span data-ttu-id="a4ad6-142">**Port パラメーターを** 使用してポートを指定し、 **Credential** パラメーターを使用して、リモートコンピューターに接続する権限を持つユーザーのアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-142">It uses the **Port** parameter to specify the port and the **Credential** parameter to specify the account of a user who has permission to connect to the remote computer.</span></span>

### <span data-ttu-id="a4ad6-143">例 5: 対話型セッションを停止する</span><span class="sxs-lookup"><span data-stu-id="a4ad6-143">Example 5: Stop an interactive session</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS C:\> Exit-PSSession
PS C:\>
```

<span data-ttu-id="a4ad6-144">この例は、対話型セッションを開始および停止する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-144">This example shows how to start and stop an interactive session.</span></span> <span data-ttu-id="a4ad6-145">最初のコマンドは、 `Enter-PSSession` コマンドレットを使用して、Server01 コンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-145">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

<span data-ttu-id="a4ad6-146">2番目のコマンドは、 `Exit-PSSession` コマンドレットを使用してセッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-146">The second command uses the `Exit-PSSession` cmdlet to end the session.</span></span> <span data-ttu-id="a4ad6-147">また、 **Exit** キーワードを使用して、対話型セッションを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-147">You can also use the **Exit** keyword to end the interactive session.</span></span> <span data-ttu-id="a4ad6-148">`Exit-PSSession` また、 **Exit** は同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-148">`Exit-PSSession` and **Exit** have the same effect.</span></span>

## <span data-ttu-id="a4ad6-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a4ad6-149">PARAMETERS</span></span>

### <span data-ttu-id="a4ad6-150">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="a4ad6-150">-AllowRedirection</span></span>

<span data-ttu-id="a4ad6-151">この接続を代替 Uniform Resource Identifier (URI) にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-151">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="a4ad6-152">既定では、リダイレクトは許可されません。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-152">By default, redirection is not allowed.</span></span>

<span data-ttu-id="a4ad6-153">**ConnectionURI** パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトするように指示を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-153">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="a4ad6-154">既定では、Windows PowerShell は接続をリダイレクトしませんが、ユーザーはこのパラメーターを使用して接続をリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-154">By default, Windows PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="a4ad6-155">また、 **MaximumConnectionRedirectionCount** セッション オプション値を変更することで、接続をリダイレクトする回数を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-155">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="a4ad6-156">コマンドレットの **Maximumredirection** パラメーターを使用する `New-PSSessionOption` か、Preference 変数の **MaximumConnectionRedirectionCount** プロパティを設定し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-156">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="a4ad6-157">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-157">The default value is 5.</span></span>

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

### <span data-ttu-id="a4ad6-158">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="a4ad6-158">-ApplicationName</span></span>

<span data-ttu-id="a4ad6-159">接続 URI のアプリケーション名セグメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-159">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="a4ad6-160">このパラメーターは、このコマンドの **ConnectionURI** パラメーターを使用しないときに、アプリケーション名を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-160">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="a4ad6-161">既定値は、 `$PSSessionApplicationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-161">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="a4ad6-162">このユーザー設定変数が定義されていない場合、既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-162">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="a4ad6-163">この値はほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-163">This value is appropriate for most uses.</span></span> <span data-ttu-id="a4ad6-164">詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-164">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="a4ad6-165">**WinRM** サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-165">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="a4ad6-166">このパラメーターの値は、リモート コンピューター上のリスナーの **URLPrefix** プロパティの値に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-166">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="a4ad6-167">-認証</span><span class="sxs-lookup"><span data-stu-id="a4ad6-167">-Authentication</span></span>

<span data-ttu-id="a4ad6-168">ユーザーの資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-168">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="a4ad6-169">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-169">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a4ad6-170">Default</span><span class="sxs-lookup"><span data-stu-id="a4ad6-170">Default</span></span>
- <span data-ttu-id="a4ad6-171">Basic</span><span class="sxs-lookup"><span data-stu-id="a4ad6-171">Basic</span></span>
- <span data-ttu-id="a4ad6-172">Credssp</span><span class="sxs-lookup"><span data-stu-id="a4ad6-172">Credssp</span></span>
- <span data-ttu-id="a4ad6-173">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="a4ad6-173">Digest</span></span>
- <span data-ttu-id="a4ad6-174">Kerberos</span><span class="sxs-lookup"><span data-stu-id="a4ad6-174">Kerberos</span></span>
- <span data-ttu-id="a4ad6-175">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="a4ad6-175">Negotiate</span></span>
- <span data-ttu-id="a4ad6-176">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="a4ad6-176">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="a4ad6-177">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-177">The default value is Default.</span></span>

<span data-ttu-id="a4ad6-178">CredSSP 認証は、windows Vista、Windows Server 2008、およびそれ以降のバージョンの Windows オペレーティングシステムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-178">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="a4ad6-179">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-179">For more information about the values of this parameter, see [AuthenticationMechanism Enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="a4ad6-180">注意: ユーザーの資格情報が認証対象のリモートコンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-180">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="a4ad6-181">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-181">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="a4ad6-182">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-182">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="a4ad6-183">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="a4ad6-183">-CertificateThumbprint</span></span>

<span data-ttu-id="a4ad6-184">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-184">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="a4ad6-185">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-185">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="a4ad6-186">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-186">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="a4ad6-187">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-187">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="a4ad6-188">証明書を取得するに `Get-Item` は、 `Get-ChildItem` Windows PowerShell Cert: ドライブのまたはコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-188">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="a4ad6-189">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="a4ad6-189">-ComputerName</span></span>

<span data-ttu-id="a4ad6-190">コンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-190">Specifies a computer name.</span></span> <span data-ttu-id="a4ad6-191">このコマンドレットは、指定されたリモートコンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-191">This cmdlet starts an interactive session with the specified remote computer.</span></span> <span data-ttu-id="a4ad6-192">コンピューター名を1 つだけ入力します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-192">Enter only one computer name.</span></span> <span data-ttu-id="a4ad6-193">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-193">The default is the local computer.</span></span>

<span data-ttu-id="a4ad6-194">コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-194">Type the NetBIOS name, the IP address, or the fully qualified domain name of the computer.</span></span> <span data-ttu-id="a4ad6-195">パイプを使用してコンピューター名をにパイプすることもでき `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-195">You can also pipe a computer name to `Enter-PSSession`.</span></span>

<span data-ttu-id="a4ad6-196">**ComputerName** パラメーターの値に IP アドレスを使用するには、コマンドに **Credential** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-196">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="a4ad6-197">また、HTTPS トランスポート用にコンピューターを構成するか、リモート コンピューターの IP アドレスをローカル コンピューター上の WinRM TrustedHosts 一覧に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-197">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="a4ad6-198">TrustedHosts の一覧にコンピューター名を追加する手順については、 [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md)の「信頼されたホストの一覧にコンピューターを追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-198">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="a4ad6-199">注: windows Vista 以降のバージョンの Windows オペレーティングシステムでは、ローカルコンピューターを **ComputerName** パラメーターの値に含めるには、[管理者として実行] オプションを使用して windows PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-199">Note: In Windows Vista and later versions of the Windows operating system, to include the local computer in the value of the **ComputerName** parameter, you must start Windows PowerShell with the Run as administrator option.</span></span>

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

### <span data-ttu-id="a4ad6-200">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="a4ad6-200">-ConfigurationName</span></span>

<span data-ttu-id="a4ad6-201">対話型セッションに使用するセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-201">Specifies the session configuration that is used for the interactive session.</span></span>

<span data-ttu-id="a4ad6-202">セッション構成の構成名または完全修飾リソース URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-202">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="a4ad6-203">構成名だけを指定した場合は、次のスキーマ URI が付加され `http://schemas.microsoft.com/powershell` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-203">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="a4ad6-204">セッションのセッション構成は、リモート コンピューター上にあります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-204">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="a4ad6-205">指定したセッション構成がリモート コンピューター上に存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-205">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="a4ad6-206">既定値は、 `$PSSessionConfigurationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-206">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="a4ad6-207">このユーザー設定変数が設定されていない場合、既定値は Microsoft.PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-207">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="a4ad6-208">詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-208">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

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

### <span data-ttu-id="a4ad6-209">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="a4ad6-209">-ConnectionUri</span></span>

<span data-ttu-id="a4ad6-210">セッションの接続エンドポイントを定義する URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-210">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="a4ad6-211">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-211">The URI must be fully qualified.</span></span> <span data-ttu-id="a4ad6-212">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-212">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="a4ad6-213">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-213">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="a4ad6-214">**ConnectionURI** を指定しなかった場合は、 **UseSSL** 、 **ComputerName** 、 **Port** 、および **ApplicationName** パラメーターを使用して、 **ConnectionURI** 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-214">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="a4ad6-215">URI のトランスポート セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-215">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="a4ad6-216">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合は、HTTP の場合は80、HTTPS の場合は443という標準ポートを使用してセッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-216">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created by using standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="a4ad6-217">Windows PowerShell リモート処理用の既定のポートを使用するには、HTTP の場合は 5985、HTTPS の場合は 5986 を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-217">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="a4ad6-218">送信先コンピューターが別の URI に接続をリダイレクトする場合、コマンドで **AllowRedirection** パラメーターを使用しない限り、Windows PowerShell はリダイレクションを阻止します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-218">If the destination computer redirects the connection to a different URI, Windows PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

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

### <span data-ttu-id="a4ad6-219">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="a4ad6-219">-ContainerId</span></span>

<span data-ttu-id="a4ad6-220">コンテナーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-220">Specifies the ID of a container.</span></span>

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

### <span data-ttu-id="a4ad6-221">-Credential</span><span class="sxs-lookup"><span data-stu-id="a4ad6-221">-Credential</span></span>

<span data-ttu-id="a4ad6-222">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-222">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="a4ad6-223">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-223">The default is the current user.</span></span>

<span data-ttu-id="a4ad6-224">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-224">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="a4ad6-225">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-225">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="a4ad6-226">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-226">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="a4ad6-227">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-227">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="a4ad6-228">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="a4ad6-228">-EnableNetworkAccess</span></span>

<span data-ttu-id="a4ad6-229">このコマンドレットが、ループバックセッションに対話型セキュリティトークンを追加することを示します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-229">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="a4ad6-230">対話型トークンを使用すると、他のコンピューターからデータを取得するコマンドをループバック セッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-230">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="a4ad6-231">たとえば、リモート コンピューターからローカル コンピューターに XML ファイルをコピーするコマンドをセッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-231">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="a4ad6-232">ループバックセッションは、同じコンピューター上で発生して終了する **PSSession** です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-232">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="a4ad6-233">ループバックセッションを作成するには、 **ComputerName** パラメーターを省略するか、値をに設定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-233">To create a loopback session, omit the **ComputerName** parameter or set its value to .</span></span> <span data-ttu-id="a4ad6-234">(ドット)、localhost、またはローカルコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-234">(dot), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="a4ad6-235">既定では、ループバックセッションはネットワークトークンを使用して作成されますが、リモートコンピューターに対して認証を行うための十分なアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-235">By default, loopback sessions are created by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="a4ad6-236">**EnableNetworkAccess** パラメーターは、ループバック セッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-236">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="a4ad6-237">リモートコンピューターでセッションを作成するときに **EnableNetworkAccess** を使用すると、コマンドは成功しますが、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-237">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="a4ad6-238">**Authentication** パラメーターの **CredSSP** 値を使用して、ループバック セッションでリモート アクセスを許可することもできます。その場合、セッションの資格情報が他のコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-238">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="a4ad6-239">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a4ad6-240">-Id</span><span class="sxs-lookup"><span data-stu-id="a4ad6-240">-Id</span></span>

<span data-ttu-id="a4ad6-241">既存のセッションの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-241">Specifies the ID of an existing session.</span></span> <span data-ttu-id="a4ad6-242">`Enter-PSSession` 対話型セッションに対して指定されたセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-242">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="a4ad6-243">セッションの ID を検索するには、コマンドレットを使用し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-243">To find the ID of a session, use the `Get-PSSession` cmdlet.</span></span>

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

### <span data-ttu-id="a4ad6-244">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="a4ad6-244">-InstanceId</span></span>

<span data-ttu-id="a4ad6-245">既存のセッションのインスタンス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-245">Specifies the instance ID of an existing session.</span></span> <span data-ttu-id="a4ad6-246">`Enter-PSSession` 対話型セッションに対して指定されたセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-246">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="a4ad6-247">インスタンス ID は GUID です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-247">The instance ID is a GUID.</span></span> <span data-ttu-id="a4ad6-248">セッションのインスタンス ID を検索するには、コマンドレットを使用し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-248">To find the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="a4ad6-249">**Session** 、 **Name** 、または **ID** パラメーターを使用して、既存のセッションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-249">You can also use the **Session** , **Name** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="a4ad6-250">または、 **ComputerName** パラメーターを使用して、一時的なセッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-250">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

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

### <span data-ttu-id="a4ad6-251">-Name</span><span class="sxs-lookup"><span data-stu-id="a4ad6-251">-Name</span></span>

<span data-ttu-id="a4ad6-252">既存のセッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-252">Specifies the friendly name of an existing session.</span></span> <span data-ttu-id="a4ad6-253">`Enter-PSSession` 対話型セッションに対して指定されたセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-253">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="a4ad6-254">指定した名前が複数のセッションと一致する場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-254">If the name that you specify matches more than one session, the command fails.</span></span> <span data-ttu-id="a4ad6-255">**Session** 、 **InstanceID** 、または **ID** パラメーターを使用して、既存のセッションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-255">You can also use the **Session** , **InstanceID** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="a4ad6-256">または、 **ComputerName** パラメーターを使用して、一時的なセッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-256">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

<span data-ttu-id="a4ad6-257">セッションのフレンドリ名を設定するには、コマンドレットの **name** パラメーターを使用し `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-257">To establish a friendly name for a session, use the **Name** parameter of the `New-PSSession` cmdlet.</span></span>

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

### <span data-ttu-id="a4ad6-258">-Port</span><span class="sxs-lookup"><span data-stu-id="a4ad6-258">-Port</span></span>

<span data-ttu-id="a4ad6-259">このコマンドに使用するリモートコンピューターのネットワークポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-259">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="a4ad6-260">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-260">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="a4ad6-261">既定のポートは5985で、これは HTTP 用の WinRM ポート、および HTTPS 用の WinRM ポートである5986です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-261">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="a4ad6-262">代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-262">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="a4ad6-263">リスナーを構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-263">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="a4ad6-264">必要な場合を除き、 **Port** パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-264">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="a4ad6-265">コマンドのポート設定は、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-265">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="a4ad6-266">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-266">An alternate port setting might prevent the command from running on all computers.</span></span>

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

### <span data-ttu-id="a4ad6-267">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a4ad6-267">-RunAsAdministrator</span></span>

<span data-ttu-id="a4ad6-268">**PSSession** が管理者として実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-268">Indicates that the **PSSession** runs as administrator.</span></span>

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

### <span data-ttu-id="a4ad6-269">-セッション</span><span class="sxs-lookup"><span data-stu-id="a4ad6-269">-Session</span></span>

<span data-ttu-id="a4ad6-270">対話型セッションに使用する Windows PowerShell セッション ( **PSSession** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-270">Specifies a Windows PowerShell session ( **PSSession** ) to use for the interactive session.</span></span> <span data-ttu-id="a4ad6-271">このパラメーターは、セッション オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-271">This parameter takes a session object.</span></span> <span data-ttu-id="a4ad6-272">また、 **Name** 、 **InstanceID** 、または **ID** パラメーターを使用して **PSSession** を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-272">You can also use the **Name** , **InstanceID** , or **ID** parameters to specify a **PSSession**.</span></span>

<span data-ttu-id="a4ad6-273">セッションオブジェクトを含む変数、またはやコマンドなどのセッションオブジェクトを作成または取得するコマンドを入力し `New-PSSession` `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-273">Enter a variable that contains a session object or a command that creates or gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="a4ad6-274">パイプを使用してセッションオブジェクトをにパイプすることもでき `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-274">You can also pipe a session object to `Enter-PSSession`.</span></span> <span data-ttu-id="a4ad6-275">このパラメーターを使用すると、 **PSSession** を1つだけ送信できます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-275">You can submit only one **PSSession** by using this parameter.</span></span> <span data-ttu-id="a4ad6-276">複数の **PSSession** を含む変数を入力すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-276">If you enter a variable that contains more than one **PSSession** , the command fails.</span></span>

<span data-ttu-id="a4ad6-277">`Exit-PSSession`または **EXIT** キーワードを使用すると、対話型セッションは終了しますが、作成した **PSSession** は開いたままになり、使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-277">When you use `Exit-PSSession` or the **EXIT** keyword, the interactive session ends, but the **PSSession** that you created remains open and available for use.</span></span>

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

### <span data-ttu-id="a4ad6-278">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="a4ad6-278">-SessionOption</span></span>

<span data-ttu-id="a4ad6-279">セッションの詳細オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-279">Sets advanced options for the session.</span></span> <span data-ttu-id="a4ad6-280">コマンドレットを使用して作成する **sessionoption** オブジェクト、 `New-PSSessionOption` またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-280">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="a4ad6-281">オプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-281">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="a4ad6-282">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-282">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="a4ad6-283">セッションオプションの値は、ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-283">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="a4ad6-284">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-284">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="a4ad6-285">既定値を含む、セッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-285">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="a4ad6-286">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-286">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="a4ad6-287">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-287">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="a4ad6-288">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="a4ad6-288">-UseSSL</span></span>

<span data-ttu-id="a4ad6-289">このコマンドレットが、リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-289">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="a4ad6-290">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-290">By default, SSL is not used.</span></span>

<span data-ttu-id="a4ad6-291">WS-Management は、ネットワークを介して転送されるすべての Windows PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-291">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="a4ad6-292">**UseSSL** パラメーターは、HTTP 接続ではなく HTTPS 接続を介してデータを送信する追加の保護です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-292">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="a4ad6-293">このパラメーターを使用しても、コマンドに使用されているポートで SSL を使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-293">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="a4ad6-294">-VMId</span><span class="sxs-lookup"><span data-stu-id="a4ad6-294">-VMId</span></span>

<span data-ttu-id="a4ad6-295">仮想マシンの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-295">Specifies the ID of a virtual machine.</span></span>

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

### <span data-ttu-id="a4ad6-296">-VMName</span><span class="sxs-lookup"><span data-stu-id="a4ad6-296">-VMName</span></span>

<span data-ttu-id="a4ad6-297">仮想マシンの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-297">Specifies the name of a virtual machine.</span></span>

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

### <span data-ttu-id="a4ad6-298">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4ad6-298">CommonParameters</span></span>

<span data-ttu-id="a4ad6-299">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-299">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a4ad6-300">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-300">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a4ad6-301">入力</span><span class="sxs-lookup"><span data-stu-id="a4ad6-301">INPUTS</span></span>

### <span data-ttu-id="a4ad6-302">System.string、システムの管理.... 実行空間</span><span class="sxs-lookup"><span data-stu-id="a4ad6-302">System.String, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="a4ad6-303">パイプを使用して、コンピューター名を文字列として、またはセッションオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-303">You can pipe a computer name, as a string, or a session object to this cmdlet.</span></span>

## <span data-ttu-id="a4ad6-304">出力</span><span class="sxs-lookup"><span data-stu-id="a4ad6-304">OUTPUTS</span></span>

### <span data-ttu-id="a4ad6-305">なし</span><span class="sxs-lookup"><span data-stu-id="a4ad6-305">None</span></span>

<span data-ttu-id="a4ad6-306">このコマンドレットは出力を返しません。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-306">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="a4ad6-307">注</span><span class="sxs-lookup"><span data-stu-id="a4ad6-307">NOTES</span></span>

<span data-ttu-id="a4ad6-308">リモート コンピューターに接続するには、リモート コンピューターの Administrators グループのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-308">To connect to a remote computer, you must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="a4ad6-309">ローカルコンピューターで対話型セッションを開始するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-309">To start an interactive session on the local computer, you must start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="a4ad6-310">を使用すると `Enter-PSSession` 、リモートコンピューターのユーザープロファイルが対話型セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-310">When you use `Enter-PSSession`, your user profile on the remote computer is used for the interactive session.</span></span> <span data-ttu-id="a4ad6-311">PowerShell モジュールを追加するコマンドやコマンドプロンプトを変更するコマンドなど、リモートユーザープロファイル内のコマンドは、リモートプロンプトが表示される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-311">The commands in the remote user profile, including commands to add PowerShell modules and to change the command prompt, run before the remote prompt is displayed.</span></span>

<span data-ttu-id="a4ad6-312">`Enter-PSSession` ローカルコンピューターの UI カルチャ設定を対話型セッションに使用します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-312">`Enter-PSSession` uses the UI culture setting on the local computer for the interactive session.</span></span> <span data-ttu-id="a4ad6-313">ローカル UI カルチャを検索するには、 `$UICulture` 自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-313">To find the local UI culture, use the `$UICulture` automatic variable.</span></span>

<span data-ttu-id="a4ad6-314">`Enter-PSSession` には `Get-Command` 、、 `Out-Default` 、およびの各コマンドレットが必要です `Exit-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-314">`Enter-PSSession` requires the `Get-Command`, `Out-Default`, and `Exit-PSSession` cmdlets.</span></span> <span data-ttu-id="a4ad6-315">これらのコマンドレットがリモートコンピューターのセッション構成に含まれていない場合、 `Enter-PSSession` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-315">If these cmdlets are not included in the session configuration on the remote computer, the `Enter-PSSession` commands fails.</span></span>

<span data-ttu-id="a4ad6-316">とは異なり、 `Invoke-Command` コマンドをリモートコンピューターに送信する前に解析して解釈すると、は、 `Enter-PSSession` コマンドを解釈せずにリモートコンピューターに直接送信します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-316">Unlike `Invoke-Command`, which parses and interprets the commands before it sends them to the remote computer, `Enter-PSSession` sends the commands directly to the remote computer without interpretation.</span></span>

<span data-ttu-id="a4ad6-317">入力するセッションがコマンドの処理中である場合は、PowerShell がコマンドに応答するまでに遅延が発生する可能性があり `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-317">If the session you want to enter is busy processing a command, there might be a delay before PowerShell responds to the `Enter-PSSession` command.</span></span> <span data-ttu-id="a4ad6-318">セッションが使用可能になるとすぐに接続されます。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-318">You are connected as soon as the session is available.</span></span> <span data-ttu-id="a4ad6-319">コマンドを取り消すには `Enter-PSSession` 、 <kbd>ctrl</kbd> + <kbd>C</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a4ad6-319">To cancel the `Enter-PSSession` command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

## <span data-ttu-id="a4ad6-320">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a4ad6-320">RELATED LINKS</span></span>

[<span data-ttu-id="a4ad6-321">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="a4ad6-321">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="a4ad6-322">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="a4ad6-322">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="a4ad6-323">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a4ad6-323">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="a4ad6-324">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="a4ad6-324">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="a4ad6-325">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="a4ad6-325">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="a4ad6-326">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="a4ad6-326">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="a4ad6-327">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="a4ad6-327">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="a4ad6-328">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="a4ad6-328">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="a4ad6-329">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="a4ad6-329">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="a4ad6-330">about_Remote</span><span class="sxs-lookup"><span data-stu-id="a4ad6-330">about_Remote</span></span>](About/about_Remote.md)

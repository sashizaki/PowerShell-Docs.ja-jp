---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: a6a0f0f4778cad3b3f55d408b67f456e3152c83e
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218483"
---
# <span data-ttu-id="387bc-103">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="387bc-103">Connect-PSSession</span></span>

## <span data-ttu-id="387bc-104">概要</span><span class="sxs-lookup"><span data-stu-id="387bc-104">SYNOPSIS</span></span>
<span data-ttu-id="387bc-105">切断されたセッションに再接続します。</span><span class="sxs-lookup"><span data-stu-id="387bc-105">Reconnects to disconnected sessions.</span></span>

## <span data-ttu-id="387bc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="387bc-106">SYNTAX</span></span>

### <span data-ttu-id="387bc-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="387bc-107">Name (Default)</span></span>

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="387bc-108">Session</span><span class="sxs-lookup"><span data-stu-id="387bc-108">Session</span></span>

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="387bc-109">コンピューター名 Guid</span><span class="sxs-lookup"><span data-stu-id="387bc-109">ComputerNameGuid</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="387bc-110">[ComputerName]</span><span class="sxs-lookup"><span data-stu-id="387bc-110">ComputerName</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="387bc-111">ConnectionUriGuid</span><span class="sxs-lookup"><span data-stu-id="387bc-111">ConnectionUriGuid</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="387bc-112">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="387bc-112">ConnectionUri</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="387bc-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="387bc-113">InstanceId</span></span>

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="387bc-114">Id</span><span class="sxs-lookup"><span data-stu-id="387bc-114">Id</span></span>

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="387bc-115">Description</span><span class="sxs-lookup"><span data-stu-id="387bc-115">DESCRIPTION</span></span>

<span data-ttu-id="387bc-116">接続が切断されたユーザー管理の PowerShell **セッション (** **PSSession** ) に再接続します。</span><span class="sxs-lookup"><span data-stu-id="387bc-116">The **Connect-PSSession** cmdlet reconnects to user-managed PowerShell sessions ( **PSSessions** ) that were disconnected.</span></span>
<span data-ttu-id="387bc-117">これは意図的に切断されたセッションで機能します。たとえば、Disconnect-PSSession コマンドレットや、Invoke-Command コマンドレットの *Indisconnectedsession* パラメーターを使用したり、一時的なネットワークの停止などによって誤って切断されたセッションを使用したりします。</span><span class="sxs-lookup"><span data-stu-id="387bc-117">It works on sessions that are disconnected intentionally, such as by using the Disconnect-PSSession cmdlet or the *InDisconnectedSession* parameter of the Invoke-Command cmdlet, and those that were disconnected unintentionally, such as by a temporary network outage.</span></span>

<span data-ttu-id="387bc-118">**接続 PSSession** は、同じユーザーによって開始された切断されたセッションに接続できます。</span><span class="sxs-lookup"><span data-stu-id="387bc-118">**Connect-PSSession** can connect to any disconnected session that was started by the same user.</span></span>
<span data-ttu-id="387bc-119">これには、他のコンピューター上の他のセッションによって開始または切断されたものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="387bc-119">These include those that were started by or disconnected from other sessions on other computers.</span></span>

<span data-ttu-id="387bc-120">ただし、 **接続が** 切断されているか閉じられているセッション、または Enter-PSSession コマンドレットを使用して開始された対話型セッションに接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="387bc-120">However, **Connect-PSSession** cannot connect to broken or closed sessions, or interactive sessions started by using the Enter-PSSession cmdlet.</span></span>
<span data-ttu-id="387bc-121">このほか、別のユーザーが開始したセッションには接続できません。ただし、そのセッションを作成したユーザーの資格情報がある場合には、このコマンドレットを使用した再接続が可能です。</span><span class="sxs-lookup"><span data-stu-id="387bc-121">Also you cannot connect sessions to sessions started by other users, unless you can provide the credentials of the user who created the session.</span></span>

<span data-ttu-id="387bc-122">切断されたセッションの機能の詳細については、「about_Remote_Disconnected_Sessions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-122">For more information about the Disconnected Sessions feature, see about_Remote_Disconnected_Sessions.</span></span>

<span data-ttu-id="387bc-123">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="387bc-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="387bc-124">例</span><span class="sxs-lookup"><span data-stu-id="387bc-124">EXAMPLES</span></span>

### <span data-ttu-id="387bc-125">例 1: セッションに再接続する</span><span class="sxs-lookup"><span data-stu-id="387bc-125">Example 1: Reconnect to a session</span></span>

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

<span data-ttu-id="387bc-126">このコマンドは、Server01 コンピューターの ITTask セッションに再接続するものです。</span><span class="sxs-lookup"><span data-stu-id="387bc-126">This command reconnects to the ITTask session on the Server01 computer.</span></span>

<span data-ttu-id="387bc-127">出力は、コマンドが成功したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="387bc-127">The output shows that the command was successful.</span></span>
<span data-ttu-id="387bc-128">セッションの **状態** が開かれ、 **可用性** が利用可能になっています。これは、セッションでコマンドを実行できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="387bc-128">The **State** of the session is Opened and the **Availability** is Available, which indicates that you can run commands in the session.</span></span>

### <span data-ttu-id="387bc-129">例 2: 切断と再接続の影響</span><span class="sxs-lookup"><span data-stu-id="387bc-129">Example 2: Effect of disconnecting and reconnecting</span></span>

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

<span data-ttu-id="387bc-130">この例では、セッションを切断した後で、改めて同じセッションに接続する効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="387bc-130">This example shows the effect of disconnecting and then reconnecting to a session.</span></span>

<span data-ttu-id="387bc-131">最初のコマンドは、Get-PSSession コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="387bc-131">The first command uses the Get-PSSession cmdlet.</span></span>
<span data-ttu-id="387bc-132">*ComputerName* パラメーターを指定しなかった場合には、コマンドは現在のセッションで作成されたセッションのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="387bc-132">Without the *ComputerName* parameter, the command gets only sessions that were created in the current session.</span></span>

<span data-ttu-id="387bc-133">出力は、ローカル コンピューターの Backups セッションを取得したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="387bc-133">The output shows that the command gets the Backups session on the local computer.</span></span>
<span data-ttu-id="387bc-134">セッションの **状態** が開かれ、 **可用性** が使用可能になっています。</span><span class="sxs-lookup"><span data-stu-id="387bc-134">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="387bc-135">2番目のコマンドは、 **Get PSSession** コマンドレットを使用して、現在のセッションで作成された **pssession** オブジェクトを取得します。また、 **pssession** コマンドレットを使用してセッションを切断します。</span><span class="sxs-lookup"><span data-stu-id="387bc-135">The second command uses the **Get-PSSession** cmdlet to get the **PSSession** objects that were created in the current session and the **Disconnect-PSSession** cmdlet to disconnect the sessions.</span></span>
<span data-ttu-id="387bc-136">出力は、Backups セッションが切断されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="387bc-136">The output shows that the Backups session was disconnected.</span></span>
<span data-ttu-id="387bc-137">セッションの **状態** は Disconnected であり、 **Availability** は None です。</span><span class="sxs-lookup"><span data-stu-id="387bc-137">The **State** of the session is Disconnected and the **Availability** is None.</span></span>

<span data-ttu-id="387bc-138">3番目のコマンドは、 **Get PSSession** コマンドレットを使用して、現在のセッションで作成された **PSSession** オブジェクトを取得し、 **接続 pssession** コマンドレットを使用してセッションを再接続します。</span><span class="sxs-lookup"><span data-stu-id="387bc-138">The third command uses the **Get-PSSession** cmdlet to get the **PSSession** objects that were created in the current session and the **Connect-PSSession** cmdlet to reconnect the sessions.</span></span>
<span data-ttu-id="387bc-139">出力は、Backups セッションに再接続したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="387bc-139">The output shows that the Backups session was reconnected.</span></span>
<span data-ttu-id="387bc-140">セッションの **状態** が開かれ、 **可用性** が使用可能になっています。</span><span class="sxs-lookup"><span data-stu-id="387bc-140">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="387bc-141">切断されていないセッションで **接続の PSSession** コマンドレットを使用すると、このコマンドはセッションに影響を与えず、エラーも生成されません。</span><span class="sxs-lookup"><span data-stu-id="387bc-141">If you use the **Connect-PSSession** cmdlet on a session that is not disconnected, the command does not affect the session and it does not generate any errors.</span></span>

### <span data-ttu-id="387bc-142">例 3: エンタープライズシナリオにおける一連のコマンド</span><span class="sxs-lookup"><span data-stu-id="387bc-142">Example 3: Series of commands in an enterprise scenario</span></span>

```
The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the **New-PSSession** cmdlet to create the ITTask session on the Server01 remote computer. The command uses the *ConfigurationName* parameter to specify the ITTasks session configuration. The command saves the sessions in the $s variable.
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks

 The second command **Invoke-Command** cmdlet to start a background job in the session in the $s variable. It uses the *FilePath* parameter to run the script in the background job.
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

The third command uses the Disconnect-PSSession cmdlet to disconnect from the session in the $s variable. The command uses the *OutputBufferingMode* parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session. It uses the *IdleTimeoutSec* parameter to extend the session time-out to 15 hours.When the command is completed, the administrator locks her computer and goes home for the evening.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts PowerShell. The fourth command uses the Get-PSSession cmdlet to get the sessions on the Server01 computer. The command finds the ITTask session.The fifth command uses the **Connect-PSSession** cmdlet to connect to the ITTask session. The command saves the session in the $s variable.
PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

The sixth command uses the **Invoke-Command** cmdlet to run a Get-Job command in the session in the $s variable. The output shows that the job finished successfully.The seventh command uses the **Invoke-Command** cmdlet to run a Receive-Job command in the session in the $s variable in the session. The command saves the results in the $BackupSpecs variable.The eighth command uses the **Invoke-Command** cmdlet to runs another script in the session. The command uses the value of the $BackupSpecs variable in the session as input to the script.


PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

The ninth command disconnects from the session in the $s variable.The administrator closes PowerShell and closes the computer. She can reconnect to the session on the next day and check the script status from her work computer.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

<span data-ttu-id="387bc-143">この一連のコマンドは、エンタープライズで **Connect-PSSession** コマンドレットを使用する方法の一例を示したものです。</span><span class="sxs-lookup"><span data-stu-id="387bc-143">This series of commands shows how the **Connect-PSSession** cmdlet might be used in an enterprise scenario.</span></span>
<span data-ttu-id="387bc-144">この例では、システム管理者がリモート コンピューター上のセッションで、実行時間の長いジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="387bc-144">In this case, a system administrator starts a long-running job in a session on a remote computer.</span></span>
<span data-ttu-id="387bc-145">管理者はジョブを開始した後、セッションを切断し、帰宅します。</span><span class="sxs-lookup"><span data-stu-id="387bc-145">After starting the job, the administrator disconnects from the session and goes home.</span></span>
<span data-ttu-id="387bc-146">その後、管理者が自宅のコンピューターにログオンし、ジョブが完了するまで実行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="387bc-146">Later that evening, the administrator logs on to her home computer and verifies that the job ran until it is completed.</span></span>

## <span data-ttu-id="387bc-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="387bc-147">PARAMETERS</span></span>

### <span data-ttu-id="387bc-148">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="387bc-148">-AllowRedirection</span></span>

<span data-ttu-id="387bc-149">このコマンドレットがこの接続を代替 URI にリダイレクトできることを示します。</span><span class="sxs-lookup"><span data-stu-id="387bc-149">Indicates that this cmdlet allows redirection of this connection to an alternate URI.</span></span>

<span data-ttu-id="387bc-150">*ConnectionURI* パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトするように指示を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="387bc-150">When you use the *ConnectionURI* parameter, the remote destination can return an instruction to redirect to a different URI.</span></span>
<span data-ttu-id="387bc-151">既定では、PowerShell は接続をリダイレクトしませんが、このパラメーターを使用して接続をリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="387bc-151">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="387bc-152">また、 **MaximumConnectionRedirectionCount** セッション オプション値を変更することで、接続をリダイレクトする回数を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="387bc-152">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span>
<span data-ttu-id="387bc-153">New-PSSessionOption コマンドレットの *Maximumredirection* パラメーターを使用するか、 **$PSSessionOption** ユーザー設定変数の **MaximumConnectionRedirectionCount** プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-153">Use the *MaximumRedirection* parameter of the New-PSSessionOption cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span>
<span data-ttu-id="387bc-154">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="387bc-154">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-155">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="387bc-155">-ApplicationName</span></span>

<span data-ttu-id="387bc-156">アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-156">Specifies the name of an application.</span></span>
<span data-ttu-id="387bc-157">このコマンドレットは、指定されたアプリケーションを使用するセッションにのみ接続します。</span><span class="sxs-lookup"><span data-stu-id="387bc-157">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="387bc-158">接続 URI のアプリケーション名セグメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="387bc-158">Enter the application name segment of the connection URI.</span></span>
<span data-ttu-id="387bc-159">たとえば、次の接続 URI では、アプリケーション名は WSMan: `http://localhost:5985/WSMAN` です。</span><span class="sxs-lookup"><span data-stu-id="387bc-159">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span>
<span data-ttu-id="387bc-160">セッションのアプリケーション名は、セッションの **Runspace.ConnectionInfo.AppName** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="387bc-160">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="387bc-161">このパラメーター値は、セッションを選択してフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-161">The value of this parameter is used to select and filter sessions.</span></span>
<span data-ttu-id="387bc-162">セッションが使用するアプリケーションが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="387bc-162">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-163">-認証</span><span class="sxs-lookup"><span data-stu-id="387bc-163">-Authentication</span></span>

<span data-ttu-id="387bc-164">切断されたセッションに再接続するためにコマンドでユーザー資格情報を認証するために使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-164">Specifies the mechanism that is used to authenticate user credentials in the command to reconnect to the disconnected session.</span></span> <span data-ttu-id="387bc-165">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="387bc-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="387bc-166">Default</span><span class="sxs-lookup"><span data-stu-id="387bc-166">Default</span></span>
- <span data-ttu-id="387bc-167">Basic</span><span class="sxs-lookup"><span data-stu-id="387bc-167">Basic</span></span>
- <span data-ttu-id="387bc-168">Credssp</span><span class="sxs-lookup"><span data-stu-id="387bc-168">Credssp</span></span>
- <span data-ttu-id="387bc-169">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="387bc-169">Digest</span></span>
- <span data-ttu-id="387bc-170">Kerberos</span><span class="sxs-lookup"><span data-stu-id="387bc-170">Kerberos</span></span>
- <span data-ttu-id="387bc-171">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="387bc-171">Negotiate</span></span>
- <span data-ttu-id="387bc-172">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="387bc-172">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="387bc-173">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="387bc-173">The default value is Default.</span></span>

<span data-ttu-id="387bc-174">このパラメーターの値の詳細については、MSDN ライブラリの「 [Authenticationmechanism 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-174">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="387bc-175">注意: ユーザーの資格情報が認証対象のリモートコンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="387bc-175">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="387bc-176">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="387bc-176">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="387bc-177">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="387bc-177">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-178">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="387bc-178">-CertificateThumbprint</span></span>

<span data-ttu-id="387bc-179">切断されたセッションに接続するためのアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-179">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="387bc-180">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="387bc-180">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="387bc-181">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-181">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="387bc-182">ローカルユーザーアカウントにのみマップできます。</span><span class="sxs-lookup"><span data-stu-id="387bc-182">They can be mapped only to local user accounts.</span></span>
<span data-ttu-id="387bc-183">ドメインアカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="387bc-183">They do not work with domain accounts.</span></span>

<span data-ttu-id="387bc-184">証明書の拇印を取得するには、PowerShell Cert: ドライブで Get-Item または Get-ChildItem コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="387bc-184">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-185">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="387bc-185">-ComputerName</span></span>

<span data-ttu-id="387bc-186">切断されたセッションが格納されているコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-186">Specifies the computers on which the disconnected sessions are stored.</span></span>
<span data-ttu-id="387bc-187">セッションは、接続のサーバー側または受信側のコンピューターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-187">Sessions are stored on the computer that is at the server-side or receiving end of a connection.</span></span>
<span data-ttu-id="387bc-188">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="387bc-188">The default is the local computer.</span></span>

<span data-ttu-id="387bc-189">コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="387bc-189">Type the NetBIOS name, an IP address, or a fully qualified domain name of one computer.</span></span>
<span data-ttu-id="387bc-190">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="387bc-190">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="387bc-191">ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="387bc-191">To specify the local computer, type the computer name, localhost, or a dot (.)</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameGuid, ComputerName
Aliases: Cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-192">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="387bc-192">-ConfigurationName</span></span>

<span data-ttu-id="387bc-193">指定したセッション構成を使用するセッションにのみ接続します。</span><span class="sxs-lookup"><span data-stu-id="387bc-193">Connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="387bc-194">セッション構成の構成名または完全修飾リソース URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="387bc-194">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span>
<span data-ttu-id="387bc-195">構成名だけを指定した場合は、次のスキーマ URI が付加され `http://schemas.microsoft.com/powershell` ます。</span><span class="sxs-lookup"><span data-stu-id="387bc-195">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>
<span data-ttu-id="387bc-196">セッションの構成名は、セッションの **ConfigurationName** プロパティに保存されています。</span><span class="sxs-lookup"><span data-stu-id="387bc-196">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="387bc-197">このパラメーター値は、セッションを選択してフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-197">The value of this parameter is used to select and filter sessions.</span></span>
<span data-ttu-id="387bc-198">セッションが使用するセッション構成が変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="387bc-198">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="387bc-199">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-199">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-200">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="387bc-200">-ConnectionUri</span></span>

<span data-ttu-id="387bc-201">切断されたセッションの接続エンドポイントの Uri を指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-201">Specifies the URIs of the connection endpoints for the disconnected sessions.</span></span>

<span data-ttu-id="387bc-202">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="387bc-202">The URI must be fully qualified.</span></span>
<span data-ttu-id="387bc-203">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="387bc-203">The format of this string is as follows:</span></span>

`\<Transport\>://\<ComputerName\>:\<Port\>/\<ApplicationName\>`

<span data-ttu-id="387bc-204">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="387bc-204">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="387bc-205">接続 URI を指定しない場合は、 *UseSSL* パラメーターと *Port* パラメーターを使用して接続 uri の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="387bc-205">If you do not specify a connection URI, you can use the *UseSSL* and *Port* parameters to specify the connection URI values.</span></span>

<span data-ttu-id="387bc-206">URI の **Transport** セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="387bc-206">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span>
<span data-ttu-id="387bc-207">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準ポート80で HTTP 用および 443 (HTTPS 用) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-207">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span>
<span data-ttu-id="387bc-208">PowerShell リモート処理に既定のポートを使用するには、HTTP の場合はポート5985、HTTPS の場合は5986を指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-208">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="387bc-209">対象のコンピューターが接続を別の URI にリダイレクトする場合、コマンドで *Allowredirection* パラメーターを使用しない限り、PowerShell によってリダイレクトが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-209">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the *AllowRedirection* parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-210">-Credential</span><span class="sxs-lookup"><span data-stu-id="387bc-210">-Credential</span></span>

<span data-ttu-id="387bc-211">切断されたセッションに接続するためのアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-211">Specifies a user account that has permission to connect to the disconnected session.</span></span>
<span data-ttu-id="387bc-212">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="387bc-212">The default is the current user.</span></span>

<span data-ttu-id="387bc-213">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="387bc-213">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="387bc-214">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="387bc-214">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="387bc-215">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-215">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="387bc-216">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-216">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-217">-Id</span><span class="sxs-lookup"><span data-stu-id="387bc-217">-Id</span></span>

<span data-ttu-id="387bc-218">切断されたセッションの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-218">Specifies the IDs of the disconnected sessions.</span></span>
<span data-ttu-id="387bc-219">*Id* パラメーターは、切断されたセッションが現在のセッションに既に接続されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="387bc-219">The *Id* parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="387bc-220">このパラメーターは、セッションがローカル コンピューター上に保存されているものの、現在のセッションに接続されていなかった場合には、有効でありながら効力を発揮しません。</span><span class="sxs-lookup"><span data-stu-id="387bc-220">This parameter is valid, but not effective, when the session is stored on the local computer, but was not connected to the current session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-221">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="387bc-221">-InstanceId</span></span>

<span data-ttu-id="387bc-222">切断されたセッションのインスタンス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-222">Specifies the instance IDs of the disconnected sessions.</span></span>

<span data-ttu-id="387bc-223">インスタンス ID は、ローカルコンピューターまたはリモートコンピューター上の **PSSession** を一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="387bc-223">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span>

<span data-ttu-id="387bc-224">インスタンス ID は、 **PSSession** の **InstanceID** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-224">The instance ID is stored in the **InstanceID** property of the **PSSession**.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-225">-Name</span><span class="sxs-lookup"><span data-stu-id="387bc-225">-Name</span></span>

<span data-ttu-id="387bc-226">切断されたセッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-226">Specifies the friendly names of the disconnected sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-227">-Port</span><span class="sxs-lookup"><span data-stu-id="387bc-227">-Port</span></span>

<span data-ttu-id="387bc-228">セッションに再接続するときに使用するリモート コンピューターのネットワーク ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-228">Specifies the network port on the remote computer that is used to reconnect to the session.</span></span>
<span data-ttu-id="387bc-229">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="387bc-229">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span>
<span data-ttu-id="387bc-230">既定のポートは5985で、これは HTTP 用の WinRM ポート、および HTTPS 用の WinRM ポートである5986です。</span><span class="sxs-lookup"><span data-stu-id="387bc-230">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="387bc-231">代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="387bc-231">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>
<span data-ttu-id="387bc-232">リスナーを構成するには、PowerShell プロンプトで次の2つのコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="387bc-232">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="387bc-233">必要な場合を除き、 *Port* パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="387bc-233">Do not use the *Port* parameter unless you must.</span></span>
<span data-ttu-id="387bc-234">コマンドに設定されているポートは、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-234">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span>
<span data-ttu-id="387bc-235">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="387bc-235">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-236">-セッション</span><span class="sxs-lookup"><span data-stu-id="387bc-236">-Session</span></span>

<span data-ttu-id="387bc-237">切断されたセッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-237">Specifies the disconnected sessions.</span></span>
<span data-ttu-id="387bc-238">**Pssession** オブジェクトを含む変数、または Get-PSSession コマンドなどの **pssession** オブジェクトを作成または取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="387bc-238">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a Get-PSSession command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-239">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="387bc-239">-SessionOption</span></span>

<span data-ttu-id="387bc-240">セッションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-240">Specifies advanced options for the session.</span></span>
<span data-ttu-id="387bc-241">New-PSSessionOption コマンドレットを使用して作成する **sessionoption** オブジェクト、またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="387bc-241">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="387bc-242">オプションの既定値は、$PSSessionOption ユーザー設定変数が設定されている場合は、その値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="387bc-242">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span>
<span data-ttu-id="387bc-243">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="387bc-243">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="387bc-244">セッション オプションの値は、$PSSessionOption ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-244">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span>
<span data-ttu-id="387bc-245">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="387bc-245">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="387bc-246">既定値を含むセッションオプションの説明については、「New-PSSessionOption」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-246">For a description of the session options that includes the default values, see New-PSSessionOption.</span></span>
<span data-ttu-id="387bc-247">**$PSSessionOption** ユーザー設定変数の詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-247">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="387bc-248">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-248">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-249">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="387bc-249">-ThrottleLimit</span></span>

<span data-ttu-id="387bc-250">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="387bc-250">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="387bc-251">このパラメーターを省略した場合、または値 0 を入力した場合は、既定値の 32 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-251">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="387bc-252">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="387bc-252">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="387bc-253">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="387bc-253">-UseSSL</span></span>

<span data-ttu-id="387bc-254">このコマンドレットが、切断されたセッションに接続するために Secure Sockets Layer (SSL) プロトコルを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="387bc-254">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="387bc-255">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="387bc-255">By default, SSL is not used.</span></span>

<span data-ttu-id="387bc-256">WS-Management は、ネットワーク経由で送信されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="387bc-256">WS-Management encrypts all PowerShell content transmitted over the network.</span></span>
<span data-ttu-id="387bc-257">*UseSSL* パラメーターは、HTTP 接続ではなく HTTPS 接続を介してデータを送信する追加の保護です。</span><span class="sxs-lookup"><span data-stu-id="387bc-257">The *UseSSL* parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="387bc-258">このパラメーターを使用しても、コマンドに使用されているポートで SSL を使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="387bc-258">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="387bc-259">-Confirm</span><span class="sxs-lookup"><span data-stu-id="387bc-259">-Confirm</span></span>

<span data-ttu-id="387bc-260">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-260">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="387bc-261">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="387bc-261">-WhatIf</span></span>

<span data-ttu-id="387bc-262">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="387bc-262">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="387bc-263">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="387bc-263">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="387bc-264">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="387bc-264">CommonParameters</span></span>

<span data-ttu-id="387bc-265">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="387bc-265">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="387bc-266">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-266">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="387bc-267">入力</span><span class="sxs-lookup"><span data-stu-id="387bc-267">INPUTS</span></span>

### <span data-ttu-id="387bc-268">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="387bc-268">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="387bc-269">パイプを使用してセッション ( **PSSession** ) をこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="387bc-269">You can pipe a session ( **PSSession** ) to this cmdlet.</span></span>

## <span data-ttu-id="387bc-270">出力</span><span class="sxs-lookup"><span data-stu-id="387bc-270">OUTPUTS</span></span>

### <span data-ttu-id="387bc-271">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="387bc-271">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="387bc-272">このコマンドレットは、再接続先のセッションを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="387bc-272">This cmdlet returns an object that represents the session to which it reconnected.</span></span>

## <span data-ttu-id="387bc-273">注</span><span class="sxs-lookup"><span data-stu-id="387bc-273">NOTES</span></span>

* <span data-ttu-id="387bc-274">**接続** が切断されているセッション、つまり **State** プロパティの値が disconnected のセッションにのみ再接続します。</span><span class="sxs-lookup"><span data-stu-id="387bc-274">**Connect-PSSession** reconnects only to sessions that are disconnected, that is, sessions that have a value of Disconnected for the **State** property.</span></span> <span data-ttu-id="387bc-275">Windows PowerShell 3.0 以降のバージョンを実行しているコンピューターに接続されている、または終了したセッションのみを切断し、再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="387bc-275">Only sessions that are connected to, or end at, computers that run Windows PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>
* <span data-ttu-id="387bc-276">切断されていないセッションで **接続-PSSession** を使用すると、このコマンドはセッションに影響を与えず、エラーを生成しません。</span><span class="sxs-lookup"><span data-stu-id="387bc-276">If you use **Connect-PSSession** on a session that is not disconnected, the command does not affect the session and it does not generate errors.</span></span>
* <span data-ttu-id="387bc-277">*EnableNetworkAccess* パラメーターを使用して作成された対話型トークンを使用して切断されたループバックセッションは、セッションが作成されたコンピューターからのみ再接続できます。</span><span class="sxs-lookup"><span data-stu-id="387bc-277">Disconnected loopback sessions with interactive tokens, which are created by using the *EnableNetworkAccess* parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="387bc-278">この制約は、悪意のあるアクセスからコンピューターを保護するためのものです。</span><span class="sxs-lookup"><span data-stu-id="387bc-278">This restriction protects the computer from malicious access.</span></span>
* <span data-ttu-id="387bc-279">**PSSession** の **State** プロパティの値は、現在のセッションを基準としています。</span><span class="sxs-lookup"><span data-stu-id="387bc-279">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
<span data-ttu-id="387bc-280">したがって、値が **Disconnected** の場合は、 **PSSession** が現在のセッションに接続されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="387bc-280">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="387bc-281">ただし、 **PSSession** がすべてのセッションから切断されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="387bc-281">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="387bc-282">別のセッションに接続されている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="387bc-282">It might be connected to a different session.</span></span> <span data-ttu-id="387bc-283">セッションに接続または再接続できるかどうかを確認するには、 **Availability** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="387bc-283">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="387bc-284">**Availability** の値が None の場合は、セッションに接続できることを示します。</span><span class="sxs-lookup"><span data-stu-id="387bc-284">An **Availability** value of None indicates that you can connect to the session.</span></span>
<span data-ttu-id="387bc-285">値が Busy の場合は、PSSession が別のセッションに接続されているため、 **PSSession** に接続できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="387bc-285">A value of Busy indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

  <span data-ttu-id="387bc-286">セッションの **State** プロパティの値の詳細については、MSDN ライブラリの「 [RunspaceState 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-286">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) in the MSDN library.</span></span>

  <span data-ttu-id="387bc-287">セッションの **Availability** プロパティの値の詳細については、MSDN ライブラリの「 [RunspaceAvailability 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387bc-287">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) in the MSDN library.</span></span>

* <span data-ttu-id="387bc-288">Pssession に接続するときに、 **pssession** のアイドルタイムアウト値を変更することはできませ **ん。**</span><span class="sxs-lookup"><span data-stu-id="387bc-288">You cannot change the idle time-out value of a **PSSession** when you connect to the **PSSession**.</span></span> <span data-ttu-id="387bc-289">*Connect-PSSession* の **SessionOption** パラメーターは、 **IdleTimeout** の値が設定されている **SessionOption** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="387bc-289">The *SessionOption* parameter of **Connect-PSSession** takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="387bc-290">ただし、 **Sessionoption** オブジェクトの **idletimeout** 値と $PSSessionOption 変数の **idletimeout** 値は、 **PSSession** に接続するときには無視されます。</span><span class="sxs-lookup"><span data-stu-id="387bc-290">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the $PSSessionOption variable are ignored when connecting to a **PSSession**.</span></span>

  <span data-ttu-id="387bc-291">Pssession の **作成時に pssession の** アイドル **タイムアウトを設定** および変更するには、pssession コマンドレットまたは **コマンド** レットを使用 **するか、** **pssession** から切断します。</span><span class="sxs-lookup"><span data-stu-id="387bc-291">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the **New-PSSession** or **Invoke-Command** cmdlets, and when you disconnect from the **PSSession**.</span></span>

  <span data-ttu-id="387bc-292">**PSSession** の **IdleTimeout** プロパティは、切断されたセッションをリモートコンピューターで保持する期間を決定するため、切断されたセッションにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="387bc-292">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions, because it determines how long a disconnected session is maintained on the remote computer.</span></span>
<span data-ttu-id="387bc-293">セッションが切断されると、その時点からアイドル状態であると判断されます。これは、そのセッションでコマンドを実行している場合であっても同じです。</span><span class="sxs-lookup"><span data-stu-id="387bc-293">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

## <span data-ttu-id="387bc-294">関連リンク</span><span class="sxs-lookup"><span data-stu-id="387bc-294">RELATED LINKS</span></span>

[<span data-ttu-id="387bc-295">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="387bc-295">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="387bc-296">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="387bc-296">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="387bc-297">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="387bc-297">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="387bc-298">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="387bc-298">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="387bc-299">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="387bc-299">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="387bc-300">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="387bc-300">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="387bc-301">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="387bc-301">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="387bc-302">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="387bc-302">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="387bc-303">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="387bc-303">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="387bc-304">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="387bc-304">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="387bc-305">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="387bc-305">Remove-PSSession</span></span>](Remove-PSSession.md)

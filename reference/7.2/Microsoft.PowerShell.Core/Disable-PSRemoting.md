---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 4410c8f41fffcaae9c9f447af246f335033d53a1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604955"
---
# <span data-ttu-id="620d3-102">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="620d3-102">Disable-PSRemoting</span></span>

## <span data-ttu-id="620d3-103">概要</span><span class="sxs-lookup"><span data-stu-id="620d3-103">SYNOPSIS</span></span>
<span data-ttu-id="620d3-104">PowerShell エンドポイントがリモート接続を受信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="620d3-104">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="620d3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="620d3-105">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="620d3-106">Description</span><span class="sxs-lookup"><span data-stu-id="620d3-106">DESCRIPTION</span></span>

<span data-ttu-id="620d3-107">この `Disable-PSRemoting` コマンドレットは、ローカルコンピューター上のすべての PowerShell バージョン6以降のセッションエンドポイント構成へのリモートアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="620d3-107">The `Disable-PSRemoting` cmdlet blocks remote access to all PowerShell version 6 and greater session endpoint configurations on the local computer.</span></span> <span data-ttu-id="620d3-108">Windows PowerShell エンドポイントの構成には影響しません。</span><span class="sxs-lookup"><span data-stu-id="620d3-108">It does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="620d3-109">Windows PowerShell セッションエンドポイントの構成を無効にするには、 `Disable-PSRemoting` Windows powershell セッション内からコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="620d3-109">To disable Windows PowerShell session endpoint configurations, run `Disable-PSRemoting` command from within a Windows PowerShell session.</span></span>

<span data-ttu-id="620d3-110">すべての PowerShell バージョン6以降のセッションエンドポイント構成へのリモートアクセスを再度有効にするには、コマンドレットを使用し `Enable-PSRemoting` ます。</span><span class="sxs-lookup"><span data-stu-id="620d3-110">To re-enable remote access to all PowerShell version 6 and greater session endpoint configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="620d3-111">すべての Windows PowerShell セッションエンドポイント構成へのリモートアクセスを再度有効にするには、 `Enable-PSRemoting` Windows powershell セッション内からを実行します。</span><span class="sxs-lookup"><span data-stu-id="620d3-111">To re-enable remote access to all Windows PowerShell session endpoint configurations, run `Enable-PSRemoting` from within a Windows PowerShell session.</span></span>

> [!NOTE]
> <span data-ttu-id="620d3-112">ローカル Windows コンピューターへのすべての PowerShell リモートアクセスを無効にする場合は、PowerShell バージョン6以降のセッション内、および Windows PowerShell セッション内から、このコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="620d3-112">If you want to disable all PowerShell remote access to a local Windows machine, you must run this command both from a within PowerShell version 6 or greater session and from within a Windows PowerShell session.</span></span> <span data-ttu-id="620d3-113">Windows PowerShell は、既定ではすべての Windows マシンにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="620d3-113">Windows PowerShell is installed on all Windows machines by default.</span></span>

<span data-ttu-id="620d3-114">特定のセッションエンドポイント構成へのリモートアクセスを無効にしてから再度有効にするには、 `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="620d3-114">To disable and re-enable remote access to specific session endpoint configurations, use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="620d3-115">個々のエンドポイントの特定のアクセス構成を設定するには、 `Set-PSSessionConfiguration` コマンドレットを **accessmode** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="620d3-115">To set specific access configurations of individual endpoints, use the `Set-PSSessionConfiguration` cmdlet along with the **AccessMode** parameter.</span></span> <span data-ttu-id="620d3-116">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="620d3-116">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="620d3-117">を実行した後も、 `Disable-PSRemoting` ローカルコンピューターでループバック接続を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="620d3-117">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="620d3-118">ループバック接続は、から発信され、同じローカルコンピューターに接続する PowerShell リモートセッションです。</span><span class="sxs-lookup"><span data-stu-id="620d3-118">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="620d3-119">外部ソースからのリモートセッションはブロックされたままになります。</span><span class="sxs-lookup"><span data-stu-id="620d3-119">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="620d3-120">ループバック接続の場合は、 **EnableNetworkAccess** パラメーターに従って暗黙的な資格情報を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="620d3-120">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="620d3-121">ループバック接続の詳細については、「 [新規-PSSession](New-PSSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="620d3-121">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="620d3-122">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="620d3-122">This cmdlet is only available on the Windows platform.</span></span> <span data-ttu-id="620d3-123">Linux または macOS バージョンの PowerShell では使用できません。</span><span class="sxs-lookup"><span data-stu-id="620d3-123">It is not available on Linux or macOS versions of PowerShell.</span></span> <span data-ttu-id="620d3-124">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="620d3-124">To run this cmdlet, start PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="620d3-125">例</span><span class="sxs-lookup"><span data-stu-id="620d3-125">EXAMPLES</span></span>

### <span data-ttu-id="620d3-126">例 1: すべての PowerShell セッション構成へのリモートアクセスを禁止する</span><span class="sxs-lookup"><span data-stu-id="620d3-126">Example 1: Prevent remote access to all PowerShell session configurations</span></span>

<span data-ttu-id="620d3-127">この例では、コンピューター上のすべての PowerShell セッションエンドポイント構成にリモートアクセスできないようにします。</span><span class="sxs-lookup"><span data-stu-id="620d3-127">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

```powershell
Disable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="620d3-128">例 2: 確認メッセージを表示せずにすべての PowerShell セッション構成にリモートアクセスすることを禁止する</span><span class="sxs-lookup"><span data-stu-id="620d3-128">Example 2: Prevent remote access to all PowerShell session configurations without confirmation prompt</span></span>

<span data-ttu-id="620d3-129">この例では、メッセージを表示せずに、コンピューター上のすべての PowerShell セッションエンドポイント構成をリモートアクセスできないようにします。</span><span class="sxs-lookup"><span data-stu-id="620d3-129">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="620d3-130">例 3: このコマンドレットを実行した場合の影響</span><span class="sxs-lookup"><span data-stu-id="620d3-130">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="620d3-131">この例は、コマンドレットを使用した場合の効果を示して `Disable-PSRemoting` います。</span><span class="sxs-lookup"><span data-stu-id="620d3-131">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="620d3-132">このコマンドシーケンスを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="620d3-132">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="620d3-133">セッション構成を無効にすると、 `New-PSSession` コマンドレットはローカルコンピューター ("ループバック" とも呼ばれます) へのリモートセッションを作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="620d3-133">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="620d3-134">リモートアクセスはローカルコンピューターで無効になっているため、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="620d3-134">Because remote access is disabled on the local machine, the command fails.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### <span data-ttu-id="620d3-135">例 4: このコマンドレットと Enable-PSRemoting を実行した場合の影響</span><span class="sxs-lookup"><span data-stu-id="620d3-135">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="620d3-136">この例では、 `Disable-PSRemoting` コマンドレットとコマンドレットを使用して、のセッション構成への影響を示し `Enable-PSRemoting` ます。</span><span class="sxs-lookup"><span data-stu-id="620d3-136">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="620d3-137">`Disable-PSRemoting` は、すべての PowerShell セッションエンドポイント構成へのリモートアクセスを無効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-137">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="620d3-138">**Force** パラメーターにより、すべてのユーザー メッセージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="620d3-138">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="620d3-139">`Get-PSSessionConfiguration` `Format-Table` コマンドレットおよびコマンドレットは、コンピューター上のセッション構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="620d3-139">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="620d3-140">出力には、ネットワークトークンを持つすべてのリモートユーザーが、エンドポイント構成へのアクセスを拒否されていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="620d3-140">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="620d3-141">ローカルコンピューター上の Administrators グループは、ローカル (ループバックとも呼ばれます) で暗黙的な資格情報を使用して接続されている限り、エンドポイント構成へのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-141">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
```

<span data-ttu-id="620d3-142">この `Enable-PSRemoting` コマンドレットは、コンピューター上のすべての PowerShell セッションエンドポイント構成へのリモートアクセスを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="620d3-142">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="620d3-143">**Force** パラメーターを指定すると、すべてのユーザープロンプトが表示されなくなり、プロンプトなしで WinRM サービスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-143">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="620d3-144">新しい出力は、 **Accessdenied** セキュリティ記述子がすべてのセッション構成から削除されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="620d3-144">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="620d3-145">例 5: 無効なセッションエンドポイント構成を使用したループバック接続</span><span class="sxs-lookup"><span data-stu-id="620d3-145">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="620d3-146">この例では、エンドポイントの構成を無効にする方法を示し、無効になっているエンドポイントへのループバック接続を成功させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="620d3-146">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="620d3-147">`Disable-PSRemoting` すべての PowerShell セッションエンドポイント構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="620d3-147">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -Credential (Get-Credential)
```

```Output
PowerShell credential request
Enter your credentials.
User: UserName
Password for user UserName: ************

New-PSSession: [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

<span data-ttu-id="620d3-148">を初めて使用する場合は、 `New-PSSession` ローカルコンピューターへのリモートセッションの作成が試行されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-148">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="620d3-149">**ConfigurationName** パラメーターは、無効になっている PowerShell エンドポイントを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-149">The **ConfigurationName** parameter is used to specify a disabled PowerShell endpoint.</span></span> <span data-ttu-id="620d3-150">資格情報は、 **Credential** パラメーターを使用してコマンドに明示的に渡されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-150">Credentials are explicitly passed to the command through the **Credential** parameter.</span></span> <span data-ttu-id="620d3-151">この種類の接続はネットワークスタックを経由し、ループバックではありません。</span><span class="sxs-lookup"><span data-stu-id="620d3-151">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="620d3-152">その結果、無効なエンドポイントへの接続は失敗し、" **アクセスが拒否されまし** た" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-152">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="620d3-153">2つ目の使用では、 `New-PSSession` ローカルコンピューターへのリモートセッションの作成も試行します。</span><span class="sxs-lookup"><span data-stu-id="620d3-153">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="620d3-154">この場合、ネットワークスタックをバイパスするループバック接続であるため、成功します。</span><span class="sxs-lookup"><span data-stu-id="620d3-154">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="620d3-155">次の条件が満たされると、ループバック接続が作成されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-155">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="620d3-156">接続先のコンピューター名は ' localhost ' です。</span><span class="sxs-lookup"><span data-stu-id="620d3-156">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="620d3-157">資格情報は渡されません。</span><span class="sxs-lookup"><span data-stu-id="620d3-157">No credentials are passed in.</span></span> <span data-ttu-id="620d3-158">現在ログインしているユーザー (暗黙的な資格情報) は、接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-158">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="620d3-159">**EnableNetworkAccess** スイッチパラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-159">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="620d3-160">ループバック接続の詳細については、「 [新しい PSSession](New-PSSession.md) ドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="620d3-160">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="620d3-161">例 6: すべての PowerShell リモート処理エンドポイント構成を無効にする</span><span class="sxs-lookup"><span data-stu-id="620d3-161">Example 6: Disabling all PowerShell remoting endpoint configurations</span></span>

<span data-ttu-id="620d3-162">この例では、コマンドを実行して `Disable-PSRemoting` も Windows PowerShell エンドポイントの構成に影響がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="620d3-162">This example demonstrates how running the `Disable-PSRemoting` command does not affect Windows PowerShell endpoint configurations.</span></span> <span data-ttu-id="620d3-163">`Get-PSSessionConfiguration` Windows PowerShell 内で実行すると、すべてのエンドポイントの構成が表示されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-163">`Get-PSSessionConfiguration` run within Windows PowerShell shows all endpoint configurations.</span></span> <span data-ttu-id="620d3-164">Windows PowerShell エンドポイントの構成が無効になっていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="620d3-164">We see that the Windows PowerShell endpoint configurations are not disabled.</span></span>

```powershell
Disable-PSRemoting -Force
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

```powershell
powershell.exe -command 'Disable-PSRemoting -Force'
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting or
Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the
Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management
                Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

<span data-ttu-id="620d3-165">これらのエンドポイント構成を無効にするには、 `Disable-PSRemoting` Windows PowerShell セッション内からコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="620d3-165">To disable these endpoint configurations, the `Disable-PSRemoting` command must be run from within a Windows PowerShell session.</span></span> <span data-ttu-id="620d3-166">ここで、 `Get-PSSessionConfiguration` Windows PowerShell 内からを実行すると、すべてのエンドポイント構成が無効になっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="620d3-166">Now, `Get-PSSessionConfiguration` run from within Windows PowerShell shows that all endpoint configurations are disabled.</span></span>

### <span data-ttu-id="620d3-167">例 7: カスタムセキュリティ記述子を持つセッション構成へのリモートアクセスを禁止する</span><span class="sxs-lookup"><span data-stu-id="620d3-167">Example 7: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="620d3-168">この例では、 `Disable-PSRemoting` コマンドレットを使用して、カスタムセキュリティ記述子を持つセッション構成を含むすべてのセッション構成へのリモートアクセスを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="620d3-168">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="620d3-169">`Register-PSSessionConfiguration`**テスト** セッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="620d3-169">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="620d3-170">**FilePath** パラメーターでは、セッションをカスタマイズするセッション構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="620d3-170">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="620d3-171">**Showsecurity記述子 ui** パラメーターを使用すると、セッション構成のアクセス許可を設定するダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-171">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="620d3-172">[アクセス許可] ダイアログボックスで、指定されたユーザーに対してカスタムのフルアクセス許可を作成します。</span><span class="sxs-lookup"><span data-stu-id="620d3-172">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="620d3-173">`Get-PSSessionConfiguration`およびコマンドレットでは、 `Format-Table` セッション構成とそのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-173">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="620d3-174">出力には、 **テスト** セッション構成で、指定されたユーザーに対する対話型アクセスと特殊なアクセス許可が許可されていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="620d3-174">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="620d3-175">`Disable-PSRemoting` すべてのセッション構成へのリモートアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="620d3-175">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, User01 AccessAllowed

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName Test
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

<span data-ttu-id="620d3-176">ここで `Get-PSSessionConfiguration` 、 `Format-Table` コマンドレットとコマンドレットは、すべてのネットワークユーザーに対する **accessdenied** セキュリティ記述子が、 **テスト** セッション構成を含むすべてのセッション構成に追加されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="620d3-176">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="620d3-177">他のセキュリティ記述子は変更されませんが、"network_deny_all" セキュリティ記述子が優先されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-177">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="620d3-178">これは、 `New-PSSession` **テスト** セッション構成に接続するためにを使用した場合に示されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-178">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="620d3-179">例 8: 選択したセッション構成へのリモートアクセスを再度有効にする</span><span class="sxs-lookup"><span data-stu-id="620d3-179">Example 8: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="620d3-180">この例では、選択したセッション構成にのみリモート アクセスを再度有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="620d3-180">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="620d3-181">すべてのセッション構成を無効にした後、特定のセッションを再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="620d3-181">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="620d3-182">`Set-PSSessionConfiguration`コマンドレットを使用して、 **PowerShell. 6** セッション構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="620d3-182">The `Set-PSSessionConfiguration` cmdlet is used to change the **PowerShell.6** session configuration.</span></span> <span data-ttu-id="620d3-183">**Accessmode** パラメーターの値を **remote** に設定すると、構成へのリモートアクセスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="620d3-183">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name PowerShell.6 -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\ ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
```

## <span data-ttu-id="620d3-184">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="620d3-184">PARAMETERS</span></span>

### <span data-ttu-id="620d3-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="620d3-185">-Confirm</span></span>

<span data-ttu-id="620d3-186">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="620d3-186">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="620d3-187">-Force</span><span class="sxs-lookup"><span data-stu-id="620d3-187">-Force</span></span>

<span data-ttu-id="620d3-188">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="620d3-188">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="620d3-189">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="620d3-189">-WhatIf</span></span>

<span data-ttu-id="620d3-190">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="620d3-190">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="620d3-191">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="620d3-191">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="620d3-192">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="620d3-192">CommonParameters</span></span>

<span data-ttu-id="620d3-193">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="620d3-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="620d3-194">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="620d3-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="620d3-195">入力</span><span class="sxs-lookup"><span data-stu-id="620d3-195">INPUTS</span></span>

### <span data-ttu-id="620d3-196">なし</span><span class="sxs-lookup"><span data-stu-id="620d3-196">None</span></span>

<span data-ttu-id="620d3-197">パイプを使用してこのコマンドレットにオブジェクトを送ることはできません。</span><span class="sxs-lookup"><span data-stu-id="620d3-197">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="620d3-198">出力</span><span class="sxs-lookup"><span data-stu-id="620d3-198">OUTPUTS</span></span>

### <span data-ttu-id="620d3-199">なし</span><span class="sxs-lookup"><span data-stu-id="620d3-199">None</span></span>

<span data-ttu-id="620d3-200">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="620d3-200">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="620d3-201">注</span><span class="sxs-lookup"><span data-stu-id="620d3-201">NOTES</span></span>

<span data-ttu-id="620d3-202">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="620d3-202">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="620d3-203">セッション構成を無効にしても、 `Enable-PSRemoting` またはコマンドレットによって行われたすべての変更が元に戻されるわけではありません `Enable-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="620d3-203">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="620d3-204">場合によっては次の変更を手動で元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="620d3-204">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="620d3-205">WinRM サービスを停止して無効にする。</span><span class="sxs-lookup"><span data-stu-id="620d3-205">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="620d3-206">任意の IP アドレスで要求を受け入れるリスナーを削除する。</span><span class="sxs-lookup"><span data-stu-id="620d3-206">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="620d3-207">WS-Management 通信用のファイアウォールの例外を無効にする。</span><span class="sxs-lookup"><span data-stu-id="620d3-207">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="620d3-208">LocalAccountTokenFilterPolicy の値を 0 に復元して、リモート アクセスをコンピューターの Administrators グループのメンバーに制限する。</span><span class="sxs-lookup"><span data-stu-id="620d3-208">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

- <span data-ttu-id="620d3-209">セッションエンドポイント構成は、セッションの環境を定義する設定のグループです。</span><span class="sxs-lookup"><span data-stu-id="620d3-209">A session endpoint configuration is a group of settings that define the environment for a session.</span></span>
  <span data-ttu-id="620d3-210">コンピューターに接続するすべてのセッションでは、コンピューターに登録されているセッションエンドポイント構成のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="620d3-210">Every session that connects to the computer must use one of the session endpoint configurations that are registered on the computer.</span></span> <span data-ttu-id="620d3-211">すべてのセッションエンドポイント構成へのリモートアクセスを拒否することにより、リモートユーザーがコンピューターに接続するセッションを確立するのを効果的に防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="620d3-211">By denying remote access to all session endpoint configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

## <span data-ttu-id="620d3-212">関連リンク</span><span class="sxs-lookup"><span data-stu-id="620d3-212">RELATED LINKS</span></span>

[<span data-ttu-id="620d3-213">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="620d3-213">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="620d3-214">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="620d3-214">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="620d3-215">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="620d3-215">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="620d3-216">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="620d3-216">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="620d3-217">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="620d3-217">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="620d3-218">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="620d3-218">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="620d3-219">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="620d3-219">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="620d3-220">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="620d3-220">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

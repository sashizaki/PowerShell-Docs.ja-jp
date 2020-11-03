---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 3a281786f99b2a46d0aeb9785480f02b35b2b433
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212104"
---
# <span data-ttu-id="b3598-103">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="b3598-103">Disable-PSRemoting</span></span>

## <span data-ttu-id="b3598-104">概要</span><span class="sxs-lookup"><span data-stu-id="b3598-104">SYNOPSIS</span></span>
<span data-ttu-id="b3598-105">PowerShell エンドポイントがリモート接続を受信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="b3598-105">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="b3598-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3598-106">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b3598-107">Description</span><span class="sxs-lookup"><span data-stu-id="b3598-107">DESCRIPTION</span></span>

<span data-ttu-id="b3598-108">この `Disable-PSRemoting` コマンドレットは、ローカルコンピューター上のすべての Windows PowerShell セッションエンドポイント構成へのリモートアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="b3598-108">The `Disable-PSRemoting` cmdlet blocks remote access to all Windows PowerShell session endpoint configurations on the local computer.</span></span> <span data-ttu-id="b3598-109">これには、PowerShell 6 以降で作成されたすべてのエンドポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3598-109">This includes any endpoints created by PowerShell 6 or higher.</span></span>

<span data-ttu-id="b3598-110">すべてのセッション構成へのリモートアクセスを再度有効にするには、コマンドレットを使用し `Enable-PSRemoting` ます。</span><span class="sxs-lookup"><span data-stu-id="b3598-110">To re-enable remote access to all session configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="b3598-111">これには、PowerShell 6 以降で作成されたすべてのエンドポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3598-111">This includes any endpoints created by PowerShell 6 or higher.</span></span> <span data-ttu-id="b3598-112">選択したセッション構成へのリモートアクセスを有効にするには、コマンドレットの **Accessmode** パラメーターを使用し `Set-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="b3598-112">To enable remote access to selected session configurations, use the **AccessMode** parameter of the `Set-PSSessionConfiguration` cmdlet.</span></span>
<span data-ttu-id="b3598-113">また、 `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` コマンドレットとコマンドレットを使用して、すべてのユーザーのセッション構成を有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b3598-113">You can also use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets to enable and disable session configurations for all users.</span></span> <span data-ttu-id="b3598-114">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3598-114">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b3598-115">を実行した後も、 `Disable-PSRemoting` ローカルコンピューターでループバック接続を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b3598-115">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="b3598-116">ループバック接続は、から発信され、同じローカルコンピューターに接続する PowerShell リモートセッションです。</span><span class="sxs-lookup"><span data-stu-id="b3598-116">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="b3598-117">外部ソースからのリモートセッションはブロックされたままになります。</span><span class="sxs-lookup"><span data-stu-id="b3598-117">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="b3598-118">ループバック接続の場合は、 **EnableNetworkAccess** パラメーターに従って暗黙的な資格情報を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3598-118">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="b3598-119">ループバック接続の詳細については、「 [新規-PSSession](New-PSSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3598-119">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="b3598-120">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="b3598-120">To run this cmdlet, start Windows PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="b3598-121">例</span><span class="sxs-lookup"><span data-stu-id="b3598-121">EXAMPLES</span></span>

### <span data-ttu-id="b3598-122">例 1: すべてのセッション構成へのリモートアクセスを禁止する</span><span class="sxs-lookup"><span data-stu-id="b3598-122">Example 1: Prevent remote access to all session configurations</span></span>

<span data-ttu-id="b3598-123">この例では、コンピューター上のすべての PowerShell セッションエンドポイント構成にリモートアクセスできないようにします。</span><span class="sxs-lookup"><span data-stu-id="b3598-123">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

```powershell
Disable-PSRemoting
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="b3598-124">例 2: 確認メッセージを表示せずにすべてのセッション構成へのリモートアクセスを禁止する</span><span class="sxs-lookup"><span data-stu-id="b3598-124">Example 2: Prevent remote access to all session configurations without confirmation prompt</span></span>

<span data-ttu-id="b3598-125">この例では、メッセージを表示せずに、コンピューター上のすべての PowerShell セッションエンドポイント構成をリモートアクセスできないようにします。</span><span class="sxs-lookup"><span data-stu-id="b3598-125">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="b3598-126">例 3: このコマンドレットを実行した場合の影響</span><span class="sxs-lookup"><span data-stu-id="b3598-126">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="b3598-127">この例は、コマンドレットを使用した場合の効果を示して `Disable-PSRemoting` います。</span><span class="sxs-lookup"><span data-stu-id="b3598-127">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="b3598-128">このコマンドシーケンスを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="b3598-128">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="b3598-129">セッション構成を無効にすると、 `New-PSSession` コマンドレットはローカルコンピューター ("ループバック" とも呼ばれます) へのリモートセッションを作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="b3598-129">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="b3598-130">リモートアクセスはローカルコンピューターで無効になっているため、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="b3598-130">Because remote access is disabled on the local machine, the command fails.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
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

### <span data-ttu-id="b3598-131">例 4: このコマンドレットと Enable-PSRemoting を実行した場合の影響</span><span class="sxs-lookup"><span data-stu-id="b3598-131">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="b3598-132">この例では、 `Disable-PSRemoting` コマンドレットとコマンドレットを使用して、のセッション構成への影響を示し `Enable-PSRemoting` ます。</span><span class="sxs-lookup"><span data-stu-id="b3598-132">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="b3598-133">`Disable-PSRemoting` は、すべての PowerShell セッションエンドポイント構成へのリモートアクセスを無効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-133">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="b3598-134">**Force** パラメーターにより、すべてのユーザー メッセージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="b3598-134">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="b3598-135">`Get-PSSessionConfiguration` `Format-Table` コマンドレットおよびコマンドレットは、コンピューター上のセッション構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="b3598-135">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="b3598-136">出力には、ネットワークトークンを持つすべてのリモートユーザーが、エンドポイント構成へのアクセスを拒否されていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="b3598-136">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="b3598-137">ローカルコンピューター上の Administrators グループは、ローカル (ループバックとも呼ばれます) で暗黙的な資格情報を使用して接続されている限り、エンドポイント構成へのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-137">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow BUILTIN\Administrators AccessAllowed
microsoft.powershell32        BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="b3598-138">この `Enable-PSRemoting` コマンドレットは、コンピューター上のすべての PowerShell セッションエンドポイント構成へのリモートアクセスを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="b3598-138">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="b3598-139">**Force** パラメーターを指定すると、すべてのユーザープロンプトが表示されなくなり、プロンプトなしで WinRM サービスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-139">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="b3598-140">新しい出力は、 **Accessdenied** セキュリティ記述子がすべてのセッション構成から削除されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b3598-140">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="b3598-141">例 5: 無効なセッションエンドポイント構成を使用したループバック接続</span><span class="sxs-lookup"><span data-stu-id="b3598-141">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="b3598-142">この例では、エンドポイントの構成を無効にする方法を示し、無効になっているエンドポイントへのループバック接続を成功させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b3598-142">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="b3598-143">`Disable-PSRemoting` すべての PowerShell セッションエンドポイント構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b3598-143">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message : Access is
denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [New-PSSession], PSRemotin
   gTransportException
    + FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed

```

```powershell
New-PSSession -ComputerName localhost -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

<span data-ttu-id="b3598-144">を初めて使用する場合は、 `New-PSSession` ローカルコンピューターへのリモートセッションの作成が試行されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-144">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="b3598-145">この種類の接続はネットワークスタックを経由し、ループバックではありません。</span><span class="sxs-lookup"><span data-stu-id="b3598-145">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="b3598-146">その結果、無効なエンドポイントへの接続は失敗し、" **アクセスが拒否されまし** た" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-146">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="b3598-147">2つ目の使用では、 `New-PSSession` ローカルコンピューターへのリモートセッションの作成も試行します。</span><span class="sxs-lookup"><span data-stu-id="b3598-147">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="b3598-148">この場合、ネットワークスタックをバイパスするループバック接続であるため、成功します。</span><span class="sxs-lookup"><span data-stu-id="b3598-148">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="b3598-149">次の条件が満たされると、ループバック接続が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-149">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="b3598-150">接続先のコンピューター名は ' localhost ' です。</span><span class="sxs-lookup"><span data-stu-id="b3598-150">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="b3598-151">資格情報は渡されません。</span><span class="sxs-lookup"><span data-stu-id="b3598-151">No credentials are passed in.</span></span> <span data-ttu-id="b3598-152">現在ログインしているユーザー (暗黙的な資格情報) は、接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-152">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="b3598-153">**EnableNetworkAccess** スイッチパラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-153">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="b3598-154">ループバック接続の詳細については、「 [新しい PSSession](New-PSSession.md) ドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3598-154">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="b3598-155">例 6: カスタムセキュリティ記述子を持つセッション構成へのリモートアクセスを禁止する</span><span class="sxs-lookup"><span data-stu-id="b3598-155">Example 6: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="b3598-156">この例では、 `Disable-PSRemoting` コマンドレットを使用して、カスタムセキュリティ記述子を持つセッション構成を含むすべてのセッション構成へのリモートアクセスを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b3598-156">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="b3598-157">`Register-PSSessionConfiguration`**テスト** セッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="b3598-157">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="b3598-158">**FilePath** パラメーターでは、セッションをカスタマイズするセッション構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3598-158">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="b3598-159">**Showsecurity記述子 ui** パラメーターを使用すると、セッション構成のアクセス許可を設定するダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-159">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="b3598-160">[アクセス許可] ダイアログボックスで、指定されたユーザーに対してカスタムのフルアクセス許可を作成します。</span><span class="sxs-lookup"><span data-stu-id="b3598-160">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="b3598-161">`Get-PSSessionConfiguration`およびコマンドレットでは、 `Format-Table` セッション構成とそのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-161">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="b3598-162">出力には、 **テスト** セッション構成で、指定されたユーザーに対する対話型アクセスと特殊なアクセス許可が許可されていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="b3598-162">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="b3598-163">`Disable-PSRemoting` すべてのセッション構成へのリモートアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b3598-163">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
DOMAIN01\User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\NETWORK AccessDenied, NTAUTHORITY\INTERACTIVE AccessAllowed,
BUILTIN\Administrators AccessAllowed, DOMAIN01\User01 AccessAllowed


[Server01] Connecting to remote server failed with the following error message : Access is denied. For more information, see the about_Rem
ote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="b3598-164">ここで `Get-PSSessionConfiguration` 、 `Format-Table` コマンドレットとコマンドレットは、すべてのネットワークユーザーに対する **accessdenied** セキュリティ記述子が、 **テスト** セッション構成を含むすべてのセッション構成に追加されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b3598-164">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="b3598-165">他のセキュリティ記述子は変更されませんが、"network_deny_all" セキュリティ記述子が優先されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-165">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="b3598-166">これは、 `New-PSSession` **テスト** セッション構成に接続するためにを使用した場合に示されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-166">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="b3598-167">例 7: 選択したセッション構成へのリモートアクセスを再度有効にする</span><span class="sxs-lookup"><span data-stu-id="b3598-167">Example 7: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="b3598-168">この例では、選択したセッション構成にのみリモート アクセスを再度有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b3598-168">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="b3598-169">すべてのセッション構成を無効にした後、特定のセッションを再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="b3598-169">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="b3598-170">`Set-PSSessionConfiguration`コマンドレットは、microsoft を変更するために使用され **ます。ServerManager** セッション構成。</span><span class="sxs-lookup"><span data-stu-id="b3598-170">The `Set-PSSessionConfiguration` cmdlet is used to change the **microsoft.ServerManager** session configuration.</span></span> <span data-ttu-id="b3598-171">**Accessmode** パラメーターの値を **remote** に設定すると、構成へのリモートアクセスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="b3598-171">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name Microsoft.ServerManager -AccessMode Remote -Force
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

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
```

## <span data-ttu-id="b3598-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3598-172">PARAMETERS</span></span>

### <span data-ttu-id="b3598-173">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b3598-173">-Confirm</span></span>

<span data-ttu-id="b3598-174">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3598-174">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b3598-175">-Force</span><span class="sxs-lookup"><span data-stu-id="b3598-175">-Force</span></span>
<span data-ttu-id="b3598-176">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3598-176">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="b3598-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b3598-177">-WhatIf</span></span>

<span data-ttu-id="b3598-178">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="b3598-178">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b3598-179">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="b3598-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b3598-180">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3598-180">CommonParameters</span></span>

<span data-ttu-id="b3598-181">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b3598-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3598-182">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3598-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b3598-183">入力</span><span class="sxs-lookup"><span data-stu-id="b3598-183">INPUTS</span></span>

### <span data-ttu-id="b3598-184">なし</span><span class="sxs-lookup"><span data-stu-id="b3598-184">None</span></span>

<span data-ttu-id="b3598-185">パイプを使用してこのコマンドレットにオブジェクトを送ることはできません。</span><span class="sxs-lookup"><span data-stu-id="b3598-185">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="b3598-186">出力</span><span class="sxs-lookup"><span data-stu-id="b3598-186">OUTPUTS</span></span>

### <span data-ttu-id="b3598-187">なし</span><span class="sxs-lookup"><span data-stu-id="b3598-187">None</span></span>

<span data-ttu-id="b3598-188">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="b3598-188">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b3598-189">注</span><span class="sxs-lookup"><span data-stu-id="b3598-189">NOTES</span></span>

- <span data-ttu-id="b3598-190">セッション構成を無効にしても、 `Enable-PSRemoting` またはコマンドレットによって行われたすべての変更が元に戻されるわけではありません `Enable-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="b3598-190">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="b3598-191">場合によっては次の変更を手動で元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3598-191">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="b3598-192">WinRM サービスを停止して無効にする。</span><span class="sxs-lookup"><span data-stu-id="b3598-192">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="b3598-193">任意の IP アドレスで要求を受け入れるリスナーを削除する。</span><span class="sxs-lookup"><span data-stu-id="b3598-193">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="b3598-194">WS-Management 通信用のファイアウォールの例外を無効にする。</span><span class="sxs-lookup"><span data-stu-id="b3598-194">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="b3598-195">LocalAccountTokenFilterPolicy の値を 0 に復元して、リモート アクセスをコンピューターの Administrators グループのメンバーに制限する。</span><span class="sxs-lookup"><span data-stu-id="b3598-195">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

  <span data-ttu-id="b3598-196">セッション構成は、セッションの環境を定義する設定のグループです。</span><span class="sxs-lookup"><span data-stu-id="b3598-196">A session configuration is a group of settings that define the environment for a session.</span></span> <span data-ttu-id="b3598-197">コンピューターに接続するすべてのセッションは、コンピューターに登録されているセッション構成のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3598-197">Every session that connects to the computer must use one of the session configurations that are registered on the computer.</span></span> <span data-ttu-id="b3598-198">すべてのセッション構成へのリモート アクセスを拒否することにより、リモート ユーザーがコンピューターに接続するセッションを確立するのを効果的に防止できます。</span><span class="sxs-lookup"><span data-stu-id="b3598-198">By denying remote access to all session configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

  <span data-ttu-id="b3598-199">Windows PowerShell 2.0 では、は、 `Disable-PSRemoting` すべてのセッション構成のセキュリティ記述子に Deny_All エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b3598-199">In Windows PowerShell 2.0, `Disable-PSRemoting` adds a Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="b3598-200">この設定は、すべてのユーザーがローカルコンピューターに対してユーザー管理セッションを作成できないようにします。</span><span class="sxs-lookup"><span data-stu-id="b3598-200">This setting prevents all users from creating user-managed sessions to the local computer.</span></span> <span data-ttu-id="b3598-201">Windows PowerShell 3.0 では、は、 `Disable-PSRemoting` すべてのセッション構成のセキュリティ記述子に Network_Deny_All エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b3598-201">In Windows PowerShell 3.0, `Disable-PSRemoting` adds a Network_Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="b3598-202">この設定は、他のコンピューター上のユーザーがローカルコンピューター上にユーザー管理セッションを作成できないようにしますが、ローカルコンピューターのユーザーがユーザー管理のループバックセッションを作成することを許可します。</span><span class="sxs-lookup"><span data-stu-id="b3598-202">This setting prevents users on other computers from creating user-managed sessions on the local computer, but allows users of the local computer to create user-managed loopback sessions.</span></span>

  <span data-ttu-id="b3598-203">Windows PowerShell 2.0 で `Disable-PSRemoting` は、はと同じです `Disable-PSSessionConfiguration -Name *` 。</span><span class="sxs-lookup"><span data-stu-id="b3598-203">In Windows PowerShell 2.0, `Disable-PSRemoting` is the equivalent of `Disable-PSSessionConfiguration -Name *`.</span></span> <span data-ttu-id="b3598-204">Windows PowerShell 3.0 以降のリリースで `Disable-PSRemoting` は、はに相当します。 `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span><span class="sxs-lookup"><span data-stu-id="b3598-204">In Windows PowerShell 3.0 and later releases, `Disable-PSRemoting` is the equivalent of `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span></span>

## <span data-ttu-id="b3598-205">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b3598-205">RELATED LINKS</span></span>

[<span data-ttu-id="b3598-206">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3598-206">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="b3598-207">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="b3598-207">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="b3598-208">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3598-208">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="b3598-209">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="b3598-209">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="b3598-210">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3598-210">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="b3598-211">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3598-211">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="b3598-212">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3598-212">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="b3598-213">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="b3598-213">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: 4b40d765002791f45f093c7912b8f9ba58248da9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599320"
---
# <span data-ttu-id="ab58a-102">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab58a-102">New-PSSession</span></span>

## <span data-ttu-id="ab58a-103">概要</span><span class="sxs-lookup"><span data-stu-id="ab58a-103">SYNOPSIS</span></span>
<span data-ttu-id="ab58a-104">ローカル コンピューターまたはリモート コンピューターへの永続的な接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-104">Creates a persistent connection to a local or remote computer.</span></span>

## <span data-ttu-id="ab58a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab58a-105">SYNTAX</span></span>

### <span data-ttu-id="ab58a-106">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="ab58a-106">ComputerName (Default)</span></span>

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="ab58a-107">Uri</span><span class="sxs-lookup"><span data-stu-id="ab58a-107">Uri</span></span>

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="ab58a-108">VMId</span><span class="sxs-lookup"><span data-stu-id="ab58a-108">VMId</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="ab58a-109">VMName</span><span class="sxs-lookup"><span data-stu-id="ab58a-109">VMName</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="ab58a-110">セッション</span><span class="sxs-lookup"><span data-stu-id="ab58a-110">Session</span></span>

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="ab58a-111">ContainerId</span><span class="sxs-lookup"><span data-stu-id="ab58a-111">ContainerId</span></span>

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="ab58a-112">UseWindowsPowerShellParameterSet</span><span class="sxs-lookup"><span data-stu-id="ab58a-112">UseWindowsPowerShellParameterSet</span></span>

```
New-PSSession [-Name <String[]>] [-UseWindowsPowerShell] [<CommonParameters>]
```

### <span data-ttu-id="ab58a-113">SSHHost</span><span class="sxs-lookup"><span data-stu-id="ab58a-113">SSHHost</span></span>

```
New-PSSession [-Name <String[]>] [-Port <Int32>] [-HostName] <String[]> [-UserName <String>]
 [-KeyFilePath <String>] [-SSHTransport] [-Subsystem <String>] [<CommonParameters>]
```

### <span data-ttu-id="ab58a-114">SSHHostHashParam</span><span class="sxs-lookup"><span data-stu-id="ab58a-114">SSHHostHashParam</span></span>

```
New-PSSession [-Name <String[]>] -SSHConnection <Hashtable[]> [<CommonParameters>]
```

## <span data-ttu-id="ab58a-115">Description</span><span class="sxs-lookup"><span data-stu-id="ab58a-115">DESCRIPTION</span></span>

<span data-ttu-id="ab58a-116">コマンドレットでは、 `New-PSSession` ローカルコンピューターまたはリモートコンピューターに PowerShell セッション (**PSSession**) を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-116">The `New-PSSession` cmdlet creates a PowerShell session (**PSSession**) on a local or remote computer.</span></span> <span data-ttu-id="ab58a-117">**PSSession** を作成すると、PowerShell によって、リモートコンピューターへの永続的な接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-117">When you create a **PSSession**, PowerShell establishes a persistent connection to the remote computer.</span></span>

<span data-ttu-id="ab58a-118">**PSSession** を使用して、関数や変数の値など、データを共有する複数のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-118">Use a **PSSession** to run multiple commands that share data, such as a function or the value of a variable.</span></span> <span data-ttu-id="ab58a-119">**PSSession** でコマンドを実行するには、コマンドレットを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-119">To run commands in a **PSSession**, use the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="ab58a-120">**PSSession** を使用してリモートコンピューターと直接対話するには、 `Enter-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-120">To use the **PSSession** to interact directly with a remote computer, use the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="ab58a-121">詳細については、「 [about_PSSessions](about/about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-121">For more information, see [about_PSSessions](about/about_PSSessions.md).</span></span>

<span data-ttu-id="ab58a-122">またはの **ComputerName** パラメーターを使用して、 **PSSession** を作成せずにリモートコンピューターでコマンドを実行でき `Enter-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-122">You can run commands on a remote computer without creating a **PSSession** by using the **ComputerName** parameters of `Enter-PSSession` or `Invoke-Command`.</span></span> <span data-ttu-id="ab58a-123">**ComputerName** パラメーターを使用すると、PowerShell はコマンドに使用される一時的な接続を作成してから閉じます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-123">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that is used for the command and is then closed.</span></span>

<span data-ttu-id="ab58a-124">PowerShell 6.0 以降では、Secure Shell (SSH) を使用して接続を確立し、リモートコンピューター上にセッションを作成することができます (SSH がローカルコンピューターで利用可能で、リモートコンピューターに PowerShell SSH エンドポイントが構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="ab58a-124">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to and create a session on a remote computer, if SSH is available on the local computer and the remote computer is configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="ab58a-125">SSH ベースの PowerShell リモートセッションの利点は、複数のプラットフォーム (Windows、Linux、macOS) で動作できることです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-125">The benefit of an SSH based PowerShell remote session is that it can work across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="ab58a-126">SSH ベースのセッションの場合は、 **HostName** パラメーターまたは **SSHConnection** パラメーターを設定して、リモートコンピューターと関連する接続情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-126">For SSH based sessions you use the **HostName** or **SSHConnection** parameter set to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="ab58a-127">PowerShell SSH リモート処理の設定方法の詳細については、「 [Ssh 経由の Powershell リモート](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)処理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-127">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

> [!NOTE]
> <span data-ttu-id="ab58a-128">Linux または macOS クライアントから、サーバー証明書が信頼されていない HTTPS エンドポイント (自己署名証明書など) で WSMan リモート処理を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="ab58a-128">When using WSMan remoting from a Linux or macOS client with a HTTPS endpoint where the server certificate is not trusted (e.g., a self-signed certificate).</span></span> <span data-ttu-id="ab58a-129">接続を正常に `PSSessionOption` `-SkipCACheck` 確立するには、とを含むを指定する必要があり `-SkipCNCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-129">You must provide a `PSSessionOption` that includes `-SkipCACheck` and `-SkipCNCheck` to successfully establish the connection.</span></span> <span data-ttu-id="ab58a-130">この操作は、サーバー証明書とターゲットシステムへのネットワーク接続を特定できる環境内にある場合にのみ実行してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-130">Only do this if you are in an environment where you can be certain of the server certificate and the network connection to the target system.</span></span>

## <span data-ttu-id="ab58a-131">例</span><span class="sxs-lookup"><span data-stu-id="ab58a-131">EXAMPLES</span></span>

### <span data-ttu-id="ab58a-132">例 1: ローカルコンピューターにセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-132">Example 1: Create a session on the local computer</span></span>

```powershell
$s = New-PSSession
```

<span data-ttu-id="ab58a-133">このコマンドは、ローカルコンピューター上に新しい **pssession** を作成し、その変数に **pssession** を保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-133">This command creates a new **PSSession** on the local computer and saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="ab58a-134">この **PSSession** を使用して、ローカルコンピューターでコマンドを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ab58a-134">You can now use this **PSSession** to run commands on the local computer.</span></span>

### <span data-ttu-id="ab58a-135">例 2: リモートコンピューターにセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-135">Example 2: Create a session on a remote computer</span></span>

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

<span data-ttu-id="ab58a-136">このコマンドは、Server01 コンピューター上に新しい **PSSession** を作成し、変数に保存し `$Server01` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-136">This command creates a new **PSSession** on the Server01 computer and saves it in the `$Server01` variable.</span></span>

<span data-ttu-id="ab58a-137">複数の **PSSession** オブジェクトを作成する場合は、便利な名前の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-137">When creating multiple **PSSession** objects, assign them to variables with useful names.</span></span> <span data-ttu-id="ab58a-138">これは、後続のコマンドで **PSSession** オブジェクトを管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-138">This will help you manage the **PSSession** objects in subsequent commands.</span></span>

### <span data-ttu-id="ab58a-139">例 3: 複数のコンピューターでセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-139">Example 3: Create sessions on multiple computers</span></span>

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

<span data-ttu-id="ab58a-140">このコマンドは、 **ComputerName** パラメーターで指定された各コンピューター上に1つずつ、3つの **PSSession** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-140">This command creates three **PSSession** objects, one on each of the computers specified by the **ComputerName** parameter.</span></span>

<span data-ttu-id="ab58a-141">このコマンドは、代入演算子 (=) を使用して、新しい **PSSession** オブジェクトを変数に代入します: `$s1` 、 `$s2` 、 `$s3` 。</span><span class="sxs-lookup"><span data-stu-id="ab58a-141">The command uses the assignment operator (=) to assign the new **PSSession** objects to variables: `$s1`, `$s2`, `$s3`.</span></span> <span data-ttu-id="ab58a-142">Server01 **pssession** をに、Server02 `$s1` **Pssession** をに、 `$s2` Server03 **pssession** をに割り当て `$s3` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-142">It assigns the Server01 **PSSession** to `$s1`, the Server02 **PSSession** to `$s2`, and the Server03 **PSSession** to `$s3`.</span></span>

<span data-ttu-id="ab58a-143">複数のオブジェクトを一連の変数に割り当てると、PowerShell によって各オブジェクトが系列の変数にそれぞれ割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-143">When you assign multiple objects to a series of variables, PowerShell assigns each object to a variable in the series respectively.</span></span> <span data-ttu-id="ab58a-144">変数よりオブジェクトが多い場合、残りのすべてのオブジェクトが最後の変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-144">If there are more objects than variables, all remaining objects are assigned to the last variable.</span></span> <span data-ttu-id="ab58a-145">オブジェクトより変数が多い場合、残りの変数は空 (null) になります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-145">If there are more variables than objects, the remaining variables are empty (null).</span></span>

### <span data-ttu-id="ab58a-146">例 4: 指定したポートを使用してセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-146">Example 4: Create a session with a specified port</span></span>

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

<span data-ttu-id="ab58a-147">このコマンドは、サーバーポート8081に接続し、SSL プロトコルを使用する Server01 コンピューター上に新しい **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-147">This command creates a new **PSSession** on the Server01 computer that connects to server port 8081 and uses the SSL protocol.</span></span> <span data-ttu-id="ab58a-148">新しい **PSSession** では、E12 という別のセッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-148">The new **PSSession** uses an alternative session configuration called E12.</span></span>

<span data-ttu-id="ab58a-149">ポートを設定する前に、ポート 8081 でリッスンするように、リモートのコンピューター上で WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-149">Before setting the port, you must configure the WinRM listener on the remote computer to listen on port 8081.</span></span> <span data-ttu-id="ab58a-150">詳細については、 **Port** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-150">For more information, see the description of the **Port** parameter.</span></span>

### <span data-ttu-id="ab58a-151">例 5: 既存のセッションに基づいてセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-151">Example 5: Create a session based on an existing session</span></span>

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

<span data-ttu-id="ab58a-152">このコマンドは、既存の **pssession** と同じプロパティを使用して **pssession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-152">This command creates a **PSSession** with the same properties as an existing **PSSession**.</span></span> <span data-ttu-id="ab58a-153">このコマンド形式は、既存の **pssession** のリソースが使い果たされ、要求の一部をオフロードするために新しい **pssession** が必要な場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-153">You can use this command format when the resources of an existing **PSSession** are exhausted and a new **PSSession** is needed to offload some of the demand.</span></span>

<span data-ttu-id="ab58a-154">このコマンドは、の **Session** パラメーターを使用して、 `New-PSSession` 変数に保存されている **PSSession** を指定し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-154">The command uses the **Session** parameter of `New-PSSession` to specify the **PSSession** saved in the `$s` variable.</span></span> <span data-ttu-id="ab58a-155">Domain1\Admin01 ユーザーの資格情報を使用して、コマンドを完成させます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-155">It uses the credentials of the Domain1\Admin01 user to complete the command.</span></span>

### <span data-ttu-id="ab58a-156">例 6: 別のドメイン内のグローバルスコープを持つセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-156">Example 6: Create a session with a global scope in a different domain</span></span>

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

<span data-ttu-id="ab58a-157">この例では、別のドメインにあるコンピューター上のグローバルスコープを持つ **PSSession** を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-157">This example shows how to create a **PSSession** with a global scope on a computer in a different domain.</span></span>

<span data-ttu-id="ab58a-158">既定では、コマンドラインで作成された **pssession** オブジェクトはローカルスコープで作成され、スクリプトで作成された **pssession** オブジェクトはスクリプトスコープを持ちます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-158">By default, **PSSession** objects created at the command line are created with local scope and **PSSession** objects created in a script have script scope.</span></span>

<span data-ttu-id="ab58a-159">グローバルスコープの **pssession** を作成するには、新しい **pssession** を作成し、グローバルスコープにキャストされる変数に **pssession** を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-159">To create a **PSSession** with global scope, create a new **PSSession** and then store the **PSSession** in a variable that is cast to a global scope.</span></span> <span data-ttu-id="ab58a-160">この場合、 `$s` 変数はグローバルスコープにキャストされます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-160">In this case, the `$s` variable is cast to a global scope.</span></span>

<span data-ttu-id="ab58a-161">このコマンドは、**ComputerName** パラメーターを使用してリモート コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-161">The command uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="ab58a-162">コンピューターがユーザーアカウントとは別のドメインにあるため、コンピューターの完全名がユーザーの資格情報と共に指定されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-162">Because the computer is in a different domain than the user account, the full name of the computer is specified together with the credentials of the user.</span></span>

### <span data-ttu-id="ab58a-163">例 7: 多くのコンピューターのセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-163">Example 7: Create sessions for many computers</span></span>

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

<span data-ttu-id="ab58a-164">このコマンドは、Servers.txt ファイルに一覧表示されている200コンピューターそれぞれに **pssession** を作成し、結果の **pssession** を変数に格納し `$rs` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-164">This command creates a **PSSession** on each of the 200 computers listed in the Servers.txt file and it stores the resulting **PSSession** in the `$rs` variable.</span></span> <span data-ttu-id="ab58a-165">**PSSession** オブジェクトのスロットル制限は50です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-165">The **PSSession** objects have a throttle limit of 50.</span></span>

<span data-ttu-id="ab58a-166">このコマンドの形式は、コンピューターの名前がデータベース、スプレッドシート、テキスト ファイル、またはその他のテキストに変換できる形式に格納されている場合、使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-166">You can use this command format when the names of computers are stored in a database, spreadsheet, text file, or other text-convertible format.</span></span>

### <span data-ttu-id="ab58a-167">例 8: URI を使用してセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-167">Example 8: Create a session by using a URI</span></span>

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

<span data-ttu-id="ab58a-168">このコマンドは、Server01 コンピューター上に **PSSession** を作成し、変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-168">This command creates a **PSSession** on the Server01 computer and stores it in the `$s` variable.</span></span> <span data-ttu-id="ab58a-169">**URI** パラメーターを使用して、トランスポートプロトコル、リモートコンピューター、ポート、および代替のセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-169">It uses the **URI** parameter to specify the transport protocol, the remote computer, the port, and an alternate session configuration.</span></span> <span data-ttu-id="ab58a-170">また、 **Credential** パラメーターを使用して、リモートコンピューター上にセッションを作成するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-170">It also uses the **Credential** parameter to specify a user account that has permission to create a session on the remote computer.</span></span>

### <span data-ttu-id="ab58a-171">例 9: 一連のセッションでバックグラウンドジョブを実行する</span><span class="sxs-lookup"><span data-stu-id="ab58a-171">Example 9: Run a background job in a set of sessions</span></span>

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

<span data-ttu-id="ab58a-172">これらのコマンドは、 **pssession** オブジェクトのセットを作成し、各 **pssession** オブジェクトでバックグラウンドジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-172">These commands create a set of **PSSession** objects and then run a background job in each of the **PSSession** objects.</span></span>

<span data-ttu-id="ab58a-173">最初のコマンドは、Servers.txt ファイルに一覧表示されている各コンピューター上に新しい **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-173">The first command creates a new **PSSession** on each of the computers listed in the Servers.txt file.</span></span> <span data-ttu-id="ab58a-174">コマンドレットを使用して `New-PSSession` **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-174">It uses the `New-PSSession` cmdlet to create the **PSSession**.</span></span> <span data-ttu-id="ab58a-175">**ComputerName** パラメーターの値は、コマンドレットを使用して、 `Get-Content` Servers.txt ファイルのコンピューター名の一覧を取得するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-175">The value of the **ComputerName** parameter is a command that uses the `Get-Content` cmdlet to get the list of computer names the Servers.txt file.</span></span>

<span data-ttu-id="ab58a-176">このコマンドは、 **Credential** パラメーターを使用して、ドメイン管理者のアクセス許可を持つ **PSSession** オブジェクトを作成します。また、 **ThrottleLimit** パラメーターを使用して、コマンドの同時接続数を16に制限します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-176">The command uses the **Credential** parameter to create the **PSSession** objects that have the permission of a domain administrator, and it uses the **ThrottleLimit** parameter to limit the command to 16 concurrent connections.</span></span> <span data-ttu-id="ab58a-177">このコマンドは、 **PSSession** オブジェクトを変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-177">The command saves the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="ab58a-178">2番目のコマンドは、コマンドレットの **AsJob** パラメーターを使用して、の `Invoke-Command` `Get-Process PowerShell` 各 **PSSession** オブジェクトでコマンドを実行するバックグラウンドジョブを開始し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-178">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a background job that runs a `Get-Process PowerShell` command in each of the **PSSession** objects in `$s`.</span></span>

<span data-ttu-id="ab58a-179">PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](About/about_Jobs.md) 」および「 [about_Remote_Jobs](About/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-179">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

### <span data-ttu-id="ab58a-180">例 10: URI を使用してコンピューターのセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-180">Example 10: Create a session for a computer by using its URI</span></span>

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

<span data-ttu-id="ab58a-181">このコマンドは、コンピューター名の代わりに URI で指定されたコンピューターに接続する **PSSession** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-181">This command creates a **PSSession** objects that connects to a computer that is specified by a URI instead of a computer name.</span></span>

### <span data-ttu-id="ab58a-182">例 11: セッションオプションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-182">Example 11: Create a session option</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

<span data-ttu-id="ab58a-183">この例では、セッションオプションオブジェクトを作成し、 **sessionoption** パラメーターを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-183">This example shows how to create a session option object and use the **SessionOption** parameter.</span></span>

<span data-ttu-id="ab58a-184">最初のコマンドは、コマンドレットを使用して `New-PSSessionOption` セッションオプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-184">The first command uses the `New-PSSessionOption` cmdlet to create a session option.</span></span> <span data-ttu-id="ab58a-185">結果として得られる **Sessionoption** オブジェクトを変数に保存し `$so` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-185">It saves the resulting **SessionOption** object in the `$so` variable.</span></span>

<span data-ttu-id="ab58a-186">2 番目のコマンドは、新しいセッションでこのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-186">The second command uses the option in a new session.</span></span> <span data-ttu-id="ab58a-187">コマンドは、コマンド `New-PSSession` レットを使用して新しいセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-187">The command uses the `New-PSSession` cmdlet to create a new session.</span></span> <span data-ttu-id="ab58a-188">SessionOption パラメーターの値は、変数内の **sessionoption** オブジェクトです `$so` 。</span><span class="sxs-lookup"><span data-stu-id="ab58a-188">The value of the SessionOption parameter is the **SessionOption** object in the `$so` variable.</span></span>

### <span data-ttu-id="ab58a-189">例 12: SSH を使用してセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-189">Example 12: Create a session using SSH</span></span>

```powershell
New-PSSession -HostName UserA@LinuxServer01
```

<span data-ttu-id="ab58a-190">この例では、Secure Shell (SSH) を使用して新しい **PSSession** を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-190">This example shows how to create a new **PSSession** using Secure Shell (SSH).</span></span> <span data-ttu-id="ab58a-191">SSH がリモートコンピューターでパスワードを要求するように構成されている場合は、パスワードの入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-191">If SSH is configured on the remote computer to prompt for passwords then you will get a password prompt.</span></span> <span data-ttu-id="ab58a-192">それ以外の場合は、SSH キーベースのユーザー認証を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-192">Otherwise you will have to use SSH key based user authentication.</span></span>

### <span data-ttu-id="ab58a-193">例 13: SSH を使用してセッションを作成し、ポートとユーザー認証キーを指定する</span><span class="sxs-lookup"><span data-stu-id="ab58a-193">Example 13: Create a session using SSH and specify the port and user authentication key</span></span>

```powershell
New-PSSession -HostName UserA@LinuxServer01:22 -KeyFilePath c:\<path>\userAKey_rsa
```

<span data-ttu-id="ab58a-194">この例では、Secure Shell (SSH) を使用して **PSSession** を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-194">This example shows how to create a **PSSession** using Secure Shell (SSH).</span></span> <span data-ttu-id="ab58a-195">**Port** パラメーターを使用して、使用するポートを指定し、 **keyfilepath** パラメーターを使用して、リモートコンピューター上のユーザーを識別し、認証するために使用する RSA キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-195">It uses the **Port** parameter to specify the port to use and the **KeyFilePath** parameter to specify an RSA key used to identify and authenticate the user on the remote computer.</span></span>

### <span data-ttu-id="ab58a-196">例 14: SSH を使用して複数のセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="ab58a-196">Example 14: Create multiple sessions using SSH</span></span>

```powershell
$sshConnections = @{ HostName="WinServer1"; UserName="domain\userA"; KeyFilePath="c:\users\UserA\id_rsa" }, @{ HostName="UserB@LinuxServer5"; KeyFilePath="c:\UserB\<path>\id_rsa" }
New-PSSession -SSHConnection $sshConnections
```

<span data-ttu-id="ab58a-197">この例では、Secure Shell (SSH) と **SSHConnection** パラメーターセットを使用して複数のセッションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-197">This example shows how to create multiple sessions using Secure Shell (SSH) and the **SSHConnection** parameter set.</span></span> <span data-ttu-id="ab58a-198">**SSHConnection** パラメーターは、各セッションの接続情報を含むハッシュテーブルの配列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-198">The **SSHConnection** parameter takes an array of hash tables that contain connection information for each session.</span></span> <span data-ttu-id="ab58a-199">この例では、ターゲットのリモートコンピューターで、キーベースのユーザー認証をサポートするように SSH が構成されている必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-199">Note that this example requires that the target remote computers have SSH configured to support key based user authentication.</span></span>

## <span data-ttu-id="ab58a-200">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab58a-200">PARAMETERS</span></span>

### <span data-ttu-id="ab58a-201">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="ab58a-201">-AllowRedirection</span></span>

<span data-ttu-id="ab58a-202">このコマンドレットがこの接続を代替 Uniform Resource Identifier (URI) にリダイレクトできることを示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-202">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="ab58a-203">**ConnectionURI** パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトするように指示を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-203">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="ab58a-204">既定では、PowerShell は接続をリダイレクトしませんが、このパラメーターを使用して接続をリダイレクトできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-204">By default, PowerShell does not redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="ab58a-205">また、**MaximumConnectionRedirectionCount** セッション オプション値を変更することで、接続をリダイレクトする回数を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-205">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="ab58a-206">コマンドレットの **Maximumredirection** パラメーターを使用する `New-PSSessionOption` か、 **$PSSessionOption** preference 変数の **MaximumConnectionRedirectionCount** プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-206">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="ab58a-207">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-207">The default value is 5.</span></span>

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

### <span data-ttu-id="ab58a-208">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="ab58a-208">-ApplicationName</span></span>

<span data-ttu-id="ab58a-209">接続 URI のアプリケーション名セグメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-209">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="ab58a-210">このパラメーターは、このコマンドの **ConnectionURI** パラメーターを使用しないときに、アプリケーション名を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-210">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="ab58a-211">既定値は、 `$PSSessionApplicationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-211">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="ab58a-212">このユーザー設定変数が定義されていない場合、既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-212">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="ab58a-213">この値はほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="ab58a-213">This value is appropriate for most uses.</span></span> <span data-ttu-id="ab58a-214">詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-214">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="ab58a-215">WinRM サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-215">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="ab58a-216">このパラメーターの値は、リモート コンピューター上のリスナーの **URLPrefix** プロパティの値に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-216">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="ab58a-217">-認証</span><span class="sxs-lookup"><span data-stu-id="ab58a-217">-Authentication</span></span>

<span data-ttu-id="ab58a-218">ユーザーの資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-218">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="ab58a-219">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-219">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ab58a-220">Default</span><span class="sxs-lookup"><span data-stu-id="ab58a-220">Default</span></span>
- <span data-ttu-id="ab58a-221">Basic</span><span class="sxs-lookup"><span data-stu-id="ab58a-221">Basic</span></span>
- <span data-ttu-id="ab58a-222">Credssp</span><span class="sxs-lookup"><span data-stu-id="ab58a-222">Credssp</span></span>
- <span data-ttu-id="ab58a-223">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="ab58a-223">Digest</span></span>
- <span data-ttu-id="ab58a-224">Kerberos</span><span class="sxs-lookup"><span data-stu-id="ab58a-224">Kerberos</span></span>
- <span data-ttu-id="ab58a-225">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="ab58a-225">Negotiate</span></span>
- <span data-ttu-id="ab58a-226">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="ab58a-226">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="ab58a-227">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-227">The default value is Default.</span></span>

<span data-ttu-id="ab58a-228">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-228">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="ab58a-229">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="ab58a-229">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="ab58a-230">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-230">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="ab58a-231">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-231">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="ab58a-232">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="ab58a-232">-CertificateThumbprint</span></span>

<span data-ttu-id="ab58a-233">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-233">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="ab58a-234">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-234">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="ab58a-235">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-235">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="ab58a-236">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-236">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="ab58a-237">証明書を取得するに `Get-Item` は、 `Get-ChildItem` PowerShell Cert: ドライブのまたはコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-237">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="ab58a-238">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="ab58a-238">-ComputerName</span></span>

<span data-ttu-id="ab58a-239">コンピューターの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-239">Specifies an array of names of computers.</span></span> <span data-ttu-id="ab58a-240">このコマンドレットは、指定されたコンピューターへの永続的な接続 (**PSSession**) を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-240">This cmdlet creates a persistent connection (**PSSession**) to the specified computer.</span></span> <span data-ttu-id="ab58a-241">複数のコンピューター名を入力すると、は、 `New-PSSession` コンピューターごとに1つずつ、複数の **PSSession** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-241">If you enter multiple computer names, `New-PSSession` creates multiple **PSSession** objects, one for each computer.</span></span> <span data-ttu-id="ab58a-242">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-242">The default is the local computer.</span></span>

<span data-ttu-id="ab58a-243">1 台または複数のリモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-243">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="ab58a-244">ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-244">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="ab58a-245">コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名が必要です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-245">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="ab58a-246">パイプを使用してコンピューター名を引用符で囲むこともでき `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-246">You can also pipe a computer name, in quotation marks, to `New-PSSession`.</span></span>

<span data-ttu-id="ab58a-247">**ComputerName** パラメーターの値に IP アドレスを使用するには、コマンドに **Credential** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-247">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="ab58a-248">また、HTTPS トランスポート用にコンピューターを構成するか、リモート コンピューターの IP アドレスをローカル コンピューター上の WinRM TrustedHosts 一覧に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-248">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="ab58a-249">TrustedHosts の一覧にコンピューター名を追加する手順については、 [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md)の「信頼されたホストの一覧にコンピューターを追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-249">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="ab58a-250">ローカルコンピューターを **ComputerName** パラメーターの値に含めるには、[管理者として実行] オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-250">To include the local computer in the value of the **ComputerName** parameter, start Windows PowerShell by using the Run as administrator option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-251">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="ab58a-251">-ConfigurationName</span></span>

<span data-ttu-id="ab58a-252">新しい **PSSession** に使用するセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-252">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="ab58a-253">セッション構成の構成名または完全修飾リソース URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-253">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="ab58a-254">構成名だけを指定した場合は、次のスキーマ URI が付加され `http://schemas.microsoft.com/PowerShell` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-254">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="ab58a-255">セッションのセッション構成は、リモート コンピューター上にあります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-255">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="ab58a-256">指定したセッション構成がリモート コンピューター上に存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-256">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="ab58a-257">既定値は、 `$PSSessionConfigurationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-257">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="ab58a-258">このユーザー設定変数が設定されていない場合、既定値は Microsoft.PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-258">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="ab58a-259">詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-259">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

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

### <span data-ttu-id="ab58a-260">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="ab58a-260">-ConnectionUri</span></span>

<span data-ttu-id="ab58a-261">セッションの接続エンドポイントを定義する URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-261">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="ab58a-262">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-262">The URI must be fully qualified.</span></span> <span data-ttu-id="ab58a-263">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-263">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="ab58a-264">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-264">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="ab58a-265">**ConnectionURI** を指定しなかった場合は、**UseSSL**、**ComputerName**、**Port**、および **ApplicationName** パラメーターを使用して、**ConnectionURI** 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-265">If you do not specify a **ConnectionURI**, you can use the **UseSSL**, **ComputerName**, **Port**, and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="ab58a-266">URI のトランスポート セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-266">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="ab58a-267">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準ポート80で HTTP 用および 443 (HTTPS 用) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-267">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="ab58a-268">PowerShell リモート処理に既定のポートを使用するには、HTTP の場合はポート5985、HTTPS の場合は5986を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-268">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="ab58a-269">対象のコンピューターが接続を別の URI にリダイレクトする場合、コマンドで **Allowredirection** パラメーターを使用しない限り、PowerShell によってリダイレクトが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-269">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: Uri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-270">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="ab58a-270">-ContainerId</span></span>

<span data-ttu-id="ab58a-271">コンテナーの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-271">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="ab58a-272">このコマンドレットは、指定された各コンテナーとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-272">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="ab58a-273">`docker ps`コンテナー id の一覧を取得するには、コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-273">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="ab58a-274">詳細については、 [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) コマンドのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-274">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-275">-Credential</span><span class="sxs-lookup"><span data-stu-id="ab58a-275">-Credential</span></span>

<span data-ttu-id="ab58a-276">このアクションを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-276">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="ab58a-277">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-277">The default is the current user.</span></span>

<span data-ttu-id="ab58a-278">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-278">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ab58a-279">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-279">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="ab58a-280">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-280">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="ab58a-281">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-281">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-282">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="ab58a-282">-EnableNetworkAccess</span></span>

<span data-ttu-id="ab58a-283">このコマンドレットが、ループバックセッションに対話型セキュリティトークンを追加することを示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-283">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="ab58a-284">対話型トークンを使用すると、他のコンピューターからデータを取得するコマンドをループバック セッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-284">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="ab58a-285">たとえば、リモート コンピューターからローカル コンピューターに XML ファイルをコピーするコマンドをセッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-285">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="ab58a-286">ループバックセッションは、同じコンピューター上で発生して終了する **PSSession** です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-286">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="ab58a-287">ループバックセッションを作成するには、 **ComputerName** パラメーターを省略するか、値をドット (.)、localhost、またはローカルコンピューターの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-287">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (.), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="ab58a-288">既定では、このコマンドレットはネットワークトークンを使用してループバックセッションを作成しますが、これにより、リモートコンピューターを認証するための十分なアクセス許可が与えられない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-288">By default, this cmdlet creates loopback sessions by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="ab58a-289">**EnableNetworkAccess** パラメーターは、ループバック セッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-289">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="ab58a-290">リモートコンピューターでセッションを作成するときに **EnableNetworkAccess** を使用すると、コマンドは成功しますが、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-290">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="ab58a-291">また、 **認証** パラメーターの CredSSP 値を使用して、ループバックセッションでリモートアクセスを有効にすることもできます。これにより、セッションの資格情報が他のコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-291">You can also enable remote access in a loopback session by using the CredSSP value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="ab58a-292">悪意のあるアクセスからコンピューターを保護するために、 **EnableNetworkAccess** パラメーターを使用して作成された、対話型トークンを持つ切断されたループバックセッションは、セッションが作成されたコンピューターからのみ再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-292">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="ab58a-293">CredSSP 認証を使用するセッションが切断された場合には、他のコンピューターから再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-293">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="ab58a-294">詳細については、「`Disconnect-PSSession`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-294">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="ab58a-295">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab58a-295">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri, Session
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-296">-HostName</span><span class="sxs-lookup"><span data-stu-id="ab58a-296">-HostName</span></span>

<span data-ttu-id="ab58a-297">Secure Shell (SSH) ベースの接続に使用するコンピューター名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-297">Specifies an array of computer names for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="ab58a-298">これは ComputerName パラメーターと似ていますが、リモートコンピューターへの接続は Windows WinRM ではなく SSH を使用して行われる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-298">This is similar to the ComputerName parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span>

<span data-ttu-id="ab58a-299">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab58a-299">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-300">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="ab58a-300">-KeyFilePath</span></span>

<span data-ttu-id="ab58a-301">リモートコンピューター上のユーザーを認証するために Secure Shell (SSH) によって使用されるキーファイルパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-301">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="ab58a-302">SSH では、基本パスワード認証の代わりに、秘密キーまたは公開キーを使用してユーザー認証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-302">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="ab58a-303">リモートコンピューターがキー認証用に構成されている場合、このパラメーターを使用して、ユーザーを識別するキーを提供できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-303">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="ab58a-304">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab58a-304">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="ab58a-305">-Name</span><span class="sxs-lookup"><span data-stu-id="ab58a-305">-Name</span></span>

<span data-ttu-id="ab58a-306">**PSSession** のフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-306">Specifies a friendly name for the **PSSession**.</span></span>

<span data-ttu-id="ab58a-307">やなどの他のコマンドレットを使用する場合は、名前を使用して **PSSession** を参照でき `Get-PSSession` `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-307">You can use the name to refer to the **PSSession** when you use other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="ab58a-308">名前は、コンピューターや現在のセッションで一意である必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-308">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-309">-Port</span><span class="sxs-lookup"><span data-stu-id="ab58a-309">-Port</span></span>

<span data-ttu-id="ab58a-310">この接続に使用するリモート コンピューター上のネットワーク ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-310">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="ab58a-311">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-311">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="ab58a-312">既定のポートは5985で、これは HTTP 用の WinRM ポート、および HTTPS 用の WinRM ポートである5986です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-312">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="ab58a-313">別のポートを使用する前に、そのポートでリッスンするようにリモートコンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-313">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="ab58a-314">リスナーを構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-314">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="ab58a-315">必要な場合を除き、**Port** パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-315">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="ab58a-316">コマンドのポート設定は、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-316">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="ab58a-317">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-317">An alternate port setting might prevent the command from running on all computers.</span></span>

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

### <span data-ttu-id="ab58a-318">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ab58a-318">-RunAsAdministrator</span></span>

<span data-ttu-id="ab58a-319">**PSSession** が管理者として実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-319">Indicates that the **PSSession** runs as administrator.</span></span>

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

### <span data-ttu-id="ab58a-320">-セッション</span><span class="sxs-lookup"><span data-stu-id="ab58a-320">-Session</span></span>

<span data-ttu-id="ab58a-321">このコマンドレットが新しい **pssession** のモデルとして使用する **pssession** オブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-321">Specifies an array of **PSSession** objects that this cmdlet uses as a model for the new **PSSession**.</span></span> <span data-ttu-id="ab58a-322">このパラメーターは、指定された **pssession** オブジェクトと同じプロパティを持つ新しい **PSSession** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-322">This parameter creates new **PSSession** objects that have the same properties as the specified **PSSession** objects.</span></span>

<span data-ttu-id="ab58a-323">**Pssession** オブジェクトを含む変数、  `New-PSSession` またはコマンドやコマンドなどの pssession オブジェクトを作成または取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-323">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="ab58a-324">結果として得られる **PSSession** オブジェクトのコンピューター名、アプリケーション名、接続 URI、ポート、構成名、スロットル制限、および SECURE SOCKETS LAYER (SSL) 値は元のものと同じですが、表示名、ID、インスタンス ID (GUID) は異なります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-324">The resulting **PSSession** objects have the same computer name, application name, connection URI, port, configuration name, throttle limit, and Secure Sockets Layer (SSL) value as the originals, but they have a different display name, ID, and instance ID (GUID).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-325">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="ab58a-325">-SessionOption</span></span>

<span data-ttu-id="ab58a-326">セッションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-326">Specifies advanced options for the session.</span></span> <span data-ttu-id="ab58a-327">コマンドレットを使用して作成する **sessionoption** オブジェクト、 `New-PSSessionOption` またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-327">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="ab58a-328">オプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-328">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="ab58a-329">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-329">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="ab58a-330">セッションオプションの値は、ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-330">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="ab58a-331">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-331">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="ab58a-332">既定値を含むセッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="ab58a-332">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="ab58a-333">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-333">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="ab58a-334">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-334">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="ab58a-335">-SSHConnection</span><span class="sxs-lookup"><span data-stu-id="ab58a-335">-SSHConnection</span></span>

<span data-ttu-id="ab58a-336">このパラメーターは、ハッシュテーブルの配列を受け取ります。各ハッシュテーブルには、Secure Shell (SSH) 接続を確立するために必要な1つ以上の接続パラメーター (HostName、Port、UserName、KeyFilePath) が格納されています。</span><span class="sxs-lookup"><span data-stu-id="ab58a-336">This parameter takes an array of hashtables where each hashtable contains one or more connection parameters needed to establish a Secure Shell (SSH) connection (HostName, Port, UserName, KeyFilePath).</span></span>

<span data-ttu-id="ab58a-337">ハッシュテーブルの接続パラメーターは、 **HostName** パラメーターセットに対して定義されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-337">The hashtable connection parameters are the same as defined for the **HostName** parameter set.</span></span>

<span data-ttu-id="ab58a-338">**SSHConnection** パラメーターは、各セッションが異なる接続情報を必要とする複数のセッションを作成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-338">The **SSHConnection** parameter is useful for creating multiple sessions where each session requires different connection information.</span></span>

<span data-ttu-id="ab58a-339">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab58a-339">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-340">-SSHTransport</span><span class="sxs-lookup"><span data-stu-id="ab58a-340">-SSHTransport</span></span>

<span data-ttu-id="ab58a-341">リモート接続が Secure Shell (SSH) を使用して確立されることを示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-341">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="ab58a-342">既定では、PowerShell は Windows WinRM を使用してリモートコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-342">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="ab58a-343">このスイッチは、SSH ベースのリモート接続を確立するために、ホスト名パラメーターセットを使用するように PowerShell を強制します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-343">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="ab58a-344">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab58a-344">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="ab58a-345">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="ab58a-345">-ThrottleLimit</span></span>

<span data-ttu-id="ab58a-346">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-346">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="ab58a-347">このパラメーターを省略した場合、または値 0 (ゼロ) を入力した場合は、既定値の 32 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-347">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span>

<span data-ttu-id="ab58a-348">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-348">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, Uri, VMId, VMName, Session, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-349">-UserName</span><span class="sxs-lookup"><span data-stu-id="ab58a-349">-UserName</span></span>

<span data-ttu-id="ab58a-350">リモートコンピューターでセッションを作成するために使用するアカウントのユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-350">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="ab58a-351">ユーザー認証方法は、リモートコンピューターで Secure Shell (SSH) がどのように構成されているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-351">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="ab58a-352">SSH が基本パスワード認証用に構成されている場合は、ユーザーのパスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-352">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="ab58a-353">SSH がキーベースのユーザー認証用に構成されている場合、KeyFilePath パラメーターを使用してキーファイルのパスを指定することができます。パスワードプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-353">If SSH is configured for key based user authentication then a key file path can be provided via the KeyFilePath parameter and no password prompt will occur.</span></span> <span data-ttu-id="ab58a-354">クライアントユーザーキーファイルが SSH の既知の場所にある場合、キーベースの認証に KeyFilePath パラメーターは必要ありません。ユーザー認証は、ユーザー名に基づいて自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-354">Note that if the client user key file is located in an SSH known location then the KeyFilePath parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="ab58a-355">詳細については、キーベースのユーザー認証に関する SSH ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-355">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="ab58a-356">これは必須のパラメーターではありません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-356">This is not a required parameter.</span></span> <span data-ttu-id="ab58a-357">UserName パラメーターが指定されていない場合は、現在のログオンユーザー名が接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-357">If no UserName parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="ab58a-358">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab58a-358">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="ab58a-359">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="ab58a-359">-UseSSL</span></span>

<span data-ttu-id="ab58a-360">このコマンドレットが SSL プロトコルを使用してリモートコンピューターへの接続を確立することを示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-360">Indicates that this cmdlet uses the SSL protocol to establish a connection to the remote computer.</span></span>
<span data-ttu-id="ab58a-361">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-361">By default, SSL is not used.</span></span>

<span data-ttu-id="ab58a-362">WS-Management は、ネットワーク経由で送信されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-362">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="ab58a-363">**UseSSL** パラメーターは、HTTP 接続ではなく HTTPS 接続を介してデータを送信する追加の保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-363">The **UseSSL** parameter offers an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="ab58a-364">このパラメーターを使用しても、コマンドに使用されているポートで SSL を使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-364">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="ab58a-365">-VMId</span><span class="sxs-lookup"><span data-stu-id="ab58a-365">-VMId</span></span>

<span data-ttu-id="ab58a-366">仮想マシンの ID の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-366">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="ab58a-367">このコマンドレットは、指定された各仮想マシンとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-367">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="ab58a-368">使用可能な仮想マシンを表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-368">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-369">-VMName</span><span class="sxs-lookup"><span data-stu-id="ab58a-369">-VMName</span></span>

<span data-ttu-id="ab58a-370">仮想マシンの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-370">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="ab58a-371">このコマンドレットは、指定された各仮想マシンとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-371">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="ab58a-372">使用可能な仮想マシンを表示するには、コマンドレットを使用し `Get-VM` ます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-372">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-373">-サブシステム</span><span class="sxs-lookup"><span data-stu-id="ab58a-373">-Subsystem</span></span>

<span data-ttu-id="ab58a-374">新しい **PSSession** に使用する SSH サブシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-374">Specifies the SSH subsystem used for the new **PSSession**.</span></span>

<span data-ttu-id="ab58a-375">これは sshd_config で定義されているターゲットで使用するサブシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-375">This specifies the subsystem to use on the target as defined in sshd_config.</span></span>
<span data-ttu-id="ab58a-376">サブシステムは、定義済みのパラメーターを使用して特定のバージョンの PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-376">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span>
<span data-ttu-id="ab58a-377">指定したサブシステムがリモートコンピューターに存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-377">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="ab58a-378">このパラメーターを使用しない場合、既定値は ' powershell ' サブシステムになります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-378">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

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

### <span data-ttu-id="ab58a-379">-UseWindowsPowerShell</span><span class="sxs-lookup"><span data-stu-id="ab58a-379">-UseWindowsPowerShell</span></span>

<span data-ttu-id="ab58a-380">{{UseWindowsPowerShell の説明を入力}}</span><span class="sxs-lookup"><span data-stu-id="ab58a-380">{{ Fill UseWindowsPowerShell Description }}</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseWindowsPowerShellParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab58a-381">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ab58a-381">CommonParameters</span></span>

<span data-ttu-id="ab58a-382">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-382">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab58a-383">詳細については、「about_CommonParameters」 (https://go.microsoft.com/fwlink/?LinkID=113216) ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-383">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab58a-384">入力</span><span class="sxs-lookup"><span data-stu-id="ab58a-384">INPUTS</span></span>

### <span data-ttu-id="ab58a-385">System.string、System.string、system......。</span><span class="sxs-lookup"><span data-stu-id="ab58a-385">System.String, System.URI, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="ab58a-386">パイプを使用して、文字列、URI、またはセッションオブジェクトをこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-386">You can pipe a string, URI, or session object to this cmdlet.</span></span>

## <span data-ttu-id="ab58a-387">出力</span><span class="sxs-lookup"><span data-stu-id="ab58a-387">OUTPUTS</span></span>

### <span data-ttu-id="ab58a-388">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="ab58a-388">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="ab58a-389">注</span><span class="sxs-lookup"><span data-stu-id="ab58a-389">NOTES</span></span>

- <span data-ttu-id="ab58a-390">このコマンドレットは、PowerShell リモート処理インフラストラクチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-390">This cmdlet uses the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="ab58a-391">このコマンドレットを使用するには、ローカルコンピューターとリモートコンピューターを PowerShell リモート処理用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-391">To use this cmdlet, the local computer and any remote computers must be configured for PowerShell remoting.</span></span> <span data-ttu-id="ab58a-392">詳細については、「[about_Remote_Requirements](About/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-392">For more information, see [about_Remote_Requirements](About/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="ab58a-393">ローカルコンピューター上に **PSSession** を作成するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-393">To create a **PSSession** on the local computer, start PowerShell with the Run as administrator option.</span></span>
- <span data-ttu-id="ab58a-394">**Pssession** が終了したら、コマンドレットを使用して `Remove-PSSession` **pssession** を削除し、そのリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-394">When you are finished with the **PSSession**, use the `Remove-PSSession` cmdlet to delete the **PSSession** and release its resources.</span></span>
- <span data-ttu-id="ab58a-395">**ホスト名** と **SSHConnection** パラメーターセットは、PowerShell 6.0 以降に含まれていました。</span><span class="sxs-lookup"><span data-stu-id="ab58a-395">The **HostName** and **SSHConnection** parameter sets were included starting with PowerShell 6.0.</span></span>
  <span data-ttu-id="ab58a-396">これらは、Secure Shell (SSH) に基づいて PowerShell リモート処理を提供するために追加されました。</span><span class="sxs-lookup"><span data-stu-id="ab58a-396">They were added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="ab58a-397">複数のプラットフォーム (Windows、Linux、macOS) では SSH と PowerShell の両方がサポートされており、powershell リモート処理は PowerShell と SSH がインストールおよび構成されているこれらのプラットフォーム上で機能します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-397">Both SSH and PowerShell are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting will work over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="ab58a-398">これは、WinRM に基づく以前の Windows のみのリモート処理とは別のものであり、WinRM 固有の機能の多くは適用されません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-398">This is separate from the previous Windows only remoting that is based on WinRM and much of the WinRM specific features and limitations do not apply.</span></span> <span data-ttu-id="ab58a-399">たとえば、WinRM ベースのクォータ、セッションオプション、カスタムエンドポイントの構成、および切断/再接続機能は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-399">For example WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="ab58a-400">PowerShell SSH リモート処理の設定方法の詳細については、「 [Ssh 経由の Powershell リモート](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)処理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-400">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <span data-ttu-id="ab58a-401">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ab58a-401">RELATED LINKS</span></span>

[<span data-ttu-id="ab58a-402">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab58a-402">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="ab58a-403">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab58a-403">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="ab58a-404">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab58a-404">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="ab58a-405">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab58a-405">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="ab58a-406">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab58a-406">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="ab58a-407">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="ab58a-407">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="ab58a-408">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab58a-408">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="ab58a-409">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="ab58a-409">Remove-PSSession</span></span>](Remove-PSSession.md)


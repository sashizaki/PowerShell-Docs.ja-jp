---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: 1835d0bd4294161f83728a63e8da8fc64c2bf9e0
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218192"
---
# <span data-ttu-id="0178d-103">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="0178d-103">New-PSSession</span></span>

## <span data-ttu-id="0178d-104">概要</span><span class="sxs-lookup"><span data-stu-id="0178d-104">SYNOPSIS</span></span>
<span data-ttu-id="0178d-105">ローカル コンピューターまたはリモート コンピューターへの永続的な接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-105">Creates a persistent connection to a local or remote computer.</span></span>

## <span data-ttu-id="0178d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0178d-106">SYNTAX</span></span>

### <span data-ttu-id="0178d-107">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="0178d-107">ComputerName (Default)</span></span>

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="0178d-108">Uri</span><span class="sxs-lookup"><span data-stu-id="0178d-108">Uri</span></span>

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="0178d-109">VMId</span><span class="sxs-lookup"><span data-stu-id="0178d-109">VMId</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="0178d-110">VMName</span><span class="sxs-lookup"><span data-stu-id="0178d-110">VMName</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="0178d-111">Session</span><span class="sxs-lookup"><span data-stu-id="0178d-111">Session</span></span>

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="0178d-112">ContainerId</span><span class="sxs-lookup"><span data-stu-id="0178d-112">ContainerId</span></span>

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="0178d-113">Description</span><span class="sxs-lookup"><span data-stu-id="0178d-113">DESCRIPTION</span></span>

<span data-ttu-id="0178d-114">コマンドレットでは、 `New-PSSession` ローカルコンピューターまたはリモートコンピューターに PowerShell セッション ( **PSSession** ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-114">The `New-PSSession` cmdlet creates a PowerShell session ( **PSSession** ) on a local or remote computer.</span></span> <span data-ttu-id="0178d-115">**PSSession** を作成すると、PowerShell によって、リモートコンピューターへの永続的な接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-115">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span>

<span data-ttu-id="0178d-116">**PSSession** を使用して、関数や変数の値など、データを共有する複数のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0178d-116">Use a **PSSession** to run multiple commands that share data, such as a function or the value of a variable.</span></span> <span data-ttu-id="0178d-117">**PSSession** でコマンドを実行するには、コマンドレットを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-117">To run commands in a **PSSession** , use the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="0178d-118">**PSSession** を使用してリモートコンピューターと直接対話するには、 `Enter-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0178d-118">To use the **PSSession** to interact directly with a remote computer, use the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="0178d-119">詳細については、「 [about_PSSessions](about/about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-119">For more information, see [about_PSSessions](about/about_PSSessions.md).</span></span>

<span data-ttu-id="0178d-120">またはの **ComputerName** パラメーターを使用して、 **PSSession** を作成せずにリモートコンピューターでコマンドを実行でき `Enter-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-120">You can run commands on a remote computer without creating a **PSSession** by using the **ComputerName** parameters of `Enter-PSSession` or `Invoke-Command`.</span></span> <span data-ttu-id="0178d-121">**ComputerName** パラメーターを使用すると、PowerShell はコマンドに使用される一時的な接続を作成してから閉じます。</span><span class="sxs-lookup"><span data-stu-id="0178d-121">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that is used for the command and is then closed.</span></span>

## <span data-ttu-id="0178d-122">例</span><span class="sxs-lookup"><span data-stu-id="0178d-122">EXAMPLES</span></span>

### <span data-ttu-id="0178d-123">例 1: ローカルコンピューターにセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-123">Example 1: Create a session on the local computer</span></span>

```powershell
$s = New-PSSession
```

<span data-ttu-id="0178d-124">このコマンドは、ローカルコンピューター上に新しい **pssession** を作成し、その変数に **pssession** を保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-124">This command creates a new **PSSession** on the local computer and saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="0178d-125">この **PSSession** を使用して、ローカルコンピューターでコマンドを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0178d-125">You can now use this **PSSession** to run commands on the local computer.</span></span>

### <span data-ttu-id="0178d-126">例 2: リモートコンピューターにセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-126">Example 2: Create a session on a remote computer</span></span>

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

<span data-ttu-id="0178d-127">このコマンドは、Server01 コンピューター上に新しい **PSSession** を作成し、変数に保存し `$Server01` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-127">This command creates a new **PSSession** on the Server01 computer and saves it in the `$Server01` variable.</span></span>

<span data-ttu-id="0178d-128">複数の **PSSession** オブジェクトを作成する場合は、便利な名前の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0178d-128">When creating multiple **PSSession** objects, assign them to variables with useful names.</span></span> <span data-ttu-id="0178d-129">これは、後続のコマンドで **PSSession** オブジェクトを管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0178d-129">This will help you manage the **PSSession** objects in subsequent commands.</span></span>

### <span data-ttu-id="0178d-130">例 3: 複数のコンピューターでセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-130">Example 3: Create sessions on multiple computers</span></span>

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

<span data-ttu-id="0178d-131">このコマンドは、 **ComputerName** パラメーターで指定された各コンピューター上に1つずつ、3つの **PSSession** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-131">This command creates three **PSSession** objects, one on each of the computers specified by the **ComputerName** parameter.</span></span>

<span data-ttu-id="0178d-132">このコマンドは、代入演算子 (=) を使用して、新しい **PSSession** オブジェクトを変数に代入します: `$s1` 、 `$s2` 、 `$s3` 。</span><span class="sxs-lookup"><span data-stu-id="0178d-132">The command uses the assignment operator (=) to assign the new **PSSession** objects to variables: `$s1`, `$s2`, `$s3`.</span></span> <span data-ttu-id="0178d-133">Server01 **pssession** をに、Server02 `$s1` **Pssession** をに、 `$s2` Server03 **pssession** をに割り当て `$s3` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-133">It assigns the Server01 **PSSession** to `$s1`, the Server02 **PSSession** to `$s2`, and the Server03 **PSSession** to `$s3`.</span></span>

<span data-ttu-id="0178d-134">複数のオブジェクトを一連の変数に割り当てると、PowerShell によって各オブジェクトが系列の変数にそれぞれ割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0178d-134">When you assign multiple objects to a series of variables, PowerShell assigns each object to a variable in the series respectively.</span></span> <span data-ttu-id="0178d-135">変数よりオブジェクトが多い場合、残りのすべてのオブジェクトが最後の変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-135">If there are more objects than variables, all remaining objects are assigned to the last variable.</span></span> <span data-ttu-id="0178d-136">オブジェクトより変数が多い場合、残りの変数は空 (null) になります。</span><span class="sxs-lookup"><span data-stu-id="0178d-136">If there are more variables than objects, the remaining variables are empty (null).</span></span>

### <span data-ttu-id="0178d-137">例 4: 指定したポートを使用してセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-137">Example 4: Create a session with a specified port</span></span>

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

<span data-ttu-id="0178d-138">このコマンドは、サーバーポート8081に接続し、SSL プロトコルを使用する Server01 コンピューター上に新しい **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-138">This command creates a new **PSSession** on the Server01 computer that connects to server port 8081 and uses the SSL protocol.</span></span> <span data-ttu-id="0178d-139">新しい **PSSession** では、E12 という別のセッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="0178d-139">The new **PSSession** uses an alternative session configuration called E12.</span></span>

<span data-ttu-id="0178d-140">ポートを設定する前に、ポート 8081 でリッスンするように、リモートのコンピューター上で WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-140">Before setting the port, you must configure the WinRM listener on the remote computer to listen on port 8081.</span></span> <span data-ttu-id="0178d-141">詳細については、 **Port** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-141">For more information, see the description of the **Port** parameter.</span></span>

### <span data-ttu-id="0178d-142">例 5: 既存のセッションに基づいてセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-142">Example 5: Create a session based on an existing session</span></span>

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

<span data-ttu-id="0178d-143">このコマンドは、既存の **pssession** と同じプロパティを使用して **pssession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-143">This command creates a **PSSession** with the same properties as an existing **PSSession**.</span></span> <span data-ttu-id="0178d-144">このコマンド形式は、既存の **pssession** のリソースが使い果たされ、要求の一部をオフロードするために新しい **pssession** が必要な場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0178d-144">You can use this command format when the resources of an existing **PSSession** are exhausted and a new **PSSession** is needed to offload some of the demand.</span></span>

<span data-ttu-id="0178d-145">このコマンドは、の **Session** パラメーターを使用して、 `New-PSSession` 変数に保存されている **PSSession** を指定し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-145">The command uses the **Session** parameter of `New-PSSession` to specify the **PSSession** saved in the `$s` variable.</span></span> <span data-ttu-id="0178d-146">Domain1\Admin01 ユーザーの資格情報を使用して、コマンドを完成させます。</span><span class="sxs-lookup"><span data-stu-id="0178d-146">It uses the credentials of the Domain1\Admin01 user to complete the command.</span></span>

### <span data-ttu-id="0178d-147">例 6: 別のドメイン内のグローバルスコープを持つセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-147">Example 6: Create a session with a global scope in a different domain</span></span>

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

<span data-ttu-id="0178d-148">この例では、別のドメインにあるコンピューター上のグローバルスコープを持つ **PSSession** を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0178d-148">This example shows how to create a **PSSession** with a global scope on a computer in a different domain.</span></span>

<span data-ttu-id="0178d-149">既定では、コマンドラインで作成された **pssession** オブジェクトはローカルスコープで作成され、スクリプトで作成された **pssession** オブジェクトはスクリプトスコープを持ちます。</span><span class="sxs-lookup"><span data-stu-id="0178d-149">By default, **PSSession** objects created at the command line are created with local scope and **PSSession** objects created in a script have script scope.</span></span>

<span data-ttu-id="0178d-150">グローバルスコープの **pssession** を作成するには、新しい **pssession** を作成し、グローバルスコープにキャストされる変数に **pssession** を格納します。</span><span class="sxs-lookup"><span data-stu-id="0178d-150">To create a **PSSession** with global scope, create a new **PSSession** and then store the **PSSession** in a variable that is cast to a global scope.</span></span> <span data-ttu-id="0178d-151">この場合、 `$s` 変数はグローバルスコープにキャストされます。</span><span class="sxs-lookup"><span data-stu-id="0178d-151">In this case, the `$s` variable is cast to a global scope.</span></span>

<span data-ttu-id="0178d-152">このコマンドは、 **ComputerName** パラメーターを使用してリモート コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-152">The command uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="0178d-153">コンピューターがユーザーアカウントとは別のドメインにあるため、コンピューターの完全名がユーザーの資格情報と共に指定されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-153">Because the computer is in a different domain than the user account, the full name of the computer is specified together with the credentials of the user.</span></span>

### <span data-ttu-id="0178d-154">例 7: 多くのコンピューターのセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-154">Example 7: Create sessions for many computers</span></span>

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

<span data-ttu-id="0178d-155">このコマンドは、Servers.txt ファイルに一覧表示されている200コンピューターそれぞれに **pssession** を作成し、結果の **pssession** を変数に格納し `$rs` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-155">This command creates a **PSSession** on each of the 200 computers listed in the Servers.txt file and it stores the resulting **PSSession** in the `$rs` variable.</span></span> <span data-ttu-id="0178d-156">**PSSession** オブジェクトのスロットル制限は50です。</span><span class="sxs-lookup"><span data-stu-id="0178d-156">The **PSSession** objects have a throttle limit of 50.</span></span>

<span data-ttu-id="0178d-157">このコマンドの形式は、コンピューターの名前がデータベース、スプレッドシート、テキスト ファイル、またはその他のテキストに変換できる形式に格納されている場合、使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0178d-157">You can use this command format when the names of computers are stored in a database, spreadsheet, text file, or other text-convertible format.</span></span>

### <span data-ttu-id="0178d-158">例 8: URI を使用してセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-158">Example 8: Create a session by using a URI</span></span>

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

<span data-ttu-id="0178d-159">このコマンドは、Server01 コンピューター上に **PSSession** を作成し、変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-159">This command creates a **PSSession** on the Server01 computer and stores it in the `$s` variable.</span></span> <span data-ttu-id="0178d-160">**URI** パラメーターを使用して、トランスポートプロトコル、リモートコンピューター、ポート、および代替のセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-160">It uses the **URI** parameter to specify the transport protocol, the remote computer, the port, and an alternate session configuration.</span></span> <span data-ttu-id="0178d-161">また、 **Credential** パラメーターを使用して、リモートコンピューター上にセッションを作成するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-161">It also uses the **Credential** parameter to specify a user account that has permission to create a session on the remote computer.</span></span>

### <span data-ttu-id="0178d-162">例 9: 一連のセッションでバックグラウンドジョブを実行する</span><span class="sxs-lookup"><span data-stu-id="0178d-162">Example 9: Run a background job in a set of sessions</span></span>

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

<span data-ttu-id="0178d-163">これらのコマンドは、 **pssession** オブジェクトのセットを作成し、各 **pssession** オブジェクトでバックグラウンドジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="0178d-163">These commands create a set of **PSSession** objects and then run a background job in each of the **PSSession** objects.</span></span>

<span data-ttu-id="0178d-164">最初のコマンドは、Servers.txt ファイルに一覧表示されている各コンピューター上に新しい **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-164">The first command creates a new **PSSession** on each of the computers listed in the Servers.txt file.</span></span> <span data-ttu-id="0178d-165">コマンドレットを使用して `New-PSSession` **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-165">It uses the `New-PSSession` cmdlet to create the **PSSession**.</span></span> <span data-ttu-id="0178d-166">**ComputerName** パラメーターの値は、コマンドレットを使用して、 `Get-Content` Servers.txt ファイルのコンピューター名の一覧を取得するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="0178d-166">The value of the **ComputerName** parameter is a command that uses the `Get-Content` cmdlet to get the list of computer names the Servers.txt file.</span></span>

<span data-ttu-id="0178d-167">このコマンドは、 **Credential** パラメーターを使用して、ドメイン管理者のアクセス許可を持つ **PSSession** オブジェクトを作成します。また、 **ThrottleLimit** パラメーターを使用して、コマンドの同時接続数を16に制限します。</span><span class="sxs-lookup"><span data-stu-id="0178d-167">The command uses the **Credential** parameter to create the **PSSession** objects that have the permission of a domain administrator, and it uses the **ThrottleLimit** parameter to limit the command to 16 concurrent connections.</span></span> <span data-ttu-id="0178d-168">このコマンドは、 **PSSession** オブジェクトを変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-168">The command saves the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="0178d-169">2番目のコマンドは、コマンドレットの **AsJob** パラメーターを使用して、の `Invoke-Command` `Get-Process PowerShell` 各 **PSSession** オブジェクトでコマンドを実行するバックグラウンドジョブを開始し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-169">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a background job that runs a `Get-Process PowerShell` command in each of the **PSSession** objects in `$s`.</span></span>

<span data-ttu-id="0178d-170">PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](About/about_Jobs.md) 」および「 [about_Remote_Jobs](About/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-170">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

### <span data-ttu-id="0178d-171">例 10: URI を使用してコンピューターのセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-171">Example 10: Create a session for a computer by using its URI</span></span>

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

<span data-ttu-id="0178d-172">このコマンドは、コンピューター名の代わりに URI で指定されたコンピューターに接続する **PSSession** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-172">This command creates a **PSSession** objects that connects to a computer that is specified by a URI instead of a computer name.</span></span>

### <span data-ttu-id="0178d-173">例 11: セッションオプションを作成する</span><span class="sxs-lookup"><span data-stu-id="0178d-173">Example 11: Create a session option</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

<span data-ttu-id="0178d-174">この例では、セッションオプションオブジェクトを作成し、 **sessionoption** パラメーターを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0178d-174">This example shows how to create a session option object and use the **SessionOption** parameter.</span></span>

<span data-ttu-id="0178d-175">最初のコマンドは、コマンドレットを使用して `New-PSSessionOption` セッションオプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-175">The first command uses the `New-PSSessionOption` cmdlet to create a session option.</span></span> <span data-ttu-id="0178d-176">結果として得られる **Sessionoption** オブジェクトを変数に保存し `$so` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-176">It saves the resulting **SessionOption** object in the `$so` variable.</span></span>

<span data-ttu-id="0178d-177">2 番目のコマンドは、新しいセッションでこのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="0178d-177">The second command uses the option in a new session.</span></span> <span data-ttu-id="0178d-178">コマンドは、コマンド `New-PSSession` レットを使用して新しいセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-178">The command uses the `New-PSSession` cmdlet to create a new session.</span></span> <span data-ttu-id="0178d-179">SessionOption パラメーターの値は、変数内の **sessionoption** オブジェクトです `$so` 。</span><span class="sxs-lookup"><span data-stu-id="0178d-179">The value of the SessionOption parameter is the **SessionOption** object in the `$so` variable.</span></span>

## <span data-ttu-id="0178d-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0178d-180">PARAMETERS</span></span>

### <span data-ttu-id="0178d-181">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="0178d-181">-AllowRedirection</span></span>

<span data-ttu-id="0178d-182">このコマンドレットがこの接続を代替 Uniform Resource Identifier (URI) にリダイレクトできることを示します。</span><span class="sxs-lookup"><span data-stu-id="0178d-182">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="0178d-183">**ConnectionURI** パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトするように指示を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="0178d-183">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="0178d-184">既定では、PowerShell は接続をリダイレクトしませんが、このパラメーターを使用して接続をリダイレクトできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0178d-184">By default, PowerShell does not redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="0178d-185">また、 **MaximumConnectionRedirectionCount** セッション オプション値を変更することで、接続をリダイレクトする回数を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="0178d-185">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="0178d-186">コマンドレットの **Maximumredirection** パラメーターを使用する `New-PSSessionOption` か、 **$PSSessionOption** preference 変数の **MaximumConnectionRedirectionCount** プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-186">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="0178d-187">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="0178d-187">The default value is 5.</span></span>

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

### <span data-ttu-id="0178d-188">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="0178d-188">-ApplicationName</span></span>

<span data-ttu-id="0178d-189">接続 URI のアプリケーション名セグメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-189">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="0178d-190">このパラメーターは、このコマンドの **ConnectionURI** パラメーターを使用しないときに、アプリケーション名を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0178d-190">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="0178d-191">既定値は、 `$PSSessionApplicationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="0178d-191">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="0178d-192">このユーザー設定変数が定義されていない場合、既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="0178d-192">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="0178d-193">この値はほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="0178d-193">This value is appropriate for most uses.</span></span> <span data-ttu-id="0178d-194">詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-194">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="0178d-195">WinRM サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0178d-195">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="0178d-196">このパラメーターの値は、リモート コンピューター上のリスナーの **URLPrefix** プロパティの値に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-196">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="0178d-197">-認証</span><span class="sxs-lookup"><span data-stu-id="0178d-197">-Authentication</span></span>

<span data-ttu-id="0178d-198">ユーザーの資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-198">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="0178d-199">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0178d-199">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0178d-200">Default</span><span class="sxs-lookup"><span data-stu-id="0178d-200">Default</span></span>
- <span data-ttu-id="0178d-201">Basic</span><span class="sxs-lookup"><span data-stu-id="0178d-201">Basic</span></span>
- <span data-ttu-id="0178d-202">Credssp</span><span class="sxs-lookup"><span data-stu-id="0178d-202">Credssp</span></span>
- <span data-ttu-id="0178d-203">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="0178d-203">Digest</span></span>
- <span data-ttu-id="0178d-204">Kerberos</span><span class="sxs-lookup"><span data-stu-id="0178d-204">Kerberos</span></span>
- <span data-ttu-id="0178d-205">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="0178d-205">Negotiate</span></span>
- <span data-ttu-id="0178d-206">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="0178d-206">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="0178d-207">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="0178d-207">The default value is Default.</span></span>

<span data-ttu-id="0178d-208">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-208">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="0178d-209">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="0178d-209">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="0178d-210">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="0178d-210">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="0178d-211">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-211">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="0178d-212">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="0178d-212">-CertificateThumbprint</span></span>

<span data-ttu-id="0178d-213">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-213">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="0178d-214">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="0178d-214">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="0178d-215">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-215">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="0178d-216">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="0178d-216">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="0178d-217">証明書を取得するに `Get-Item` は、 `Get-ChildItem` PowerShell Cert: ドライブのまたはコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0178d-217">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="0178d-218">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0178d-218">-ComputerName</span></span>

<span data-ttu-id="0178d-219">コンピューターの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-219">Specifies an array of names of computers.</span></span> <span data-ttu-id="0178d-220">このコマンドレットは、指定されたコンピューターへの永続的な接続 ( **PSSession** ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-220">This cmdlet creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="0178d-221">複数のコンピューター名を入力すると、は、 `New-PSSession` コンピューターごとに1つずつ、複数の **PSSession** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-221">If you enter multiple computer names, `New-PSSession` creates multiple **PSSession** objects, one for each computer.</span></span> <span data-ttu-id="0178d-222">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="0178d-222">The default is the local computer.</span></span>

<span data-ttu-id="0178d-223">1 台または複数のリモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="0178d-223">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="0178d-224">ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="0178d-224">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="0178d-225">コンピューターがユーザーとは異なるドメインにある場合は、完全修飾ドメイン名が必要です。</span><span class="sxs-lookup"><span data-stu-id="0178d-225">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="0178d-226">パイプを使用してコンピューター名を引用符で囲むこともでき `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-226">You can also pipe a computer name, in quotation marks, to `New-PSSession`.</span></span>

<span data-ttu-id="0178d-227">**ComputerName** パラメーターの値に IP アドレスを使用するには、コマンドに **Credential** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-227">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="0178d-228">また、HTTPS トランスポート用にコンピューターを構成するか、リモート コンピューターの IP アドレスをローカル コンピューター上の WinRM TrustedHosts 一覧に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-228">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="0178d-229">TrustedHosts の一覧にコンピューター名を追加する手順については、 [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md)の「信頼されたホストの一覧にコンピューターを追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-229">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="0178d-230">ローカルコンピューターを **ComputerName** パラメーターの値に含めるには、[管理者として実行] オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="0178d-230">To include the local computer in the value of the **ComputerName** parameter, start Windows PowerShell by using the Run as administrator option.</span></span>

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

### <span data-ttu-id="0178d-231">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="0178d-231">-ConfigurationName</span></span>

<span data-ttu-id="0178d-232">新しい **PSSession** に使用するセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-232">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="0178d-233">セッション構成の構成名または完全修飾リソース URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="0178d-233">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="0178d-234">構成名だけを指定した場合は、次のスキーマ URI が付加され `http://schemas.microsoft.com/PowerShell` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-234">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="0178d-235">セッションのセッション構成は、リモート コンピューター上にあります。</span><span class="sxs-lookup"><span data-stu-id="0178d-235">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="0178d-236">指定したセッション構成がリモート コンピューター上に存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0178d-236">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="0178d-237">既定値は、 `$PSSessionConfigurationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="0178d-237">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="0178d-238">このユーザー設定変数が設定されていない場合、既定値は Microsoft.PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="0178d-238">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="0178d-239">詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-239">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

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

### <span data-ttu-id="0178d-240">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="0178d-240">-ConnectionUri</span></span>

<span data-ttu-id="0178d-241">セッションの接続エンドポイントを定義する URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-241">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="0178d-242">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-242">The URI must be fully qualified.</span></span> <span data-ttu-id="0178d-243">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0178d-243">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="0178d-244">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0178d-244">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="0178d-245">**ConnectionURI** を指定しなかった場合は、 **UseSSL** 、 **ComputerName** 、 **Port** 、および **ApplicationName** パラメーターを使用して、 **ConnectionURI** 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0178d-245">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="0178d-246">URI のトランスポート セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="0178d-246">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="0178d-247">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準ポート80で HTTP 用および 443 (HTTPS 用) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-247">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="0178d-248">PowerShell リモート処理に既定のポートを使用するには、HTTP の場合はポート5985、HTTPS の場合は5986を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-248">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="0178d-249">対象のコンピューターが接続を別の URI にリダイレクトする場合、コマンドで **Allowredirection** パラメーターを使用しない限り、PowerShell によってリダイレクトが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-249">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

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

### <span data-ttu-id="0178d-250">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="0178d-250">-ContainerId</span></span>

<span data-ttu-id="0178d-251">コンテナーの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-251">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="0178d-252">このコマンドレットは、指定された各コンテナーとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="0178d-252">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="0178d-253">`docker ps`コンテナー id の一覧を取得するには、コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0178d-253">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="0178d-254">詳細については、 [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) コマンドのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-254">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

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

### <span data-ttu-id="0178d-255">-Credential</span><span class="sxs-lookup"><span data-stu-id="0178d-255">-Credential</span></span>

<span data-ttu-id="0178d-256">このアクションを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-256">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="0178d-257">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="0178d-257">The default is the current user.</span></span>

<span data-ttu-id="0178d-258">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-258">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0178d-259">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="0178d-259">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="0178d-260">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-260">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0178d-261">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-261">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="0178d-262">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="0178d-262">-EnableNetworkAccess</span></span>

<span data-ttu-id="0178d-263">このコマンドレットが、ループバックセッションに対話型セキュリティトークンを追加することを示します。</span><span class="sxs-lookup"><span data-stu-id="0178d-263">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="0178d-264">対話型トークンを使用すると、他のコンピューターからデータを取得するコマンドをループバック セッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="0178d-264">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="0178d-265">たとえば、リモート コンピューターからローカル コンピューターに XML ファイルをコピーするコマンドをセッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="0178d-265">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="0178d-266">ループバックセッションは、同じコンピューター上で発生して終了する **PSSession** です。</span><span class="sxs-lookup"><span data-stu-id="0178d-266">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="0178d-267">ループバックセッションを作成するには、 **ComputerName** パラメーターを省略するか、値をドット (.)、localhost、またはローカルコンピューターの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-267">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (.), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="0178d-268">既定では、このコマンドレットはネットワークトークンを使用してループバックセッションを作成しますが、これにより、リモートコンピューターを認証するための十分なアクセス許可が与えられない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-268">By default, this cmdlet creates loopback sessions by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="0178d-269">**EnableNetworkAccess** パラメーターは、ループバック セッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="0178d-269">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="0178d-270">リモートコンピューターでセッションを作成するときに **EnableNetworkAccess** を使用すると、コマンドは成功しますが、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-270">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="0178d-271">また、 **認証** パラメーターの CredSSP 値を使用して、ループバックセッションでリモートアクセスを有効にすることもできます。これにより、セッションの資格情報が他のコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-271">You can also enable remote access in a loopback session by using the CredSSP value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="0178d-272">悪意のあるアクセスからコンピューターを保護するために、 **EnableNetworkAccess** パラメーターを使用して作成された、対話型トークンを持つ切断されたループバックセッションは、セッションが作成されたコンピューターからのみ再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="0178d-272">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="0178d-273">CredSSP 認証を使用するセッションが切断された場合には、他のコンピューターから再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="0178d-273">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="0178d-274">詳細については、「`Disconnect-PSSession`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-274">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="0178d-275">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0178d-275">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0178d-276">-Name</span><span class="sxs-lookup"><span data-stu-id="0178d-276">-Name</span></span>

<span data-ttu-id="0178d-277">**PSSession** のフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-277">Specifies a friendly name for the **PSSession**.</span></span>

<span data-ttu-id="0178d-278">やなどの他のコマンドレットを使用する場合は、名前を使用して **PSSession** を参照でき `Get-PSSession` `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-278">You can use the name to refer to the **PSSession** when you use other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="0178d-279">名前は、コンピューターや現在のセッションで一意である必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0178d-279">The name is not required to be unique to the computer or the current session.</span></span>

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

### <span data-ttu-id="0178d-280">-Port</span><span class="sxs-lookup"><span data-stu-id="0178d-280">-Port</span></span>

<span data-ttu-id="0178d-281">この接続に使用するリモート コンピューター上のネットワーク ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-281">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="0178d-282">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="0178d-282">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="0178d-283">既定のポートは5985で、これは HTTP 用の WinRM ポート、および HTTPS 用の WinRM ポートである5986です。</span><span class="sxs-lookup"><span data-stu-id="0178d-283">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="0178d-284">別のポートを使用する前に、そのポートでリッスンするようにリモートコンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-284">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="0178d-285">リスナーを構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0178d-285">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="0178d-286">必要な場合を除き、 **Port** パラメーターを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0178d-286">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="0178d-287">コマンドのポート設定は、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-287">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="0178d-288">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-288">An alternate port setting might prevent the command from running on all computers.</span></span>

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

### <span data-ttu-id="0178d-289">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0178d-289">-RunAsAdministrator</span></span>

<span data-ttu-id="0178d-290">**PSSession** が管理者として実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="0178d-290">Indicates that the **PSSession** runs as administrator.</span></span>

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

### <span data-ttu-id="0178d-291">-セッション</span><span class="sxs-lookup"><span data-stu-id="0178d-291">-Session</span></span>

<span data-ttu-id="0178d-292">このコマンドレットが新しい **pssession** のモデルとして使用する **pssession** オブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-292">Specifies an array of **PSSession** objects that this cmdlet uses as a model for the new **PSSession**.</span></span> <span data-ttu-id="0178d-293">このパラメーターは、指定された **pssession** オブジェクトと同じプロパティを持つ新しい **PSSession** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0178d-293">This parameter creates new **PSSession** objects that have the same properties as the specified **PSSession** objects.</span></span>

<span data-ttu-id="0178d-294">**Pssession** オブジェクトを含む変数、 **PSSession** `New-PSSession` またはコマンドやコマンドなどの pssession オブジェクトを作成または取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-294">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="0178d-295">結果として得られる **PSSession** オブジェクトのコンピューター名、アプリケーション名、接続 URI、ポート、構成名、スロットル制限、および SECURE SOCKETS LAYER (SSL) 値は元のものと同じですが、表示名、ID、インスタンス ID (GUID) は異なります。</span><span class="sxs-lookup"><span data-stu-id="0178d-295">The resulting **PSSession** objects have the same computer name, application name, connection URI, port, configuration name, throttle limit, and Secure Sockets Layer (SSL) value as the originals, but they have a different display name, ID, and instance ID (GUID).</span></span>

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

### <span data-ttu-id="0178d-296">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="0178d-296">-SessionOption</span></span>

<span data-ttu-id="0178d-297">セッションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-297">Specifies advanced options for the session.</span></span> <span data-ttu-id="0178d-298">コマンドレットを使用して作成する **sessionoption** オブジェクト、 `New-PSSessionOption` またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="0178d-298">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="0178d-299">オプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-299">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="0178d-300">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="0178d-300">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="0178d-301">セッションオプションの値は、ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-301">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="0178d-302">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="0178d-302">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="0178d-303">既定値を含むセッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="0178d-303">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="0178d-304">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-304">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="0178d-305">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-305">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="0178d-306">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0178d-306">-ThrottleLimit</span></span>

<span data-ttu-id="0178d-307">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-307">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="0178d-308">このパラメーターを省略した場合、または値 0 (ゼロ) を入力した場合は、既定値の 32 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0178d-308">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span>

<span data-ttu-id="0178d-309">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="0178d-309">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="0178d-310">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="0178d-310">-UseSSL</span></span>

<span data-ttu-id="0178d-311">このコマンドレットが SSL プロトコルを使用してリモートコンピューターへの接続を確立することを示します。</span><span class="sxs-lookup"><span data-stu-id="0178d-311">Indicates that this cmdlet uses the SSL protocol to establish a connection to the remote computer.</span></span>
<span data-ttu-id="0178d-312">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="0178d-312">By default, SSL is not used.</span></span>

<span data-ttu-id="0178d-313">WS-Management は、ネットワーク経由で送信されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="0178d-313">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="0178d-314">**UseSSL** パラメーターは、HTTP 接続ではなく HTTPS 接続を介してデータを送信する追加の保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="0178d-314">The **UseSSL** parameter offers an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="0178d-315">このパラメーターを使用しても、コマンドに使用されているポートで SSL を使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0178d-315">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="0178d-316">-VMId</span><span class="sxs-lookup"><span data-stu-id="0178d-316">-VMId</span></span>

<span data-ttu-id="0178d-317">仮想マシンの ID の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-317">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="0178d-318">このコマンドレットは、指定された各仮想マシンとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="0178d-318">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="0178d-319">使用可能な仮想マシンを表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0178d-319">To see the virtual machines that are available to you, use the following command:</span></span>

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

### <span data-ttu-id="0178d-320">-VMName</span><span class="sxs-lookup"><span data-stu-id="0178d-320">-VMName</span></span>

<span data-ttu-id="0178d-321">仮想マシンの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0178d-321">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="0178d-322">このコマンドレットは、指定された各仮想マシンとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="0178d-322">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="0178d-323">使用可能な仮想マシンを表示するには、コマンドレットを使用し `Get-VM` ます。</span><span class="sxs-lookup"><span data-stu-id="0178d-323">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

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

### <span data-ttu-id="0178d-324">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0178d-324">CommonParameters</span></span>

<span data-ttu-id="0178d-325">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0178d-325">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0178d-326">詳細については、「about_CommonParameters」 (https://go.microsoft.com/fwlink/?LinkID=113216) ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-326">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0178d-327">入力</span><span class="sxs-lookup"><span data-stu-id="0178d-327">INPUTS</span></span>

### <span data-ttu-id="0178d-328">System.string、System.string、system......。</span><span class="sxs-lookup"><span data-stu-id="0178d-328">System.String, System.URI, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="0178d-329">パイプを使用して、文字列、URI、またはセッションオブジェクトをこのコマンドレットに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="0178d-329">You can pipe a string, URI, or session object to this cmdlet.</span></span>

## <span data-ttu-id="0178d-330">出力</span><span class="sxs-lookup"><span data-stu-id="0178d-330">OUTPUTS</span></span>

### <span data-ttu-id="0178d-331">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="0178d-331">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="0178d-332">注</span><span class="sxs-lookup"><span data-stu-id="0178d-332">NOTES</span></span>

- <span data-ttu-id="0178d-333">このコマンドレットは、PowerShell リモート処理インフラストラクチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="0178d-333">This cmdlet uses the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="0178d-334">このコマンドレットを使用するには、ローカルコンピューターとリモートコンピューターを PowerShell リモート処理用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0178d-334">To use this cmdlet, the local computer and any remote computers must be configured for PowerShell remoting.</span></span> <span data-ttu-id="0178d-335">詳細については、「[about_Remote_Requirements](About/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0178d-335">For more information, see [about_Remote_Requirements](About/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="0178d-336">ローカルコンピューター上に **PSSession** を作成するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="0178d-336">To create a **PSSession** on the local computer, start PowerShell with the Run as administrator option.</span></span>
- <span data-ttu-id="0178d-337">**Pssession** が終了したら、コマンドレットを使用して `Remove-PSSession` **pssession** を削除し、そのリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="0178d-337">When you are finished with the **PSSession** , use the `Remove-PSSession` cmdlet to delete the **PSSession** and release its resources.</span></span>

## <span data-ttu-id="0178d-338">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0178d-338">RELATED LINKS</span></span>

[<span data-ttu-id="0178d-339">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0178d-339">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="0178d-340">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0178d-340">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="0178d-341">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="0178d-341">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="0178d-342">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="0178d-342">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="0178d-343">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="0178d-343">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="0178d-344">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="0178d-344">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="0178d-345">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="0178d-345">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="0178d-346">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="0178d-346">Remove-PSSession</span></span>](Remove-PSSession.md)

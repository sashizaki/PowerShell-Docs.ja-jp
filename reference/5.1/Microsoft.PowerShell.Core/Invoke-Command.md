---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: 652ff321ea1c6507915be9748715604166207200
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218235"
---
# <span data-ttu-id="82698-103">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="82698-103">Invoke-Command</span></span>

## <span data-ttu-id="82698-104">概要</span><span class="sxs-lookup"><span data-stu-id="82698-104">SYNOPSIS</span></span>
<span data-ttu-id="82698-105">ローカル コンピューターおよびリモート コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-105">Runs commands on local and remote computers.</span></span>

## <span data-ttu-id="82698-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="82698-106">SYNTAX</span></span>

### <span data-ttu-id="82698-107">InProcess (既定)</span><span class="sxs-lookup"><span data-stu-id="82698-107">InProcess (Default)</span></span>

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="82698-108">Session</span><span class="sxs-lookup"><span data-stu-id="82698-108">Session</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="82698-109">FilePathRunspace 空間</span><span class="sxs-lookup"><span data-stu-id="82698-109">FilePathRunspace</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="82698-110">FilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="82698-110">FilePathComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="82698-111">[ComputerName]</span><span class="sxs-lookup"><span data-stu-id="82698-111">ComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="82698-112">Uri</span><span class="sxs-lookup"><span data-stu-id="82698-112">Uri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="82698-113">FilePathUri</span><span class="sxs-lookup"><span data-stu-id="82698-113">FilePathUri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="82698-114">VMId</span><span class="sxs-lookup"><span data-stu-id="82698-114">VMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="82698-115">VMName</span><span class="sxs-lookup"><span data-stu-id="82698-115">VMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="82698-116">FilePathVMId</span><span class="sxs-lookup"><span data-stu-id="82698-116">FilePathVMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="82698-117">FilePathVMName</span><span class="sxs-lookup"><span data-stu-id="82698-117">FilePathVMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="82698-118">ContainerId</span><span class="sxs-lookup"><span data-stu-id="82698-118">ContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="82698-119">FilePathContainerId</span><span class="sxs-lookup"><span data-stu-id="82698-119">FilePathContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

## <span data-ttu-id="82698-120">Description</span><span class="sxs-lookup"><span data-stu-id="82698-120">DESCRIPTION</span></span>

<span data-ttu-id="82698-121">コマンド `Invoke-Command` レットは、ローカルコンピューターまたはリモートコンピューターでコマンドを実行し、エラーを含め、コマンドからのすべての出力を返します。</span><span class="sxs-lookup"><span data-stu-id="82698-121">The `Invoke-Command` cmdlet runs commands on a local or remote computer and returns all output from the commands, including errors.</span></span> <span data-ttu-id="82698-122">1つの `Invoke-Command` コマンドを使用すると、複数のコンピューターでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="82698-122">Using a single `Invoke-Command` command, you can run commands on multiple computers.</span></span>

<span data-ttu-id="82698-123">リモート コンピューターで 1 つのコマンドを実行するには、 **ComputerName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-123">To run a single command on a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="82698-124">データを共有する一連の関連コマンドを実行するには、コマンドレットを使用して、 `New-PSSession` リモートコンピューター上に **pssession** (永続的な接続) を作成し、の **Session** パラメーターを使用して、 `Invoke-Command` **pssession** でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-124">To run a series of related commands that share data, use the `New-PSSession` cmdlet to create a **PSSession** (a persistent connection) on the remote computer, and then use the **Session** parameter of `Invoke-Command` to run the command in the **PSSession**.</span></span> <span data-ttu-id="82698-125">切断されたセッションのコマンドを実行するには、 **InDisconnectedSession** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-125">To run a command in a disconnected session, use the **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="82698-126">コマンドをバックグラウンド ジョブとして実行するには、 **AsJob** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-126">To run a command in a background job, use the **AsJob** parameter.</span></span>

<span data-ttu-id="82698-127">また、 `Invoke-Command` コマンドとしてスクリプトブロックにローカルコンピューターでを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="82698-127">You can also use `Invoke-Command` on a local computer to a script block as a command.</span></span> <span data-ttu-id="82698-128">PowerShell は、現在のスコープの子スコープでスクリプトブロックを直ちに実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-128">PowerShell runs the script block immediately in a child scope of the current scope.</span></span>

<span data-ttu-id="82698-129">を使用して `Invoke-Command` リモートコンピューターでコマンドを実行する前に、 [about_Remote](./About/about_Remote.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-129">Before using `Invoke-Command` to run commands on a remote computer, read [about_Remote](./About/about_Remote.md).</span></span>

<span data-ttu-id="82698-130">一部のコードサンプルでは、スプラッティングを使用して行の長さを減らしています。</span><span class="sxs-lookup"><span data-stu-id="82698-130">Some code samples use splatting to reduce the line length.</span></span> <span data-ttu-id="82698-131">詳細については、「 [about_Splatting](./About/about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-131">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="82698-132">例</span><span class="sxs-lookup"><span data-stu-id="82698-132">EXAMPLES</span></span>

### <span data-ttu-id="82698-133">例 1: サーバーでスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="82698-133">Example 1: Run a script on a server</span></span>

<span data-ttu-id="82698-134">この例では、 `Test.ps1` Server01 コンピューターでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-134">This example runs the `Test.ps1` script on the Server01 computer.</span></span>

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

<span data-ttu-id="82698-135">**FilePath** パラメーターには、ローカルコンピューター上にあるスクリプトが指定されています。</span><span class="sxs-lookup"><span data-stu-id="82698-135">The **FilePath** parameter specifies a script that is located on the local computer.</span></span> <span data-ttu-id="82698-136">このスクリプトは、リモート コンピューターで実行され、結果はローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="82698-136">The script runs on the remote computer and the results are returned to the local computer.</span></span>

### <span data-ttu-id="82698-137">例 2: リモートサーバーでコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="82698-137">Example 2: Run a command on a remote server</span></span>

<span data-ttu-id="82698-138">この例では `Get-Culture` 、Server01 リモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-138">This example runs a `Get-Culture` command on the Server01 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

<span data-ttu-id="82698-139">**ComputerName** パラメーターは、リモートコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-139">The **ComputerName** parameter specifies the name of the remote computer.</span></span> <span data-ttu-id="82698-140">**Credential** パラメーターは、コマンドを実行する権限を持つユーザーである domain01\user01」のセキュリティコンテキストでコマンドを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="82698-140">The **Credential** parameter is used to run the command in the security context of Domain01\User01, a user who has permission to run commands.</span></span> <span data-ttu-id="82698-141">**ScriptBlock** パラメーターは、リモートコンピューターで実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-141">The **ScriptBlock** parameter specifies the command to be run on the remote computer.</span></span>

<span data-ttu-id="82698-142">応答として、PowerShell は User01 アカウントのパスワードと認証方法を要求します。</span><span class="sxs-lookup"><span data-stu-id="82698-142">In response, PowerShell requests the password and an authentication method for the User01 account.</span></span>
<span data-ttu-id="82698-143">次に、Server01 コンピューターでコマンドを実行して結果を返します。</span><span class="sxs-lookup"><span data-stu-id="82698-143">It then runs the command on the Server01 computer and returns the result.</span></span>

### <span data-ttu-id="82698-144">例 3: 永続的な接続でコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="82698-144">Example 3: Run a command in a persistent connection</span></span>

<span data-ttu-id="82698-145">この例では、 `Get-Culture` Server02 という名前のリモートコンピューター上で、永続的な接続を使用してセッションで同じコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-145">This example runs the same `Get-Culture` command in a session, using a persistent connection, on the remote computer named Server02.</span></span>

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="82698-146">`New-PSSession`コマンドレットは、Server02 リモートコンピューター上にセッションを作成し、変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-146">The `New-PSSession` cmdlet creates a session on the Server02 remote computer and saves it in the `$s` variable.</span></span> <span data-ttu-id="82698-147">通常、セッションを作成するには、リモートコンピューターで一連のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82698-147">Typically, you create a session only when you run a series of commands on the remote computer.</span></span>

<span data-ttu-id="82698-148">`Invoke-Command`コマンドレットでは、 `Get-Culture` Server02 でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-148">The `Invoke-Command` cmdlet runs the `Get-Culture` command on Server02.</span></span> <span data-ttu-id="82698-149">**Session** パラメーターは、変数に保存されているセッションを指定し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-149">The **Session** parameter specifies the session saved in the `$s` variable.</span></span>

<span data-ttu-id="82698-150">応答として、PowerShell は Server02 コンピューター上のセッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-150">In response, PowerShell runs the command in the session on the Server02 computer.</span></span>

### <span data-ttu-id="82698-151">例 4: セッションを使用してデータを共有する一連のコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="82698-151">Example 4: Use a session to run a series of commands that share data</span></span>

<span data-ttu-id="82698-152">この例では、の **ComputerName** パラメーターと **Session** パラメーターを使用した場合の効果を比較し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-152">This example compares the effects of using **ComputerName** and **Session** parameters of `Invoke-Command`.</span></span> <span data-ttu-id="82698-153">セッションを使用して、同じデータを共有する一連のコマンドを実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="82698-153">It shows how to use a session to run a series of commands that share the same data.</span></span>

```powershell
Invoke-Command -ComputerName Server02 -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -ComputerName Server02 -ScriptBlock {$p.VirtualMemorySize}
$s = New-PSSession -ComputerName Server02
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -Session $s -ScriptBlock {$p.VirtualMemorySize}
```

```Output
17930240
```

<span data-ttu-id="82698-154">最初の2つのコマンドは、の **ComputerName** パラメーターを使用して `Invoke-Command` 、Server02 リモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-154">The first two commands use the **ComputerName** parameter of `Invoke-Command` to run commands on the Server02 remote computer.</span></span> <span data-ttu-id="82698-155">最初のコマンドは、 `Get-Process` コマンドレットを使用して、リモートコンピューター上の PowerShell プロセスを取得し、変数に保存し `$p` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-155">The first command uses the `Get-Process` cmdlet to get the PowerShell process on the remote computer and to save it in the `$p` variable.</span></span> <span data-ttu-id="82698-156">2 番目のコマンドは、PowerShell プロセスの **VirtualMemorySize** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="82698-156">The second command gets the value of the **VirtualMemorySize** property of the PowerShell process.</span></span>

<span data-ttu-id="82698-157">**ComputerName** パラメーターを使用すると、PowerShell によってコマンドを実行する新しいセッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="82698-157">When you use the **ComputerName** parameter, PowerShell creates a new session to run the command.</span></span>
<span data-ttu-id="82698-158">コマンドが完了すると、セッションは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="82698-158">The session is closed when the command completes.</span></span> <span data-ttu-id="82698-159">`$p`変数は1つの接続で作成されましたが、2番目のコマンド用に作成された接続には存在しません。</span><span class="sxs-lookup"><span data-stu-id="82698-159">The `$p` variable was created in one connection, but it doesn't exist in the connection created for the second command.</span></span>

<span data-ttu-id="82698-160">この問題は、リモートコンピューターで永続的なセッションを作成し、両方のコマンドを同じセッションで実行することによって解決されます。</span><span class="sxs-lookup"><span data-stu-id="82698-160">The problem is solved by creating a persistent session on the remote computer, then running both of the commands in the same session.</span></span>

<span data-ttu-id="82698-161">この `New-PSSession` コマンドレットは、Server02 コンピューター上に永続的なセッションを作成し、そのセッションを変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-161">The `New-PSSession` cmdlet creates a persistent session on the computer Server02 and saves the session in the `$s` variable.</span></span> <span data-ttu-id="82698-162">次の行では、 `Invoke-Command` **session** パラメーターを使用して、同じセッションで両方のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-162">The `Invoke-Command` lines that follow use the **Session** parameter to run both of the commands in the same session.</span></span> <span data-ttu-id="82698-163">両方のコマンドが同じセッションで実行されるため、 `$p` 値はアクティブなままになります。</span><span class="sxs-lookup"><span data-stu-id="82698-163">Since both commands run in the same session, the `$p` value remains active.</span></span>

### <span data-ttu-id="82698-164">例 5: ローカル変数に格納されているコマンドを入力する</span><span class="sxs-lookup"><span data-stu-id="82698-164">Example 5: Enter a command stored in a local variable</span></span>

<span data-ttu-id="82698-165">この例では、スクリプトブロックとしてローカル変数に格納されているコマンドを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82698-165">This example shows how to create a command that is stored as a script block in a local variable.</span></span>
<span data-ttu-id="82698-166">スクリプトブロックがローカル変数に保存されている場合は、 **ScriptBlock** パラメーターの値として変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82698-166">When the script block is saved in a local variable, you can specify the variable as the value of the **ScriptBlock** parameter.</span></span>

```powershell
$command = { Get-EventLog -LogName "Windows PowerShell" |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

<span data-ttu-id="82698-167">変数には、 `$command` `Get-EventLog` スクリプトブロックとして書式設定されたコマンドが格納されます。</span><span class="sxs-lookup"><span data-stu-id="82698-167">The `$command` variable stores the `Get-EventLog` command that's formatted as a script block.</span></span> <span data-ttu-id="82698-168">は、 `Invoke-Command` `$command` S1 および S2 リモートコンピューター上のに格納されているコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-168">The `Invoke-Command` runs the command stored in `$command` on the S1 and S2 remote computers.</span></span>

### <span data-ttu-id="82698-169">例 6: 複数のコンピューターで1つのコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="82698-169">Example 6: Run a single command on several computers</span></span>

<span data-ttu-id="82698-170">この例 `Invoke-Command` では、を使用して、複数のコンピューターで1つのコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82698-170">This example demonstrates how to use `Invoke-Command` to run a single command on multiple computers.</span></span>

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-EventLog "Windows PowerShell" }
}
Invoke-Command @parameters
```

<span data-ttu-id="82698-171">**ComputerName** パラメーターは、コンマで区切られたコンピューター名のリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-171">The **ComputerName** parameter specifies a comma-separated list of computer names.</span></span> <span data-ttu-id="82698-172">コンピューターの一覧には、ローカルコンピューターを表す localhost 値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82698-172">The list of computers includes the localhost value, which represents the local computer.</span></span> <span data-ttu-id="82698-173">**ConfigurationName** パラメーターは、代替のセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-173">The **ConfigurationName** parameter specifies an alternate session configuration.</span></span> <span data-ttu-id="82698-174">**ScriptBlock** パラメーターは、 `Get-EventLog` 各コンピューターから Windows PowerShell イベントログを取得するために実行されます。</span><span class="sxs-lookup"><span data-stu-id="82698-174">The **ScriptBlock** parameter runs `Get-EventLog` to get the Windows PowerShell event logs from each computer.</span></span>

### <span data-ttu-id="82698-175">例 7: 複数のコンピューターでホストプログラムのバージョンを取得する</span><span class="sxs-lookup"><span data-stu-id="82698-175">Example 7: Get the version of the host program on multiple computers</span></span>

<span data-ttu-id="82698-176">この例では、200リモートコンピューター上で実行されている PowerShell ホストプログラムのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="82698-176">This example gets the version of the PowerShell host program running on 200 remote computers.</span></span>

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

<span data-ttu-id="82698-177">実行されるコマンドは1つだけなので、各コンピューターへの永続的な接続を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="82698-177">Because only one command is run, you don't have to create persistent connections to each of the computers.</span></span> <span data-ttu-id="82698-178">ただし、 **ComputerName** パラメーターを使用してコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-178">Instead, the command uses the **ComputerName** parameter to indicate the computers.</span></span> <span data-ttu-id="82698-179">コンピューターを指定するには、コマンドレットを使用して、 `Get-Content` コンピューター名のファイルである Machine.txt ファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="82698-179">To specify the computers, it uses the `Get-Content` cmdlet to get the contents of the Machine.txt file, a file of computer names.</span></span>

<span data-ttu-id="82698-180">`Invoke-Command`コマンドレットは、 `Get-Host` リモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-180">The `Invoke-Command` cmdlet runs a `Get-Host` command on the remote computers.</span></span> <span data-ttu-id="82698-181">ドット表記を使用して、PowerShell ホストの **Version** プロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="82698-181">It uses dot notation to get the **Version** property of the PowerShell host.</span></span>

<span data-ttu-id="82698-182">これらのコマンドは一度に1つずつ実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-182">These commands run one at a time.</span></span> <span data-ttu-id="82698-183">コマンドが完了すると、すべてのコンピューターからのコマンドの出力が変数に保存され `$version` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-183">When the commands complete, the output of the commands from all of the computers is saved in the `$version` variable.</span></span> <span data-ttu-id="82698-184">出力には、データの発生元であるコンピューターの名前も含まれます。</span><span class="sxs-lookup"><span data-stu-id="82698-184">The output includes the name of the computer from which the data originated.</span></span>

### <span data-ttu-id="82698-185">例 8: 複数のリモートコンピューターでバックグラウンドジョブを実行する</span><span class="sxs-lookup"><span data-stu-id="82698-185">Example 8: Run a background job on several remote computers</span></span>

<span data-ttu-id="82698-186">この例では、2台のリモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-186">This example runs a command on two remote computers.</span></span> <span data-ttu-id="82698-187">コマンドは `Invoke-Command` **AsJob** パラメーターを使用して、コマンドがバックグラウンドジョブとして実行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="82698-187">The `Invoke-Command` command uses the **AsJob** parameter so that the command runs as a background job.</span></span> <span data-ttu-id="82698-188">コマンドはリモートコンピューター上で実行されますが、ジョブはローカルコンピューター上に存在します。</span><span class="sxs-lookup"><span data-stu-id="82698-188">The commands run on the remote computers, but the job exists on the local computer.</span></span> <span data-ttu-id="82698-189">結果はローカルコンピューターに送信されます。</span><span class="sxs-lookup"><span data-stu-id="82698-189">The results are transmitted to the local computer.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
Invoke-Command -Session $s -ScriptBlock {Get-EventLog system} -AsJob
```

```Output
Id   Name    State      HasMoreData   Location           Command
---  ----    -----      -----         -----------        ---------------
1    Job1    Running    True          Server01,Server02  Get-EventLog system
```

```powershell
$j = Get-Job
$j | Format-List -Property *
```

```Output
HasMoreData   : True
StatusMessage :
Location      : Server01,Server02
Command       : Get-EventLog system
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : e124bb59-8cb2-498b-a0d2-2e07d4e030ca
Id            : 1
Name          : Job1
ChildJobs     : {Job2, Job3}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
$results = $j | Receive-Job
```

<span data-ttu-id="82698-190">コマンドレットでは、 `New-PSSession` Server01 と Server02 のリモートコンピューターにセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="82698-190">The `New-PSSession` cmdlet creates sessions on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="82698-191">`Invoke-Command`コマンドレットは、各セッションでバックグラウンドジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-191">The `Invoke-Command` cmdlet runs a background job in each of the sessions.</span></span> <span data-ttu-id="82698-192">このコマンドは **AsJob** パラメーターを使用して、バックグラウンド ジョブとしてコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-192">The command uses the **AsJob** parameter to run the command as a background job.</span></span> <span data-ttu-id="82698-193">このコマンドは、2 台のリモート コンピューターでそれぞれ実行されるジョブに対応する 2 つの子ジョブ オブジェクトを含むジョブ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="82698-193">This command returns a job object that contains two child job objects, one for each of the jobs run on the two remote computers.</span></span>

<span data-ttu-id="82698-194">この `Get-Job` コマンドは、ジョブオブジェクトを変数に保存し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-194">The `Get-Job` command saves the job object in the `$j` variable.</span></span> <span data-ttu-id="82698-195">次に、 `$j` 変数をコマンドレットにパイプして、 `Format-List` ジョブオブジェクトのすべてのプロパティを一覧に表示します。</span><span class="sxs-lookup"><span data-stu-id="82698-195">The `$j` variable is then piped to the `Format-List` cmdlet to display all properties of the job object in a list.</span></span> <span data-ttu-id="82698-196">最後のコマンドは、ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="82698-196">The last command gets the results of the jobs.</span></span> <span data-ttu-id="82698-197">ジョブオブジェクトを `$j` コマンドレットにパイプ処理 `Receive-Job` し、結果を変数に格納し `$results` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-197">It pipes the job object in `$j` to the `Receive-Job` cmdlet and stores the results in the `$results` variable.</span></span>

### <span data-ttu-id="82698-198">例 9: リモートコンピューターでコマンドを実行するときにローカル変数を含める</span><span class="sxs-lookup"><span data-stu-id="82698-198">Example 9: Include local variables in a command run on a remote computer</span></span>

<span data-ttu-id="82698-199">この例は、リモート コンピューターで実行されるコマンドにローカル変数の値を含める方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="82698-199">This example shows how to include the values of local variables in a command run on a remote computer.</span></span> <span data-ttu-id="82698-200">このコマンドは、 `Using` スコープ修飾子を使用して、リモートコマンドでローカル変数を識別します。</span><span class="sxs-lookup"><span data-stu-id="82698-200">The command uses the `Using` scope modifier to identify a local variable in a remote command.</span></span> <span data-ttu-id="82698-201">既定では、すべての変数は、リモート セッションで定義されると見なされます。</span><span class="sxs-lookup"><span data-stu-id="82698-201">By default, all variables are assumed to be defined in the remote session.</span></span> <span data-ttu-id="82698-202">`Using`スコープ修飾子は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="82698-202">The `Using` scope modifier was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="82698-203">スコープ修飾子の詳細については `Using` 、「 [about_Remote_Variables](./About/about_Remote_Variables.md) 」および「 [about_Scopes](./about/about_scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-203">For more information about the `Using` scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md) and [about_Scopes](./about/about_scopes.md).</span></span>

```powershell
$Log = "Windows PowerShell"
Invoke-Command -ComputerName Server01 -ScriptBlock { Get-EventLog -LogName $Using:Log -Newest 10 }
```

<span data-ttu-id="82698-204">変数には、 `$Log` イベントログの名前 (Windows PowerShell) が格納されます。</span><span class="sxs-lookup"><span data-stu-id="82698-204">The `$Log` variable stores the name of the event log, Windows PowerShell.</span></span> <span data-ttu-id="82698-205">`Invoke-Command`コマンドレットは、Server01 上で実行され、 `Get-EventLog` イベントログから最新の10個のイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="82698-205">The `Invoke-Command` cmdlet runs `Get-EventLog` on Server01 to get the ten newest events from the event log.</span></span> <span data-ttu-id="82698-206">**LogName** パラメーターの値は、変数です `$Log` 。この変数は、 `Using` リモートセッションではなくローカルセッションで作成されたことを示すために、スコープ修飾子でプレフィックスが付けられています。</span><span class="sxs-lookup"><span data-stu-id="82698-206">The value of the **LogName** parameter is the `$Log` variable, which is prefixed by the `Using` scope modifier to indicate that it was created in the local session, not in the remote session.</span></span>

### <span data-ttu-id="82698-207">例 10: コンピューター名を非表示にする</span><span class="sxs-lookup"><span data-stu-id="82698-207">Example 10: Hide the computer name</span></span>

<span data-ttu-id="82698-208">この例は、の **HideComputerName** パラメーターを使用した場合の効果を示して `Invoke-Command` います。</span><span class="sxs-lookup"><span data-stu-id="82698-208">This example shows the effect of using the **HideComputerName** parameter of `Invoke-Command`.</span></span>
<span data-ttu-id="82698-209">**HideComputerName** は、このコマンドレットが返すオブジェクトを変更しません。</span><span class="sxs-lookup"><span data-stu-id="82698-209">**HideComputerName** doesn't change the object that this cmdlet returns.</span></span> <span data-ttu-id="82698-210">表示のみが変更されます。</span><span class="sxs-lookup"><span data-stu-id="82698-210">It changes only the display.</span></span> <span data-ttu-id="82698-211">**Format** コマンドレットを使用して、影響を受けるオブジェクトの **PsComputerName** プロパティを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="82698-211">You can still use the **Format** cmdlets to display the **PsComputerName** property of any of the affected objects.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell}
```

```Output
PSComputerName    Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
--------------    -------  ------    -----      ----- -----   ------     --   -----------
S1                575      15        45100      40988   200     4.68     1392 PowerShell
S2                777      14        35100      30988   150     3.68     67   PowerShell
```

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell} -HideComputerName
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
575      15        45100      40988   200     4.68     1392 PowerShell
777      14        35100      30988   150     3.68     67   PowerShell
```

<span data-ttu-id="82698-212">最初の2つのコマンドは、を使用して `Invoke-Command` `Get-Process` PowerShell プロセス用のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-212">The first two commands use `Invoke-Command` to run a `Get-Process` command for the PowerShell process.</span></span> <span data-ttu-id="82698-213">最初のコマンドの出力には、 **PsComputerName** プロパティが含まれます。このプロパティは、コマンドが実行されているコンピューター名を示します。</span><span class="sxs-lookup"><span data-stu-id="82698-213">The output of the first command includes the **PsComputerName** property, which contains the name of the computer on which the command ran.</span></span> <span data-ttu-id="82698-214">**HideComputerName** を使用する2番目のコマンドの出力には、 **PsComputerName** 列が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="82698-214">The output of the second command, which uses **HideComputerName** , doesn't include the **PsComputerName** column.</span></span>

### <span data-ttu-id="82698-215">例 11: スクリプトブロックで Param キーワードを使用する</span><span class="sxs-lookup"><span data-stu-id="82698-215">Example 11: Use the Param keyword in a script block</span></span>

<span data-ttu-id="82698-216">`Param`キーワードと **ArgumentList** パラメーターは、変数の値をスクリプトブロック内の名前付きパラメーターに渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="82698-216">The `Param` keyword and the **ArgumentList** parameter are used to pass variable values to named parameters in a script block.</span></span> <span data-ttu-id="82698-217">この例では、文字で始まり、拡張子がのファイル名が表示され `a` `.pdf` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-217">This example displays filenames that begin with the letter `a` and have the `.pdf` extension.</span></span>

<span data-ttu-id="82698-218">キーワードの詳細については `Param` 、「 [about_Language_Keywords](./about/about_language_keywords.md#param)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-218">For more information about the `Param` keyword, see [about_Language_Keywords](./about/about_language_keywords.md#param).</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Param ($param1,$param2) Get-ChildItem -Name $param1 -Include $param2 }
    ArgumentList = "a*", "*.pdf"
}
Invoke-Command @parameters
```

```Output
aa.pdf
ab.pdf
ac.pdf
az.pdf
```

<span data-ttu-id="82698-219">`Invoke-Command` 2つの変数 (と) を定義する **ScriptBlock** パラメーターを使用し `$param1` `$param2` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-219">`Invoke-Command` uses the **ScriptBlock** parameter that defines two variables, `$param1` and `$param2`.</span></span> <span data-ttu-id="82698-220">`Get-ChildItem` 名前付きパラメーター、 **名前** **、およびを変数名と共** に使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-220">`Get-ChildItem` uses the named parameters, **Name** and **Include** with the variable names.</span></span> <span data-ttu-id="82698-221">**ArgumentList** は、値を変数に渡します。</span><span class="sxs-lookup"><span data-stu-id="82698-221">The **ArgumentList** passes the values to the variables.</span></span>

### <span data-ttu-id="82698-222">例 12: スクリプトブロックで $args 自動変数を使用する</span><span class="sxs-lookup"><span data-stu-id="82698-222">Example 12: Use the $args automatic variable in a script block</span></span>

<span data-ttu-id="82698-223">`$args`自動変数と **ArgumentList** パラメーターは、配列の値をスクリプトブロック内のパラメーターの位置に渡すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="82698-223">The `$args` automatic variable and the **ArgumentList** parameter are used to pass array values to parameter positions in a script block.</span></span> <span data-ttu-id="82698-224">この例では、ファイルのサーバーのディレクトリの内容を表示 `.txt` します。</span><span class="sxs-lookup"><span data-stu-id="82698-224">This example displays a server's directory contents of `.txt` files.</span></span> <span data-ttu-id="82698-225">`Get-ChildItem` **Path** パラメーターは position 0 で、 **Filter** パラメーターは position です。</span><span class="sxs-lookup"><span data-stu-id="82698-225">The `Get-ChildItem` **Path** parameter is position 0 and the **Filter** parameter is position</span></span>
1.

<span data-ttu-id="82698-226">変数の詳細については `$args` 、「」を参照してください [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span><span class="sxs-lookup"><span data-stu-id="82698-226">For more information about the `$args` variable, see [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Get-ChildItem $args[0] $args[1] }
    ArgumentList = "C:\Test", "*.txt*"
}
Invoke-Command @parameters
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           6/12/2019    15:15            128 alog.txt
-a---           7/27/2019    15:16            256 blog.txt
-a---           9/28/2019    17:10             64 zlog.txt
```

<span data-ttu-id="82698-227">`Invoke-Command`**ScriptBlock** パラメーターを使用し、 `Get-ChildItem` との配列値を指定し `$args[0]` `$args[1]` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-227">`Invoke-Command` uses a **ScriptBlock** parameter and `Get-ChildItem` specifies the `$args[0]` and `$args[1]` array values.</span></span> <span data-ttu-id="82698-228">**ArgumentList** は、 `$args` `Get-ChildItem` **パス** と **フィルター** のパラメーター位置に配列値を渡します。</span><span class="sxs-lookup"><span data-stu-id="82698-228">The **ArgumentList** passes the `$args` array values to the `Get-ChildItem` parameter positions for **Path** and **Filter**.</span></span>

### <span data-ttu-id="82698-229">例 13: テキストファイルに一覧表示されているすべてのコンピューターでスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="82698-229">Example 13: Run a script on all the computers listed in a text file</span></span>

<span data-ttu-id="82698-230">この例では、 `Invoke-Command` コマンドレットを使用し `Sample.ps1` て、ファイルに一覧表示されているすべてのコンピューターでスクリプトを実行し `Servers.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-230">This example uses the `Invoke-Command` cmdlet to run the `Sample.ps1` script on all the computers listed in the `Servers.txt` file.</span></span> <span data-ttu-id="82698-231">このコマンドは、 **FilePath** パラメーターを使用して、スクリプト ファイルを指定しています。</span><span class="sxs-lookup"><span data-stu-id="82698-231">The command uses the **FilePath** parameter to specify the script file.</span></span> <span data-ttu-id="82698-232">このコマンドを使用すると、リモートコンピューターでスクリプトファイルにアクセスできない場合でも、リモートコンピューターでスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="82698-232">This command lets you run the script on the remote computers, even if the script file isn't accessible to the remote computers.</span></span>

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

<span data-ttu-id="82698-233">コマンドを送信すると、ファイルの内容 `Sample.ps1` がスクリプトブロックにコピーされ、スクリプトブロックが各リモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="82698-233">When you submit the command, the content of the `Sample.ps1` file is copied into a script block and the script block is run on each of the remote computers.</span></span> <span data-ttu-id="82698-234">この手順では、 **ScriptBlock** パラメーターを使用してスクリプトの内容を送信した場合と同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="82698-234">This procedure is equivalent to using the **ScriptBlock** parameter to submit the contents of the script.</span></span>

### <span data-ttu-id="82698-235">例 14: URI を使用してリモートコンピューターでコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="82698-235">Example 14: Run a command on a remote computer using a URI</span></span>

<span data-ttu-id="82698-236">この例では、Uniform Resource Identifier (URI) で識別されるリモートコンピューターでコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82698-236">This example shows how to run a command on a remote computer that's identified by a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="82698-237">この特定の例では、 `Set-Mailbox` リモートの Exchange サーバー上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-237">This particular example runs a `Set-Mailbox` command on a remote Exchange server.</span></span>

```powershell
$LiveCred = Get-Credential
$parameters = @{
  ConfigurationName = 'Microsoft.Exchange'
  ConnectionUri = 'https://ps.exchangelabs.com/PowerShell'
  Credential = $LiveCred
  Authentication = 'Basic'
  ScriptBlock = {Set-Mailbox Dan -DisplayName "Dan Park"}
}
Invoke-Command @parameters
```

<span data-ttu-id="82698-238">最初の行では、コマンドレットを使用して、 `Get-Credential` Windows LIVE ID の資格情報を変数に格納し `$LiveCred` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-238">The first line uses the `Get-Credential` cmdlet to store Windows Live ID credentials in the `$LiveCred` variable.</span></span> <span data-ttu-id="82698-239">PowerShell は、Windows Live ID の資格情報を入力するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="82698-239">PowerShell prompts the user to enter Windows Live ID credentials.</span></span>

<span data-ttu-id="82698-240">`$parameters`変数は、コマンドレットに渡されるパラメーターを含むハッシュテーブルです `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="82698-240">The `$parameters` variable is a hash table containing the parameters to be passed to the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="82698-241">`Invoke-Command`コマンドレットは、 `Set-Mailbox` **Microsoft Exchange** のセッション構成を使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-241">The `Invoke-Command` cmdlet runs a `Set-Mailbox` command using the **Microsoft.Exchange** session configuration.</span></span> <span data-ttu-id="82698-242">**ConnectionURI** パラメーターは、Exchange サーバーのエンドポイントの URL を指定しています。</span><span class="sxs-lookup"><span data-stu-id="82698-242">The **ConnectionURI** parameter specifies the URL of the Exchange server endpoint.</span></span> <span data-ttu-id="82698-243">**Credential** パラメーターは、変数に格納されている資格情報を指定し `$LiveCred` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-243">The **Credential** parameter specifies the credentials stored in the `$LiveCred` variable.</span></span> <span data-ttu-id="82698-244">**AuthenticationMechanism** パラメーターでは、基本認証の使用を指定しています。</span><span class="sxs-lookup"><span data-stu-id="82698-244">The **AuthenticationMechanism** parameter specifies the use of basic authentication.</span></span> <span data-ttu-id="82698-245">**ScriptBlock** パラメーターは、コマンドが含まれているスクリプト ブロックを指定しています。</span><span class="sxs-lookup"><span data-stu-id="82698-245">The **ScriptBlock** parameter specifies a script block that contains the command.</span></span>

### <span data-ttu-id="82698-246">例 15: セッションオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="82698-246">Example 15: Use a session option</span></span>

<span data-ttu-id="82698-247">この例では、 **Sessionoption** パラメーターを作成して使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82698-247">This example shows how to create and use a **SessionOption** parameter.</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

<span data-ttu-id="82698-248">コマンドレットでは、 `New-PSSessionOption` セッションオプションオブジェクトを作成します。これにより、リモートエンドは、受信 HTTPS 接続の評価中に証明機関、正規名、および失効リストを検証しません。</span><span class="sxs-lookup"><span data-stu-id="82698-248">The `New-PSSessionOption` cmdlet creates a session option object that causes the remote end not to verify the Certificate Authority, Canonical Name, and Revocation Lists while evaluating the incoming HTTPS connection.</span></span> <span data-ttu-id="82698-249">**Sessionoption** オブジェクトは変数に保存され `$so` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-249">The **SessionOption** object is saved in the `$so` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="82698-250">これらのチェックを無効にすると、トラブルシューティングには便利ですが、セキュリティが明らかになります。</span><span class="sxs-lookup"><span data-stu-id="82698-250">Disabling these checks is convenient for troubleshooting, but obviously not secure.</span></span>

<span data-ttu-id="82698-251">`Invoke-Command`コマンドレットは、 `Get-HotFix` コマンドをリモートで実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-251">The `Invoke-Command` cmdlet runs a `Get-HotFix` command remotely.</span></span> <span data-ttu-id="82698-252">**Sessionoption** パラメーターには、変数が指定されてい `$so` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-252">The **SessionOption** parameter is given the `$so` variable.</span></span>

### <span data-ttu-id="82698-253">例 16: リモートコマンドで URI リダイレクトを管理する</span><span class="sxs-lookup"><span data-stu-id="82698-253">Example 16: Manage URI redirection in a remote command</span></span>

<span data-ttu-id="82698-254">この例では、 **Allowredirection** パラメーターと **sessionoption** パラメーターを使用して、リモートコマンドで URI リダイレクトを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82698-254">This example shows how to use the **AllowRedirection** and **SessionOption** parameters to manage URI redirection in a remote command.</span></span>

```powershell
$max = New-PSSessionOption -MaximumRedirection 1
$parameters = @{
  ConnectionUri = "https://ps.exchangelabs.com/PowerShell"
  ScriptBlock = { Get-Mailbox dan }
  AllowRedirection = $true
  SessionOption = $max
}
Invoke-Command @parameters
```

<span data-ttu-id="82698-255">`New-PSSessionOption`コマンドレットでは、変数に保存される **Pssessionoption** オブジェクトを作成し `$max` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-255">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object that is saved in the `$max` variable.</span></span> <span data-ttu-id="82698-256">このコマンドは、 **MaximumRedirection** パラメーターを使用して、 **PSSessionOption** オブジェクトの **MaximumConnectionRedirectionCount** プロパティを 1 に設定しています。</span><span class="sxs-lookup"><span data-stu-id="82698-256">The command uses the **MaximumRedirection** parameter to set the **MaximumConnectionRedirectionCount** property of the **PSSessionOption** object to 1.</span></span>

<span data-ttu-id="82698-257">`Invoke-Command`コマンドレットは、 `Get-Mailbox` リモートの Microsoft Exchange サーバー上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-257">The `Invoke-Command` cmdlet runs a `Get-Mailbox` command on a remote Microsoft Exchange Server.</span></span> <span data-ttu-id="82698-258">**Allowredirection** パラメーターは、接続を代替エンドポイントにリダイレクトするための明示的なアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="82698-258">The **AllowRedirection** parameter provides explicit permission to redirect the connection to an alternate endpoint.</span></span> <span data-ttu-id="82698-259">**Sessionoption** パラメーターは、変数に格納されているセッションオブジェクトを使用し `$max` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-259">The **SessionOption** parameter uses the session object stored in the `$max` variable.</span></span>

<span data-ttu-id="82698-260">その結果、 **Connectionuri** によって指定されたリモートコンピューターがリダイレクトメッセージを返す場合、PowerShell は接続をリダイレクトしますが、新しい送信先が別のリダイレクトメッセージを返す場合は、リダイレクトカウントの値1を超え、 `Invoke-Command` 終了しないエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="82698-260">As a result, if the remote computer specified by **ConnectionURI** returns a redirection message, PowerShell redirects the connection, but if the new destination returns another redirection message, the redirection count value of 1 is exceeded, and `Invoke-Command` returns a non-terminating error.</span></span>

### <span data-ttu-id="82698-261">例 17: リモートセッションでネットワーク共有にアクセスする</span><span class="sxs-lookup"><span data-stu-id="82698-261">Example 17: Access a network share in a remote session</span></span>

<span data-ttu-id="82698-262">この例では、リモートセッションからネットワーク共有にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82698-262">This example shows how to access a network share from a remote session.</span></span> <span data-ttu-id="82698-263">例を示すために、3台のコンピューターが使用されています。</span><span class="sxs-lookup"><span data-stu-id="82698-263">Three computers are used to demonstrate the example.</span></span> <span data-ttu-id="82698-264">Server01 はローカルコンピューター、Server02 はリモートコンピューター、Net03 にはネットワーク共有が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82698-264">Server01 is the local computer, Server02 is the remote computer, and Net03 contains the network share.</span></span> <span data-ttu-id="82698-265">Server01 は Server02 に接続し、Server02 はネットワーク共有にアクセスするために Net03 に2番目のホップを行います。</span><span class="sxs-lookup"><span data-stu-id="82698-265">Server01 connects to Server02, and then Server02 does a second hop to Net03 to access the network share.</span></span> <span data-ttu-id="82698-266">PowerShell リモート処理でコンピューター間のホップがサポートされる方法の詳細については、「 [Powershell リモート処理で2番目のホップを作成](/powershell/scripting/learn/remoting/ps-remoting-second-hop)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-266">For more information about how PowerShell Remoting supports hops between computers, see [Making the second hop in PowerShell Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span></span>

<span data-ttu-id="82698-267">必要な Credential Security Support Provider (CredSSP) 委任は、ローカルコンピューターのクライアント設定およびリモートコンピューターのサービス設定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="82698-267">The required Credential Security Support Provider (CredSSP) delegation is enabled in the client settings on the local computer, and in the service settings on the remote computer.</span></span> <span data-ttu-id="82698-268">この例のコマンドを実行するには、ローカルコンピューターとリモートコンピューターの **Administrators** グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82698-268">To run the commands in this example, you must be a member of the **Administrators** group on the local computer and the remote computer.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer Server02
$s = New-PSSession Server02
Invoke-Command -Session $s -ScriptBlock {Enable-WSManCredSSP -Role Server -Force}
$parameters = @{
  Session = $s
  ScriptBlock = { Get-Item \\Net03\Scripts\LogFiles.ps1 }
  Authentication = "CredSSP"
  Credential = "Domain01\Admin01"
}
Invoke-Command @parameters
```

<span data-ttu-id="82698-269">`Enable-WSManCredSSP`コマンドレットは、Server01 ローカルコンピューターから Server02 リモートコンピューターへの CredSSP 委任を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82698-269">The `Enable-WSManCredSSP` cmdlet enables CredSSP delegation from the Server01 local computer to the Server02 remote computer.</span></span> <span data-ttu-id="82698-270">**Role** パラメーターは、ローカルコンピューターの CredSSP クライアント設定を構成する **クライアント** を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-270">The **Role** parameter specifies **Client** to configure the CredSSP client setting on the local computer.</span></span>

<span data-ttu-id="82698-271">`New-PSSession` Server02 の **PSSession** オブジェクトを作成し、そのオブジェクトを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-271">`New-PSSession` creates a **PSSession** object for Server02 and stores the object in the `$s` variable.</span></span>

<span data-ttu-id="82698-272">この `Invoke-Command` コマンドレットは、変数を使用して `$s` リモートコンピューター Server02 に接続します。</span><span class="sxs-lookup"><span data-stu-id="82698-272">The `Invoke-Command` cmdlet uses the `$s` variable to connect to the remote computer, Server02.</span></span> <span data-ttu-id="82698-273">**ScriptBlock** パラメーターは、 `Enable-WSManCredSSP` リモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="82698-273">The **ScriptBlock** parameter runs `Enable-WSManCredSSP` on the remote computer.</span></span> <span data-ttu-id="82698-274">**Role** パラメーターは、リモートコンピューターの CredSSP サーバー設定を構成する **サーバー** を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-274">The **Role** parameter specifies **Server** to configure the CredSSP server setting on the remote computer.</span></span>

<span data-ttu-id="82698-275">変数には、 `$parameters` ネットワーク共有に接続するためのパラメーター値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82698-275">The `$parameters` variable contains the parameter values to connect to the network share.</span></span> <span data-ttu-id="82698-276">`Invoke-Command`コマンドレットは、 `Get-Item` のセッションでコマンドを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-276">The `Invoke-Command` cmdlet runs a `Get-Item` command in the session in `$s`.</span></span> <span data-ttu-id="82698-277">このコマンドは、ネットワーク共有からスクリプトを取得し `\\Net03\Scripts` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-277">This command gets a script from the `\\Net03\Scripts` network share.</span></span> <span data-ttu-id="82698-278">このコマンドでは、 **Authentication** パラメーターの値が **CredSSP** で、 **Credential** パラメーターに値 **Domain01\Admin01** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="82698-278">The command uses the **Authentication** parameter with a value of **CredSSP** and the **Credential** parameter with a value of **Domain01\Admin01**.</span></span>

### <span data-ttu-id="82698-279">例 18: 多くのリモートコンピューターでスクリプトを起動する</span><span class="sxs-lookup"><span data-stu-id="82698-279">Example 18: Start scripts on many remote computers</span></span>

<span data-ttu-id="82698-280">この例では、100台以上のコンピューターでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-280">This example runs a script on more than a hundred computers.</span></span> <span data-ttu-id="82698-281">ローカル コンピューターへの影響を最小限に抑えるために、各コンピューターに接続してスクリプトを起動した後で、各コンピューターとの接続を切断します。</span><span class="sxs-lookup"><span data-stu-id="82698-281">To minimize the impact on the local computer, it connects to each computer, starts the script, and then disconnects from each computer.</span></span>
<span data-ttu-id="82698-282">スクリプトは、引き続き切断されたセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="82698-282">The script continues to run in the disconnected sessions.</span></span>

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

<span data-ttu-id="82698-283">このコマンドは、を使用し `Invoke-Command` てスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-283">The command uses `Invoke-Command` to run the script.</span></span> <span data-ttu-id="82698-284">**ComputerName** パラメーターの値は、 `Get-Content` テキストファイルからリモートコンピューターの名前を取得するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="82698-284">The value of the **ComputerName** parameter is a `Get-Content` command that gets the names of the remote computers from a text file.</span></span> <span data-ttu-id="82698-285">**InDisconnectedSession** パラメーターにより、コマンドを起動するとすぐにセッションが切断されます。</span><span class="sxs-lookup"><span data-stu-id="82698-285">The **InDisconnectedSession** parameter disconnects the sessions as soon as it starts the command.</span></span> <span data-ttu-id="82698-286">**FilePath** パラメーターの値は、 `Invoke-Command` 各コンピューターで実行されるスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="82698-286">The value of the **FilePath** parameter is the script that `Invoke-Command` runs on each computer.</span></span>

<span data-ttu-id="82698-287">**Sessionoption** の値はハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="82698-287">The value of **SessionOption** is a hash table.</span></span> <span data-ttu-id="82698-288">**OutputBufferingMode** 値が **Drop** に設定され、 **IdleTimeout** 値が **4320万** ミリ秒 (12 時間) に設定されています。</span><span class="sxs-lookup"><span data-stu-id="82698-288">The **OutputBufferingMode** value is set to **Drop** and the **IdleTimeout** value is set to **43200000** milliseconds (12 hours).</span></span>

<span data-ttu-id="82698-289">切断されたセッションで実行されるコマンドとスクリプトの結果を取得するには、コマンドレットを使用し `Receive-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-289">To get the results of commands and scripts that run in disconnected sessions, use the `Receive-PSSession` cmdlet.</span></span>

## <span data-ttu-id="82698-290">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="82698-290">PARAMETERS</span></span>

### <span data-ttu-id="82698-291">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="82698-291">-AllowRedirection</span></span>

<span data-ttu-id="82698-292">この接続を代替 Uniform Resource Identifier (URI) にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="82698-292">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="82698-293">**ConnectionURI** パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトするように指示を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="82698-293">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="82698-294">既定では、PowerShell は接続をリダイレクトしませんが、このパラメーターを使用して接続をリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="82698-294">By default, PowerShell doesn't redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="82698-295">また、 **MaximumConnectionRedirectionCount** セッション オプション値を変更することで、接続をリダイレクトする回数を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="82698-295">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="82698-296">コマンドレットの **Maximumredirection** パラメーターを使用する `New-PSSessionOption` か、Preference 変数の **MaximumConnectionRedirectionCount** プロパティを設定し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-296">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="82698-297">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="82698-297">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-298">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="82698-298">-ApplicationName</span></span>

<span data-ttu-id="82698-299">接続 URI のアプリケーション名セグメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-299">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="82698-300">コマンドで **Connectionuri** パラメーターを使用しない場合は、このパラメーターを使用してアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-300">Use this parameter to specify the application name when you aren't using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="82698-301">既定値は、 `$PSSessionApplicationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="82698-301">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="82698-302">このユーザー設定変数が定義されていない場合、既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="82698-302">If this preference variable isn't defined, the default value is WSMAN.</span></span> <span data-ttu-id="82698-303">この値はほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="82698-303">This value is appropriate for most uses.</span></span> <span data-ttu-id="82698-304">詳細については、「 [about_Preference_Variables](./About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-304">For more information, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="82698-305">WinRM サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="82698-305">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="82698-306">このパラメーターの値は、リモート コンピューター上のリスナーの **URLPrefix** プロパティの値に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="82698-306">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="82698-307">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="82698-307">-ArgumentList</span></span>

<span data-ttu-id="82698-308">コマンド内のローカル変数の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-308">Supplies the values of local variables in the command.</span></span> <span data-ttu-id="82698-309">コマンド内のローカル変数は、リモート コンピューターでコマンドが実行される前に、これらの値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="82698-309">The variables in the command are replaced by these values before the command is run on the remote computer.</span></span> <span data-ttu-id="82698-310">コンマ区切りのリストで、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="82698-310">Enter the values in a comma-separated list.</span></span> <span data-ttu-id="82698-311">値は、一覧表示されている順序で変数に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="82698-311">Values are associated with variables in the order that they're listed.</span></span> <span data-ttu-id="82698-312">**ArgumentList** のエイリアスは Args です。</span><span class="sxs-lookup"><span data-stu-id="82698-312">The alias for **ArgumentList** is Args.</span></span>

<span data-ttu-id="82698-313">**ArgumentList** パラメーターの値には、1024などの実際の値を指定することも、ローカル変数 (など) への参照を指定することもでき `$max` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-313">The values in the **ArgumentList** parameter can be actual values, such as 1024, or they can be references to local variables, such as `$max`.</span></span>

<span data-ttu-id="82698-314">コマンド内でローカル変数を使用するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-314">To use local variables in a command, use the following command format:</span></span>

<span data-ttu-id="82698-315">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` または `<local-variable>`</span><span class="sxs-lookup"><span data-stu-id="82698-315">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -or- `<local-variable>`</span></span>

<span data-ttu-id="82698-316">**Param** キーワードは、コマンドで使用されるローカル変数を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="82698-316">The **param** keyword lists the local variables that are used in the command.</span></span> <span data-ttu-id="82698-317">**ArgumentList** は、変数の値を一覧の順序で指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-317">**ArgumentList** supplies the values of the variables, in the order that they're listed.</span></span> <span data-ttu-id="82698-318">**ArgumentList** の動作の詳細については、「 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-318">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-319">-AsJob</span><span class="sxs-lookup"><span data-stu-id="82698-319">-AsJob</span></span>

<span data-ttu-id="82698-320">このコマンドレットがリモートコンピューター上でコマンドをバックグラウンドジョブとして実行することを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-320">Indicates that this cmdlet runs the command as a background job on a remote computer.</span></span> <span data-ttu-id="82698-321">このパラメーターを使用して、完了までに時間のかかるコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-321">Use this parameter to run commands that take an extensive time to finish.</span></span>

<span data-ttu-id="82698-322">**AsJob** パラメーターを使用すると、コマンドによってジョブを表すオブジェクトが返され、コマンドプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82698-322">When you use the **AsJob** parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span> <span data-ttu-id="82698-323">ジョブが完了しても、引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="82698-323">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="82698-324">ジョブを管理するには、 `*-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-324">To manage the job, use the `*-Job` cmdlets.</span></span> <span data-ttu-id="82698-325">ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-325">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="82698-326">**AsJob** パラメーターはコマンドレットを使用して、 `Invoke-Command` `Start-Job` コマンドレットをリモートで実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-326">The **AsJob** parameter resembles using the `Invoke-Command` cmdlet to run a `Start-Job` cmdlet remotely.</span></span> <span data-ttu-id="82698-327">ただし、 **AsJob** を使用すると、ジョブがリモートコンピューター上で実行されている場合でも、ジョブはローカルコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="82698-327">However, with **AsJob** , the job is created on the local computer, even though the job runs on a remote computer.</span></span> <span data-ttu-id="82698-328">リモートジョブの結果は、自動的にローカルコンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="82698-328">The results of the remote job are automatically returned to the local computer.</span></span>

<span data-ttu-id="82698-329">PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](About/about_Jobs.md) 」および「 [about_Remote_Jobs](About/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-329">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-330">-認証</span><span class="sxs-lookup"><span data-stu-id="82698-330">-Authentication</span></span>

<span data-ttu-id="82698-331">ユーザーの資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-331">Specifies the mechanism that's used to authenticate the user's credentials.</span></span> <span data-ttu-id="82698-332">CredSSP 認証は、windows Vista、Windows Server 2008、およびそれ以降のバージョンの Windows オペレーティングシステムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="82698-332">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="82698-333">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82698-333">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="82698-334">Default</span><span class="sxs-lookup"><span data-stu-id="82698-334">Default</span></span>
- <span data-ttu-id="82698-335">Basic</span><span class="sxs-lookup"><span data-stu-id="82698-335">Basic</span></span>
- <span data-ttu-id="82698-336">Credssp</span><span class="sxs-lookup"><span data-stu-id="82698-336">Credssp</span></span>
- <span data-ttu-id="82698-337">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="82698-337">Digest</span></span>
- <span data-ttu-id="82698-338">Kerberos</span><span class="sxs-lookup"><span data-stu-id="82698-338">Kerberos</span></span>
- <span data-ttu-id="82698-339">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="82698-339">Negotiate</span></span>
- <span data-ttu-id="82698-340">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="82698-340">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="82698-341">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="82698-341">The default value is Default.</span></span>

<span data-ttu-id="82698-342">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-342">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="82698-343">ユーザーの資格情報が認証対象のリモート コンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモート ネットワーク共有にアクセスする場合など、複数のリソースの認証を必要とするコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="82698-343">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="82698-344">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="82698-344">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="82698-345">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="82698-345">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span> <span data-ttu-id="82698-346">詳細については、「 [Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-346">For more information, see [Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-347">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="82698-347">-CertificateThumbprint</span></span>

<span data-ttu-id="82698-348">切断されたセッションに接続するためのアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-348">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="82698-349">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="82698-349">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="82698-350">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="82698-350">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="82698-351">ローカルユーザーアカウントにしかマップできず、ドメインアカウントでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="82698-351">They can be mapped only to local user accounts and they don't work with domain accounts.</span></span>

<span data-ttu-id="82698-352">証明書の拇印を取得するに `Get-Item` は、 `Get-ChildItem` PowerShell Cert: ドライブでまたはコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-352">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="82698-353">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="82698-353">-ComputerName</span></span>

<span data-ttu-id="82698-354">コマンドを実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-354">Specifies the computers on which the command runs.</span></span> <span data-ttu-id="82698-355">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="82698-355">The default is the local computer.</span></span>

<span data-ttu-id="82698-356">**ComputerName** パラメーターを使用すると、PowerShell は、指定されたコマンドを実行するためだけに使用され、その後閉じられる一時的な接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="82698-356">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that's used only to run the specified command and is then closed.</span></span> <span data-ttu-id="82698-357">永続的な接続が必要な場合は、 **Session** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-357">If you need a persistent connection, use the **Session** parameter.</span></span>

<span data-ttu-id="82698-358">コンマ区切りのリストで、1 台または複数のコンピューターの NETBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="82698-358">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="82698-359">ローカルコンピューターを指定するには、コンピューター名、localhost、またはドット () を入力し `.` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-359">To specify the local computer, type the computer name, localhost, or a dot (`.`).</span></span>

<span data-ttu-id="82698-360">**ComputerName** の値に IP アドレスを使用するには、コマンドに **Credential** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="82698-360">To use an IP address in the value of **ComputerName** , the command must include the **Credential** parameter.</span></span> <span data-ttu-id="82698-361">コンピューターが HTTPS トランスポート用に構成されているか、リモートコンピューターの IP アドレスがローカルコンピューターの WinRM **TrustedHosts** 一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82698-361">The computer must be configured for the HTTPS transport or the IP address of the remote computer must be included in the local computer's WinRM **TrustedHosts** list.</span></span> <span data-ttu-id="82698-362">**TrustedHosts** の一覧にコンピューター名を追加する手順については、「 [コンピューターを信頼されたホストの一覧に追加する方法](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-362">For instructions to add a computer name to the **TrustedHosts** list, see [How to Add a Computer to the Trusted Host List](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span></span>

<span data-ttu-id="82698-363">Windows Vista 以降のバージョンの Windows オペレーティングシステムでは、ローカルコンピューターを **ComputerName** の値に含めるには、[ **管理者として実行** ] オプションを使用して PowerShell を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82698-363">On Windows Vista and later versions of the Windows operating system, to include the local computer in the value of **ComputerName** , you must run PowerShell using the **Run as administrator** option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-364">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="82698-364">-ConfigurationName</span></span>

<span data-ttu-id="82698-365">新しい **PSSession** に使用するセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-365">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="82698-366">セッション構成の構成名または完全修飾リソース URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="82698-366">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="82698-367">構成名だけを指定した場合は、次のスキーマ URI が付加され `http://schemas.microsoft.com/PowerShell` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-367">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="82698-368">セッションのセッション構成は、リモート コンピューター上にあります。</span><span class="sxs-lookup"><span data-stu-id="82698-368">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="82698-369">指定したセッション構成がリモートコンピューターに存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="82698-369">If the specified session configuration doesn't exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="82698-370">既定値は、 `$PSSessionConfigurationName` ローカルコンピューター上のユーザー設定変数の値です。</span><span class="sxs-lookup"><span data-stu-id="82698-370">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="82698-371">このユーザー設定変数が設定されていない場合、既定値は [ **Microsoft. PowerShell** ] です。</span><span class="sxs-lookup"><span data-stu-id="82698-371">If this preference variable isn't set, the default is **Microsoft.PowerShell**.</span></span> <span data-ttu-id="82698-372">詳細については、「 [about_Preference_Variables](about/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-372">For more information, see [about_Preference_Variables](about/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="82698-373">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="82698-373">-ConnectionUri</span></span>

<span data-ttu-id="82698-374">セッションの接続エンドポイントを定義する Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-374">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint of the session.</span></span>
<span data-ttu-id="82698-375">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82698-375">The URI must be fully qualified.</span></span>

<span data-ttu-id="82698-376">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82698-376">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="82698-377">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82698-377">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="82698-378">接続 URI を指定しない場合は、 **UseSSL** パラメーターと **Port** パラメーターを使用して接続 uri の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82698-378">If you don't specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="82698-379">URI の **Transport** セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="82698-379">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="82698-380">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準ポート80で HTTP と443が HTTPS 用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="82698-380">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with the standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="82698-381">PowerShell リモート処理に既定のポートを使用するには、HTTP の場合はポート5985、HTTPS の場合は5986を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-381">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="82698-382">対象のコンピューターが接続を別の URI にリダイレクトする場合、コマンドで **Allowredirection** パラメーターを使用しない限り、PowerShell によってリダイレクトが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="82698-382">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: Uri, FilePathUri
Aliases: URI, CU

Required: False
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-383">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="82698-383">-ContainerId</span></span>

<span data-ttu-id="82698-384">コンテナー Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-384">Specifies an array of container IDs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="82698-385">-Credential</span><span class="sxs-lookup"><span data-stu-id="82698-385">-Credential</span></span>

<span data-ttu-id="82698-386">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-386">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="82698-387">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="82698-387">The default is the current user.</span></span>

<span data-ttu-id="82698-388">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-388">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="82698-389">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="82698-389">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="82698-390">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="82698-390">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="82698-391">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-391">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName
Aliases:

Required: True (VMId, VMName, FilePathVMId, FilePathVMName), False (ComputerName, FilePathComputerName, Uri, FilePathUri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="82698-392">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="82698-392">-EnableNetworkAccess</span></span>

<span data-ttu-id="82698-393">このコマンドレットが、ループバックセッションに対話型セキュリティトークンを追加することを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-393">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="82698-394">対話型トークンを使用すると、他のコンピューターからデータを取得するコマンドをループバック セッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="82698-394">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="82698-395">たとえば、リモート コンピューターからローカル コンピューターに XML ファイルをコピーするコマンドをセッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="82698-395">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="82698-396">ループバックセッションは、同じコンピューター上で発生して終了する **PSSession** です。</span><span class="sxs-lookup"><span data-stu-id="82698-396">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="82698-397">ループバックセッションを作成するには、 **ComputerName** パラメーターを省略するか、値をドット ( `.` )、localhost、またはローカルコンピューターの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="82698-397">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (`.`), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="82698-398">既定では、ループバックセッションはネットワークトークンを使用して作成されますが、リモートコンピューターに対して認証を行うための十分なアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82698-398">By default, loopback sessions are created using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="82698-399">**EnableNetworkAccess** パラメーターは、ループバック セッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="82698-399">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="82698-400">リモートコンピューターでセッションを作成するときに **EnableNetworkAccess** を使用すると、コマンドは成功しますが、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="82698-400">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="82698-401">**認証** パラメーターの **CredSSP** 値を使用して、ループバックセッションでリモートアクセスを許可できます。これにより、セッションの資格情報が他のコンピューターに委任されます。</span><span class="sxs-lookup"><span data-stu-id="82698-401">You can allow remote access in a loopback session using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="82698-402">悪意のあるアクセスからコンピューターを保護するために、 **EnableNetworkAccess** を使用して作成された対話型トークンを持つ切断されたループバックセッションは、セッションが作成されたコンピューターからのみ再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="82698-402">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created using **EnableNetworkAccess** , can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="82698-403">CredSSP 認証を使用するセッションが切断された場合には、他のコンピューターから再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="82698-403">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="82698-404">詳細については、「`Disconnect-PSSession`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-404">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="82698-405">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="82698-405">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-406">-FilePath</span><span class="sxs-lookup"><span data-stu-id="82698-406">-FilePath</span></span>

<span data-ttu-id="82698-407">このコマンドレットが1つ以上のリモートコンピューターで実行するローカルスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-407">Specifies a local script that this cmdlet runs on one or more remote computers.</span></span> <span data-ttu-id="82698-408">スクリプトのパスとファイル名を入力するか、パイプを介してへのスクリプトパスを指定し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-408">Enter the path and filename of the script, or pipe a script path to `Invoke-Command`.</span></span> <span data-ttu-id="82698-409">スクリプトは、ローカルコンピューターまたはローカルコンピューターがアクセスできるディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82698-409">The script must exist on the local computer or in a directory that the local computer can access.</span></span> <span data-ttu-id="82698-410">**ArgumentList** を使用して、スクリプト内のパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-410">Use **ArgumentList** to specify the values of parameters in the script.</span></span>

<span data-ttu-id="82698-411">このパラメーターを使用すると、PowerShell は指定されたスクリプトファイルの内容をスクリプトブロックに変換し、スクリプトブロックをリモートコンピューターに送信して、リモートコンピューター上で実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-411">When you use this parameter, PowerShell converts the contents of the specified script file to a script block, transmits the script block to the remote computer, and runs it on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-412">-HideComputerName</span><span class="sxs-lookup"><span data-stu-id="82698-412">-HideComputerName</span></span>

<span data-ttu-id="82698-413">このコマンドレットは、出力表示から各オブジェクトのコンピューター名を省略することを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-413">Indicates that this cmdlet omits the computer name of each object from the output display.</span></span> <span data-ttu-id="82698-414">既定では、オブジェクトを生成したコンピューター名が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="82698-414">By default, the name of the computer that generated the object appears in the display.</span></span>

<span data-ttu-id="82698-415">このパラメーターが有効なのは、出力の表示だけです。</span><span class="sxs-lookup"><span data-stu-id="82698-415">This parameter affects only the output display.</span></span> <span data-ttu-id="82698-416">オブジェクトは変更されません。</span><span class="sxs-lookup"><span data-stu-id="82698-416">It doesn't change the object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases: HCN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-417">-InDisconnectedSession</span><span class="sxs-lookup"><span data-stu-id="82698-417">-InDisconnectedSession</span></span>

<span data-ttu-id="82698-418">このコマンドレットが、切断されたセッションでコマンドまたはスクリプトを実行することを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-418">Indicates that this cmdlet runs a command or script in a disconnected session.</span></span>

<span data-ttu-id="82698-419">**Indisconnectedsession** パラメーターを使用すると、は `Invoke-Command` 各リモートコンピューター上に永続的なセッションを作成し、 **ScriptBlock** または **FilePath** パラメーターで指定されたコマンドを開始してから、セッションから切断します。</span><span class="sxs-lookup"><span data-stu-id="82698-419">When you use the **InDisconnectedSession** parameter, `Invoke-Command` creates a persistent session on each remote computer, starts the command specified by the **ScriptBlock** or **FilePath** parameter, and then disconnects from the session.</span></span> <span data-ttu-id="82698-420">これらのコマンドは、切断されたセッションで引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="82698-420">The commands continue to run in the disconnected sessions.</span></span> <span data-ttu-id="82698-421">**Indisconnectedsession** を使用すると、リモートセッションへの接続を維持せずにコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="82698-421">**InDisconnectedSession** enables you to run commands without maintaining a connection to the remote sessions.</span></span> <span data-ttu-id="82698-422">また、セッションは、結果が返される前に切断されるため、 **Indisconnectedsession** は、セッション間で分割されるのではなく、すべてのコマンドの結果が再接続されたセッションに返されるようにします。</span><span class="sxs-lookup"><span data-stu-id="82698-422">And, because the session is disconnected before any results are returned, **InDisconnectedSession** makes sure that all command results are returned to the reconnected session, instead of being split between sessions.</span></span>

<span data-ttu-id="82698-423">**セッション** パラメーターまたは **AsJob** パラメーターと共に **indisconnectedsession** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="82698-423">You can't use **InDisconnectedSession** with the **Session** parameter or the **AsJob** parameter.</span></span>

<span data-ttu-id="82698-424">**Indisconnectedsession** を使用するコマンドは、切断されたセッションを表す **PSSession** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="82698-424">Commands that use **InDisconnectedSession** return a **PSSession** object that represents the disconnected session.</span></span> <span data-ttu-id="82698-425">コマンドの出力は返されません。</span><span class="sxs-lookup"><span data-stu-id="82698-425">They don't return the command output.</span></span> <span data-ttu-id="82698-426">切断されたセッションに接続するに `Connect-PSSession` は、コマンドレットまたはコマンドレットを使用し `Receive-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-426">To connect to the disconnected session, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span> <span data-ttu-id="82698-427">セッションで実行されたコマンドの結果を取得するには、コマンドレットを使用し `Receive-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-427">To get the results of commands that ran in the session, use the `Receive-PSSession` cmdlet.</span></span> <span data-ttu-id="82698-428">切断されたセッションで出力を生成するコマンドを実行するには、 **OutputBufferingMode** session オプションの値を **Drop** に設定します。</span><span class="sxs-lookup"><span data-stu-id="82698-428">To run commands that generate output in a disconnected session, set the value of the **OutputBufferingMode** session option to **Drop**.</span></span> <span data-ttu-id="82698-429">切断されたセッションに接続する場合は、セッションのアイドルタイムアウトを設定して、セッションを削除する前に接続するのに十分な時間を確保できるようにします。</span><span class="sxs-lookup"><span data-stu-id="82698-429">If you intend to connect to the disconnected session, set the idle time-out in the session so that it provides sufficient time for you to connect before deleting the session.</span></span>

<span data-ttu-id="82698-430">**Sessionoption** パラメーターまたはユーザー設定変数で、出力バッファーモードとアイドルタイムアウトを設定でき `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-430">You can set the output buffering mode and idle time-out in the **SessionOption** parameter or in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="82698-431">セッションオプションの詳細については、「」および about_Preference_Variables を参照してください `New-PSSessionOption` 。 [about_Preference_Variables](./about/about_preference_variables.md)</span><span class="sxs-lookup"><span data-stu-id="82698-431">For more information about session options, see `New-PSSessionOption` and [about_Preference_Variables](./about/about_preference_variables.md).</span></span>

<span data-ttu-id="82698-432">切断されたセッションの機能の詳細については、「[about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-432">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="82698-433">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="82698-433">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-434">-InputObject</span><span class="sxs-lookup"><span data-stu-id="82698-434">-InputObject</span></span>

<span data-ttu-id="82698-435">コマンドへの入力を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-435">Specifies input to the command.</span></span> <span data-ttu-id="82698-436">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="82698-436">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="82698-437">**InputObject** パラメーターを使用する場合は、 `$Input` **ScriptBlock** パラメーターの値で自動変数を使用して入力オブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="82698-437">When using the **InputObject** parameter, use the `$Input` automatic variable in the value of the **ScriptBlock** parameter to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="82698-438">-JobName</span><span class="sxs-lookup"><span data-stu-id="82698-438">-JobName</span></span>

<span data-ttu-id="82698-439">バックグラウンド ジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-439">Specifies a friendly name for the background job.</span></span> <span data-ttu-id="82698-440">既定では、ジョブにはという名前が付けられ `Job<n>` ます。ここで、 `<n>` は序数です。</span><span class="sxs-lookup"><span data-stu-id="82698-440">By default, jobs are named `Job<n>`, where `<n>` is an ordinal number.</span></span>

<span data-ttu-id="82698-441">コマンドで **JobName** パラメーターを使用すると、コマンドはジョブとして実行され、 `Invoke-Command` コマンドに **AsJob** が含まれていない場合でも、ジョブオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="82698-441">If you use the **JobName** parameter in a command, the command is run as a job, and `Invoke-Command` returns a job object, even if you don't include **AsJob** in the command.</span></span>

<span data-ttu-id="82698-442">PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](./About/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-442">For more information about PowerShell background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

```yaml
Type: System.String
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-443">-None Wscope</span><span class="sxs-lookup"><span data-stu-id="82698-443">-NoNewScope</span></span>

<span data-ttu-id="82698-444">このコマンドレットが、指定されたコマンドを現在のスコープ内で実行することを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-444">Indicates that this cmdlet runs the specified command in the current scope.</span></span> <span data-ttu-id="82698-445">既定では、は `Invoke-Command` 独自のスコープでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-445">By default, `Invoke-Command` runs commands in their own scope.</span></span>

<span data-ttu-id="82698-446">このパラメーターは、現在のセッションで実行されるコマンド、つまり、 **ComputerName** および **Session** の両パラメーターを除外したコマンド内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="82698-446">This parameter is valid only in commands that are run in the current session, that is, commands that omit both the **ComputerName** and **Session** parameters.</span></span>

<span data-ttu-id="82698-447">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="82698-447">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InProcess
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-448">-Port</span><span class="sxs-lookup"><span data-stu-id="82698-448">-Port</span></span>

<span data-ttu-id="82698-449">このコマンドに使用するリモートコンピューターのネットワークポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-449">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="82698-450">リモート コンピューターに接続するには、リモート コンピューターで、接続に使用されるポートをリッスンすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="82698-450">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="82698-451">既定のポートは 5985 (HTTP の場合は WinRM ポート)、5986 (HTTPS の場合は WinRM ポート) です。</span><span class="sxs-lookup"><span data-stu-id="82698-451">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="82698-452">別のポートを使用する場合には、そのポートでリッスンするようにリモート コンピューターの WinRM リスナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="82698-452">Before using an alternate port, configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="82698-453">リスナーを構成するには、PowerShell プロンプトで次の2つのコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="82698-453">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="82698-454">必要な場合を除き、 **Port** パラメーターは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="82698-454">Don't use the **Port** parameter unless you must.</span></span> <span data-ttu-id="82698-455">コマンドに設定されているポートは、コマンドが実行されるすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="82698-455">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="82698-456">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="82698-456">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-457">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="82698-457">-RunAsAdministrator</span></span>

<span data-ttu-id="82698-458">このコマンドレットが管理者としてコマンドを呼び出すことを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-458">Indicates that this cmdlet invokes a command as an Administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-459">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="82698-459">-ScriptBlock</span></span>

<span data-ttu-id="82698-460">実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-460">Specifies the commands to run.</span></span> <span data-ttu-id="82698-461">コマンドを中かっこで囲み、 `{ }` スクリプトブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="82698-461">Enclose the commands in curly braces `{ }` to create a script block.</span></span>
<span data-ttu-id="82698-462">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="82698-462">This parameter is required.</span></span>

<span data-ttu-id="82698-463">既定では、コマンド内のどの変数もリモート コンピューター上で評価されます。</span><span class="sxs-lookup"><span data-stu-id="82698-463">By default, any variables in the command are evaluated on the remote computer.</span></span> <span data-ttu-id="82698-464">コマンドにローカル変数を含めるには、 **ArgumentList** を使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-464">To include local variables in the command, use **ArgumentList**.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, ContainerId
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-465">-セッション</span><span class="sxs-lookup"><span data-stu-id="82698-465">-Session</span></span>

<span data-ttu-id="82698-466">このコマンドレットがコマンドを実行するセッションの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-466">Specifies an array of sessions in which this cmdlet runs the command.</span></span> <span data-ttu-id="82698-467">**Pssession** オブジェクトを含む変数、 **PSSession** `New-PSSession` またはコマンドやコマンドなどの pssession オブジェクトを作成または取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-467">Enter a variable that contains **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="82698-468">**PSSession** を作成すると、PowerShell によって、リモートコンピューターへの永続的な接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="82698-468">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="82698-469">**PSSession** を使用して、データを共有する一連の関連コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82698-469">Use a **PSSession** to run a series of related commands that share data.</span></span> <span data-ttu-id="82698-470">1つのコマンドまたは一連の関連のないコマンドを実行するには、 **ComputerName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-470">To run a single command or a series of unrelated commands, use the **ComputerName** parameter.</span></span> <span data-ttu-id="82698-471">詳細については、「 [about_PSSessions](./About/about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-471">For more information, see [about_PSSessions](./About/about_PSSessions.md).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session, FilePathRunspace
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-472">-セッション名</span><span class="sxs-lookup"><span data-stu-id="82698-472">-SessionName</span></span>

<span data-ttu-id="82698-473">切断されたセッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-473">Specifies a friendly name for a disconnected session.</span></span> <span data-ttu-id="82698-474">この名前を使用して、コマンドなどの後続のコマンドでセッションを参照することができ `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-474">You can use the name to refer to the session in subsequent commands, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="82698-475">このパラメーターは、 **InDisconnectedSession** パラメーターと共に使用する場合に限り有効です。</span><span class="sxs-lookup"><span data-stu-id="82698-475">This parameter is valid only with the **InDisconnectedSession** parameter.</span></span>

<span data-ttu-id="82698-476">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="82698-476">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-477">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="82698-477">-SessionOption</span></span>

<span data-ttu-id="82698-478">セッションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-478">Specifies advanced options for the session.</span></span> <span data-ttu-id="82698-479">コマンドレットを使用して作成する **sessionoption** オブジェクト、 `New-PSSessionOption` またはキーがセッションオプションの名前で、値がセッションオプションの値であるハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="82698-479">Enter a **SessionOption** object, such as one that you create using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="82698-480">オプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-480">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="82698-481">それ以外の場合、既定値はセッション構成で設定されたオプションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="82698-481">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="82698-482">セッションオプションの値は、ユーザー設定変数およびセッション構成で設定されたセッションの既定値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-482">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="82698-483">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="82698-483">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="82698-484">既定値を含むセッションオプションの説明については、「」を参照してください `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="82698-484">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="82698-485">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-485">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="82698-486">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-486">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-487">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="82698-487">-ThrottleLimit</span></span>

<span data-ttu-id="82698-488">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-488">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="82698-489">このパラメーターを省略した場合、または値 0 を入力した場合は、既定値の 32 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="82698-489">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="82698-490">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="82698-490">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-491">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="82698-491">-UseSSL</span></span>

<span data-ttu-id="82698-492">このコマンドレットが、リモートコンピューターへの接続を確立するために Secure Sockets Layer (SSL) プロトコルを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-492">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="82698-493">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="82698-493">By default, SSL isn't used.</span></span>

<span data-ttu-id="82698-494">WS-Management は、ネットワーク経由で送信されるすべての PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="82698-494">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="82698-495">**UseSSL** パラメーターは、HTTP ではなく HTTPS 経由でデータを送信する追加の保護です。</span><span class="sxs-lookup"><span data-stu-id="82698-495">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span>

<span data-ttu-id="82698-496">このパラメーターを使用しても、コマンドに使用されているポートで SSL が使用できない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="82698-496">If you use this parameter, but SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82698-497">-VMId</span><span class="sxs-lookup"><span data-stu-id="82698-497">-VMId</span></span>

<span data-ttu-id="82698-498">仮想マシンの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-498">Specifies an array of IDs of virtual machines.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: VMId, FilePathVMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="82698-499">-VMName</span><span class="sxs-lookup"><span data-stu-id="82698-499">-VMName</span></span>

<span data-ttu-id="82698-500">仮想マシンの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="82698-500">Specifies an array of names of virtual machines.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName, FilePathVMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="82698-501">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="82698-501">CommonParameters</span></span>

<span data-ttu-id="82698-502">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="82698-502">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="82698-503">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-503">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="82698-504">入力</span><span class="sxs-lookup"><span data-stu-id="82698-504">INPUTS</span></span>

### <span data-ttu-id="82698-505">システムの管理. ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="82698-505">System.Management.Automation.ScriptBlock</span></span>

<span data-ttu-id="82698-506">パイプを使用して、スクリプトブロック内のコマンドをにパイプすることができ `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="82698-506">You can pipe a command in a script block to `Invoke-Command`.</span></span> <span data-ttu-id="82698-507">`$Input`コマンド内の入力オブジェクトを表すには、自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-507">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="82698-508">出力</span><span class="sxs-lookup"><span data-stu-id="82698-508">OUTPUTS</span></span>

### <span data-ttu-id="82698-509">システムの管理. PSRemotingJob、System...、または呼び出されたコマンドの出力です。</span><span class="sxs-lookup"><span data-stu-id="82698-509">System.Management.Automation.PSRemotingJob, System.Management.Automation.Runspaces.PSSession, or the output of the invoked command</span></span>

<span data-ttu-id="82698-510">**AsJob** パラメーターを使用した場合、このコマンドレットはジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="82698-510">This cmdlet returns a job object, if you use the **AsJob** parameter.</span></span> <span data-ttu-id="82698-511">**Indisconnectedsession** パラメーターを指定すると、は `Invoke-Command` **PSSession** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="82698-511">If you specify the **InDisconnectedSession** parameter, `Invoke-Command` returns a **PSSession** object.</span></span> <span data-ttu-id="82698-512">それ以外の場合は、呼び出されたコマンドの出力を返します。これは **ScriptBlock** パラメーターの値です。</span><span class="sxs-lookup"><span data-stu-id="82698-512">Otherwise, it returns the output of the invoked command, which is the value of the **ScriptBlock** parameter.</span></span>

## <span data-ttu-id="82698-513">注</span><span class="sxs-lookup"><span data-stu-id="82698-513">NOTES</span></span>

<span data-ttu-id="82698-514">Windows Vista 以降のバージョンの Windows オペレーティングシステムでは、の **ComputerName** パラメーターを使用して `Invoke-Command` ローカルコンピューターでコマンドを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82698-514">On Windows Vista, and later versions of the Windows operating system, to use the **ComputerName** parameter of `Invoke-Command` to run a command on the local computer, you must run PowerShell using the **Run as administrator** option.</span></span>

<span data-ttu-id="82698-515">複数のコンピューターでコマンドを実行すると、PowerShell は、一覧に表示されている順序でコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="82698-515">When you run commands on multiple computers, PowerShell connects to the computers in the order in which they appear in the list.</span></span> <span data-ttu-id="82698-516">ただし、コマンドの出力は、リモートコンピューターから受信した順序で表示されますが、異なる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="82698-516">However, the command output is displayed in the order that it's received from the remote computers, which might be different.</span></span>

<span data-ttu-id="82698-517">実行するコマンドによって発生したエラー `Invoke-Command` は、コマンドの結果に含まれています。</span><span class="sxs-lookup"><span data-stu-id="82698-517">Errors that result from the command that `Invoke-Command` runs are included in the command results.</span></span>
<span data-ttu-id="82698-518">ローカル コマンドでは "終了するエラー" となるエラーは、リモート コマンドでは "終了しないエラー" として扱われます。</span><span class="sxs-lookup"><span data-stu-id="82698-518">Errors that would be terminating errors in a local command are treated as non-terminating errors in a remote command.</span></span> <span data-ttu-id="82698-519">この方法を使用すると、1台のコンピューターでエラーが発生しても、実行されているすべてのコンピューターでコマンドが終了しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="82698-519">This strategy makes sure that terminating errors on one computer don't close the command on all computers on which it's run.</span></span> <span data-ttu-id="82698-520">また、この方法は、1 台のコンピューターでリモート コマンドを実行する場合にも、使用されます。</span><span class="sxs-lookup"><span data-stu-id="82698-520">This practice is used even when a remote command is run on a single computer.</span></span>

<span data-ttu-id="82698-521">リモートコンピューターがローカルコンピューターによって信頼されているドメインにない場合、そのコンピューターはユーザーの資格情報を認証できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82698-521">If the remote computer isn't in a domain that the local computer trusts, the computer might not be able to authenticate the user's credentials.</span></span> <span data-ttu-id="82698-522">WS-MANAGEMENT の信頼されたホストの一覧にリモートコンピューターを追加するには、プロバイダーで次のコマンドを使用し `WSMAN` ます。ここで、 `<Remote-Computer-Name>` はリモートコンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="82698-522">To add the remote computer to the list of trusted hosts in WS-Management, use the following command in the `WSMAN` provider, where `<Remote-Computer-Name>` is the name of the remote computer:</span></span>

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

<span data-ttu-id="82698-523">**Indisconnectedsession** パラメーターを使用して **PSSession** を切断すると、セッション状態は **Disconnected** になり、可用性は **None** になります。</span><span class="sxs-lookup"><span data-stu-id="82698-523">When you disconnect a **PSSession** using the **InDisconnectedSession** parameter, the session state is **Disconnected** and the availability is **None**.</span></span> <span data-ttu-id="82698-524">**State** プロパティの値は、現在のセッションに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="82698-524">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="82698-525">値が **Disconnected** の場合は、 **PSSession** が現在のセッションに接続されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-525">A value of **Disconnected** means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="82698-526">ただし、 **PSSession** がすべてのセッションから切断されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="82698-526">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="82698-527">別のセッションに接続されている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="82698-527">It might be connected to a different session.</span></span> <span data-ttu-id="82698-528">セッションに接続または再接続できるかどうかを確認するには、 **Availability** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="82698-528">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

<span data-ttu-id="82698-529">**Availability** の値が **None** の場合は、セッションに接続できることを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-529">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="82698-530">値が **Busy** の場合は、PSSession が別のセッションに接続されているため、 **PSSession** に接続できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="82698-530">A value of **Busy** indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span> <span data-ttu-id="82698-531">セッションの **State** プロパティの値の詳細については、「 [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-531">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span> <span data-ttu-id="82698-532">セッションの **Availability** プロパティの値の詳細については、「 [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82698-532">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="82698-533">関連リンク</span><span class="sxs-lookup"><span data-stu-id="82698-533">RELATED LINKS</span></span>

[<span data-ttu-id="82698-534">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="82698-534">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="82698-535">about_Remote</span><span class="sxs-lookup"><span data-stu-id="82698-535">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="82698-536">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="82698-536">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="82698-537">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="82698-537">about_Remote_Troubleshooting</span></span>](./About/about_remote_troubleshooting.md)

[<span data-ttu-id="82698-538">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="82698-538">about_Remote_Variables</span></span>](./About/about_Remote_Variables.md)

[<span data-ttu-id="82698-539">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="82698-539">about_Scopes</span></span>](./About/about_scopes.md)

[<span data-ttu-id="82698-540">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="82698-540">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="82698-541">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="82698-541">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="82698-542">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="82698-542">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="82698-543">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="82698-543">Invoke-Item</span></span>](../Microsoft.PowerShell.Management/Invoke-Item.md)

[<span data-ttu-id="82698-544">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="82698-544">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="82698-545">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="82698-545">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="82698-546">WSMan プロバイダー</span><span class="sxs-lookup"><span data-stu-id="82698-546">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

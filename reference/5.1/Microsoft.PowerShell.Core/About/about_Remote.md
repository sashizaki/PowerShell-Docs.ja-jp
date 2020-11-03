---
description: Windows PowerShell でリモートコマンドを実行する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote に関するページ
ms.openlocfilehash: ce75863c616bebcdb4a8273c287271b9feea3396
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223312"
---
# <a name="about-remote"></a><span data-ttu-id="f0e0b-104">リモートの概要</span><span class="sxs-lookup"><span data-stu-id="f0e0b-104">About Remote</span></span>

## <a name="short-description"></a><span data-ttu-id="f0e0b-105">概要</span><span class="sxs-lookup"><span data-stu-id="f0e0b-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="f0e0b-106">Windows PowerShell でリモートコマンドを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-106">Describes how to run remote commands in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="f0e0b-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="f0e0b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f0e0b-108">一時接続または固定接続を使用して、1台のコンピューターまたは複数のコンピューターでリモートコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-108">You can run remote commands on a single computer or on multiple computers by using a temporary or persistent connection.</span></span> <span data-ttu-id="f0e0b-109">また、1台のリモートコンピューターで対話型セッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-109">You can also start an interactive session with a single remote computer.</span></span>

<span data-ttu-id="f0e0b-110">このトピックでは、さまざまな種類のリモートコマンドを実行する方法を示す一連の例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-110">This topic provides a series of examples to show you how to run different types of remote command.</span></span> <span data-ttu-id="f0e0b-111">これらの基本的なコマンドを実行した後、これらのコマンドで使用される各コマンドレットについて説明しているヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-111">After you try these basic commands, read the Help topics that describe each cmdlet that is used in these commands.</span></span> <span data-ttu-id="f0e0b-112">これらのトピックでは、詳細を説明し、ニーズに合わせてコマンドを変更する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-112">The topics provide the details and explain how you can modify the commands to meet your needs.</span></span>

<span data-ttu-id="f0e0b-113">注: Windows PowerShell リモート処理を使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-113">Note: To use Windows PowerShell remoting, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="f0e0b-114">詳細については、「[about_Remote_Requirements](about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-114">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

## <a name="how-to-start-an-interactive-session-enter-pssession"></a><span data-ttu-id="f0e0b-115">対話型セッションを開始する方法 (ENTER PSSESSION)</span><span class="sxs-lookup"><span data-stu-id="f0e0b-115">HOW TO START AN INTERACTIVE SESSION (ENTER-PSSESSION)</span></span>

<span data-ttu-id="f0e0b-116">リモートコマンドを実行する最も簡単な方法は、リモートコンピューターとの対話型セッションを開始することです。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-116">The easiest way to run remote commands is to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="f0e0b-117">セッションが開始されると、入力したコマンドはリモートコンピューター上で直接入力した場合と同様に、リモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-117">When the session starts, the commands that you type run on the remote computer, just as though you typed them directly on the remote computer.</span></span> <span data-ttu-id="f0e0b-118">各対話型セッションでは、1台のコンピューターにのみ接続できます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-118">You can connect to only one computer in each interactive session.</span></span>

<span data-ttu-id="f0e0b-119">対話型セッションを開始するには、Enter-PSSession コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-119">To start an interactive session, use the Enter-PSSession cmdlet.</span></span> <span data-ttu-id="f0e0b-120">次のコマンドは、Server01 コンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-120">The following command starts an interactive session with the Server01 computer:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="f0e0b-121">コマンドプロンプトが変更され、Server01 コンピューターに接続されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-121">The command prompt changes to indicate that you are connected to the Server01 computer.</span></span>

```
Server01\PS>
```

<span data-ttu-id="f0e0b-122">これで、Server01 コンピューターにコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-122">Now, you can type commands on the Server01 computer.</span></span>

<span data-ttu-id="f0e0b-123">対話型セッションを終了するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-123">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="f0e0b-124">詳細については、「PSSession」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-124">For more information, see Enter-PSSession.</span></span>

## <a name="how-to-use-cmdlets-that-have-a-computername-parameter-to-get-remote-data"></a><span data-ttu-id="f0e0b-125">COMPUTERNAME パラメーターを持つコマンドレットを使用してリモートデータを取得する方法</span><span class="sxs-lookup"><span data-stu-id="f0e0b-125">HOW TO USE CMDLETS THAT HAVE A COMPUTERNAME PARAMETER TO GET REMOTE DATA</span></span>

<span data-ttu-id="f0e0b-126">いくつかのコマンドレットには、リモートコンピューターからオブジェクトを取得できる ComputerName パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-126">Several cmdlets have a ComputerName parameter that lets you get objects from remote computers.</span></span>

<span data-ttu-id="f0e0b-127">これらのコマンドレットは WS-MANAGEMENT ベースの Windows PowerShell リモート処理を使用しないため、Windows PowerShell を実行している任意のコンピューターでこれらのコマンドレットの ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-127">Because these cmdlets do not use WS-Management-based Windows PowerShell remoting, you can use the ComputerName parameter of these cmdlets on any computer that is running Windows PowerShell.</span></span> <span data-ttu-id="f0e0b-128">コンピューターは、Windows PowerShell リモート処理用に構成する必要はありません。また、コンピューターがリモート処理のシステム要件を満たしている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-128">The computers do not have to be configured for Windows PowerShell remoting, and the computers do not have to meet the system requirements for remoting.</span></span>

<span data-ttu-id="f0e0b-129">次のコマンドレットには ComputerName パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-129">The following cmdlets have a ComputerName parameter:</span></span>

```
Clear-EventLog    Limit-EventLog
Get-Counter       New-EventLog
Get-EventLog      Remove-EventLog
Get-HotFix        Restart-Computer
Get-Process       Show-EventLog
Get-Service       Stop-Computer
Get-WinEvent      Test-Connection
Get-WmiObject     Write-EventLog
```

<span data-ttu-id="f0e0b-130">たとえば、次のコマンドは、Server01 リモートコンピューター上のサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-130">For example, the following command gets the services on the Server01 remote computer:</span></span>

```powershell
Get-Service -ComputerName Server01
```

<span data-ttu-id="f0e0b-131">通常、特別な構成なしでリモート処理をサポートするコマンドレットには **ComputerName** パラメーターがあり、 **セッション** パラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-131">Typically, cmdlets that support remoting without special configuration have a **ComputerName** parameter and do not have a **Session** parameter.</span></span> <span data-ttu-id="f0e0b-132">セッションでこれらのコマンドレットを見つけるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-132">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | Where-Object {
  $_.Parameters.Keys -contains 'ComputerName' -and
  $_.Parameters.Keys -notcontains 'Session'
}
```

## <a name="how-to-run-a-remote-command"></a><span data-ttu-id="f0e0b-133">リモートコマンドを実行する方法</span><span class="sxs-lookup"><span data-stu-id="f0e0b-133">HOW TO RUN A REMOTE COMMAND</span></span>

<span data-ttu-id="f0e0b-134">リモートコンピューターで他のコマンドを実行するには、Invoke-Command コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-134">To run other commands on remote computers, use the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="f0e0b-135">1つのコマンドまたはいくつかの関連のないコマンドを実行するには、Invoke-Command の ComputerName パラメーターを使用して、リモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-135">To run a single command or a few unrelated commands, use the ComputerName parameter of Invoke-Command to specify the remote computers.</span></span> <span data-ttu-id="f0e0b-136">ScriptBlock パラメーターを使用して、コマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-136">Use the ScriptBlock parameter to specify the command.</span></span>

<span data-ttu-id="f0e0b-137">たとえば、次のコマンドは、Server01 コンピューターで Get-Culture コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-137">For example, the following command runs a Get-Culture command on the Server01 computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="f0e0b-138">ComputerName パラメーターは、1つまたは複数のコンピューターで1つのコマンドまたは複数の関連のないコマンドを実行する状況を想定して設計されています。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-138">The ComputerName parameter is designed for situation in which you run a single command or several unrelated commands on one or many computers.</span></span> <span data-ttu-id="f0e0b-139">リモートコンピューターへの永続的な接続を確立するには、Session パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-139">To establish a persistent connection to a remote computer, use the Session parameter.</span></span>

## <a name="how-to-create-a-persistent-connection-pssession"></a><span data-ttu-id="f0e0b-140">永続的な接続を作成する方法 (PSSESSION)</span><span class="sxs-lookup"><span data-stu-id="f0e0b-140">HOW TO CREATE A PERSISTENT CONNECTION (PSSESSION)</span></span>

<span data-ttu-id="f0e0b-141">Invoke-Command コマンドレットの ComputerName パラメーターを使用すると、Windows PowerShell はコマンドに対してのみ接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-141">When you use the ComputerName parameter of the Invoke-Command cmdlet, Windows PowerShell establishes a connection just for the command.</span></span> <span data-ttu-id="f0e0b-142">そのため、コマンドが完了すると接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-142">Then, it closes the connection when the command is complete.</span></span> <span data-ttu-id="f0e0b-143">コマンドで定義されている変数または関数はすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-143">Any variables or functions that are defined in the command are lost.</span></span>

<span data-ttu-id="f0e0b-144">リモートコンピューターへの永続的な接続を作成するには、New-PSSession コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-144">To create a persistent connection to a remote computer, use the New-PSSession cmdlet.</span></span> <span data-ttu-id="f0e0b-145">たとえば、次のコマンドは、Server01 コンピューターと Server02 コンピューター上に pssession を作成し、PSSessions を $s 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-145">For example, the following command creates PSSessions on the Server01 and Server02 computers and then saves the PSSessions in the $s variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="f0e0b-146">PSSESSION でコマンドを実行する方法</span><span class="sxs-lookup"><span data-stu-id="f0e0b-146">HOW TO RUN COMMANDS IN A PSSESSION</span></span>

<span data-ttu-id="f0e0b-147">PSSession を使用すると、関数、別名、変数の値などのデータを共有する一連のリモートコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-147">With a PSSession, you can run a series of remote commands that share data, like functions, aliases, and the values of variables.</span></span> <span data-ttu-id="f0e0b-148">PSSession でコマンドを実行するには、Invoke-Command コマンドレットの Session パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-148">To run commands in a PSSession, use the Session parameter of the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="f0e0b-149">たとえば、次のコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューターと Server02 コンピューター上の pssession で Get-Process コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-149">For example, the following command uses the Invoke-Command cmdlet to run a Get-Process command in the PSSessions on the Server01 and Server02 computers.</span></span>
<span data-ttu-id="f0e0b-150">このコマンドは、各 PSSession の $p 変数にプロセスを保存します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-150">The command saves the processes in a $p variable in each PSSession.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process}
```

<span data-ttu-id="f0e0b-151">PSSession は永続的な接続を使用するので、$p 変数を使用するのと同じ PSSession で別のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-151">Because the PSSession uses a persistent connection, you can run another command in the same PSSession that uses the $p variable.</span></span> <span data-ttu-id="f0e0b-152">次のコマンドは $p に保存されているプロセスの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-152">The following command counts the number of processes saved in $p.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p.count}
```

## <a name="how-to-run-a-remote-command-on-multiple-computers"></a><span data-ttu-id="f0e0b-153">複数のコンピューターでリモートコマンドを実行する方法</span><span class="sxs-lookup"><span data-stu-id="f0e0b-153">HOW TO RUN A REMOTE COMMAND ON MULTIPLE COMPUTERS</span></span>

<span data-ttu-id="f0e0b-154">複数のコンピューターでリモートコマンドを実行するには、Invoke-Command の ComputerName パラメーターの値にすべてのコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-154">To run a remote command on multiple computers, type all of the computer names in the value of the ComputerName parameter of Invoke-Command.</span></span> <span data-ttu-id="f0e0b-155">名前はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-155">Separate the names with commas.</span></span>

<span data-ttu-id="f0e0b-156">たとえば、次のコマンドは、3台のコンピューターで Get-Culture コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-156">For example, the following command runs a Get-Culture command on three computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="f0e0b-157">複数の pssession でコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-157">You can also run a command in multiple PSSessions.</span></span> <span data-ttu-id="f0e0b-158">次のコマンドは、Server01、Server02、および Server03 コンピューター上に pssession を作成し、各 pssession で Get-Culture コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-158">The following commands create PSSessions on the Server01, Server02, and Server03 computers and then run a Get-Culture command in each of the PSSessions.</span></span>

```powershell
$s = New-PSSession -ComputerName S1, S2, S3
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="f0e0b-159">コンピューターのローカルコンピューターの一覧を含めるには、ローカルコンピューターの名前を入力するか、ドット (.) を入力するか、「localhost」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-159">To include the local computer list of computers, type the name of the local computer, type a dot (.), or type  "localhost".</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3, localhost -ScriptBlock {Get-Culture}
```

## <a name="how-to-run-a-script-on-remote-computers"></a><span data-ttu-id="f0e0b-160">リモートコンピューターでスクリプトを実行する方法</span><span class="sxs-lookup"><span data-stu-id="f0e0b-160">HOW TO RUN A SCRIPT ON REMOTE COMPUTERS</span></span>

<span data-ttu-id="f0e0b-161">リモートコンピューターでローカルスクリプトを実行するには、コマンドの FilePath パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-161">To run a local script on remote computers, use the FilePath parameter of Invoke-Command.</span></span>

<span data-ttu-id="f0e0b-162">たとえば、次のコマンドは、S1 および S2 コンピューターで Sample.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-162">For example, the following command runs the Sample.ps1 script on the S1 and S2 computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -FilePath C:\Test\Sample.ps1
```

<span data-ttu-id="f0e0b-163">スクリプトの結果がローカルコンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-163">The results of the script are returned to the local computer.</span></span> <span data-ttu-id="f0e0b-164">ファイルをコピーする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-164">You do not need to copy any files.</span></span>

## <a name="how-to-stop-a-remote-command"></a><span data-ttu-id="f0e0b-165">リモートコマンドを停止する方法</span><span class="sxs-lookup"><span data-stu-id="f0e0b-165">HOW TO STOP A REMOTE COMMAND</span></span>

<span data-ttu-id="f0e0b-166">コマンドを中断するには、CTRL + C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-166">To interrupt a command, press CTRL+C.</span></span> <span data-ttu-id="f0e0b-167">割り込み要求は、リモートコマンドを終了するリモートコンピューターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-167">The interrupt request is passed to the remote computer where it terminates the remote command.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f0e0b-168">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f0e0b-168">FOR MORE INFORMATION</span></span>

- <span data-ttu-id="f0e0b-169">リモート処理のシステム要件の詳細については、「 [about_Remote_Requirements](about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-169">For information about the system requirements for remoting, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

- <span data-ttu-id="f0e0b-170">リモート出力の書式設定のヘルプについては、「 [about_Remote_Output](about_Remote_Output.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-170">For help in formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

- <span data-ttu-id="f0e0b-171">リモート処理のしくみ、リモートデータの管理方法、特別な構成、セキュリティの問題、およびその他のよく寄せられる質問については、「 [about_Remote_FAQ](about_Remote_FAQ.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-171">For information about how remoting works, how to manage remote data, special configurations, security issues, and other frequently asked questions, see [about_Remote_FAQ](about_Remote_FAQ.md).</span></span>

- <span data-ttu-id="f0e0b-172">リモート処理エラーの解決については、「about_Remote_Troubleshooting」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-172">For help in resolving remoting errors, see about_Remote_Troubleshooting.</span></span>

- <span data-ttu-id="f0e0b-173">PSSessions と永続的な接続の詳細については、「 [about_PSSessions](about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-173">For information about PSSessions and persistent connections, see [about_PSSessions](about_PSSessions.md).</span></span>

- <span data-ttu-id="f0e0b-174">Windows PowerShell のバックグラウンドジョブの詳細については、「 [about_Jobs](about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0e0b-174">For information about Windows PowerShell background jobs, see [about_Jobs](about_Jobs.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="f0e0b-175">KEYWORDS</span><span class="sxs-lookup"><span data-stu-id="f0e0b-175">KEYWORDS</span></span>

<span data-ttu-id="f0e0b-176">about_Remoting</span><span class="sxs-lookup"><span data-stu-id="f0e0b-176">about_Remoting</span></span>

## <a name="see-also"></a><span data-ttu-id="f0e0b-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0e0b-177">SEE ALSO</span></span>

[<span data-ttu-id="f0e0b-178">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="f0e0b-178">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="f0e0b-179">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="f0e0b-179">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="f0e0b-180">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="f0e0b-180">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="f0e0b-181">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="f0e0b-181">about_Remote_FAQ</span></span>](about_Remote_FAQ.md)

[<span data-ttu-id="f0e0b-182">about_Remote_TroubleShooting</span><span class="sxs-lookup"><span data-stu-id="f0e0b-182">about_Remote_TroubleShooting</span></span>](about_Remote_TroubleShooting.md)

[<span data-ttu-id="f0e0b-183">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="f0e0b-183">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="f0e0b-184">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="f0e0b-184">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="f0e0b-185">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f0e0b-185">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="f0e0b-186">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f0e0b-186">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 553b61c9669afab325e9feec101d701c2b9a7c83
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218264"
---
# <span data-ttu-id="d8a7d-103">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="d8a7d-103">Restart-Computer</span></span>

## <span data-ttu-id="d8a7d-104">概要</span><span class="sxs-lookup"><span data-stu-id="d8a7d-104">SYNOPSIS</span></span>
<span data-ttu-id="d8a7d-105">ローカルコンピューターとリモートコンピューターのオペレーティングシステムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-105">Restarts the operating system on local and remote computers.</span></span>

## <span data-ttu-id="d8a7d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d8a7d-106">SYNTAX</span></span>

### <span data-ttu-id="d8a7d-107">DefaultSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="d8a7d-107">DefaultSet (Default)</span></span>

```
Restart-Computer [-DcomAuthentication <AuthenticationLevel>] [-Impersonation <ImpersonationLevel>]
 [-WsmanAuthentication <String>] [-Protocol <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d8a7d-108">AsJobSet</span><span class="sxs-lookup"><span data-stu-id="d8a7d-108">AsJobSet</span></span>

```
Restart-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>]
 [-Impersonation <ImpersonationLevel>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Force] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d8a7d-109">Description</span><span class="sxs-lookup"><span data-stu-id="d8a7d-109">DESCRIPTION</span></span>

<span data-ttu-id="d8a7d-110">コマンドレットにより、 `Restart-Computer` ローカルコンピューターとリモートコンピューターのオペレーティングシステムが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-110">The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.</span></span>

<span data-ttu-id="d8a7d-111">のパラメーターを使用し `Restart-Computer` て、バックグラウンドジョブとして再起動操作を実行し、認証レベルと代替資格情報を指定し、同時に実行される操作を制限し、即時再起動を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-111">You can use the parameters of `Restart-Computer` to run the restart operations as a background job, to specify the authentication levels and alternate credentials, to limit the operations that run at the same time, and to force an immediate restart.</span></span>

<span data-ttu-id="d8a7d-112">Windows PowerShell 3.0 以降では、再起動が完了するのを待ってから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-112">Starting in Windows PowerShell 3.0, you can wait for the restart to complete before you run the next command.</span></span> <span data-ttu-id="d8a7d-113">待機中のタイムアウトとクエリ間隔を指定し、再起動されたコンピューターで特定のサービスが利用可能になるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-113">Specify a waiting time-out and query interval, and wait for particular services to be available on the restarted computer.</span></span> <span data-ttu-id="d8a7d-114">この機能により、スクリプトや関数でを使用することが実用的になり `Restart-Computer` ます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-114">This feature makes it practical to use `Restart-Computer` in scripts and functions.</span></span>

<span data-ttu-id="d8a7d-115">エンタープライズファイアウォールなどによって分散コンポーネントオブジェクトモデル (DCOM) の呼び出しがブロックされている場合は、WS-Management (WSMan) プロトコルを使用してコンピューターを再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-115">You can use the WS-Management (WSMan) protocol to restart the computer, in case Distributed Component Object Model (DCOM) calls are blocked, such as by an enterprise firewall.</span></span> <span data-ttu-id="d8a7d-116">詳細については、「 [WS-Management プロトコル](/windows/desktop/WinRM/ws-management-protocol)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-116">For more information, see [WS-Management Protocol](/windows/desktop/WinRM/ws-management-protocol).</span></span>

<span data-ttu-id="d8a7d-117">このコマンドレットは、コマンドで **AsJob** パラメーターを使用する場合にだけ、Windows PowerShell のリモート処理を必要とします。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-117">This cmdlet requires Windows PowerShell remoting only when you use the **AsJob** parameter in a command.</span></span>

## <span data-ttu-id="d8a7d-118">例</span><span class="sxs-lookup"><span data-stu-id="d8a7d-118">EXAMPLES</span></span>

### <span data-ttu-id="d8a7d-119">例 1: ローカルコンピューターを再起動する</span><span class="sxs-lookup"><span data-stu-id="d8a7d-119">Example 1: Restart the local computer</span></span>

<span data-ttu-id="d8a7d-120">`Restart-Computer` ローカルコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-120">`Restart-Computer` restarts the local computer.</span></span>

```powershell
Restart-Computer
```

### <span data-ttu-id="d8a7d-121">例 2: 複数のコンピューターを再起動する</span><span class="sxs-lookup"><span data-stu-id="d8a7d-121">Example 2: Restart multiple computers</span></span>

<span data-ttu-id="d8a7d-122">`Restart-Computer` リモートコンピューターとローカルコンピューターを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-122">`Restart-Computer` can restart remote and local computers.</span></span> <span data-ttu-id="d8a7d-123">**ComputerName** パラメーターは、コンピューター名の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-123">The **ComputerName** parameter accepts an array of computer names.</span></span>

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### <span data-ttu-id="d8a7d-124">例 3: バックグラウンドジョブとしてコンピューターを再起動する</span><span class="sxs-lookup"><span data-stu-id="d8a7d-124">Example 3: Restart computers as a background job</span></span>

<span data-ttu-id="d8a7d-125">これらのコマンドは、 `Restart-Computer` 2 台のリモートコンピューター上でバックグラウンドジョブとしてコマンドを実行し、結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-125">These commands run a `Restart-Computer` command as a background job on two remote computers, and then get the results.</span></span>

<span data-ttu-id="d8a7d-126">**AsJob** はローカルコンピューターにジョブを作成し、結果をローカルコンピューターに自動的に返すため、 `Receive-Job` ローカルコマンドとしてを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-126">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

```powershell
$Job = Restart-Computer -ComputerName "Server01", "Server02" -AsJob
$Job | Receive-Job
```

<span data-ttu-id="d8a7d-127">`Restart-Computer`**ComputerName** パラメーターを使用して、 **Server01** と **Server02** を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-127">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01** and **Server02**.</span></span> <span data-ttu-id="d8a7d-128">**AsJob** パラメーターは、コマンドをバックグラウンドジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-128">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="d8a7d-129">ジョブオブジェクトは変数に格納され `$Job` ます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-129">The job object is stored in the `$Job` variable.</span></span> <span data-ttu-id="d8a7d-130">`$Job` は、 `Receive-Job` 結果を取得するコマンドレットにパイプラインを送信します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-130">`$Job` is sent down the pipeline to the `Receive-Job` cmdlet that gets the results.</span></span>

### <span data-ttu-id="d8a7d-131">例 4: リモートコンピューターを再起動する</span><span class="sxs-lookup"><span data-stu-id="d8a7d-131">Example 4: Restart a remote computer</span></span>

<span data-ttu-id="d8a7d-132">`Restart-Computer` カスタマイズされた偽装と認証の設定を使用してリモートコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-132">`Restart-Computer` restarts a remote computer with customized impersonation and authentication settings.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="d8a7d-133">`Restart-Computer`**ComputerName** パラメーターを使用して **Server01** を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-133">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="d8a7d-134">**権限借用** パラメーターは、要求元の id を非表示にする匿名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-134">The **Impersonation** parameter specifies Anonymous to hide the requester's identity.</span></span> <span data-ttu-id="d8a7d-135">**DcomAuthentication** パラメーターは、接続の認証レベルとして packetintegrity を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-135">The **DcomAuthentication** parameter specifies PacketIntegrity as the connection's authentication level.</span></span>

### <span data-ttu-id="d8a7d-136">例 5: テキストファイルに一覧表示されているコンピューターを強制的に再起動する</span><span class="sxs-lookup"><span data-stu-id="d8a7d-136">Example 5: Force restart of computers listed in a text file</span></span>

<span data-ttu-id="d8a7d-137">この例では、ファイルに一覧表示されているコンピューターを直ちに再起動 `Domain01.txt` します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-137">This example forces an immediate restart of the computers listed in the `Domain01.txt` file.</span></span> <span data-ttu-id="d8a7d-138">テキストファイルからのコンピューター名は、変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-138">The computer names from the text file are stored in a variable.</span></span> <span data-ttu-id="d8a7d-139">**Force** パラメーターは即時再起動を強制し、 **ThrottleLimit** パラメーターは同時接続の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-139">The **Force** parameter forces an immediate restart and the **ThrottleLimit** parameter limits the number of concurrent connections.</span></span>

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force -ThrottleLimit 10
```

<span data-ttu-id="d8a7d-140">`Get-Content`**Path** パラメーターを使用して、 **Domain01.txt** テキストファイルからコンピューター名の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-140">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="d8a7d-141">コンピューター名は変数に格納され `$Names` ます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-141">The computer names are stored in the variable `$Names`.</span></span> <span data-ttu-id="d8a7d-142">`Get-Credential` ユーザー名とパスワードの入力を求め、変数に値を格納し `$Creds` ます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-142">`Get-Credential` prompts you for a username and password and stores the values in the variable `$Creds`.</span></span> <span data-ttu-id="d8a7d-143">`Restart-Computer` では、 **ComputerName** パラメーターと **Credential** パラメーターをその変数と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-143">`Restart-Computer` uses the **ComputerName** and **Credential** parameters with their variables.</span></span> <span data-ttu-id="d8a7d-144">**Force** パラメーターを指定すると、各コンピューターが直ちに再起動されます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-144">The **Force** parameter causes an immediate restart of each computer.</span></span> <span data-ttu-id="d8a7d-145">**ThrottleLimit** パラメーターは、コマンドの同時接続数を10に制限します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-145">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span>

### <span data-ttu-id="d8a7d-146">例 6: リモートコンピューターを再起動し、PowerShell を待機する</span><span class="sxs-lookup"><span data-stu-id="d8a7d-146">Example 6: Restart a remote computer and wait for PowerShell</span></span>

<span data-ttu-id="d8a7d-147">`Restart-Computer` リモートコンピューターを再起動してから、再起動されたコンピューターで PowerShell が使用できるようになるまで最大5分 (300 秒) 待機してから続行します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-147">`Restart-Computer` restarts the remote computer and then waits up to 5 minutes (300 seconds) for PowerShell to become available on the restarted computer before it continues.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

<span data-ttu-id="d8a7d-148">`Restart-Computer`**ComputerName** パラメーターを使用して **Server01** を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-148">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="d8a7d-149">**Wait** パラメーターは、再起動が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-149">The **Wait** parameter waits for the restart to finish.</span></span> <span data-ttu-id="d8a7d-150">**の** は、PowerShell がリモートコンピューターでコマンドを実行できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-150">The **For** specifies that PowerShell can run commands on the remote computer.</span></span> <span data-ttu-id="d8a7d-151">**Timeout** パラメーターは、5分間の待機を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-151">The **Timeout** parameter specifies a five-minute wait.</span></span> <span data-ttu-id="d8a7d-152">**Delay** パラメータは、リモートコンピュータを再起動するかどうかを確認するために、2秒ごとにクエリを行います。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-152">The **Delay** parameter queries the remote computer every two seconds to determine whether it's restarted.</span></span>

### <span data-ttu-id="d8a7d-153">例 7: WSMan プロトコルを使用してコンピューターを再起動する</span><span class="sxs-lookup"><span data-stu-id="d8a7d-153">Example 7: Restart a computer by using the WSMan Protocol</span></span>

<span data-ttu-id="d8a7d-154">`Restart-Computer` 既定の DCOM ではなく、WSMan プロトコルを使用してリモートコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-154">`Restart-Computer` restarts the remote computer by using the WSMan protocol instead of the default, DCOM.</span></span> <span data-ttu-id="d8a7d-155">Kerberos 認証は、現在のユーザーがリモートコンピューターを再起動するアクセス許可を持っているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-155">Kerberos authentication determines whether the current user has permission to restart the remote computer.</span></span>

<span data-ttu-id="d8a7d-156">これらの設定は、dcom がブロックされているために DCOM ベースの再起動が失敗する企業向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-156">These settings are designed for enterprises in which DCOM-based restarts fail because DCOM is blocked.</span></span> <span data-ttu-id="d8a7d-157">たとえば、ファイアウォールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-157">For example, by a firewall.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Protocol WSMan -WsmanAuthentication Kerberos
```

<span data-ttu-id="d8a7d-158">`Restart-Computer`**ComputerName** パラメーターを使用して、リモートコンピューター **Server01** を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-158">`Restart-Computer` uses the **ComputerName** parameter to specify the remote computer, **Server01**.</span></span>
<span data-ttu-id="d8a7d-159">**Protocol** パラメーターは、WSMan プロトコルを使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-159">The **Protocol** parameter specifies to use the WSMan protocol.</span></span> <span data-ttu-id="d8a7d-160">**WsmanAuthentication** パラメーターは、認証方法を **Kerberos** として指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-160">The **WsmanAuthentication** parameter specifies the authentication method as **Kerberos**.</span></span>

## <span data-ttu-id="d8a7d-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d8a7d-161">PARAMETERS</span></span>

### <span data-ttu-id="d8a7d-162">-AsJob</span><span class="sxs-lookup"><span data-stu-id="d8a7d-162">-AsJob</span></span>

<span data-ttu-id="d8a7d-163">が `Restart-Computer` バックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-163">Indicates that `Restart-Computer` runs as a background job.</span></span>

<span data-ttu-id="d8a7d-164">このパラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-164">To use this parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="d8a7d-165">Windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[ **管理者として実行** ] オプションを使用して PowerShell を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-165">On Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as Administrator** option.</span></span> <span data-ttu-id="d8a7d-166">詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-166">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="d8a7d-167">**AsJob** パラメーターを指定すると、コマンドは、バックグラウンドジョブを表すオブジェクトを直ちに返します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-167">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="d8a7d-168">ジョブが完了しても、引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-168">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="d8a7d-169">ジョブは、ローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-169">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="d8a7d-170">ジョブを管理するには、 **Job** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-170">To manage the job, use the **Job** cmdlets.</span></span> <span data-ttu-id="d8a7d-171">ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-171">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="d8a7d-172">Windows PowerShell のバックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-172">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-173">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d8a7d-173">-ComputerName</span></span>

<span data-ttu-id="d8a7d-174">1つのコンピューター名、またはコンピューター名のコンマ区切りの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-174">Specifies one computer name or a comma-separated array of computer names.</span></span> <span data-ttu-id="d8a7d-175">`Restart-Computer` パイプラインまたは変数から **ComputerName** オブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-175">`Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.</span></span>

<span data-ttu-id="d8a7d-176">リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-176">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span> <span data-ttu-id="d8a7d-177">ローカルコンピューターを指定するには、コンピューター名、ドット `.` 、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-177">To specify the local computer, type the computer name, a dot `.`, or localhost.</span></span>

<span data-ttu-id="d8a7d-178">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-178">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="d8a7d-179">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-179">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

<span data-ttu-id="d8a7d-180">**ComputerName** パラメーターが指定されていない場合、は `Restart-Computer` ローカルコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-180">If the **ComputerName** parameter isn't specified, `Restart-Computer` restarts the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="d8a7d-181">-Credential</span></span>

<span data-ttu-id="d8a7d-182">このアクションを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-182">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="d8a7d-183">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-183">The default is the current user.</span></span>

<span data-ttu-id="d8a7d-184">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-184">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d8a7d-185">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-185">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="d8a7d-186">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-186">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="d8a7d-187">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-187">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="d8a7d-188">-DcomAuthentication</span><span class="sxs-lookup"><span data-stu-id="d8a7d-188">-DcomAuthentication</span></span>

<span data-ttu-id="d8a7d-189">WMI 接続に使用する認証レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-189">Specifies the authentication level that is used for the WMI connection.</span></span> <span data-ttu-id="d8a7d-190">`Restart-Computer` WMI を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-190">`Restart-Computer` uses WMI.</span></span>

<span data-ttu-id="d8a7d-191">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-191">Valid values are:</span></span>

- <span data-ttu-id="d8a7d-192">**呼び出し** : 呼び出しレベルの COM 認証</span><span class="sxs-lookup"><span data-stu-id="d8a7d-192">**Call** :            Call-level COM authentication</span></span>
- <span data-ttu-id="d8a7d-193">**接続** : 接続レベルの COM 認証</span><span class="sxs-lookup"><span data-stu-id="d8a7d-193">**Connect** :         Connect-level COM authentication</span></span>
- <span data-ttu-id="d8a7d-194">**既定** : Windows 認証</span><span class="sxs-lookup"><span data-stu-id="d8a7d-194">**Default** :         Windows Authentication</span></span>
- <span data-ttu-id="d8a7d-195">**None** : COM 認証なし</span><span class="sxs-lookup"><span data-stu-id="d8a7d-195">**None** :            No COM authentication</span></span>
- <span data-ttu-id="d8a7d-196">**パケット** : パケットレベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-196">**Packet** :          Packet-level COM authentication.</span></span>
- <span data-ttu-id="d8a7d-197">**Packetintegrity** : パケットの整合性レベルの COM 認証</span><span class="sxs-lookup"><span data-stu-id="d8a7d-197">**PacketIntegrity** : Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="d8a7d-198">**Packetprivacy** : パケットプライバシーレベルの COM 認証。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-198">**PacketPrivacy** :   Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="d8a7d-199">**Unchanged** : 認証レベルは前のコマンドと同じです。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-199">**Unchanged** :       The authentication level is the same as the previous command.</span></span>

<span data-ttu-id="d8a7d-200">詳細については、「 [Authenticationlevel 列挙型](/dotnet/api/system.management.authenticationlevel)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-200">For more information, see [AuthenticationLevel Enumeration](/dotnet/api/system.management.authenticationlevel).</span></span>

<span data-ttu-id="d8a7d-201">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-201">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-202">-Delay</span><span class="sxs-lookup"><span data-stu-id="d8a7d-202">-Delay</span></span>

<span data-ttu-id="d8a7d-203">クエリの頻度を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-203">Specifies the frequency of queries, in seconds.</span></span> <span data-ttu-id="d8a7d-204">PowerShell は、For パラメーターによって指定されたサービスに **対し** てクエリを実行し、コンピューターの再起動後にサービスを使用できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-204">PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.</span></span>

<span data-ttu-id="d8a7d-205">このパラメーターは、 **Wait** パラメーターと **For** パラメーターと共に使用する場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-205">This parameter is valid only together with the **Wait** and **For** parameters.</span></span>

<span data-ttu-id="d8a7d-206">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d8a7d-207">**Delay** パラメーターが指定されていない場合、で `Restart-Computer` は5秒の遅延が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-207">If the **Delay** parameter isn't specified, `Restart-Computer` uses a five second delay.</span></span>

```yaml
Type: System.Int16
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-208">-の場合</span><span class="sxs-lookup"><span data-stu-id="d8a7d-208">-For</span></span>

<span data-ttu-id="d8a7d-209">コンピューターの再起動後に、指定されたサービスまたは機能が使用可能になるのを待機するときの PowerShell の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-209">Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts.</span></span> <span data-ttu-id="d8a7d-210">このパラメーターは、 **Wait** パラメーターでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-210">This parameter is only valid with the **Wait** parameter.</span></span>

<span data-ttu-id="d8a7d-211">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d8a7d-212">**既定値** : PowerShell が再開されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-212">**Default** : Waits for PowerShell to restart.</span></span>
- <span data-ttu-id="d8a7d-213">**Powershell** : コンピューター上の powershell リモートセッションでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-213">**PowerShell** : Can run commands in a PowerShell remote session on the computer.</span></span>
- <span data-ttu-id="d8a7d-214">**WMI** : コンピューターの Win32_ComputerSystem クエリへの応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-214">**WMI** : Receives a reply to a Win32_ComputerSystem query for the computer.</span></span>
- <span data-ttu-id="d8a7d-215">**WinRM** : ws-management を使用して、コンピューターへのリモートセッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-215">**WinRM** : Can establish a remote session to the computer by using WS-Management.</span></span>

<span data-ttu-id="d8a7d-216">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-216">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: DefaultSet
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-217">-Force</span><span class="sxs-lookup"><span data-stu-id="d8a7d-217">-Force</span></span>

<span data-ttu-id="d8a7d-218">コンピューターの即時再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-218">Forces an immediate restart of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-219">-偽装</span><span class="sxs-lookup"><span data-stu-id="d8a7d-219">-Impersonation</span></span>

<span data-ttu-id="d8a7d-220">このコマンドレットが WMI を呼び出すために使用する偽装レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-220">Specifies the impersonation level that this cmdlet uses to call WMI.</span></span> <span data-ttu-id="d8a7d-221">`Restart-Computer` WMI を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-221">`Restart-Computer` uses WMI.</span></span>
<span data-ttu-id="d8a7d-222">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d8a7d-223">**既定** 値: 既定の偽装。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-223">**Default** : Default impersonation.</span></span> <span data-ttu-id="d8a7d-224">名前にかかわらず、これは既定値ではありません。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-224">Despite the name, this isn't the default value.</span></span>
- <span data-ttu-id="d8a7d-225">**Anonymous** : 呼び出し元の id を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-225">**Anonymous** : Hides the identity of the caller.</span></span>
- <span data-ttu-id="d8a7d-226">**識別** : オブジェクトが呼び出し元の資格情報を照会できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-226">**Identify** : Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="d8a7d-227">**Impersonate** : オブジェクトが呼び出し元の資格情報を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-227">**Impersonate** : Allows objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-228">-Protocol</span><span class="sxs-lookup"><span data-stu-id="d8a7d-228">-Protocol</span></span>

<span data-ttu-id="d8a7d-229">コンピューターの再起動にどのプロトコルを使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-229">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="d8a7d-230">有効な値は **WSMan** と **DCOM** です。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-230">The valid values are **WSMan** and **DCOM**.</span></span>

<span data-ttu-id="d8a7d-231">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-232">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d8a7d-232">-ThrottleLimit</span></span>

<span data-ttu-id="d8a7d-233">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-233">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="d8a7d-234">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-234">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="d8a7d-235">**ThrottleLimit** パラメーターが指定されていない場合、または値0が使用されている場合、では `Restart-Computer` 最大32の同時接続が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-235">If the **ThrottleLimit** parameter isn't specified or a value of 0 is used, `Restart-Computer` uses a maximum of 32 concurrent connections.</span></span>

```yaml
Type: System.Int32
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-236">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="d8a7d-236">-Timeout</span></span>

<span data-ttu-id="d8a7d-237">待機期間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-237">Specifies the duration of the wait, in seconds.</span></span> <span data-ttu-id="d8a7d-238">タイムアウトが経過すると、 `Restart-Computer` コンピューターが再起動されていない場合でも、はコマンドプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-238">When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.</span></span>

<span data-ttu-id="d8a7d-239">**Timeout** パラメーターは、 **Wait** パラメーターと共にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-239">The **Timeout** parameter is only valid with the **Wait** parameter.</span></span> <span data-ttu-id="d8a7d-240">**Timeout** は、 **待機** パラメーターの無期限の待機期間をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-240">**Timeout** overrides the **Wait** parameter's indefinite waiting period.</span></span>

<span data-ttu-id="d8a7d-241">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-241">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultSet
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-242">-Wait</span><span class="sxs-lookup"><span data-stu-id="d8a7d-242">-Wait</span></span>

<span data-ttu-id="d8a7d-243">`Restart-Computer` PowerShell プロンプトを非表示にし、コンピューターが再起動されるまでパイプラインをブロックします。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-243">`Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted.</span></span> <span data-ttu-id="d8a7d-244">このパラメーターをスクリプトで使用すると、コンピューターを再起動し、再起動が完了したときに処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-244">You can use this parameter in a script to restart computers and then continue to process when the restart is finished.</span></span>

<span data-ttu-id="d8a7d-245">**Wait** パラメーターは、コンピューターが再起動するまで無期限に待機します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-245">The **Wait** parameter waits indefinitely for the computers to restart.</span></span> <span data-ttu-id="d8a7d-246">**タイムアウト** を使用してタイミングを調整し、 **For** および **Delay** パラメーターを使用して、再起動されたコンピューターで特定のサービスが利用可能になるまで待機することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-246">You can use **Timeout** to adjust the timing and the **For** and **Delay** parameters to wait for particular services to become available on the restarted computers.</span></span>

<span data-ttu-id="d8a7d-247">ローカルコンピューターを再起動する場合、 **Wait** パラメーターは無効です。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-247">The **Wait** parameter isn't valid when you're restarting the local computer.</span></span> <span data-ttu-id="d8a7d-248">**ComputerName** パラメーターの値にリモートコンピューターとローカルコンピューターの名前が含まれている場合、は、 `Restart-Computer` ローカルコンピューターの **待機** に対して終了しないエラーを生成しますが、リモートコンピューターの再起動を待機します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-248">If the value of the **ComputerName** parameter contains the names of remote computers and the local computer, `Restart-Computer` generates a non-terminating error for **Wait** on the local computer, but waits for the remote computers to restart.</span></span>

<span data-ttu-id="d8a7d-249">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-250">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="d8a7d-250">-WsmanAuthentication</span></span>

<span data-ttu-id="d8a7d-251">ユーザー資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-251">Specifies the mechanism that is used to authenticate the user credentials.</span></span> <span data-ttu-id="d8a7d-252">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-252">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d8a7d-253">このパラメーターに指定できる値は、 **Basic** 、 **CredSSP** 、 **Default** 、 **Digest** 、 **Kerberos** 、および **Negotiate** です。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-253">The acceptable values for this parameter are: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** , and **Negotiate**.</span></span>

<span data-ttu-id="d8a7d-254">詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-254">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="d8a7d-255">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-255">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="d8a7d-256">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-256">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="d8a7d-257">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-257">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8a7d-258">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d8a7d-258">-Confirm</span></span>

<span data-ttu-id="d8a7d-259">実行前に確認メッセージを表示 `Restart-Computer` します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-259">Prompts you for confirmation before running `Restart-Computer`.</span></span>

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

### <span data-ttu-id="d8a7d-260">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d8a7d-260">-WhatIf</span></span>

<span data-ttu-id="d8a7d-261">が実行された場合に何が起こるかを示し `Restart-Computer` ます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-261">Shows what would happen if the `Restart-Computer` runs.</span></span> <span data-ttu-id="d8a7d-262">`Restart-Computer`コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-262">The `Restart-Computer` cmdlet isn't run.</span></span>

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

### <span data-ttu-id="d8a7d-263">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8a7d-263">CommonParameters</span></span>

<span data-ttu-id="d8a7d-264">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-264">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d8a7d-265">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-265">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d8a7d-266">入力</span><span class="sxs-lookup"><span data-stu-id="d8a7d-266">INPUTS</span></span>

### <span data-ttu-id="d8a7d-267">System.String</span><span class="sxs-lookup"><span data-stu-id="d8a7d-267">System.String</span></span>

<span data-ttu-id="d8a7d-268">`Restart-Computer` パイプラインまたは変数のコンピューター名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-268">`Restart-Computer` accepts computer names from the pipeline or variables.</span></span>

<span data-ttu-id="d8a7d-269">Windows PowerShell 2.0 では、 **ComputerName** パラメーターはプロパティ名によるパイプラインからの入力だけを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-269">In Windows PowerShell 2.0, the **ComputerName** parameter takes input from the pipeline only by property name.</span></span> <span data-ttu-id="d8a7d-270">Windows PowerShell 3.0 以降では、 **ComputerName** パラメーターはパイプラインからの値によって入力を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-270">In Windows PowerShell 3.0, and later, the **ComputerName** parameter takes input from the pipeline by value.</span></span>

## <span data-ttu-id="d8a7d-271">出力</span><span class="sxs-lookup"><span data-stu-id="d8a7d-271">OUTPUTS</span></span>

### <span data-ttu-id="d8a7d-272">なし、システムの管理. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="d8a7d-272">None, System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="d8a7d-273">**AsJob** パラメーターを指定すると、は `Restart-Computer` ジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-273">If you specify the **AsJob** parameter, `Restart-Computer` returns a job object.</span></span> <span data-ttu-id="d8a7d-274">それ以外には出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-274">Otherwise, no output is generated.</span></span>

## <span data-ttu-id="d8a7d-275">注</span><span class="sxs-lookup"><span data-stu-id="d8a7d-275">NOTES</span></span>

- <span data-ttu-id="d8a7d-276">`Restart-Computer` Windows を実行しているコンピューターでのみ機能し、ローカルシステムを含むシステムをシャットダウンするには、WinRM と WMI が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-276">`Restart-Computer` only work on computers running Windows and requires WinRM and WMI to shutdown a system, including the local system.</span></span>
- <span data-ttu-id="d8a7d-277">`Restart-Computer`Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem)クラスの[Win32Shutdown メソッド](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-277">`Restart-Computer` uses the [Win32Shutdown method](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) of the Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) class.</span></span>  <span data-ttu-id="d8a7d-278">この方法では、コンピューターの再起動に使用するユーザーアカウントに対して、 **Seshutdownprivilege** 特権を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-278">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="d8a7d-279">Windows PowerShell 2.0 では、リモートコンピューターを再起動または停止する場合、 **AsJob** パラメーターは確実に動作しません。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-279">In Windows PowerShell 2.0, the **AsJob** parameter doesn't work reliably when you are restarting or stopping remote computers.</span></span> <span data-ttu-id="d8a7d-280">Windows PowerShell 3.0 では、この問題を解決するように実装が変更されました。</span><span class="sxs-lookup"><span data-stu-id="d8a7d-280">In Windows PowerShell 3.0, the implementation is changed to resolve this problem.</span></span>

## <span data-ttu-id="d8a7d-281">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d8a7d-281">RELATED LINKS</span></span>

[<span data-ttu-id="d8a7d-282">Windows リモート管理について</span><span class="sxs-lookup"><span data-stu-id="d8a7d-282">About Windows Remote Management</span></span>](/windows/desktop/WinRM/about-windows-remote-management)

[<span data-ttu-id="d8a7d-283">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="d8a7d-283">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="d8a7d-284">WS-Management Protocol (WS-Management プロトコル)</span><span class="sxs-lookup"><span data-stu-id="d8a7d-284">WS-Management Protocol</span></span>](/windows/desktop/WinRM/ws-management-protocol)

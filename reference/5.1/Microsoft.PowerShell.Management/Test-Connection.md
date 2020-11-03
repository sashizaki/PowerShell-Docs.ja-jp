---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: a8d3923db69a20cfada58391944b592cf999e6ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214336"
---
# <span data-ttu-id="9375d-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="9375d-103">Test-Connection</span></span>

## <span data-ttu-id="9375d-104">概要</span><span class="sxs-lookup"><span data-stu-id="9375d-104">SYNOPSIS</span></span>
<span data-ttu-id="9375d-105">ICMP エコー要求パケット (ping) を1台以上のコンピューターに送信します。</span><span class="sxs-lookup"><span data-stu-id="9375d-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="9375d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9375d-106">SYNTAX</span></span>

### <span data-ttu-id="9375d-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="9375d-107">Default (Default)</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="9375d-108">source</span><span class="sxs-lookup"><span data-stu-id="9375d-108">Source</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="9375d-109">静的</span><span class="sxs-lookup"><span data-stu-id="9375d-109">Quiet</span></span>

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## <span data-ttu-id="9375d-110">Description</span><span class="sxs-lookup"><span data-stu-id="9375d-110">DESCRIPTION</span></span>

<span data-ttu-id="9375d-111">`Test-Connection`コマンドレットは、インターネット制御メッセージプロトコル (ICMP) エコー要求パケット (ping) を1つ以上のリモートコンピューターに送信し、エコー応答応答を返します。</span><span class="sxs-lookup"><span data-stu-id="9375d-111">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="9375d-112">このコマンドレットを使用すると、特定のコンピューターに IP ネットワーク経由で接続できるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="9375d-112">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="9375d-113">のパラメーターを使用し `Test-Connection` て、送信側と受信側の両方のコンピューターの指定、バックグラウンドジョブとしてのコマンドの実行、タイムアウトと ping の回数の設定、および接続と認証の構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9375d-113">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="9375d-114">使い慣れた **ping** コマンドとは異なり、は `Test-Connection` PowerShell で調査できる **Win32_PingStatus** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9375d-114">Unlike the familiar **ping** command, `Test-Connection` returns a **Win32_PingStatus** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="9375d-115">**Quiet** パラメーターは、テストされた各接続の **ブール値を** **system.string オブジェクトで返します。**</span><span class="sxs-lookup"><span data-stu-id="9375d-115">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="9375d-116">複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-116">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="9375d-117">例</span><span class="sxs-lookup"><span data-stu-id="9375d-117">EXAMPLES</span></span>

### <span data-ttu-id="9375d-118">例 1: リモートコンピューターにエコー要求を送信する</span><span class="sxs-lookup"><span data-stu-id="9375d-118">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="9375d-119">この例では、エコー要求パケットをローカルコンピューターから Server01 コンピューターに送信します。</span><span class="sxs-lookup"><span data-stu-id="9375d-119">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -ComputerName Server01
```

```Output
Source        Destination     IPV4Address     IPV6Address  Bytes    Time(ms)
------        -----------     -----------     -----------  -----    --------
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       1
```

<span data-ttu-id="9375d-120">`Test-Connection`**ComputerName** パラメーターを使用して、Server01 コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-120">`Test-Connection` uses the **ComputerName** parameter to specify the Server01 computer.</span></span>

### <span data-ttu-id="9375d-121">例 2: 複数のコンピューターにエコー要求を送信する</span><span class="sxs-lookup"><span data-stu-id="9375d-121">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="9375d-122">この例では、ローカルコンピューターから複数のリモートコンピューターに ping を送信します。</span><span class="sxs-lookup"><span data-stu-id="9375d-122">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### <span data-ttu-id="9375d-123">例 3: 複数のコンピューターからコンピューターにエコー要求を送信する</span><span class="sxs-lookup"><span data-stu-id="9375d-123">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="9375d-124">この例では、別のソースコンピューターから1台のリモートコンピューター Server01 に ping を送信します。</span><span class="sxs-lookup"><span data-stu-id="9375d-124">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="9375d-125">`Test-Connection` は、 **Credential** パラメーターを使用して、ソースコンピューターから ping 要求を送信するアクセス許可を持つユーザーの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-125">`Test-Connection` uses the **Credential** parameter to specify the credentials of a user who has permission to send a ping request from the source computers.</span></span> <span data-ttu-id="9375d-126">複数のポイントからの接続の待機時間をテストするには、このコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="9375d-126">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="9375d-127">例 4: パラメーターを使用してテストコマンドをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="9375d-127">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="9375d-128">この例では、のパラメーターを使用し `Test-Connection` て、コマンドをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="9375d-128">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="9375d-129">ローカルコンピューターからリモートコンピューターに ping テストが送信されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-129">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

<span data-ttu-id="9375d-130">`Test-Connection`**ComputerName** パラメーターを使用して Server01 を指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-130">`Test-Connection` uses the **ComputerName** parameter to specify Server01.</span></span> <span data-ttu-id="9375d-131">**Count** パラメーターは、3秒間隔の **遅延** で Server01 コンピューターに送信される3つの ping を指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-131">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="9375d-132">これらのオプションは、ホップ数の増加またはトラフィックの多いネットワーク状態が原因で ping 応答が通常よりも長くかかることが予想される場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="9375d-132">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="9375d-133">例 5: バックグラウンドジョブとしてテストを実行する</span><span class="sxs-lookup"><span data-stu-id="9375d-133">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="9375d-134">この例では、 `Test-Connection` PowerShell バックグラウンドジョブとしてコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9375d-134">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

<span data-ttu-id="9375d-135">コマンドは、 `Test-Connection` 企業内の多くのコンピューターに ping を実行します。</span><span class="sxs-lookup"><span data-stu-id="9375d-135">The `Test-Connection` command pings many computers in an enterprise.</span></span> <span data-ttu-id="9375d-136">**ComputerName** パラメーターの値は `Get-Content` 、からコンピューター名の一覧を読み取るコマンドです `Servers.txt file` 。</span><span class="sxs-lookup"><span data-stu-id="9375d-136">The value of the **ComputerName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt file`.</span></span> <span data-ttu-id="9375d-137">このコマンドは、 **AsJob** パラメーターを使用して、バックグラウンドジョブとしてコマンドを実行し、そのジョブを変数に保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="9375d-137">The command uses the **AsJob** parameter to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="9375d-138">コマンドは、 `if` ジョブがまだ実行されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9375d-138">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="9375d-139">ジョブが実行されていない場合は、 `Receive-Job` 結果を取得して変数に格納し `$Results` ます。</span><span class="sxs-lookup"><span data-stu-id="9375d-139">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="9375d-140">例 6: 資格情報を使用してリモートコンピューターに Ping を実行する</span><span class="sxs-lookup"><span data-stu-id="9375d-140">Example 6: Ping a remote computer with credentials</span></span>

<span data-ttu-id="9375d-141">このコマンドは、 `Test-Connection` コマンドレットを使用してリモートコンピューターに ping を実行します。</span><span class="sxs-lookup"><span data-stu-id="9375d-141">This command uses the `Test-Connection` cmdlet to ping a remote computer.</span></span>

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

<span data-ttu-id="9375d-142">このコマンドは、 **Credential** パラメーターを使用して、リモートコンピューターに ping を実行するアクセス許可を持つユーザーアカウントを指定し、 **impersonation** パラメーターを使用して偽装レベルを **識別** するように変更します。</span><span class="sxs-lookup"><span data-stu-id="9375d-142">The command uses the **Credential** parameter to specify a user account that has permission to ping the remote computer and the **Impersonation** parameter to change the impersonation level to **Identify** .</span></span>

### <span data-ttu-id="9375d-143">例 7: 接続テストが成功した場合にのみセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="9375d-143">Example 7: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="9375d-144">この例では、コンピューターに送信された ping の少なくとも1つが成功した場合にのみ、Server01 コンピューターでセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9375d-144">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="9375d-145">このコマンドは、コマンド `if` レットを使用して `Test-Connection` 、Server01 コンピューターに ping を実行します。</span><span class="sxs-lookup"><span data-stu-id="9375d-145">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="9375d-146">このコマンドは、 **Win32_PingStatus** オブジェクトではなく **ブール** 値を返す **Quiet** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9375d-146">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **Win32_PingStatus** object.</span></span> <span data-ttu-id="9375d-147">`$True`4 つの ping のいずれかが成功した場合、値はになります。それ以外の場合はです `$False` 。</span><span class="sxs-lookup"><span data-stu-id="9375d-147">The value is `$True` if any of the four pings succeed and is, otherwise, `$False`.</span></span>

<span data-ttu-id="9375d-148">コマンドが `Test-Connection` 値を返す場合 `$True` 、コマンドはコマンドレットを使用して `New-PSSession` **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="9375d-148">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

## <span data-ttu-id="9375d-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9375d-149">PARAMETERS</span></span>

### <span data-ttu-id="9375d-150">-AsJob</span><span class="sxs-lookup"><span data-stu-id="9375d-150">-AsJob</span></span>

<span data-ttu-id="9375d-151">このコマンドレットがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="9375d-151">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="9375d-152">このパラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。 windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[ **管理者として実行** ] オプションを使用して PowerShell を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="9375d-152">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="9375d-153">詳細については、「[about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9375d-153">For more information, see [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="9375d-154">**AsJob** パラメーターを指定すると、コマンドは、バックグラウンドジョブを表すオブジェクトを直ちに返します。</span><span class="sxs-lookup"><span data-stu-id="9375d-154">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="9375d-155">ジョブが完了しても、引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="9375d-155">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="9375d-156">ジョブは、ローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-156">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="9375d-157">ジョブの結果を取得するには、`Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9375d-157">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="9375d-158">PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9375d-158">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-159">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="9375d-159">-BufferSize</span></span>

<span data-ttu-id="9375d-160">このコマンドで送信されるバッファーのサイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-160">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="9375d-161">既定値は 32 です。</span><span class="sxs-lookup"><span data-stu-id="9375d-161">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9375d-162">-ComputerName</span></span>

<span data-ttu-id="9375d-163">ping するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-163">Specifies the computers to ping.</span></span> <span data-ttu-id="9375d-164">コンピューター名を入力するか、IP アドレスを IPv4 または IPv6 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="9375d-164">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="9375d-165">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="9375d-165">Wildcard characters are not permitted.</span></span> <span data-ttu-id="9375d-166">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="9375d-166">This parameter is required.</span></span>

<span data-ttu-id="9375d-167">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="9375d-167">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="9375d-168">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9375d-168">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

> [!NOTE]
> <span data-ttu-id="9375d-169">**ComputerName** パラメーターは、PowerShell 6.0 以降では **TargetName** に名前が変更されました。</span><span class="sxs-lookup"><span data-stu-id="9375d-169">The **ComputerName** parameter is renamed to **TargetName** in PowerShell 6.0 and above.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, IPAddress, __SERVER, Server, Destination

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-170">-カウント</span><span class="sxs-lookup"><span data-stu-id="9375d-170">-Count</span></span>

<span data-ttu-id="9375d-171">送信するエコー要求の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-171">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="9375d-172">既定値は 4 ですが、</span><span class="sxs-lookup"><span data-stu-id="9375d-172">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="9375d-173">-Credential</span></span>

<span data-ttu-id="9375d-174">送信元コンピューターから ping 要求を送信するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-174">Specifies a user account that has permission to send a ping request from the source computer.</span></span> <span data-ttu-id="9375d-175">User01 や Domain01\user01」などのユーザー名を入力するか、コマンドレットのような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="9375d-175">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="9375d-176">**Credential** パラメーターは、 **Source** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9375d-176">The **Credential** parameter is valid only when the **Source** parameter is used in the command.</span></span> <span data-ttu-id="9375d-177">資格情報は、対象のコンピューターには影響しません。</span><span class="sxs-lookup"><span data-stu-id="9375d-177">The credentials don't affect the destination computer.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Source
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-178">-DcomAuthentication</span><span class="sxs-lookup"><span data-stu-id="9375d-178">-DcomAuthentication</span></span>

<span data-ttu-id="9375d-179">このコマンドレットが WMI で使用する認証レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-179">Specifies the authentication level that this cmdlet uses with WMI.</span></span>
<span data-ttu-id="9375d-180">`Test-Connection` WMI を使用します。</span><span class="sxs-lookup"><span data-stu-id="9375d-180">`Test-Connection` uses WMI.</span></span>
<span data-ttu-id="9375d-181">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9375d-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9375d-182">**Default** 。</span><span class="sxs-lookup"><span data-stu-id="9375d-182">**Default** .</span></span> <span data-ttu-id="9375d-183">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="9375d-183">Windows Authentication</span></span>
- <span data-ttu-id="9375d-184">**なし** 。</span><span class="sxs-lookup"><span data-stu-id="9375d-184">**None** .</span></span> <span data-ttu-id="9375d-185">COM 認証なし</span><span class="sxs-lookup"><span data-stu-id="9375d-185">No COM authentication</span></span>
- <span data-ttu-id="9375d-186">**接続** します。</span><span class="sxs-lookup"><span data-stu-id="9375d-186">**Connect** .</span></span> <span data-ttu-id="9375d-187">接続レベルの COM 認証</span><span class="sxs-lookup"><span data-stu-id="9375d-187">Connect-level COM authentication</span></span>
- <span data-ttu-id="9375d-188">を **呼び出し** ます。</span><span class="sxs-lookup"><span data-stu-id="9375d-188">**Call** .</span></span> <span data-ttu-id="9375d-189">呼び出しレベルの COM 認証</span><span class="sxs-lookup"><span data-stu-id="9375d-189">Call-level COM authentication</span></span>
- <span data-ttu-id="9375d-190">**パケット** 。</span><span class="sxs-lookup"><span data-stu-id="9375d-190">**Packet** .</span></span> <span data-ttu-id="9375d-191">パケットレベルの COM 認証</span><span class="sxs-lookup"><span data-stu-id="9375d-191">Packet-level COM authentication</span></span>
- <span data-ttu-id="9375d-192">**Packetintegrity** 。</span><span class="sxs-lookup"><span data-stu-id="9375d-192">**PacketIntegrity** .</span></span> <span data-ttu-id="9375d-193">パケット整合性レベルの COM 認証</span><span class="sxs-lookup"><span data-stu-id="9375d-193">Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="9375d-194">**Packetprivacy** 。</span><span class="sxs-lookup"><span data-stu-id="9375d-194">**PacketPrivacy** .</span></span> <span data-ttu-id="9375d-195">パケットのプライバシーレベルの COM 認証</span><span class="sxs-lookup"><span data-stu-id="9375d-195">Packet Privacy-level COM authentication</span></span>
- <span data-ttu-id="9375d-196">**変更なし** 。</span><span class="sxs-lookup"><span data-stu-id="9375d-196">**Unchanged** .</span></span> <span data-ttu-id="9375d-197">前のコマンドと同じ</span><span class="sxs-lookup"><span data-stu-id="9375d-197">Same as the previous command</span></span>

<span data-ttu-id="9375d-198">既定値は、列挙値が **4** の **パケット** です。</span><span class="sxs-lookup"><span data-stu-id="9375d-198">The default value is **Packet** that has an enumerated value of **4** .</span></span> <span data-ttu-id="9375d-199">このパラメーターの値の詳細については、「 [Authenticationlevel](/dotnet/api/system.management.authenticationlevel) 列挙型」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9375d-199">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) enumeration.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet (enumerated value of 4)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-200">-Delay</span><span class="sxs-lookup"><span data-stu-id="9375d-200">-Delay</span></span>

<span data-ttu-id="9375d-201">ping 間の間隔を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-201">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1 (second)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-202">-偽装</span><span class="sxs-lookup"><span data-stu-id="9375d-202">-Impersonation</span></span>

<span data-ttu-id="9375d-203">このコマンドレットが WMI を呼び出すときに使用する偽装レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-203">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="9375d-204">`Test-Connection` WMI を使用します。</span><span class="sxs-lookup"><span data-stu-id="9375d-204">`Test-Connection` uses WMI.</span></span>

<span data-ttu-id="9375d-205">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9375d-205">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="9375d-206">**Default** 。</span><span class="sxs-lookup"><span data-stu-id="9375d-206">**Default** .</span></span> <span data-ttu-id="9375d-207">既定の偽装。</span><span class="sxs-lookup"><span data-stu-id="9375d-207">Default impersonation.</span></span>
- <span data-ttu-id="9375d-208">**匿名** 。</span><span class="sxs-lookup"><span data-stu-id="9375d-208">**Anonymous** .</span></span> <span data-ttu-id="9375d-209">呼び出し元の ID は非表示になります。</span><span class="sxs-lookup"><span data-stu-id="9375d-209">Hides the identity of the caller.</span></span>
- <span data-ttu-id="9375d-210">を **識別** します。</span><span class="sxs-lookup"><span data-stu-id="9375d-210">**Identify** .</span></span> <span data-ttu-id="9375d-211">オブジェクトによる呼び出し元の資格情報のクエリが許可されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-211">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="9375d-212">**Impersonate** 。</span><span class="sxs-lookup"><span data-stu-id="9375d-212">**Impersonate** .</span></span> <span data-ttu-id="9375d-213">オブジェクトによる呼び出し元の資格情報の使用が許可されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-213">Allows objects to use the credentials of the caller.</span></span>

<span data-ttu-id="9375d-214">既定値は **Impersonate** です。</span><span class="sxs-lookup"><span data-stu-id="9375d-214">The default value is **Impersonate** .</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-215">-Protocol</span><span class="sxs-lookup"><span data-stu-id="9375d-215">-Protocol</span></span>

<span data-ttu-id="9375d-216">プロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-216">Specifies a protocol.</span></span> <span data-ttu-id="9375d-217">このパラメーターに指定できる値は、DCOM および WSMan です。</span><span class="sxs-lookup"><span data-stu-id="9375d-217">The acceptable values for this parameter are DCOM and WSMan.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-218">-非表示</span><span class="sxs-lookup"><span data-stu-id="9375d-218">-Quiet</span></span>

<span data-ttu-id="9375d-219">**Quiet** パラメーター **は、boolean 値を** **system.string オブジェクトで返します。**</span><span class="sxs-lookup"><span data-stu-id="9375d-219">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="9375d-220">このパラメーターを使用すると、すべてのエラーが抑制します。</span><span class="sxs-lookup"><span data-stu-id="9375d-220">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="9375d-221">テストされた各接続は、 **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="9375d-221">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="9375d-222">**ComputerName** パラメーターに複数のコンピューターが指定されている場合は、 **ブール** 値の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-222">If the **ComputerName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="9375d-223">Ping **any** が成功した場合 `$True` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-223">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="9375d-224">**すべて** の ping が失敗 `$False` した場合は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-224">If **all** pings fail, `$False` is returned.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Quiet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-225">-Source</span><span class="sxs-lookup"><span data-stu-id="9375d-225">-Source</span></span>

<span data-ttu-id="9375d-226">ping の送信元コンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-226">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="9375d-227">コンピューター名のコンマ区切りのリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="9375d-227">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="9375d-228">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="9375d-228">The default is the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: FCN, SRC

Required: True
Position: 1
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-229">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="9375d-229">-ThrottleLimit</span></span>

<span data-ttu-id="9375d-230">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-230">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="9375d-231">このパラメーターを省略した場合、または値 0 を入力した場合は、既定値の 32 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-231">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="9375d-232">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="9375d-232">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-233">-TimeToLive</span><span class="sxs-lookup"><span data-stu-id="9375d-233">-TimeToLive</span></span>

<span data-ttu-id="9375d-234">パケットを転送できる最大回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-234">Specifies the maximum times a packet can be forwarded.</span></span> <span data-ttu-id="9375d-235">ゲートウェイやルーターなどのホップごとに、 **TimeToLive** 値が1つ減少します。</span><span class="sxs-lookup"><span data-stu-id="9375d-235">For every hop in gateways, routers etc. the **TimeToLive** value is decreased by one.</span></span> <span data-ttu-id="9375d-236">0の場合、パケットは破棄され、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-236">At zero the packet is discarded and an error is returned.</span></span>
<span data-ttu-id="9375d-237">**Windows** では、既定値は **128** です。</span><span class="sxs-lookup"><span data-stu-id="9375d-237">In **Windows** , The default value is **128** .</span></span> <span data-ttu-id="9375d-238">**TimeToLive** パラメーターのエイリアスは **TTL** です。</span><span class="sxs-lookup"><span data-stu-id="9375d-238">The alias of the **TimeToLive** parameter is **TTL** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: 128 in Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-239">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="9375d-239">-WsmanAuthentication</span></span>

<span data-ttu-id="9375d-240">このコマンドレットで WSMan プロトコルを使用するときに、ユーザー資格情報の認証に使用されるメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="9375d-240">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span>
<span data-ttu-id="9375d-241">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9375d-241">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9375d-242">Basic</span><span class="sxs-lookup"><span data-stu-id="9375d-242">Basic</span></span>
- <span data-ttu-id="9375d-243">CredSSP</span><span class="sxs-lookup"><span data-stu-id="9375d-243">CredSSP</span></span>
- <span data-ttu-id="9375d-244">Default</span><span class="sxs-lookup"><span data-stu-id="9375d-244">Default</span></span>
- <span data-ttu-id="9375d-245">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="9375d-245">Digest</span></span>
- <span data-ttu-id="9375d-246">Kerberos</span><span class="sxs-lookup"><span data-stu-id="9375d-246">Kerberos</span></span>
- <span data-ttu-id="9375d-247">Negotiate</span><span class="sxs-lookup"><span data-stu-id="9375d-247">Negotiate.</span></span>

<span data-ttu-id="9375d-248">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="9375d-248">The default value is Default.</span></span>

<span data-ttu-id="9375d-249">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9375d-249">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).</span></span>

<span data-ttu-id="9375d-250">注意: ユーザーの資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="9375d-250">Caution: Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="9375d-251">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="9375d-251">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="9375d-252">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9375d-252">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="9375d-253">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9375d-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9375d-254">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9375d-254">CommonParameters</span></span>

<span data-ttu-id="9375d-255">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9375d-255">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9375d-256">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9375d-256">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9375d-257">入力</span><span class="sxs-lookup"><span data-stu-id="9375d-257">INPUTS</span></span>

### <span data-ttu-id="9375d-258">なし</span><span class="sxs-lookup"><span data-stu-id="9375d-258">None</span></span>

<span data-ttu-id="9375d-259">このコマンドレットに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9375d-259">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9375d-260">出力</span><span class="sxs-lookup"><span data-stu-id="9375d-260">OUTPUTS</span></span>

### <span data-ttu-id="9375d-261">System.management.managementobject # Win32_PingStatus root\cimv2\、、system.--... RemotingJob、system.string</span><span class="sxs-lookup"><span data-stu-id="9375d-261">System.Management.ManagementObject#root\cimv2\Win32_PingStatus, System.Management.Automation.RemotingJob, System.Boolean</span></span>

<span data-ttu-id="9375d-262">**AsJob** パラメーターを指定した場合、このコマンドレットはジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9375d-262">This cmdlet returns a job object, if you specify the **AsJob** parameter.</span></span>

<span data-ttu-id="9375d-263">**Quiet** パラメーターを指定すると、 **ブール** 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-263">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="9375d-264">複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="9375d-264">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="9375d-265">それ以外の場合は、 `Test-Connection` 各 ping の **Win32_PingStatus** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9375d-265">Otherwise, `Test-Connection` returns a **Win32_PingStatus** object for each ping.</span></span>

## <span data-ttu-id="9375d-266">注</span><span class="sxs-lookup"><span data-stu-id="9375d-266">NOTES</span></span>

<span data-ttu-id="9375d-267">このコマンドレットは、 **Win32_PingStatus** クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9375d-267">This cmdlet uses the **Win32_PingStatus** class.</span></span> <span data-ttu-id="9375d-268">コマンドは `Get-WMIObject Win32_PingStatus` 、コマンドに相当 `Test-Connection` します。</span><span class="sxs-lookup"><span data-stu-id="9375d-268">A `Get-WMIObject Win32_PingStatus` command is equivalent to a `Test-Connection` command.</span></span>

<span data-ttu-id="9375d-269">**ソース** パラメーターセットは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9375d-269">The **Source** parameter set was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="9375d-270">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9375d-270">RELATED LINKS</span></span>

[<span data-ttu-id="9375d-271">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="9375d-271">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="9375d-272">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="9375d-272">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="9375d-273">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="9375d-273">Stop-Computer</span></span>](Stop-Computer.md)

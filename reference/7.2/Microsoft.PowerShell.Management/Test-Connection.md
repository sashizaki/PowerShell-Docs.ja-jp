---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: af8a953536bb9683ba737522ad738348c5c695e2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599537"
---
# <span data-ttu-id="3dbe2-102">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="3dbe2-102">Test-Connection</span></span>

## <span data-ttu-id="3dbe2-103">概要</span><span class="sxs-lookup"><span data-stu-id="3dbe2-103">SYNOPSIS</span></span>
<span data-ttu-id="3dbe2-104">ICMP エコー要求パケット (ping) を1台以上のコンピューターに送信します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-104">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="3dbe2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3dbe2-105">SYNTAX</span></span>

### <span data-ttu-id="3dbe2-106">DefaultPing (既定)</span><span class="sxs-lookup"><span data-stu-id="3dbe2-106">DefaultPing (Default)</span></span>

```
Test-Connection [-TargetName] <string[]> [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Count <int>] [-Delay <int>] [-BufferSize <int>]
 [-DontFragment] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="3dbe2-107">RepeatPing</span><span class="sxs-lookup"><span data-stu-id="3dbe2-107">RepeatPing</span></span>

```
Test-Connection [-TargetName] <string[]> -Repeat [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Delay <int>] [-BufferSize <int>] [-DontFragment]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="3dbe2-108">MtuSizeDetect</span><span class="sxs-lookup"><span data-stu-id="3dbe2-108">MtuSizeDetect</span></span>

```
Test-Connection [-TargetName] <string[]> -MtuSize [-IPv4] [-IPv6] [-ResolveDestination]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="3dbe2-109">TraceRoute</span><span class="sxs-lookup"><span data-stu-id="3dbe2-109">TraceRoute</span></span>

```
Test-Connection [-TargetName] <string[]> -Traceroute [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="3dbe2-110">TcpPort</span><span class="sxs-lookup"><span data-stu-id="3dbe2-110">TcpPort</span></span>

```
Test-Connection [-TargetName] <string[]> -TcpPort <int> [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

## <span data-ttu-id="3dbe2-111">Description</span><span class="sxs-lookup"><span data-stu-id="3dbe2-111">DESCRIPTION</span></span>

<span data-ttu-id="3dbe2-112">`Test-Connection`コマンドレットは、インターネット制御メッセージプロトコル (ICMP) エコー要求パケット (ping) を1つ以上のリモートコンピューターに送信し、エコー応答応答を返します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-112">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="3dbe2-113">このコマンドレットを使用すると、特定のコンピューターに IP ネットワーク経由で接続できるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-113">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="3dbe2-114">のパラメーターを使用し `Test-Connection` て、送信側と受信側の両方のコンピューターの指定、バックグラウンドジョブとしてのコマンドの実行、タイムアウトと ping の回数の設定、および接続と認証の構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-114">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="3dbe2-115">使い慣れた **ping** コマンドとは異なり、は、 `Test-Connection` PowerShell で調査できる **Testconnectioncommand + ping status** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-115">Unlike the familiar **ping** command, `Test-Connection` returns a **TestConnectionCommand+PingStatus** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="3dbe2-116">**Quiet** パラメーターは、テストされた各接続の **ブール値を** **system.string オブジェクトで返します。**</span><span class="sxs-lookup"><span data-stu-id="3dbe2-116">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="3dbe2-117">複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-117">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="3dbe2-118">例</span><span class="sxs-lookup"><span data-stu-id="3dbe2-118">EXAMPLES</span></span>

### <span data-ttu-id="3dbe2-119">例 1: リモートコンピューターにエコー要求を送信する</span><span class="sxs-lookup"><span data-stu-id="3dbe2-119">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="3dbe2-120">この例では、エコー要求パケットをローカルコンピューターから Server01 コンピューターに送信します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-120">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
   Destination: Server01

Ping Source           Address                   Latency BufferSize Status
                                                   (ms)        (B)
---- ------           -------                   ------- ---------- ------
   1 ADMIN1           10.59.137.44                   24         32 Success
   2 ADMIN1           10.59.137.44                   39         32 Success
   3 ADMIN1           *                               *          * TimedOut
   4 ADMIN1           10.59.137.44                   28         32 Success
```

<span data-ttu-id="3dbe2-121">`Test-Connection`**TargetName** パラメーターを使用して、Server01 コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-121">`Test-Connection` uses the **TargetName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="3dbe2-122">**IPv4** パラメーターでは、テスト用のプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-122">The **IPv4** parameter specifies the protocol for the test.</span></span>

<span data-ttu-id="3dbe2-123">一連の **Testconnectioncommand + Ping status** オブジェクトが出力ストリームに送信されます。これは、ターゲットコンピューターからの ping 応答ごとに1つのオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-123">A series of **TestConnectionCommand+PingStatus** objects are sent to the output stream, one object per ping reply from the target machine.</span></span>

### <span data-ttu-id="3dbe2-124">例 2: 複数のコンピューターにエコー要求を送信する</span><span class="sxs-lookup"><span data-stu-id="3dbe2-124">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="3dbe2-125">この例では、ローカルコンピューターから複数のリモートコンピューターに ping を送信します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-125">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### <span data-ttu-id="3dbe2-126">例 3: パラメーターを使用してテストコマンドをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="3dbe2-126">Example 3: Use parameters to customize the test command</span></span>

<span data-ttu-id="3dbe2-127">この例では、のパラメーターを使用し `Test-Connection` て、コマンドをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-127">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="3dbe2-128">ローカルコンピューターからリモートコンピューターに ping テストが送信されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-128">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

<span data-ttu-id="3dbe2-129">`Test-Connection`**TargetName** パラメーターを使用して Server01 を指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-129">`Test-Connection` uses the **TargetName** parameter to specify Server01.</span></span> <span data-ttu-id="3dbe2-130">**Count** パラメーターは、3秒間隔の **遅延** で Server01 コンピューターに送信される3つの ping を指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-130">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="3dbe2-131">これらのオプションは、ホップ数の増加またはトラフィックの多いネットワーク状態が原因で ping 応答が通常よりも長くかかることが予想される場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-131">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="3dbe2-132">例 4: バックグラウンドジョブとしてテストを実行する</span><span class="sxs-lookup"><span data-stu-id="3dbe2-132">Example 4: Run a test as a background job</span></span>

<span data-ttu-id="3dbe2-133">この例では、 `Test-Connection` PowerShell バックグラウンドジョブとしてコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-133">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content -Path "Servers.txt") }
$Results = Receive-Job $job -Wait
```

<span data-ttu-id="3dbe2-134">このコマンドは、コマンド `Start-Job` レットを使用して、 `Test-Connection` 企業内の多くのコンピューターに ping を実行します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-134">The `Start-Job` command uses the `Test-Connection` cmdlet to ping many computers in an enterprise.</span></span>
<span data-ttu-id="3dbe2-135">**TargetName** パラメーターの値は、 `Get-Content` ファイルからコンピューター名の一覧を読み取るコマンドです `Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-135">The value of the **TargetName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="3dbe2-136">コマンドはコマンドレットを使用し `Start-Job` てバックグラウンドジョブとしてコマンドを実行し、変数にジョブを保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-136">The command uses the `Start-Job` cmdlet to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="3dbe2-137">この `Receive-Job` コマンドは、ジョブが完了するまでに指示され、 `-Wait` 結果を取得して変数に格納し `$Results` ます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-137">The `Receive-Job` command is instructed to `-Wait` until the job is completed, and then gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="3dbe2-138">例 5: 接続テストが成功した場合にのみセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="3dbe2-138">Example 5: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="3dbe2-139">この例では、コンピューターに送信された ping の少なくとも1つが成功した場合にのみ、Server01 コンピューターでセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-139">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -TargetName Server01 -Quiet) { New-PSSession -ComputerName Server01 }
```

<span data-ttu-id="3dbe2-140">`Test-Connection`コマンドレットは、 `Server01` **Quiet** パラメーターを指定してコンピューターに ping を行います。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-140">The `Test-Connection` cmdlet pings the `Server01` computer, with the **Quiet** parameter provided.</span></span>
<span data-ttu-id="3dbe2-141">`$True`4 つの ping のいずれかが成功した場合、結果の値はになります。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-141">The resulting value is `$True` if any of the four pings succeed.</span></span> <span data-ttu-id="3dbe2-142">Ping が成功しなかった場合、値はに `$False` なります。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-142">If none of the pings succeed, the value is `$False`.</span></span>

<span data-ttu-id="3dbe2-143">コマンドが `Test-Connection` 値を返す場合 `$True` 、コマンドはコマンドレットを使用して `New-PSSession` **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-143">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession**.</span></span>

### <span data-ttu-id="3dbe2-144">例 6: Traceroute パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="3dbe2-144">Example 6: Use the Traceroute parameter</span></span>

<span data-ttu-id="3dbe2-145">PowerShell 6.0 で導入された **Traceroute** パラメーターは、ローカルコンピューターと、 **TargetName** パラメーターを使用して指定したリモート接続先との間のルートをマップします。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-145">Introduced in PowerShell 6.0, the **Traceroute** parameter maps a route between the local computer and the remote destination you specify with the **TargetName** parameter.</span></span>

```powershell
Test-Connection -TargetName www.google.com -Traceroute
```

```Output
   Target: google.com

Hop Hostname                  Ping Latency Status           Source       TargetAddress
                                      (ms)
--- --------                  ---- ------- ------           ------       -------------
  1 172.20.0.1                   1       4 Success          Lira         172.217.9.174
  1 172.20.0.1                   2       3 Success          Lira         172.217.9.174
  1 172.20.0.1                   3       2 Success          Lira         172.217.9.174
  2 12.108.153.193               1       3 Success          Lira         172.217.9.174
  2 12.108.153.193               2       3 Success          Lira         172.217.9.174
  2 12.108.153.193               3       2 Success          Lira         172.217.9.174
  3 12.244.85.177                1      11 Success          Lira         172.217.9.174
  3 12.244.85.177                2      12 Success          Lira         172.217.9.174
  3 12.244.85.177                3      12 Success          Lira         172.217.9.174
  4 *                            1      14 DestinationNetw… Lira         172.217.9.174
  4 *                            2       * TimedOut         Lira         172.217.9.174
  4 *                            3      20 DestinationNetw… Lira         172.217.9.174
  5 *                            1       * TimedOut         Lira         172.217.9.174
  5 *                            2      15 DestinationNetw… Lira         172.217.9.174
  5 *                            3       * TimedOut         Lira         172.217.9.174
  6 *                            1      18 DestinationNetw… Lira         172.217.9.174
  6 *                            2       * TimedOut         Lira         172.217.9.174
  6 *                            3      16 DestinationNetw… Lira         172.217.9.174
  7 *                            1       * TimedOut         Lira         172.217.9.174
  7 *                            2       * TimedOut         Lira         172.217.9.174
  7 *                            3       * TimedOut         Lira         172.217.9.174
  8 *                            1       * TimedOut         Lira         172.217.9.174
  8 *                            2       * TimedOut         Lira         172.217.9.174
  8 *                            3       * TimedOut         Lira         172.217.9.174
  9 *                            1       * TimedOut         Lira         172.217.9.174
  9 *                            2       * TimedOut         Lira         172.217.9.174
  9 *                            3       * TimedOut         Lira         172.217.9.174
 10 *                            1       * TimedOut         Lira         172.217.9.174
 10 *                            2       * TimedOut         Lira         172.217.9.174
 10 *                            3       * TimedOut         Lira         172.217.9.174
 11 172.217.9.174                1      23 Success          Lira         172.217.9.174
 11 172.217.9.174                2      21 Success          Lira         172.217.9.174
 11 172.217.9.174                3      22 Success          Lira         172.217.9.174
```

<span data-ttu-id="3dbe2-146">`Test-Connection`コマンドは、 **Traceroute** パラメーターを使用して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-146">The `Test-Connection` command is called with the **Traceroute** parameter.</span></span> <span data-ttu-id="3dbe2-147">結果 ( `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` オブジェクト) は、 **成功** 出力ストリームに出力されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-147">The results, which are `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` objects, are output to the **Success** output stream.</span></span>

## <span data-ttu-id="3dbe2-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3dbe2-148">PARAMETERS</span></span>

### <span data-ttu-id="3dbe2-149">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="3dbe2-149">-BufferSize</span></span>

<span data-ttu-id="3dbe2-150">このコマンドで送信されるバッファーのサイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-150">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="3dbe2-151">既定値は 32 です。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-151">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-152">-Repeat</span><span class="sxs-lookup"><span data-stu-id="3dbe2-152">-Repeat</span></span>

<span data-ttu-id="3dbe2-153">コマンドレットによって ping 要求が連続して送信されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-153">Causes the cmdlet to send ping requests continuously.</span></span> <span data-ttu-id="3dbe2-154">このパラメーターは、 **Count** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-154">This parameter can't be used with the **Count** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RepeatPing
Aliases: Continuous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-155">-カウント</span><span class="sxs-lookup"><span data-stu-id="3dbe2-155">-Count</span></span>

<span data-ttu-id="3dbe2-156">送信するエコー要求の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-156">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="3dbe2-157">既定値は 4 ですが、</span><span class="sxs-lookup"><span data-stu-id="3dbe2-157">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-158">-Delay</span><span class="sxs-lookup"><span data-stu-id="3dbe2-158">-Delay</span></span>

<span data-ttu-id="3dbe2-159">ping 間の間隔を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-159">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-160">-DontFragment</span><span class="sxs-lookup"><span data-stu-id="3dbe2-160">-DontFragment</span></span>

<span data-ttu-id="3dbe2-161">このパラメーターは、IP ヘッダーに don't **Fragment** フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-161">This parameter sets the **Don't Fragment** flag in the IP header.</span></span> <span data-ttu-id="3dbe2-162">このパラメーターを **BufferSize** パラメーターと共に使用して、パスの MTU サイズをテストできます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-162">You can use this parameter with the **BufferSize** parameter to test the Path MTU size.</span></span> <span data-ttu-id="3dbe2-163">パス MTU の詳細については、wikipedia の [パス Mtu 検出](https://wikipedia.org/wiki/Path_MTU_Discovery) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-163">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-164">-IPv4</span><span class="sxs-lookup"><span data-stu-id="3dbe2-164">-IPv4</span></span>

<span data-ttu-id="3dbe2-165">テストに IPv4 プロトコルを使用するようにコマンドレットを強制します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-165">Forces the cmdlet to use the IPv4 protocol for the test.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-166">-IPv6</span><span class="sxs-lookup"><span data-stu-id="3dbe2-166">-IPv6</span></span>

<span data-ttu-id="3dbe2-167">テストに IPv6 プロトコルを使用するようにコマンドレットを強制します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-167">Forces the cmdlet to use the IPv6 protocol for the test.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-168">-MaxHops</span><span class="sxs-lookup"><span data-stu-id="3dbe2-168">-MaxHops</span></span>

<span data-ttu-id="3dbe2-169">ICMP 要求メッセージを送信できる最大ホップ数を設定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-169">Sets the maximum number of hops that an ICMP request message can be sent.</span></span> <span data-ttu-id="3dbe2-170">既定値は、オペレーティングシステムによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-170">The default value is controlled by the operating system.</span></span> <span data-ttu-id="3dbe2-171">Windows 10 の既定値は128ホップです。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-171">The default value for Windows 10 is 128 hops.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-172">-Ping</span><span class="sxs-lookup"><span data-stu-id="3dbe2-172">-Ping</span></span>

<span data-ttu-id="3dbe2-173">コマンドレットによって ping テストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-173">Causes the cmdlet to do a ping test.</span></span> <span data-ttu-id="3dbe2-174">これは、コマンドレットの既定のモードです `Test-Connection` 。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-174">This is the default mode for the `Test-Connection` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-175">-非表示</span><span class="sxs-lookup"><span data-stu-id="3dbe2-175">-Quiet</span></span>

<span data-ttu-id="3dbe2-176">**Quiet** パラメーターは **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-176">The **Quiet** parameter returns a **Boolean** value.</span></span> <span data-ttu-id="3dbe2-177">このパラメーターを使用すると、すべてのエラーが抑制します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-177">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="3dbe2-178">テストされた各接続は、 **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-178">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="3dbe2-179">**TargetName** パラメーターに複数のコンピューターが指定されている場合は、**ブール** 値の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-179">If the **TargetName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="3dbe2-180">特定のターゲットへの ping が成功 **した場合** は、 `$True` が返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-180">If **any** ping to a given target succeeds, `$True` is returned.</span></span>

<span data-ttu-id="3dbe2-181">特定のターゲットへの ping が **すべて** 失敗した場合 `$False` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-181">If **all** pings to a given target fail, `$False` is returned.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-182">-ResolveDestination</span><span class="sxs-lookup"><span data-stu-id="3dbe2-182">-ResolveDestination</span></span>

<span data-ttu-id="3dbe2-183">コマンドレットがターゲットの DNS 名を解決しようとします。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-183">Causes the cmdlet to attempt to resolve the DNS name of the target.</span></span> <span data-ttu-id="3dbe2-184">**Traceroute** パラメーターと組み合わせて使用すると、可能であれば、すべての中間ホストの DNS 名も取得されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-184">When used in conjunction with the **Traceroute** parameter, the DNS names of all intermediate hosts will also be retrieved, if possible.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-185">-Source</span><span class="sxs-lookup"><span data-stu-id="3dbe2-185">-Source</span></span>

<span data-ttu-id="3dbe2-186">ping の送信元コンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-186">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="3dbe2-187">コンピューター名のコンマ区切りのリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-187">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="3dbe2-188">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-188">The default is the local computer.</span></span>

<span data-ttu-id="3dbe2-189">**注:** このパラメーターは、PowerShell バージョン6以降では機能しません。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-189">**NOTE:** This parameter is not functional in PowerShell versions 6 and up.</span></span>
<span data-ttu-id="3dbe2-190">このパラメーターを指定しても、コマンドには影響しません。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-190">Supplying this parameter will have no effect on the command.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultPing, RepeatPing, TraceRoute, TcpPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-191">-TargetName</span><span class="sxs-lookup"><span data-stu-id="3dbe2-191">-TargetName</span></span>

<span data-ttu-id="3dbe2-192">テストするコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-192">Specifies the computer(s) to test.</span></span> <span data-ttu-id="3dbe2-193">コンピューター名を入力するか、IP アドレスを IPv4 または IPv6 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-193">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ComputerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-194">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="3dbe2-194">-TimeoutSeconds</span></span>

<span data-ttu-id="3dbe2-195">テストのタイムアウト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-195">Sets the timeout value for the test.</span></span> <span data-ttu-id="3dbe2-196">タイムアウトの期限が切れる前に応答を受信しなかった場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-196">The test fails if a response isn't received before the timeout expires.</span></span> <span data-ttu-id="3dbe2-197">既定値は 5 秒です。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-197">The default is five seconds.</span></span>

<span data-ttu-id="3dbe2-198">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-198">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5 seconds
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-199">-Traceroute</span><span class="sxs-lookup"><span data-stu-id="3dbe2-199">-Traceroute</span></span>

<span data-ttu-id="3dbe2-200">コマンドレットが traceroute テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-200">Causes the cmdlet to do a traceroute test.</span></span> <span data-ttu-id="3dbe2-201">このパラメーターを使用すると、コマンドレットは `TestConnectionCommand+TraceStatus` オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-201">When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceStatus` object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TraceRoute
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-202">-MtuSize</span><span class="sxs-lookup"><span data-stu-id="3dbe2-202">-MtuSize</span></span>

<span data-ttu-id="3dbe2-203">このパラメーターは、パスの MTU サイズを検出するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-203">This parameter is used to discover the Path MTU size.</span></span> <span data-ttu-id="3dbe2-204">コマンドレットは、ターゲットにパスの MTU サイズを含む、 **ping # MTUSize** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-204">The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target.</span></span> <span data-ttu-id="3dbe2-205">パス MTU の詳細については、wikipedia の [パス Mtu 検出](https://wikipedia.org/wiki/Path_MTU_Discovery) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-205">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MtuSizeDetect
Aliases: MtuSizeDetect

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-206">-TcpPort</span><span class="sxs-lookup"><span data-stu-id="3dbe2-206">-TcpPort</span></span>

<span data-ttu-id="3dbe2-207">TCP 接続テストで使用するターゲットの TCP ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-207">Specifies the TCP port number on the target to be used in the TCP connection test.</span></span> <span data-ttu-id="3dbe2-208">コマンドレットは、ターゲットの指定されたポートへの TCP 接続を試行します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-208">The cmdlet will attempt to make a TCP connection to the specified port on the target.</span></span>

<span data-ttu-id="3dbe2-209">接続を確立できる場合は、 `$True` が返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-209">If a connection can be made, `$True` will be returned.</span></span>

<span data-ttu-id="3dbe2-210">接続を確立できない場合は、 `$False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-210">If a connection cannot be made, `$False` will be returned.</span></span>

```yaml
Type: System.Int32
Parameter Sets: TcpPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbe2-211">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3dbe2-211">CommonParameters</span></span>

<span data-ttu-id="3dbe2-212">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-212">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3dbe2-213">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-213">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3dbe2-214">入力</span><span class="sxs-lookup"><span data-stu-id="3dbe2-214">INPUTS</span></span>

### <span data-ttu-id="3dbe2-215">なし</span><span class="sxs-lookup"><span data-stu-id="3dbe2-215">None</span></span>

<span data-ttu-id="3dbe2-216">このコマンドレットに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-216">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3dbe2-217">出力</span><span class="sxs-lookup"><span data-stu-id="3dbe2-217">OUTPUTS</span></span>

### <span data-ttu-id="3dbe2-218">TestConnectionCommand + Ping Status、TestConnectionCommand + TraceStatus、Boolean、TestConnectionCommand + PingMtuStatus</span><span class="sxs-lookup"><span data-stu-id="3dbe2-218">TestConnectionCommand+PingStatus, TestConnectionCommand+TraceStatus, Boolean, TestConnectionCommand+PingMtuStatus</span></span>

<span data-ttu-id="3dbe2-219">既定では、は、 `Test-Connection` 各 ping 応答の **Testconnectioncommand + ping status** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-219">By default, `Test-Connection` returns a **TestConnectionCommand+PingStatus** object for each ping reply.</span></span>

<span data-ttu-id="3dbe2-220">**Traceroute** パラメーターを指定すると、コマンドレットは、ルートに沿って ping 応答ごとに **testconnectioncommand + tracestatus** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-220">If you specify the **Traceroute** parameter, the cmdlet will return a **TestConnectionCommand+TraceStatus** object for each ping reply along the route.</span></span>

<span data-ttu-id="3dbe2-221">**Quiet** パラメーターまたは **TcpPort** パラメーターを指定すると、**ブール** 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-221">If you specify the **Quiet** or **TcpPort** parameters, it returns a **Boolean** value.</span></span> <span data-ttu-id="3dbe2-222">複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbe2-222">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="3dbe2-223">注</span><span class="sxs-lookup"><span data-stu-id="3dbe2-223">NOTES</span></span>

## <span data-ttu-id="3dbe2-224">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3dbe2-224">RELATED LINKS</span></span>

[<span data-ttu-id="3dbe2-225">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="3dbe2-225">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="3dbe2-226">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="3dbe2-226">Stop-Computer</span></span>](Stop-Computer.md)


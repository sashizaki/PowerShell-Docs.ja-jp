---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 54ba1d7db60db7b4bb64f3161bba9c1fba124219
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212195"
---
# <span data-ttu-id="7019d-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="7019d-103">Test-Connection</span></span>

## <span data-ttu-id="7019d-104">概要</span><span class="sxs-lookup"><span data-stu-id="7019d-104">SYNOPSIS</span></span>
<span data-ttu-id="7019d-105">ICMP エコー要求パケット (ping) を1台以上のコンピューターに送信します。</span><span class="sxs-lookup"><span data-stu-id="7019d-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="7019d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7019d-106">SYNTAX</span></span>

### <span data-ttu-id="7019d-107">Ping の回数 (既定値)</span><span class="sxs-lookup"><span data-stu-id="7019d-107">PingCount (Default)</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="7019d-108">Ping の続行</span><span class="sxs-lookup"><span data-stu-id="7019d-108">PingContinues</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="7019d-109">DetectionOfMTUSize</span><span class="sxs-lookup"><span data-stu-id="7019d-109">DetectionOfMTUSize</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="7019d-110">TraceRoute</span><span class="sxs-lookup"><span data-stu-id="7019d-110">TraceRoute</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="7019d-111">ConnectionByTCPPort</span><span class="sxs-lookup"><span data-stu-id="7019d-111">ConnectionByTCPPort</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## <span data-ttu-id="7019d-112">Description</span><span class="sxs-lookup"><span data-stu-id="7019d-112">DESCRIPTION</span></span>

<span data-ttu-id="7019d-113">`Test-Connection`コマンドレットは、インターネット制御メッセージプロトコル (ICMP) エコー要求パケット (ping) を1つ以上のリモートコンピューターに送信し、エコー応答応答を返します。</span><span class="sxs-lookup"><span data-stu-id="7019d-113">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="7019d-114">このコマンドレットを使用すると、特定のコンピューターに IP ネットワーク経由で接続できるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="7019d-114">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="7019d-115">のパラメーターを使用し `Test-Connection` て、送信側と受信側の両方のコンピューターの指定、バックグラウンドジョブとしてのコマンドの実行、タイムアウトと ping の回数の設定、および接続と認証の構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7019d-115">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="7019d-116">使い慣れた **ping** コマンドとは異なり、は、 `Test-Connection` PowerShell で調査できる **Testconnectioncommand + ping レポート** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7019d-116">Unlike the familiar **ping** command, `Test-Connection` returns a **TestConnectionCommand+PingReport** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="7019d-117">**Quiet** パラメーターは、テストされた各接続の **ブール値を** **system.string オブジェクトで返します。**</span><span class="sxs-lookup"><span data-stu-id="7019d-117">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="7019d-118">複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-118">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="7019d-119">例</span><span class="sxs-lookup"><span data-stu-id="7019d-119">EXAMPLES</span></span>

### <span data-ttu-id="7019d-120">例 1: リモートコンピューターにエコー要求を送信する</span><span class="sxs-lookup"><span data-stu-id="7019d-120">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="7019d-121">この例では、エコー要求パケットをローカルコンピューターから Server01 コンピューターに送信します。</span><span class="sxs-lookup"><span data-stu-id="7019d-121">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
Pinging Server01 [10.59.137.44] with 32 bytes of data:
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Ping complete.

Source     Destination Replies
------     ----------- -------
Server01   Server01    {System.Net.NetworkInformation.PingReply, System.Net.NetworkInformation ...
```

<span data-ttu-id="7019d-122">`Test-Connection`**TargetName** パラメーターを使用して、Server01 コンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-122">`Test-Connection` uses the **TargetName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="7019d-123">**IPv4** パラメーターでは、テスト用のプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-123">The **IPv4** parameter specifies the protocol for the test.</span></span>

<span data-ttu-id="7019d-124">**Testconnectioncommand + Ping report** オブジェクトが **成功** ストリームに送信されるときに、Ping の出力が **情報** ストリームに送信されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-124">The ping output is sent to the **Information** stream while the **TestConnectionCommand+PingReport** object sent to the **Success** stream.</span></span> <span data-ttu-id="7019d-125">出力ストリームの詳細については、「 [about_Redirection](../microsoft.powershell.core/about/about_redirection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7019d-125">For more information about the output streams, see [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).</span></span>

### <span data-ttu-id="7019d-126">例 2: 複数のコンピューターにエコー要求を送信する</span><span class="sxs-lookup"><span data-stu-id="7019d-126">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="7019d-127">この例では、ローカルコンピューターから複数のリモートコンピューターに ping を送信します。</span><span class="sxs-lookup"><span data-stu-id="7019d-127">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### <span data-ttu-id="7019d-128">例 3: 複数のコンピューターからコンピューターにエコー要求を送信する</span><span class="sxs-lookup"><span data-stu-id="7019d-128">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="7019d-129">この例では、別のソースコンピューターから1台のリモートコンピューター Server01 に ping を送信します。</span><span class="sxs-lookup"><span data-stu-id="7019d-129">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

<span data-ttu-id="7019d-130">複数のポイントからの接続の待機時間をテストするには、このコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7019d-130">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="7019d-131">例 4: パラメーターを使用してテストコマンドをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="7019d-131">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="7019d-132">この例では、のパラメーターを使用し `Test-Connection` て、コマンドをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="7019d-132">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="7019d-133">ローカルコンピューターからリモートコンピューターに ping テストが送信されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-133">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

<span data-ttu-id="7019d-134">`Test-Connection`**TargetName** パラメーターを使用して Server01 を指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-134">`Test-Connection` uses the **TargetName** parameter to specify Server01.</span></span> <span data-ttu-id="7019d-135">**Count** パラメーターは、3秒間隔の **遅延** で Server01 コンピューターに送信される3つの ping を指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-135">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="7019d-136">これらのオプションは、ホップ数の増加またはトラフィックの多いネットワーク状態が原因で ping 応答が通常よりも長くかかることが予想される場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7019d-136">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="7019d-137">例 5: バックグラウンドジョブとしてテストを実行する</span><span class="sxs-lookup"><span data-stu-id="7019d-137">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="7019d-138">この例では、 `Test-Connection` PowerShell バックグラウンドジョブとしてコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7019d-138">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

<span data-ttu-id="7019d-139">このコマンドは、コマンド `Start-Job` レットを使用して、 `Test-Connection` 企業内の多くのコンピューターに ping を実行します。</span><span class="sxs-lookup"><span data-stu-id="7019d-139">The `Start-Job` command uses the `Test-Connection` cmdlet to ping many computers in an enterprise.</span></span>
<span data-ttu-id="7019d-140">**TargetName** パラメーターの値は、 `Get-Content` ファイルからコンピューター名の一覧を読み取るコマンドです `Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="7019d-140">The value of the **TargetName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="7019d-141">コマンドはコマンドレットを使用し `Start-Job` てバックグラウンドジョブとしてコマンドを実行し、変数にジョブを保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="7019d-141">The command uses the `Start-Job` cmdlet to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="7019d-142">コマンドは、 `if` ジョブがまだ実行されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7019d-142">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="7019d-143">ジョブが実行されていない場合は、 `Receive-Job` 結果を取得して変数に格納し `$Results` ます。</span><span class="sxs-lookup"><span data-stu-id="7019d-143">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="7019d-144">例 6: 接続テストが成功した場合にのみセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="7019d-144">Example 6: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="7019d-145">この例では、コンピューターに送信された ping の少なくとも1つが成功した場合にのみ、Server01 コンピューターでセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7019d-145">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="7019d-146">このコマンドは、コマンド `if` レットを使用して `Test-Connection` 、Server01 コンピューターに ping を実行します。</span><span class="sxs-lookup"><span data-stu-id="7019d-146">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="7019d-147">このコマンドは、 **Testconnectioncommand + Ping report** オブジェクトではなく、 **ブール** 値を返す **Quiet** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7019d-147">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **TestConnectionCommand+PingReport** object.</span></span>

<span data-ttu-id="7019d-148">`$True`4 つの ping のいずれかが成功した場合、値はになります。</span><span class="sxs-lookup"><span data-stu-id="7019d-148">The value is `$True` if any of the four pings succeed.</span></span> <span data-ttu-id="7019d-149">Ping が成功しなかった場合、値はに `$False` なります。</span><span class="sxs-lookup"><span data-stu-id="7019d-149">If none of the pings succeed, the value is `$False`.</span></span>

<span data-ttu-id="7019d-150">コマンドが `Test-Connection` 値を返す場合 `$True` 、コマンドはコマンドレットを使用して `New-PSSession` **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="7019d-150">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

### <span data-ttu-id="7019d-151">例 7: Traceroute パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="7019d-151">Example 7: Use the Traceroute parameter</span></span>

<span data-ttu-id="7019d-152">PowerShell 6.0 以降では、 **Traceroute** パラメーターを使用して、ローカルコンピューターと指定したリモートターゲットの間のルートを **TargetName** パラメーターでマップします。</span><span class="sxs-lookup"><span data-stu-id="7019d-152">Beginning in PowerShell 6.0, the **Traceroute** parameter maps a route between the local computer and the remote destination you specify with the **TargetName** parameter.</span></span>

```powershell
Test-Connection -TargetName www.microsoft.com -Traceroute | ForEach-Object {
  $_ | Format-Table Source, DestinationAddress, DestinationHost
  $_.Replies | ForEach-Object {
      $_ | Format-Table Hop, ReplyRouterAddress
      $_.PingReplies | Format-Table
  }
}
```

```Output
Tracing route to www.microsoft.com [96.6.27.90] over a maximum of 128 hops:
  1   0 ms   0 ms   0 ms   192.168.0.3 [192.168.0.3]
  2   0 ms   0 ms   0 ms   192.168.1.1 [192.168.1.1]
  3   3 ms   29 ms   4 ms   96.6.27.90 [96.6.27.90]
Trace complete.

Source      DestinationAddress DestinationHost   Replies
------      ------------------ ---------------   -------
SERVER01    96.6.27.90         www.microsoft.com {, , }

Hop ReplyRouterAddress
--- ------------------
  1 192.168.0.3

    Status Address      RoundtripTime Options Buffer
    ------ -------      ------------- ------- ------
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  2 192.168.1.1

    Status Address     RoundtripTime Options Buffer
    ------ -------     ------------- ------- ------
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  3 96.6.27.90

 Status Address    RoundtripTime Options                                   Buffer
 ------ -------    ------------- -------                                   ------
Success 96.6.27.90             3 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             2 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             4 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
```

<span data-ttu-id="7019d-153">この `Test-Connection` コマンドでは、 **Traceroute** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7019d-153">The `Test-Connection` command uses the **Traceroute** parameter.</span></span> <span data-ttu-id="7019d-154">結果 (オブジェクト) は、パイプを使用して `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` コマンドレットに渡され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="7019d-154">The results, which are `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` objects, are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="7019d-155">`ForEach-Object` 格納されているオブジェクトと後続のオブジェクトの構造化された出力を作成し `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` `[System.Net.NetworkInformation.PingReply]` ます。</span><span class="sxs-lookup"><span data-stu-id="7019d-155">`ForEach-Object` creates a structured output of the contained `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` objects and subsequent `[System.Net.NetworkInformation.PingReply]` objects.</span></span>

## <span data-ttu-id="7019d-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7019d-156">PARAMETERS</span></span>

### <span data-ttu-id="7019d-157">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="7019d-157">-BufferSize</span></span>

<span data-ttu-id="7019d-158">このコマンドで送信されるバッファーのサイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-158">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="7019d-159">既定値は 32 です。</span><span class="sxs-lookup"><span data-stu-id="7019d-159">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-160">-カウント</span><span class="sxs-lookup"><span data-stu-id="7019d-160">-Count</span></span>

<span data-ttu-id="7019d-161">送信するエコー要求の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-161">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="7019d-162">既定値は 4 ですが、</span><span class="sxs-lookup"><span data-stu-id="7019d-162">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-163">-Delay</span><span class="sxs-lookup"><span data-stu-id="7019d-163">-Delay</span></span>

<span data-ttu-id="7019d-164">ping 間の間隔を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-164">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-165">-DontFragment</span><span class="sxs-lookup"><span data-stu-id="7019d-165">-DontFragment</span></span>

<span data-ttu-id="7019d-166">このパラメーターは、IP ヘッダーに don't **Fragment** フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-166">This parameter sets the **Don't Fragment** flag in the IP header.</span></span> <span data-ttu-id="7019d-167">このパラメーターを **BufferSize** パラメーターと共に使用して、パスの MTU サイズをテストできます。</span><span class="sxs-lookup"><span data-stu-id="7019d-167">You can use this parameter with the **BufferSize** parameter to test the Path MTU size.</span></span> <span data-ttu-id="7019d-168">パス MTU の詳細については、wikipedia の [パス Mtu 検出](https://wikipedia.org/wiki/Path_MTU_Discovery) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7019d-168">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-169">-IPv4</span><span class="sxs-lookup"><span data-stu-id="7019d-169">-IPv4</span></span>

<span data-ttu-id="7019d-170">テストに IPv4 プロトコルを使用するようにコマンドレットを強制します。</span><span class="sxs-lookup"><span data-stu-id="7019d-170">Forces the cmdlet to use the IPv4 protocol for the test.</span></span>

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

### <span data-ttu-id="7019d-171">-IPv6</span><span class="sxs-lookup"><span data-stu-id="7019d-171">-IPv6</span></span>

<span data-ttu-id="7019d-172">テストに IPv6 プロトコルを使用するようにコマンドレットを強制します。</span><span class="sxs-lookup"><span data-stu-id="7019d-172">Forces the cmdlet to use the IPv6 protocol for the test.</span></span>

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

### <span data-ttu-id="7019d-173">-MaxHops</span><span class="sxs-lookup"><span data-stu-id="7019d-173">-MaxHops</span></span>

<span data-ttu-id="7019d-174">ICMP 要求メッセージを送信できる最大ホップ数を設定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-174">Sets the maximum number of hops that an ICMP request message can be sent.</span></span> <span data-ttu-id="7019d-175">既定値は、オペレーティングシステムによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-175">The default value is controlled by the operating system.</span></span> <span data-ttu-id="7019d-176">Windows 10 の既定値は128ホップです。</span><span class="sxs-lookup"><span data-stu-id="7019d-176">The default value for Windows 10 is 128 hops.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-177">-Ping</span><span class="sxs-lookup"><span data-stu-id="7019d-177">-Ping</span></span>

<span data-ttu-id="7019d-178">コマンドレットが ping テストを実行します。これは、既定のアクションです。</span><span class="sxs-lookup"><span data-stu-id="7019d-178">Causes the cmdlet to do a ping test, which is the default action.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: Ping test
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-179">-非表示</span><span class="sxs-lookup"><span data-stu-id="7019d-179">-Quiet</span></span>

<span data-ttu-id="7019d-180">**Quiet** パラメーター **は、boolean 値を** **system.string オブジェクトで返します。**</span><span class="sxs-lookup"><span data-stu-id="7019d-180">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="7019d-181">このパラメーターを使用すると、すべてのエラーが抑制します。</span><span class="sxs-lookup"><span data-stu-id="7019d-181">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="7019d-182">テストされた各接続は、 **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="7019d-182">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="7019d-183">**TargetName** パラメーターに複数のコンピューターが指定されている場合は、 **ブール** 値の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-183">If the **TargetName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="7019d-184">Ping **any** が成功した場合 `$True` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-184">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="7019d-185">**すべて** の ping が失敗 `$False` した場合は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-185">If **all** pings fail, `$False` is returned.</span></span>

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

### <span data-ttu-id="7019d-186">-ResolveDestination</span><span class="sxs-lookup"><span data-stu-id="7019d-186">-ResolveDestination</span></span>

<span data-ttu-id="7019d-187">コマンドレットがターゲットの DNS 名を解決しようとします。</span><span class="sxs-lookup"><span data-stu-id="7019d-187">Causes the cmdlet to attempt to resolve the DNS name of the target.</span></span>

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

### <span data-ttu-id="7019d-188">-Source</span><span class="sxs-lookup"><span data-stu-id="7019d-188">-Source</span></span>

<span data-ttu-id="7019d-189">ping の送信元コンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-189">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="7019d-190">コンピューター名のコンマ区切りのリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="7019d-190">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="7019d-191">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="7019d-191">The default is the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: PingCount, PingContinues, TraceRoute, ConnectionByTCPPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-192">-TargetName</span><span class="sxs-lookup"><span data-stu-id="7019d-192">-TargetName</span></span>

<span data-ttu-id="7019d-193">テストするコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-193">Specifies the computers to test.</span></span> <span data-ttu-id="7019d-194">コンピューター名を入力するか、IP アドレスを IPv4 または IPv6 形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="7019d-194">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="7019d-195">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7019d-195">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="7019d-196">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="7019d-196">This parameter is required.</span></span> <span data-ttu-id="7019d-197">**ComputerName** は、このパラメーターのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="7019d-197">**ComputerName** is an alias for this parameter.</span></span>

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

### <span data-ttu-id="7019d-198">-TCPPort</span><span class="sxs-lookup"><span data-stu-id="7019d-198">-TCPPort</span></span>

<span data-ttu-id="7019d-199">TCP 接続テストで使用するターゲットの TCP ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-199">Specifies the TCP port number on the target to be used in the TCP connection test.</span></span> <span data-ttu-id="7019d-200">コマンドレットは、ターゲットの指定されたポートへの TCP 接続を試行します。</span><span class="sxs-lookup"><span data-stu-id="7019d-200">The cmdlet will attempt to make a TCP connection to the specified port on the target.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ConnectionByTCPPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-201">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="7019d-201">-TimeoutSeconds</span></span>

<span data-ttu-id="7019d-202">テストのタイムアウト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7019d-202">Sets the timeout value for the test.</span></span> <span data-ttu-id="7019d-203">タイムアウトの期限が切れる前に応答を受信しなかった場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="7019d-203">The test fails if a response isn't received before the timeout expires.</span></span> <span data-ttu-id="7019d-204">既定値は 5 秒です。</span><span class="sxs-lookup"><span data-stu-id="7019d-204">The default is five seconds.</span></span>

<span data-ttu-id="7019d-205">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7019d-205">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="7019d-206">-Traceroute</span><span class="sxs-lookup"><span data-stu-id="7019d-206">-Traceroute</span></span>

<span data-ttu-id="7019d-207">コマンドレットが traceroute テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7019d-207">Causes the cmdlet to do a traceroute test.</span></span> <span data-ttu-id="7019d-208">このパラメーターを使用すると、コマンドレットは `TestConnectionCommand+TraceRouteResult` オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7019d-208">When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceRouteResult` object.</span></span>

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

### <span data-ttu-id="7019d-209">-続行</span><span class="sxs-lookup"><span data-stu-id="7019d-209">-Continues</span></span>

<span data-ttu-id="7019d-210">コマンドレットによって ping 要求が連続して送信されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-210">Causes the cmdlet to send ping requests continuously.</span></span> <span data-ttu-id="7019d-211">このパラメーターは、 **Count** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7019d-211">This parameter can't be used with the **Count** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-212">-MTUSizeDetect</span><span class="sxs-lookup"><span data-stu-id="7019d-212">-MTUSizeDetect</span></span>

<span data-ttu-id="7019d-213">このパラメーターは、パスの MTU サイズを検出するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-213">This parameter is used to discover the Path MTU size.</span></span> <span data-ttu-id="7019d-214">コマンドレットは、ターゲットにパスの MTU サイズを含む、 **ping # MTUSize** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7019d-214">The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target.</span></span> <span data-ttu-id="7019d-215">パス MTU の詳細については、wikipedia の [パス Mtu 検出](https://wikipedia.org/wiki/Path_MTU_Discovery) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7019d-215">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetectionOfMTUSize
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7019d-216">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7019d-216">CommonParameters</span></span>

<span data-ttu-id="7019d-217">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7019d-217">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7019d-218">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7019d-218">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7019d-219">入力</span><span class="sxs-lookup"><span data-stu-id="7019d-219">INPUTS</span></span>

### <span data-ttu-id="7019d-220">なし</span><span class="sxs-lookup"><span data-stu-id="7019d-220">None</span></span>

<span data-ttu-id="7019d-221">このコマンドレットに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7019d-221">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7019d-222">出力</span><span class="sxs-lookup"><span data-stu-id="7019d-222">OUTPUTS</span></span>

### <span data-ttu-id="7019d-223">TestConnectionCommand + Ping Report、TestConnectionCommand + TraceRouteResult、Boolean、Ping Reply # MTUSize</span><span class="sxs-lookup"><span data-stu-id="7019d-223">TestConnectionCommand+PingReport, TestConnectionCommand+TraceRouteResult, Boolean, PingReply#MTUSize</span></span>

<span data-ttu-id="7019d-224">**Quiet** パラメーターを指定すると、 **ブール** 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-224">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="7019d-225">複数の接続がテストされている場合は、 **ブール** 値の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="7019d-225">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="7019d-226">それ以外の場合は、 `Test-Connection` 各 ping に対して **Testconnectioncommand + ping report** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7019d-226">Otherwise, `Test-Connection` returns a **TestConnectionCommand+PingReport** object for each ping.</span></span>

## <span data-ttu-id="7019d-227">注</span><span class="sxs-lookup"><span data-stu-id="7019d-227">NOTES</span></span>

## <span data-ttu-id="7019d-228">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7019d-228">RELATED LINKS</span></span>

[<span data-ttu-id="7019d-229">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="7019d-229">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="7019d-230">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="7019d-230">Stop-Computer</span></span>](Stop-Computer.md)

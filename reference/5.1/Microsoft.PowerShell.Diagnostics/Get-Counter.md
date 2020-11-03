---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: 7c1ab665fc7ffddc54ec936f80b76b4329291a3b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212683"
---
# <span data-ttu-id="85b70-103">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="85b70-103">Get-Counter</span></span>

## <span data-ttu-id="85b70-104">概要</span><span class="sxs-lookup"><span data-stu-id="85b70-104">SYNOPSIS</span></span>
<span data-ttu-id="85b70-105">ローカル コンピューターおよびリモート コンピューターからパフォーマンス カウンターのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-105">Gets performance counter data from local and remote computers.</span></span>

## <span data-ttu-id="85b70-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85b70-106">SYNTAX</span></span>

### <span data-ttu-id="85b70-107">GetCounterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="85b70-107">GetCounterSet (Default)</span></span>

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="85b70-108">ListSetSet</span><span class="sxs-lookup"><span data-stu-id="85b70-108">ListSetSet</span></span>

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="85b70-109">Description</span><span class="sxs-lookup"><span data-stu-id="85b70-109">DESCRIPTION</span></span>

<span data-ttu-id="85b70-110">`Get-Counter`コマンドレットは、Windows ファミリのオペレーティングシステムのパフォーマンス監視インストルメンテーションからパフォーマンスカウンターデータを直接取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-110">The `Get-Counter` cmdlet gets performance counter data directly from the performance monitoring instrumentation in the Windows family of operating systems.</span></span> <span data-ttu-id="85b70-111">`Get-Counter` ローカルコンピューターまたはリモートコンピューターからパフォーマンスデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-111">`Get-Counter` gets performance data from a local computer or remote computers.</span></span>

<span data-ttu-id="85b70-112">パラメーターを使用して、 `Get-Counter` 1 つまたは複数のコンピューターを指定したり、パフォーマンスカウンターセットとそれらに含まれるインスタンスを一覧表示したり、サンプル間隔を設定したり、サンプルの最大数を指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="85b70-112">You can use the `Get-Counter` parameters to specify one or more computers, list the performance counter sets and the instances they contain, set the sample intervals, and specify the maximum number of samples.</span></span> <span data-ttu-id="85b70-113">パラメーターを指定しない場合は、 `Get-Counter` 一連のシステムカウンターのパフォーマンスカウンターデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-113">Without parameters, `Get-Counter` gets performance counter data for a set of system counters.</span></span>

<span data-ttu-id="85b70-114">多くのカウンターセットは、アクセス制御リスト (ACL) によって保護されています。</span><span class="sxs-lookup"><span data-stu-id="85b70-114">Many counter sets are protected by access control lists (ACL).</span></span> <span data-ttu-id="85b70-115">すべてのカウンターセットを表示するには、[ **管理者として実行** ] オプションを使用して PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="85b70-115">To see all counter sets, open PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="85b70-116">例</span><span class="sxs-lookup"><span data-stu-id="85b70-116">EXAMPLES</span></span>

### <span data-ttu-id="85b70-117">例 1: カウンターセットの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="85b70-117">Example 1: Get the counter set list</span></span>

<span data-ttu-id="85b70-118">この例では、ローカルコンピューターのカウンターセットの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-118">This example gets the local computer's list of counter sets.</span></span>

```powershell
Get-Counter -ListSet *
```

```Output
CounterSetName     : Processor
MachineName        : .
CounterSetType     : MultiInstance
Description        : The Processor performance object consists of counters that measure aspects ...
                     computer that performs arithmetic and logical computations, initiates ...
                     computer can have multiple processors.  The processor object represents ...
Paths              : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
PathsWithInstances : {\Processor(0)\% Processor Time, \Processor(1)\% Processor Time, ...
Counter            : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
```

<span data-ttu-id="85b70-119">`Get-Counter`**Listset** パラメーターをアスタリスク () と共に使用して `*` 、カウンターセットの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-119">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get the list of counter sets.</span></span>
<span data-ttu-id="85b70-120">MachineName 列のドット ( `.` ) **MachineName** は、ローカルコンピューターを表します。</span><span class="sxs-lookup"><span data-stu-id="85b70-120">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="85b70-121">例 2: SampleInterval と MaxSamples を指定する</span><span class="sxs-lookup"><span data-stu-id="85b70-121">Example 2: Specify the SampleInterval and MaxSamples</span></span>

<span data-ttu-id="85b70-122">この例では、ローカルコンピューター上のすべてのプロセッサのカウンターデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-122">This examples gets the counter data for all processors on the local computer.</span></span> <span data-ttu-id="85b70-123">データは、3つのサンプルが存在するまで2秒間隔で収集されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-123">Data is collected at two-second intervals until there are three samples.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 3
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/18/2019 14:39:56        \\Computer01\processor(_total)\% processor time :
                          20.7144271584086

6/18/2019 14:39:58        \\Computer01\processor(_total)\% processor time :
                          10.4391790575511

6/18/2019 14:40:01        \\Computer01\processor(_total)\% processor time :
                          37.5968799396998
```

<span data-ttu-id="85b70-124">`Get-Counter`**counter パラメーターを** 使用して、カウンターのパスを指定し `\Processor(_Total)\% Processor Time` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-124">`Get-Counter` uses the **Counter** parameter to specify the counter path `\Processor(_Total)\% Processor Time`.</span></span> <span data-ttu-id="85b70-125">**Sampleinterval** パラメーターは、カウンターをチェックする2秒間隔を設定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-125">The **SampleInterval** parameter sets a two-second interval to check the counter.</span></span> <span data-ttu-id="85b70-126">**Maxsamples** によって、カウンターをチェックする最大回数が3であることが決定されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-126">**MaxSamples** determines that three is the maximum number of times to check the counter.</span></span>

### <span data-ttu-id="85b70-127">例 3: カウンターの継続的なサンプルを取得する</span><span class="sxs-lookup"><span data-stu-id="85b70-127">Example 3: Get continuous samples of a counter</span></span>

<span data-ttu-id="85b70-128">この例では、1秒ごとにカウンターの連続サンプルを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-128">This examples gets continuous samples for a counter every second.</span></span> <span data-ttu-id="85b70-129">コマンドを停止するには、 <kbd>ctrl</kbd> + <kbd>C</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="85b70-129">To stop the command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="85b70-130">サンプル間に長い間隔を指定するには、 **sampleinterval** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-130">To specify a longer interval between samples, use the **SampleInterval** parameter.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -Continuous
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 15:35:03        \\Computer01\processor(_total)\% processor time :
                          43.8522842937022

6/19/2019 15:35:04        \\Computer01\processor(_total)\% processor time :
                          29.7896844697383

6/19/2019 15:35:05        \\Computer01\processor(_total)\% processor time :
                          29.4962645638135

6/19/2019 15:35:06        \\Computer01\processor(_total)\% processor time :
                          25.5901500127408
```

<span data-ttu-id="85b70-131">`Get-Counter`**counter パラメーターを** 使用してカウンタを指定し `\Processor\% Processor Time` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-131">`Get-Counter` uses the **Counter** parameter to specify the `\Processor\% Processor Time` counter.</span></span>
<span data-ttu-id="85b70-132">**Continuous** パラメーターは、コマンドが <kbd>CTRL</kbd>C で停止されるまで、1秒ごとにサンプルを取得することを指定し + <kbd>C</kbd>ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-132">The **Continuous** parameter specifies to get samples every second until the command is stopped with <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <span data-ttu-id="85b70-133">例 4: カウンターセットのアルファベット順の一覧</span><span class="sxs-lookup"><span data-stu-id="85b70-133">Example 4: Alphabetical list of counter sets</span></span>

<span data-ttu-id="85b70-134">この例では、パイプラインを使用してカウンターの一覧を取得し、リストをアルファベット順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="85b70-134">This example uses the pipeline to get the counter list set and then sort the list in alphabetical order.</span></span>

```powershell
Get-Counter -ListSet * | Sort-Object -Property CounterSetName | Format-Table -AutoSize
```

```Output
CounterSetName                        MachineName CounterSetType  Description
--------------                        ----------- --------------  -----------
.NET CLR Data                         .           SingleInstance  .Net CLR Data
.NET Data Provider for SqlServer      .           SingleInstance  Counters for System.Data.SqlClient
AppV Client Streamed Data Percentage  .           SingleInstance  Size of data streamed to disk ...
Authorization Manager Applications    .           SingleInstance  The set of Counters for ...
BitLocker                             .           MultiInstance   BitLocker Drive Encryption ...
Bluetooth Device                      .           SingleInstance  Counters related to a remote ...
Cache                                 .           SingleInstance  The Cache performance object ...
Client Side Caching                   .           SingleInstance  Performance counters for SMB ...
```

<span data-ttu-id="85b70-135">`Get-Counter`**listset** パラメーターをアスタリスク () と共に使用して、 `*` カウンターセットの完全な一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-135">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get a complete list of counter sets.</span></span> <span data-ttu-id="85b70-136">**CounterSet** オブジェクトは、パイプラインを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-136">The **CounterSet** objects are sent down the pipeline.</span></span> <span data-ttu-id="85b70-137">`Sort-Object`**Property** パラメーターを使用して、オブジェクトが **CounterSetName** によって並べ替えられるように指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-137">`Sort-Object` uses the **Property** parameter to specify that the objects are sorted by **CounterSetName** .</span></span> <span data-ttu-id="85b70-138">オブジェクトは、パイプラインの下位に送信され `Format-Table` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-138">The objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="85b70-139">**AutoSize** パラメーターを指定すると、列の幅が調整され、切り捨てが最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="85b70-139">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

<span data-ttu-id="85b70-140">MachineName 列のドット ( `.` ) **MachineName** は、ローカルコンピューターを表します。</span><span class="sxs-lookup"><span data-stu-id="85b70-140">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="85b70-141">例 5: バックグラウンドジョブを実行してカウンターデータを取得する</span><span class="sxs-lookup"><span data-stu-id="85b70-141">Example 5: Run a background job to get counter data</span></span>

<span data-ttu-id="85b70-142">この例では、は、 `Start-Job` `Get-Counter` ローカルコンピューター上でバックグラウンドジョブとしてコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="85b70-142">In this example, `Start-Job` runs a `Get-Counter` command as a background job on the local computer.</span></span>
<span data-ttu-id="85b70-143">ジョブからのパフォーマンスカウンターの出力を表示するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-143">To view the performance counter output from the job, use the `Receive-Job` cmdlet.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

<span data-ttu-id="85b70-144">`Start-Job`**ScriptBlock** パラメーターを使用してコマンドを実行 `Get-Counter` します。</span><span class="sxs-lookup"><span data-stu-id="85b70-144">`Start-Job` uses the **ScriptBlock** parameter to run a `Get-Counter` command.</span></span> <span data-ttu-id="85b70-145">`Get-Counter`**counter パラメーターを** 使用して、カウンターのパスを指定し `\LogicalDisk(_Total)\% Free Space` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-145">`Get-Counter` uses the **Counter** parameter to specify the counter path `\LogicalDisk(_Total)\% Free Space`.</span></span> <span data-ttu-id="85b70-146">**Maxsamples** パラメーターでは、カウンターの1000サンプルを取得するように指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-146">The **MaxSamples** parameter specifies to get 1000 samples of the counter.</span></span>

### <span data-ttu-id="85b70-147">例 6: 複数のコンピューターからカウンターデータを取得する</span><span class="sxs-lookup"><span data-stu-id="85b70-147">Example 6: Get counter data from multiple computers</span></span>

<span data-ttu-id="85b70-148">この例では、変数を使用して、2台のコンピューターからパフォーマンスカウンターデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-148">This example uses a variable to get performance counter data from two computers.</span></span>

```powershell
$DiskReads = "\LogicalDisk(C:)\Disk Reads/sec"
$DiskReads | Get-Counter -ComputerName Server01, Server02 -MaxSamples 10
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/21/2019 10:51:04        \\Server01\logicaldisk(c:)\disk reads/sec :
                          0

                          \\Server02\logicaldisk(c:)\disk reads/sec :
                          0.983050344269146
```

<span data-ttu-id="85b70-149">変数には `$DiskReads` 、カウンターパスが格納され `\LogicalDisk(C:)\Disk Reads/sec` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-149">The `$DiskReads` variable stores the `\LogicalDisk(C:)\Disk Reads/sec` counter path.</span></span> <span data-ttu-id="85b70-150">変数は、パイプラインを介し `$DiskReads` てに送信され `Get-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-150">The `$DiskReads` variable is sent down the pipeline to `Get-Counter`.</span></span> <span data-ttu-id="85b70-151">**Counter** は最初の位置パラメーターであり、に格納されているパスを受け入れ `$DiskReads` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-151">**Counter** is the first position parameter and accepts the path stored in `$DiskReads`.</span></span> <span data-ttu-id="85b70-152">**ComputerName** は2台のコンピューターを指定し、 **maxsamples** は各コンピューターから10個のサンプルを取得するように指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-152">**ComputerName** specifies the two computers and **MaxSamples** specifies to get 10 samples from each computer.</span></span>

### <span data-ttu-id="85b70-153">例 7: 複数のランダムなコンピューターからカウンターのインスタンス値を取得する</span><span class="sxs-lookup"><span data-stu-id="85b70-153">Example 7: Get a counter's instance values from multiple random computers</span></span>

<span data-ttu-id="85b70-154">この例では、企業内のリモートコンピューター50のパフォーマンスカウンターの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-154">This example gets the value of a performance counter on 50 random, remote computers in the enterprise.</span></span> <span data-ttu-id="85b70-155">**ComputerName** パラメーターは、変数に格納されているランダムなコンピューター名を使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-155">The **ComputerName** parameter uses random computer names stored in a variable.</span></span> <span data-ttu-id="85b70-156">変数内のコンピューター名を更新するには、変数を再作成します。</span><span class="sxs-lookup"><span data-stu-id="85b70-156">To update the computer names in the variable, recreate the variable.</span></span>

<span data-ttu-id="85b70-157">**ComputerName** パラメーターのサーバー名の代わりに、テキストファイルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="85b70-157">An alternative for the server names in the **ComputerName** parameter is to use a text file.</span></span> <span data-ttu-id="85b70-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="85b70-158">For example:</span></span>

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

<span data-ttu-id="85b70-159">カウンターパスには、 `*` 各リモートコンピューターのプロセッサのデータを取得するために、インスタンス名にアスタリスク () が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85b70-159">The counter path includes an asterisk (`*`) in the instance name to get the data for each of the remote computer's processors.</span></span>

```powershell
$Servers = Get-Random (Get-Content -Path C:\Servers.txt) -Count 50
$Counter = "\Processor(*)\% Processor Time"
Get-Counter -Counter $Counter -ComputerName $Servers
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/20/2019 12:20:35        \\Server01\processor(0)\% processor time :
                          6.52610319637854

                          \\Server01\processor(1)\% processor time :
                          3.41030663625782

                          \\Server01\processor(2)\% processor time :
                          9.64189975649925

                          \\Server01\processor(3)\% processor time :
                          1.85240835619747

                          \\Server01\processor(_total)\% processor time :
                          5.35768447160776
```

<span data-ttu-id="85b70-160">`Get-Random`コマンドレットでは、を使用し `Get-Content` て、ファイルから50のランダムなコンピューター名を選択し `Servers.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-160">The `Get-Random` cmdlet uses `Get-Content` to select 50 random computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="85b70-161">リモートコンピューター名は変数に格納され `$Servers` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-161">The remote computer names are stored in the `$Servers` variable.</span></span> <span data-ttu-id="85b70-162">`\Processor(*)\% Processor Time`カウンターのパスは変数に格納され `$Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-162">The `\Processor(*)\% Processor Time` counter's path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="85b70-163">`Get-Counter`**Counter** パラメーターを使用して、変数内のカウンターを指定し `$Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-163">`Get-Counter` uses the **Counter** parameter to specify the counters in the `$Counter` variable.</span></span> <span data-ttu-id="85b70-164">**ComputerName** パラメーターは、変数内のコンピューター名を指定し `$Servers` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-164">The **ComputerName** parameter specifies the computer names in the `$Servers` variable.</span></span>

### <span data-ttu-id="85b70-165">例 8: Path プロパティを使用して、書式設定されたパス名を取得する</span><span class="sxs-lookup"><span data-stu-id="85b70-165">Example 8: Use the Path property to get formatted path names</span></span>

<span data-ttu-id="85b70-166">この例では、カウンターセットの **path** プロパティを使用して、パフォーマンスカウンターの書式設定されたパス名を検索します。</span><span class="sxs-lookup"><span data-stu-id="85b70-166">This example uses the **Path** property of a counter set to find the formatted path names for the performance counters.</span></span>

<span data-ttu-id="85b70-167">パイプラインをコマンドレットと共に使用して、 `Where-Object` パス名のサブセットを検索します。</span><span class="sxs-lookup"><span data-stu-id="85b70-167">The pipeline is used with the `Where-Object` cmdlet to find a subset of the path names.</span></span> <span data-ttu-id="85b70-168">カウンターのパスの完全な一覧を検索するには、パイプライン ( `|` ) とコマンドを削除し `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-168">To find a counter sets complete list of counter paths, remove the pipeline (`|`) and `Where-Object` command.</span></span>

<span data-ttu-id="85b70-169">`$_`は、パイプライン内の現在のオブジェクトの自動変数です。</span><span class="sxs-lookup"><span data-stu-id="85b70-169">The `$_` is an automatic variable for the current object in the pipeline.</span></span>
<span data-ttu-id="85b70-170">詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b70-170">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
(Get-Counter -ListSet Memory).Paths | Where-Object { $_ -like "*Cache*" }
```

```Output
\Memory\Cache Faults/sec
\Memory\Cache Bytes
\Memory\Cache Bytes Peak
\Memory\System Cache Resident Bytes
\Memory\Standby Cache Reserve Bytes
\Memory\Standby Cache Normal Priority Bytes
\Memory\Standby Cache Core Bytes
\Memory\Long-Term Average Standby Cache Lifetime (s)
```

<span data-ttu-id="85b70-171">`Get-Counter`**listset** パラメーターを使用して、 **メモリ** カウンターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-171">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="85b70-172">コマンドはかっこで囲まれているため、 **Paths** プロパティは各パスを文字列として返します。</span><span class="sxs-lookup"><span data-stu-id="85b70-172">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="85b70-173">オブジェクトは、パイプラインの下位に送信され `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-173">The objects are sent down the pipeline to `Where-Object`.</span></span> <span data-ttu-id="85b70-174">`Where-Object` 変数を使用 `$_` して各オブジェクトを処理し、演算子を使用して `-like` 文字列の一致を検索し `*Cache*` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-174">`Where-Object` uses the variable `$_` to process each object and uses the `-like` operator to find matches for the string `*Cache*`.</span></span> <span data-ttu-id="85b70-175">アスタリスク ( `*` ) は、任意の文字に対するワイルドカードです。</span><span class="sxs-lookup"><span data-stu-id="85b70-175">The asterisks (`*`) are wildcards for any characters.</span></span>

### <span data-ttu-id="85b70-176">例 9: PathsWithInstances プロパティを使用して、書式設定されたパス名を取得する</span><span class="sxs-lookup"><span data-stu-id="85b70-176">Example 9: Use the PathsWithInstances property to get formatted path names</span></span>

<span data-ttu-id="85b70-177">この例では、 **PhysicalDisk** パフォーマンスカウンターのインスタンスを含む、書式設定されたパス名を取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-177">This example gets the formatted path names that include the instances for the **PhysicalDisk** performance counters.</span></span>

```powershell
(Get-Counter -ListSet PhysicalDisk).PathsWithInstances
```

```Output
\PhysicalDisk(0 C:)\Current Disk Queue Length
\PhysicalDisk(_Total)\Current Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Time
\PhysicalDisk(_Total)\% Disk Time
\PhysicalDisk(0 C:)\Avg. Disk Queue Length
\PhysicalDisk(_Total)\Avg. Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Read Time
\PhysicalDisk(_Total)\% Disk Read Time
```

<span data-ttu-id="85b70-178">`Get-Counter`**listset** パラメーターを使用して、 **PhysicalDisk** カウンターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-178">`Get-Counter` uses the **ListSet** parameter to specify the **PhysicalDisk** counter set.</span></span> <span data-ttu-id="85b70-179">このコマンドは、 **PathsWithInstances** プロパティが各パスインスタンスを文字列として返すように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="85b70-179">The command is enclosed in parentheses so that the **PathsWithInstances** property returns each path instance as a string.</span></span>

### <span data-ttu-id="85b70-180">例 10: カウンターセット内のカウンターごとに1つの値を取得する</span><span class="sxs-lookup"><span data-stu-id="85b70-180">Example 10: Get a single value for each counter in a counter set</span></span>

<span data-ttu-id="85b70-181">この例では、ローカルコンピューターの **メモリ** カウンターセット内のパフォーマンスカウンターごとに1つの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-181">In this example, a single value is returned for each performance counter in the local computer's **Memory** counter set.</span></span>

```powershell
$MemCounters = (Get-Counter -ListSet Memory).Paths
Get-Counter -Counter $MemCounters
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 12:05:00        \\Computer01\memory\page faults/sec :
                          868.772077545597

                          \\Computer01\memory\available bytes :
                          9031176192

                          \\Computer01\memory\committed bytes :
                          8242982912

                          \\Computer01\memory\commit limit :
                          19603333120
```

<span data-ttu-id="85b70-182">`Get-Counter`**listset** パラメーターを使用して、 **メモリ** カウンターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-182">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="85b70-183">コマンドはかっこで囲まれているため、 **Paths** プロパティは各パスを文字列として返します。</span><span class="sxs-lookup"><span data-stu-id="85b70-183">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="85b70-184">パスは変数に格納され `$MemCounters` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-184">The paths are stored in the `$MemCounters` variable.</span></span> <span data-ttu-id="85b70-185">`Get-Counter`**counter** パラメーターを使用して、変数内のカウンターパスを指定し `$MemCounters` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-185">`Get-Counter` uses the **Counter** parameter to specify the counter paths in the `$MemCounters` variable.</span></span>

### <span data-ttu-id="85b70-186">例 11: オブジェクトのプロパティ値を表示する</span><span class="sxs-lookup"><span data-stu-id="85b70-186">Example 11: Display an object's property values</span></span>

<span data-ttu-id="85b70-187">**PerformanceCounterSample** オブジェクトのプロパティ値は、各データサンプルを表します。</span><span class="sxs-lookup"><span data-stu-id="85b70-187">The property values in the **PerformanceCounterSample** object represent each data sample.</span></span> <span data-ttu-id="85b70-188">この例では、 **Countersamples** オブジェクトのプロパティを使用して、データの確認、選択、並べ替え、およびグループ化を行います。</span><span class="sxs-lookup"><span data-stu-id="85b70-188">In this example we use the properties of the **CounterSamples** object to examine, select, sort, and group the data.</span></span>

```powershell
$Counter = "\\Server01\Process(Idle)\% Processor Time"
$Data = Get-Counter $Counter
$Data.CounterSamples | Format-List -Property *
```

```Output
Path             : \\Server01\process(idle)\% processor time
InstanceName     : idle
CookedValue      : 198.467899571389
RawValue         : 14329160321003
SecondValue      : 128606459528326201
MultipleCount    : 1
CounterType      : Timer100Ns
Timestamp        : 6/19/2019 12:20:49
Timestamp100NSec : 128606207528320000
Status           : 0
DefaultScale     : 0
TimeBase         : 10000000
```

<span data-ttu-id="85b70-189">カウンターパスは変数に格納され `$Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-189">The counter path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="85b70-190">`Get-Counter` カウンター値の1つのサンプルを取得し、その結果を変数に格納し `$Data` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-190">`Get-Counter` gets one sample of the counter values and stores the results in the `$Data` variable.</span></span> <span data-ttu-id="85b70-191">変数は、 `$Data` **countersamples** プロパティを使用して、オブジェクトのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-191">The `$Data` variable uses the **CounterSamples** property to get the object's properties.</span></span> <span data-ttu-id="85b70-192">オブジェクトは、パイプライン内でに送信され `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-192">The object is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="85b70-193">**Property** パラメーターは、アスタリスク ( `*` ) ワイルドカードを使用してすべてのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="85b70-193">The **Property** parameter uses an asterisk (`*`) wildcard to select all the properties.</span></span>

### <span data-ttu-id="85b70-194">例 12: パフォーマンスカウンターの配列値</span><span class="sxs-lookup"><span data-stu-id="85b70-194">Example 12: Performance counter array values</span></span>

<span data-ttu-id="85b70-195">この例では、変数に各パフォーマンスカウンターが格納されています。</span><span class="sxs-lookup"><span data-stu-id="85b70-195">In this example, a variable stores each performance counter.</span></span> <span data-ttu-id="85b70-196">**Countersamples** プロパティは、特定のカウンター値を表示できる配列です。</span><span class="sxs-lookup"><span data-stu-id="85b70-196">The **CounterSamples** property is an array that can display specific counter values.</span></span>

<span data-ttu-id="85b70-197">各カウンターサンプルを表示するには、を使用し `$Counter.CounterSamples` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-197">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

<span data-ttu-id="85b70-198">`Get-Counter`**counter パラメーターを** 使用してカウンタを指定し `\Processor(*)\% Processor Time` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-198">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="85b70-199">値は変数に格納され `$Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-199">The values are stored in the `$Counter` variable.</span></span>
<span data-ttu-id="85b70-200">`$Counter.CounterSamples[0]` 最初のカウンター値の配列値を表示します。</span><span class="sxs-lookup"><span data-stu-id="85b70-200">`$Counter.CounterSamples[0]` displays the array value for the first counter value.</span></span>

### <span data-ttu-id="85b70-201">例 13: パフォーマンスカウンターの値を比較する</span><span class="sxs-lookup"><span data-stu-id="85b70-201">Example 13: Compare performance counter values</span></span>

<span data-ttu-id="85b70-202">この例では、ローカルコンピューター上の各プロセッサによって使用されるプロセッサ時間を検索します。</span><span class="sxs-lookup"><span data-stu-id="85b70-202">This example finds the amount of processor time used by each processor on the local computer.</span></span> <span data-ttu-id="85b70-203">**Countersamples** プロパティは、カウンターデータを指定した値と比較するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-203">The **CounterSamples** property is used to compare the counter data against a specified value.</span></span>

<span data-ttu-id="85b70-204">各カウンターサンプルを表示するには、を使用し `$Counter.CounterSamples` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-204">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples | Where-Object { $_.CookedValue -lt "20" }
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              12.6398025240208
\\Computer01\processor(1)\% processor time   1              15.7598095767344
```

<span data-ttu-id="85b70-205">`Get-Counter`**counter パラメーターを** 使用してカウンタを指定し `\Processor(*)\% Processor Time` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-205">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="85b70-206">値は変数に格納され `$Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-206">The values are stored in the `$Counter` variable.</span></span> <span data-ttu-id="85b70-207">に格納されて `$Counter.CounterSamples` いるオブジェクトは、パイプラインを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-207">The objects stored in `$Counter.CounterSamples` are sent down the pipeline.</span></span> <span data-ttu-id="85b70-208">`Where-Object` スクリプトブロックを使用して、各オブジェクトの値を指定した20の値と比較します。</span><span class="sxs-lookup"><span data-stu-id="85b70-208">`Where-Object` uses a script block to compare each objects value against a specified value of 20.</span></span> <span data-ttu-id="85b70-209">`$_.CookedValue`は、パイプライン内の現在のオブジェクトの変数です。</span><span class="sxs-lookup"><span data-stu-id="85b70-209">The `$_.CookedValue` is a variable for the current object in the pipeline.</span></span> <span data-ttu-id="85b70-210">**CookedValue** が20未満のカウンターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-210">Counters with a **CookedValue** that is less than 20 are displayed.</span></span>

### <span data-ttu-id="85b70-211">例 14: パフォーマンスカウンターデータを並べ替える</span><span class="sxs-lookup"><span data-stu-id="85b70-211">Example 14: Sort performance counter data</span></span>

<span data-ttu-id="85b70-212">この例では、パフォーマンスカウンターデータを並べ替える方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85b70-212">This example shows how to sort performance counter data.</span></span> <span data-ttu-id="85b70-213">この例では、サンプル中に最もプロセッサ時間を使用しているコンピューター上のプロセスを検索します。</span><span class="sxs-lookup"><span data-stu-id="85b70-213">The example finds the processes on the computer that are using the most processor time during the sample.</span></span>

```powershell
$Procs = Get-Counter -Counter "\Process(*)\% Processor Time"
$Procs.CounterSamples | Sort-Object -Property CookedValue -Descending |
   Format-Table -Property Path, InstanceName, CookedValue -AutoSize
```

```Output
Path                                                         InstanceName             CookedValue
----                                                         ------------             -----------
\\Computer01\process(_total)\% processor time                _total              395.464129650573
\\Computer01\process(idle)\% processor time                  idle                389.356575524695
\\Computer01\process(mssense)\% processor time               mssense             3.05377706293879
\\Computer01\process(csrss#1)\% processor time               csrss               1.52688853146939
\\Computer01\process(microsoftedgecp#10)\% processor time    microsoftedgecp     1.52688853146939
\\Computer01\process(runtimebroker#5)\% processor time       runtimebroker                      0
\\Computer01\process(settingsynchost)\% processor time       settingsynchost                    0
\\Computer01\process(microsoftedgecp#16)\% processor time    microsoftedgecp                    0
```

<span data-ttu-id="85b70-214">`Get-Counter`**counter** パラメーターを使用して、 `\Process(*)\% Processor Time` ローカルコンピューター上のすべてのプロセスのカウンターを指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-214">`Get-Counter` uses the **Counter** parameter to specify the `\Process(*)\% Processor Time` counter for all the processes on the local computer.</span></span> <span data-ttu-id="85b70-215">結果は変数に格納され `$Procs` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-215">The result is stored in the `$Procs` variable.</span></span> <span data-ttu-id="85b70-216">`$Procs` **Countersamples** プロパティを持つ変数は、 **PerformanceCounterSample** オブジェクトをパイプラインの下位に送信します。</span><span class="sxs-lookup"><span data-stu-id="85b70-216">The `$Procs` variable with the **CounterSamples** property sends the **PerformanceCounterSample** objects down the pipeline.</span></span> <span data-ttu-id="85b70-217">`Sort-Object`**Property** パラメーターを使用して、オブジェクトを **CookedValue** で **降順** に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="85b70-217">`Sort-Object` uses the **Property** parameter to sort the objects by **CookedValue** in **Descending** order.</span></span> <span data-ttu-id="85b70-218">`Format-Table`**Property** パラメーターを使用して、出力の列を選択します。</span><span class="sxs-lookup"><span data-stu-id="85b70-218">`Format-Table` uses the **Property** parameter to select the columns for the output.</span></span> <span data-ttu-id="85b70-219">**AutoSize** パラメーターを指定すると、列の幅が調整され、切り捨てが最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="85b70-219">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

## <span data-ttu-id="85b70-220">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85b70-220">PARAMETERS</span></span>

### <span data-ttu-id="85b70-221">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="85b70-221">-ComputerName</span></span>

<span data-ttu-id="85b70-222">1つのコンピューター名、または **リモート** コンピューター名のコンマ区切りの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-222">Specifies one computer name or a comma-separated array of **remote** computer names.</span></span> <span data-ttu-id="85b70-223">NetBIOS 名、IP アドレス、またはコンピューターの完全修飾ドメイン名を使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-223">Use the NetBIOS name, an IP address, or the computer's fully qualified domain name.</span></span>

<span data-ttu-id="85b70-224">**ローカル** コンピューターからパフォーマンスカウンターデータを取得するには、 **ComputerName** パラメーターを除外します。</span><span class="sxs-lookup"><span data-stu-id="85b70-224">To get performance counter data from the **local** computer, exclude the **ComputerName** parameter.</span></span>
<span data-ttu-id="85b70-225">**MachineName** 列を含む **listset** などの出力の場合、ドット () は `.` ローカルコンピューターを示します。</span><span class="sxs-lookup"><span data-stu-id="85b70-225">For output such as a **ListSet** that contains the **MachineName** column, a dot (`.`) indicates the local computer.</span></span>

<span data-ttu-id="85b70-226">`Get-Counter` は、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="85b70-226">`Get-Counter` doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="85b70-227">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="85b70-227">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85b70-228">-Continuous</span><span class="sxs-lookup"><span data-stu-id="85b70-228">-Continuous</span></span>

<span data-ttu-id="85b70-229">**Continuous** が指定されている場合、は、 `Get-Counter` <kbd>CTRL</kbd>C キーを押すまでサンプルを取得し + <kbd>C</kbd>ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-229">When the **Continuous** is specified, `Get-Counter` gets samples until you press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="85b70-230">サンプルは、指定されたパフォーマンスカウンターごとに1秒ごとに取得されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-230">Samples are obtained every second for each specified performance counter.</span></span> <span data-ttu-id="85b70-231">**Sampleinterval** パラメーターを使用して、連続サンプルの間隔を長くします。</span><span class="sxs-lookup"><span data-stu-id="85b70-231">Use the **SampleInterval** parameter to increase the interval between continuous samples.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85b70-232">-カウンター</span><span class="sxs-lookup"><span data-stu-id="85b70-232">-Counter</span></span>

<span data-ttu-id="85b70-233">1つ以上のカウンターパスへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-233">Specifies the path to one or more counter paths.</span></span> <span data-ttu-id="85b70-234">パスは、コンマで区切られた配列、変数、またはテキストファイルの値として入力します。</span><span class="sxs-lookup"><span data-stu-id="85b70-234">Paths are input as a comma-separated array, a variable, or values from a text file.</span></span> <span data-ttu-id="85b70-235">パイプラインの下にあるカウンターパス文字列をに送信でき `Get-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-235">You can send counter path strings down the pipeline to `Get-Counter`.</span></span>

<span data-ttu-id="85b70-236">カウンターパスは、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-236">Counter paths use the following syntax:</span></span>

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

<span data-ttu-id="85b70-237">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="85b70-237">For example:</span></span>

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

<span data-ttu-id="85b70-238">`\\ComputerName`パフォーマンスカウンターパスでは、は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="85b70-238">The `\\ComputerName` is optional in a performance counter path.</span></span> <span data-ttu-id="85b70-239">カウンターパスにコンピューター名が含まれていない場合、は `Get-Counter` ローカルコンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-239">If the counter path doesn't include the computer name, `Get-Counter` uses the local computer.</span></span>

<span data-ttu-id="85b70-240">インスタンス内のアスタリスク ( `*` ) は、カウンターのすべてのインスタンスを取得するためのワイルドカード文字です。</span><span class="sxs-lookup"><span data-stu-id="85b70-240">An asterisk (`*`) in the instance is a wildcard character to get all instances of the counter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="85b70-241">-ListSet</span><span class="sxs-lookup"><span data-stu-id="85b70-241">-ListSet</span></span>

<span data-ttu-id="85b70-242">コンピューター上のパフォーマンスカウンターセットの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="85b70-242">Lists the performance counter sets on the computers.</span></span> <span data-ttu-id="85b70-243">`*`すべてのカウンターセットを指定するには、アスタリスク () を使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-243">Use an asterisk (`*`) to specify all counter sets.</span></span> <span data-ttu-id="85b70-244">カウンターセット名を1つまたはコンマで区切った文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="85b70-244">Enter one name or a comma-separated string of counter set names.</span></span> <span data-ttu-id="85b70-245">カウンターセット名は、パイプラインの下位に送信できます。</span><span class="sxs-lookup"><span data-stu-id="85b70-245">You can send counter set names down the pipeline.</span></span>

<span data-ttu-id="85b70-246">カウンターセットの書式設定されたカウンターパスを取得するには、 **Listset** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-246">To get a counter sets formatted counter paths, use the **ListSet** parameter.</span></span> <span data-ttu-id="85b70-247">各カウンターセットの **paths** プロパティと **PathsWithInstances** プロパティには、文字列として書式設定された個々のカウンターパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="85b70-247">The **Paths** and **PathsWithInstances** properties of each counter set contain the individual counter paths formatted as a string.</span></span>

<span data-ttu-id="85b70-248">カウンターパス文字列を変数に保存することも、パイプラインを使用して別のコマンドに文字列を送信することもでき `Get-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-248">You can save the counter path strings in a variable or use the pipeline to send the string to another `Get-Counter` command.</span></span>

<span data-ttu-id="85b70-249">たとえば、各 **プロセッサ** カウンターパスをに送信するには、次のようにし `Get-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-249">For example to send each **Processor** counter path to `Get-Counter`:</span></span>

`Get-Counter -ListSet Processor | Get-Counter`

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="85b70-250">-MaxSamples</span><span class="sxs-lookup"><span data-stu-id="85b70-250">-MaxSamples</span></span>

<span data-ttu-id="85b70-251">指定された各パフォーマンスカウンターから取得するサンプルの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-251">Specifies the number of samples to get from each specified performance counter.</span></span> <span data-ttu-id="85b70-252">サンプルの定数ストリームを取得するには、 **Continuous** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-252">To get a constant stream of samples, use the **Continuous** parameter.</span></span>

<span data-ttu-id="85b70-253">**Maxsamples** パラメーターが指定されていない場合は、 `Get-Counter` 指定されたカウンターごとに1つのサンプルのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-253">If the **MaxSamples** parameter isn't specified, `Get-Counter` only gets one sample for each specified counter.</span></span>

<span data-ttu-id="85b70-254">大きなデータセットを収集するには、 `Get-Counter` PowerShell バックグラウンドジョブとしてを実行します。</span><span class="sxs-lookup"><span data-stu-id="85b70-254">To collect a large data set, run `Get-Counter` as a PowerShell background job.</span></span> <span data-ttu-id="85b70-255">詳細については、「[about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b70-255">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85b70-256">-SampleInterval</span><span class="sxs-lookup"><span data-stu-id="85b70-256">-SampleInterval</span></span>

<span data-ttu-id="85b70-257">指定された各パフォーマンスカウンターのサンプル間の秒数を指定します。</span><span class="sxs-lookup"><span data-stu-id="85b70-257">Specifies the number of seconds between samples for each specified performance counter.</span></span> <span data-ttu-id="85b70-258">**Sampleinterval** パラメーターが指定されていない場合、で `Get-Counter` は1秒間隔が使用されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-258">If the **SampleInterval** parameter isn't specified, `Get-Counter` uses a one-second interval.</span></span>

```yaml
Type: System.Int32
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85b70-259">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="85b70-259">CommonParameters</span></span>

<span data-ttu-id="85b70-260">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="85b70-260">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85b70-261">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b70-261">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85b70-262">入力</span><span class="sxs-lookup"><span data-stu-id="85b70-262">INPUTS</span></span>

### <span data-ttu-id="85b70-263">System.String[]</span><span class="sxs-lookup"><span data-stu-id="85b70-263">System.String[]</span></span>

<span data-ttu-id="85b70-264">`Get-Counter` カウンターパスとカウンターセット名のパイプライン入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="85b70-264">`Get-Counter` accepts pipeline input for counter paths and counter set names.</span></span>

## <span data-ttu-id="85b70-265">出力</span><span class="sxs-lookup"><span data-stu-id="85b70-265">OUTPUTS</span></span>

### <span data-ttu-id="85b70-266">PerformanceCounterSampleSet では、PerformanceCounterSample が、その後には、そのようになります。この場合は、このコマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="85b70-266">Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample</span></span>

<span data-ttu-id="85b70-267">オブジェクトのプロパティを表示するには、パイプラインの出力をに送信し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-267">To view an object's properties, send the output down the pipeline to `Get-Member`.</span></span> <span data-ttu-id="85b70-268">出力されるオブジェクトの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85b70-268">The object types that are output are as follows:</span></span>

<span data-ttu-id="85b70-269">**Listset** パラメーター: **Microsoft. PowerShell. Getcounter。 CounterSet**</span><span class="sxs-lookup"><span data-stu-id="85b70-269">**ListSet** parameter: **Microsoft.PowerShell.Commands.GetCounter.CounterSet**</span></span>

<span data-ttu-id="85b70-270">**カウンター** のパラメーター: **PerformanceCounterSampleSet** を実行します。</span><span class="sxs-lookup"><span data-stu-id="85b70-270">**Counter** parameter: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet**</span></span>

<span data-ttu-id="85b70-271">**Countersamples** プロパティには、 **PerformanceCounterSample** があります。</span><span class="sxs-lookup"><span data-stu-id="85b70-271">**CounterSamples** property: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample**</span></span>

## <span data-ttu-id="85b70-272">注</span><span class="sxs-lookup"><span data-stu-id="85b70-272">NOTES</span></span>

<span data-ttu-id="85b70-273">パラメーターが指定されていない場合は、 `Get-Counter` 指定されたパフォーマンスカウンターごとに1つのサンプルを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b70-273">If no parameters are specified, `Get-Counter` gets one sample for each specified performance counter.</span></span> <span data-ttu-id="85b70-274">詳細なサンプルを取得するには、 **Maxsamples** パラメーターと **Continuous** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-274">Use the **MaxSamples** and **Continuous** parameters to get more samples.</span></span>

<span data-ttu-id="85b70-275">`Get-Counter` サンプル間で1秒間隔を使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-275">`Get-Counter` uses a one-second interval between samples.</span></span> <span data-ttu-id="85b70-276">間隔を長くするには、 **sampleinterval** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85b70-276">Use the **SampleInterval** parameter to increase the interval.</span></span>

<span data-ttu-id="85b70-277">**Maxsamples** と **sampleinterval** の値は、コマンド内の各コンピューター上のすべてのカウンターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="85b70-277">The **MaxSamples** and **SampleInterval** values apply to all the counters on each computer in the command.</span></span> <span data-ttu-id="85b70-278">カウンターごとに異なる値を設定するには、個別のコマンドを入力し `Get-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="85b70-278">To set different values for different counters, enter separate `Get-Counter` commands.</span></span>

## <span data-ttu-id="85b70-279">関連リンク</span><span class="sxs-lookup"><span data-stu-id="85b70-279">RELATED LINKS</span></span>

[<span data-ttu-id="85b70-280">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="85b70-280">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="85b70-281">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="85b70-281">about_Jobs</span></span>](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[<span data-ttu-id="85b70-282">Format-List</span><span class="sxs-lookup"><span data-stu-id="85b70-282">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="85b70-283">Format-Table</span><span class="sxs-lookup"><span data-stu-id="85b70-283">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="85b70-284">Get-Member</span><span class="sxs-lookup"><span data-stu-id="85b70-284">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="85b70-285">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="85b70-285">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)

[<span data-ttu-id="85b70-286">Start-Job</span><span class="sxs-lookup"><span data-stu-id="85b70-286">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="85b70-287">Where-Object</span><span class="sxs-lookup"><span data-stu-id="85b70-287">Where-Object</span></span>](..//Microsoft.PowerShell.Core/Where-Object.md)

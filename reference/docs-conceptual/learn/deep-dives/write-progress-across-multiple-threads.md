---
title: マルチスレッド処理中の進行状況の表示
description: Foreach-Object -Parallel を用いて複数のスレッド間で Write-Progress を使用する方法
ms.date: 08/02/2020
ms.openlocfilehash: 909fc1bbdeded8845b1955e3384fb55db7173030
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "89410844"
---
# <a name="writing-progress-across-multiple-threads-with-foreach-parallel"></a><span data-ttu-id="986f2-103">Foreach Parallel を使用した複数のスレッド間での進行状況の書き込み</span><span class="sxs-lookup"><span data-stu-id="986f2-103">Writing Progress across multiple threads with Foreach Parallel</span></span>

<span data-ttu-id="986f2-104">PowerShell 7.0 以降では、[Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) コマンドレットで **Parallel** パラメーターを使用して、複数のスレッドで同時に作業できるようになります。</span><span class="sxs-lookup"><span data-stu-id="986f2-104">Starting in PowerShell 7.0, the ability to work in multiple threads simultaneously is possible using the **Parallel** parameter in the [Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) cmdlet.</span></span> <span data-ttu-id="986f2-105">ただし、これらのスレッドの進行状況を監視することは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="986f2-105">Monitoring the progress of these threads can be a challenge though.</span></span> <span data-ttu-id="986f2-106">通常は、[Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress) を使用してプロセスの進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="986f2-106">Normally, you can monitor the progress of a process using [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress).</span></span>
<span data-ttu-id="986f2-107">ただし、PowerShell では **Parallel** を使用するときにスレッドごとに個別の実行空間が使用されるため、進行状況をホストに報告することは、`Write-Progress` の通常の使用時ほど簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="986f2-107">However, since PowerShell uses a separate runspace for each thread when using **Parallel**, reporting the progress back to the host isn't as straight forward as normal use of `Write-Progress`.</span></span>

## <a name="using-a-synced-hashtable-to-track-progress"></a><span data-ttu-id="986f2-108">同期されたハッシュテーブルを使用した進行状況の追跡</span><span class="sxs-lookup"><span data-stu-id="986f2-108">Using a synced hashtable to track progress</span></span>

<span data-ttu-id="986f2-109">複数のスレッドの進行状況を書き込む場合、PowerShell で並列プロセスを実行すると、各プロセスで独自の実行空間が使用されるため、追跡が困難になります。</span><span class="sxs-lookup"><span data-stu-id="986f2-109">When writing the progress from multiple threads, tracking becomes difficult because when running parallel processes in PowerShell, each process has it's own runspace.</span></span> <span data-ttu-id="986f2-110">この問題を回避するには、[同期されたハッシュテーブル](/dotnet/api/system.collections.hashtable.synchronized)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="986f2-110">To get around this, you can use a [synchronized hashtable](/dotnet/api/system.collections.hashtable.synchronized).</span></span> <span data-ttu-id="986f2-111">同期されたハッシュテーブルは、スレッド セーフなデータ構造であり、エラーをスローすることなく複数のスレッドによって同時に変更できます。</span><span class="sxs-lookup"><span data-stu-id="986f2-111">A synced hashtable is a thread safe data structure that can be modified by multiple threads simultaneously without throwing an error.</span></span>

### <a name="set-up"></a><span data-ttu-id="986f2-112">設定</span><span class="sxs-lookup"><span data-stu-id="986f2-112">Set up</span></span>

<span data-ttu-id="986f2-113">このアプローチの欠点の 1 つは、すべてがエラーなしで確実に実行されるように、やや複雑な設定となることです。</span><span class="sxs-lookup"><span data-stu-id="986f2-113">One of the downsides to this approach is it takes a, somewhat, complex set up to ensure everything runs without error.</span></span>

```powershell
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)
```

<span data-ttu-id="986f2-114">このセクションでは、3 つの異なる目的で、3 つの異なるデータ構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="986f2-114">This section creates three different data structures, for three different purposes.</span></span>

<span data-ttu-id="986f2-115">`$dataSet` 変数には、変更されるリスクを伴わずに次の手順を調整するために使用されるハッシュテーブルの配列が格納されます。</span><span class="sxs-lookup"><span data-stu-id="986f2-115">The `$dataSet` variable stores an array of hashtables that is used to coordinate the next steps without the risk of being modified.</span></span> <span data-ttu-id="986f2-116">コレクションの反復処理中にオブジェクト コレクションが変更された場合、PowerShell によってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="986f2-116">If an object collection is modified while iterating through the collection, PowerShell throws an error.</span></span> <span data-ttu-id="986f2-117">オブジェクト コレクションは、変更対象のオブジェクトとは別のループに保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="986f2-117">You must keep the object collection in the loop separate from the objects being modified.</span></span> <span data-ttu-id="986f2-118">各ハッシュテーブルの `Id` キーは、モック プロセスの識別子です。</span><span class="sxs-lookup"><span data-stu-id="986f2-118">The `Id` key in each hashtable is the identifier for a mock process.</span></span> <span data-ttu-id="986f2-119">`Wait` キーにより、追跡されている各モック プロセスのワークロードがシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="986f2-119">The `Wait` key simulates the workload of each mock process being tracked.</span></span>

<span data-ttu-id="986f2-120">`$origin` 変数には、各キーがモック プロセス ID の 1 つである、入れ子になったハッシュテーブルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="986f2-120">The `$origin` variable stores a nested hashtable with each key being one of the mock process id's.</span></span>
<span data-ttu-id="986f2-121">次に、これは `$sync` 変数に格納されている同期済みのハッシュテーブルをハイドレートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="986f2-121">Then, it is used to hydrate the synchronized hashtable stored in the `$sync` variable.</span></span> <span data-ttu-id="986f2-122">`$sync` 変数は、進行状況が表示される親実行空間に進行状況を報告する役割を担います。</span><span class="sxs-lookup"><span data-stu-id="986f2-122">The `$sync` variable is responsible for reporting the progress back to the parent runspace, which displays the progress.</span></span>

### <a name="running-the-processes"></a><span data-ttu-id="986f2-123">プロセスの実行</span><span class="sxs-lookup"><span data-stu-id="986f2-123">Running the processes</span></span>

<span data-ttu-id="986f2-124">このセクションでは、マルチスレッド プロセスを実行し、進行状況を表示するために使用される出力の一部を作成します。</span><span class="sxs-lookup"><span data-stu-id="986f2-124">This section runs the multi-threaded processes and creates some of the output used to display progress.</span></span>

```powershell
$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}
```

<span data-ttu-id="986f2-125">モック プロセスは `Foreach-Object` に送信され、ジョブとして開始されます。</span><span class="sxs-lookup"><span data-stu-id="986f2-125">The mock processes are sent to `Foreach-Object` and started as jobs.</span></span> <span data-ttu-id="986f2-126">**ThrottleLimit** は **3** に設定されて、キュー内の複数のプロセスの実行が強調されます。</span><span class="sxs-lookup"><span data-stu-id="986f2-126">The **ThrottleLimit** is set to **3** to highlight running multiple processes in a queue.</span></span> <span data-ttu-id="986f2-127">ジョブは `$job` 変数に格納され、これにより、後ですべてのプロセスが完了したときに知ることができます。</span><span class="sxs-lookup"><span data-stu-id="986f2-127">The jobs are stored in the `$job` variable and allows us to know when all the processes have finished later on.</span></span>

<span data-ttu-id="986f2-128">`using:` ステートメントを使用して PowerShell で親スコープ変数を参照する場合、式を使用してこれを動的にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="986f2-128">When using the `using:` statement to reference a parent scope variable in PowerShell, you can't use expressions to make it dynamic.</span></span> <span data-ttu-id="986f2-129">たとえば、`$process = $using:sync.$($PSItem.id)` のような `$process` 変数を作成しようとすると、ここで式を使用できないことを示すエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="986f2-129">For example, if you tried to create the `$process` variable like this, `$process = $using:sync.$($PSItem.id)`, you would get an error stating you can't use expressions there.</span></span> <span data-ttu-id="986f2-130">そのため、エラーが表示されることなく `$sync` 変数を参照および変更できるように、`$syncCopy` 変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="986f2-130">So, we create the `$syncCopy` variable to be able to reference and modify the `$sync` variable without the risk of it failing.</span></span>

<span data-ttu-id="986f2-131">次に、同期されたハッシュテーブル キーを参照することで、`$process` 変数を使用して現在ループ内にあるプロセスの進行状況を表すハッシュテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="986f2-131">Next, we build out a hashtable to represent the progress of the process currently in the loop using the `$process` variable by referencing the synchronized hashtable keys.</span></span> <span data-ttu-id="986f2-132">**Activity** および **Status** キーは、次のセクションで特定のモック プロセスの状態を表示するために `Write-Progress` のパラメーター値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="986f2-132">The **Activity** and the **Status** keys are used as parameter values for `Write-Progress` to display the status of a given mock process in the next section.</span></span>

<span data-ttu-id="986f2-133">`foreach` ループは、プロセスの動作をシミュレートする 1 つの方法であり、`$dataSet` **Wait** 属性に基づいてランダム化され、ミリ秒を使用して `Start-Sleep` が設定されます。</span><span class="sxs-lookup"><span data-stu-id="986f2-133">The `foreach` loop is just a way to simulate the process working and is randomized based on the `$dataSet` **Wait** attribute to set `Start-Sleep` using milliseconds.</span></span> <span data-ttu-id="986f2-134">プロセスの進行状況を計算する方法は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="986f2-134">How you calculate the progress of your process may vary.</span></span>

### <a name="displaying-the-progress-of-multiple-processes"></a><span data-ttu-id="986f2-135">複数のプロセスの進行状況の表示</span><span class="sxs-lookup"><span data-stu-id="986f2-135">Displaying the progress of multiple processes</span></span>

<span data-ttu-id="986f2-136">これで、モック プロセスがジョブとして実行されるようになったので、プロセスの進行状況を PowerShell ウィンドウに書き込み始めることができます。</span><span class="sxs-lookup"><span data-stu-id="986f2-136">Now that the mock processes are running as jobs, we can start to write the processes progress to the PowerShell window.</span></span>

```powershell
while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

<span data-ttu-id="986f2-137">`$job` 変数には親 **ジョブ** が含まれており、モック プロセスごとに子 **ジョブ** が存在します。</span><span class="sxs-lookup"><span data-stu-id="986f2-137">The `$job` variable contains the parent **job** and has a child **job** for each of the mock processes.</span></span> <span data-ttu-id="986f2-138">子ジョブがまだ実行されている間、親ジョブの **State** は "Running" のままになります。</span><span class="sxs-lookup"><span data-stu-id="986f2-138">While any of the child jobs are still running, the parent job **State** will remain "Running".</span></span> <span data-ttu-id="986f2-139">これにより、すべてのプロセスが完了するまで、`while` ループを使用してすべてのプロセスの進行状況を継続的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="986f2-139">This allows us to use the `while` loop to continually update the progress of every process until all processes are finished.</span></span>

<span data-ttu-id="986f2-140">while ループ内で、`$sync` 変数内の各キーをループ処理します。</span><span class="sxs-lookup"><span data-stu-id="986f2-140">Within the while loop, we loop through each of the keys in the `$sync` variable.</span></span> <span data-ttu-id="986f2-141">これは同期されたハッシュテーブルであるため、常に更新されますが、依然としてエラーがスローされることなくアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="986f2-141">Since this is a synchronized hashtable, it is constantly updated but can still be accessed without throwing any errors.</span></span>

<span data-ttu-id="986f2-142">報告されるプロセスが `IsNullOrEmpty()` メソッドを使用して実際に実行されていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="986f2-142">There is a check to ensure that the process being reported is actually running using the `IsNullOrEmpty()` method.</span></span> <span data-ttu-id="986f2-143">プロセスが開始されていない場合、ループではそれが報告されず、開始されたプロセスに達するまで次のプロセスに移動します。</span><span class="sxs-lookup"><span data-stu-id="986f2-143">If the process hasn't been started, the loop won't report on it and move on to the next until it gets to a process that has been started.</span></span> <span data-ttu-id="986f2-144">プロセスが開始されている場合は、現在のキーのハッシュテーブルを使用して、パラメーターが `Write-Progress` にスプラッティングされます。</span><span class="sxs-lookup"><span data-stu-id="986f2-144">If the process is started, the hashtable from the current key is used to splat the parameters to `Write-Progress`.</span></span>

### <a name="full-example"></a><span data-ttu-id="986f2-145">完全な例</span><span class="sxs-lookup"><span data-stu-id="986f2-145">Full example</span></span>

```powershell
# Example workload
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)

$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}

while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

## <a name="related-links"></a><span data-ttu-id="986f2-146">関連リンク</span><span class="sxs-lookup"><span data-stu-id="986f2-146">Related Links</span></span>

- [<span data-ttu-id="986f2-147">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="986f2-147">about_Jobs</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Jobs)
- [<span data-ttu-id="986f2-148">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="986f2-148">about_Scopes</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Scopes)
- [<span data-ttu-id="986f2-149">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="986f2-149">about_Splatting</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Splatting)

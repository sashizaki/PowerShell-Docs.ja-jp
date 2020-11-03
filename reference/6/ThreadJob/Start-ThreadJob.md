---
external help file: ThreadJob.dll-Help.xml
Locale: en-US
Module Name: ThreadJob
ms.date: 01/28/2020
online version: https://docs.microsoft.com/powershell/module/threadjob/start-threadjob?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ThreadJob
ms.openlocfilehash: debe4002ec4d7ba7651f739316c4127243d8ebd3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216496"
---
# <span data-ttu-id="d7e40-102">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="d7e40-102">Start-ThreadJob</span></span>

## <span data-ttu-id="d7e40-103">概要</span><span class="sxs-lookup"><span data-stu-id="d7e40-103">SYNOPSIS</span></span>
<span data-ttu-id="d7e40-104">コマンドレットに似たバックグラウンドジョブを作成し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-104">Creates background jobs similar to the `Start-Job` cmdlet.</span></span>

## <span data-ttu-id="d7e40-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d7e40-105">SYNTAX</span></span>

### <span data-ttu-id="d7e40-106">スクリプト ブロック</span><span class="sxs-lookup"><span data-stu-id="d7e40-106">ScriptBlock</span></span>

```
Start-ThreadJob [-ScriptBlock] <ScriptBlock> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d7e40-107">FilePath</span><span class="sxs-lookup"><span data-stu-id="d7e40-107">FilePath</span></span>

```
Start-ThreadJob [-FilePath] <String> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="d7e40-108">Description</span><span class="sxs-lookup"><span data-stu-id="d7e40-108">DESCRIPTION</span></span>

<span data-ttu-id="d7e40-109">`Start-ThreadJob` コマンドレットに似たバックグラウンドジョブを作成し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-109">`Start-ThreadJob` creates background jobs similar to the `Start-Job` cmdlet.</span></span> <span data-ttu-id="d7e40-110">主な違いは、作成されるジョブはローカルプロセス内の別々のスレッドで実行されるという点です。</span><span class="sxs-lookup"><span data-stu-id="d7e40-110">The main difference is that the jobs which are created run in separate threads within the local process.</span></span> <span data-ttu-id="d7e40-111">既定では、ジョブはジョブを開始した呼び出し元の現在の作業ディレクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-111">By default, the jobs use the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="d7e40-112">コマンドレットでは、同時に実行されるジョブの数を制限する **ThrottleLimit** パラメーターもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d7e40-112">The cmdlet also supports a **ThrottleLimit** parameter to limit the number of jobs running at one time.</span></span> <span data-ttu-id="d7e40-113">ジョブが開始されると、キューに登録され、現在のジョブ数がスロットル制限を下回るまで待機します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-113">As more jobs are started, they are queued and wait until the current number of jobs drops below the throttle limit.</span></span>

## <span data-ttu-id="d7e40-114">例</span><span class="sxs-lookup"><span data-stu-id="d7e40-114">EXAMPLES</span></span>

### <span data-ttu-id="d7e40-115">例 1-スレッドの制限が2のバックグラウンドジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="d7e40-115">Example 1 - Create background jobs with a thread limit of 2</span></span>

```powershell
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } } -ThrottleLimit 2
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Get-Job
```

```Output
Id   Name   PSJobTypeName   State        HasMoreData   Location     Command
--   ----   -------------   -----        -----------   --------     -------
1    Job1   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
2    Job2   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
3    Job3   ThreadJob       NotStarted   False         PowerShell   1..100 | % { sleep 1;...
```

### <span data-ttu-id="d7e40-116">例 2-Start-Job と Start-ThreadJob のパフォーマンスを比較する</span><span class="sxs-lookup"><span data-stu-id="d7e40-116">Example 2 - Compare the performance of Start-Job and Start-ThreadJob</span></span>

<span data-ttu-id="d7e40-117">この例は、との違いを示して `Start-Job` `Start-ThreadJob` います。</span><span class="sxs-lookup"><span data-stu-id="d7e40-117">This example shows the difference between `Start-Job` and `Start-ThreadJob`.</span></span> <span data-ttu-id="d7e40-118">このコマンドレットは、ジョブによって `Start-Sleep` 1 秒間実行されます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-118">The jobs run the `Start-Sleep` cmdlet for 1 second.</span></span> <span data-ttu-id="d7e40-119">ジョブは並行して実行されるため、合計実行時間は約1秒で、ジョブの作成に必要な時間もあります。</span><span class="sxs-lookup"><span data-stu-id="d7e40-119">Since the jobs run in parallel, the total execution time is about 1 second, plus any time required to create the jobs.</span></span>

```powershell
# start five background jobs each running 1 second
Measure-Command {1..5 | % {Start-Job {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
Measure-Command {1..5 | % {Start-ThreadJob {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
```

```Output
TotalSeconds
------------
   5.7665849
   1.5735008
```

<span data-ttu-id="d7e40-120">実行時間が1秒を引いた後は、 `Start-Job` 5 つのジョブを作成するのに約4.8 秒かかることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d7e40-120">After subtracting 1 second for execution time, you can see that `Start-Job` takes about 4.8 seconds to create five jobs.</span></span> <span data-ttu-id="d7e40-121">`Start-ThreadJob` は8倍高速です。5つのジョブを作成するには約0.6 秒かかります。</span><span class="sxs-lookup"><span data-stu-id="d7e40-121">`Start-ThreadJob` is 8 times faster, taking about 0.6 seconds to create five jobs.</span></span> <span data-ttu-id="d7e40-122">結果は環境によって異なる場合がありますが、相対的な改善は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e40-122">The results may vary in your environment but the relative improvement should be the same.</span></span>

### <span data-ttu-id="d7e40-123">例 3-InputObject を使用してジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="d7e40-123">Example 3 - Create jobs using InputObject</span></span>

<span data-ttu-id="d7e40-124">この例では、スクリプトブロックは変数を使用して `$input` **InputObject** パラメーターから入力を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d7e40-124">In this example, the script block uses the `$input` variable to receive input from the **InputObject** parameter.</span></span> <span data-ttu-id="d7e40-125">これは、オブジェクトをにパイプ処理することによっても実行でき `Start-ThreadJob` ます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-125">This can also be done by piping objects to `Start-ThreadJob`.</span></span>

```powershell
$j = Start-ThreadJob -InputObject (Get-Process pwsh) -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

```powershell
$j = Get-Process pwsh | Start-ThreadJob -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

## <span data-ttu-id="d7e40-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d7e40-126">PARAMETERS</span></span>

### <span data-ttu-id="d7e40-127">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="d7e40-127">-ArgumentList</span></span>

<span data-ttu-id="d7e40-128">**FilePath** または **ScriptBlock** パラメーターで指定されたスクリプトの引数の配列、またはパラメーター値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-128">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** or **ScriptBlock** parameters.</span></span>

<span data-ttu-id="d7e40-129">**ArgumentList** は、コマンドラインの最後のパラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e40-129">**ArgumentList** must be the last parameter on the command line.</span></span> <span data-ttu-id="d7e40-130">パラメーター名の後に続くすべての値は、引数リスト内の値として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-130">All the values that follow the parameter name are interpreted values in the argument list.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d7e40-131">-FilePath</span><span class="sxs-lookup"><span data-stu-id="d7e40-131">-FilePath</span></span>

<span data-ttu-id="d7e40-132">バックグラウンドジョブとして実行するスクリプトファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-132">Specifies a script file to run as a background job.</span></span> <span data-ttu-id="d7e40-133">スクリプトのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-133">Enter the path and filename of the script.</span></span> <span data-ttu-id="d7e40-134">スクリプトは、ローカルコンピューター上、またはローカルコンピューターがアクセスできるフォルダー内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7e40-134">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="d7e40-135">このパラメーターを使用すると、PowerShell によって、指定したスクリプトファイルの内容がスクリプトブロックに変換され、バックグラウンドジョブとしてスクリプトブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-135">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d7e40-136">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="d7e40-136">-InitializationScript</span></span>

<span data-ttu-id="d7e40-137">ジョブの開始前に実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-137">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="d7e40-138">コマンドを中かっこ () で囲み、 `{}` スクリプトブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-138">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="d7e40-139">このパラメーターは、ジョブを実行するセッションを準備するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-139">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="d7e40-140">たとえば、このメソッドを使用して、関数とモジュールをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-140">For example, you can use it to add functions and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d7e40-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d7e40-141">-InputObject</span></span>

<span data-ttu-id="d7e40-142">スクリプトブロックへの入力として使用されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-142">Specifies the objects used as input to the script block.</span></span> <span data-ttu-id="d7e40-143">また、パイプラインを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-143">It also allows for pipeline input.</span></span> <span data-ttu-id="d7e40-144">`$input`入力オブジェクトにアクセスするには、スクリプトブロックで自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-144">Use the `$input` automatic variable in the script block to access the input objects.</span></span>

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

### <span data-ttu-id="d7e40-145">-Name</span><span class="sxs-lookup"><span data-stu-id="d7e40-145">-Name</span></span>

<span data-ttu-id="d7e40-146">新しいジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-146">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="d7e40-147">この名前を使用して、コマンドレットなど、他のジョブコマンドレットに対してジョブを識別でき `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-147">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="d7e40-148">既定のフレンドリ名は "Job #" です。ここで、"#" は、ジョブごとに増加する序数です。</span><span class="sxs-lookup"><span data-stu-id="d7e40-148">The default friendly name is "Job#", where "#" is an ordinal number that is incremented for each job.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d7e40-149">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="d7e40-149">-ScriptBlock</span></span>

<span data-ttu-id="d7e40-150">バックグラウンド ジョブで実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-150">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="d7e40-151">コマンドを中かっこ () で囲み、 `{}` スクリプトブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-151">Enclose the commands in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="d7e40-152">`$Input` **InputObject** パラメーターの値にアクセスするには、自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-152">Use the `$Input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="d7e40-153">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="d7e40-153">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d7e40-154">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d7e40-154">-ThrottleLimit</span></span>

<span data-ttu-id="d7e40-155">このパラメーターは、一度に実行されるジョブの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-155">This parameter limits the number of jobs running at one time.</span></span> <span data-ttu-id="d7e40-156">ジョブが開始されると、キューに入れられ、スレッドプールでスレッドを使用してジョブを実行できるようになるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="d7e40-156">As jobs are started, they are queued and wait until a thread is available in the thread pool to run the job.</span></span> <span data-ttu-id="d7e40-157">既定の制限は5スレッドです。</span><span class="sxs-lookup"><span data-stu-id="d7e40-157">The default limit is 5 threads.</span></span>

<span data-ttu-id="d7e40-158">スレッドプールのサイズは、PowerShell セッションに対してグローバルです。</span><span class="sxs-lookup"><span data-stu-id="d7e40-158">The thread pool size is global to the PowerShell session.</span></span> <span data-ttu-id="d7e40-159">1回の呼び出しで **ThrottleLimit** を指定すると、同じセッション内の後続の呼び出しの制限が設定されます。</span><span class="sxs-lookup"><span data-stu-id="d7e40-159">Specifying a **ThrottleLimit** in one call sets the limit for subsequent calls in the same session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d7e40-160">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7e40-160">CommonParameters</span></span>

<span data-ttu-id="d7e40-161">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d7e40-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d7e40-162">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e40-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d7e40-163">入力</span><span class="sxs-lookup"><span data-stu-id="d7e40-163">INPUTS</span></span>

### <span data-ttu-id="d7e40-164">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="d7e40-164">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="d7e40-165">出力</span><span class="sxs-lookup"><span data-stu-id="d7e40-165">OUTPUTS</span></span>

### <span data-ttu-id="d7e40-166">ThreadJob。 ThreadJob</span><span class="sxs-lookup"><span data-stu-id="d7e40-166">ThreadJob.ThreadJob</span></span>

## <span data-ttu-id="d7e40-167">注</span><span class="sxs-lookup"><span data-stu-id="d7e40-167">NOTES</span></span>

## <span data-ttu-id="d7e40-168">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d7e40-168">RELATED LINKS</span></span>

[<span data-ttu-id="d7e40-169">Start-Job</span><span class="sxs-lookup"><span data-stu-id="d7e40-169">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="d7e40-170">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="d7e40-170">Stop-Job</span></span>](../Microsoft.PowerShell.Core/Stop-Job.md)

[<span data-ttu-id="d7e40-171">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="d7e40-171">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)

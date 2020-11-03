---
description: PowerShell スレッドベースのジョブに関する情報を提供します。 スレッドジョブは、現在のセッションプロセス内の別のスレッドでコマンドまたは式を実行するバックグラウンドジョブの一種です。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 973d0ddf18b63cd7462817cf68f7c5d7466f4724
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224643"
---
# <a name="about-thread-jobs"></a>スレッドジョブについて

## <a name="short-description"></a>簡単な説明

PowerShell スレッドベースのジョブに関する情報を提供します。 スレッドジョブは、現在のセッションプロセス内の別のスレッドでコマンドまたは式を実行するバックグラウンドジョブの一種です。

## <a name="long-description"></a>長い説明

この記事では、ローカルコンピューター上の PowerShell でスレッドジョブを実行する方法について説明します。
ローカルコンピューターでのバックグラウンドジョブの実行の詳細については、「 [about_Jobs](about_Jobs.md)」を参照してください。

コマンドレットを使用して、スレッドジョブを開始し `Start-ThreadJob` ます。 このコマンドレットは、PowerShell に付属している **Threadjob** モジュールで使用できます。
`Start-ThreadJob` 実行中のコマンドまたはスクリプトをカプセル化し、コマンドレットを操作するすべての PowerShell ジョブで使用できる単一のジョブオブジェクトを返します。

## <a name="the-job-cmdlets"></a>ジョブのコマンドレット

|コマンドレット           |説明                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|ローカルコンピューター上でスレッドジョブを開始します。               |
|`Get-Job`        |現在のセッションで開始されたジョブを取得します。|
|`Receive-Job`    |ジョブの結果を取得します。                              |
|`Stop-Job`       |実行中のジョブを停止します。                                   |
|`Wait-Job`       |1つまたはすべてのジョブが完了するまで、コマンドプロンプトを表示しません。|
|                 |完了.                                              |
|`Remove-Job`     |ジョブを削除します。                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a>ローカルコンピューターでスレッドジョブを開始する方法

ローカルコンピューターでスレッドジョブを開始するには、コマンドレットを使用し `Start-ThreadJob` ます。

コマンドを記述するに `Start-ThreadJob` は、コマンドを囲むか、ジョブの実行を中かっこ () で囲み `{ }` ます。

次のコマンドは、 `Get-Process` ローカルコンピューター上でコマンドを実行するスレッドジョブを開始します。

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

コマンドは、 `Start-ThreadJob` `ThreadJob` 実行中のジョブを表すオブジェクトを返します。 Job オブジェクトには、現在実行中の状態を含む、ジョブに関する有用な情報が含まれています。 結果が生成されると、ジョブの結果が収集されます。

コマンドを記述するには `ForEach-Object -Parallel` 、パイプでデータをコマンドに渡し、コマンドまたはスクリプトを囲みます。ジョブは中かっこ () で実行し `{}` ます。 パラメータースイッチを使用し `-AsJob` て、ジョブオブジェクトが返されるようにします。

次のコマンドは、コマンドにパイプを使用して、各入力値の子ジョブを含むジョブを開始します。 各子ジョブは、 `Write-Output` パイプを使用した入力値を引数としてコマンドを実行します。

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

このコマンドは、パイプ処理された `ForEach-Object -Parallel` `PSTaskJob` 各入力値の子ジョブを含むオブジェクトを返します。 Job オブジェクトには、実行状態の子ジョブに関する有用な情報が含まれています。 結果が生成されるときに子ジョブの結果を収集します。

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a>ジョブの完了を待機してジョブの結果を取得する方法

やなどの PowerShell ジョブコマンドレットを使用して、 `Wait-Job` `Receive-Job` ジョブが完了するのを待ってから、ジョブによって生成されたすべての結果を返すことができます。

次のコマンドは、コマンドを実行するスレッドジョブを開始し、 `Get-Process` コマンドが完了するまで待機します。最後に、コマンドによって生成されたすべてのデータ結果を返します。

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

次のコマンドは、パイプ処理された `Write-Output` 各入力に対してコマンドを実行し、すべての子ジョブが完了するまで待機して、最後に子ジョブによって生成されるすべてのデータ結果を返すジョブを開始します。

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

`Receive-Job`コマンドレットは、子ジョブの結果を返します。

```powershell
1
3
2
4
5
```

各子ジョブは並行して実行されるため、生成される結果の順序は保証されません。

## <a name="powershell-concurrency-and-jobs"></a>PowerShell の同時実行とジョブ

PowerShell では、コマンドを同時に実行してジョブをスクリプト化します。 同時実行をサポートするために PowerShell によって提供される3つのジョブベースのソリューションがあります。

|ジョブ            |説明                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |コマンドとスクリプトをリモートコンピューターで実行します。                 |
|`BackgroundJob`|コマンドとスクリプトがローカルの別のプロセスで実行される    |
|               |割り当てます。                                                     |
|`ThreadJob`    |コマンドとスクリプトが同じ内の別のスレッドで実行される  |
|               |ローカルコンピューターでプロセスを実行します。                                |

各種類のジョブには、利点と欠点があります。 別のコンピューターまたは別のプロセスでスクリプトをリモートで実行すると、優れた分離ができます。 エラーが発生しても、他の実行中のジョブや、ジョブを開始したクライアントには影響しません。 ただし、リモート処理層では、オブジェクトのシリアル化などのオーバーヘッドが発生します。 リモートセッションとの間でやり取りされるすべてのオブジェクトをシリアル化してから、クライアントとターゲットセッション間でやり取りするときに逆シリアル化する必要があります。 シリアル化操作では、大規模な複雑なデータオブジェクトに対して多くのコンピューティングリソースとメモリリソースを使用できます。

## <a name="powershell-thread-based-jobs"></a>PowerShell スレッドベースのジョブ

スレッドベースのジョブは、異なるスレッドで同じプロセスで実行されるため、リモートジョブやバックグラウンドジョブほど堅牢ではありません。 あるジョブで、プロセスをクラッシュさせる重大なエラーが発生している場合は、プロセス内の他のすべてのジョブも失敗します。

ただし、スレッドベースのジョブのオーバーヘッドはかなり少なくなります。 リモート処理レイヤーまたはシリアル化を使用する必要はありません。 その結果、スレッドベースのジョブの実行速度が大幅に向上し、他の種類のジョブよりもはるかに少ないリソースが使用されます。

## <a name="thread-job-performance"></a>スレッドジョブのパフォーマンス

スレッドジョブは、他の種類のジョブよりも高速で軽量です。 ただし、ジョブが行っている作業と比べると、大きなオーバーヘッドが発生する可能性があります。

PowerShell は、セッションでコマンドとスクリプトを実行します。 セッションで一度に実行できるコマンドまたはスクリプトは1つだけです。 そのため、複数のジョブを実行する場合、各ジョブは個別のセッションで実行されます。 各セッションは、オーバーヘッドに寄与します。

スレッドジョブは、実行する作業がジョブの実行に使用されるセッションのオーバーヘッドよりも大きい場合に最適なパフォーマンスを提供します。 この条件を満たすには、2つのケースがあります。

- 作業は多くのコンピューティング処理を必要とします。複数のスレッドジョブでスクリプトを実行すると、複数のプロセッサコアを利用し、より高速に完了できます。

- 作業は、i/o またはリモート呼び出しの結果を待機する時間を費やすスクリプトで構成されています。 並列実行は通常、連続して実行した場合よりも短時間で完了します。

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
10457.962


(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
24.9277
```

上の最初の例は、単純な文字列の書き込みを行うために1000のスレッドジョブを作成する foreach ループを示しています。 ジョブのオーバーヘッドが原因で、完了までに33秒以上かかります。

2番目の例では、 `ForEach` コマンドレットを実行して同じ1000操作を実行します。また、各文字列の書き込みは、ジョブのオーバーヘッドなしで順番に実行されます。 わずか25ミリ秒で完了します。

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach {
        Start-ThreadJob {
            Get-WinEvent -LogName $using:_ -MaxEvents 5000 2>$null
        } -ThrottleLimit 10
    } | Wait-Job | Receive-Job
}

TotalMilliseconds : 115994.3 (1 minute 56 seconds)
$logs.Count
50000
```

上の例では、10個の個別のシステムログに対して最大5000のエントリが収集されます。 このスクリプトには多数のログが含まれているため、操作を並行して実行するのが理にかなっています。 また、ジョブは、スクリプトが順番に実行されるのと同じ速さで完了します。

```powershell
Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a>スレッドジョブと変数

変数は、さまざまな方法でスレッドジョブに渡されます。

`Start-ThreadJob`は、コマンドレットにパイプ処理されるか、キーワードを使用してスクリプトブロックに渡されるか、ArgumentList パラメーターを介して渡される変数を受け入れることができ `$using` ます。 **ArgumentList**

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job

`ForEach-Object -Parallel` accepts piped in variables, and variables passed
directly to the script block via the `$using` keyword.

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

スレッドジョブは同じプロセスで実行されるため、ジョブに渡される変数参照型は慎重に扱う必要があります。 スレッドセーフなオブジェクトでない場合は、に割り当てられないようにし、メソッドとプロパティを呼び出さないようにする必要があります。

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
$jobs = Get-Process | ForEach {
    Start-ThreadJob {
        $proc = $using:_
        $dict = $using:threadSafeDictionary
        $dict.TryAdd($proc.ProcessName, $proc)
    }
}
$jobs | Wait-Job | Receive-Job

$threadSafeDictionary.Count
96

$threadSafeDictionary["pwsh"]

NPM(K)  PM(M)   WS(M) CPU(s)    Id SI ProcessName
------  -----   ----- ------    -- -- -----------
  112  108.25  124.43  69.75 16272  1 pwsh
```

上の例では、スレッドセーフな dotNet `ConcurrentDictionary` オブジェクトをすべての子ジョブに渡して、一意の名前を付けた process オブジェクトを収集します。 スレッドセーフなオブジェクトであるため、ジョブがプロセス内で同時に実行されている間に安全に使用できます。

## <a name="see-also"></a>関連項目

- [about_Remote_Jobs](about_Remote_Jobs.md)
- [about_Thread_Jobs](about_Thread_Jobs.md)
- [about_Job_Details](about_Job_Details.md)
- [about_Remote](about_Remote.md)
- [about_PSSessions](about_PSSessions.md)
- [Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)
- [Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)
- [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job)
- [Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)
- [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)
- [Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)

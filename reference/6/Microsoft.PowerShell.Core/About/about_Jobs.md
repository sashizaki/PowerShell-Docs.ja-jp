---
description: PowerShell バックグラウンドジョブが、現在のセッションと対話せずにバックグラウンドでコマンドまたは式を実行する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: 6668e8a060c2468a4c7d98f52c7d493e1751970b
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224571"
---
# <a name="about-jobs"></a>ジョブについて

## <a name="short-description"></a>簡単な説明
PowerShell バックグラウンドジョブが、現在のセッションと対話せずにバックグラウンドでコマンドまたは式を実行する方法について説明します。

## <a name="long-description"></a>長い説明

PowerShell では、コマンドを同時に実行してジョブをスクリプト化します。 同時実行をサポートするために PowerShell によって提供される3つのジョブベースのソリューションがあります。

|ジョブ            |説明                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |コマンドとスクリプトをリモートコンピューターで実行します。                 |
|`BackgroundJob`|コマンドとスクリプトがローカルの別のプロセスで実行される    |
|               |割り当てます。                                                     |
|`ThreadJob`    |コマンドとスクリプトが同じ内の別のスレッドで実行される  |
|               |ローカルコンピューターでプロセスを実行します。                                |

各種類のジョブには、利点と欠点があります。 別のコンピューターまたは別のプロセスでスクリプトをリモートで実行すると、優れた分離ができます。 エラーが発生しても、他の実行中のジョブや、ジョブを開始したクライアントには影響しません。 ただし、リモート処理層では、オブジェクトのシリアル化などのオーバーヘッドが発生します。 リモートセッションとの間でやり取りされるすべてのオブジェクトをシリアル化してから、クライアントとターゲットセッション間でやり取りするときに逆シリアル化する必要があります。 シリアル化操作では、大規模な複雑なデータオブジェクトに対して多くのコンピューティングリソースとメモリリソースを使用できます。

このトピックでは、ローカルコンピューター上の PowerShell でバックグラウンドジョブを実行する方法について説明します。 リモートコンピューターでバックグラウンドジョブを実行する方法の詳細については、「 [about_Remote_Jobs](about_Remote_Jobs.md)」を参照してください。 スレッドジョブの詳細については、「 [about_Thread_Jobs](about_Thread_Jobs.md)」を参照してください。

バックグラウンドジョブを開始すると、ジョブが完了するまでに時間がかかる場合でも、コマンドプロンプトがすぐに返されます。 ジョブの実行中は、中断されることなく引き続きセッションで作業できます。

## <a name="the-job-cmdlets"></a>ジョブのコマンドレット

|コマンドレット          |説明                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |ローカルコンピューターでバックグラウンドジョブを開始します。           |
|`Get-Job`       |で開始されたバックグラウンドジョブを取得します。      |
|                |現在のセッション。                                       |
|`Receive-Job`   |バックグラウンドジョブの結果を取得します。                   |
|`Stop-Job`      |バックグラウンドジョブを停止します。                                |
|`Wait-Job`      |1つまたはすべてのジョブが完了するまで、コマンドプロンプトを表示しません。|
|                |完了.                                              |
|`Remove-Job`    |バックグラウンドジョブを削除します。                              |
|`Invoke-Command`|**AsJob** パラメーターは、に対してバックグラウンドジョブを作成します。  |
|                |リモートコンピューター。 を使用して、 `Invoke-Command`   |
|                |を含め、任意のジョブコマンドをリモートで実行 `Start-Job` します。       |

## <a name="how-to-start-a-job-on-the-local-computer"></a>ローカルコンピューターでジョブを開始する方法

ローカルコンピューターでバックグラウンドジョブを開始するには、コマンドレットを使用し `Start-Job` ます。

コマンドを記述するには、 `Start-Job` ジョブを実行するコマンドを中かっこ ( `{}` ) で囲みます。 **ScriptBlock** パラメーターを使用して、コマンドを指定します。

次のコマンドは、ローカルコンピューターでコマンドを実行するバックグラウンドジョブを開始し `Get-Process` ます。

```powershell
Start-Job -ScriptBlock {Get-Process}
```

この `Start-Job` コマンドは、ジョブを表すオブジェクトを返します。 ジョブ オブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれません。

ジョブオブジェクトを変数に保存し、他のジョブコマンドレットと共に使用してバックグラウンドジョブを管理します。 次のコマンドは、ジョブオブジェクトを開始し、結果として生成されたジョブオブジェクトを変数に保存し `$job` ます。

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

PowerShell 6.0 以降では、 `&` パイプラインの最後で amersand () を使用してバックグラウンドジョブを開始できます。 次のコマンドは、機能的には上記のコマンドと同等です。

```powershell
$job = Get-Process &
```

アンパサンド ( `&` ) は、background 演算子と呼ばれます。 詳細については、「 [background operator](about_Operators.md#background-operator-)」を参照してください。

また、コマンドレットを使用して、 `Get-Job` 現在のセッションで開始されたジョブを表すオブジェクトを取得することもできます。 `Get-Job` を返す同じジョブオブジェクトを返し `Start-Job` ます。

## <a name="getting-job-objects"></a>ジョブオブジェクトの取得

現在のセッションで開始されたバックグラウンドジョブを表すオブジェクトを取得するには、コマンドレットを使用し `Get-Job` ます。 パラメーターを指定しない場合は、 `Get-Job` 現在のセッションで開始されたすべてのジョブが返されます。

たとえば、次のコマンドは、現在のセッションのジョブを取得します。

```powershell
PS C:> Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Running    True         localhost  Get-Process
```

また、ジョブオブジェクトを変数に保存し、後のコマンドでジョブを表すために使用することもできます。 次のコマンドは、ID が1のジョブを取得し、変数に保存し `$job` ます。

```powershell
$job = Get-Job -Id 1
```

ジョブオブジェクトには、ジョブが完了したかどうかを示すジョブの状態が含まれています。 完了したジョブの状態が " **完了** " または " **失敗** " になっています。 ジョブも **ブロック** されているか、実行され **ている** 可能性があります。

```powershell
Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

## <a name="getting-the-results-of-a-job"></a>ジョブの結果を取得する

バックグラウンドジョブを実行しても、結果はすぐには表示されません。 代わりに、 `Start-Job` コマンドレットはジョブを表すジョブオブジェクトを返しますが、結果は含まれません。 バックグラウンドジョブの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。

次のコマンドでは、 `Receive-Job` コマンドレットを使用してジョブの結果を取得します。 変数に保存されているジョブオブジェクトを使用して `$job` 、ジョブを識別します。

```powershell
Receive-Job -Job $job
```

`Receive-Job`コマンドレットは、ジョブの結果を返します。

```
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
# ...
```

ジョブの結果を変数に保存することもできます。 次のコマンドは、変数内のジョブの結果を `$job` 変数に保存し `$results` ます。

```powershell
$results = Receive-Job -Job $job
```

また、リダイレクト演算子 ( `>` ) またはコマンドレットを使用して、ジョブの結果をファイルに保存することもでき `Out-File` ます。 次のコマンドは、リダイレクト演算子を使用して、ジョブの結果を `$job` ファイル内の変数に保存し `Results.txt` ます。

```powershell
Receive-Job -Job $job > results.txt
```

## <a name="getting-and-keeping-partial-job-results"></a>部分的なジョブ結果の取得と保持

コマンドレットでは、 `Receive-Job` バックグラウンドジョブの結果を取得します。 ジョブが完了すると、は `Receive-Job` すべてのジョブの結果を取得します。 ジョブがまだ実行中の場合は、 `Receive-Job` これまでに生成された結果を取得します。 `Receive-Job`コマンドをもう一度実行して、残りの結果を取得することができます。

`Receive-Job`が結果を返す場合、既定では、ジョブの結果が格納されているキャッシュから結果が削除されます。 別のコマンドを実行すると `Receive-Job` 、まだ受け取っていない結果だけが取得されます。

次のコマンドは、 `Receive-Job` ジョブが完了する前に実行されたコマンドの結果を示しています。

```powershell
C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    68       3     2632        664    29     0.36   1388 ccmsetup
   749      22    21468      19940   203   122.13   3644 communicator
   905       7     2980       2628    34   197.97    424 csrss
  1121      25    28408      32940   174   430.14   3048 explorer
```

によって返されたジョブの結果が削除されないようにするには `Receive-Job` 、 **Keep** パラメーターを使用します。 その結果、は、 `Receive-Job` その時点までに生成されたすべての結果を返します。

次のコマンドは、まだ完了していないジョブで **Keep** パラメーターを使用した場合の影響を示しています。

```powershell
C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec
     68       3     2632        664    29     0.36   1388 ccmsetup
    749      22    21468      19940   203   122.13   3644 communicator
    905       7     2980       2628    34   197.97    424 csrss
   1121      25    28408      32940   174   430.14   3048 explorer
```

## <a name="waiting-for-the-results"></a>結果を待機しています

完了までに時間がかかるコマンドを実行する場合は、ジョブオブジェクトのプロパティを使用して、ジョブがいつ完了したかを判断できます。 次のコマンドでは、オブジェクトを使用して、 `Get-Job` 現在のセッションのすべてのバックグラウンドジョブを取得します。

```powershell
Get-Job
```

結果はテーブルに表示されます。 ジョブの状態が [ **状態** 列に表示されます。

```
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

この場合、State プロパティは、ジョブ2がまだ実行されていることを示します。 コマンドレットを使用して `Receive-Job` ジョブの結果を取得した場合、結果は不完全になります。 `Receive-Job`コマンドレットを繰り返し使用して、すべての結果を取得することができます。 既定では、これを使用するたびに、まだ受け取っていない結果のみが取得されますが、コマンドレットの **Keep** パラメーターを使用すると、 `Receive-Job` 既に受信している場合でも結果を保持できます。

部分的な結果をファイルに書き込んでから、新しい結果を受け取るか、後でジョブの状態を確認することができます。

コマンドレットの **Wait** パラメーターを使用できます `Receive-Job` 。これにより、ジョブが完了し、すべての結果が利用可能になるまで、コマンドプロンプトは返されません。

また、コマンドレットを使用して、 `Wait-Job` ジョブの結果のいずれかまたはすべてを待機することもできます。 `Wait-Job` では、特定のジョブ、すべてのジョブ、またはいずれかのジョブが完了するまで待つことができます。

次のコマンドは、 `Wait-Job` コマンドレットを使用して、 **ID** を持つジョブを待機します。
10.

```powershell
Wait-Job -ID 10
```

その結果、ジョブが完了するまで PowerShell プロンプトは表示されません。

事前に定義した時間が経過するまで待機することもできます。 このコマンドでは、 **Timeout** パラメーターを使用して、待機時間を120秒に制限します。 時間が経過すると、コマンドプロンプトは返されますが、ジョブはバックグラウンドで実行され続けます。

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a>ジョブの停止

バックグラウンドジョブを停止するには、 `Stop-Job` コマンドレットを使用します。 次のコマンドは、システムイベントログ内のすべてのエントリを取得するジョブを開始します。 ジョブオブジェクトは変数に保存され `$job` ます。

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

次のコマンドは、ジョブを停止します。 パイプライン演算子 () を使用して `|` 、変数内のジョブをに送信し `$job` `Stop-Job` ます。

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a>ジョブの削除

バックグラウンドジョブを削除するには、 `Remove-Job` コマンドレットを使用します。 次のコマンドは、変数内のジョブを削除し `$job` ます。

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a>失敗したジョブの調査

ジョブが失敗した原因を調べるには、job オブジェクトの **Reason** プロパティを使用します。

次のコマンドは、必要な資格情報を使用せずにジョブを開始します。 ジョブオブジェクトは変数に保存され `$job` ます。

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

次のコマンドでは、Reason プロパティを使用して、ジョブが失敗する原因となったエラーを見つけます。

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

この場合、リモートコンピューターでコマンドを実行するための明示的な資格情報が必要であったため、ジョブが失敗しました。 **Reason** プロパティの値は次のとおりです。

リモートサーバーに接続できませんでした。次のエラーメッセージが表示されました: "アクセスが拒否されました。"

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
- [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

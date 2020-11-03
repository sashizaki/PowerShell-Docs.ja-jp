---
description: リモートコンピューターでバックグラウンドジョブを実行する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: ad0400c4b4c25c9b0c7133bd916af5056dab1430
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221267"
---
# <a name="about-remote-jobs"></a>リモートジョブについて

## <a name="short-description"></a>概要
リモートコンピューターでバックグラウンドジョブを実行する方法について説明します。

## <a name="detailed-description"></a>詳細説明

バックグラウンドジョブは、現在のセッションと対話せずに非同期的に実行されるコマンドです。 コマンドプロンプトはすぐに返され、ジョブの実行中に引き続きセッションを使用できます。

既定では、バックグラウンドジョブはローカルコンピューター上で実行されます。 ただし、リモートコンピューターでバックグラウンドジョブを実行するには、いくつかの異なる手順を使用できます。

このトピックでは、リモートコンピューターでバックグラウンドジョブを実行する方法について説明します。 ローカルコンピューターでバックグラウンドジョブを実行する方法の詳細については、「 [about_Jobs](about_Jobs.md)」を参照してください。 バックグラウンドジョブの詳細については、「 [about_Job_Details](about_Job_Details.md)」を参照してください。

## <a name="remote-background-jobs"></a>リモートバックグラウンドジョブ

リモートコンピューターでは、3つの異なる方法を使用してバックグラウンドジョブを実行できます。

- リモートコンピューターとの対話型セッションを開始し、対話型セッションでジョブを開始します。 これらの手順はローカルジョブを実行するのと同じですが、すべての操作はリモートコンピューター上で実行されます。

- リモートコンピューターでバックグラウンドジョブを実行し、その結果をローカルコンピューターに返します。 この方法は、バックグラウンドジョブの結果を収集し、ローカルコンピューター上の中央の場所に保持する場合に使用します。

- リモートコンピューター上で結果が保持されているリモートコンピューターでバックグラウンドジョブを実行します。 この方法は、ジョブデータを元のコンピューターでより安全に維持する場合に使用します。

### <a name="start-a-background-job-in-an-interactive-session"></a>対話型セッションでバックグラウンドジョブを開始する

リモートコンピューターで対話型セッションを開始し、対話型セッション中にバックグラウンドジョブを開始することができます。 対話型セッションの詳細については、「about_Remote」および「Enter-PSSession」を参照してください。

対話型セッションでバックグラウンドジョブを開始する手順は、ローカルコンピューターでバックグラウンドジョブを開始する手順とほぼ同じです。 ただし、すべての操作は、ローカルコンピューターではなく、リモートコンピューター上で行われます。

#### <a name="step-1-enter-pssession"></a>手順 1:-PSSESSION を入力する

リモートコンピューターとの対話型セッションを開始するには、Enter-PSSession コマンドレットを使用します。 Enter-PSSession の ComputerName パラメーターを使用して、対話型セッションの一時的な接続を確立できます。 または、Session パラメーターを使用して、PowerShell セッション (PSSession) で対話型セッションを実行できます。

次のコマンドは、Server01 コンピューター上で対話型セッションを開始します。

```powershell
C:\PS> Enter-PSSession -computername Server01
```

Server01 コンピューターに接続されていることを示すために、コマンドプロンプトが変更されます。

```
Server01\C:>
```

#### <a name="step-2-start-job"></a>手順 2: ジョブの開始

セッションでバックグラウンドジョブを開始するには、Start-Job コマンドレットを使用します。

次のコマンドは、Server01 コンピューター上の Windows PowerShell イベントログ内のイベントを取得するバックグラウンドジョブを実行します。 Start-Job コマンドレットは、ジョブを表すオブジェクトを返します。

このコマンドは、ジョブオブジェクトをジョブ変数に保存し \$ ます。

```powershell
Server01\C:> $job = start-job -scriptblock {
  get-eventlog "Windows PowerShell"
}
```

ジョブの実行中に、対話型セッションを使用して他のコマンド (他のバックグラウンドジョブなど) を実行できます。 ただし、ジョブが完了するまで、対話型セッションを開いたままにしておく必要があります。 セッションを終了すると、ジョブは中断され、結果は失われます。

#### <a name="step-3-get-job"></a>手順 3: ジョブの取得

ジョブが完了したかどうかを確認するには、ジョブ変数の値を表示する \$ か、Get-Job コマンドレットを使用してジョブを取得します。 次のコマンドでは、Get-Job コマンドレットを使用してジョブを表示します。

```powershell
Server01\C:> get-job $job

SessionId  Name  State      HasMoreData  Location   Command
---------  ----  -----      -----------  --------   -------
1          Job1  Complete   True         localhost  get-eventlog "Windows...
```

Get-Job 出力は、ジョブが "localhost" コンピューター上で実行されていることを示しています。これは、ジョブがで開始され、同じコンピューター (この場合は Server01) で実行されているためです。

#### <a name="step-4-receive-job"></a>手順 4: 受信-ジョブ

ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。 対話型セッションで結果を表示したり、リモートコンピューター上のファイルに結果を保存したりできます。 次のコマンドは、$job 変数内のジョブの結果を取得します。 このコマンドは、リダイレクト演算子 (>) を使用して、ジョブの結果を Server01 コンピューター上の PsLog.txt ファイルに保存します。

```powershell
Server01\C:> receive-job $job > c:\logs\PsLog.txt
```

#### <a name="step-5-exit-pssession"></a>手順 5: PSSESSION を終了する

対話型セッションを終了するには、Exit-PSSession コマンドレットを使用します。 コマンドプロンプトが変更され、ローカルコンピューターの元のセッションに戻ったことが示されます。

```powershell
Server01\C:> Exit-PSSession
C:\PS>
```

#### <a name="step-6-invoke-command-get-content"></a>手順 6: INVOKE コマンド: GET CONTENT

Server01 コンピューター上の PsLog.txt ファイルの内容をいつでも表示するには、別の対話型セッションを開始するか、リモートコマンドを実行します。 この種類のコマンドは、複数のコマンドを使用して PsLog.txt ファイル内のデータを調査および管理する場合に、PSSession (固定接続) で実行することをお勧めします。 PSSessions の詳細については、「about_PSSessions」を参照してください。

次のコマンドは、New-PSSession コマンドレットを使用して、Server01 コンピューターに接続されている PSSession を作成し、Invoke-Command コマンドレットを使用して PSSession の Get-Content コマンドを実行し、ファイルの内容を表示します。

```powershell
$s = new-pssession -computername Server01
invoke-command -session $s -scriptblock {
  get-content c:\logs\pslog.txt}
```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a>結果をローカルコンピューター ASJOB に返すリモートジョブを開始します。 \(\)

コマンドの結果をローカルコンピューターに返すリモートコンピューターでバックグラウンドジョブを開始するには、Invoke-Command コマンドレットなどのコマンドレットの AsJob パラメーターを使用します。

AsJob パラメーターを使用すると、ジョブがリモートコンピューター上で実行されている場合でも、ジョブオブジェクトは実際にはローカルコンピューター上に作成されます。 ジョブが完了すると、結果がローカルコンピューターに返されます。

ジョブの名詞を含むコマンドレット (Job コマンドレット) を使用して、任意のコマンドレットによって作成されたすべてのジョブを管理できます。 AsJob パラメーターを持つコマンドレットの多くは、PowerShell リモート処理を使用しないので、リモート処理用に構成されておらず、リモート処理の要件を満たしていないコンピューターでも使用できます。

#### <a name="step-1-invoke-command--asjob"></a>手順 1: INVOKE-コマンド-ASJOB

次のコマンドでは、Invoke-Command の AsJob パラメーターを使用して、Server01 コンピューター上でバックグラウンドジョブを開始します。 このジョブは、システム ログのイベントを取得する Get-Eventlog コマンドを実行します。 JobName パラメーターを使用して、ジョブに表示名を割り当てることができます。

```powershell
invoke-command -computername Server01 -scriptblock {
  get-eventlog system} -asjob
```

コマンドの結果は、次のサンプル出力のようになります。

```Output
SessionId   Name   State    HasMoreData   Location   Command
---------   ----   -----    -----------   --------   -------
1           Job1   Running  True          Server01   get-eventlog system
```

AsJob パラメーターを使用すると、Invoke-Command は、Start-Job が返すのと同じ種類のジョブオブジェクトを返します。 ジョブオブジェクトを変数に保存することも、Get-Job コマンドを使用してジョブを取得することもできます。

Location プロパティの値は、Server01 コンピューターでジョブが実行されたことを示しています。

#### <a name="step-2-get-job"></a>手順 2: ジョブの取得

Invoke-Command コマンドレットの AsJob パラメーターを使用して開始されたジョブを管理するには、Job コマンドレットを使用します。 リモートジョブを表すジョブオブジェクトはローカルコンピューター上にあるため、リモートコマンドを実行してジョブを管理する必要はありません。

ジョブが完了したかどうかを確認するには、Get-Job コマンドを使用します。 次のコマンドは、現在のセッションで開始されたすべてのジョブを取得します。

```powershell
get-job
```

リモートジョブが現在のセッションで開始されたため、ローカル Get-Job コマンドはジョブを取得します。 ジョブオブジェクトの State プロパティは、コマンドが正常に完了したことを示しています。

```Output
SessionId   Name   State      HasMoreData   Location   Command
---------   ----   -----      -----------   --------   -------
1           Job1   Completed  True          Server01   get-eventlog system
```

#### <a name="step-3-receive-job"></a>手順 3: 受信-ジョブ

ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。 ジョブの結果は、ジョブオブジェクトが存在するコンピュータに自動的に返されるため、ローカルの Receive-Job コマンドを使用して結果を取得できます。

次のコマンドでは、Receive-Job コマンドレットを使用して、ジョブの結果を取得します。 セッション ID を使用してジョブを識別します。 このコマンドは、ジョブの結果を $results 変数に保存します。 また、結果をファイルにリダイレクトすることもできます。

```powershell
$results = receive-job -id 1
```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a>リモートコンピューターで結果を保持するリモートジョブを開始する

リモートコンピューターでコマンドの結果を保持するバックグラウンドジョブをリモートコンピューターで開始するには、Invoke-Command コマンドレットを使用して、リモートコンピューターで Start-Job コマンドを実行します。 この方法を使用すると、複数のコンピューターでバックグラウンドジョブを実行できます。

Start-Job コマンドをリモートで実行すると、ジョブオブジェクトがリモートコンピューター上に作成され、ジョブの結果がリモートコンピューターに保持されます。
ジョブの観点から見ると、すべての操作はローカルです。 リモートコンピューター上のローカルジョブを管理するために、コマンドをリモートで実行しているだけです。

#### <a name="step-1-invoke-command-start-job"></a>手順 1: コマンドの起動-ジョブ

Invoke-Command コマンドレットを使用して、リモートコンピューターで Start-Job コマンドを実行します。

このコマンドには PSSession (永続的な接続) が必要です。 Invoke-Command の ComputerName パラメーターを使用して一時的な接続を確立した場合、ジョブオブジェクトが返されると、Invoke-Command コマンドは完了したと見なされます。 その結果、一時的な接続は閉じられ、ジョブは取り消されます。

次のコマンドは、New-PSSession コマンドレットを使用して、Server01 コンピューターに接続されている PSSession を作成します。 このコマンドは、PSSession を s 変数に保存し \$ ます。

```powershell
$s = new-pssession -computername Server01
```

次のコマンドは、Invoke-Command コマンドレットを使用して、PSSession で Start-Job コマンドを実行します。 Start-Job コマンドと Get-Eventlog コマンドは、中かっこで囲まれています。

```powershell
invoke-command -session $s -scriptblock {
  start-job -scriptblock {get-eventlog system}}
```

結果は次のサンプル出力のようになります。

```Output
Id       Name    State      HasMoreData     Location   Command
--       ----    -----      -----------     --------   -------
2        Job2    Running    True            Localhost  get-eventlog system
```

Start-Job コマンドをリモートで実行すると、Invoke-Command によっ Start-Job て返されるのと同じ種類のジョブオブジェクトが返されます。 ジョブオブジェクトを変数に保存することも、Get-Job コマンドを使用してジョブを取得することもできます。

Location プロパティの値は、ジョブが Server01 コンピューター上で実行された場合でも、ローカルコンピューター上でジョブが実行されたことを示しています。これは、"LocalHost" と呼ばれています。 ジョブオブジェクトは Server01 コンピューター上に作成され、ジョブは同じコンピューター上で実行されるため、ローカルのバックグラウンドジョブと見なされます。

#### <a name="step-2-invoke-command-get-job"></a>手順 2: コマンドの取得-ジョブ

リモートのバックグラウンドジョブを管理するには、Job コマンドレットを使用します。 ジョブオブジェクトはリモートコンピューター上にあるため、リモートコマンドを実行して、ジョブの結果を取得、停止、待機、または取得する必要があります。

ジョブが完了したかどうかを確認するには、Invoke-Command コマンドを使用して、Server01 コンピューターに接続されている PSSession で Get-Job コマンドを実行します。

```powershell
invoke-command -session $s -scriptblock {get-job}
```

このコマンドによって返されるのは、ジョブ オブジェクトです。 ジョブオブジェクトの State プロパティは、コマンドが正常に完了したことを示しています。

```Output
SessionId   Name  State      HasMoreData   Location   Command
---------   ----  -----      -----------   --------   -------
2           Job2  Completed  True          LocalHost   get-eventlog system
```

#### <a name="step-3-invoke-command-receive-job"></a>手順 3: コマンドの受信-ジョブ

ジョブの結果を取得するには、Invoke-Command コマンドレットを使用して、Server01 コンピューターに接続されている PSSession で Receive-Job コマンドを実行します。

次のコマンドでは、Receive-Job コマンドレットを使用して、ジョブの結果を取得します。 セッション ID を使用してジョブを識別します。 このコマンドは、結果変数にジョブの結果を保存し \$ ます。 Receive-Job の Keep パラメーターを使用して、リモートコンピューター上のジョブキャッシュに結果を保持します。

```powershell
$results = invoke-command -session $s -scriptblock {
  receive-job -sessionid 2 -keep}
```

また、ローカルコンピューターまたはリモートコンピューター上のファイルに結果をリダイレクトすることもできます。
次のコマンドは、リダイレクト演算子を使用して、Server01 コンピューター上のファイルに結果を保存します。

```powershell
invoke-command -session $s -command {
  receive-job -sessionid 2 > c:\logs\pslog.txt}
```

## <a name="see-also"></a>関連項目

[about_Jobs](about_Jobs.md)

[about_Job_Details](about_Job_Details.md)

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)

[Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)

[Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)

[Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)

[Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)

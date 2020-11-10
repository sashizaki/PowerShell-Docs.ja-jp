---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: 560202531a992b9db8ba5d5ebc957f96750f1feb
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389251"
---
# Wait-Job

## 概要
セッションで実行されている PowerShell バックグラウンドジョブの1つまたはすべてが完了するまで、コマンドプロンプトを表示しません。

## SYNTAX

### SessionIdParameterSet (既定値)

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### JobParameterSet

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### NameParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### InstanceIdParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### StateParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### FilterParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## Description

`Wait-Job`コマンドレットは、PowerShell のバックグラウンドジョブが完了するのを待ってから、コマンドプロンプトを表示します。 任意のバックグラウンド ジョブまたはすべてのバックグラウンド ジョブが完了まで待機できます。さらに、ジョブの最大待機時間を設定できます。

ジョブのコマンドが完了すると、によって `Wait-Job` コマンドプロンプトが表示され、別のコマンドにパイプできるようにジョブオブジェクトが返されます。

コマンドレットまたはコマンドレット `Wait-Job` の AsJob パラメーターを使用して開始されたジョブなど、バックグラウンドジョブを待機するには、コマンドレットを使用し `Start-Job` **AsJob** `Invoke-Command` ます。 Windows PowerShell のバックグラウンド ジョブの詳細については、「[about_Jobs](./about/about_Jobs.md)」を参照してください。

Windows PowerShell 3.0 以降では、 `Wait-Job` コマンドレットは、ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も待機します。 が特定の種類のジョブを待機できるようにするには、コマンドレットを実行する前に、コマンドレットを使用するか、 `Wait-Job` `Get-Job` `Import-Module` またはモジュールのコマンドレットを使用して、カスタムジョブの種類をサポートするモジュールをセッションにインポートします。 特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。

## 例

### 例 1: すべてのジョブを待機する

```powershell
Get-Job | Wait-Job
```

このコマンドは、セッションで実行されているすべてのバックグラウンドジョブが完了するまで待機します。

### 例 2: Start-Job を使用してリモートコンピューターで開始されたジョブを待機する

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

この例では、コマンドレットを使用して、 `Wait-Job` リモートコンピューターで開始されたジョブと共にコマンドレットを使用する方法を示し `Start-Job` ます。 コマンド `Start-Job` レットを使用して、コマンドとコマンドの両方を `Wait-Job` リモートコンピューターに送信し `Invoke-Command` ます。

この例では `Wait-Job` 、を使用し `Get-Date` て、3台の異なるコンピューターでバックグラウンドジョブとして実行されているコマンドが終了しているかどうかを確認します。

最初のコマンドは、3台のリモートコンピューターそれぞれに Windows PowerShell セッション ( **PSSession** ) を作成し、それらを変数に格納し `$s` ます。

2番目のコマンドは、を使用して `Invoke-Command` `Start-Job` 、の3つの各セッションでを実行し `$s` ます。
すべてのジョブには、Date1 という名前が付けられます。

3番目のコマンドは、を使用して `Invoke-Command` を実行し `Wait-Job` ます。 このコマンドは、各コンピューター上の Date1 ジョブが完了するまで待機します。 これにより、ジョブオブジェクトの結果のコレクション (配列) が変数に格納され `$done` ます。

4番目のコマンドは、変数内のジョブオブジェクトの配列の **Count** プロパティを使用して `$done` 、完了したジョブの数を確認します。

### 例 3: 最初のバックグラウンドジョブがいつ終了するかを判断する

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

この例では、の **任意** のパラメーターを使用して、 `Wait-Job` 現在のセッションで実行されている多くのバックグラウンドジョブが完了したことを確認します。 また、コマンドレットを使用して `Wait-Job` リモートジョブの完了を待機する方法も示します。

最初のコマンドは、Machines.txt ファイルに一覧表示されている各コンピューター上に **pssession** を作成し、その **pssession** オブジェクトを変数に格納し `$s` ます。 このコマンドは、コマンドレットを使用して、 `Get-Content` ファイルの内容を取得します。 コマンドは、 `Get-Content` コマンドの前に実行されるように、かっこで囲まれてい `New-PSSession` ます。

2番目のコマンドは、 `Get-EventLog` コマンド文字列を引用符で囲んで変数に格納し `$c` ます。

3番目のコマンドは、 `Invoke-Command` コマンドレットを使用して `Start-Job` 、の各セッションでを実行し `$s` ます。
コマンドは、 `Start-Job` 変数でコマンドを実行するバックグラウンドジョブを開始し `Get-EventLog` `$c` ます。

このコマンドは、 **Using** スコープ修飾子を使用して、 `$c` 変数がローカルコンピューター上で定義されていることを示します。 **Using** スコープ修飾子は、Windows PowerShell 3.0 で導入されました。 スコープ修飾子の **使用** の詳細については、「 [about_Remote_Variables](./about/about_Remote_Variables.md)」を参照してください。

4番目のコマンドは、を使用し `Invoke-Command` `Wait-Job` て、セッションでコマンドを実行します。 また、 **Any** パラメーターを使用して、リモートコンピューター上の最初のジョブが完了するまで待機します。

### 例 4: リモートコンピューター上のジョブの待機時間を設定する

```powershell
$s = New-PSSession Server01, Server02, Server03
$jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

この例では、の **Timeout** パラメーターを使用して、 `Wait-Job` リモートコンピューターで実行されているジョブの最大待機時間を設定する方法を示します。

最初のコマンドは、3台のリモートコンピューター (Server01、Server02、および Server03) のそれぞれに **pssession** を作成し、その後、 **pssession** オブジェクトを変数に格納し `$s` ます。

2番目のコマンドは、を使用して、の `Invoke-Command` `Start-Job` 各 **PSSession** オブジェクトでを実行し `$s` ます。 結果として得られるジョブオブジェクトが変数に格納され `$jobs` ます。

3番目のコマンドは、を使用して `Invoke-Command` `Wait-Job` 、の各セッションでを実行し `$s` ます。 `Wait-Job`コマンドは、すべてのコマンドが30秒以内に完了したかどうかを判断します。 **タイムアウト** パラメーターを30に設定して最大待機時間を設定し、コマンドの結果を変数に格納し `$done` ます。

この場合に、30 秒後に Server02 コンピューター上のコマンドのみが完了しました。 `Wait-Job` 待機を終了し、コマンドプロンプトを表示して、完了したジョブを表すオブジェクトを返します。

変数には、 `$done` Server02 で実行されたジョブを表す job オブジェクトが含まれています。

### 例 5: 複数のジョブのいずれかが完了するまで待機する

```powershell
Wait-Job -id 1,2,5 -Any
```

このコマンドは、3つのジョブを Id で識別し、いずれかのジョブが完了するまで待機します。
最初のジョブが完了すると、コマンドプロンプトが返されます。

### 例 6: 期間を待機してから、ジョブをバックグラウンドで続行することを許可する

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

このコマンドは、DailyLog ジョブが完了するまで120秒 (2 分) 待機します。 ジョブが次の2分以内に完了しなかった場合は、コマンドプロンプトが返され、ジョブはバックグラウンドで実行され続けます。

### 例 7: 名前でジョブを待機する

```powershell
Wait-Job -Name "Job3"
```

このコマンドは、ジョブ名を使用して、待機するジョブを識別します。

### 例 8: Start-Job で開始されたローカルコンピューター上のジョブを待機する

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

この例では、を使用して、 `Wait-Job` ローカルコンピューターで開始されたジョブと共にコマンドレットを使用する方法を示し `Start-Job` ます。

これらのコマンドは、過去 1 週間に追加または更新された Windows PowerShell スクリプト ファイルを取得するジョブを開始します。

最初のコマンドは、を使用して、 `Start-Job` ローカルコンピューター上でバックグラウンドジョブを開始します。 このジョブは、 `Get-ChildItem` 過去1週間に追加または更新されたファイル名拡張子が ps1 のすべてのファイルを取得するコマンドを実行します。

3番目のコマンドは、を使用して `Wait-Job` 、ジョブが完了するまで待機します。 ジョブが完了すると、ジョブに関する情報を含むジョブオブジェクトが表示されます。

### 例 9: Invoke-Command を使用してリモートコンピューターで開始されたジョブを待機する

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

この例では `Wait-Job` 、の **AsJob** パラメーターを使用して、リモートコンピューターで開始されたジョブと共にを使用する方法を示し `Invoke-Command` ます。 **AsJob** を使用する場合、ジョブはローカルコンピューター上に作成され、そのジョブがリモートコンピューター上で実行されている場合でも、結果はローカルコンピューターに自動的に返されます。

この例では、を使用して `Wait-Job` `Get-Process` 、3台のリモートコンピューター上のセッションで実行されているコマンドが完了したかどうかを確認します。

最初のコマンドは、3台のコンピューター上に **PSSession** オブジェクトを作成し、それらを変数に格納し `$s` ます。

2番目のコマンドは、を使用して `Invoke-Command` `Get-Process` 、の3つの各セッションでを実行し `$s` ます。
このコマンドは、 **AsJob** パラメーターを使用して、バックグラウンドジョブとしてコマンドを非同期的に実行します。 コマンドは、を使用して開始されたジョブと同様に、ジョブオブジェクトを返し、 `Start-Job` ジョブオブジェクトは変数に格納され `$j` ます。

3番目のコマンドは、パイプライン演算子 () を使用して、 `|` のジョブオブジェクトを `$j` コマンドレットに送信し `Wait-Job` ます。 `Invoke-Command`この場合、ジョブはローカルコンピューター上に存在するため、コマンドは必要ありません。

### 例 10: ID を持つジョブを待機する

```powershell
Get-Job
```

```Output
Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where
```

```powershell
Wait-Job -Id 1
```

このコマンドは、ID 値が 1 であるジョブを待機します。

## PARAMETERS

### -任意

このコマンドレットによってコマンドプロンプトが表示され、ジョブの完了時にジョブオブジェクトが返されることを示します。 既定では、は、 `Wait-Job` 指定されたすべてのジョブが完了するまで待機してから、プロンプトを表示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter

条件のハッシュテーブルを指定します。 このコマンドレットは、ハッシュテーブル内のすべての条件を満たすジョブを待機します。 ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。

このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。 コマンドレットを使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。 このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

このコマンドレットが中断または切断状態のジョブを引き続き待機することを示します。 既定では、 `Wait-Job` ジョブが次のいずれかの状態にある場合、は待機を返すか、または終了します。

- 完了
- 失敗
- 停止済み
- Suspended
- [Disconnected]\(切断済み\)

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

このコマンドレットが待機するジョブの Id の配列を指定します。

ID は、現在のセッションでジョブを一意に識別する整数です。 インスタンス ID よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。 1つ以上の Id をコンマで区切って入力できます。 ジョブの ID を検索するには、「」と入力 `Get-Job` します。

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

このコマンドレットが待機するジョブのインスタンス Id の配列を指定します。 既定値はすべてのジョブです。

インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。 ジョブのインスタンス ID を検索するには、を使用 `Get-Job` します。

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ジョブ

このコマンドレットが待機するジョブを指定します。 ジョブ オブジェクトが格納されている変数、またはジョブ オブジェクトを取得するコマンドを入力します。 パイプライン演算子を使用して、ジョブオブジェクトをコマンドレットに渡すこともでき `Wait-Job` ます。 既定では、は、 `Wait-Job` 現在のセッションで作成されたすべてのジョブを待機します。

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

このコマンドレットが待機するジョブのフレンドリ名を指定します。

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -状態

ジョブの状態を指定します。 このコマンドレットは、指定された状態のジョブのみを待機します。 このパラメーターの有効値は、次のとおりです。

- NotStarted
- 実行中
- 完了
- 失敗
- 停止済み
- ［ブロック済み］
- Suspended
- [Disconnected]\(切断済み\)
- 中断中
- 停止中

ジョブの状態の詳細については、「 [Jobstate 列挙型](/dotnet/api/system.management.automation.jobstate)」を参照してください。

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -タイムアウト

各バックグラウンドジョブの最大待機時間を秒単位で指定します。 既定値は-1 です。このコマンドレットは、ジョブが完了するまで待機することを示します。 コマンドではなくコマンドを送信すると、タイミングが開始 `Wait-Job` され `Start-Job` ます。

この時間を超えた場合、ジョブがまだ実行中でも、待機が終了し、コマンド プロンプトが返されます。 このコマンドでは、エラーメッセージは表示されません。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System. Automation. RemotingJob

パイプを使用してジョブオブジェクトをこのコマンドレットに渡します。

## 出力

### システムの管理. PSRemotingJob

このコマンドレットは、完了したジョブを表すジョブオブジェクトを返します。 **Timeout** パラメーターの値を超えたことが原因で待機が終了した場合、 `Wait-Job` はオブジェクトを返しません。

## 注

既定では、 `Wait-Job` ジョブが次のいずれかの状態にある場合、は待機を返すか、または終了します。

- 完了
- 失敗
- 停止済み
- Suspended
- `Wait-Job`中断されたジョブと切断されたジョブを引き続き待機するために切断された場合は、 **Force** パラメーターを使用します。

## 関連リンク

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: acf01415c9722b6da95e70a8db1b558c3e14662b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212712"
---
# Wait-Job

## 概要
セッションで実行されている Windows PowerShell のバックグラウンドジョブの1つまたはすべてが完了するまで、コマンドプロンプトを表示しません。

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
**Wait ジョブ** コマンドレットは、Windows PowerShell のバックグラウンドジョブが完了するのを待ってから、コマンドプロンプトを表示します。
任意のバックグラウンド ジョブまたはすべてのバックグラウンド ジョブが完了まで待機できます。さらに、ジョブの最大待機時間を設定できます。

ジョブ内のコマンドが完了すると、 **Wait-Job** はコマンド プロンプトを表示し、ジョブ オブジェクトを返します。そのため、パイプを使用して別のコマンドにジョブ オブジェクトを渡すことができます。

Start-Job コマンドレットまたは Invoke-Command コマンドレットの *AsJob* パラメーターを使用して開始されたジョブなど、バックグラウンドジョブを待機するには、 **wait-Job** コマンドレットを使用します。
Windows PowerShell のバックグラウンド ジョブの詳細については、「about_Jobs」を参照してください。

Windows PowerShell 3.0 以降では、 **待機ジョブ** コマンドレットは、ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も待機します。
**待機ジョブ** が特定の種類のジョブを待機できるようにするには、Get-Job コマンドレットを実行する前に、カスタムジョブの種類をサポートするモジュールをセッションにインポートします。そのためには、Import-Module コマンドレットを使用するか、またはモジュールのコマンドレットを使用または取得します。
特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。

## 例

### 例 1: すべてのジョブを待機する

```
PS C:\> Get-Job | Wait-Job
```

このコマンドは、セッションで実行されているすべてのバックグラウンドジョブが完了するまで待機します。

### 例 2: Start-Job を使用してリモートコンピューターで開始されたジョブを待機する

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
PS C:\> $done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
PS C:\> $done.Count
3
```

この例では、 **Start ジョブ** コマンドレットを使用して、リモートコンピューターで開始されたジョブで、 **Wait-job** コマンドレットを使用する方法を示します。
**開始ジョブ** と **待機ジョブ** の両方のコマンドをリモートコンピューターに送信するには、 **コマンド** レットを使用します。

この例では、 **待機ジョブ** を使用して、3台の異なるコンピューター上でバックグラウンドジョブとして実行されている Get-Date コマンドが終了しているかどうかを判断します。

最初のコマンドは、3台のリモートコンピューターそれぞれに Windows PowerShell セッション ( **PSSession** ) を作成し、それらを $s 変数に格納します。

2番目のコマンドは、 **Invoke コマンド** を使用して、$s 内の3つの各セッションで **Start ジョブ** を実行します。
すべてのジョブには、Date1 という名前が付けられます。

3番目のコマンドは、 **Invoke コマンド** を使用して **待機ジョブ** を実行します。
このコマンドは、各コンピューター上の Date1 ジョブが完了するまで待機します。
このコマンドは、ジョブ オブジェクトの結果のコレクション (配列) を $done 変数に格納します。

4番目のコマンドは、$done 変数内のジョブオブジェクトの配列の **Count** プロパティを使用して、完了したジョブの数を確認します。

### 例 3: 最初のバックグラウンドジョブがいつ終了するかを判断する

```
PS C:\> $s = New-PSSession (Get-Content Machines.txt)
PS C:\> $c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
PS C:\> Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
PS C:\> Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

この例では、 **Wait-Job** の *任意* のパラメーターを使用して、現在のセッションで実行されている多くのバックグラウンドジョブが完了したことを確認します。
また、 **wait-Job** コマンドレットを使用して、リモートジョブが終了するのを待機する方法についても説明します。

最初のコマンドは、Machines.txt ファイルに一覧表示されている各コンピューター上に **pssession** を作成し、$s 変数に **pssession** オブジェクトを格納します。
このコマンドは、Get-Content コマンドレットを使用して、ファイルの内容を取得します。
**Get Content** コマンドは、New-PSSession コマンドの前に実行されるように、かっこで囲まれています。

2番目のコマンドは、 **Get EventLog** コマンド文字列を $c 変数に引用符で囲んで格納します。

3番目のコマンドは、Invoke-Command コマンドレットを使用して、$s 内の各セッションで **Start ジョブ** を実行します。
**Start ジョブ** コマンドを実行すると、$c 変数で **Get EventLog** コマンドを実行するバックグラウンドジョブが開始されます。

このコマンドは、 **Using** スコープ修飾子を使用して、$c 変数がローカル コンピューター上で定義されたことを示します。
**Using** スコープ修飾子は、Windows PowerShell 3.0 で導入されました。
スコープ修飾子の **使用** の詳細については、「about_Remote_Variables (」を参照してください https://go.microsoft.com/fwlink/?LinkID=252653) 。

4番目のコマンドは、 **Invoke コマンド** を使用して、セッションで **待機ジョブ** コマンドを実行します。
また、 *Any* パラメーターを使用して、リモートコンピューター上の最初のジョブが完了するまで待機します。

### 例 4: リモートコンピューター上のジョブの待機時間を設定する

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> $jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
PS C:\> $done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

この例では、 **Wait ジョブ** の *Timeout* パラメーターを使用して、リモートコンピューターで実行されているジョブの最大待機時間を設定する方法を示します。

最初のコマンドは、3台のリモートコンピューター (Server01、Server02、および Server03) のそれぞれに **pssession** を作成し、 **pssession** オブジェクトを $s 変数に格納します。

2番目のコマンドは、 **Invoke コマンド** を使用して、$s 内の各 **PSSession** オブジェクトで **Start ジョブ** を実行します。
結果として得られるジョブオブジェクトが $jobs 変数に格納されます。

3番目のコマンドは、$s 内の各セッションで、 **Invoke コマンド** を使用して **待機ジョブ** を実行します。
**Wait ジョブ** コマンドは、すべてのコマンドが30秒以内に完了したかどうかを判断します。
*タイムアウト* パラメーターを30に設定して最大待機時間を設定し、コマンドの結果を $done 変数に格納します。

この場合に、30 秒後に Server02 コンピューター上のコマンドのみが完了しました。
**Wait-job** は待機を終了し、コマンドプロンプトを表示して、完了したジョブを表すオブジェクトを返します。

$done 変数には、Server02 上で実行されたジョブを表すジョブ オブジェクトが含まれています。

### 例 5: 複数のジョブのいずれかが完了するまで待機する

```
PS C:\> Wait-Job -id 1,2,5 -Any
```

このコマンドは、3つのジョブを Id で識別し、いずれかのジョブが完了するまで待機します。
最初のジョブが完了すると、コマンドプロンプトが返されます。

### 例 6: 期間を待機してから、ジョブをバックグラウンドで続行することを許可する

```
PS C:\> Wait-Job -Name "DailyLog" -Timeout 120
```

このコマンドは、DailyLog ジョブが完了するまで120秒 (2 分) 待機します。
ジョブが次の2分以内に完了しなかった場合は、コマンドプロンプトが返され、ジョブはバックグラウンドで実行され続けます。

### 例 7: 名前でジョブを待機する

```
PS C:\> Wait-Job -Name "Job3"
```

このコマンドは、ジョブ名を使用して、待機するジョブを識別します。

### 例 8: Start-Job で開始されたローカルコンピューター上のジョブを待機する

```
PS C:\> $j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
PS C:\> $j | Wait-Job
```

この例では、 **Start ジョブ** を使用してローカルコンピューターで開始されたジョブで、 **Wait-job** コマンドレットを使用する方法を示します。

これらのコマンドは、過去 1 週間に追加または更新された Windows PowerShell スクリプト ファイルを取得するジョブを開始します。

最初のコマンドは、 **開始ジョブ** を使用して、ローカルコンピューター上でバックグラウンドジョブを開始します。
このジョブは、過去1週間に追加または更新されたファイル名拡張子が ps1 のすべてのファイルを取得する Get-ChildItem コマンドを実行します。

3番目のコマンドは、ジョブが完了するまで待機するために、 **Wait ジョブ** を使用します。
ジョブが完了すると、ジョブに関する情報を含むジョブオブジェクトが表示されます。

### 例 9: Invoke-Command を使用してリモートコンピューターで開始されたジョブを待機する

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> $j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
PS C:\> $j | Wait-Job
```

この例では、リモートコンピューターで開始されたジョブに対して、 **Invoke コマンド** の *AsJob* パラメーターを使用して、 **待機ジョブ** を使用する方法を示します。
*AsJob* を使用する場合、ジョブはローカルコンピューター上に作成され、そのジョブがリモートコンピューター上で実行されている場合でも、結果はローカルコンピューターに自動的に返されます。

この例では、 **待機ジョブ** を使用して、3台のリモートコンピューター上のセッションで実行されている **Get Process** コマンドが完了しているかどうかを確認します。

最初のコマンドは、3台のコンピューター上に **PSSession** オブジェクトを作成し、それらを $s 変数に格納します。

2番目のコマンドは、 **Invoke コマンド** を使用して、$s 内の3つの各セッションで **Get Process** を実行します。
このコマンドは、 *AsJob* パラメーターを使用して、バックグラウンドジョブとしてコマンドを非同期的に実行します。
このコマンドは、 **Start ジョブ** を使用して開始されたジョブと同様に、ジョブオブジェクトを返します。ジョブオブジェクトは $j 変数に格納されます。

3番目のコマンドは、パイプライン演算子 (|) を使用して、$j 内のジョブオブジェクトを、 **Wait ジョブ** コマンドレットに送信します。
この場合、ジョブはローカルコンピューター上に存在するので、 **コマンドの呼び出し** は必要ありません。

### 例 10: ID を持つジョブを待機する

```
PS C:\> Get-Job

Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where

PS C:\> Wait-Job -Id 1
```

このコマンドは、ID 値が 1 であるジョブを待機します。

## PARAMETERS

### -任意
このコマンドレットによってコマンドプロンプトが表示され、ジョブの完了時にジョブオブジェクトが返されることを示します。
既定では、指定されたすべてのジョブが完了する **まで待機し** てから、プロンプトが表示されます。

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
条件のハッシュテーブルを指定します。
このコマンドレットは、ハッシュテーブル内のすべての条件を満たすジョブを待機します。
ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。

このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。
これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。
このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。

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
このコマンドレットが中断または切断状態のジョブを引き続き待機することを示します。
既定では、ジョブが次のいずれかの状態にある場合は、 **待機時間** が返されるか、待機が終了します。

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

ID は、現在のセッションでジョブを一意に識別する整数です。
インスタンス ID よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。
1つ以上の Id をコンマで区切って入力できます。
ジョブの ID を検索するには、「」と入力 `Get-Job` します。

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
このコマンドレットが待機するジョブのインスタンス Id の配列を指定します。
既定値はすべてのジョブです。

インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。
ジョブのインスタンス ID を調べるには、 **Get-Job** を使用します。

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
このコマンドレットが待機するジョブを指定します。
ジョブ オブジェクトが格納されている変数、またはジョブ オブジェクトを取得するコマンドを入力します。
また、パイプライン演算子を使用して、ジョブオブジェクトを **Wait** コマンドレットに送信することもできます。
既定では、 **Wait** は、現在のセッションで作成されたすべてのジョブを待機します。

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
ジョブの状態を指定します。
このコマンドレットは、指定された状態のジョブのみを待機します。
このパラメーターの有効値は、次のとおりです。

- NotStarted
- 実行中
- 完了
- 失敗
- 停止済み
- Blocked
- Suspended
- [Disconnected]\(切断済み\)
- 中断中
- 停止中

ジョブの状態の詳細については、MSDN ライブラリの「 [Jobstate 列挙型](https://msdn.microsoft.com/library/system.management.automation.jobstate) 」を参照してください。

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
各バックグラウンドジョブの最大待機時間を秒単位で指定します。
既定値は-1 です。このコマンドレットは、ジョブが完了するまで待機することを示します。
タイミングは、 **開始ジョブ** コマンドではなく、 **Wait ジョブ** コマンドを送信すると開始されます。

この時間を超えた場合、ジョブがまだ実行中でも、待機が終了し、コマンド プロンプトが返されます。
このコマンドでは、エラーメッセージは表示されません。

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
このコマンドレットは、完了したジョブを表すジョブオブジェクトを返します。
*Timeout* パラメーターの値を超えたために待機が終了した場合、 **待機** 時間はオブジェクトを返しません。

## 注

* 既定では、ジョブが次のいずれかの状態にある場合は、 **待機時間** が返されるか、待機が終了します。

- 完了
- 失敗
- 停止済み
- Suspended
- 中断されたジョブと切断されたジョブの待機を続けるために、direct **Wait ジョブ** が切断されました。 *Force* パラメーターを使用してください。

## 関連リンク

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

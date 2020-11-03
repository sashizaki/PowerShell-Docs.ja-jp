---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213424"
---
# New-JobTrigger

## 概要
スケジュールされたジョブのジョブ トリガーを作成します。

## SYNTAX

### Once (既定値)

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### 毎日

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### 週単位

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### AtStartup

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### AtLogon

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## Description
**新しい-JobTrigger** コマンドレットは、スケジュールされたジョブを1回だけ、または定期的なスケジュールで開始するか、イベントが発生したときに開始するジョブトリガーを作成します。

**New-JobTrigger** から返された **ScheduledJobTrigger** オブジェクトを使用して、新しいまたは既存のスケジュールされたジョブのジョブ トリガーを設定できます。
また、Get-JobTrigger コマンドレットを使用して、既存のスケジュールされたジョブのジョブトリガーを取得したり、ジョブトリガーを表すハッシュテーブル値を使用して、ジョブトリガーを作成することもできます。

ジョブトリガーを作成するときに、New-ScheduledJobOption コマンドレットによって指定されたオプションの既定値を確認します。
これらのオプションは、有効な値と既定値が **Task Scheduler** の対応するオプションと同じで、スケジュールされたジョブのスケジュールとタイミングに影響します。

**New-JobTrigger** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: スケジュールを設定する

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

このコマンドは、 **New-JobTrigger** コマンドレットを使用して、スケジュールされたジョブを 1 回だけ開始するジョブ トリガーを作成します。
*At* パラメーターの値は、Windows PowerShell によって **DateTime** オブジェクトに変換される文字列です。
*At* パラメーターの値には、時刻だけでなく、明示的な日付も含まれています。
日付を省略すると、現在の日付の午前 3 時 00 分のトリガーが作成されます。これは、過去の時刻を表す可能性があります。

### 例 2: 日単位のスケジュール

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

このコマンドは、3 日おきの午前 4 時 15 分にスケジュールされたジョブを開始するジョブ トリガーを作成します。

*At* パラメーターの値には日付が含まれていないため、 **DateTime** オブジェクトの日付の値として現在の日付が使用されます。
日時が過去の場合、スケジュールされたジョブは次の実行日 ( *At* パラメーターの値の 3 日後) に開始されます。

### 例 3: 週単位のスケジュール

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

このコマンドは、4 週間おきの月曜日、水曜日、および金曜日の 23:00 (午後 11 時 00 分) にスケジュールされたジョブを開始するジョブ トリガーを作成します。

*DaysOfWeek* パラメーターの値は、のような整数で入力することもでき `-DaysOfWeek 1, 5` ます。

### 例 4: ログオンスケジュール

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

このコマンドは、ドメイン管理者がコンピューターにログオンするたびに、スケジュールされたジョブを開始するジョブ トリガーを作成します。

### 例 5: ランダム遅延の使用

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

このコマンドは、毎日午前 1 時 00 分にスケジュールされたジョブを開始するジョブ トリガーを作成します。
このコマンドでは、 *RandomDelay* パラメーターを使用して、遅延の最大値を 20 分に設定します。
その結果、ジョブは、毎日午前 1 時 00 分から 1 時 20 分の間に実行されます (時刻は擬似ランダムに変動します)。

ランダムな遅延は、サンプリング、負荷分散、およびその他の管理タスクに使用できます。
遅延値を設定するときは、New-ScheduledJobOption コマンドレットの有効値と既定値を確認し、オプション設定で遅延を調整します。

### 例 6: 新しいスケジュールされたジョブのジョブトリガーを作成する

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

これらのコマンドは、ジョブ トリガーを使用して、スケジュールされた新しいジョブを作成します。

### 例 7: スケジュールされたジョブにジョブトリガーを追加する

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

この例では、既存のスケジュールされたジョブにジョブ トリガーを追加する方法を示します。
任意のスケジュールされたジョブに複数のジョブ トリガーを追加できます。

このコマンドは、Add-JobTrigger コマンドレットを使用して、スケジュールされたジョブ SynchronizeApps にジョブトリガーを追加します。
*Trigger* パラメーターの値は、毎日午前 3 時 10 分にジョブを実行する **New-JobTrigger** コマンドです。

コマンドが完了すると、SynchronizeApps は、ジョブ トリガーで指定された時刻に実行されるスケジュールされたジョブになります。

### 例 8: 繰り返しジョブトリガーを作成する

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

このコマンドを実行すると、60年9月 2013 12 日から 1:00 AM に48時間、ジョブを実行するジョブトリガーが作成されます。

### 例 9: 繰り返しのジョブトリガーを停止する

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

このコマンドは、トリガーされた SecurityCheck ジョブ (ジョブ トリガーの期限が過ぎるまで 60 分おきに実行されます) を強制的に停止します。

ジョブが繰り返されないようにするには、Get-JobTrigger を使用して SecurityCheck ジョブのジョブトリガーを取得し、Set-JobTrigger コマンドレットを使用して、ジョブトリガーの繰り返し間隔と繰り返し期間をゼロ (0) に変更します。

### 例 10: 1 時間ごとのジョブトリガーを作成する

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

次のコマンドは、無期限で、12 時間おきに 1 回スケジュールされたジョブを実行するジョブ トリガーを作成します。
スケジュールは、翌日 (2012 年 9 月 21 日) の午前 0 時 (0:00 AM) に開始されます。

## PARAMETERS

### -At
指定された日時にジョブを開始します。
Get-Date コマンドレットが返す **DateTime** オブジェクト、または日付と時刻に変換できる文字列 ("April 19, 2012 15:00"、"12/31"、または "3am" など) を入力します。
年などの日付の要素を指定しない場合、トリガーの日付には、現在の日付の対応する要素が使用されます。

*Once* パラメーターを使用する場合は、 *At* パラメーターの値の設定を未来の日時に設定します。
**DateTime** オブジェクトの既定の日付は現在の日付です。そのため、日付を明示的に指定せずに、現在の時刻より前の時刻を指定すると、過去の時刻のジョブ トリガーが作成されます。

**Datetime オブジェクト** 、および **datetime** オブジェクトに変換された文字列は、コントロールパネルの [地域と言語] で選択した日付と時刻の形式と互換性があるように自動的に調整されます。

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtLogOn
指定されたユーザーがコンピューターにログオンしたときに、スケジュールされたジョブを開始します。
ユーザーを指定するには、 *User* パラメーターを使用します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtStartup
Windows の起動時に、スケジュールされたジョブを開始します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -毎日
日単位の定期的なジョブ スケジュールを指定します。
*Daily* パラメーターセットの他のパラメーターを使用して、スケジュールの詳細を指定します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysInterval
日単位のスケジュールの実行間隔を日数で指定します。
たとえば、値が 3 の場合、スケジュールされたジョブは、1 日、4 日、7 日というように 3 日おきに開始されます。
既定値は 1 です。

```yaml
Type: System.Int32
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
週単位でスケジュールされたジョブを実行する曜日を指定します。
"Monday" などの曜日名または 0 ～ 6 の整数 (0 は日曜日を表します) を入力します。
Weekly パラメーター セットでは、このパラメーターは必須です。

ジョブ トリガーでは、曜日名は整数値に変換されます。
コマンド内で曜日名を引用符で囲む場合は、"Monday", "Tuesday" など、各曜日名を別々に引用符で囲みます。
複数の曜日名を 1 つの引用符のペアで囲んだ場合は、対応する整数値が合計されます。
たとえば、"Monday, Tuesday" (1, 2) は、"Wednesday" (3) になります。

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -1 回
非定期的な (1 回だけの) スケジュールまたは繰り返しのカスタム スケジュールを指定します。
繰り返しのスケジュールを作成するには、 *Once* パラメーターと一緒に *RepetitionDuration* パラメーターと *RepetitionInterval* パラメーターを使用します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RandomDelay
スケジュールされた開始時刻のランダムな遅延を有効にし、遅延の最大値を設定します。
遅延の長さは、開始ごとに擬似ランダムに設定され、遅延なしから、このパラメーターの値で指定された時間の間で変動します。
既定値のゼロ (00:00:00) では、ランダムな遅延が無効になります。

New-TimeSpan コマンドレットによって返されるような timespan オブジェクトを入力するか、:: format に値を入力します。この値は、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換されます。

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -繰り返し (無期限)
このパラメーターは、Windows PowerShell 4.0 以降で利用でき、 **RepetitionDuration** パラメーターの *TimeSpan.MaxValue* 値を指定することなく、スケジュールされたジョブを無期限に繰り返し実行します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepetitionDuration
指定された期間を過ぎるまでジョブを繰り返し実行します。
繰り返しの頻度は、 *RepetitionInterval* パラメーターの値によって決まります。
たとえば、 **RepetitionInterval** の値が 5 分で、 **RepetitionDuration** の値が 2 時間の場合、ジョブは 2 時間の間 5 分おきにトリガーされます。

New-TimeSpan コマンドレットが返す timespan オブジェクトや、timespan オブジェクトに変換できる文字列 ("1:05:30" など) を入力します。

ジョブを無期限に実行するには、代わりに *RepeatIndefinitely* パラメーターを追加します。

ジョブトリガーの繰り返し期間の有効期限が切れる前にジョブを停止するには、Set-JobTrigger コマンドレットを使用して *RepetitionDuration* 値をゼロ (0) に設定します。

このパラメーターは、 *Once* 、 *At* 、および *RepetitionInterval* パラメーターがコマンドで使用されている場合にのみ有効です。

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepetitionInterval
ジョブは、指定された時間間隔で繰り返し実行されます。
たとえば、このパラメーターの値が 2 時間の場合、ジョブは 2 時間おきにトリガーされます。
既定値の 0 では、ジョブは繰り返し実行されません。

New-TimeSpan コマンドレットが返す timespan オブジェクトや、timespan オブジェクトに変換できる文字列 ("1:05:30" など) を入力します。

このパラメーターは、 *Once* 、 *At* 、および *RepetitionDuration* パラメーターがコマンドで使用されている場合にのみ有効です。

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
スケジュールされたジョブの *AtLogon* 開始をトリガーするユーザーを指定します。
ユーザーの名前を \<UserName\> または形式で入力 \<Domain\Username\> するか、アスタリスク () を入力して \* すべてのユーザーを表します。
既定値は、すべてのユーザーです。

```yaml
Type: System.String
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -毎週
週単位の定期的なジョブ スケジュールを指定します。
Weekly パラメーター セットの他のパラメーターを使用して、スケジュールの詳細を指定します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeksInterval
週単位のジョブ スケジュールの実行間隔を週数で指定します。
たとえば、値が 3 の場合、スケジュールされたジョブは、1 週目、4 週目、7 週目というように 3 週おきに開始されます。
既定値は 1 です。

```yaml
Type: System.Int32
Parameter Sets: Weekly
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし
パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### Microsoft. ScheduledJob. ScheduledJobTrigger

## 注

* ジョブ トリガーはディスクに保存されません。 ただし、スケジュールされたジョブはディスクに保存されるので、Get-JobTrigger を使用して、スケジュールされたジョブのジョブトリガーを取得できます。
* **新しい-JobTrigger** では、過去の日付の1回限りのトリガーなど、スケジュールされたジョブを実行しないジョブトリガーを作成することはできません。
* Register-ScheduledJob コマンドレットは、 **新しい-jobtrigger** または Get-JobTrigger コマンドレットによって返されるものや、トリガー値を含むハッシュテーブルなど、scheduledjobtrigger オブジェクトを受け入れます。

  ハッシュ テーブルを渡すには、次のキーを使用します。

  `@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (または任意の有効な時刻文字列)。 `DaysOfWeek="Monday", "Wednesday"` (または曜日名の任意の組み合わせ)。 `Interval=2` (または任意の有効な頻度の間隔)。 `RandomDelay="30minutes"` (または任意の有効な timespan 文字列)。 `User="Domain1\User01` (または任意の有効なユーザーです。 *Atlogon* frequency 値を指定した場合にのみ使用されます)}

## 関連リンク

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)

---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213400"
---
# Set-JobTrigger

## 概要
スケジュールされたジョブのジョブ トリガーを変更します。

## SYNTAX

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## Description
**Set-JobTrigger** コマンドレットは、スケジュールされたジョブのジョブ トリガーのプロパティを変更します。
このコマンドレットを使用すると、ジョブを開始する時間や頻度を変更することや、時間ベースのスケジュールから、ログオンまたは起動によってトリガーされるスケジュールに変更することができます。

ジョブトリガーは、スケジュールされたジョブを開始するための定期的なスケジュールまたは条件を定義します。
ジョブ トリガーはディスクに保存されませんが、スケジュールされたジョブのジョブ トリガーを変更することはできます。スケジュールされたジョブは、ディスクに保存されます。

スケジュールされたジョブのジョブトリガーを変更するには、まず Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブのジョブトリガーを取得します。
次に、パイプを使用してトリガーを **Set-JobTrigger** に渡すか、トリガーを変数に保存し、 *Set-JobTrigger* コマンドレットの **InputObject** パラメーターを使用して、トリガーを特定します。
**Set-JobTrigger** の他のパラメーターを使用して、ジョブ トリガーを変更します。

ジョブトリガーの種類 (たとえば、ジョブトリガーを毎日または毎週のトリガーから *Atlogon* トリガーに変更する) を変更すると、元のトリガーのプロパティが削除されます。
ただし、週単位のトリガーの曜日の変更など、トリガーの種類ではなく、値を変更した場合は、指定したプロパティのみが変更されます。
元のジョブ トリガーの他のすべてのプロパティは保持されます。

**設定-JobTrigger** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*`  ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: ジョブトリガーの日数を変更する

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

この例では、週単位のジョブ トリガーの曜日を変更する方法を示します。

最初のコマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブ DeployPackage のジョブトリガーを取得します。
出力には、トリガーによって毎週水曜日と土曜日の午前 0 時にジョブが開始されることが示されています。

このコマンドは必須ではありません。トリガーの変更の結果を表示するためにのみ含まれています。

### 例 2: ジョブトリガーの種類を変更する

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

この例では、ジョブを開始するジョブ トリガーの種類を変更する方法を示します。
この例のコマンドは、AtStartup ジョブ トリガーを週単位のトリガーに置き換えます。

最初のコマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたインベントリジョブのジョブトリガーを取得します。
出力には、ジョブに1日のトリガーと *Atstartup* トリガーという2つのトリガーがあることが示されています。

このコマンドは必須ではありません。トリガーの変更の結果を表示するためにのみ含まれています。

### 例 3: リモートジョブトリガーのユーザーを変更する

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

このコマンドは、Server01 コンピューター上のスケジュールされたジョブのすべての *Atlogon* ジョブトリガーのユーザーを変更します。

このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。

リモートコマンドは、コンピューター上のスケジュールされたすべてのジョブを取得する Get-ScheduledJob コマンドで開始します。
スケジュールされたジョブは Get-JobTrigger コマンドレットにパイプ処理され、スケジュールされたジョブのジョブトリガーを取得します。
各ジョブ トリガーには、スケジュールされたジョブを含む JobDefinition プロパティが含まれています。そのため、トリガーを変更しても、スケジュールされたジョブとの関連付けは維持されます。

ジョブトリガーは、パイプを使用して Where-Object コマンドレットに渡されます。このコマンドレットは、User プロパティを持つジョブトリガーを取得します。
パイプを使用して、選択されたジョブ トリガーを **Set-JobTrigger** コマンドレットに渡して、ユーザーを Domain01\Admin02 に変更します。

### 例 4: 多くのジョブトリガーのいずれかを変更する

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

この例のコマンドは、スケジュールされたジョブ SecurityCheck の *Once* ジョブ トリガーの繰り返し間隔を 60 分おきから 90 分おきに変更します。
セキュリティチェックのスケジュールされたジョブには3つのジョブトリガーがあるため、コマンドは Get-JobTrigger コマンドレットの *TriggerId* パラメーターを使用して、変更されているジョブトリガーを識別します。

最初のコマンドは、 **Get-JobTrigger** コマンドレットを使用して、スケジュールされたジョブ SecurityCheck のすべてのジョブ トリガーを取得します。
出力にはジョブ トリガーの ID が示されており、 *Once* ジョブ トリガーの ID が 3 であることがわかります。

## PARAMETERS

### -At
指定された日時にジョブを開始します。
Get-Date コマンドレットによって返される **DateTime** オブジェクトや、時刻に変換できる文字列 ("April 19, 2012 15:00"、"12/31/2013 9:00 PM"、"3am" など) を入力します。

**DateTime** オブジェクトの要素 (秒など) を指定しない場合、ジョブトリガーのその要素は変更されません。
元のジョブトリガーに **DateTime** オブジェクトが含まれておらず、要素を省略した場合は、現在の日付と時刻から対応する要素を使用してジョブトリガーが作成されます。

*Once* パラメーターを使用する場合は、 *At* パラメーターの値を特定の日時に設定します。
**DateTime** オブジェクトの既定値の日付は現在の日付です。そのため、日付を明示的に指定せずに、現在の時刻よりも前の時刻を指定すると、過去の時刻のジョブ トリガーが作成されます。

**Datetime オブジェクト** 、および **datetime** オブジェクトに変換された文字列は、コントロールパネルの [地域と言語] で選択した日付と時刻の形式と互換性があるように自動的に調整されます。

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtStartup
Windows の起動時に、スケジュールされたジョブを開始します。

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

### -毎日
日単位の定期的なジョブ スケジュールを指定します。
*Daily* パラメーターセットの他のパラメーターを使用して、スケジュールの詳細を指定します。

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

### -DaysInterval
日単位のスケジュールの実行間隔を日数で指定します。
たとえば、値が 3 の場合、スケジュールされたジョブは、1 日、4 日、7 日というように 3 日おきに開始されます。
既定値は 1 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
週単位でスケジュールされたジョブを実行する曜日を指定します。
曜日を入力します。たとえば、月曜日、木曜日、整数0-6 のようになります。0は日曜日を表し、アスタリスク ( \* ) は毎日を表します。
Weekly パラメーター セットでは、このパラメーターは必須です。

ジョブ トリガーでは、曜日名は整数値に変換されます。
コマンド内で曜日名を引用符で囲む場合は、"Monday", "Tuesday" など、各曜日名を別々に引用符で囲みます。
複数の曜日名を 1 つの引用符のペアで囲んだ場合は、対応する整数値が合計されます。
たとえば、"Monday, Tuesday" (1, 2) は、"Wednesday" (3) になります。

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
ジョブ トリガーを指定します。
**Scheduledjobtrigger** オブジェクトを含む変数を入力するか、Get-JobTrigger コマンドなど、 **scheduledjobtrigger** オブジェクトを取得するコマンドまたは式を入力します。
また、パイプを使用して **scheduledjobtrigger** オブジェクトを **Set-jobtrigger** にパイプ処理することもできます。

複数のジョブ トリガーを指定すると、 **Set-JobTrigger** はすべてのジョブ トリガーに同じ変更を加えます。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -1 回
定期的ではない (1 回だけ) のスケジュールを指定します。

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

### -PassThru
変更されたジョブ トリガーを返します。
既定では、このコマンドレットによる出力はありません。

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

### -RandomDelay
スケジュールされた開始時刻のランダムな遅延を有効にし、遅延の最大値を設定します。
遅延の長さは、開始ごとに擬似ランダムに設定され、遅延なしから、このパラメーターの値で指定された時間の間で変動します。
既定値のゼロ (00:00:00) では、ランダムな遅延が無効になります。

New-TimeSpan コマンドレットによって返されるような timespan オブジェクトを入力するか、:: format に値を入力します。この値は、 \<hours\> \<minutes\> \<seconds\> timespan オブジェクトに自動的に変換されます。

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
Parameter Sets: (All)
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
たとえば、 **RepetitionInterval** の値が 5 分で、 *RepetitionDuration* の値が 2 時間の場合、ジョブは 2 時間の間 5 分おきにトリガーされます。

New-TimeSpan コマンドレットが返す timespan オブジェクトや、timespan オブジェクトに変換できる文字列 ("1:05:30" など) を入力します。

ジョブを無期限に実行するには、代わりに *RepeatIndefinitely* パラメーターを追加します。

ジョブ トリガーの繰り返し期間を過ぎる前にジョブを停止するには、 **RepetitionDuration** の値をゼロ (0) に設定します。

*Once* ジョブ トリガーの繰り返し期間または繰り返し間隔を変更するには、コマンドに **RepetitionInterval** と **RepetitionDuration** の両方のパラメーターを含める必要があります。
他の種類のジョブ トリガーの繰り返し期間または繰り返し間隔を変更するには、コマンドに *Once* 、 *At* 、 *RepetitionInterval* 、および *RepetitionDuration* パラメーターを含める必要があります。

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

### -RepetitionInterval
ジョブは、指定された時間間隔で繰り返し実行されます。
たとえば、このパラメーターの値が 2 時間の場合、ジョブは 2 時間おきにトリガーされます。
既定値の 0 では、ジョブは繰り返し実行されません。

New-TimeSpan コマンドレットが返す timespan オブジェクトや、timespan オブジェクトに変換できる文字列 ("1:05:30" など) を入力します。

**Once** ジョブ トリガーの繰り返し期間または繰り返し間隔を変更するには、コマンドに **RepetitionInterval** と **RepetitionDuration** の両方のパラメーターを含める必要があります。
他の種類のジョブ トリガーの繰り返し期間または繰り返し間隔を変更するには、コマンドに **Once** 、 **At** 、 **RepetitionInterval** 、および **RepetitionDuration** パラメーターを含める必要があります。

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

### -User
スケジュールされたジョブの *AtLogon* 開始をトリガーするユーザーを指定します。
ユーザーの名前を \<UserName\> または形式で入力 \<Domain\Username\> するか、アスタリスク () を入力して \* すべてのユーザーを表します。
既定値は、すべてのユーザーです。

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

### -毎週
週単位の定期的なジョブ スケジュールを指定します。
*週単位* のパラメーターセットの他のパラメーターを使用して、スケジュールの詳細を指定します。

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

### -WeeksInterval
週単位のジョブ スケジュールの実行間隔を週数で指定します。
たとえば、値が 3 の場合、スケジュールされたジョブは、1 週目、4 週目、7 週目というように 3 週おきに開始されます。
既定値は 1 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
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

### Microsoft. ScheduledJob. ScheduledJobTrigger
パイプを使用して複数のジョブトリガーを **設定-JobTrigger** にすることができます。

## 出力

### None または Microsoft. PowerShell. ScheduledJobTrigger
*Passthru* パラメーターを使用すると、 **Set-JobTrigger** は変更されたジョブ トリガーを返します。
それ以外の場合、このコマンドレットによる出力はありません。

## 注

* ジョブ トリガーには、スケジュールされたジョブにジョブ トリガーを関連付ける JobDefintion プロパティがあります。 スケジュールされたジョブのジョブ トリガーを変更すると、ジョブが変更されます。 Set-ScheduledJob コマンドを使用して、変更したトリガーをスケジュールされたジョブに適用する必要はありません。

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

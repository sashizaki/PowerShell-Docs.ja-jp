---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213440"
---
# Get-JobTrigger

## 概要
スケジュールされたジョブのジョブ トリガーを取得します。

## SYNTAX

### JobDefinition (既定値)

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### JobDefinitionId

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### JobDefinitionName

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## Description
**Get-JobTrigger** コマンドレットは、スケジュールされたジョブのジョブ トリガーを取得します。
このコマンドを使用すると、ジョブ トリガーを確認することや、パイプを使用してジョブ トリガーを他のコマンドレットに渡すことができます。

ジョブトリガーは、スケジュールされたジョブを開始するための定期的なスケジュールまたは条件を定義します。
ジョブ トリガーは、スケジュールされたジョブの一部であり、ディスクに単独で保存されるわけではありません。
ジョブ トリガーを取得するには、そのトリガーによって開始されるスケジュールされたジョブを指定します。

**Get-JobTrigger** コマンドレットのパラメーターを使用して、スケジュールされたジョブを特定します。
スケジュールされたジョブは、名前または識別番号で識別できます。または、Get-ScheduledJob コマンドレットによって返されるものなどの **Scheduledjob** オブジェクトを入力するか、パイプを使用して、 **jobtrigger** に渡します。

**Get-JobTrigger** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: スケジュールされたジョブ名でジョブトリガーを取得する

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

このコマンドは、 **Get JobTrigger** の *Name* パラメーターを使用して、スケジュールされたジョブ backupjob のジョブトリガーを取得します。

### 例 2: ID を使用してジョブトリガーを取得する

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

この例では、 **Get JobTrigger** の *ID* パラメーターを使用して、スケジュールされたジョブのジョブトリガーを取得します。

### 例 3: ジョブをパイプ処理してジョブトリガーを取得する

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

このコマンドは、名前に Backup または Archive を含むすべてのジョブのジョブトリガーを取得します。

### 例 4: リモートコンピューター上のジョブのジョブトリガーを取得する

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

このコマンドは、リモート コンピューター上のスケジュールされたジョブの 2 つのジョブ トリガーのうちの 1 つを取得します。

このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。
Get-ScheduledJob コマンドレットを使用して、スケジュールされたバックアップジョブを取得します。このジョブは、 **Get JobTrigger** コマンドレットにパイプします。
*TriggerID* パラメーターを使用して、2番目のトリガーのみを取得します。

### 例 5: すべてのジョブトリガーを取得する

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブのすべてのジョブ トリガーを取得します。

このコマンドは、Get-ScheduledJob を使用して、ローカルコンピューター上のスケジュールされたジョブを取得し、そのジョブを **Get JobTrigger** にパイプします。このトリガーは、スケジュールされた各ジョブ (存在する場合) のジョブトリガーを取得します。

スケジュールされたジョブの名前をジョブトリガーの表示に追加するには、Format-Table コマンドレットの計算されたプロパティ機能を使用します。
既定で表示されるジョブトリガーのプロパティに加えて、このコマンドは、スケジュールされたジョブの名前を表示する新しい ScheduledJob プロパティを作成します。

### 例 6: スケジュールされたジョブのジョブトリガーのプロパティを取得する

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

スケジュールされたジョブのジョブ トリガーは、ジョブの JobTriggers プロパティに格納されています。
この例では、 **Get JobTrigger** コマンドレットを使用してジョブトリガーを取得する方法について説明します。
結果は **Get-JobTrigger** コマンドレットを使用した場合と同じです。どちらの手法を使用しても変わりはありません。

### 例 7: ジョブトリガーを比較する

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

この例では、スケジュールされた 2 つのジョブのジョブ トリガーを比較する方法を示します。

## PARAMETERS

### -Id
スケジュールされたジョブの識別番号を指定します。
**Get-JobTrigger** は、指定されたスケジュールされたジョブのジョブ トリガーを取得します。

ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの識別番号を取得するには、Get-ScheduledJob コマンドレットを使用します。

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
スケジュールされたジョブを指定します。
**Scheduledjob** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **scheduledjob** オブジェクトを取得するコマンドまたは式を入力します。
また、 **Scheduledjob** オブジェクトを **Get jobtrigger** にパイプすることもできます。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
スケジュールされたジョブの名前を指定します。
**Get-JobTrigger** は、指定されたスケジュールされたジョブのジョブ トリガーを取得します。
ワイルドカードを利用できます。

ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの名前を取得するには、Get-ScheduledJob コマンドレットを使用します。

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TriggerId
指定されたジョブ トリガーを取得します。
スケジュールされたジョブの 1 つまたは複数のジョブ トリガーの ID を入力します。
*Name* 、 *ID* 、または *InputObject* パラメーターで指定したスケジュールされたジョブに複数のジョブ トリガーが設定されている場合に、このパラメーターを使用します。

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### ScheduledJobDefinition (Microsoft PowerShell)
スケジュールされたジョブを Get-ScheduledJob から **Get JobTrigger** にパイプすることができます。

## 出力

### Microsoft. ScheduledJob. ScheduledJobTrigger

## 注

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

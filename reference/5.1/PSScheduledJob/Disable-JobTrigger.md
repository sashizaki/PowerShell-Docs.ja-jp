---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213491"
---
# Disable-JobTrigger

## 概要
スケジュールされたジョブのジョブ トリガーを無効にします。

## SYNTAX

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Disable-JobTrigger** コマンドレットは、スケジュールされたジョブのジョブ トリガーを一時的に無効にします。
無効にしても、ジョブ トリガーのプロパティはすべて保持されますが、スケジュールされたジョブがジョブ トリガーによって開始されることはありません。

このコマンドレットを使用するには、Get-JobTrigger コマンドレットを使用してジョブトリガーを取得します。
次に、パイプを使用してジョブ トリガーを **Disable-JobTrigger** に渡すか、 *InputObject* パラメーターを使用します。

ジョブトリガーを無効にするには、 **jobtrigger** コマンドレットを使用して、ジョブトリガーの Enabled プロパティを $False に設定します。
ジョブトリガーを再度有効にするには、Enable-JobTrigger コマンドレットを使用します。これにより、ジョブトリガーの **Enabled** プロパティが $True に設定されます。
ジョブトリガーを無効にしても、スケジュールされたジョブ (Disable-ScheduledJob コマンドレットによって実行されるなど) は無効になりませんが、すべてのジョブトリガーを無効にすると、スケジュールされたジョブを無効にした場合と同じ結果になります。

スケジュールされたジョブを無効にした場合、またはスケジュールされたジョブのすべてのジョブトリガーを無効にした場合でも、Start-Job コマンドレットを使用してジョブを開始したり、無効にしたスケジュールされたジョブをテンプレートとして使用したりできます。

**Disable-scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: ジョブトリガーを無効にする

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

このコマンドは、ローカル コンピューター上のスケジュールされたジョブ Backup-Archives の最初のトリガー (ID=1) を無効にします。

このコマンドは、Get-JobTrigger コマンドレットを使用して、ジョブトリガーを取得します。
パイプライン演算子により、ジョブ トリガーを **Disable-JobTrigger** コマンドレットに渡して、無効にします。

### 例 2: すべてのジョブトリガーを無効にする

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

これらのコマンドは、スケジュールされた 2 つのジョブのすべてのジョブ トリガーを無効にし、結果を表示します。

### 例 3: リモートコンピューター上のスケジュールされたジョブのジョブトリガーを無効にする

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

このコマンドは、Server01 リモート コンピューター上のスケジュールされたジョブ DeployPackage の日単位のジョブ トリガーを無効にします。

このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。
Remote コマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブ DeployPackage のジョブトリガーを取得します。
パイプライン演算子は、ジョブトリガーを Where-Object コマンドレットに送信します。このコマンドレットは、1日のジョブトリガーのみを返します。
パイプライン演算子は、日単位のジョブトリガーを **無効** にして、無効にします。

## PARAMETERS

### -InputObject
無効にするジョブ トリガーを指定します。
**Scheduledjobtrigger** オブジェクトを含む変数を入力するか、Get-JobTrigger コマンドなど、 **scheduledjobtrigger** オブジェクトを取得するコマンドまたは式を入力します。
また、パイプを使用して **scheduledjobtrigger** オブジェクトを無効にし、 **-Jobtrigger を無効** にすることもできます。

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

### -PassThru
作業中の項目を表すオブジェクトを返します。
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

### -Confirm
コマンドレットの実行前に確認を求めるメッセージが表示されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
コマンドレットの実行時に発生する内容を示します。
このコマンドレットは実行されません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### Microsoft. ScheduledJob. ScheduledJobTrigger
パイプを使用してジョブ トリガーを **Disable-JobTrigger** に渡すことができます。

## 出力

### なし
このコマンドレットは出力を生成しません。

## 注

* **無効化-JobTrigger** は、既に無効になっているジョブトリガーを無効にした場合、エラーまたは警告を生成しません。

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

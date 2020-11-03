---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213443"
---
# Enable-JobTrigger

## 概要
スケジュールされたジョブのジョブ トリガーを有効にします。

## SYNTAX

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Enable-JobTrigger** コマンドレットは、Disable-JobTrigger コマンドレットを使用して無効になったジョブなど、スケジュールされたジョブのジョブトリガーを再度有効にします。
ジョブ トリガーを有効および再度有効にして、スケジュールされたジョブをすぐに開始することができます。Windows や Windows PowerShell を再起動する必要はありません。

このコマンドレットを使用するには、Get-JobTrigger コマンドレットを使用してジョブトリガーを取得します。
次に、パイプを使用してジョブトリガーを有効にし、 **-JobTrigger を有効** にするか、 *InputObject* パラメーターを使用します。

ジョブトリガーを有効にするには、 **jobtrigger** コマンドレットを使用して、ジョブトリガーの Enabled プロパティを $True に設定します。

**Enable-scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: ジョブトリガーを有効にする

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

このコマンドは、ローカル コンピューター上のスケジュールされたジョブ Backup-Archives の最初のトリガー (ID=1) を有効にします。

このコマンドは、Get-JobTrigger コマンドレットを使用して、ジョブトリガーを取得します。
パイプライン演算子により、ジョブ トリガーを **Enable-JobTrigger** コマンドレットに渡して、有効にします。

### 例 2: すべてのジョブトリガーを有効にする

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

このコマンドは、Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたジョブを取得します。
パイプライン演算子 (|) は、スケジュールされたジョブを Get-JobTrigger コマンドレットに送信します。このコマンドレットは、スケジュールされたジョブのすべてのジョブトリガーを取得します。
もう 1 つのパイプライン演算子により、ジョブ トリガーを **Enable-JobTrigger** コマンドレットに渡して、有効にします。

### 例 3: リモートコンピューター上のスケジュールされたジョブのジョブトリガーを有効にする

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

このコマンドは、Server01 リモート コンピューター上のスケジュールされたジョブ DeployPackage の AtLogon ジョブ トリガーを再度有効にします。

このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。
Remote コマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブ DeployPackage のジョブトリガーを取得します。
パイプライン演算子は、AtLogon ジョブトリガーのみを返す Where-Object コマンドレットにジョブトリガーを送信します。
パイプライン演算子は、AtLogon ジョブトリガーを **Enable JobTrigger** コマンドレットに送信します。これにより、これらのトリガーが有効になります。

### 例 4: 無効になっているジョブトリガーを表示する

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

このコマンドは、スケジュールされたすべてのジョブの無効になっているすべてのジョブ トリガーを表形式で表示します。
このようなコマンドを使用して、有効にする必要があるジョブ トリガーを見つけることができます。

このコマンドは、Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたジョブを取得します。
パイプライン演算子 (|) は、スケジュールされたジョブを Get-JobTrigger コマンドレットに送信します。このコマンドレットは、スケジュールされたジョブのすべてのジョブトリガーを取得します。
もう1つのパイプライン演算子によって Where-Object コマンドレットにジョブトリガーが送信されます。このコマンドレットは、ジョブトリガーの Enabled プロパティの値が (!) true ではない、無効になっているジョブトリガーのみを返します。

もう1つのパイプライン演算子は、無効になっているジョブトリガーを Format-Table コマンドレットに送信します。このコマンドレットには、テーブル内のジョブトリガーの選択されたプロパティが表示されます。
これらのプロパティには、ジョブ トリガーの JobDefinition プロパティのスケジュールされたジョブの名前を表示する新しい JobName プロパティが含まれています。

## PARAMETERS

### -InputObject
有効にするジョブトリガーを指定します。
**Scheduledjobtrigger** オブジェクトを含む変数を入力するか、Get-JobTrigger コマンドなど、 **scheduledjobtrigger** オブジェクトを取得するコマンドまたは式を入力します。
また、パイプを使用して **scheduledjobtrigger** オブジェクトを **有効** にすることもできます。

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
パイプを使用してジョブトリガーを **有効** にすることができます。

## 出力

### なし
このコマンドレットは出力を生成しません。

## 注

* **Enable-JobTrigger** は、既に有効になっているジョブトリガーを有効にすると、エラーまたは警告を生成しません。

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

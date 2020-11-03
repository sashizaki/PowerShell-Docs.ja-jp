---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213371"
---
# Unregister-ScheduledJob

## 概要
ローカル コンピューター上のスケジュールされたジョブを削除します。

## SYNTAX

### 定義 (既定)

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Unregister-ScheduledJob** コマンドレットは、ローカル コンピューターからスケジュールされたジョブを削除します。

スケジュールされたジョブを削除または登録 **解除** すると、\appdata\local\microsoft\windows\powershell\scheduledjobs ディレクトリに $home あるスケジュールされたジョブのディレクトリが削除されます。このディレクトリには、スケジュールされたジョブ、ジョブ実行履歴、およびすべてのジョブの結果を定義する XML ファイルが含まれています。
この操作では、タスク スケジューラからもジョブが削除されます。

**登録解除-ScheduledJob** は、Register-ScheduledJob コマンドレットを使用して作成されたスケジュールされたジョブのみを削除します。
タスク スケジューラで作成されたスケジュールされたジョブは削除しません。

ID または名前によってスケジュールされたジョブを削除するには、 **登録解除ジョブ** のパラメーターを使用します。また、スケジュールされたジョブを Get-ScheduledJob から **登録解除-scheduledjob** に渡すこともできます。

**登録解除-scheduledjob** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: スケジュールされたジョブを削除する

```
PS C:\> Unregister-ScheduledJob TestJob
```

このコマンドは、ローカル コンピューター上のスケジュールされたジョブ TestJob を削除します。

### 例 2: スケジュールされたすべてのジョブを削除する

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

この例は、ローカルコンピューター上のスケジュールされたすべてのジョブを削除する2つの異なるコマンドを示しています。

最初のコマンドは、Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたすべてのジョブを取得します。
パイプライン演算子 (|) により、スケジュールされたジョブを **Unregister-ScheduleJob** に渡して、それらのジョブを削除します。

2 番目のコマンドは、 *Unregister-ScheduledJob* の **Name** パラメーターにすべての値 (*) を指定して、スケジュールされたすべてのジョブを削除します。

どちらのコマンドも *Force* パラメーターを使用しているため、ジョブのインスタンスが実行されている場合でも、スケジュールされたジョブが削除されます。

### 例 3: リモートコンピューター上のスケジュールされたジョブを削除する

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

このコマンドは、Server01 リモートコンピューターで、名前が Test で始まるスケジュールされたジョブを削除します。
このコマンドは、Invoke-Command コマンドレットを使用して、Server02 コンピューター上で **登録解除-ScheduledJob** コマンドを実行します。

## PARAMETERS

### -Force
ジョブのインスタンスが実行されている場合でも、スケジュールされたジョブを削除します。
既定では、 **Unregister-ScheduledJob** は実行中のジョブを中断しません。

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
指定された識別番号 (ID) のスケジュールされたジョブを削除します。
コンピューター上のスケジュールされたジョブの ID を入力します。

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
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
また、パイプを使用して **Scheduledjob** オブジェクト **の登録を解除** することもできます。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
指定された名前のスケジュールされたジョブを削除します。
コンピューター上の 1 つまたは複数のスケジュールされたジョブの名前を入力します。
ワイルドカードを利用できます。

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
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

### ScheduledJobDefinition (Microsoft PowerShell)
パイプを使用して、スケジュールされたジョブを Unregister-ScheduledJob に渡すことができます。

## 出力

### なし
このコマンドレットは出力を生成しません。

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

---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213448"
---
# Enable-ScheduledJob

## 概要
スケジュールされたジョブを有効にします。

## SYNTAX

### 定義 (既定)

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Enable ScheduledJob** コマンドレットは、Disable-ScheduledJob コマンドレットを使用して無効になっているジョブなど、無効になっているスケジュールされたジョブを再度有効にします。
有効にされたジョブは、トリガーされると、自動的に実行されます。

スケジュールされたジョブを有効にするには、 **enable-scheduledjob** コマンドレットを使用して、スケジュールされたジョブの Enabled プロパティを $True に設定します。

**有効-scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: スケジュールされたジョブを有効にする

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

このコマンドは、ローカル コンピューター上の ID が 2 のスケジュールされたジョブを有効にします。
出力には、コマンドの結果が示されています。

### 例 2: すべてのスケジュールされたジョブを有効にする

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブを有効にします。
また、Get-ScheduledJob コマンドレットを使用してスケジュールされたすべてのジョブを取得し、 **enable-scheduledjob** コマンドレットを使用してそれらを有効にします。

**Enable-ScheduledJob** では、既に有効になっているスケジュールされたジョブを有効にした場合、警告やエラーは生成されません。そのため、すべてのスケジュールされたジョブを条件なしで有効にできます。

### 例 3: 選択したスケジュールされたジョブを有効にする

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

このコマンドは、ネットワーク接続を必要としないスケジュールされたジョブを有効にします。

このコマンドは、Get-ScheduledJob コマンドレットを使用して、コンピューター上のスケジュールされたすべてのジョブを取得します。
パイプライン演算子は、スケジュールされたジョブを Get-ScheduledJobOption コマンドレットに送信します。このコマンドレットは、スケジュールされた各ジョブのジョブオプションを取得します。
各ジョブ オプション オブジェクトには、関連付けられているスケジュールされたジョブが含まれている JobDefinition プロパティがあります。
JobDefinition プロパティを使用して、コマンドを完了します。

このコマンドは、パイプライン演算子 (|) を使用してジョブオプションを Where-Object コマンドレットに送信します。このコマンドレットは、 **Runno network** プロパティの値が True ($true) に設定されているスケジュールされたジョブオプションオブジェクトを選択します。
もう1つのパイプライン演算子は、選択したスケジュールされたジョブオプションオブジェクトを ForEach-Object コマンドレットに送信します。このコマンドレットは、各ジョブオプションオブジェクトの JobDefinition プロパティの値で、スケジュールされたジョブに対して **Enable-ScheduledJob** コマンドを実行します。

### 例 4: リモートコンピューターでスケジュールされたジョブを有効にする

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

このコマンドは、Srv01 と Srv10 の 2 台のリモート コンピューター上の名前に "test" が含まれているスケジュールされたジョブを有効にします。

このコマンドは、Invoke-Command コマンドレットを使用して、Srv01 コンピューターと Srv10 コンピューター上で **ScheduledJob** コマンドを実行します。
このコマンドは、 *Enable-ScheduledJob* の **Name** パラメーターを使用して、各コンピューター上のスケジュールされたジョブ Inventory を有効にします。

## PARAMETERS

### -Id
指定された識別番号 (ID) のスケジュールされたジョブを有効にします。
スケジュールされたジョブの ID を入力します。

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
有効にするスケジュールされたジョブを指定します。
**ScheduledJobDefinition** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **ScheduledJobDefinition** オブジェクトを取得するコマンドまたは式を入力します。
パイプを使用して **ScheduledJobDefinition** オブジェクトを有効にし、 **-Scheduledjob を有効** にすることもできます。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
指定された名前のスケジュールされたジョブを有効にします。
スケジュールされたジョブの名前を入力します。
ワイルドカードを利用できます。

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### ScheduledJobDefinition (Microsoft PowerShell)
パイプを使用してスケジュールされたジョブを有効にし、 **-ScheduledJob を有効** にすることができます。

## 出力

### [なし] または [ScheduledJobDefinition]
**Passthru** パラメーターを使用すると、 **Enable-ScheduledJob** は有効にしたスケジュールされたジョブを返します。
それ以外の場合、このコマンドレットによる出力はありません。

## 注

* **Enable-ScheduledJob** を使用して、既に有効になっているスケジュールされたジョブを有効にすると、警告やエラーは生成されません。

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

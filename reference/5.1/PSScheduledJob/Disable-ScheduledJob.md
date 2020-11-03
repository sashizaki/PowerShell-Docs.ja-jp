---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213475"
---
# Disable-ScheduledJob

## 概要
スケジュールされたジョブを無効にします。

## SYNTAX

### 定義 (既定)

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Disable-ScheduledJob** コマンドレットは、スケジュールされたジョブを一時的に無効にします。
無効にしても、ジョブのプロパティはすべて保持され、ジョブ トリガーは無効になりません。ただし、スケジュールされたジョブはトリガーされても自動的に開始されることはありません。
無効なスケジュールされたジョブを開始するには、Start-Job コマンドレットを使用するか、無効なスケジュールされたジョブをテンプレートとして使用します。

スケジュールされたジョブを無効にするために、 **Disable-ScheduledJob** コマンドレットは、スケジュールされたジョブの **Enabled** プロパティを False ($false) に設定します。
スケジュールされたジョブを再度有効にするには、Enable-ScheduledJob コマンドレットを使用します。

**Disable-scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: スケジュールされたジョブを無効にする

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

このコマンドは、ローカル コンピューター上の ID が 2 のスケジュールされたジョブを無効にします。
出力には、コマンドの結果が示されています。

### 例 2: すべてのスケジュールされたジョブを無効にする

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブを無効にします。
また、Get-ScheduledJob コマンドレットを使用してスケジュールされたすべてのジョブを取得し、 **無効化-scheduledjob** コマンドレットを使用してそれらを無効にします。

Enable-ScheduledJob コマンドレットを使用してスケジュールされたジョブを再度有効にし、Start-Job コマンドレットを使用して、無効になっているスケジュールされたジョブを実行できます。

無効 **-ScheduledJob** は、既に無効になっているスケジュールされたジョブを無効にした場合に、警告やエラーを生成しません。そのため、すべてのスケジュールされたジョブを条件なしで無効にすることができます。

### 例 3: 選択したスケジュールされたジョブを無効にする

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

このコマンドは、資格情報が含まれていないスケジュールされたジョブを無効にします。
資格情報が含まれていないジョブは、そのジョブを作成したユーザーのアクセス許可で実行されます。

このコマンドは、Get-ScheduledJob コマンドレットを使用して、コンピューター上のスケジュールされたすべてのジョブを取得します。
パイプライン演算子は、スケジュールされたジョブを Where-Object コマンドレットに送信します。これにより、資格情報のないスケジュールされたジョブが選択されます。
このコマンドは、not (!) 演算子を使用し、スケジュールされたジョブの Credential プロパティを参照します。
もう 1 つのパイプライン演算子により、選択されたスケジュールされたジョブを **Disable-ScheduledJob** コマンドレットに渡して、無効にします。

### 例 4: リモートコンピューター上のスケジュールされたジョブを無効にする

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

このコマンドは、2 台のリモート コンピューター Srv01 と Srv10 上のスケジュールされたジョブ TestJob を無効にします。

このコマンドは、Invoke-Command コマンドレットを使用して、Srv01 および Srv10 コンピューターで無効になっている **ScheduledJob** コマンドを実行します。
このコマンドは、 *Disable-ScheduledJob* の **Name** パラメーターを使用して、各コンピューター上のスケジュールされたジョブ TestJob を選択します。

### 例 5: スケジュールされたジョブをグローバル ID で無効にする

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

この例では、グローバル識別子を使用して、スケジュールされたジョブを無効にする方法を示します。
スケジュールされたジョブの GlobalID プロパティの値は一意識別子 (GUID) です。
複数のコンピューター上のスケジュールされたジョブを無効にする場合など、正確性が求められる場合に、GlobalID 値を使用します。

## PARAMETERS

### -Id
指定された識別番号 (ID) のスケジュールされたジョブを無効にします。
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
無効にするスケジュールされたジョブを指定します。
**ScheduledJobDefinition** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **ScheduledJobDefinition** オブジェクトを取得するコマンドまたは式を入力します。
パイプを使用して **ScheduledJobDefinition** オブジェクトを無効にし、 **-Scheduledjob を無効** にすることもできます。

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
指定された名前のスケジュールされたジョブを無効にします。
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
パイプを使用して、スケジュールされたジョブを **Disable-ScheduledJob** に渡すことができます。

## 出力

### [なし] または [ScheduledJobDefinition]
**Passthru** パラメーターを使用すると、 **Disable-ScheduledJob** は無効にしたスケジュールされたジョブを返します。
それ以外の場合、このコマンドレットによる出力はありません。

## 注

* **無効-ScheduledJob** を使用して、既に無効になっているスケジュールされたジョブを無効にすると、警告やエラーは生成されません。

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

---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213411"
---
# Remove-JobTrigger

## 概要
スケジュールされたジョブからジョブトリガーを削除します。

## SYNTAX

### JobDefinition (既定値)

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### JobDefinitionId

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### JobDefinitionName

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## Description
Delete **JobTrigger** コマンドレットは、スケジュールされたジョブからジョブトリガーを削除します。

ジョブトリガーは、スケジュールされたジョブを開始するための定期的なスケジュールまたは条件を定義します。
ジョブトリガーを管理するには、New-JobTrigger、Add JobTrigger、Set JobTrigger、および Set-ScheduledJob コマンドレットを使用します。

トリガーを削除するスケジュールされたジョブを特定するには、 *Remove-JobTrigger* の *Name* 、 *ID* 、または **InputObject** パラメーターを使用します。
削除するジョブトリガーを特定するには、 *TriggerID* パラメーターを使用します。
既定では、 **Remove-JobTrigger** は、スケジュールされたジョブのすべてのジョブ トリガーを削除します。

**削除-JobTrigger** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: すべてのジョブトリガーを削除する

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

このコマンドは、名前が Test で始まるスケジュールされたジョブからすべてのジョブトリガーを削除します。

### 例 2: 選択したジョブトリガーを削除する

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

このコマンドは、スケジュールされたジョブ BackupArchive から 3 番目のトリガー (ID = 3) のみを削除します。

### 例 3: すべてのスケジュールされたジョブから AtStartup ジョブトリガーを削除する

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

この関数は、ローカル コンピューター上のすべてのジョブからすべての AtStartup ジョブ トリガーを削除します。
関数を使用するには、セッションで関数を実行し、「」と入力し `Delete-AtStartup` ます。

Delete-AtStartup 関数には、1 つのコマンドが含まれています。
このコマンドは、Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたジョブを取得します。
パイプライン演算子 (|) によって、スケジュールされたジョブが Get-JobTrigger コマンドレットに送信されます。このコマンドレットは、スケジュールされた各ジョブからすべてのジョブトリガーを取得します。
パイプライン演算子は、ジョブトリガーを Where-Object コマンドレットに送信します。このコマンドレットは、ジョブトリガーの Frequency プロパティの値が AtStartup と等しいジョブトリガーを選択します。

**Jobtrigger** オブジェクトには、トリガーされるスケジュールされたジョブを含む **JobDefinition** プロパティがあります。
このコマンドの残りの部分では、その便利な機能を使用しています。

パイプライン演算子は、AtStartup ジョブトリガーを ForEach-Object コマンドレットに送信します。このコマンドレットは、各 AtStartup トリガーで **Remove jobtrigger** コマンドを実行します。
*Remove-JobTrigger* の **InputObject** パラメーターの値は、ジョブ トリガーの JobDefinition プロパティに格納されているスケジュールされたジョブです。
*TriggerID* パラメーターの値は、ジョブ トリガーの ID プロパティに格納されている ID です。

### 例 4: リモートのスケジュールされたジョブからジョブトリガーを削除する

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

このコマンドは、Server01 コンピューター上の Inventory ジョブから最初のジョブ トリガーを削除します。

このコマンド **は、Server01 コマンドレットを** 使用して、コンピューター上で **Remove jobtrigger** コマンドレットを実行します。
**削除 JobTrigger** コマンドレットは、 *ID* パラメーターを使用して、スケジュールされたジョブのインベントリを識別し、 *TriggerID* パラメーターを使用して最初のトリガーを指定します。
*ID* パラメーターは、スケジュールされた複数のジョブが同じ名前または類似した名前を持つ場合に特に便利です。

## PARAMETERS

### -Id
スケジュールされたジョブの識別番号を指定します。
**Remove-JobTrigger** は、指定されたスケジュールされたジョブからジョブ トリガーを削除します。

ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの識別番号を取得するには、Get-ScheduledJob コマンドレットを使用します。

```yaml
Type: System.Int32[]
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
また、パイプを使用して **Scheduledjob** オブジェクトを **削除し、-Jobtrigger を削除** することもできます。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
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
**Remove-JobTrigger** は、指定されたスケジュールされたジョブからジョブ トリガーを削除します。
ワイルドカードを利用できます。

ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの名前を取得するには、Get-ScheduledJob コマンドレットを使用します。

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TriggerId
指定されたジョブ トリガーのみを削除します。
既定では、 **Remove-JobTrigger** は、スケジュールされたジョブからすべてのトリガーを削除します。
スケジュールされたジョブに複数のジョブ トリガーが設定されている場合に、このパラメーターを使用します。

スケジュールされたジョブの 1 つまたは複数のジョブ トリガーの ID を入力します。
複数のスケジュールされたジョブを指定した場合、 **-JobTrigger を削除** すると、指定した ID を持つジョブトリガーがすべてのスケジュールされたジョブから削除されます。

```yaml
Type: System.Int32[]
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

### ScheduledJobDefinition (Microsoft PowerShell)
パイプを使用して、スケジュールされたジョブを **Remove-JobTrigger** コマンドレットに渡すことができます。

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

---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214664"
---
# Limit-EventLog

## 概要
イベント ログのサイズおよびエントリの期間を制限するイベント ログ プロパティを設定します。

## SYNTAX

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Limit-EventLog** コマンドレットは、従来のイベントログの最大サイズ、各イベントを保持する必要がある期間、およびログが最大サイズに達したときの動作を設定します。
このコマンドレットを使用して、ローカル コンピューターまたはリモート コンピューター上のイベント ログを制限できます。

EventLog という名詞を含むコマンドレット (EventLog コマンドレット) は、従来のイベント ログでのみ有効です。
Windows Vista 以降のバージョンで Windows イベント ログ技術を使用しているログからイベントを取得するには、Get-WinEvent を使用します。

## 例

### 例 1: イベントログのサイズを大きくする

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

このコマンドは、ローカル コンピューター上の Windows PowerShell イベント ログの最大サイズを 20,480 バイト (20 KB) に増やします。

### 例 2: 指定した期間のイベントログを保持する

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

このコマンドは、Server01 コンピューターと Server02 コンピューター上のセキュリティ ログのイベントを少なくとも 7 日間確実に保持します。

### 例 3: すべてのイベントログのオーバーフローアクションを変更する

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

この例では、ローカルコンピューター上のすべてのイベントログのオーバーフローアクションを OverwriteOlder に変更します。

最初のコマンドは、ローカル コンピューター上のすべてのログのログ名を取得します。
2 番目のコマンドはオーバーフロー アクションを設定します。
3 番目のコマンドは結果を表示します。

## PARAMETERS

### -ComputerName
リモートコンピューターを指定します。
既定値はローカル コンピューターです。

リモートコンピューターの NetBIOS 名、インターネットプロトコル (IP) アドレス、または完全修飾ドメイン名 (FQDN) を入力します。
ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。

このパラメーターは、Windows PowerShell リモート処理に依存しません。
コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **Limit-EventLog** の *ComputerName* パラメーターを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
イベント ログを指定します。
1 つ以上のイベント ログのログ名 (LogDisplayName ではなく Log プロパティの値) をコンマ区切りで入力します。
ワイルドカード文字は使用できません。
このパラメーターは必須です。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumSize
イベント ログの最大サイズをバイト単位で指定します。
64 キロバイト (KB) ～ 4 ギガバイト (GB) の値を入力します。
値は 64 KB (65536) で割り切れる必要があります。

このパラメーター **は、従来** のイベントログを表す system.string オブジェクトの **maximumkilobytes** プロパティの値を指定します。

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowAction
イベント ログが最大サイズに達したときのアクションを指定します。

このパラメーターの有効値は、次のとおりです。

- DoNotOverwrite: 既存のエントリは保持され、新しいエントリは破棄されます。
- OverwriteAsNeeded: 新しいエントリごとに、最も古いエントリが上書きされます。
- OverwriteOlder: 新しいイベントは、 **MinimumRetentionDays** プロパティで指定された値よりも古いイベントを上書きします。 **MinimumRetentionDays** プロパティ値によって指定されたよりも古いイベントがない場合、新しいイベントは破棄されます。

このパラメーターは、従来のイベントログを表す OverflowAction **オブジェクトの** **OverflowAction** プロパティの値を指定します。

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionDays
イベントをイベント ログに残す必要がある最小日数を指定します。

このパラメーターは、従来のイベントログを表す MinimumRetentionDays **オブジェクトの** **MinimumRetentionDays** プロパティの値を指定します。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

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

### なし
パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### なし
このコマンドレットは出力を生成しません。

## 注

* Windows Vista 以降のバージョンの Windows でこのコマンドレットを使用するには、[管理者として実行] オプションを使用して Windows PowerShell を開きます。

  このコマンドレットは、従来のイベントログを表す **system.string オブジェクトの** プロパティを変更します。
イベントログのプロパティの現在の設定を表示するには、「」と入力 `Get-EventLog -List` します。

*

## 関連リンク

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)

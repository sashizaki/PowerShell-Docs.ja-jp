---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214555"
---
# Remove-EventLog

## 概要
イベント ログを削除またはイベント ソースの登録を解除します。

## SYNTAX

### 既定値 (既定値)

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### source

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
EventLog コマンドレットは、ローカルまたはリモートのコンピューターからイベントログファイルを削除し、ログのすべてのイベントソースの登録を **解除** します。
このコマンドレットを使用して、イベント ログを削除せずにイベント ソースの登録を解除することもできます。

**Eventlog** 名詞を含むコマンドレット ( **eventlog** コマンドレット) は、従来のイベントログでのみ機能します。
Windows Vista 以降のバージョンの Windows オペレーティングシステムで Windows イベントログテクノロジを使用するログからイベントを取得するには、Get-WinEvent を使用します。

注意: このコマンドレットでは、オペレーティングシステムのイベントログを削除できます。これにより、アプリケーションのエラーや予期しないシステムの動作が発生する可能性があります。

## 例

### 例 1: ローカルコンピューターからイベントログを削除する

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

このコマンドは、ローカル コンピューターから MyLog イベント ログを削除し、そのイベント ソースの登録を解除します。

### 例 2: 複数のコンピューターからイベントログを削除する

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

このコマンドは、ローカルコンピューターと Server01 および Server02 リモートコンピューターから MyLog イベントログと TestLog イベントログを削除します。
コマンドは、これらのログのイベント ソースの登録も解除します。

### 例 3: イベントソースを削除する

```
PS C:\> Remove-EventLog -Source "MyApp"
```

このコマンドを実行すると、ローカル コンピューター上のログから MyApp イベント ソースが削除されます。
コマンドが完了すると、MyApp プログラムはイベントログに書き込むことができません。

### 例 4: イベントログを削除してアクションを確認する

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

これらのコマンドは、コンピューター上のイベントログの一覧を表示し、イベント **削除** コマンドが正常に実行されたことを確認する方法を示しています。

### 例 5: イベントソースを削除してアクションを確認する

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

これらのコマンドは、Get-WmiObject コマンドレットを使用して、ローカル コンピューター上のイベント ソースの一覧を表示します。
これらのコマンドを実行して、コマンドの成功を確認したり、イベント ソースを削除したりすることができます。

最初のコマンドは、ローカル コンピューター上の TestLog イベント ログのイベント ソースを取得します。
MyApp はソースの 1 つです。

2番目のコマンドは、 **削除** イベントの *source* パラメーターを使用して、MyApp イベントソースを削除します。

3 番目のコマンドは、最初のコマンドと同一です。
MyApp イベント ソースが削除されたことを示します。

## PARAMETERS

### -ComputerName
リモート コンピューターを指定します。
既定値はローカル コンピューターです。

リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。
ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。

このパラメーターは、Windows PowerShell リモート処理に依存しません。
コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **削除イベントログ** の *ComputerName* パラメーターを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
イベント ログを指定します。
1つ以上のイベントログのログ名をコンマで区切って入力します。
ログ名は *Logdisplayname* ではなく **log** プロパティの値であり、ワイルドカード文字は使用できません。
このパラメーターは必須です。

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
このコマンドレットが登録を解除するイベントソースを指定します。
実行可能ファイル名ではなく、ソース名をコンマで区切って入力します。

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

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
このコマンドレットによる戻り値はありません。

## 注

* Windows Vista 以降のバージョンの Windows オペレーティングシステムで **削除イベントログ** を使用するには、[管理者として実行] オプションを使用して windows PowerShell を起動します。

  イベント ログを削除した後、ログを再作成する場合、同じイベント ソースを登録することはできません。
エントリを元のログに書き込むためにイベント ソースを使用したアプリケーションは、新しいログに書き込むことはできません。

* 特定ログのイベント ソースの登録を解除すると、エントリの他のイベント ログへの書き込みが防止されます。

## 関連リンク

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)

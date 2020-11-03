---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: cae34c4cf942d9aa4abb9a2d716ef9854f70de2e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214296"
---
# Write-EventLog

## 概要
イベントをイベント ログに書き込みます。

## SYNTAX

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## Description
**書き込み** イベントレットは、イベントをイベントログに書き込みます。

イベントをイベント ログに書き込むには、イベント ログがコンピューター上に存在し、イベント ソースがイベント ログに登録されている必要があります。

**Eventlog** 名詞を含むコマンドレット ( **eventlog** コマンドレット) は、従来のイベントログでのみ機能します。
Windows Vista 以降のバージョンの windows オペレーティングシステムで Windows イベントログテクノロジを使用するログからイベントを取得するには、Get-WinEvent コマンドレットを使用します。

## 例

### 例 1: アプリケーションイベントログにイベントを書き込む

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

このコマンドは、MyApp ソースのイベントをアプリケーション イベント ログに書き込みます。

### 例 2: リモートコンピューターのアプリケーションイベントログにイベントを書き込む

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

このコマンドは、MyApp ソースのイベントを Server01 リモート コンピューター上のアプリケーション イベント ログに書き込みます。

## PARAMETERS

### -カテゴリ
イベントのタスク カテゴリを指定します。
イベント ログのカテゴリ メッセージ ファイルに記載された文字列に関連付けられた整数を入力します。

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
リモート コンピューターを指定します。
既定値はローカル コンピューターです。

リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。

このパラメーターは、Windows PowerShell リモート処理に依存しません。
コンピューターがリモートコマンドを実行するように構成されていない場合でも、Get-EventLog コマンドレットの *ComputerName* パラメーターを使用できます。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntryType
イベントのエントリの種類を指定します。
このパラメーターに指定できる値は、Error、Warning、Information、SuccessAudit、および FailureAudit です。
既定値は Information です。

値の説明については、MSDN ライブラリの「 [詳細列挙体](https://go.microsoft.com/fwlink/?LinkId=143599) 」を参照してください。

```yaml
Type: System.Diagnostics.EventLogEntryType
Parameter Sets: (All)
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventId
イベント識別子を指定します。
このパラメーターは必須です。
*EventId* パラメーターの最大値は65535です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ID, EID

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
イベントを書き込むログの名前を指定します。
ログ名を入力します。
ログ名は **Logdisplayname** ではなく **log** プロパティの値です。
ワイルドカード文字は使用できません。
このパラメーターは必須です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -メッセージ
イベント メッセージを指定します。
このパラメーターは必須です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MSG

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RawData
イベントに関連付けるバイナリ データをバイト単位で指定します。

```yaml
Type: System.Byte[]
Parameter Sets: (All)
Aliases: RD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
イベント ソースを指定します。通常は、イベントをログに書き込むアプリケーションの名前です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし
パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### EventLogEntry
このコマンドレットは、ログ内のイベントを表すオブジェクトを返します。

## 注

* **書き込みイベントログ** を使用するには、[管理者として実行] オプションを使用して Windows PowerShell を起動します。

*

## 関連リンク

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)

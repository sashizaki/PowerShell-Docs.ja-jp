---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215467"
---
# Get-EventLog

## 概要
ローカルコンピューターまたはリモートコンピューター上のイベントログまたはイベントログの一覧のイベントを取得します。

## SYNTAX

### LogName (既定値)

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### List

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## Description

`Get-EventLog`コマンドレットは、ローカルコンピューターとリモートコンピューターからイベントとイベントログを取得します。 既定では、は `Get-EventLog` ローカルコンピューターからログを取得します。 リモートコンピューターからログを取得するには、 **ComputerName** パラメーターを使用します。

パラメーターとプロパティ値を使用して、 `Get-EventLog` イベントを検索できます。 コマンドレットは、指定されたプロパティ値に一致するイベントを取得します。

名詞が含まれている PowerShell コマンドレット `EventLog` は、Windows クラシックイベントログ (アプリケーション、システム、セキュリティなど) でのみ機能します。 Windows Vista 以降の windows バージョンで windows イベントログテクノロジを使用するログを取得するには、を使用し `Get-WinEvent` ます。

> [!NOTE]
> `Get-EventLog` 非推奨の Win32 API を使用します。 結果が正確でない可能性があります。 `Get-WinEvent`代わりにコマンドレットを使用してください。

## 例

### 例 1: ローカルコンピューター上のイベントログを取得する

この例では、ローカルコンピューターで使用できるイベントログの一覧を表示します。 Log 列の名前は、イベントを検索するログを指定するために、 **LogName** パラメーターと共に使用されます。

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

`Get-EventLog`コマンドレットは **List** パラメーターを使用して、使用可能なログを表示します。

### 例 2: ローカルコンピューターのイベントログから最近のエントリを取得する

この例では、システムイベントログから最新のエントリを取得します。

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムイベントログを指定します。 最新 **のパラメーターは、最新** の5つのイベントを返します。

### 例 3: イベントログ内の特定の数のエントリのすべてのソースを検索する

この例では、システムイベントログの最新のエントリ1000に含まれているすべてのソースを検索する方法を示します。

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。 最新 **のパラメーターは** 、最新の1000のイベントを選択します。 イベントオブジェクトは変数に格納され `$Events` ます。 オブジェクトは、パイプラインを介して `$Events` コマンドレットに送信され `Group-Object` ます。
`Group-Object`**Property** パラメーターを使用して、ソースごとにオブジェクトをグループ化し、各ソースのオブジェクト数をカウントします。 **Noelement** パラメーターは、グループメンバーを出力から削除します。
コマンドレットでは、 `Sort-Object` **Property** パラメーターを使用して、各ソース名のカウントで並べ替えます。
**降順** のパラメーターは、リストを降順で並べ替えます。

### 例 4: 特定のイベントログからエラーイベントを取得する

この例では、システムイベントログからエラーイベントを取得します。

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。 **Entrytype** パラメーターは、エラーイベントのみを表示するようにイベントをフィルター処理します。

### 例 5: InstanceId とソース値を使用してイベントログからイベントを取得する

この例では、特定の InstanceId とソースのシステムログからイベントを取得します。

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。 **InstanceID** パラメーターは、指定されたインスタンス ID を持つイベントを選択します。 **Source** パラメーターは、イベントプロパティを指定します。

### 例 6: 複数のコンピューターからイベントを取得する

このコマンドは、Server01、Server02、および Server03 の3台のコンピューター上のシステムイベントログからイベントを取得します。

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。 **ComputerName** パラメーターでは、コンマ区切りの文字列を使用して、イベントログを取得するコンピューターを一覧表示します。

### 例 7: メッセージ内の特定の単語を含むすべてのイベントを取得する

このコマンドは、イベントのメッセージ内の特定の単語を含む、システムイベントログ内のすべてのイベントを取得します。 指定した **メッセージ** パラメーターの値がメッセージのコンテンツに含まれていても、PowerShell コンソールに表示されない可能性があります。

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムイベントログを指定します。 **Message** パラメーターは、各イベントのメッセージフィールドで検索する単語を指定します。

### 例 8: イベントのプロパティ値を表示する

この例では、イベントのすべてのプロパティと値を表示する方法を示します。

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムイベントログを指定します。 最新 **のパラメーターは** 、最新のイベントオブジェクトを選択します。 オブジェクトは変数に格納され `$A` ます。 変数内のオブジェクトは、パイプラインを介して `$A` コマンドレットに送信され `Select-Object` ます。
`Select-Object`**Property** パラメーターをアスタリスク () と共に使用して `*` 、すべてのオブジェクトのプロパティを選択します。

### 例 9: ソースとイベント ID を使用してイベントログからイベントを取得する

この例では、指定されたソースとイベント ID のイベントを取得します。

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してアプリケーションイベントログを指定します。 **Source** パラメーターは、アプリケーション名である Outlook を指定します。 オブジェクトは、パイプラインを介してコマンドレットに送信され `Where-Object` ます。 コマンドレットは、パイプライン内の各オブジェクトに対して、変数を使用して、 `Where-Object` `$_.EventID` イベント ID プロパティを指定された値と比較します。 オブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。 `Select-Object`**プロパティ** パラメーターを使用して、PowerShell コンソールに表示するプロパティを選択します。

### 例 10: イベントを取得し、プロパティでグループ化する

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

`Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。 **UserName** パラメーターには、 `*` ユーザー名の一部を指定するためのアスタリスク () ワイルドカードが含まれています。 イベントオブジェクトは、パイプラインを介してコマンドレットに送信され `Group-Object` ます。 `Group-Object`**Property** パラメーターを使用し **て、ユーザー名プロパティを** 使用してオブジェクトをグループ化し、各ユーザー名のオブジェクトの数をカウントするように指定します。 **Noelement** パラメーターは、グループメンバーを出力から削除します。 オブジェクトは、パイプラインを介してコマンドレットに送信され `Select-Object` ます。
`Select-Object`**プロパティ** パラメーターを使用して、PowerShell コンソールに表示するプロパティを選択します。

### 例 11: 特定の日付と時刻の範囲内に発生したイベントを取得する

この例では、指定された日付と時刻の範囲について、システムイベントログからエラーイベントを取得します。 **Before** および **After** パラメーターは、日付と時刻の範囲を設定しますが、出力から除外されます。

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

この `Get-Date` コマンドレットで **は、date** パラメーターを使用して日付と時刻を指定します。 **DateTime** オブジェクトは、変数と変数に格納され `$Begin` `$End` ます。 `Get-EventLog`コマンドレットでは、 **LogName** パラメーターを使用してシステムログを指定します。 **Entrytype** パラメーターは、エラーイベントの種類を指定します。 日付と時刻の範囲は、 **After** パラメーターと変数、および `$Begin` **Before** パラメーターと variable によって設定され `$End` ます。

## PARAMETERS

### -After

指定した日付と時刻の後に発生したイベントを取得します。 **After** パラメーターの日付と時刻は、出力から除外されます。 コマンドレットによって返される値など、 **DateTime** オブジェクトを入力し `Get-Date` ます。

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsBaseObject

このコマンドレットが各イベントの標準 **EventLogEntry** オブジェクトを返すことを示します。 このパラメーターを指定しない場合、は、 `Get-EventLog` 追加 **の eventlogname** 、 **Source** 、および **InstanceId** プロパティを持つ拡張 **PSObject** オブジェクトを返します。

このパラメーターの効果を確認するには、イベントをコマンドレットにパイプ処理 `Get-Member` し、結果の **TypeName** 値を調べます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsString

このコマンドレットが、オブジェクトではなく文字列として出力を返すことを示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Before

指定した日付と時刻の前に発生したイベントを取得します。 **Before** パラメーターの日付と時刻は、出力から除外されます。 コマンドレットによって返される値など、 **DateTime** オブジェクトを入力し `Get-Date` ます。

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

このパラメーターは、リモートコンピューターの NetBIOS 名、インターネットプロトコル (IP) アドレス、または完全修飾ドメイン名 (FQDN) を指定します。

**ComputerName** パラメーターが指定されていない場合、は `Get-EventLog` 既定でローカルコンピューターになります。 パラメーターでは、ドット ( `.` ) を指定してローカルコンピューターを指定することもできます。

**ComputerName** パラメーターは、Windows PowerShell リモート処理に依存しません。 `Get-EventLog`コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターと共にを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntryType

文字列配列として、このコマンドレットが取得するイベントのエントリの種類を指定します。

このパラメーターの有効値は、次のとおりです。

- エラー
- Information
- FailureAudit
- SuccessAudit
- 警告

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -インデックス

イベントログから取得するインデックス値を指定します。 パラメーターは、値のコンマ区切りの文字列を受け入れます。

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

イベントログから取得するインスタンス Id を指定します。 パラメーターは、値のコンマ区切りの文字列を受け入れます。

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -List

コンピューター上のイベントログの一覧を表示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

1つのイベントログの名前を指定します。 ログ名を検索するには、を使用 `Get-EventLog -List` します。 ワイルドカード文字を使用できます。 このパラメーターは必須です。

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -メッセージ

イベントメッセージに文字列を指定します。 このパラメーターを使用して、特定の単語または語句を含むメッセージを検索できます。 ワイルドカードを使用できます。

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -最新

は、最新のイベントから開始し、指定された数のイベントを取得します。 たとえば、イベントの数が必要です `-Newest 100` 。 返されるイベントの最大数を指定します。

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

このコマンドレットが取得するログに書き込まれたソースを文字列配列として指定します。 ワイルドカードを使用できます。

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -UserName

イベントに関連付けられているユーザー名を文字列配列として指定します。 名前または名前パターンを入力します (、、など) `User01` `User*` `Domain01\User*` 。 ワイルドカードを使用できます。

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

入力をにパイプすることはできません `Get-EventLog` 。

## 出力

### EventLogEntry。 システムの診断。 System.String

**LogName** パラメーターを指定した場合、出力は **EventLogEntry** オブジェクトのコレクションになります。

**List** パラメーターのみを指定した場合、出力は、 **system.string オブジェクトの** コレクションになります。

**List** パラメーターと **asstring** パラメーターの両方を指定した場合、出力は **system.string** オブジェクトのコレクションになります。

## 注

コマンドレット `Get-EventLog` と `Get-WinEvent` は、Windows プレインストール環境 (Windows PE) ではサポートされていません。

## 関連リンク

[Clear-EventLog](Clear-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)

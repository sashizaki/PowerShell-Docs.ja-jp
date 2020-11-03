---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "93219048"
---
# Register-WmiEvent

## 概要
Windows Management Instrumentation (WMI) イベントにサブスクライブします。

## SYNTAX

### クラス (既定値)

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### query

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## Description

この `Register-WmiEvent` コマンドレットは、ローカルコンピューターまたはリモートコンピューター上の Windows Management Instrumentation (WMI) イベントをサブスクライブします。

サブスクライブされた WMI イベントの発生時には、リモート コンピューター上で発生した場合でもローカル セッションのイベント キューに追加されます。 イベントキュー内のイベントを取得するには、コマンドレットを使用し `Get-Event` ます。

のパラメーターを使用して、 `Register-WmiEvent` リモートコンピューター上のイベントをサブスクライブしたり、キュー内のイベントを識別するのに役立つイベントのプロパティ値を指定したりすることができます。 **Action** パラメーターを使用して、サブスクライブしたイベントが発生したときに実行するアクションを指定することもできます。

イベントにサブスクライブするとき、イベント サブスクライバーがセッションに追加されます。 セッションのイベント サブスクライバーを取得するには、`Get-EventSubscriber` コマンドレットを使用します。 サブスクリプションをキャンセルするには、`Unregister-Event` コマンドレットを使用して、セッションからイベント サブスクライバーを削除します。

Windows PowerShell 3.0 で導入された新しい Common Information Model (CIM) コマンドレットでは、WMI コマンドレットと同じタスクを実行します。 CIM コマンドレットは、WS-Management (WSMan) 標準と CIM 標準に準拠しています。これにより、コマンドレットは、Windows オペレーティングシステムを実行するコンピューターと他のオペレーティングシステムを実行するコンピューターを管理する同じ手法を使用できます。 を使用する代わり `Register-WmiEvent` に、 [CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) コマンドレットを使用することを検討してください。

## 例

### 例 1: クラスによって生成されたイベントをサブスクライブする

このコマンドは、 **Win32_ProcessStartTrace** クラスによって生成されたイベントをサブスクライブします。 プロセスが開始されるたびに、このクラスによってイベントが発生します。

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### 例 2: プロセスの作成イベントをサブスクライブする

このコマンドは、クエリを使用して、Win32_process インスタンス作成イベントにサブスクライブします。

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### 例 3: アクションを使用してイベントに応答する

この例は、イベントに応えるアクションの使用方法を示しています。 この場合、プロセスの開始時に、 `Start-Process` 現在のセッションのすべてのコマンドが XML ファイルに書き込まれます。

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

**Action** パラメーターを使用すると、は `Register-WmiEvent` イベントアクションを表すバックグラウンドジョブを返します。 やなどの **ジョブ** コマンドレットを使用して、 `Get-Job` `Receive-Job` イベントジョブを管理できます。

詳細については、「about_Jobs」を参照してください。

### 例 4: リモートコンピューターのイベントに登録する

この例では、Server01 リモート コンピューターのイベントを登録します。

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

イベントは WMI によってローカル コンピューターに返され、現在のセッションのイベント キューに保存されます。 イベントを取得するには、ローカル `Get-Event` コマンドを実行します。

## PARAMETERS

### -Action

イベントを処理するコマンドを指定します。 **アクション** パラメーターのコマンドは、イベントをイベントキューに送信するのではなく、イベントが発生したときに実行されます。 コマンドを中かっこ () で囲み、 `{}` スクリプトブロックを作成します。

**Action** の値には `$Event` 、 `$EventSubscriber` `$Sender` `$EventArgs` `$Args` イベントに関する情報を **action** スクリプトブロックに提供する、、、、および自動変数を含めることができます。 詳細については、「about_Automatic_Variables」を参照してください。

アクションを指定すると、は `Register-WmiEvent` そのアクションを表すイベントジョブオブジェクトを返します。 **ジョブ** の名詞を含むコマンドレット ( **job** コマンドレット) を使用して、イベントジョブを管理できます。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -クラス

サブスクライブするイベントを指定します。 イベントを生成する WMI クラスを入力します。 すべてのコマンドで **クラス** または **クエリ** パラメーターが必要です。

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

コマンドを実行するコンピューターの名前を指定します。 既定値はローカル コンピューターです。

コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。 ローカルコンピューターを指定するには、コンピューター名、ドット ( `.` )、または localhost を入力します。

このパラメーターは、Windows PowerShell リモート処理に依存しません。 コンピューターがリモート コマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

この処理を実行するアクセス許可を持つユーザー アカウントを指定します。 既定値は現在のユーザーです。

User01 や Domain01\user01」などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。 ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -転送

このコマンドレットによって、このサブスクリプションのイベントがローカルコンピューター上のセッションに送信されることを示します。
このパラメーターは、リモート コンピューターまたはリモート セッションのイベントに登録する場合に使用します。

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

### -MaxTriggerCount

最大トリガー数を指定します。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageData

このイベント サブスクリプションに関連付けられる任意の追加データを指定します。 このパラメーターの値は、このサブスクリプションに関連付けられているすべてのイベントの **Messagedata** プロパティに表示されます。

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

WMI クラスの名前空間を指定します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

WMI イベントクラスを識別する WMI Query Language (WQL) のクエリを指定します。たとえば、のように `select * from __InstanceDeletionEvent` なります。

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

サブスクリプション用に選択した名前を指定します。 選択した名前は、現在のセッションで一意でなければなりません。 既定値は Windows PowerShell が割り当てた GUID です。

このパラメーターの値は、サブスクライバー オブジェクトおよびこのサブスクリプションに関連付けられたすべてのイベント オブジェクトの **SourceIdentifier** プロパティの値に表示されます。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEvent

このコマンドレットがイベントサブスクリプションを非表示にすることを示します。 このパラメーターは、現在のサブスクリプションがさらに複雑なイベント登録メカニズムの一部であり、単独で検出されない場合に使用します。

**Supportevent** パラメーターを使用して作成されたサブスクリプションを表示またはキャンセルする **Force** には、 `Get-EventSubscriber` コマンドレットとコマンドレットの Force パラメーターを指定し `Unregister-Event` ます。

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

### -タイムアウト

このコマンドが終了するまで Windows PowerShell が待機する時間を指定します。

既定値は 0 (ゼロ) で、タイムアウトがないため、Windows PowerShell は無期限に待機します。

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

Windows Vista 以降のバージョンの Windows オペレーティングシステムでこのコマンドレットを使用するには、[管理者として実行] オプションを使用して Windows PowerShell を起動します。

イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。 現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。

## 関連リンク

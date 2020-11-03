---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: f9f4edca0fce4633daeac9ac11a3ccfb09feb98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213992"
---
# Get-Event

## 概要
イベント キュー内のイベントを取得します。

## SYNTAX

### BySource (既定値)

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### ById

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## Description
**Get イベント** コマンドレットは、現在のセッションの Windows PowerShell イベントキューにあるイベントを取得します。
すべてのイベントを取得するか、 *EventIdentifier* パラメーターまたは *SourceIdentifier* パラメーターを使用してイベントを指定できます。

イベントは、発生時に、イベント キューに追加されます。
イベント キューには、登録したイベント、New-Event コマンドレットを使用して作成されたイベント、および Windows PowerShell の終了時に発生するイベントが含まれます。
イベントを取得するには、 **Get イベント** または Wait-Event を使用します。

このコマンドレットは、イベント ビューアーのログからイベントを取得しません。
これらのイベントを取得するには、Get-WinEvent または Get-EventLog を使用します。

## 例

### 例 1: すべてのイベントを取得する

```
PS C:\> Get-Event
```

このコマンドは、イベント キュー内のすべてのイベントを取得します。

### 例 2: ソース識別子でイベントを取得する

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

このコマンドは、SourceIdentifier プロパティの値が PowerShell. ProcessCreated であるイベントを取得します。

### 例 3: 生成された時刻に基づいてイベントを取得する

```
PS C:\> $Events = Get-Event
PS C:\> $Events[0] | Format-List -Property *
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b805917d1b7b
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:09:32 PM
MessageData      : PS C:\> Get-Event | Where {$_.TimeGenerated -ge "11/13/2008 12:15:00 PM"}
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b8059325d1a0
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:15:00 PM
MessageData      :
```

この例では SourceIdentifier 以外のプロパティを使用してイベントを取得する方法を示します。

最初のコマンドは、イベントキュー内のすべてのイベントを取得し、$Events 変数に保存します。

2番目のコマンドは、配列表記を使用して、$Events 変数内の配列内の最初の (0 インデックス) イベントを取得します。
コマンドは、パイプライン演算子 (|) を使用して Format-List コマンドにイベントを送信します。Format-List コマンドは、一覧内のイベントのすべてのプロパティを表示します。
これによって、イベント オブジェクトのプロパティを調べることができます。

3番目のコマンドは、Where-Object コマンドレットを使用して、生成された時刻に基づいてイベントを取得する方法を示しています。

### 例 4: 識別子を使用してイベントを取得する

```
PS C:\> Get-Event -EventIdentifier 2
```

このコマンドは、イベント識別子が 2 のイベントを取得します。

## PARAMETERS

### -EventIdentifier
このコマンドレットがイベントを取得するイベント識別子を指定します。

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceIdentifier
このコマンドレットがイベントを取得するソース識別子を指定します。
既定では、イベント キュー内のすべてのイベントです。
ワイルドカードは使用できません。

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし
パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### PSEventArgs (システム管理)
**PSEventArgs** は、イベントごとに1つのオブジェクト **を返します** 。
このオブジェクトの説明を表示するには、「」 `Get-Help Get-Event -Full` と入力し、ヘルプトピックの「メモ」セクションを参照してください。

## 注

* イベント、イベント サブスクリプション、およびイベント キューは、現在のセッションにのみ存在します。 現在のセッションを閉じた場合、イベント キューが破棄され、イベント サブスクリプションが取り消されます。

  **Get Event** コマンドレットは、次のプロパティを持つ **PSEventArgs** オブジェクト ( **PSEventArgs** ) を返します。

  - ComputerName。
イベントが発生したコンピューターの名前。
このプロパティ値は、リモート コンピューターからイベントが転送された場合にのみ入力されます。

  - RunspaceId.
イベントが発生したセッションを一意に識別する GUID。
このプロパティ値は、リモート コンピューターからイベントが転送された場合にのみ入力されます。

  - EventIdentifier.
現在のセッションにおけるイベント通知を一意に識別する整数 (Int32)。

  - センダー.
イベントを生成したオブジェクト。
*Action* パラメーターの値では、$Sender の自動変数に Sender オブジェクトが含まれています。

  - SourceEventArgs.
存在する場合は、EventArgs から派生した最初のパラメーター。
たとえば、署名に "オブジェクト送信者, ElapsedEventArgs e" という形式の timer elapsed イベントがある場合、SourceEventArgs プロパティには ElapsedEventArgs が含まれます。
*Action* パラメーターの値には、$EventArgs の自動変数にこの値が含まれています。

  - SourceArgs。
元のイベント署名のすべてのパラメーター。
標準イベントシグネチャの場合、$Args \[ 0 は \] 送信者を表し、$Args \[ 1 \] は sourceeventargs を表します。
*Action* パラメーターの値には、$Args の自動変数にこの値が含まれています。

  - SourceIdentifier.
イベント サブスクリプションを識別する文字列。
*Action* パラメーターの値では、$Event の自動変数の SourceIdentifier プロパティにこの値が含まれています。

  - TimeGenerated.
イベントが生成された時刻を表す **DateTime** オブジェクト。
*Action* パラメーターの値では、$Event 自動変数の timegenerated プロパティにこの値が含まれています。

  --MessageData。
イベント サブスクリプションに関連付けられているデータ。
ユーザーは、イベントを登録するときに、このデータを指定します。
*Action* パラメーターの値では、$Event 自動変数の messagedata プロパティにこの値が含まれています。

*

## 関連リンク

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

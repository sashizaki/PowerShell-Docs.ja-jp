---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214619"
---
# New-EventLog

## 概要
新しいイベント ログおよび新しいイベント ソースをローカル コンピューターまたはリモート コンピューター上に作成します。

## SYNTAX

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## Description

このコマンドレットは、新しい従来のイベント ログをローカル コンピューターまたはリモート コンピューター上に作成します。 また、イベント ソースを登録して、新しいログまたは既存のログに書き込みを行うこともできます。

EventLog という名詞を含むコマンドレット (Event ログ コマンドレット) は、従来のイベント ログでのみ有効です。
Windows Vista 以降のバージョンの windows で windows イベントログテクノロジを使用するログからイベントを取得するには、を使用し `Get-WinEvent` ます。

## 例

### 例 1-新しいイベントログを作成する

このコマンドは、TestLog イベント ログをローカル コンピューター上に作成し、ログの新しいソースを登録します。

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### 例 2-既存のログに新しいイベントソースを追加する

このコマンドは、新しいイベント ソース NewTestApp を Server01 リモート コンピューター上の Application ログに追加します。

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

このコマンドを実行するには、Server01 コンピューター上に NewTestApp.dll ファイルが存在する必要があります。

## PARAMETERS

### -CategoryResourceFile

ソース イベントのカテゴリ文字列が含まれているファイルへのパスを指定します。 このファイルはカテゴリ メッセージ ファイルとも呼ばれます。

ファイルは、イベント ログを作成するコンピューター上に存在している必要があります。 このパラメーターでは、ファイルの作成または移動が行われません。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

指定されたコンピューター上に新しいイベント ログを作成します。 既定値はローカル コンピューターです。

リモートコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名。
ローカル コンピューターを指定するには、コンピューター名、ドット (.)、または「localhost」を入力します。

このパラメーターは、PowerShell リモート処理に依存しません。 **ComputerName** `Get-EventLog` コンピューターがリモートコマンドを実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

イベント ログの名前を指定します。

ログが存在しない場合、は `New-EventLog` ログを作成し、新しいイベントログの **Log** および **logdisplayname** プロパティにこの値を使用します。 ログが存在する場合は、 `New-EventLog` イベントログの新しいソースを登録します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageResourceFile

ソース イベントのメッセージ書式設定文字列が含まれているファイルへのパスを指定します。
このファイルはイベント メッセージ ファイルとも呼ばれます。

ファイルは、イベント ログを作成するコンピューター上に存在している必要があります。
このパラメーターでは、ファイルの作成または移動が行われません。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterResourceFile

イベントの説明でパラメーターに置き換えて使用する文字列が含まれているファイルへのパスを指定します。 このファイルはパラメーター メッセージ ファイルとも呼ばれます。

ファイルは、イベント ログを作成するコンピューター上に存在している必要があります。
このパラメーターでは、ファイルの作成または移動が行われません。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

イベント ログに書き込むアプリケーション プログラムのようなイベント ログ ソースの名前を指定します。 このパラメーターは必須です。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
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

## 注

Windows Vista 以降のバージョンの Windows でを使用するには `New-EventLog` 、[管理者として実行] オプションを使用して PowerShell を開きます。

Windows Vista、Windows XP Professional、または Windows Server 2003 でイベント ソースを作成するには、コンピューターの Administrators グループのメンバーであることが必要です。

新しいイベント ログと新しいイベント ソースを作成する場合、新しいログには新しいソースが登録されますが、最初のエントリが書き込まれるまでログは作成されません。

オペレーティング システムではイベント ログはファイルとして保存されます。

新しいイベントログを作成すると、関連付けられているファイルは、 `$env:SystemRoot\System32\Config` 指定したコンピューターのディレクトリに格納されます。

ファイル名は、 **Log** プロパティの最初の8文字で、ファイル名拡張子は .evt です。

## 関連リンク

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)

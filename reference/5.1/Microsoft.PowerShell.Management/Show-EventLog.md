---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214408"
---
# Show-EventLog

## 概要
イベント ビューアーでローカル コンピューターまたはリモート コンピューターのイベント ログを表示します。

## SYNTAX

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## Description
イベントログの **表示** コマンドレットは、ローカルコンピューター上のイベントビューアーを開き、ローカルコンピューターまたはリモートコンピューター上のすべての従来のイベントログに表示します。

Windows Vista 以降のバージョンの Windows オペレーティングシステムでイベントビューアーを開くには、現在のユーザーがローカルコンピューターの Administrators グループのメンバーである必要があります。

**Eventlog** 名詞を含むコマンドレット ( **eventlog** コマンドレット) は、従来のイベントログでのみ機能します。
Windows Vista 以降のバージョンの windows オペレーティングシステムで Windows イベントログテクノロジを使用するログからイベントを取得するには、Get-WinEvent コマンドレットを使用します。

## 例

### 例 1: ローカルコンピューターのイベントログを表示する

```
PS C:\> Show-EventLog
```

このコマンドを実行すると、イベント ビューアーが開き、ローカル コンピューター上の従来のイベント ログが表示されます。

### 例 2: リモートコンピューターのイベントログを表示する

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

このコマンドを実行すると、イベント ビューアーが開き、Server01 コンピューター上の従来のイベント ログが表示されます。

## PARAMETERS

### -ComputerName
リモート コンピューターを指定します。
[イベントログの **表示]** には、ローカルコンピューター上のイベントビューアーの指定したコンピューターのイベントログが表示されます。
既定値はローカル コンピューターです。

リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。

このパラメーターは、Windows PowerShell リモート処理に依存しません。
コンピューターがリモート コマンドを実行するように構成されていない場合でも、 *ComputerName* パラメーターを使用できます。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
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

### なし
このコマンドレットは出力を生成しません。

## 注

* イベント ビューアーが開くと、Windows PowerShell のコマンド プロンプトに戻ります。 イベント ビューアーが開いている間は、現在のセッションで作業できます。

  このコマンドレットにはユーザー インターフェイスが必要なので、Windows Server の Server Core インストールでは機能しません。

*

## 関連リンク

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Write-EventLog](Write-EventLog.md)

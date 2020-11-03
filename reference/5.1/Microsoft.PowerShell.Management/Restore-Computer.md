---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214475"
---
# Restore-Computer

## 概要
ローカル コンピューターでシステムの復元を開始します。

## SYNTAX

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Restore Computer** コマンドレットは、指定したシステム復元ポイントにローカルコンピューターを復元します。

**復元-** コンピューターを再起動します。
復元は再起動操作時に完了します。

システムの復元ポイントと **復元-コンピューター** は、windows 7、windows Vista、windows XP などのクライアントオペレーティングシステムでのみサポートされています。

## 例

### 例 1: ローカルコンピューターを復元する

```
PS C:\> Restore-Computer -RestorePoint 253
```

このコマンドは、シーケンス番号253を持つ復元ポイントにローカルコンピューターを復元します。

### 例 2: 確認を使用してローカルコンピューターを復元する

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

このコマンドは、シーケンス番号255を持つ復元ポイントにローカルコンピューターを復元します。
*Confirm* パラメーターを使用して、実際に操作を実行する前にユーザーに確認メッセージを表示します。

### 例 3: コンピューターを復元して状態を確認する

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

これらのコマンドはシステムの復元を実行し、その状態をチェックします。

最初のコマンドは、 **Get ComputerRestorePoint** を使用して、ローカルコンピューター上の復元ポイントを取得します。

2番目のコマンドは、シーケンス番号255を使用してコンピュータを復元ポイントに復元します。

3番目のコマンドは、 *Get ComputerRestorePoint* コマンドレットの *laststatus* パラメーターを使用して、復元操作の状態を確認します。
**復元コンピューター** によって再起動が強制されるため、このコマンドはコンピューターの再起動後に入力されます。

## PARAMETERS

### -RestorePoint
復元ポイントのシーケンス番号を指定します。
シーケンス番号を検索するには、Get-ComputerRestorePoint コマンドレットを使用します。
このパラメーターは必須です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

Required: True
Position: 0
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

* Windows Vista 以降のバージョンの Windows オペレーティングシステムで Restore-Computer コマンドを実行するには、[管理者として実行] オプションを使用して Windows PowerShell を開きます。
* このコマンドレットは、Windows Management Instrumentation (WMI) **Systemrestore** クラスを使用します。

## 関連リンク

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)

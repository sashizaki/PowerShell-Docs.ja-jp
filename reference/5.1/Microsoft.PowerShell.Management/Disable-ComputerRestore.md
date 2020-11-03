---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/disable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ComputerRestore
ms.openlocfilehash: 941829c3caa0f6bb2f5712dda9eb7d8c36908062
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215496"
---
# Disable-ComputerRestore

## 概要
指定したファイル システム ドライブのシステム復元機能を無効にします。

## SYNTAX

```
Disable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Computerrestore** コマンドレットは、1つまたは複数のファイルシステムドライブのシステム復元機能を無効にします。
その結果、指定したドライブはコンピューターを復元する際の対象になりません。

ドライブのシステム復元を無効にするには、システム ドライブ上で無効にする必要があります。これは最初にまたは同時に行います。

システム復元を再び有効にするには、Enable-ComputerRestore コマンドレットを使用します。
各ドライブのシステム復元の状態を調べるには、Rstrui.exe を使用します。

システムの復元ポイントおよび ComputerRestore コマンドレットは、Windows 7、Windows Vista、Windows XP のようなクライアント オペレーティング システムだけでサポートされています。

## 例

### 例 1: 指定されたドライブでシステムの復元を無効にする

```
PS C:\> Disable-ComputerRestore -Drive "C:\"
```

このコマンドは、C ドライブのシステム復元を無効にします。

### 例 2: 複数のドライブのシステム復元を無効にする

```
PS C:\> Disable-ComputerRestore "C:\", "D:\"
```

このコマンドは、C ドライブおよび D ドライブのシステム復元を無効にします。
このコマンドでは *drive* パラメーターを使用しますが、ドライブパラメーター名は省略しています。

## PARAMETERS

### -ドライブ
ファイル システム ドライブを指定します。
1つまたは複数のファイルシステムドライブ文字を入力し、その後にコロンと円記号を入力して、C:\ などの引用符で囲みます。または D:\
このパラメーターは必須です。

リモート ネットワーク ドライブは、ローカル コンピューターにマップされていてもこのコマンドレットを使用してシステム復元を無効にすることはできません。また、外部ドライブのようにシステム復元の対象にならないドライブのシステム復元を無効にすることはできません。

ドライブのシステム復元を無効にするには、システム ドライブ上でシステム復元を無効にする必要があります。これは事前にまたは同時に行います。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

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

* Windows Vista 以降のバージョンの Windows でこのコマンドレットを実行するには、[管理者として実行] オプションを使用して Windows PowerShell を開きます。

  システムの復元の対象となるファイルシステムドライブを調べるには、コントロールパネルの [システム] で、[システムの保護] タブを参照してください。Windows PowerShell でこのタブを開くには、「」と入力 `SystemPropertiesProtection` します。

  このコマンドレットは、Windows Management Instrumentation (WMI) **Systemrestore** クラスを使用します。

*

## 関連リンク

[Checkpoint-Computer](Checkpoint-Computer.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

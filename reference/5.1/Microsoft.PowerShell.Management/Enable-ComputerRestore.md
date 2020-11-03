---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/enable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ComputerRestore
ms.openlocfilehash: f9616a7f9af4dd2fa45e150bb64eef65427b4947
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215491"
---
# Enable-ComputerRestore

## 概要
指定したファイル システム ドライブのシステム復元機能を有効にします。

## SYNTAX

```
Enable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Computerrestore** コマンドレットは、1つまたは複数のファイルシステムドライブのシステム復元機能を有効にします。
その結果、Restore-Computer コマンドレットなどのツールを使用してコンピューターを以前の状態に復元できます。

既定では、システム復元を使用できるすべてのドライブでシステム復元は有効ですが、Disable-ComputerRestore コマンドレットなどを使用して無効にすることもできます。
任意のドライブのシステム復元を有効に (または再び有効に) するには、システム ドライブ上でシステム復元を有効にする必要があります。これは最初にまたは同時に行います。
各ドライブのシステム復元の状態を調べるには、Rstrui.exe を使用します。

システムの復元ポイントおよび ComputerRestore コマンドレットは、Windows 7、Windows Vista、Windows XP のようなクライアント オペレーティング システムだけでサポートされています。

## 例

### 例 1: 指定されたドライブでシステムの復元を有効にする

```
PS C:\> Enable-ComputerRestore -Drive "C:\"
```

このコマンドは、ローカル コンピューターの C ドライブのシステム復元を有効にします。

### 例 2: 複数のドライブでシステムの復元を有効にする

```
PS C:\> Enable-ComputerRestore -Drive "C:\", "D:\"
```

このコマンドは、ローカル コンピューターの C ドライブと D ドライブのシステム復元を有効にします。

## PARAMETERS

### -ドライブ
ファイル システム ドライブを指定します。
1つまたは複数のファイルシステムドライブ文字を入力し、その後にコロンと円記号を入力して、C:\ などの引用符で囲みます。または D:\
このパラメーターは必須です。

リモート ネットワーク ドライブは、ローカル コンピューターにマップされていてもこのコマンドレットを使用してシステム復元を有効にすることはできません。また、外部ドライブのようにシステム復元の対象にならないドライブのシステム復元を有効にすることはできません。

任意のドライブのシステム復元を有効にするには、システム ドライブ上でシステム復元を有効にする必要があります。これは事前にまたは同時に行います。

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
このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。

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

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

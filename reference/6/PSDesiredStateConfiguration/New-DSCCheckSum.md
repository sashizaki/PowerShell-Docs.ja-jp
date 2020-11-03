---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 2637cc092d3be2bb3bff051268ef288c81ef3ad7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212480"
---
# New-DscChecksum

## 概要
DSC ドキュメントと DSC リソースのチェックサムファイルを作成します。

## SYNTAX

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

**新しい-dscchecksum** コマンドレットは、PowerShell Desired State CONFIGURATION (DSC) ドキュメントと圧縮された dsc リソースのチェックサムファイルを生成します。
このコマンドレットは、プルモードで使用される構成およびリソースごとにチェックサムファイルを生成します。
DSC サービスでは、チェックサムを使用して、ターゲットノードに正しい構成とリソースが存在することを確認します。
チェックサムを、関連付けられている DSC ドキュメントと、DSC サービスストアの圧縮された DSC リソースと一緒に配置します。

## 例

### 例 1: 特定のパスにあるすべての構成のチェックサムファイルを作成する

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

以下のコマンドは、パス C:\DSC\Configurations にあるすべての構成のチェックサム ファイルを作成します。
既に存在するチェックサムファイルはスキップされます。

### 例 2: 特定のパスのすべての構成のチェックサムファイルを作成し、既存のチェックサムファイルを上書きする

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

以下のコマンドは、パス C:\DSC\Configurations にあるすべての構成の新しいチェックサム ファイルを作成します。
*Force* パラメーターを指定すると、既に存在するチェックサムファイルが上書きされます。

## PARAMETERS

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

### -Force

指定した出力ファイルが既に存在する場合はコマンドレットによってそのファイルが上書きされることを示します。

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

### -OutPath

出力チェックサム ファイルのパスとファイル名を指定します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

入力ファイルのパスを指定します。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ConfigurationPath

Required: True
Position: 0
Default value: None
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

## 出力

### System.Object

## 注

## 関連リンク

[Windows PowerShell Desired State Configuration の概要](/powershell/scripting/dsc/overview/dscforengineers)

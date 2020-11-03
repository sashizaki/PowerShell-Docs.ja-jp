---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: a0b5d7e86f9d63b487bc093feb18ecc7a4496999
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217003"
---
# Set-PSDebug

## 概要
スクリプトのデバッグ機能のオン/オフの切り替え、トレース レベルの設定、厳格モードの切り替えを行います。

## SYNTAX

### on

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### オフ

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## Description

`Set-PSDebug`コマンドレットは、スクリプトのデバッグ機能のオンとオフの切り替え、トレースレベルの設定、厳格モードの切り替えを行います。 既定では、PowerShell デバッグ機能はオフになっています。

**Trace** パラメーターの値がの場合 `1` 、スクリプトの各行は実行時にトレースされます。 パラメーターの値がの場合 `2` 、変数の代入、関数の呼び出し、およびスクリプトの呼び出しもトレースされます。 **Step** パラメーターを指定した場合は、スクリプトの各行が実行される前にプロンプトが表示されます。

## 例

### 例 1: トレースレベルを設定する

この例では、トレースレベルをに設定し、 `2` 1、2、およびの数値を表示するスクリプトを実行します。
3.

```powershell
Set-PSDebug -Trace 2; foreach ($i in 1..3) {$i}
```

```Output
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in  >>>> 1..3) {$i}
DEBUG:     ! SET $foreach = 'IEnumerator'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '1'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
1
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '2'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
2
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '3'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
3
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $foreach = ''.
```

### 例 2: ステップ実行を有効にする

この例では、ステップ実行をオンにして、1、2、および3の番号を表示するスクリプトを実行します。

```powershell
Set-PSDebug -Step; foreach ($i in 1..3) {$i}
```

```Output
Continue with this operation?
   1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
DEBUG:    1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
1
2
3
```

### 例 3: strict モードを使用する

この例では、PowerShell を厳格モードで配置し、値が割り当てられていない変数にアクセスしようとします。

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### 例 4: デバッグ機能を無効にする

この例では、すべてのデバッグ機能をオフにしてから、1、2、および3の番号を表示するスクリプトを実行します。

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## PARAMETERS

### -Off

すべてのスクリプト デバッグ機能をオフにします。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: off
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ステップ

スクリプトのステップ実行をオンにします。 各行が実行される前に、PowerShell は、スクリプトの状態を検査するために、停止するか、続行するか、新しいインタープリターレベルを入力するように求めます。

**Step** パラメーターを指定すると、のトレースレベルが自動的に設定さ `1` れます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Strict

スクリプトで参照される前に、変数に値を代入する必要があることを指定します。 値が割り当てられる前に変数が参照されている場合、PowerShell は例外エラーを返します。 これは、`Set-StrictMode -Version 1` と同じです。 詳細については、「 [set-strictmode](Set-StrictMode.md)」を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -トレース

スクリプトの各行のトレースレベルを指定します。 各行は実行時にトレースされます。

このパラメーターに指定できる値は次のとおりです。

- 0: スクリプトのトレースをオフにします。
- 1: 実行時にスクリプト行をトレースします。
- 2: スクリプト行、変数の代入、関数呼び出し、およびスクリプトをトレースします。

```yaml
Type: System.Int32
Parameter Sets: on
Aliases:

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

このコマンドレットに入力をパイプラインすることはできません。

## 出力

### なし

このコマンドレットは出力を返しません。

## 注

## 関連リンク

[about_Debuggers](./About/about_Debuggers.md)

[Debug-Process](../Microsoft.PowerShell.Management/Debug-Process.md)

[Set-PSBreakpoint](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[Set-StrictMode](Set-StrictMode.md)

[Write-Debug](../Microsoft.PowerShell.Utility/Write-Debug.md)


---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 905f3522a071fdd3f59d020b734c689a59e68a63
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217680"
---
# Debug-Process

## 概要
ローカル コンピューター上で実行中の 1 つ以上のプロセスをデバッグします。

## SYNTAX

### 名前 (既定値)

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

**Debug Process** コマンドレットは、ローカルコンピューター上で実行中の1つ以上のプロセスにデバッガーをアタッチします。
プロセスは、プロセス名またはプロセス ID (PID) で指定することも、パイプを使用してこのコマンドレットに処理することもできます。

このコマンドレットは、プロセスに対して現在登録されているデバッガーをアタッチします。
このコマンドレットを使用する前に、デバッガーがダウンロードされていて適切に設定されていることを確認します。

## 例

### 例 1: コンピューター上のプロセスにデバッガーをアタッチする

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

このコマンドは、コンピューターの PowerShell プロセスにデバッガーを結合します。

### 例 2: 指定した文字列で始まるすべてのプロセスにデバッガーをアタッチする

```
PS C:\> Debug-Process -Name "SQL*"
```

このコマンドは、名前が SQL で始まるすべてのプロセスにデバッガーをアタッチします。

### 例 3: デバッガーを複数のプロセスにアタッチする

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

このコマンドは、Winlogon、Explorer、Outlook の各プロセスにデバッガーを結合します。

### 例 4: デバッガーを複数のプロセス Id にアタッチする

```
PS C:\> Debug-Process -Id 1132, 2028
```

このコマンドは、プロセス ID 1132 および 2028 のプロセスにデバッガーを結合します。

### 例 5: Get-Process を使用してプロセスを取得し、デバッガーをアタッチする

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

このコマンドは、コンピューターの PowerShell プロセスにデバッガーを結合します。
このコマンドは、 **Get process** コマンドレットを使用してコンピューター上の PowerShell プロセスを取得し、パイプライン演算子 (|) を使用してプロセスを **デバッグプロセス** コマンドレットに送信します。

特定の PowerShell プロセスを指定するには、 **Get process** の ID パラメーターを使用します。

### 例 6: ローカルコンピューター上の現在のプロセスにデバッガーをアタッチする

```
PS C:\> $PID | Debug-Process
```

このコマンドは、コンピューターの現在の PowerShell プロセスにデバッガーを結合します。

このコマンドは、現在の PowerShell プロセスのプロセス ID を含む $PID 自動変数を使用します。
次に、パイプライン演算子 (|) を使用してプロセス ID を **デバッグプロセス** のコマンドレットに送信します。

$PID 自動変数の詳細については、「about_Automatic_Variables」を参照してください。

### 例 7: InputObject パラメーターを使用するプロセスにデバッガーをアタッチする

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

このコマンドは、ローカル コンピューターの PowerShell プロセスにデバッガーを結合します。

最初のコマンドは、 **Get Process** コマンドレットを使用して、コンピューター上の PowerShell プロセスを取得します。
これにより、結果として得られるプロセスオブジェクトが $P という名前の変数に保存されます。

2番目のコマンドは、 **Debug process** コマンドレットの *InputObject* パラメーターを使用して、$P 変数にプロセスオブジェクトを送信します。

## PARAMETERS

### -Id

デバッグするプロセスのプロセス ID を指定します。
*Id* パラメーター名は省略可能です。

プロセスのプロセス ID を検索するには、「」と入力 `Get-Process` します。

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

デバッグするプロセスを表すプロセス オブジェクトを指定します。
プロセスオブジェクトを含む変数、または Get-Process コマンドレットなどのプロセスオブジェクトを取得するコマンドを入力します。
パイプを使用してプロセスオブジェクトをこのコマンドレットに送ることもできます。

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

デバッグするプロセスの名前を指定します。
同じ名前のプロセスが複数ある場合、このコマンドレットは、その名前を持つすべてのプロセスにデバッガーをアタッチします。
*Name* パラメーターは省略可能です。

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.string, System.string, System.string, System.string,

パイプを使用して、プロセス ID (Int32)、プロセスオブジェクト (システム診断プロセス)、またはプロセス名 (文字列) をこのコマンドレットに渡します。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

* このコマンドレットは、Windows Management Instrumentation (WMI) Win32_Process クラスの AttachDebugger メソッドを使用します。 このメソッドの詳細については、MSDN ライブラリの「 [Attachdebugger メソッド](https://go.microsoft.com/fwlink/?LinkId=143640) 」を参照してください。

## 関連リンク

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)


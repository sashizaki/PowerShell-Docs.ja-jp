---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212059"
---
# Export-Console

## 概要
現在のセッションのスナップインの名前をコンソール ファイルにエクスポートします。

## SYNTAX

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Export console** コマンドレットは、現在のセッションの windows powershell スナップインの名前を windows powershell コンソールファイル (. .psc1) にエクスポートします。
このコマンドレットを使用すると、将来のセッションで使用するためにスナップインを保存できます。

.Psc1 コンソールファイルのスナップインをセッションに追加するには、コマンドラインで Cmd.exe または別の Windows PowerShell セッションを使用して Windows PowerShell (Powershell.exe) を起動し、Powershell.exe の *Psconsolefile* パラメーターを使用してコンソールファイルを指定します。

Windows PowerShell スナップインの詳細については、「about_PSSnapins」を参照してください。

## 例

### 例 1: 現在のセッションでスナップインの名前をエクスポートする

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

このコマンドを実行すると、現在のセッションの Windows PowerShell スナップインの名前が、Windows PowerShell インストールフォルダー $pshome の [コンソール] フォルダーの Consoles1.psc1 ファイルにエクスポートされます。

### 例 2: 最新のコンソールファイルにスナップインの名前をエクスポートする

```
PS C:\> Export-Console
```

このコマンドは、Windows PowerShell スナップインの名前を、現在のセッションから、現在のセッションで最近使用された Windows PowerShell コンソール ファイルにエクスポートします。
前のファイルの内容は上書きされます。

現在のセッション中に、コンソール ファイルをエクスポートしていない場合は、続行するためのアクセス許可の入力が求められ、その後、ファイル名の入力が求められます。

### 例 3: スナップインを追加し、スナップインの名前をエクスポートする

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

これらのコマンドは、NewPSSnapin Windows PowerShell スナップインを現在のセッションに追加し、現在のセッションの Windows PowerShell スナップインの名前をコンソール ファイルにエクスポートして、コンソール ファイルで Windows PowerShell セッションを開始します。

最初のコマンドは、 **add-pssnapin** コマンドレットを使用して、NewPSSnapin スナップインを現在のセッションに追加します。
システムに登録されている Windows PowerShell スナップインのみを追加できます。

2 番目のコマンドは、Windows PowerShell スナップインの名前を NewPSSnapinConsole.psc1 ファイルにエクスポートします。

3 番目のコマンドは、NewPSSnapinConsole.psc1 ファイルを使用して、Windows PowerShell を起動します。
コンソール ファイルには Windows PowerShell スナップインの名前が含まれるため、スナップイン内のコマンドレットとプロバイダーを現在のセッションで使用できます。

### 例 4: スナップインの名前を指定した場所にエクスポートする

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

このコマンドは、現在のセッションの Windows PowerShell スナップインの名前を、現在のディレクトリ内の Console01.psc1 ファイルにエクスポートします。

2 番目のコマンドは、メモ帳で、Console01.psc1 ファイルの内容を表示します。

### 例 5: 更新するコンソールファイルを決定する

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

この例では、$ConsoleFileName の自動変数を使用して、 *Path* パラメーター値を指定せずに **エクスポートコンソール** を使用する場合に更新されるコンソールファイルを決定する方法を示します。

最初のコマンドは、PowerShell.exe の *Psconsolefile* パラメーターを使用して、.psc1 ファイルと共に Windows PowerShell を開きます。

2番目のコマンドは、 **add-pssnapin** コマンドレットを使用して、Mysnapin イン Windows PowerShell スナップインを現在のセッションに追加します。

3番目のコマンドは、 **Export-console** コマンドレットを使用して、セッション内のすべての Windows PowerShell スナップインの名前を newconsole ファイルにエクスポートします。

4番目のコマンドは、$ConsoleFileName 変数を表示します。
これには、最近使用したコンソールファイルが含まれます。
サンプル出力は NewConsole.ps1 が最近使用されたファイルであることを示しています。

5 番目のコマンドは、SnapIn03 を現在のコンソールに追加します。

6番目のコマンドは、 *Path* パラメーターを指定せずに、 **Export Console** コマンドレットを使用します。
このコマンドは、現在のセッションのすべての Windows PowerShell スナップインの名前を最近使用されたファイルである NewConsole.psc1 にエクスポートします。

## PARAMETERS

### -Force
ファイルに読み取り専用属性が指定されている場合でも、このコマンドレットによってコンソールファイル内のデータが警告なしに上書きされることを示します。
読み取り専用属性は変更され、コマンドの完了時にリセットされません。

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

### -NoClobber
このコマンドレットによって既存のコンソールファイルが上書きされないことを示します。
既定では、指定されたパスにファイルが存在する場合、 **エクスポート** は警告なしでファイルを上書きします。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
コンソール ファイル (*.psc1) のパスとファイル名を指定します。
省略可能なパスと名前を入力します。
ワイルドカード文字は使用できません。

ファイル名のみを指定すると、.psc1 ファイル名拡張子を持つファイルが現在のディレクトリ **に作成さ** れます。

このパラメーターは、 *Psconsolefile* パラメーターを指定して Windows PowerShell を開いているか、現在のセッション中にコンソールファイルをエクスポートしていない場合に必要です。
また、 *NoClobber* パラメーターを使用して、現在のコンソールファイルが上書きされないようにする場合にも必要です。

このパラメーターを省略すると、このセッションで最近使用されたコンソールファイル **が上書きさ** れます。
最近使用したコンソールファイルのパスは、$ConsoleFileName 自動変数の値に格納されます。
詳細については、「about_Automatic_Variables」を参照してください。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.String
パイプを使用してパス文字列をこのコマンドレットに渡します。

## 出力

### システム. IO. FileInfo
このコマンドレットは、エクスポートされたエイリアスを含むファイルを作成します。

## 注

* コンソール ファイル (.psc1) を使用してセッションを開始すると、コンソール ファイルの名前が自動的に $ConsoleFileName の自動変数に格納されます。 $ConsoleFileName の値は、 **エクスポートコンソール** の *Path* パラメーターを使用して新しいコンソールファイルを指定したときに更新されます。 コンソールファイルが使用されていない場合、$ConsoleFileName には値 ($Null) がありません。

  新しいセッションで Windows PowerShell コンソール ファイルを使用するには、次の構文を使用して Windows PowerShell を起動します。

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  Windows PowerShell プロファイルに Add-PSSnapin コマンドを追加することで、今後のセッションで使用するために Windows PowerShell スナップインを保存することもできます。
詳細については、「about_Profiles」を参照してください。


## 関連リンク

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)

---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: 5d4a27f1a1949056ca63b9b6a2340bf1226592e0
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219216"
---
# Measure-Object

## 概要
オブジェクトの数値プロパティと、テキストのファイルなど文字列オブジェクト内の文字、単語、および行を計算します。

## SYNTAX

### GenericMeasure (既定値)

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Sum] [-Average] [-Maximum] [-Minimum]
 [<CommonParameters>]
```

### TextMeasure

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Line] [-Word] [-Character]
 [-IgnoreWhiteSpace] [<CommonParameters>]
```

## Description

コマンドレットでは、 `Measure-Object` 特定の種類のオブジェクトのプロパティ値を計算します。
`Measure-Object` コマンド内のパラメーターに応じて、3種類の測定を実行します。

コマンドレットでは、 `Measure-Object` オブジェクトのプロパティ値に対して計算を実行します。 を使用すると、 `Measure-Object` オブジェクトをカウントしたり、指定した **プロパティ** を使用してオブジェクトをカウントしたりできます。 また、を使用して、 `Measure-Object` 数値の **最小** 値、 **最大** 値、 **合計** 、 **標準偏差** 、 **平均** を計算することもできます。 **文字列** オブジェクトの場合は、を使用して、 `Measure-Object` 行、単語、および文字の数をカウントすることもできます。

## 例

### 例 1: ディレクトリ内のファイルとフォルダーの数をカウントする

このコマンドは、現在のディレクトリ内のファイルとフォルダーをカウントします。

```powershell
Get-ChildItem | Measure-Object
```

### 例 2: ディレクトリ内のファイルを測定する

このコマンドは、現在のディレクトリにあるすべてのファイルのサイズの **最小値** 、 **最大** 値、および **合計** 値と、ディレクトリ内のファイルの平均サイズを表示します。

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### 例 3: テキストファイル内のテキストを測定する

このコマンドは、Text.txt ファイル内の文字数、単語数、および行数を表示します。
**Raw** パラメーターを指定しない場合、は `Get-Content` ファイルを行の配列として出力します。

最初のコマンドは、を使用して、 `Set-Content` いくつかの既定のテキストをファイルに追加します。

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### 例 4: 指定されたプロパティを含む Measure オブジェクト

この例では、 **DisplayName** プロパティを持つオブジェクトの数をカウントします。 最初の2つのコマンドは、ローカルコンピューター上のすべてのサービスとプロセスを取得します。 3番目のコマンドは、結合されたサービスとプロセスの数をカウントします。 最後のコマンドは、2つのコレクションを結合し、結果をにパイプし `Measure-Object` ます。

System.string **オブジェクトに** は **DisplayName** プロパティがないため、最終的なカウントから除外されます。

```powershell
$services = Get-Service
$processes = Get-Process
$services + $processes | Measure-Object
$services + $processes | Measure-Object -Property DisplayName
```

```Output
Count    : 682
Average  :
Sum      :
Maximum  :
Minimum  :
Property :

Count    : 290
Average  :
Sum      :
Maximum  :
Minimum  :
Property : DisplayName
```

### 例 5: CSV ファイルの内容を測定する

このコマンドは、企業の従業員のサービスの平均年数を計算します。

この `ServiceYrs.csv` ファイルは、各従業員の従業員番号とサービス年数を含む CSV ファイルです。 テーブルの最初の行は、 **Empno** , **Years** のヘッダー行です。

を使用してファイルをインポートすると、結果として、 `Import-Csv` **empno** と **Years** の Note プロパティを含む **pscustomobject** 生成されます。
を使用すると `Measure-Object` 、オブジェクトの他のプロパティと同じように、これらのプロパティの値を計算できます。

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### 例 6: ブール値を測定する

この例では、が `Measure-Object` ブール値を測定する方法を示します。
この場合、 **PSIsContainer** の **ブール型** プロパティを使用して、現在のディレクトリ内のフォルダー (またはファイル) の発生を測定します。

```powershell
Get-ChildItem | Measure-Object -Property psiscontainer -Maximum -Sum -Minimum -Average
```

```Output
Count             : 126
Average           : 0.0634920634920635
Sum               : 8
Maximum           : 1
Minimum           : 0
StandardDeviation :
Property          : PSIsContainer
```

### 例 7: メジャー文字列

次の例では、複数の文字列に対して、行の数、1つ目の文字列を測定します。 改行文字は、 <code>`n</code> 文字列を複数の行に分割します。

```powershell
# The newline character `n separates the string into separate lines, as shown in the output.
"One`nTwo`nThree"
"One`nTwo`nThree" | Measure-Object -Line
```

```Output
One
Two
Three


Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The first string counts as a single line.
# The second string is separated into two lines by the newline character.
"One", "Two`nThree" | Measure-Object -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The Word switch counts the number of words in each InputObject
# Each InputObject is treated as a single line.
"One, Two", "Three", "Four Five" | Measure-Object -Word -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3     5
```

## PARAMETERS

### -平均

コマンドレットによって、指定されたプロパティの平均値が表示されることを示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -文字

コマンドレットが入力オブジェクトの文字数をカウントすることを示します。

> [!NOTE]
> *各入力* オブジェクトと入力オブジェクトの *間* で、 **Word** 、 **Char** 、および **Line** スイッチがカウントされます。 例7を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreWhiteSpace

コマンドレットが文字数の空白を無視することを示します。
既定では、空白は無視されません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

測定するオブジェクトを指定します。
オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。

で **inputobject** パラメーターを使用すると、 `Measure-Object` コマンドの結果をにパイプするのではなく、 `Measure-Object` **inputobject** 値が1つのオブジェクトとして扱われます。

オブジェクトが `Measure-Object` 定義されたプロパティに特定の値を持つかどうかに基づいてオブジェクトのコレクションを測定する場合は、パイプラインでを使用することをお勧めします。

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Line

コマンドレットによって入力オブジェクトの行数がカウントされることを示します。

> [!NOTE]
> *各入力* オブジェクトと入力オブジェクトの *間* で、 **Word** 、 **Char** 、および **Line** スイッチがカウントされます。 例7を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -最大

コマンドレットによって、指定されたプロパティの最大値が表示されることを示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -最小

コマンドレットによって、指定されたプロパティの最小値が表示されることを示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -プロパティ

測定する1つ以上のプロパティを指定します。 他のメジャーを指定しない場合は、によって、指定した `Measure-Object` プロパティを持つオブジェクトがカウントされます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Sum

コマンドレットによって、指定されたプロパティの値の合計が表示されることを示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Word

コマンドレットによって入力オブジェクト内の単語数がカウントされることを示します。

> [!NOTE]
> *各入力* オブジェクトと入力オブジェクトの *間* で、 **Word** 、 **Char** 、および **Line** スイッチがカウントされます。 例7を参照してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
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

### システム管理. PSObject

パイプを使用してオブジェクトをにパイプ処理でき `Measure-Object` ます。

## 出力

### Microsoft. PowerShell. GenericMeasureInfo

### Microsoft. PowerShell. TextMeasureInfo

**Word** パラメーターを使用すると、は `Measure-Object` **textmeasureinfo** オブジェクトを返します。
それ以外の場合は、 **Genericmeasureinfo** オブジェクトを返します。

## 注

## 関連リンク

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)

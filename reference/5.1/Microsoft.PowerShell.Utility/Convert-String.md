---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214147"
---
# Convert-String

## 概要
例と一致するように文字列を書式設定します。

## SYNTAX

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## Description

**Convert 文字列** コマンドレットは、例の形式に一致するように文字列を書式設定します。

## 例

### 例 1: 文字列の形式を変換する

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

最初のコマンドは、名と姓を含む配列を作成します。

2番目のコマンドは、例に従って名前を書式設定します。
このメソッドは、出力の先頭に姓を付け、その後に最初のを配置します。

### 例 2: 文字列の書式を簡略化する

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

最初のコマンドは、名、ミドルネーム、および姓を含む配列を作成します。
最後のエントリにはミドルネームが含まれていないことに注意してください。

2番目のコマンドは、例に従って名前を書式設定します。
このメソッドは、出力の先頭に姓を置き、その後に名を付けます。
すべてのミドルネームが削除されました。ミドルネームのないエントリが正しく処理されています。

### 例 3: 文字列が一致しない場合の出力管理の例

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

最初のコマンドは、名、ミドルネーム、および姓を含む配列を作成します。
最後のエントリにはミドルネームが含まれていないことに注意してください。

2番目のコマンドは、例に従って名前を書式設定します。
このメソッドは、出力の先頭に **ミドル** ネームを付け、その後に名を指定します。
**$Composers** の最後のエントリは、サンプルパターンと一致しないため、スキップされます。ミドルネームはありません。

### 例 4: 美しさスペースでの注意事項

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

最初のコマンドは、姓と名の配列を作成します。
2番目と4番目の項目は、最後の名前の後に余分な末尾のスペースがあることに注意してください。

2番目のコマンドは、サンプルパターンに一致するすべての文字列を変換します。これは、 _単語、スペース、単語、および最後の末尾のスペース_ で、等号の前にあります。
また、出力の先頭のスペースに注意してください。

### 例 5: 複数のパターンを使用したプロセス情報の書式設定

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

**$ExamplePatterns** は、例を使用して、データ内のさまざまな予想されるパターンを定義します。

最初のパターンであるは、次のように `@{before='"Hello","World"'; after='World: Hello'}` 読み取られます。 _単語が二重引用符で囲まれていること、コンマ、_ 
 _2 番目、最後の単語が引用符で囲ま_ れていることを想定しています。 
_文字列にスペースが含まれていません。出力: 2 番目の単語を_ 
 _引用符で囲まずに1つだけ配置します。次に、単一の空白と最初の単語を引用符で囲み_ ません。

2番目のパターンは、次のように `@{before='"Hello","1"'; after='1: Hello'}` 読み取られます。 _単語が二重引用符で囲まれていること、コンマ、_ 
 _および引用符で囲ま_ れた数値であることが想定されます。 
_文字列にスペースが含まれていません。[出力]:_ 引用符を使用せずに数字を最初に配置します。次に、 
 _単一のスペースと単語を引用符で囲みません。_

3番目のパターンでは、は `@{before='"Hello-World","22"'; after='22: Hello-World'}` 次のように読み取られます。 _2 つの単語の間にハイフン_ が含まれている場合は、 
 _二重引用符、コンマ、および引用符で囲ま_ れた数字で囲まれます。 
_コンマと3番目の二重引用符の間にスペースを入れません。_ 
_出力の場合: 最初に数字を引用符で囲み、1つのスペース_ 
 を追加します。 _ハイフンで囲まれた単語は引用符で囲みません。_

4番目と最後のパターンは、次のように `@{before='"hello world","333"'; after='333: hello world'}` 読み取られます。 _2 つの単語の間にスペースが含ま_ れている場合は、 
 _二重引用符、コンマ、および引用符で囲ま_ れた数字で囲まれます。 
_コンマと3番目の二重引用符の間にスペースを入れません。_ 
_出力の場合: 最初に数字を引用符で囲み、1つのスペース_ 
 を追加します。次に、引用符を使用 _せずに、between の間にスペースがある単語を指定します。_

最初のコマンドは、Get-Process コマンドレットを使用して、すべてのプロセスを取得します。
このコマンドは、プロセス名とプロセス ID を選択する Select-Object コマンドレットに渡します。 パイプラインの最後では、ConvertTo-Csv コマンドレットを使用して、出力を型情報のないコンマ区切り値に変換します。
このコマンドは、結果を **$Processes** 変数に格納します。
**$Processes** にプロセス名と PID が含まれるようになりました。

2番目のコマンドは、入力項目の順序を変更するサンプル変数を指定します。
このコマンドは、 **$Processes** 内の各文字列を指定します。

>**メモ** 4番目のパターンは、スペースで区切られた2つ以上の単語が一致することを暗黙的に示しています。
>
>4番目のパターンを使用しない場合、二重引用符で囲まれた文字列の最初の単語のみが一致します。

## PARAMETERS

### -例

対象の形式の例の一覧を指定します。
次の例のように、等号 (=) 記号で区切られたペアを指定します。次の例のように、左側にはソースパターン、右側にはターゲットパターンを指定します。

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

>**メモ** 2番目の例では、パターンの一覧を使用します。

または、 **Before** および **After** プロパティを含むハッシュテーブルの一覧を指定します。

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

>**注意** 等号はパターンの一部として扱われるため、等号の周りにスペースを使用しないでください。

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

書式設定する文字列を指定します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### String

このコマンドレットに文字列をパイプすることができます。

## 出力

### String

このコマンドレットは文字列を返します。

## 注

## 関連リンク

[ConvertFrom-String](ConvertFrom-String.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)

[Out-String](Out-String.md)

[Select-Object](Select-Object.md)

---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 514a66ebee3827de998622a738c75d4f8e0c7279
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214027"
---
# Format-Hex

## 概要

ファイルまたはその他の入力を16進数として表示します。

## SYNTAX

### パス (既定値)

```
Format-Hex [-Path] <string[]> [<CommonParameters>]
```

### LiteralPath

```
Format-Hex -LiteralPath <string[]> [<CommonParameters>]
```

### ByInputObject

```
Format-Hex -InputObject <Object> [-Encoding <string>] [-Raw] [<CommonParameters>]
```

## Description

`Format-Hex`コマンドレットは、ファイルまたはその他の入力を16進数値として表示します。 出力からの文字のオフセットを確認するには、行の左端にある数値をその文字の列の先頭にある数値に追加します。

`Format-Hex`コマンドレットを使用すると、破損したファイルのファイルの種類やファイル名の拡張子が付いていないファイルを特定できます。 このコマンドレットを実行し、16進数の出力を読み取ってファイル情報を取得できます。

ファイルでを使用する場合 `Format-Hex` 、コマンドレットは、改行文字を無視して、改行文字が保持された1つの文字列内のファイルの内容全体を返します。

## 例

### 例 1: 文字列の16進数表現を取得する

このコマンドは、文字列の16進数の値を返します。

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

文字列 **Hello World** は、パイプラインを介してコマンドレットに送信され `Format-Hex` ます。 からの16進数の出力は、 `Format-Hex` 文字列の各文字の値を示しています。

### 例 2:16 進数の出力からファイルの種類を検索する

この例では、16進数の出力を使用して、ファイルの種類を決定します。 コマンドレットにより、ファイルの完全なパスと16進値が表示されます。

次のコマンドをテストするには、ローカルコンピューター上の既存の PDF ファイルのコピーを作成し、コピーしたファイルの名前を **t7f** に変更します。

```powershell
Format-Hex -Path .\File.t7f
```

```Output
           Path: C:\Test\File.t7f

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D  %PDF-1.5..%????.
00000010   0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70  .1 0 obj..<</Typ
00000020   65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20  e/Catalog/Pages
```

この `Format-Hex` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイル名を指定し `File.t7f` ます。 ファイル拡張子は `.t7f` 一般的ではありませんが、16進数の出力は `%PDF` PDF ファイルであることを示しています。

### 例 3: 生の16進数の出力を表示する

既定では `Format-Hex` 、数値データ型のコンパクト出力を指定します。値が十分小さい場合は、1バイトまたは2バイトのシーケンスが使用されます。 **Raw** パラメーターは、この動作を非アクティブにします。

```
PS> 1,2,3,1000 | Format-Hex

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 02 03 E8 03                                   ...è.


PS> 1,2,3,1000 | Format-Hex -Raw

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 00 00 00 02 00 00 00 03 00 00 00 E8 03 00 00  ............è...
```

出力の違いに注目してください。 **Raw** パラメーターは、4バイト値として数値を表示します。これらの **Int32** 型には true を指定します。

## PARAMETERS

### -Encoding

出力のエンコーディングを指定します。 これは、入力にのみ適用さ `[string]` れます。 パラメーターは数値型には影響しません。 既定値は `ASCII` です。

このパラメーターに指定できる値は次のとおりです。

- `Ascii` ASCII (7 ビット) 文字セットを使用します。
- `BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。
- `Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。
- `UTF7` UTF-7 を使用します。
- `UTF8` UTF-8 を使用します。
- `UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。

入力の ASCII 以外の文字は、リテラル文字として出力され、 `?` 情報が失われます。

```yaml
Type: System.String
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

パイプラインの入力に使用されます。 パイプライン入力は、パイプの特定のスカラー型とインスタンスのみをサポート `[system.io.fileinfo]` `Get-ChildItem` しています。

サポートされているスカラー型は次のとおりです。

- `[string]`
- `[byte]`
- `[int]`, `[int32]`
- `[long]`, `[int64]`

```yaml
Type: System.Object
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

ファイルへの完全パスを指定します。 **LiteralPath** の値は、入力されたとおりに使用されます。
このパラメーターでは、ワイルドカード文字は使用できません。 ファイルへの複数のパスを指定するには、パスをコンマで区切ります。 **LiteralPath** パラメーターにエスケープ文字が含まれている場合は、そのパスを単一引用符で囲みます。 PowerShell は、1つの引用符で囲まれた文字列内の文字をエスケープシーケンスとして解釈しません。 詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

ファイルへのパスを指定します。 現在の場所を指定するには、ドット () を使用し `.` ます。 ワイルドカード文字 ( `*` ) は受け入れられ、場所のすべての項目を指定するために使用できます。 **Path** パラメーターにエスケープ文字が含まれている場合は、パスを単一引用符で囲みます。 ファイルへの複数のパスを指定するには、パスをコンマで区切ります。

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Raw

既定では `Format-Hex` 、数値データ型のコンパクト出力を指定します。値が十分小さい場合は、1バイトまたは2バイトのシーケンスが使用されます。 **Raw** パラメーターは、この動作を非アクティブにします。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
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

### System.String

パイプを使用してこのコマンドレットに文字列を送ることができます。

## 出力

### ByteCollection です。

このコマンドレットは、 **ByteCollection** を返します。 このオブジェクトは、バイトのコレクションを表します。 これには、バイトのコレクションを、によって返される出力の各行のように書式設定された文字列に変換するメソッドが含まれてい `Format-Hex` ます。 **Path** または **LiteralPath** パラメーターを指定した場合、オブジェクトには、各バイトを含むファイルのパスも含まれます。

## 注

出力の右端の列は、バイトを文字として表示しようとします。

通常、各バイトは Unicode コードポイントとして解釈されます。これは、次のことを意味します。

- 印刷可能な ASCII 文字は、常に正しく表示されます。
- 複数バイトの UTF-8 文字が正しく表示されることはありません
- UTF-16 文字は、上位バイトが発生した場合にのみ正しくレンダリングさ `NUL` れます。

## 関連リンク

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[Format-Custom](Format-Custom.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)

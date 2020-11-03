---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-String
ms.openlocfilehash: 665a0ca8332c4052b59362c7947e408ba811c5f2
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "93219795"
---
# ConvertFrom-String

## 概要
文字列のコンテンツから構造化されたプロパティを抽出して解析します。

## SYNTAX

### ByDelimiter (既定値)

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### TemplateParsing

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## Description

**Convertfrom-csv** コマンドレットは、文字列のコンテンツから構造化されたプロパティを抽出して解析します。
このコマンドレットは、従来のテキストストリームからテキストを解析することによってオブジェクトを生成します。
コマンドレットは、パイプライン内の各文字列に対して、区切り記号または解析式によって入力を分割し、結果として得られる分割された各要素にプロパティ名を割り当てます。
これらのプロパティ名を指定できます。そうしないと、自動的に生成されます。

コマンドレットの既定のパラメーター set **Bydelimiter** は、正規表現の区切り記号で正確に分割されます。
コマンドレットの場合、引用符の照合や区切り記号のエスケープは実行されません `Import-Csv` 。

コマンドレットの代替パラメーターセットである **Templateparsing** は、正規表現によってキャプチャされたグループから要素を生成します。 正規表現の詳細については、「 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)」を参照してください。

このコマンドレットは、基本的に区切られた解析と、自動的に生成されたサンプルドリブン解析の2つのモードをサポートしています。

区切り記号による解析では、既定で、入力を空白の位置で分割し、生成されるグループにプロパティ名を割り当てます。

区切り記号をカスタマイズするには、 `ConvertFrom-String` コマンドレットのいずれかに結果をパイプし `Format-*` ます。または、 **delimiter** パラメーターを使用することもできます。

このコマンドレットは、 [FlashExtract、Microsoft research による研究作業](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/)に基づいて、自動的に生成された例に基づく解析もサポートしています。

## 例

### 例 1: 既定のプロパティ名を使用してオブジェクトを生成する

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

このコマンドは、既定のプロパティ名 **P1** および **P2** を持つオブジェクトを生成します。

### 例 1A: 生成されたオブジェクトを確認する

このコマンドは、 **P1** 、 **P2** のプロパティを持つ1つのオブジェクトを生成します。既定では、両方のプロパティが **文字列** 型です。

```powershell
"Hello World" | ConvertFrom-String | Get-Member
```

```Output

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
P1          NoteProperty string P1=Hello
P2          NoteProperty string P2=World
```

### 例 2: 区切り記号を使用して既定のプロパティ名を持つオブジェクトを生成する

このコマンドは、区切り記号として円記号 () を使用して、ドメインとユーザー名を持つオブジェクトを生成し `\` ます。 正規表現を使用する場合は、円記号を別の円記号でエスケープする必要があります。

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### 例 3: 2 つの名前付きプロパティを含むオブジェクトを生成する

次の例では、Windows ホストのファイルエントリからオブジェクトを作成します。

```powershell
$content = Get-Content C:\Windows\System32\drivers\etc\hosts
$content = $content -match "^[^#]"
$content | ConvertFrom-String -PropertyNames IP, Server
```

```Output
IP             Server
--             ------
192.168.7.10   W2012R2
192.168.7.20   W2016
192.168.7.101  WIN8
192.168.7.102  WIN10
```

この `Get-Content` コマンドレットは、Windows hosts ファイルの内容をに格納し `$content` ます。 2番目のコマンドは、() で始まらない任意の行と一致する正規表現を使用して、ホストファイルの先頭にあるすべてのコメントを削除し `#` ます。 最後のコマンドは、残りのテキストを、 **サーバー** と **IP** のプロパティを持つオブジェクトに変換します。

### 例 4: TemplateContent パラメーターの値として式を使用し、結果を変数に保存します。

このコマンドでは、 **templatecontent** パラメーターの値として式を使用します。
式は、わかりやすくするために変数に保存されます。
Windows PowerShell では、パイプラインで使用される文字列に3つのプロパティがあることが認識されて `ConvertFrom-String` います。

- **名前**
- **phone**
- **変更**

```powershell
$template = @'
{Name*:Phoebe Cat}, {phone:425-123-6789}, {age:6}
{Name*:Lucky Shot}, {phone:(206) 987-4321}, {age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789    6
Lucky Shot    (206) 987-4321  12
Elephant Wise 425-888-7766    87
Wild Shrimp   (111)  222-3333 1
```

入力の各行は、サンプルの一致によって評価されます。 この行がパターンに示されている例と一致する場合、値が抽出され、出力変数に渡されます。

サンプルデータには、 `$template` 次の2つの異なる電話形式が用意されています。

- `425-123-6789`
- `(206) 987-4321`

このサンプルデータには、次の2つの異なる年齢形式も用意されています。

- `6`
- `12`

これは、のような電話が認識されないことを意味 `(206) 987 4321` します。これは、ハイフンがないため、そのパターンに一致するサンプルデータがないためです。

### 例 5: 生成されるプロパティへのデータ型の指定

これは、上記の例4と同じ例です。
違いは、パターン文字列には、目的の各プロパティのデータ型が含まれていることです。

```powershell
$template = @'
{[string]Name*:Phoebe Cat}, {[string]phone:425-123-6789}, {[int]age:6}
{[string]Name*:Lucky Shot}, {[string]phone:(206) 987-4321}, {[int]age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789      6
Lucky Shot    (206) 987-4321   12
Elephant Wise 425-888-7766     87
Wild Shrimp   (111)  222-3333   1
```

```powershell
$PersonalData | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
age         NoteProperty int age=6
Name        NoteProperty string Name=Phoebe Cat
phone       NoteProperty string phone=425-123-6789
```

`Get-Member` **Age** プロパティが整数であることを示すには、コマンドレットを使用します。

## PARAMETERS

### -区切り記号

要素間の境界を識別する正規表現を指定します。
Split によって作成された要素は、結果として得られるオブジェクトのプロパティになります。
この区切り記号は、最終的に型の **Split** メソッドの呼び出しで使用され `[System.Text.RegularExpressions.RegularExpression]` ます。

```yaml
Type: System.String
Parameter Sets: ByDelimiter
Aliases: DEL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeExtent

このコマンドレットに、既定で削除されるエクステントテキストプロパティが含まれていることを示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: IE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

パイプラインから受け取る文字列、または文字列オブジェクトを含む変数を指定します。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PropertyNames

結果として得られるオブジェクトでの分割された値の割り当て先となるプロパティ名の配列を指定します。
分割または解析するテキストのすべての行で、プロパティ値を表す要素が生成されます。
要素がキャプチャグループの結果であり、そのキャプチャグループにという名前が付けられている場合 ( `(?<name>)` やなど `(?'name')` )、そのキャプチャグループの名前がプロパティに割り当てられます。

**PropertyName** 配列に要素を指定した場合、それらの名前は、まだ名前が付けられていないプロパティに割り当てられます。

フィールドの数よりも多くのプロパティ名を指定した場合、PowerShell は余分なプロパティ名を無視します。 すべてのフィールドに名前を付けるのに十分なプロパティ名を指定しない場合、PowerShell では、名前のないプロパティ ( **P1** 、 **P2** など) に数値プロパティ名が自動的に割り当てられます。

```yaml
Type: System.String[]
Parameter Sets: ByDelimiter
Aliases: PN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateContent 場合

このコマンドレットによって文字列が割り当てられるプロパティを記述する式、または変数として保存された式を指定します。 テンプレートフィールドの指定の構文は次のとおりです `{[optional-typecast]<name>:<example-value>}` 。

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateFile

文字列を解析するためのテンプレートを含むファイルを配列として指定します。
テンプレートファイルでは、次に示すように、プロパティとその値が角かっこで囲まれています。
**Name** プロパティやそれに関連付けられたその他のプロパティなどのプロパティが複数回表示される場合は、アスタリスク () を追加して、 `*` この結果が複数のレコードであることを示すことができます。 これにより、複数のプロパティを1つのレコードに抽出することが回避されます。

```
{Name*:David Chew}
{City:Redmond}, {State:WA}
{Name*:Evan Narvaez}    {Name*:Antonio Moreno}
{City:Issaquah}, {State:WA}
```

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateTemplate

このコマンドレットが、学習アルゴリズムの結果をテンプレートファイル内のコメントに保存することを示します。
これにより、アルゴリズム学習プロセスが高速になります。
このパラメーターを使用するには、 **TemplateFile** パラメーターを使用してテンプレートファイルを指定する必要もあります。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: UT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### System.String

## 出力

## 注

## 関連リンク

[Convertfrom-csv: サンプルベースのテキスト解析](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)

[ConvertFrom-StringData](ConvertFrom-StringData.md)

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Xml](ConvertTo-Xml.md)

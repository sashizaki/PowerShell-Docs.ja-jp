---
description: PowerShell の値を比較する演算子について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: b6076e20ad3ecbe9f2def157bb20bdb3bee5b7ad
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224531"
---
# <a name="about-comparison-operators"></a>比較演算子について

## <a name="short-description"></a>簡単な説明
PowerShell の値を比較する演算子について説明します。

## <a name="long-description"></a>長い説明

比較演算子を使用すると、値を比較し、指定したパターンに一致する値を検索するための条件を指定できます。 比較演算子を使用するには、比較する値を、これらの値を区切る演算子と組み合わせて指定します。

PowerShell には、次の比較演算子が含まれています。

| Type        | 演算子    | 説明                                 |
| ----------- | ------------ | --------------------------------------------|
| 等式    | -eq          | 次の値に等しい                                      |
|             | -ne          | 等しくない                                  |
|             | -gt          | より大きい                                |
|             | -ge          | 以上                       |
|             | -lt          | 次の値未満                                   |
|             | -le          | 以下                          |
|             |              |                                             |
| Matching    | -like        | 文字列がワイルドカードに一致する場合に true を返します   |
|             |              | pattern                                     |
|             | -notlike     | 文字列が一致しない場合に true を返します     |
|             |              | ワイルドカードパターン                            |
|             | -match       | 文字列が regex と一致する場合に true を返します      |
|             |              | 種類$matches に一致する文字列が含まれています |
|             | -notmatch    | 文字列が一致しない場合に true を返します     |
|             |              | regex パターン;一致する $matches が含まれています   |
|             |              | 文字列                                     |
|             |              |                                             |
| Containment | -contains    | 参照値が含まれている場合に true を返します |
|             |              | コレクション内                             |
|             | -notcontains | 参照値が指定されていない場合に true を返します       |
|             |              | コレクションに含まれる                   |
|             | -in          | テスト値がに含まれている場合に true を返します |
|             |              | collection                                  |
|             | -notin       | テスト値が含まれていない場合に true を返します  |
|             |              | コレクション内                             |
|             |              |                                             |
| Replacement | -replace     | 文字列パターンを置換します。                   |
|             |              |                                             |
| Type        | -が          | 両方のオブジェクトが同じ場合に true を返します。    |
|             |              | type                                        |
|             | -isnot       | オブジェクトが同じでない場合に true を返します。|
|             |              | type                                        |

既定では、すべての比較演算子で大文字と小文字が区別されます。 大文字と小文字を区別する比較演算子を作成するには、演算子名の前にを付け `c` ます。 たとえば、の大文字と小文字を区別するバージョン `-eq` はです `-ceq` 。 大文字小文字を区別しないようにするには、演算子の前にを付け `i` ます。 たとえば、の明示的な大文字と小文字を区別しないバージョン `-eq` はです `-ieq` 。

演算子への入力がスカラー値の場合、比較演算子はブール値を返します。 入力が値のコレクションである場合、比較演算子は一致する値を返します。 コレクションに一致するものがない場合、比較演算子は空の配列を返します。

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

例外は、包含演算子、In 演算子、および型演算子で、常に **ブール** 値を返します。

> [!NOTE]
> 値をと比較する必要がある場合は、 `$null` `$null` 比較の左側に配置する必要があります。 `$null`**オブジェクト []** と比較すると、比較オブジェクトが配列であるため、結果は **False** になります。 配列をと比較すると `$null` 、比較によって `$null` 配列に格納されているすべての値が除外されます。 次に例を示します。
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a>等値演算子

等値演算子 ( `-eq` 、 `-ne` ) は、1つ以上の入力値が指定されたパターンと同じ場合に TRUE または一致する値を返します。 パターン全体が値全体と一致している必要があります。

例:

#### <a name="-eq"></a>-eq

説明: と等しい。 には、同じ値が含まれます。

例:

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

#### <a name="-ne"></a>-ne

説明: 等しくない。 に別の値が含まれています。

例:

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

#### <a name="-gt"></a>-gt

説明: より大きい。

例:

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> `>`他の多くのプログラミング言語では、大なり演算子と混同しないようにしてください。 PowerShell で `>` は、はリダイレクトに使用されます。 詳細については、「 [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators)」を参照してください。

#### <a name="-ge"></a>-ge

説明: より大きいか等しい。

例:

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a>-lt

説明: より小さい。

例:

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a>-le

説明: 次の値より小さいか等しい。

例:

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a>照合演算子

Like 演算子 ( `-like` および) は、 `-notlike` ワイルドカード式を使用して、指定したパターンに一致するか一致しない要素を検索します。

の構文は次のとおりです。

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

一致演算子 ( `-match` および) は、 `-notmatch` 正規表現を使用して、指定したパターンに一致するか一致しない要素を検索します。

一致演算子は、 `$Matches` 演算子への入力 (左側の引数) が単一のスカラーオブジェクトである場合に、自動変数を設定します。 入力がスカラーの場合、 `-match` および `-notmatch` 演算子はブール値を返し、 `$Matches` 自動変数の値を引数の一致するコンポーネントに設定します。

の構文は次のとおりです。

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a>-like

説明: ワイルドカード文字 () を使用して一致し \* ます。

例:

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a>-notlike

説明: は、ワイルドカード文字 () を使用して一致しません \* 。

例:

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a>-match

説明: 正規表現を使用して文字列に一致します。 入力がスカラーの場合は、自動変数が設定され `$Matches` ます。

入力がコレクションの場合、演算子 `-match` と演算子は、 `-notmatch` そのコレクションの一致するメンバーを返しますが、演算子は変数に値を設定しません `$Matches` 。

たとえば、次のコマンドは、文字列のコレクションを演算子に送信し `-match` ます。 演算子は、 `-match` 一致するコレクション内の項目を返します。 自動変数は設定されません `$Matches` 。

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

これに対して、次のコマンドは、1つの文字列を演算子に送信し `-match` ます。 `-match`演算子はブール値を返し、自動変数を設定し `$Matches` ます。 `$Matches`自動変数は **ハッシュテーブル** です。 グループ化またはキャプチャが使用されていない場合は、1つのキーだけが設定されます。
キーは、 `0` 一致したすべてのテキストを表します。 正規表現を使用したグループ化とキャプチャの詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

ハッシュテーブルには、一致するパターンが最初に出現するだけが含まれていることに注意して `$Matches` ください。

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> `0`キーは **整数** です。 任意の **ハッシュテーブル** メソッドを使用して、格納されている値にアクセスできます。
>
> ```powershell
> PS> "Good Dog" -match "Dog"
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

演算子は、 `-notmatch` `$Matches` 入力がスカラーのときに自動変数を設定し、結果が False であること、つまり一致が検出されたときにその変数を設定します。

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

#### <a name="-notmatch"></a>-notmatch

説明: が文字列と一致しません。 正規表現を使用します。 入力がスカラーの場合は、自動変数が設定され `$Matches` ます。

例:

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

### <a name="containment-operators"></a>含有演算子

含有演算子 ( `-contains` と `-notcontains` ) は、等値演算子に似ています。 ただし、入力がコレクションの場合でも、コンテインメント演算子は常にブール値を返します。

また、等値演算子とは異なり、コンテインメント演算子は、最初の一致を検出するとすぐに値を返します。 等値演算子は、すべての入力を評価し、コレクション内のすべての一致を返します。

#### <a name="-contains"></a>-contains

説明: コンテインメント演算子。 参照値のコレクションに1つのテスト値が含まれているかどうかを示します。 常にブール値を返します。 テスト値が参照値の少なくとも1つと完全に一致する場合にのみ TRUE を返します。

テスト値がコレクションの場合、Contains 演算子は参照の等価性を使用します。 参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。

非常に大きなコレクションでは、 `-contains` 演算子は equal to 演算子よりも結果を迅速に返します。

構文:

`<Reference-values> -contains <Test-value>`

例:

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

#### <a name="-notcontains"></a>-notcontains

説明: コンテインメント演算子。 参照値のコレクションに1つのテスト値が含まれているかどうかを示します。 常にブール値を返します。 テスト値が参照値の少なくとも1つと完全に一致しない場合に TRUE を返します。

テスト値がコレクションの場合、NotContains 演算子は参照の等価性を使用します。

構文:

`<Reference-values> -notcontains <Test-value>`

例:

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

#### <a name="-in"></a>-in

説明: In 演算子。 テスト値が参照値のコレクションに表示されるかどうかを示します。 常にブール値として返されます。 テスト値が参照値の少なくとも1つと完全に一致する場合にのみ TRUE を返します。

テスト値がコレクションの場合、In 演算子は参照の等価性を使用します。
参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。

演算子は、 `-in` PowerShell 3.0 で導入されました。

構文:

`<Test-value> -in <Reference-values>`

例:

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

#### <a name="-notin"></a>-notin

Description: テスト値が参照値のコレクションに表示されるかどうかを示します。 常にブール値を返します。 テスト値が参照値の少なくとも1つと完全に一致しない場合に TRUE を返します。

テスト値がコレクションの場合、In 演算子は参照の等価性を使用します。
参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。

演算子は、 `-notin` PowerShell 3.0 で導入されました。

構文:

`<Test-value> -notin <Reference-values>`

例:

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

### <a name="replacement-operator"></a>置換演算子

演算子は、 `-replace` 値のすべてまたは一部を、正規表現を使用して、指定された値に置き換えます。 `-replace`演算子は、ファイル名の変更など、多くの管理タスクに使用できます。 たとえば、次のコマンドは、すべての .txt ファイルのファイル名拡張子を .log に変更します。

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

演算子の構文は次のようになります。プレースホルダーは、置換する `-replace` 文字を表し、プレースホルダーはそれらを `<original>` `<substitute>` 置き換える文字を表します。

`<input> <operator> <original>, <substitute>`

既定では、 `-replace` 演算子は大文字と小文字を区別しません。 大文字と小文字を区別するには、を使用 `-creplace` します。 大文字と小文字を区別しないようにするには、を使用 `-ireplace` します。

次の例を考慮してください。

```powershell
PS> "book" -replace "B", "C"
```

```Output
Cook
```

```powershell
"book" -ireplace "B", "C"
```

```Output
Cook
```

```powershell
"book" -creplace "B", "C"
```

```Output
book
```

また、正規表現を使用して、キャプチャグループと置換を使用してテキストを動的に置換することもできます。 詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。

#### <a name="substitutions-in-regular-expressions"></a>正規表現での置換

さらに、キャプチャグループは文字列で参照でき \<substitute\> ます。
これを行うには、 `$` グループ識別子の前にある文字を使用します。

キャプチャグループを参照する2つの方法は、数値と **名前** で **指定** します。

- **数値** による -
   キャプチャグループには、左から右に番号が付けられます。

  ```powershell
  "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- 名前 **によって** -
   キャプチャグループを名前で参照することもできます。

  ```powershell
  "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKOM\Administrator
  ```

> [!WARNING]
> 文字は `$` 文字列の展開で使用されるため、置換でリテラル文字列を使用するか、文字をエスケープする必要があり `$` ます。
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> ```
>
> また、 `$` 文字が置換で使用されるため、文字列内のすべてのインスタンスをエスケープする必要があります。
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> ```
>
> ```Output
> $5.72
> ```

詳細については、「[正規表現での](/dotnet/standard/base-types/substitutions-in-regular-expressions) [about_Regular_Expressions](about_Regular_Expressions.md)と置換」を参照してください。

### <a name="type-comparison"></a>型の比較

型の比較演算子 ( `-is` と `-isnot` ) は、オブジェクトが特定の型であるかどうかを判断するために使用されます。

#### <a name="-is"></a>-が

構文:

`<object> -is <type reference>`

例:

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a>-isnot

構文:

`<object> -isnot <type reference>`

例:

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a>関連項目

- [about_Operators](about_Operators.md)
- [about_Regular_Expressions](about_Regular_Expressions.md)
- [about_Wildcards](about_Wildcards.md)
- [Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [Foreach-オブジェクト](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)

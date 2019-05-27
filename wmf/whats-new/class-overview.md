---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: PowerShell クラスを使用したカスタム型の作成
ms.openlocfilehash: 0dd5bbaca50abb746e15a7bb64a706c7eceee905
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855537"
---
# <a name="creating-custom-types-using-powershell-classes"></a>PowerShell クラスを使用したカスタム型の作成

PowerShell 5.0 では、他のオブジェクト指向プログラミング言語のように、形式的構文とセマンティクスを使って、クラスや他のユーザー定義型を定義する機能が追加されました。 開発者や IT プロフェッショナルがより広範なユース ケースで PowerShell を採用できるようにし、PowerShell アーティファクト (DSC リソースなど) の開発を簡素化し、管理面の対応を促進することがその目標です。

## <a name="supported-scenarios-in-this-release"></a>このリリースでサポートされるシナリオ

- PowerShell 言語を使用して DSC リソースとその関連する型を定義する
- クラス、プロパティ、メソッドなどの使い慣れたオブジェクト指向プログラミングの構成要素を使用して PowerShell でカスタム型を定義する
- PowerShell のクラスおよびクラス ベース DSC リソースを使用した継承のサポート
- PowerShell 言語を使用した型のデバッグ
- 公式的なメカニズムを適切なレベルで使用した例外の生成および処理

# <a name="declare-base-class"></a>基本クラスの宣言

ある PowerShell クラスを、別の PowerShell クラスの基本型として宣言できます。

```powershell
class bar
{
   [int]foo()
       {
           return 100500
       }
}

class baz : bar {}

[baz]::new().foo() # return 100500
```

既存の .NET Framework 型を基本クラスとして使用することもできます。

```powershell
class MyIntList : system.collections.generic.list[int]
{

}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```

# <a name="call-base-class-constructor"></a>基本クラス コンストラクターの呼び出し

サブクラスから基本クラス コンストラクターを呼び出すには、キーワード **base** を使用します。

```powershell
class A
{
    [int]$a

    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

[B]::new().a # return 103
```

基本クラスに既定の (パラメーターなし) コンストラクターがある場合は、明示的なコンストラクター呼び出しを省略できます。

```powershell
class C : B
{
    C([int]$c) {}
}
```

# <a name="call-base-class-method"></a>基本クラス メソッドの呼び出し

サブクラスで既存のメソッドをオーバーライドすることができます。 そのためには、同じ名前およびシグネチャを使用してメソッドを宣言します。

```powershell
class baseClass
{
    [int]foo() {return 100500}
}

class childClass1 : baseClass
{
    [int]foo() {return 200600}
}

[childClass1]::new().foo() # return 200600
```

オーバーライドされた実装から基底クラスのメソッドを呼び出すには、呼び出し時に基底クラスにキャストします (`[baseClass]$this`)。

```powershell
class childClass2 : baseClass
{
    [int]foo()
    {
        return 3 * ([baseClass]$this).foo()
    }
}

[childClass2]::new().foo() # return 301500
```

すべての PowerShell メソッドは仮想です。 オーバーライドの場合と同じ構文を使用し、同じ名前とシグネチャを持つメソッドを宣言することにより、サブクラスの非仮想 .NET メソッドを隠ぺいできます。

```powershell
class MyIntList : system.collections.generic.list[int]
{
    # Add is final in system.collections.generic.list
    [void] Add([int]$arg)
    {
        ([system.collections.generic.list[int]]$this).Add($arg * 2)
    }
}

$list = [MyIntList]::new()
$list.Add(100)
$list[0] # return 200
```

# <a name="declare-implemented-interface"></a>実装されたインターフェイスの宣言

基本型が指定されていない場合、基本型の後、またはコロン (:) の直後に、実装されたインターフェイスを宣言することができます。 コンマを使用してすべての型名を区切ります。 C# の構文と似ています。

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableBar : bar, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

# <a name="new-language-features-in-powershell-50"></a>PowerShell 5.0 の新しい言語機能

PowerShell 5.0 では、PowerShell に次の新しい言語要素が導入されています。

## <a name="class-keyword"></a>class キーワード

`class` キーワードでは新しいクラスを定義します。 これは、真の .NET Framework 型です。 クラス メンバーはパブリックですが、モジュール スコープ内でのみパブリックです。 型名を文字列として参照することはできません (たとえば、`New-Object` は機能しません)。このリリースでは、クラスが定義されているスクリプトまたはモジュール ファイルの外で type リテラル (`[MyClass]` など) を使用することはできません。

```powershell
class MyClass
{
    ...
}
```

## <a name="enum-keyword-and-enumerations"></a>enum キーワードおよび列挙

区切り文字として改行文字を使用する `enum` キーワードのサポートが追加されました。 現時点では、列挙子自体に関して列挙子を定義することはできません。 ただし、次の例に示すように、別の列挙型に関して列挙型を初期化することはできます。 また、基本データ型を指定することはできません。基本データ型は常に `[int]` です。

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

列挙子の値は、解析時定数である必要があります。 呼び出されたコマンドの結果に、それを設定することはできません。

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

次の例に示すように、enum では算術演算がサポートされます。

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

## <a name="import-dscresource"></a>Import-DscResource

`Import-DscResource` は真の動的キーワードです。 PowerShell では、**DscResource** 属性を含むクラスを探して、指定されたモジュールのルート モジュールを解析します。

## <a name="implementingassembly"></a>ImplementingAssembly

新しいフィールド **ImplementingAssembly** が **ModuleInfo** に追加されました。 これは、スクリプトでクラスが定義されている場合はスクリプト モジュールに作成された動的アセンブリに設定されるか、またはバイナリ モジュールの読み込み済みアセンブリに設定されます。 **ModuleType** が **Manifest** の場合は設定されません。

**ImplementingAssembly** フィールドのリフレクションでは、モジュール内のリソースが検出されます。 これは、PowerShell または他の管理言語で記述されたリソースを検出できることを意味します。

初期化子を含むフィールド:

```powershell
[int] $i = 5
```

`Static` はサポートされています。 属性のように動作し、型の制約を行います。 任意の順序で指定できます。

```powershell
static [int] $count = 0
```

型は省略できます。

```powershell
$s = "hello"
```

すべてのメンバーはパブリックです。

## <a name="constructors-and-instantiation"></a>コンストラクターとインスタンス化

PowerShell のクラスは、コンストラクターを持つことができます。 クラスと同じ名前です。 コンストラクターはオーバーロードできます。 静的コンストラクターがサポートされています。 初期化式を持つプロパティは、コンストラクター内のコードを実行する前に初期化されます。 静的プロパティは、静的コンストラクターの本体の前に初期化され、インスタンスのプロパティは、非静的コンストラクターの本体の前に初期化されます。 現時点では、(C\# 構文 ": this()" のような) 別のコンストラクターからコンストラクターを呼び出す構文はありません。 回避策は、一般的な `Init()` メソッドを定義することです。

### <a name="creating-instances"></a>インスタンスの作成

> [!NOTE]
> PowerShell 5.0 では、PowerShell で定義されたクラスでは `New-Object` は機能しません。 また、型名は語彙的にのみ表示され、クラスを定義するモジュールまたはスクリプトの外部では表示されません。 関数は、PowerShell で定義されているクラスのインスタンスを返すことができます。 それらのインスタンスは、モジュールまたはスクリプトの外部で動作します。

1. 既定のコンストラクターを使用したインスタンス化。

   ```powershell
   $a = [MyClass]::new()
   ```

1. パラメーターを持つコンストラクターの呼び出し

   ```powershell
   $b = [MyClass]::new(42)
   ```

1. 複数のパラメーターを持つコンストラクターへの配列の引き渡し。

   ```powershell
   $c = [MyClass]::new(@(42,43,44), "Hello")
   ```

次の例に示すように、擬似静的メソッド `new()` は .NET 型で機能します。

```powershell
[hashtable]::new()
```

### <a name="discovering-constructors"></a>コンストラクターの検出

`Get-Member` を使って、またはこの例で示すようにして、コンストラクターのオーバーロードを確認できるようになりました。

```powershell
PS> [hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

`Get-Member -Static` ではコンストラクターが一覧表示されるため、他のメソッドと同様にオーバーロードを表示できます。 また、この構文のパフォーマンスは、`New-Object` より大幅に高速です。

## <a name="methods"></a>メソッド

PowerShell のクラス メソッドは、end ブロックのみを持つ **ScriptBlock** として実装されます。 すべてのメソッドはパブリックです。 **DoSomething** という名前のメソッドを定義する例を次に示します。

```powershell
class MyClass
{
    DoSomething($x)
    {
        $this._doSomething($x) # method syntax
    }
    private _doSomething($a) {}
}
```

メソッドの呼び出し:

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

オーバーロードされたメソッドもサポートされます。

## <a name="properties"></a>プロパティ

すべてのプロパティはパブリックです。 プロパティには、改行文字かセミコロンが必要です。 オブジェクトの種類が指定されていない場合、プロパティの型はオブジェクトです。

検証属性または引数変換属性を使用するプロパティ (`[ValidateSet("aaa")]` など) は期待どおりに動作します。

## <a name="hidden"></a>Hidden

新しいキーワード `Hidden` が追加されました。 `Hidden` は、プロパティとメソッド (コンストラクターを含む) に適用できます。

Hidden のメンバーはパブリックですが、-Force パラメーターを追加しない限り、`Get-Member` の出力には含められません。 Hidden のメンバーを定義するクラスで完了が発生しない限り、タブの完了時、または IntelliSense の使用時に Hidden のメンバーは含まれません。

C\# コードで PowerShell 内と同じセマンティクスを使用できるように、新しい属性 **System.Management.Automation.HiddenAttribute** が追加されました。

## <a name="return-types"></a>戻り値の型

戻り値の型はコントラクトです。 戻り値は、予期された型に変換されます。 戻り値の型が指定されていない場合、戻り値の型は **void** です。 オブジェクトのストリーミングはありません。 オブジェクトが意図的または誤ってパイプラインに書き込まれることはありません。

## <a name="attributes"></a>属性

2 つの新しい属性 **DscResource** と **DscProperty** が追加されました。

## <a name="lexical-scoping-of-variables"></a>変数の語彙的スコープ

今回のリリースで語彙的スコープが機能する方法の例を次に示します。

```powershell
$d = 42 # Script scope

function bar
{
    $d = 0 # Function scope
    [MyClass]::DoSomething()
}

class MyClass
{
    static [object] DoSomething()
    {
        return $d # error, not found dynamically
        return $script:d # no error
        $d = $script:d
        return $d # no error, found lexically
    }
}

$v = bar
$v -eq $d # true
```

## <a name="end-to-end-example"></a>エンド ツー エンドの例

次の例では、HTML 動的スタイル シート言語 (DSL) を実装するいくつかのカスタム クラスを作成します。 次に、モジュールのスコープの外部では型を使用できないため、この例では見出しスタイルやテーブルなど、要素クラスの一部として特定の要素型を作成するヘルパー関数を追加します。

```powershell
# Classes that define the structure of the document
#
class Html
{
    [string] $docType
    [HtmlHead] $Head
    [Element[]] $Body

    [string] Render()
    {
        $text = "<html>`n<head>`n"
        $text += $this.Head
        $text += "`n</head>`n<body>`n"
        $text += $this.Body -join "`n" # Render all of the body elements
        $text += "</body>`n</html>"
        return $text
    }
    [string] ToString() { return $this.Render() }
}

class HtmlHead
{
    $Title
    $Base
    $Link
    $Style
    $Meta
    $Script
    [string] Render() { return "<title>$($this.Title)</title>" }
    [string] ToString() { return $this.Render() }
}

class Element
{
    [string] $Tag
    [string] $Text
    [hashtable] $Attributes
    [string] Render() {
        $attributesText= ""
        if ($this.Attributes)
        {
            foreach ($attr in $this.Attributes.Keys)
            {
                #BUGBUG - need to validate keys against attribute
                $attributesText += " $attr=`"$($this.Attributes[$attr])\`""
            }
        }
        return "<$($this.tag)${attributesText}>$($this.text)</$($this.tag)>`n"
    }
[string] ToString() { return $this.Render() }
}

#
# Helper functions for creating specific element types on top of the classes.
# These are required because types aren't visible outside of the module.
#

function H1 { [Element] @{ Tag = "H1" ; Text = $args.foreach{$_} -join " " }}
function H2 { [Element] @{ Tag = "H2" ; Text = $args.foreach{$_} -join " " }}
function H3 { [Element] @{ Tag = "H3" ; Text = $args.foreach{$_} -join " " }}
function P { [Element] @{ Tag = "P" ; Text = $args.foreach{$_} -join " " }}
function B { [Element] @{ Tag = "B" ; Text = $args.foreach{$_} -join " " }}
function I { [Element] @{ Tag = "I" ; Text = $args.foreach{$_} -join " " }}
function HREF
{
    param (
        $Name,
        $Link
    )
    return [Element] @{
        Tag = "A"
        Attributes = @{ HREF = $link }
        Text = $name
    }
}
function Table
{
    param (
    [Parameter(Mandatory)]
    [object[]]
        $Data,
    [Parameter()]
    [string[]]
        $Properties = "*",
    [Parameter()]
    [hashtable]
        $Attributes = @{ border=2; cellpadding=2; cellspacing=2 }
    )
$bodyText = ""
# Add the header tags
$bodyText += $Properties.foreach{TH $_}
# Add the rows
$bodyText += foreach ($row in $Data)
    {
        TR (-join $Properties.Foreach{ TD ($row.$_) } )
    }

    $table = [Element] @{
        Tag = "Table"
        Attributes = $Attributes
        Text = $bodyText
    }
$table
}
function TH { ([Element] @{ Tag = "TH" ; Text = $args.foreach{$_} -join " " }) }
function TR { ([Element] @{ Tag = "TR" ; Text = $args.foreach{$_} -join " " }) }
function TD { ([Element] @{ Tag = "TD" ; Text = $args.foreach{$_} -join " " }) }
function Style

{
    return [Element] @{
        Tag = "style"
        Text = "$args"
    }
}

# Takes a hash table, casts it to and HTML document
# and then returns the resulting type.
#
function Html ([HTML] $doc) { return $doc }
```

---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: a96a4a58dafa01fb43f5bdffb52ef833816148e7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058371"
---
# <a name="new-language-features-in-powershell-50"></a><span data-ttu-id="150e7-102">PowerShell 5.0 の新しい言語機能</span><span class="sxs-lookup"><span data-stu-id="150e7-102">New language features in PowerShell 5.0</span></span>

<span data-ttu-id="150e7-103">PowerShell 5.0 では、Windows PowerShell に次の新しい言語要素が導入されています。</span><span class="sxs-lookup"><span data-stu-id="150e7-103">PowerShell 5.0 introduces the following new language elements in Windows PowerShell:</span></span>

## <a name="class-keyword"></a><span data-ttu-id="150e7-104">class キーワード</span><span class="sxs-lookup"><span data-stu-id="150e7-104">Class keyword</span></span>

<span data-ttu-id="150e7-105">**class** キーワードでは新しいクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="150e7-105">The **class** keyword defines a new class.</span></span> <span data-ttu-id="150e7-106">これは、真の .NET Framework 型です。</span><span class="sxs-lookup"><span data-stu-id="150e7-106">This is a true .NET Framework type.</span></span>
<span data-ttu-id="150e7-107">クラス メンバーはパブリックですが、モジュール スコープ内でのみパブリックです。</span><span class="sxs-lookup"><span data-stu-id="150e7-107">Class members are public, but only public within the module scope.</span></span>
<span data-ttu-id="150e7-108">型名を文字列として参照することはできません (たとえば、`New-Object` は機能しません)。このリリースでは、クラスが定義されているスクリプトまたはモジュール ファイルの外で type リテラル (`[MyClass]` など) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="150e7-108">You can't refer to the type name as a string (for example, `New-Object` doesn't work), and in this release, you can't use a type literal (for example, `[MyClass]`) outside the script/module file in which the class is defined.</span></span>

```powershell
class MyClass
{
    ...
}
```

## <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="150e7-109">enum キーワードおよび列挙</span><span class="sxs-lookup"><span data-stu-id="150e7-109">Enum keyword and enumerations</span></span>

<span data-ttu-id="150e7-110">区切り文字として改行文字を使用する **enum** キーワードのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="150e7-110">Support for the **enum** keyword has been added, which uses newline as the delimiter.</span></span>
<span data-ttu-id="150e7-111">現在の制限事項: 列挙子自体から列挙子を定義することはできませんが、次の例に示すように、別の enum から enum を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="150e7-111">Current limitations: you cannot define an enumerator in terms of itself, but you can initialize an enum in terms of another enum, as shown in the following example.</span></span>
<span data-ttu-id="150e7-112">また、現在、基本型を指定することはできません。基本型は常に [int] です。</span><span class="sxs-lookup"><span data-stu-id="150e7-112">Also, the base type cannot currently be specified; it is always [int].</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="150e7-113">列挙子の値は、解析時定数である必要があります。呼び出されたコマンドの結果に設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="150e7-113">An enumerator value must be a parse time constant; you cannot set it to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="150e7-114">次の例に示すように、enum では算術演算がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="150e7-114">Enums support arithmetic operations, as shown in the following example.</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

## <a name="import-dscresource"></a><span data-ttu-id="150e7-115">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="150e7-115">Import-DscResource</span></span>

<span data-ttu-id="150e7-116">**Import-DscResource** は真の動的キーワードです。</span><span class="sxs-lookup"><span data-stu-id="150e7-116">**Import-DscResource** is now a true dynamic keyword.</span></span>
<span data-ttu-id="150e7-117">PowerShell では、**DscResource** 属性を含むクラスを探して、指定されたモジュールのルート モジュールを解析します。</span><span class="sxs-lookup"><span data-stu-id="150e7-117">PowerShell parses the specified module’s root module, searching for classes that contain the **DscResource** attribute.</span></span>

## <a name="implementingassembly"></a><span data-ttu-id="150e7-118">ImplementingAssembly</span><span class="sxs-lookup"><span data-stu-id="150e7-118">ImplementingAssembly</span></span>

<span data-ttu-id="150e7-119">新しいフィールド **ImplementingAssembly** が ModuleInfo に追加されました。</span><span class="sxs-lookup"><span data-stu-id="150e7-119">A new field, **ImplementingAssembly**, has been added to ModuleInfo.</span></span> <span data-ttu-id="150e7-120">これは、スクリプトでクラスが定義されている場合はスクリプト モジュールに作成された動的アセンブリに設定されるか、またはバイナリ モジュールの読み込み済みアセンブリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="150e7-120">It is set to the dynamic assembly created for a script module if the script defines classes, or the loaded assembly for binary modules.</span></span> <span data-ttu-id="150e7-121">ModuleType = Manifest の場合は設定されません。</span><span class="sxs-lookup"><span data-stu-id="150e7-121">It is not set when ModuleType = Manifest.</span></span>

<span data-ttu-id="150e7-122">**ImplementingAssembly** フィールドのリフレクションでは、モジュール内のリソースが検出されます。</span><span class="sxs-lookup"><span data-stu-id="150e7-122">Reflection on the **ImplementingAssembly** field discovers resources in a module.</span></span> <span data-ttu-id="150e7-123">これは、PowerShell または他の管理言語で記述されたリソースを検出できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="150e7-123">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

<span data-ttu-id="150e7-124">初期化子を含むフィールド:</span><span class="sxs-lookup"><span data-stu-id="150e7-124">Fields with initializers:</span></span>

```powershell
[int] $i = 5
```

<span data-ttu-id="150e7-125">static がサポートされています。これは型の制約と同様に属性のように機能するため、任意の順序で指定できます。</span><span class="sxs-lookup"><span data-stu-id="150e7-125">Static is supported; it works like an attribute, as do the type constraints, so it can be specified in any order.</span></span>

```powershell
static [int] $count = 0
```

<span data-ttu-id="150e7-126">型は省略できます。</span><span class="sxs-lookup"><span data-stu-id="150e7-126">A type is optional.</span></span>

```powershell
$s = "hello"
```

<span data-ttu-id="150e7-127">すべてのメンバーはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="150e7-127">All members are public.</span></span>

## <a name="constructors-and-instantiation"></a><span data-ttu-id="150e7-128">コンストラクターとインスタンス化</span><span class="sxs-lookup"><span data-stu-id="150e7-128">Constructors and instantiation</span></span>

<span data-ttu-id="150e7-129">Windows PowerShell クラスはコンストラクターを持つことができます。コンストラクターはクラスと同じ名前を持ちます。</span><span class="sxs-lookup"><span data-stu-id="150e7-129">Windows PowerShell classes can have constructors; they have the same name as their class.</span></span> <span data-ttu-id="150e7-130">コンストラクターはオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="150e7-130">Constructors can be overloaded.</span></span> <span data-ttu-id="150e7-131">静的コンストラクターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="150e7-131">Static constructors are supported.</span></span> <span data-ttu-id="150e7-132">初期化式を持つプロパティは、コンストラクター内のコードを実行する前に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="150e7-132">Properties with initialization expressions are initialized before running any code in a constructor.</span></span> <span data-ttu-id="150e7-133">静的プロパティは、静的コンストラクターの本体の前に初期化され、インスタンスのプロパティは、非静的コンストラクターの本体の前に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="150e7-133">Static properties are initialized before the body of a static constructor, and instance properties are initialized before the body of the non-static constructor.</span></span> <span data-ttu-id="150e7-134">現時点では、(C\# 構文 ": this()" のような) 別のコンストラクターからコンストラクターを呼び出す構文はありません。</span><span class="sxs-lookup"><span data-stu-id="150e7-134">Currently, there is no syntax for calling a constructor from another constructor (like the C\# syntax ": this()").</span></span> <span data-ttu-id="150e7-135">対応策は、一般的な Init メソッドを定義することです。</span><span class="sxs-lookup"><span data-stu-id="150e7-135">The workaround is to define a common Init method.</span></span>

<span data-ttu-id="150e7-136">このリリースでクラスをインスタンス化する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="150e7-136">The following are ways of instantiating classes in this release.</span></span>

<span data-ttu-id="150e7-137">既定のコンストラクターを使用したインスタンス化。</span><span class="sxs-lookup"><span data-stu-id="150e7-137">Instantiating by using the default constructor.</span></span> <span data-ttu-id="150e7-138">New-Object はこのリリースではサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="150e7-138">Note that New-Object is not supported in this release.</span></span>

```powershell
$a = [MyClass]::new()
```

<span data-ttu-id="150e7-139">パラメーターを持つコンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="150e7-139">Calling a constructor with a parameter</span></span>

```powershell
$b = [MyClass]::new(42)
```

<span data-ttu-id="150e7-140">複数のパラメーターを持つコンストラクターに配列を渡す</span><span class="sxs-lookup"><span data-stu-id="150e7-140">Passing an array to a constructor with multiple parameters</span></span>
```powershell
$c = [MyClass]::new(@(42,43,44), "Hello")
```

<span data-ttu-id="150e7-141">このリリースでは、New-Object は Windows PowerShell で定義されたクラスでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="150e7-141">In this release, New-Object does not work with classes defined in Windows PowerShell.</span></span> <span data-ttu-id="150e7-142">また、このリリースでは、型名は語彙的にのみ表示され、クラスを定義するモジュールまたはスクリプトの外部では表示されません。</span><span class="sxs-lookup"><span data-stu-id="150e7-142">Also for this release, the type name is only visible lexically, meaning it is not visible outside of the module or script that defines the class.</span></span> <span data-ttu-id="150e7-143">関数は、Windows PowerShell で定義されているクラスのインスタンスを返すことができ、インスタンスは、モジュールまたはスクリプトの外部でも機能します。</span><span class="sxs-lookup"><span data-stu-id="150e7-143">Functions can return instances of a class defined in Windows PowerShell, and instances work well outside of the module or script.</span></span>

<span data-ttu-id="150e7-144">`Get-Member -Static` ではコンストラクターが一覧表示されるため、他のメソッドと同様にオーバーロードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="150e7-144">`Get-Member -Static` lists constructors, so you can view overloads like any other method.</span></span> <span data-ttu-id="150e7-145">この構文のパフォーマンスは、New-Object より大幅に高速です。</span><span class="sxs-lookup"><span data-stu-id="150e7-145">The performance of this syntax is also considerably faster than New-Object.</span></span>

<span data-ttu-id="150e7-146">次の例に示すように、**new** という名前の擬似静的メソッドは .NET 型で機能します。</span><span class="sxs-lookup"><span data-stu-id="150e7-146">The pseudo-static method named **new** works with .NET types, as shown in the following example.</span></span>

```powershell
[hashtable]::new()
```

<span data-ttu-id="150e7-147">Get-Member を使用して、またはこの例で示すように、コンストラクターのオーバーロードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="150e7-147">You can now see constructor overloads with Get-Member, or as shown in this example:</span></span>

```powershell
PS> [hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

## <a name="methods"></a><span data-ttu-id="150e7-148">メソッド</span><span class="sxs-lookup"><span data-stu-id="150e7-148">Methods</span></span>

<span data-ttu-id="150e7-149">Windows PowerShell のクラス メソッドは、end ブロックのみを持つ ScriptBlock として実装されます。</span><span class="sxs-lookup"><span data-stu-id="150e7-149">A Windows PowerShell class method is implemented as a ScriptBlock that has only an end block.</span></span> <span data-ttu-id="150e7-150">すべてのメソッドはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="150e7-150">All methods are public.</span></span> <span data-ttu-id="150e7-151">**DoSomething** という名前のメソッドを定義する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="150e7-151">The following shows an example of defining a method named **DoSomething**.</span></span>

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

<span data-ttu-id="150e7-152">メソッドの呼び出し:</span><span class="sxs-lookup"><span data-stu-id="150e7-152">Method invocation:</span></span>

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

<span data-ttu-id="150e7-153">オーバーロードされたメソッド、つまり、既存のメソッドと同じ名前を持つが、指定した値によって区別されるメソッドもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="150e7-153">Overloaded methods--that is, those that are named the same as an existing method, but differentiated by their specified values--are also supported.</span></span>

## <a name="properties"></a><span data-ttu-id="150e7-154">プロパティ</span><span class="sxs-lookup"><span data-stu-id="150e7-154">Properties</span></span>

<span data-ttu-id="150e7-155">すべてのプロパティはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="150e7-155">All properties are public.</span></span> <span data-ttu-id="150e7-156">プロパティには、改行文字かセミコロンが必要です。</span><span class="sxs-lookup"><span data-stu-id="150e7-156">Properties require either a newline or semicolon.</span></span> <span data-ttu-id="150e7-157">オブジェクトの種類が指定されていない場合、プロパティの型はオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="150e7-157">If no object type is specified, the property type is object.</span></span>

<span data-ttu-id="150e7-158">検証属性または引数変換属性を使用するプロパティ (`[ValidateSet("aaa")]` など) は期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="150e7-158">Properties that use validation attributes or argument transformation attributes (e.g. `[ValidateSet("aaa")]`) work as expected.</span></span>

## <a name="hidden"></a><span data-ttu-id="150e7-159">Hidden</span><span class="sxs-lookup"><span data-stu-id="150e7-159">Hidden</span></span>

<span data-ttu-id="150e7-160">新しいキーワード **Hidden** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="150e7-160">A new keyword, **Hidden**, has been added.</span></span> <span data-ttu-id="150e7-161">**Hidden** は、プロパティとメソッド (コンストラクターを含む) に適用できます。</span><span class="sxs-lookup"><span data-stu-id="150e7-161">**Hidden** can be applied to properties and methods (including constructors).</span></span>

<span data-ttu-id="150e7-162">Hidden のメンバーはパブリックですが、-Force パラメーターを追加しない限り、Get-Member の出力には含められません。</span><span class="sxs-lookup"><span data-stu-id="150e7-162">Hidden members are public, but do not appear in the output of Get-Member unless the -Force parameter is added.</span></span>

<span data-ttu-id="150e7-163">Hidden のメンバーを定義するクラスで完了が発生しない限り、タブの完了時、または IntelliSense の使用時に Hidden のメンバーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="150e7-163">Hidden members are not included when tab completing or using Intellisense unless the completion occurs in the class defining the hidden member.</span></span>

<span data-ttu-id="150e7-164">C# コードで Windows PowerShell 内と同じセマンティクスを使用できるように、新しい属性 **System.Management.Automation.HiddenAttribute** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="150e7-164">A new attribute, **System.Management.Automation.HiddenAttribute** has been added so that C# code can have the same semantics within Windows PowerShell.</span></span>

## <a name="return-types"></a><span data-ttu-id="150e7-165">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="150e7-165">Return types</span></span>

<span data-ttu-id="150e7-166">戻り値の型は、コントラクトです。戻り値は、予期された型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="150e7-166">Return type is a contract; the return value is converted to the expected type.</span></span> <span data-ttu-id="150e7-167">戻り値の型が指定されていない場合、戻り値の型は void です。</span><span class="sxs-lookup"><span data-stu-id="150e7-167">If no return type is specified, the return type is void.</span></span> <span data-ttu-id="150e7-168">オブジェクトのストリーミングはありません。オブジェクトが意図的または誤ってパイプラインに書き込まれることはありません。</span><span class="sxs-lookup"><span data-stu-id="150e7-168">There is no streaming of objects; objects cannot be written to the pipeline either intentionally or by accident.</span></span>

## <a name="attributes"></a><span data-ttu-id="150e7-169">属性</span><span class="sxs-lookup"><span data-stu-id="150e7-169">Attributes</span></span>

<span data-ttu-id="150e7-170">2 つの新しい属性 **DscResource** と **DscProperty** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="150e7-170">Two new attributes, **DscResource** and **DscProperty** have been added.</span></span>

## <a name="lexical-scoping-of-variables"></a><span data-ttu-id="150e7-171">変数の語彙的スコープ</span><span class="sxs-lookup"><span data-stu-id="150e7-171">Lexical scoping of variables</span></span>

<span data-ttu-id="150e7-172">今回のリリースで語彙的スコープが機能する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="150e7-172">The following shows an example of how lexical scoping works in this release.</span></span>

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

## <a name="end-to-end-example"></a><span data-ttu-id="150e7-173">エンド ツー エンドの例</span><span class="sxs-lookup"><span data-stu-id="150e7-173">End-to-End Example</span></span>

<span data-ttu-id="150e7-174">次の例では、HTML 動的スタイル シート言語 (DSL) を実装するいくつかの新しいカスタム クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="150e7-174">The following example creates several new, custom classes to implement an HTML dynamic style sheet language (DSL).</span></span>
<span data-ttu-id="150e7-175">次に、モジュールのスコープの外部では型を使用できないため、この例では見出しスタイルやテーブルなど、要素クラスの一部として特定の要素型を作成するヘルパー関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="150e7-175">Then, the example adds helper functions to create specific element types as part of the element class, such as heading styles and tables, because types cannot be used outside the scope of a module.</span></span>

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
# These are required because types aren’t visible outside of the module.
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

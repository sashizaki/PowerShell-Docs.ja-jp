---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: PowerShell クラスを使用したカスタム型の作成
ms.openlocfilehash: c2c50fb65ce4931fcf6ae529b4146df391c831c4
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147842"
---
# <a name="creating-custom-types-using-powershell-classes"></a><span data-ttu-id="8ff89-103">PowerShell クラスを使用したカスタム型の作成</span><span class="sxs-lookup"><span data-stu-id="8ff89-103">Creating Custom Types using PowerShell Classes</span></span>

<span data-ttu-id="8ff89-104">PowerShell 5.0 では、他のオブジェクト指向プログラミング言語のように、形式的構文とセマンティクスを使って、クラスや他のユーザー定義型を定義する機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="8ff89-104">PowerShell 5.0 added the ability to define classes and other user-defined types using formal syntax and semantics like other object-oriented programming languages.</span></span> <span data-ttu-id="8ff89-105">開発者や IT プロフェッショナルがより広範なユース ケースで PowerShell を採用できるようにし、PowerShell アーティファクト (DSC リソースなど) の開発を簡素化し、管理面の対応を促進することがその目標です。</span><span class="sxs-lookup"><span data-stu-id="8ff89-105">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios-in-this-release"></a><span data-ttu-id="8ff89-106">このリリースでサポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="8ff89-106">Supported scenarios in this release</span></span>

- <span data-ttu-id="8ff89-107">PowerShell 言語を使用して DSC リソースとその関連する型を定義する</span><span class="sxs-lookup"><span data-stu-id="8ff89-107">Define DSC resources and their associated types by using the PowerShell language</span></span>
- <span data-ttu-id="8ff89-108">クラス、プロパティ、メソッドなどの使い慣れたオブジェクト指向プログラミングの構成要素を使用して PowerShell でカスタム型を定義する</span><span class="sxs-lookup"><span data-stu-id="8ff89-108">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, etc.</span></span>
- <span data-ttu-id="8ff89-109">PowerShell のクラスおよびクラス ベース DSC リソースを使用した継承のサポート</span><span class="sxs-lookup"><span data-stu-id="8ff89-109">Inheritance support with class in PowerShell and class base DSC resource</span></span>
- <span data-ttu-id="8ff89-110">PowerShell 言語を使用した型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="8ff89-110">Debug types by using the PowerShell language</span></span>
- <span data-ttu-id="8ff89-111">公式的なメカニズムを適切なレベルで使用した例外の生成および処理</span><span class="sxs-lookup"><span data-stu-id="8ff89-111">Generate and handle exceptions by using formal mechanisms, and at the right level</span></span>

## <a name="declare-base-class"></a><span data-ttu-id="8ff89-112">基本クラスの宣言</span><span class="sxs-lookup"><span data-stu-id="8ff89-112">Declare Base Class</span></span>

<span data-ttu-id="8ff89-113">ある PowerShell クラスを、別の PowerShell クラスの基本型として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-113">You can declare a PowerShell class as a base type for another PowerShell class.</span></span>

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

<span data-ttu-id="8ff89-114">既存の .NET Framework 型を基本クラスとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-114">You can also use existing .NET Framework types as base classes:</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{

}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```

### <a name="call-base-class-constructor"></a><span data-ttu-id="8ff89-115">基本クラス コンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="8ff89-115">Call Base Class Constructor</span></span>

<span data-ttu-id="8ff89-116">サブクラスから基本クラス コンストラクターを呼び出すには、キーワード **base** を使用します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-116">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

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

<span data-ttu-id="8ff89-117">基本クラスに既定の (パラメーターなし) コンストラクターがある場合は、明示的なコンストラクター呼び出しを省略できます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-117">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-method"></a><span data-ttu-id="8ff89-118">基本クラス メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="8ff89-118">Call Base Class Method</span></span>

<span data-ttu-id="8ff89-119">サブクラスで既存のメソッドをオーバーライドすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-119">You can override existing methods in subclasses.</span></span> <span data-ttu-id="8ff89-120">そのためには、同じ名前およびシグネチャを使用してメソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-120">To do this, declare methods by using the same name and signature:</span></span>

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

<span data-ttu-id="8ff89-121">オーバーライドされた実装から基底クラスのメソッドを呼び出すには、呼び出し時に基底クラスにキャストします (`[baseClass]$this`)。</span><span class="sxs-lookup"><span data-stu-id="8ff89-121">To call base class methods from overridden implementations, cast to the base class (`[baseClass]$this`) on invocation:</span></span>

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

<span data-ttu-id="8ff89-122">すべての PowerShell メソッドは仮想です。</span><span class="sxs-lookup"><span data-stu-id="8ff89-122">All PowerShell methods are virtual.</span></span> <span data-ttu-id="8ff89-123">オーバーライドの場合と同じ構文を使用し、同じ名前とシグネチャを持つメソッドを宣言することにより、サブクラスの非仮想 .NET メソッドを隠ぺいできます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-123">You can hide non-virtual .NET methods in a subclass by using the same syntax as you do for an override, by declaring methods with same name and signature.</span></span>

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

### <a name="declare-implemented-interface"></a><span data-ttu-id="8ff89-124">実装されたインターフェイスの宣言</span><span class="sxs-lookup"><span data-stu-id="8ff89-124">Declare Implemented Interface</span></span>

<span data-ttu-id="8ff89-125">基本型が指定されていない場合、基本型の後、またはコロン (:) の直後に、実装されたインターフェイスを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-125">You can declare implemented interfaces after base types, or immediately after a colon (:), if there is no base type specified.</span></span> <span data-ttu-id="8ff89-126">コンマを使用してすべての型名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="8ff89-126">Separate all type names by using commas.</span></span> <span data-ttu-id="8ff89-127">C# の構文と似ています。</span><span class="sxs-lookup"><span data-stu-id="8ff89-127">It's similar to C# syntax.</span></span>

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

## <a name="new-language-features-in-powershell-50"></a><span data-ttu-id="8ff89-128">PowerShell 5.0 の新しい言語機能</span><span class="sxs-lookup"><span data-stu-id="8ff89-128">New language features in PowerShell 5.0</span></span>

<span data-ttu-id="8ff89-129">PowerShell 5.0 では、PowerShell に次の新しい言語要素が導入されています。</span><span class="sxs-lookup"><span data-stu-id="8ff89-129">PowerShell 5.0 introduces the following new language elements in PowerShell:</span></span>

### <a name="class-keyword"></a><span data-ttu-id="8ff89-130">class キーワード</span><span class="sxs-lookup"><span data-stu-id="8ff89-130">Class keyword</span></span>

<span data-ttu-id="8ff89-131">`class` キーワードでは新しいクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-131">The `class` keyword defines a new class.</span></span> <span data-ttu-id="8ff89-132">これは、真の .NET Framework 型です。</span><span class="sxs-lookup"><span data-stu-id="8ff89-132">This is a true .NET Framework type.</span></span> <span data-ttu-id="8ff89-133">クラス メンバーはパブリックですが、モジュール スコープ内でのみパブリックです。</span><span class="sxs-lookup"><span data-stu-id="8ff89-133">Class members are public, but only public within the module scope.</span></span> <span data-ttu-id="8ff89-134">型名を文字列として参照することはできません (たとえば、`New-Object` は機能しません)。このリリースでは、クラスが定義されているスクリプトまたはモジュール ファイルの外で type リテラル (`[MyClass]` など) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-134">You can't refer to the type name as a string (for example, `New-Object` doesn't work), and in this release, you can't use a type literal (for example, `[MyClass]`) outside the script or module file in which the class is defined.</span></span>

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="8ff89-135">enum キーワードおよび列挙</span><span class="sxs-lookup"><span data-stu-id="8ff89-135">Enum keyword and enumerations</span></span>

<span data-ttu-id="8ff89-136">区切り文字として改行文字を使用する `enum` キーワードのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8ff89-136">Support for the `enum` keyword has been added, which uses newline as the delimiter.</span></span> <span data-ttu-id="8ff89-137">現時点では、列挙子自体に関して列挙子を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-137">Currently, you cannot define an enumerator in terms of itself.</span></span> <span data-ttu-id="8ff89-138">ただし、次の例に示すように、別の列挙型に関して列挙型を初期化することはできます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-138">However, you can initialize an enum in terms of another enum, as shown in the following example.</span></span> <span data-ttu-id="8ff89-139">また、基本データ型を指定することはできません。基本データ型は常に `[int]` です。</span><span class="sxs-lookup"><span data-stu-id="8ff89-139">Also, the base type cannot be specified; it is always `[int]`.</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="8ff89-140">列挙子の値は、解析時定数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ff89-140">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="8ff89-141">呼び出されたコマンドの結果に、それを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-141">You cannot set it to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="8ff89-142">次の例に示すように、enum では算術演算がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-142">Enums support arithmetic operations, as shown in the following example.</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a><span data-ttu-id="8ff89-143">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="8ff89-143">Import-DscResource</span></span>

<span data-ttu-id="8ff89-144">`Import-DscResource` は真の動的キーワードです。</span><span class="sxs-lookup"><span data-stu-id="8ff89-144">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="8ff89-145">PowerShell では、**DscResource** 属性を含むクラスを探して、指定されたモジュールのルート モジュールを解析します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-145">PowerShell parses the specified module's root module, searching for classes that contain the **DscResource** attribute.</span></span>

### <a name="implementingassembly"></a><span data-ttu-id="8ff89-146">ImplementingAssembly</span><span class="sxs-lookup"><span data-stu-id="8ff89-146">ImplementingAssembly</span></span>

<span data-ttu-id="8ff89-147">新しいフィールド **ImplementingAssembly** が **ModuleInfo** に追加されました。</span><span class="sxs-lookup"><span data-stu-id="8ff89-147">A new field, **ImplementingAssembly**, has been added to **ModuleInfo**.</span></span> <span data-ttu-id="8ff89-148">これは、スクリプトでクラスが定義されている場合はスクリプト モジュールに作成された動的アセンブリに設定されるか、またはバイナリ モジュールの読み込み済みアセンブリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-148">It is set to the dynamic assembly created for a script module if the script defines classes, or the loaded assembly for binary modules.</span></span> <span data-ttu-id="8ff89-149">**ModuleType** が **Manifest** の場合は設定されません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-149">It is not set when **ModuleType** is **Manifest**.</span></span>

<span data-ttu-id="8ff89-150">**ImplementingAssembly** フィールドのリフレクションでは、モジュール内のリソースが検出されます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-150">Reflection on the **ImplementingAssembly** field discovers resources in a module.</span></span> <span data-ttu-id="8ff89-151">これは、PowerShell または他の管理言語で記述されたリソースを検出できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-151">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

<span data-ttu-id="8ff89-152">初期化子を含むフィールド:</span><span class="sxs-lookup"><span data-stu-id="8ff89-152">Fields with initializers:</span></span>

```powershell
[int] $i = 5
```

<span data-ttu-id="8ff89-153">`Static` はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8ff89-153">`Static` is supported.</span></span> <span data-ttu-id="8ff89-154">属性のように動作し、型の制約を行います。</span><span class="sxs-lookup"><span data-stu-id="8ff89-154">It works like an attribute, as do the type constraints.</span></span> <span data-ttu-id="8ff89-155">任意の順序で指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-155">It can be specified in any order.</span></span>

```powershell
static [int] $count = 0
```

<span data-ttu-id="8ff89-156">型は省略できます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-156">A type is optional.</span></span>

```powershell
$s = "hello"
```

<span data-ttu-id="8ff89-157">すべてのメンバーはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="8ff89-157">All members are public.</span></span>

### <a name="constructors-and-instantiation"></a><span data-ttu-id="8ff89-158">コンストラクターとインスタンス化</span><span class="sxs-lookup"><span data-stu-id="8ff89-158">Constructors and instantiation</span></span>

<span data-ttu-id="8ff89-159">PowerShell のクラスは、コンストラクターを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-159">PowerShell classes can have constructors.</span></span> <span data-ttu-id="8ff89-160">クラスと同じ名前です。</span><span class="sxs-lookup"><span data-stu-id="8ff89-160">They have the same name as their class.</span></span> <span data-ttu-id="8ff89-161">コンストラクターはオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-161">Constructors can be overloaded.</span></span> <span data-ttu-id="8ff89-162">静的コンストラクターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8ff89-162">Static constructors are supported.</span></span> <span data-ttu-id="8ff89-163">初期化式を持つプロパティは、コンストラクター内のコードを実行する前に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-163">Properties with initialization expressions are initialized before running any code in a constructor.</span></span> <span data-ttu-id="8ff89-164">静的プロパティは、静的コンストラクターの本体の前に初期化され、インスタンスのプロパティは、非静的コンストラクターの本体の前に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-164">Static properties are initialized before the body of a static constructor, and instance properties are initialized before the body of the non-static constructor.</span></span> <span data-ttu-id="8ff89-165">現時点では、(C\# 構文 ": this()" のような) 別のコンストラクターからコンストラクターを呼び出す構文はありません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-165">Currently, there is no syntax for calling a constructor from another constructor (like the C\# syntax ": this()").</span></span> <span data-ttu-id="8ff89-166">回避策は、一般的な `Init()` メソッドを定義することです。</span><span class="sxs-lookup"><span data-stu-id="8ff89-166">The workaround is to define a common `Init()` method.</span></span>

#### <a name="creating-instances"></a><span data-ttu-id="8ff89-167">インスタンスの作成</span><span class="sxs-lookup"><span data-stu-id="8ff89-167">Creating instances</span></span>

> [!NOTE]
> <span data-ttu-id="8ff89-168">PowerShell 5.0 では、PowerShell で定義されたクラスでは `New-Object` は機能しません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-168">In PowerShell 5.0, `New-Object` does not work with classes defined in PowerShell.</span></span> <span data-ttu-id="8ff89-169">また、型名は語彙的にのみ表示され、クラスを定義するモジュールまたはスクリプトの外部では表示されません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-169">Also, the type name is only visible lexically, meaning it is not visible outside of the module or script that defines the class.</span></span> <span data-ttu-id="8ff89-170">関数は、PowerShell で定義されているクラスのインスタンスを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-170">Functions can return instances of a class defined in PowerShell.</span></span> <span data-ttu-id="8ff89-171">それらのインスタンスは、モジュールまたはスクリプトの外部で動作します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-171">Those instances work outside of the module or script.</span></span>

1. <span data-ttu-id="8ff89-172">既定のコンストラクターを使用したインスタンス化。</span><span class="sxs-lookup"><span data-stu-id="8ff89-172">Instantiating by using the default constructor.</span></span>

   ```powershell
   $a = [MyClass]::new()
   ```

1. <span data-ttu-id="8ff89-173">パラメーターを持つコンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="8ff89-173">Calling a constructor with a parameter</span></span>

   ```powershell
   $b = [MyClass]::new(42)
   ```

1. <span data-ttu-id="8ff89-174">複数のパラメーターを持つコンストラクターへの配列の引き渡し。</span><span class="sxs-lookup"><span data-stu-id="8ff89-174">Passing an array to a constructor with multiple parameters.</span></span>

   ```powershell
   $c = [MyClass]::new(@(42,43,44), "Hello")
   ```

<span data-ttu-id="8ff89-175">次の例に示すように、擬似静的メソッド `new()` は .NET 型で機能します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-175">The pseudo-static method `new()` works with .NET types, as shown in the following example.</span></span>

```powershell
[hashtable]::new()
```

#### <a name="discovering-constructors"></a><span data-ttu-id="8ff89-176">コンストラクターの検出</span><span class="sxs-lookup"><span data-stu-id="8ff89-176">Discovering constructors</span></span>

<span data-ttu-id="8ff89-177">`Get-Member` を使って、またはこの例で示すようにして、コンストラクターのオーバーロードを確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8ff89-177">You can now see constructor overloads with `Get-Member`, or as shown in this example:</span></span>

```powershell
PS> [hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

<span data-ttu-id="8ff89-178">`Get-Member -Static` ではコンストラクターが一覧表示されるため、他のメソッドと同様にオーバーロードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-178">`Get-Member -Static` lists constructors, so you can view overloads like any other method.</span></span> <span data-ttu-id="8ff89-179">また、この構文のパフォーマンスは、`New-Object` より大幅に高速です。</span><span class="sxs-lookup"><span data-stu-id="8ff89-179">The performance of this syntax is also considerably faster than `New-Object`.</span></span>

### <a name="methods"></a><span data-ttu-id="8ff89-180">メソッド</span><span class="sxs-lookup"><span data-stu-id="8ff89-180">Methods</span></span>

<span data-ttu-id="8ff89-181">PowerShell のクラス メソッドは、end ブロックのみを持つ **ScriptBlock** として実装されます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-181">A PowerShell class method is implemented as a **ScriptBlock** that has only an end block.</span></span> <span data-ttu-id="8ff89-182">すべてのメソッドはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="8ff89-182">All methods are public.</span></span> <span data-ttu-id="8ff89-183">**DoSomething** という名前のメソッドを定義する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-183">The following shows an example of defining a method named **DoSomething**.</span></span>

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

<span data-ttu-id="8ff89-184">メソッドの呼び出し:</span><span class="sxs-lookup"><span data-stu-id="8ff89-184">Method invocation:</span></span>

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

<span data-ttu-id="8ff89-185">オーバーロードされたメソッドもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-185">Overloaded methods are also supported.</span></span>

### <a name="properties"></a><span data-ttu-id="8ff89-186">Properties</span><span class="sxs-lookup"><span data-stu-id="8ff89-186">Properties</span></span>

<span data-ttu-id="8ff89-187">すべてのプロパティはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="8ff89-187">All properties are public.</span></span> <span data-ttu-id="8ff89-188">プロパティには、改行文字かセミコロンが必要です。</span><span class="sxs-lookup"><span data-stu-id="8ff89-188">Properties require either a newline or semicolon.</span></span> <span data-ttu-id="8ff89-189">オブジェクトの種類が指定されていない場合、プロパティの型はオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="8ff89-189">If no object type is specified, the property type is object.</span></span>

<span data-ttu-id="8ff89-190">検証属性または引数変換属性を使用するプロパティ (`[ValidateSet("aaa")]` など) は期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-190">Properties that use validation or argument transformation attributes (like `[ValidateSet("aaa")]`) work as expected.</span></span>

### <a name="hidden"></a><span data-ttu-id="8ff89-191">[非表示]</span><span class="sxs-lookup"><span data-stu-id="8ff89-191">Hidden</span></span>

<span data-ttu-id="8ff89-192">新しいキーワード `Hidden` が追加されました。</span><span class="sxs-lookup"><span data-stu-id="8ff89-192">A new keyword, `Hidden`, has been added.</span></span> <span data-ttu-id="8ff89-193">`Hidden` は、プロパティとメソッド (コンストラクターを含む) に適用できます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-193">`Hidden` can be applied to properties and methods (including constructors).</span></span>

<span data-ttu-id="8ff89-194">Hidden のメンバーはパブリックですが、`-Force` パラメーターを追加しない限り、`Get-Member` の出力には含められません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-194">Hidden members are public, but do not appear in the output of `Get-Member` unless the `-Force` parameter is added.</span></span> <span data-ttu-id="8ff89-195">Hidden のメンバーを定義するクラスで完了が発生しない限り、タブの完了時、または IntelliSense の使用時に Hidden のメンバーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-195">Hidden members are not included when tab completing or using Intellisense unless the completion occurs in the class defining the hidden member.</span></span>

<span data-ttu-id="8ff89-196">C\# コードで PowerShell 内と同じセマンティクスを使用できるように、新しい属性 **System.Management.Automation.HiddenAttribute** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="8ff89-196">A new attribute, **System.Management.Automation.HiddenAttribute** has been added so that C\# code can have the same semantics within PowerShell.</span></span>

### <a name="return-types"></a><span data-ttu-id="8ff89-197">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="8ff89-197">Return types</span></span>

<span data-ttu-id="8ff89-198">戻り値の型はコントラクトです。</span><span class="sxs-lookup"><span data-stu-id="8ff89-198">Return type is a contract.</span></span> <span data-ttu-id="8ff89-199">戻り値は、予期された型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="8ff89-199">The return value is converted to the expected type.</span></span> <span data-ttu-id="8ff89-200">戻り値の型が指定されていない場合、戻り値の型は **void** です。</span><span class="sxs-lookup"><span data-stu-id="8ff89-200">If no return type is specified, the return type is **void**.</span></span> <span data-ttu-id="8ff89-201">オブジェクトのストリーミングはありません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-201">There is no streaming of objects.</span></span> <span data-ttu-id="8ff89-202">オブジェクトが意図的または誤ってパイプラインに書き込まれることはありません。</span><span class="sxs-lookup"><span data-stu-id="8ff89-202">Objects cannot be written to the pipeline either intentionally or by accident.</span></span>

### <a name="attributes"></a><span data-ttu-id="8ff89-203">属性</span><span class="sxs-lookup"><span data-stu-id="8ff89-203">Attributes</span></span>

<span data-ttu-id="8ff89-204">2 つの新しい属性 **DscResource** と **DscProperty** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="8ff89-204">Two new attributes, **DscResource** and **DscProperty** have been added.</span></span>

### <a name="lexical-scoping-of-variables"></a><span data-ttu-id="8ff89-205">変数の語彙的スコープ</span><span class="sxs-lookup"><span data-stu-id="8ff89-205">Lexical scoping of variables</span></span>

<span data-ttu-id="8ff89-206">今回のリリースで語彙的スコープが機能する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-206">The following shows an example of how lexical scoping works in this release.</span></span>

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

## <a name="end-to-end-example"></a><span data-ttu-id="8ff89-207">エンド ツー エンドの例</span><span class="sxs-lookup"><span data-stu-id="8ff89-207">End-to-End Example</span></span>

<span data-ttu-id="8ff89-208">次の例では、HTML 動的スタイル シート言語 (DSL) を実装するいくつかのカスタム クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-208">The following example creates some custom classes to implement an HTML dynamic style sheet language (DSL).</span></span> <span data-ttu-id="8ff89-209">次に、モジュールのスコープの外部では型を使用できないため、この例では見出しスタイルやテーブルなど、要素クラスの一部として特定の要素型を作成するヘルパー関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ff89-209">Then, the example adds helper functions to create specific element types as part of the element class, such as heading styles and tables, because types cannot be used outside the scope of a module.</span></span>

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

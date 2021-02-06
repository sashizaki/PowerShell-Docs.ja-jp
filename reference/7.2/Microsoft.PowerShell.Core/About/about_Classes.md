---
description: クラスを使用して独自のカスタム型を作成する方法について説明します。
Locale: en-US
ms.date: 01/19/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_classes?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes
ms.openlocfilehash: 306bd973b5600707b28428dcaa29c17ee965fd76
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "99601031"
---
# <a name="about-classes"></a><span data-ttu-id="c71bb-103">クラスの概要</span><span class="sxs-lookup"><span data-stu-id="c71bb-103">About Classes</span></span>

## <a name="short-description"></a><span data-ttu-id="c71bb-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="c71bb-104">Short description</span></span>
<span data-ttu-id="c71bb-105">クラスを使用して独自のカスタム型を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-105">Describes how you can use classes to create your own custom types.</span></span>

## <a name="long-description"></a><span data-ttu-id="c71bb-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="c71bb-106">Long description</span></span>

<span data-ttu-id="c71bb-107">PowerShell 5.0 では、クラスやその他のユーザー定義型を定義するための正式な構文が追加されます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-107">PowerShell 5.0 adds a formal syntax to define classes and other user-defined types.</span></span> <span data-ttu-id="c71bb-108">クラスを追加することで、開発者や IT プロフェッショナルは幅広いユースケースに対して PowerShell を採用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-108">The addition of classes enables developers and IT professionals to embrace PowerShell for a wider range of use cases.</span></span> <span data-ttu-id="c71bb-109">PowerShell アーティファクトの開発が簡素化され、管理サーフェイスの範囲が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-109">It simplifies development of PowerShell artifacts and accelerates coverage of management surfaces.</span></span>

<span data-ttu-id="c71bb-110">クラス宣言は、実行時にオブジェクトのインスタンスを作成するために使用されるブループリントです。</span><span class="sxs-lookup"><span data-stu-id="c71bb-110">A class declaration is a blueprint used to create instances of objects at run time.</span></span> <span data-ttu-id="c71bb-111">クラスを定義すると、クラス名が型の名前になります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-111">When you define a class, the class name is the name of the type.</span></span> <span data-ttu-id="c71bb-112">たとえば **、device という名前の** クラスを宣言し、その変数を `$dev` **デバイス** の新しいインスタンスに初期化すると、 `$dev` は **デバイス** または型のインスタンスになります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-112">For example, if you declare a class named **Device** and initialize a variable `$dev` to a new instance of **Device**, `$dev` is an object or instance of type **Device**.</span></span> <span data-ttu-id="c71bb-113">**デバイス** の各インスタンスのプロパティには、異なる値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-113">Each instance of **Device** can have different values in its properties.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="c71bb-114">サポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="c71bb-114">Supported scenarios</span></span>

- <span data-ttu-id="c71bb-115">クラス、プロパティ、メソッド、継承などの使い慣れたオブジェクト指向プログラミングセマンティクスを使用して、PowerShell でカスタム型を定義します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-115">Define custom types in PowerShell using familiar object-oriented programming semantics like classes, properties, methods, inheritance, etc.</span></span>
- <span data-ttu-id="c71bb-116">PowerShell 言語を使用して型をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="c71bb-116">Debug types using the PowerShell language.</span></span>
- <span data-ttu-id="c71bb-117">正式なメカニズムを使用して例外を生成し、処理します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-117">Generate and handle exceptions using formal mechanisms.</span></span>
- <span data-ttu-id="c71bb-118">PowerShell 言語を使用して、DSC リソースとそれに関連付けられている型を定義します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-118">Define DSC resources and their associated types by using the PowerShell language.</span></span>

## <a name="syntax"></a><span data-ttu-id="c71bb-119">構文</span><span class="sxs-lookup"><span data-stu-id="c71bb-119">Syntax</span></span>

<span data-ttu-id="c71bb-120">クラスは、次の構文を使用して宣言されます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-120">Classes are declared using the following syntax:</span></span>

```syntax
class <class-name> [: [<base-class>][,<interface-list]] {
    [[<attribute>] [hidden] [static] <property-definition> ...]
    [<class-name>([<constructor-argument-list>])
      {<constructor-statement-list>} ...]
    [[<attribute>] [hidden] [static] <method-definition> ...]
}
```

<span data-ttu-id="c71bb-121">クラスは、次の構文のいずれかを使用してインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-121">Classes are instantiated using either of the following syntaxes:</span></span>

```syntax
[$<variable-name> =] New-Object -TypeName <class-name> [
  [-ArgumentList] <constructor-argument-list>]
```

```syntax
[$<variable-name> =] [<class-name>]::new([<constructor-argument-list>])
```

> [!NOTE]
> <span data-ttu-id="c71bb-122">構文を使用する場合 `[<class-name>]::new()` は、クラス名を囲むかっこが必須です。</span><span class="sxs-lookup"><span data-stu-id="c71bb-122">When using the `[<class-name>]::new()` syntax, brackets around the class name are mandatory.</span></span> <span data-ttu-id="c71bb-123">角かっこは、PowerShell の型定義を通知します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-123">The brackets signal a type definition for PowerShell.</span></span>

### <a name="example-syntax-and-usage"></a><span data-ttu-id="c71bb-124">構文と使用例</span><span class="sxs-lookup"><span data-stu-id="c71bb-124">Example syntax and usage</span></span>

<span data-ttu-id="c71bb-125">この例は、使用可能なクラスを作成するために必要な最低限の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="c71bb-125">This example shows the minimum syntax needed to create a usable class.</span></span>

```powershell
class Device {
    [string]$Brand
}

$dev = [Device]::new()
$dev.Brand = "Microsoft"
$dev
```

```Output
Brand
-----
Microsoft
```

## <a name="class-properties"></a><span data-ttu-id="c71bb-126">クラスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c71bb-126">Class properties</span></span>

<span data-ttu-id="c71bb-127">プロパティは、クラススコープで宣言された変数です。</span><span class="sxs-lookup"><span data-stu-id="c71bb-127">Properties are variables declared at class scope.</span></span> <span data-ttu-id="c71bb-128">プロパティには、任意の組み込み型または別のクラスのインスタンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-128">A property may be of any built-in type or an instance of another class.</span></span> <span data-ttu-id="c71bb-129">クラスに含まれるプロパティの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-129">Classes have no restriction in the number of properties they have.</span></span>

### <a name="example-class-with-simple-properties"></a><span data-ttu-id="c71bb-130">単純なプロパティを持つクラスの例</span><span class="sxs-lookup"><span data-stu-id="c71bb-130">Example class with simple properties</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
}

$device = [Device]::new()
$device.Brand = "Microsoft"
$device.Model = "Surface Pro 4"
$device.VendorSku = "5072641000"

$device
```

```Output
Brand     Model         VendorSku
-----     -----         ---------
Microsoft Surface Pro 4 5072641000
```

### <a name="example-complex-types-in-class-properties"></a><span data-ttu-id="c71bb-131">クラスプロパティの複合型の例</span><span class="sxs-lookup"><span data-stu-id="c71bb-131">Example complex types in class properties</span></span>

<span data-ttu-id="c71bb-132">この例では、**デバイス** クラスを使用して空の **ラック** クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-132">This example defines an empty **Rack** class using the **Device** class.</span></span> <span data-ttu-id="c71bb-133">この後の例では、デバイスをラックに追加する方法と、事前に読み込まれたラックから始める方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-133">The examples, following this one, show how to add devices to the rack and how to start with a pre-loaded rack.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
}

class Rack {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new(8)

}

$rack = [Rack]::new()

$rack
```

```Output

Brand     :
Model     :
VendorSku :
AssetId   :
Devices   : {$null, $null, $null, $null...}


```

## <a name="class-methods"></a><span data-ttu-id="c71bb-134">クラスのメソッド</span><span class="sxs-lookup"><span data-stu-id="c71bb-134">Class methods</span></span>

<span data-ttu-id="c71bb-135">メソッドは、クラスが実行できるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-135">Methods define the actions that a class can perform.</span></span> <span data-ttu-id="c71bb-136">メソッドは、入力データを提供するパラメーターを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-136">Methods may take parameters that provide input data.</span></span> <span data-ttu-id="c71bb-137">メソッドは出力を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-137">Methods can return output.</span></span> <span data-ttu-id="c71bb-138">メソッドによって返されるデータは、任意の定義済みデータ型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-138">Data returned by a method can be any defined data type.</span></span>

<span data-ttu-id="c71bb-139">クラスのメソッドを定義する場合は、自動変数を使用して現在のクラスオブジェクトを参照し `$this` ます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-139">When defining a method for a class, you reference the current class object by using the `$this` automatic variable.</span></span> <span data-ttu-id="c71bb-140">これにより、現在のクラスで定義されているプロパティおよびその他のメソッドにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-140">This allows you to access properties and other methods defined in the current class.</span></span>

### <a name="example-simple-class-with-properties-and-methods"></a><span data-ttu-id="c71bb-141">プロパティとメソッドを持つ単純なクラスの例</span><span class="sxs-lookup"><span data-stu-id="c71bb-141">Example simple class with properties and methods</span></span>

<span data-ttu-id="c71bb-142">**ラック** クラスを拡張して、デバイスを追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-142">Extending the **Rack** class to add and remove devices to or from it.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    [string]ToString(){
        return ("{0}|{1}|{2}" -f $this.Brand, $this.Model, $this.VendorSku)
    }
}

class Rack {
    [int]$Slots = 8
    [string]$Brand
    [string]$Model
    [string]$VendorSku
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    [void] AddDevice([Device]$dev, [int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $dev
    }

    [void]RemoveDevice([int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $null
    }

    [int[]] GetAvailableSlots(){
        [int]$i = 0
        return @($this.Devices.foreach{ if($_ -eq $null){$i}; $i++})
    }
}

$rack = [Rack]::new()

$surface = [Device]::new()
$surface.Brand = "Microsoft"
$surface.Model = "Surface Pro 4"
$surface.VendorSku = "5072641000"

$rack.AddDevice($surface, 2)

$rack
$rack.GetAvailableSlots()
```

```Output

Slots     : 8
Brand     :
Model     :
VendorSku :
AssetId   :
Devices   : {$null, $null, Microsoft|Surface Pro 4|5072641000, $null...}

0
1
3
4
5
6
7

```

## <a name="output-in-class-methods"></a><span data-ttu-id="c71bb-143">クラスのメソッドの出力</span><span class="sxs-lookup"><span data-stu-id="c71bb-143">Output in class methods</span></span>

<span data-ttu-id="c71bb-144">メソッドには、戻り値の型が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-144">Methods should have a return type defined.</span></span> <span data-ttu-id="c71bb-145">メソッドが出力を返さない場合、出力の型はになり `[void]` ます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-145">If a method doesn't return output, then the output type should be `[void]`.</span></span>

<span data-ttu-id="c71bb-146">クラスのメソッドでは、ステートメントに示されているものを除き、パイプラインにオブジェクトが送信されることはありません `return` 。</span><span class="sxs-lookup"><span data-stu-id="c71bb-146">In class methods, no objects get sent to the pipeline except those mentioned in the `return` statement.</span></span> <span data-ttu-id="c71bb-147">コードからパイプラインに誤って出力されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-147">There's no accidental output to the pipeline from the code.</span></span>

> [!NOTE]
> <span data-ttu-id="c71bb-148">これは、すべてがパイプラインに送信される PowerShell 関数が出力を処理する方法とは基本的に異なります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-148">This is fundamentally different from how PowerShell functions handle output, where everything goes to the pipeline.</span></span>

<span data-ttu-id="c71bb-149">クラスメソッド内からエラーストリームに書き込まれた終了しないエラーは、渡されません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-149">Non-terminating errors written to the error stream from inside a class method are not passed through.</span></span> <span data-ttu-id="c71bb-150">終了エラーを表面化させるには、を使用する必要があり `throw` ます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-150">You must use `throw` to surface a terminating error.</span></span>
<span data-ttu-id="c71bb-151">コマンドレットを使用して `Write-*` も、クラスメソッド内から PowerShell の出力ストリームに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-151">Using the `Write-*` cmdlets, you can still write to PowerShell's output streams from within a class method.</span></span> <span data-ttu-id="c71bb-152">ただし、メソッドがステートメントのみを使用してオブジェクトを出力するように避ける必要があり `return` ます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-152">However, this should be avoided so that the method emits objects using only the `return` statement.</span></span>

### <a name="method-output"></a><span data-ttu-id="c71bb-153">メソッドの出力</span><span class="sxs-lookup"><span data-stu-id="c71bb-153">Method output</span></span>

<span data-ttu-id="c71bb-154">この例では、ステートメントを除き、クラスメソッドからパイプラインに誤って出力されることを示してい `return` ます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-154">This example demonstrates no accidental output to the pipeline from class methods, except on the `return` statement.</span></span>

```powershell
class FunWithIntegers
{
    [int[]]$Integers = 0..10

    [int[]]GetOddIntegers(){
        return $this.Integers.Where({ ($_ % 2) })
    }

    [void] GetEvenIntegers(){
        # this following line doesn't go to the pipeline
        $this.Integers.Where({ ($_ % 2) -eq 0})
    }

    [string]SayHello(){
        # this following line doesn't go to the pipeline
        "Good Morning"

        # this line goes to the pipeline
        return "Hello World"
    }
}

$ints = [FunWithIntegers]::new()
$ints.GetOddIntegers()
$ints.GetEvenIntegers()
$ints.SayHello()
```

```Output
1
3
5
7
9
Hello World

```

## <a name="constructor"></a><span data-ttu-id="c71bb-155">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="c71bb-155">Constructor</span></span>

<span data-ttu-id="c71bb-156">コンストラクターを使用すると、クラスのインスタンスを作成する時点で既定値を設定し、オブジェクトロジックを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-156">Constructors enable you to set default values and validate object logic at the moment of creating the instance of the class.</span></span> <span data-ttu-id="c71bb-157">コンストラクターには、クラスと同じ名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="c71bb-157">Constructors have the same name as the class.</span></span> <span data-ttu-id="c71bb-158">コンストラクターには、新しいオブジェクトのデータメンバーを初期化するための引数が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-158">Constructors might have arguments, to initialize the data members of the new object.</span></span>

<span data-ttu-id="c71bb-159">クラスには、0個以上のコンストラクターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-159">The class can have zero or more constructors defined.</span></span> <span data-ttu-id="c71bb-160">コンストラクターが定義されていない場合、クラスには既定のパラメーターなしのコンストラクターが与えられます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-160">If no constructor is defined, the class is given a default parameterless constructor.</span></span> <span data-ttu-id="c71bb-161">このコンストラクターは、すべてのメンバーを既定値に初期化します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-161">This constructor initializes all members to their default values.</span></span> <span data-ttu-id="c71bb-162">オブジェクトの型と文字列には null 値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-162">Object types and strings are given null values.</span></span> <span data-ttu-id="c71bb-163">コンストラクターを定義するときに、既定のパラメーターなしのコンストラクターは作成されません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-163">When you define constructor, no default parameterless constructor is created.</span></span> <span data-ttu-id="c71bb-164">必要に応じて、パラメーターなしのコンストラクターを作成します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-164">Create a parameterless constructor if one is needed.</span></span>

### <a name="constructor-basic-syntax"></a><span data-ttu-id="c71bb-165">コンストラクターの基本構文</span><span class="sxs-lookup"><span data-stu-id="c71bb-165">Constructor basic syntax</span></span>

<span data-ttu-id="c71bb-166">この例では、デバイスクラスはプロパティとコンストラクターを使用して定義されています。</span><span class="sxs-lookup"><span data-stu-id="c71bb-166">In this example, the Device class is defined with properties and a constructor.</span></span>
<span data-ttu-id="c71bb-167">このクラスを使用するには、ユーザーがコンストラクターに一覧表示されているパラメーターの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-167">To use this class, the user is required to provide values for the parameters listed in the constructor.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    Device(
        [string]$b,
        [string]$m,
        [string]$vsk
    ){
        $this.Brand = $b
        $this.Model = $m
        $this.VendorSku = $vsk
    }
}

[Device]$surface = [Device]::new("Microsoft", "Surface Pro 4", "5072641000")

$surface
```

```Output
Brand     Model         VendorSku
-----     -----         ---------
Microsoft Surface Pro 4 5072641000
```

### <a name="example-with-multiple-constructors"></a><span data-ttu-id="c71bb-168">複数のコンストラクターを使用した例</span><span class="sxs-lookup"><span data-stu-id="c71bb-168">Example with multiple constructors</span></span>

<span data-ttu-id="c71bb-169">この例では、 **デバイス** クラスは、プロパティ、既定のコンストラクター、およびインスタンスを初期化するコンストラクターを使用して定義されています。</span><span class="sxs-lookup"><span data-stu-id="c71bb-169">In this example, the **Device** class is defined with properties, a default constructor, and a constructor to initialize the instance.</span></span>

<span data-ttu-id="c71bb-170">既定のコンストラクターは、 **ブランド** を **Undefined** に設定し、 **モデル** と **ベンダの sku** を null 値にします。</span><span class="sxs-lookup"><span data-stu-id="c71bb-170">The default constructor sets the **brand** to **Undefined**, and leaves **model** and **vendor-sku** with null values.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    Device(){
        $this.Brand = 'Undefined'
    }

    Device(
        [string]$b,
        [string]$m,
        [string]$vsk
    ){
        $this.Brand = $b
        $this.Model = $m
        $this.VendorSku = $vsk
    }
}

[Device]$somedevice = [Device]::new()
[Device]$surface = [Device]::new("Microsoft", "Surface Pro 4", "5072641000")

$somedevice
$surface
```

```Output
Brand       Model           VendorSku
-----       -----           ---------
Undefined
Microsoft   Surface Pro 4   5072641000
```

## <a name="hidden-attribute"></a><span data-ttu-id="c71bb-171">Hidden 属性</span><span class="sxs-lookup"><span data-stu-id="c71bb-171">Hidden attribute</span></span>

<span data-ttu-id="c71bb-172">属性は、 `hidden` プロパティまたはメソッドを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="c71bb-172">The `hidden` attribute hides a property or method.</span></span> <span data-ttu-id="c71bb-173">プロパティまたはメソッドは、ユーザーが引き続きアクセスでき、オブジェクトが使用可能なすべてのスコープで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-173">The property or method is still accessible to the user and is available in all scopes in which the object is available.</span></span> <span data-ttu-id="c71bb-174">非表示のメンバーはコマンドレットによって非表示にされ、 `Get-Member` タブ補完または IntelliSense を使用してクラス定義の外部に表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-174">Hidden members are hidden from the `Get-Member` cmdlet and can't be displayed using tab completion or IntelliSense outside the class definition.</span></span>

<span data-ttu-id="c71bb-175">詳細については、「 [About_hidden](About_hidden.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c71bb-175">For more information, see [About_hidden](About_hidden.md).</span></span>

### <a name="example-using-hidden-attributes"></a><span data-ttu-id="c71bb-176">隠し属性の使用例</span><span class="sxs-lookup"><span data-stu-id="c71bb-176">Example using hidden attributes</span></span>

<span data-ttu-id="c71bb-177">**ラック** オブジェクトが作成されると、デバイスのスロットの数は固定値になり、いつでも変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-177">When a **Rack** object is created, the number of slots for devices is a fixed value that shouldn't be changed at any time.</span></span> <span data-ttu-id="c71bb-178">この値は作成時に認識されます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-178">This value is known at creation time.</span></span>

<span data-ttu-id="c71bb-179">開発者は、hidden 属性を使用して、スロットの数を非表示にし、意図しない変更がラックのサイズになるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-179">Using the hidden attribute allows the developer to keep the number of slots hidden and prevents unintentional changes the size of the rack.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
}

class Rack {
    [int] hidden $Slots = 8
    [string]$Brand
    [string]$Model
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack ([string]$b, [string]$m, [int]$capacity){
        ## argument validation here

        $this.Brand = $b
        $this.Model = $m
        $this.Slots = $capacity

        ## reset rack size to new capacity
        $this.Devices = [Device[]]::new($this.Slots)
    }
}

[Rack]$r1 = [Rack]::new("Microsoft", "Surface Pro 4", 16)

$r1
$r1.Devices.Length
$r1.Slots
```

```Output
Brand     Model         Devices
-----     -----         -------
Microsoft Surface Pro 4 {$null, $null, $null, $null...}
16
16
```

<span data-ttu-id="c71bb-180">通知 **スロット** プロパティが出力に表示されません `$r1` 。</span><span class="sxs-lookup"><span data-stu-id="c71bb-180">Notice **Slots** property isn't shown in `$r1` output.</span></span> <span data-ttu-id="c71bb-181">ただし、サイズはコンストラクターによって変更されました。</span><span class="sxs-lookup"><span data-stu-id="c71bb-181">However, the size was changed by the constructor.</span></span>

## <a name="static-attribute"></a><span data-ttu-id="c71bb-182">静的属性</span><span class="sxs-lookup"><span data-stu-id="c71bb-182">Static attribute</span></span>

<span data-ttu-id="c71bb-183">属性は、 `static` クラスに存在し、インスタンスを必要としないプロパティまたはメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-183">The `static` attribute defines a property or a method that exists in the class and needs no instance.</span></span>

<span data-ttu-id="c71bb-184">静的プロパティは、クラスのインスタンス化とは関係なく、常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-184">A static property is always available, independent of class instantiation.</span></span> <span data-ttu-id="c71bb-185">静的プロパティは、クラスのすべてのインスタンスで共有されます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-185">A static property is shared across all instances of the class.</span></span> <span data-ttu-id="c71bb-186">静的メソッドは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-186">A static method is available always.</span></span> <span data-ttu-id="c71bb-187">すべての静的プロパティは、セッションスパン全体に対して有効です。</span><span class="sxs-lookup"><span data-stu-id="c71bb-187">All static properties live for the entire session span.</span></span>

### <a name="example-using-static-attributes-and-methods"></a><span data-ttu-id="c71bb-188">静的な属性とメソッドの使用例</span><span class="sxs-lookup"><span data-stu-id="c71bb-188">Example using static attributes and methods</span></span>

<span data-ttu-id="c71bb-189">ここでインスタンス化されたラックは、データセンターに存在するものとします。</span><span class="sxs-lookup"><span data-stu-id="c71bb-189">Assume the racks instantiated here exist in your data center.</span></span> <span data-ttu-id="c71bb-190">では、コードのラックを追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-190">So, you would like to keep track of the racks in your code.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
}

class Rack {
    hidden [int] $Slots = 8
    static [Rack[]]$InstalledRacks = @()
    [string]$Brand
    [string]$Model
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack ([string]$b, [string]$m, [string]$id, [int]$capacity){
        ## argument validation here

        $this.Brand = $b
        $this.Model = $m
        $this.AssetId = $id
        $this.Slots = $capacity

        ## reset rack size to new capacity
        $this.Devices = [Device[]]::new($this.Slots)

        ## add rack to installed racks
        [Rack]::InstalledRacks += $this
    }

    static [void]PowerOffRacks(){
        foreach ($rack in [Rack]::InstalledRacks) {
            Write-Warning ("Turning off rack: " + ($rack.AssetId))
        }
    }
}
```

### <a name="testing-static-property-and-method-exist"></a><span data-ttu-id="c71bb-191">静的なプロパティとメソッドをテストしています</span><span class="sxs-lookup"><span data-stu-id="c71bb-191">Testing static property and method exist</span></span>

```
PS> [Rack]::InstalledRacks.Length
0

PS> [Rack]::PowerOffRacks()

PS> (1..10) | ForEach-Object {
>>   [Rack]::new("Adatum Corporation", "Standard-16",
>>     $_.ToString("Std0000"), 16)
>> } > $null

PS> [Rack]::InstalledRacks.Length
10

PS> [Rack]::InstalledRacks[3]
Brand              Model       AssetId Devices
-----              -----       ------- -------
Adatum Corporation Standard-16 Std0004 {$null, $null, $null, $null...}

PS> [Rack]::PowerOffRacks()
WARNING: Turning off rack: Std0001
WARNING: Turning off rack: Std0002
WARNING: Turning off rack: Std0003
WARNING: Turning off rack: Std0004
WARNING: Turning off rack: Std0005
WARNING: Turning off rack: Std0006
WARNING: Turning off rack: Std0007
WARNING: Turning off rack: Std0008
WARNING: Turning off rack: Std0009
WARNING: Turning off rack: Std0010
```

<span data-ttu-id="c71bb-192">この例を実行するたびにラック数が増加することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c71bb-192">Notice that the number of racks increases each time you run this example.</span></span>

## <a name="property-validation-attributes"></a><span data-ttu-id="c71bb-193">プロパティ検証属性</span><span class="sxs-lookup"><span data-stu-id="c71bb-193">Property validation attributes</span></span>

<span data-ttu-id="c71bb-194">検証属性を使用すると、プロパティに指定された値が定義された要件を満たしているかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-194">Validation attributes allow you to test that values given to properties meet defined requirements.</span></span> <span data-ttu-id="c71bb-195">値が割り当てられる瞬間に検証がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-195">Validation is triggered the moment that the value is assigned.</span></span> <span data-ttu-id="c71bb-196">「 [About_functions_advanced_parameters](about_functions_advanced_parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c71bb-196">See [about_functions_advanced_parameters](about_functions_advanced_parameters.md).</span></span>

### <a name="example-using-validation-attributes"></a><span data-ttu-id="c71bb-197">検証属性を使用した例</span><span class="sxs-lookup"><span data-stu-id="c71bb-197">Example using validation attributes</span></span>

```powershell
class Device {
    [ValidateNotNullOrEmpty()][string]$Brand
    [ValidateNotNullOrEmpty()][string]$Model
}

[Device]$dev = [Device]::new()

Write-Output "Testing dev"
$dev

$dev.Brand = ""
```

```Output
Testing dev

Brand Model
----- -----

Exception setting "Brand": "The argument is null or empty. Provide an
argument that is not null or empty, and then try the command again."
At C:\tmp\Untitled-5.ps1:11 char:1
+ $dev.Brand = ""
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], SetValueInvocationException
    + FullyQualifiedErrorId : ExceptionWhenSetting
```

## <a name="inheritance-in-powershell-classes"></a><span data-ttu-id="c71bb-198">PowerShell クラスでの継承</span><span class="sxs-lookup"><span data-stu-id="c71bb-198">Inheritance in PowerShell classes</span></span>

<span data-ttu-id="c71bb-199">クラスを拡張するには、既存のクラスから派生する新しいクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-199">You can extend a class by creating a new class that derives from an existing class.</span></span> <span data-ttu-id="c71bb-200">派生クラスは、基底クラスのプロパティを継承します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-200">The derived class inherits the properties of the base class.</span></span> <span data-ttu-id="c71bb-201">必要に応じて、メソッドとプロパティを追加またはオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-201">You can add or override methods and properties as required.</span></span>

<span data-ttu-id="c71bb-202">PowerShell は、多重継承をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-202">PowerShell does not support multiple inheritance.</span></span> <span data-ttu-id="c71bb-203">クラスは、複数のクラスから継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-203">Classes cannot inherit from more than one class.</span></span> <span data-ttu-id="c71bb-204">ただし、その目的のためにインターフェイスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-204">However, you can use interfaces for that purpose.</span></span>

<span data-ttu-id="c71bb-205">継承の実装は演算子によって定義されます。これは、 `:` このクラスを拡張するか、これらのインターフェイスを実装することを意味します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-205">Inheritance implementation is defined by the `:` operator; which means to extend this class or implements these interfaces.</span></span> <span data-ttu-id="c71bb-206">派生クラスは、常にクラス宣言の左端にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-206">The derived class should always be leftmost in the class declaration.</span></span>

### <a name="example-using-simple-inheritance-syntax"></a><span data-ttu-id="c71bb-207">単純な継承構文を使用した例</span><span class="sxs-lookup"><span data-stu-id="c71bb-207">Example using simple inheritance syntax</span></span>

<span data-ttu-id="c71bb-208">この例は、単純な PowerShell クラスの継承構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="c71bb-208">This example shows the simple PowerShell class inheritance syntax.</span></span>

```powershell
Class Derived : Base {...}
```

<span data-ttu-id="c71bb-209">この例では、基底クラスの後に来るインターフェイス宣言を使用した継承を示します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-209">This example shows inheritance with an interface declaration coming after the base class.</span></span>

```powershell
Class Derived : Base, Interface {...}
```

### <a name="example-of-simple-inheritance-in-powershell-classes"></a><span data-ttu-id="c71bb-210">PowerShell クラスでの単純な継承の例</span><span class="sxs-lookup"><span data-stu-id="c71bb-210">Example of simple inheritance in PowerShell classes</span></span>

<span data-ttu-id="c71bb-211">この例では、前の例で使用した **ラック** および **デバイス** クラスが、プロパティの繰り返しを回避し、共通のプロパティをより適切に配置し、一般的なビジネスロジックを再利用するために、より適切に定義されています。</span><span class="sxs-lookup"><span data-stu-id="c71bb-211">In this example the **Rack** and **Device** classes used in the previous examples are better defined to: avoid property repetitions, better align common properties, and reuse common business logic.</span></span>

<span data-ttu-id="c71bb-212">データセンター内のほとんどのオブジェクトは会社の資産であり、資産としての追跡を開始するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="c71bb-212">Most objects in the data center are company assets, which makes sense to start tracking them as assets.</span></span> <span data-ttu-id="c71bb-213">デバイスの種類は列挙型によって定義され `DeviceType` ます。列挙の詳細については、 [about_Enum](about_Enum.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c71bb-213">Device types are defined by the `DeviceType` enumeration, see [about_Enum](about_Enum.md) for details on enumerations.</span></span>

<span data-ttu-id="c71bb-214">この例では、とを定義しているだけで、 `Rack` `ComputeServer` 両方の拡張機能がクラスに対して定義されてい `Device` ます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-214">In our example, we're only defining `Rack` and `ComputeServer`; both extensions to the `Device` class.</span></span>

```powershell
enum DeviceType {
    Undefined = 0
    Compute = 1
    Storage = 2
    Networking = 4
    Communications = 8
    Power = 16
    Rack = 32
}

class Asset {
    [string]$Brand
    [string]$Model
}

class Device : Asset {
    hidden [DeviceType]$devtype = [DeviceType]::Undefined
    [string]$Status

    [DeviceType] GetDeviceType(){
        return $this.devtype
    }
}

class ComputeServer : Device {
    hidden [DeviceType]$devtype = [DeviceType]::Compute
    [string]$ProcessorIdentifier
    [string]$Hostname
}

class Rack : Device {
    hidden [DeviceType]$devtype = [DeviceType]::Rack
    hidden [int]$Slots = 8

    [string]$Datacenter
    [string]$Location
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack (){
        ## Just create the default rack with 8 slots
    }

    Rack ([int]$s){
        ## Add argument validation logic here
        $this.Devices = [Device[]]::new($s)
    }

    [void] AddDevice([Device]$dev, [int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $dev
    }

    [void] RemoveDevice([int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $null
    }
}

$FirstRack = [Rack]::new(16)
$FirstRack.Status = "Operational"
$FirstRack.Datacenter = "PNW"
$FirstRack.Location = "F03R02.J10"

(0..15).ForEach({
    $ComputeServer = [ComputeServer]::new()
    $ComputeServer.Brand = "Fabrikam, Inc."       ## Inherited from Asset
    $ComputeServer.Model = "Fbk5040"              ## Inherited from Asset
    $ComputeServer.Status = "Installed"           ## Inherited from Device
    $ComputeServer.ProcessorIdentifier = "x64"    ## ComputeServer
    $ComputeServer.Hostname = ("r1s" + $_.ToString("000")) ## ComputeServer
    $FirstRack.AddDevice($ComputeServer, $_)
  })

$FirstRack
$FirstRack.Devices
```

```Output
Datacenter : PNW
Location   : F03R02.J10
Devices    : {r1s000, r1s001, r1s002, r1s003...}
Status     : Operational
Brand      :
Model      :

ProcessorIdentifier : x64
Hostname            : r1s000
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040

ProcessorIdentifier : x64
Hostname            : r1s001
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040

<... content truncated here for brevity ...>

ProcessorIdentifier : x64
Hostname            : r1s015
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040
```

### <a name="calling-base-class-constructors"></a><span data-ttu-id="c71bb-215">基底クラスのコンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="c71bb-215">Calling base class constructors</span></span>

<span data-ttu-id="c71bb-216">サブクラスから基底クラスのコンストラクターを呼び出すには、キーワードを追加し `base` ます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-216">To invoke a base class constructor from a subclass, add the `base` keyword.</span></span>

```powershell
class Person {
    [int]$Age

    Person([int]$a)
    {
        $this.Age = $a
    }
}

class Child : Person
{
    [string]$School

    Child([int]$a, [string]$s ) : base($a) {
        $this.School = $s
    }
}

[Child]$littleone = [Child]::new(10, "Silver Fir Elementary School")

$littleone.Age
```

```Output

10
```

### <a name="invoke-base-class-methods"></a><span data-ttu-id="c71bb-217">基底クラスのメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="c71bb-217">Invoke base class methods</span></span>

<span data-ttu-id="c71bb-218">サブクラスの既存のメソッドをオーバーライドするには、同じ名前とシグネチャを使用してメソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-218">To override existing methods in subclasses, declare methods using the same name and signature.</span></span>

```powershell
class BaseClass
{
    [int]days() {return 1}
}
class ChildClass1 : BaseClass
{
    [int]days () {return 2}
}

[ChildClass1]::new().days()
```

```Output

2
```

<span data-ttu-id="c71bb-219">オーバーライドされた実装から基本クラスメソッドを呼び出すには、呼び出し時に基本クラス ([baseclass] $this) にキャストします。</span><span class="sxs-lookup"><span data-stu-id="c71bb-219">To call base class methods from overridden implementations, cast to the base class ([baseclass]$this) on invocation.</span></span>

```powershell
class BaseClass
{
    [int]days() {return 1}
}
class ChildClass1 : BaseClass
{
    [int]days () {return 2}
    [int]basedays() {return ([BaseClass]$this).days()}
}

[ChildClass1]::new().days()
[ChildClass1]::new().basedays()
```

```Output

2
1
```

### <a name="inheriting-from-interfaces"></a><span data-ttu-id="c71bb-220">継承 (インターフェイスから)</span><span class="sxs-lookup"><span data-stu-id="c71bb-220">Inheriting from interfaces</span></span>

<span data-ttu-id="c71bb-221">PowerShell クラスは、基底クラスの拡張に使用したのと同じ継承構文を使用してインターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-221">PowerShell classes can implement an interface using the same inheritance syntax used to extend base classes.</span></span> <span data-ttu-id="c71bb-222">インターフェイスでは複数の継承が許可されるため、インターフェイスを実装する PowerShell クラスは、型名をコロン () の後に `:` コンマ () で区切って、複数の型から継承でき `,` ます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-222">Because interfaces allow multiple inheritance, a PowerShell class implementing an interface may inherit from multiple types, by separating the type names after the colon (`:`) with commas (`,`).</span></span> <span data-ttu-id="c71bb-223">インターフェイスを実装する PowerShell クラスは、そのインターフェイスのすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-223">A PowerShell class that implements an interface must implement all the members of that interface.</span></span> <span data-ttu-id="c71bb-224">実装インターフェイスのメンバーを省略すると、スクリプトで解析時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-224">Omitting the implemention interface members causes a parse-time error in the script.</span></span>

> [!NOTE]
> <span data-ttu-id="c71bb-225">Powershell では、PowerShell スクリプトでの新しいインターフェイスの宣言は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-225">PowerShell does not currently support declaring new interfaces in PowerShell script.</span></span>

```powershell
class MyComparable : System.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableBar : bar, System.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

## <a name="importing-classes-from-a-powershell-module"></a><span data-ttu-id="c71bb-226">PowerShell モジュールからのクラスのインポート</span><span class="sxs-lookup"><span data-stu-id="c71bb-226">Importing classes from a PowerShell module</span></span>

<span data-ttu-id="c71bb-227">`Import-Module` また、ステートメントでは、モジュール `#requires` で定義されているモジュール関数、エイリアス、および変数のみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c71bb-227">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="c71bb-228">クラスはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-228">Classes are not imported.</span></span> <span data-ttu-id="c71bb-229">ステートメントは、 `using module` モジュールで定義されているクラスをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c71bb-229">The `using module` statement imports the classes defined in the module.</span></span> <span data-ttu-id="c71bb-230">現在のセッションでモジュールが読み込まれていない場合、 `using` ステートメントは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-230">If the module isn't loaded in the current session, the `using` statement fails.</span></span> <span data-ttu-id="c71bb-231">ステートメントの詳細については `using` 、「 [about_Using](about_Using.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c71bb-231">For more information about the `using` statement, see [about_Using](about_Using.md).</span></span>

<span data-ttu-id="c71bb-232">ステートメントは、 `using module` `ModuleToProcess` スクリプトモジュールまたはバイナリモジュールのルートモジュール () からクラスをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c71bb-232">The `using module` statement imports classes from the root module (`ModuleToProcess`) of a script module or binary module.</span></span> <span data-ttu-id="c71bb-233">入れ子になったモジュールで定義されているクラスや、ドットソースのスクリプトで定義されているクラスをモジュールに常にインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-233">It does not consistently import classes defined in nested modules or classes defined in scripts that are dot-sourced into the module.</span></span> <span data-ttu-id="c71bb-234">モジュールの外部のユーザーが使用できるようにするクラスは、ルートモジュールで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-234">Classes that you want to be available to users outside of the module should be defined in the root module.</span></span>

## <a name="loading-newly-changed-code-during-development"></a><span data-ttu-id="c71bb-235">開発中に新しく変更されたコードの読み込み</span><span class="sxs-lookup"><span data-stu-id="c71bb-235">Loading newly changed code during development</span></span>

<span data-ttu-id="c71bb-236">スクリプトモジュールの開発時には、コードに変更を加えた後、Force パラメーターを指定してを使用して新しいバージョンのモジュールを読み込むのが一般的です `Import-Module` 。 </span><span class="sxs-lookup"><span data-stu-id="c71bb-236">During development of a script module, it is common to make changes to the code then load the new version of the module using `Import-Module` with the **Force** parameter.</span></span> <span data-ttu-id="c71bb-237">これは、ルートモジュールの関数の変更に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-237">This works for changes to functions in the root module only.</span></span> <span data-ttu-id="c71bb-238">`Import-Module` では、入れ子になったモジュールは再読み込みされません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-238">`Import-Module` does not reload any nested modules.</span></span> <span data-ttu-id="c71bb-239">また、更新されたクラスを読み込む方法はありません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-239">Also, there is no way to load any updated classes.</span></span>

<span data-ttu-id="c71bb-240">最新バージョンを実行していることを確認するには、コマンドレットを使用してモジュールをアンロードする必要があり `Remove-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="c71bb-240">To ensure that you are running the latest version, you must unload the module using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="c71bb-241">`Remove-Module` ルートモジュール、すべての入れ子になったモジュール、およびモジュールで定義されているすべてのクラスを削除します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-241">`Remove-Module` removes the root module, all nested modules, and any classes defined in the modules.</span></span> <span data-ttu-id="c71bb-242">次に、およびステートメントを使用して、モジュールとクラスを再度読み込みます `Import-Module` `using module` 。</span><span class="sxs-lookup"><span data-stu-id="c71bb-242">Then you can reload the module and the classes using `Import-Module` and the `using module` statement.</span></span>

<span data-ttu-id="c71bb-243">もう1つの一般的な開発手法は、コードを別のファイルに分割することです。</span><span class="sxs-lookup"><span data-stu-id="c71bb-243">Another common development practice is to separate your code into different files.</span></span> <span data-ttu-id="c71bb-244">別のモジュールで定義されているクラスを使用する関数が1つのファイルにある場合は、ステートメントを使用して、 `using module` 必要なクラス定義が関数に確実に含まれるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-244">If you have function in one file that use classes defined in another module, you should using the `using module` statement to ensure that the functions have the class definitions that are needed.</span></span>

## <a name="the-psreference-type-is-not-supported-with-class-members"></a><span data-ttu-id="c71bb-245">PSReference 型はクラスメンバーではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="c71bb-245">The PSReference type is not supported with class members</span></span>

<span data-ttu-id="c71bb-246">`[ref]`クラスメンバーによる型キャストの使用は、暗黙的に失敗します。</span><span class="sxs-lookup"><span data-stu-id="c71bb-246">Using the `[ref]` type-cast with a class member silently fails.</span></span> <span data-ttu-id="c71bb-247">パラメーターを使用する Api `[ref]` は、クラスメンバーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c71bb-247">APIs that use `[ref]` parameters cannot be used with class members.</span></span> <span data-ttu-id="c71bb-248">**Psreference** クラスは、COM オブジェクトをサポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c71bb-248">The **PSReference** class was designed to support COM objects.</span></span> <span data-ttu-id="c71bb-249">COM オブジェクトには、参照によっての値を渡す必要があるケースがあります。</span><span class="sxs-lookup"><span data-stu-id="c71bb-249">COM objects have cases where you need to pass a value in by reference.</span></span>

<span data-ttu-id="c71bb-250">型の詳細については `[ref]` 、「 [Psreference クラス](/dotnet/api/system.management.automation.psreference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c71bb-250">For more information about the `[ref]` type, see [PSReference Class](/dotnet/api/system.management.automation.psreference).</span></span>

## <a name="see-also"></a><span data-ttu-id="c71bb-251">関連項目</span><span class="sxs-lookup"><span data-stu-id="c71bb-251">See also</span></span>

- [<span data-ttu-id="c71bb-252">About_hidden</span><span class="sxs-lookup"><span data-stu-id="c71bb-252">About_hidden</span></span>](About_hidden.md)
- [<span data-ttu-id="c71bb-253">about_Enum</span><span class="sxs-lookup"><span data-stu-id="c71bb-253">about_Enum</span></span>](about_Enum.md)
- [<span data-ttu-id="c71bb-254">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="c71bb-254">about_Language_Keywords</span></span>](about_language_keywords.md)
- [<span data-ttu-id="c71bb-255">about_Methods</span><span class="sxs-lookup"><span data-stu-id="c71bb-255">about_Methods</span></span>](about_methods.md)
- [<span data-ttu-id="c71bb-256">about_Using</span><span class="sxs-lookup"><span data-stu-id="c71bb-256">about_Using</span></span>](about_using.md)

---
description: PowerShell でオブジェクトを作成する方法について説明します。
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_object_creation?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Object_Creation
ms.openlocfilehash: 72c0d763fe7f3838c8b2ca68930521e24d0e6139
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605194"
---
# <a name="about-object-creation"></a><span data-ttu-id="d324f-103">オブジェクトの作成について</span><span class="sxs-lookup"><span data-stu-id="d324f-103">About Object Creation</span></span>

## <a name="short-description"></a><span data-ttu-id="d324f-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="d324f-104">Short description</span></span>

<span data-ttu-id="d324f-105">PowerShell でオブジェクトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d324f-105">Explains how to create objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="d324f-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="d324f-106">Long description</span></span>

<span data-ttu-id="d324f-107">PowerShell でオブジェクトを作成し、コマンドやスクリプトで作成したオブジェクトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d324f-107">You can create objects in PowerShell and use the objects that you create in commands and scripts.</span></span>

<span data-ttu-id="d324f-108">オブジェクトを作成するには多くの方法がありますが、このリストは明確ではありません。</span><span class="sxs-lookup"><span data-stu-id="d324f-108">There are many ways to create objects, this list is not definitive:</span></span>

- <span data-ttu-id="d324f-109">[New-object](xref:Microsoft.PowerShell.Utility.New-Object): .NET Framework オブジェクトまたは COM オブジェクトのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d324f-109">[New-Object](xref:Microsoft.PowerShell.Utility.New-Object): Creates an instance of a .NET Framework object or COM object.</span></span>
- <span data-ttu-id="d324f-110">[インポート-Csv](xref:Microsoft.PowerShell.Utility.Import-Csv) /
  [Convertfrom-csv](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): コンマ区切り値として定義された項目からカスタムオブジェクト (**pscustomobject**) を作成します。</span><span class="sxs-lookup"><span data-stu-id="d324f-110">[Import-Csv](xref:Microsoft.PowerShell.Utility.Import-Csv)/
  [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): Creates custom objects (**PSCustomObject**) from the items defined as comma separated values.</span></span>
- <span data-ttu-id="d324f-111">[Convertfrom-csv](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): json (JavaScript Object Notation) で定義されているカスタムオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d324f-111">[ConvertFrom-Json](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): Creates custom objects defined in JavaScript Object Notation (JSON).</span></span>
- <span data-ttu-id="d324f-112">[Convertfrom-csv-convertfrom-stringdata](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): キーと値のペアとして定義されたカスタムオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d324f-112">[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): Creates custom objects defined as key value pairs.</span></span>
- <span data-ttu-id="d324f-113">[Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): PowerShell セッションでインスタンス化できるクラスを定義でき `New-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="d324f-113">[Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): Allows you to define a class in your PowerShell session that you can instantiate with `New-Object`.</span></span>
- <span data-ttu-id="d324f-114">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): **ascustomobject** いうパラメーターは、スクリプトブロックを使用して定義するカスタムオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d324f-114">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): The **AsCustomObject** parameter creates a custom object you define using script block.</span></span>
- <span data-ttu-id="d324f-115">[メンバーの追加](xref:Microsoft.PowerShell.Utility.Add-Member): 既存のオブジェクトにプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="d324f-115">[Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): Adds properties to existing objects.</span></span> <span data-ttu-id="d324f-116">を使用すると `Add-Member` 、などの単純な型からカスタムオブジェクトを作成でき `[System.Int32]` ます。</span><span class="sxs-lookup"><span data-stu-id="d324f-116">You can use `Add-Member` to create a custom object out of a simple type, like `[System.Int32]`.</span></span>
- <span data-ttu-id="d324f-117">[[オブジェクトの選択]](xref:Microsoft.PowerShell.Utility.Select-Object): オブジェクトのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="d324f-117">[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): Selects properties on an object.</span></span> <span data-ttu-id="d324f-118">を使用する `Select-Object` と、既にインスタンス化されたオブジェクトに対して、カスタムプロパティおよび計算されるプロパティを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d324f-118">You can use `Select-Object` to create custom and calculated properties on an already instantiated object.</span></span>

<span data-ttu-id="d324f-119">この記事では、次の追加の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d324f-119">The following additional methods are covered in this article:</span></span>

- <span data-ttu-id="d324f-120">静的メソッドを使用して型のコンストラクターを呼び出す `new()`</span><span class="sxs-lookup"><span data-stu-id="d324f-120">By calling a type's constructor using a static `new()` method</span></span>
- <span data-ttu-id="d324f-121">Typecasting ハッシュテーブルのプロパティ名とプロパティ値</span><span class="sxs-lookup"><span data-stu-id="d324f-121">By typecasting hash tables of property names and property values</span></span>

## <a name="static-new-method"></a><span data-ttu-id="d324f-122">Static new () メソッド</span><span class="sxs-lookup"><span data-stu-id="d324f-122">Static new() method</span></span>

<span data-ttu-id="d324f-123">すべての .NET 型には、 `new()` インスタンスをより簡単に構築できるメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d324f-123">All .NET types have a `new()` method that allows you to construct instances more easily.</span></span> <span data-ttu-id="d324f-124">また、指定された型に対して使用可能なすべてのコンストラクターを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="d324f-124">You can also see all the available constructors for a given type.</span></span>

<span data-ttu-id="d324f-125">型のコンストラクターを表示するには、 `new` 型名の後にメソッド名を指定し、キーを押し `<ENTER>` ます。</span><span class="sxs-lookup"><span data-stu-id="d324f-125">To see the constructors for a type, specify the `new` method name after the type name and press `<ENTER>`.</span></span>

```powershell
[System.Uri]::new
```

```Output
OverloadDefinitions
-------------------
uri new(string uriString)
uri new(string uriString, bool dontEscape)
uri new(uri baseUri, string relativeUri, bool dontEscape)
uri new(string uriString, System.UriKind uriKind)
uri new(uri baseUri, string relativeUri)
uri new(uri baseUri, uri relativeUri)
```

<span data-ttu-id="d324f-126">ここで、適切なコンストラクターを指定 **して、system.string を作成** できます。</span><span class="sxs-lookup"><span data-stu-id="d324f-126">Now, you can create a **System.Uri** by specifying the appropriate constructor.</span></span>

```powershell
[System.Uri]::new("https://www.bing.com")
```

```Output
AbsolutePath   : /
AbsoluteUri    : https://www.bing.com/
LocalPath      : /
Authority      : www.bing.com
...
```

<span data-ttu-id="d324f-127">次のサンプルを使用して、インスタンス化するために現在読み込まれている .NET 型を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d324f-127">You can use the following sample to determine what .NET types are currently loaded for you to instantiate.</span></span>

```powershell
[AppDomain]::CurrentDomain.GetAssemblies() |
  ForEach-Object {
    $_.GetExportedTypes() |
      ForEach-Object { $_.FullName }
  }
```

<span data-ttu-id="d324f-128">メソッドを使用して作成されたオブジェクトは、 `new()` PowerShell コマンドレットで作成された同じ型のオブジェクトと同じプロパティを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="d324f-128">Objects created using the `new()` method may not have the same properties as objects of the same type that are created by PowerShell cmdlets.</span></span> <span data-ttu-id="d324f-129">PowerShell コマンドレット、プロバイダー、および拡張型システムでは、インスタンスに追加のプロパティを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d324f-129">PowerShell cmdlets, providers, and Extended Type System can add extra properties to the instance.</span></span>

<span data-ttu-id="d324f-130">たとえば、PowerShell の FileSystem プロバイダーは、によって返される **DirectoryInfo** オブジェクトに、6つの **メモプロパティ** 値を追加し `Get-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="d324f-130">For example, the FileSystem provider in PowerShell adds six **NoteProperty** values to the **DirectoryInfo** object returned by `Get-Item`.</span></span>

```powershell
$PSDirInfo = Get-Item /
$PSDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    6 NoteProperty
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="d324f-131">**DirectoryInfo** オブジェクトを直接作成した場合、そのオブジェクトには、これらの **メモプロパティ** 値は含まれません。</span><span class="sxs-lookup"><span data-stu-id="d324f-131">When you create a **DirectoryInfo** object directly, it does not have those six **NoteProperty** values.</span></span>

```powershell
$NewDirInfo = [System.IO.DirectoryInfo]::new('/')
$NewDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="d324f-132">拡張型システムの詳細については、「 [about_Types.ps1xml](about_Types.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d324f-132">For more information about the Extended Type System, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

<span data-ttu-id="d324f-133">この機能は PowerShell 5.0 で追加されました</span><span class="sxs-lookup"><span data-stu-id="d324f-133">This feature was added in PowerShell 5.0</span></span>

## <a name="create-objects-from-hash-tables"></a><span data-ttu-id="d324f-134">ハッシュテーブルからオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="d324f-134">Create objects from hash tables</span></span>

<span data-ttu-id="d324f-135">プロパティとプロパティ値のハッシュテーブルからオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d324f-135">You can create an object from a hash table of properties and property values.</span></span>

<span data-ttu-id="d324f-136">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d324f-136">The syntax is as follows:</span></span>

```
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

<span data-ttu-id="d324f-137">このメソッドは、パラメーターなしのコンストラクターを持つクラスに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="d324f-137">This method works only for classes that have a parameterless constructor.</span></span> <span data-ttu-id="d324f-138">オブジェクトのプロパティは、パブリックで設定可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d324f-138">The object properties must be public and settable.</span></span>

<span data-ttu-id="d324f-139">この機能は PowerShell バージョン3.0 で追加されました</span><span class="sxs-lookup"><span data-stu-id="d324f-139">This feature was added in PowerShell version 3.0</span></span>

## <a name="create-custom-objects-from-hash-tables"></a><span data-ttu-id="d324f-140">ハッシュテーブルからカスタムオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="d324f-140">Create custom objects from hash tables</span></span>

<span data-ttu-id="d324f-141">カスタムオブジェクトは非常に便利で、ハッシュテーブルメソッドを使用して簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="d324f-141">Custom objects are very useful and are easy to create using the hash table method.</span></span> <span data-ttu-id="d324f-142">**Pscustomobject** 各クラスは、特にこの目的のために設計されています。</span><span class="sxs-lookup"><span data-stu-id="d324f-142">The **PSCustomObject** class is designed specifically for this purpose.</span></span>

<span data-ttu-id="d324f-143">カスタムオブジェクトは、関数またはスクリプトからカスタマイズされた出力を返すための優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="d324f-143">Custom objects are an excellent way to return customized output from a function or script.</span></span> <span data-ttu-id="d324f-144">これは、他のコマンドに再フォーマットしたりパイプを使用したりできない書式設定された出力を返すよりも便利です。</span><span class="sxs-lookup"><span data-stu-id="d324f-144">This is more useful than returning formatted output that cannot be reformatted or piped to other commands.</span></span>

<span data-ttu-id="d324f-145">のコマンドは、 `Test-Object function` 変数の値を設定し、それらの値を使用してカスタムオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d324f-145">The commands in the `Test-Object function` set some variable values and then use those values to create a custom object.</span></span> <span data-ttu-id="d324f-146">このオブジェクトは、コマンドレットのヘルプトピックの「例」のセクションで使用して `Update-Help` います。</span><span class="sxs-lookup"><span data-stu-id="d324f-146">You can see this object in use in the example section of the `Update-Help` cmdlet help topic.</span></span>

```powershell
function Test-Object {
  $ModuleName = "PSScheduledJob"
  $HelpCulture = "en-us"
  $HelpVersion = "3.1.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
  $ModuleName = "PSWorkflow"
  $HelpCulture = "en-us"
  $HelpVersion = "3.0.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
}
Test-Object
```

<span data-ttu-id="d324f-147">この関数の出力は、既定ではテーブルとして書式設定されたカスタムオブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d324f-147">The output of this function is a collection of custom objects formatted as a table by default.</span></span>

```Output
ModuleName        UICulture      Version
---------         ---------      -------
PSScheduledJob    en-us          3.1.0.0
PSWorkflow        en-us          3.0.0.0
```

<span data-ttu-id="d324f-148">ユーザーは、標準のオブジェクトの場合と同じように、カスタムオブジェクトのプロパティを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d324f-148">Users can manage the properties of the custom objects just as they do with standard objects.</span></span>

```powershell
(Test-Object).ModuleName
```

```Output
 PSScheduledJob
 PSWorkflow
```

## <a name="create-non-custom-objects-from-hash-tables"></a><span data-ttu-id="d324f-149">ハッシュテーブルからの非カスタムオブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d324f-149">Create non-custom objects from hash tables</span></span>

<span data-ttu-id="d324f-150">また、ハッシュテーブルを使用して、非カスタムクラスのオブジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d324f-150">You can also use hash tables to create objects for non-custom classes.</span></span> <span data-ttu-id="d324f-151">カスタムではないクラスのオブジェクトを作成する場合は、名前空間で修飾された型名が必要です。ただし、最初の **システム** 名前空間コンポーネントは省略できます。</span><span class="sxs-lookup"><span data-stu-id="d324f-151">When you create an object for a non-custom class, the namespace-qualified type name is required, although you may omit any initial **System** namespace component.</span></span>

<span data-ttu-id="d324f-152">たとえば、次のコマンドでは、セッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d324f-152">For example, the following command creates a session option object.</span></span>

```powershell
[System.Management.Automation.Remoting.PSSessionOption]@{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
```

<span data-ttu-id="d324f-153">ハッシュテーブル機能の要件 (特にパラメーターなしのコンストラクターの要件) によって、既存のクラスが多数削除されます。</span><span class="sxs-lookup"><span data-stu-id="d324f-153">The requirements of the hash table feature, especially the parameterless constructor requirement, eliminate many existing classes.</span></span> <span data-ttu-id="d324f-154">ただし、ほとんどの PowerShell _オプション_ クラスは、この機能を使用するように設計されています。また、 **ProcessStartInfo** クラスなどの非常に便利なクラスでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d324f-154">However, most PowerShell _option_ classes are designed to work with this feature, as well as other very useful classes, such as the **ProcessStartInfo** class.</span></span>

```powershell
[System.Diagnostics.ProcessStartInfo]@{
  CreateNoWindow="$true"
  Verb="run as"
}
```

```Output
Arguments               :
ArgumentList            : {}
CreateNoWindow          : True
EnvironmentVariables    : {OneDriveConsumer, PROCESSOR_ARCHITECTURE,
                           CommonProgramFiles(x86), APPDATA...}
Environment             : {[OneDriveConsumer, C:\Users\user1\OneDrive],
                           [PROCESSOR_ARCHITECTURE, AMD64],
                           [CommonProgramFiles(x86),
                           C:\Program Files (x86)\Common Files],
                           [APPDATA, C:\Users\user1\AppData\Roaming]...}
RedirectStandardInput   : False
RedirectStandardOutput  : False
RedirectStandardError   : False
...
```

<span data-ttu-id="d324f-155">また、パラメーター値を設定するときに、ハッシュテーブル機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d324f-155">You can also use the hash table feature when setting parameter values.</span></span> <span data-ttu-id="d324f-156">たとえば、の **Sessionoption** パラメーターの値 `New-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="d324f-156">For example, the value of the **SessionOption** parameter of the `New-PSSession`.</span></span>
<span data-ttu-id="d324f-157">コマンドレットはハッシュテーブルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d324f-157">cmdlet can be a hash table.</span></span>

```powershell
New-PSSession -ComputerName Server01 -SessionOption @{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
Register-ScheduledJob Name Test -FilePath .\Get-Inventory.ps1 -Trigger @{
  Frequency="Daily"
  At="15:00"
}
```

## <a name="generic-objects"></a><span data-ttu-id="d324f-158">汎用オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d324f-158">Generic objects</span></span>

<span data-ttu-id="d324f-159">PowerShell で汎用オブジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d324f-159">You can also create generic objects in PowerShell.</span></span> <span data-ttu-id="d324f-160">ジェネリックは、格納または使用される 1 つ以上の型のプレースホルダー (型パラメーター) を持つクラス、構造体、インターフェイス、およびメソッドです。</span><span class="sxs-lookup"><span data-stu-id="d324f-160">Generics are classes, structures, interfaces, and methods that have placeholders (type parameters) for one or more of the types that they store or use.</span></span>

<span data-ttu-id="d324f-161">次の例では、 **ディクショナリ** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d324f-161">The following example creates a **Dictionary** object.</span></span>

```powershell
$dict = New-Object 'System.Collections.Generic.Dictionary[String,Int]'
$dict.Add("One", 1)
$dict
```

```Output
Key Value
--- -----
One     1
```

<span data-ttu-id="d324f-162">ジェネリックの詳細については、「 [.net のジェネリック](/dotnet/standard/generics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d324f-162">For more information on Generics, see [Generics in .NET](/dotnet/standard/generics).</span></span>

## <a name="see-also"></a><span data-ttu-id="d324f-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="d324f-163">See also</span></span>

[<span data-ttu-id="d324f-164">about_Objects</span><span class="sxs-lookup"><span data-stu-id="d324f-164">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="d324f-165">about_Methods</span><span class="sxs-lookup"><span data-stu-id="d324f-165">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="d324f-166">about_Properties</span><span class="sxs-lookup"><span data-stu-id="d324f-166">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="d324f-167">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="d324f-167">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="d324f-168">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="d324f-168">about_Types.ps1xml</span></span>](about_Types.ps1xml.md)

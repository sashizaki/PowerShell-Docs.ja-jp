---
description: PowerShell でオブジェクトを作成する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_object_creation?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Object_Creation
ms.openlocfilehash: 885218848081aae364e662c3060500af3f5759ab
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220979"
---
# <a name="about-object-creation"></a><span data-ttu-id="d74fc-104">オブジェクトの作成について</span><span class="sxs-lookup"><span data-stu-id="d74fc-104">About Object Creation</span></span>

## <a name="short-description"></a><span data-ttu-id="d74fc-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="d74fc-105">Short description</span></span>

<span data-ttu-id="d74fc-106">PowerShell でオブジェクトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-106">Explains how to create objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="d74fc-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="d74fc-107">Long description</span></span>

<span data-ttu-id="d74fc-108">PowerShell でオブジェクトを作成し、コマンドやスクリプトで作成したオブジェクトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-108">You can create objects in PowerShell and use the objects that you create in commands and scripts.</span></span>

<span data-ttu-id="d74fc-109">オブジェクトを作成するには多くの方法がありますが、このリストは明確ではありません。</span><span class="sxs-lookup"><span data-stu-id="d74fc-109">There are many ways to create objects, this list is not definitive:</span></span>

- <span data-ttu-id="d74fc-110">[New-object](xref:Microsoft.PowerShell.Utility.New-Object): .NET Framework オブジェクトまたは COM オブジェクトのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-110">[New-Object](xref:Microsoft.PowerShell.Utility.New-Object): Creates an instance of a .NET Framework object or COM object.</span></span>
- <span data-ttu-id="d74fc-111">[インポート-Csv](xref:Microsoft.PowerShell.Utility.Import-Csv) /
  [Convertfrom-csv](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): コンマ区切り値として定義された項目からカスタムオブジェクト ( **pscustomobject** ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-111">[Import-Csv](xref:Microsoft.PowerShell.Utility.Import-Csv)/
  [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): Creates custom objects ( **PSCustomObject** ) from the items defined as comma separated values.</span></span>
- <span data-ttu-id="d74fc-112">[Convertfrom-csv](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): json (JavaScript Object Notation) で定義されているカスタムオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-112">[ConvertFrom-Json](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): Creates custom objects defined in JavaScript Object Notation (JSON).</span></span>
- <span data-ttu-id="d74fc-113">[Convertfrom-csv-convertfrom-stringdata](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): キーと値のペアとして定義されたカスタムオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-113">[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): Creates custom objects defined as key value pairs.</span></span>
- <span data-ttu-id="d74fc-114">[Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): PowerShell セッションでインスタンス化できるクラスを定義でき `New-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-114">[Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): Allows you to define a class in your PowerShell session that you can instantiate with `New-Object`.</span></span>
- <span data-ttu-id="d74fc-115">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): **ascustomobject** いうパラメーターは、スクリプトブロックを使用して定義するカスタムオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-115">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): The **AsCustomObject** parameter creates a custom object you define using script block.</span></span>
- <span data-ttu-id="d74fc-116">[メンバーの追加](xref:Microsoft.PowerShell.Utility.Add-Member): 既存のオブジェクトにプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-116">[Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): Adds properties to existing objects.</span></span> <span data-ttu-id="d74fc-117">を使用すると `Add-Member` 、などの単純な型からカスタムオブジェクトを作成でき `[System.Int32]` ます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-117">You can use `Add-Member` to create a custom object out of a simple type, like `[System.Int32]`.</span></span>
- <span data-ttu-id="d74fc-118">[[オブジェクトの選択]](xref:Microsoft.PowerShell.Utility.Select-Object): オブジェクトのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-118">[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): Selects properties on an object.</span></span> <span data-ttu-id="d74fc-119">を使用する `Select-Object` と、既にインスタンス化されたオブジェクトに対して、カスタムプロパティおよび計算されるプロパティを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-119">You can use `Select-Object` to create custom and calculated properties on an already instantiated object.</span></span>

<span data-ttu-id="d74fc-120">この記事では、次の追加の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-120">The following additional methods are covered in this article:</span></span>

- <span data-ttu-id="d74fc-121">静的メソッドを使用して型のコンストラクターを呼び出す `new()`</span><span class="sxs-lookup"><span data-stu-id="d74fc-121">By calling a type's constructor using a static `new()` method</span></span>
- <span data-ttu-id="d74fc-122">Typecasting ハッシュテーブルのプロパティ名とプロパティ値</span><span class="sxs-lookup"><span data-stu-id="d74fc-122">By typecasting hash tables of property names and property values</span></span>

## <a name="static-new-method"></a><span data-ttu-id="d74fc-123">Static new () メソッド</span><span class="sxs-lookup"><span data-stu-id="d74fc-123">Static new() method</span></span>

<span data-ttu-id="d74fc-124">すべての .NET 型には、 `new()` インスタンスをより簡単に構築できるメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d74fc-124">All .NET types have a `new()` method that allows you to construct instances more easily.</span></span> <span data-ttu-id="d74fc-125">また、指定された型に対して使用可能なすべてのコンストラクターを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-125">You can also see all the available constructors for a given type.</span></span>

<span data-ttu-id="d74fc-126">型のコンストラクターを表示するには、 `new` 型名の後にメソッド名を指定し、キーを押し `<ENTER>` ます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-126">To see the constructors for a type, specify the `new` method name after the type name and press `<ENTER>`.</span></span>

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

<span data-ttu-id="d74fc-127">ここで、適切なコンストラクターを指定 **して、system.string を作成** できます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-127">Now, you can create a **System.Uri** by specifying the appropriate constructor.</span></span>

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

<span data-ttu-id="d74fc-128">次のサンプルを使用して、インスタンス化するために現在読み込まれている .NET 型を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-128">You can use the following sample to determine what .NET types are currently loaded for you to instantiate.</span></span>

```powershell
[AppDomain]::CurrentDomain.GetAssemblies() |
  ForEach-Object {
    $_.GetExportedTypes() |
      ForEach-Object { $_.FullName }
  }
```

<span data-ttu-id="d74fc-129">メソッドを使用して作成されたオブジェクトは、 `new()` PowerShell コマンドレットで作成された同じ型のオブジェクトと同じプロパティを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="d74fc-129">Objects created using the `new()` method may not have the same properties as objects of the same type that are created by PowerShell cmdlets.</span></span> <span data-ttu-id="d74fc-130">PowerShell コマンドレット、プロバイダー、および拡張型システムでは、インスタンスに追加のプロパティを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-130">PowerShell cmdlets, providers, and Extended Type System can add extra properties to the instance.</span></span>

<span data-ttu-id="d74fc-131">たとえば、PowerShell の FileSystem プロバイダーは、によって返される **DirectoryInfo** オブジェクトに、6つの **メモプロパティ** 値を追加し `Get-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-131">For example, the FileSystem provider in PowerShell adds six **NoteProperty** values to the **DirectoryInfo** object returned by `Get-Item`.</span></span>

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

<span data-ttu-id="d74fc-132">**DirectoryInfo** オブジェクトを直接作成した場合、そのオブジェクトには、これらの **メモプロパティ** 値は含まれません。</span><span class="sxs-lookup"><span data-stu-id="d74fc-132">When you create a **DirectoryInfo** object directly, it does not have those six **NoteProperty** values.</span></span>

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

<span data-ttu-id="d74fc-133">拡張型システムの詳細については、「 [about_Types.ps1xml](about_Types.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d74fc-133">For more information about the Extended Type System, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

<span data-ttu-id="d74fc-134">この機能は PowerShell 5.0 で追加されました</span><span class="sxs-lookup"><span data-stu-id="d74fc-134">This feature was added in PowerShell 5.0</span></span>

## <a name="create-objects-from-hash-tables"></a><span data-ttu-id="d74fc-135">ハッシュテーブルからオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="d74fc-135">Create objects from hash tables</span></span>

<span data-ttu-id="d74fc-136">プロパティとプロパティ値のハッシュテーブルからオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-136">You can create an object from a hash table of properties and property values.</span></span>

<span data-ttu-id="d74fc-137">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d74fc-137">The syntax is as follows:</span></span>

```
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

<span data-ttu-id="d74fc-138">このメソッドは、パラメーターなしのコンストラクターを持つクラスに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-138">This method works only for classes that have a parameterless constructor.</span></span> <span data-ttu-id="d74fc-139">オブジェクトのプロパティは、パブリックで設定可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d74fc-139">The object properties must be public and settable.</span></span>

<span data-ttu-id="d74fc-140">この機能は PowerShell バージョン3.0 で追加されました</span><span class="sxs-lookup"><span data-stu-id="d74fc-140">This feature was added in PowerShell version 3.0</span></span>

## <a name="create-custom-objects-from-hash-tables"></a><span data-ttu-id="d74fc-141">ハッシュテーブルからカスタムオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="d74fc-141">Create custom objects from hash tables</span></span>

<span data-ttu-id="d74fc-142">カスタムオブジェクトは非常に便利で、ハッシュテーブルメソッドを使用して簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-142">Custom objects are very useful and are easy to create using the hash table method.</span></span> <span data-ttu-id="d74fc-143">**Pscustomobject** 各クラスは、特にこの目的のために設計されています。</span><span class="sxs-lookup"><span data-stu-id="d74fc-143">The **PSCustomObject** class is designed specifically for this purpose.</span></span>

<span data-ttu-id="d74fc-144">カスタムオブジェクトは、関数またはスクリプトからカスタマイズされた出力を返すための優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="d74fc-144">Custom objects are an excellent way to return customized output from a function or script.</span></span> <span data-ttu-id="d74fc-145">これは、他のコマンドに再フォーマットしたりパイプを使用したりできない書式設定された出力を返すよりも便利です。</span><span class="sxs-lookup"><span data-stu-id="d74fc-145">This is more useful than returning formatted output that cannot be reformatted or piped to other commands.</span></span>

<span data-ttu-id="d74fc-146">のコマンドは、 `Test-Object function` 変数の値を設定し、それらの値を使用してカスタムオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-146">The commands in the `Test-Object function` set some variable values and then use those values to create a custom object.</span></span> <span data-ttu-id="d74fc-147">このオブジェクトは、コマンドレットのヘルプトピックの「例」のセクションで使用して `Update-Help` います。</span><span class="sxs-lookup"><span data-stu-id="d74fc-147">You can see this object in use in the example section of the `Update-Help` cmdlet help topic.</span></span>

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

<span data-ttu-id="d74fc-148">この関数の出力は、既定ではテーブルとして書式設定されたカスタムオブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d74fc-148">The output of this function is a collection of custom objects formatted as a table by default.</span></span>

```Output
ModuleName        UICulture      Version
---------         ---------      -------
PSScheduledJob    en-us          3.1.0.0
PSWorkflow        en-us          3.0.0.0
```

<span data-ttu-id="d74fc-149">ユーザーは、標準のオブジェクトの場合と同じように、カスタムオブジェクトのプロパティを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-149">Users can manage the properties of the custom objects just as they do with standard objects.</span></span>

```powershell
(Test-Object).ModuleName
```

```Output
 PSScheduledJob
 PSWorkflow
```

## <a name="create-non-custom-objects-from-hash-tables"></a><span data-ttu-id="d74fc-150">ハッシュテーブルからの非カスタムオブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d74fc-150">Create non-custom objects from hash tables</span></span>

<span data-ttu-id="d74fc-151">また、ハッシュテーブルを使用して、非カスタムクラスのオブジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-151">You can also use hash tables to create objects for non-custom classes.</span></span> <span data-ttu-id="d74fc-152">カスタムではないクラスのオブジェクトを作成する場合は、名前空間で修飾された型名が必要です。ただし、最初の **システム** 名前空間コンポーネントは省略できます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-152">When you create an object for a non-custom class, the namespace-qualified type name is required, although you may omit any initial **System** namespace component.</span></span>

<span data-ttu-id="d74fc-153">たとえば、次のコマンドでは、セッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-153">For example, the following command creates a session option object.</span></span>

```powershell
[System.Management.Automation.Remoting.PSSessionOption]@{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
```

<span data-ttu-id="d74fc-154">ハッシュテーブル機能の要件 (特にパラメーターなしのコンストラクターの要件) によって、既存のクラスが多数削除されます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-154">The requirements of the hash table feature, especially the parameterless constructor requirement, eliminate many existing classes.</span></span> <span data-ttu-id="d74fc-155">ただし、ほとんどの PowerShell _オプション_ クラスは、この機能を使用するように設計されています。また、 **ProcessStartInfo** クラスなどの非常に便利なクラスでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-155">However, most PowerShell _option_ classes are designed to work with this feature, as well as other very useful classes, such as the **ProcessStartInfo** class.</span></span>

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

<span data-ttu-id="d74fc-156">また、パラメーター値を設定するときに、ハッシュテーブル機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-156">You can also use the hash table feature when setting parameter values.</span></span> <span data-ttu-id="d74fc-157">たとえば、の **Sessionoption** パラメーターの値 `New-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="d74fc-157">For example, the value of the **SessionOption** parameter of the `New-PSSession`.</span></span>
<span data-ttu-id="d74fc-158">コマンドレットはハッシュテーブルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-158">cmdlet can be a hash table.</span></span>

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

## <a name="generic-objects"></a><span data-ttu-id="d74fc-159">汎用オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d74fc-159">Generic objects</span></span>

<span data-ttu-id="d74fc-160">PowerShell で汎用オブジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d74fc-160">You can also create generic objects in PowerShell.</span></span> <span data-ttu-id="d74fc-161">ジェネリックは、格納または使用される 1 つ以上の型のプレースホルダー (型パラメーター) を持つクラス、構造体、インターフェイス、およびメソッドです。</span><span class="sxs-lookup"><span data-stu-id="d74fc-161">Generics are classes, structures, interfaces, and methods that have placeholders (type parameters) for one or more of the types that they store or use.</span></span>

<span data-ttu-id="d74fc-162">次の例では、 **ディクショナリ** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d74fc-162">The following example creates a **Dictionary** object.</span></span>

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

<span data-ttu-id="d74fc-163">ジェネリックの詳細については、「 [.net のジェネリック](/dotnet/standard/generics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d74fc-163">For more information on Generics, see [Generics in .NET](/dotnet/standard/generics).</span></span>

## <a name="see-also"></a><span data-ttu-id="d74fc-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="d74fc-164">See also</span></span>

[<span data-ttu-id="d74fc-165">about_Objects</span><span class="sxs-lookup"><span data-stu-id="d74fc-165">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="d74fc-166">about_Methods</span><span class="sxs-lookup"><span data-stu-id="d74fc-166">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="d74fc-167">about_Properties</span><span class="sxs-lookup"><span data-stu-id="d74fc-167">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="d74fc-168">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="d74fc-168">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="d74fc-169">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="d74fc-169">about_Types.ps1xml</span></span>](about_Types.ps1xml.md)
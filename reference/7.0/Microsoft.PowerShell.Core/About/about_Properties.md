---
description: PowerShell でオブジェクトのプロパティを使用する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Properties
ms.openlocfilehash: a9ba35ea0a999b116f818bffa5fba3a1366687b1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220680"
---
# <a name="about-properties"></a><span data-ttu-id="6b3d8-104">プロパティについて</span><span class="sxs-lookup"><span data-stu-id="6b3d8-104">About Properties</span></span>

## <a name="short-description"></a><span data-ttu-id="6b3d8-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6b3d8-105">Short description</span></span>
<span data-ttu-id="6b3d8-106">PowerShell でオブジェクトのプロパティを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-106">Describes how to use object properties in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6b3d8-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="6b3d8-107">Long description</span></span>

<span data-ttu-id="6b3d8-108">PowerShell では、オブジェクトと呼ばれる情報の構造化されたコレクションを使用して、データストア内の項目またはコンピューターの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-108">PowerShell uses structured collections of information called objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="6b3d8-109">通常は、Microsoft .NET Framework の一部であるオブジェクトを使用しますが、PowerShell でカスタムオブジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-109">Typically, you work with object that are part of the Microsoft .NET Framework, but you can also create custom objects in PowerShell.</span></span>

<span data-ttu-id="6b3d8-110">項目とそのオブジェクトの間の関連付けは非常に近いものです。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-110">The association between an item and its object is very close.</span></span> <span data-ttu-id="6b3d8-111">オブジェクトを変更する場合は、通常、そのオブジェクトが表すアイテムを変更します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-111">When you change an object, you usually change the item that it represents.</span></span> <span data-ttu-id="6b3d8-112">たとえば、PowerShell でファイルを取得する場合、実際のファイルは取得されません。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-112">For example, when you get a file in PowerShell, you do not get the actual file.</span></span> <span data-ttu-id="6b3d8-113">代わりに、ファイルを表す FileInfo オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-113">Instead, you get a FileInfo object that represents the file.</span></span> <span data-ttu-id="6b3d8-114">FileInfo オブジェクトを変更すると、ファイルも変更されます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-114">When you change the FileInfo object, the file changes too.</span></span>

<span data-ttu-id="6b3d8-115">ほとんどのオブジェクトにはプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-115">Most objects have properties.</span></span> <span data-ttu-id="6b3d8-116">プロパティは、オブジェクトに関連付けられているデータです。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-116">Properties are the data that is associated with an object.</span></span> <span data-ttu-id="6b3d8-117">オブジェクトの種類によって、プロパティが異なります。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-117">Different types of object have different properties.</span></span> <span data-ttu-id="6b3d8-118">たとえば、ファイルを表す FileInfo オブジェクトには、ファイルが読み取り専用の属性を持っている場合は $True を含む **IsReadOnly** プロパティがあり、存在しない場合は $False ます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-118">For example, a FileInfo object, which represents a file, has an **IsReadOnly** property that contains $True if the file the read-only attribute and $False if it does not.</span></span>
<span data-ttu-id="6b3d8-119">ファイルシステムディレクトリを表す DirectoryInfo オブジェクトには、親ディレクトリへのパスを含む親プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-119">A DirectoryInfo object, which represents a file system directory, has a Parent property that contains the path to the parent directory.</span></span>

### <a name="object-properties"></a><span data-ttu-id="6b3d8-120">オブジェクトのプロパティ</span><span class="sxs-lookup"><span data-stu-id="6b3d8-120">Object properties</span></span>

<span data-ttu-id="6b3d8-121">オブジェクトのプロパティを取得するには、コマンドレットを使用し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-121">To get the properties of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="6b3d8-122">たとえば、 **fileinfo** オブジェクトのプロパティを取得するには、コマンドレットを使用して、 `Get-ChildItem` ファイルを表す fileinfo オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-122">For example, to get the properties of a **FileInfo** object, use the `Get-ChildItem` cmdlet to get the FileInfo object that represents a file.</span></span> <span data-ttu-id="6b3d8-123">次に、パイプライン演算子 (&#124;) を使用して、 **FileInfo** オブジェクトをに送信し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-123">Then, use a pipeline operator (&#124;) to send the **FileInfo** object to `Get-Member`.</span></span> <span data-ttu-id="6b3d8-124">次のコマンドは、PowerShell.exe ファイルを取得してに送信し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-124">The following command gets the PowerShell.exe file and sends it to `Get-Member`.</span></span>
<span data-ttu-id="6b3d8-125">\$Pshome 自動変数には、PowerShell インストールディレクトリのパスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-125">The \$Pshome automatic variable contains the path of the PowerShell installation directory.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member
```

<span data-ttu-id="6b3d8-126">コマンドの出力には、 **FileInfo** オブジェクトのメンバーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-126">The output of the command lists the members of the **FileInfo** object.</span></span>
<span data-ttu-id="6b3d8-127">メンバーには、プロパティとメソッドの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-127">Members include both properties and methods.</span></span> <span data-ttu-id="6b3d8-128">PowerShell で作業する場合は、オブジェクトのすべてのメンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-128">When you work in PowerShell, you have access to all the members of the objects.</span></span>

<span data-ttu-id="6b3d8-129">メソッドではなく、オブジェクトのプロパティのみを取得するには、 `Get-Member` 次の例に示すように、コマンドレットの MemberType パラメーターに値 "property" を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-129">To get only the properties of an object and not the methods, use the MemberType parameter of the `Get-Member` cmdlet with a value of "property", as shown in the following example.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member -MemberType property
```

```Output
TypeName: System.IO.FileInfo

Name              MemberType Definition
----              ---------- ----------
Attributes        Property   System.IO.FileAttributes Attributes {get;set;}
CreationTime      Property   System.DateTime CreationTime {get;set;}
CreationTimeUtc   Property   System.DateTime CreationTimeUtc {get;set;}
Directory         Property   System.IO.DirectoryInfo Directory {get;}
DirectoryName     Property   System.String DirectoryName {get;}
Exists            Property   System.Boolean Exists {get;}
Extension         Property   System.String Extension {get;}
FullName          Property   System.String FullName {get;}
IsReadOnly        Property   System.Boolean IsReadOnly {get;set;}
LastAccessTime    Property   System.DateTime LastAccessTime {get;set;}
LastAccessTimeUtc Property   System.DateTime LastAccessTimeUtc {get;set;}
LastWriteTime     Property   System.DateTime LastWriteTime {get;set;}
LastWriteTimeUtc  Property   System.DateTime LastWriteTimeUtc {get;set;}
Length            Property   System.Int64 Length {get;}
Name              Property   System.String Name {get;}
```

<span data-ttu-id="6b3d8-130">プロパティが見つかったら、それらを PowerShell コマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-130">After you find the properties, you can use them in your PowerShell commands.</span></span>

## <a name="property-values"></a><span data-ttu-id="6b3d8-131">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="6b3d8-131">Property values</span></span>

<span data-ttu-id="6b3d8-132">特定の型のすべてのオブジェクトに同じプロパティがありますが、これらのプロパティの値によって特定のオブジェクトが記述されます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-132">Although every object of a specific type has the same properties, the values of those properties describe the particular object.</span></span> <span data-ttu-id="6b3d8-133">たとえば、すべての FileInfo オブジェクトには、"ファイルの時刻" プロパティがありますが、そのプロパティの値はファイルごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-133">For example, every FileInfo object has a CreationTime property, but the value of that property differs for each file.</span></span>

<span data-ttu-id="6b3d8-134">オブジェクトのプロパティの値を取得する最も一般的な方法は、ドットメソッドを使用することです。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-134">The most common way to get the values of the properties of an object is to use the dot method.</span></span> <span data-ttu-id="6b3d8-135">オブジェクトを格納する変数などのオブジェクトへの参照、またはオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-135">Type a reference to the object, such as a variable that contains the object, or a command that gets the object.</span></span> <span data-ttu-id="6b3d8-136">次に、ドット (.) の後にプロパティ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-136">Then, type a dot (.) followed by the property name.</span></span>

<span data-ttu-id="6b3d8-137">たとえば、次のコマンドは、PowerShell.exe ファイルの "値の指定" プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-137">For example, the following command displays the value of the CreationTime property of the PowerShell.exe file.</span></span> <span data-ttu-id="6b3d8-138">この `Get-ChildItem` コマンドは、PowerShell.exe ファイルを表す FileInfo オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-138">The `Get-ChildItem` command returns a FileInfo object that represents the PowerShell.exe file.</span></span> <span data-ttu-id="6b3d8-139">コマンドは、プロパティがアクセスされる前に実行されるように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-139">The command is enclosed in parentheses to make sure that it is executed before any properties are accessed.</span></span> <span data-ttu-id="6b3d8-140">`Get-ChildItem`次に示すように、コマンドの後には、ドットと、"値の指定" プロパティの名前が続きます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-140">The `Get-ChildItem` command is followed by a dot and the name of the CreationTime property, as follows:</span></span>

```powershell
(Get-ChildItem $pshome\PowerShell.exe).creationtime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="6b3d8-141">また、次の例に示すように、オブジェクトを変数に保存し、ドットメソッドを使用してそのプロパティを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-141">You can also save an object in a variable and then get its properties by using the dot method, as shown in the following example:</span></span>

```powershell
$a = Get-ChildItem $pshome\PowerShell.exe
$a.CreationTime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="6b3d8-142">また、 `Select-Object` `Format-List` コマンドレットとコマンドレットを使用して、オブジェクトのプロパティ値を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-142">You can also use the `Select-Object` and `Format-List` cmdlets to display the property values of an object.</span></span> <span data-ttu-id="6b3d8-143">`Select-Object``Format-List`それぞれに **プロパティ** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-143">`Select-Object` and `Format-List` each have a **Property** parameter.</span></span> <span data-ttu-id="6b3d8-144">**Property** パラメーターを使用して、1つまたは複数のプロパティとその値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-144">You can use the **Property** parameter to specify one or more properties and their values.</span></span> <span data-ttu-id="6b3d8-145">または、ワイルドカード文字 ( \* ) を使用してすべてのプロパティを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-145">Or, you can use the wildcard character (\*) to represent all the properties.</span></span>

<span data-ttu-id="6b3d8-146">たとえば、次のコマンドは、PowerShell.exe ファイルのすべてのプロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-146">For example, the following command displays the values of all the properties of the PowerShell.exe file.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Format-List -Property *
```

```output
PSPath            : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0\PowerShell.exe
PSParentPath      : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0
PSChildName       : PowerShell.exe
PSDrive           : C
PSProvider        : Microsoft.PowerShell.Core\FileSystem
PSIsContainer     : False
Mode              : -a----
VersionInfo       : File:             C:\Windows\System32\WindowsPowerShell\
                    v1.0\PowerShell.exe
                    InternalName:     POWERSHELL
                    OriginalFilename: PowerShell.EXE.MUI
                    FileVersion:      10.0.16299.15 (WinBuild.160101.0800)
                    FileDescription:  Windows PowerShell
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.16299.15
                    Debug:            False
                    Patched:          False
                    PreRelease:       False
                    PrivateBuild:     False
                    SpecialBuild:     False
                    Language:         English (United States)

BaseName          : PowerShell
Target            : {C:\Windows\WinSxS\amd64_microsoft-windows-powershell-ex
                    e_31bf3856ad364e35_10.0.16299.15_none_8c022aa6735716ae\p
                    owershell.exe}
LinkType          : HardLink
Name              : PowerShell.exe
Length            : 449024
DirectoryName     : C:\Windows\System32\WindowsPowerShell\v1.0
Directory         : C:\Windows\System32\WindowsPowerShell\v1.0
IsReadOnly        : False
Exists            : True
FullName          : C:\Windows\System32\WindowsPowerShell\v1.0\PowerShell.ex
Extension         : .exe
CreationTime      : 9/29/2017 6:43:19 AM
CreationTimeUtc   : 9/29/2017 1:43:19 PM
LastAccessTime    : 9/29/2017 6:43:19 AM
LastAccessTimeUtc : 9/29/2017 1:43:19 PM
LastWriteTime     : 9/29/2017 6:43:19 AM
LastWriteTimeUtc  : 9/29/2017 1:43:19 PM
Attributes        : Archive
```

### <a name="static-properties"></a><span data-ttu-id="6b3d8-147">静的プロパティ</span><span class="sxs-lookup"><span data-stu-id="6b3d8-147">Static properties</span></span>

<span data-ttu-id="6b3d8-148">PowerShell では、.NET クラスの静的プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-148">You can use the static properties of .NET classes in PowerShell.</span></span> <span data-ttu-id="6b3d8-149">静的プロパティは、オブジェクトのプロパティである標準プロパティとは異なり、クラスのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-149">Static properties are properties of class, unlike standard properties, which are properties of an object.</span></span>

<span data-ttu-id="6b3d8-150">クラスの静的プロパティを取得するには、Get-Member コマンドレットの Static パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-150">To get the static properties of an class, use the Static parameter of the Get-Member cmdlet.</span></span>

<span data-ttu-id="6b3d8-151">たとえば、次のコマンドは、クラスの静的プロパティを取得し `System.DateTime` ます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-151">For example, the following command gets the static properties of the `System.DateTime` class.</span></span>

```powershell
Get-Date | Get-Member -MemberType Property -Static
```

```Output
TypeName: System.DateTime

Name     MemberType Definition
----     ---------- ----------
MaxValue Property   static datetime MaxValue {get;}
MinValue Property   static datetime MinValue {get;}
Now      Property   datetime Now {get;}
Today    Property   datetime Today {get;}
UtcNow   Property   datetime UtcNow {get;}
```

<span data-ttu-id="6b3d8-152">静的プロパティの値を取得するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-152">To get the value of a static property, use the following syntax.</span></span>

```
[<ClassName>]::<Property>
```

<span data-ttu-id="6b3d8-153">たとえば、次のコマンドは、クラスの UtcNow 静的プロパティの値を取得し `System.DateTime` ます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-153">For example, the following command gets the value of the UtcNow static property of the `System.DateTime` class.</span></span>

```powershell
[System.DateTime]::UtcNow
```

### <a name="properties-of-scalar-objects-and-collections"></a><span data-ttu-id="6b3d8-154">スカラーオブジェクトとコレクションのプロパティ</span><span class="sxs-lookup"><span data-stu-id="6b3d8-154">Properties of scalar objects and collections</span></span>

<span data-ttu-id="6b3d8-155">特定の型の1つの ("スカラー") オブジェクトのプロパティは、多くの場合、同じ型のオブジェクトのコレクションのプロパティとは異なります。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-155">The properties of one ("scalar") object of a particular type are often different from the properties of a collection of objects of the same type.</span></span>
<span data-ttu-id="6b3d8-156">たとえば、すべてのサービスには **displayname** プロパティがありますが、サービスのコレクションには **displayname** プロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-156">For example, every service has as **DisplayName** property, but a collection of services does not have a **DisplayName** property.</span></span>

<span data-ttu-id="6b3d8-157">次のコマンドは、' Audiosrv ' サービスの **DisplayName** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-157">The following command gets the value of the **DisplayName** property of the 'Audiosrv' service.</span></span>

```powershell
(Get-Service Audiosrv).DisplayName
```

```output
Windows Audio
```

<span data-ttu-id="6b3d8-158">PowerShell 3.0 以降、PowerShell は、スカラーオブジェクトとコレクションの異なるプロパティに起因するスクリプトエラーを防止しようとします。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-158">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing properties of scalar objects and collections.</span></span> <span data-ttu-id="6b3d8-159">同じコマンドを実行すると、を返すすべてのサービスの **DisplayName** プロパティの値が返され `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-159">The same command returns the value of the **DisplayName** property of every service that `Get-Service` returns.</span></span>

```powershell
(Get-Service).DisplayName
```

```output
Application Experience
Application Layer Gateway Service
Windows All-User Install Agent
Application Identity
Application Information
...
```

<span data-ttu-id="6b3d8-160">コレクションを送信するときに、単一の ("スカラー") オブジェクトにのみ存在するプロパティを要求した場合、PowerShell はコレクション内のすべてのオブジェクトについて、そのプロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-160">When you submit a collection, but request a property that exists only on single ("scalar") objects, PowerShell returns the value of that property for every object in the collection.</span></span>

<span data-ttu-id="6b3d8-161">すべてのコレクションには、コレクションに含まれるオブジェクトの数を返す **Count** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-161">All collections have a **Count** property that returns how many objects are in the collection.</span></span>

```powershell
(Get-Service).Count
```

```output
176
```

<span data-ttu-id="6b3d8-162">PowerShell 3.0 以降、0個のオブジェクトまたは1つのオブジェクトの Count または Length プロパティを要求した場合、PowerShell は正しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-162">Beginning in PowerShell 3.0, if you request the Count or Length property of zero objects or one object, PowerShell returns the correct value.</span></span>

```powershell
(Get-Service Audiosrv).Count
```

```output
1
```

<span data-ttu-id="6b3d8-163">プロパティが個々のオブジェクトとコレクションに存在する場合は、コレクションのプロパティだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-163">If a property exists on the individual objects and on the collection, only the collection's property is returned.</span></span>

 ```powershell
 $collection = @(
 [pscustomobject]@{length = "foo"}
 [pscustomobject]@{length = "bar"}
 )
 # PowerShell returns the collection's Length.
 $collection.length
 ```

 ```output
 2
 ```

<span data-ttu-id="6b3d8-164">この機能は、スカラーオブジェクトおよびコレクションのメソッドに対しても機能します。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-164">This feature also works on methods of scalar objects and collections.</span></span> <span data-ttu-id="6b3d8-165">詳細については、「 [about_Methods](about_methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b3d8-165">For more information, see [about_Methods](about_methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b3d8-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b3d8-166">See also</span></span>

[<span data-ttu-id="6b3d8-167">about_Methods</span><span class="sxs-lookup"><span data-stu-id="6b3d8-167">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="6b3d8-168">about_Objects</span><span class="sxs-lookup"><span data-stu-id="6b3d8-168">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="6b3d8-169">Get-Member</span><span class="sxs-lookup"><span data-stu-id="6b3d8-169">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="6b3d8-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="6b3d8-170">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="6b3d8-171">Format-List</span><span class="sxs-lookup"><span data-stu-id="6b3d8-171">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)

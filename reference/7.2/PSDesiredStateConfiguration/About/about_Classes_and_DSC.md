---
description: クラスを使用して、Desired State Configuration (DSC) を使用して PowerShell で開発する方法について説明します。
Locale: en-US
ms.date: 01/11/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes_and_DSC
ms.openlocfilehash: a5819ac54f34393e0fbbf3b8933e840730c5d827
ms.sourcegitcommit: cc72c40315fd2981d3009b335accbfa52d57640c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "99600088"
---
# <a name="about-classes-and-desired-state-configuration"></a><span data-ttu-id="ed07e-103">クラスと Desired State Configuration について</span><span class="sxs-lookup"><span data-stu-id="ed07e-103">About Classes and Desired State Configuration</span></span>

## <a name="short-description"></a><span data-ttu-id="ed07e-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="ed07e-104">Short description</span></span>

<span data-ttu-id="ed07e-105">クラスを使用して、Desired State Configuration (DSC) を使用して PowerShell で開発する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-105">Describes how you can use classes to develop in PowerShell with Desired State Configuration (DSC).</span></span>

## <a name="long-description"></a><span data-ttu-id="ed07e-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="ed07e-106">Long description</span></span>

<span data-ttu-id="ed07e-107">Windows PowerShell 5.0 以降では、他のオブジェクト指向プログラミング言語に似た正式な構文とセマンティクスを使用して、クラスやその他のユーザー定義型を定義するための言語が追加されました。</span><span class="sxs-lookup"><span data-stu-id="ed07e-107">Starting in Windows PowerShell 5.0, language was added to define classes and other user-defined types, by using formal syntax and semantics that are similar to other object-oriented programming languages.</span></span> <span data-ttu-id="ed07e-108">目標は、開発者や IT プロフェッショナルがさまざまなユースケースで PowerShell を採用できるようにし、DSC リソースなどの PowerShell アーティファクトの開発を簡素化し、管理面の範囲を短縮できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-108">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts such as DSC resources, and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="ed07e-109">サポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="ed07e-109">Supported scenarios</span></span>

<span data-ttu-id="ed07e-110">次のシナリオがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-110">The following scenarios are supported:</span></span>

- <span data-ttu-id="ed07e-111">PowerShell 言語を使用して、DSC リソースとそれに関連付けられている型を定義します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-111">Define DSC resources and their associated types by using the PowerShell language.</span></span>
- <span data-ttu-id="ed07e-112">クラス、プロパティ、メソッド、継承などの使い慣れたオブジェクト指向プログラミング構造を使用して、PowerShell でカスタム型を定義します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-112">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, and inheritance.</span></span>
- <span data-ttu-id="ed07e-113">PowerShell 言語を使用して型をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="ed07e-113">Debug types by using the PowerShell language.</span></span>
- <span data-ttu-id="ed07e-114">正式なメカニズムと適切なレベルを使用して、例外を生成して処理します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-114">Generate and handle exceptions by using formal mechanisms, and at the right level.</span></span>

## <a name="define-dsc-resources-with-classes"></a><span data-ttu-id="ed07e-115">クラスを使用して DSC リソースを定義する</span><span class="sxs-lookup"><span data-stu-id="ed07e-115">Define DSC resources with classes</span></span>

<span data-ttu-id="ed07e-116">構文の変更とは別に、クラス定義の DSC リソースとコマンドレット DSC リソースプロバイダーの主な違いは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-116">Apart from syntax changes, the major differences between a class-defined DSC resource and a cmdlet DSC resource provider are the following items:</span></span>

- <span data-ttu-id="ed07e-117">管理オブジェクトフォーマット (MOF) ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ed07e-117">A Management Object Format (MOF) file is not required.</span></span>
- <span data-ttu-id="ed07e-118">モジュール フォルダーの DSCResource サブフォルダーは不要です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-118">A DSCResource subfolder in the module folder is not required.</span></span>
- <span data-ttu-id="ed07e-119">PowerShell モジュールのファイルには、複数の DSC リソース クラスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-119">A PowerShell module file can contain multiple DSC resource classes.</span></span>

## <a name="create-a-class-defined-dsc-resource-provider"></a><span data-ttu-id="ed07e-120">クラス定義の DSC リソースプロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="ed07e-120">Create a class-defined DSC resource provider</span></span>

<span data-ttu-id="ed07e-121">次の例は、Mydscresource.psd1 というモジュールとして保存されているクラス定義の DSC リソースプロバイダーです。 hbase-runner.psm1 です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-121">The following example is a class-defined DSC resource provider that is saved as a module, MyDSCResource.psm1.</span></span> <span data-ttu-id="ed07e-122">常に、クラス定義の DSC リソースプロバイダーにキープロパティを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed07e-122">You must always include a key property in a class-defined DSC resource provider.</span></span>

```powershell
enum Ensure
{
    Absent
    Present
}

<#
    This resource manages the file in a specific path.
    [DscResource()] indicates the class is a DSC resource
#>

[DscResource()]
class FileResource
{
    <#
        This property is the fully qualified path to the file that is
        expected to be present or absent.

        The [DscProperty(Key)] attribute indicates the property is a
        key and its value uniquely identifies a resource instance.
        Defining this attribute also means the property is required
        and DSC will ensure a value is set before calling the resource.

        A DSC resource must define at least one key property.
    #>
    [DscProperty(Key)]
    [string]$Path

    <#
        This property indicates if the settings should be present or absent
        on the system. For present, the resource ensures the file pointed
        to by $Path exists. For absent, it ensures the file point to by
        $Path does not exist.

        The [DscProperty(Mandatory)] attribute indicates the property is
        required and DSC will guarantee it is set.

        If Mandatory is not specified or if it is defined as
        Mandatory=$false, the value is not guaranteed to be set when DSC
        calls the resource.  This is appropriate for optional properties.
    #>
    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    <#
        This property defines the fully qualified path to a file that will
        be placed on the system if $Ensure = Present and $Path does not
        exist.

        NOTE: This property is required because [DscProperty(Mandatory)] is
        set.
    #>
    [DscProperty(Mandatory)]
    [string] $SourcePath

    <#
        This property reports the file's create timestamp.

        [DscProperty(NotConfigurable)] attribute indicates the property is
        not configurable in DSC configuration.  Properties marked this way
        are populated by the Get() method to report additional details
        about the resource when it is present.

    #>
    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime

    <#
        This method is equivalent of the Set-TargetResource script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#

        This method is equivalent of the Test-TargetResource script
        function. It should return True or False, showing whether the
        resource is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
{
            return -not $present
        }
    }

    <#
        This method is equivalent of the Get-TargetResource script function.
        The implementation should use the keys to find appropriate
        resources. This method returns an instance of this class with the
        updated key properties.
    #>
    [FileResource] Get()
    {
        $present = $this.TestFilePath($this.Path)

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }
        return $this
    }

    <#
        Helper method to check if the file exists and it is correct file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ea Ignore
        if ($null -eq $item)
        {
            $present = $false
        }
        elseif( $item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif($item.PSIsContainer)
        {
            throw "Path $($location) is a directory path."
        }
        return $present
    }

    <#
        Helper method to copy file from source to path
    #>
    [void] CopyFile()
    {
        if(-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo]
        $destFileInfo = new-object System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            $FullName = $destFileInfo.Directory.FullName
            $Message = "Creating directory $FullName"

            Write-Verbose -Message $Message

            #use CreateDirectory instead of New-Item to avoid code
            # to handle the non-terminating error
            [System.IO.Directory]::CreateDirectory($FullName)
        }

        if(Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $this.SourcePath to $this.Path"

        #DSC engine catches and reports any error that occurs
        Copy-Item -Path $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <a name="create-a-module-manifest"></a><span data-ttu-id="ed07e-123">モジュールマニフェストを作成する</span><span class="sxs-lookup"><span data-stu-id="ed07e-123">Create a module manifest</span></span>

<span data-ttu-id="ed07e-124">クラス定義の DSC リソース プロバイダーを作成し、モジュールとして保存すると、モジュールのモジュール マニフェストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-124">After creating the class-defined DSC resource provider, and saving it as a module, create a module manifest for the module.</span></span> <span data-ttu-id="ed07e-125">クラスベースのリソースを DSC エンジンで使用できるようにするには、マニフェスト ファイルに、リソースをエクスポートするようにモジュールに指示する `DscResourcesToExport` ステートメントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed07e-125">To make a class-based resource available to the DSC engine, you must include a `DscResourcesToExport` statement in the manifest file that instructs the module to export the resource.</span></span> <span data-ttu-id="ed07e-126">この例では、次のモジュール マニフェストは MyDscResource.psd1 として保存されます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-126">In this example, the following module manifest is saved as MyDscResource.psd1.</span></span>

```powershell
@{

# Script module or binary module file associated with this manifest.
RootModule = 'MyDscResource.psm1'

DscResourcesToExport = 'FileResource'

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '81624038-5e71-40f8-8905-b1a87afe22d7'

# Author of this module
Author = 'Microsoft Corporation'

# Company or vendor of this module
CompanyName = 'Microsoft Corporation'

# Copyright statement for this module
Copyright = '(c) 2014 Microsoft. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
PowerShellVersion = '5.0'

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

}
```

## <a name="deploy-a-dsc-resource-provider"></a><span data-ttu-id="ed07e-127">DSC リソースプロバイダーをデプロイする</span><span class="sxs-lookup"><span data-stu-id="ed07e-127">Deploy a DSC resource provider</span></span>

<span data-ttu-id="ed07e-128">またはで Mydscresource.psd1 フォルダーを作成して、新しい DSC リソースプロバイダーをデプロイし `$pshome\Modules` `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-128">Deploy the new DSC resource provider by creating a MyDscResource folder in `$pshome\Modules` or `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="ed07e-129">DSCResource サブフォルダーを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed07e-129">You do not need to create a DSCResource subfolder.</span></span> <span data-ttu-id="ed07e-130">モジュールとモジュールのマニフェスト ファイル (MyDscResource.psm1 と MyDscResource.psd1) を MyDscResource フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ed07e-130">Copy the module and module manifest files (MyDscResource.psm1 and MyDscResource.psd1) to the MyDscResource folder.</span></span>

<span data-ttu-id="ed07e-131">これ以降、他の DSC リソースの場合と同様に、構成スクリプトを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-131">From this point, you create and run a configuration script as you would with any DSC resource.</span></span>

## <a name="create-a-dsc-configuration-script"></a><span data-ttu-id="ed07e-132">DSC 構成スクリプトを作成する</span><span class="sxs-lookup"><span data-stu-id="ed07e-132">Create a DSC configuration script</span></span>

<span data-ttu-id="ed07e-133">既に説明したように、クラスとマニフェスト ファイルをフォルダー構造で保存した後で、新しいリソースを使用する構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-133">After saving the class and manifest files in the folder structure as described earlier, you can create a configuration that uses the new resource.</span></span> <span data-ttu-id="ed07e-134">次の構成は、Mydscresource.psd1 モジュールを参照します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-134">The following configuration references the MyDSCResource module.</span></span> <span data-ttu-id="ed07e-135">構成をスクリプトとして保存し、MyResource.ps1 します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-135">Save the configuration as a script, MyResource.ps1.</span></span>

<span data-ttu-id="ed07e-136">DSC 構成を実行する方法の詳細については、「 [Windows PowerShell Desired State configuration の概要](/powershell/scripting/dsc/overview/dscforengineers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed07e-136">For information about how to run a DSC configuration, see [Windows PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/dscforengineers).</span></span>

<span data-ttu-id="ed07e-137">構成を実行する前に、を作成 `C:\test.txt` します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-137">Before you run the configuration, create `C:\test.txt`.</span></span> <span data-ttu-id="ed07e-138">構成では、ファイルがに存在するかどうかを確認し `c:\test\test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-138">The configuration checks if the file exists at `c:\test\test.txt`.</span></span> <span data-ttu-id="ed07e-139">ファイルが存在しない場合は、構成によってからファイルがコピーされ `C:\test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-139">If the file does not exist, the configuration copies the file from `C:\test.txt`.</span></span>

```powershell
Configuration Test
{
    Import-DSCResource -module MyDscResource
    FileResource file
    {
        Path = "C:\test\test.txt"
        SourcePath = "C:\test.txt"
        Ensure = "Present"
    }
}
Test
Start-DscConfiguration -Wait -Force Test
```

<span data-ttu-id="ed07e-140">このスクリプトは、DSC 構成スクリプトの場合と同様に実行します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-140">Run this script as you would any DSC configuration script.</span></span> <span data-ttu-id="ed07e-141">構成を開始するには、管理者特権の PowerShell コンソールで、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-141">To start the configuration, in an elevated PowerShell console, run the following:</span></span>

`PS C:\test> .\MyResource.ps1`

## <a name="inheritance-in-powershell-classes"></a><span data-ttu-id="ed07e-142">PowerShell クラスでの継承</span><span class="sxs-lookup"><span data-stu-id="ed07e-142">Inheritance in PowerShell classes</span></span>

### <a name="declare-base-classes-for-powershell-classes"></a><span data-ttu-id="ed07e-143">PowerShell クラスの基底クラスを宣言する</span><span class="sxs-lookup"><span data-stu-id="ed07e-143">Declare base classes for PowerShell classes</span></span>

<span data-ttu-id="ed07e-144">次の例に示すように、PowerShell クラスを別の PowerShell クラスの基本データ型として宣言できます。この例では、 **フルーツ** は **apple** の基本データ型です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-144">You can declare a PowerShell class as a base type for another PowerShell class, as shown in the following example, in which **fruit** is a base type for **apple**.</span></span>

```powershell
class fruit
{
    [int]sold() {return 100500}
}

class apple : fruit {}
    [apple]::new().sold() # return 100500
```

### <a name="declare-implemented-interfaces-for-powershell-classes"></a><span data-ttu-id="ed07e-145">PowerShell クラスの実装されたインターフェイスを宣言する</span><span class="sxs-lookup"><span data-stu-id="ed07e-145">Declare implemented interfaces for PowerShell classes</span></span>

<span data-ttu-id="ed07e-146">基本型が指定されていない場合は、基本型の後、またはコロン () の直後に、実装されたインターフェイスを宣言でき `:` ます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-146">You can declare implemented interfaces after base types, or immediately after a colon (`:`) if there is no base type specified.</span></span> <span data-ttu-id="ed07e-147">コンマを使用してすべての型名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="ed07e-147">Separate all type names by using commas.</span></span> <span data-ttu-id="ed07e-148">これは、C# の構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="ed07e-148">This is similar to C# syntax.</span></span>

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableTest : test, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

### <a name="call-base-class-constructors"></a><span data-ttu-id="ed07e-149">基底クラスのコンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="ed07e-149">Call base class constructors</span></span>

<span data-ttu-id="ed07e-150">サブクラスから基底クラスのコンストラクターを呼び出すには、 `base` 次の例に示すように、キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-150">To call a base class constructor from a subclass, add the `base` keyword, as shown in the following example:</span></span>

```powershell
class A {
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

<span data-ttu-id="ed07e-151">基底クラスに既定のコンストラクター (パラメーターなし) がある場合は、以下に示すように、明示的なコンストラクター呼び出しを省略できます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-151">If a base class has a default constructor (no parameters), you can omit an explicit constructor call, as shown.</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-methods"></a><span data-ttu-id="ed07e-152">基底クラスのメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="ed07e-152">Call base class methods</span></span>

<span data-ttu-id="ed07e-153">サブクラスで既存のメソッドをオーバーライドすることができます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-153">You can override existing methods in subclasses.</span></span> <span data-ttu-id="ed07e-154">オーバーライドを行うには、同じ名前とシグネチャを使用してメソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-154">To do the override, declare methods by using the same name and signature.</span></span>

```powershell
class baseClass
{
    [int]days() {return 100500}
}
class childClass1 : baseClass
{
    [int]days () {return 200600}
}

    [childClass1]::new().days() # return 200600
```

<span data-ttu-id="ed07e-155">オーバーライドされた実装から基本クラスメソッドを呼び出すには、呼び出し時に基本クラスにキャストし `([baseclass]$this)` ます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-155">To call base class methods from overridden implementations, cast to the base class `([baseclass]$this)` on invocation.</span></span>

```powershell
class childClass2 : baseClass
{
    [int]days()
    {
        return 3 * ([baseClass]$this).days()
    }
}

    [childClass2]::new().days() # return 301500
```

<span data-ttu-id="ed07e-156">すべての PowerShell メソッドは仮想です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-156">All PowerShell methods are virtual.</span></span> <span data-ttu-id="ed07e-157">オーバーライドの場合と同じ構文を使用して、サブクラスで非仮想 .NET メソッドを非表示にすることができます。同じ名前およびシグネチャを持つメソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-157">You can hide non-virtual .NET methods in a subclass by using the same syntax as you do for an override: declare methods with same name and signature.</span></span>

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

### <a name="current-limitations-with-class-inheritance"></a><span data-ttu-id="ed07e-158">クラス継承に関する現在の制限事項</span><span class="sxs-lookup"><span data-stu-id="ed07e-158">Current limitations with class inheritance</span></span>

<span data-ttu-id="ed07e-159">クラスの継承に関する制限は、PowerShell でインターフェイスを宣言する構文がないことです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-159">A limitation with class inheritance is that there is no syntax to declare interfaces in PowerShell.</span></span>

## <a name="defining-custom-types-in-powershell"></a><span data-ttu-id="ed07e-160">PowerShell でのカスタム型の定義</span><span class="sxs-lookup"><span data-stu-id="ed07e-160">Defining custom types in PowerShell</span></span>

<span data-ttu-id="ed07e-161">Windows PowerShell 5.0 では、いくつかの言語要素が導入されました。</span><span class="sxs-lookup"><span data-stu-id="ed07e-161">Windows PowerShell 5.0 introduced several language elements.</span></span>

### <a name="class-keyword"></a><span data-ttu-id="ed07e-162">class キーワード</span><span class="sxs-lookup"><span data-stu-id="ed07e-162">Class keyword</span></span>

<span data-ttu-id="ed07e-163">新しいクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-163">Defines a new class.</span></span>
<span data-ttu-id="ed07e-164">`class`キーワードは、true .NET Framework 型です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-164">The `class` keyword is a true .NET Framework type.</span></span>
<span data-ttu-id="ed07e-165">クラスメンバーはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-165">Class members are public.</span></span>

```powershell
class MyClass
{
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="ed07e-166">enum キーワードおよび列挙</span><span class="sxs-lookup"><span data-stu-id="ed07e-166">Enum keyword and enumerations</span></span>

<span data-ttu-id="ed07e-167">キーワードのサポートが `enum` 追加されましたが、互換性に影響する変更点です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-167">Support for the `enum` keyword was added and is a breaking change.</span></span> <span data-ttu-id="ed07e-168">`enum`現在、区切り記号は改行です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-168">The `enum` delimiter is currently a newline.</span></span> <span data-ttu-id="ed07e-169">既にを使用しているユーザーのための回避策 `enum` は、 `&` 単語の前にアンパサンド () を挿入することです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-169">A workaround for those who are already using `enum` is to insert an ampersand (`&`) before the word.</span></span> <span data-ttu-id="ed07e-170">現在の制限事項: 列挙子自体を使用して列挙子を定義することはできませんが、 `enum` 次の例に示すように、別の条件で初期化することができ `enum` ます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-170">Current limitations: you cannot define an enumerator in terms of itself, but you can initialize `enum` in terms of another `enum`, as shown in the following example:</span></span>

<span data-ttu-id="ed07e-171">現在、基本データ型を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed07e-171">The base type cannot currently be specified.</span></span> <span data-ttu-id="ed07e-172">基本型は常に [int] です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-172">The base type is always [int].</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="ed07e-173">列挙子の値は、解析時定数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed07e-173">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="ed07e-174">列挙子の値を、呼び出されたコマンドの結果に設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed07e-174">The enumerator value cannot be set to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="ed07e-175">`Enum` では、次の例に示すように算術演算がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ed07e-175">`Enum` supports arithmetic operations, as shown in the following example:</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="hidden-keyword"></a><span data-ttu-id="ed07e-176">Hidden キーワード</span><span class="sxs-lookup"><span data-stu-id="ed07e-176">Hidden keyword</span></span>

<span data-ttu-id="ed07e-177">`hidden`Windows PowerShell 5.0 で導入されたキーワードは、既定の結果からクラスメンバーを非表示にし `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-177">The `hidden` keyword, introduced in Windows PowerShell 5.0, hides class members from default `Get-Member` results.</span></span> <span data-ttu-id="ed07e-178">次の行に示すように、非表示のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-178">Specify the hidden property as shown in the following line:</span></span>

```powershell
hidden [type] $classmember = <value>
```

<span data-ttu-id="ed07e-179">非表示のメンバーは、非表示のメンバーを定義するクラスで完了が発生しない限り、タブ補完や IntelliSense を使用して表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="ed07e-179">Hidden members are not displayed by using tab completion or IntelliSense, unless the completion occurs in the class that defines the hidden member.</span></span>

<span data-ttu-id="ed07e-180">新しい属性 **system.management.automation.hiddenattribute** が追加され、C# コードが PowerShell 内で同じセマンティクスを持つことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ed07e-180">A new attribute, **System.Management.Automation.HiddenAttribute**, was added, so that C# code can have the same semantics within PowerShell.</span></span>

<span data-ttu-id="ed07e-181">詳細については、「 [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed07e-181">For more information, see [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).</span></span>

### <a name="import-dscresource"></a><span data-ttu-id="ed07e-182">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="ed07e-182">Import-DscResource</span></span>

<span data-ttu-id="ed07e-183">`Import-DscResource` は真の動的キーワードです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-183">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="ed07e-184">PowerShell では、DscResource 属性を含むクラスを探して、指定されたモジュールのルート モジュールを解析します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-184">PowerShell parses the specified module's root module, searching for classes that contain the DscResource attribute.</span></span>

### <a name="properties"></a><span data-ttu-id="ed07e-185">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ed07e-185">Properties</span></span>

<span data-ttu-id="ed07e-186">新しいフィールドが `ImplementingAssembly` に追加されました `ModuleInfo` 。</span><span class="sxs-lookup"><span data-stu-id="ed07e-186">A new field, `ImplementingAssembly`, was added to `ModuleInfo`.</span></span> <span data-ttu-id="ed07e-187">スクリプトでクラスが定義されている場合、またはバイナリモジュール用に読み込まれたアセンブリ `ImplementingAssembly` が、スクリプトモジュール用に作成された動的アセンブリに設定されている場合。</span><span class="sxs-lookup"><span data-stu-id="ed07e-187">If the script defines classes, or the loaded assembly for binary modules `ImplementingAssembly` is set to the dynamic assembly created for a script module.</span></span> <span data-ttu-id="ed07e-188">ModuleType = Manifest の場合は設定されません。</span><span class="sxs-lookup"><span data-stu-id="ed07e-188">It is not set when ModuleType = Manifest.</span></span>

<span data-ttu-id="ed07e-189">フィールドのリフレクション `ImplementingAssembly` では、モジュール内のリソースが検出されます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-189">Reflection on the `ImplementingAssembly` field discovers resources in a module.</span></span> <span data-ttu-id="ed07e-190">これは、PowerShell または他の管理言語で記述されたリソースを検出できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-190">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

<span data-ttu-id="ed07e-191">初期化子を持つフィールド。</span><span class="sxs-lookup"><span data-stu-id="ed07e-191">Fields with initializers.</span></span>

`[int] $i = 5`

<span data-ttu-id="ed07e-192">Static はサポートされており、型の制約と同様に属性のように動作するため、任意の順序で指定できます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-192">Static is supported and works like an attribute, similar to the type constraints, so it can be specified in any order.</span></span>

`static [int] $count = 0`

<span data-ttu-id="ed07e-193">型は省略できます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-193">A type is optional.</span></span>

`$s = "hello"`

<span data-ttu-id="ed07e-194">すべてのメンバーはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-194">All members are public.</span></span> <span data-ttu-id="ed07e-195">プロパティには、改行文字かセミコロンが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-195">Properties require either a newline or semicolon.</span></span> <span data-ttu-id="ed07e-196">オブジェクトの種類が指定されていない場合、プロパティの型は **object** です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-196">If no object type is specified, the property type is **Object**.</span></span>

### <a name="constructors-and-instantiation"></a><span data-ttu-id="ed07e-197">コンストラクターとインスタンス化</span><span class="sxs-lookup"><span data-stu-id="ed07e-197">Constructors and instantiation</span></span>

<span data-ttu-id="ed07e-198">PowerShell クラスは、クラスと同じ名前を持つコンストラクターを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-198">PowerShell classes can have constructors that have the same name as their class.</span></span> <span data-ttu-id="ed07e-199">コンストラクターはオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-199">Constructors can be overloaded.</span></span> <span data-ttu-id="ed07e-200">静的コンストラクターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ed07e-200">Static constructors are supported.</span></span>
<span data-ttu-id="ed07e-201">初期化式を持つプロパティは、コンストラクター内のコードを実行する前に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-201">Properties with initialization expressions are initialized before running any code in a constructor.</span></span> <span data-ttu-id="ed07e-202">静的プロパティは、静的コンストラクターの本体の前に初期化され、インスタンスのプロパティは、非静的コンストラクターの本体の前に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-202">Static properties are initialized before the body of a static constructor, and instance properties are initialized before the body of the non-static constructor.</span></span> <span data-ttu-id="ed07e-203">現在、C# 構文など、別のコンストラクターからコンストラクターを呼び出すための構文はありませ `": this()")` ん。</span><span class="sxs-lookup"><span data-stu-id="ed07e-203">Currently, there is no syntax for calling a constructor from another constructor such as the C# syntax: `": this()")`.</span></span> <span data-ttu-id="ed07e-204">対応策は、一般的な Init メソッドを定義することです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-204">The workaround is to define a common Init method.</span></span>

<span data-ttu-id="ed07e-205">クラスをインスタンス化する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-205">The following are ways of instantiating classes:</span></span>

- <span data-ttu-id="ed07e-206">既定のコンストラクターを使用したインスタンス化。</span><span class="sxs-lookup"><span data-stu-id="ed07e-206">Instantiating by using the default constructor.</span></span> <span data-ttu-id="ed07e-207">は、 `New-Object` このリリースではサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ed07e-207">Note that `New-Object` is not supported in this release.</span></span>

  `$a = [MyClass]::new()`

- <span data-ttu-id="ed07e-208">パラメーターを使用してコンストラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-208">Calling a constructor with a parameter.</span></span>

  `$b = [MyClass]::new(42)`

- <span data-ttu-id="ed07e-209">複数のパラメーターを持つコンストラクターに配列を渡す</span><span class="sxs-lookup"><span data-stu-id="ed07e-209">Passing an array to a constructor with multiple parameters</span></span>

  `$c = [MyClass]::new(@(42,43,44), "Hello")`

<span data-ttu-id="ed07e-210">このリリースでは、型名は構文的にのみ表示されます。つまり、クラスを定義するモジュールまたはスクリプトの外部では参照できません。</span><span class="sxs-lookup"><span data-stu-id="ed07e-210">For this release, the type name is only visible lexically, meaning it is not visible outside of the module or script that defines the class.</span></span> <span data-ttu-id="ed07e-211">関数は、PowerShell で定義されているクラスのインスタンスを返すことができ、インスタンスはモジュールまたはスクリプトの外部で正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-211">Functions can return instances of a class defined in PowerShell, and instances work well outside of the module or script.</span></span>

<span data-ttu-id="ed07e-212">`Get-Member`**静的** パラメーターはコンストラクターを一覧表示しているため、他のメソッドと同様にオーバーロードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-212">The `Get-Member` **Static** parameter lists constructors, so you can view overloads like any other method.</span></span> <span data-ttu-id="ed07e-213">また、この構文のパフォーマンスは、`New-Object` より大幅に高速です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-213">The performance of this syntax is also considerably faster than `New-Object`.</span></span>

<span data-ttu-id="ed07e-214">次の例に示すように、**new** という名前の擬似静的メソッドは .NET 型で機能します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-214">The pseudo-static method named **new** works with .NET types, as shown in the following example.</span></span> `[hashtable]::new()`

<span data-ttu-id="ed07e-215">`Get-Member` を使って、またはこの例で示すようにして、コンストラクターのオーバーロードを確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ed07e-215">You can now see constructor overloads with `Get-Member`, or as shown in this example:</span></span>

```powershell
[hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

### <a name="methods"></a><span data-ttu-id="ed07e-216">メソッド</span><span class="sxs-lookup"><span data-stu-id="ed07e-216">Methods</span></span>

<span data-ttu-id="ed07e-217">PowerShell のクラス メソッドは、end ブロックのみを持つ **ScriptBlock** として実装されます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-217">A PowerShell class method is implemented as a **ScriptBlock** that has only an end block.</span></span> <span data-ttu-id="ed07e-218">すべてのメソッドはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-218">All methods are public.</span></span> <span data-ttu-id="ed07e-219">**DoSomething** という名前のメソッドを定義する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-219">The following shows an example of defining a method named **DoSomething**.</span></span>

```powershell
class MyClass
{
    DoSomething($x)
    {
        $this._doSomething($x)       # method syntax
    }
    private _doSomething($a) {}
}
```

### <a name="method-invocation"></a><span data-ttu-id="ed07e-220">メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="ed07e-220">Method invocation</span></span>

<span data-ttu-id="ed07e-221">オーバーロードされたメソッドがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ed07e-221">Overloaded methods are supported.</span></span> <span data-ttu-id="ed07e-222">オーバーロードされたメソッドには、既存のメソッドと同じ名前が付けられますが、指定された値によって区別されます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-222">Overloaded methods are named the same as an existing method but differentiated by their specified values.</span></span>

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

### <a name="invocation"></a><span data-ttu-id="ed07e-223">呼び出し</span><span class="sxs-lookup"><span data-stu-id="ed07e-223">Invocation</span></span>

<span data-ttu-id="ed07e-224">「 [メソッドの呼び出し](#method-invocation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed07e-224">See [Method invocation](#method-invocation).</span></span>

### <a name="attributes"></a><span data-ttu-id="ed07e-225">属性</span><span class="sxs-lookup"><span data-stu-id="ed07e-225">Attributes</span></span>

<span data-ttu-id="ed07e-226">`DscResource`、 `DscResourceKey` 、およびという3つの新しい属性が追加されました `DscResourceMandatory` 。</span><span class="sxs-lookup"><span data-stu-id="ed07e-226">Three new attributes were added: `DscResource`, `DscResourceKey`, and `DscResourceMandatory`.</span></span>

### <a name="return-types"></a><span data-ttu-id="ed07e-227">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="ed07e-227">Return types</span></span>

<span data-ttu-id="ed07e-228">戻り値の型はコントラクトです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-228">Return type is a contract.</span></span> <span data-ttu-id="ed07e-229">戻り値は、予期された型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ed07e-229">The return value is converted to the expected type.</span></span>
<span data-ttu-id="ed07e-230">戻り値の型が指定されていない場合、戻り値の型は void です。</span><span class="sxs-lookup"><span data-stu-id="ed07e-230">If no return type is specified, the return type is void.</span></span> <span data-ttu-id="ed07e-231">オブジェクトのストリーミングはありません。オブジェクトは意図的にも誤ってもパイプラインに書き込むことができません。</span><span class="sxs-lookup"><span data-stu-id="ed07e-231">There is no streaming of objects and objects cannot be written to the pipeline either intentionally or by accident.</span></span>

### <a name="lexical-scoping-of-variables"></a><span data-ttu-id="ed07e-232">変数の語彙的スコープ</span><span class="sxs-lookup"><span data-stu-id="ed07e-232">Lexical scoping of variables</span></span>

<span data-ttu-id="ed07e-233">今回のリリースで語彙的スコープが機能する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-233">The following shows an example of how lexical scoping works in this release.</span></span>

```powershell
$d = 42  # Script scope

function bar
{
    $d = 0  # Function scope
    [MyClass]::DoSomething()
}

class MyClass
{
    static [object] DoSomething()
    {
        return $d  # error, not found dynamically
        return $script:d # no error

        $d = $script:d
        return $d # no error, found lexically
    }
}

$v = bar
$v -eq $d # true
```

## <a name="example-create-custom-classes"></a><span data-ttu-id="ed07e-234">例: カスタムクラスの作成</span><span class="sxs-lookup"><span data-stu-id="ed07e-234">Example: Create custom classes</span></span>

<span data-ttu-id="ed07e-235">次の例では、HTML 動的スタイルシート言語 (DSL) を実装するために、いくつかの新しいカスタムクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed07e-235">The following example creates several new, custom classes to implement an HTML Dynamic Stylesheet Language (DSL).</span></span> <span data-ttu-id="ed07e-236">この例では、要素クラスの一部として特定の要素型を作成するヘルパー関数を追加します。これは、モジュールのスコープ外では型を使用できないためです。</span><span class="sxs-lookup"><span data-stu-id="ed07e-236">The example adds helper functions to create specific element types as part of the element class, such as heading styles and tables, because types cannot be used outside the scope of a module.</span></span>

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
        $text += $Head
        $text += "`n</head>`n<body>`n"
        $text += $Body -join "`n" # Render all of the body elements
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
    [string] Render() { return "<title>$Title</title>" }
    [string] ToString() { return $this.Render() }
}

class Element
{
    [string] $Tag
    [string] $Text
    [hashtable] $Attributes
    [string] Render() {
        $attributesText= ""
        if ($Attributes)
        {
            foreach ($attr in $Attributes.Keys)
            {
                $attributesText = " $attr=`"$($Attributes[$attr])`""
            }
        }

        return "<${tag}${attributesText}>$text</$tag>`n"
    }
    [string] ToString() { return $this.Render() }
}

#
# Helper functions for creating specific element types on top of the classes.
# These are required because types aren't visible outside of the module.
#
function H1 {[Element] @{Tag = "H1"; Text = $args.foreach{$_} -join " "}}
function H2 {[Element] @{Tag = "H2"; Text = $args.foreach{$_} -join " "}}
function H3 {[Element] @{Tag = "H3"; Text = $args.foreach{$_} -join " "}}
function P  {[Element] @{Tag = "P" ; Text = $args.foreach{$_} -join " "}}
function B  {[Element] @{Tag = "B" ; Text = $args.foreach{$_} -join " "}}
function I  {[Element] @{Tag = "I" ; Text = $args.foreach{$_} -join " "}}
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
    $bodyText +=  $Properties.foreach{TH $_}
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
function TH  {([Element] @{Tag="TH"; Text=$args.foreach{$_} -join " "})}
function TR  {([Element] @{Tag="TR"; Text=$args.foreach{$_} -join " "})}
function TD  {([Element] @{Tag="TD"; Text=$args.foreach{$_} -join " "})}

function Style
{
    return  [Element]  @{
        Tag = "style"
        Text = "$args"
    }
}

# Takes a hash table, casts it to and HTML document
# and then returns the resulting type.
#
function Html ([HTML] $doc) { return $doc }
```

## <a name="see-also"></a><span data-ttu-id="ed07e-237">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed07e-237">See also</span></span>

[<span data-ttu-id="ed07e-238">about_Enum</span><span class="sxs-lookup"><span data-stu-id="ed07e-238">about_Enum</span></span>](../../Microsoft.PowerShell.Core/About/about_Enum.md)

[<span data-ttu-id="ed07e-239">about_Hidden</span><span class="sxs-lookup"><span data-stu-id="ed07e-239">about_Hidden</span></span>](../../Microsoft.PowerShell.Core/About/about_hidden.md)

[<span data-ttu-id="ed07e-240">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="ed07e-240">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="ed07e-241">about_Methods</span><span class="sxs-lookup"><span data-stu-id="ed07e-241">about_Methods</span></span>](../../Microsoft.PowerShell.Core/About/about_Methods.md)

[<span data-ttu-id="ed07e-242">カスタム PowerShell Desired State Configuration リソースのビルド</span><span class="sxs-lookup"><span data-stu-id="ed07e-242">Build Custom PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/authoringResource)


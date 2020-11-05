---
ms.date: 07/08/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell クラスを使用したカスタム DSC リソースの記述
description: この記事では、指定されたパス内のファイルを管理する単純なリソースを作成する方法について説明します。
ms.openlocfilehash: 72a828795c29e10ff66f164b8871b0fea7a1e0a8
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667319"
---
# <a name="writing-a-custom-dsc-resource-with-powershell-classes"></a><span data-ttu-id="5b0b7-104">PowerShell クラスを使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="5b0b7-104">Writing a custom DSC resource with PowerShell classes</span></span>

> <span data-ttu-id="5b0b7-105">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="5b0b7-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="5b0b7-106">Windows PowerShell 5.0 の PowerShell クラスの導入により、クラスを作成して DSC リソースを定義できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-106">With the introduction of PowerShell classes in Windows PowerShell 5.0, you can now define a DSC resource by creating a class.</span></span> <span data-ttu-id="5b0b7-107">クラスでは、スキーマとリソースの実装の両方を定義するため、MOF ファイルを別途作成する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-107">The class defines both the schema and the implementation of the resource, so there is no need to create a separate MOF file.</span></span> <span data-ttu-id="5b0b7-108">**DSCResources** フォルダーが必要ないため、クラスベースのリソースのフォルダー構造は単純になりました。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-108">The folder structure for a class-based resource is also simpler, because a **DSCResources** folder is not necessary.</span></span>

<span data-ttu-id="5b0b7-109">クラスベースの DSC リソースでは、スキーマは、プロパティの型を指定する属性で変更できるクラスのプロパティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-109">In a class-based DSC resource, the schema is defined as properties of the class which can be modified with attributes to specify the property type..</span></span> <span data-ttu-id="5b0b7-110">リソースは、`Get()` 、`Set()` 、および `Test()` メソッド (スクリプト リソースの `Get-TargetResource`、`Set-TargetResource`、および `Test-TargetResource` 関数に相当します) によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-110">The resource is implemented by `Get()`, `Set()`, and `Test()` methods (equivalent to the `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions in a script resource.</span></span>

<span data-ttu-id="5b0b7-111">この記事では、指定されたパス内のファイルを管理する **FileResource** という名前の単純なリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-111">In this article, we will create a simple resource named **FileResource** that manages a file in a specified path.</span></span>

<span data-ttu-id="5b0b7-112">DSC リソースの詳細については、「[カスタム Windows PowerShell Desired State Configuration のビルド](authoringResource.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-112">For more information about DSC resources, see [Build Custom Windows PowerShell Desired State Configuration Resources](authoringResource.md)</span></span>

> [!Note]
> <span data-ttu-id="5b0b7-113">クラスベースのリソースでは、汎用コレクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-113">Generic collections are not supported in class-based resources.</span></span>

## <a name="folder-structure-for-a-class-resource"></a><span data-ttu-id="5b0b7-114">クラス リソースのフォルダー構造</span><span class="sxs-lookup"><span data-stu-id="5b0b7-114">Folder structure for a class resource</span></span>

<span data-ttu-id="5b0b7-115">PowerShell クラスを使用して DSC カスタム リソースを実装するには、次のフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-115">To implement a DSC custom resource with a PowerShell class, create the following folder structure.</span></span>
<span data-ttu-id="5b0b7-116">クラスは `MyDscResource.psm1` で定義し、モジュール マニフェストは `MyDscResource.psd1` で定義します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-116">The class is defined in `MyDscResource.psm1` and the module manifest is defined in `MyDscResource.psd1`.</span></span>

```
$env:ProgramFiles\WindowsPowerShell\Modules (folder)
    |- MyDscResource (folder)
        MyDscResource.psm1
        MyDscResource.psd1
```

## <a name="create-the-class"></a><span data-ttu-id="5b0b7-117">クラスの作成</span><span class="sxs-lookup"><span data-stu-id="5b0b7-117">Create the class</span></span>

<span data-ttu-id="5b0b7-118">PowerShell クラスを作成するには、class キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-118">You use the class keyword to create a PowerShell class.</span></span> <span data-ttu-id="5b0b7-119">クラスを DSC リソースとして指定するには、`DscResource()` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-119">To specify that a class is a DSC resource, use the `DscResource()` attribute.</span></span> <span data-ttu-id="5b0b7-120">クラスの名前は、DSC リソースの名前です。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-120">The name of the class is the name of the DSC resource.</span></span>

```powershell
[DscResource()]
class FileResource {
}
```

### <a name="declare-properties"></a><span data-ttu-id="5b0b7-121">プロパティの宣言</span><span class="sxs-lookup"><span data-stu-id="5b0b7-121">Declare properties</span></span>

<span data-ttu-id="5b0b7-122">DSC リソースのスキーマは、クラスのプロパティとして定義します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-122">The DSC resource schema is defined as properties of the class.</span></span> <span data-ttu-id="5b0b7-123">3 つのプロパティを次のように宣言します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-123">We declare three properties as follows.</span></span>

```powershell
[DscProperty(Key)]
[string]$Path

[DscProperty(Mandatory)]
[Ensure] $Ensure

[DscProperty(Mandatory)]
[string] $SourcePath

[DscProperty(NotConfigurable)]
[Nullable[datetime]] $CreationTime
```

<span data-ttu-id="5b0b7-124">属性によってプロパティが変更されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-124">Notice that the properties are modified by attributes.</span></span> <span data-ttu-id="5b0b7-125">属性の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-125">The meaning of the attributes is as follows:</span></span>

- <span data-ttu-id="5b0b7-126">**DscProperty(Key)** :このプロパティは必須です。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-126">**DscProperty(Key)** : The property is required.</span></span> <span data-ttu-id="5b0b7-127">プロパティはキーです。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-127">The property is a key.</span></span> <span data-ttu-id="5b0b7-128">キーとしてマークされたすべてのプロパティの値を組み合わせて、構成内のリソース インスタンスを一意に識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-128">The values of all properties marked as keys must combine to uniquely identify a resource instance within a configuration.</span></span>
- <span data-ttu-id="5b0b7-129">**DscProperty(Mandatory)** :このプロパティは必須です。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-129">**DscProperty(Mandatory)** : The property is required.</span></span>
- <span data-ttu-id="5b0b7-130">**DscProperty(NotConfigurable)** :このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-130">**DscProperty(NotConfigurable)** : The property is read-only.</span></span> <span data-ttu-id="5b0b7-131">この属性でマークされたプロパティは、構成で設定できませんが、`Get()` メソッド (存在する場合) によって設定されます。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-131">Properties marked with this attribute cannot be set by a configuration, but are populated by the `Get()` method when present.</span></span>
- <span data-ttu-id="5b0b7-132">**DscProperty()** :このプロパティは構成可能ですが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-132">**DscProperty()** : The property is configurable, but it is not required.</span></span>

<span data-ttu-id="5b0b7-133">`$Path` プロパティと `$SourcePath` プロパティは、両方とも文字列です。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-133">The `$Path` and `$SourcePath` properties are both strings.</span></span> <span data-ttu-id="5b0b7-134">`$CreationTime` は、[DateTime](/dotnet/api/system.datetime) プロパティです。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-134">The `$CreationTime` is a [DateTime](/dotnet/api/system.datetime) property.</span></span> <span data-ttu-id="5b0b7-135">`$Ensure` プロパティは、次のように定義された列挙型です。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-135">The `$Ensure` property is an enumeration type, defined as follows.</span></span>

```powershell
enum Ensure
{
    Absent
    Present
}
```

### <a name="implementing-the-methods"></a><span data-ttu-id="5b0b7-136">メソッドの実装</span><span class="sxs-lookup"><span data-stu-id="5b0b7-136">Implementing the methods</span></span>

<span data-ttu-id="5b0b7-137">`Get()` 、`Set()` 、および `Test()` メソッドは、スクリプト リソースの `Get-TargetResource`、`Set-TargetResource`、および `Test-TargetResource` 関数に似ています。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-137">The `Get()`, `Set()`, and `Test()` methods are analogous to the `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions in a script resource.</span></span>

<span data-ttu-id="5b0b7-138">このコードには、ファイルを `$SourcePath` から `$Path` にコピーするヘルパー関数である `CopyFile()` 関数も含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-138">This code also includes the `CopyFile()` function, a helper function that copies the file from `$SourcePath` to `$Path`.</span></span>

```powershell
    <#
        This method is equivalent of the Set-TargetResource script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)

        if ($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#
        This method is equivalent of the Test-TargetResource script function.
        It should return True or False, showing whether the resource
        is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if ($this.Ensure -eq [Ensure]::Present)
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
        The implementation should use the keys to find appropriate resources.
        This method returns an instance of this class with the updated key
         properties.
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
        Helper method to check if the file exists and it is file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ErrorAction Ignore

        if ($item -eq $null)
        {
            $present = $false
        }
        elseif ($item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif ($item.PSIsContainer)
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
        if (-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo] $destFileInfo = New-Object -TypeName System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            Write-Verbose -Message "Creating directory $($destFileInfo.Directory.FullName)"

            <#
                Use CreateDirectory instead of New-Item to avoid code
                to handle the non-terminating error
            #>
            [System.IO.Directory]::CreateDirectory($destFileInfo.Directory.FullName)
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $($this.SourcePath) to $($this.Path)"

        # DSC engine catches and reports any error that occurs
        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
```

### <a name="the-complete-file"></a><span data-ttu-id="5b0b7-139">完全なファイル</span><span class="sxs-lookup"><span data-stu-id="5b0b7-139">The complete file</span></span>

<span data-ttu-id="5b0b7-140">完全なクラス ファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-140">The complete class file follows.</span></span>

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
        if ($this.ensure -eq [Ensure]::Present)
        {
            if (-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#
        This method is equivalent of the Test-TargetResource script function.
        It should return True or False, showing whether the resource
        is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if ($this.Ensure -eq [Ensure]::Present)
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
        The implementation should use the keys to find appropriate resources.
        This method returns an instance of this class with the updated key
         properties.
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
        Helper method to check if the file exists and it is file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ea Ignore
        if ($item -eq $null)
        {
            $present = $false
        }
        elseif ($item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif ($item.PSIsContainer)
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
        if (-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo] $destFileInfo = new-object System.IO.FileInfo($this.Path)
        if (-not $destFileInfo.Directory.Exists)
        {
            Write-Verbose -Message "Creating directory $($destFileInfo.Directory.FullName)"

            <#
                Use CreateDirectory instead of New-Item to avoid code
                 to handle the non-terminating error
            #>
            [System.IO.Directory]::CreateDirectory($destFileInfo.Directory.FullName)
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $($this.SourcePath) to $($this.Path)"

        # DSC engine catches and reports any error that occurs
        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
} # This module defines a class for a DSC "FileResource" provider.
```

## <a name="create-a-manifest"></a><span data-ttu-id="5b0b7-141">マニフェストの作成</span><span class="sxs-lookup"><span data-stu-id="5b0b7-141">Create a manifest</span></span>

<span data-ttu-id="5b0b7-142">クラスベースのリソースを DSC エンジンで使用できるようにするには、マニフェスト ファイルに、リソースをエクスポートするようにモジュールに指示する `DscResourcesToExport` ステートメントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-142">To make a class-based resource available to the DSC engine, you must include a `DscResourcesToExport` statement in the manifest file that instructs the module to export the resource.</span></span> <span data-ttu-id="5b0b7-143">この例では、マニフェストは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-143">Our manifest looks like this:</span></span>

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

# Minimum version of the Windows PowerShell engine required by this module
PowerShellVersion = '5.0'

# Name of the Windows PowerShell host required by this module
# PowerShellHostName = ''
}
```

## <a name="test-the-resource"></a><span data-ttu-id="5b0b7-144">リソースのテスト</span><span class="sxs-lookup"><span data-stu-id="5b0b7-144">Test the resource</span></span>

<span data-ttu-id="5b0b7-145">既に説明したように、クラスとマニフェスト ファイルをフォルダー構造で保存した後で、新しいリソースを使用する構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-145">After saving the class and manifest files in the folder structure as described earlier, you can create a configuration that uses the new resource.</span></span> <span data-ttu-id="5b0b7-146">DSC 構成を実行する方法については、「[構成の適用](../pull-server/enactingConfigurations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-146">For information about how to run a DSC configuration, see [Enacting configurations](../pull-server/enactingConfigurations.md).</span></span> <span data-ttu-id="5b0b7-147">次の構成では、`c:\test\test.txt` のファイルが存在するかどうかを確認し、存在しない場合は、ファイルを `c:\test.txt` からコピーします (構成を実行する前に `c:\test.txt` を作成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-147">The following configuration will check to see whether the file at `c:\test\test.txt` exists, and, if not, copies the file from `c:\test.txt` (you should create `c:\test.txt` before you run the configuration).</span></span>

```powershell
Configuration Test
{
    Import-DSCResource -module MyDscResource
    FileResource file
    {
        Path = "C:\test\test.txt"
        SourcePath = "c:\test.txt"
        Ensure = "Present"
    }
}
Test
Start-DscConfiguration -Wait -Force Test
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="5b0b7-148">PsDscRunAsCredential のサポート</span><span class="sxs-lookup"><span data-stu-id="5b0b7-148">Supporting PsDscRunAsCredential</span></span>

> <span data-ttu-id="5b0b7-149">[注] **PsDscRunAsCredential** は、PowerShell 5.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-149">[Note] **PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="5b0b7-150">**PsDscRunAsCredential** プロパティを [DSC 構成](../configurations/configurations.md)リソース ブロックで使用して、指定した資格情報のもとでリソースを実行する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-150">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span> <span data-ttu-id="5b0b7-151">詳細については、「[ユーザーの資格情報を指定して DSC を実行する](../configurations/runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-151">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

### <a name="require-or-disallow-psdscrunascredential-for-your-resource"></a><span data-ttu-id="5b0b7-152">使用するリソースに対する PsDscRunAsCredential の要求または却下</span><span class="sxs-lookup"><span data-stu-id="5b0b7-152">Require or disallow PsDscRunAsCredential for your resource</span></span>

<span data-ttu-id="5b0b7-153">`DscResource()` 属性でオプションのパラメーター **RunAsCredential** を指定します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-153">The `DscResource()` attribute takes an optional parameter **RunAsCredential**.</span></span> <span data-ttu-id="5b0b7-154">このパラメーターには以下の 3 つの値のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-154">This parameter takes one of three values:</span></span>

- <span data-ttu-id="5b0b7-155">`Optional` **PsDscRunAsCredential** は、このリソースを呼び出す構成ではオプションです。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-155">`Optional` **PsDscRunAsCredential** is optional for configurations that call this resource.</span></span> <span data-ttu-id="5b0b7-156">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-156">This is the default value.</span></span>
- <span data-ttu-id="5b0b7-157">`Mandatory` **PsDscRunAsCredential** は、このリソースを呼び出す構成で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-157">`Mandatory` **PsDscRunAsCredential** must be used for any configuration that calls this resource.</span></span>
- <span data-ttu-id="5b0b7-158">`NotSupported`このリソースを呼び出す構成には **PsDscRunAsCredential** を使用できません。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-158">`NotSupported` Configurations that call this resource cannot use **PsDscRunAsCredential**.</span></span>
- <span data-ttu-id="5b0b7-159">`Default``Optional` と同じです。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-159">`Default` Same as `Optional`.</span></span>

<span data-ttu-id="5b0b7-160">たとえば、次の属性を使用して、ご使用のカスタム リソースが **PsDscRunAsCredential** の使用をサポートしないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-160">For example, use the following attribute to specify that your custom resource does not support using **PsDscRunAsCredential** :</span></span>

```powershell
[DscResource(RunAsCredential=NotSupported)]
class FileResource {
}
```

### <a name="declaring-multiple-class-resources-in-a-module"></a><span data-ttu-id="5b0b7-161">1 つのモジュールで複数のクラス リソースを宣言する</span><span class="sxs-lookup"><span data-stu-id="5b0b7-161">Declaring multiple class resources in a module</span></span>

<span data-ttu-id="5b0b7-162">1 つのモジュールで複数のクラスベースの DSC リソースを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-162">A module can define multiple class based DSC resources.</span></span> <span data-ttu-id="5b0b7-163">次の方法でフォルダー構造を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-163">You can create the folder structure in the following ways:</span></span>

1. <span data-ttu-id="5b0b7-164">`<ModuleName>.psm1` ファイルに最初のリソースを定義し、以降のリソースは **DSCResources** フォルダー以下に定義します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-164">Define the first resource in the `<ModuleName>.psm1` file and subsequent resources under the **DSCResources** folder.</span></span>

   ```
   $env:ProgramFiles\WindowsPowerShell\Modules (folder)
        |- MyDscResource (folder)
           |- MyDscResource.psm1
              MyDscResource.psd1
        |- DSCResources
           |- SecondResource.psm1
   ```

1. <span data-ttu-id="5b0b7-165">すべてのリソースは、 **DSCResources** フォルダー以下で定義します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-165">Define all resources under the **DSCResources** folder.</span></span>

   ```
   $env:ProgramFiles\WindowsPowerShell\Modules (folder)
        |- MyDscResource (folder)
           |- MyDscResource.psm1
              MyDscResource.psd1
        |- DSCResources
           |- FirstResource.psm1
              SecondResource.psm1
   ```

> [!NOTE]
> <span data-ttu-id="5b0b7-166">上記の例で、 **DSCResource** 以下の PSM1 ファイルを PSD1 ファイルの **NestedModules** キーに追加します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-166">In the examples above, add any PSM1 files under the **DSCResources** to the **NestedModules** key in your PSD1 file.</span></span>

### <a name="access-the-user-context"></a><span data-ttu-id="5b0b7-167">ユーザー コンテキストへのアクセス</span><span class="sxs-lookup"><span data-stu-id="5b0b7-167">Access the user context</span></span>

<span data-ttu-id="5b0b7-168">カスタム リソース内からユーザー コンテキストにアクセスするには、自動変数 `$global:PsDscContext` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-168">To access the user context from within a custom resource, you can use the automatic variable `$global:PsDscContext`.</span></span>

<span data-ttu-id="5b0b7-169">たとえば、次のコードは、リソースが詳細出力ストリームに実行しているユーザー コンテキストを記述します。</span><span class="sxs-lookup"><span data-stu-id="5b0b7-169">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if (PsDscContext.RunAsUser) {
    Write-Verbose "User: $global:PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a><span data-ttu-id="5b0b7-170">参照</span><span class="sxs-lookup"><span data-stu-id="5b0b7-170">See Also</span></span>

[<span data-ttu-id="5b0b7-171">Build Custom Windows PowerShell Desired State Configuration Resources (カスタム Windows PowerShell Desired State Configuration のビルド)</span><span class="sxs-lookup"><span data-stu-id="5b0b7-171">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>](authoringResource.md)

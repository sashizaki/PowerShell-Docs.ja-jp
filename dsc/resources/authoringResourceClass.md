---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell クラスを使用したカスタム DSC リソースの記述
ms.openlocfilehash: 0759685b04688f574d72b62a15833832ad19e816
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402870"
---
# <a name="writing-a-custom-dsc-resource-with-powershell-classes"></a><span data-ttu-id="c5c3a-103">PowerShell クラスを使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="c5c3a-103">Writing a custom DSC resource with PowerShell classes</span></span>

> <span data-ttu-id="c5c3a-104">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="c5c3a-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="c5c3a-105">Windows PowerShell 5.0 の PowerShell クラスの導入により、クラスを作成して DSC リソースを定義できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-105">With the introduction of PowerShell classes in Windows PowerShell 5.0, you can now define a DSC resource by creating a class.</span></span> <span data-ttu-id="c5c3a-106">クラスでは、スキーマとリソースの実装の両方を定義するため、MOF ファイルを別途作成する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-106">The class defines both the schema and the implementation of the resource, so there is no need to create a separate MOF file.</span></span> <span data-ttu-id="c5c3a-107">**DSCResources** フォルダーが必要ないため、クラスベースのリソースのフォルダー構造は単純になりました。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-107">The folder structure for a class-based resource is also simpler, because a **DSCResources** folder is not necessary.</span></span>

<span data-ttu-id="c5c3a-108">クラスベースの DSC リソースでは、スキーマは、プロパティの型を指定する属性で変更できるクラスのプロパティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-108">In a class-based DSC resource, the schema is defined as properties of the class which can be modified with attributes to specify the property type..</span></span> <span data-ttu-id="c5c3a-109">リソースは、**Get()**、**Set()**、および **Test()** メソッド (スクリプト リソースの **Get-TargetResource**、**Set-TargetResource**、および **Test-TargetResource** 関数に相当します) によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-109">The resource is implemented by **Get()**, **Set()**, and **Test()** methods (equivalent to the **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource** functions in a script resource.</span></span>

<span data-ttu-id="c5c3a-110">このトピックでは、指定されたパス内のファイルを管理する **FileResource** という名前の単純なリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-110">In this topic, we will create a simple resource named **FileResource** that manages a file in a specified path.</span></span>

<span data-ttu-id="c5c3a-111">DSC リソースの詳細については、「[カスタム Windows PowerShell Desired State Configuration のビルド](authoringResource.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-111">For more information about DSC resources, see [Build Custom Windows PowerShell Desired State Configuration Resources](authoringResource.md)</span></span>

><span data-ttu-id="c5c3a-112">**注:** ジェネリック コレクションは、クラス ベースのリソースでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-112">**Note:** Generic collections are not supported in class-based resources.</span></span>

## <a name="folder-structure-for-a-class-resource"></a><span data-ttu-id="c5c3a-113">クラス リソースのフォルダー構造</span><span class="sxs-lookup"><span data-stu-id="c5c3a-113">Folder structure for a class resource</span></span>

<span data-ttu-id="c5c3a-114">PowerShell クラスを使用して DSC カスタム リソースを実装するには、次のフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-114">To implement a DSC custom resource with a PowerShell class, create the following folder structure.</span></span> <span data-ttu-id="c5c3a-115">クラスは **MyDscResource.psm1** で定義し、モジュール マニフェストは **MyDscResource.psd1** で定義します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-115">The class is defined in **MyDscResource.psm1** and the module manifest is defined in **MyDscResource.psd1**.</span></span>

```
$env:ProgramFiles\WindowsPowerShell\Modules (folder)
    |- MyDscResource (folder)
        |- MyDscResource.psm1
           MyDscResource.psd1
```

## <a name="create-the-class"></a><span data-ttu-id="c5c3a-116">クラスの作成</span><span class="sxs-lookup"><span data-stu-id="c5c3a-116">Create the class</span></span>

<span data-ttu-id="c5c3a-117">PowerShell クラスを作成するには、class キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-117">You use the class keyword to create a PowerShell class.</span></span> <span data-ttu-id="c5c3a-118">クラスを DSC リソースとして指定するには、**DscResource()** 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-118">To specify that a class is a DSC resource, use the **DscResource()** attribute.</span></span> <span data-ttu-id="c5c3a-119">クラスの名前は、DSC リソースの名前です。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-119">The name of the class is the name of the DSC resource.</span></span>

```powershell
[DscResource()]
class FileResource {
}
```

### <a name="declare-properties"></a><span data-ttu-id="c5c3a-120">プロパティの宣言</span><span class="sxs-lookup"><span data-stu-id="c5c3a-120">Declare properties</span></span>

<span data-ttu-id="c5c3a-121">DSC リソースのスキーマは、クラスのプロパティとして定義します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-121">The DSC resource schema is defined as properties of the class.</span></span> <span data-ttu-id="c5c3a-122">3 つのプロパティを次のように宣言します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-122">We declare three properties as follows.</span></span>

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

<span data-ttu-id="c5c3a-123">属性によってプロパティが変更されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-123">Notice that the properties are modified by attributes.</span></span> <span data-ttu-id="c5c3a-124">属性の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-124">The meaning of the attributes is as follows:</span></span>

- <span data-ttu-id="c5c3a-125">**Dscproperty (key)**:プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-125">**DscProperty(Key)**: The property is required.</span></span> <span data-ttu-id="c5c3a-126">プロパティはキーです。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-126">The property is a key.</span></span> <span data-ttu-id="c5c3a-127">キーとしてマークされたすべてのプロパティの値を組み合わせて、構成内のリソース インスタンスを一意に識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-127">The values of all properties marked as keys must combine to uniquely identify a resource instance within a configuration.</span></span>
- <span data-ttu-id="c5c3a-128">**Dscproperty (mandatory)**:プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-128">**DscProperty(Mandatory)**: The property is required.</span></span>
- <span data-ttu-id="c5c3a-129">**Dscproperty (notconfigurable)**:プロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-129">**DscProperty(NotConfigurable)**: The property is read-only.</span></span> <span data-ttu-id="c5c3a-130">この属性でマークされたプロパティは、構成で設定できませんが、**Get()** メソッド (存在する場合) によって設定されます。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-130">Properties marked with this attribute cannot be set by a configuration, but are populated by the **Get()** method when present.</span></span>
- <span data-ttu-id="c5c3a-131">**DscProperty()**:プロパティは構成可能ですが必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-131">**DscProperty()**: The property is configurable, but it is not required.</span></span>

<span data-ttu-id="c5c3a-132">**$Path** プロパティと **$SourcePath** プロパティは、両方とも文字列です。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-132">The **$Path** and **$SourcePath** properties are both strings.</span></span> <span data-ttu-id="c5c3a-133">**$CreationTime** は、[DateTime](/dotnet/api/system.datetime) プロパティです。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-133">The **$CreationTime** is a [DateTime](/dotnet/api/system.datetime) property.</span></span> <span data-ttu-id="c5c3a-134">**$Ensure** プロパティは、次のように定義された列挙型です。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-134">The **$Ensure** property is an enumeration type, defined as follows.</span></span>

```powershell
enum Ensure
{
    Absent
    Present
}
```

### <a name="implementing-the-methods"></a><span data-ttu-id="c5c3a-135">メソッドの実装</span><span class="sxs-lookup"><span data-stu-id="c5c3a-135">Implementing the methods</span></span>

<span data-ttu-id="c5c3a-136">**Get()**、**Set()**、および **Test()** メソッドは、スクリプト リソースの **Get-TargetResource**、**Set-TargetResource**、および **Test-TargetResource** 関数に似ています。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-136">The **Get()**, **Set()**, and **Test()** methods are analogous to the **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource** functions in a script resource.</span></span>

<span data-ttu-id="c5c3a-137">このコードには、ファイルを **$SourcePath** から **$Path** にコピーするヘルパー関数である CopyFile() 関数も含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-137">This code also includes the CopyFile() function, a helper function that copies the file from **$SourcePath** to **$Path**.</span></span>

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

### <a name="the-complete-file"></a><span data-ttu-id="c5c3a-138">完全なファイル</span><span class="sxs-lookup"><span data-stu-id="c5c3a-138">The complete file</span></span>
<span data-ttu-id="c5c3a-139">完全なクラス ファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-139">The complete class file follows.</span></span>

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


## <a name="create-a-manifest"></a><span data-ttu-id="c5c3a-140">マニフェストの作成</span><span class="sxs-lookup"><span data-stu-id="c5c3a-140">Create a manifest</span></span>

<span data-ttu-id="c5c3a-141">クラスベースのリソースを DSC エンジンで使用できるようにするには、マニフェスト ファイルに、リソースをエクスポートするようにモジュールに指示する **DscResourcesToExport** ステートメントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-141">To make a class-based resource available to the DSC engine, you must include a **DscResourcesToExport** statement in the manifest file that instructs the module to export the resource.</span></span> <span data-ttu-id="c5c3a-142">この例では、マニフェストは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-142">Our manifest looks like this:</span></span>

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

## <a name="test-the-resource"></a><span data-ttu-id="c5c3a-143">リソースのテスト</span><span class="sxs-lookup"><span data-stu-id="c5c3a-143">Test the resource</span></span>

<span data-ttu-id="c5c3a-144">既に説明したように、クラスとマニフェスト ファイルをフォルダー構造で保存した後で、新しいリソースを使用する構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-144">After saving the class and manifest files in the folder structure as described earlier, you can create a configuration that uses the new resource.</span></span> <span data-ttu-id="c5c3a-145">DSC 構成を実行する方法については、「[構成の適用](../pull-server/enactingConfigurations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-145">For information about how to run a DSC configuration, see [Enacting configurations](../pull-server/enactingConfigurations.md).</span></span> <span data-ttu-id="c5c3a-146">次の構成では、`c:\test\test.txt` のファイルが存在するかどうかを確認し、存在しない場合は、ファイルを `c:\test.txt` からコピーします (構成を実行する前に `c:\test.txt` を作成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-146">The following configuration will check to see whether the file at `c:\test\test.txt` exists, and, if not, copies the file from `c:\test.txt` (you should create `c:\test.txt` before you run the configuration).</span></span>

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

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="c5c3a-147">PsDscRunAsCredential のサポート</span><span class="sxs-lookup"><span data-stu-id="c5c3a-147">Supporting PsDscRunAsCredential</span></span>

><span data-ttu-id="c5c3a-148">**注:\*\*\*\*PsDscRunAsCredential** PowerShell 5.0 以降ではサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-148">**Note:** **PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="c5c3a-149">**PsDscRunAsCredential** プロパティを [DSC 構成](../configurations/configurations.md)リソース ブロックで使用して、指定した資格情報のもとでリソースを実行する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-149">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span>
<span data-ttu-id="c5c3a-150">詳細については、「[ユーザーの資格情報を指定して DSC を実行する](../configurations/runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-150">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

### <a name="require-or-disallow-psdscrunascredential-for-your-resource"></a><span data-ttu-id="c5c3a-151">使用するリソースに対する PsDscRunAsCredential の要求または却下</span><span class="sxs-lookup"><span data-stu-id="c5c3a-151">Require or disallow PsDscRunAsCredential for your resource</span></span>

<span data-ttu-id="c5c3a-152">**DscResource()** 属性でオプションのパラメーター **RunAsCredential** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-152">The **DscResource()** attribute takes an optional parameter **RunAsCredential**.</span></span>
<span data-ttu-id="c5c3a-153">このパラメーターには以下の 3 つの値のいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-153">This parameter takes one of three values:</span></span>

- <span data-ttu-id="c5c3a-154">`Optional`**PsDscRunAsCredential** は、このリソースを呼び出す構成ではオプションです。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-154">`Optional` **PsDscRunAsCredential** is optional for configurations that call this resource.</span></span> <span data-ttu-id="c5c3a-155">これは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-155">This is the default value.</span></span>
- <span data-ttu-id="c5c3a-156">`Mandatory`**PsDscRunAsCredential** は、このリソースを呼び出す構成で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-156">`Mandatory` **PsDscRunAsCredential** must be used for any configuration that calls this resource.</span></span>
- <span data-ttu-id="c5c3a-157">`NotSupported`このリソースを呼び出す構成には **PsDscRunAsCredential** を使用できません。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-157">`NotSupported` Configurations that call this resource cannot use **PsDscRunAsCredential**.</span></span>
- <span data-ttu-id="c5c3a-158">`Default``Optional` と同じです。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-158">`Default` Same as `Optional`.</span></span>

<span data-ttu-id="c5c3a-159">たとえば、次の属性を使用して、ご使用のカスタム リソースが **PsDscRunAsCredential** の使用をサポートしないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-159">For example, use the following attribute to specify that your custom resource does not support using **PsDscRunAsCredential**:</span></span>

```powershell
[DscResource(RunAsCredential=NotSupported)]
class FileResource {
}
```

### <a name="access-the-user-context"></a><span data-ttu-id="c5c3a-160">ユーザー コンテキストへのアクセス</span><span class="sxs-lookup"><span data-stu-id="c5c3a-160">Access the user context</span></span>

<span data-ttu-id="c5c3a-161">カスタム リソース内からユーザー コンテキストにアクセスするには、自動変数 `$global:PsDscContext` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-161">To access the user context from within a custom resource, you can use the automatic variable `$global:PsDscContext`.</span></span>

<span data-ttu-id="c5c3a-162">たとえば、次のコードは、リソースが詳細出力ストリームに実行しているユーザー コンテキストを記述します。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-162">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if (PsDscContext.RunAsUser) {
    Write-Verbose "User: $global:PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a><span data-ttu-id="c5c3a-163">参照</span><span class="sxs-lookup"><span data-stu-id="c5c3a-163">See Also</span></span>
### <a name="concepts"></a><span data-ttu-id="c5c3a-164">概念</span><span class="sxs-lookup"><span data-stu-id="c5c3a-164">Concepts</span></span>
[<span data-ttu-id="c5c3a-165">Build Custom Windows PowerShell Desired State Configuration Resources (カスタム Windows PowerShell Desired State Configuration のビルド)</span><span class="sxs-lookup"><span data-stu-id="c5c3a-165">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>](authoringResource.md)
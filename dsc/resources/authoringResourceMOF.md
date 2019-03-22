---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MOF を使用したカスタム DSC リソースの記述
ms.openlocfilehash: f243c3e3297711e6f6346a0f813a9c017fe227c3
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "58059730"
---
# <a name="writing-a-custom-dsc-resource-with-mof"></a><span data-ttu-id="59686-103">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="59686-103">Writing a custom DSC resource with MOF</span></span>

> <span data-ttu-id="59686-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="59686-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="59686-105">このトピックでは、MOF ファイルで Windows PowerShell Desired State Configuration (DSC) カスタム リソースのスキーマを定義し、Windows PowerShell スクリプト ファイルでリソースを実装します。</span><span class="sxs-lookup"><span data-stu-id="59686-105">In this topic, we will define the schema for a Windows PowerShell Desired State Configuration (DSC) custom resource in a MOF file, and implement the resource in a Windows PowerShell script file.</span></span> <span data-ttu-id="59686-106">このカスタム リソースは、Web サイトを作成および保守するためのものです。</span><span class="sxs-lookup"><span data-stu-id="59686-106">This custom resource is for creating and maintaining a web site.</span></span>

## <a name="creating-the-mof-schema"></a><span data-ttu-id="59686-107">MOF スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="59686-107">Creating the MOF schema</span></span>

<span data-ttu-id="59686-108">スキーマでは、DSC 構成スクリプトによって構成できるリソースのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="59686-108">The schema defines the properties of your resource that can be configured by a DSC configuration script.</span></span>

### <a name="folder-structure-for-a-mof-resource"></a><span data-ttu-id="59686-109">MOF リソースのフォルダー構造</span><span class="sxs-lookup"><span data-stu-id="59686-109">Folder structure for a MOF resource</span></span>

<span data-ttu-id="59686-110">MOF スキーマを使用して DSC カスタム リソースを実装するには、次のフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="59686-110">To implement a DSC custom resource with a MOF schema, create the following folder structure.</span></span> <span data-ttu-id="59686-111">MOF スキーマは Demo_IISWebsite.schema.mof ファイルで定義し、リソース スクリプトは Demo_IISWebsite.psm1 で定義します。</span><span class="sxs-lookup"><span data-stu-id="59686-111">The MOF schema is defined in the file Demo_IISWebsite.schema.mof, and the resource script is defined in Demo_IISWebsite.psm1.</span></span> <span data-ttu-id="59686-112">必要に応じて、モジュール マニフェスト (psd1) ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="59686-112">Optionally, you can create a module manifest (psd1) file.</span></span>

```
$env:ProgramFiles\WindowsPowerShell\Modules (folder)
    |- MyDscResources (folder)
        |- DSCResources (folder)
            |- Demo_IISWebsite (folder)
                |- Demo_IISWebsite.psd1 (file, optional)
                |- Demo_IISWebsite.psm1 (file, required)
                |- Demo_IISWebsite.schema.mof (file, required)
```

<span data-ttu-id="59686-113">最上位のフォルダーの下に DSCResources という名前のフォルダーを作成し、各リソースのフォルダーにリソースと同じ名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="59686-113">Note that it is necessary to create a folder named DSCResources under the top-level folder, and that the folder for each resource must have the same name as the resource.</span></span>

### <a name="the-contents-of-the-mof-file"></a><span data-ttu-id="59686-114">MOF ファイルの内容</span><span class="sxs-lookup"><span data-stu-id="59686-114">The contents of the MOF file</span></span>

<span data-ttu-id="59686-115">カスタム Web サイト リソースに使用できる MOF ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="59686-115">Following is an example MOF file that can be used for a custom website resource.</span></span> <span data-ttu-id="59686-116">この例に従うには、このスキーマをファイルに保存し、ファイルの名前は *Demo_IISWebsite.schema.mof* にします。</span><span class="sxs-lookup"><span data-stu-id="59686-116">To follow this example, save this schema to a file, and call the file *Demo_IISWebsite.schema.mof*.</span></span>

```
[ClassVersion("1.0.0"), FriendlyName("Website")]
class Demo_IISWebsite : OMI_BaseResource
{
  [Key] string Name;
  [Required] string PhysicalPath;
  [write,ValueMap{"Present", "Absent"},Values{"Present", "Absent"}] string Ensure;
  [write,ValueMap{"Started","Stopped"},Values{"Started", "Stopped"}] string State;
  [write] string Protocol[];
  [write] string BindingInfo[];
  [write] string ApplicationPool;
  [read] string ID;
};
```

<span data-ttu-id="59686-117">前のコードについて、次のことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="59686-117">Note the following about the previous code:</span></span>

* <span data-ttu-id="59686-118">`FriendlyName` では、DSC 構成スクリプトでこのカスタム リソースを参照するために使用できる名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="59686-118">`FriendlyName` defines the name you can use to refer to this custom resource in DSC configuration scripts.</span></span> <span data-ttu-id="59686-119">この例では、`Website` は、組み込みのアーカイブ リソースのフレンドリ名 `Archive` に相当します。</span><span class="sxs-lookup"><span data-stu-id="59686-119">In this example, `Website` is equivalent to the friendly name `Archive` for the built-in Archive resource.</span></span>
* <span data-ttu-id="59686-120">カスタム リソース用に定義するクラスは、`OMI_BaseResource` から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59686-120">The class you define for your custom resource must derive from `OMI_BaseResource`.</span></span>
* <span data-ttu-id="59686-121">プロパティの型修飾子 `[Key]` は、このプロパティがリソース インスタンスを一意に識別することを示します。</span><span class="sxs-lookup"><span data-stu-id="59686-121">The type qualifier, `[Key]`, on a property indicates that this property will uniquely identify the resource instance.</span></span> <span data-ttu-id="59686-122">1 つ以上の `[Key]` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="59686-122">At least one `[Key]` property is required.</span></span>
* <span data-ttu-id="59686-123">`[Required]` 修飾子は、プロパティが必須であることを示します (このリソースを使用する構成スクリプトで値を指定する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="59686-123">The `[Required]` qualifier indicates that the property is required (a value must be specified in any configuration script that uses this resource).</span></span>
* <span data-ttu-id="59686-124">`[write]` 修飾子は、構成スクリプトでカスタム リソースを使用するときにこのプロパティが省略可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="59686-124">The `[write]` qualifier indicates that this property is optional when using the custom resource in a configuration script.</span></span> <span data-ttu-id="59686-125">`[read]` 修飾子は、プロパティが構成では設定できず、報告のみを目的とするとを示します。</span><span class="sxs-lookup"><span data-stu-id="59686-125">The `[read]` qualifier indicates that a property cannot be set by a configuration, and is for reporting purposes only.</span></span>
* <span data-ttu-id="59686-126">`Values` は、プロパティに割り当てることのできる値を `ValueMap` で定義されている値の一覧に制限します。</span><span class="sxs-lookup"><span data-stu-id="59686-126">`Values` restricts the values that can be assigned to the property to the list of values defined in `ValueMap`.</span></span> <span data-ttu-id="59686-127">詳細については、「[ValueMap and Value Qualifiers (ValueMap 修飾子と Value 修飾子)](/windows/desktop/WmiSdk/value-map)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59686-127">For more information, see [ValueMap and Value Qualifiers](/windows/desktop/WmiSdk/value-map).</span></span>
* <span data-ttu-id="59686-128">組み込みの DSC リソースとの一貫したスタイルを維持する方法として、値 `Present` と `Absent` を持つ `Ensure` というプロパティをリソースに含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59686-128">Including a property called `Ensure` with values `Present` and `Absent` in your resource is recommended as a way to maintain a consistent style with built-in DSC resources.</span></span>
* <span data-ttu-id="59686-129">カスタム リソースのスキーマ ファイルには、`classname.schema.mof` のように名前を付けます。ここで、`classname` はスキーマ定義内の `class` キーワードに続く識別子です。</span><span class="sxs-lookup"><span data-stu-id="59686-129">Name the schema file for your custom resource as follows: `classname.schema.mof`, where `classname` is the identifier that follows the `class` keyword in your schema definition.</span></span>

### <a name="writing-the-resource-script"></a><span data-ttu-id="59686-130">リソース スクリプトの作成</span><span class="sxs-lookup"><span data-stu-id="59686-130">Writing the resource script</span></span>

<span data-ttu-id="59686-131">リソース スクリプトでは、リソースのロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="59686-131">The resource script implements the logic of the resource.</span></span> <span data-ttu-id="59686-132">このモジュールでは、**Get-TargetResource**、**Set-TargetResource**、および **Test-TargetResource** という 3 つの関数を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="59686-132">In this module, you must include three functions called **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource**.</span></span> <span data-ttu-id="59686-133">3 つのすべての関数は、リソース用に作成した MOF スキーマで定義されている一連のプロパティと同じパラメーター セットを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="59686-133">All three functions must take a parameter set that is identical to the set of properties defined in the MOF schema that you created for your resource.</span></span> <span data-ttu-id="59686-134">このドキュメントでは、この一連のプロパティを "リソース プロパティ" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="59686-134">In this document, this set of properties is referred to as the “resource properties.”</span></span> <span data-ttu-id="59686-135">これらの 3 つの関数は、<ResourceName>.psm1 というファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="59686-135">Store these three functions in a file called <ResourceName>.psm1.</span></span> <span data-ttu-id="59686-136">次の例では、関数は Demo_IISWebsite.psm1 というファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="59686-136">In the following example, the functions are stored in a file called Demo_IISWebsite.psm1.</span></span>

> [!NOTE]
> <span data-ttu-id="59686-137">リソースに対して同じ構成スクリプトを複数回実行する場合、エラーが発生せずに、スクリプトを 1 回実行したときと同じ状態にリソースが保たれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="59686-137">When you run the same configuration script on your resource more than once, you should receive no errors and the resource should remain in the same state as running the script once.</span></span> <span data-ttu-id="59686-138">これを実現するには、**Get-TargetResource** と **Test-TargetResource** 関数によってリソースが変更されないようにし、シーケンス内で同じパラメーター値を使用して **Set-TargetResource** 関数を複数回呼び出した場合に、1 回呼び出した場合と常に同じ結果になるようにします。</span><span class="sxs-lookup"><span data-stu-id="59686-138">To accomplish this, ensure that your **Get-TargetResource** and **Test-TargetResource** functions leave the resource unchanged, and that invoking the **Set-TargetResource** function more than once in a sequence with the same parameter values is always equivalent to invoking it once.</span></span>

<span data-ttu-id="59686-139">**Get-TargetResource** 関数の実装では、パラメーターとして指定されたキー リソース プロパティ値を使用して、指定されたリソース インスタンスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="59686-139">In the **Get-TargetResource** function implementation, use the key resource property values that are provided as parameters to check the status of the specified resource instance.</span></span> <span data-ttu-id="59686-140">この関数は、キーとしてすべてのリソース プロパティを、対応する値としてこれらのプロパティの実際の値を一覧表示するハッシュ テーブルを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="59686-140">This function must return a hash table that lists all the resource properties as keys and the actual values of these properties as the corresponding values.</span></span> <span data-ttu-id="59686-141">コードの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="59686-141">The following code provides an example.</span></span>

```powershell
# DSC uses the Get-TargetResource function to fetch the status of the resource instance specified in the parameters for the target machine
function Get-TargetResource
{
    param
    (
        [ValidateSet("Present", "Absent")]
        [string]$Ensure = "Present",

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$Name,

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$PhysicalPath,

        [ValidateSet("Started", "Stopped")]
        [string]$State = "Started",

        [string]$ApplicationPool,

        [string[]]$BindingInfo,

        [string[]]$Protocol
    )

        $getTargetResourceResult = $null;

        <# Insert logic that uses the mandatory parameter values to get the website and assign it to a variable called $Website #>
        <# Set $ensureResult to "Present" if the requested website exists and to "Absent" otherwise #>

        # Add all Website properties to the hash table
        # This simple example assumes that $Website is not null
        $getTargetResourceResult = @{
                                      Name = $Website.Name;
                                        Ensure = $ensureResult;
                                        PhysicalPath = $Website.physicalPath;
                                        State = $Website.state;
                                        ID = $Website.id;
                                        ApplicationPool = $Website.applicationPool;
                                        Protocol = $Website.bindings.Collection.protocol;
                                        Binding = $Website.bindings.Collection.bindingInformation;
                                    }

        $getTargetResourceResult;
}
```

<span data-ttu-id="59686-142">構成スクリプトでリソース プロパティに指定されている値に応じて、**Set-TargetResource** は次のいずれかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59686-142">Depending on the values that are specified for the resource properties in the configuration script, the **Set-TargetResource** must do one of the following:</span></span>

* <span data-ttu-id="59686-143">新しい Web サイトの作成</span><span class="sxs-lookup"><span data-stu-id="59686-143">Create a new website</span></span>
* <span data-ttu-id="59686-144">既存の Web サイトの更新</span><span class="sxs-lookup"><span data-stu-id="59686-144">Update an existing website</span></span>
* <span data-ttu-id="59686-145">既存の Web サイトの削除</span><span class="sxs-lookup"><span data-stu-id="59686-145">Delete an existing website</span></span>

<span data-ttu-id="59686-146">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="59686-146">The following example illustrates this.</span></span>

```powershell
# The Set-TargetResource function is used to create, delete or configure a website on the target machine.
function Set-TargetResource
{
    [CmdletBinding(SupportsShouldProcess=$true)]
    param
    (
        [ValidateSet("Present", "Absent")]
        [string]$Ensure = "Present",

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$Name,

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$PhysicalPath,

        [ValidateSet("Started", "Stopped")]
        [string]$State = "Started",

        [string]$ApplicationPool,

        [string[]]$BindingInfo,

        [string[]]$Protocol
    )

    <# If Ensure is set to "Present" and the website specified in the mandatory input parameters does not exist, then create it using the specified parameter values #>
    <# Else, if Ensure is set to "Present" and the website does exist, then update its properties to match the values provided in the non-mandatory parameter values #>
    <# Else, if Ensure is set to "Absent" and the website does not exist, then do nothing #>
    <# Else, if Ensure is set to "Absent" and the website does exist, then delete the website #>
}
```

<span data-ttu-id="59686-147">最後に、**Test-TargetResource** 関数は、**Get-TargetResource** および **Set-TargetResource** と同じパラメーター セットを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="59686-147">Finally, the **Test-TargetResource** function must take the same parameter set as **Get-TargetResource** and **Set-TargetResource**.</span></span> <span data-ttu-id="59686-148">**Test-TargetResource** の実装で、キー パラメーターで指定されているリソース インスタンスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="59686-148">In your implementation of **Test-TargetResource**, check the status of the resource instance that is specified in the key parameters.</span></span> <span data-ttu-id="59686-149">リソース インスタンスの実際の状態がパラメーター セットで指定された値と一致しない場合は、**$false** を返します。</span><span class="sxs-lookup"><span data-stu-id="59686-149">If the actual status of the resource instance does not match the values specified in the parameter set, return **$false**.</span></span> <span data-ttu-id="59686-150">それ以外の場合は、**$true**  を返します。</span><span class="sxs-lookup"><span data-stu-id="59686-150">Otherwise, return **$true**.</span></span>

<span data-ttu-id="59686-151">次のコードでは、**Test-TargetResource** 関数を実装します。</span><span class="sxs-lookup"><span data-stu-id="59686-151">The following code implements the **Test-TargetResource** function.</span></span>

```powershell
function Test-TargetResource
{
[CmdletBinding()]
[OutputType([System.Boolean])]
param
(
[ValidateSet("Present","Absent")]
[System.String]
$Ensure,

[parameter(Mandatory = $true)]
[System.String]
$Name,

[parameter(Mandatory = $true)]
[System.String]
$PhysicalPath,

[ValidateSet("Started","Stopped")]
[System.String]
$State,

[System.String[]]
$Protocol,

[System.String[]]
$BindingData,

[System.String]
$ApplicationPool
)

#Write-Verbose "Use this cmdlet to deliver information about command processing."

#Write-Debug "Use this cmdlet to write debug information while troubleshooting."


#Include logic to
$result = [System.Boolean]
#Add logic to test whether the website is present and its status mathes the supplied parameter values. If it does, return true. If it does not, return false.
$result
}
```

<span data-ttu-id="59686-152">**注**:簡単にデバッグするには、前の 3 つの関数の実装で **Write-Verbose** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="59686-152">**Note**: For easier debugging, use the **Write-Verbose** cmdlet in your implementation of the previous three functions.</span></span>
><span data-ttu-id="59686-153">このコマンドレットは、テキストを詳細メッセージ ストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="59686-153">This cmdlet writes text to the verbose message stream.</span></span>
><span data-ttu-id="59686-154">既定では、詳細メッセージ ストリームは表示されません。表示するには、**$VerbosePreference** 変数の値を変更するか、DSC コマンドレットで **Verbose** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="59686-154">By default, the verbose message stream is not displayed, but you can display it by changing the value of the **$VerbosePreference** variable or by using the **Verbose** parameter in the DSC cmdlets = new.</span></span>

### <a name="creating-the-module-manifest"></a><span data-ttu-id="59686-155">モジュール マニフェストの作成</span><span class="sxs-lookup"><span data-stu-id="59686-155">Creating the module manifest</span></span>

<span data-ttu-id="59686-156">最後に、**New-ModuleManifest** コマンドレットを使用して、カスタム リソース モジュールの <ResourceName>.psd1 ファイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="59686-156">Finally, use the **New-ModuleManifest** cmdlet to define a <ResourceName>.psd1 file for your custom resource module.</span></span> <span data-ttu-id="59686-157">このコマンドレットを呼び出すときに、前のセクションで説明したスクリプト モジュール (.psm1) ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="59686-157">When you invoke this cmdlet, reference the script module (.psm1) file described in the previous section.</span></span> <span data-ttu-id="59686-158">**Get-TargetResource**、**Set-TargetResource**、および **Test-TargetResource** をエクスポートする関数の一覧に含めます。</span><span class="sxs-lookup"><span data-stu-id="59686-158">Include **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource** in the list of functions to export.</span></span> <span data-ttu-id="59686-159">マニフェスト ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="59686-159">Following is an example manifest file.</span></span>

```powershell
# Module manifest for module 'Demo.IIS.Website'
#
# Generated on: 1/10/2013
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '6AB5ED33-E923-41d8-A3A4-5ADDA2B301DE'

# Author of this module
Author = 'Contoso'

# Company or vendor of this module
CompanyName = 'Contoso'

# Copyright statement for this module
Copyright = 'Contoso. All rights reserved.'

# Description of the functionality provided by this module
Description = 'This Module is used to support the creation and configuration of IIS Websites through Get, Set and Test API on the DSC managed nodes.'

# Minimum version of the Windows PowerShell engine required by this module
PowerShellVersion = '4.0'

# Minimum version of the common language runtime (CLR) required by this module
CLRVersion = '4.0'

# Modules that must be imported into the global environment prior to importing this module
RequiredModules = @("WebAdministration")

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
NestedModules = @("Demo_IISWebsite.psm1")

# Functions to export from this module
FunctionsToExport = @("Get-TargetResource", "Set-TargetResource", "Test-TargetResource")

# Cmdlets to export from this module
#CmdletsToExport = '*'

# HelpInfo URI of this module
# HelpInfoURI = ''
}
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="59686-160">PsDscRunAsCredential のサポート</span><span class="sxs-lookup"><span data-stu-id="59686-160">Supporting PsDscRunAsCredential</span></span>

><span data-ttu-id="59686-161">**注:** **PsDscRunAsCredential** は PowerShell 5.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="59686-161">**Note:** **PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="59686-162">**PsDscRunAsCredential** プロパティを [DSC 構成](../configurations/configurations.md)リソース ブロックで使用して、指定した資格情報のもとでリソースを実行する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="59686-162">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span>
<span data-ttu-id="59686-163">詳細については、「[ユーザーの資格情報を指定して DSC を実行する](../configurations/runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59686-163">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="59686-164">カスタム リソース内からユーザー コンテキストにアクセスするには、自動変数 `$PsDscContext` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="59686-164">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="59686-165">たとえば、次のコードは、リソースが詳細出力ストリームに実行しているユーザー コンテキストを記述します。</span><span class="sxs-lookup"><span data-stu-id="59686-165">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if (PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="rebooting-the-node"></a><span data-ttu-id="59686-166">Node を再起動する</span><span class="sxs-lookup"><span data-stu-id="59686-166">Rebooting the Node</span></span>

<span data-ttu-id="59686-167">`Set-TargetResource` 関数で行われるアクションに再起動が必要となる場合、グローバル フラグを使用し、Node の再起動を LCM に指示できます。</span><span class="sxs-lookup"><span data-stu-id="59686-167">If the actions taken in your `Set-TargetResource` function require a reboot, you can use a global flag to tell the LCM to reboot the Node.</span></span> <span data-ttu-id="59686-168">この再起動は、`Set-TargetResource` 関数の完了直後に行われます。</span><span class="sxs-lookup"><span data-stu-id="59686-168">This reboot occurs directly after the `Set-TargetResource` function completes.</span></span>

<span data-ttu-id="59686-169">`Set-TargetResource` 関数内で次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="59686-169">Inside your `Set-TargetResource` function, add the following line of code.</span></span>

```powershell
# Include this line if the resource requires a system reboot.
$global:DSCMachineStatus = 1
```

<span data-ttu-id="59686-170">LCM で Node を再起動するには、**RebootNodeIfNeeded** フラグを `$true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59686-170">In order for the LCM to reboot the Node, the **RebootNodeIfNeeded** flag needs to be set to `$true`.</span></span> <span data-ttu-id="59686-171">また、**ActionAfterReboot** 設定を既定である **ContinueConfiguration** に設定してください。</span><span class="sxs-lookup"><span data-stu-id="59686-171">The **ActionAfterReboot** setting should also be set to **ContinueConfiguration**, which is the default.</span></span> <span data-ttu-id="59686-172">LCM の構成方法については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」または「[ローカル構成マネージャーの構成 (v4)](../managing-nodes/metaConfig4.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59686-172">For more information on configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configuring the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>

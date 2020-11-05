---
ms.date: 07/08/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: MOF を使用したカスタム DSC リソースの記述
description: この記事では、MOF ファイルで DSC カスタム リソースのスキーマを定義し、そのリソースを PowerShell スクリプト ファイルで実装します。
ms.openlocfilehash: e79a37699c468b2c55c307c96f1c193a2c1595b3
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667183"
---
# <a name="writing-a-custom-dsc-resource-with-mof"></a><span data-ttu-id="5d38f-104">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="5d38f-104">Writing a custom DSC resource with MOF</span></span>

> <span data-ttu-id="5d38f-105">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="5d38f-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="5d38f-106">この記事では、MOF ファイルで Windows PowerShell Desired State Configuration (DSC) カスタム リソースのスキーマを定義し、そのリソースを Windows PowerShell スクリプト ファイルで実装します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-106">In this article, we will define the schema for a Windows PowerShell Desired State Configuration (DSC) custom resource in a MOF file, and implement the resource in a Windows PowerShell script file.</span></span>
<span data-ttu-id="5d38f-107">このカスタム リソースは、Web サイトを作成および保守するためのものです。</span><span class="sxs-lookup"><span data-stu-id="5d38f-107">This custom resource is for creating and maintaining a web site.</span></span>

## <a name="creating-the-mof-schema"></a><span data-ttu-id="5d38f-108">MOF スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="5d38f-108">Creating the MOF schema</span></span>

<span data-ttu-id="5d38f-109">スキーマでは、DSC 構成スクリプトによって構成できるリソースのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-109">The schema defines the properties of your resource that can be configured by a DSC configuration script.</span></span>

### <a name="folder-structure-for-a-mof-resource"></a><span data-ttu-id="5d38f-110">MOF リソースのフォルダー構造</span><span class="sxs-lookup"><span data-stu-id="5d38f-110">Folder structure for a MOF resource</span></span>

<span data-ttu-id="5d38f-111">MOF スキーマを使用して DSC カスタム リソースを実装するには、次のフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-111">To implement a DSC custom resource with a MOF schema, create the following folder structure.</span></span> <span data-ttu-id="5d38f-112">MOF スキーマは、`Demo_IISWebsite.schema.mof` ファイルで定義され、リソース スクリプトは `Demo_IISWebsite.psm1` で定義されます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-112">The MOF schema is defined in the file `Demo_IISWebsite.schema.mof`, and the resource script is defined in `Demo_IISWebsite.psm1`.</span></span> <span data-ttu-id="5d38f-113">必要に応じて、モジュール マニフェスト (psd1) ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-113">Optionally, you can create a module manifest (psd1) file.</span></span>

```
$env:ProgramFiles\WindowsPowerShell\Modules (folder)
    |- MyDscResources (folder)
        |- DSCResources (folder)
            |- Demo_IISWebsite (folder)
                |- Demo_IISWebsite.psd1 (file, optional)
                |- Demo_IISWebsite.psm1 (file, required)
                |- Demo_IISWebsite.schema.mof (file, required)
```

> [!NOTE]
> <span data-ttu-id="5d38f-114">最上位のフォルダーに DSCResources という名前のフォルダーを作成し、各リソースのフォルダーにリソースと同じ名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d38f-114">It is necessary to create a folder named DSCResources under the top-level folder, and that the folder for each resource must have the same name as the resource.</span></span>

### <a name="the-contents-of-the-mof-file"></a><span data-ttu-id="5d38f-115">MOF ファイルの内容</span><span class="sxs-lookup"><span data-stu-id="5d38f-115">The contents of the MOF file</span></span>

<span data-ttu-id="5d38f-116">カスタム Web サイト リソースに使用できる MOF ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-116">Following is an example MOF file that can be used for a custom website resource.</span></span> <span data-ttu-id="5d38f-117">この例に従うには、このスキーマをファイルに保存し、ファイルの名前は `Demo_IISWebsite.schema.mof` にします。</span><span class="sxs-lookup"><span data-stu-id="5d38f-117">To follow this example, save this schema to a file, and call the file `Demo_IISWebsite.schema.mof`.</span></span>

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

<span data-ttu-id="5d38f-118">前のコードについて、次のことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5d38f-118">Note the following about the previous code:</span></span>

- <span data-ttu-id="5d38f-119">`FriendlyName` では、DSC 構成スクリプトでこのカスタム リソースを参照するために使用できる名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-119">`FriendlyName` defines the name you can use to refer to this custom resource in DSC configuration scripts.</span></span> <span data-ttu-id="5d38f-120">この例では、`Website` は、組み込みのアーカイブ リソースのフレンドリ名 `Archive` に相当します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-120">In this example, `Website` is equivalent to the friendly name `Archive` for the built-in Archive resource.</span></span>
- <span data-ttu-id="5d38f-121">カスタム リソース用に定義するクラスは、`OMI_BaseResource` から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d38f-121">The class you define for your custom resource must derive from `OMI_BaseResource`.</span></span>
- <span data-ttu-id="5d38f-122">プロパティの型修飾子 `[Key]` は、このプロパティがリソース インスタンスを一意に識別することを示します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-122">The type qualifier, `[Key]`, on a property indicates that this property will uniquely identify the resource instance.</span></span> <span data-ttu-id="5d38f-123">1 つ以上の `[Key]` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="5d38f-123">At least one `[Key]` property is required.</span></span>
- <span data-ttu-id="5d38f-124">`[Required]` 修飾子は、プロパティが必須であることを示します (このリソースを使用する構成スクリプトで値を指定する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="5d38f-124">The `[Required]` qualifier indicates that the property is required (a value must be specified in any configuration script that uses this resource).</span></span>
- <span data-ttu-id="5d38f-125">`[write]` 修飾子は、構成スクリプトでカスタム リソースを使用するときにこのプロパティが省略可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-125">The `[write]` qualifier indicates that this property is optional when using the custom resource in a configuration script.</span></span> <span data-ttu-id="5d38f-126">`[read]` 修飾子は、プロパティが構成では設定できず、報告のみを目的とするとを示します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-126">The `[read]` qualifier indicates that a property cannot be set by a configuration, and is for reporting purposes only.</span></span>
- <span data-ttu-id="5d38f-127">`Values` は、プロパティに割り当てることのできる値を `ValueMap` で定義されている値の一覧に制限します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-127">`Values` restricts the values that can be assigned to the property to the list of values defined in `ValueMap`.</span></span> <span data-ttu-id="5d38f-128">詳細については、「[ValueMap and Value Qualifiers (ValueMap 修飾子と Value 修飾子)](/windows/desktop/WmiSdk/value-map)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d38f-128">For more information, see [ValueMap and Value Qualifiers](/windows/desktop/WmiSdk/value-map).</span></span>
- <span data-ttu-id="5d38f-129">組み込みの DSC リソースとの一貫したスタイルを維持する方法として、値 `Present` と `Absent` を持つ `Ensure` というプロパティをリソースに含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d38f-129">Including a property called `Ensure` with values `Present` and `Absent` in your resource is recommended as a way to maintain a consistent style with built-in DSC resources.</span></span>
- <span data-ttu-id="5d38f-130">カスタム リソースのスキーマ ファイルには、`classname.schema.mof` のように名前を付けます。ここで、`classname` はスキーマ定義内の `class` キーワードに続く識別子です。</span><span class="sxs-lookup"><span data-stu-id="5d38f-130">Name the schema file for your custom resource as follows: `classname.schema.mof`, where `classname` is the identifier that follows the `class` keyword in your schema definition.</span></span>

### <a name="writing-the-resource-script"></a><span data-ttu-id="5d38f-131">リソース スクリプトの作成</span><span class="sxs-lookup"><span data-stu-id="5d38f-131">Writing the resource script</span></span>

<span data-ttu-id="5d38f-132">リソース スクリプトでは、リソースのロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-132">The resource script implements the logic of the resource.</span></span> <span data-ttu-id="5d38f-133">このモジュールでは、`Get-TargetResource`、`Set-TargetResource`、および `Test-TargetResource` という 3 つの関数を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d38f-133">In this module, you must include three functions called `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource`.</span></span> <span data-ttu-id="5d38f-134">3 つのすべての関数は、リソース用に作成した MOF スキーマで定義されている一連のプロパティと同じパラメーター セットを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d38f-134">All three functions must take a parameter set that is identical to the set of properties defined in the MOF schema that you created for your resource.</span></span> <span data-ttu-id="5d38f-135">このドキュメントでは、この一連のプロパティを "リソース プロパティ" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-135">In this document, this set of properties is referred to as the "resource properties."</span></span> <span data-ttu-id="5d38f-136">これらの 3 つの関数は `<ResourceName>.psm1`というファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-136">Store these three functions in a file called `<ResourceName>.psm1`.</span></span> <span data-ttu-id="5d38f-137">次の例では、関数は `Demo_IISWebsite.psm1` というファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-137">In the following example, the functions are stored in a file called `Demo_IISWebsite.psm1`.</span></span>

> [!NOTE]
> <span data-ttu-id="5d38f-138">リソースに対して同じ構成スクリプトを複数回実行する場合、エラーが発生せずに、スクリプトを 1 回実行したときと同じ状態にリソースが保たれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d38f-138">When you run the same configuration script on your resource more than once, you should receive no errors and the resource should remain in the same state as running the script once.</span></span> <span data-ttu-id="5d38f-139">これを実現するには、`Get-TargetResource` と `Test-TargetResource` 関数によってリソースが変更されないようにし、シーケンス内で同じパラメーター値を使用して `Set-TargetResource` 関数を複数回呼び出した場合に、1 回呼び出した場合と常に同じ結果になるようにします。</span><span class="sxs-lookup"><span data-stu-id="5d38f-139">To accomplish this, ensure that your `Get-TargetResource` and `Test-TargetResource` functions leave the resource unchanged, and that invoking the `Set-TargetResource` function more than once in a sequence with the same parameter values is always equivalent to invoking it once.</span></span>

<span data-ttu-id="5d38f-140">`Get-TargetResource` 関数の実装では、パラメーターとして指定されたキー リソース プロパティ値を使用して、指定されたリソース インスタンスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-140">In the `Get-TargetResource` function implementation, use the key resource property values that are provided as parameters to check the status of the specified resource instance.</span></span> <span data-ttu-id="5d38f-141">この関数は、キーとしてすべてのリソース プロパティを、対応する値としてこれらのプロパティの実際の値を一覧表示するハッシュ テーブルを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d38f-141">This function must return a hash table that lists all the resource properties as keys and the actual values of these properties as the corresponding values.</span></span> <span data-ttu-id="5d38f-142">コードの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5d38f-142">The following code provides an example.</span></span>

```powershell
# DSC uses the Get-TargetResource function to fetch the status of the resource instance
# specified in the parameters for the target machine
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

        <#
          Insert logic that uses the mandatory parameter values to get the website and
          assign it to a variable called $Website
          Set $ensureResult to "Present" if the requested website exists and to "Absent" otherwise
        #>

        # Add all Website properties to the hash table
        # This simple example assumes that $Website is not null
        $getTargetResourceResult = @{
            Name = $Website.Name
            Ensure = $ensureResult
            PhysicalPath = $Website.physicalPath
            State = $Website.state
            ID = $Website.id
            ApplicationPool = $Website.applicationPool
            Protocol = $Website.bindings.Collection.protocol
            Binding = $Website.bindings.Collection.bindingInformation
        }

        $getTargetResourceResult
}
```

<span data-ttu-id="5d38f-143">構成スクリプトでリソース プロパティに指定されている値に応じて、`Set-TargetResource` は次のいずれかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d38f-143">Depending on the values that are specified for the resource properties in the configuration script, the `Set-TargetResource` must do one of the following:</span></span>

- <span data-ttu-id="5d38f-144">新しい Web サイトの作成</span><span class="sxs-lookup"><span data-stu-id="5d38f-144">Create a new website</span></span>
- <span data-ttu-id="5d38f-145">既存の Web サイトの更新</span><span class="sxs-lookup"><span data-stu-id="5d38f-145">Update an existing website</span></span>
- <span data-ttu-id="5d38f-146">既存の Web サイトの削除</span><span class="sxs-lookup"><span data-stu-id="5d38f-146">Delete an existing website</span></span>

<span data-ttu-id="5d38f-147">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-147">The following example illustrates this.</span></span>

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

    <#
        If Ensure is set to "Present" and the website specified in the mandatory input parameters
          does not exist, then create it using the specified parameter values
        Else, if Ensure is set to "Present" and the website does exist, then update its properties
          to match the values provided in the non-mandatory parameter values
        Else, if Ensure is set to "Absent" and the website does not exist, then do nothing
        Else, if Ensure is set to "Absent" and the website does exist, then delete the website
    #>
}
```

<span data-ttu-id="5d38f-148">最後に、`Test-TargetResource` 関数は、`Get-TargetResource` および `Set-TargetResource` と同じパラメーター セットを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d38f-148">Finally, the `Test-TargetResource` function must take the same parameter set as `Get-TargetResource` and `Set-TargetResource`.</span></span> <span data-ttu-id="5d38f-149">`Test-TargetResource` の実装で、キー パラメーターで指定されているリソース インスタンスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-149">In your implementation of `Test-TargetResource`, check the status of the resource instance that is specified in the key parameters.</span></span> <span data-ttu-id="5d38f-150">リソース インスタンスの実際の状態がパラメーター セットで指定された値と一致しない場合は、 `$false` を返します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-150">If the actual status of the resource instance does not match the values specified in the parameter set, return `$false`.</span></span> <span data-ttu-id="5d38f-151">それ以外の場合は、`$true` を返します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-151">Otherwise, return `$true`.</span></span>

<span data-ttu-id="5d38f-152">次のコードでは、`Test-TargetResource` 関数を実装します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-152">The following code implements the `Test-TargetResource` function.</span></span>

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

    # Get the current state
    $currentState = Get-TargetResource -Ensure $Ensure -Name $Name -PhysicalPath $PhysicalPath -State $State -ApplicationPool $ApplicationPool -BindingInfo $BindingInfo -Protocol $Protocol

    # Write-Verbose "Use this cmdlet to deliver information about command processing."

    # Write-Debug "Use this cmdlet to write debug information while troubleshooting."

    # Include logic to
    $result = [System.Boolean]
    # Add logic to test whether the website is present and its status matches the supplied
    # parameter values. If it does, return true. If it does not, return false.
    $result
}
```

> [!NOTE]
> <span data-ttu-id="5d38f-153">簡単にデバッグするには、前の 3 つの関数の実装で `Write-Verbose` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-153">For easier debugging, use the `Write-Verbose` cmdlet in your implementation of the previous three functions.</span></span> <span data-ttu-id="5d38f-154">このコマンドレットは、テキストを詳細メッセージ ストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-154">This cmdlet writes text to the verbose message stream.</span></span> <span data-ttu-id="5d38f-155">既定では、詳細メッセージ ストリームは表示されません。表示するには、 **$VerbosePreference** 変数の値を変更するか、DSC コマンドレットで **Verbose** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-155">By default, the verbose message stream is not displayed, but you can display it by changing the value of the **$VerbosePreference** variable or by using the **Verbose** parameter in the DSC cmdlets = new.</span></span>

### <a name="creating-the-module-manifest"></a><span data-ttu-id="5d38f-156">モジュール マニフェストの作成</span><span class="sxs-lookup"><span data-stu-id="5d38f-156">Creating the module manifest</span></span>

<span data-ttu-id="5d38f-157">最後に、`New-ModuleManifest` コマンドレットを使用して、ご自分のカスタム リソース モジュールに `<ResourceName>.psd1` ファイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-157">Finally, use the `New-ModuleManifest` cmdlet to define a `<ResourceName>.psd1` file for your custom resource module.</span></span> <span data-ttu-id="5d38f-158">このコマンドレットを呼び出すときに、前のセクションで説明したスクリプト モジュール (.psm1) ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-158">When you invoke this cmdlet, reference the script module (.psm1) file described in the previous section.</span></span> <span data-ttu-id="5d38f-159">`Get-TargetResource`、`Set-TargetResource`、および `Test-TargetResource` をエクスポートする関数の一覧に含めます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-159">Include `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` in the list of functions to export.</span></span> <span data-ttu-id="5d38f-160">マニフェスト ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-160">Following is an example manifest file.</span></span>

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

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="5d38f-161">PsDscRunAsCredential のサポート</span><span class="sxs-lookup"><span data-stu-id="5d38f-161">Supporting PsDscRunAsCredential</span></span>

> [!Note]
> <span data-ttu-id="5d38f-162">**PsDscRunAsCredential** は PowerShell 5.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d38f-162">**PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="5d38f-163">**PsDscRunAsCredential** プロパティを [DSC 構成](../configurations/configurations.md)リソース ブロックで使用して、指定した資格情報のもとでリソースを実行する必要があることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-163">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span> <span data-ttu-id="5d38f-164">詳細については、「[ユーザーの資格情報を指定して DSC を実行する](../configurations/runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d38f-164">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="5d38f-165">カスタム リソース内からユーザー コンテキストにアクセスするには、自動変数 `$PsDscContext` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-165">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="5d38f-166">たとえば、次のコードは、リソースが詳細出力ストリームに実行しているユーザー コンテキストを記述します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-166">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if (PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="rebooting-the-node"></a><span data-ttu-id="5d38f-167">Node を再起動する</span><span class="sxs-lookup"><span data-stu-id="5d38f-167">Rebooting the Node</span></span>

<span data-ttu-id="5d38f-168">`Set-TargetResource` 関数で行われるアクションに再起動が必要となる場合、グローバル フラグを使用し、Node の再起動を LCM に指示できます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-168">If the actions taken in your `Set-TargetResource` function require a reboot, you can use a global flag to tell the LCM to reboot the Node.</span></span> <span data-ttu-id="5d38f-169">この再起動は、`Set-TargetResource` 関数の完了直後に行われます。</span><span class="sxs-lookup"><span data-stu-id="5d38f-169">This reboot occurs directly after the `Set-TargetResource` function completes.</span></span>

<span data-ttu-id="5d38f-170">`Set-TargetResource` 関数内で次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="5d38f-170">Inside your `Set-TargetResource` function, add the following line of code.</span></span>

```powershell
# Include this line if the resource requires a system reboot.
$global:DSCMachineStatus = 1
```

<span data-ttu-id="5d38f-171">LCM で Node を再起動するには、 **RebootNodeIfNeeded** フラグを `$true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d38f-171">In order for the LCM to reboot the Node, the **RebootNodeIfNeeded** flag needs to be set to `$true`.</span></span>
<span data-ttu-id="5d38f-172">また、 **ActionAfterReboot** 設定を既定である **ContinueConfiguration** に設定してください。</span><span class="sxs-lookup"><span data-stu-id="5d38f-172">The **ActionAfterReboot** setting should also be set to **ContinueConfiguration** , which is the default.</span></span> <span data-ttu-id="5d38f-173">LCM の構成方法については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」または「[ローカル構成マネージャーの構成 (v4)](../managing-nodes/metaConfig4.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d38f-173">For more information on configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configuring the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>

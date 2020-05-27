---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: Import-DSCResource の使用
ms.openlocfilehash: 1b066e231d158fb5b6333e42c91d24690e9b0223
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692465"
---
# <a name="using-import-dscresource"></a><span data-ttu-id="f5948-103">Import-DSCResource の使用</span><span class="sxs-lookup"><span data-stu-id="f5948-103">Using Import-DSCResource</span></span>

<span data-ttu-id="f5948-104">`Import-DScResource` は動的なキーワードであり、Configuration スクリプト ブロックの内部でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5948-104">`Import-DScResource` is a dynamic keyword, which can only be used inside a Configuration script block.</span></span> <span data-ttu-id="f5948-105">`Import-DSCResource` キーワードは、ご自身の Configuration で必要なリソースをインポートするために使います。</span><span class="sxs-lookup"><span data-stu-id="f5948-105">The `Import-DSCResource` keyword to import any resources needed in your Configuration.</span></span> <span data-ttu-id="f5948-106">`$pshome` の下にあるリソースは自動的にインポートされますが、ご自身の [Configuration](Configurations.md) 内で使用されるすべてのリソースを明示的にインポートするのがやはりベスト プラクティスと考えられます。</span><span class="sxs-lookup"><span data-stu-id="f5948-106">Resources under `$pshome` are imported automatically, but it is still considered best practice to explicitly import all resources used in your [Configuration](Configurations.md).</span></span>

<span data-ttu-id="f5948-107">`Import-DSCResource` の構文は次に示すとおりです。</span><span class="sxs-lookup"><span data-stu-id="f5948-107">The syntax for `Import-DSCResource` is shown below.</span></span>  <span data-ttu-id="f5948-108">モジュールを名前で指定するときは、1 行に 1 つずつ列記する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5948-108">When specifying modules by name, it is a requirement to list each on a new line.</span></span>

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName>] [-ModuleVersion <ModuleVersion>]
```

|<span data-ttu-id="f5948-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5948-109">Parameter</span></span>  |<span data-ttu-id="f5948-110">説明</span><span class="sxs-lookup"><span data-stu-id="f5948-110">Description</span></span>  |
|---------|---------|
|`-Name`|<span data-ttu-id="f5948-111">インポートする必要がある DSC リソースの名前です。</span><span class="sxs-lookup"><span data-stu-id="f5948-111">The DSC resource name(s) that you must import.</span></span> <span data-ttu-id="f5948-112">モジュール名を指定した場合は、このコマンドにより、そのモジュール内でこれらの DSC リソースが検索されます。それ以外の場合は、このコマンドにより、すべての DSC リソース パスで DSC リソースが検索されます。</span><span class="sxs-lookup"><span data-stu-id="f5948-112">If the module name is specified, the command searches for these DSC resources within this module; otherwise the command searches the DSC resources in all DSC resource paths.</span></span> <span data-ttu-id="f5948-113">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f5948-113">Wildcards are supported.</span></span>|
|`-ModuleName`|<span data-ttu-id="f5948-114">モジュール名またはモジュールの指定です。</span><span class="sxs-lookup"><span data-stu-id="f5948-114">The module name, or module specification.</span></span>  <span data-ttu-id="f5948-115">モジュールからインポートするリソースを指定した場合は、このコマンドにより、それらのリソースだけのインポートが試みられます。</span><span class="sxs-lookup"><span data-stu-id="f5948-115">If you specify resources to import from a module, the command will try to import only those resources.</span></span> <span data-ttu-id="f5948-116">モジュールのみを指定した場合は、このコマンドにより、モジュール内のすべての DSC リソースがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="f5948-116">If you specify the module only, the command imports all the DSC resources in the module.</span></span>|
|`-ModuleVersion`|<span data-ttu-id="f5948-117">PowerShell 5.0 以降では、構成で使用するモジュールのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5948-117">Beginning in PowerShell 5.0, you can specify which version of a module a configuration should use.</span></span> <span data-ttu-id="f5948-118">詳細については、「[インストールされているリソースの特定のバージョンをインポートする](sxsresource.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5948-118">For more information, see [Import a specific version of an installed resource](sxsresource.md).</span></span>|

```powershell
Import-DscResource -ModuleName xActiveDirectory
```

## <a name="example-use-import-dscresource-within-a-configuration"></a><span data-ttu-id="f5948-119">例:構成内で Import-DSCResource を使用する</span><span class="sxs-lookup"><span data-stu-id="f5948-119">Example: Use Import-DSCResource within a configuration</span></span>

```powershell
Configuration MSDSCConfiguration
{
    # Search for and imports Service, File, and Registry from the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration -Name Service, File, Registry

    # Search for and import Resource1 from the module that defines it.
    # If only –Name parameter is used then resources can belong to different PowerShell modules as well.
    # TimeZone resource is from the ComputerManagementDSC module which is not installed by default.
    # As a best practice, list each requirement on a different line if possible.  This makes reviewing
    # multiple changes in source control a bit easier.
    Import-DSCResource -Name File
    Import-DSCResource -Name TimeZone

    # Search for and import all DSC resources inside the module PSDesiredStateConfiguration.
    # When specifying the modulename parameter, it is a requirement to list each on a new line.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration
    # In PowerShell 5.0 and later, you can specify a ModuleVersion parameter
    Import-DSCResource -ModuleName ComputerManagementDsc -ModuleVersion 6.0.0.0
...
```

> [!NOTE]
> <span data-ttu-id="f5948-120">同じコマンド内でリソース名およびモジュール名に複数の値を指定することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f5948-120">Specifying multiple values for Resource names and modules names in same command are not supported.</span></span> <span data-ttu-id="f5948-121">同じリソースが複数のモジュールに存在する場合、どのモジュールからどのリソースが読み込まれるかについて、決定論的でない動作が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="f5948-121">It can have non-deterministic behavior about which resource to load from which module in case same resource exists in multiple modules.</span></span> <span data-ttu-id="f5948-122">次のコマンドでは、コンパイル中にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f5948-122">Below command will result in error during compilation.</span></span>
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

<span data-ttu-id="f5948-123">Name パラメーターのみを使用するときに考慮すべき事項:</span><span class="sxs-lookup"><span data-stu-id="f5948-123">Things to consider when using only the Name parameter:</span></span>

- <span data-ttu-id="f5948-124">コンピューターにインストールされているモジュールの数によっては、リソースを大量に消費する操作です。</span><span class="sxs-lookup"><span data-stu-id="f5948-124">It is a resource-intensive operation depending on the number of modules installed on machine.</span></span>
- <span data-ttu-id="f5948-125">指定した名前で最初に見つかったリソースが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="f5948-125">It will load the first resource found with the given name.</span></span> <span data-ttu-id="f5948-126">同じ名前で複数のリソースがインストールされている場合は、間違ったリソースが読み込まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5948-126">In the case where there is more than one resource with same name installed, it could load the wrong resource.</span></span>

<span data-ttu-id="f5948-127">推奨される使用方法は、以下で説明するように、`-Name` パラメーターと共に `–ModuleName` を指定することです。</span><span class="sxs-lookup"><span data-stu-id="f5948-127">The recommended usage is to specify `–ModuleName` with the `-Name` parameter, as described below.</span></span>

<span data-ttu-id="f5948-128">この使用方法には次のようなメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="f5948-128">This usage has the following benefits:</span></span>

- <span data-ttu-id="f5948-129">指定したリソースに検索範囲が制限されるため、パフォーマンスへの影響が減少します。</span><span class="sxs-lookup"><span data-stu-id="f5948-129">It reduces the performance impact by limiting the search scope for the specified resource.</span></span>
- <span data-ttu-id="f5948-130">リソースが定義されているモジュールを明示的に定義することで、正しいリソースが確実に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="f5948-130">It explicitly defines the module defining the resource, ensuring the correct resource is loaded.</span></span>

> [!NOTE]
> <span data-ttu-id="f5948-131">PowerShell 5.0 では、DSC リソースに複数バージョンを用意することができ、コンピューターにその複数のバージョンをサイド バイ サイドでインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f5948-131">In PowerShell 5.0, DSC resources can have multiple versions, and versions can be installed on a computer side-by-side.</span></span> <span data-ttu-id="f5948-132">これを実装するには、リソース モジュールの複数のバージョンを同じモジュール フォルダーに格納します。</span><span class="sxs-lookup"><span data-stu-id="f5948-132">This is implemented by having multiple versions of a resource module that are contained in the same module folder.</span></span>
> <span data-ttu-id="f5948-133">詳細については、「[複数のバージョンがあるリソースの使用](sxsresource.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5948-133">For more information, see [Using resources with multiple versions](sxsresource.md).</span></span>

## <a name="intellisense-with-import-dscresource"></a><span data-ttu-id="f5948-134">Import-DSCResource での IntelliSense</span><span class="sxs-lookup"><span data-stu-id="f5948-134">Intellisense with Import-DSCResource</span></span>

<span data-ttu-id="f5948-135">ISE で DSC の構成を作成するとき、PowerShell ではリソースおよびリソースのプロパティに対して IntelliSence が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f5948-135">When authoring the DSC configuration in ISE, PowerShell provides IntelliSence for resources and resource properties.</span></span> <span data-ttu-id="f5948-136">`$pshome` モジュール パスの下にあるリソースの定義が、自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="f5948-136">Resource definitions under the `$pshome` module path are loaded automatically.</span></span> <span data-ttu-id="f5948-137">`Import-DSCResource` キーワードを使ってリソースをインポートすると、指定したリソース定義が追加されて、インポートされたリソースのスキーマを含むように IntelliSence が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="f5948-137">When you import resources using the `Import-DSCResource` keyword, the specified resource definitions are added and Intellisense is expanded to include the imported resource's schema.</span></span>

![リソースの IntelliSense](media/import-dscresource/resource-intellisense.png)

> [!NOTE]
> <span data-ttu-id="f5948-139">PowerShell 5.0 以降では、DSC リソースとそのプロパティ用の ISE に対して Tab 補完機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="f5948-139">Beginning in PowerShell 5.0, tab completion was added to the ISE for DSC resources and their properties.</span></span> <span data-ttu-id="f5948-140">詳しくは、[リソース](../resources/resources.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5948-140">For more information, see [Resources](../resources/resources.md).</span></span>

<span data-ttu-id="f5948-141">Configuration をコンパイルするとき、PowerShell では、インポートされたリソース定義を使って、構成内のすべてのリソース ブロックが検証されます。</span><span class="sxs-lookup"><span data-stu-id="f5948-141">When compiling the Configuration, PowerShell uses the imported resource definitions to validate all resource blocks in the configuration.</span></span>
<span data-ttu-id="f5948-142">リソースのスキーマ定義を使って、各リソース ブロックで次の規則が検証されます。</span><span class="sxs-lookup"><span data-stu-id="f5948-142">Each resource block is validated, using the resource's schema definition, for the following rules.</span></span>

- <span data-ttu-id="f5948-143">スキーマで定義されているプロパティのみが使用されている。</span><span class="sxs-lookup"><span data-stu-id="f5948-143">Only properties defined in schema are used.</span></span>
- <span data-ttu-id="f5948-144">各プロパティのデータ型が正しい。</span><span class="sxs-lookup"><span data-stu-id="f5948-144">The data types for each property are correct.</span></span>
- <span data-ttu-id="f5948-145">キー プロパティが指定されている。</span><span class="sxs-lookup"><span data-stu-id="f5948-145">Keys properties are specified.</span></span>
- <span data-ttu-id="f5948-146">読み取り専用プロパティが使用されていない。</span><span class="sxs-lookup"><span data-stu-id="f5948-146">No read-only property is used.</span></span>
- <span data-ttu-id="f5948-147">値の検証が型にマップされる。</span><span class="sxs-lookup"><span data-stu-id="f5948-147">Validation on value maps types.</span></span>

<span data-ttu-id="f5948-148">以下のような構成について考えます。</span><span class="sxs-lookup"><span data-stu-id="f5948-148">Consider the following configuration:</span></span>

```powershell
Configuration SchemaValidationInCorrectEnumValue
{
    # It is best practice to explicitly import all resources used in your Configuration.
    # This includes resources that are imported automatically, like WindowsFeature.
    Import-DSCResource -Name WindowsFeature
    Node localhost
    {
        WindowsFeature ROLE1
        {
            Name = "Telnet-Client"
            Ensure = "Invalid"
        }
    }
}
```

<span data-ttu-id="f5948-149">この Configuration をコンパイルすると、結果はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="f5948-149">Compiling this Configuration results in an error.</span></span>

```output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values 'Invalid' is not supported or valid for property 'Ensure' on class 'WindowsFeature'. Please specify only supported values: Present, Absent.
```

<span data-ttu-id="f5948-150">IntelliSence とスキーマ検証により、解析とコンパイル時の間にさらに多くのエラーをキャッチでき、実行時の問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="f5948-150">Intellisense and schema validation allow you to catch more errors during parse and compilation time, avoiding complications at run time.</span></span>

> [!NOTE]
> <span data-ttu-id="f5948-151">各 DSC リソースは、名前と、リソースのスキーマによって定義された **FriendlyName** を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="f5948-151">Each DSC resource can have a name, and a **FriendlyName** defined by the resource's schema.</span></span> <span data-ttu-id="f5948-152">"MSFT_ServiceResource.shema.mof" の先頭の 2 行を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f5948-152">Below are the first two lines of "MSFT_ServiceResource.shema.mof".</span></span>
>
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
>
> <span data-ttu-id="f5948-153">このリソースを Configuration で使用するときは、**MSFT_ServiceResource** または **Service** を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5948-153">When using this resource in a Configuration, you can specify **MSFT_ServiceResource** or **Service**.</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="f5948-154">PowerShell の v4 と v5 の違い</span><span class="sxs-lookup"><span data-stu-id="f5948-154">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="f5948-155">Configuration を作成するときに、複数の相違点が PowerShell 4.0 と PowerShell 5.0 以降の間に存在します。</span><span class="sxs-lookup"><span data-stu-id="f5948-155">There are multiple differences you see when authoring Configurations in PowerShell 4.0 vs. PowerShell 5.0 and later.</span></span> <span data-ttu-id="f5948-156">このセクションでは、特にこの記事に関連する相違点を示します。</span><span class="sxs-lookup"><span data-stu-id="f5948-156">This section will highlight the differences that you see relevant to this article.</span></span>

### <a name="multiple-resource-versions"></a><span data-ttu-id="f5948-157">複数のリソース バージョン</span><span class="sxs-lookup"><span data-stu-id="f5948-157">Multiple Resource Versions</span></span>

<span data-ttu-id="f5948-158">複数のバージョンのリソースのサイド バイ サイドでのインストールと使用は、PowerShell 4.0 ではサポートされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="f5948-158">Installing and using multiple versions of resources side by side was not supported in PowerShell 4.0.</span></span> <span data-ttu-id="f5948-159">リソースをご自身の Configuration にインポートするときに問題がある場合は、インストールされているリソースのバージョンが 1 つだけであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5948-159">If you notice issues importing resources into your Configuration, ensure that you only have one version of the resource installed.</span></span>

<span data-ttu-id="f5948-160">次の図では、2 つのバージョンの **xPSDesiredStateConfiguration** モジュールがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f5948-160">In the image below, two versions of the **xPSDesiredStateConfiguration** module are installed.</span></span>

![修正された複数リソース バージョン](media/import-dscresource/multiple-resource-versions-broken.png)

<span data-ttu-id="f5948-162">必要なモジュールのバージョンの内容を、モジュール ディレクトリの最上位レベルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f5948-162">Copy the contents of your desired module version to the top level of the module directory.</span></span>

![修正された複数リソース バージョン](media/import-dscresource/multiple-resource-versions-fixed.png)

### <a name="resource-location"></a><span data-ttu-id="f5948-164">リソースの場所</span><span class="sxs-lookup"><span data-stu-id="f5948-164">Resource location</span></span>

<span data-ttu-id="f5948-165">Configuration を作成してコンパイルするとき、[PSModulePath](/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path) で指定した任意のディレクトリにリソースを格納できます。</span><span class="sxs-lookup"><span data-stu-id="f5948-165">When authoring and compiling Configurations, your resources can be stored in any directory specified by your [PSModulePath](/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path).</span></span> <span data-ttu-id="f5948-166">PowerShell 4.0 の LCM では、すべての DSC リソース モジュールが "Program Files\WindowsPowerShell\Modules" または `$pshome\Modules` に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5948-166">In PowerShell 4.0, the LCM requires all DSC resource modules to be stored under "Program Files\WindowsPowerShell\Modules" or `$pshome\Modules`.</span></span> <span data-ttu-id="f5948-167">PowerShell 5.0 以降では、この要件はなくなり、`PSModulePath` で指定した任意のディレクトリにリソース モジュールを格納できます。</span><span class="sxs-lookup"><span data-stu-id="f5948-167">Beginning in PowerShell 5.0, this requirement was removed, and resource modules can be stored in any directory specified by `PSModulePath`.</span></span>

### <a name="moduleversion-added"></a><span data-ttu-id="f5948-168">ModuleVersion の追加</span><span class="sxs-lookup"><span data-stu-id="f5948-168">ModuleVersion added</span></span>

<span data-ttu-id="f5948-169">PowerShell 5.0 以降では、`-ModuleVersion` パラメーターを使用すると、構成内で使用するモジュールのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5948-169">Beginning in PowerShell 5.0, the `-ModuleVersion` parameter allows you to specify which version of a module to use within your configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5948-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5948-170">See also</span></span>

- [<span data-ttu-id="f5948-171">リソース</span><span class="sxs-lookup"><span data-stu-id="f5948-171">Resources</span></span>](../resources/resources.md)

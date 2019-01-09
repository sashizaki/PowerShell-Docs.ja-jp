---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: Import-DSCResource の使用
ms.openlocfilehash: 6bc3c1aa1d34a05e3188666da825322235c0672e
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402773"
---
# <a name="using-import-dscresource"></a><span data-ttu-id="0237b-103">Import-DSCResource の使用</span><span class="sxs-lookup"><span data-stu-id="0237b-103">Using Import-DSCResource</span></span>

<span data-ttu-id="0237b-104">`Import-DScResource` 動的なキーワードは、構成スクリプト ブロック内でのみ使用できますです。</span><span class="sxs-lookup"><span data-stu-id="0237b-104">`Import-DScResource` is a dynamic keyword, which can only be used inside a Configuration script block.</span></span> <span data-ttu-id="0237b-105">`Import-DSCResource`構成に必要なすべてのリソースをインポートするキーワード。</span><span class="sxs-lookup"><span data-stu-id="0237b-105">The `Import-DSCResource` keyword to import any resources needed in your Configuration.</span></span> <span data-ttu-id="0237b-106">下にあるリソース`$phsome`は自動的に、インポートで使用されるすべてのリソースを明示的にインポートするベスト プラクティスをまだと見なされますが、[構成](Configurations.md)します。</span><span class="sxs-lookup"><span data-stu-id="0237b-106">Resources under `$phsome` are imported automatically, but it is still considered best practice to explicitly import all resources used in your [Configuration](Configurations.md).</span></span>

<span data-ttu-id="0237b-107">構文は、`Import-DSCResource`を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0237b-107">The syntax for `Import-DSCResource` is shown below.</span></span>

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName(s)>]
```

|<span data-ttu-id="0237b-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0237b-108">Parameter</span></span>  |<span data-ttu-id="0237b-109">説明</span><span class="sxs-lookup"><span data-stu-id="0237b-109">Description</span></span>  |
|---------|---------|
|`-Name`|<span data-ttu-id="0237b-110">DSC リソースの名前をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0237b-110">The DSC resource name(s) that you must import.</span></span> <span data-ttu-id="0237b-111">コマンドで検索します。 このモジュール内でこれらの DSC リソース モジュール名が指定されている場合それ以外の場合、コマンドは、すべての DSC リソースのパスでの DSC リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="0237b-111">If the module name is specified, the command searches for these DSC resources within this module; otherwise the command searches the DSC resources in all DSC resource paths.</span></span> <span data-ttu-id="0237b-112">ワイルド カードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0237b-112">Wildcards are supported.</span></span>|
|`-ModuleName`|<span data-ttu-id="0237b-113">コンテナー モジュール名、またはモジュール スペシフィケーションします。</span><span class="sxs-lookup"><span data-stu-id="0237b-113">The container module name(s), or module specification(s).</span></span>  <span data-ttu-id="0237b-114">モジュールからインポートするリソースを指定すると、コマンドはリソースのみをインポートしようとします。</span><span class="sxs-lookup"><span data-stu-id="0237b-114">If you specify resources to import from a module, the command will try to import only those resources.</span></span> <span data-ttu-id="0237b-115">モジュールのみを指定する場合、コマンドは、モジュール内のすべての DSC リソースをインポートします。</span><span class="sxs-lookup"><span data-stu-id="0237b-115">If you specify the module only, the command imports all the DSC resources in the module.</span></span>|

<span data-ttu-id="0237b-116">は、ワイルドカードを使用することができます、`-Name`パラメーターを使用する場合`Import-DSCResource`します。</span><span class="sxs-lookup"><span data-stu-id="0237b-116">You can use wildcards with the `-Name` parameter when using `Import-DSCResource`.</span></span>

```powershell
Import-DscResource -Name * -ModuleName xActiveDirectory;
```

## <a name="example-use-import-dscresource-within-a-configuration"></a><span data-ttu-id="0237b-117">次に例を示します。Import-dscresource を使用して、構成内で</span><span class="sxs-lookup"><span data-stu-id="0237b-117">Example: Use Import-DSCResource within a configuration</span></span>

```powershell
Configuration MSDSCConfiguration
{
    # Search for and imports Service, File, and Registry from the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName MS_DSC1 -name Service, File, Registry

    # Search for and import Resource1 from the module that defines it.
    # If only –Name parameter is used then resources can belong to different PowerShell modules as well.
    # TimeZone resource is from the ComputerManagementDSC module which is not installed by default.
    Import-DSCResource -Name File, TimeZone

    # Search for and import all DSC resources inside the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration
...
```

> [!NOTE]
> <span data-ttu-id="0237b-118">同じコマンドでリソース名とモジュール名の複数の値を指定することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0237b-118">Specifying multiple values for Resource names and modules names in same command are not supported.</span></span> <span data-ttu-id="0237b-119">非確定的な動作を複数のモジュールで同じリソースが存在する場合は、どのモジュールから読み込むには、どのリソースに関することができます。</span><span class="sxs-lookup"><span data-stu-id="0237b-119">It can have non-deterministic behavior about which resource to load from which module in case same resource exists in multiple modules.</span></span> <span data-ttu-id="0237b-120">次のコマンドは、コンパイル中にエラーに発生します。</span><span class="sxs-lookup"><span data-stu-id="0237b-120">Below command will result in error during compilation.</span></span>
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

<span data-ttu-id="0237b-121">名前のパラメーターのみを使用するときに考慮すべき事項:</span><span class="sxs-lookup"><span data-stu-id="0237b-121">Things to consider when using only the Name parameter:</span></span>

- <span data-ttu-id="0237b-122">コンピューターにインストールされているモジュールの数に応じてリソースを消費する操作です。</span><span class="sxs-lookup"><span data-stu-id="0237b-122">It is a resource-intensive operation depending on the number of modules installed on machine.</span></span>
- <span data-ttu-id="0237b-123">指定した名前で見つかった最初のリソースが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="0237b-123">It will load the first resource found with the given name.</span></span> <span data-ttu-id="0237b-124">場合は、間違ったリソースを読み込むことがインストールされている同じ名前の 1 つ以上のリソースがある場合。</span><span class="sxs-lookup"><span data-stu-id="0237b-124">In the case where there is more than one resource with same name installed, it could load the wrong resource.</span></span>

<span data-ttu-id="0237b-125">推奨される使用法は指定`–ModuleName`で、`-Name`パラメーターは、次のようです。</span><span class="sxs-lookup"><span data-stu-id="0237b-125">The recommended usage is to specify `–ModuleName` with the `-Name` parameter, as described below.</span></span>

<span data-ttu-id="0237b-126">この使用法には、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="0237b-126">This usage has the following benefits:</span></span>

- <span data-ttu-id="0237b-127">指定したリソースの検索範囲を制限することによってパフォーマンスに与える影響が減少します。</span><span class="sxs-lookup"><span data-stu-id="0237b-127">It reduces the performance impact by limiting the search scope for the specified resource.</span></span>
- <span data-ttu-id="0237b-128">適切なリソースが読み込まれることを確認、リソースを定義するモジュールを明示的に定義します。</span><span class="sxs-lookup"><span data-stu-id="0237b-128">It explicitly defines the module defining the resource, ensuring the correct resource is loaded.</span></span>

> [!NOTE]
> <span data-ttu-id="0237b-129">PowerShell 5.0 では、DSC リソースに複数バージョンを用意することができ、コンピューターにその複数のバージョンをサイド バイ サイドでインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0237b-129">In PowerShell 5.0, DSC resources can have multiple versions, and versions can be installed on a computer side-by-side.</span></span> <span data-ttu-id="0237b-130">これを実装するには、リソース モジュールの複数のバージョンを同じモジュール フォルダーに格納します。</span><span class="sxs-lookup"><span data-stu-id="0237b-130">This is implemented by having multiple versions of a resource module that are contained in the same module folder.</span></span>
> <span data-ttu-id="0237b-131">詳細については、「[複数のバージョンがあるリソースの使用](sxsresource.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0237b-131">For more information, see [Using resources with multiple versions](sxsresource.md).</span></span>

## <a name="intellisense-with-import-dscresource"></a><span data-ttu-id="0237b-132">Import-dscresource の Intellisense</span><span class="sxs-lookup"><span data-stu-id="0237b-132">Intellisense with Import-DSCResource</span></span>

<span data-ttu-id="0237b-133">ISE で DSC 構成を作成するときに、PowerShell は、リソースとリソースのプロパティの IntelliSence を提供します。</span><span class="sxs-lookup"><span data-stu-id="0237b-133">When authoring the DSC configuration in ISE, PowerShell provides IntelliSence for resources and resource properties.</span></span> <span data-ttu-id="0237b-134">リソースの定義、`$pshome`モジュールのパスが自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="0237b-134">Resource definitions under the `$pshome` module path are loaded automatically.</span></span> <span data-ttu-id="0237b-135">使用してリソースをインポートするときに、`Import-DSCResource`キーワード、指定したリソース定義を追加および Intellisense を拡張して、インポートされたリソースのスキーマが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0237b-135">When you import resources using the `Import-DSCResource` keyword, the specified resource definitions are added and Intellisense is expanded to include the imported resource's schema.</span></span>

![リソースの Intellisense](/media/resource-intellisense.png)

> [!NOTE]
> <span data-ttu-id="0237b-137">PowerShell 5.0 以降では、タブ補完は、DSC リソースとそのプロパティの ISE に追加されました。</span><span class="sxs-lookup"><span data-stu-id="0237b-137">Beginning in PowerShell 5.0, tab completion was added to the ISE for DSC resources and their properties.</span></span> <span data-ttu-id="0237b-138">詳細については、次を参照してください。[リソース](../resources/resources.md)します。</span><span class="sxs-lookup"><span data-stu-id="0237b-138">For more information, see [Resources](../resources/resources.md).</span></span>

<span data-ttu-id="0237b-139">構成をコンパイルするときに、PowerShell は、構成内のすべてのリソース ブロックを検証するのにインポートされたリソース定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="0237b-139">When compiling the Configuration, PowerShell uses the imported resource definitions to validate all resource blocks in the configuration.</span></span>
<span data-ttu-id="0237b-140">各リソース ブロックは、次の規則のリソースのスキーマ定義を使用して検証されます。</span><span class="sxs-lookup"><span data-stu-id="0237b-140">Each resource block is validated, using the resource's schema definition, for the following rules.</span></span>

- <span data-ttu-id="0237b-141">スキーマで定義されたプロパティのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0237b-141">Only properties defined in schema are used.</span></span>
- <span data-ttu-id="0237b-142">各プロパティのデータ型が正しいです。</span><span class="sxs-lookup"><span data-stu-id="0237b-142">The data types for each property are correct.</span></span>
- <span data-ttu-id="0237b-143">キー プロパティが指定されます。</span><span class="sxs-lookup"><span data-stu-id="0237b-143">Keys properties are specified.</span></span>
- <span data-ttu-id="0237b-144">読み取り専用プロパティは使用されません。</span><span class="sxs-lookup"><span data-stu-id="0237b-144">No read-only property is used.</span></span>
- <span data-ttu-id="0237b-145">値の検証は、型をマップします。</span><span class="sxs-lookup"><span data-stu-id="0237b-145">Validation on value maps types.</span></span>

<span data-ttu-id="0237b-146">次の構成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="0237b-146">Consider the following configuration:</span></span>

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
            Name = “Telnet-Client”
            Ensure = “Invalid”
        }
    }
}
```

<span data-ttu-id="0237b-147">この構成の結果、エラーをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="0237b-147">Compiling this Configuration results in an error.</span></span>

```output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values ‘Invalid’ is not supported or valid for property ‘Ensure’ on class ‘WindowsFeature’. Please specify only supported values: Present, Absent.
```

<span data-ttu-id="0237b-148">Intellisense およびスキーマ検証を使用すると、実行時に複雑な問題を回避する解析とコンパイル時に多くのエラーをキャッチできます。</span><span class="sxs-lookup"><span data-stu-id="0237b-148">Intellisense and schema validation allow you to catch more errors during parse and compilation time, avoiding complications at run time.</span></span>

> [!NOTE]
> <span data-ttu-id="0237b-149">各 DSC リソースの名前を付けることができます、 **FriendlyName**リソースのスキーマで定義します。</span><span class="sxs-lookup"><span data-stu-id="0237b-149">Each DSC resource can have a name, and a **FriendlyName** defined by the resource's schema.</span></span> <span data-ttu-id="0237b-150">"MSFT_ServiceResource.shema.mof"の最初の 2 つの行を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0237b-150">Below are the first two lines of "MSFT_ServiceResource.shema.mof".</span></span>
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
> <span data-ttu-id="0237b-151">このリソースを使用して、構成では場合、は、指定**MSFT_ServiceResource**または**サービス**します。</span><span class="sxs-lookup"><span data-stu-id="0237b-151">When using this resource in a Configuration, you can specify **MSFT_ServiceResource** or **Service**.</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="0237b-152">PowerShell v4 および v5 の違い</span><span class="sxs-lookup"><span data-stu-id="0237b-152">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="0237b-153">PowerShell 4.0 の vs での構成を作成するときに「する複数違いがあります。PowerShell 5.0 以降。</span><span class="sxs-lookup"><span data-stu-id="0237b-153">There are multiple differences you see when authoring Configurations in PowerShell 4.0 vs. PowerShell 5.0 and later.</span></span> <span data-ttu-id="0237b-154">このセクションでは、相違点を強調表示されますこの記事に関連する表示します。</span><span class="sxs-lookup"><span data-stu-id="0237b-154">This section will highlight the differences that you see relevant to this article.</span></span>

### <a name="multiple-resource-versions"></a><span data-ttu-id="0237b-155">複数のリソース バージョン</span><span class="sxs-lookup"><span data-stu-id="0237b-155">Multiple Resource Versions</span></span>

<span data-ttu-id="0237b-156">インストールとサイド バイ サイドのリソースの複数のバージョンを使用した、PowerShell 4.0 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0237b-156">Installing and using multiple versions of resources side by side was not supported in PowerShell 4.0.</span></span> <span data-ttu-id="0237b-157">問題のリソースの構成をインポートする場合は、インストールされているリソースの 1 つのバージョンのみがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0237b-157">If you notice issues importing resources into your Configuration, ensure that you only have one version of the resource installed.</span></span>

<span data-ttu-id="0237b-158">2 つのバージョンの次の図で、 **xPSDesiredStateConfiguration**モジュールがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="0237b-158">In the image below, two versions of the **xPSDesiredStateConfiguration** module are installed.</span></span>

![複数のリソース バージョンを修正しました](/media/multiple-resource-versions-broken.md)

<span data-ttu-id="0237b-160">モジュール ディレクトリの最上位レベルに、必要なモジュールのバージョンの内容をコピーします。</span><span class="sxs-lookup"><span data-stu-id="0237b-160">Copy the contents of your desired module version to the top level of the module directory.</span></span>

![複数のリソース バージョンを修正しました](/media/multiple-resource-versions-fixed.md)

### <a name="resource-location"></a><span data-ttu-id="0237b-162">リソースの場所</span><span class="sxs-lookup"><span data-stu-id="0237b-162">Resource location</span></span>

<span data-ttu-id="0237b-163">指定された任意のディレクトリに、リソースを格納できる作成と構成のコンパイル、 [PSModulePath](/powershell/developer/module/modifying-the-psmodulepath-installation-path)します。</span><span class="sxs-lookup"><span data-stu-id="0237b-163">When authoring and compiling Configurations, your resources can be stored in any directory specified by your [PSModulePath](/powershell/developer/module/modifying-the-psmodulepath-installation-path).</span></span> <span data-ttu-id="0237b-164">PowerShell 4.0 のでは、LCM は、"プログラム \windowspowershell\modules"を格納するすべての DSC リソース モジュールを必要があります。 または`$pshome\Modules`します。</span><span class="sxs-lookup"><span data-stu-id="0237b-164">In PowerShell 4.0, the LCM requires all DSC resource modules to be stored under "Program Files\WindowsPowerShell\Modules" or `$pshome\Modules`.</span></span> <span data-ttu-id="0237b-165">PowerShell 5.0 以降では、この要件が削除され、リソース モジュールで指定された任意のディレクトリに格納できる`PSModulePath`します。</span><span class="sxs-lookup"><span data-stu-id="0237b-165">Beginning in PowerShell 5.0, this requirement was removed, and resource modules can be stored in any directory specified by `PSModulePath`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0237b-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="0237b-166">See also</span></span>

- [<span data-ttu-id="0237b-167">リソース</span><span class="sxs-lookup"><span data-stu-id="0237b-167">Resources</span></span>](../resources/resources.md)

---
ms.date: 07/23/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース
ms.openlocfilehash: 6ab831c9d423c6189951b43bfab92f800366ceca
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87777931"
---
# <a name="dsc-resources"></a><span data-ttu-id="17ae8-103">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-103">DSC Resources</span></span>

> <span data-ttu-id="17ae8-104">適用対象: Windows PowerShell 4.0 以上。</span><span class="sxs-lookup"><span data-stu-id="17ae8-104">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="17ae8-105">概要</span><span class="sxs-lookup"><span data-stu-id="17ae8-105">Overview</span></span>

<span data-ttu-id="17ae8-106">Desired State Configuration (DSC) リソースは、DSC 構成の構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="17ae8-106">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="17ae8-107">リソースは、構成 (スキーマ) 可能なプロパティを公開し、また、指定されたことを実現するためにローカル構成マネージャー (LCM) が呼び出す PowerShell スクリプト関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="17ae8-107">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="17ae8-108">リソースでは、ファイルのように汎用的なものをモデル化したり、IIS サーバー設定のように具体的なものをモデル化したりできます。</span><span class="sxs-lookup"><span data-stu-id="17ae8-108">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="17ae8-109">リソースなどのグループは、DSC モジュールに結合されます。DSC モジュールでは、リソースの使用目的を識別するためのメタデータが含まれている移植可能な構造にすべての必須ファイルが編成されます。</span><span class="sxs-lookup"><span data-stu-id="17ae8-109">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="17ae8-110">各リソースには、[Configuration](../configurations/configurations.md) でリソースを使用するために必要な構文を決定する\*スキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="17ae8-110">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span>
<span data-ttu-id="17ae8-111">リソースのスキーマは、次のように定義できます。</span><span class="sxs-lookup"><span data-stu-id="17ae8-111">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="17ae8-112">`Schema.Mof` ファイル:ほとんどのリソースでは、[マネージド オブジェクト フォーマット](/windows/desktop/wmisdk/managed-object-format--mof-)を使用して、`schema.mof` ファイルに "_スキーマ_" を定義します。</span><span class="sxs-lookup"><span data-stu-id="17ae8-112">`Schema.Mof` file: Most resources define their _schema_ in a `schema.mof` file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="17ae8-113">`<Resource Name>.schema.psm1` ファイル:[複合リソース](../configurations/compositeConfigs.md)では、[パラメーター ブロック](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters)を使用して、`<ResourceName>.schema.psm1` ファイルに_スキーマ_を定義します。</span><span class="sxs-lookup"><span data-stu-id="17ae8-113">`<Resource Name>.schema.psm1` file: [Composite Resources](../configurations/compositeConfigs.md) define their _schema_ in a `<ResourceName>.schema.psm1` file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="17ae8-114">`<Resource Name>.psm1` ファイル:クラス ベースの DSC リソースは、クラス定義で "_スキーマ_" を定義します。</span><span class="sxs-lookup"><span data-stu-id="17ae8-114">`<Resource Name>.psm1` file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="17ae8-115">構文の項目は Class プロパティとして表されます。</span><span class="sxs-lookup"><span data-stu-id="17ae8-115">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="17ae8-116">詳細については、「[about_Remote](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17ae8-116">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="17ae8-117">DSC リソースの構文を取得するには、**Syntax** パラメーターを指定して、[Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="17ae8-117">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the **Syntax** parameter.</span></span> <span data-ttu-id="17ae8-118">この使用法は、**Syntax** パラメーターを指定して、[Get-Command](/powershell/module/microsoft.powershell.core/get-command) を使用して、コマンドレットの構文を取得する場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="17ae8-118">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the **Syntax** parameter to get cmdlet syntax.</span></span> <span data-ttu-id="17ae8-119">表示される出力には、指定したリソースのリソース ブロックに使用されているテンプレートが示されます。</span><span class="sxs-lookup"><span data-stu-id="17ae8-119">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="17ae8-120">このリソースの構文は今後変更される可能性がありますが、表示される出力は以下ような出力になります。</span><span class="sxs-lookup"><span data-stu-id="17ae8-120">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="17ae8-121">コマンドレットの構文と同様に、角かっこで囲まれた "_キー_" は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="17ae8-121">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="17ae8-122">型には、各キーで想定されているデータの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="17ae8-122">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="17ae8-123">**Ensure** キーは既定値が "Present" なので省略可能です。</span><span class="sxs-lookup"><span data-stu-id="17ae8-123">The **Ensure** key is optional because it defaults to "Present".</span></span>

```output
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

> [!NOTE]
> <span data-ttu-id="17ae8-124">PowerShell バージョン 7.0 より前のバージョンでは、`Get-DscResource` によるクラス ベースの DSC リソースの検出は行われません。</span><span class="sxs-lookup"><span data-stu-id="17ae8-124">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="17ae8-125">Configuration 内では、スプーラー サービスが実行されていることを確認 (**Ensure**) するため、**Service** リソース ブロックを次のようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="17ae8-125">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="17ae8-126">Configuration でリソースを使用する前に、[Import-DSCResource](../configurations/import-dscresource.md) を使用してリソースをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17ae8-126">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }
    }
}
```

<span data-ttu-id="17ae8-127">Configuration には、同じリソースの種類の複数インスタンスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="17ae8-127">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="17ae8-128">各インスタンスには一意の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="17ae8-128">Each instance must be uniquely named.</span></span> <span data-ttu-id="17ae8-129">次の例では、"DHCP" サービスを構成するために 2 つ目の **Service** リソース ブロックが追加されています。</span><span class="sxs-lookup"><span data-stu-id="17ae8-129">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }

        # To configure a second service resource block, add another Service resource block and use a unique name.
        Service "DHCP:Running"
        {
            Name = "DHCP"
            State = "Running"
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="17ae8-130">PowerShell 5.0 以降、IntelliSense が DSC に追加されました。</span><span class="sxs-lookup"><span data-stu-id="17ae8-130">Beginning in PowerShell 5.0, IntelliSense was added for DSC.</span></span> <span data-ttu-id="17ae8-131">この新機能を使用すると、<kbd>Tab</kbd> キーと <kbd>Ctrl</kbd>+<kbd>Space</kbd> キーを使用してキー名をオートコンプリートすることができます。</span><span class="sxs-lookup"><span data-stu-id="17ae8-131">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![Tab 補完機能を使用したリソース IntelliSense](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="17ae8-133">リソースの種類</span><span class="sxs-lookup"><span data-stu-id="17ae8-133">Types of resources</span></span>

<span data-ttu-id="17ae8-134">Windows には組み込みリソースが付属しており、Linux には OS 固有のリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="17ae8-134">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="17ae8-135">[ノード間の依存関係](../configurations/crossNodeDependencies.md)のリソース、パッケージ管理リソース、および[コミュニティ所有の管理リソース](https://github.com/dsccommunity)があります。</span><span class="sxs-lookup"><span data-stu-id="17ae8-135">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as[community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="17ae8-136">前述の手順を使用して、これらのリソースの構文とその使用方法を判断できます。</span><span class="sxs-lookup"><span data-stu-id="17ae8-136">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="17ae8-137">これらのリソースを提供するページは、「**関連項目**」にアーカイブされています。</span><span class="sxs-lookup"><span data-stu-id="17ae8-137">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="17ae8-138">Windows 組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-138">Windows built-in resources</span></span>

- [<span data-ttu-id="17ae8-139">アーカイブ リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-139">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="17ae8-140">環境リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-140">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="17ae8-141">ファイル リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-141">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="17ae8-142">グループ リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-142">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="17ae8-143">GroupSet リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-143">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="17ae8-144">ログ リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-144">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="17ae8-145">パッケージ リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-145">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="17ae8-146">ProcessSet リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-146">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="17ae8-147">レジストリ リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-147">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="17ae8-148">スクリプト リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-148">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="17ae8-149">サービス リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-149">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="17ae8-150">ServiceSet リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-150">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="17ae8-151">ユーザー リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-151">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="17ae8-152">WindowsFeature リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-152">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="17ae8-153">WindowsFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-153">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="17ae8-154">WindowsOptionalFeature リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-154">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="17ae8-155">WindowsOptionalFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-155">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="17ae8-156">WindowsPackageCabResource リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-156">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="17ae8-157">WindowsProcess リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-157">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="17ae8-158">ノード間の依存関係リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-158">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="17ae8-159">WaitForAll リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-159">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="17ae8-160">WaitForSome リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-160">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="17ae8-161">WaitForAny リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-161">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="17ae8-162">パッケージ管理リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-162">Package Management resources</span></span>

- [<span data-ttu-id="17ae8-163">PackageManagement リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-163">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="17ae8-164">PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-164">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="17ae8-165">Linux リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-165">Linux resources</span></span>

- [<span data-ttu-id="17ae8-166">Linux Archive リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-166">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- [<span data-ttu-id="17ae8-167">Linux Environment リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-167">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
- [<span data-ttu-id="17ae8-168">Linux FileLine リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-168">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="17ae8-169">Linux File リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-169">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="17ae8-170">Linux Group リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-170">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="17ae8-171">Linux Package リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-171">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="17ae8-172">Linux Script リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-172">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="17ae8-173">Linux Service リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-173">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="17ae8-174">Linux SshAuthorizedKeys リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-174">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="17ae8-175">Linux User リソース</span><span class="sxs-lookup"><span data-stu-id="17ae8-175">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)

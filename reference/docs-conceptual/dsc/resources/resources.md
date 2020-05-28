---
ms.date: 02/28/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース
ms.openlocfilehash: bae08447763a3bdb6ee8fcdd4f8d49209a5de805
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692203"
---
# <a name="dsc-resources"></a><span data-ttu-id="b9dc8-103">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-103">DSC Resources</span></span>

> <span data-ttu-id="b9dc8-104">適用対象: Windows PowerShell 4.0 以上。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-104">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="b9dc8-105">概要</span><span class="sxs-lookup"><span data-stu-id="b9dc8-105">Overview</span></span>

<span data-ttu-id="b9dc8-106">Desired State Configuration (DSC) リソースは、DSC 構成の構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-106">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="b9dc8-107">リソースは、構成 (スキーマ) 可能なプロパティを公開し、また、指定されたことを実現するためにローカル構成マネージャー (LCM) が呼び出す PowerShell スクリプト関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-107">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="b9dc8-108">リソースでは、ファイルのように汎用的なものをモデル化したり、IIS サーバー設定のように具体的なものをモデル化したりできます。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-108">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="b9dc8-109">リソースなどのグループは、DSC モジュールに結合されます。DSC モジュールでは、リソースの使用目的を識別するためのメタデータが含まれている移植可能な構造にすべての必須ファイルが編成されます。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-109">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="b9dc8-110">各リソースには、[Configuration](../configurations/configurations.md) でリソースを使用するために必要な構文を決定する\*スキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-110">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span>
<span data-ttu-id="b9dc8-111">リソースのスキーマは、次のように定義できます。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-111">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="b9dc8-112">`Schema.Mof` ファイル:ほとんどのリソースは、[管理オブジェクト フォーマット](/windows/desktop/wmisdk/managed-object-format--mof-)を使用して 'schema.mof' ファイルに "_スキーマ_" を定義します。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-112">`Schema.Mof` file: Most resources define their _schema_ in a 'schema.mof' file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="b9dc8-113">`<Resource Name>.schema.psm1` ファイル:[複合リソース](../configurations/compositeConfigs.md)では、[パラメーター ブロック](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters)を使用して、`<ResourceName>.schema.psm1` ファイルに*スキーマ*を定義します。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-113">`<Resource Name>.schema.psm1` file: [Composite Resources](../configurations/compositeConfigs.md) define their *schema* in a `<ResourceName>.schema.psm1` file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="b9dc8-114">`<Resource Name>.psm1` ファイル:クラス ベースの DSC リソースは、クラス定義で "_スキーマ_" を定義します。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-114">`<Resource Name>.psm1` file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="b9dc8-115">構文の項目は Class プロパティとして表されます。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-115">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="b9dc8-116">詳細については、「[about_Remote](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-116">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="b9dc8-117">DSC リソースの構文を取得するには、`-Syntax` パラメーターを指定した [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-117">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the `-Syntax` parameter.</span></span> <span data-ttu-id="b9dc8-118">この使用法は、`-Syntax` パラメーターを指定した [Get-Command](/powershell/module/microsoft.powershell.core/get-command)を使用してコマンドレットの構文を取得する場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-118">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the `-Syntax` parameter to get cmdlet syntax.</span></span> <span data-ttu-id="b9dc8-119">表示される出力には、指定したリソースのリソース ブロックに使用されているテンプレートが示されます。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-119">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="b9dc8-120">このリソースの構文は今後変更される可能性がありますが、表示される出力は以下ような出力になります。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-120">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="b9dc8-121">コマンドレットの構文と同様に、角かっこで囲まれた "_キー_" は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-121">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="b9dc8-122">型には、各キーで想定されているデータの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-122">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="b9dc8-123">**Ensure** キーは既定値が "Present" なので省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-123">The **Ensure** key is optional because it defaults to "Present".</span></span>

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

<span data-ttu-id="b9dc8-124">Configuration 内では、スプーラー サービスが実行されていることを確認 (**Ensure**) するため、**Service** リソース ブロックを次のようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-124">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="b9dc8-125">Configuration でリソースを使用する前に、[Import-DSCResource](../configurations/import-dscresource.md) を使用してリソースをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-125">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

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

<span data-ttu-id="b9dc8-126">Configuration には、同じリソースの種類の複数インスタンスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-126">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="b9dc8-127">各インスタンスには一意の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-127">Each instance must be uniquely named.</span></span> <span data-ttu-id="b9dc8-128">次の例では、"DHCP" サービスを構成するために 2 つ目の **Service** リソース ブロックが追加されています。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-128">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

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
> <span data-ttu-id="b9dc8-129">PowerShell 5.0 以降、IntelliSense が DSC に追加されました。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-129">Beginning in PowerShell 5.0, intellisense was added for DSC.</span></span> <span data-ttu-id="b9dc8-130">この新機能を使用すると、<kbd>Tab</kbd> キーと <kbd>Ctrl</kbd>+<kbd>Space</kbd> キーを使用してキー名をオートコンプリートすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-130">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![リソースのタブ補完](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="b9dc8-132">リソースの種類</span><span class="sxs-lookup"><span data-stu-id="b9dc8-132">Types of resources</span></span>

<span data-ttu-id="b9dc8-133">Windows には組み込みリソースが付属しており、Linux には OS 固有のリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-133">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="b9dc8-134">[ノード間の依存関係](../configurations/crossNodeDependencies.md)のリソース、パッケージ管理リソース、および[コミュニティ所有の管理リソース](https://github.com/dsccommunity)があります。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-134">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as[community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="b9dc8-135">前述の手順を使用して、これらのリソースの構文とその使用方法を判断できます。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-135">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="b9dc8-136">これらのリソースを提供するページは、「**関連項目**」にアーカイブされています。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-136">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="b9dc8-137">Windows 組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-137">Windows built-in resources</span></span>

- [<span data-ttu-id="b9dc8-138">アーカイブ リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-138">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="b9dc8-139">環境リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-139">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="b9dc8-140">ファイル リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-140">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="b9dc8-141">グループ リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-141">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="b9dc8-142">GroupSet リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-142">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="b9dc8-143">ログ リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-143">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="b9dc8-144">パッケージ リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-144">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="b9dc8-145">ProcessSet リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-145">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="b9dc8-146">レジストリ リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-146">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="b9dc8-147">スクリプト リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-147">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="b9dc8-148">サービス リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-148">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="b9dc8-149">ServiceSet リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-149">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="b9dc8-150">ユーザー リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-150">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="b9dc8-151">WindowsFeature リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-151">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="b9dc8-152">WindowsFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-152">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="b9dc8-153">WindowsOptionalFeature リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-153">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="b9dc8-154">WindowsOptionalFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-154">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="b9dc8-155">WindowsPackageCabResource リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-155">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="b9dc8-156">WindowsProcess リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-156">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="b9dc8-157">ノード間の依存関係リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-157">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="b9dc8-158">WaitForAll リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-158">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="b9dc8-159">WaitForSome リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-159">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="b9dc8-160">WaitForAny リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-160">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="b9dc8-161">パッケージ管理リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-161">Package Management resources</span></span>

- [<span data-ttu-id="b9dc8-162">PackageManagement リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-162">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="b9dc8-163">PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-163">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="b9dc8-164">Linux リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-164">Linux resources</span></span>

- [<span data-ttu-id="b9dc8-165">Linux Archive リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-165">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- [<span data-ttu-id="b9dc8-166">Linux Environment リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-166">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
- [<span data-ttu-id="b9dc8-167">Linux FileLine リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-167">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="b9dc8-168">Linux File リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-168">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="b9dc8-169">Linux Group リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-169">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="b9dc8-170">Linux Package リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-170">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="b9dc8-171">Linux Script リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-171">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="b9dc8-172">Linux Service リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-172">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="b9dc8-173">Linux SshAuthorizedKeys リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-173">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="b9dc8-174">Linux User リソース</span><span class="sxs-lookup"><span data-stu-id="b9dc8-174">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)

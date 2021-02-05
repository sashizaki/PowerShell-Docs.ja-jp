---
ms.date: 07/23/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース
description: DSC リソースには、DSC 構成の構成要素が用意されています。 リソースでは構成可能なプロパティ (スキーマ) が公開され、構成を適用するために LCM によって使用される PowerShell スクリプト関数が含まれています。
ms.openlocfilehash: 33268c68638bb581e0b2235a53aee9d186dff6be
ms.sourcegitcommit: 0f003644684422e425a59b7361121e05ac772e15
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98771789"
---
# <a name="dsc-resources"></a><span data-ttu-id="5966d-105">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-105">DSC Resources</span></span>

> <span data-ttu-id="5966d-106">適用対象: Windows PowerShell 4.0 以上。</span><span class="sxs-lookup"><span data-stu-id="5966d-106">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="5966d-107">概要</span><span class="sxs-lookup"><span data-stu-id="5966d-107">Overview</span></span>

<span data-ttu-id="5966d-108">Desired State Configuration (DSC) リソースは、DSC 構成の構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="5966d-108">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="5966d-109">リソースは、構成 (スキーマ) 可能なプロパティを公開し、また、指定されたことを実現するためにローカル構成マネージャー (LCM) が呼び出す PowerShell スクリプト関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5966d-109">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="5966d-110">リソースでは、ファイルのように汎用的なものをモデル化したり、IIS サーバー設定のように具体的なものをモデル化したりできます。</span><span class="sxs-lookup"><span data-stu-id="5966d-110">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="5966d-111">リソースなどのグループは、DSC モジュールに結合されます。DSC モジュールでは、リソースの使用目的を識別するためのメタデータが含まれている移植可能な構造にすべての必須ファイルが編成されます。</span><span class="sxs-lookup"><span data-stu-id="5966d-111">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="5966d-112">各リソースには、[Configuration](../configurations/configurations.md) でリソースを使用するために必要な構文を決定する\*スキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="5966d-112">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span> <span data-ttu-id="5966d-113">リソースのスキーマは、次のように定義できます。</span><span class="sxs-lookup"><span data-stu-id="5966d-113">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="5966d-114">`Schema.Mof` ファイル:ほとんどのリソースでは、[マネージド オブジェクト フォーマット](/windows/desktop/wmisdk/managed-object-format--mof-)を使用して、`schema.mof` ファイルに "_スキーマ_" を定義します。</span><span class="sxs-lookup"><span data-stu-id="5966d-114">`Schema.Mof` file: Most resources define their _schema_ in a `schema.mof` file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="5966d-115">`<Resource Name>.schema.psm1` ファイル:[複合リソース](../configurations/compositeConfigs.md)では、[パラメーター ブロック](/powershell/module/microsoft.powershell.core/about/about_functions#functions-with-parameters)を使用して、`<ResourceName>.schema.psm1` ファイルに _スキーマ_ を定義します。</span><span class="sxs-lookup"><span data-stu-id="5966d-115">`<Resource Name>.schema.psm1` file: [Composite Resources](../configurations/compositeConfigs.md) define their _schema_ in a `<ResourceName>.schema.psm1` file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions#functions-with-parameters).</span></span>
- <span data-ttu-id="5966d-116">`<Resource Name>.psm1` ファイル:クラス ベースの DSC リソースは、クラス定義で "_スキーマ_" を定義します。</span><span class="sxs-lookup"><span data-stu-id="5966d-116">`<Resource Name>.psm1` file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="5966d-117">構文の項目は Class プロパティとして表されます。</span><span class="sxs-lookup"><span data-stu-id="5966d-117">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="5966d-118">詳細については、「[about_Remote](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5966d-118">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="5966d-119">DSC リソースの構文を取得するには、**Syntax** パラメーターを指定して、[Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5966d-119">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the **Syntax** parameter.</span></span> <span data-ttu-id="5966d-120">この使用法は、**Syntax** パラメーターを指定して、[Get-Command](/powershell/module/microsoft.powershell.core/get-command) を使用して、コマンドレットの構文を取得する場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="5966d-120">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the **Syntax** parameter to get cmdlet syntax.</span></span> <span data-ttu-id="5966d-121">表示される出力には、指定したリソースのリソース ブロックに使用されているテンプレートが示されます。</span><span class="sxs-lookup"><span data-stu-id="5966d-121">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="5966d-122">このリソースの構文は今後変更される可能性がありますが、表示される出力は以下ような出力になります。</span><span class="sxs-lookup"><span data-stu-id="5966d-122">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="5966d-123">コマンドレットの構文と同様に、角かっこで囲まれた "_キー_" は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5966d-123">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="5966d-124">型には、各キーで想定されているデータの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="5966d-124">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="5966d-125">**Ensure** キーは既定値が "Present" なので省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5966d-125">The **Ensure** key is optional because it defaults to "Present".</span></span>

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
> <span data-ttu-id="5966d-126">PowerShell バージョン 7.0 より前のバージョンでは、`Get-DscResource` によるクラス ベースの DSC リソースの検出は行われません。</span><span class="sxs-lookup"><span data-stu-id="5966d-126">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="5966d-127">Configuration 内では、スプーラー サービスが実行されていることを確認 (**Ensure**) するため、**Service** リソース ブロックを次のようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5966d-127">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="5966d-128">Configuration でリソースを使用する前に、[Import-DSCResource](../configurations/import-dscresource.md) を使用してリソースをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5966d-128">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the
    # resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as l
        # ong as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }
    }
}
```

<span data-ttu-id="5966d-129">Configuration には、同じリソースの種類の複数インスタンスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5966d-129">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="5966d-130">各インスタンスには一意の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="5966d-130">Each instance must be uniquely named.</span></span> <span data-ttu-id="5966d-131">次の例では、"DHCP" サービスを構成するために 2 つ目の **Service** リソース ブロックが追加されています。</span><span class="sxs-lookup"><span data-stu-id="5966d-131">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the
    # resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as
        # long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }

        # To configure a second service resource block, add another Service
        # resource block and use a unique name.
        Service "DHCP:Running"
        {
            Name = "DHCP"
            State = "Running"
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="5966d-132">PowerShell 5.0 以降、IntelliSense が DSC に追加されました。</span><span class="sxs-lookup"><span data-stu-id="5966d-132">Beginning in PowerShell 5.0, IntelliSense was added for DSC.</span></span> <span data-ttu-id="5966d-133">この新機能を使用すると、<kbd>Tab</kbd> キーと <kbd>Ctrl</kbd>+<kbd>Space</kbd> キーを使用してキー名をオートコンプリートすることができます。</span><span class="sxs-lookup"><span data-stu-id="5966d-133">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![Tab 補完機能を使用したリソース IntelliSense](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="5966d-135">リソースの種類</span><span class="sxs-lookup"><span data-stu-id="5966d-135">Types of resources</span></span>

<span data-ttu-id="5966d-136">Windows には組み込みリソースが付属しており、Linux には OS 固有のリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="5966d-136">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="5966d-137">[ノード間の依存関係](../configurations/crossNodeDependencies.md)のリソース、パッケージ管理リソース、および[コミュニティ所有の管理リソース](https://github.com/dsccommunity)があります。</span><span class="sxs-lookup"><span data-stu-id="5966d-137">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as [community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="5966d-138">前述の手順を使用して、これらのリソースの構文とその使用方法を判断できます。</span><span class="sxs-lookup"><span data-stu-id="5966d-138">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="5966d-139">これらのリソースを提供するページは、「**関連項目**」にアーカイブされています。</span><span class="sxs-lookup"><span data-stu-id="5966d-139">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="5966d-140">Windows 組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="5966d-140">Windows built-in resources</span></span>

- [<span data-ttu-id="5966d-141">アーカイブ リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-141">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="5966d-142">環境リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-142">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="5966d-143">ファイル リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-143">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="5966d-144">グループ リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-144">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="5966d-145">GroupSet リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-145">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="5966d-146">ログ リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-146">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="5966d-147">パッケージ リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-147">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="5966d-148">ProcessSet リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-148">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="5966d-149">レジストリ リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-149">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="5966d-150">スクリプト リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-150">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="5966d-151">サービス リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-151">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="5966d-152">ServiceSet リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-152">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="5966d-153">ユーザー リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-153">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="5966d-154">WindowsFeature リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-154">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="5966d-155">WindowsFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-155">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="5966d-156">WindowsOptionalFeature リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-156">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="5966d-157">WindowsOptionalFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-157">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="5966d-158">WindowsPackageCabResource リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-158">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="5966d-159">WindowsProcess リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-159">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="5966d-160">ノード間の依存関係リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-160">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="5966d-161">WaitForAll リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-161">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="5966d-162">WaitForSome リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-162">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="5966d-163">WaitForAny リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-163">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="5966d-164">パッケージ管理リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-164">Package Management resources</span></span>

- [<span data-ttu-id="5966d-165">PackageManagement リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-165">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="5966d-166">PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-166">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="5966d-167">Linux リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-167">Linux resources</span></span>

- [<span data-ttu-id="5966d-168">Linux Archive リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-168">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- [<span data-ttu-id="5966d-169">Linux Environment リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-169">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
- [<span data-ttu-id="5966d-170">Linux FileLine リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-170">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="5966d-171">Linux File リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-171">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="5966d-172">Linux Group リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-172">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="5966d-173">Linux Package リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-173">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="5966d-174">Linux Script リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-174">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="5966d-175">Linux Service リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-175">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="5966d-176">Linux SshAuthorizedKeys リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-176">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="5966d-177">Linux User リソース</span><span class="sxs-lookup"><span data-stu-id="5966d-177">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)

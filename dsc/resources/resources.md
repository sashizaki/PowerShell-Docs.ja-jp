---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース
ms.openlocfilehash: 1f77b5e6630a2e3de6e1d1a05638f94d2df039ae
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076636"
---
# <a name="dsc-resources"></a><span data-ttu-id="7238d-103">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-103">DSC Resources</span></span>

><span data-ttu-id="7238d-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="7238d-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="7238d-105">Desired State Configuration (DSC) リソースは、DSC 構成の構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="7238d-105">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="7238d-106">リソースは、構成 (スキーマ) 可能なプロパティを公開し、また、指定されたことを実現するためにローカル構成マネージャー (LCM) が呼び出す PowerShell スクリプト関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7238d-106">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="7238d-107">リソースでは、ファイルのように汎用的なものをモデル化したり、IIS サーバー設定のように具体的なものをモデル化したりできます。</span><span class="sxs-lookup"><span data-stu-id="7238d-107">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span>  <span data-ttu-id="7238d-108">リソースなどのグループは、DSC モジュールに結合されます。DSC モジュールでは、リソースの使用目的を識別するためのメタデータが含まれている移植可能な構造にすべての必須ファイルが編成されます。</span><span class="sxs-lookup"><span data-stu-id="7238d-108">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="7238d-109">各リソースには、[Configuration](../configurations/configurations.md) でリソースを使用するために必要な構文を決定する\*スキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="7238d-109">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span> <span data-ttu-id="7238d-110">リソースのスキーマは、次のように定義できます。</span><span class="sxs-lookup"><span data-stu-id="7238d-110">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="7238d-111">**'Schema.Mof'** ファイル:ほとんどのリソースは、[管理オブジェクト フォーマット](/windows/desktop/wmisdk/managed-object-format--mof-)を使用して 'schema.mof' ファイルに "*スキーマ*" を定義します。</span><span class="sxs-lookup"><span data-stu-id="7238d-111">**'Schema.Mof'** file: Most resources define their *schema* in a 'schema.mof' file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="7238d-112">**'\<リソース名\>.schema.psm1'** ファイル:[複合リソース](../configurations/compositeConfigs.md)では、[パラメーター ブロック](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters) を使用して '<ResourceName>.schema.psm1' ファイルに "*スキーマ*" を定義します。</span><span class="sxs-lookup"><span data-stu-id="7238d-112">**'\<Resource Name\>.schema.psm1'** file: [Composite Resources](../configurations/compositeConfigs.md) define their *schema* in a '<ResourceName>.schema.psm1' file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="7238d-113">**'\<リソース名\>.psm1'** ファイル:クラス ベースの DSC リソースは、クラス定義で "*スキーマ*" を定義します。</span><span class="sxs-lookup"><span data-stu-id="7238d-113">**'\<Resource Name\>.psm1'** file: Class based DSC resources define their *schema* in the class definition.</span></span> <span data-ttu-id="7238d-114">構文の項目は Class プロパティとして表されます。</span><span class="sxs-lookup"><span data-stu-id="7238d-114">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="7238d-115">詳細については、「[about_Remote](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7238d-115">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="7238d-116">DSC リソースの構文を取得するには、`-Syntax` パラメーターを指定した [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7238d-116">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the `-Syntax` parameter.</span></span> <span data-ttu-id="7238d-117">この使用法は、`-Syntax` パラメーターを指定した [Get-Command](/powershell/module/microsoft.powershell.core/get-command)を使用してコマンドレットの構文を取得する場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="7238d-117">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the `-Syntax` parameter to get cmdlet syntax.</span></span> <span data-ttu-id="7238d-118">表示される出力には、指定したリソースのリソース ブロックに使用されているテンプレートが示されます。</span><span class="sxs-lookup"><span data-stu-id="7238d-118">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="7238d-119">このリソースの構文は今後変更される可能性がありますが、表示される出力は以下ような出力になります。</span><span class="sxs-lookup"><span data-stu-id="7238d-119">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="7238d-120">コマンドレットの構文と同様に、角かっこで囲まれた "*キー*" は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7238d-120">Like cmdlet syntax, the *keys* seen in square brackets, are optional.</span></span> <span data-ttu-id="7238d-121">型には、各キーで想定されているデータの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7238d-121">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="7238d-122">**Ensure** キーは既定値が "Present" なので省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7238d-122">The **Ensure** key is optional because it defaults to "Present".</span></span>

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

<span data-ttu-id="7238d-123">Configuration 内では、スプーラー サービスが実行されていることを確認 (**Ensure**) するため、**Service** リソース ブロックを次のようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7238d-123">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="7238d-124">Configuration でリソースを使用する前に、[Import-DSCResource](../configurations/import-dscresource.md) を使用してリソースをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7238d-124">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

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

<span data-ttu-id="7238d-125">Configuration には、同じリソースの種類の複数インスタンスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7238d-125">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="7238d-126">各インスタンスには一意の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="7238d-126">Each instance must be uniquely named.</span></span> <span data-ttu-id="7238d-127">次の例では、"DHCP" サービスを構成するために 2 つ目の **Service** リソース ブロックが追加されています。</span><span class="sxs-lookup"><span data-stu-id="7238d-127">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

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
> <span data-ttu-id="7238d-128">PowerShell 5.0 以降、IntelliSense が DSC に追加されました。</span><span class="sxs-lookup"><span data-stu-id="7238d-128">Beginning in PowerShell 5.0, intellisense was added for DSC.</span></span> <span data-ttu-id="7238d-129">この新機能を使用すると、\<Tab\> キーと \<Ctrl + Space\> キーを使用してキー名をオートコンプリートすることができます。</span><span class="sxs-lookup"><span data-stu-id="7238d-129">This new feature allows you to use \<TAB\> and \<Ctrl+Space\> to auto-complete key names.</span></span>

![リソースのタブ補完](../media/resource-tabcompletion.png)

## <a name="built-in-resources"></a><span data-ttu-id="7238d-131">組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="7238d-131">Built-in resources</span></span>

<span data-ttu-id="7238d-132">コミュニティ リソースに加え、Windows 用の組み込みリソース、Linux 用のリソース、およびノード間の依存関係に関するリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="7238d-132">In addition to community resources, there are built-in resources for Windows, resources for Linux, and resources for cross-node dependency.</span></span> <span data-ttu-id="7238d-133">前述の手順を使用して、これらのリソースの構文とその使用方法を判断できます。</span><span class="sxs-lookup"><span data-stu-id="7238d-133">You can use the steps above to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="7238d-134">これらのリソースを提供するページは、「**関連項目**」にアーカイブされています。</span><span class="sxs-lookup"><span data-stu-id="7238d-134">The pages that serve these resources have been archived under **Reference**.</span></span>

<span data-ttu-id="7238d-135">Windows 組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="7238d-135">Windows built-in resources</span></span>

* [<span data-ttu-id="7238d-136">アーカイブ リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-136">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
* [<span data-ttu-id="7238d-137">環境リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-137">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
* [<span data-ttu-id="7238d-138">ファイル リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-138">File Resource</span></span>](../reference/resources/windows/fileResource.md)
* [<span data-ttu-id="7238d-139">グループ リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-139">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
* [<span data-ttu-id="7238d-140">GroupSet リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-140">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
* [<span data-ttu-id="7238d-141">ログ リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-141">Log Resource</span></span>](../reference/resources/windows/logResource.md)
* [<span data-ttu-id="7238d-142">パッケージ リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-142">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
* [<span data-ttu-id="7238d-143">ProcessSet リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-143">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
* [<span data-ttu-id="7238d-144">レジストリ リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-144">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
* [<span data-ttu-id="7238d-145">スクリプト リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-145">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
* [<span data-ttu-id="7238d-146">サービス リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-146">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
* [<span data-ttu-id="7238d-147">ServiceSet リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-147">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
* [<span data-ttu-id="7238d-148">ユーザー リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-148">User Resource</span></span>](../reference/resources/windows/userResource.md)
* [<span data-ttu-id="7238d-149">WindowsFeature リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-149">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
* [<span data-ttu-id="7238d-150">WindowsFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-150">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
* [<span data-ttu-id="7238d-151">WindowsOptionalFeature リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-151">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
* [<span data-ttu-id="7238d-152">WindowsOptionalFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-152">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
* [<span data-ttu-id="7238d-153">WindowsPackageCabResource リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-153">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
* [<span data-ttu-id="7238d-154">WindowsProcess リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-154">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

<span data-ttu-id="7238d-155">[ノード間の依存関係](../configurations/crossNodeDependencies.md)リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-155">[Cross-Node dependency](../configurations/crossNodeDependencies.md) resources</span></span>

* [<span data-ttu-id="7238d-156">WaitForAll リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-156">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
* [<span data-ttu-id="7238d-157">WaitForSome リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-157">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
* [<span data-ttu-id="7238d-158">WaitForAny リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-158">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

<span data-ttu-id="7238d-159">パッケージ管理リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-159">Package Management resources</span></span>

* [<span data-ttu-id="7238d-160">PackageManagement リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-160">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
* [<span data-ttu-id="7238d-161">PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-161">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

<span data-ttu-id="7238d-162">Linux リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-162">Linux resources</span></span>

* [<span data-ttu-id="7238d-163">Linux Archive リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-163">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
* [<span data-ttu-id="7238d-164">Linux Environment リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-164">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
* [<span data-ttu-id="7238d-165">Linux FileLine リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-165">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
* [<span data-ttu-id="7238d-166">Linux File リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-166">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
* [<span data-ttu-id="7238d-167">Linux Group リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-167">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
* [<span data-ttu-id="7238d-168">Linux Package リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-168">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
* [<span data-ttu-id="7238d-169">Linux Script リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-169">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
* [<span data-ttu-id="7238d-170">Linux Service リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-170">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
* [<span data-ttu-id="7238d-171">Linux SshAuthorizedKeys リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-171">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
* [<span data-ttu-id="7238d-172">Linux User リソース</span><span class="sxs-lookup"><span data-stu-id="7238d-172">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)

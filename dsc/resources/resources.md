---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース
ms.openlocfilehash: 1f77b5e6630a2e3de6e1d1a05638f94d2df039ae
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54046693"
---
# <a name="dsc-resources"></a><span data-ttu-id="df4bf-103">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-103">DSC Resources</span></span>

><span data-ttu-id="df4bf-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="df4bf-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="df4bf-105">Desired State Configuration (DSC) リソースは、DSC 構成の構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-105">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="df4bf-106">リソースは、構成 (スキーマ) 可能なプロパティを公開し、また、指定されたことを実現するためにローカル構成マネージャー (LCM) が呼び出す PowerShell スクリプト関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="df4bf-106">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="df4bf-107">リソースでは、ファイルのように汎用的なものをモデル化したり、IIS サーバー設定のように具体的なものをモデル化したりできます。</span><span class="sxs-lookup"><span data-stu-id="df4bf-107">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span>  <span data-ttu-id="df4bf-108">リソースなどのグループは、DSC モジュールに結合されます。DSC モジュールでは、リソースの使用目的を識別するためのメタデータが含まれている移植可能な構造にすべての必須ファイルが編成されます。</span><span class="sxs-lookup"><span data-stu-id="df4bf-108">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="df4bf-109">各リソースには、\* スキーマ内のリソースを使用するために必要な構文を決定する、[構成](../configurations/configurations.md)します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-109">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span> <span data-ttu-id="df4bf-110">次の方法では、リソースのスキーマを定義できます。</span><span class="sxs-lookup"><span data-stu-id="df4bf-110">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="df4bf-111">**'Schema.Mof'** ファイル。ほとんどのリソースを定義、*スキーマ*'schema.mof' でファイルを使用して[マネージ オブジェクト形式](/windows/desktop/wmisdk/managed-object-format--mof-)します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-111">**'Schema.Mof'** file: Most resources define their *schema* in a 'schema.mof' file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="df4bf-112">**'\<リソース名\>. schema.psm1'** ファイル。[複合リソース](../configurations/compositeConfigs.md)定義、*スキーマ*で、'<ResourceName>. schema.psm1' ファイルを使用して、 [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters)します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-112">**'\<Resource Name\>.schema.psm1'** file: [Composite Resources](../configurations/compositeConfigs.md) define their *schema* in a '<ResourceName>.schema.psm1' file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="df4bf-113">**'\<リソース名\>.psm1'** ファイル。クラス ベース DSC リソースの定義、*スキーマ*クラス定義にします。</span><span class="sxs-lookup"><span data-stu-id="df4bf-113">**'\<Resource Name\>.psm1'** file: Class based DSC resources define their *schema* in the class definition.</span></span> <span data-ttu-id="df4bf-114">構文項目は、クラスのプロパティとして表されます。</span><span class="sxs-lookup"><span data-stu-id="df4bf-114">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="df4bf-115">詳細については、次を参照してください。 [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-115">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="df4bf-116">DSC リソースの構文を取得する、 [Get-dscresource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)コマンドレットと、`-Syntax`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="df4bf-116">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the `-Syntax` parameter.</span></span> <span data-ttu-id="df4bf-117">この使用法の使用と似ています[Get-command](/powershell/module/microsoft.powershell.core/get-command)で、`-Syntax`パラメーターをコマンドレットの構文を取得します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-117">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the `-Syntax` parameter to get cmdlet syntax.</span></span> <span data-ttu-id="df4bf-118">表示出力は、指定したリソースのリソース ブロックで使用するテンプレートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="df4bf-118">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="df4bf-119">表示出力は、このリソースの構文は、後で変わる可能性がありますが、次のようなことがあります。</span><span class="sxs-lookup"><span data-stu-id="df4bf-119">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="df4bf-120">などのコマンドレットの構文、*キー*角かっこで囲んで表示は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="df4bf-120">Like cmdlet syntax, the *keys* seen in square brackets, are optional.</span></span> <span data-ttu-id="df4bf-121">種類は、各キーはデータの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-121">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="df4bf-122">**を確認してください**既定値は"present"にあるために、キーは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="df4bf-122">The **Ensure** key is optional because it defaults to "Present".</span></span>

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

<span data-ttu-id="df4bf-123">構成では、内部、**サービス**リソース ブロックするようになります**を確認してください**スプーラ サービスを実行しています。</span><span class="sxs-lookup"><span data-stu-id="df4bf-123">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="df4bf-124">構成では、リソースを使用する前に使用してインポートする必要があります[Import-dscresource](../configurations/import-dscresource.md)します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-124">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

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

<span data-ttu-id="df4bf-125">構成は、同じリソースの種類の複数のインスタンスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="df4bf-125">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="df4bf-126">各インスタンスを一意に名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df4bf-126">Each instance must be uniquely named.</span></span> <span data-ttu-id="df4bf-127">次の例では、1 秒あたり**サービス**リソース ブロックは、"DHCP"サービスの構成に追加されます。</span><span class="sxs-lookup"><span data-stu-id="df4bf-127">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

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
> <span data-ttu-id="df4bf-128">DSC の PowerShell 5.0 以降では、intellisense が追加されました。</span><span class="sxs-lookup"><span data-stu-id="df4bf-128">Beginning in PowerShell 5.0, intellisense was added for DSC.</span></span> <span data-ttu-id="df4bf-129">この新しい機能では、使用できます。\<タブ\>と\<Ctrl + Space\>キー名のオートコンプリートにします。</span><span class="sxs-lookup"><span data-stu-id="df4bf-129">This new feature allows you to use \<TAB\> and \<Ctrl+Space\> to auto-complete key names.</span></span>

![リソースの Tab 補完機能](../media/resource-tabcompletion.png)

## <a name="built-in-resources"></a><span data-ttu-id="df4bf-131">組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-131">Built-in resources</span></span>

<span data-ttu-id="df4bf-132">コミュニティ リソース、Windows、linux の場合、リソースおよびノードの相互依存関係のリソース用組み込みリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="df4bf-132">In addition to community resources, there are built-in resources for Windows, resources for Linux, and resources for cross-node dependency.</span></span> <span data-ttu-id="df4bf-133">上記の手順を使用すると、これらのリソースとその使用方法の構文を確認します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-133">You can use the steps above to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="df4bf-134">これらのリソースを提供するページがアーカイブされた**参照**します。</span><span class="sxs-lookup"><span data-stu-id="df4bf-134">The pages that serve these resources have been archived under **Reference**.</span></span>

<span data-ttu-id="df4bf-135">Windows 組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-135">Windows built-in resources</span></span>

* [<span data-ttu-id="df4bf-136">アーカイブ リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-136">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
* [<span data-ttu-id="df4bf-137">環境リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-137">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
* [<span data-ttu-id="df4bf-138">ファイル リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-138">File Resource</span></span>](../reference/resources/windows/fileResource.md)
* [<span data-ttu-id="df4bf-139">グループ リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-139">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
* [<span data-ttu-id="df4bf-140">GroupSet リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-140">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
* [<span data-ttu-id="df4bf-141">ログ リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-141">Log Resource</span></span>](../reference/resources/windows/logResource.md)
* [<span data-ttu-id="df4bf-142">パッケージ リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-142">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
* [<span data-ttu-id="df4bf-143">ProcessSet リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-143">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
* [<span data-ttu-id="df4bf-144">レジストリ リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-144">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
* [<span data-ttu-id="df4bf-145">スクリプト リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-145">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
* [<span data-ttu-id="df4bf-146">サービス リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-146">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
* [<span data-ttu-id="df4bf-147">ServiceSet リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-147">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
* [<span data-ttu-id="df4bf-148">ユーザー リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-148">User Resource</span></span>](../reference/resources/windows/userResource.md)
* [<span data-ttu-id="df4bf-149">WindowsFeature リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-149">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
* [<span data-ttu-id="df4bf-150">WindowsFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-150">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
* [<span data-ttu-id="df4bf-151">WindowsOptionalFeature リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-151">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
* [<span data-ttu-id="df4bf-152">WindowsOptionalFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-152">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
* [<span data-ttu-id="df4bf-153">WindowsPackageCabResource リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-153">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
* [<span data-ttu-id="df4bf-154">WindowsProcess リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-154">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

<span data-ttu-id="df4bf-155">[ノードの相互依存関係](../configurations/crossNodeDependencies.md)リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-155">[Cross-Node dependency](../configurations/crossNodeDependencies.md) resources</span></span>

* [<span data-ttu-id="df4bf-156">WaitForAll リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-156">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
* [<span data-ttu-id="df4bf-157">WaitForSome リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-157">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
* [<span data-ttu-id="df4bf-158">WaitForAny リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-158">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

<span data-ttu-id="df4bf-159">パッケージの管理リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-159">Package Management resources</span></span>

* [<span data-ttu-id="df4bf-160">PackageManagement リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-160">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
* [<span data-ttu-id="df4bf-161">PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-161">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

<span data-ttu-id="df4bf-162">Linux のリソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-162">Linux resources</span></span>

* [<span data-ttu-id="df4bf-163">Linux の Archive リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-163">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
* [<span data-ttu-id="df4bf-164">Linux 環境のリソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-164">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
* [<span data-ttu-id="df4bf-165">Linux FileLine リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-165">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
* [<span data-ttu-id="df4bf-166">Linux ファイル リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-166">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
* [<span data-ttu-id="df4bf-167">Linux グループ リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-167">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
* [<span data-ttu-id="df4bf-168">Linux パッケージ リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-168">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
* [<span data-ttu-id="df4bf-169">Linux スクリプト リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-169">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
* [<span data-ttu-id="df4bf-170">Linux のサービス リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-170">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
* [<span data-ttu-id="df4bf-171">Linux SshAuthorizedKeys リソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-171">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
* [<span data-ttu-id="df4bf-172">Linux ユーザーのリソース</span><span class="sxs-lookup"><span data-stu-id="df4bf-172">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)

---
ms.date: 12/12/2018
keywords: dsc,powershell,リソース,ギャラリー,セットアップ
title: 追加の DSC リソースをインストールする
description: この記事では、PSDesiredStateConfiguration モジュールに含まれている DSC リソースの一覧を示します。 また、PowerShell ギャラリーからリソースを検索してインストールする方法についても説明します。
ms.openlocfilehash: e75561ed539e06716c9a103f905b9d1e4f3e71d3
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645131"
---
# <a name="install-additional-dsc-resources"></a><span data-ttu-id="be111-105">追加の DSC リソースをインストールする</span><span class="sxs-lookup"><span data-stu-id="be111-105">Install Additional DSC Resources</span></span>

<span data-ttu-id="be111-106">PowerShell には、Desired State Configuration (DSC) 用に複数のそのまま利用できるリソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="be111-106">PowerShell includes several Out-of-the-box resources for Desired State Configuration (DSC).</span></span> <span data-ttu-id="be111-107">**PSDesiredStateConfiguration** モジュールには、PowerShell の特定のインスタンスで使用可能なすべての OOB DSC リソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="be111-107">The **PSDesiredStateConfiguration** module contains all of the OOB DSC resources available on your specific instance of PowerShell.</span></span>

<span data-ttu-id="be111-108">次に示すのは、PowerShell 4.0 に含まれる OOB リソースの一覧とリソースの機能の説明です。</span><span class="sxs-lookup"><span data-stu-id="be111-108">This is a list of the OOB resources included in PowerShell 4.0 and a description of the resource's capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="be111-109">PowerShell のバージョンごとに OOB リソースの数は増えているため、これは完全な一覧ではありません。</span><span class="sxs-lookup"><span data-stu-id="be111-109">This is an incomplete list, as the number of OOB resources has grown with each version of PowerShell.</span></span>

|      <span data-ttu-id="be111-110">リソース</span><span class="sxs-lookup"><span data-stu-id="be111-110">Resource</span></span>      |                                                                                       <span data-ttu-id="be111-111">説明</span><span class="sxs-lookup"><span data-stu-id="be111-111">Description</span></span>                                                                                        |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="be111-112">**[最近使ったファイル]**</span><span class="sxs-lookup"><span data-stu-id="be111-112">**File**</span></span>           | <span data-ttu-id="be111-113">ファイルとディレクトリの状態を制御します。</span><span class="sxs-lookup"><span data-stu-id="be111-113">Controls the state of files and directories.</span></span> <span data-ttu-id="be111-114">**コピー元** から **コピー先** にファイルをコピーし、日付、チェックサム、およびハッシュを比較することによって **コピー元** が変更されたらファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="be111-114">Copies files from a **Source** to a **Destination** and updates them when the **Source** changes by comparing dates, checksums, and hashes.</span></span> |
| <span data-ttu-id="be111-115">**Archive**</span><span class="sxs-lookup"><span data-stu-id="be111-115">**Archive**</span></span>        | <span data-ttu-id="be111-116">アーカイブと指定された場所をアンパックします。</span><span class="sxs-lookup"><span data-stu-id="be111-116">Unpacks archives and a specified location.</span></span> <span data-ttu-id="be111-117">指定された **チェックサム** でアーカイブを検証します。</span><span class="sxs-lookup"><span data-stu-id="be111-117">Validates the archives with a specified **Checksum**.</span></span>                                                                                         |
| <span data-ttu-id="be111-118">**Environment**</span><span class="sxs-lookup"><span data-stu-id="be111-118">**Environment**</span></span>    | <span data-ttu-id="be111-119">環境変数を管理します。</span><span class="sxs-lookup"><span data-stu-id="be111-119">Manages environment variables.</span></span>                                                                                                                                                           |
| <span data-ttu-id="be111-120">**グループ**</span><span class="sxs-lookup"><span data-stu-id="be111-120">**Group**</span></span>          | <span data-ttu-id="be111-121">ローカル グループを管理し、グループ メンバーシップを制御します。</span><span class="sxs-lookup"><span data-stu-id="be111-121">Manages local groups and controls group membership.</span></span>                                                                                                                                      |
| <span data-ttu-id="be111-122">**Log**</span><span class="sxs-lookup"><span data-stu-id="be111-122">**Log**</span></span>            | <span data-ttu-id="be111-123">`Microsoft-Windows-Desired State Configuration/Analytic` イベント ログにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="be111-123">Writes messages to the `Microsoft-Windows-Desired State Configuration/Analytic` event log.</span></span>                                                                                               |
| <span data-ttu-id="be111-124">**Package**</span><span class="sxs-lookup"><span data-stu-id="be111-124">**Package**</span></span>        | <span data-ttu-id="be111-125">**Arguments** 、 **LogPath** 、 **ReturnCode** 、その他の設定を使って、パッケージをインストールまたはアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="be111-125">Installs or uninstalls packages using **Arguments** , **LogPath** , **ReturnCode** , other settings.</span></span>                                                                                        |
| <span data-ttu-id="be111-126">**レジストリ**</span><span class="sxs-lookup"><span data-stu-id="be111-126">**Registry**</span></span>       | <span data-ttu-id="be111-127">レジストリ キーと値を管理します。</span><span class="sxs-lookup"><span data-stu-id="be111-127">Manages registry keys and values.</span></span>                                                                                                                                                        |
| <span data-ttu-id="be111-128">**スクリプト**</span><span class="sxs-lookup"><span data-stu-id="be111-128">**Script**</span></span>         | <span data-ttu-id="be111-129">独自の [get-test-set](../resources/get-test-set.md) スクリプト ブロックを設計できます。</span><span class="sxs-lookup"><span data-stu-id="be111-129">Allows you to design your own [get-test-set](../resources/get-test-set.md) script blocks.</span></span>                                                                                                |
| <span data-ttu-id="be111-130">**サービス**</span><span class="sxs-lookup"><span data-stu-id="be111-130">**Service**</span></span>        | <span data-ttu-id="be111-131">Windows サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="be111-131">Configures Windows services.</span></span>                                                                                                                                                             |
| <span data-ttu-id="be111-132">**User**</span><span class="sxs-lookup"><span data-stu-id="be111-132">**User**</span></span>           | <span data-ttu-id="be111-133">ローカル ユーザーと属性を管理します。</span><span class="sxs-lookup"><span data-stu-id="be111-133">Manages local users and attributes.</span></span>                                                                                                                                                      |
| <span data-ttu-id="be111-134">**WindowsFeature**</span><span class="sxs-lookup"><span data-stu-id="be111-134">**WindowsFeature**</span></span> | <span data-ttu-id="be111-135">ロールと機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="be111-135">Manages roles and features.</span></span>                                                                                                                                                              |
| <span data-ttu-id="be111-136">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="be111-136">**WindowsProcess**</span></span> | <span data-ttu-id="be111-137">Windows プロセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="be111-137">Configures Windows processes.</span></span>                                                                                                                                                            |

<span data-ttu-id="be111-138">OOB リソースは、一般的な操作のよい起点になります。</span><span class="sxs-lookup"><span data-stu-id="be111-138">The OOB resources allow a good starting point for common operations.</span></span> <span data-ttu-id="be111-139">OOB リソースがニーズを満たさない場合は、独自の[カスタム リソース](../resources/authoringResource.md)を作成できます。</span><span class="sxs-lookup"><span data-stu-id="be111-139">If the OOB resources do not meet your needs, you can write your own [Custom Resource](../resources/authoringResource.md).</span></span> <span data-ttu-id="be111-140">問題を解決するためのカスタム リソースを記述する前に、Microsoft と PowerShell コミュニティの両方で既に作成されている膨大な数の DSC リソースを調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="be111-140">Before you write a custom resource to solve your problem, you should look through the vast number of DSC resources that have already been created by both Microsoft and the PowerShell community.</span></span>

<span data-ttu-id="be111-141">[PowerShell ギャラリー](https://www.powershellgallery.com/)と [GitHub](https://github.com/) の両方で、DSC リソースを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="be111-141">You can find DSC resources in both the [PowerShell Gallery](https://www.powershellgallery.com/) and [GitHub](https://github.com/).</span></span> <span data-ttu-id="be111-142">また、[PowerShellGet](/powershell/module/powershellget/) を使って PowerShell コンソールから DSC リソースを直接インストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="be111-142">You can also install DSC resources directly from the PowerShell console using [PowerShellGet](/powershell/module/powershellget/).</span></span>

## <a name="installing-powershellget"></a><span data-ttu-id="be111-143">PowerShellGet のインストール</span><span class="sxs-lookup"><span data-stu-id="be111-143">Installing PowerShellGet</span></span>

<span data-ttu-id="be111-144">**PowerShellGet** が既にあるかどうかを調べたり、そのインストールに関するヘルプ情報を見たりするには、次のガイドを参照してください: 「[PowerShellGet のインストール](/powershell/scripting/gallery/installing-psget)」。</span><span class="sxs-lookup"><span data-stu-id="be111-144">To determine if you already have **PowerShell** get, or to get help installing it, see the following guide: [Installing PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span>

## <a name="finding-dsc-resources-using-powershellget"></a><span data-ttu-id="be111-145">PowerShellGet を使用して DSC リソースを検索する</span><span class="sxs-lookup"><span data-stu-id="be111-145">Finding DSC resources using PowerShellGet</span></span>

<span data-ttu-id="be111-146">**PowerShellGet** をシステムにインストールした後は、 [PowerShell ギャラリー](https://www.powershellgallery.com/)でホストされている DSC リソースを検索してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="be111-146">Once **PowerShellGet** is installed on your system, you can find and install DSC resources hosted in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>

<span data-ttu-id="be111-147">最初に、[Find-DSCResource](/powershell/module/powershellget/find-dscresource) コマンドレットを使って DSC リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="be111-147">First, use the [Find-DSCResource](/powershell/module/powershellget/find-dscresource) cmdlet to find DSC resources.</span></span> <span data-ttu-id="be111-148">`Find-DSCResource` を初めて実行すると、"NuGet プロバイダー" のインストールを求める次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be111-148">When you run `Find-DSCResource` for the first time, you see the following prompt to install the "NuGet provider".</span></span>

```
PS> Find-DSCResource

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based
repositories. The NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies'
or 'C:\Users\xAdministrator\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install
the NuGet provider by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201
-Force'. Do you want PowerShellGet to install and import the NuGet provider now?
[Y] Yes  [N] No  [?] Help (default is "Y"):
```

<span data-ttu-id="be111-149">Y キーを押すと、"NuGet" プロバイダーがインストールされて、PowerShell ギャラリーからインストールできる DSC リソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be111-149">After pressing 'y', the "NuGet" provider is installed, you see a list of DSC resources that you can install from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="be111-150">一覧は非常に大きいため示してありません。</span><span class="sxs-lookup"><span data-stu-id="be111-150">List is not shown because it is very large.</span></span>

<span data-ttu-id="be111-151">ワイルドカードを使って `-Name` パラメーターを指定するか、またはワイルドカードを使わないで `-Filter` パラメーターを指定して、検索を絞り込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="be111-151">You can also specify the `-Name` parameter using wildcards, or `-Filter` parameter without wildcards to narrow down your search.</span></span> <span data-ttu-id="be111-152">次の例では、ワイルドカードを使って "TimeZone" DSC リソースを検索しています。</span><span class="sxs-lookup"><span data-stu-id="be111-152">This example attempts to find a "TimeZone" DSC resource using the wildcards.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be111-153">現在は `Find-DSCResource` コマンドレットにバグがあり、`-Name` と `-Filter` 両方のパラメーターでワイルドカードを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="be111-153">Currently there is a bug in the `Find-DSCResource` cmdlet that prevents using wildcards in both the `-Name` and `-Filter` parameters.</span></span> <span data-ttu-id="be111-154">次の 2 番目の例では、`Where-Object` を使った回避策を示します。</span><span class="sxs-lookup"><span data-stu-id="be111-154">The second example below shows a workaround using `Where-Object`.</span></span>

```
PS> Find-DSCResource -Name *Time*

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Carbon_EnvironmentVariable          2.6.0      Carbon                              PSGallery
Carbon_FirewallRule                 2.6.0      Carbon                              PSGallery
Carbon_Group                        2.6.0      Carbon                              PSGallery
Carbon_IniFile                      2.6.0      Carbon                              PSGallery
Carbon_Permission                   2.6.0      Carbon                              PSGallery
Carbon_Privilege                    2.6.0      Carbon                              PSGallery
Carbon_ScheduledTask                2.6.0      Carbon                              PSGallery
Carbon_Service                      2.6.0      Carbon                              PSGallery
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
xTimeZone                           1.8.0.0    xTimeZone                           PSGallery
xSqlServerDefaultDir                1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerMoveDatabaseFiles         1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerSQLDataRoot               1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerStartupParam              1.0.0      mlSqlServerDSC                      PSGallery
```

<span data-ttu-id="be111-155">`Where-Object` を使ってさらに詳細なフィルターで DSC リソースを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="be111-155">You can also use `Where-Object` to find DSC resources with more granular filtering.</span></span> <span data-ttu-id="be111-156">この方法では、組み込みのフィルター処理パラメーターを使うより処理が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="be111-156">This approach will be slower than using built in filtering parameters.</span></span>

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

<span data-ttu-id="be111-157">フィルター処理について詳しくは、「[Where-Object](/powershell/module/microsoft.powershell.core/where-object)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="be111-157">For more information on filtering, see [Where-Object](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="installing-dsc-resources-using-powershellget"></a><span data-ttu-id="be111-158">PowerShellGet を使用して DSC リソースをインストールする</span><span class="sxs-lookup"><span data-stu-id="be111-158">Installing DSC Resources using PowerShellGet</span></span>

<span data-ttu-id="be111-159">DSC リソースをインストールするには、 [Install-Module](/powershell/module/PowershellGet/Install-Module) コマンドレットを使い、検索結果の **[ModuleName]** の下に表示されるモジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="be111-159">To install a DSC resource, use the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet, specifying the name of the module shown under **Module** name in your search results.</span></span>

<span data-ttu-id="be111-160">"TimeZone" リソースは "ComputerManagementDSC" モジュールに存在するので、この例ではそのモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="be111-160">The "TimeZone" resource exists in the "ComputerManagementDSC" module, so that is the module this example installs.</span></span>

> [!NOTE]
> <span data-ttu-id="be111-161">PowerShell ギャラリーを信頼していない場合は、確認を要求し、以降のインストールでメッセージが表示されないようにする方法を示す、次のような警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be111-161">If you have not trusted the PowerShell gallery, you see the warning below asking for confirmation, and instructing you how to avoid subsequent prompts on installs.</span></span>

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to
install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="be111-162">Y キーを押して、モジュールのインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="be111-162">Press 'y' to continue installing the module.</span></span> <span data-ttu-id="be111-163">インストール後は、[Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) を使って、新しいリソースがインストールされたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="be111-163">After install, you can verify that your new resource is installed using [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).</span></span>

```
PS> Get-DSCResource -Name TimeZone -Syntax

TimeZone [String] #ResourceName
{
    IsSingleInstance = [string]{ Yes }
    TimeZone = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

<span data-ttu-id="be111-164">また、`-ModuleName` パラメーターを指定することで、新しくインストールしたモジュール内の他のリソースを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="be111-164">You can also view other resources in your newly installed module, by specifying the `-ModuleName` parameter.</span></span>

```
PS> Get-DSCResource -Module ComputerManagementDSC

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      Computer                  ComputerManagementDsc          6.0.0.0    {Name, Credential, DependsOn, ...
PowerShell      OfflineDomainJoin         ComputerManagementDsc          6.0.0.0    {IsSingleInstance, RequestFile...
PowerShell      PowerPlan                 ComputerManagementDsc          6.0.0.0    {IsSingleInstance, Name, Depen...
PowerShell      PowerShellExecutionPolicy ComputerManagementDsc          6.0.0.0    {ExecutionPolicy, ExecutionPol...
PowerShell      ScheduledTask             ComputerManagementDsc          6.0.0.0    {TaskName, ActionArguments, Ac...
PowerShell      TimeZone                  ComputerManagementDsc          6.0.0.0    {IsSingleInstance, TimeZone, D...
PowerShell      VirtualMemory             ComputerManagementDsc          6.0.0.0    {Drive, Type, DependsOn, Initi...
```

## <a name="see-also"></a><span data-ttu-id="be111-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="be111-165">See also</span></span>

- [<span data-ttu-id="be111-166">リソースとは</span><span class="sxs-lookup"><span data-stu-id="be111-166">What are Resources?</span></span>](../resources/resources.md)

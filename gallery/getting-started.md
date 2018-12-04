---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリーの概要
ms.openlocfilehash: c8beba3009e462ce52cdecd34fc0313d9234f289
ms.sourcegitcommit: 1082b13115c5c5be4b76574ba55307b3e567983f
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "52576891"
---
# <a name="getting-started-with-the-powershell-gallery"></a><span data-ttu-id="7bd28-103">PowerShell ギャラリーの概要</span><span class="sxs-lookup"><span data-stu-id="7bd28-103">Getting Started with the PowerShell Gallery</span></span>

<span data-ttu-id="7bd28-104">PowerShell ギャラリーは、スクリプト、モジュール、およびダウンロードして利用できる DSC リソースを含むパッケージ リポジトリです。</span><span class="sxs-lookup"><span data-stu-id="7bd28-104">The PowerShell Gallery is a package repository containing scripts, modules, and DSC resources you can download and leverage.</span></span> <span data-ttu-id="7bd28-105">コマンドレットを使用する、 [PowerShellGet](/powershell/module/powershellget)モジュールを PowerShell ギャラリーからパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7bd28-105">You use the cmdlets in the [PowerShellGet](/powershell/module/powershellget) module to install packages from the PowerShell Gallery.</span></span> <span data-ttu-id="7bd28-106">PowerShell ギャラリーから項目をダウンロードするのにサインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7bd28-106">You do not need to sign in to download items from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="7bd28-107">PowerShell ギャラリーから直接パッケージをダウンロードすることもできますが、この方法はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="7bd28-107">It is possible to download a package from the PowerShell Gallery directly, but this is not a recommended approach.</span></span>
> <span data-ttu-id="7bd28-108">詳細については、「[パッケージの手動ダウンロード](/powershell/gallery/how-to/working-with-packages/manual-download)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bd28-108">For more details, see [Manual Package Download](/powershell/gallery/how-to/working-with-packages/manual-download).</span></span>

## <a name="discovering-packages-from-the-powershell-gallery"></a><span data-ttu-id="7bd28-109">PowerShell ギャラリーでのパッケージの検出</span><span class="sxs-lookup"><span data-stu-id="7bd28-109">Discovering packages from the PowerShell Gallery</span></span>

<span data-ttu-id="7bd28-110">使用して、PowerShell ギャラリーでパッケージを見つけることができます、**検索**PowerShell ギャラリーの上のコントロール[ホーム ページ](https://www.powershellgallery.com)、またはモジュールおよびスクリプトを参照してから、[パッケージ ページ](https://www.powershellgallery.com/packages).</span><span class="sxs-lookup"><span data-stu-id="7bd28-110">You can find packages in the PowerShell Gallery by using the **Search** control on the PowerShell Gallery's [home page](https://www.powershellgallery.com), or by browsing through the Modules and Scripts from the [Packages page](https://www.powershellgallery.com/packages).</span></span> <span data-ttu-id="7bd28-111">実行して、PowerShell ギャラリーからパッケージを検索することもできます、 [Find-module][]、 [Find-dscresource]、および[Find-script][]コマンドレットは、パッケージの種類に応じて`-Repository PSGallery`します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-111">You can also find packages from the PowerShell Gallery by running the [Find-Module][], [Find-DscResource], and [Find-Script][] cmdlets, depending on the package type, with `-Repository PSGallery`.</span></span>

<span data-ttu-id="7bd28-112">次のパラメーターを使用して、ギャラリーからの結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-112">You can filter results from the Gallery by using the following parameters:</span></span>

- <span data-ttu-id="7bd28-113">名前</span><span class="sxs-lookup"><span data-stu-id="7bd28-113">Name</span></span>
- <span data-ttu-id="7bd28-114">AllVersions</span><span class="sxs-lookup"><span data-stu-id="7bd28-114">AllVersions</span></span>
- <span data-ttu-id="7bd28-115">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="7bd28-115">MinimumVersion</span></span>
- <span data-ttu-id="7bd28-116">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="7bd28-116">RequiredVersion</span></span>
- <span data-ttu-id="7bd28-117">タグ</span><span class="sxs-lookup"><span data-stu-id="7bd28-117">Tag</span></span>
- <span data-ttu-id="7bd28-118">Includes</span><span class="sxs-lookup"><span data-stu-id="7bd28-118">Includes</span></span>
- <span data-ttu-id="7bd28-119">DscResource</span><span class="sxs-lookup"><span data-stu-id="7bd28-119">DscResource</span></span>
- <span data-ttu-id="7bd28-120">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="7bd28-120">RoleCapability</span></span>
- <span data-ttu-id="7bd28-121">コマンド</span><span class="sxs-lookup"><span data-stu-id="7bd28-121">Command</span></span>
- <span data-ttu-id="7bd28-122">フィルター</span><span class="sxs-lookup"><span data-stu-id="7bd28-122">Filter</span></span>

<span data-ttu-id="7bd28-123">ギャラリー内の特定の DSC リソースのみを検出したい場合は、[Find-DscResource] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-123">If you're only interested in discovering specific DSC resources in the Gallery, you can run the [Find-DscResource] cmdlet.</span></span> <span data-ttu-id="7bd28-124">Find-DscResource では、ギャラリーに含まれている DSC リソースのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-124">Find-DscResource returns data on DSC resources contained in the Gallery.</span></span>
<span data-ttu-id="7bd28-125">DSC リソースは常にモジュールの一部として配布されるため、この DSC リソースをインストールする場合も [Install-Module][] を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bd28-125">Because DSC resources are always delivered as part of a module, you still need to run [Install-Module][] to install those DSC resources.</span></span>

## <a name="learning-about-packages-in-the-powershell-gallery"></a><span data-ttu-id="7bd28-126">PowerShell ギャラリーのパッケージの詳細</span><span class="sxs-lookup"><span data-stu-id="7bd28-126">Learning about packages in the PowerShell Gallery</span></span>

<span data-ttu-id="7bd28-127">関心のあるパッケージを特定できたら、その詳細を入手することができます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-127">Once you've identified a package that you're interested in, you may want to learn more about it.</span></span> <span data-ttu-id="7bd28-128">これは、ギャラリー上でパッケージの特定のページを調べると見つかります。</span><span class="sxs-lookup"><span data-stu-id="7bd28-128">You can do this by examining that package's specific page on the Gallery.</span></span> <span data-ttu-id="7bd28-129">そのページでは、そのパッケージと共にアップロードされているメタデータをすべて参照することができます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-129">On that page, you'll be able to see all of the metadata uploaded with the package.</span></span> <span data-ttu-id="7bd28-130">このメタデータはパッケージの作成者が提供するものであり、Microsoft で検証したものではありません。</span><span class="sxs-lookup"><span data-stu-id="7bd28-130">This metadata is provided by the package's author, and is not verified by Microsoft.</span></span> <span data-ttu-id="7bd28-131">パッケージの所有者は、パッケージの公開に使用したギャラリーのアカウントと厳密に関連付けられており、[作成者] フィールドよりも信頼性があります。</span><span class="sxs-lookup"><span data-stu-id="7bd28-131">The Owner of the package is strongly tied to the Gallery account used to publish the package, and is more trustworthy than the Author field.</span></span>

<span data-ttu-id="7bd28-132">誠意をもって公開されていると思われないパッケージが見つかった場合は、そのパッケージのページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bd28-132">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

<span data-ttu-id="7bd28-133">[Find-Module][] または [Find-Script][] を実行している場合、返される PSGetModuleInfo オブジェクトにこのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-133">If you're running [Find-Module][] or [Find-Script][], you can view this data in the returned PSGetModuleInfo object.</span></span> <span data-ttu-id="7bd28-134">たとえば、`Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` を実行すると、</span><span class="sxs-lookup"><span data-stu-id="7bd28-134">For example, running `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member`</span></span>
<span data-ttu-id="7bd28-135">ギャラリーの PSReadLine モジュールのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-135">returns data on the PSReadLine module in the Gallery.</span></span>

## <a name="downloading-packages-from-the-powershell-gallery"></a><span data-ttu-id="7bd28-136">PowerShell ギャラリーでのパッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="7bd28-136">Downloading packages from the PowerShell Gallery</span></span>

<span data-ttu-id="7bd28-137">PowerShell ギャラリーからパッケージをダウンロードするとき、次のプロセスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7bd28-137">We encourage the following process when downloading packages from the PowerShell Gallery:</span></span>

### <a name="inspect"></a><span data-ttu-id="7bd28-138">検査</span><span class="sxs-lookup"><span data-stu-id="7bd28-138">Inspect</span></span>

<span data-ttu-id="7bd28-139">検査のためにギャラリーからパッケージをダウンロードするには、パッケージの種類に応じて [Save-Module][] または [Save-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-139">To download a package from the Gallery for inspection, run either the [Save-Module][] or [Save-Script][] cmdlet, depending on the package type.</span></span> <span data-ttu-id="7bd28-140">これにより、パッケージをインストールすることなくローカルに保存し、パッケージの内容を検査することができます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-140">This lets you save the package locally without installing it, and inspect the package contents.</span></span> <span data-ttu-id="7bd28-141">保存したパッケージは必ず手動で削除してください。</span><span class="sxs-lookup"><span data-stu-id="7bd28-141">Remember to delete the saved package manually.</span></span>

<span data-ttu-id="7bd28-142">このパッケージの一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="7bd28-142">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>
<span data-ttu-id="7bd28-143">このギャラリーのパッケージの内容とコードは、インストールする前に確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7bd28-143">Microsoft recommends that you review the contents and code of packages on this gallery prior to installation.</span></span>

<span data-ttu-id="7bd28-144">誠意をもって公開されていると思われないパッケージが見つかった場合は、そのパッケージのページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bd28-144">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

### <a name="install"></a><span data-ttu-id="7bd28-145">インストール</span><span class="sxs-lookup"><span data-stu-id="7bd28-145">Install</span></span>

<span data-ttu-id="7bd28-146">使用のためにギャラリーからパッケージをインストールするには、パッケージの種類に応じて [Install-Module][] または [Install-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-146">To install a package from the Gallery for use, run either the [Install-Module][] or [Install-Script][] cmdlet, depending on the package type.</span></span>

<span data-ttu-id="7bd28-147">[Install-Module][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Modules` にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7bd28-147">[Install-Module][] installs the module to `$env:ProgramFiles\WindowsPowerShell\Modules` by default.</span></span>
<span data-ttu-id="7bd28-148">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="7bd28-148">This requires an administrator account.</span></span> <span data-ttu-id="7bd28-149">`-Scope CurrentUser` パラメーターを追加する場合は、モジュールは `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-149">If you add the `-Scope CurrentUser` parameter, the module is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` .</span></span>

<span data-ttu-id="7bd28-150">[Install-Script][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Scripts` にスクリプトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7bd28-150">[Install-Script][] installs the script to `$env:ProgramFiles\WindowsPowerShell\Scripts` by default.</span></span>
<span data-ttu-id="7bd28-151">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="7bd28-151">This requires an administrator account.</span></span> <span data-ttu-id="7bd28-152">`-Scope CurrentUser` パラメーターを追加する場合は、スクリプトは `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-152">If you add the `-Scope CurrentUser` parameter, the script is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` .</span></span>

<span data-ttu-id="7bd28-153">既定では、[Install-Module][] および [Install-Script][] は最新バージョンのパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7bd28-153">By default, [Install-Module][] and [Install-Script][] installs the most current version of a package.</span></span>
<span data-ttu-id="7bd28-154">前のバージョンのパッケージをインストールするには、`-RequiredVersion` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-154">To install an older version of the package, add the `-RequiredVersion` parameter.</span></span>

### <a name="deploy"></a><span data-ttu-id="7bd28-155">展開</span><span class="sxs-lookup"><span data-stu-id="7bd28-155">Deploy</span></span>

<span data-ttu-id="7bd28-156">Azure Automation に PowerShell ギャラリーからパッケージを展開する をクリックして**Azure Automation**、順にクリックします**Azure Automation にデプロイする**パッケージ詳細ページにします。</span><span class="sxs-lookup"><span data-stu-id="7bd28-156">To deploy a package from the PowerShell Gallery to Azure Automation, click **Azure Automation**, then click **Deploy to Azure Automation** on the package details page.</span></span> <span data-ttu-id="7bd28-157">Azure 管理ポータル、Azure アカウント資格情報を使用してサインインする場所にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-157">You are redirected to the Azure Management Portal where you sign in by using your Azure account credentials.</span></span> <span data-ttu-id="7bd28-158">Azure Automation にすべての依存関係を配置依存関係を持つパッケージを展開することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7bd28-158">Note that deploying packages with dependencies deploys all the dependencies to Azure Automation.</span></span> <span data-ttu-id="7bd28-159">[Azure Automation にデプロイする] ボタンは、**AzureAutomationNotSupported** タグをパッケージのメタデータに追加すると無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7bd28-159">The 'Deploy to Azure Automation' button can be disabled by adding the **AzureAutomationNotSupported** tag to your package metadata.</span></span>

<span data-ttu-id="7bd28-160">Azure Automation の詳細については、[Azure Automation](/azure/automation) のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7bd28-160">To learn more about Azure Automation, see the [Azure Automation](/azure/automation) documentation.</span></span>

## <a name="updating-packages-from-the-powershell-gallery"></a><span data-ttu-id="7bd28-161">PowerShell ギャラリーからのパッケージの更新</span><span class="sxs-lookup"><span data-stu-id="7bd28-161">Updating packages from the PowerShell Gallery</span></span>

<span data-ttu-id="7bd28-162">PowerShell ギャラリーからインストールされたパッケージを更新するには、[Update-Module][] または [Update-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-162">To update packages installed from the PowerShell Gallery, run either the [Update-Module][] or [Update-Script][] cmdlet.</span></span> <span data-ttu-id="7bd28-163">[Update-module] を実行してインストールされているすべてのモジュールを更新しようとしたときに、追加パラメーターなしで実行、 [Install-module][]します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-163">When run without any additional parameters, [Update-Module][] attempts to update all modules installed by running [Install-Module][].</span></span> <span data-ttu-id="7bd28-164">モジュールを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-164">To selectively update modules, add the `-Name` parameter.</span></span> 

<span data-ttu-id="7bd28-165">同様に、その他のパラメーターなしで実行時に [更新スクリプト] のが更新されますを実行してインストールされているすべてのスクリプト[Install-script][]します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-165">Similarly, when run without any additional parameters, [Update-Script][] also attempts to update all scripts installed by running [Install-Script][].</span></span> <span data-ttu-id="7bd28-166">スクリプトを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-166">To selectively update scripts, add the `-Name` parameter.</span></span>

## <a name="list-packages-that-you-have-installed-from-the-powershell-gallery"></a><span data-ttu-id="7bd28-167">PowerShell ギャラリーからインストールしたパッケージの一覧</span><span class="sxs-lookup"><span data-stu-id="7bd28-167">List packages that you have installed from the PowerShell Gallery</span></span>

<span data-ttu-id="7bd28-168">PowerShell ギャラリーからどのモジュールをインストールしたかを調べるには、[Get-InstalledModule][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-168">To find out which modules you have installed from the PowerShell Gallery, run the [Get-InstalledModule][] cmdlet.</span></span> <span data-ttu-id="7bd28-169">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるモジュールをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-169">This command lists all of the modules you have on your system that were installed directly from the PowerShell Gallery.</span></span>

<span data-ttu-id="7bd28-170">同様に、PowerShell ギャラリーからどのスクリプトをインストールしたかを調べるには、[Get-InstalledScript][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-170">Similarly, to find out which scripts you have installed from the PowerShell Gallery, run the [Get-InstalledScript][] cmdlet.</span></span> <span data-ttu-id="7bd28-171">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるスクリプトをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7bd28-171">This command lists all of the scripts you have on your system that were installed directly from the PowerShell Gallery.</span></span>

[Find-DscResource]: /powershell/module/powershellget/Find-DscResource
[Find-Module]: /powershell/module/powershellget/Find-Module
[Find-Script]: /powershell/module/powershellget/Find-Script
[Get-InstalledModule]: /powershell/module/powershellget/Get-InstalledModule
[Get-InstalledScript]: /powershell/module/powershellget/Get-InstalledScript
[Install-Module]: /powershell/module/powershellget/Install-Module
[Install-Script]: /powershell/module/powershellget/Install-Script
[Publish-Module]: /powershell/module/powershellget/Publish-Module
[Publish-Script]: /powershell/module/powershellget/Publish-Script
[Register-PSRepository]: /powershell/module/powershellget/Register-Repository
[Save-Module]: /powershell/module/powershellget/Save-Module
[Save-Script]: /powershell/module/powershellget/Save-Script

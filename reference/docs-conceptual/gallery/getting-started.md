---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリーの概要
ms.openlocfilehash: ee3fe7d9c65ad1a8f9ffd2ddec0f4ce6659bc3d5
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71328463"
---
# <a name="getting-started-with-the-powershell-gallery"></a><span data-ttu-id="145fe-103">PowerShell ギャラリーの概要</span><span class="sxs-lookup"><span data-stu-id="145fe-103">Getting Started with the PowerShell Gallery</span></span>

<span data-ttu-id="145fe-104">PowerShell ギャラリーは、ダウンロードして利用できるスクリプト、モジュール、DSC リソースが含まれるパッケージ リポジトリです。</span><span class="sxs-lookup"><span data-stu-id="145fe-104">The PowerShell Gallery is a package repository containing scripts, modules, and DSC resources you can download and leverage.</span></span> <span data-ttu-id="145fe-105">PowerShell ギャラリーからパッケージをインストールするには、[PowerShellGet](/powershell/module/powershellget) モジュールのコマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="145fe-105">You use the cmdlets in the [PowerShellGet](/powershell/module/powershellget) module to install packages from the PowerShell Gallery.</span></span> <span data-ttu-id="145fe-106">PowerShell ギャラリーから項目をダウンロードするのにサインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="145fe-106">You do not need to sign in to download items from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="145fe-107">PowerShell ギャラリーから直接パッケージをダウンロードすることもできますが、この方法はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="145fe-107">It is possible to download a package from the PowerShell Gallery directly, but this is not a recommended approach.</span></span> <span data-ttu-id="145fe-108">詳細については、「[パッケージの手動ダウンロード](how-to/working-with-packages/manual-download.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="145fe-108">For more details, see [Manual Package Download](how-to/working-with-packages/manual-download.md).</span></span>

## <a name="discovering-packages-from-the-powershell-gallery"></a><span data-ttu-id="145fe-109">PowerShell ギャラリーでのパッケージの検出</span><span class="sxs-lookup"><span data-stu-id="145fe-109">Discovering packages from the PowerShell Gallery</span></span>

<span data-ttu-id="145fe-110">PowerShell ギャラリーの[ホーム ページ](https://www.powershellgallery.com)の **[検索]** コントロールを使用して、または [[パッケージ] ページ](https://www.powershellgallery.com/packages)からモジュールとスクリプトを参照することによって、PowerShell ギャラリー内のパッケージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="145fe-110">You can find packages in the PowerShell Gallery by using the **Search** control on the PowerShell Gallery's [home page](https://www.powershellgallery.com), or by browsing through the Modules and Scripts from the [Packages page](https://www.powershellgallery.com/packages).</span></span> <span data-ttu-id="145fe-111">また、[Find-Module][]、[Find-DscResource]、[Find-Script][] コマンドレットを、パッケージの種類に応じて `-Repository PSGallery` を指定して実行すると、PowerShell ギャラリーからパッケージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="145fe-111">You can also find packages from the PowerShell Gallery by running the [Find-Module][], [Find-DscResource], and [Find-Script][] cmdlets, depending on the package type, with `-Repository PSGallery`.</span></span>

<span data-ttu-id="145fe-112">次のパラメーターを使用して、ギャラリーからの結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="145fe-112">You can filter results from the Gallery by using the following parameters:</span></span>

- <span data-ttu-id="145fe-113">名前</span><span class="sxs-lookup"><span data-stu-id="145fe-113">Name</span></span>
- <span data-ttu-id="145fe-114">AllVersions</span><span class="sxs-lookup"><span data-stu-id="145fe-114">AllVersions</span></span>
- <span data-ttu-id="145fe-115">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="145fe-115">MinimumVersion</span></span>
- <span data-ttu-id="145fe-116">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="145fe-116">RequiredVersion</span></span>
- <span data-ttu-id="145fe-117">タグ</span><span class="sxs-lookup"><span data-stu-id="145fe-117">Tag</span></span>
- <span data-ttu-id="145fe-118">Includes</span><span class="sxs-lookup"><span data-stu-id="145fe-118">Includes</span></span>
- <span data-ttu-id="145fe-119">DscResource</span><span class="sxs-lookup"><span data-stu-id="145fe-119">DscResource</span></span>
- <span data-ttu-id="145fe-120">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="145fe-120">RoleCapability</span></span>
- <span data-ttu-id="145fe-121">コマンド</span><span class="sxs-lookup"><span data-stu-id="145fe-121">Command</span></span>
- <span data-ttu-id="145fe-122">フィルター</span><span class="sxs-lookup"><span data-stu-id="145fe-122">Filter</span></span>

<span data-ttu-id="145fe-123">ギャラリー内の特定の DSC リソースのみを検出したい場合は、[Find-DscResource][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="145fe-123">If you're only interested in discovering specific DSC resources in the Gallery, you can run the [Find-DscResource][] cmdlet.</span></span> <span data-ttu-id="145fe-124">Find-DscResource では、ギャラリーに含まれている DSC リソースのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="145fe-124">Find-DscResource returns data on DSC resources contained in the Gallery.</span></span> <span data-ttu-id="145fe-125">DSC リソースは常にモジュールの一部として配布されるため、この DSC リソースをインストールする場合も [Install-Module][] を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="145fe-125">Because DSC resources are always delivered as part of a module, you still need to run [Install-Module][] to install those DSC resources.</span></span>

## <a name="learning-about-packages-in-the-powershell-gallery"></a><span data-ttu-id="145fe-126">PowerShell ギャラリーのパッケージの詳細</span><span class="sxs-lookup"><span data-stu-id="145fe-126">Learning about packages in the PowerShell Gallery</span></span>

<span data-ttu-id="145fe-127">関心のあるパッケージを特定できたら、その詳細を入手することができます。</span><span class="sxs-lookup"><span data-stu-id="145fe-127">Once you've identified a package that you're interested in, you may want to learn more about it.</span></span> <span data-ttu-id="145fe-128">これは、ギャラリー上でパッケージの特定のページを調べると見つかります。</span><span class="sxs-lookup"><span data-stu-id="145fe-128">You can do this by examining that package's specific page on the Gallery.</span></span> <span data-ttu-id="145fe-129">そのページでは、そのパッケージと共にアップロードされているメタデータをすべて参照することができます。</span><span class="sxs-lookup"><span data-stu-id="145fe-129">On that page, you'll be able to see all of the metadata uploaded with the package.</span></span> <span data-ttu-id="145fe-130">このメタデータはパッケージの作成者が提供するものであり、Microsoft で検証したものではありません。</span><span class="sxs-lookup"><span data-stu-id="145fe-130">This metadata is provided by the package's author, and is not verified by Microsoft.</span></span> <span data-ttu-id="145fe-131">パッケージの所有者は、パッケージの公開に使用したギャラリーのアカウントと厳密に関連付けられており、[作成者] フィールドよりも信頼性があります。</span><span class="sxs-lookup"><span data-stu-id="145fe-131">The Owner of the package is strongly tied to the Gallery account used to publish the package, and is more trustworthy than the Author field.</span></span>

<span data-ttu-id="145fe-132">誠意をもって公開されていると思われないパッケージが見つかった場合は、そのパッケージのページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="145fe-132">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

<span data-ttu-id="145fe-133">[Find-Module][] または [Find-Script][] を実行している場合、返される PSGetModuleInfo オブジェクトにこのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="145fe-133">If you're running [Find-Module][] or [Find-Script][], you can view this data in the returned PSGetModuleInfo object.</span></span> <span data-ttu-id="145fe-134">たとえば、`Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` を実行すると、ギャラリーの PSReadLine モジュールのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="145fe-134">For example, running `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` returns data on the PSReadLine module in the Gallery.</span></span>

## <a name="downloading-packages-from-the-powershell-gallery"></a><span data-ttu-id="145fe-135">PowerShell ギャラリーでのパッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="145fe-135">Downloading packages from the PowerShell Gallery</span></span>

<span data-ttu-id="145fe-136">PowerShell ギャラリーからパッケージをダウンロードするとき、次のプロセスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="145fe-136">We encourage the following process when downloading packages from the PowerShell Gallery:</span></span>

### <a name="inspect"></a><span data-ttu-id="145fe-137">検査</span><span class="sxs-lookup"><span data-stu-id="145fe-137">Inspect</span></span>

<span data-ttu-id="145fe-138">検査のためにギャラリーからパッケージをダウンロードするには、パッケージの種類に応じて [Save-Module][] または [Save-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="145fe-138">To download a package from the Gallery for inspection, run either the [Save-Module][] or [Save-Script][] cmdlet, depending on the package type.</span></span> <span data-ttu-id="145fe-139">これにより、パッケージをインストールすることなくローカルに保存し、パッケージの内容を検査することができます。</span><span class="sxs-lookup"><span data-stu-id="145fe-139">This lets you save the package locally without installing it, and inspect the package contents.</span></span> <span data-ttu-id="145fe-140">保存したパッケージは必ず手動で削除してください。</span><span class="sxs-lookup"><span data-stu-id="145fe-140">Remember to delete the saved package manually.</span></span>

<span data-ttu-id="145fe-141">このパッケージの一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="145fe-141">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span> <span data-ttu-id="145fe-142">このギャラリーのパッケージの内容とコードは、インストールする前に確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="145fe-142">Microsoft recommends that you review the contents and code of packages on this gallery prior to installation.</span></span>

<span data-ttu-id="145fe-143">誠意をもって公開されていると思われないパッケージが見つかった場合は、そのパッケージのページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="145fe-143">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

### <a name="install"></a><span data-ttu-id="145fe-144">インストール</span><span class="sxs-lookup"><span data-stu-id="145fe-144">Install</span></span>

<span data-ttu-id="145fe-145">使用のためにギャラリーからパッケージをインストールするには、パッケージの種類に応じて [Install-Module][] または [Install-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="145fe-145">To install a package from the Gallery for use, run either the [Install-Module][] or [Install-Script][] cmdlet, depending on the package type.</span></span>

<span data-ttu-id="145fe-146">[Install-Module][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Modules` にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="145fe-146">[Install-Module][] installs the module to `$env:ProgramFiles\WindowsPowerShell\Modules` by default.</span></span>
<span data-ttu-id="145fe-147">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="145fe-147">This requires an administrator account.</span></span> <span data-ttu-id="145fe-148">`-Scope CurrentUser` パラメーターを追加する場合は、モジュールは `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="145fe-148">If you add the `-Scope CurrentUser` parameter, the module is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` .</span></span>

<span data-ttu-id="145fe-149">[Install-Script][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Scripts` にスクリプトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="145fe-149">[Install-Script][] installs the script to `$env:ProgramFiles\WindowsPowerShell\Scripts` by default.</span></span>
<span data-ttu-id="145fe-150">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="145fe-150">This requires an administrator account.</span></span> <span data-ttu-id="145fe-151">`-Scope CurrentUser` パラメーターを追加する場合は、スクリプトは `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="145fe-151">If you add the `-Scope CurrentUser` parameter, the script is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` .</span></span>

<span data-ttu-id="145fe-152">既定では、[Install-Module][] および [Install-Script][] は最新バージョンのパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="145fe-152">By default, [Install-Module][] and [Install-Script][] installs the most current version of a package.</span></span> <span data-ttu-id="145fe-153">前のバージョンのパッケージをインストールするには、`-RequiredVersion` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="145fe-153">To install an older version of the package, add the `-RequiredVersion` parameter.</span></span>

### <a name="deploy"></a><span data-ttu-id="145fe-154">展開</span><span class="sxs-lookup"><span data-stu-id="145fe-154">Deploy</span></span>

<span data-ttu-id="145fe-155">パッケージを PowerShell ギャラリーから Azure Automation にデプロイするには、 **[Azure Automation]** をクリックした後、パッケージの詳細ページで **[Deploy to Azure Automation]\(Azure Automation にデプロイする\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="145fe-155">To deploy a package from the PowerShell Gallery to Azure Automation, click **Azure Automation**, then click **Deploy to Azure Automation** on the package details page.</span></span> <span data-ttu-id="145fe-156">Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="145fe-156">You are redirected to the Azure Management Portal where you sign in by using your Azure account credentials.</span></span> <span data-ttu-id="145fe-157">依存関係のあるパッケージをデプロイすると、すべての依存関係が Azure Automation にデプロイされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="145fe-157">Note that deploying packages with dependencies deploys all the dependencies to Azure Automation.</span></span> <span data-ttu-id="145fe-158">[Azure Automation にデプロイする] ボタンは、**AzureAutomationNotSupported** タグをパッケージのメタデータに追加すると無効にできます。</span><span class="sxs-lookup"><span data-stu-id="145fe-158">The 'Deploy to Azure Automation' button can be disabled by adding the **AzureAutomationNotSupported** tag to your package metadata.</span></span>

<span data-ttu-id="145fe-159">Azure Automation の詳細については、[Azure Automation](/azure/automation) のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="145fe-159">To learn more about Azure Automation, see the [Azure Automation](/azure/automation) documentation.</span></span>

## <a name="updating-packages-from-the-powershell-gallery"></a><span data-ttu-id="145fe-160">PowerShell ギャラリーからのパッケージの更新</span><span class="sxs-lookup"><span data-stu-id="145fe-160">Updating packages from the PowerShell Gallery</span></span>

<span data-ttu-id="145fe-161">PowerShell ギャラリーからインストールされたパッケージを更新するには、[Update-Module][] または [Update-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="145fe-161">To update packages installed from the PowerShell Gallery, run either the [Update-Module][] or [Update-Script][] cmdlet.</span></span> <span data-ttu-id="145fe-162">パラメーターを追加せずに [Update-Module][] を実行すると、[Install-Module][] を実行してインストールされたすべてのモジュールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="145fe-162">When run without any additional parameters, [Update-Module][] attempts to update all modules installed by running [Install-Module][].</span></span> <span data-ttu-id="145fe-163">モジュールを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="145fe-163">To selectively update modules, add the `-Name` parameter.</span></span>

<span data-ttu-id="145fe-164">同様に、パラメーターを追加せずに [Update-Script][] を実行すると、[Install-Script][] を実行してインストールされたすべてのスクリプトが更新されます。</span><span class="sxs-lookup"><span data-stu-id="145fe-164">Similarly, when run without any additional parameters, [Update-Script][] also attempts to update all scripts installed by running [Install-Script][].</span></span> <span data-ttu-id="145fe-165">スクリプトを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="145fe-165">To selectively update scripts, add the `-Name` parameter.</span></span>

## <a name="list-packages-that-you-have-installed-from-the-powershell-gallery"></a><span data-ttu-id="145fe-166">PowerShell ギャラリーからインストールしたパッケージの一覧</span><span class="sxs-lookup"><span data-stu-id="145fe-166">List packages that you have installed from the PowerShell Gallery</span></span>

<span data-ttu-id="145fe-167">PowerShell ギャラリーからどのモジュールをインストールしたかを調べるには、[Get-InstalledModule][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="145fe-167">To find out which modules you have installed from the PowerShell Gallery, run the [Get-InstalledModule][] cmdlet.</span></span> <span data-ttu-id="145fe-168">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるモジュールをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="145fe-168">This command lists all of the modules you have on your system that were installed directly from the PowerShell Gallery.</span></span>

<span data-ttu-id="145fe-169">同様に、PowerShell ギャラリーからどのスクリプトをインストールしたかを調べるには、[Get-InstalledScript][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="145fe-169">Similarly, to find out which scripts you have installed from the PowerShell Gallery, run the [Get-InstalledScript][] cmdlet.</span></span> <span data-ttu-id="145fe-170">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるスクリプトをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="145fe-170">This command lists all the scripts you have on your system that were installed directly from the PowerShell Gallery.</span></span>

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
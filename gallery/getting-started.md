---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリーの概要
ms.openlocfilehash: 85b0a754aba25d850dc918024419318554f92b33
ms.sourcegitcommit: e76665315fd928bf85210778f1fea2be15264fea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "50225677"
---
# <a name="getting-started-with-the-powershell-gallery"></a><span data-ttu-id="8f156-103">PowerShell ギャラリーの概要</span><span class="sxs-lookup"><span data-stu-id="8f156-103">Getting Started with the PowerShell Gallery</span></span>

<span data-ttu-id="8f156-104">PowerShell ギャラリーからパッケージをインストールする適切な方法は、[PowerShellGet](/powershell/module/powershellget) モジュールでコマンドレットを使用することです。</span><span class="sxs-lookup"><span data-stu-id="8f156-104">The proper way to install packages from the PowerShell Gallery is to use the cmdlets in the [PowerShellGet](/powershell/module/powershellget) module.</span></span> <span data-ttu-id="8f156-105">PowerShell ギャラリーから項目をダウンロードするのにサインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f156-105">You do not need to sign in to download items from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="8f156-106">PowerShell ギャラリーから直接パッケージをダウンロードすることもできますが、この方法はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="8f156-106">It is possible to download a package from the PowerShell Gallery directly, but this is not a recommended approach.</span></span>
> <span data-ttu-id="8f156-107">詳細については、「[パッケージの手動ダウンロード](/powershell/gallery/how-to/working-with-packages/manual-download)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f156-107">For more details, see [Manual Package Download](/powershell/gallery/how-to/working-with-packages/manual-download).</span></span>

## <a name="discovering-packages-from-the-powershell-gallery"></a><span data-ttu-id="8f156-108">PowerShell ギャラリーでのパッケージの検出</span><span class="sxs-lookup"><span data-stu-id="8f156-108">Discovering packages from the PowerShell Gallery</span></span>

<span data-ttu-id="8f156-109">この Web サイトで**検索**コントロールを使用するか、[モジュールとスクリプト] ページを閲覧すると PowerShell ギャラリーのパッケージが見つかります。</span><span class="sxs-lookup"><span data-stu-id="8f156-109">You can find packages in the PowerShell Gallery by using the **Search** control on this website, or by browsing through the Modules and Scripts pages.</span></span> <span data-ttu-id="8f156-110">また、[Find-Module][] および [Find-Script][] コマンドレットを、パッケージの種類に応じて `-Repository PSGallery` を指定して実行すると、PowerShell ギャラリーからパッケージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8f156-110">You can also find packages from the PowerShell Gallery by running the [Find-Module][] and [Find-Script][] cmdlets, depending on the item type, with `-Repository PSGallery`.</span></span>

<span data-ttu-id="8f156-111">次のパラメーターを使用すると、ギャラリーからの結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="8f156-111">Filtering results from the Gallery can be done by using the following parameters:</span></span>

- <span data-ttu-id="8f156-112">名前</span><span class="sxs-lookup"><span data-stu-id="8f156-112">Name</span></span>
- <span data-ttu-id="8f156-113">AllVersions</span><span class="sxs-lookup"><span data-stu-id="8f156-113">AllVersions</span></span>
- <span data-ttu-id="8f156-114">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="8f156-114">MinimumVersion</span></span>
- <span data-ttu-id="8f156-115">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="8f156-115">RequiredVersion</span></span>
- <span data-ttu-id="8f156-116">タグ</span><span class="sxs-lookup"><span data-stu-id="8f156-116">Tag</span></span>
- <span data-ttu-id="8f156-117">Includes</span><span class="sxs-lookup"><span data-stu-id="8f156-117">Includes</span></span>
- <span data-ttu-id="8f156-118">DscResource</span><span class="sxs-lookup"><span data-stu-id="8f156-118">DscResource</span></span>
- <span data-ttu-id="8f156-119">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="8f156-119">RoleCapability</span></span>
- <span data-ttu-id="8f156-120">コマンド</span><span class="sxs-lookup"><span data-stu-id="8f156-120">Command</span></span>
- <span data-ttu-id="8f156-121">フィルター</span><span class="sxs-lookup"><span data-stu-id="8f156-121">Filter</span></span>

<span data-ttu-id="8f156-122">ギャラリー内の特定の DSC リソースのみを検出したい場合は、[Find-DscResource] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f156-122">If you're only interested in discovering specific DSC resources in the Gallery, you can run the [Find-DscResource] cmdlet.</span></span> <span data-ttu-id="8f156-123">Find-DscResource では、ギャラリーに含まれている DSC リソースのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="8f156-123">Find-DscResource returns data on DSC resources contained in the Gallery.</span></span>
<span data-ttu-id="8f156-124">DSC リソースは常にモジュールの一部として配布されるため、この DSC リソースをインストールする場合も [Install-Module][] を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f156-124">Because DSC resources are always delivered as part of a module, you still need to run [Install-Module][] to install those DSC resources.</span></span>

## <a name="learning-about-packages-in-the-powershell-gallery"></a><span data-ttu-id="8f156-125">PowerShell ギャラリーのパッケージの詳細</span><span class="sxs-lookup"><span data-stu-id="8f156-125">Learning about packages in the PowerShell Gallery</span></span>

<span data-ttu-id="8f156-126">関心のあるパッケージを特定できたら、その詳細を入手することができます。</span><span class="sxs-lookup"><span data-stu-id="8f156-126">Once you've identified a package that you're interested in, you may want to learn more about it.</span></span> <span data-ttu-id="8f156-127">これは、ギャラリー上でパッケージの特定のページを調べると見つかります。</span><span class="sxs-lookup"><span data-stu-id="8f156-127">You can do this by examining that package's specific page on the Gallery.</span></span> <span data-ttu-id="8f156-128">そのページでは、そのパッケージと共にアップロードされているメタデータをすべて参照することができます。</span><span class="sxs-lookup"><span data-stu-id="8f156-128">On that page, you'll be able to see all of the metadata uploaded with the package.</span></span> <span data-ttu-id="8f156-129">このメタデータはパッケージの作成者が提供するものであり、Microsoft で検証したものではありません。</span><span class="sxs-lookup"><span data-stu-id="8f156-129">This metadata is provided by the package's author, and is not verified by Microsoft.</span></span> <span data-ttu-id="8f156-130">パッケージの所有者は、パッケージの公開に使用したギャラリーのアカウントと厳密に関連付けられており、[作成者] フィールドよりも信頼性があります。</span><span class="sxs-lookup"><span data-stu-id="8f156-130">The Owner of the package is strongly tied to the Gallery account used to publish the package, and is more trustworthy than the Author field.</span></span>

<span data-ttu-id="8f156-131">誠意をもって公開されていると思われないパッケージが見つかった場合は、そのパッケージのページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f156-131">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

<span data-ttu-id="8f156-132">[Find-Module][] または [Find-Script][] を実行している場合、返される PSGetModuleInfo オブジェクトにこのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f156-132">If you're running [Find-Module][] or [Find-Script][], you can view this data in the returned PSGetModuleInfo object.</span></span> <span data-ttu-id="8f156-133">たとえば、`Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` を実行すると、</span><span class="sxs-lookup"><span data-stu-id="8f156-133">For example, running `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member`</span></span>
<span data-ttu-id="8f156-134">ギャラリーの PSReadLine モジュールのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="8f156-134">returns data on the PSReadLine module in the Gallery.</span></span>

## <a name="downloading-packages-from-the-powershell-gallery"></a><span data-ttu-id="8f156-135">PowerShell ギャラリーでのパッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="8f156-135">Downloading packages from the PowerShell Gallery</span></span>

<span data-ttu-id="8f156-136">PowerShell ギャラリーからパッケージをダウンロードするとき、次のプロセスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8f156-136">We encourage the following process when downloading packages from the PowerShell Gallery:</span></span>

### <a name="inspect"></a><span data-ttu-id="8f156-137">検査</span><span class="sxs-lookup"><span data-stu-id="8f156-137">Inspect</span></span>

<span data-ttu-id="8f156-138">検査のためにギャラリーからパッケージをダウンロードするには、パッケージの種類に応じて [Save-Module][] または [Save-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f156-138">To download a package from the Gallery for inspection, run either the [Save-Module][] or [Save-Script][] cmdlet, depending on the package type.</span></span> <span data-ttu-id="8f156-139">これにより、パッケージをインストールすることなくローカルに保存し、パッケージの内容を検査することができます。</span><span class="sxs-lookup"><span data-stu-id="8f156-139">This lets you save the package locally without installing it, and inspect the package contents.</span></span> <span data-ttu-id="8f156-140">保存したパッケージは必ず手動で削除してください。</span><span class="sxs-lookup"><span data-stu-id="8f156-140">Remember to delete the saved package manually.</span></span>

<span data-ttu-id="8f156-141">このパッケージの一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="8f156-141">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>
<span data-ttu-id="8f156-142">このギャラリーのパッケージの内容とコードは、インストールする前に確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8f156-142">Microsoft recommends that you review the contents and code of packages on this gallery prior to installation.</span></span>

<span data-ttu-id="8f156-143">誠意をもって公開されていると思われないパッケージが見つかった場合は、そのパッケージのページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f156-143">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

### <a name="install"></a><span data-ttu-id="8f156-144">[インストール]</span><span class="sxs-lookup"><span data-stu-id="8f156-144">Install</span></span>

<span data-ttu-id="8f156-145">使用のためにギャラリーからパッケージをインストールするには、パッケージの種類に応じて [Install-Module][] または [Install-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f156-145">To install a package from the Gallery for use, run either the [Install-Module][] or [Install-Script][] cmdlet, depending on the package type.</span></span>

<span data-ttu-id="8f156-146">[Install-Module][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Modules` にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8f156-146">[Install-Module][] installs the module to `$env:ProgramFiles\WindowsPowerShell\Modules` by default.</span></span>
<span data-ttu-id="8f156-147">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f156-147">This requires an administrator account.</span></span> <span data-ttu-id="8f156-148">`-Scope CurrentUser` パラメーターを追加する場合は、モジュールは `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8f156-148">If you add the `-Scope CurrentUser` parameter, the module is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` .</span></span>

<span data-ttu-id="8f156-149">[Install-Script][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Scripts` にスクリプトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8f156-149">[Install-Script][] installs the script to `$env:ProgramFiles\WindowsPowerShell\Scripts` by default.</span></span>
<span data-ttu-id="8f156-150">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f156-150">This requires an administrator account.</span></span> <span data-ttu-id="8f156-151">`-Scope CurrentUser` パラメーターを追加する場合は、スクリプトは `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8f156-151">If you add the `-Scope CurrentUser` parameter, the script is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` .</span></span>

<span data-ttu-id="8f156-152">既定では、[Install-Module][] および [Install-Script][] は最新バージョンのパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8f156-152">By default, [Install-Module][] and [Install-Script][] installs the most current version of a package.</span></span>
<span data-ttu-id="8f156-153">前のバージョンのパッケージをインストールするには、`-RequiredVersion` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f156-153">To install an older version of the package, add the `-RequiredVersion` parameter.</span></span>

### <a name="deploy"></a><span data-ttu-id="8f156-154">展開</span><span class="sxs-lookup"><span data-stu-id="8f156-154">Deploy</span></span>

<span data-ttu-id="8f156-155">パッケージを PowerShell ギャラリーから Azure Automation にデプロイするには、パッケージの詳細ページで **[Azure Automation にデプロイする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f156-155">To deploy a package from the PowerShell Gallery to Azure Automation, click **Deploy to Azure Automation** on the package details page.</span></span> <span data-ttu-id="8f156-156">Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="8f156-156">You will be redirected to the Azure Management Portal where you sign in by using your Azure account credentials.</span></span> <span data-ttu-id="8f156-157">依存関係のあるパッケージをデプロイすると、すべての依存関係が Azure Automation にデプロイされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8f156-157">Note that deploying packages with dependencies will deploy all the dependencies to Azure Automation.</span></span> <span data-ttu-id="8f156-158">[Azure Automation にデプロイする] ボタンは、**AzureAutomationNotSupported** タグをパッケージのメタデータに追加すると無効にできます。</span><span class="sxs-lookup"><span data-stu-id="8f156-158">The 'Deploy to Azure Automation' button can be disabled by adding the **AzureAutomationNotSupported** tag to your package metadata.</span></span>

<span data-ttu-id="8f156-159">Azure Automation の詳細については、[Azure Automation](/azure/automation) のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f156-159">To learn more about Azure Automation, see the [Azure Automation](/azure/automation) documentation.</span></span>

## <a name="updating-packages-from-the-powershell-gallery"></a><span data-ttu-id="8f156-160">PowerShell ギャラリーからのパッケージの更新</span><span class="sxs-lookup"><span data-stu-id="8f156-160">Updating packages from the PowerShell Gallery</span></span>

<span data-ttu-id="8f156-161">PowerShell ギャラリーからインストールされたパッケージを更新するには、[Update-Module][] または [Update-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f156-161">To update packages installed from the PowerShell Gallery, run either the [Update-Module][] or [Update-Script][] cmdlet.</span></span> <span data-ttu-id="8f156-162">パラメーターを追加せずに [Update-Module][] を実行すると、[Install-Module][] を実行してインストールされた各モジュールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="8f156-162">When run without any additional parameters, [Update-Module][] attempts to update each module installed by running [Install-Module][].</span></span> <span data-ttu-id="8f156-163">モジュールを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f156-163">To selectively update modules, add the `-Name` parameter.</span></span>

<span data-ttu-id="8f156-164">同様に、パラメーターを追加せずに [Update-Script][] を実行すると、[Install-Script][] を実行してインストールされた各スクリプトが更新されます。</span><span class="sxs-lookup"><span data-stu-id="8f156-164">Similarly, when run without any additional parameters, [Update-Script][] also attempts to update each script installed by running [Install-Script][].</span></span> <span data-ttu-id="8f156-165">スクリプトを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f156-165">To selectively update scripts, add the `-Name` parameter.</span></span>

## <a name="list-packages-that-you-have-installed-from-the-powershell-gallery"></a><span data-ttu-id="8f156-166">PowerShell ギャラリーからインストールしたパッケージの一覧</span><span class="sxs-lookup"><span data-stu-id="8f156-166">List packages that you have installed from the PowerShell Gallery</span></span>

<span data-ttu-id="8f156-167">PowerShell ギャラリーからどのモジュールをインストールしたかを調べるには、[Get-InstalledModule][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f156-167">To find out which modules you have installed from the PowerShell Gallery, run the [Get-InstalledModule][] cmdlet.</span></span> <span data-ttu-id="8f156-168">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるモジュールをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8f156-168">This command lists all of the modules you have on your system that were installed directly from the PowerShell Gallery.</span></span>

<span data-ttu-id="8f156-169">同様に、PowerShell ギャラリーからどのスクリプトをインストールしたかを調べるには、[Get-InstalledScript][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f156-169">Similarly, to find out which scripts you have installed from the PowerShell Gallery, run the [Get-InstalledScript][] cmdlet.</span></span> <span data-ttu-id="8f156-170">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるスクリプトをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8f156-170">This command lists all of the scripts you have on your system that were installed directly from the PowerShell Gallery.</span></span>

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

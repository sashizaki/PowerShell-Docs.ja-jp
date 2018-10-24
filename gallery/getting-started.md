---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリーの概要
ms.openlocfilehash: 39998df1a2bf9363dd008dc96a802157c8d691d7
ms.sourcegitcommit: e46b868f56f359909ff7c8230b1d1770935cce0e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45523058"
---
# <a name="get-started-with-the-powershell-gallery"></a><span data-ttu-id="12dea-103">PowerShell ギャラリーの概要</span><span class="sxs-lookup"><span data-stu-id="12dea-103">Get Started with the PowerShell Gallery</span></span>

<span data-ttu-id="12dea-104">PowerShell ギャラリーからアイテムをインストールする適切な方法は、[PowerShellGet](/powershell/module/powershellget) モジュールでコマンドレットを使用することです。</span><span class="sxs-lookup"><span data-stu-id="12dea-104">The proper way to install items from the PowerShell Gallery is to use the cmdlets in the [PowerShellGet](/powershell/module/powershellget) module.</span></span> <span data-ttu-id="12dea-105">PowerShell ギャラリーから項目をダウンロードするのにサインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="12dea-105">You do not need to sign in to download items from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="12dea-106">PowerShell ギャラリーから直接パッケージをダウンロードすることもできますが、この方法はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="12dea-106">It is possible to download a package from the PowerShell Gallery directly, but this is not a recommended approach.</span></span> <span data-ttu-id="12dea-107">詳細については、「[パッケージの手動ダウンロード](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/how-to/working-with-items/manual-download.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12dea-107">For more details, see [Manual Package Download](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/how-to/working-with-items/manual-download.md).</span></span>  


## <a name="discovering-items-from-the-powershell-gallery"></a><span data-ttu-id="12dea-108">PowerShell ギャラリーでの項目の検出</span><span class="sxs-lookup"><span data-stu-id="12dea-108">Discovering items from the PowerShell Gallery</span></span>

<span data-ttu-id="12dea-109">この Web サイトで**検索**コントロールを使用するか、[モジュールとスクリプト] ページを閲覧すると PowerShell ギャラリーの項目が見つかります。</span><span class="sxs-lookup"><span data-stu-id="12dea-109">You can find items in the PowerShell Gallery by using the **Search** control on this website, or by browsing through the Modules and Scripts pages.</span></span> <span data-ttu-id="12dea-110">また、[Find-Module][] および [Find-Script][] コマンドレットを、アイテムの種類に応じて `-Repository PSGallery` を指定して実行すると、PowerShell ギャラリーからアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="12dea-110">You can also find items from the PowerShell Gallery by running the [Find-Module][] and [Find-Script][] cmdlets, depending on the item type, with `-Repository PSGallery`.</span></span>

<span data-ttu-id="12dea-111">次のパラメーターを使用すると、ギャラリーからの結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="12dea-111">Filtering results from the Gallery can be done by using the following parameters:</span></span>

- <span data-ttu-id="12dea-112">名前</span><span class="sxs-lookup"><span data-stu-id="12dea-112">Name</span></span>
- <span data-ttu-id="12dea-113">AllVersions</span><span class="sxs-lookup"><span data-stu-id="12dea-113">AllVersions</span></span>
- <span data-ttu-id="12dea-114">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="12dea-114">MinimumVersion</span></span>
- <span data-ttu-id="12dea-115">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="12dea-115">RequiredVersion</span></span>
- <span data-ttu-id="12dea-116">タグ</span><span class="sxs-lookup"><span data-stu-id="12dea-116">Tag</span></span>
- <span data-ttu-id="12dea-117">Includes</span><span class="sxs-lookup"><span data-stu-id="12dea-117">Includes</span></span>
- <span data-ttu-id="12dea-118">DscResource</span><span class="sxs-lookup"><span data-stu-id="12dea-118">DscResource</span></span>
- <span data-ttu-id="12dea-119">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="12dea-119">RoleCapability</span></span>
- <span data-ttu-id="12dea-120">コマンド</span><span class="sxs-lookup"><span data-stu-id="12dea-120">Command</span></span>
- <span data-ttu-id="12dea-121">フィルター</span><span class="sxs-lookup"><span data-stu-id="12dea-121">Filter</span></span>

<span data-ttu-id="12dea-122">ギャラリー内の特定の DSC リソースのみを検出したい場合は、[Find-DscResource] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="12dea-122">If you're only interested in discovering specific DSC resources in the Gallery, you can run the [Find-DscResource] cmdlet.</span></span> <span data-ttu-id="12dea-123">Find-DscResource では、ギャラリーに含まれている DSC リソースのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="12dea-123">Find-DscResource returns data on DSC resources contained in the Gallery.</span></span>
<span data-ttu-id="12dea-124">DSC リソースは常にモジュールの一部として配布されるため、この DSC リソースをインストールする場合も [Install-Module][] を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12dea-124">Because DSC resources are always delivered as part of a module, you still need to run [Install-Module][] to install those DSC resources.</span></span>

## <a name="learning-about-items-in-the-powershell-gallery"></a><span data-ttu-id="12dea-125">PowerShell ギャラリーの項目の詳細</span><span class="sxs-lookup"><span data-stu-id="12dea-125">Learning about items in the PowerShell Gallery</span></span>

<span data-ttu-id="12dea-126">関心のある項目を特定できたら、その詳細を入手することができます。</span><span class="sxs-lookup"><span data-stu-id="12dea-126">Once you've identified an item you're interested in, you may want to learn more about it.</span></span> <span data-ttu-id="12dea-127">これは、ギャラリー上で項目の特定のページを調べると見つかります。</span><span class="sxs-lookup"><span data-stu-id="12dea-127">You can do this by examining that item's specific page on the Gallery.</span></span> <span data-ttu-id="12dea-128">そのページでは、その項目と共にアップロードされているメタデータをすべて参照することができます。</span><span class="sxs-lookup"><span data-stu-id="12dea-128">On that page, you'll be able to see all of the metadata uploaded with the item.</span></span> <span data-ttu-id="12dea-129">この項目のメタデータは項目の作成者が提供するものであり、Microsoft で検証したものではありません。</span><span class="sxs-lookup"><span data-stu-id="12dea-129">This metadata for an item is provided by the item's author, and is not verified by Microsoft.</span></span> <span data-ttu-id="12dea-130">項目の所有者は、項目の公開に使用したギャラリーのアカウントと厳密に関連付けられており、[作成者] フィールドよりも信頼性があります。</span><span class="sxs-lookup"><span data-stu-id="12dea-130">The Owner of the item is strongly tied to the Gallery account used to publish the item, and is more trustworthy than the Author field.</span></span>

<span data-ttu-id="12dea-131">誠意をもって公開されていると思われない項目が見つかった場合は、その項目のページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12dea-131">If you discover an item that you feel is not published in good faith, click **Report Abuse** on that item's page.</span></span>

<span data-ttu-id="12dea-132">[Find-Module][] または [Find-Script][] を実行している場合、返される PSGetModuleInfo オブジェクトにこのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="12dea-132">If you're running [Find-Module][] or [Find-Script][], you can view this data in the returned PSGetModuleInfo object.</span></span> <span data-ttu-id="12dea-133">たとえば、`Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` を実行すると、</span><span class="sxs-lookup"><span data-stu-id="12dea-133">For example, running `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member`</span></span>
<span data-ttu-id="12dea-134">ギャラリーの PSReadLine モジュールのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="12dea-134">returns data on the PSReadLine module in the Gallery.</span></span>

## <a name="downloading-items-from-the-powershell-gallery"></a><span data-ttu-id="12dea-135">PowerShell ギャラリーでの項目のダウンロード</span><span class="sxs-lookup"><span data-stu-id="12dea-135">Downloading items from the PowerShell Gallery</span></span>

<span data-ttu-id="12dea-136">PowerShell ギャラリーから項目をダウンロードするとき、次のプロセスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12dea-136">We encourage the following process when downloading items from the PowerShell Gallery:</span></span>

### <a name="inspect"></a><span data-ttu-id="12dea-137">検査</span><span class="sxs-lookup"><span data-stu-id="12dea-137">Inspect</span></span>

<span data-ttu-id="12dea-138">検査のためにギャラリーから項目をダウンロードするには、項目の種類に応じて [Save-Module][] または [Save-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="12dea-138">To download an item from the Gallery for inspection, run either the [Save-Module][] or [Save-Script][] cmdlet, depending on the item type.</span></span> <span data-ttu-id="12dea-139">これにより、項目をインストールすることなくローカルに保存し、項目の内容を検査することができます。</span><span class="sxs-lookup"><span data-stu-id="12dea-139">This lets you save the item locally without installing it, and inspect the item contents.</span></span> <span data-ttu-id="12dea-140">保存した項目は必ず手動で削除してください。</span><span class="sxs-lookup"><span data-stu-id="12dea-140">Remember to delete the saved item manually.</span></span>

<span data-ttu-id="12dea-141">この項目の一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="12dea-141">Some of these items are authored by Microsoft, and others are authored by the PowerShell community.</span></span>
<span data-ttu-id="12dea-142">このギャラリーの項目の内容とコードは、インストールする前に確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12dea-142">Microsoft recommends that you review the contents and code of items on this gallery prior to installation.</span></span>

<span data-ttu-id="12dea-143">誠意をもって公開されていると思われない項目が見つかった場合は、その項目のページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12dea-143">If you discover an item that you feel is not published in good faith, click **Report Abuse** on that item's page.</span></span>

### <a name="install"></a><span data-ttu-id="12dea-144">[インストール]</span><span class="sxs-lookup"><span data-stu-id="12dea-144">Install</span></span>

<span data-ttu-id="12dea-145">使用のためにギャラリーから項目をインストールするには、項目の種類に応じて [Install-Module][] または [Install-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="12dea-145">To install an item from the Gallery for use, run either the [Install-Module][] or [Install-Script][] cmdlet, depending on the item type.</span></span>

<span data-ttu-id="12dea-146">[Install-Module][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Modules` にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="12dea-146">[Install-Module][] installs the module to `$env:ProgramFiles\WindowsPowerShell\Modules` by default.</span></span>
<span data-ttu-id="12dea-147">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="12dea-147">This requires an administrator account.</span></span> <span data-ttu-id="12dea-148">`-Scope CurrentUser` パラメーターを追加する場合は、モジュールは `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="12dea-148">If you add the `-Scope CurrentUser` parameter, the module is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` .</span></span>

<span data-ttu-id="12dea-149">[Install-Script][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Scripts` にスクリプトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="12dea-149">[Install-Script][] installs the script to `$env:ProgramFiles\WindowsPowerShell\Scripts` by default.</span></span>
<span data-ttu-id="12dea-150">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="12dea-150">This requires an administrator account.</span></span> <span data-ttu-id="12dea-151">`-Scope CurrentUser` パラメーターを追加する場合は、スクリプトは `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="12dea-151">If you add the `-Scope CurrentUser` parameter, the script is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` .</span></span>

<span data-ttu-id="12dea-152">既定では、[Install-Module][] および [Install-Script][] は項目の最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="12dea-152">By default, [Install-Module][] and [Install-Script][] installs the most current version of an item.</span></span>
<span data-ttu-id="12dea-153">前のバージョンのアイテムをインストールするには、 `-RequiredVersion` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="12dea-153">To install an older version of the item, add the `-RequiredVersion` parameter.</span></span>

### <a name="deploy"></a><span data-ttu-id="12dea-154">展開</span><span class="sxs-lookup"><span data-stu-id="12dea-154">Deploy</span></span>

<span data-ttu-id="12dea-155">項目を PowerShell ギャラリーから Azure Automation にデプロイするには、項目の詳細ページで **[Azure Automation にデプロイする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12dea-155">To deploy an item from the PowerShell Gallery to Azure Automation, click **Deploy to Azure Automation** on the item details page.</span></span> <span data-ttu-id="12dea-156">Azure 管理ポータルにリダイレクトされるため、そこでAzure アカウント資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="12dea-156">You will be redirected to the Azure Management Portal, where you sign in by using your Azure account credentials.</span></span> <span data-ttu-id="12dea-157">依存関係のある項目をデプロイすると、すべての依存関係が Azure Automation にデプロイされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="12dea-157">Note that deploying items with dependencies will deploy all the dependencies to Azure Automation.</span></span> <span data-ttu-id="12dea-158">[Azure Automation にデプロイする] ボタンは、**AzureAutomationNotSupported** タグを項目のメタデータに追加すると無効にできます。</span><span class="sxs-lookup"><span data-stu-id="12dea-158">The 'Deploy to Azure Automation' button can be disabled by adding the **AzureAutomationNotSupported** tag to your item metadata.</span></span>

<span data-ttu-id="12dea-159">Azure Automation の詳細については、[Azure Automation](/azure/automation) のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12dea-159">To learn more about Azure Automation, see the [Azure Automation](/azure/automation) documentation.</span></span>

## <a name="updating-items-from-the-powershell-gallery"></a><span data-ttu-id="12dea-160">PowerShell ギャラリーからの項目の更新</span><span class="sxs-lookup"><span data-stu-id="12dea-160">Updating items from the PowerShell Gallery</span></span>

<span data-ttu-id="12dea-161">PowerShell ギャラリーからインストールされたアイテムを更新するには、[Update-Module][] または [Update-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="12dea-161">To update items installed from the PowerShell Gallery, run either the [Update-Module][] or [Update-Script][] cmdlet.</span></span> <span data-ttu-id="12dea-162">パラメーターを追加せずに [Update-Module][] を実行すると、[Install-Module][] を実行してインストールされた各モジュールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="12dea-162">When run without any additional parameters, [Update-Module][] attempts to update each module installed by running [Install-Module][].</span></span> <span data-ttu-id="12dea-163">モジュールを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="12dea-163">To selectively update modules, add the `-Name` parameter.</span></span>

<span data-ttu-id="12dea-164">同様に、パラメーターを追加せずに [Update-Script][] を実行すると、[Install-Script][] を実行してインストールされた各スクリプトが更新されます。</span><span class="sxs-lookup"><span data-stu-id="12dea-164">Similarly, when run without any additional parameters, [Update-Script][] also attempts to update each script installed by running [Install-Script][].</span></span> <span data-ttu-id="12dea-165">スクリプトを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="12dea-165">To selectively update scripts, add the `-Name` parameter.</span></span>

## <a name="list-items-that-you-have-installed-from-the-powershell-gallery"></a><span data-ttu-id="12dea-166">PowerShell ギャラリーからインストールした項目の一覧</span><span class="sxs-lookup"><span data-stu-id="12dea-166">List items that you have installed from the PowerShell Gallery</span></span>

<span data-ttu-id="12dea-167">PowerShell ギャラリーからどのモジュールをインストールしたかを調べるには、[Get-InstalledModule][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="12dea-167">To find out which modules you have installed from the PowerShell Gallery, run the [Get-InstalledModule][] cmdlet.</span></span> <span data-ttu-id="12dea-168">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるモジュールをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="12dea-168">This command lists all of the modules you have on your system that were installed directly from the PowerShell Gallery.</span></span>

<span data-ttu-id="12dea-169">同様に、PowerShell ギャラリーからどのスクリプトをインストールしたかを調べるには、[Get-InstalledScript][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="12dea-169">Similarly, to find out which scripts you have installed from the PowerShell Gallery, run the [Get-InstalledScript][] cmdlet.</span></span> <span data-ttu-id="12dea-170">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるスクリプトをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="12dea-170">This command lists all of the scripts you have on your system that were installed directly from the PowerShell Gallery.</span></span>

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
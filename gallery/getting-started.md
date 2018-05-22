---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリーの概要
ms.openlocfilehash: 83974698152e75efac66ea725a9c220486676d6f
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="get-started-with-the-powershell-gallery"></a><span data-ttu-id="b0481-103">PowerShell ギャラリーの概要</span><span class="sxs-lookup"><span data-stu-id="b0481-103">Get Started with the PowerShell Gallery</span></span>

<span data-ttu-id="b0481-104">PowerShell ギャラリーからシステムに項目をダウンロードするには、[PowerShellGet](/powershell/module/powershellget) モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0481-104">Downloading items from the PowerShell Gallery to your system requires the [PowerShellGet](/powershell/module/powershellget) module.</span></span> <span data-ttu-id="b0481-105">PowerShellGet モジュールは次のいずれかで見つかります。</span><span class="sxs-lookup"><span data-stu-id="b0481-105">You can find the PowerShellGet module in any of the following.</span></span> <span data-ttu-id="b0481-106">PowerShell ギャラリーから項目をダウンロードするのにサインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b0481-106">You do not need to sign in to download items from the PowerShell Gallery.</span></span>

## <a name="discovering-items-from-the-powershell-gallery"></a><span data-ttu-id="b0481-107">PowerShell ギャラリーでの項目の検出</span><span class="sxs-lookup"><span data-stu-id="b0481-107">Discovering items from the PowerShell Gallery</span></span>

<span data-ttu-id="b0481-108">この Web サイトで**検索**コントロールを使用するか、[モジュールとスクリプト] ページを閲覧すると PowerShell ギャラリーの項目が見つかります。</span><span class="sxs-lookup"><span data-stu-id="b0481-108">You can find items in the PowerShell Gallery by using the **Search** control on this website, or by browsing through the Modules and Scripts pages.</span></span> <span data-ttu-id="b0481-109">また、[Find-Module][] および [Find-Script][] コマンドレットを、アイテムの種類に応じて `-Repository PSGallery` を指定して実行すると、PowerShell ギャラリーからアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b0481-109">You can also find items from the PowerShell Gallery by running the [Find-Module][] and [Find-Script][] cmdlets, depending on the item type, with `-Repository PSGallery`.</span></span>

<span data-ttu-id="b0481-110">次のパラメーターを使用すると、ギャラリーからの結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="b0481-110">Filtering results from the Gallery can be done by using the following parameters:</span></span>

- <span data-ttu-id="b0481-111">名前</span><span class="sxs-lookup"><span data-stu-id="b0481-111">Name</span></span>
- <span data-ttu-id="b0481-112">AllVersions</span><span class="sxs-lookup"><span data-stu-id="b0481-112">AllVersions</span></span>
- <span data-ttu-id="b0481-113">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="b0481-113">MinimumVersion</span></span>
- <span data-ttu-id="b0481-114">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="b0481-114">RequiredVersion</span></span>
- <span data-ttu-id="b0481-115">タグ</span><span class="sxs-lookup"><span data-stu-id="b0481-115">Tag</span></span>
- <span data-ttu-id="b0481-116">Includes</span><span class="sxs-lookup"><span data-stu-id="b0481-116">Includes</span></span>
- <span data-ttu-id="b0481-117">DscResource</span><span class="sxs-lookup"><span data-stu-id="b0481-117">DscResource</span></span>
- <span data-ttu-id="b0481-118">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="b0481-118">RoleCapability</span></span>
- <span data-ttu-id="b0481-119">コマンド</span><span class="sxs-lookup"><span data-stu-id="b0481-119">Command</span></span>
- <span data-ttu-id="b0481-120">フィルター</span><span class="sxs-lookup"><span data-stu-id="b0481-120">Filter</span></span>

<span data-ttu-id="b0481-121">ギャラリー内の特定の DSC リソースのみを検出したい場合は、[Find-DscResource] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0481-121">If you're only interested in discovering specific DSC resources in the Gallery, you can run the [Find-DscResource] cmdlet.</span></span> <span data-ttu-id="b0481-122">Find-DscResource では、ギャラリーに含まれている DSC リソースのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="b0481-122">Find-DscResource returns data on DSC resources contained in the Gallery.</span></span>
<span data-ttu-id="b0481-123">DSC リソースは常にモジュールの一部として配布されるため、この DSC リソースをインストールする場合も [Install-Module][] を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0481-123">Because DSC resources are always delivered as part of a module, you still need to run [Install-Module][] to install those DSC resources.</span></span>

## <a name="learning-about-items-in-the-powershell-gallery"></a><span data-ttu-id="b0481-124">PowerShell ギャラリーの項目の詳細</span><span class="sxs-lookup"><span data-stu-id="b0481-124">Learning about items in the PowerShell Gallery</span></span>

<span data-ttu-id="b0481-125">関心のある項目を特定できたら、その詳細を入手することができます。</span><span class="sxs-lookup"><span data-stu-id="b0481-125">Once you've identified an item you're interested in, you may want to learn more about it.</span></span> <span data-ttu-id="b0481-126">これは、ギャラリー上で項目の特定のページを調べると見つかります。</span><span class="sxs-lookup"><span data-stu-id="b0481-126">You can do this by examining that item's specific page on the Gallery.</span></span> <span data-ttu-id="b0481-127">そのページでは、その項目と共にアップロードされているメタデータをすべて参照することができます。</span><span class="sxs-lookup"><span data-stu-id="b0481-127">On that page, you'll be able to see all of the metadata uploaded with the item.</span></span> <span data-ttu-id="b0481-128">この項目のメタデータは項目の作成者が提供するものであり、Microsoft で検証したものではありません。</span><span class="sxs-lookup"><span data-stu-id="b0481-128">This metadata for an item is provided by the item's author, and is not verified by Microsoft.</span></span> <span data-ttu-id="b0481-129">項目の所有者は、項目の公開に使用したギャラリーのアカウントと厳密に関連付けられており、[作成者] フィールドよりも信頼性があります。</span><span class="sxs-lookup"><span data-stu-id="b0481-129">The Owner of the item is strongly tied to the Gallery account used to publish the item, and is more trustworthy than the Author field.</span></span>

<span data-ttu-id="b0481-130">誠意をもって公開されていると思われない項目が見つかった場合は、その項目のページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0481-130">If you discover an item that you feel is not published in good faith, click **Report Abuse** on that item's page.</span></span>

<span data-ttu-id="b0481-131">[Find-Module][] または [Find-Script][] を実行している場合、返される PSGetModuleInfo オブジェクトにこのデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0481-131">If you're running [Find-Module][] or [Find-Script][], you can view this data in the returned PSGetModuleInfo object.</span></span> <span data-ttu-id="b0481-132">たとえば、`Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` を実行すると、ギャラリーの PSReadLine モジュールのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="b0481-132">For example, running `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` returns data on the PSReadLine module in the Gallery.</span></span>

## <a name="downloading-items-from-the-powershell-gallery"></a><span data-ttu-id="b0481-133">PowerShell ギャラリーでの項目のダウンロード</span><span class="sxs-lookup"><span data-stu-id="b0481-133">Downloading items from the PowerShell Gallery</span></span>

<span data-ttu-id="b0481-134">PowerShell ギャラリーから項目をダウンロードするとき、次のプロセスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b0481-134">We encourage the following process when downloading items from the PowerShell Gallery:</span></span>

### <a name="inspect"></a><span data-ttu-id="b0481-135">検査</span><span class="sxs-lookup"><span data-stu-id="b0481-135">Inspect</span></span>

<span data-ttu-id="b0481-136">検査のためにギャラリーから項目をダウンロードするには、項目の種類に応じて [Save-Module][] または [Save-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0481-136">To download an item from the Gallery for inspection, run either the [Save-Module][] or [Save-Script][] cmdlet, depending on the item type.</span></span> <span data-ttu-id="b0481-137">これにより、項目をインストールすることなくローカルに保存し、項目の内容を検査することができます。</span><span class="sxs-lookup"><span data-stu-id="b0481-137">This lets you save the item locally without installing it, and inspect the item contents.</span></span> <span data-ttu-id="b0481-138">保存した項目は必ず手動で削除してください。</span><span class="sxs-lookup"><span data-stu-id="b0481-138">Remember to delete the saved item manually.</span></span>

<span data-ttu-id="b0481-139">この項目の一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="b0481-139">Some of these items are authored by Microsoft, and others are authored by the PowerShell community.</span></span>
<span data-ttu-id="b0481-140">このギャラリーの項目の内容とコードは、インストールする前に確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b0481-140">Microsoft recommends that you review the contents and code of items on this gallery prior to installation.</span></span>

<span data-ttu-id="b0481-141">誠意をもって公開されていると思われない項目が見つかった場合は、その項目のページの **[不正使用を報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0481-141">If you discover an item that you feel is not published in good faith, click **Report Abuse** on that item's page.</span></span>

### <a name="install"></a><span data-ttu-id="b0481-142">[インストール]</span><span class="sxs-lookup"><span data-stu-id="b0481-142">Install</span></span>

<span data-ttu-id="b0481-143">使用のためにギャラリーから項目をインストールするには、項目の種類に応じて [Install-Module][] または [Install-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0481-143">To install an item from the Gallery for use, run either the [Install-Module][] or [Install-Script][] cmdlet, depending on the item type.</span></span>

<span data-ttu-id="b0481-144">[Install-Module][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Modules` にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b0481-144">[Install-Module][] installs the module to `$env:ProgramFiles\WindowsPowerShell\Modules` by default.</span></span>
<span data-ttu-id="b0481-145">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0481-145">This requires an administrator account.</span></span> <span data-ttu-id="b0481-146">`-Scope CurrentUser` パラメーターを追加する場合は、モジュールは `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b0481-146">If you add the `-Scope CurrentUser` parameter, the module is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` .</span></span>

<span data-ttu-id="b0481-147">[Install-Script][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Scripts` にスクリプトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b0481-147">[Install-Script][] installs the script to `$env:ProgramFiles\WindowsPowerShell\Scripts` by default.</span></span>
<span data-ttu-id="b0481-148">これには管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0481-148">This requires an administrator account.</span></span> <span data-ttu-id="b0481-149">`-Scope CurrentUser` パラメーターを追加する場合は、スクリプトは `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b0481-149">If you add the `-Scope CurrentUser` parameter, the script is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` .</span></span>

<span data-ttu-id="b0481-150">既定では、[Install-Module][] および [Install-Script][] は項目の最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b0481-150">By default, [Install-Module][] and [Install-Script][] installs the most current version of an item.</span></span>
<span data-ttu-id="b0481-151">前のバージョンのアイテムをインストールするには、 `-RequiredVersion` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b0481-151">To install an older version of the item, add the `-RequiredVersion` parameter.</span></span>

### <a name="deploy"></a><span data-ttu-id="b0481-152">展開</span><span class="sxs-lookup"><span data-stu-id="b0481-152">Deploy</span></span>

<span data-ttu-id="b0481-153">項目を PowerShell ギャラリーから Azure Automation にデプロイするには、項目の詳細ページで **[Azure Automation にデプロイする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0481-153">To deploy an item from the PowerShell Gallery to Azure Automation, click **Deploy to Azure Automation** on the item details page.</span></span> <span data-ttu-id="b0481-154">Azure 管理ポータルにリダイレクトされるため、そこでAzure アカウント資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="b0481-154">You will be redirected to the Azure Management Portal, where you sign in by using your Azure account credentials.</span></span> <span data-ttu-id="b0481-155">依存関係のある項目をデプロイすると、すべての依存関係が Azure Automation にデプロイされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b0481-155">Note that deploying items with dependencies will deploy all the dependencies to Azure Automation.</span></span> <span data-ttu-id="b0481-156">[Azure Automation にデプロイする] ボタンは、**AzureAutomationNotSupported** タグを項目のメタデータに追加すると無効にできます。</span><span class="sxs-lookup"><span data-stu-id="b0481-156">The 'Deploy to Azure Automation' button can be disabled by adding the **AzureAutomationNotSupported** tag to your item metadata.</span></span>

<span data-ttu-id="b0481-157">Azure Automation の詳細については、[Azure Automation](/azure/automation) のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b0481-157">To learn more about Azure Automation, see the [Azure Automation](/azure/automation) documentation.</span></span>

## <a name="updating-items-from-the-powershell-gallery"></a><span data-ttu-id="b0481-158">PowerShell ギャラリーからの項目の更新</span><span class="sxs-lookup"><span data-stu-id="b0481-158">Updating items from the PowerShell Gallery</span></span>

<span data-ttu-id="b0481-159">PowerShell ギャラリーからインストールされたアイテムを更新するには、[Update-Module][] または [Update-Script][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0481-159">To update items installed from the PowerShell Gallery, run either the [Update-Module][] or [Update-Script][] cmdlet.</span></span> <span data-ttu-id="b0481-160">パラメーターを追加せずに [Update-Module][] を実行すると、[Install-Module][] を実行してインストールされた各モジュールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="b0481-160">When run without any additional parameters, [Update-Module][] attempts to update each module installed by running [Install-Module][].</span></span> <span data-ttu-id="b0481-161">モジュールを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b0481-161">To selectively update modules, add the `-Name` parameter.</span></span>

<span data-ttu-id="b0481-162">同様に、パラメーターを追加せずに [Update-Script][] を実行すると、[Install-Script][] を実行してインストールされた各スクリプトが更新されます。</span><span class="sxs-lookup"><span data-stu-id="b0481-162">Similarly, when run without any additional parameters, [Update-Script][] also attempts to update each script installed by running [Install-Script][].</span></span> <span data-ttu-id="b0481-163">スクリプトを選択して更新するには、`-Name` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b0481-163">To selectively update scripts, add the `-Name` parameter.</span></span>

## <a name="list-items-that-you-have-installed-from-the-powershell-gallery"></a><span data-ttu-id="b0481-164">PowerShell ギャラリーからインストールした項目の一覧</span><span class="sxs-lookup"><span data-stu-id="b0481-164">List items that you have installed from the PowerShell Gallery</span></span>

<span data-ttu-id="b0481-165">PowerShell ギャラリーからどのモジュールをインストールしたかを調べるには、[Get-InstalledModule][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0481-165">To find out which modules you have installed from the PowerShell Gallery, run the [Get-InstalledModule][] cmdlet.</span></span> <span data-ttu-id="b0481-166">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるモジュールをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0481-166">This command lists all of the modules you have on your system that were installed directly from the PowerShell Gallery.</span></span>

<span data-ttu-id="b0481-167">同様に、PowerShell ギャラリーからどのスクリプトをインストールしたかを調べるには、[Get-InstalledScript][] コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0481-167">Similarly, to find out which scripts you have installed from the PowerShell Gallery, run the [Get-InstalledScript][] cmdlet.</span></span> <span data-ttu-id="b0481-168">このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるスクリプトをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0481-168">This command lists all of the scripts you have on your system that were installed directly from the PowerShell Gallery.</span></span>

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
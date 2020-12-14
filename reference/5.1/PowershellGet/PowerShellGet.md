---
Download Help Link: https://go.microsoft.com/fwlink/?LinkId=393271
Help Version: 5.2.0.0
keywords: powershell,コマンドレット
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 130582b1b9f18a8f6ada7c009c6d25a7dab75e46
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890714"
---
# <span data-ttu-id="025a3-103">PowerShellGet モジュール</span><span class="sxs-lookup"><span data-stu-id="025a3-103">PowerShellGet Module</span></span>

## <span data-ttu-id="025a3-104">説明</span><span class="sxs-lookup"><span data-stu-id="025a3-104">Description</span></span>

<span data-ttu-id="025a3-105">PowerShellGet は、モジュール、DSC リソース、ロール機能、スクリプトなどの PowerShell アーティファクトを検出、インストール、更新、公開するためのコマンドを含むモジュールです。</span><span class="sxs-lookup"><span data-stu-id="025a3-105">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="025a3-106">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="025a3-106">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="025a3-107">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="025a3-107">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="025a3-108">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="025a3-108">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="025a3-109">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="025a3-109">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="025a3-110">PowerShellGet コマンドレット</span><span class="sxs-lookup"><span data-stu-id="025a3-110">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="025a3-111">Find-Command</span><span class="sxs-lookup"><span data-stu-id="025a3-111">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="025a3-112">モジュール内の PowerShell コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="025a3-112">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="025a3-113">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="025a3-113">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="025a3-114">DSC リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="025a3-114">Finds a DSC resource.</span></span>

### [<span data-ttu-id="025a3-115">Find-Module</span><span class="sxs-lookup"><span data-stu-id="025a3-115">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="025a3-116">指定された条件に一致するリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="025a3-116">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="025a3-117">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="025a3-117">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="025a3-118">モジュール内のロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="025a3-118">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="025a3-119">Find-Script</span><span class="sxs-lookup"><span data-stu-id="025a3-119">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="025a3-120">スクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="025a3-120">Finds a script.</span></span>

### [<span data-ttu-id="025a3-121">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="025a3-121">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="025a3-122">PowerShellGet によってインストールされたコンピューター上のモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="025a3-122">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="025a3-123">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="025a3-123">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="025a3-124">インストールされているスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="025a3-124">Gets an installed script.</span></span>

### [<span data-ttu-id="025a3-125">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="025a3-125">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="025a3-126">PowerShell リポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="025a3-126">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="025a3-127">Install-Module</span><span class="sxs-lookup"><span data-stu-id="025a3-127">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="025a3-128">1つ以上のモジュールをリポジトリからダウンロードし、ローカルコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="025a3-128">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="025a3-129">Install-Script</span><span class="sxs-lookup"><span data-stu-id="025a3-129">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="025a3-130">スクリプトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="025a3-130">Installs a script.</span></span>

### [<span data-ttu-id="025a3-131">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="025a3-131">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="025a3-132">メタデータを持つスクリプト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="025a3-132">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="025a3-133">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="025a3-133">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="025a3-134">指定したモジュールをローカル コンピューターからオンライン ギャラリーに発行します。</span><span class="sxs-lookup"><span data-stu-id="025a3-134">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="025a3-135">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="025a3-135">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="025a3-136">スクリプトを発行します。</span><span class="sxs-lookup"><span data-stu-id="025a3-136">Publishes a script.</span></span>

### [<span data-ttu-id="025a3-137">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="025a3-137">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="025a3-138">PowerShell リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="025a3-138">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="025a3-139">Save-Module</span><span class="sxs-lookup"><span data-stu-id="025a3-139">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="025a3-140">モジュールとその依存関係をローカルコンピューターに保存しますが、モジュールはインストールしません。</span><span class="sxs-lookup"><span data-stu-id="025a3-140">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="025a3-141">Save-Script</span><span class="sxs-lookup"><span data-stu-id="025a3-141">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="025a3-142">スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="025a3-142">Saves a script.</span></span>

### [<span data-ttu-id="025a3-143">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="025a3-143">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="025a3-144">登録されているリポジトリの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="025a3-144">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="025a3-145">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="025a3-145">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="025a3-146">スクリプトのコメントブロックを検証します。</span><span class="sxs-lookup"><span data-stu-id="025a3-146">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="025a3-147">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="025a3-147">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="025a3-148">モジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="025a3-148">Uninstalls a module.</span></span>

### [<span data-ttu-id="025a3-149">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="025a3-149">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="025a3-150">スクリプトをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="025a3-150">Uninstalls a script.</span></span>

### [<span data-ttu-id="025a3-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="025a3-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="025a3-152">リポジトリの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="025a3-152">Unregisters a repository.</span></span>

### [<span data-ttu-id="025a3-153">Update-Module</span><span class="sxs-lookup"><span data-stu-id="025a3-153">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="025a3-154">指定したモジュールの最新バージョンをオンライン ギャラリーからダウンロードし、ローカル コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="025a3-154">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="025a3-155">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="025a3-155">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="025a3-156">モジュール マニフェスト ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="025a3-156">Updates a module manifest file.</span></span>

### [<span data-ttu-id="025a3-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="025a3-157">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="025a3-158">スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="025a3-158">Updates a script.</span></span>

### [<span data-ttu-id="025a3-159">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="025a3-159">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="025a3-160">スクリプトの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="025a3-160">Updates information for a script.</span></span>

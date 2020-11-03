---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell,コマンドレット
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 87d4b62b866e0b477668ab4f4a5ec426d9a0df76
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "93220379"
---
# <span data-ttu-id="d1d66-103">PowerShellGet モジュール</span><span class="sxs-lookup"><span data-stu-id="d1d66-103">PowerShellGet Module</span></span>

## <span data-ttu-id="d1d66-104">説明</span><span class="sxs-lookup"><span data-stu-id="d1d66-104">Description</span></span>

<span data-ttu-id="d1d66-105">PowerShellGet は、モジュール、DSC リソース、ロール機能、スクリプトなどの PowerShell アーティファクトを検出、インストール、更新、公開するためのコマンドを含むモジュールです。</span><span class="sxs-lookup"><span data-stu-id="d1d66-105">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

## <span data-ttu-id="d1d66-106">PowerShellGet コマンドレット</span><span class="sxs-lookup"><span data-stu-id="d1d66-106">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="d1d66-107">Find-Command</span><span class="sxs-lookup"><span data-stu-id="d1d66-107">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="d1d66-108">モジュール内の PowerShell コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-108">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="d1d66-109">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="d1d66-109">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="d1d66-110">Desired State Configuration (DSC) リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-110">Finds Desired State Configuration (DSC) resources.</span></span>

### [<span data-ttu-id="d1d66-111">Find-Module</span><span class="sxs-lookup"><span data-stu-id="d1d66-111">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="d1d66-112">指定された条件に一致するリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-112">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="d1d66-113">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="d1d66-113">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="d1d66-114">モジュール内のロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-114">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="d1d66-115">Find-Script</span><span class="sxs-lookup"><span data-stu-id="d1d66-115">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="d1d66-116">スクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-116">Finds a script.</span></span>

### [<span data-ttu-id="d1d66-117">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="d1d66-117">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="d1d66-118">PowerShellGet によってインストールされたコンピューター上のモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-118">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="d1d66-119">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="d1d66-119">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="d1d66-120">インストールされているスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-120">Gets an installed script.</span></span>

### [<span data-ttu-id="d1d66-121">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d1d66-121">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="d1d66-122">PowerShell リポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-122">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="d1d66-123">Install-Module</span><span class="sxs-lookup"><span data-stu-id="d1d66-123">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="d1d66-124">1つ以上のモジュールをリポジトリからダウンロードし、ローカルコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-124">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="d1d66-125">Install-Script</span><span class="sxs-lookup"><span data-stu-id="d1d66-125">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="d1d66-126">スクリプトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-126">Installs a script.</span></span>

### [<span data-ttu-id="d1d66-127">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="d1d66-127">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="d1d66-128">メタデータを持つスクリプト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-128">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="d1d66-129">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="d1d66-129">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="d1d66-130">指定したモジュールをローカル コンピューターからオンライン ギャラリーに発行します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-130">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="d1d66-131">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="d1d66-131">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="d1d66-132">スクリプトを発行します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-132">Publishes a script.</span></span>

### [<span data-ttu-id="d1d66-133">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d1d66-133">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="d1d66-134">PowerShell リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-134">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="d1d66-135">Save-Module</span><span class="sxs-lookup"><span data-stu-id="d1d66-135">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="d1d66-136">モジュールとその依存関係をローカルコンピューターに保存しますが、モジュールはインストールしません。</span><span class="sxs-lookup"><span data-stu-id="d1d66-136">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="d1d66-137">Save-Script</span><span class="sxs-lookup"><span data-stu-id="d1d66-137">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="d1d66-138">スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-138">Saves a script.</span></span>

### [<span data-ttu-id="d1d66-139">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d1d66-139">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="d1d66-140">登録されているリポジトリの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-140">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="d1d66-141">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="d1d66-141">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="d1d66-142">スクリプトのコメントブロックを検証します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-142">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="d1d66-143">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="d1d66-143">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="d1d66-144">モジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-144">Uninstalls a module.</span></span>

### [<span data-ttu-id="d1d66-145">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="d1d66-145">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="d1d66-146">スクリプトをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-146">Uninstalls a script.</span></span>

### [<span data-ttu-id="d1d66-147">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d1d66-147">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="d1d66-148">リポジトリの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-148">Unregisters a repository.</span></span>

### [<span data-ttu-id="d1d66-149">Update-Module</span><span class="sxs-lookup"><span data-stu-id="d1d66-149">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="d1d66-150">指定したモジュールの最新バージョンをオンライン ギャラリーからダウンロードし、ローカル コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1d66-150">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="d1d66-151">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="d1d66-151">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="d1d66-152">モジュール マニフェスト ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-152">Updates a module manifest file.</span></span>

### [<span data-ttu-id="d1d66-153">Update-Script</span><span class="sxs-lookup"><span data-stu-id="d1d66-153">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="d1d66-154">スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-154">Updates a script.</span></span>

### [<span data-ttu-id="d1d66-155">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="d1d66-155">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="d1d66-156">スクリプトの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="d1d66-156">Updates information for a script.</span></span>


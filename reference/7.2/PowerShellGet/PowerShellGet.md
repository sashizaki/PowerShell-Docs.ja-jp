---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 0d4e5e26184558055a17f99bd5321aaf3f3789f7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599539"
---
# <span data-ttu-id="b97e9-102">PowerShellGet モジュール</span><span class="sxs-lookup"><span data-stu-id="b97e9-102">PowerShellGet Module</span></span>

## <span data-ttu-id="b97e9-103">説明</span><span class="sxs-lookup"><span data-stu-id="b97e9-103">Description</span></span>

<span data-ttu-id="b97e9-104">PowerShellGet は、モジュール、DSC リソース、ロール機能、スクリプトなどの PowerShell アーティファクトを検出、インストール、更新、公開するためのコマンドを含むモジュールです。</span><span class="sxs-lookup"><span data-stu-id="b97e9-104">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b97e9-105">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="b97e9-105">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="b97e9-106">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-106">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="b97e9-107">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="b97e9-107">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="b97e9-108">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97e9-108">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="b97e9-109">PowerShellGet コマンドレット</span><span class="sxs-lookup"><span data-stu-id="b97e9-109">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="b97e9-110">Find-Command</span><span class="sxs-lookup"><span data-stu-id="b97e9-110">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="b97e9-111">モジュール内の PowerShell コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-111">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="b97e9-112">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="b97e9-112">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="b97e9-113">Desired State Configuration (DSC) リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-113">Finds Desired State Configuration (DSC) resources.</span></span>

### [<span data-ttu-id="b97e9-114">Find-Module</span><span class="sxs-lookup"><span data-stu-id="b97e9-114">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="b97e9-115">指定された条件に一致するリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-115">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="b97e9-116">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="b97e9-116">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="b97e9-117">モジュール内のロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-117">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="b97e9-118">Find-Script</span><span class="sxs-lookup"><span data-stu-id="b97e9-118">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="b97e9-119">スクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-119">Finds a script.</span></span>

### [<span data-ttu-id="b97e9-120">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="b97e9-120">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="b97e9-121">PowerShellGet によってインストールされたコンピューター上のモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-121">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="b97e9-122">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="b97e9-122">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="b97e9-123">インストールされているスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-123">Gets an installed script.</span></span>

### [<span data-ttu-id="b97e9-124">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b97e9-124">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="b97e9-125">PowerShell リポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-125">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="b97e9-126">Install-Module</span><span class="sxs-lookup"><span data-stu-id="b97e9-126">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="b97e9-127">1つ以上のモジュールをリポジトリからダウンロードし、ローカルコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="b97e9-127">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="b97e9-128">Install-Script</span><span class="sxs-lookup"><span data-stu-id="b97e9-128">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="b97e9-129">スクリプトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b97e9-129">Installs a script.</span></span>

### [<span data-ttu-id="b97e9-130">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="b97e9-130">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="b97e9-131">メタデータを持つスクリプト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-131">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="b97e9-132">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="b97e9-132">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="b97e9-133">指定したモジュールをローカル コンピューターからオンライン ギャラリーに発行します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-133">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="b97e9-134">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="b97e9-134">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="b97e9-135">スクリプトを発行します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-135">Publishes a script.</span></span>

### [<span data-ttu-id="b97e9-136">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b97e9-136">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="b97e9-137">PowerShell リポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-137">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="b97e9-138">Save-Module</span><span class="sxs-lookup"><span data-stu-id="b97e9-138">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="b97e9-139">モジュールとその依存関係をローカルコンピューターに保存しますが、モジュールはインストールしません。</span><span class="sxs-lookup"><span data-stu-id="b97e9-139">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="b97e9-140">Save-Script</span><span class="sxs-lookup"><span data-stu-id="b97e9-140">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="b97e9-141">スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-141">Saves a script.</span></span>

### [<span data-ttu-id="b97e9-142">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b97e9-142">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="b97e9-143">登録されているリポジトリの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-143">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="b97e9-144">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="b97e9-144">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="b97e9-145">スクリプトのコメントブロックを検証します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-145">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="b97e9-146">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="b97e9-146">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="b97e9-147">モジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="b97e9-147">Uninstalls a module.</span></span>

### [<span data-ttu-id="b97e9-148">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="b97e9-148">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="b97e9-149">スクリプトをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="b97e9-149">Uninstalls a script.</span></span>

### [<span data-ttu-id="b97e9-150">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b97e9-150">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="b97e9-151">リポジトリの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-151">Unregisters a repository.</span></span>

### [<span data-ttu-id="b97e9-152">Update-Module</span><span class="sxs-lookup"><span data-stu-id="b97e9-152">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="b97e9-153">指定したモジュールの最新バージョンをオンライン ギャラリーからダウンロードし、ローカル コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="b97e9-153">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="b97e9-154">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="b97e9-154">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="b97e9-155">モジュール マニフェスト ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-155">Updates a module manifest file.</span></span>

### [<span data-ttu-id="b97e9-156">Update-Script</span><span class="sxs-lookup"><span data-stu-id="b97e9-156">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="b97e9-157">スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-157">Updates a script.</span></span>

### [<span data-ttu-id="b97e9-158">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="b97e9-158">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="b97e9-159">スクリプトの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="b97e9-159">Updates information for a script.</span></span>

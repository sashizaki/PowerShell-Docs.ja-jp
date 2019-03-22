---
ms.date: 09/11/2018
contributor: JKeithB
keywords: ギャラリー, PowerShell, PSGallery
title: パッケージの手動ダウンロード
ms.openlocfilehash: af628f99befe50c16c2c0c60f1a352647af34ff4
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "58054878"
---
# <a name="manual-package-download"></a><span data-ttu-id="8a219-103">パッケージの手動ダウンロード</span><span class="sxs-lookup"><span data-stu-id="8a219-103">Manual Package Download</span></span>

<span data-ttu-id="8a219-104">PowerShell ギャラリーでは、PowerShellGet コマンドレットを使用せずに、Web サイトから直接パッケージのダウンロードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8a219-104">The PowerShell Gallery supports downloading a package from the website directly, without using the PowerShellGet cmdlets.</span></span> <span data-ttu-id="8a219-105">任意のパッケージを NuGet パッケージ (.nupkg) ファイルとしてダウンロードできます。その後、内部リポジトリにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="8a219-105">You can download any package as a NuGet package (.nupkg) file, which you can then copy to an internal repository.</span></span>

> [!NOTE]
> <span data-ttu-id="8a219-106">パッケージの手動ダウンロードは、Install-module コマンドレットの代替手段を意図したものでは**ありません**。</span><span class="sxs-lookup"><span data-stu-id="8a219-106">Manual package download is **not** intended as a replacement for the Install-Module cmdlet.</span></span>
> <span data-ttu-id="8a219-107">パッケージのダウンロードでは、モジュールまたはスクリプトはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="8a219-107">Downloading the package does not install the module or script.</span></span> <span data-ttu-id="8a219-108">NuGet パッケージのダウンロードには依存関係は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8a219-108">Dependencies are not included in the NuGet package downloaded.</span></span> <span data-ttu-id="8a219-109">次の手順は、参照目的にのみ提供されています。</span><span class="sxs-lookup"><span data-stu-id="8a219-109">The following instructions are provided for reference purposes only.</span></span>

## <a name="using-manual-download-to-acquire-a-package"></a><span data-ttu-id="8a219-110">手動ダウンロードを使用してパッケージを取得</span><span class="sxs-lookup"><span data-stu-id="8a219-110">Using manual download to acquire a package</span></span>

<span data-ttu-id="8a219-111">次に示すように、各ページには [手動ダウンロード] のリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="8a219-111">Each page has a link for Manual Download, as shown here:</span></span>

![手動ダウンロード](../../Images/packagedisplaypagewithpseditions.png)

<span data-ttu-id="8a219-113">手動でダウンロードするには、**[Download the raw nupkg file]\(raw nupk ファイルのダウンロード\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a219-113">To download manually, click on **Download the raw nupkg file**.</span></span> <span data-ttu-id="8a219-114">パッケージのコピーがブラウザーのダウンロード フォルダーに `<name>.<version>.nupkg` という名前でコピーされます。</span><span class="sxs-lookup"><span data-stu-id="8a219-114">A copy of the package copied to the download folder for your browser with the name `<name>.<version>.nupkg`.</span></span>

<span data-ttu-id="8a219-115">NuGet パッケージは、パッケージの内容に関する情報を含む追加のファイルが含まれた ZIP アーカイブです。</span><span class="sxs-lookup"><span data-stu-id="8a219-115">A NuGet package is a ZIP archive with extra files containing information about the contents of the package.</span></span> <span data-ttu-id="8a219-116">Internet Explorer などの一部のブラウザーでは、ファイル拡張子が `.nupkg` から `.zip` に自動的に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="8a219-116">Some browsers, like Internet Explorer, automatically replace the `.nupkg` file extension with `.zip`.</span></span> <span data-ttu-id="8a219-117">パッケージを展開するには、必要に応じて `.nupkg` ファイルの名前を `.zip` に変更してから、ローカル フォルダーに内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="8a219-117">To expand the package, rename the `.nupkg` file to `.zip`, if needed, then extract the contents to a local folder.</span></span>

<span data-ttu-id="8a219-118">NuGet パッケージ ファイルには、元のパッケージ化されたコードの一部ではない次の NuGet に固有の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a219-118">A NuGet package file includes the following NuGet-specific elements that aren't part of the original packaged code:</span></span>

- <span data-ttu-id="8a219-119">`_rels` という名前のフォルダーには、依存関係の一覧表示する `.rels` ファイルが含まれています</span><span class="sxs-lookup"><span data-stu-id="8a219-119">A folder named `_rels` - contains a `.rels` file that lists the dependencies</span></span>
- <span data-ttu-id="8a219-120">`package` という名前のフォルダーには、NuGet に固有のデータが含まれています</span><span class="sxs-lookup"><span data-stu-id="8a219-120">A folder named `package` - contains the NuGet-specific data</span></span>
- <span data-ttu-id="8a219-121">`[Content_Types].xml` という名前のファイルには、PowerShellGet などの拡張機能が NuGet でどのように機能するかが説明されています</span><span class="sxs-lookup"><span data-stu-id="8a219-121">A file named `[Content_Types].xml` - describes how extensions like PowerShellGet work with NuGet</span></span>
- <span data-ttu-id="8a219-122">`<name>.nuspec` という名前のファイルには、メタデータの大部分が含まれています</span><span class="sxs-lookup"><span data-stu-id="8a219-122">A file named `<name>.nuspec` - contains the bulk of the metadata</span></span>

## <a name="installing-powershell-modules-from-a-nuget-package"></a><span data-ttu-id="8a219-123">NuGet パッケージから PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="8a219-123">Installing PowerShell Modules from a NuGet package</span></span>

> [!NOTE]
> <span data-ttu-id="8a219-124">これらの手順を実行しても、`Install-Module` を実行した場合と同じ結果には**なりません**。</span><span class="sxs-lookup"><span data-stu-id="8a219-124">These instructions **DO NOT** give the same result as running `Install-Module`.</span></span> <span data-ttu-id="8a219-125">これらの手順は、最小要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="8a219-125">These instructions fulfill the minimum requirements.</span></span> <span data-ttu-id="8a219-126">これらは、`Install-Module` の代替手段を意図したものではありません。</span><span class="sxs-lookup"><span data-stu-id="8a219-126">They are not intended to be a replacement for `Install-Module`.</span></span> <span data-ttu-id="8a219-127">`Install-Module` によって実行されるいくつかの手順は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8a219-127">Some steps performed by `Install-Module` are not included.</span></span>

<span data-ttu-id="8a219-128">最も簡単な方法は、フォルダーから NuGet に固有の要素を削除することです。</span><span class="sxs-lookup"><span data-stu-id="8a219-128">The easiest approach is to remove the NuGet-specific elements from the folder.</span></span> <span data-ttu-id="8a219-129">これにより、パッケージの作成者によって作成された PowerShell コードが残ります。</span><span class="sxs-lookup"><span data-stu-id="8a219-129">This leaves the PowerShell code created by the package author.</span></span> <span data-ttu-id="8a219-130">手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a219-130">The steps are:</span></span>

1. <span data-ttu-id="8a219-131">NuGet パッケージの内容をローカル フォルダーに抽出します。</span><span class="sxs-lookup"><span data-stu-id="8a219-131">Extract the contents of the NuGet package to a local folder.</span></span>
2. <span data-ttu-id="8a219-132">フォルダーから NuGet に固有の要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="8a219-132">Delete the NuGet-specific elements from the folder.</span></span>
3. <span data-ttu-id="8a219-133">フォルダーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="8a219-133">Rename the folder.</span></span> <span data-ttu-id="8a219-134">既定のフォルダー名は通常、`<name>.<version>` です。</span><span class="sxs-lookup"><span data-stu-id="8a219-134">The default folder name is usually `<name>.<version>`.</span></span> <span data-ttu-id="8a219-135">モジュールがプレリリース バージョンとしてタグ付けされされている場合は、バージョンに "-prerelease" を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8a219-135">The version can include "-prerelease" if the module is tagged as a prerelease version.</span></span> <span data-ttu-id="8a219-136">フォルダーの名前をモジュールの名前だけに変更します。</span><span class="sxs-lookup"><span data-stu-id="8a219-136">Rename the folder to just the module name.</span></span> <span data-ttu-id="8a219-137">たとえば、"azurerm.storage.5.0.4-preview" は "azurerm.storage" になります。</span><span class="sxs-lookup"><span data-stu-id="8a219-137">For example, "azurerm.storage.5.0.4-preview" becomes "azurerm.storage".</span></span>
4. <span data-ttu-id="8a219-138">フォルダーを `$env:PSModulePath value` 内のフォルダーのいずれかにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8a219-138">Copy the folder to one of the folders in the `$env:PSModulePath value`.</span></span> <span data-ttu-id="8a219-139">`$env:PSModulePath` はセミコロンで区切られたパスのセットです。ここで、PowerShell によってモジュールが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8a219-139">`$env:PSModulePath` is a semicolon delimited set of paths in which PowerShell should look for modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a219-140">手動ダウンロードには、モジュールで必要な依存関係は何も含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8a219-140">The manual download does not include any dependencies required by the module.</span></span> <span data-ttu-id="8a219-141">パッケージに依存関係がある場合は、このモジュールが正常に動作するために、それらをシステムにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a219-141">If the package has dependencies, they must be installed on the system for this module to work correctly.</span></span> <span data-ttu-id="8a219-142">PowerShell ギャラリーには、パッケージで必要なすべての依存関係が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a219-142">The PowerShell Gallery shows all dependencies required by the package.</span></span>

## <a name="installing-powershell-scripts-from-a-nuget-package"></a><span data-ttu-id="8a219-143">NuGet パッケージから PowerShell スクリプトをインストールする</span><span class="sxs-lookup"><span data-stu-id="8a219-143">Installing PowerShell Scripts from a NuGet package</span></span>

> [!NOTE]
> <span data-ttu-id="8a219-144">これらの手順を実行しても、`Install-Script` を実行した場合と同じ結果には**なりません**。</span><span class="sxs-lookup"><span data-stu-id="8a219-144">These instructions **DO NOT** give the same result as running `Install-Script`.</span></span> <span data-ttu-id="8a219-145">これらの手順は、最小要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="8a219-145">These instructions fulfill the minimum requirements.</span></span> <span data-ttu-id="8a219-146">これらは、`Install-Script` の代替手段を意図したものではありません。</span><span class="sxs-lookup"><span data-stu-id="8a219-146">They are not intended to be a replacement for `Install-Script`.</span></span>

<span data-ttu-id="8a219-147">最も簡単な方法は、NuGet パッケージを抽出してから、スクリプトを直接使用することです。</span><span class="sxs-lookup"><span data-stu-id="8a219-147">The easiest approach is to extract the NuGet package, then use the script directly.</span></span> <span data-ttu-id="8a219-148">手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a219-148">The steps are:</span></span>

1. <span data-ttu-id="8a219-149">NuGet パッケージの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="8a219-149">Extract the contents of the NuGet package.</span></span>
2. <span data-ttu-id="8a219-150">フォルダー内の `.PS1` ファイルは、この場所から直接使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8a219-150">The `.PS1` file in the folder can be used directly from this location.</span></span>
3. <span data-ttu-id="8a219-151">フォルダー内の NuGet に固有の要素を削除できます。</span><span class="sxs-lookup"><span data-stu-id="8a219-151">You may delete the NuGet-specific elements in the folder.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a219-152">手動ダウンロードには、モジュールで必要な依存関係は何も含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8a219-152">The manual download does not include any dependencies required by the module.</span></span> <span data-ttu-id="8a219-153">パッケージに依存関係がある場合は、このモジュールが正常に動作するために、それらをシステムにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a219-153">If the package has dependencies, they must be installed on the system for this module to work correctly.</span></span> <span data-ttu-id="8a219-154">PowerShell ギャラリーには、パッケージで必要なすべての依存関係が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a219-154">The PowerShell Gallery shows all dependencies required by the package.</span></span>

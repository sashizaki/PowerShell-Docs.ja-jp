---
ms.openlocfilehash: 61a70db9ae7a38d6731f1cefb011072c12d1e39a
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "95514917"
---
# <a name="microsoft-open-source-code-of-conduct"></a><span data-ttu-id="30e24-101">Microsoft オープン ソース倫理規定</span><span class="sxs-lookup"><span data-stu-id="30e24-101">Microsoft Open Source Code of Conduct</span></span>

> <span data-ttu-id="30e24-102">更新:2020/11/02</span><span class="sxs-lookup"><span data-stu-id="30e24-102">Updated: 11/02/2020</span></span>

<span data-ttu-id="30e24-103">このプロジェクトは、「[Microsoft のオープン ソースの倫理規定](https://opensource.microsoft.com/codeofconduct/)」を採用しています。</span><span class="sxs-lookup"><span data-stu-id="30e24-103">This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span> <span data-ttu-id="30e24-104">詳細については[論理規定についてのよくある質問](https://opensource.microsoft.com/codeofconduct/faq/)をご覧ください。また、追加の質問やコメントがある場合は[opencode@microsoft.com](mailto:opencode@microsoft.com)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="30e24-104">For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.</span></span>

[live-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[staging-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a><span data-ttu-id="30e24-107">ビルドの状態</span><span class="sxs-lookup"><span data-stu-id="30e24-107">Build Status</span></span>

|          <span data-ttu-id="30e24-108">ライブ ブランチ</span><span class="sxs-lookup"><span data-stu-id="30e24-108">Live Branch</span></span>          |           <span data-ttu-id="30e24-109">ステージング ブランチ</span><span class="sxs-lookup"><span data-stu-id="30e24-109">Staging Branch</span></span>            |
| :---------------------------- | :---------------------------------- |
| <span data-ttu-id="30e24-110">[![live-badge][]][live-badge]</span><span class="sxs-lookup"><span data-stu-id="30e24-110">[![live-badge][]][live-badge]</span></span> | <span data-ttu-id="30e24-111">[![staging-badge][]][staging-badge]</span><span class="sxs-lookup"><span data-stu-id="30e24-111">[![staging-badge][]][staging-badge]</span></span> |

## <a name="powershell-documentation"></a><span data-ttu-id="30e24-112">PowerShell ドキュメント</span><span class="sxs-lookup"><span data-stu-id="30e24-112">PowerShell Documentation</span></span>

<span data-ttu-id="30e24-113">公式の PowerShell ドキュメントが格納される PowerShell-Docs リポジトリへようこそ。</span><span class="sxs-lookup"><span data-stu-id="30e24-113">Welcome to the PowerShell-Docs repository, the home of the official PowerShell documentation.</span></span>

## <a name="repository-structure"></a><span data-ttu-id="30e24-114">リポジトリの構造</span><span class="sxs-lookup"><span data-stu-id="30e24-114">Repository Structure</span></span>

<span data-ttu-id="30e24-115">次の一覧は、このリポジトリ内の主なフォルダーについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="30e24-115">The following list describes the main folders in this repository.</span></span>

- <span data-ttu-id="30e24-116">`.github` - このリポジトリで GitHub によって使用される構成設定が含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-116">`.github` - contains configuration settings used by GitHub for this repository</span></span>
- <span data-ttu-id="30e24-117">`.vscode` - Visual Studio Code (VS Code) の構成設定と推奨される拡張機能が含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-117">`.vscode` - contains configuration settings and recommended extensions for Visual Studio Code (VS Code)</span></span>
- <span data-ttu-id="30e24-118">`assets` - ドキュメントにリンクされているダウンロード可能なファイルが含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-118">`assets` - contains downloadable files linked in the documentation</span></span>
- <span data-ttu-id="30e24-119">`reference` - [docs.microsoft.com]([https://docs.microsoft.com/powershell/scripting/) に発行されたドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="30e24-119">`reference` - contains the documentation published to [docs.microsoft.com]([https://docs.microsoft.com/powershell/scripting/).</span></span> <span data-ttu-id="30e24-120">これには、リファレンスと概念のコンテンツの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="30e24-120">This includes both reference and conceptual content.</span></span>
  - <span data-ttu-id="30e24-121">`5.1` - コマンドレット リファレンスと PowerShell 5.1 に関するトピックが含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-121">`5.1` - contains the cmdlet reference and about topics for PowerShell 5.1</span></span>
  - <span data-ttu-id="30e24-122">`7.0` - コマンドレット リファレンスと PowerShell 7.0 に関するトピックが含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-122">`7.0` - contains the cmdlet reference and about topics for PowerShell 7.0</span></span>
  - <span data-ttu-id="30e24-123">`7.1` - コマンドレット リファレンスと PowerShell 7.1 に関するトピックが含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-123">`7.1` - contains the cmdlet reference and about topics for PowerShell 7.1</span></span>
  - <span data-ttu-id="30e24-124">`7.2` - コマンドレット リファレンスと PowerShell 7.2 (プレビュー) に関するトピックが含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-124">`7.2` - contains the cmdlet reference and about topics for PowerShell 7.2 (preview)</span></span>
  - <span data-ttu-id="30e24-125">`bread` - 階層リンク ナビゲーションに使用される TOC が含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-125">`bread` - contains the TOC used for breadcrumb navigation</span></span>
  - <span data-ttu-id="30e24-126">`docs-conceptual` - ドキュメント サイトに公開されている概念説明の記事が含まれています。</span><span class="sxs-lookup"><span data-stu-id="30e24-126">`docs-conceptual` - contains the conceptual articles that are published to the Docs site.</span></span> <span data-ttu-id="30e24-127">一般に、フォルダー構造は目次 (TOC) を反映しています。</span><span class="sxs-lookup"><span data-stu-id="30e24-127">In general, the folder structure mirrors the Table of Contents (TOC).</span></span>
  - <span data-ttu-id="30e24-128">`mapping` - ビルド システムで使用されるバージョン マッピング構成が含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-128">`mapping` - contains the version mapping configuration used by the build system</span></span>
  - <span data-ttu-id="30e24-129">`media` - ドキュメントで使用される画像ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="30e24-129">`media` - contains image files used in documentation.</span></span> <span data-ttu-id="30e24-130">`docs-conceptual` のコンテンツ全体にメディア フォルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="30e24-130">There are media folders throughout the `docs-conceptual` content.</span></span> <span data-ttu-id="30e24-131">ドキュメントの画像の使用方法については、共同作成者ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e24-131">See the Contributor Guide for information on using images in documentation.</span></span>
  - <span data-ttu-id="30e24-132">`module` - モジュール ブラウザーのページの Markdown ソースが含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-132">`module` - contains the markdown source for the Module Browser page</span></span>
- <span data-ttu-id="30e24-133">`tests` - ビルド システムで使用される Pester テストが含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-133">`tests` - contains the Pester tests used by the build system</span></span>
- <span data-ttu-id="30e24-134">`tools` - ビルド システムで使用されるその他のツールが含まれています</span><span class="sxs-lookup"><span data-stu-id="30e24-134">`tools` - contains other tools used by the build system</span></span>

> <span data-ttu-id="30e24-135">注: 参照コンテンツ (番号付きフォルダー内) は、ドキュメント サイトの Web ページと、PowerShell で使用される更新可能なヘルプを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="30e24-135">NOTE: The reference content (in the numbered folders) is used to create the webpages on the Docs site as well as the updateable help used by PowerShell.</span></span>
> <span data-ttu-id="30e24-136">`docs-conceptual` フォルダー内の記事は、ドキュメント Web サイトにのみ公開されています。</span><span class="sxs-lookup"><span data-stu-id="30e24-136">The articles in the `docs-conceptual` folder are only published to the Docs website.</span></span>

## <a name="contributing"></a><span data-ttu-id="30e24-137">寄与</span><span class="sxs-lookup"><span data-stu-id="30e24-137">Contributing</span></span>

<span data-ttu-id="30e24-138">このリポジトリへの公開投稿は、_ステージング_ ブランチへの [pull request](https://help.github.com/articles/using-pull-requests/) から行ってください。</span><span class="sxs-lookup"><span data-stu-id="30e24-138">We welcome public contributions into this repository via [pull requests](https://help.github.com/articles/using-pull-requests/) into the _staging_ branch.</span></span>
<span data-ttu-id="30e24-139">pull request が受け入れられるには、[貢献者使用許諾契約書](https://cla.microsoft.com/)に署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e24-139">Please note that before we can accept your pull request you must sign our [Contribution License Agreement](https://cla.microsoft.com/).</span></span> <span data-ttu-id="30e24-140">これは 1 回限りの要件です。</span><span class="sxs-lookup"><span data-stu-id="30e24-140">This is a one-time requirement.</span></span>

<span data-ttu-id="30e24-141">投稿の詳細については、[共同作成者ガイド](https://aka.ms/PSDocsContributor)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e24-141">For more information on contributing, read our [contributor's guide](https://aka.ms/PSDocsContributor).</span></span> <span data-ttu-id="30e24-142">共同作成者ガイドには、ドキュメント、お勧めのツール、スタイルや書式設定に関する要求を投稿する方法についての詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="30e24-142">The contributor's guide contains detail information about how to contribute documentation, suggested tools, and style and formatting requirements.</span></span> <span data-ttu-id="30e24-143">異なるバージョン間で一貫性のあるドキュメントを保つため、問題と Pull Request のテンプレートを使用してください。</span><span class="sxs-lookup"><span data-stu-id="30e24-143">Please use the Issue and Pull Request templates to help keep documentation consistent across versions.</span></span>

## <a name="licenses"></a><span data-ttu-id="30e24-144">ライセンス</span><span class="sxs-lookup"><span data-stu-id="30e24-144">Licenses</span></span>

<span data-ttu-id="30e24-145">このプロジェクトには、2 つのライセンス ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="30e24-145">There are two license files for this project.</span></span> <span data-ttu-id="30e24-146">MIT ライセンスは、このリポジトリに含まれるコードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="30e24-146">The MIT License applies to the code contained in this repo.</span></span> <span data-ttu-id="30e24-147">Creative Commons ライセンスは、ドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="30e24-147">The Creative Commons license applies to the documentation.</span></span>

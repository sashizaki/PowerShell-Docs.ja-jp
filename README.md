---
ms.openlocfilehash: 0d91230aa063e58106b35a4ada1d577f316f8f27
ms.sourcegitcommit: c752ae8d0fa47eaaf3c5eae2a5a770f06c63921c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840993"
---
# <a name="microsoft-open-source-code-of-conduct"></a><span data-ttu-id="5cd7b-101">Microsoft オープン ソース倫理規定</span><span class="sxs-lookup"><span data-stu-id="5cd7b-101">Microsoft Open Source Code of Conduct</span></span>

<span data-ttu-id="5cd7b-102">このプロジェクトは、「[Microsoft のオープン ソースの倫理規定](https://opensource.microsoft.com/codeofconduct/)」を採用しています。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-102">This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span> <span data-ttu-id="5cd7b-103">詳細については[論理規定についてのよくある質問](https://opensource.microsoft.com/codeofconduct/faq/)をご覧ください。また、追加の質問やコメントがある場合は[opencode@microsoft.com](mailto:opencode@microsoft.com)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-103">For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.</span></span>

[live-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[staging-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a><span data-ttu-id="5cd7b-106">ビルドの状態</span><span class="sxs-lookup"><span data-stu-id="5cd7b-106">Build Status</span></span>

|          <span data-ttu-id="5cd7b-107">ライブ ブランチ</span><span class="sxs-lookup"><span data-stu-id="5cd7b-107">Live Branch</span></span>          |           <span data-ttu-id="5cd7b-108">ステージング ブランチ</span><span class="sxs-lookup"><span data-stu-id="5cd7b-108">Staging Branch</span></span>            |
| :---------------------------- | :---------------------------------- |
| <span data-ttu-id="5cd7b-109">[![live-badge][]][live-badge]</span><span class="sxs-lookup"><span data-stu-id="5cd7b-109">[![live-badge][]][live-badge]</span></span> | <span data-ttu-id="5cd7b-110">[![staging-badge][]][staging-badge]</span><span class="sxs-lookup"><span data-stu-id="5cd7b-110">[![staging-badge][]][staging-badge]</span></span> |

## <a name="powershell-documentation"></a><span data-ttu-id="5cd7b-111">PowerShell ドキュメント</span><span class="sxs-lookup"><span data-stu-id="5cd7b-111">PowerShell Documentation</span></span>

<span data-ttu-id="5cd7b-112">PowerShell-Docs リポジトリへようこそ。PowerShell-Docs は、公式の PowerShell ドキュメントが格納されている場所です。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-112">Welcome to the PowerShell-Docs repository, housing the official PowerShell documentation.</span></span>

## <a name="repository-structure"></a><span data-ttu-id="5cd7b-113">リポジトリの構造</span><span class="sxs-lookup"><span data-stu-id="5cd7b-113">Repository Structure</span></span>

<span data-ttu-id="5cd7b-114">このリポジトリ内の次の各最上位フォルダーには、[Microsoft Docs](https://docs.microsoft.com/powershell) に公開されるドキュメント セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-114">Each of the following top-level folders in this repo contain a DocSet that is published to [Microsoft Docs](https://docs.microsoft.com/powershell).</span></span>

- <span data-ttu-id="5cd7b-115">[/reference/](https://docs.microsoft.com/powershell/scripting/) は、バージョン 5.1、6.0、7.0 にわたる PowerShell の概念説明のトピックおよびモジュール リファレンス用です。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-115">[/reference/](https://docs.microsoft.com/powershell/scripting/) is for PowerShell conceptual topics and module reference across versions 5.1, 6.0, and 7.0.</span></span> <span data-ttu-id="5cd7b-116">また、このコンテンツは、`Get-Help` コマンドレットによって取得されるヘルプ コンテンツのソースでもあります。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-116">This content is also the source of help content retrieved by the `Get-Help` cmdlet.</span></span>
  - <span data-ttu-id="5cd7b-117">[docs-conceptual/](https://docs.microsoft.com/powershell) - このフォルダーには、概念説明のドキュメントと次のドキュメント セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-117">[docs-conceptual/](https://docs.microsoft.com/powershell) - this folder contains the conceptual documentation and the following docsets:</span></span>
    - <span data-ttu-id="5cd7b-118">[developer/](https://docs.microsoft.com/powershell/scripting/developer/) は PowerShell SDK のドキュメントです (MSDN から移行)</span><span class="sxs-lookup"><span data-stu-id="5cd7b-118">[developer/](https://docs.microsoft.com/powershell/scripting/developer/) is the PowerShell SDK documentation (migrated from MSDN)</span></span>
    - <span data-ttu-id="5cd7b-119">[dsc/](https://docs.microsoft.com/powershell/scripting/dsc/) は Desired State Configuration 機能用です</span><span class="sxs-lookup"><span data-stu-id="5cd7b-119">[dsc/](https://docs.microsoft.com/powershell/scripting/dsc/) is for the Desired State Configuration feature</span></span>
    - <span data-ttu-id="5cd7b-120">[gallery/](https://docs.microsoft.com/powershell/scripting/gallery) は [PowerShell ギャラリー](https://www.powershellgallery.com/)用です</span><span class="sxs-lookup"><span data-stu-id="5cd7b-120">[gallery/](https://docs.microsoft.com/powershell/scripting/gallery) is for the [PowerShell Gallery](https://www.powershellgallery.com/)</span></span>
    - <span data-ttu-id="5cd7b-121">[jea/](https://docs.microsoft.com/powershell/scripting/learn/remoting/jea/overview) は Just Enough Administration 機能用です</span><span class="sxs-lookup"><span data-stu-id="5cd7b-121">[jea/](https://docs.microsoft.com/powershell/scripting/learn/remoting/jea/overview) is for the Just Enough Administration feature</span></span>
    - <span data-ttu-id="5cd7b-122">[wmf](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview) には Windows Management Framework のリリース ノートが含まれています。これは、Windows の以前のバージョンに対して PowerShell の新しいバージョンを配布するために使用するパッケージです。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-122">[wmf/](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview) contains release notes for the Windows Management Framework, the package used to distribute new versions of PowerShell to previous versions of Windows.</span></span>

## <a name="contributing"></a><span data-ttu-id="5cd7b-123">寄与</span><span class="sxs-lookup"><span data-stu-id="5cd7b-123">Contributing</span></span>

<span data-ttu-id="5cd7b-124">[pull request](https://help.github.com/articles/using-pull-requests/) を使用したこのリポジトリへの投稿は、_ステージング_ ブランチに積極的に組み込んでいます。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-124">We actively merge contributions into this repository via [pull requests](https://help.github.com/articles/using-pull-requests/) into the _staging_ branch.</span></span>
<span data-ttu-id="5cd7b-125">pull request を送信する前に、[投稿の使用許諾契約](https://cla.microsoft.com/)に署名して、コミュニティがあなたの投稿を自由に使用できるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-125">Please note that before you submit a pull request you must sign a [Contribution License Agreement](https://cla.microsoft.com/) to ensure that the community is free to use your submissions.</span></span>

<span data-ttu-id="5cd7b-126">投稿の詳細については、[共同作成者ガイド](https://docs.microsoft.com/powershell/scripting/community/contributing/overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-126">For more information on contributing, read our [contributor's guide](https://docs.microsoft.com/powershell/scripting/community/contributing/overview).</span></span>
<span data-ttu-id="5cd7b-127">共同作成者ガイドには、ドキュメント、お勧めのツール、スタイルや書式設定に関する要求を投稿する方法についての詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-127">The contributor's guide contains detail information about how to contribute documentation, suggested tools, and style and formatting requirements.</span></span> <span data-ttu-id="5cd7b-128">異なるバージョン間で一貫性のあるドキュメントを保つため、問題と Pull Request のテンプレートを使用してください。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-128">Please use the Issue and Pull Request templates to help keep documentation consistent across versions.</span></span>

## <a name="licenses"></a><span data-ttu-id="5cd7b-129">ライセンス</span><span class="sxs-lookup"><span data-stu-id="5cd7b-129">Licenses</span></span>

<span data-ttu-id="5cd7b-130">このプロジェクトには、2 つのライセンス ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-130">There are two license files for this project.</span></span> <span data-ttu-id="5cd7b-131">MIT ライセンスは、このリポジトリに含まれるコードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-131">The MIT License applies to the code contained in this repo.</span></span> <span data-ttu-id="5cd7b-132">Creative Commons ライセンスは、ドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5cd7b-132">The Creative Commons license applies to the documentation.</span></span>

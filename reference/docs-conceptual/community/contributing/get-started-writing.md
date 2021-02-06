---
title: PowerShell ドキュメントへの投稿を開始する
description: この記事では、PowerShell ドキュメントの共同作成者として作業を開始する方法の概要を説明します。
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: ddcbf79de1ab05b901ce1abd67f65b2524ed164d
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "99602387"
---
# <a name="get-started-contributing-to-powershell-documentation"></a><span data-ttu-id="6b34b-103">PowerShell ドキュメントへの投稿を開始する</span><span class="sxs-lookup"><span data-stu-id="6b34b-103">Get started contributing to PowerShell documentation</span></span>

<span data-ttu-id="6b34b-104">この記事では、PowerShell ドキュメントの共同作成者として作業を開始する方法の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="6b34b-104">This article is an overview of how to get started as a contributor to the PowerShell documentation.</span></span>

## <a name="powershell-docs-structure"></a><span data-ttu-id="6b34b-105">PowerShell-Docs の構造</span><span class="sxs-lookup"><span data-stu-id="6b34b-105">PowerShell-Docs structure</span></span>

<span data-ttu-id="6b34b-106">[PowerShell Docs リポジトリ][psdocs]は、リファレンスと概念という2つのコンテンツグループに分かれています。</span><span class="sxs-lookup"><span data-stu-id="6b34b-106">The [PowerShell-Docs repository][psdocs] is divided into two groups of content: reference and conceptual.</span></span>

### <a name="reference-content"></a><span data-ttu-id="6b34b-107">リファレンス コンテンツ</span><span class="sxs-lookup"><span data-stu-id="6b34b-107">Reference content</span></span>

<span data-ttu-id="6b34b-108">参照コンテンツは、PowerShell に付属するコマンドレットの PowerShell コマンドレットリファレンスです。</span><span class="sxs-lookup"><span data-stu-id="6b34b-108">The reference content is the PowerShell cmdlet reference for the cmdlets that ship in PowerShell.</span></span>
<span data-ttu-id="6b34b-109">[参照][ref]は、バージョンフォルダー (5.1、7.0、7.1、および 7.2) で収集されます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-109">The [reference][ref] is collected in versions folders (5.1, 7.0, 7.1, and 7.2).</span></span> <span data-ttu-id="6b34b-110">このコンテンツには、PowerShell に付属するモジュールに対してのみコマンドレットリファレンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b34b-110">This content contains cmdlet reference only for the modules that ship with PowerShell.</span></span> <span data-ttu-id="6b34b-111">このコンテンツは、コマンドレットによって表示されるヘルプ情報を作成するためにも使用され `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-111">This content is also used to create the help information displayed by the `Get-Help` cmdlet.</span></span>

### <a name="conceptual-content"></a><span data-ttu-id="6b34b-112">概念的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="6b34b-112">Conceptual content</span></span>

<span data-ttu-id="6b34b-113">概念説明のドキュメントには、次のコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b34b-113">The conceptual documentation includes the following content:</span></span>

- <span data-ttu-id="6b34b-114">リリース ノート</span><span class="sxs-lookup"><span data-stu-id="6b34b-114">Release notes</span></span>
- <span data-ttu-id="6b34b-115">セットアップ手順</span><span class="sxs-lookup"><span data-stu-id="6b34b-115">Setup instructions</span></span>
- <span data-ttu-id="6b34b-116">サンプルスクリプトと操作方法に関する記事</span><span class="sxs-lookup"><span data-stu-id="6b34b-116">Sample scripts and how-to articles</span></span>
- <span data-ttu-id="6b34b-117">DSC のドキュメント</span><span class="sxs-lookup"><span data-stu-id="6b34b-117">DSC documentation</span></span>
- <span data-ttu-id="6b34b-118">SDK のドキュメント</span><span class="sxs-lookup"><span data-stu-id="6b34b-118">SDK documentation</span></span>

<span data-ttu-id="6b34b-119">[概念説明のドキュメント][conceptual]は、バージョン別に分類されていません。</span><span class="sxs-lookup"><span data-stu-id="6b34b-119">The [conceptual documentation][conceptual] is not organized by version.</span></span> <span data-ttu-id="6b34b-120">すべてのバージョンの PowerShell について、すべての記事が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-120">All articles are displayed for every version of PowerShell.</span></span> <span data-ttu-id="6b34b-121">バージョン固有の記事の作成に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-121">We're working to create version-specific articles.</span></span> <span data-ttu-id="6b34b-122">この機能がドキュメントで利用できるようになると、このガイドは適切な情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-122">When that feature is available in our documentation, this guide will be update with the appropriate information.</span></span>

> [!NOTE]
> <span data-ttu-id="6b34b-123">概念的な記事を追加、削除、または名前変更した場合はいつでも、TOC を更新してプル要求に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-123">Anytime a conceptual article is added, removed, or renamed, the TOC must be updated and included in the pull request.</span></span>

## <a name="creating-new-articles"></a><span data-ttu-id="6b34b-124">新しい記事の作成</span><span class="sxs-lookup"><span data-stu-id="6b34b-124">Creating new articles</span></span>

<span data-ttu-id="6b34b-125">投稿する新しいドキュメントについては、GitHub の問題を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-125">A GitHub issue must be created for any new document you want to contribute.</span></span> <span data-ttu-id="6b34b-126">既存の問題を確認して、作業を複製していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b34b-126">Check for existing issues to make sure you're not duplicating efforts.</span></span> <span data-ttu-id="6b34b-127">割り当てられた問題はと見なされ `in progress` ます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-127">Assigned issues are considered to be `in progress`.</span></span> <span data-ttu-id="6b34b-128">問題に対して共同作業を行う場合は、問題に割り当てられている担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6b34b-128">If you wish to collaborate on an issue, contact the person assigned to the issue.</span></span>

<span data-ttu-id="6b34b-129">PowerShell [RFC プロセス][rfc]と同様に、コンテンツを書き込む前に問題を作成します。</span><span class="sxs-lookup"><span data-stu-id="6b34b-129">Similar to the PowerShell [RFC process][rfc], create an issue before you write the content.</span></span> <span data-ttu-id="6b34b-130">この問題により、PowerShell-Docs チームによって却下された作業の時間と労力を無駄にすることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-130">The issue ensures you don't waste time and effort on work that gets rejected by the PowerShell-Docs team.</span></span> <span data-ttu-id="6b34b-131">この問題により、コンテンツのスコープと、PowerShell ドキュメントに含まれる内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-131">The issue allows us to consult with you on the scope of the content and where it fits in the PowerShell documentation.</span></span> <span data-ttu-id="6b34b-132">すべての記事が目次 (目次) に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-132">All articles must be included in the Table of Contents (TOC).</span></span> <span data-ttu-id="6b34b-133">提案された TOC の場所は、問題のディスカッションに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-133">The proposed TOC location should be included in the issue discussion.</span></span>

> [!NOTE]
> <span data-ttu-id="6b34b-134">参照コンテンツの TOC は、公開システムによって自動生成されます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-134">The TOC for reference content is autogenerated by the publishing system.</span></span> <span data-ttu-id="6b34b-135">TOC を更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6b34b-135">You don't have to update the TOC.</span></span>

## <a name="updating-existing-articles"></a><span data-ttu-id="6b34b-136">既存のアーティクルの更新</span><span class="sxs-lookup"><span data-stu-id="6b34b-136">Updating existing articles</span></span>

<span data-ttu-id="6b34b-137">該当する場合、コマンドレットのリファレンス記事は、このリポジトリに保持されているすべてのバージョンの PowerShell で重複しています。</span><span class="sxs-lookup"><span data-stu-id="6b34b-137">Where applicable, cmdlet reference articles are duplicated across all versions of PowerShell maintained in this repository.</span></span> <span data-ttu-id="6b34b-138">コマンドレット参照またはアーティクルに関する問題を報告する場合は、 `About_` 問題の影響を受けるバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-138">When reporting an issue about a cmdlet reference or an `About_` article, you must specify which versions are affected by the issue.</span></span> <span data-ttu-id="6b34b-139">GitHub の issue テンプレートには、バージョンのチェックリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b34b-139">The issue template in GitHub includes a checklist of versions.</span></span> <span data-ttu-id="6b34b-140">チェックボックスを使用して、影響を受けるコンテンツのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b34b-140">Use the checkboxes to specify which versions of the content are affected.</span></span>

<span data-ttu-id="6b34b-141">他のバージョンでも同じ変更が必要かどうかを確認するには、記事のすべてのバージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6b34b-141">Check all version of the article to see if the same change is needed in the other versions.</span></span> <span data-ttu-id="6b34b-142">ファイルの各バージョンに適切な変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="6b34b-142">Apply the appropriate change to each version of the file.</span></span>

## <a name="localized-content"></a><span data-ttu-id="6b34b-143">ローカライズされたコンテンツ</span><span class="sxs-lookup"><span data-stu-id="6b34b-143">Localized content</span></span>

<span data-ttu-id="6b34b-144">PowerShell ドキュメントは英語で書かれており、17個の他の言語に翻訳されています。</span><span class="sxs-lookup"><span data-stu-id="6b34b-144">The PowerShell documentation is written in English and translated into 17 other languages.</span></span> <span data-ttu-id="6b34b-145">英語のコンテンツは、という名前の GitHub リポジトリに格納され `MicrosoftDocs/PowerShell-Docs` ます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-145">The English content is stored in the GitHub repository named `MicrosoftDocs/PowerShell-Docs`.</span></span> <span data-ttu-id="6b34b-146">ローカライズされたコンテンツは、言語ごとに個別のリポジトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-146">The localized content is stored in a separate repository for each language.</span></span> <span data-ttu-id="6b34b-147">リポジトリでは、同じベース名が使用されますが、ロケール名が末尾に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-147">The repositories use the same basename but add the locale name to the end.</span></span> <span data-ttu-id="6b34b-148">たとえば、には `MicrosoftDocs/PowerShell-Docs.de-de` ドイツ語に翻訳されたコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b34b-148">For example, `MicrosoftDocs/PowerShell-Docs.de-de` contains the content that was translated to German.</span></span>

<span data-ttu-id="6b34b-149">一般に、問題と変更は英語のリポジトリに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-149">In general, issues and changes should be submitted to the English repository.</span></span> <span data-ttu-id="6b34b-150">すべての翻訳は最初に英語のコンテンツから開始されます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-150">All translations start from the English content first.</span></span> <span data-ttu-id="6b34b-151">人間と機械の両方の翻訳を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b34b-151">We use both human and machine translation.</span></span>

| <span data-ttu-id="6b34b-152">Translation メソッド</span><span class="sxs-lookup"><span data-stu-id="6b34b-152">Translation method</span></span>  |                              <span data-ttu-id="6b34b-153">Languages</span><span class="sxs-lookup"><span data-stu-id="6b34b-153">Languages</span></span>                               |
| ------------------- | -------------------------------------------------------------------- |
| <span data-ttu-id="6b34b-154">人間による翻訳</span><span class="sxs-lookup"><span data-stu-id="6b34b-154">Human translation</span></span>   | <span data-ttu-id="6b34b-155">de、es、fr-fr、it-IT、ja-jp、ko、韓国、pt-BR、ru-RU、zh-tw、zh-tw、または、-TW</span><span class="sxs-lookup"><span data-stu-id="6b34b-155">de-DE, es-ES, fr-FR, it-IT, ja-JP, ko-KR, pt-BR, ru-RU, zh-CN, zh-TW</span></span> |
| <span data-ttu-id="6b34b-156">機械翻訳</span><span class="sxs-lookup"><span data-stu-id="6b34b-156">Machine translation</span></span> | <span data-ttu-id="6b34b-157">CS-CZ, hu-HU, nl-NL, pl-PL, pt-PT, sv-SE, tr-TR</span><span class="sxs-lookup"><span data-stu-id="6b34b-157">cs-CZ, hu-HU, nl-NL, pl-PL, pt-PT, sv-SE, tr-TR</span></span>                      |

<span data-ttu-id="6b34b-158">機械翻訳によって翻訳されたコンテンツは、単語の選択や文法が必ずしも正しいとは限りません。</span><span class="sxs-lookup"><span data-stu-id="6b34b-158">The content translated by machine translation may not always result in correct word choices and grammar.</span></span> <span data-ttu-id="6b34b-159">記事の技術的な詳細ではなく、任意の言語の翻訳でエラーが見つかった場合は、ローカライズされたリポジトリで問題を開きます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-159">If you find an error in translation for any language, rather than in the technical details of the article, open an issue in the localized repository.</span></span> <span data-ttu-id="6b34b-160">翻訳が間違っていると思われる理由を説明します。</span><span class="sxs-lookup"><span data-stu-id="6b34b-160">Explain why you think the translation is incorrect.</span></span> <span data-ttu-id="6b34b-161">Microsoft のローカライズチームは、これらの問題を確認して対応しています。</span><span class="sxs-lookup"><span data-stu-id="6b34b-161">Our localization team reviews and responds to these issues.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6b34b-162">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6b34b-162">Next steps</span></span>

<span data-ttu-id="6b34b-163">GitHub で変更を送信するには、2つの一般的な方法があります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-163">There are two common ways of submitting changes in GitHub.</span></span> <span data-ttu-id="6b34b-164">両方の方法については、中央の共同作成者ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b34b-164">Both methods are described in the central Contributor's Guide:</span></span>

1. <span data-ttu-id="6b34b-165">GitHub web インターフェイスで [既存のドキュメントを簡単に編集](/contribute/#quick-edits-to-existing-documents) できます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-165">You can make [quick edits to existing documents](/contribute/#quick-edits-to-existing-documents) in the GitHub web interface.</span></span>
1. <span data-ttu-id="6b34b-166">新しい記事を追加したり、複数のファイルを更新したり、その他の大きな変更を行ったりするには、 [完全な GitHub ワークフロー][making-changes] を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b34b-166">Use the [full GitHub workflow][making-changes] for adding new articles, updating multiple files, or other large changes.</span></span>

<span data-ttu-id="6b34b-167">変更を開始する前に、PowerShell-Docs リポジトリのフォークを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-167">Before starting any changes, you should create a fork of the PowerShell-Docs repository.</span></span> <span data-ttu-id="6b34b-168">変更は、PowerShell ドキュメントのコピーの作業ブランチで行う必要があります。GitHub の **クイック編集** 方法を使用している場合は、これらの手順が処理されます。</span><span class="sxs-lookup"><span data-stu-id="6b34b-168">The changes should be made in a working branch in you copy of the PowerShell-Docs. If you're using the **quick edit** method in GitHub, these steps are handled for you.</span></span> <span data-ttu-id="6b34b-169">**完全な GitHub ワークフロー** を使用している場合は、[ローカルで動作][fork]するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b34b-169">If you're using the **full GitHub workflow**, you must be set up to [work locally][fork].</span></span>

<span data-ttu-id="6b34b-170">どちらの方法も、プル要求 (PR) の作成で終了します。</span><span class="sxs-lookup"><span data-stu-id="6b34b-170">Both methods end with the creation of a Pull Request (PR).</span></span> <span data-ttu-id="6b34b-171">詳細とベストプラクティスについて [は、「プル要求の送信](pull-requests.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b34b-171">See [Submitting a pull request](pull-requests.md) for more information and best practices.</span></span>

<!--link refs-->
[conceptual]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference/docs-conceptual
[fork]: /contribute/get-started-setup-local#fork-the-repository
[making-changes]: /contribute/how-to-write-workflows-major#making-your-changes
[psdocs]: https://github.com/MicrosoftDocs/PowerShell-Docs
[ref]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference
[rfc]: https://github.com/PowerShell/powershell-rfc/blob/master/RFC0000-RFC-Process.md

---
title: プル要求を管理する方法
description: この記事では、PowerShell-Docs チームがプル要求を管理する方法について説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: af5280e91aa3744b6172dc3555df6989cb0ce1a2
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86158175"
---
# <a name="managing-pull-requests"></a><span data-ttu-id="bbfac-103">プル要求の管理</span><span class="sxs-lookup"><span data-stu-id="bbfac-103">Managing pull requests</span></span>

<span data-ttu-id="bbfac-104">この記事では、PowerShell-Docs リポジトリでプル要求を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbfac-104">This article documents how we manage pull requests in the PowerShell-Docs repository.</span></span> <span data-ttu-id="bbfac-105">この記事は、PowerShell-Docs チームのメンバーの作業を支援することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="bbfac-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="bbfac-106">一般の共同作成者に対してプロセスを透明化するために、ここで公開されています。</span><span class="sxs-lookup"><span data-stu-id="bbfac-106">It is published here to provide process transparency for our public contributors.</span></span>

## <a name="best-practices"></a><span data-ttu-id="bbfac-107">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="bbfac-107">Best practices</span></span>

- <span data-ttu-id="bbfac-108">PR を送信するユーザーは、ピア レビューなしで PR をマージすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bbfac-108">The person submitting the PR should not merge the PR without a peer review.</span></span>
- <span data-ttu-id="bbfac-109">PR の送信時にピア レビュー担当者を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bbfac-109">Assign the peer reviewer when the PR is submitted.</span></span> <span data-ttu-id="bbfac-110">早期の割り当てにより、レビュー担当者はコメントを付けて速やかに対応できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bbfac-110">Early assignment allows the reviewer to respond sooner with editorial remarks.</span></span>
- <span data-ttu-id="bbfac-111">コメントを使用して、変更の性質や依頼するレビューの種類を説明します。</span><span class="sxs-lookup"><span data-stu-id="bbfac-111">Use comments to describe the nature of the change or the type of review being requested.</span></span> <span data-ttu-id="bbfac-112">レビュー担当者を必ず @mention してください。</span><span class="sxs-lookup"><span data-stu-id="bbfac-112">Be sure to @mention the reviewer.</span></span> <span data-ttu-id="bbfac-113">たとえば、変更が軽微であり、完全な技術レビューを必要としない場合は、それをコメントで説明します。</span><span class="sxs-lookup"><span data-stu-id="bbfac-113">For example, if the change is minor and you don't need a full technical review, explain this in a comment.</span></span>

## <a name="pr-process-steps"></a><span data-ttu-id="bbfac-114">PR プロセスの手順</span><span class="sxs-lookup"><span data-stu-id="bbfac-114">PR Process steps</span></span>

1. <span data-ttu-id="bbfac-115">作成者: PR を作成する</span><span class="sxs-lookup"><span data-stu-id="bbfac-115">Writer: Create PR</span></span>
   - <span data-ttu-id="bbfac-116">PR で解決するイシューをリンクする</span><span class="sxs-lookup"><span data-stu-id="bbfac-116">Link any issues resolved by the PR</span></span>
   - <span data-ttu-id="bbfac-117">GitHub の[自動クローズ](https://help.github.com/en/articles/closing-issues-using-keywords)機能を使用してイシューを閉じる</span><span class="sxs-lookup"><span data-stu-id="bbfac-117">Use GitHub's [autoclose](https://help.github.com/en/articles/closing-issues-using-keywords) feature to close the issue</span></span>
1. <span data-ttu-id="bbfac-118">作成者: ピア レビュー担当者を割り当てる</span><span class="sxs-lookup"><span data-stu-id="bbfac-118">Writer: Assign peer reviewer</span></span>
1. <span data-ttu-id="bbfac-119">レビュー担当者: 校正を行い、(必要に応じて) コメントを付ける</span><span class="sxs-lookup"><span data-stu-id="bbfac-119">Reviewer: proofreads and comments (as necessary)</span></span>
1. <span data-ttu-id="bbfac-120">作成者: レビューのフィードバックを組み込む</span><span class="sxs-lookup"><span data-stu-id="bbfac-120">Writer: Incorporate review feedback</span></span>
1. <span data-ttu-id="bbfac-121">両方: プレビュー表示を確認する</span><span class="sxs-lookup"><span data-stu-id="bbfac-121">Both: Review preview rendering</span></span>
1. <span data-ttu-id="bbfac-122">両方: 検証レポートを確認する - 警告とエラーを修正</span><span class="sxs-lookup"><span data-stu-id="bbfac-122">Both: Review validation report - fix warnings and errors</span></span>
1. <span data-ttu-id="bbfac-123">作成者: サインオフ コメント (Acrolinx 情報を含む) を追加する</span><span class="sxs-lookup"><span data-stu-id="bbfac-123">Writer: Add sign-off comment (include Acrolinx info)</span></span>
1. <span data-ttu-id="bbfac-124">レビュー担当者: レビューを "承認済み" としてマークする</span><span class="sxs-lookup"><span data-stu-id="bbfac-124">Reviewer: Mark review "Approved"</span></span>
1. <span data-ttu-id="bbfac-125">リポジトリ管理者: PR をマージする (条件については下記を参照)</span><span class="sxs-lookup"><span data-stu-id="bbfac-125">Repo Admin: Merge PR (see below for criteria)</span></span>

## <a name="content-reviewer-checklist"></a><span data-ttu-id="bbfac-126">コンテンツ レビュー担当者チェックリスト</span><span class="sxs-lookup"><span data-stu-id="bbfac-126">Content Reviewer Checklist</span></span>

<span data-ttu-id="bbfac-127">より包括的なリストについては、[編集チェックリスト](editorial-checklist.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbfac-127">See the [editorial checklist](editorial-checklist.md) for a more comprehensive list.</span></span>

- <span data-ttu-id="bbfac-128">文法、スタイル、簡潔さ、技術的正確さをチェックする</span><span class="sxs-lookup"><span data-stu-id="bbfac-128">Proofread for grammar, style, concision, technical accuracy</span></span>
- <span data-ttu-id="bbfac-129">各例がターゲット バージョンに対応していることを確認する</span><span class="sxs-lookup"><span data-stu-id="bbfac-129">Ensure examples still apply for the target version</span></span>
- <span data-ttu-id="bbfac-130">プレビュー表示を確認する</span><span class="sxs-lookup"><span data-stu-id="bbfac-130">Check Preview rendering</span></span>
- <span data-ttu-id="bbfac-131">メタデータを確認する - ms.date、ms.assetid の削除、必須フィールドの確認</span><span class="sxs-lookup"><span data-stu-id="bbfac-131">Check metadata - ms.date, remove ms.assetid, ensure required fields</span></span>
- <span data-ttu-id="bbfac-132">マークダウンの正確さを検証する</span><span class="sxs-lookup"><span data-stu-id="bbfac-132">Validate markdown correctness</span></span>
  - <span data-ttu-id="bbfac-133">特定のコンテンツの書式設定について、スタイル ガイドを参照する</span><span class="sxs-lookup"><span data-stu-id="bbfac-133">See style guide for formatting specific content</span></span>
- <span data-ttu-id="bbfac-134">次のように例を再構成する</span><span class="sxs-lookup"><span data-stu-id="bbfac-134">Reorganize examples as follows:</span></span>
  - <span data-ttu-id="bbfac-135">序文</span><span class="sxs-lookup"><span data-stu-id="bbfac-135">Intro sentence(s)</span></span>
  - <span data-ttu-id="bbfac-136">コードと出力</span><span class="sxs-lookup"><span data-stu-id="bbfac-136">Code and output</span></span>
  - <span data-ttu-id="bbfac-137">コードの詳細な説明 (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="bbfac-137">Detailed explanation of code (as necessary)</span></span>
- <span data-ttu-id="bbfac-138">ハイパーリンクの正確性を確認する</span><span class="sxs-lookup"><span data-stu-id="bbfac-138">Check hyperlinks for accuracy</span></span>
  - <span data-ttu-id="bbfac-139">TechNet/MSDN リンクを置換または削除する</span><span class="sxs-lookup"><span data-stu-id="bbfac-139">Replace or remove TechNet/MSDN links</span></span>
  - <span data-ttu-id="bbfac-140">ターゲットへのリダイレクトの最小数を確保する</span><span class="sxs-lookup"><span data-stu-id="bbfac-140">Ensure minimum number of redirects to target</span></span>
  - <span data-ttu-id="bbfac-141">HTTPS を確認する</span><span class="sxs-lookup"><span data-stu-id="bbfac-141">Ensure HTTPS</span></span>
  - <span data-ttu-id="bbfac-142">リンクの種類を修正する</span><span class="sxs-lookup"><span data-stu-id="bbfac-142">Correct link type</span></span>
    - <span data-ttu-id="bbfac-143">ローカル ファイルのファイル リンク</span><span class="sxs-lookup"><span data-stu-id="bbfac-143">File links for local files</span></span>
    - <span data-ttu-id="bbfac-144">ドキュメント セットの外部のファイルの URL リンク</span><span class="sxs-lookup"><span data-stu-id="bbfac-144">URL links for files outside of the docset</span></span>
  - <span data-ttu-id="bbfac-145">URL からロケールを削除する</span><span class="sxs-lookup"><span data-stu-id="bbfac-145">Remove locales from URLs</span></span>
  - <span data-ttu-id="bbfac-146">`docs.microsoft.com` を参照する URL を簡略化する</span><span class="sxs-lookup"><span data-stu-id="bbfac-146">Simplify URLs pointing to `docs.microsoft.com`</span></span>

## <a name="branch-merge-process"></a><span data-ttu-id="bbfac-147">ブランチ マージ プロセス</span><span class="sxs-lookup"><span data-stu-id="bbfac-147">Branch Merge Process</span></span>

<span data-ttu-id="bbfac-148">staging ブランチは、live にマージされる唯一のブランチです。</span><span class="sxs-lookup"><span data-stu-id="bbfac-148">The staging branch is the only branch that should ever be merged into live.</span></span> <span data-ttu-id="bbfac-149">有効期間が短い (作業) ブランチからのマージはスカッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbfac-149">Merges from short-lived (working) branches should be squashed.</span></span>

| <span data-ttu-id="bbfac-150">*マージ元/マージ先*</span><span class="sxs-lookup"><span data-stu-id="bbfac-150">*Merge from/to*</span></span>  | <span data-ttu-id="bbfac-151">*release ブランチ*</span><span class="sxs-lookup"><span data-stu-id="bbfac-151">*release-branch*</span></span> | <span data-ttu-id="bbfac-152">*staging*</span><span class="sxs-lookup"><span data-stu-id="bbfac-152">*staging*</span></span>        | <span data-ttu-id="bbfac-153">*live*</span><span class="sxs-lookup"><span data-stu-id="bbfac-153">*live*</span></span>      |
| ---------------- |:----------------:|:----------------:|:-----------:|
| <span data-ttu-id="bbfac-154">*作業ブランチ*</span><span class="sxs-lookup"><span data-stu-id="bbfac-154">*working-branch*</span></span> | <span data-ttu-id="bbfac-155">スカッシュしてマージ</span><span class="sxs-lookup"><span data-stu-id="bbfac-155">squash and merge</span></span> | <span data-ttu-id="bbfac-156">スカッシュしてマージ</span><span class="sxs-lookup"><span data-stu-id="bbfac-156">squash and merge</span></span> | <span data-ttu-id="bbfac-157">禁止</span><span class="sxs-lookup"><span data-stu-id="bbfac-157">Not allowed</span></span> |
| <span data-ttu-id="bbfac-158">*release ブランチ*</span><span class="sxs-lookup"><span data-stu-id="bbfac-158">*release-branch*</span></span> | &mdash;          | <span data-ttu-id="bbfac-159">merge</span><span class="sxs-lookup"><span data-stu-id="bbfac-159">merge</span></span>            | <span data-ttu-id="bbfac-160">禁止</span><span class="sxs-lookup"><span data-stu-id="bbfac-160">Not allowed</span></span> |
| <span data-ttu-id="bbfac-161">*staging*</span><span class="sxs-lookup"><span data-stu-id="bbfac-161">*staging*</span></span>        | <span data-ttu-id="bbfac-162">リベース</span><span class="sxs-lookup"><span data-stu-id="bbfac-162">rebase</span></span>           | &mdash;          | <span data-ttu-id="bbfac-163">merge</span><span class="sxs-lookup"><span data-stu-id="bbfac-163">merge</span></span>       |

### <a name="pr-merger-checklist"></a><span data-ttu-id="bbfac-164">PR マージ担当者チェックリスト</span><span class="sxs-lookup"><span data-stu-id="bbfac-164">PR Merger checklist</span></span>

- <span data-ttu-id="bbfac-165">コンテンツのレビューが完了している</span><span class="sxs-lookup"><span data-stu-id="bbfac-165">Content review complete</span></span>
- <span data-ttu-id="bbfac-166">その変更の正しいターゲット ブランチである</span><span class="sxs-lookup"><span data-stu-id="bbfac-166">Correct target branch for the change</span></span>
- <span data-ttu-id="bbfac-167">マージの競合がない</span><span class="sxs-lookup"><span data-stu-id="bbfac-167">No merge conflicts</span></span>
- <span data-ttu-id="bbfac-168">検証とビルド ステップがすべて成功している</span><span class="sxs-lookup"><span data-stu-id="bbfac-168">All validation and build step pass</span></span>
  - <span data-ttu-id="bbfac-169">警告と推奨事項が修正されている (例外については、「[Notes](#notes)」を参照)</span><span class="sxs-lookup"><span data-stu-id="bbfac-169">Warnings and suggestions should be fixed (see [Notes](#notes) for exceptions)</span></span>
  - <span data-ttu-id="bbfac-170">壊れたリンクがない</span><span class="sxs-lookup"><span data-stu-id="bbfac-170">No broken links</span></span>
- <span data-ttu-id="bbfac-171">テーブルに従ってマージする</span><span class="sxs-lookup"><span data-stu-id="bbfac-171">Merge according to table</span></span>

### <a name="notes"></a><span data-ttu-id="bbfac-172">Notes</span><span class="sxs-lookup"><span data-stu-id="bbfac-172">Notes</span></span>

<span data-ttu-id="bbfac-173">次の警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="bbfac-173">The following warnings can be ignored:</span></span>

```
Can't find service name for `<version>/<modulepath>/About/About.md`
```

```
Metadata with following name(s) are not allowed to be set in Yaml header, or as file level
metadata in docfx.json, or as global metadata in docfx.json: `locale`. They are generated by
Docs platform, so the values set in these 3 places will be ignored. Please remove them from all
3 places to resolve the warning.
```

<span data-ttu-id="bbfac-174">PR がマージされると、ターゲット ブランチの HEAD が変更されます。</span><span class="sxs-lookup"><span data-stu-id="bbfac-174">When a PR is merged, the HEAD of the target branch is changed.</span></span> <span data-ttu-id="bbfac-175">以前の HEAD に基づいたオープン PR は古くなっています。</span><span class="sxs-lookup"><span data-stu-id="bbfac-175">Any open PRs that were based on the previous HEAD are now outdated.</span></span> <span data-ttu-id="bbfac-176">古い PR は、GitHub でマージの警告をオーバーライドする管理者権限を使用してマージできます。</span><span class="sxs-lookup"><span data-stu-id="bbfac-176">The outdated PR can be merged using Admin rights to override the merge warnings in GitHub.</span></span> <span data-ttu-id="bbfac-177">以前にマージされた PR で同じファイルを操作していない場合は、これを安全に実行できます。</span><span class="sxs-lookup"><span data-stu-id="bbfac-177">This is safe to do if the previously merged PR(s) have not touched the same files.</span></span> <span data-ttu-id="bbfac-178">ただし、 **[Update Branch]** ボタンをクリックするのが最も安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="bbfac-178">However, clicking the **Update Branch** button is the safest option.</span></span> <span data-ttu-id="bbfac-179">修正する必要がある未解決の競合が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bbfac-179">You may have unresolved conflicts that need to be fixed.</span></span>

## <a name="publishing-to-live"></a><span data-ttu-id="bbfac-180">ライブへの公開</span><span class="sxs-lookup"><span data-stu-id="bbfac-180">Publishing to Live</span></span>

<span data-ttu-id="bbfac-181">`staging` ブランチに蓄積された変更をライブ Web サイトに定期的に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbfac-181">Periodically, the changes accumulated in the `staging` branch need to be published to the live website.</span></span> <span data-ttu-id="bbfac-182">そのためには、`staging` ブランチを `live` ブランチにマージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbfac-182">This require merging the `staging` branch into the `live` branch.</span></span>

- <span data-ttu-id="bbfac-183">少なくとも週に 1 回は、`staging` ブランチを `live` ブランチにマージします。</span><span class="sxs-lookup"><span data-stu-id="bbfac-183">The `staging` branch should be merged to `live` at least once per week.</span></span>
- <span data-ttu-id="bbfac-184">重要な変更の後、`staging` ブランチを `live` にマージします。</span><span class="sxs-lookup"><span data-stu-id="bbfac-184">The `staging` branch should be merged to `live` after any significant change.</span></span>
  - <span data-ttu-id="bbfac-185">50 個以上のファイルを変更したとき</span><span class="sxs-lookup"><span data-stu-id="bbfac-185">Changes to 50 or more files</span></span>
  - <span data-ttu-id="bbfac-186">release ブランチをマージした後</span><span class="sxs-lookup"><span data-stu-id="bbfac-186">After merging a release branch</span></span>
  - <span data-ttu-id="bbfac-187">リポジトリまたはドキュメント セットの構成 (docfx.json、OPS 構成、ビルド スクリプトなど) を変更したとき</span><span class="sxs-lookup"><span data-stu-id="bbfac-187">Changes to repo or docset configurations (docfx.json, OPS configs, build scripts, etc.)</span></span>
  - <span data-ttu-id="bbfac-188">リダイレクト ファイルを変更したとき</span><span class="sxs-lookup"><span data-stu-id="bbfac-188">Changes to the redirection file</span></span>
  - <span data-ttu-id="bbfac-189">TOC を変更したとき</span><span class="sxs-lookup"><span data-stu-id="bbfac-189">Changes to the TOC</span></span>
  - <span data-ttu-id="bbfac-190">"プロジェクト" ブランチをマージした後 (コンテンツの再構成、一括更新など)</span><span class="sxs-lookup"><span data-stu-id="bbfac-190">After merging a "project" branch (content reorg, bulk update, etc.)</span></span>

---
title: プル要求を管理する方法
description: この記事では、PowerShell-Docs チームがプル要求を管理する方法について説明します。
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 7050db6ad30963d0a75b2a083daace494d703027
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "99601786"
---
# <a name="managing-pull-requests"></a><span data-ttu-id="e75bc-103">プル要求の管理</span><span class="sxs-lookup"><span data-stu-id="e75bc-103">Managing pull requests</span></span>

<span data-ttu-id="e75bc-104">この記事では、PowerShell-Docs リポジトリでプル要求を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e75bc-104">This article documents how we manage pull requests in the PowerShell-Docs repository.</span></span> <span data-ttu-id="e75bc-105">この記事は、PowerShell-Docs チームのメンバーの作業を支援することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="e75bc-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="e75bc-106">ここで公開されているので、パブリックコントリビューターのプロセスの透明性を提供します。</span><span class="sxs-lookup"><span data-stu-id="e75bc-106">It's published here to provide process transparency for our public contributors.</span></span>

## <a name="best-practices"></a><span data-ttu-id="e75bc-107">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="e75bc-107">Best practices</span></span>

- <span data-ttu-id="e75bc-108">PR を送信する人は、ピアレビューを行わずに PR を結合することはできません。</span><span class="sxs-lookup"><span data-stu-id="e75bc-108">The person submitting the PR shouldn't merge the PR without a peer review.</span></span>
- <span data-ttu-id="e75bc-109">PR の送信時にピア レビュー担当者を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e75bc-109">Assign the peer reviewer when the PR is submitted.</span></span> <span data-ttu-id="e75bc-110">早期の割り当てにより、レビュー担当者はコメントを付けて速やかに対応できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e75bc-110">Early assignment allows the reviewer to respond sooner with editorial remarks.</span></span>
- <span data-ttu-id="e75bc-111">コメントを使用して、変更の性質や依頼するレビューの種類を説明します。</span><span class="sxs-lookup"><span data-stu-id="e75bc-111">Use comments to describe the nature of the change or the type of review being requested.</span></span> <span data-ttu-id="e75bc-112">レビュー担当者を必ず @mention してください。</span><span class="sxs-lookup"><span data-stu-id="e75bc-112">Be sure to @mention the reviewer.</span></span> <span data-ttu-id="e75bc-113">たとえば、変更が軽微であり、完全な技術レビューを必要としない場合は、それをコメントで説明します。</span><span class="sxs-lookup"><span data-stu-id="e75bc-113">For example, if the change is minor and you don't need a full technical review, explain this in a comment.</span></span>

## <a name="pr-process-steps"></a><span data-ttu-id="e75bc-114">PR プロセスの手順</span><span class="sxs-lookup"><span data-stu-id="e75bc-114">PR Process steps</span></span>

1. <span data-ttu-id="e75bc-115">作成者: PR を作成する</span><span class="sxs-lookup"><span data-stu-id="e75bc-115">Writer: Create PR</span></span>
   - <span data-ttu-id="e75bc-116">PR で解決するイシューをリンクする</span><span class="sxs-lookup"><span data-stu-id="e75bc-116">Link any issues resolved by the PR</span></span>
   - <span data-ttu-id="e75bc-117">GitHub の[自動クローズ](https://help.github.com/en/articles/closing-issues-using-keywords)機能を使用してイシューを閉じる</span><span class="sxs-lookup"><span data-stu-id="e75bc-117">Use GitHub's [autoclose](https://help.github.com/en/articles/closing-issues-using-keywords) feature to close the issue</span></span>
1. <span data-ttu-id="e75bc-118">作成者: ピア レビュー担当者を割り当てる</span><span class="sxs-lookup"><span data-stu-id="e75bc-118">Writer: Assign peer reviewer</span></span>
1. <span data-ttu-id="e75bc-119">レビュー担当者: 校正を行い、(必要に応じて) コメントを付ける</span><span class="sxs-lookup"><span data-stu-id="e75bc-119">Reviewer: proofreads and comments (as necessary)</span></span>
1. <span data-ttu-id="e75bc-120">作成者: レビューのフィードバックを組み込む</span><span class="sxs-lookup"><span data-stu-id="e75bc-120">Writer: Incorporate review feedback</span></span>
1. <span data-ttu-id="e75bc-121">両方: プレビュー表示を確認する</span><span class="sxs-lookup"><span data-stu-id="e75bc-121">Both: Review preview rendering</span></span>
1. <span data-ttu-id="e75bc-122">両方: 検証レポートを確認する - 警告とエラーを修正</span><span class="sxs-lookup"><span data-stu-id="e75bc-122">Both: Review validation report - fix warnings and errors</span></span>
1. <span data-ttu-id="e75bc-123">作成者: サインオフ コメント (Acrolinx 情報を含む) を追加する</span><span class="sxs-lookup"><span data-stu-id="e75bc-123">Writer: Add sign-off comment (include Acrolinx info)</span></span>
1. <span data-ttu-id="e75bc-124">レビュー担当者: レビューを "承認済み" としてマークする</span><span class="sxs-lookup"><span data-stu-id="e75bc-124">Reviewer: Mark review "Approved"</span></span>
1. <span data-ttu-id="e75bc-125">リポジトリ管理者: PR をマージする (条件については下記を参照)</span><span class="sxs-lookup"><span data-stu-id="e75bc-125">Repo Admin: Merge PR (see below for criteria)</span></span>

## <a name="content-reviewer-checklist"></a><span data-ttu-id="e75bc-126">コンテンツ レビュー担当者チェックリスト</span><span class="sxs-lookup"><span data-stu-id="e75bc-126">Content Reviewer Checklist</span></span>

<span data-ttu-id="e75bc-127">より包括的なリストについては、[編集チェックリスト](editorial-checklist.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e75bc-127">See the [editorial checklist](editorial-checklist.md) for a more comprehensive list.</span></span>

- <span data-ttu-id="e75bc-128">文法、スタイル、簡潔さ、技術的正確さをチェックする</span><span class="sxs-lookup"><span data-stu-id="e75bc-128">Proofread for grammar, style, concision, technical accuracy</span></span>
- <span data-ttu-id="e75bc-129">各例がターゲット バージョンに対応していることを確認する</span><span class="sxs-lookup"><span data-stu-id="e75bc-129">Ensure examples still apply for the target version</span></span>
- <span data-ttu-id="e75bc-130">プレビュー表示を確認する</span><span class="sxs-lookup"><span data-stu-id="e75bc-130">Check Preview rendering</span></span>
- <span data-ttu-id="e75bc-131">メタデータを確認する - ms.date、ms.assetid の削除、必須フィールドの確認</span><span class="sxs-lookup"><span data-stu-id="e75bc-131">Check metadata - ms.date, remove ms.assetid, ensure required fields</span></span>
- <span data-ttu-id="e75bc-132">マークダウンの正確さを検証する</span><span class="sxs-lookup"><span data-stu-id="e75bc-132">Validate markdown correctness</span></span>
  - <span data-ttu-id="e75bc-133">コンテンツ固有の書式規則については、「スタイルガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e75bc-133">See style guide for content-specific formatting rules</span></span>
- <span data-ttu-id="e75bc-134">次のように例を再構成する</span><span class="sxs-lookup"><span data-stu-id="e75bc-134">Reorganize examples as follows:</span></span>
  - <span data-ttu-id="e75bc-135">序文</span><span class="sxs-lookup"><span data-stu-id="e75bc-135">Intro sentence(s)</span></span>
  - <span data-ttu-id="e75bc-136">コードと出力</span><span class="sxs-lookup"><span data-stu-id="e75bc-136">Code and output</span></span>
  - <span data-ttu-id="e75bc-137">コードの詳細な説明 (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="e75bc-137">Detailed explanation of code (as necessary)</span></span>
- <span data-ttu-id="e75bc-138">ハイパーリンクの正確性を確認する</span><span class="sxs-lookup"><span data-stu-id="e75bc-138">Check hyperlinks for accuracy</span></span>
  - <span data-ttu-id="e75bc-139">TechNet/MSDN リンクを置換または削除する</span><span class="sxs-lookup"><span data-stu-id="e75bc-139">Replace or remove TechNet/MSDN links</span></span>
  - <span data-ttu-id="e75bc-140">ターゲットへのリダイレクトの最小数を確保する</span><span class="sxs-lookup"><span data-stu-id="e75bc-140">Ensure minimum number of redirects to target</span></span>
  - <span data-ttu-id="e75bc-141">HTTPS を確認する</span><span class="sxs-lookup"><span data-stu-id="e75bc-141">Ensure HTTPS</span></span>
  - <span data-ttu-id="e75bc-142">リンクの種類を修正する</span><span class="sxs-lookup"><span data-stu-id="e75bc-142">Correct link type</span></span>
    - <span data-ttu-id="e75bc-143">ローカル ファイルのファイル リンク</span><span class="sxs-lookup"><span data-stu-id="e75bc-143">File links for local files</span></span>
    - <span data-ttu-id="e75bc-144">ドキュメント セットの外部のファイルの URL リンク</span><span class="sxs-lookup"><span data-stu-id="e75bc-144">URL links for files outside of the docset</span></span>
  - <span data-ttu-id="e75bc-145">URL からロケールを削除する</span><span class="sxs-lookup"><span data-stu-id="e75bc-145">Remove locales from URLs</span></span>
  - <span data-ttu-id="e75bc-146">`docs.microsoft.com` を参照する URL を簡略化する</span><span class="sxs-lookup"><span data-stu-id="e75bc-146">Simplify URLs pointing to `docs.microsoft.com`</span></span>

## <a name="branch-merge-process"></a><span data-ttu-id="e75bc-147">ブランチ マージ プロセス</span><span class="sxs-lookup"><span data-stu-id="e75bc-147">Branch Merge Process</span></span>

<span data-ttu-id="e75bc-148">分岐は、 `staging` にマージされる唯一の分岐です `live` 。</span><span class="sxs-lookup"><span data-stu-id="e75bc-148">The `staging` branch is the only branch that is merged into `live`.</span></span> <span data-ttu-id="e75bc-149">有効期間が短い (作業) ブランチからのマージはスカッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e75bc-149">Merges from short-lived (working) branches should be squashed.</span></span>

| <span data-ttu-id="e75bc-150">*マージ元/マージ先*</span><span class="sxs-lookup"><span data-stu-id="e75bc-150">*Merge from/to*</span></span>  | <span data-ttu-id="e75bc-151">*release ブランチ*</span><span class="sxs-lookup"><span data-stu-id="e75bc-151">*release-branch*</span></span> | <span data-ttu-id="e75bc-152">*staging*</span><span class="sxs-lookup"><span data-stu-id="e75bc-152">*staging*</span></span>        | <span data-ttu-id="e75bc-153">*live*</span><span class="sxs-lookup"><span data-stu-id="e75bc-153">*live*</span></span>      |
| ---------------- |:----------------:|:----------------:|:-----------:|
| <span data-ttu-id="e75bc-154">*作業ブランチ*</span><span class="sxs-lookup"><span data-stu-id="e75bc-154">*working-branch*</span></span> | <span data-ttu-id="e75bc-155">スカッシュしてマージ</span><span class="sxs-lookup"><span data-stu-id="e75bc-155">squash and merge</span></span> | <span data-ttu-id="e75bc-156">スカッシュしてマージ</span><span class="sxs-lookup"><span data-stu-id="e75bc-156">squash and merge</span></span> | <span data-ttu-id="e75bc-157">禁止</span><span class="sxs-lookup"><span data-stu-id="e75bc-157">Not allowed</span></span> |
| <span data-ttu-id="e75bc-158">*release ブランチ*</span><span class="sxs-lookup"><span data-stu-id="e75bc-158">*release-branch*</span></span> | &mdash;          | <span data-ttu-id="e75bc-159">merge</span><span class="sxs-lookup"><span data-stu-id="e75bc-159">merge</span></span>            | <span data-ttu-id="e75bc-160">禁止</span><span class="sxs-lookup"><span data-stu-id="e75bc-160">Not allowed</span></span> |
| <span data-ttu-id="e75bc-161">*staging*</span><span class="sxs-lookup"><span data-stu-id="e75bc-161">*staging*</span></span>        | <span data-ttu-id="e75bc-162">リベース</span><span class="sxs-lookup"><span data-stu-id="e75bc-162">rebase</span></span>           | &mdash;          | <span data-ttu-id="e75bc-163">merge</span><span class="sxs-lookup"><span data-stu-id="e75bc-163">merge</span></span>       |

### <a name="pr-merger-checklist"></a><span data-ttu-id="e75bc-164">PR マージ担当者チェックリスト</span><span class="sxs-lookup"><span data-stu-id="e75bc-164">PR Merger checklist</span></span>

- <span data-ttu-id="e75bc-165">コンテンツのレビューが完了している</span><span class="sxs-lookup"><span data-stu-id="e75bc-165">Content review complete</span></span>
- <span data-ttu-id="e75bc-166">その変更の正しいターゲット ブランチである</span><span class="sxs-lookup"><span data-stu-id="e75bc-166">Correct target branch for the change</span></span>
- <span data-ttu-id="e75bc-167">マージの競合がない</span><span class="sxs-lookup"><span data-stu-id="e75bc-167">No merge conflicts</span></span>
- <span data-ttu-id="e75bc-168">検証とビルド ステップがすべて成功している</span><span class="sxs-lookup"><span data-stu-id="e75bc-168">All validation and build step pass</span></span>
  - <span data-ttu-id="e75bc-169">警告と推奨事項が修正されている (例外については、「[Notes](#notes)」を参照)</span><span class="sxs-lookup"><span data-stu-id="e75bc-169">Warnings and suggestions should be fixed (see [Notes](#notes) for exceptions)</span></span>
  - <span data-ttu-id="e75bc-170">壊れたリンクがない</span><span class="sxs-lookup"><span data-stu-id="e75bc-170">No broken links</span></span>
- <span data-ttu-id="e75bc-171">テーブルに従ってマージする</span><span class="sxs-lookup"><span data-stu-id="e75bc-171">Merge according to table</span></span>

### <a name="notes"></a><span data-ttu-id="e75bc-172">Notes</span><span class="sxs-lookup"><span data-stu-id="e75bc-172">Notes</span></span>

<span data-ttu-id="e75bc-173">次の警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="e75bc-173">The following warnings can be ignored:</span></span>

```
Can't find service name for `<version>/<modulepath>/About/About.md`
```

```
Metadata with following name(s) are not allowed to be set in Yaml header, or as file level
metadata in docfx.json, or as global metadata in docfx.json: `locale`. They are generated by
Docs platform, so the values set in these 3 places will be ignored. Please remove them from all
3 places to resolve the warning.
```

<span data-ttu-id="e75bc-174">PR がマージされると、ターゲット ブランチの HEAD が変更されます。</span><span class="sxs-lookup"><span data-stu-id="e75bc-174">When a PR is merged, the HEAD of the target branch is changed.</span></span> <span data-ttu-id="e75bc-175">以前の HEAD に基づいたオープン PR は古くなっています。</span><span class="sxs-lookup"><span data-stu-id="e75bc-175">Any open PRs that were based on the previous HEAD are now outdated.</span></span> <span data-ttu-id="e75bc-176">古い PR は、GitHub でマージの警告をオーバーライドする管理者権限を使用してマージできます。</span><span class="sxs-lookup"><span data-stu-id="e75bc-176">The outdated PR can be merged using Admin rights to override the merge warnings in GitHub.</span></span> <span data-ttu-id="e75bc-177">以前にマージされた PR で同じファイルを操作していない場合は、これを安全に実行できます。</span><span class="sxs-lookup"><span data-stu-id="e75bc-177">This is safe to do if the previously merged PR(s) have not touched the same files.</span></span> <span data-ttu-id="e75bc-178">ただし、 **[Update Branch]** ボタンをクリックするのが最も安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="e75bc-178">However, clicking the **Update Branch** button is the safest option.</span></span> <span data-ttu-id="e75bc-179">修正する必要がある未解決の競合が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e75bc-179">You may have unresolved conflicts that need to be fixed.</span></span>

## <a name="publishing-to-live"></a><span data-ttu-id="e75bc-180">ライブへの公開</span><span class="sxs-lookup"><span data-stu-id="e75bc-180">Publishing to Live</span></span>

<span data-ttu-id="e75bc-181">`staging` ブランチに蓄積された変更をライブ Web サイトに定期的に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e75bc-181">Periodically, the changes accumulated in the `staging` branch need to be published to the live website.</span></span>

- <span data-ttu-id="e75bc-182">`staging`分岐は、3PM PST の各曜日にマージされ `live` ます。</span><span class="sxs-lookup"><span data-stu-id="e75bc-182">The `staging` branch is merged to `live` each weekday at 3pm PST.</span></span>
- <span data-ttu-id="e75bc-183">重要な変更の後、`staging` ブランチを `live` にマージします。</span><span class="sxs-lookup"><span data-stu-id="e75bc-183">The `staging` branch should be merged to `live` after any significant change.</span></span>
  - <span data-ttu-id="e75bc-184">50 個以上のファイルを変更したとき</span><span class="sxs-lookup"><span data-stu-id="e75bc-184">Changes to 50 or more files</span></span>
  - <span data-ttu-id="e75bc-185">release ブランチをマージした後</span><span class="sxs-lookup"><span data-stu-id="e75bc-185">After merging a release branch</span></span>
  - <span data-ttu-id="e75bc-186">リポジトリまたはドキュメント セットの構成 (docfx.json、OPS 構成、ビルド スクリプトなど) を変更したとき</span><span class="sxs-lookup"><span data-stu-id="e75bc-186">Changes to repo or docset configurations (docfx.json, OPS configs, build scripts, etc.)</span></span>
  - <span data-ttu-id="e75bc-187">リダイレクト ファイルを変更したとき</span><span class="sxs-lookup"><span data-stu-id="e75bc-187">Changes to the redirection file</span></span>
  - <span data-ttu-id="e75bc-188">TOC を変更したとき</span><span class="sxs-lookup"><span data-stu-id="e75bc-188">Changes to the TOC</span></span>
  - <span data-ttu-id="e75bc-189">"プロジェクト" ブランチをマージした後 (コンテンツの再構成、一括更新など)</span><span class="sxs-lookup"><span data-stu-id="e75bc-189">After merging a "project" branch (content reorg, bulk update, etc.)</span></span>

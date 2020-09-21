---
title: プル要求を送信する方法
description: この記事では、PowerShell-Docs リポジトリにプル要求を送信する方法について説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 8b392a36c9469b83cf4f088c1799720a091434b4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782652"
---
# <a name="how-to-submit-pull-requests"></a><span data-ttu-id="11a40-103">プル要求を送信する方法</span><span class="sxs-lookup"><span data-stu-id="11a40-103">How to submit pull requests</span></span>

<span data-ttu-id="11a40-104">コンテンツを変更するには、フォークからプル要求 (PR) を送信します。</span><span class="sxs-lookup"><span data-stu-id="11a40-104">To make changes to content, submit a pull request (PR) from your fork.</span></span> <span data-ttu-id="11a40-105">プル要求をマージするには、レビューが必要です。</span><span class="sxs-lookup"><span data-stu-id="11a40-105">A pull request must be reviewed before it can merged.</span></span> <span data-ttu-id="11a40-106">最良の結果を得るために、プル要求を送信する前に[編集チェックリスト](editorial-checklist.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="11a40-106">For best results, review the [editorial checklist](editorial-checklist.md) before submitting your pull request.</span></span>

## <a name="target-the-correct-branch"></a><span data-ttu-id="11a40-107">正しいブランチをターゲットにする</span><span class="sxs-lookup"><span data-stu-id="11a40-107">Target the correct branch</span></span>

<span data-ttu-id="11a40-108">すべてのプル要求は、`staging` ブランチをターゲットにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11a40-108">All pull requests should target the `staging` branch.</span></span> <span data-ttu-id="11a40-109">変更を `live` ブランチに送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="11a40-109">Changes should never be submitted to the `live` branch.</span></span> <span data-ttu-id="11a40-110">`staging` ブランチで行われた変更が `live` にマージされ、`live` に対する変更が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="11a40-110">Changes made in the `staging` branch get merged into `live`, overwriting any changes made to `live`.</span></span>

<span data-ttu-id="11a40-111">PowerShell のリリースされていないバージョンにのみ適用される変更を送信する場合は、そのバージョンの release ブランチがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="11a40-111">If you are submitting a change that only applies to an unreleased version of PowerShell, check for a release branch for that version.</span></span> <span data-ttu-id="11a40-112">PR は、release ブランチをターゲットにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11a40-112">Your PR should be targeted at the release branch.</span></span> <span data-ttu-id="11a40-113">release ブランチの名前のパターンは、`release-<version>` です。</span><span class="sxs-lookup"><span data-stu-id="11a40-113">Release branches have the following name pattern: `release-<version>`.</span></span>

## <a name="make-the-pull-request-process-work-better-for-everyone"></a><span data-ttu-id="11a40-114">プル要求プロセスをすべてのユーザーに対して効果的に機能させる</span><span class="sxs-lookup"><span data-stu-id="11a40-114">Make the pull request process work better for everyone</span></span>

<span data-ttu-id="11a40-115">PR をよりシンプルで焦点を絞ったものにすると、レビューとマージに要する時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="11a40-115">The simpler and more focused you can make your PR, the faster it can be reviewed and merged.</span></span>

### <a name="avoid-branches-that-update-large-numbers-of-files-or-contain-unrelated-changes"></a><span data-ttu-id="11a40-116">多数のファイルを更新するブランチや、関連性のない変更を含むブランチを避けます。</span><span class="sxs-lookup"><span data-stu-id="11a40-116">Avoid branches that update large numbers of files or contain unrelated changes</span></span>

<span data-ttu-id="11a40-117">関連性のない変更を含む PR を作成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="11a40-117">Avoid creating PRs that contain unrelated changes.</span></span> <span data-ttu-id="11a40-118">既存の記事の軽微な更新は、新しい記事や大規模な改訂から切り離します。</span><span class="sxs-lookup"><span data-stu-id="11a40-118">Separate minor updates to existing articles from new articles or major rewrites.</span></span> <span data-ttu-id="11a40-119">このような変更には、別の作業ブランチで対応します。</span><span class="sxs-lookup"><span data-stu-id="11a40-119">Work on these changes in separate working branches.</span></span>

<span data-ttu-id="11a40-120">一括変更では、多数の変更されたファイルを含む PR が作成されます。</span><span class="sxs-lookup"><span data-stu-id="11a40-120">Bulk changes create PRs with large numbers of changed files.</span></span> <span data-ttu-id="11a40-121">PR の変更されたファイルを最大 50 個に制限します。</span><span class="sxs-lookup"><span data-stu-id="11a40-121">Limit your PRs to a maximum of 50 changed files.</span></span> <span data-ttu-id="11a40-122">大規模な PR はレビューするのが難しく、エラーを含む可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="11a40-122">Large PRs are difficult to review and are more prone to contain errors.</span></span>

### <a name="renaming-or-deleting-files"></a><span data-ttu-id="11a40-123">ファイル名の変更またはファイルの削除</span><span class="sxs-lookup"><span data-stu-id="11a40-123">Renaming or deleting files</span></span>

<span data-ttu-id="11a40-124">ファイル名を変更したり、ファイルを削除したりする場合は、PR にイシューを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="11a40-124">If you are renaming or deleting files, there must be an issue associated with the PR.</span></span> <span data-ttu-id="11a40-125">そのイシューでは、ファイルの名前変更または削除の必要性について話し合う必要があります。</span><span class="sxs-lookup"><span data-stu-id="11a40-125">That issue must discuss the need to rename or delete the files.</span></span>

<span data-ttu-id="11a40-126">コンテンツの追加または変更を、ファイル名の変更やファイルの削除と一緒にしないでください。</span><span class="sxs-lookup"><span data-stu-id="11a40-126">Avoid mixing content additions or change with file renames and deletes.</span></span> <span data-ttu-id="11a40-127">名前を変更したファイルまたは削除したファイルは、マスター リダイレクト ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11a40-127">Any file that is renamed or deleted must be added to the master redirection file.</span></span> <span data-ttu-id="11a40-128">可能であれば、名前を変更したコンテンツまたは削除したコンテンツにリンクするファイルも更新してください。</span><span class="sxs-lookup"><span data-stu-id="11a40-128">When possible, you should also update any files that link to the renamed or deleted content.</span></span> <span data-ttu-id="11a40-129">これには TOC ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="11a40-129">This includes any TOC files.</span></span>

## <a name="docs-pr-validation-service"></a><span data-ttu-id="11a40-130">Docs PR 検証サービス</span><span class="sxs-lookup"><span data-stu-id="11a40-130">Docs PR validation service</span></span>

<span data-ttu-id="11a40-131">Docs PR 検証サービスは、PR 内のファイルに対して検証ルールを実行する GitHub アプリです。</span><span class="sxs-lookup"><span data-stu-id="11a40-131">The Docs PR validation service is a GitHub app that runs validation rules on the files in a PR.</span></span> <span data-ttu-id="11a40-132">検証サービスによって報告されたエラーや警告 (例外を参照) は修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11a40-132">You must fix any errors or warnings (see exceptions) reported by the validation service.</span></span>

<span data-ttu-id="11a40-133">次の警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="11a40-133">The following warnings can be ignored:</span></span>

```
Can't find service name for `<version>/<modulepath>/About/About.md`
```

```
Metadata with following name(s) are not allowed to be set in Yaml header, or as file level
metadata in docfx.json, or as global metadata in docfx.json: `locale`. They are generated by
Docs platform, so the values set in these 3 places will be ignored. Please remove them from all
3 places to resolve the warning.
```

<span data-ttu-id="11a40-134">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="11a40-134">You'll see the following behavior:</span></span>

1. <span data-ttu-id="11a40-135">PR を送信します。</span><span class="sxs-lookup"><span data-stu-id="11a40-135">You submit a PR.</span></span>
1. <span data-ttu-id="11a40-136">PR の状態を示す GitHub コメント内に、リポジトリで有効になっている "チェック" の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11a40-136">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repository.</span></span> <span data-ttu-id="11a40-137">この例では、"Commit Validation" (コミットの検証) と "OpenPublishing.Build" の 2 つのチェックが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="11a40-137">Note that in this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![検証の状態 - 一部のチェックに失敗しました](media/pull-requests/validation-failed.png)

   <span data-ttu-id="11a40-139">コミットの検証に失敗した場合でも、ビルドは検証を通過できます。</span><span class="sxs-lookup"><span data-stu-id="11a40-139">The build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="11a40-140">**[詳細]** をクリックして、詳細情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="11a40-140">Click **Details** for more information.</span></span>
1. <span data-ttu-id="11a40-141">[詳細] ページには、失敗したすべての検証チェックと、問題を修正する方法に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11a40-141">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues.</span></span>
1. <span data-ttu-id="11a40-142">検証が成功すると、PR に次のコメントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="11a40-142">When validation succeeds, the following comment is added to the PR:</span></span>

   ![検証の状態: 成功](media/pull-requests/build-validation.png)

> [!NOTE]
> <span data-ttu-id="11a40-144">外部 (Microsoft の従業員以外) の共同作成者の場合、詳細なビルド レポートやプレビュー リンクにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="11a40-144">If you are an external (not a Microsoft employee) contributor you do not have access to the detailed build reports or preview links.</span></span>

<span data-ttu-id="11a40-145">PowerShell-Docs チームのメンバーによって PR がレビューされると、変更や、検証レポートでフラグが設定された問題の修正を求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="11a40-145">When the PR is reviewed by a member of the PowerShell-Docs team, you may be asked to make changes or fix problems flagged by the validation report.</span></span> <span data-ttu-id="11a40-146">PowerShell-Docs チームは、今後の送信に備えて、これらの問題を修正および回避する方法を理解できるよう支援します。</span><span class="sxs-lookup"><span data-stu-id="11a40-146">The PowerShell-Docs team can help you understand how to fix and avoid these problems for future submissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="11a40-147">次のステップ</span><span class="sxs-lookup"><span data-stu-id="11a40-147">Next steps</span></span>

[<span data-ttu-id="11a40-148">PowerShell-Docs スタイル ガイド</span><span class="sxs-lookup"><span data-stu-id="11a40-148">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)

## <a name="additional-resources"></a><span data-ttu-id="11a40-149">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="11a40-149">Additional resources</span></span>

[<span data-ttu-id="11a40-150">プル要求を管理する方法</span><span class="sxs-lookup"><span data-stu-id="11a40-150">How we manage pull requests</span></span>](managing-pull-requests.md)

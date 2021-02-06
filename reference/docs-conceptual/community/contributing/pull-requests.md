---
title: プル要求を送信する方法
description: この記事では、PowerShell-Docs リポジトリにプル要求を送信する方法について説明します。
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 1a21c25e19189aec4f48ad034147b02f4f804f9d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "99599690"
---
# <a name="how-to-submit-pull-requests"></a><span data-ttu-id="44f51-103">プル要求を送信する方法</span><span class="sxs-lookup"><span data-stu-id="44f51-103">How to submit pull requests</span></span>

<span data-ttu-id="44f51-104">コンテンツを変更するには、フォークからプル要求 (PR) を送信します。</span><span class="sxs-lookup"><span data-stu-id="44f51-104">To make changes to content, submit a pull request (PR) from your fork.</span></span> <span data-ttu-id="44f51-105">プル要求をマージする前に、レビューする必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f51-105">A pull request must be reviewed before it can be merged.</span></span> <span data-ttu-id="44f51-106">最良の結果を得るために、プル要求を送信する前に[編集チェックリスト](editorial-checklist.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="44f51-106">For best results, review the [editorial checklist](editorial-checklist.md) before submitting your pull request.</span></span>

## <a name="using-git-branches"></a><span data-ttu-id="44f51-107">Git ブランチの使用</span><span class="sxs-lookup"><span data-stu-id="44f51-107">Using git branches</span></span>

<span data-ttu-id="44f51-108">PowerShell-Docs の既定の分岐は `staging` 分岐です。</span><span class="sxs-lookup"><span data-stu-id="44f51-108">The default branch for PowerShell-Docs is the `staging` branch.</span></span> <span data-ttu-id="44f51-109">作業ブランチで行われた変更は、 `staging` 発行される前に分岐にマージされます。</span><span class="sxs-lookup"><span data-stu-id="44f51-109">Changes made in working branches are merged into the `staging` branch before then being published.</span></span> <span data-ttu-id="44f51-110">ブランチは、 `staging` `live` 平日の午後 3:00 (太平洋標準時) に分岐にマージされます。</span><span class="sxs-lookup"><span data-stu-id="44f51-110">The `staging` branch is merged into the `live` branch every weekday at 3:00 PM (Pacific Time).</span></span> <span data-ttu-id="44f51-111">この `live` 分岐には、docs.microsoft.com に公開されているコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44f51-111">The `live` branch contains the content that is published to docs.microsoft.com.</span></span>

<span data-ttu-id="44f51-112">変更を開始する前に、PowerShell-Docs リポジトリのローカルコピーに作業ブランチを作成します。</span><span class="sxs-lookup"><span data-stu-id="44f51-112">Before starting any changes, create a working branch in your local copy of the PowerShell-Docs repository.</span></span> <span data-ttu-id="44f51-113">ローカルで作業している場合は、作業ブランチを作成する前にローカルリポジトリを同期してください。</span><span class="sxs-lookup"><span data-stu-id="44f51-113">When working locally, be sure to synchronize your local repository before creating your working branch.</span></span> <span data-ttu-id="44f51-114">作業ブランチは、ブランチの更新後のコピーから作成する必要があり `staging` ます。</span><span class="sxs-lookup"><span data-stu-id="44f51-114">The working branch should be created from an update-to-date copy of the `staging` branch.</span></span>

<span data-ttu-id="44f51-115">すべてのプル要求は、`staging` ブランチをターゲットにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f51-115">All pull requests should target the `staging` branch.</span></span> <span data-ttu-id="44f51-116">ブランチに変更を送信しないで `live` ください。</span><span class="sxs-lookup"><span data-stu-id="44f51-116">Don't submit change to the `live` branch.</span></span>
<span data-ttu-id="44f51-117">`staging` ブランチで行われた変更が `live` にマージされ、`live` に対する変更が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="44f51-117">Changes made in the `staging` branch get merged into `live`, overwriting any changes made to `live`.</span></span>

## <a name="make-the-pull-request-process-work-better-for-everyone"></a><span data-ttu-id="44f51-118">プル要求プロセスをすべてのユーザーに対して効果的に機能させる</span><span class="sxs-lookup"><span data-stu-id="44f51-118">Make the pull request process work better for everyone</span></span>

<span data-ttu-id="44f51-119">PR をよりシンプルで焦点を絞ったものにすると、レビューとマージに要する時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="44f51-119">The simpler and more focused you can make your PR, the faster it can be reviewed and merged.</span></span>

### <a name="avoid-pull-requests-that-update-large-numbers-of-files-or-contain-unrelated-changes"></a><span data-ttu-id="44f51-120">大量のファイルを更新したり、関連のない変更を含むプル要求を回避する</span><span class="sxs-lookup"><span data-stu-id="44f51-120">Avoid pull requests that update large numbers of files or contain unrelated changes</span></span>

<span data-ttu-id="44f51-121">関連性のない変更を含む PR を作成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="44f51-121">Avoid creating PRs that contain unrelated changes.</span></span> <span data-ttu-id="44f51-122">既存の記事の軽微な更新は、新しい記事や大規模な改訂から切り離します。</span><span class="sxs-lookup"><span data-stu-id="44f51-122">Separate minor updates to existing articles from new articles or major rewrites.</span></span> <span data-ttu-id="44f51-123">このような変更には、別の作業ブランチで対応します。</span><span class="sxs-lookup"><span data-stu-id="44f51-123">Work on these changes in separate working branches.</span></span>

<span data-ttu-id="44f51-124">一括変更では、多数の変更されたファイルを含む PR が作成されます。</span><span class="sxs-lookup"><span data-stu-id="44f51-124">Bulk changes create PRs with large numbers of changed files.</span></span> <span data-ttu-id="44f51-125">PR の変更されたファイルを最大 50 個に制限します。</span><span class="sxs-lookup"><span data-stu-id="44f51-125">Limit your PRs to a maximum of 50 changed files.</span></span> <span data-ttu-id="44f51-126">大規模な PR はレビューするのが難しく、エラーを含む可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="44f51-126">Large PRs are difficult to review and are more prone to contain errors.</span></span>

### <a name="renaming-or-deleting-files"></a><span data-ttu-id="44f51-127">ファイル名の変更またはファイルの削除</span><span class="sxs-lookup"><span data-stu-id="44f51-127">Renaming or deleting files</span></span>

<span data-ttu-id="44f51-128">ファイルの名前を変更したり、ファイルを削除したりする場合は、PR に関連した問題が発生している必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f51-128">When renaming or deleting files, there must be an issue associated with the PR.</span></span> <span data-ttu-id="44f51-129">そのイシューでは、ファイルの名前変更または削除の必要性について話し合う必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f51-129">That issue must discuss the need to rename or delete the files.</span></span>

<span data-ttu-id="44f51-130">コンテンツの追加または変更を、ファイル名の変更やファイルの削除と一緒にしないでください。</span><span class="sxs-lookup"><span data-stu-id="44f51-130">Avoid mixing content additions or change with file renames and deletes.</span></span> <span data-ttu-id="44f51-131">名前を変更または削除したファイルは、グローバルリダイレクトファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f51-131">Any file that is renamed or deleted must be added to the global redirection file.</span></span> <span data-ttu-id="44f51-132">可能であれば、名前の変更または削除されたコンテンツ (TOC ファイルを含む) にリンクされているすべてのファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="44f51-132">When possible, update any files that link to the renamed or deleted content, including any TOC files.</span></span>

## <a name="docs-pr-validation-service"></a><span data-ttu-id="44f51-133">Docs PR 検証サービス</span><span class="sxs-lookup"><span data-stu-id="44f51-133">Docs PR validation service</span></span>

<span data-ttu-id="44f51-134">Docs PR 検証サービスは、変更に対して検証規則を実行する GitHub アプリです。</span><span class="sxs-lookup"><span data-stu-id="44f51-134">The Docs PR validation service is a GitHub app that runs validation rules on your changes.</span></span> <span data-ttu-id="44f51-135">検証サービスによって報告されたエラーまたは警告を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f51-135">You must fix any errors or warnings reported by the validation service.</span></span>

<span data-ttu-id="44f51-136">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44f51-136">You'll see the following behavior:</span></span>

1. <span data-ttu-id="44f51-137">PR を送信します。</span><span class="sxs-lookup"><span data-stu-id="44f51-137">You submit a PR.</span></span>
1. <span data-ttu-id="44f51-138">PR の状態を示す GitHub コメント内に、リポジトリで有効になっている "チェック" の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f51-138">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repository.</span></span> <span data-ttu-id="44f51-139">この例では、"コミットの検証" と "OpenPublishing. ビルド" の2つのチェックが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="44f51-139">In this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![検証の状態 - 一部のチェックに失敗しました](media/pull-requests/validation-failed.png)

   <span data-ttu-id="44f51-141">コミットの検証に失敗した場合でも、ビルドは検証を通過できます。</span><span class="sxs-lookup"><span data-stu-id="44f51-141">The build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="44f51-142">**[詳細]** をクリックして、詳細情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="44f51-142">Click **Details** for more information.</span></span>
1. <span data-ttu-id="44f51-143">[詳細] ページには、失敗したすべての検証チェックと、問題を修正する方法に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f51-143">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues.</span></span>
1. <span data-ttu-id="44f51-144">検証が成功すると、PR に次のコメントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="44f51-144">When validation succeeds, the following comment is added to the PR:</span></span>

   ![検証の状態: 成功](media/pull-requests/build-validation.png)

> [!NOTE]
> <span data-ttu-id="44f51-146">外部 (Microsoft の従業員以外) の共同作成者の場合、詳細なビルド レポートやプレビュー リンクにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="44f51-146">If you are an external (not a Microsoft employee) contributor you do not have access to the detailed build reports or preview links.</span></span>

<span data-ttu-id="44f51-147">PR を確認すると、変更を加えたり、検証警告メッセージを修正したりすることが求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="44f51-147">When the PR is reviewed, you may be asked to make changes or fix validation warning messages.</span></span> <span data-ttu-id="44f51-148">PowerShell-Docs チームは、検証エラーと編集要件を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="44f51-148">The PowerShell-Docs team can help you understand validation errors and editorial requirements.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44f51-149">次のステップ</span><span class="sxs-lookup"><span data-stu-id="44f51-149">Next steps</span></span>

[<span data-ttu-id="44f51-150">PowerShell-Docs スタイル ガイド</span><span class="sxs-lookup"><span data-stu-id="44f51-150">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)

## <a name="additional-resources"></a><span data-ttu-id="44f51-151">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="44f51-151">Additional resources</span></span>

[<span data-ttu-id="44f51-152">プル要求を管理する方法</span><span class="sxs-lookup"><span data-stu-id="44f51-152">How we manage pull requests</span></span>](managing-pull-requests.md)

<!--link refs-->
[fork]: /contribute/get-started-setup-local#fork-the-repository

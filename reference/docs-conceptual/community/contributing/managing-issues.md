---
title: イシューを管理する方法
description: この記事では、PowerShell-Docs チームがイシューを管理する方法について説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 56f0ea5b4c5c700db8fdd0b16e3ce1c4040a43dc
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354594"
---
# <a name="how-we-manage-issues"></a><span data-ttu-id="ad47d-103">イシューを管理する方法</span><span class="sxs-lookup"><span data-stu-id="ad47d-103">How we manage issues</span></span>

<span data-ttu-id="ad47d-104">この記事では、PowerShell-Docs リポジトリでイシューを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-104">This article documents how we manage issues in the PowerShell-Docs repo.</span></span> <span data-ttu-id="ad47d-105">この記事は、PowerShell-Docs チームのメンバーの作業を支援することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ad47d-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="ad47d-106">一般の共同作成者に対してプロセスを透明化するために、ここで公開されています。</span><span class="sxs-lookup"><span data-stu-id="ad47d-106">It is published here to provide process transparency for our public contributors.</span></span>

## <a name="sources-of-issues"></a><span data-ttu-id="ad47d-107">イシューのソース</span><span class="sxs-lookup"><span data-stu-id="ad47d-107">Sources of issues</span></span>

- <span data-ttu-id="ad47d-108">コミュニティの共同作成者</span><span class="sxs-lookup"><span data-stu-id="ad47d-108">Community contributors</span></span>
- <span data-ttu-id="ad47d-109">内部の共同作成者</span><span class="sxs-lookup"><span data-stu-id="ad47d-109">Internal contributors</span></span>
- <span data-ttu-id="ad47d-110">ソーシャル メディア チャネルからのコメントの転記</span><span class="sxs-lookup"><span data-stu-id="ad47d-110">Transcriptions of comments from social media channels</span></span>
- <span data-ttu-id="ad47d-111">ドキュメント フィードバック フォームによるフィードバック</span><span class="sxs-lookup"><span data-stu-id="ad47d-111">Feedback via the Docs feedback form</span></span>

## <a name="response-time-targets"></a><span data-ttu-id="ad47d-112">目標対応時間</span><span class="sxs-lookup"><span data-stu-id="ad47d-112">Response time targets</span></span>

- <span data-ttu-id="ad47d-113">トリアージ - 5 営業日</span><span class="sxs-lookup"><span data-stu-id="ad47d-113">Triaged - 5 business days</span></span>
- <span data-ttu-id="ad47d-114">修正または変更 - 具体的な目標なし - ベスト エフォートのみ</span><span class="sxs-lookup"><span data-stu-id="ad47d-114">Fix or change - no specific target - best effort only</span></span>

### <a name="labeling--milestones"></a><span data-ttu-id="ad47d-115">ラベル付けとマイルストーン</span><span class="sxs-lookup"><span data-stu-id="ad47d-115">Labeling & Milestones</span></span>

#### <a name="label-types"></a><span data-ttu-id="ad47d-116">ラベルの種類</span><span class="sxs-lookup"><span data-stu-id="ad47d-116">Label Types</span></span>

|<span data-ttu-id="ad47d-117">Prefix</span><span class="sxs-lookup"><span data-stu-id="ad47d-117">Prefix</span></span>  | <span data-ttu-id="ad47d-118">説明</span><span class="sxs-lookup"><span data-stu-id="ad47d-118">Description</span></span>                                                         |
|------- | --------------------------------------------------------------------|
|<span data-ttu-id="ad47d-119">領域</span><span class="sxs-lookup"><span data-stu-id="ad47d-119">Area</span></span>    | <span data-ttu-id="ad47d-120">イシューを議論する、PowerShell またはドキュメントの部分を示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-120">Used to indicate what part of PowerShell or the docs that the issue is discussing.</span></span><br><span data-ttu-id="ad47d-121">機能の所有者が機能に関するイシューを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad47d-121">Useful for feature owners to find issues for their feature.</span></span>|
|<span data-ttu-id="ad47d-122">Pri</span><span class="sxs-lookup"><span data-stu-id="ad47d-122">Pri</span></span>     | <span data-ttu-id="ad47d-123">イシューの優先度を示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-123">Used to indicate the priority of the issue.</span></span> <span data-ttu-id="ad47d-124">値の範囲は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="ad47d-124">Value range 0-4.</span></span>        |
|<span data-ttu-id="ad47d-125">問題</span><span class="sxs-lookup"><span data-stu-id="ad47d-125">Issue</span></span>   | <span data-ttu-id="ad47d-126">イシューのフィードバックの種類を分類するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-126">Used to classify the type of feedback for issue</span></span>                     |
|<span data-ttu-id="ad47d-127">確認</span><span class="sxs-lookup"><span data-stu-id="ad47d-127">Review</span></span>  | <span data-ttu-id="ad47d-128">チームがさらにレビューする必要があるイシューに使用します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-128">Used for issue that require further review by the team</span></span>              |
|<span data-ttu-id="ad47d-129">Status</span><span class="sxs-lookup"><span data-stu-id="ad47d-129">Status</span></span>  | <span data-ttu-id="ad47d-130">作業項目の状態を示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-130">Used to indicate the status of the work item</span></span>                        |
|<span data-ttu-id="ad47d-131">待機中</span><span class="sxs-lookup"><span data-stu-id="ad47d-131">Waiting</span></span> | <span data-ttu-id="ad47d-132">チームが何かを待機していることを示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-132">Used to indicate that we are waiting on something</span></span>                   |

#### <a name="milestones"></a><span data-ttu-id="ad47d-133">Milestones</span><span class="sxs-lookup"><span data-stu-id="ad47d-133">Milestones</span></span>

<span data-ttu-id="ad47d-134">イシューと PR は、適切なマイルストーンでタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad47d-134">Issues and PRs should be tagged with the appropriate milestone.</span></span> <span data-ttu-id="ad47d-135">イシューが特定のバージョンを対象としていない場合、マイルストーンは使用されません。</span><span class="sxs-lookup"><span data-stu-id="ad47d-135">If the issue is not targeted for a specific version then no milestone is used.</span></span> <span data-ttu-id="ad47d-136">PowerShell コード ベースにまだマージされていない変更に関するドキュメント PR のイシューは、 **Future** マイルストーンに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad47d-136">Issues for Docs PRs for changes that have yet to be merged into the PowerShell code base should be assigned to the **Future** milestone.</span></span> <span data-ttu-id="ad47d-137">コードの変更がマージされたら、マイルストーンを適切なバージョンに変更します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-137">After the code change has been merged, change the milestone to the appropriate version.</span></span>

|    <span data-ttu-id="ad47d-138">マイルストーン</span><span class="sxs-lookup"><span data-stu-id="ad47d-138">Milestone</span></span>     |                    <span data-ttu-id="ad47d-139">説明</span><span class="sxs-lookup"><span data-stu-id="ad47d-139">Description</span></span>                     |
| ---------------- | -------------------------------------------------- |
| <span data-ttu-id="ad47d-140">6.x</span><span class="sxs-lookup"><span data-stu-id="ad47d-140">6.x</span></span>              | <span data-ttu-id="ad47d-141">PowerShell 6.0 から 6.2.x に関連する作業項目</span><span class="sxs-lookup"><span data-stu-id="ad47d-141">Work items related to PowerShell 6.0 through 6.2.x</span></span> |
| <span data-ttu-id="ad47d-142">7.0.0</span><span class="sxs-lookup"><span data-stu-id="ad47d-142">7.0.0</span></span>            | <span data-ttu-id="ad47d-143">PowerShell 7.0 に関連する作業項目</span><span class="sxs-lookup"><span data-stu-id="ad47d-143">Work items related to PowerShell 7.0</span></span>               |
| <span data-ttu-id="ad47d-144">7.1.0</span><span class="sxs-lookup"><span data-stu-id="ad47d-144">7.1.0</span></span>            | <span data-ttu-id="ad47d-145">PowerShell 7.1 に関連する作業項目</span><span class="sxs-lookup"><span data-stu-id="ad47d-145">Work items related to PowerShell 7.1</span></span>               |
| <span data-ttu-id="ad47d-146">予定</span><span class="sxs-lookup"><span data-stu-id="ad47d-146">Future</span></span>           | <span data-ttu-id="ad47d-147">将来のバージョンの PowerShell の作業項目</span><span class="sxs-lookup"><span data-stu-id="ad47d-147">Work items a future version of PowerShell</span></span>          |
| <span data-ttu-id="ad47d-148">PSReadline-vNext</span><span class="sxs-lookup"><span data-stu-id="ad47d-148">PSReadline-vNext</span></span> | <span data-ttu-id="ad47d-149">将来のバージョンの PSReadline の作業項目</span><span class="sxs-lookup"><span data-stu-id="ad47d-149">Work items a future version of PSReadline</span></span>          |

## <a name="triage-process"></a><span data-ttu-id="ad47d-150">トリアージ プロセス</span><span class="sxs-lookup"><span data-stu-id="ad47d-150">Triage process</span></span>

<span data-ttu-id="ad47d-151">PowerShell ドキュメント チームは、週に 1 回集まって、前回の会議以降に追加されたイシューについて話し合います。</span><span class="sxs-lookup"><span data-stu-id="ad47d-151">The PowerShell docs team meets once per week to discuss any issues added since last meeting.</span></span> <span data-ttu-id="ad47d-152">ラベルが割り当てられたとき、または所有者が割り当てられたときに、イシューはトリアージされたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="ad47d-152">An issue is considered to have been triaged when labels have been assigned or an owner has been assigned.</span></span> <span data-ttu-id="ad47d-153">PowerShell ドキュメント チームのメンバーには、イシューを毎日レビューし、新たに報告されたイシューをトリアージすることが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="ad47d-153">PowerShell docs team members are encouraged to review the issues daily and triage new issues as they arrive.</span></span> <span data-ttu-id="ad47d-154">必要に応じて、週 1 回のトリアージ会議を利用して、新しいイシューについてさらに詳しく話し合うこともできます。</span><span class="sxs-lookup"><span data-stu-id="ad47d-154">The weekly triage meeting can then be used to discuss the new issues in more detail, as needed.</span></span>

### <a name="misplaced-product-feedback"></a><span data-ttu-id="ad47d-155">間違って送られた製品フィードバック</span><span class="sxs-lookup"><span data-stu-id="ad47d-155">Misplaced product feedback</span></span>

- <span data-ttu-id="ad47d-156">その顧客に対して、製品フィードバックであることを示すコメントを入力し、適切なフィードバック チャネルへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-156">Enter a comment for the customer indicating it is product feedback and provide a link to the appropriate feedback channel.</span></span>
- <span data-ttu-id="ad47d-157">省略可能:イシューを適切な製品フィードバックの場所にコピーし、コピーした項目へのリンクを追加して、イシューを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ad47d-157">Optional: Copy the issue to the appropriate product feedback location, add a link to the copied item, and close the issue.</span></span> <span data-ttu-id="ad47d-158">イシューを UserVoice にコピーしないでください。</span><span class="sxs-lookup"><span data-stu-id="ad47d-158">DO NOT copy issues to UserVoice.</span></span>

  | <span data-ttu-id="ad47d-159">ドキュメント セット</span><span class="sxs-lookup"><span data-stu-id="ad47d-159">DocSet</span></span>    | <span data-ttu-id="ad47d-160">製品フィードバックの URL</span><span class="sxs-lookup"><span data-stu-id="ad47d-160">Product Feedback URL</span></span>                                           |
  | --------- | -------------------------------------------------------------- |
  | <span data-ttu-id="ad47d-161">developer</span><span class="sxs-lookup"><span data-stu-id="ad47d-161">developer</span></span> | `https://github.com/PowerShell/PowerShell/issues/new/choose`   |
  | <span data-ttu-id="ad47d-162">dsc</span><span class="sxs-lookup"><span data-stu-id="ad47d-162">dsc</span></span>       | `https://windowsserver.uservoice.com/forums/301869-powershell` |
  | <span data-ttu-id="ad47d-163">ギャラリー</span><span class="sxs-lookup"><span data-stu-id="ad47d-163">gallery</span></span>   | `https://github.com/powershell/powershellgallery/issues/new`   |
  | <span data-ttu-id="ad47d-164">jea</span><span class="sxs-lookup"><span data-stu-id="ad47d-164">jea</span></span>       | `https://github.com/powershell/jea/issues/new`                 |
  | <span data-ttu-id="ad47d-165">reference</span><span class="sxs-lookup"><span data-stu-id="ad47d-165">reference</span></span> | `https://github.com/PowerShell/PowerShell/issues/new/choose`   |
  | <span data-ttu-id="ad47d-166">wmf</span><span class="sxs-lookup"><span data-stu-id="ad47d-166">wmf</span></span>       | `https://windowsserver.uservoice.com/forums/301869-powershell` |

### <a name="support-requests"></a><span data-ttu-id="ad47d-167">サポート要求</span><span class="sxs-lookup"><span data-stu-id="ad47d-167">Support requests</span></span>

- <span data-ttu-id="ad47d-168">サポートに関する質問が単純な場合は、質問に丁寧に答えてイシューを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ad47d-168">If the support question is simple, answer it politely and close the issue.</span></span>
- <span data-ttu-id="ad47d-169">質問が複雑な場合や、送信者からさらに多くの質問が返ってきた場合は、フォーラムおよびサポート チャネルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="ad47d-169">If the question is more complicated, or the submitter replies with more questions, redirect them to forums and support channels.</span></span> <span data-ttu-id="ad47d-170">フォーラムにリダイレクトする際の推奨されるテキストは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad47d-170">Suggested text for redirecting to forums:</span></span>

  ```Markdown
  > This is not the right forum for these kinds of questions. Try posting your question in a
  > community support forum. For a list of community forums see:
  > https://docs.microsoft.com/powershell/scripting/community/community-support
  ```

### <a name="code-of-conduct-violations"></a><span data-ttu-id="ad47d-171">行動規範違反</span><span class="sxs-lookup"><span data-stu-id="ad47d-171">Code of conduct violations</span></span>

- <span data-ttu-id="ad47d-172">必要に応じて、イシューを編集し、不快感を与えるコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="ad47d-172">Edit the issue to remove any offensive content, if necessary.</span></span>
- <span data-ttu-id="ad47d-173">そのイシューがスパムであることを示すコメントを入力し、イシューを閉じ、それ以上コメントできないようにロックします。</span><span class="sxs-lookup"><span data-stu-id="ad47d-173">Enter a comment indicating the issue is spam, close the issue, and then lock it to prevent further comments.</span></span>
- <span data-ttu-id="ad47d-174">これが発生するたびに、毎週のトリアージで話し合って、さらなる措置 (GitHub または Microsoft 法務部への報告) の必要性を判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad47d-174">Each occurrence of this should be discussed in the weekly triage to determine the need for further action (report to GitHub or Microsoft Legal).</span></span>

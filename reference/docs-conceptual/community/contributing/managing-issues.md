---
title: イシューを管理する方法
description: この記事では、PowerShell-Docs チームがイシューを管理する方法について説明します。
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 72267137a2657f51e5f616113adf92d80647acad
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "99602165"
---
# <a name="how-we-manage-issues"></a><span data-ttu-id="41c8c-103">イシューを管理する方法</span><span class="sxs-lookup"><span data-stu-id="41c8c-103">How we manage issues</span></span>

<span data-ttu-id="41c8c-104">この記事では、PowerShell-Docs リポジトリでイシューを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-104">This article documents how we manage issues in the PowerShell-Docs repo.</span></span> <span data-ttu-id="41c8c-105">この記事は、PowerShell-Docs チームのメンバーの作業を支援することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="41c8c-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="41c8c-106">ここで公開されているので、パブリックコントリビューターのプロセスの透明性を提供します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-106">It's published here to provide process transparency for our public contributors.</span></span>

## <a name="sources-of-issues"></a><span data-ttu-id="41c8c-107">イシューのソース</span><span class="sxs-lookup"><span data-stu-id="41c8c-107">Sources of issues</span></span>

- <span data-ttu-id="41c8c-108">コミュニティの共同作成者</span><span class="sxs-lookup"><span data-stu-id="41c8c-108">Community contributors</span></span>
- <span data-ttu-id="41c8c-109">内部の共同作成者</span><span class="sxs-lookup"><span data-stu-id="41c8c-109">Internal contributors</span></span>
- <span data-ttu-id="41c8c-110">ソーシャル メディア チャネルからのコメントの転記</span><span class="sxs-lookup"><span data-stu-id="41c8c-110">Transcriptions of comments from social media channels</span></span>
- <span data-ttu-id="41c8c-111">ドキュメント フィードバック フォームによるフィードバック</span><span class="sxs-lookup"><span data-stu-id="41c8c-111">Feedback via the Docs feedback form</span></span>

## <a name="response-time-targets"></a><span data-ttu-id="41c8c-112">目標対応時間</span><span class="sxs-lookup"><span data-stu-id="41c8c-112">Response time targets</span></span>

<span data-ttu-id="41c8c-113">新しい問題の80% は、3営業日以内に終了します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-113">80% of new issues are closed within 3 business days.</span></span>

- <span data-ttu-id="41c8c-114">トリアージ済み-1 営業日以内</span><span class="sxs-lookup"><span data-stu-id="41c8c-114">Triaged - 1 business days</span></span>
- <span data-ttu-id="41c8c-115">10営業日以内の修正または変更</span><span class="sxs-lookup"><span data-stu-id="41c8c-115">Fix or change - 10 business days</span></span>

### <a name="labeling--milestones"></a><span data-ttu-id="41c8c-116">ラベル付けとマイルストーン</span><span class="sxs-lookup"><span data-stu-id="41c8c-116">Labeling & Milestones</span></span>

#### <a name="label-types"></a><span data-ttu-id="41c8c-117">ラベルの種類</span><span class="sxs-lookup"><span data-stu-id="41c8c-117">Label Types</span></span>

|   <span data-ttu-id="41c8c-118">Type</span><span class="sxs-lookup"><span data-stu-id="41c8c-118">Type</span></span>   | <span data-ttu-id="41c8c-119">説明</span><span class="sxs-lookup"><span data-stu-id="41c8c-119">Description</span></span>                                                         |
| -------- | ------------------------------------------------------------------- |
| <span data-ttu-id="41c8c-120">領域</span><span class="sxs-lookup"><span data-stu-id="41c8c-120">Area</span></span>     | <span data-ttu-id="41c8c-121">イシューを議論する、PowerShell またはドキュメントの部分を示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-121">Used to indicate what part of PowerShell or the docs that the issue is discussing.</span></span><br><span data-ttu-id="41c8c-122">機能の所有者が機能に関するイシューを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41c8c-122">Useful for feature owners to find issues for their feature.</span></span> |
| <span data-ttu-id="41c8c-123">問題</span><span class="sxs-lookup"><span data-stu-id="41c8c-123">Issue</span></span>    | <span data-ttu-id="41c8c-124">問題の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-124">Indicates the type of issue</span></span>                                         |
| <span data-ttu-id="41c8c-125">優先度</span><span class="sxs-lookup"><span data-stu-id="41c8c-125">Priority</span></span> | <span data-ttu-id="41c8c-126">問題の優先度を示します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-126">Indicates the priority of the issue.</span></span> <span data-ttu-id="41c8c-127">値の範囲 0 (高)-4 (低)</span><span class="sxs-lookup"><span data-stu-id="41c8c-127">Value range 0 (high) -4 (low)</span></span>  |
| <span data-ttu-id="41c8c-128">Status</span><span class="sxs-lookup"><span data-stu-id="41c8c-128">Status</span></span>   | <span data-ttu-id="41c8c-129">作業項目の状態または作業項目が閉じられた理由を示します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-129">Indicates the status of the work item or why it was closed</span></span>          |
| <span data-ttu-id="41c8c-130">タグ</span><span class="sxs-lookup"><span data-stu-id="41c8c-130">Tag</span></span>      | <span data-ttu-id="41c8c-131">追加の分類のためにに使用されるラベル</span><span class="sxs-lookup"><span data-stu-id="41c8c-131">Labels used to for additional classification</span></span>                        |
| <span data-ttu-id="41c8c-132">待機中</span><span class="sxs-lookup"><span data-stu-id="41c8c-132">Waiting</span></span>  | <span data-ttu-id="41c8c-133">他のイベントまたは他のイベントで待機していることを示します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-133">Indicates that we're waiting on someone or some other event</span></span>         |

#### <a name="milestones"></a><span data-ttu-id="41c8c-134">Milestones</span><span class="sxs-lookup"><span data-stu-id="41c8c-134">Milestones</span></span>

<span data-ttu-id="41c8c-135">イシューと PR は、適切なマイルストーンでタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41c8c-135">Issues and PRs should be tagged with the appropriate milestone.</span></span> <span data-ttu-id="41c8c-136">問題が特定のバージョンに適用されない場合、マイルストーンは使用されません。</span><span class="sxs-lookup"><span data-stu-id="41c8c-136">If the issue doesn't apply to a specific version, then no milestone is used.</span></span> <span data-ttu-id="41c8c-137">PowerShell コードベースにまだマージされていない変更に関する Pr および関連する問題は、 **今後** のマイルストーンに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="41c8c-137">PRs and related issues for changes that have yet to be merged into the PowerShell code base should be assigned to the **Future** milestone.</span></span> <span data-ttu-id="41c8c-138">コードの変更がマージされたら、マイルストーンを適切なバージョンに変更します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-138">After the code change has been merged, change the milestone to the appropriate version.</span></span>

|    <span data-ttu-id="41c8c-139">マイルストーン</span><span class="sxs-lookup"><span data-stu-id="41c8c-139">Milestone</span></span>     |                    <span data-ttu-id="41c8c-140">説明</span><span class="sxs-lookup"><span data-stu-id="41c8c-140">Description</span></span>                     |
| ---------------- | -------------------------------------------------- |
| <span data-ttu-id="41c8c-141">7.0.0</span><span class="sxs-lookup"><span data-stu-id="41c8c-141">7.0.0</span></span>            | <span data-ttu-id="41c8c-142">PowerShell 7.0 に関連する作業項目</span><span class="sxs-lookup"><span data-stu-id="41c8c-142">Work items related to PowerShell 7.0</span></span>               |
| <span data-ttu-id="41c8c-143">7.1.0</span><span class="sxs-lookup"><span data-stu-id="41c8c-143">7.1.0</span></span>            | <span data-ttu-id="41c8c-144">PowerShell 7.1 に関連する作業項目</span><span class="sxs-lookup"><span data-stu-id="41c8c-144">Work items related to PowerShell 7.1</span></span>               |
| <span data-ttu-id="41c8c-145">7.2.0</span><span class="sxs-lookup"><span data-stu-id="41c8c-145">7.2.0</span></span>            | <span data-ttu-id="41c8c-146">PowerShell 7.2 に関連する作業項目</span><span class="sxs-lookup"><span data-stu-id="41c8c-146">Work items related to PowerShell 7.2</span></span>               |
| <span data-ttu-id="41c8c-147">予定</span><span class="sxs-lookup"><span data-stu-id="41c8c-147">Future</span></span>           | <span data-ttu-id="41c8c-148">将来のバージョンの PowerShell の作業項目</span><span class="sxs-lookup"><span data-stu-id="41c8c-148">Work items a future version of PowerShell</span></span>          |

## <a name="triage-process"></a><span data-ttu-id="41c8c-149">トリアージ プロセス</span><span class="sxs-lookup"><span data-stu-id="41c8c-149">Triage process</span></span>

<span data-ttu-id="41c8c-150">PowerShell docs チームメンバーは、問題を毎日確認し、新しい問題が発生したときにトリアージします。</span><span class="sxs-lookup"><span data-stu-id="41c8c-150">PowerShell docs team members review the issues daily and triage new issues as they arrive.</span></span> <span data-ttu-id="41c8c-151">チームは週に1回、トリアージが必要な問題、または未解決のままの問題について話し合います。</span><span class="sxs-lookup"><span data-stu-id="41c8c-151">The team meets weekly to discuss issues that need triage or remain unresolved.</span></span>

### <a name="misplaced-product-feedback"></a><span data-ttu-id="41c8c-152">間違って送られた製品フィードバック</span><span class="sxs-lookup"><span data-stu-id="41c8c-152">Misplaced product feedback</span></span>

- <span data-ttu-id="41c8c-153">顧客を正しいフィードバックチャネルにリダイレクトするコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-153">Enter a comment redirecting the customer to the correct feedback channel.</span></span>
- <span data-ttu-id="41c8c-154">省略可能:イシューを適切な製品フィードバックの場所にコピーし、コピーした項目へのリンクを追加して、イシューを閉じます。</span><span class="sxs-lookup"><span data-stu-id="41c8c-154">Optional: Copy the issue to the appropriate product feedback location, add a link to the copied item, and close the issue.</span></span> <span data-ttu-id="41c8c-155">イシューを UserVoice にコピーしないでください。</span><span class="sxs-lookup"><span data-stu-id="41c8c-155">DO NOT copy issues to UserVoice.</span></span>

  <span data-ttu-id="41c8c-156">PowerShell の問題の既定の場所は [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose) です。</span><span class="sxs-lookup"><span data-stu-id="41c8c-156">The default location for PowerShell issues is [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

  <span data-ttu-id="41c8c-157">次のサブジェクト領域には、さまざまな問題があります。</span><span class="sxs-lookup"><span data-stu-id="41c8c-157">The following subject areas have different locations for issues:</span></span>

  | <span data-ttu-id="41c8c-158">件名</span><span class="sxs-lookup"><span data-stu-id="41c8c-158">Subjects</span></span> |                                                     <span data-ttu-id="41c8c-159">製品フィードバックの URL</span><span class="sxs-lookup"><span data-stu-id="41c8c-159">Product Feedback URL</span></span>                                                     |
  | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
  | <span data-ttu-id="41c8c-160">dsc</span><span class="sxs-lookup"><span data-stu-id="41c8c-160">dsc</span></span>      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |
  | <span data-ttu-id="41c8c-161">ギャラリー</span><span class="sxs-lookup"><span data-stu-id="41c8c-161">gallery</span></span>  | [https://github.com/powershell/powershellgallery/issues/new](https://github.com/powershell/powershellgallery/issues/new)     |
  | <span data-ttu-id="41c8c-162">jea</span><span class="sxs-lookup"><span data-stu-id="41c8c-162">jea</span></span>      | [https://github.com/powershell/jea/issues/new](https://github.com/powershell/jea/issues/new)                                 |
  | <span data-ttu-id="41c8c-163">wmf</span><span class="sxs-lookup"><span data-stu-id="41c8c-163">wmf</span></span>      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |

### <a name="support-requests"></a><span data-ttu-id="41c8c-164">サポート要求</span><span class="sxs-lookup"><span data-stu-id="41c8c-164">Support requests</span></span>

- <span data-ttu-id="41c8c-165">サポートに関する質問が単純な場合は、質問に丁寧に答えてイシューを閉じます。</span><span class="sxs-lookup"><span data-stu-id="41c8c-165">If the support question is simple, answer it politely and close the issue.</span></span>
- <span data-ttu-id="41c8c-166">質問が複雑な場合や、送信者からさらに多くの質問が返ってきた場合は、フォーラムおよびサポート チャネルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="41c8c-166">If the question is more complicated, or the submitter replies with more questions, redirect them to forums and support channels.</span></span> <span data-ttu-id="41c8c-167">フォーラムにリダイレクトする際の推奨されるテキストは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="41c8c-167">Suggested text for redirecting to forums:</span></span>

  ```Markdown
  > This is not the right forum for these kinds of questions. Try posting your question in a
  > community support forum. For a list of community forums see:
  > https://docs.microsoft.com/powershell/scripting/community/community-support
  ```

### <a name="code-of-conduct-violations"></a><span data-ttu-id="41c8c-168">行動規範違反</span><span class="sxs-lookup"><span data-stu-id="41c8c-168">Code of conduct violations</span></span>

- <span data-ttu-id="41c8c-169">必要に応じて、イシューを編集し、不快感を与えるコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="41c8c-169">Edit the issue to remove any offensive content, if necessary.</span></span>
- <span data-ttu-id="41c8c-170">そのイシューがスパムであることを示すコメントを入力し、イシューを閉じ、それ以上コメントできないようにロックします。</span><span class="sxs-lookup"><span data-stu-id="41c8c-170">Enter a comment indicating the issue is spam, close the issue, and then lock it to prevent further comments.</span></span>
- <span data-ttu-id="41c8c-171">各違反については、週次のトリアージで説明し、さらにアクションを実行する必要があるかどうかを判断する必要があります (GitHub または Microsoft 法務への報告)。</span><span class="sxs-lookup"><span data-stu-id="41c8c-171">Each violation should be discussed in the weekly triage to determine the need for further action (report to GitHub or Microsoft Legal).</span></span>

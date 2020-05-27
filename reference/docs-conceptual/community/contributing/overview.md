---
title: PowerShell ドキュメントへの投稿
description: この記事では、PowerShell ドキュメントの共同作成者として作業を開始する方法の概要を説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 5f9efbff500b1fd0c11e9b43ca0a7feb77684c6a
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560663"
---
# <a name="contributing-to-powershell-documentation"></a><span data-ttu-id="df202-103">PowerShell ドキュメントへの投稿</span><span class="sxs-lookup"><span data-stu-id="df202-103">Contributing to PowerShell documentation</span></span>

<span data-ttu-id="df202-104">PowerShell のサポートにご協力いただき、ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="df202-104">Thank you for your support of PowerShell!</span></span>

<span data-ttu-id="df202-105">共同作成者ガイドは、Microsoft でドキュメントを作成するために使用するツールとプロセスについて説明する記事のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="df202-105">The Contributor's Guide is a collection of articles that explain the tools and processes we use to create documentation at Microsoft.</span></span> <span data-ttu-id="df202-106">これらのガイドの一部では、[docs.microsoft.com][docs] に公開されているすべてのドキュメント セットに共通する情報について説明しています。</span><span class="sxs-lookup"><span data-stu-id="df202-106">Some of these guides cover information that is common to any documentation set published to [docs.microsoft.com][docs].</span></span> <span data-ttu-id="df202-107">ガイドの一部は、PowerShell のドキュメントを記述する方法に特有のものです。</span><span class="sxs-lookup"><span data-stu-id="df202-107">Some of the guides are specific to how we write documentation for PowerShell.</span></span>

<span data-ttu-id="df202-108">一般的な記事については、一元管理された[共同作成者ガイド][contribute]で確認できます。</span><span class="sxs-lookup"><span data-stu-id="df202-108">The common articles are available in our centralized [Contributor's Guide][contribute].</span></span> <span data-ttu-id="df202-109">PowerShell 固有のガイドは、ここで参照できます。</span><span class="sxs-lookup"><span data-stu-id="df202-109">The PowerShell-specific guides are available here.</span></span>

## <a name="ways-to-contribute"></a><span data-ttu-id="df202-110">作成協力の方法</span><span class="sxs-lookup"><span data-stu-id="df202-110">Ways to contribute</span></span>

<span data-ttu-id="df202-111">投稿するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="df202-111">There are two ways to contribute.</span></span> <span data-ttu-id="df202-112">どちらの方法も、Microsoft にとって価値があります。</span><span class="sxs-lookup"><span data-stu-id="df202-112">Both contributions are valuable to us.</span></span>

- <span data-ttu-id="df202-113">[イシューの報告][file-an-issue]により、Microsoft は弊社のドキュメントの問題や矛盾点を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="df202-113">[Filing issues][file-an-issue] helps us identify problems and gaps in our documentation.</span></span> <span data-ttu-id="df202-114">場合によっては、イシューは解決が難しく、調査がさらに必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="df202-114">Sometimes the issues are difficult to resolve, requiring more investigation and research.</span></span> <span data-ttu-id="df202-115">イシューのプロセスにより、私たちは問題について会話し、十分な解決策を策定することができます。</span><span class="sxs-lookup"><span data-stu-id="df202-115">The issue process allows us to have a conversation about the problem and develop a satisfactory resolution.</span></span>

- <span data-ttu-id="df202-116">新しいコンテンツや変更を既存の記事に送信することは、より複雑なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="df202-116">Submitting new content or changes to existing articles is a more involved process.</span></span> <span data-ttu-id="df202-117">次の情報では、ドキュメントにコンテンツを送信するためのツール、プロセス、基準について説明します。</span><span class="sxs-lookup"><span data-stu-id="df202-117">The following information outlines the tools, processes, and standards for submitting content to the documentation.</span></span>

## <a name="prepare-to-make-a-contribution"></a><span data-ttu-id="df202-118">投稿するための準備</span><span class="sxs-lookup"><span data-stu-id="df202-118">Prepare to make a contribution</span></span>

<span data-ttu-id="df202-119">ドキュメントの共同作成には、GitHub アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="df202-119">Contributing to the documentation requires a GitHub account.</span></span> <span data-ttu-id="df202-120">次のチェックリストを使用して、ツールを入手し、投稿の作成について Microsoft が採用しているプロセスを理解できます。</span><span class="sxs-lookup"><span data-stu-id="df202-120">Use the following checklist to get the tools and understand the processes we use for making contributions.</span></span>

1. [<span data-ttu-id="df202-121">GitHub にサインアップします</span><span class="sxs-lookup"><span data-stu-id="df202-121">Sign up for GitHub</span></span>](/contribute/get-started-setup-github)
1. [<span data-ttu-id="df202-122">Git ツールと Markdown ツールをインストールします</span><span class="sxs-lookup"><span data-stu-id="df202-122">Install Git and Markdown tools</span></span>](/contribute/get-started-setup-tools)
1. [<span data-ttu-id="df202-123">Docs Authoring パックをインストールします</span><span class="sxs-lookup"><span data-stu-id="df202-123">Install the Docs Authoring Pack</span></span>](/contribute/how-to-write-docs-auth-pack)
1. <span data-ttu-id="df202-124">[Posh-Git をインストールします][posh-git] (推奨されますが、必須ではありません)</span><span class="sxs-lookup"><span data-stu-id="df202-124">[Install Posh-Git][posh-git] - not required but recommended</span></span>
1. [<span data-ttu-id="df202-125">ローカル Git リポジトリを設定します</span><span class="sxs-lookup"><span data-stu-id="df202-125">Set up a local Git repository</span></span>](/contribute/get-started-setup-local)
1. [<span data-ttu-id="df202-126">Git と GitHub の基礎を確認します</span><span class="sxs-lookup"><span data-stu-id="df202-126">Review Git and GitHub fundamentals</span></span>](/contribute/git-github-fundamentals)

## <a name="get-started-writing-docs"></a><span data-ttu-id="df202-127">ドキュメントの作成を開始する</span><span class="sxs-lookup"><span data-stu-id="df202-127">Get started writing docs</span></span>

<span data-ttu-id="df202-128">ドキュメントに変更を加えるには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="df202-128">There are two ways to contribute changes to the documentation:</span></span>

1. [<span data-ttu-id="df202-129">既存のドキュメントへのクイック編集</span><span class="sxs-lookup"><span data-stu-id="df202-129">Quick edits to existing docs</span></span>](/contribute/#quick-edits-to-existing-documents)
   - <span data-ttu-id="df202-130">軽微な修正、誤字の修正、または小さな追加</span><span class="sxs-lookup"><span data-stu-id="df202-130">Minor corrections, fixing typos, or small additions</span></span>
1. [<span data-ttu-id="df202-131">ドキュメント用の完全な GitHub ワークフロー</span><span class="sxs-lookup"><span data-stu-id="df202-131">Full GitHub workflow for docs</span></span>](/contribute/how-to-write-workflows-major)
   - <span data-ttu-id="df202-132">大きな変更、複数のバージョン、画像の追加または変更、または新しい記事の投稿</span><span class="sxs-lookup"><span data-stu-id="df202-132">large changes, multiple versions, adding or changing images, or contributing new articles</span></span>

<span data-ttu-id="df202-133">また、一元化された共同作成者ガイドの「[書き込みの要点](/contribute/style-quick-start)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="df202-133">Also, read the [Writing essentials](/contribute/style-quick-start) section of the centralized Contributor's Guide.</span></span> <span data-ttu-id="df202-134">もう 1 つの優れたリソースは、[Microsoft ライティング スタイル ガイド][style-guide]です。</span><span class="sxs-lookup"><span data-stu-id="df202-134">Another excellent resource is the [Microsoft Writing Style Guide][style-guide].</span></span> <span data-ttu-id="df202-135">Microsoft ライティング スタイル ガイドの目的は、エディター、テクニカル ライター、開発者、マーケティング担当者など IT に関するすべての人の記述するコンテンツを向上させることです。</span><span class="sxs-lookup"><span data-stu-id="df202-135">The goal of the Microsoft Writing Style Guide is to help editors, technical writers, developers, marketers, and anyone else in IT write better content.</span></span>

<span data-ttu-id="df202-136">パブリック リポジトリに含まれているドキュメントとコード例に対する軽微な修正や明確化は、[docs.microsoft.com の使用条件][terms-of-use]の対象になります。</span><span class="sxs-lookup"><span data-stu-id="df202-136">Minor corrections or clarifications to documentation and code examples in public repositories are covered by the docs.microsoft.com [Terms of Use][terms-of-use].</span></span>

<span data-ttu-id="df202-137">重要な変更を行う場合は、完全な GitHub ワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="df202-137">Use the full GitHub workflow when you're making significant changes.</span></span> <span data-ttu-id="df202-138">Microsoft の従業員でない場合は、重要な変更によって、オンラインの [Contribution Licensing Agreement (CLA)][cla] を送信するように求めるコメントがプル要求に生成されます。</span><span class="sxs-lookup"><span data-stu-id="df202-138">If you're not an employee of Microsoft, significant changes generate a comment in the pull request that asks you to submit an online [Contribution Licensing Agreement (CLA)][cla].</span></span> <span data-ttu-id="df202-139">プル要求が正しく確認され受理されるように、オンライン フォームへのご記入をお願いいたします。</span><span class="sxs-lookup"><span data-stu-id="df202-139">We need you to complete the online form before we can review or accept your pull request.</span></span>

## <a name="code-of-conduct"></a><span data-ttu-id="df202-140">倫理規定</span><span class="sxs-lookup"><span data-stu-id="df202-140">Code of conduct</span></span>

<span data-ttu-id="df202-141">docs.microsoft.com に公開されるすべてのリポジトリには、「[Microsoft オープン ソース倫理規定](https://opensource.microsoft.com/codeofconduct/)」または「[.NET Foundation 倫理規定](https://dotnetfoundation.org/code-of-conduct)」が適用されます。</span><span class="sxs-lookup"><span data-stu-id="df202-141">All repositories that publish to docs.microsoft.com have adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/) or the [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct).</span></span> <span data-ttu-id="df202-142">詳細については、[倫理規定に関する FAQ](https://opensource.microsoft.com/codeofconduct/faq/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df202-142">For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="df202-143">次のステップ</span><span class="sxs-lookup"><span data-stu-id="df202-143">Next steps</span></span>

<span data-ttu-id="df202-144">次の記事では、PowerShell ドキュメントに固有の情報を紹介します。</span><span class="sxs-lookup"><span data-stu-id="df202-144">The following articles cover information specific to PowerShell documentation.</span></span> <span data-ttu-id="df202-145">一元化された共同作成者ガイドのガイダンスと重複している箇所については、それらの規則が PowerShell コンテンツの場合ではどのように異なるかについて示しています。</span><span class="sxs-lookup"><span data-stu-id="df202-145">Where there's overlap with the guidance in the centralized Contributor's Guide, we call out how those rules differ for the PowerShell content.</span></span>

<span data-ttu-id="df202-146">以下のドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="df202-146">Review the following documents:</span></span>

- [<span data-ttu-id="df202-147">イシューを報告する方法</span><span class="sxs-lookup"><span data-stu-id="df202-147">How to file an issue</span></span>](file-an-issue.md)
- [<span data-ttu-id="df202-148">ドキュメントの作成を開始する</span><span class="sxs-lookup"><span data-stu-id="df202-148">Get started writing docs</span></span>](get-started-writing.md)
- [<span data-ttu-id="df202-149">プル要求の送信</span><span class="sxs-lookup"><span data-stu-id="df202-149">Submitting a pull request</span></span>](pull-requests.md)
- [<span data-ttu-id="df202-150">PowerShell ドキュメントのスタイル ガイド</span><span class="sxs-lookup"><span data-stu-id="df202-150">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)
- [<span data-ttu-id="df202-151">コマンドレット リファレンスの編集</span><span class="sxs-lookup"><span data-stu-id="df202-151">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<span data-ttu-id="df202-152">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="df202-152">Additional resources</span></span>

- [<span data-ttu-id="df202-153">編集のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="df202-153">Editorial checklist</span></span>](editorial-checklist.md)
- [<span data-ttu-id="df202-154">イシューを管理する方法</span><span class="sxs-lookup"><span data-stu-id="df202-154">How we manage issues</span></span>](managing-issues.md)
- [<span data-ttu-id="df202-155">プル要求を管理する方法</span><span class="sxs-lookup"><span data-stu-id="df202-155">How we manage pull requests</span></span>](managing-pull-requests.md)

<!--link refs-->
[cla]: https://cla.microsoft.com/
[contribute]: /contribute/
[docs]: https://docs.microsoft.com/
[file-an-issue]: file-an-issue.md
[posh-git]: https://www.powershellgallery.com/packages/posh-git
[psdocs]: https://docs.microsoft.com/powershell
[style-guide]: https://docs.microsoft.com/style-guide/welcome/
[terms-of-use]: https://docs.microsoft.com/legal/termsofuse

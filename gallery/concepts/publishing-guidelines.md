---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
description: パブリッシャー向けのガイドライン
title: PowerShell ギャラリーへの公開に関するガイドラインとベスト プラクティス
ms.openlocfilehash: 3aca76f8904c7eb64e5c96ae4f0f26014e0d2609
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="powershellgallery-publishing-guidelines-and-best-practices"></a><span data-ttu-id="14200-104">PowerShell ギャラリーへの公開に関するガイドラインとベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="14200-104">PowerShellGallery Publishing Guidelines and Best Practices</span></span>

<span data-ttu-id="14200-105">このトピックでは、PowerShell ギャラリーでのマニフェスト データの処理方法に基づいて、また多数の PowerShell ギャラリー ユーザーからのフィードバックに基づいて、PowerShell ギャラリーに公開したアイテムがユーザーに広く受け入れられ、高い価値をもたらすことができるように、Microsoft チームが行っている推奨の手順をご説明します。</span><span class="sxs-lookup"><span data-stu-id="14200-105">This topic describes recommended steps used by Microsoft teams to ensure the items published to the PowerShell Gallery will be widely adopted and provide high value to users, based on how the PowerShell Gallery handles manifest data and on feedback from large numbers of PowerShell Gallery users.</span></span>
<span data-ttu-id="14200-106">このガイドラインに従ってアイテムを公開すると、そのアイテムは信用されてインストールされやすくなるとともに、より多くのユーザーに興味を持ってもらうことができます。</span><span class="sxs-lookup"><span data-stu-id="14200-106">Items that are published following these guidelines will be more likely to be installed, trusted, and attract more users.</span></span>

<span data-ttu-id="14200-107">PowerShell ギャラリーの良質なアイテムを作成する上で大事なこと、オプションのマニフェスト設定で最も重要なこと、初期のレビュー担当者や [PowerShell Script Analyzer](https://aka.ms/psscriptanalyzer) からのフィードバックに基づいたコードの改善、モジュールのバージョン管理、ドキュメント、共有済みアイテムのテストと使用方法のサンプルなどに関するガイドラインを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="14200-107">Included below are guidelines for what makes a good PowerShell Gallery item, what optional Manifest settings are most important, improving your code with feedback from initial reviewers and [Powershell Script Analyzer](https://aka.ms/psscriptanalyzer), versioning your module, documentation, tests & examples for how to use what you have shared.</span></span>
<span data-ttu-id="14200-108">このドキュメントの大部分は、[高品質な DSC リソース モジュール](https://github.com/PowerShell/DscResources/blob/master/HighQualityModuleGuidelines.md)を公開するためのガイドラインを基にしています。</span><span class="sxs-lookup"><span data-stu-id="14200-108">Much of this documentation follows the guidelines for publishing [High Quality DSC Resource Modules](https://github.com/PowerShell/DscResources/blob/master/HighQualityModuleGuidelines.md).</span></span>

<span data-ttu-id="14200-109">PowerShell ギャラリーへのアイテムの公開の仕組みについては、「[アイテムの作成と公開](https://msdn.microsoft.com/powershell/gallery/psgallery/creating-and-publishing-an-item)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14200-109">For the mechanics of publishing an item to the PowerShell Gallery, see [Creating and Publishing an Item](https://msdn.microsoft.com/powershell/gallery/psgallery/creating-and-publishing-an-item).</span></span>

<span data-ttu-id="14200-110">このガイドラインについてのフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="14200-110">Feedback on these guidelines is welcomed.</span></span> <span data-ttu-id="14200-111">フィードバックをお送りいただく場合は、Microsoft の [GitHub ドキュメント リポジトリ](https://github.com/powershell/powershell-docs/) で Issue を作成してください。</span><span class="sxs-lookup"><span data-stu-id="14200-111">If you do have feedback, please open issues in our [Github documentation repository](https://github.com/powershell/powershell-docs/).</span></span>

## <a name="best-practices-for-publishing-items"></a><span data-ttu-id="14200-112">アイテムの公開に関するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="14200-112">Best practices for publishing items</span></span>

<span data-ttu-id="14200-113">以下に、PowerShell ギャラリーのアイテムのユーザーが重要と考えるベスト プラクティスを、名目上の優先度順に並べて示します。</span><span class="sxs-lookup"><span data-stu-id="14200-113">The following best practices are what the users of PowerShell Gallery items say is important, and are listed in nominal priority order.</span></span>
<span data-ttu-id="14200-114">アイテムは、以下のガイドラインに準拠していると、ユーザーにダウンロードされ使用される可能性がかなり高くなります。</span><span class="sxs-lookup"><span data-stu-id="14200-114">Items that follow these guidelines are far more likely to be downloaded and adopted by others.</span></span>

- <span data-ttu-id="14200-115">PSScriptAnalyzer を使用する</span><span class="sxs-lookup"><span data-stu-id="14200-115">Use PSScriptAnalyzer</span></span>
- <span data-ttu-id="14200-116">ドキュメントとサンプルを含める</span><span class="sxs-lookup"><span data-stu-id="14200-116">Include documentation and examples</span></span>
- <span data-ttu-id="14200-117">フィードバックに素早く対応する</span><span class="sxs-lookup"><span data-stu-id="14200-117">Be responsive to feedback</span></span>
- <span data-ttu-id="14200-118">スクリプトではなくモジュールを提供する</span><span class="sxs-lookup"><span data-stu-id="14200-118">Provide modules rather than scripts</span></span>
- <span data-ttu-id="14200-119">プロジェクト サイトへのリンクを提供する</span><span class="sxs-lookup"><span data-stu-id="14200-119">Provide links to a project site</span></span>
- <span data-ttu-id="14200-120">モジュールにテストを含める</span><span class="sxs-lookup"><span data-stu-id="14200-120">Include tests with your modules</span></span>
- <span data-ttu-id="14200-121">ライセンス条項を含めるか、ライセンス条項へのリンクを提供する (またはその両方)</span><span class="sxs-lookup"><span data-stu-id="14200-121">Include and/or link to license terms</span></span>
- <span data-ttu-id="14200-122">コードに署名する</span><span class="sxs-lookup"><span data-stu-id="14200-122">Sign your code</span></span>
- <span data-ttu-id="14200-123">バージョン管理に関する [SemVer](http://semver.org/) ガイドラインに従う</span><span class="sxs-lookup"><span data-stu-id="14200-123">Follow [SemVer](http://semver.org/) guidelines for versioning</span></span>
- <span data-ttu-id="14200-124">一般的な PowerShell ギャラリー タグに関する記事で説明されている一般的なタグを使用する</span><span class="sxs-lookup"><span data-stu-id="14200-124">Use common tags, as documented in Common PowerShell Gallery tags</span></span>
- <span data-ttu-id="14200-125">ローカル リポジトリを使用して公開に関するテストを行う</span><span class="sxs-lookup"><span data-stu-id="14200-125">Test publishing using a local repository</span></span>

<span data-ttu-id="14200-126">これらのベスト プラクティスのそれぞれについて、以下のセクションで簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="14200-126">Each of these is covered briefly in the sections below.</span></span>

## <a name="use-psscriptanalyzer"></a><span data-ttu-id="14200-127">PSScriptAnalyzer を使用する</span><span class="sxs-lookup"><span data-stu-id="14200-127">Use PSScriptAnalyzer</span></span>

<span data-ttu-id="14200-128">[PSScriptAnalyzer](https://www.powershellgallery.com/packages/PSScriptAnalyzer) は、PowerShell コードに対応した無料の静的コード分析ツールです。</span><span class="sxs-lookup"><span data-stu-id="14200-128">[PSScriptAnalyzer](https://www.powershellgallery.com/packages/PSScriptAnalyzer) is a free static code analysis tool that works on PowerShell code.</span></span>
<span data-ttu-id="14200-129">PSScriptAnalyzer では PowerShell のコードで頻繁に見られる問題が特定され、多くの場合、問題の推奨解決方法も示されます。</span><span class="sxs-lookup"><span data-stu-id="14200-129">PSScriptAnalyzer will identify the most common issues seen in PowerShell code, and often a recommendation for how to fix the issue.</span></span>
<span data-ttu-id="14200-130">このツールの使用は簡単であり、問題はエラー (重大であり対処が必須)、警告 (確認が必要であり対処した方がよい)、情報 (ベスト プラクティスの観点からチェックに値する) に分類されます。</span><span class="sxs-lookup"><span data-stu-id="14200-130">The tool is easy to use, and categorizes the issues as Errors (severe, must be addressed), Warning (need to be reviewed & should be addressed), and Information (worth checking out for best practices).</span></span>
<span data-ttu-id="14200-131">PowerShell ギャラリーに公開したアイテムはすべて PSScriptAnalyzer によりスキャンされます。エラーがある場合には所有者に報告されるので、対処を行ってください。</span><span class="sxs-lookup"><span data-stu-id="14200-131">All items item published to the PowerShell Gallery will be scanned using PSScriptAnalyzer, and any errors will be reported back to the owner and must be addressed.</span></span>

<span data-ttu-id="14200-132">`-Recurse` と `-Severity` として警告を指定して、`Invoke-ScriptAnalyzer` を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14200-132">The best practice is to run `Invoke-ScriptAnalyzer` with `-Recurse` and `-Severity` Warning.</span></span>

<span data-ttu-id="14200-133">結果を確認して以下を行います。</span><span class="sxs-lookup"><span data-stu-id="14200-133">Review the results, and ensure that:</span></span>

- <span data-ttu-id="14200-134">すべてのエラーを修正するか、ドキュメントに記載する</span><span class="sxs-lookup"><span data-stu-id="14200-134">All Errors are corrected or addressed in your documentation</span></span>
- <span data-ttu-id="14200-135">すべての警告を確認し、必要に応じて対処する</span><span class="sxs-lookup"><span data-stu-id="14200-135">All Warnings are reviewed, and addressed where applicable</span></span>

<span data-ttu-id="14200-136">PowerShell ギャラリーからアイテムを取得したユーザーには、PSScriptAnalyzer を実行してすべてのエラーと警告を確認することが強く推奨されています。</span><span class="sxs-lookup"><span data-stu-id="14200-136">Users who acquire items from the PowerShell Gallery are strongly encouraged to run PSScriptAnalyzer and evaluate all Errors and Warnings.</span></span>
<span data-ttu-id="14200-137">PSScriptAnalyzer でエラーが報告された場合、おそらくユーザーはアイテムの所有者に問い合わせるでしょう。</span><span class="sxs-lookup"><span data-stu-id="14200-137">Users are very likely to contact item owners if they see that there is an error reported by PSScriptAnalyzer.</span></span>
<span data-ttu-id="14200-138">エラーのフラグが付けられているアイテムのコードをそのままにしておかなければならない理由がある場合は、その旨をドキュメントに追加することで、同じ質問を何度も受けるのを回避できます。</span><span class="sxs-lookup"><span data-stu-id="14200-138">If there is a compelling reason for your item to keep code that is flagged as an error, add that information to your documentation to avoid having to answer the same question many times.</span></span>

## <a name="include-documentation-and-examples"></a><span data-ttu-id="14200-139">ドキュメントとサンプルを含める</span><span class="sxs-lookup"><span data-stu-id="14200-139">Include documentation and examples</span></span>

<span data-ttu-id="14200-140">ユーザーに共有コードを確実に活用してもらう一番の方法は、ドキュメントとサンプルを用意することです。</span><span class="sxs-lookup"><span data-stu-id="14200-140">Documentation and examples are the best way to ensure users can take advantage of any shared code.</span></span>

<span data-ttu-id="14200-141">ドキュメントは、PowerShell ギャラリーに公開するアイテムに含めておくと非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14200-141">Documentation is the most helpful thing to include in items published to the PowerShell Gallery.</span></span>
<span data-ttu-id="14200-142">アイテムにドキュメントが含まれていない場合、アイテムの中身と使用方法を理解するには代わりにコードを読まなければならないため、ほとんどのユーザーに敬遠されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="14200-142">Users will generally bypass items without documentation, as the alternative is to read the code to understand what the item is and how to use it.</span></span>
<span data-ttu-id="14200-143">PowerShell のアイテムと合わせてドキュメントを提供する方法に関する次のような記事が MSDN に掲載されています。</span><span class="sxs-lookup"><span data-stu-id="14200-143">There are several articles available in MSDN on how to provide documentation with PowerShell items, including:</span></span>

- <span data-ttu-id="14200-144">「[How to Write Cmdlet Help (コマンドレット ヘルプの書き方)](https://go.microsoft.com/fwlink/?LinkID=123415)」内のヘルプの提供に関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="14200-144">Guidelines for providing help are in [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415)</span></span>
- <span data-ttu-id="14200-145">コマンドレット ヘルプの作成。コマンドレット ヘルプは、すべての PowerShell スクリプト、関数、コマンドレットを理解するために最適な手段です。</span><span class="sxs-lookup"><span data-stu-id="14200-145">Creating cmdlet help, which is the best approach for any PowerShell script, function, or cmdlet.</span></span>
  <span data-ttu-id="14200-146">コマンドレット ヘルプの作成方法の詳細については、まず MSDN ライブラリの「[How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415)」 (コマンドレット ヘルプの書き方) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14200-146">For information about how to create cmdlet help, start with [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415) in the MSDN library.</span></span>
  <span data-ttu-id="14200-147">スクリプト内にヘルプを追加する方法については、「[About Comment Based Help (コメント ベースのヘルプの概要)](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/about/about_comment_based_help)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14200-147">To add help within a script, see [About Comment Based Help](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/about/about_comment_based_help).</span></span>
- <span data-ttu-id="14200-148">また、多くのモジュールには、テキスト形式のドキュメント (MarkDown ファイルなど) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="14200-148">Many modules also include documentation in text format, such as MarkDown files.</span></span>
  <span data-ttu-id="14200-149">MarkDown 形式が頻繁に使用されている GitHub にプロジェクト サイトを設置する場合、この方法は特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14200-149">This can be particularly helpful when there is a project site in Github, where Markdown is a heavily used format.</span></span>
  <span data-ttu-id="14200-150">[GitHub 用の Markdown](https://help.github.com/categories/writing-on-github/) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14200-150">The best practice is to use [Github-flavored Markdown](https://help.github.com/categories/writing-on-github/)</span></span>

<span data-ttu-id="14200-151">サンプルでは、アイテムの用途をユーザーに説明します。</span><span class="sxs-lookup"><span data-stu-id="14200-151">Examples show users how the item is intended to be used.</span></span>
<span data-ttu-id="14200-152">多くの開発者は、使用方法を確認する場合、ドキュメントの前にサンプルを見ると述べています。</span><span class="sxs-lookup"><span data-stu-id="14200-152">Many developers will say that they look at examples before documentation to understand how to use something.</span></span>
<span data-ttu-id="14200-153">基本的な使い方に加えて実際の使用例のシミュレーションを示し、コードに適切なコメントを付けると最適なサンプルになります。</span><span class="sxs-lookup"><span data-stu-id="14200-153">The best type of examples show basic use, plus a simulated realistic use case, and the code is well-commented.</span></span>
<span data-ttu-id="14200-154">PowerShell ギャラリーに公開するモジュールのサンプルは、モジュールのルートの下の Examples フォルダーに配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14200-154">Examples for modules published to the PowerShell Gallery should be in an Examples folder under the module root.</span></span>

<span data-ttu-id="14200-155">サンプルの推奨パターンは、[PSDscResource モジュール](https://www.powershellgallery.com/packages/PSDscResources) の Examples\RegistryResource フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="14200-155">A good pattern for examples can be found in the [PSDscResource module](https://www.powershellgallery.com/packages/PSDscResources) under the Examples\RegistryResource folder.</span></span>
<span data-ttu-id="14200-156">各ファイルの冒頭には、4 つのサンプルの使用例とともに、サンプルの内容を示す簡単な説明が記載されています。</span><span class="sxs-lookup"><span data-stu-id="14200-156">There are four sample use cases with a brief description at the top of each file that documents what is being demonstrated.</span></span>

## <a name="respond-to-feedback"></a><span data-ttu-id="14200-157">フィードバックに対応する</span><span class="sxs-lookup"><span data-stu-id="14200-157">Respond to feedback</span></span>

<span data-ttu-id="14200-158">アイテム所有者としてフィードバックに適切に対応すると、コミュニティでの評価が高くなります。</span><span class="sxs-lookup"><span data-stu-id="14200-158">Item owners who respond properly to feedback are highly valued by the community.</span></span>
<span data-ttu-id="14200-159">建設的なフィードバックを提供してくれるユーザーは、アイテムに高い関心を持っており改善の手助けをしてくれますので、必ず対応しましょう。</span><span class="sxs-lookup"><span data-stu-id="14200-159">Users who provide constructive feedback are important to respond to, as they are interested enough in the item to try to help improve it.</span></span>

<span data-ttu-id="14200-160">PowerShell ギャラリーでフィードバックを行う方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="14200-160">There are two feedback methods available in the PowerShell Gallery:</span></span>

- <span data-ttu-id="14200-161">所有者への連絡: この方法では、ユーザーはアイテムの所有者にメールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="14200-161">Contact Owner: This allows a user to send an email to the item owner(s).</span></span> <span data-ttu-id="14200-162">アイテムの所有者は、PowerShell ギャラリーアイテムで使用しているメール アドレスをチェックし、寄せられた問題に対応することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="14200-162">As an item owner, is important to monitor the email address used with the PowerShell Gallery items, and respond to issues that are raised.</span></span> <span data-ttu-id="14200-163">この方法の 1 つのデメリットは、問い合わせをしたユーザーと所有者しか会話を見られないため、所有者は同じ質問に何度も答えなければならない可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="14200-163">The one disadvantage to this method is that only the user and owner will ever see the communication, so the owner may have to answer the same question many times.</span></span>
- <span data-ttu-id="14200-164">コメント: アイテムのページの最下部には [Comment]\(コメント\) フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="14200-164">Comments: At the bottom of the item page is a Comment field.</span></span>
  <span data-ttu-id="14200-165">この方法のメリットは、他のユーザーもコメントと回答を確認できるため、同一の質問に答えなければならない回数を少なくできることです。</span><span class="sxs-lookup"><span data-stu-id="14200-165">The advantage to this system is that other users can see the comments and responses, which reduces the number of times any single question must be answered.</span></span>
  <span data-ttu-id="14200-166">アイテムの所有者には、各アイテムに寄せられたコメントを Follow (フォロー) することが強く推奨されます。</span><span class="sxs-lookup"><span data-stu-id="14200-166">As an item owner, it is strongly recommended that you Follow the comments made for each item.</span></span>
<span data-ttu-id="14200-167">フォロー方法の詳細については、「[Providing Feedback via Social Media or Comments (ソーシャル メディアやコメントを使用したフィードバックの提供)](../how-to/working-with-items/social-media-feedback.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14200-167">See [Providing Feedback via Social Media or Comments](../how-to/working-with-items/social-media-feedback.md) for details on how to do that.</span></span>

<span data-ttu-id="14200-168">フィードバックに建設的に対応すると、コミュニティで高い評価を得られます。</span><span class="sxs-lookup"><span data-stu-id="14200-168">Owners who respond to feedback constructively are appreciated by the community.</span></span>
<span data-ttu-id="14200-169">この報告の機会を利用して、必要に応じて詳細情報を求めたり、回避策を提示したり、更新によって問題が修正されるかどうかを確認したりしましょう。</span><span class="sxs-lookup"><span data-stu-id="14200-169">Use the opportunity in the report to request more information if needed, provide a workaround, or identify if an update fixes a problem.</span></span>

<span data-ttu-id="14200-170">これらの連絡方法のいずれかで不適切な振る舞いが見られた場合には、PowerShell ギャラリーの Report Abuse (迷惑行為の報告) 機能を使用して、ギャラリーの管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="14200-170">If there is inappropriate behavior observed from either of these communication channels, use the Report Abuse feature of the PowerShell Gallery to contact the Gallery Administrators.</span></span>

## <a name="modules-versus-scripts"></a><span data-ttu-id="14200-171">モジュールとスクリプト</span><span class="sxs-lookup"><span data-stu-id="14200-171">Modules Versus Scripts</span></span>

<span data-ttu-id="14200-172">他のユーザーとのスクリプトの共有は便利であり、生じる可能性のある問題の解決方法の例を提示できます。</span><span class="sxs-lookup"><span data-stu-id="14200-172">Sharing a script with other users is great, and provides others with examples of how to solve problems they may have.</span></span>
<span data-ttu-id="14200-173">問題は、PowerShell ギャラリーではスクリプトは単一のファイルとなり、個別のドキュメントやサンプル、テストを提供できないことです。</span><span class="sxs-lookup"><span data-stu-id="14200-173">The issue is that scripts in the PowerShell Gallery are single files without separate documentation, examples, and tests.</span></span>

<span data-ttu-id="14200-174">PowerShell モジュールはフォルダー構造となっており、複数のフォルダーやファイルをパッケージ内に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="14200-174">PowerShell Modules have a folder structure that allows multiple folders and files to be included with the package.</span></span>
<span data-ttu-id="14200-175">こうしたモジュールの構造であれば、ベスト プラクティスとして示したコマンドレット ヘルプ、ドキュメント、サンプル、テストなどのアイテムも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="14200-175">The module structure enables including the other items we list as best practices: cmdlet help, documentation, examples, and tests.</span></span>
<span data-ttu-id="14200-176">最大のデメリットは、モジュール内のスクリプトを公開し関数として使用する必要があることです。</span><span class="sxs-lookup"><span data-stu-id="14200-176">The biggest disadvantage is that a script inside a module must be exposed and used as a function.</span></span>
<span data-ttu-id="14200-177">モジュールの作成方法については、「[Writing a Windows PowerShell Module (Windows PowerShell モジュールの作成)](http://go.microsoft.com/fwlink/?LinkId=144916)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14200-177">For information on how to create a module, see [Writing a Windows PowerShell Module](http://go.microsoft.com/fwlink/?LinkId=144916).</span></span>

<span data-ttu-id="14200-178">特に DSC 構成などで、スクリプトを提供すると、ユーザー エクスペリエンスを改善できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="14200-178">There are situations where a script provides a better experience for the user, particularly with DSC configurations.</span></span>
<span data-ttu-id="14200-179">DSC 構成のベスト プラクティスとして、ドキュメント、サンプル、テストが含まれる付属モジュールと合わせて、構成をスクリプトとして公開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14200-179">The best practice for DSC configurations is to publish the configuration as a script with an accompanying module that contains the docs, examples, and tests.</span></span>
<span data-ttu-id="14200-180">このスクリプトには、RequiredModules = @(モジュール名) 形式で付随モジュールの一覧を記載します。</span><span class="sxs-lookup"><span data-stu-id="14200-180">The script lists the accompanying module using RequiredModules = @(Name of the Module).</span></span>
<span data-ttu-id="14200-181">この方法はどのようなスクリプトでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="14200-181">This approach can be used with any script.</span></span>

<span data-ttu-id="14200-182">スタンドアロン スクリプトの場合、その他のベスト プラクティスに従うことで別のユーザーに大きな価値を提供できます。</span><span class="sxs-lookup"><span data-stu-id="14200-182">Standalone scripts that follow the other best practices provide real value to other users.</span></span>
<span data-ttu-id="14200-183">スクリプトを PowerShell ギャラリーに公開する場合、コメント ベースのドキュメントとプロジェクト サイトへのリンクを提供することが強く推奨されます。</span><span class="sxs-lookup"><span data-stu-id="14200-183">Providing comment-based documentation and a link to a Project Site are highly recommended when publishing a script to the PowerShell Gallery.</span></span>

## <a name="provide-a-link-to-a-project-site"></a><span data-ttu-id="14200-184">プロジェクト サイトへのリンクを提供する</span><span class="sxs-lookup"><span data-stu-id="14200-184">Provide a link to a project site</span></span>

<span data-ttu-id="14200-185">プロジェクト サイトは、パブリッシャーとパブリッシャーの PowerShell ギャラリー アイテムのユーザーが直接やりとりできる場所です。</span><span class="sxs-lookup"><span data-stu-id="14200-185">A Project Site is where a publisher can interact directly with the users of their PowerShell Gallery items.</span></span>
<span data-ttu-id="14200-186">プロジェクト サイトではアイテムの情報をより簡単に得られるため、このサイトを備えたアイテムの方がユーザーに選ばれやすくなります。</span><span class="sxs-lookup"><span data-stu-id="14200-186">Users prefer items that provide this, as it allows them to get information about the item more easily.</span></span>
<span data-ttu-id="14200-187">PowerShell ギャラリーのアイテムの多くは GitHub で開発されていますが、専用の Web サイトを持つ組織が提供しているものもあります。</span><span class="sxs-lookup"><span data-stu-id="14200-187">Many items in the PowerShell Gallery are developed in GitHub, others are provided by organizations with a dedicated web presence.</span></span>
<span data-ttu-id="14200-188">こうしたサイトのそれぞれがプロジェクト サイトとなります。</span><span class="sxs-lookup"><span data-stu-id="14200-188">Each of these can be considered a project site.</span></span>

<span data-ttu-id="14200-189">リンクを追加するには、次のようにマニフェストの PSData セクションに ProjectURI を記載します。</span><span class="sxs-lookup"><span data-stu-id="14200-189">Adding a link is done by including ProjectURI in the PSData section of the manifest as follows:</span></span>

        # A URL to the main website for this project.
        ProjectUri = 'https://github.com/powershell/powershell'

<span data-ttu-id="14200-190">ProjectURI が記載されている場合、PowerShell ギャラリーではアイテム ページの左側にプロジェクト サイトへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14200-190">When a ProjectURI is provided, the PowerShell Gallery will include a link to the Project Site on the left side of the item page.</span></span>

## <a name="include-tests"></a><span data-ttu-id="14200-191">テストを含める</span><span class="sxs-lookup"><span data-stu-id="14200-191">Include tests</span></span>

<span data-ttu-id="14200-192">オープンソースのコードにテストを含めると、検証内容を保証できるとともに、コードの仕組みに関する情報を提供できるため、ユーザーにとって非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14200-192">Including tests with open-source code is important to users, as it gives them assurance about what you validate, and provides information on how your code works.</span></span> <span data-ttu-id="14200-193">また、ユーザーはコードを自分の環境に合わせて変更した場合でも元の機能が損なわれないことをテストによって確認できます。</span><span class="sxs-lookup"><span data-stu-id="14200-193">It also allows users to ensure they do not break your original functionality if they modify your code to fit their environment.</span></span>

<span data-ttu-id="14200-194">テストは、PowerShell 専用に設計された Pester テスト フレームワークを使用して作成することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14200-194">It is strongly recommended that tests be written to take advantage of the Pester test framework, which has been designed specifically for PowerShell.</span></span>
<span data-ttu-id="14200-195">Pester は [GitHub](https://github.com/Pester/Pester) と [PowerShell ギャラリー](https://www.powershellgallery.com/packages/Pester/)で入手できます。また、Windows 10、Windows Server 2016、WMF 5.0、WMF 5.1 に同梱されています。</span><span class="sxs-lookup"><span data-stu-id="14200-195">Pester is available in [GitHub](https://github.com/Pester/Pester), the [PowerShell Gallery](https://www.powershellgallery.com/packages/Pester/), and ships in Windows 10, Windows Server 2016, WMF 5.0 and WMF 5.1.</span></span>

<span data-ttu-id="14200-196">[GitHub の Pester のプロジェクト サイト](https://github.com/Pester/Pester)では、概要を始めベスト プラクティスに至るまで、Pester でのテストの作成方法が詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="14200-196">The [Pester project site in GitHub](https://github.com/Pester/Pester) includes good documentation on writing Pester tests, from getting started to best practices.</span></span>

<span data-ttu-id="14200-197">テスト範囲の目標値は[高品質のリソース モジュール](https://github.com/PowerShell/DscResources/blob/master/HighQualityModuleGuidelines.md)に関するドキュメントに記載されており、単体テストでのコード カバレッジの推奨値は 70% です。</span><span class="sxs-lookup"><span data-stu-id="14200-197">The targets for test coverage are called out in the [High Quality Resource Module documentation](https://github.com/PowerShell/DscResources/blob/master/HighQualityModuleGuidelines.md), with 70% unit test code coverage recommended.</span></span>

## <a name="include-andor-link-to-license-terms"></a><span data-ttu-id="14200-198">ライセンス条項を含めるか、ライセンス条項へのリンクを提供する (またはその両方)</span><span class="sxs-lookup"><span data-stu-id="14200-198">Include and/or link to license terms</span></span>

<span data-ttu-id="14200-199">PowerShell ギャラリーに公開するすべてのアイテムについて、ライセンス条項を指定するか、「[Terms of Use (使用条件)](https://www.powershellgallery.com/policies/Terms)」の「Exhibit A (別紙 A)」に記載されているライセンスで拘束する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14200-199">All items published to the PowerShell Gallery must specify the license terms, or be bound by the license included in the [Terms of Use](https://www.powershellgallery.com/policies/Terms) under "Exhibit A".</span></span>
<span data-ttu-id="14200-200">別のライセンスを指定する最適な方法は、PSData の LicenseURI を利用してライセンスへのリンクを提供することです。</span><span class="sxs-lookup"><span data-stu-id="14200-200">The best approach to specifying a different license is to provide a link to the license using the LicenseURI in PSData.</span></span>
<span data-ttu-id="14200-201">サンプルは、推奨されるマニフェスト フィールドに関するトピックに記載されています。</span><span class="sxs-lookup"><span data-stu-id="14200-201">You can find an example in the Recommended Manifest Fields topic.</span></span>

```powershell
PrivateData = @{
    PSData = @{

        # Tags applied to this module. These help with module discovery in online galleries.
        Tags = @('.net','acl','active-directory')

        # A URL to the license for this module.
        LicenseUri = 'http://www.apache.org/licenses/LICENSE-2.0'
```

## <a name="sign-your-code"></a><span data-ttu-id="14200-202">コードに署名する</span><span class="sxs-lookup"><span data-stu-id="14200-202">Sign your code</span></span>

<span data-ttu-id="14200-203">コードに署名することで、アイテムの公開者について、またユーザーが取得したコードのコピーは公開者が公開したものに間違いないということを、ユーザーに対して最も確実に保証できます。</span><span class="sxs-lookup"><span data-stu-id="14200-203">Code signing provides users with the highest level of assurance for who published the item, and that the copy of the code they acquire is exactly what the publisher released.</span></span>
<span data-ttu-id="14200-204">コードへの一般的な署名方法の詳細については、「[Introduction to Code Signing (コード署名の概要)](http://go.microsoft.com/fwlink/?LinkId=106296)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14200-204">To learn more about code signing generally, see [Introduction to Code Signing](http://go.microsoft.com/fwlink/?LinkId=106296).</span></span>
<span data-ttu-id="14200-205">PowerShell では、コード署名について 2 つの主な検証方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="14200-205">PowerShell supports validation of code signing through two primary approaches:</span></span>

- <span data-ttu-id="14200-206">スクリプト ファイルへの署名</span><span class="sxs-lookup"><span data-stu-id="14200-206">Signing script files</span></span>
- <span data-ttu-id="14200-207">モジュールへのカタログ署名</span><span class="sxs-lookup"><span data-stu-id="14200-207">Catalog signing a module</span></span>

<span data-ttu-id="14200-208">PowerShell ファイルに署名することで、実行するコードが信頼できる作成元で作成されており、変更されていないことを確実に保証できます。</span><span class="sxs-lookup"><span data-stu-id="14200-208">Signing PowerShell files is a well-established approach to ensuring that the code being executed was produced by a reliable source, and has not been modified.</span></span>
<span data-ttu-id="14200-209">PowerShell スクリプト ファイルへの署名方法の詳細については、「[About Signing (署名について)](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_signing)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14200-209">Details on how to sign PowerShell script files is covered in the [About Signing](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_signing) topic.</span></span>
<span data-ttu-id="14200-210">署名はすべての .PS1 ファイルに追加することができ、スクリプトのロード時に PowerShell により検証されます。</span><span class="sxs-lookup"><span data-stu-id="14200-210">In overview, a signature can be added to any .PS1 file that PowerShell validates when the script is loaded.</span></span>
<span data-ttu-id="14200-211">[実行ポリシー](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_execution_policies) コマンドレットを使用して、署名済みのスクリプトのみが使用されるように PowerShell を制限できます。</span><span class="sxs-lookup"><span data-stu-id="14200-211">PowerShell can be constrained using the [Execution Policy](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_execution_policies) cmdlets to ensure use of signed scripts.</span></span>

<span data-ttu-id="14200-212">モジュールへのカタログ署名は、バージョン 5.1 で PowerShell に追加された機能です。</span><span class="sxs-lookup"><span data-stu-id="14200-212">Catalog signing modules is a feature added to PowerShell in version 5.1.</span></span>
<span data-ttu-id="14200-213">モジュールへの署名方法については、「[カタログ コマンドレット](https://msdn.microsoft.com/en-us/powershell/wmf/5.1/catalog-cmdlets)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14200-213">How to sign a module is covered in the [Catalog Cmdlets](https://msdn.microsoft.com/en-us/powershell/wmf/5.1/catalog-cmdlets) topic.</span></span>
<span data-ttu-id="14200-214">カタログ署名は、モジュール内の全ファイルのハッシュ値を含むカタログ ファイルを作成してそのファイルに署名することで行います。</span><span class="sxs-lookup"><span data-stu-id="14200-214">In overview, catalog signing is done by creating a catalog file, which contains a hash value for every file in the module, and then signing that file.</span></span>
<span data-ttu-id="14200-215">PowerShellGet の publish-module、install-module、save-module、update-module の各コマンドレットにより、署名が有効であることがチェックされ、各アイテムのハッシュ値がカタログに記載されているものと一致するか確認されます。</span><span class="sxs-lookup"><span data-stu-id="14200-215">The PowerShellGet publish-module, install-module, save-module, and update-module cmdlets will check the signature to ensure it is valid, then confirm that the hash value for each item matches what is in the catalog.</span></span>
<span data-ttu-id="14200-216">システムに旧バージョンのモジュールがインストールされている場合、新バージョンの署名機関がインストール済みのものと一致することが install-module によって確認されます。</span><span class="sxs-lookup"><span data-stu-id="14200-216">If a previous version of the module is installed on the system, install-module will confirm that the signing authority for the new version matches what was previously installed.</span></span>
<span data-ttu-id="14200-217">カタログ署名は、スクリプト ファイルへの署名と併用できますが、代わりになるものではありません。</span><span class="sxs-lookup"><span data-stu-id="14200-217">Catalog signing works with, but does not replace signing script files.</span></span> <span data-ttu-id="14200-218">PowerShell では、モジュールのロード時にカタログ署名の検証は行われません。</span><span class="sxs-lookup"><span data-stu-id="14200-218">PowerShell does not validate catalog signatures at module load time.</span></span>

## <a name="follow-semver-guidelines-for-versioning"></a><span data-ttu-id="14200-219">バージョン管理に関する SemVer ガイドラインに従う</span><span class="sxs-lookup"><span data-stu-id="14200-219">Follow SemVer guidelines for versioning</span></span>

<span data-ttu-id="14200-220">[SemVer](http://semver.org/) は、変更内容を簡単に判別できるようにする、バージョンの構造化と変更の方法を定めた一般的な規則です。</span><span class="sxs-lookup"><span data-stu-id="14200-220">[SemVer](http://semver.org/) is a public convention that describes how to structure and change a version to allow easy intepretation of changes.</span></span>
<span data-ttu-id="14200-221">マニフェスト データには、アイテムのバージョンを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="14200-221">The version for your item must be included in the manifest data.</span></span>

- <span data-ttu-id="14200-222">バージョンは 0.1.1 や 4.11.192 のように、3 つの数字ブロックをピリオドで区切って構造化する</span><span class="sxs-lookup"><span data-stu-id="14200-222">The version should be structured as 3 numeric blocks separated by periods, as in 0.1.1 or 4.11.192</span></span>
- <span data-ttu-id="14200-223">"0" から始まるバージョンはアイテムがまだ運用環境に対応していないことを示す。先頭の数字のみを使用する場合は、"0" から始める必要がある</span><span class="sxs-lookup"><span data-stu-id="14200-223">Versions starting with "0" indicate that the item is not yet production ready, and the first number should only begin with "0" if that is the only number used</span></span>
- <span data-ttu-id="14200-224">先頭の数字の変更 (1.9.9999 から 2.0.0) は、バージョン間で重大な変更が行われたことを示す</span><span class="sxs-lookup"><span data-stu-id="14200-224">Changes in the first number (1.9.9999 to 2.0.0) indicate major and breaking changes between the versions</span></span>
- <span data-ttu-id="14200-225">2 番目の数字の変更 (1.01 から 1.02) は、モジュールへの新しいコマンドレットの追加など、機能レベルでの変更を示す</span><span class="sxs-lookup"><span data-stu-id="14200-225">Changes to the second number (1.01 to 1.02) indicate feature-level changes, such as adding new cmdlets to a module</span></span>
- <span data-ttu-id="14200-226">3 番目の数字の変更は、パラメーターの新規追加、サンプルの更新、テストの新規追加など、小規模な変更を示す</span><span class="sxs-lookup"><span data-stu-id="14200-226">Changes to the third number indicate non-breaking changes, such as new parameters, updated samples, or new tests</span></span>
- <span data-ttu-id="14200-227">バージョンを一覧化すると、PowerShell ではバージョンは文字列として並び替えられるため、1.01.0 は 1.001.0 より大きいものと扱われる</span><span class="sxs-lookup"><span data-stu-id="14200-227">When listing versions, PowerShell will sort the versions as strings, so 1.01.0 will be treated as greater than 1.001.0</span></span>

<span data-ttu-id="14200-228">PowerShell は SemVer の公開前に作成されたため、SemVer の大半の要素をサポートしてはいますが、以下のようにサポートされていない要素もあります。</span><span class="sxs-lookup"><span data-stu-id="14200-228">PowerShell was created before SemVer was published, so it provides support for most but not all elements of SemVer, specifically:</span></span>

- <span data-ttu-id="14200-229">バージョン番号のプレリリース文字列はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="14200-229">It does not support prerelease strings in version numbers.</span></span> <span data-ttu-id="14200-230">プレリリース文字列は、パブリッシャーがバージョン 1.0.0 の提供後に新しいメジャー バージョンを提供したい場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14200-230">This is useful when a publisher wishes to deliver a preview release of a new major version after providing a version 1.0.0.</span></span> <span data-ttu-id="14200-231">この文字列は、PowerShell ギャラリーと PowerShellGet コマンドレットの今後のリリースでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="14200-231">This will be supported in a future release of the PowerShell Gallery and PowerShellGet cmdlets.</span></span>
- <span data-ttu-id="14200-232">PowerShell と PowerShell ギャラリーでは、数字ブロックが 1 つ、2 つ、4 つのバージョン文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="14200-232">PowerShell and the PowerShell Gallery allow version strings with 1, 2, and 4 segments.</span></span> <span data-ttu-id="14200-233">初期のモジュールの多くは SemVer ガイドラインに従っていませんでした。また Microsoft からの製品リリースでは、ビルド情報が 4 番目の数字ブロックとして含められています (例: 5.1.14393.1066)。</span><span class="sxs-lookup"><span data-stu-id="14200-233">Many early modules did not follow the guidelines, and product releases from Microsoft include build information as a 4th block of numbers (for example 5.1.14393.1066).</span></span> <span data-ttu-id="14200-234">バージョン管理の観点では、こうした違いは無視できます。</span><span class="sxs-lookup"><span data-stu-id="14200-234">From a versioning standpoint, these differences are ignored.</span></span>

## <a name="test-using-a-local-repository"></a><span data-ttu-id="14200-235">ローカル リポジトリを使用してテストする</span><span class="sxs-lookup"><span data-stu-id="14200-235">Test using a local repository</span></span>

<span data-ttu-id="14200-236">PowerShell ギャラリーは、公開プロセスのテストの対象となっていません。</span><span class="sxs-lookup"><span data-stu-id="14200-236">The PowerShell Gallery is not designed to be a target for testing the publishing process.</span></span>
<span data-ttu-id="14200-237">PowerShell ギャラリーへのエンドツーエンドの公開プロセスをテストする最良の方法は、独自のローカル リポジトリを設定して使用することです。</span><span class="sxs-lookup"><span data-stu-id="14200-237">The best way to test out the end-to-end process of publishing to the PowerShell Gallery is to set up and use your own local repository.</span></span>
<span data-ttu-id="14200-238">これは、次のいくつかの方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="14200-238">This can be done in a few ways, including:</span></span>

- <span data-ttu-id="14200-239">Github で [PS プライベート ギャラリー プロジェクト](https://github.com/PowerShell/PSPrivateGallery)を使用して、PowerShell ギャラリーのローカル インスタンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="14200-239">Set up a local PowerShell Gallery instance, using the [PS Private Gallery project](https://github.com/PowerShell/PSPrivateGallery) in Github.</span></span> <span data-ttu-id="14200-240">このプレビュー プロジェクトでは、制御可能でありテスト対象である PowerShell ギャラリーのインスタンスを容易に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="14200-240">This preview project will help you set up an instance of the PowerShell Gallery that you can control, and use for your tests.</span></span>
- <span data-ttu-id="14200-241">[Nuget 内部リポジトリ](https://blogs.msdn.microsoft.com/powershell/2014/05/20/setting-up-an-internal-powershellget-repository/)を設定します。</span><span class="sxs-lookup"><span data-stu-id="14200-241">Set up an [internal Nuget repository](https://blogs.msdn.microsoft.com/powershell/2014/05/20/setting-up-an-internal-powershellget-repository/).</span></span> <span data-ttu-id="14200-242">これには追加の設定作業が必要です。ただし、利点として、API キーの使用を検証したり、公開時にターゲット内に依存関係が存在するかどうかを検証したりするなど、追加の要件をいくつか検証することができます。</span><span class="sxs-lookup"><span data-stu-id="14200-242">This will require more work to set up, but will have the advantage of validating a few more of the requirements, notably validating use of an API key, and whether or not dependencies are present in the target when you publish.</span></span>
- <span data-ttu-id="14200-243">ファイル共有をテスト "リポジトリ" として設定します。</span><span class="sxs-lookup"><span data-stu-id="14200-243">Set up a file share as the test “repository”.</span></span> <span data-ttu-id="14200-244">この設定は簡単ですが、ファイル共有であるため、上記の検証は行われません。</span><span class="sxs-lookup"><span data-stu-id="14200-244">This is easy to set up, but since it is a file share, the validations noted above will not take place.</span></span> <span data-ttu-id="14200-245">この場合の潜在的な利点の 1 つは、ファイル共有で (必須の) API キーが確認されないため、PowerShell ギャラリーに公開するのと同じキーを使用できるということです。</span><span class="sxs-lookup"><span data-stu-id="14200-245">One potential advantage in this case is that the file share does not check the (required) API key, so you can use the same key you would to publish to the PowerShell Gallery.</span></span>

<span data-ttu-id="14200-246">これらのソリューションでは、Register-PSRepository を使用して、新しい "リポジトリ" を定義します。これは、Publish-Module の -Repository プロパティで使用します。</span><span class="sxs-lookup"><span data-stu-id="14200-246">With any of these solutions, use Register-PSRepository to define a new "repository", which you use in the -Repository property for Publish-Module.</span></span>

<span data-ttu-id="14200-247">テストの公開に関する追加のポイント: PowerShell ギャラリーに公開したアイテムはオペレーション チームの支援がなければ、削除できません。オペレーション チームは、公開するアイテムに何も依存していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="14200-247">One additional point about test publishing: any item you publish to the PowerShell Gallery cannot be deleted without help from the operations team, who will confirm that nothing is dependent upon the item you wish to publish.</span></span>
<span data-ttu-id="14200-248">そのため、弊社では PowerShell ギャラリーをテストの対象としてサポートしておらず、テストを行っている公開元に問い合わせします。</span><span class="sxs-lookup"><span data-stu-id="14200-248">For that reason, we do not support the PowerShell Gallery as a testing target, and will contact any publisher who does so.</span></span>

## <a name="recommended-workflow"></a><span data-ttu-id="14200-249">推奨ワークフロー</span><span class="sxs-lookup"><span data-stu-id="14200-249">Recommended workflow</span></span>

<span data-ttu-id="14200-250">PowerShell ギャラリーにアイテムを公開する上で最も効果的と考えられる方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="14200-250">The most successful approach we have found for items published to the PowerShell Gallery is this:</span></span>

- <span data-ttu-id="14200-251">初期の開発はオープンソースのプロジェクト サイトで行う。</span><span class="sxs-lookup"><span data-stu-id="14200-251">Do initial development in a an open-source project site.</span></span> <span data-ttu-id="14200-252">PowerShell チームでは Github を使用しています。</span><span class="sxs-lookup"><span data-stu-id="14200-252">The PowerShell Team uses Github.</span></span>
- <span data-ttu-id="14200-253">レビュー担当者と [PowerShell Script Analyzer](https://aka.ms/psscriptanalyzer) からのフィードバックを活用してコードを安定化させる</span><span class="sxs-lookup"><span data-stu-id="14200-253">Use feedback from reviewers and [Powershell Script Analyzer](https://aka.ms/psscriptanalyzer) to get the code to stable state</span></span>
- <span data-ttu-id="14200-254">他のユーザーがアイテムの使用方法を知ることができるようにドキュメントを含める</span><span class="sxs-lookup"><span data-stu-id="14200-254">Include documentation, so others know how to use your work</span></span>
- <span data-ttu-id="14200-255">ローカル リポジトリを使用して公開動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="14200-255">Test out the publishing action using a local repository.</span></span>
- <span data-ttu-id="14200-256">PowerShell ギャラリーには安定版またはアルファ リリースを公開し、必ずドキュメントとプロジェクト サイトへのリンクを記載する</span><span class="sxs-lookup"><span data-stu-id="14200-256">Publish a stable or Alpha release to the PowerShell Gallery, making sure to include the documentation and link to your project site</span></span>
- <span data-ttu-id="14200-257">プロジェクト サイトでフィードバックを集めてコードを反復開発し、安定した更新版を PowerShell ギャラリーに公開する</span><span class="sxs-lookup"><span data-stu-id="14200-257">Gather feedback and iterate on the code in your project site, then publish stable updates to the PowerShell Gallery</span></span>
- <span data-ttu-id="14200-258">プロジェクトとモジュールにサンプルと Pester テストを追加する</span><span class="sxs-lookup"><span data-stu-id="14200-258">Add examples and Pester tests in your project and your module</span></span>
- <span data-ttu-id="14200-259">アイテムのコード署名を行うかどうかを決定する</span><span class="sxs-lookup"><span data-stu-id="14200-259">Decide if you want to code sign your item</span></span>
- <span data-ttu-id="14200-260">プロジェクトが運用環境で使用できるようになったと思われる場合は、1.0.0 バージョンを PowerShell ギャラリーに公開する</span><span class="sxs-lookup"><span data-stu-id="14200-260">When you feel the project is ready to use in a production environment, publish a 1.0.0 version to the PowerShell Gallery</span></span>
- <span data-ttu-id="14200-261">引き続きフィードバックを収集し、ユーザーの意見に基づいてコードを反復開発する</span><span class="sxs-lookup"><span data-stu-id="14200-261">Continue to gather feedback and iterate on your code based on user input</span></span>
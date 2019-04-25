---
title: PowerShell コマンドレットのヘルプの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55908d67-7cbe-482a-a105-5a6da93c5311
caps.latest.revision: 4
ms.openlocfilehash: 8d692cf88d1d356886ef973f0989294d6b51ee6d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083163"
---
# <a name="writing-help-for-powershell-cmdlets"></a><span data-ttu-id="667ef-102">PowerShell コマンドレットについては、書き込み</span><span class="sxs-lookup"><span data-stu-id="667ef-102">Writing Help for PowerShell Cmdlets</span></span>

<span data-ttu-id="667ef-103">PowerShell コマンドレットが役に立ちますが、コマンドレットが使われませんか、ユーザーはストレスを感じる可能性があります、さらに悪いことに、ヘルプ トピックは、コマンドレットの機能とその使用方法を明確に説明、しない限り、します。</span><span class="sxs-lookup"><span data-stu-id="667ef-103">PowerShell cmdlets can be useful, but unless your Help topics clearly explain what the cmdlet does and how to use it, the cmdlet may not get used or, even worse, it might frustrate users.</span></span>
<span data-ttu-id="667ef-104">XML ベースのコマンドレットのヘルプ ファイルの形式の一貫性が向上し、非常に役立ちますがはるかに必要です。</span><span class="sxs-lookup"><span data-stu-id="667ef-104">The XML-based cmdlet Help file format enhances consistency, but great help requires much more.</span></span>

<span data-ttu-id="667ef-105">決してコマンドレットのヘルプを記述した場合は、次のガイドラインを確認します。</span><span class="sxs-lookup"><span data-stu-id="667ef-105">If you have never written cmdlet Help, review the following guidelines.</span></span>
<span data-ttu-id="667ef-106">コマンドレットのヘルプ トピックを作成するために必要な XML スキーマは、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="667ef-106">The XML schema required to author the cmdlet Help topic is described in the following section.</span></span>
<span data-ttu-id="667ef-107">始まり[コマンドレットのヘルプ ファイルを作成する](./how-to-create-the-cmdlet-help-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="667ef-107">Start with [Creating the Cmdlet Help File](./how-to-create-the-cmdlet-help-file.md).</span></span>
<span data-ttu-id="667ef-108">そのトピックには、最上位の XML ノードの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="667ef-108">That topic includes a description of the top-level XML nodes.</span></span>

## <a name="writing-guidelines-for-cmdlet-help"></a><span data-ttu-id="667ef-109">コマンドレットのヘルプのガイドライン</span><span class="sxs-lookup"><span data-stu-id="667ef-109">Writing Guidelines for Cmdlet Help</span></span>

### <a name="write-well"></a><span data-ttu-id="667ef-110">書き込み</span><span class="sxs-lookup"><span data-stu-id="667ef-110">Write well</span></span>
<span data-ttu-id="667ef-111">何も適切に記述されたトピックが置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="667ef-111">Nothing replaces a well-written topic.</span></span>
<span data-ttu-id="667ef-112">プロフェッショナル ライターでない場合は、するためには、ライターまたはエディターを検索します。</span><span class="sxs-lookup"><span data-stu-id="667ef-112">If you are not a professional writer, find a writer or editor to help you.</span></span>
<span data-ttu-id="667ef-113">別の方法としては、Microsoft Word にヘルプ テキストをコピーし、文法の使用して、作業を向上させるためにスペルを確認します。</span><span class="sxs-lookup"><span data-stu-id="667ef-113">Another alternative is to copy your Help text into Microsoft Word and use the grammar and spelling checks to improve your work.</span></span>

### <a name="write-simply"></a><span data-ttu-id="667ef-114">単純に書き込む</span><span class="sxs-lookup"><span data-stu-id="667ef-114">Write simply</span></span>
<span data-ttu-id="667ef-115">単純な単語や語句を使用します。</span><span class="sxs-lookup"><span data-stu-id="667ef-115">Use simple words and phrases.</span></span>
<span data-ttu-id="667ef-116">専門用語を回避します。</span><span class="sxs-lookup"><span data-stu-id="667ef-116">Avoid jargon.</span></span>
<span data-ttu-id="667ef-117">外国語ディクショナリと、ヘルプ トピックでのみ、多くの読者が搭載されていることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="667ef-117">Consider that many readers are equipped only with a foreign-language dictionary and your Help topic.</span></span>

### <a name="write-consistently"></a><span data-ttu-id="667ef-118">書き込み操作</span><span class="sxs-lookup"><span data-stu-id="667ef-118">Write consistently</span></span>
<span data-ttu-id="667ef-119">ヘルプ関連コマンドレットは (例、get x セット x 用) のようになります。</span><span class="sxs-lookup"><span data-stu-id="667ef-119">Help for related cmdlets should be similar (for example, get-x and set-x).</span></span>
<span data-ttu-id="667ef-120">などの標準的なパラメーターは、標準的な説明を使用して**Force**と**InputObject**します。</span><span class="sxs-lookup"><span data-stu-id="667ef-120">Use the standard descriptions for standard parameters, like **Force** and **InputObject**.</span></span>
<span data-ttu-id="667ef-121">(コピーしてヘルプからのコア コマンドレット)。標準の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="667ef-121">(Copy them from Help for the core cmdlets.) Use standard terms.</span></span>
<span data-ttu-id="667ef-122">たとえば、「パラメーター」の使用、いない「引数」と「コマンドレット」を使用しない「コマンド」または「コマンドとします」</span><span class="sxs-lookup"><span data-stu-id="667ef-122">For example, use "parameter", not "argument", and use "cmdlet" not "command" or "command-let."</span></span>

### <a name="start-the-synopsis-with-a-verb"></a><span data-ttu-id="667ef-123">動詞を使用して、概要を開始します。</span><span class="sxs-lookup"><span data-stu-id="667ef-123">Start the synopsis with a verb</span></span>
<span data-ttu-id="667ef-124">概要フィールドは、どのようなコマンドレットが、いない何がまたはしくみにユーザーを通知します。</span><span class="sxs-lookup"><span data-stu-id="667ef-124">The synopsis field informs the user what the cmdlet does, not what it is or how it works.</span></span>
<span data-ttu-id="667ef-125">動詞は、このコマンドレットは、その要件を満たしている場合は、ユーザーに通知するタスク ベースのステートメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="667ef-125">Verbs create a task-based statement that informs users if this cmdlet meets their requirements.</span></span>
<span data-ttu-id="667ef-126">"Get"、「作成」、「変更」などの単純な動詞を使用して、</span><span class="sxs-lookup"><span data-stu-id="667ef-126">Use simple verbs like "get", "create", and "change."</span></span>
<span data-ttu-id="667ef-127">回避"set"、「変更」のような漠然と手の込んだの単語があることができます。</span><span class="sxs-lookup"><span data-stu-id="667ef-127">Avoid "set", which can be vague and fancy words like "modify".</span></span>

### <a name="focus-on-objects"></a><span data-ttu-id="667ef-128">オブジェクトに集中します。</span><span class="sxs-lookup"><span data-stu-id="667ef-128">Focus on objects</span></span>
<span data-ttu-id="667ef-129">ほとんど"get"コマンドレットの表示、何かが、その主な機能は、オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="667ef-129">Most "get" cmdlets display something, but their primary function is to get an object.</span></span>
<span data-ttu-id="667ef-130">ヘルプでは、オブジェクト、焦点、既定の表示が、次のいずれかであると、メソッドとそれらのさまざまな方法で取得したオブジェクトのプロパティを使用できるユーザーが理解できるように。</span><span class="sxs-lookup"><span data-stu-id="667ef-130">In your Help, focus on the object, so that users understand that the default display is one of many, and that they can use the methods and properties of the object that you retrieved for them in different ways.</span></span>

### <a name="write-detailed-descriptions"></a><span data-ttu-id="667ef-131">詳細な説明を記述します。</span><span class="sxs-lookup"><span data-stu-id="667ef-131">Write detailed descriptions</span></span>
<span data-ttu-id="667ef-132">簡単に詳細な説明で、コマンドレットを実行できるすべての一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="667ef-132">Briefly list everything that the cmdlet can do in the detailed description.</span></span>
<span data-ttu-id="667ef-133">Main 関数は、1 つのプロパティを変更するのには、コマンドレットは、すべてのプロパティを変更できますが場合、は、これを一覧表示について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="667ef-133">If the main function is to change one property, but the cmdlet can change all properties, list this in the detailed description.</span></span>

### <a name="use-conventional-syntax"></a><span data-ttu-id="667ef-134">従来の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="667ef-134">Use conventional syntax</span></span>
<span data-ttu-id="667ef-135">これは、Windows と UNIX のコマンドライン ヘルプの一般的な標準のバッカスナウア記法形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="667ef-135">Use the standard Backus-Naur format which is common for Windows and UNIX command-line Help.</span></span>

### <a name="use-microsoft-net-framework-types-for-parameter-values"></a><span data-ttu-id="667ef-136">Microsoft .NET Framework の型を使用してパラメーター値</span><span class="sxs-lookup"><span data-stu-id="667ef-136">Use Microsoft .NET Framework types for parameter values</span></span>
<span data-ttu-id="667ef-137">(構文とパラメーターの説明) でパラメーター値のプレース ホルダーをパラメーターを受け入れるオブジェクトの .NET Framework の型を表示します。</span><span class="sxs-lookup"><span data-stu-id="667ef-137">The placeholders for parameter values (in the syntax and parameter descriptions) show the .NET Framework types of the objects that the parameter will accept.</span></span>
<span data-ttu-id="667ef-138">PowerShell チームは、.NET Framework についてユーザーに教えるためには、この規則を開発しました。</span><span class="sxs-lookup"><span data-stu-id="667ef-138">The PowerShell team developed this convention to help teach users about the .NET Framework.</span></span>

### <a name="write-complete-parameter-descriptions"></a><span data-ttu-id="667ef-139">完全なパラメーターの説明を記述します。</span><span class="sxs-lookup"><span data-stu-id="667ef-139">Write complete parameter descriptions</span></span>
<span data-ttu-id="667ef-140">パラメーターの説明を次の 2 つのユーザーに通知する必要があります。 どのようなパラメーターは (効果) と、パラメーター値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="667ef-140">Parameter descriptions must inform users of two things: what the parameter does (its effect) and what they must type for the parameter values.</span></span>

### <a name="write-practical-examples"></a><span data-ttu-id="667ef-141">実際の例を書き込む</span><span class="sxs-lookup"><span data-stu-id="667ef-141">Write practical examples</span></span>
<span data-ttu-id="667ef-142">すべてのパラメーターを使用する方法を例示する必要がありますが、最も重要な点は、実際のタスクでコマンドレットを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="667ef-142">The examples should show how to use all of the parameters, but the most important thing is to show how to use the cmdlet in real-world tasks.</span></span>
<span data-ttu-id="667ef-143">簡単な例を起動し、ますます複雑化のサンプルを記述します。</span><span class="sxs-lookup"><span data-stu-id="667ef-143">Start with a simple example and write increasingly complex examples.</span></span>
<span data-ttu-id="667ef-144">最後の例では、パイプラインでコマンドレットを使用する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="667ef-144">In the final example, show how to use the cmdlet in a pipeline.</span></span>

### <a name="use-the-notes-field"></a><span data-ttu-id="667ef-145">[メモ] フィールドを使用して、</span><span class="sxs-lookup"><span data-stu-id="667ef-145">Use the Notes field</span></span>
<span data-ttu-id="667ef-146">[メモ] フィールドを使用して、ユーザーは、コマンドレットを理解する必要がある概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="667ef-146">Use the Notes field to explain concepts that users need to understand the cmdlet.</span></span>
<span data-ttu-id="667ef-147">ユーザーが一般的なエラーを回避するのにノートを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="667ef-147">You can also use notes to help users avoid common errors.</span></span>
<span data-ttu-id="667ef-148">Url は、変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="667ef-148">Avoid URLs as they change.</span></span>
<span data-ttu-id="667ef-149">代わりに、ユーザーの検索条件を提供します。</span><span class="sxs-lookup"><span data-stu-id="667ef-149">Instead, provide users terms to search for.</span></span>

### <a name="test-your-help"></a><span data-ttu-id="667ef-150">ご協力をテストします。</span><span class="sxs-lookup"><span data-stu-id="667ef-150">Test your Help</span></span>
<span data-ttu-id="667ef-151">コードをテストするのと同じように、ヘルプをテストします。</span><span class="sxs-lookup"><span data-stu-id="667ef-151">Test the Help just like you test your code.</span></span>
<span data-ttu-id="667ef-152">フレンドを指定し、同僚は、ヘルプ コンテンツの読み取りや、フィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="667ef-152">Have friends and colleagues read your Help content and provide feedback.</span></span>
<span data-ttu-id="667ef-153">またニュースグループからのフィードバックを集めることができます。</span><span class="sxs-lookup"><span data-stu-id="667ef-153">You can also solicit feedback from newsgroups.</span></span>

## <a name="see-also"></a><span data-ttu-id="667ef-154">参照</span><span class="sxs-lookup"><span data-stu-id="667ef-154">See Also</span></span>

 [<span data-ttu-id="667ef-155">コマンドレットのヘルプ ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-155">How to Create the Cmdlet Help File</span></span>](./how-to-create-the-cmdlet-help-file.md)

 [<span data-ttu-id="667ef-156">概要とコマンドレットの名前をコマンドレットのヘルプ トピックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-156">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="667ef-157">コマンドレットのヘルプ トピックの詳細な説明を追加する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-157">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="667ef-158">コマンドレットのヘルプ トピックに構文を追加する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-158">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="667ef-159">コマンドレットのヘルプ トピックにパラメーターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-159">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="667ef-160">コマンドレットのヘルプ トピックへの入力型を追加する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-160">How to add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="667ef-161">コマンドレットのヘルプ トピックに戻り値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-161">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="667ef-162">コマンドレットのヘルプ トピックにノートを追加する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-162">How to Add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="667ef-163">コマンドレットのヘルプ トピックの例を追加する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-163">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="667ef-164">コマンドレットのヘルプ トピックに関連するリンクを追加する方法</span><span class="sxs-lookup"><span data-stu-id="667ef-164">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="667ef-165">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="667ef-165">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
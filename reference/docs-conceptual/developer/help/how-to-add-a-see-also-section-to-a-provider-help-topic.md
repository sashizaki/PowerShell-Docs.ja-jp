---
title: プロバイダーヘルプトピックの「関連項目」セクションを追加する方法Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c754ac3-cee3-4c13-9bad-e499c8a68a09
caps.latest.revision: 4
ms.openlocfilehash: b6561120d1bbe848ab4ebcdec7de92c6cad96314
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564825"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a><span data-ttu-id="0d751-102">プロバイダーのヘルプ トピックに関連項目を追加する方法</span><span class="sxs-lookup"><span data-stu-id="0d751-102">How to Add a See Also Section to a Provider Help Topic</span></span>

<span data-ttu-id="0d751-103">このセクションでは、プロバイダーヘルプトピックの **「関連項目」** セクションにデータを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d751-103">This section explains how to populate the **SEE ALSO** section of a provider help topic.</span></span>

<span data-ttu-id="0d751-104">「関連項目」セクションは、プロバイダーに関連するトピックの一覧で構成され**て**います。また、ユーザーがプロバイダーをよりよく理解し、使用するために役立つ場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0d751-104">The **SEE ALSO** section consists of a list of topics that are related to the provider or might help the user better understand and use the provider.</span></span> <span data-ttu-id="0d751-105">トピックの一覧には、Windows PowerShell のヘルプトピック (コマンドレットのヘルプ、プロバイダーのヘルプ、および概念説明の "about") を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0d751-105">The topic list can include cmdlet help, provider help and conceptual ("about") help topics in Windows PowerShell.</span></span> <span data-ttu-id="0d751-106">また、現在のプロバイダーのヘルプトピックのオンラインバージョンを含む、書籍、紙、およびオンラインのトピックへの参照を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d751-106">It can also include references to books, paper, and online topics, including an online version of the current provider help topic.</span></span>

<span data-ttu-id="0d751-107">オンライントピックを参照するときは、プレーンテキストで URI または検索語句を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d751-107">When you refer to online topics, provide the URI or a search term in plain text.</span></span> <span data-ttu-id="0d751-108">コマンドレットでは、 `Get-Help` 一覧のどのトピックにもリンクまたはリダイレクトされません。</span><span class="sxs-lookup"><span data-stu-id="0d751-108">The `Get-Help` cmdlet does not link or redirect to any of the topics in the list.</span></span> <span data-ttu-id="0d751-109">また、 `Online` コマンドレットのパラメーターは、 `Get-Help` プロバイダーのヘルプでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="0d751-109">Also, the `Online` parameter of the `Get-Help` cmdlet does not work with provider help.</span></span>

<span data-ttu-id="0d751-110">「参照」セクションは、 `RelatedLinks` 要素とそれに含まれるタグから作成されます。</span><span class="sxs-lookup"><span data-stu-id="0d751-110">The See Also section is created from the `RelatedLinks` element and the tags that it contains.</span></span> <span data-ttu-id="0d751-111">タグを追加する方法を次の XML に示します。</span><span class="sxs-lookup"><span data-stu-id="0d751-111">The following XML shows how to add the tags.</span></span>

### <a name="to-add-see-also-topics"></a><span data-ttu-id="0d751-112">「関連項目」を追加するには</span><span class="sxs-lookup"><span data-stu-id="0d751-112">To Add "SEE ALSO" Topics</span></span>

1. <span data-ttu-id="0d751-113">Dll-help ファイル*の*要素内に、 `providerHelp` 要素を追加 `RelatedLinks` します。</span><span class="sxs-lookup"><span data-stu-id="0d751-113">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `RelatedLinks` element.</span></span> <span data-ttu-id="0d751-114">要素は、 `RelatedLinks` 要素の最後の要素である必要があり `providerHelp` ます。</span><span class="sxs-lookup"><span data-stu-id="0d751-114">The `RelatedLinks` element should be the last element in the `providerHelp` element.</span></span> <span data-ttu-id="0d751-115">`RelatedLinks`各プロバイダーヘルプトピックでは、1つの要素のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="0d751-115">Only one `RelatedLinks` element is permitted in each provider help topic.</span></span>

   <span data-ttu-id="0d751-116">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0d751-116">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. <span data-ttu-id="0d751-117">**「関連**項目」セクションの各トピックについて、要素内に `RelatedLinks` 要素を追加し `navigationLink` ます。</span><span class="sxs-lookup"><span data-stu-id="0d751-117">For each topic in the **SEE ALSO** section, within the `RelatedLinks` element, add a `navigationLink` element.</span></span> <span data-ttu-id="0d751-118">次に、各 `navigationLink` 要素内に1つの `linkText` 要素と1つの要素を追加し `uri` ます。</span><span class="sxs-lookup"><span data-stu-id="0d751-118">Then, within each `navigationLink` element, add one `linkText` element and one `uri` element.</span></span> <span data-ttu-id="0d751-119">要素を使用していない場合は `uri` 、空の要素 (uri/>) として追加でき \< ます。</span><span class="sxs-lookup"><span data-stu-id="0d751-119">If you are not using the `uri` element, you can add it as an empty element (\<uri/>).</span></span>

   <span data-ttu-id="0d751-120">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0d751-120">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> </linkText>
                <uri> </uri>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```

3. <span data-ttu-id="0d751-121">タグの間にトピック名を入力し `linkText` ます。</span><span class="sxs-lookup"><span data-stu-id="0d751-121">Type the topic name between the `linkText` tags.</span></span> <span data-ttu-id="0d751-122">URI を指定する場合は、タグの間に入力し `uri` ます。</span><span class="sxs-lookup"><span data-stu-id="0d751-122">If you are providing a URI, type it between the `uri` tags.</span></span> <span data-ttu-id="0d751-123">現在のプロバイダーのヘルプトピックのオンラインバージョンを示すには、タグの間に、 `linkText` トピック名の代わりに「online version:」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0d751-123">To indicate the online version of the current provider help topic, between the `linkText` tags, type "Online version:" instead of the topic name.</span></span> <span data-ttu-id="0d751-124">通常、"オンラインバージョン:" リンクは、「関連項目」の一覧の最初のトピックです。</span><span class="sxs-lookup"><span data-stu-id="0d751-124">Typically, the "Online version:" link is the first topic in the SEE ALSO topic list.</span></span>

   <span data-ttu-id="0d751-125">次の例には、3つのトピックも含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d751-125">The following example include three SEE ALSO topics.</span></span> <span data-ttu-id="0d751-126">最初のは、現在のトピックのオンラインバージョンを参照します。</span><span class="sxs-lookup"><span data-stu-id="0d751-126">The first refer to the online version of the current topic.</span></span> <span data-ttu-id="0d751-127">2番目のコマンドレットは、Windows PowerShell コマンドレットのヘルプトピックを参照します。</span><span class="sxs-lookup"><span data-stu-id="0d751-127">The second refers to a Windows PowerShell cmdlet help topic.</span></span> <span data-ttu-id="0d751-128">3番目のトピックでは、別のオンライントピックを参照します。</span><span class="sxs-lookup"><span data-stu-id="0d751-128">The third refers to another online topic.</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> Online version: </linkText>
                <uri>http://www.fabrikam.com/help/myFunction.htm</uri>
            </navigationLink>
            <navigationLink>
                <linkText> about_functions </linkText>
                <uri/>
            </navigationLink>
            <navigationLink>
                <linkText> Windows PowerShell Getting Started Guide </linkText>
                <uri>https://go.microsoft.com/fwlink/?LinkID=89597<uri/>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```

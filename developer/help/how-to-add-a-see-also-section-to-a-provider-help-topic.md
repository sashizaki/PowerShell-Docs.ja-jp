---
title: 追加する方法を参照してくださいもセクション プロバイダーのヘルプ トピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c754ac3-cee3-4c13-9bad-e499c8a68a09
caps.latest.revision: 4
ms.openlocfilehash: f5c48fd04c620828a6e99c5c5424d11b31fd10e5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858348"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a><span data-ttu-id="7f4d3-102">プロバイダーのヘルプ トピックに関連項目を追加する方法</span><span class="sxs-lookup"><span data-stu-id="7f4d3-102">How to Add a See Also Section to a Provider Help Topic</span></span>

<span data-ttu-id="7f4d3-103">このセクションを設定する方法を説明します、**参照**プロバイダーのヘルプ トピックの「します。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-103">This section explains how to populate the **SEE ALSO** section of a provider help topic.</span></span>

<span data-ttu-id="7f4d3-104">**参照**セクションでは、プロバイダーに関連するかよりよく理解し、プロバイダーを使用して、ユーザーに役立つトピックの一覧。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-104">The **SEE ALSO** section consists of a list of topics that are related to the provider or might help the user better understand and use the provider.</span></span> <span data-ttu-id="7f4d3-105">トピックの一覧は、コマンドレットのヘルプ、プロバイダーのヘルプを含めることができます (「about」) ヘルプのトピックでは、Windows PowerShell の概念とします。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-105">The topic list can include cmdlet help, provider help and conceptual ("about") help topics in Windows PowerShell.</span></span> <span data-ttu-id="7f4d3-106">書籍、ホワイト ペーパー、および現在のプロバイダーのヘルプ トピックのオンライン バージョンを含む、オンラインのトピックへの参照型を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-106">It can also include references to books, paper, and online topics, including an online version of the current provider help topic.</span></span>

<span data-ttu-id="7f4d3-107">オンラインのトピックを参照するときに、URI またはプレーン テキストで検索用語を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-107">When you refer to online topics, provide the URI or a search term in plain text.</span></span> <span data-ttu-id="7f4d3-108">`Get-Help`コマンドレットがリンクまたは一覧の各トピックのいずれかにリダイレクトしていません。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-108">The `Get-Help` cmdlet does not link or redirect to any of the topics in the list.</span></span> <span data-ttu-id="7f4d3-109">また、`Online`のパラメーター、`Get-Help`コマンドレットは、プロバイダーのヘルプでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-109">Also, the `Online` parameter of the `Get-Help` cmdlet does not work with provider help.</span></span>

<span data-ttu-id="7f4d3-110">「参照」セクションがから作成された、`RelatedLinks`要素とそれに含まれるタグ。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-110">The See Also section is created from the `RelatedLinks` element and the tags that it contains.</span></span> <span data-ttu-id="7f4d3-111">次の XML では、タグを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-111">The following XML shows how to add the tags.</span></span>

### <a name="to-add-see-also-topics"></a><span data-ttu-id="7f4d3-112">トピックの「参照」を追加するには</span><span class="sxs-lookup"><span data-stu-id="7f4d3-112">To Add "SEE ALSO" Topics</span></span>

1. <span data-ttu-id="7f4d3-113">*AssemblyName*.dll help.xml ファイル内で、`providerHelp`要素を追加、`RelatedLinks`要素。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-113">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `RelatedLinks` element.</span></span> <span data-ttu-id="7f4d3-114">`RelatedLinks`要素の最後の要素があります、`providerHelp`要素。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-114">The `RelatedLinks` element should be the last element in the `providerHelp` element.</span></span> <span data-ttu-id="7f4d3-115">1 つだけ`RelatedLinks`要素は各プロバイダーのヘルプ トピックでは許可します。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-115">Only one `RelatedLinks` element is permitted in each provider help topic.</span></span>

   <span data-ttu-id="7f4d3-116">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-116">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. <span data-ttu-id="7f4d3-117">内の各トピックの**参照**セクション内、`RelatedLinks`要素を追加、`navigationLink`要素。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-117">For each topic in the **SEE ALSO** section, within the `RelatedLinks` element, add a `navigationLink` element.</span></span> <span data-ttu-id="7f4d3-118">その後、各`navigationLink`要素、1 つ追加`linkText`要素と 1 つ`uri`要素。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-118">Then, within each `navigationLink` element, add one `linkText` element and one `uri` element.</span></span> <span data-ttu-id="7f4d3-119">使用していない場合、`uri`要素として追加できますが、空の要素 (\<uri/>)。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-119">If you are not using the `uri` element, you can add it as an empty element (\<uri/>).</span></span>

   <span data-ttu-id="7f4d3-120">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-120">For example:</span></span>

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

3. <span data-ttu-id="7f4d3-121">間トピック名を入力、`linkText`タグ。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-121">Type the topic name between the `linkText` tags.</span></span> <span data-ttu-id="7f4d3-122">URI を提供する場合は、入力間、`uri`タグ。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-122">If you are providing a URI, type it between the `uri` tags.</span></span> <span data-ttu-id="7f4d3-123">現在のプロバイダーのヘルプ トピックのオンライン バージョンを示すために、`linkText`タグ、種類"オンライン バージョン:"トピック名の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-123">To indicate the online version of the current provider help topic, between the `linkText` tags, type "Online version:" instead of the topic name.</span></span> <span data-ttu-id="7f4d3-124">通常、"オンライン バージョン:"リンクは、「参照」トピックの一覧の最初のトピックです。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-124">Typically, the "Online version:" link is the first topic in the SEE ALSO topic list.</span></span>

   <span data-ttu-id="7f4d3-125">次の例には、3 つの参照トピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-125">The following example include three SEE ALSO topics.</span></span> <span data-ttu-id="7f4d3-126">1 つ目は、現在のトピックのオンライン バージョンを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-126">The first refer to the online version of the current topic.</span></span> <span data-ttu-id="7f4d3-127">2 つ目は、Windows PowerShell コマンドレットのヘルプ トピックを参照します。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-127">The second refers to a Windows PowerShell cmdlet help topic.</span></span> <span data-ttu-id="7f4d3-128">3 つ目は、別のオンライン トピックを参照します。</span><span class="sxs-lookup"><span data-stu-id="7f4d3-128">The third refers to another online topic.</span></span>

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
                <uri>http://go.microsoft.com/fwlink/?LinkID=89597<uri/>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```
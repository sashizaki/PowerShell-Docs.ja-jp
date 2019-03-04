---
title: コマンドレットのヘルプ トピックに関連するリンクを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5aadb730-4eb7-4936-b8df-3b0c0ca04fd5
caps.latest.revision: 5
ms.openlocfilehash: aa46cbc5bfcfdfec9fcf9d2581ff641baa532860
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855398"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="ba57e-102">コマンドレットのヘルプ トピックに関連リンクを追加する方法</span><span class="sxs-lookup"><span data-stu-id="ba57e-102">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="ba57e-103">このセクションでは、Windows PowerShell® コマンドレットのヘルプ トピックに関連するその他のコンテンツへの参照を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba57e-103">This section describes how to add references to other content that is related to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="ba57e-104">これらの参照は、コマンド ウィンドウに表示される、ため、参照コンテンツに直接リンクされません。</span><span class="sxs-lookup"><span data-stu-id="ba57e-104">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="ba57e-105">Windows PowerShell® に含まれているコマンドレットのヘルプ トピックでは、これらのリンクは、他のコマンドレット、概念的コンテンツ (「about _」)、およびその他のドキュメントおよび Windows PowerShell® に関連していないヘルプ ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="ba57e-105">In the cmdlet Help topics that are included in Windows PowerShell®, these links reference other cmdlets, conceptual content ("about_"), and other documents and Help files that are not related to Windows PowerShell®.</span></span>

<span data-ttu-id="ba57e-106">次の XML では、関連するトピックへの 2 つの参照を含む RelatedLinks ノードを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ba57e-106">The following XML shows how to add a RelatedLinks node that contains two references to related topics.</span></span>

```xml
<maml:relatedLinks>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
</ maml:relatedLinks >
```




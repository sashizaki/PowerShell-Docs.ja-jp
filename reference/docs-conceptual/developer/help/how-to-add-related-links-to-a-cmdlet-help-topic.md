---
title: コマンドレットに関連するリンクを追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5aadb730-4eb7-4936-b8df-3b0c0ca04fd5
caps.latest.revision: 5
ms.openlocfilehash: 0a6403e2dea16d73e2fdcb8cf5df39b2aa5b5dae
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560272"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="dbce8-102">コマンドレットのヘルプ トピックに関連リンクを追加する方法</span><span class="sxs-lookup"><span data-stu-id="dbce8-102">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="dbce8-103">このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックに関連するその他のコンテンツへの参照を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbce8-103">This section describes how to add references to other content that is related to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="dbce8-104">これらの参照はコマンドウィンドウに表示されるため、参照先のコンテンツに直接リンクされません。</span><span class="sxs-lookup"><span data-stu-id="dbce8-104">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="dbce8-105">Windows PowerShell®に含まれているコマンドレットのヘルプトピックでは、これらのリンクでは、他のコマンドレット、概念コンテンツ ("about_")、および Windows PowerShell®に関連しないその他のドキュメントやヘルプファイルを参照しています。</span><span class="sxs-lookup"><span data-stu-id="dbce8-105">In the cmdlet Help topics that are included in Windows PowerShell®, these links reference other cmdlets, conceptual content ("about_"), and other documents and Help files that are not related to Windows PowerShell®.</span></span>

<span data-ttu-id="dbce8-106">次の XML は、関連トピックへの2つの参照を含む、関係リンクノードを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dbce8-106">The following XML shows how to add a RelatedLinks node that contains two references to related topics.</span></span>

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

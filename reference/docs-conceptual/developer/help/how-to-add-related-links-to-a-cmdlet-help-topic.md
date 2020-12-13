---
ms.date: 09/12/2016
ms.topic: reference
title: コマンドレットのヘルプ トピックに関連リンクを追加する方法
description: コマンドレットのヘルプ トピックに関連リンクを追加する方法
ms.openlocfilehash: 7f1baefea69310bdf835c52461f8d3f49c4d94e8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662005"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a><span data-ttu-id="e0efb-103">コマンドレットのヘルプ トピックに関連リンクを追加する方法</span><span class="sxs-lookup"><span data-stu-id="e0efb-103">How to Add Related Links to a Cmdlet Help Topic</span></span>

<span data-ttu-id="e0efb-104">このセクションでは、PowerShell コマンドレットのヘルプトピックに関連するその他のコンテンツへの参照を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0efb-104">This section describes how to add references to other content that is related to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="e0efb-105">これらの参照はコマンドウィンドウに表示されるため、参照先のコンテンツに直接リンクされません。</span><span class="sxs-lookup"><span data-stu-id="e0efb-105">Because these references appear in a command window, they do not link directly to the referenced content.</span></span>

<span data-ttu-id="e0efb-106">PowerShell に含まれているコマンドレットのヘルプトピックでは、これらのリンクは、PowerShell に関連しない他のコマンドレット、概念説明コンテンツ ( `about_` )、およびその他のドキュメントやヘルプファイルを参照しています。</span><span class="sxs-lookup"><span data-stu-id="e0efb-106">In the cmdlet Help topics that are included in PowerShell, these links reference other cmdlets, conceptual content (`about_`), and other documents and Help files that are not related to PowerShell.</span></span>

<span data-ttu-id="e0efb-107">次の XML は、関連トピックへの2つの参照を含む、関係 **リンク** ノードを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0efb-107">The following XML shows how to add a **RelatedLinks** node that contains two references to related topics.</span></span>

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

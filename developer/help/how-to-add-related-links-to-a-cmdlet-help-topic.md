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
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに関連リンクを追加する方法

このセクションでは、Windows PowerShell® コマンドレットのヘルプ トピックに関連するその他のコンテンツへの参照を追加する方法について説明します。 これらの参照は、コマンド ウィンドウに表示される、ため、参照コンテンツに直接リンクされません。

Windows PowerShell® に含まれているコマンドレットのヘルプ トピックでは、これらのリンクは、他のコマンドレット、概念的コンテンツ (「about _」)、およびその他のドキュメントおよび Windows PowerShell® に関連していないヘルプ ファイルを参照します。

次の XML では、関連するトピックへの 2 つの参照を含む RelatedLinks ノードを追加する方法を示します。

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




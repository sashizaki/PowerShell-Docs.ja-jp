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
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに関連リンクを追加する方法

このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックに関連するその他のコンテンツへの参照を追加する方法について説明します。 これらの参照はコマンドウィンドウに表示されるため、参照先のコンテンツに直接リンクされません。

Windows PowerShell®に含まれているコマンドレットのヘルプトピックでは、これらのリンクでは、他のコマンドレット、概念コンテンツ ("about_")、および Windows PowerShell®に関連しないその他のドキュメントやヘルプファイルを参照しています。

次の XML は、関連トピックへの2つの参照を含む、関係リンクノードを追加する方法を示しています。

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

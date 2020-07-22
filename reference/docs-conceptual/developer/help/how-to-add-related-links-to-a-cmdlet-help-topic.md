---
title: コマンドレットのヘルプ トピックに関連リンクを追加する方法
ms.date: 09/12/2016
ms.openlocfilehash: 7557b3856d8470434070dd286cd7e30c9ba015c5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893375"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに関連リンクを追加する方法

このセクションでは、PowerShell コマンドレットのヘルプトピックに関連するその他のコンテンツへの参照を追加する方法について説明します。 これらの参照はコマンドウィンドウに表示されるため、参照先のコンテンツに直接リンクされません。

PowerShell に含まれているコマンドレットのヘルプトピックでは、これらのリンクは、PowerShell に関連しない他のコマンドレット、概念説明コンテンツ ( `about_` )、およびその他のドキュメントやヘルプファイルを参照しています。

次の XML は、関連トピックへの2つの参照を含む、関係**リンク**ノードを追加する方法を示しています。

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

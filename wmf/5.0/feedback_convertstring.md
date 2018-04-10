---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 302a347b0f4c9c322f7701e8d6a721f9ffba9b59
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="convert-string"></a>Convert-String
**Convert-String** は、"マジックによる置換" 機能を公開しています。 テキストの変換前と変換後のサンプルを提供すれば、**Convert-String** がテキストの書式を自動的に設定します。 1 つのデモを紹介します。人名の名と姓を、姓、コンマ、姓の先頭文字とドットに置き換えます。 これを正規表現で実現するとしたら、どれほど長時間を要するか考えてみてください。

```powershell
"Lee Holmes", "Steve Lee", "Jeffrey Snover" | Convert-String -Example "Bill Gates=Gates, B.","John Smith=Smith, J."

Holmes, L.
Lee, S.
Snover, J.
```
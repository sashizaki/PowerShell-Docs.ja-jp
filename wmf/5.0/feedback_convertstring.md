---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 6caff8c06174a1dcb990ed8e5062ccca5848dbb8
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="convert-string" class="xliff"></a>

# Convert-String
**Convert-String** は、"マジックによる置換" 機能を公開しています。 テキストの変換前と変換後のサンプルを提供すれば、**Convert-String** がテキストの書式を自動的に設定します。 1 つのデモを紹介します。人名の名と姓を、姓、コンマ、姓の先頭文字とドットに置き換えます。 これを正規表現で実現するとしたら、どれほど長時間を要するか考えてみてください。

```powershell
"Lee Holmes", "Steve Lee", "Jeffrey Snover" | Convert-String -Example "Bill Gates=Gates, B.","John Smith=Smith, J."

Holmes, L.
Lee, S.
Snover, J.
```


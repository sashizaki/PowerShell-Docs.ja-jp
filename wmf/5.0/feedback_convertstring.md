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
# <a name="convert-string"></a><span data-ttu-id="6bdaf-102">Convert-String</span><span class="sxs-lookup"><span data-stu-id="6bdaf-102">Convert-String</span></span>
<span data-ttu-id="6bdaf-103">**Convert-String** は、"マジックによる置換" 機能を公開しています。</span><span class="sxs-lookup"><span data-stu-id="6bdaf-103">**Convert-String** exposes "replace by magic" functionality.</span></span> <span data-ttu-id="6bdaf-104">テキストの変換前と変換後のサンプルを提供すれば、**Convert-String** がテキストの書式を自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="6bdaf-104">Provide before and after examples of how you want text to look, and **Convert-String** formats your text automatically.</span></span> <span data-ttu-id="6bdaf-105">1 つのデモを紹介します。人名の名と姓を、姓、コンマ、姓の先頭文字とドットに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6bdaf-105">Here's a demo - taking somebody's first and last name, and replacing it with their last name, a comma, the first initial of their last name, and a dot.</span></span> <span data-ttu-id="6bdaf-106">これを正規表現で実現するとしたら、どれほど長時間を要するか考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="6bdaf-106">Try it with a regex, and see how long it takes you.</span></span>

```powershell
"Lee Holmes", "Steve Lee", "Jeffrey Snover" | Convert-String -Example "Bill Gates=Gates, B.","John Smith=Smith, J."

Holmes, L.
Lee, S.
Snover, J.
```


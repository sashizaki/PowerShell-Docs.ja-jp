---
ms.date: 10/20/2020
ms.topic: reference
title: コマンドレットのヘルプ トピックに注を追加する方法
description: コマンドレットのヘルプ トピックに注を追加する方法
ms.openlocfilehash: 61363c26ab0172277d1332ed1e9de080d8da200c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92659564"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="791f5-103">コマンドレットのヘルプ トピックに注を追加する方法</span><span class="sxs-lookup"><span data-stu-id="791f5-103">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="791f5-104">このセクションでは、PowerShell コマンドレットのヘルプ トピックに **注** セクションを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="791f5-104">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="791f5-105">**注** セクションは、パラメーターの詳細な説明など、他の構造化されたセクションには当てはまりにくい詳細を説明するために使用します。</span><span class="sxs-lookup"><span data-stu-id="791f5-105">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="791f5-106">その内容には、特定のプロバイダーでのコマンドレットの動作、コマンドレットの独自かつ重要な使用方法、または想定されるエラー条件の回避方法に関するコメントなどを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="791f5-106">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="791f5-107">**注** セクションは、1 つの `<maml:alertset>` ノードを使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="791f5-107">The **NOTES** section is defined using a single `<maml:alertset>` node.</span></span> <span data-ttu-id="791f5-108">注セクションに追加できる注の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="791f5-108">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="791f5-109">注ごとに、`<maml:alertset>` ノードに `<maml:alert>` タグのペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="791f5-109">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="791f5-110">それぞれの注の内容は、一連の `<maml:para>` タグ内に追加します。</span><span class="sxs-lookup"><span data-stu-id="791f5-110">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="791f5-111">スペースに対しては空の `<maml:para>` タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="791f5-111">Use blank `<maml:para>` tags for spacing.</span></span>

```xml
<maml:alertSet>
  <maml:title>Optional title for Note</maml:title>
  <maml:alert>
    <maml:para>Note 1</maml:para>
    <maml:para>Note a</maml:para>
  </maml:alert>
  <maml:alert>
    <maml:para>Note 2</maml:para>
  </maml:alert>
</maml:alertSet>
```

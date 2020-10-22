---
title: コマンドレットのヘルプ トピックに注を追加する方法
ms.date: 10/20/2020
ms.openlocfilehash: 7f8be34a82de2c12cfd2a05deed139ddb30da95f
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "92298305"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="5bdc7-102">コマンドレットのヘルプ トピックに注を追加する方法</span><span class="sxs-lookup"><span data-stu-id="5bdc7-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="5bdc7-103">このセクションでは、PowerShell コマンドレットのヘルプ トピックに**注**セクションを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bdc7-103">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="5bdc7-104">**注**セクションは、パラメーターの詳細な説明など、他の構造化されたセクションには当てはまりにくい詳細を説明するために使用します。</span><span class="sxs-lookup"><span data-stu-id="5bdc7-104">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="5bdc7-105">その内容には、特定のプロバイダーでのコマンドレットの動作、コマンドレットの独自かつ重要な使用方法、または想定されるエラー条件の回避方法に関するコメントなどを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5bdc7-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="5bdc7-106">**注**セクションは、1 つの `<maml:alertset>` ノードを使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="5bdc7-106">The **NOTES** section is defined using a single `<maml:alertset>` node.</span></span> <span data-ttu-id="5bdc7-107">注セクションに追加できる注の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="5bdc7-107">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="5bdc7-108">注ごとに、`<maml:alertset>` ノードに `<maml:alert>` タグのペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="5bdc7-108">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="5bdc7-109">それぞれの注の内容は、一連の `<maml:para>` タグ内に追加します。</span><span class="sxs-lookup"><span data-stu-id="5bdc7-109">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="5bdc7-110">スペースに対しては空の `<maml:para>` タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="5bdc7-110">Use blank `<maml:para>` tags for spacing.</span></span>

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

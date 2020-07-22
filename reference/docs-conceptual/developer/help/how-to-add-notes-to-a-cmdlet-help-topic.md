---
title: コマンドレットのヘルプ トピックに注を追加する方法
ms.date: 09/12/2016
ms.openlocfilehash: d3679126ea34d7e86bcda700d0d050d8312a7aa2
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893409"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="88b93-102">コマンドレットのヘルプ トピックに注を追加する方法</span><span class="sxs-lookup"><span data-stu-id="88b93-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="88b93-103">このセクションでは、PowerShell コマンドレットのヘルプトピックに**メモ**セクションを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88b93-103">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="88b93-104">**メモ**セクションは、パラメーターの詳細な説明など、他の構造化されたセクションに簡単に適合しない詳細を説明するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="88b93-104">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="88b93-105">このコンテンツには、特定のプロバイダーを使用したコマンドレットの動作、一意であることが重要なコマンドレットの使用方法、またはエラー状態の発生を回避する方法に関するコメントが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="88b93-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="88b93-106">メモセクションに追加できるノートの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="88b93-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="88b93-107">各ノートについて、ノードに1組のタグを追加し `<maml:alert>` `<maml:alertset>` ます。</span><span class="sxs-lookup"><span data-stu-id="88b93-107">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="88b93-108">各ノートの内容は、一連のタグ内に追加され `<maml:para>` ます。</span><span class="sxs-lookup"><span data-stu-id="88b93-108">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="88b93-109">空白 `<maml:para>` タグをスペースに使用します。</span><span class="sxs-lookup"><span data-stu-id="88b93-109">Use blank `<maml:para>` tags for spacing.</span></span>

<span data-ttu-id="88b93-110">次の XML は、 `<maml:alertset>` 2 つのノートを持つノードを示しています。</span><span class="sxs-lookup"><span data-stu-id="88b93-110">The following XML shows an `<maml:alertset>` node with two notes.</span></span> <span data-ttu-id="88b93-111">各メモには省略可能な `<maml:title>` タグ (タイトルを使用してタグのセットをグループ化することができます) があり、各ノートには、 `<maml:alert>` スペースのコンテンツの後に空白行があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="88b93-111">Notice that each note has an optional `<maml:title>` tag (titles can be used to group any set of `<maml:alert>` tags), and that each note has a blank line following the content for spacing.</span></span>

```xml
<maml:alertSet>
  <maml:title>title for Note 1</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
  <maml:title>title for Note 2</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
</maml:alertSet>
```

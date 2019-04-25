---
title: コマンドレットのヘルプ トピックにメモを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083418"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="f2dfa-102">コマンドレットのヘルプ トピックに注を追加する方法</span><span class="sxs-lookup"><span data-stu-id="f2dfa-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="f2dfa-103">このセクションでは、Windows PowerShell® コマンドレットのヘルプ トピックをノートのセクションを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-103">This section describes how to add a Notes section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="f2dfa-104">ノートのセクションは、パラメーターの詳細な説明など、他の構造化されたセクションに簡単に適合しない詳細の説明に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-104">The Notes section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="f2dfa-105">このコンテンツは、特定のプロバイダーとコマンドレットがどのように連携するか、コマンドレット、またはエラー状況を回避する方法のいくつか一意、ながらも重要なの使用に関するコメントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="f2dfa-106">ノートのセクションに追加できるノートの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="f2dfa-107">各のメモの追加のペア\<maml:alert > タグを\<maml:alertset > ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-107">For each note, add a pair of \<maml:alert> tags to the \<maml:alertset> node.</span></span> <span data-ttu-id="f2dfa-108">各メモの内容は、一連の追加\<maml:para > タグです。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-108">The content of each note is added within a set of \<maml:para> tags.</span></span> <span data-ttu-id="f2dfa-109">使用して空白\<maml:para > タグの間隔をします。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-109">Use blank \<maml:para> tags for spacing.</span></span>

<span data-ttu-id="f2dfa-110">次の XML に示します、 \<maml:alertset > ノードに 2 つのメモ。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-110">The following XML shows an \<maml:alertset> node with two notes.</span></span> <span data-ttu-id="f2dfa-111">各メモが省略可能なことに注意してください\<maml:title > タグ (タイトルは、任意のセットをグループ化に使用できる\<maml:alert > タグ)、および間隔のコンテンツを次の空白行が各に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-111">Notice that each note has an optional \<maml:title> tag (titles can be used to group any set of \<maml:alert> tags), and that each note has a blank line following the content for spacing.</span></span>

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




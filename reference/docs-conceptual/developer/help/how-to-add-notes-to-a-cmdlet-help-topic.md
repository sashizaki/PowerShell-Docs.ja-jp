---
title: コマンドレットにメモを追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361271"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="581c1-102">コマンドレットのヘルプ トピックに注を追加する方法</span><span class="sxs-lookup"><span data-stu-id="581c1-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="581c1-103">このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックにメモセクションを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="581c1-103">This section describes how to add a Notes section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="581c1-104">メモセクションは、パラメーターの詳細な説明など、他の構造化されたセクションに簡単に適合しない詳細を説明するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="581c1-104">The Notes section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="581c1-105">このコンテンツには、特定のプロバイダーを使用したコマンドレットの動作、一意であることが重要なコマンドレットの使用方法、またはエラー状態の発生を回避する方法に関するコメントが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="581c1-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="581c1-106">メモセクションに追加できるノートの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="581c1-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="581c1-107">メモごとに、maml: alert > タグのペアを \<maml: alertset > ノードに追加 \<ます。</span><span class="sxs-lookup"><span data-stu-id="581c1-107">For each note, add a pair of \<maml:alert> tags to the \<maml:alertset> node.</span></span> <span data-ttu-id="581c1-108">各ノートの内容は \<maml: 段落 > タグのセット内に追加されます。</span><span class="sxs-lookup"><span data-stu-id="581c1-108">The content of each note is added within a set of \<maml:para> tags.</span></span> <span data-ttu-id="581c1-109">スペースには、空白の \<maml: 段落 > タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="581c1-109">Use blank \<maml:para> tags for spacing.</span></span>

<span data-ttu-id="581c1-110">次の XML は、\<maml: alertset > ノードと2つのメモを示しています。</span><span class="sxs-lookup"><span data-stu-id="581c1-110">The following XML shows an \<maml:alertset> node with two notes.</span></span> <span data-ttu-id="581c1-111">各ノートにはオプションの \<maml: title > タグがあります (タイトルは、\<maml: alert > タグの任意のセットをグループ化するために使用できます)。また、各ノートには、スペースのコンテンツの後に空白行があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="581c1-111">Notice that each note has an optional \<maml:title> tag (titles can be used to group any set of \<maml:alert> tags), and that each note has a blank line following the content for spacing.</span></span>

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




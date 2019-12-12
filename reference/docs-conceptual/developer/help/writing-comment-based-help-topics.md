---
title: コメントベースのヘルプトピックの記述 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e619ab16-90ad-46e9-9bde-d6dce492ba56
caps.latest.revision: 4
ms.openlocfilehash: e3d32f36b597088abc41e229bb0955c1b25504e6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361081"
---
# <a name="writing-comment-based-help-topics"></a><span data-ttu-id="8dab3-102">コメントベースのヘルプ トピックを記述する</span><span class="sxs-lookup"><span data-stu-id="8dab3-102">Writing Comment-Based Help Topics</span></span>

<span data-ttu-id="8dab3-103">特別なヘルプコメントキーワードを使用して、関数およびスクリプトのコメントベースのヘルプトピックを記述できます。</span><span class="sxs-lookup"><span data-stu-id="8dab3-103">You can write comment-based Help topics for functions and scripts by using special Help comment keywords.</span></span>

 <span data-ttu-id="8dab3-104">`Get-Help` コマンドレットは、XML ファイルから生成されたコマンドレットヘルプトピックを表示するのと同じ形式で、コメントベースのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="8dab3-104">The `Get-Help` cmdlet displays comment-based Help in the same format in which it displays the cmdlet Help topics that are generated from XML files.</span></span> <span data-ttu-id="8dab3-105">ユーザーは、Detailed、Full、Example、Online などの `Get-Help`のすべてのパラメーターを使用して、関数やスクリプトのヘルプを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8dab3-105">Users can use all of the parameters of `Get-Help`, such as Detailed, Full, Example, and Online, to display function and script Help.</span></span>

 <span data-ttu-id="8dab3-106">また、スクリプトや関数の XML ベースのヘルプトピックを記述し、ヘルプコメントキーワードを使用して、XML ベースのトピックやその他のトピックにユーザーをリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8dab3-106">You can also write XML-based Help topics for scripts and functions and use the Help comment keywords to redirect users to the XML-based topics or other topics.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8dab3-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8dab3-107">In This Section</span></span>

 <span data-ttu-id="8dab3-108">[コメントベースのヘルプの構文](./syntax-of-comment-based-help.md)コメントベースのヘルプの構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="8dab3-108">[Syntax of Comment-Based Help](./syntax-of-comment-based-help.md) Describes the syntax of comment-based help.</span></span>

 <span data-ttu-id="8dab3-109">[コメントベースのヘルプキーワード](./comment-based-help-keywords.md)コメントベースのヘルプのキーワードの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8dab3-109">[Comment-Based Help Keywords](./comment-based-help-keywords.md) Lists the keywords in comment-based help.</span></span>

 <span data-ttu-id="8dab3-110">[関数にコメントベースのヘルプを配置](./placing-comment-based-help-in-functions.md)する関数のコメントベースのヘルプを配置する場所を示します。</span><span class="sxs-lookup"><span data-stu-id="8dab3-110">[Placing Comment-Based Help in Functions](./placing-comment-based-help-in-functions.md) Shows where to place comment-based help for a function.</span></span>

 <span data-ttu-id="8dab3-111">[スクリプトにコメントベースのヘルプを配置](./placing-comment-based-help-in-scripts.md)するスクリプトのコメントベースのヘルプを配置する場所を示します。</span><span class="sxs-lookup"><span data-stu-id="8dab3-111">[Placing Comment-Based Help in Scripts](./placing-comment-based-help-in-scripts.md) Shows where to place comment-based help for a script.</span></span>
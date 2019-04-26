---
title: ヘルプ トピックのコメント ベースの書き込み |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e619ab16-90ad-46e9-9bde-d6dce492ba56
caps.latest.revision: 4
ms.openlocfilehash: e3d32f36b597088abc41e229bb0955c1b25504e6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083180"
---
# <a name="writing-comment-based-help-topics"></a><span data-ttu-id="3ddf5-102">コメントベースのヘルプ トピックを記述する</span><span class="sxs-lookup"><span data-stu-id="3ddf5-102">Writing Comment-Based Help Topics</span></span>

<span data-ttu-id="3ddf5-103">ヘルプ コメントの特別なキーワードを使用して、関数やスクリプトのコメント ベースのヘルプ トピックを記述できます。</span><span class="sxs-lookup"><span data-stu-id="3ddf5-103">You can write comment-based Help topics for functions and scripts by using special Help comment keywords.</span></span>

 <span data-ttu-id="3ddf5-104">`Get-Help`コマンドレットは、XML ファイルから生成されるコマンドレットのヘルプ トピックが表示されますが、同じ形式でコメント ベースのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="3ddf5-104">The `Get-Help` cmdlet displays comment-based Help in the same format in which it displays the cmdlet Help topics that are generated from XML files.</span></span> <span data-ttu-id="3ddf5-105">ユーザーは、すべてのパラメーターを使用できます`Get-Help`Detailed、Full、例では、および関数を表示し、スクリプトのヘルプ オンラインなど。</span><span class="sxs-lookup"><span data-stu-id="3ddf5-105">Users can use all of the parameters of `Get-Help`, such as Detailed, Full, Example, and Online, to display function and script Help.</span></span>

 <span data-ttu-id="3ddf5-106">スクリプトや関数のヘルプ トピックを XML ベースの書き込みし、ヘルプ コメント キーワードを使用して、XML ベースのトピックや他のトピックにユーザーをリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3ddf5-106">You can also write XML-based Help topics for scripts and functions and use the Help comment keywords to redirect users to the XML-based topics or other topics.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3ddf5-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3ddf5-107">In This Section</span></span>

 <span data-ttu-id="3ddf5-108">[コメント ベースのヘルプの構文](./syntax-of-comment-based-help.md)コメント ベースのヘルプの構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ddf5-108">[Syntax of Comment-Based Help](./syntax-of-comment-based-help.md) Describes the syntax of comment-based help.</span></span>

 <span data-ttu-id="3ddf5-109">[ヘルプのキーワードのコメント ベース](./comment-based-help-keywords.md)コメント ベースのヘルプのキーワードを示します。</span><span class="sxs-lookup"><span data-stu-id="3ddf5-109">[Comment-Based Help Keywords](./comment-based-help-keywords.md) Lists the keywords in comment-based help.</span></span>

 <span data-ttu-id="3ddf5-110">[関数のコメント ベースのヘルプを配置する](./placing-comment-based-help-in-functions.md)関数のコメント ベースのヘルプを配置する場所を示します。</span><span class="sxs-lookup"><span data-stu-id="3ddf5-110">[Placing Comment-Based Help in Functions](./placing-comment-based-help-in-functions.md) Shows where to place comment-based help for a function.</span></span>

 <span data-ttu-id="3ddf5-111">[スクリプトにコメント ベースのヘルプを配置する](./placing-comment-based-help-in-scripts.md)スクリプトのコメント ベースのヘルプを配置する場所を示します。</span><span class="sxs-lookup"><span data-stu-id="3ddf5-111">[Placing Comment-Based Help in Scripts](./placing-comment-based-help-in-scripts.md) Shows where to place comment-based help for a script.</span></span>
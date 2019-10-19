---
title: コマンドレット名と概要をコマンドレットに追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d0e1eb1-a962-4406-9625-175cfa3364ad
caps.latest.revision: 10
ms.openlocfilehash: f142548be473da15e702f4fa01835609d75b9d51
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361191"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="2d2e9-102">コマンドレットのヘルプ トピックにコマンドレットの名前と概要を追加する方法</span><span class="sxs-lookup"><span data-stu-id="2d2e9-102">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="2d2e9-103">このセクションでは、コマンドレットのヘルプの [名前] セクションと [概要] セクションに表示されるコンテンツを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-103">This section describes how to add content that is displayed in the NAME and SYNOPSIS sections of the cmdlet help.</span></span> <span data-ttu-id="2d2e9-104">ヘルプファイルでは、各コマンドレットのコマンドノードにこのコンテンツが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="2d2e9-105">ヘルプファイルの完全なビューを表示するには、Windows PowerShell のインストールディレクトリにあるいずれかの dll-Help ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="2d2e9-106">たとえば、dll-Help ファイルには、いくつかの Windows PowerShell コマンドレットのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="2d2e9-107">コマンドレット名と概要を追加するには</span><span class="sxs-lookup"><span data-stu-id="2d2e9-107">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="2d2e9-108">コマンドレットのヘルプには、コマンドレットの2つの説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-108">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="2d2e9-109">最初の説明は、簡単な説明です。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-109">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="2d2e9-110">2番目の説明では、詳細な説明を[コマンドレットヘルプトピックに追加](./how-to-add-a-cmdlet-description.md)する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-110">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span> <span data-ttu-id="2d2e9-111">これらの説明は、両方とも1つの段落として記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-111">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="2d2e9-112">ここでは、コマンドレット名を繰り返しません。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-112">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="2d2e9-113">Get Server コマンドレットがサーバーを取得することをユーザーに通知しますが、情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-113">Informing the user that the Get-Server cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="2d2e9-114">代わりに、シノニムを使用し、詳細を説明に追加します。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-114">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="2d2e9-115">例: "ローカルコンピューターまたはリモートコンピューターを表すオブジェクトを取得します。"</span><span class="sxs-lookup"><span data-stu-id="2d2e9-115">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="2d2e9-116">"Get"、"create"、"change" のような単純な動詞を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-116">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="2d2e9-117">"Set" はあいまいであるため、"modify" などの凝った単語は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-117">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="2d2e9-118">例: "ファイル内の Authenticode 署名に関する情報を取得します。"</span><span class="sxs-lookup"><span data-stu-id="2d2e9-118">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="2d2e9-119">アクティブな音声で書き込みます。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-119">Write in active voice.</span></span> <span data-ttu-id="2d2e9-120">たとえば、"TimeSpan オブジェクトの使用...""TimeSpan オブジェクトを使用して..." を</span><span class="sxs-lookup"><span data-stu-id="2d2e9-120">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="2d2e9-121">オブジェクトを取得するコマンドレットを記述するときは、動詞 "display" を避けてください。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-121">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="2d2e9-122">Windows PowerShell にはコマンドレットのデータが表示されますが、このコマンドレットによって返されるデータが表示されない .NET Framework オブジェクトが返されるという概念をユーザーに紹介することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-122">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="2d2e9-123">表示を強調すると、コマンドレットで表示されない他の便利なプロパティやメソッドが多数返された可能性があることをユーザーが認識できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d2e9-123">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d2e9-124">参照</span><span class="sxs-lookup"><span data-stu-id="2d2e9-124">See Also</span></span>

 [<span data-ttu-id="2d2e9-125">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="2d2e9-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
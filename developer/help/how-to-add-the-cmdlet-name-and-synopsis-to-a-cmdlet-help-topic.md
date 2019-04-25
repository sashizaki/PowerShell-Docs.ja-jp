---
title: 概要とコマンドレットの名前をコマンドレットのヘルプ トピックを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d0e1eb1-a962-4406-9625-175cfa3364ad
caps.latest.revision: 10
ms.openlocfilehash: f142548be473da15e702f4fa01835609d75b9d51
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083339"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="9cf89-102">コマンドレットのヘルプ トピックにコマンドレットの名前と概要を追加する方法</span><span class="sxs-lookup"><span data-stu-id="9cf89-102">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="9cf89-103">このセクションでは、名前と概要セクションでは、コマンドレットのヘルプに表示されるコンテンツを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cf89-103">This section describes how to add content that is displayed in the NAME and SYNOPSIS sections of the cmdlet help.</span></span> <span data-ttu-id="9cf89-104">ヘルプ ファイルでこのコンテンツは、各コマンドレットのコマンドのノードに追加されます。</span><span class="sxs-lookup"><span data-stu-id="9cf89-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="9cf89-105">ヘルプ ファイル、開いている Windows PowerShell のインストール ディレクトリにある dll Help.xml ファイルの 1 つの完全なビュー。</span><span class="sxs-lookup"><span data-stu-id="9cf89-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="9cf89-106">たとえば、Microsoft.PowerShell.Commands.Management.dll Help.xml ファイルには、Windows PowerShell コマンドレットのいくつかのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9cf89-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="9cf89-107">コマンドレット名と概要を追加するには</span><span class="sxs-lookup"><span data-stu-id="9cf89-107">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="9cf89-108">コマンドレットのヘルプには、コマンドレットの 2 つの説明を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9cf89-108">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="9cf89-109">最初の説明は、概要として参照される簡単な説明です。</span><span class="sxs-lookup"><span data-stu-id="9cf89-109">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="9cf89-110">2 番目の説明に記載されているより詳細な説明は、[コマンドレットのヘルプ トピックの詳細な説明を追加する](./how-to-add-a-cmdlet-description.md)します。</span><span class="sxs-lookup"><span data-stu-id="9cf89-110">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span> <span data-ttu-id="9cf89-111">段落を 1 つとして、これら両方の説明を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cf89-111">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="9cf89-112">概要でコマンドレット名を繰り返されません。</span><span class="sxs-lookup"><span data-stu-id="9cf89-112">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="9cf89-113">Get-server コマンドレットが、サーバーを取得することをユーザーに通知は、簡単な有益です。</span><span class="sxs-lookup"><span data-stu-id="9cf89-113">Informing the user that the Get-Server cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="9cf89-114">代わりに、シノニムを使用し、詳細説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="9cf89-114">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="9cf89-115">次に例を示します。「ローカルまたはリモート コンピューターを表すオブジェクトを取得します。」</span><span class="sxs-lookup"><span data-stu-id="9cf89-115">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="9cf89-116">"Get"、「作成」、および概要には、「変更」などの単純な動詞を使用します。</span><span class="sxs-lookup"><span data-stu-id="9cf89-116">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="9cf89-117">不明瞭な言葉を飾るなど「を変更します」ため、"set"を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9cf89-117">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="9cf89-118">次に例を示します。「ファイルの Authenticode 署名に関する情報を取得」します。</span><span class="sxs-lookup"><span data-stu-id="9cf89-118">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="9cf89-119">能動態で記述します。</span><span class="sxs-lookup"><span data-stu-id="9cf89-119">Write in active voice.</span></span> <span data-ttu-id="9cf89-120">たとえば、「オブジェクトを使用して、TimeSpan...」「TimeSpan オブジェクトできますを使用して...」方が明確には</span><span class="sxs-lookup"><span data-stu-id="9cf89-120">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="9cf89-121">オブジェクトを取得するコマンドレットを記述するときは、「表示」動詞を回避します。</span><span class="sxs-lookup"><span data-stu-id="9cf89-121">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="9cf89-122">Windows PowerShell には、コマンドレットのデータが表示されますは、コマンドレットは、データが表示されないことが .NET Framework オブジェクトを返す概念にユーザーを導入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cf89-122">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="9cf89-123">表示を強調する場合、ユーザー気付かない可能性があります、コマンドレットから返されたその他の多くの便利なプロパティやメソッドが表示されていないこと。</span><span class="sxs-lookup"><span data-stu-id="9cf89-123">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cf89-124">参照</span><span class="sxs-lookup"><span data-stu-id="9cf89-124">See Also</span></span>

 [<span data-ttu-id="9cf89-125">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="9cf89-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
---
title: コマンドレットの説明を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47af9d57-bd63-4596-816a-0b717418476b
caps.latest.revision: 10
ms.openlocfilehash: a2e4c4d42566d5a52006924eab02295c37cf3159
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083520"
---
# <a name="how-to-add-a-cmdlet-description"></a><span data-ttu-id="f0759-102">コマンドレットの説明を追加する方法</span><span class="sxs-lookup"><span data-stu-id="f0759-102">How to Add a Cmdlet Description</span></span>

<span data-ttu-id="f0759-103">このセクションでは、コマンドレットのヘルプの [説明] セクションに表示されるコンテンツを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0759-103">This section describes how to add content that is displayed in the DESCRIPTION section of the cmdlet Help.</span></span> <span data-ttu-id="f0759-104">ヘルプ ファイルでこのコンテンツは、各コマンドレットのコマンドのノードに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f0759-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="f0759-105">ヘルプ ファイル、開いている Windows PowerShell のインストール ディレクトリにある dll Help.xml ファイルの 1 つの完全なビュー。</span><span class="sxs-lookup"><span data-stu-id="f0759-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="f0759-106">たとえば、Microsoft.PowerShell.Commands.Management.dll Help.xml ファイルには、Windows PowerShell コマンドレットのいくつかのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0759-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-a-description"></a><span data-ttu-id="f0759-107">説明を追加するには</span><span class="sxs-lookup"><span data-stu-id="f0759-107">To Add a Description</span></span>

- <span data-ttu-id="f0759-108">さらに詳しくコマンドレットの基本的な機能の説明から始めます。</span><span class="sxs-lookup"><span data-stu-id="f0759-108">Begin by explaining the basic features of the cmdlet in more detail.</span></span> <span data-ttu-id="f0759-109">多くの場合は、コマンドレット名で使用される用語について説明し、例を使用して未知の概念を説明します。</span><span class="sxs-lookup"><span data-stu-id="f0759-109">In many cases, you can explain the terms used in the cmdlet name and illustrate unfamiliar concepts with an example.</span></span> <span data-ttu-id="f0759-110">たとえば、コマンドレットでデータをファイルに追加すると場合、は、既存のファイルの末尾にデータが追加されることを説明します。</span><span class="sxs-lookup"><span data-stu-id="f0759-110">For example, if the cmdlet appends data to a file, explain that it adds data to the end of an existing file.</span></span>

- <span data-ttu-id="f0759-111">すべてのコマンドレットの機能を検索するには、パラメーター リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0759-111">To find all of the features of the cmdlet, review the parameter list.</span></span> <span data-ttu-id="f0759-112">コマンドレットの主な機能について説明し、その他の機能と機能します。</span><span class="sxs-lookup"><span data-stu-id="f0759-112">Describe the primary function of the cmdlet, and then include other functions and features.</span></span> <span data-ttu-id="f0759-113">たとえば、コマンドレットの主な機能が 1 つのプロパティを変更するのには、コマンドレットがすべてのプロパティを変更する場合は、そのように言ってについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="f0759-113">For example, if the main function of the cmdlet is to change one property, but the cmdlet can change all of the properties, say so in the detailed description.</span></span> <span data-ttu-id="f0759-114">コマンドレットのパラメーターには、さまざまな方法で情報を要求するユーザーができるように、これについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f0759-114">If the cmdlet parameters let the users solicit information in different ways, explain it.</span></span>

- <span data-ttu-id="f0759-115">ユーザーが明らかな使用だけでなく、コマンドレットを使用できる方法に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0759-115">Include information on ways that users can use the cmdlet, in addition to the obvious uses.</span></span> <span data-ttu-id="f0759-116">たとえば、オブジェクトを使用することができる`Get-Host`コマンドレットは、Windows PowerShell コマンド ウィンドウ内のテキストの色に変更を取得します。</span><span class="sxs-lookup"><span data-stu-id="f0759-116">For example, you can use the object that the `Get-Host` cmdlet retrieves to change the color of text in the Windows PowerShell command window.</span></span>

  <span data-ttu-id="f0759-117">次に例を示します。"、`Get-Acl`コマンドレットは、ファイルまたはリソースのセキュリティ記述子を表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0759-117">Example:  "The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="f0759-118">セキュリティ記述子には、リソースのアクセス制御リスト (ACL) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0759-118">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="f0759-119">ACL アクセス許可が指定のユーザーおよびユーザー グループがリソースにアクセスする必要がある。"</span><span class="sxs-lookup"><span data-stu-id="f0759-119">The ACL specifies the permissions that users and user groups have to access the resource."</span></span>

- <span data-ttu-id="f0759-120">詳細な説明は、コマンドレットを示す必要がありますが、コマンドレットを使用する概念のについては説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0759-120">The detailed description should describe the cmdlet, but it should not describe concepts that the cmdlet uses.</span></span> <span data-ttu-id="f0759-121">その他のメモには、概念の定義を配置します。</span><span class="sxs-lookup"><span data-stu-id="f0759-121">Place concept definitions in Additional Notes.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0759-122">参照</span><span class="sxs-lookup"><span data-stu-id="f0759-122">See Also</span></span>

[<span data-ttu-id="f0759-123">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f0759-123">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

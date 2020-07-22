---
title: コマンドレットの説明を追加する方法
ms.date: 09/13/2016
ms.openlocfilehash: 2b98c4cefc3a55eccfeb7eba5a290e7d93a6088b
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893239"
---
# <a name="how-to-add-a-cmdlet-description"></a><span data-ttu-id="1074b-102">コマンドレットの説明を追加する方法</span><span class="sxs-lookup"><span data-stu-id="1074b-102">How to Add a Cmdlet Description</span></span>

<span data-ttu-id="1074b-103">このセクションでは、コマンドレットのヘルプの [**説明**] セクションに表示されるコンテンツを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1074b-103">This section describes how to add content that is displayed in the **DESCRIPTION** section of the cmdlet Help.</span></span> <span data-ttu-id="1074b-104">ヘルプファイルでは、各コマンドレットの**コマンド**ノードにこのコンテンツが追加されます。</span><span class="sxs-lookup"><span data-stu-id="1074b-104">In the Help file, this content is added to the **Command** node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="1074b-105">ヘルプファイルの完全なビューを表示するには、 `dll-Help.xml` PowerShell インストールディレクトリにあるいずれかのファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1074b-105">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="1074b-106">たとえば、ファイルには、 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` いくつかの PowerShell コマンドレットのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1074b-106">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="to-add-a-description"></a><span data-ttu-id="1074b-107">説明を追加するには</span><span class="sxs-lookup"><span data-stu-id="1074b-107">To Add a Description</span></span>

- <span data-ttu-id="1074b-108">まず、コマンドレットの基本的な機能について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="1074b-108">Begin by explaining the basic features of the cmdlet in more detail.</span></span> <span data-ttu-id="1074b-109">多くの場合、コマンドレット名に使用されている用語を説明し、例として不明な概念を示します。</span><span class="sxs-lookup"><span data-stu-id="1074b-109">In many cases, you can explain the terms used in the cmdlet name and illustrate unfamiliar concepts with an example.</span></span> <span data-ttu-id="1074b-110">たとえば、コマンドレットがデータをファイルに追加する場合は、既存のファイルの末尾にデータを追加することを説明します。</span><span class="sxs-lookup"><span data-stu-id="1074b-110">For example, if the cmdlet appends data to a file, explain that it adds data to the end of an existing file.</span></span>

- <span data-ttu-id="1074b-111">コマンドレットのすべての機能を検索するには、パラメーターの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="1074b-111">To find all of the features of the cmdlet, review the parameter list.</span></span> <span data-ttu-id="1074b-112">コマンドレットの主要な機能について説明し、その他の関数と機能を含めます。</span><span class="sxs-lookup"><span data-stu-id="1074b-112">Describe the primary function of the cmdlet, and then include other functions and features.</span></span> <span data-ttu-id="1074b-113">たとえば、コマンドレットの main 関数が1つのプロパティを変更するとしますが、コマンドレットではすべてのプロパティを変更できます。詳細については、詳細な説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1074b-113">For example, if the main function of the cmdlet is to change one property, but the cmdlet can change all of the properties, say so in the detailed description.</span></span> <span data-ttu-id="1074b-114">コマンドレットのパラメーターを使用して、ユーザーがさまざまな方法で情報を送信できるようにする場合は、その方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="1074b-114">If the cmdlet parameters let the users solicit information in different ways, explain it.</span></span>

- <span data-ttu-id="1074b-115">ユーザーがコマンドレットを使用する方法についての情報を、明確な用途にも含めます。</span><span class="sxs-lookup"><span data-stu-id="1074b-115">Include information on ways that users can use the cmdlet, in addition to the obvious uses.</span></span> <span data-ttu-id="1074b-116">たとえば、コマンドレットによって取得されたオブジェクトを使用して、 `Get-Host` Windows PowerShell コマンドウィンドウ内のテキストの色を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1074b-116">For example, you can use the object that the `Get-Host` cmdlet retrieves to change the color of text in the Windows PowerShell command window.</span></span>

  <span data-ttu-id="1074b-117">例: " `Get-Acl` コマンドレットは、ファイルまたはリソースのセキュリティ記述子を表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="1074b-117">Example: "The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="1074b-118">セキュリティ記述子には、リソースのアクセス制御リスト (ACL) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1074b-118">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="1074b-119">ACL は、ユーザーとユーザーグループがリソースにアクセスするために必要なアクセス許可を指定します。</span><span class="sxs-lookup"><span data-stu-id="1074b-119">The ACL specifies the permissions that users and user groups have to access the resource."</span></span>

- <span data-ttu-id="1074b-120">詳細な説明ではコマンドレットを記述する必要がありますが、コマンドレットで使用される概念は説明しません。</span><span class="sxs-lookup"><span data-stu-id="1074b-120">The detailed description should describe the cmdlet, but it should not describe concepts that the cmdlet uses.</span></span> <span data-ttu-id="1074b-121">概念の定義を追加のメモに配置します。</span><span class="sxs-lookup"><span data-stu-id="1074b-121">Place concept definitions in Additional Notes.</span></span>

## <a name="see-also"></a><span data-ttu-id="1074b-122">参照</span><span class="sxs-lookup"><span data-stu-id="1074b-122">See Also</span></span>

[<span data-ttu-id="1074b-123">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="1074b-123">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

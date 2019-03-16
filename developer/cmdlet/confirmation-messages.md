---
title: 確認メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a886a26d-7730-4586-aeac-fd3f0bc60b88
caps.latest.revision: 8
ms.openlocfilehash: 229725b5b9f1f0082592dcebe11564fd2f630ce1
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059475"
---
# <a name="confirmation-messages"></a><span data-ttu-id="2a00c-102">確認メッセージ</span><span class="sxs-lookup"><span data-stu-id="2a00c-102">Confirmation Messages</span></span>

<span data-ttu-id="2a00c-103">バリエーションに応じて表示できるさまざまな確認メッセージをここでは、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)呼び出されるメソッド。</span><span class="sxs-lookup"><span data-stu-id="2a00c-103">Here are different confirmation messages that can be displayed depending on the variants of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods that are called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a00c-104">確認を要求する方法を示すサンプル コードでは、次を参照してください。[要求の確認方法](./how-to-request-confirmations.md)します。</span><span class="sxs-lookup"><span data-stu-id="2a00c-104">For sample code that shows how to request confirmations, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specifying-the-resource"></a><span data-ttu-id="2a00c-105">リソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a00c-105">Specifying the Resource</span></span>

<span data-ttu-id="2a00c-106">呼び出すことによって変更される直前にあるリソースを指定することができます、 [System.Management.Automation.Cmdlet.Shouldprocess%2A でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0)メソッド。</span><span class="sxs-lookup"><span data-stu-id="2a00c-106">You can specify the resource that is about to be changed by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="2a00c-107">この場合を使用して、リソースを指定する、`target`メソッド、および操作のパラメーターは、Windows PowerShell によって追加されます。</span><span class="sxs-lookup"><span data-stu-id="2a00c-107">In this case, you supply the resource by using the `target` parameter of the method, and the operation is added by Windows PowerShell.</span></span> <span data-ttu-id="2a00c-108">次のメッセージ テキスト"MyResource"が対象のリソースで、操作が呼び出しを行うコマンドの名前とします。</span><span class="sxs-lookup"><span data-stu-id="2a00c-108">In the following message, the text "MyResource" is the resource acted on and the operation is the name of the command that makes the call.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="2a00c-109">ユーザーが選択した場合**はい**または**すべてはい**、確認を要求 (示すように、次の例) への呼び出し、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドを作成すると、これにより、2 番目の確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a00c-109">If the user selects **Yes** or **Yes to All** to the confirmation request (as shown in the following example), a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a><span data-ttu-id="2a00c-110">操作とリソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a00c-110">Specifying the Operation and Resource</span></span>

<span data-ttu-id="2a00c-111">変更されようとしているリソースおよびコマンドが呼び出すことによって実行される操作を指定することができます、 [System.Management.Automation.Cmdlet.Shouldprocess%2A でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0)メソッド。</span><span class="sxs-lookup"><span data-stu-id="2a00c-111">You can specify the resource that is about to be changed and the operation that the command is about to perform by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="2a00c-112">この場合を使用して、リソースを指定する、`target`パラメーターと、操作を使用して、`target`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2a00c-112">In this case, you supply the resource by using the `target` parameter and the operation by using the `target` parameter.</span></span> <span data-ttu-id="2a00c-113">次のメッセージ テキスト"MyResource"は対象のリソースと"myaction という名前"は、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a00c-113">In the following message, the text "MyResource" is the resource acted on and "MyAction" is the operation to be performed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="2a00c-114">ユーザーが選択した場合**はい**または**すべてはい**前のメッセージへの呼び出しに、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドが行われる原因となる、2 番目の確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a00c-114">If the user selects **Yes** or **Yes to All** to the previous message, a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a><span data-ttu-id="2a00c-115">参照</span><span class="sxs-lookup"><span data-stu-id="2a00c-115">See Also</span></span>

[<span data-ttu-id="2a00c-116">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="2a00c-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

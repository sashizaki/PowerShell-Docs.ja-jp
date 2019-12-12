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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365731"
---
# <a name="confirmation-messages"></a><span data-ttu-id="2e855-102">確認メッセージ</span><span class="sxs-lookup"><span data-stu-id="2e855-102">Confirmation Messages</span></span>

<span data-ttu-id="2e855-103">次に示すのは、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の種類によって異なる確認メッセージが表示されます。このメソッドは、呼び出さ[れるメソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2e855-103">Here are different confirmation messages that can be displayed depending on the variants of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods that are called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e855-104">確認を要求する方法を示すサンプルコードについては、「確認[を要求する方法](./how-to-request-confirmations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e855-104">For sample code that shows how to request confirmations, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specifying-the-resource"></a><span data-ttu-id="2e855-105">リソースの指定</span><span class="sxs-lookup"><span data-stu-id="2e855-105">Specifying the Resource</span></span>

<span data-ttu-id="2e855-106">変更しようとしているリソースを指定するには、このコマンドレットを呼び出してください[。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0)メソッド。</span><span class="sxs-lookup"><span data-stu-id="2e855-106">You can specify the resource that is about to be changed by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="2e855-107">この場合、メソッドの `target` パラメーターを使用してリソースを指定すると、Windows PowerShell によって操作が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2e855-107">In this case, you supply the resource by using the `target` parameter of the method, and the operation is added by Windows PowerShell.</span></span> <span data-ttu-id="2e855-108">次のメッセージでは、"MyResource" というテキストが使用されるリソースであり、操作は呼び出しを行うコマンドの名前です。</span><span class="sxs-lookup"><span data-stu-id="2e855-108">In the following message, the text "MyResource" is the resource acted on and the operation is the name of the command that makes the call.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="2e855-109">次の例に示すように、ユーザーが確認要求に対して **[はい]** または **[はい] を**選択した場合は、" [System](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) ..............................................</span><span class="sxs-lookup"><span data-stu-id="2e855-109">If the user selects **Yes** or **Yes to All** to the confirmation request (as shown in the following example), a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a><span data-ttu-id="2e855-110">操作とリソースの指定</span><span class="sxs-lookup"><span data-stu-id="2e855-110">Specifying the Operation and Resource</span></span>

<span data-ttu-id="2e855-111">変更しようとしているリソースと、コマンドが実行される操作を指定するには、そのリソースを使用します。この場合、 [% 2a を呼び出します。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0)メソッド。</span><span class="sxs-lookup"><span data-stu-id="2e855-111">You can specify the resource that is about to be changed and the operation that the command is about to perform by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="2e855-112">この場合は、`target` パラメーターを使用してリソースを指定し、`target` パラメーターを使用して操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2e855-112">In this case, you supply the resource by using the `target` parameter and the operation by using the `target` parameter.</span></span> <span data-ttu-id="2e855-113">次のメッセージでは、"MyResource" というテキストが動作しているリソースであり、"Myresource" は実行される操作です。</span><span class="sxs-lookup"><span data-stu-id="2e855-113">In the following message, the text "MyResource" is the resource acted on and "MyAction" is the operation to be performed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="2e855-114">ユーザーが前のメッセージに対して **[はい]** または **[はい] を**選択した場合は、" [System](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) ................................................</span><span class="sxs-lookup"><span data-stu-id="2e855-114">If the user selects **Yes** or **Yes to All** to the previous message, a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a><span data-ttu-id="2e855-115">参照</span><span class="sxs-lookup"><span data-stu-id="2e855-115">See Also</span></span>

[<span data-ttu-id="2e855-116">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="2e855-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

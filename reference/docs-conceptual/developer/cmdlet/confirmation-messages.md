---
ms.date: 09/13/2016
ms.topic: reference
title: 確認メッセージ
description: 確認メッセージ
ms.openlocfilehash: 76302b2f8d8ca6dcdfe1b3c36f71aad23a53f7cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355189"
---
# <a name="confirmation-messages"></a><span data-ttu-id="29562-103">確認メッセージ</span><span class="sxs-lookup"><span data-stu-id="29562-103">Confirmation Messages</span></span>

<span data-ttu-id="29562-104">次に示すのは、 [システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) の種類によって異なる確認メッセージが表示されます。このメソッドは、呼び出さ [れるメソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="29562-104">Here are different confirmation messages that can be displayed depending on the variants of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods that are called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29562-105">確認を要求する方法を示すサンプルコードについては、「確認 [を要求する方法](./how-to-request-confirmations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29562-105">For sample code that shows how to request confirmations, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specifying-the-resource"></a><span data-ttu-id="29562-106">リソースの指定</span><span class="sxs-lookup"><span data-stu-id="29562-106">Specifying the Resource</span></span>

<span data-ttu-id="29562-107">変更しようとしているリソースを指定するには、このコマンドレットを呼び出してください [。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) メソッド。</span><span class="sxs-lookup"><span data-stu-id="29562-107">You can specify the resource that is about to be changed by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="29562-108">この場合、メソッドのパラメーターを使用してリソースを指定する `target` と、操作は Windows PowerShell によって追加されます。</span><span class="sxs-lookup"><span data-stu-id="29562-108">In this case, you supply the resource by using the `target` parameter of the method, and the operation is added by Windows PowerShell.</span></span> <span data-ttu-id="29562-109">次のメッセージでは、"MyResource" というテキストが使用されるリソースであり、操作は呼び出しを行うコマンドの名前です。</span><span class="sxs-lookup"><span data-stu-id="29562-109">In the following message, the text "MyResource" is the resource acted on and the operation is the name of the command that makes the call.</span></span>

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="29562-110">次の例に示すように、ユーザーが確認要求に対して **[はい]** または **[はい] を** 選択した場合は、" [System](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) ..............................................</span><span class="sxs-lookup"><span data-stu-id="29562-110">If the user selects **Yes** or **Yes to All** to the confirmation request (as shown in the following example), a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a><span data-ttu-id="29562-111">操作とリソースの指定</span><span class="sxs-lookup"><span data-stu-id="29562-111">Specifying the Operation and Resource</span></span>

<span data-ttu-id="29562-112">変更しようとしているリソースと、コマンドが実行される操作を指定するには、そのリソースを使用します。この場合、 [% 2a を呼び出します。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) メソッド。</span><span class="sxs-lookup"><span data-stu-id="29562-112">You can specify the resource that is about to be changed and the operation that the command is about to perform by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="29562-113">この場合、パラメーターを使用してリソースを指定し、パラメーターを使用して `target` 操作を `target` 行います。</span><span class="sxs-lookup"><span data-stu-id="29562-113">In this case, you supply the resource by using the `target` parameter and the operation by using the `target` parameter.</span></span> <span data-ttu-id="29562-114">次のメッセージでは、"MyResource" というテキストが動作しているリソースであり、"Myresource" は実行される操作です。</span><span class="sxs-lookup"><span data-stu-id="29562-114">In the following message, the text "MyResource" is the resource acted on and "MyAction" is the operation to be performed.</span></span>

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="29562-115">ユーザーが前のメッセージに対して **[はい]** または **[はい] を** 選択した場合は、" [System](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) ................................................</span><span class="sxs-lookup"><span data-stu-id="29562-115">If the user selects **Yes** or **Yes to All** to the previous message, a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a><span data-ttu-id="29562-116">参照</span><span class="sxs-lookup"><span data-stu-id="29562-116">See Also</span></span>

[<span data-ttu-id="29562-117">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="29562-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

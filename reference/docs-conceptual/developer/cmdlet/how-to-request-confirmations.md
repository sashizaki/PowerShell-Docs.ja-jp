---
title: 確認を要求する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f24f77d5-e224-4b62-b128-535e045d333e
caps.latest.revision: 9
ms.openlocfilehash: 19e96b612a8778d82cdbafb528a7ffeb01f15f99
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369681"
---
# <a name="how-to-request-confirmations"></a><span data-ttu-id="c862d-102">確認を要求する方法</span><span class="sxs-lookup"><span data-stu-id="c862d-102">How to Request Confirmations</span></span>

<span data-ttu-id="c862d-103">この例で[は、メソッド](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を呼び出して、アクションを実行する前にユーザーからの確認を要求するように、メソッドを使用する方法を[示します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="c862d-103">This example shows how to call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to request confirmations from the user before an action is taken.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c862d-104">Windows PowerShell がこれらの要求を処理する方法の詳細については、「[確認の要求](./requesting-confirmation-from-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c862d-104">For more information about how Windows PowerShell handles these requests, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

## <a name="to-request-confirmation"></a><span data-ttu-id="c862d-105">確認を要求するには</span><span class="sxs-lookup"><span data-stu-id="c862d-105">To request confirmation</span></span>

1. <span data-ttu-id="c862d-106">コマンドレット属性の `SupportsShouldProcess` パラメーターが `true` に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c862d-106">Ensure that the `SupportsShouldProcess` parameter of the Cmdlet attribute is set to `true`.</span></span> <span data-ttu-id="c862d-107">(関数の場合は、この属性は、"パラメーター" になります。</span><span class="sxs-lookup"><span data-stu-id="c862d-107">(For functions this is a parameter of the CmdletBinding attribute.)</span></span>

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. <span data-ttu-id="c862d-108">コマンドレットに `Force` パラメーターを追加して、ユーザーが確認要求を上書きできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c862d-108">Add a `Force` parameter to your cmdlet so that the user can override a confirmation request.</span></span>

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. <span data-ttu-id="c862d-109">[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の戻り値を使用する `if` ステートメントを追加します。このメソッドを使用すると、system..............[コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)が呼び出されるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="c862d-109">Add an `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to determine if the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is called.</span></span>

4. <span data-ttu-id="c862d-110">2番目の `if` ステートメントを追加します。このステートメントで[は、このメソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)戻り値を使用し、`Force` パラメーターの値を使用して、操作を実行するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c862d-110">Add a second `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method and the value of the `Force` parameter to determine whether the operation should be performed.</span></span>

## <a name="example"></a><span data-ttu-id="c862d-111">例</span><span class="sxs-lookup"><span data-stu-id="c862d-111">Example</span></span>

<span data-ttu-id="c862d-112">次のコード例では、次のように、をオーバーライドすることによって、[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)オーバーライドメソッドを使用して、コマンドレットの[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).............. コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c862d-112">In the following code example, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods are called from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="c862d-113">ただし、他の入力処理メソッドからこれらのメソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="c862d-113">However, you can also call these methods from the other input processing methods.</span></span>

```csharp
protected override void ProcessRecord()
{
  if (ShouldProcess("ShouldProcess target"))
  {
    if (Force || ShouldContinue("", ""))
    {
      // Add code that performs the operation.
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="c862d-114">参照</span><span class="sxs-lookup"><span data-stu-id="c862d-114">See Also</span></span>

[<span data-ttu-id="c862d-115">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c862d-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

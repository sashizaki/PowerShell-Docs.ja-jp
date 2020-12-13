---
ms.date: 09/13/2016
ms.topic: reference
title: 確認を要求する方法
description: 確認を要求する方法
ms.openlocfilehash: 3e29803407bd9fbf13e6db0d0a02239c34e9c4fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666996"
---
# <a name="how-to-request-confirmations"></a><span data-ttu-id="54eb5-103">確認を要求する方法</span><span class="sxs-lookup"><span data-stu-id="54eb5-103">How to Request Confirmations</span></span>

<span data-ttu-id="54eb5-104">この例で[は、メソッド](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を呼び出して、アクションを実行する前にユーザーからの確認を要求するように、メソッドを使用する方法を[示します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="54eb5-104">This example shows how to call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to request confirmations from the user before an action is taken.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54eb5-105">Windows PowerShell がこれらの要求を処理する方法の詳細については、「 [確認の要求](./requesting-confirmation-from-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54eb5-105">For more information about how Windows PowerShell handles these requests, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

## <a name="to-request-confirmation"></a><span data-ttu-id="54eb5-106">確認を要求するには</span><span class="sxs-lookup"><span data-stu-id="54eb5-106">To request confirmation</span></span>

1. <span data-ttu-id="54eb5-107">`SupportsShouldProcess`コマンドレット属性のパラメーターがに設定されていることを確認し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="54eb5-107">Ensure that the `SupportsShouldProcess` parameter of the Cmdlet attribute is set to `true`.</span></span> <span data-ttu-id="54eb5-108">(関数の場合は、この属性は、"パラメーター" になります。</span><span class="sxs-lookup"><span data-stu-id="54eb5-108">(For functions this is a parameter of the CmdletBinding attribute.)</span></span>

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. <span data-ttu-id="54eb5-109">`Force`コマンドレットにパラメーターを追加して、ユーザーが確認要求をオーバーライドできるようにします。</span><span class="sxs-lookup"><span data-stu-id="54eb5-109">Add a `Force` parameter to your cmdlet so that the user can override a confirmation request.</span></span>

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. <span data-ttu-id="54eb5-110">System.string メソッド `if` の戻り値を使用するステートメント[](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)を[](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)追加し、このメソッドが呼び出されるかどうかを確認します。このメソッドは、を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="54eb5-110">Add an `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to determine if the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is called.</span></span>

4. <span data-ttu-id="54eb5-111">`if`[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)の戻り値を使用する2番目のステートメントを追加し、パラメーターの値を指定して、 `Force` 操作を実行するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="54eb5-111">Add a second `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method and the value of the `Force` parameter to determine whether the operation should be performed.</span></span>

## <a name="example"></a><span data-ttu-id="54eb5-112">例</span><span class="sxs-lookup"><span data-stu-id="54eb5-112">Example</span></span>

<span data-ttu-id="54eb5-113">次のコード例では、 [system..](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) [...](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .................... [...](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) .........</span><span class="sxs-lookup"><span data-stu-id="54eb5-113">In the following code example, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods are called from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="54eb5-114">ただし、他の入力処理メソッドからこれらのメソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="54eb5-114">However, you can also call these methods from the other input processing methods.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="54eb5-115">参照</span><span class="sxs-lookup"><span data-stu-id="54eb5-115">See Also</span></span>

[<span data-ttu-id="54eb5-116">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="54eb5-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

---
title: 確認を要求する方法 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ebe928724f1b750afc11c1e3c1207375f4ec8e42
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784097"
---
# <a name="how-to-request-confirmations"></a><span data-ttu-id="b3f9e-102">確認を要求する方法</span><span class="sxs-lookup"><span data-stu-id="b3f9e-102">How to Request Confirmations</span></span>

<span data-ttu-id="b3f9e-103">この例で[は、メソッド](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を呼び出して、アクションを実行する前にユーザーからの確認を要求するように、メソッドを使用する方法を[示します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="b3f9e-103">This example shows how to call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to request confirmations from the user before an action is taken.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3f9e-104">Windows PowerShell がこれらの要求を処理する方法の詳細については、「[確認の要求](./requesting-confirmation-from-cmdlets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3f9e-104">For more information about how Windows PowerShell handles these requests, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

## <a name="to-request-confirmation"></a><span data-ttu-id="b3f9e-105">確認を要求するには</span><span class="sxs-lookup"><span data-stu-id="b3f9e-105">To request confirmation</span></span>

1. <span data-ttu-id="b3f9e-106">`SupportsShouldProcess`コマンドレット属性のパラメーターがに設定されていることを確認し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="b3f9e-106">Ensure that the `SupportsShouldProcess` parameter of the Cmdlet attribute is set to `true`.</span></span> <span data-ttu-id="b3f9e-107">(関数の場合は、この属性は、"パラメーター" になります。</span><span class="sxs-lookup"><span data-stu-id="b3f9e-107">(For functions this is a parameter of the CmdletBinding attribute.)</span></span>

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. <span data-ttu-id="b3f9e-108">`Force`コマンドレットにパラメーターを追加して、ユーザーが確認要求をオーバーライドできるようにします。</span><span class="sxs-lookup"><span data-stu-id="b3f9e-108">Add a `Force` parameter to your cmdlet so that the user can override a confirmation request.</span></span>

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. <span data-ttu-id="b3f9e-109">System.string メソッド `if` の戻り値を使用するステートメント[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)を[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)追加し、このメソッドが呼び出されるかどうかを確認します。このメソッドは、を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b3f9e-109">Add an `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to determine if the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is called.</span></span>

4. <span data-ttu-id="b3f9e-110">`if`[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)の戻り値を使用する2番目のステートメントを追加し、パラメーターの値を指定して、 `Force` 操作を実行するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b3f9e-110">Add a second `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method and the value of the `Force` parameter to determine whether the operation should be performed.</span></span>

## <a name="example"></a><span data-ttu-id="b3f9e-111">例</span><span class="sxs-lookup"><span data-stu-id="b3f9e-111">Example</span></span>

<span data-ttu-id="b3f9e-112">次のコード例では、 [system..](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) [...](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .................... [...](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) .........</span><span class="sxs-lookup"><span data-stu-id="b3f9e-112">In the following code example, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods are called from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="b3f9e-113">ただし、他の入力処理メソッドからこれらのメソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="b3f9e-113">However, you can also call these methods from the other input processing methods.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b3f9e-114">参照</span><span class="sxs-lookup"><span data-stu-id="b3f9e-114">See Also</span></span>

[<span data-ttu-id="b3f9e-115">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="b3f9e-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

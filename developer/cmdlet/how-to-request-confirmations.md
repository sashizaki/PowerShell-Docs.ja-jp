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
ms.openlocfilehash: 8cfbcacf93733667ffba63a252c86518c0919b57
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863408"
---
# <a name="how-to-request-confirmations"></a><span data-ttu-id="5334e-102">確認を要求する方法</span><span class="sxs-lookup"><span data-stu-id="5334e-102">How to Request Confirmations</span></span>

<span data-ttu-id="5334e-103">この例では、呼び出し、 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)から確認を要求する方法、ユーザー アクションが行われる前にします。</span><span class="sxs-lookup"><span data-stu-id="5334e-103">This example shows how to call the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to request confirmations from the user before an action is taken.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5334e-104">Windows PowerShell でこれらの要求を処理する方法の詳細については、次を参照してください。[確認を要求する](./requesting-confirmation-from-cmdlets.md)します。</span><span class="sxs-lookup"><span data-stu-id="5334e-104">For more information about how Windows PowerShell handles these requests, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

## <a name="to-request-confirmation"></a><span data-ttu-id="5334e-105">確認を要求するには</span><span class="sxs-lookup"><span data-stu-id="5334e-105">To request confirmation</span></span>

1. <span data-ttu-id="5334e-106">いることを確認、`SupportsShouldProcess`コマンドレット属性のパラメーターに設定されている`true`します。</span><span class="sxs-lookup"><span data-stu-id="5334e-106">Ensure that the `SupportsShouldProcess` parameter of the Cmdlet attribute is set to `true`.</span></span> <span data-ttu-id="5334e-107">(関数のこのは CmdletBinding 属性のパラメーター) です。</span><span class="sxs-lookup"><span data-stu-id="5334e-107">(For functions this is a parameter of the CmdletBinding attribute.)</span></span>

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. <span data-ttu-id="5334e-108">追加、`Force`パラメーターをコマンドレットに、ユーザーが確認要求をオーバーライドできるようにします。</span><span class="sxs-lookup"><span data-stu-id="5334e-108">Add a `Force` parameter to your cmdlet so that the user can override a confirmation request.</span></span>

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. <span data-ttu-id="5334e-109">追加、`if`の戻り値を使用するステートメント、 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)かを判断するメソッド、 [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5334e-109">Add an `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to determine if the [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is called.</span></span>

4. <span data-ttu-id="5334e-110">1 秒あたりの追加`if`の戻り値を使用するステートメント、 [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドとの値、`Force`操作をするかどうかを決定するパラメーター実行されます。</span><span class="sxs-lookup"><span data-stu-id="5334e-110">Add a second `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method and the value of the `Force` parameter to determine whether the operation should be performed.</span></span>

## <a name="example"></a><span data-ttu-id="5334e-111">例</span><span class="sxs-lookup"><span data-stu-id="5334e-111">Example</span></span>

<span data-ttu-id="5334e-112">次のコード例で、 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドは、内部から呼び出されますが、オーバーライド、 [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。</span><span class="sxs-lookup"><span data-stu-id="5334e-112">In the following code example, the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods are called from within the override of the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="5334e-113">ただし、これらのメソッドは、他の入力処理メソッドからも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5334e-113">However, you can also call these methods from the other input processing methods.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5334e-114">参照</span><span class="sxs-lookup"><span data-stu-id="5334e-114">See Also</span></span>

[<span data-ttu-id="5334e-115">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="5334e-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

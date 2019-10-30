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
# <a name="how-to-request-confirmations"></a>確認を要求する方法

この例で[は、メソッド](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を呼び出して、アクションを実行する前にユーザーからの確認を要求するように、メソッドを使用する方法を[示します。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)

> [!IMPORTANT]
> Windows PowerShell がこれらの要求を処理する方法の詳細については、「[確認の要求](./requesting-confirmation-from-cmdlets.md)」を参照してください。

## <a name="to-request-confirmation"></a>確認を要求するには

1. コマンドレット属性の `SupportsShouldProcess` パラメーターが `true` に設定されていることを確認します。 (関数の場合は、この属性は、"パラメーター" になります。

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. コマンドレットに `Force` パラメーターを追加して、ユーザーが確認要求を上書きできるようにします。

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. [システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の戻り値を使用する `if` ステートメントを追加します。このメソッドを使用すると、system..............[コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)が呼び出されるかどうかが判断されます。

4. 2番目の `if` ステートメントを追加します。このステートメントで[は、このメソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)戻り値を使用し、`Force` パラメーターの値を使用して、操作を実行するかどうかを決定します。

## <a name="example"></a>例

次のコード例では、次のように、をオーバーライドすることによって、[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)オーバーライドメソッドを使用して、コマンドレットの[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).............. コマンドレット ただし、他の入力処理メソッドからこれらのメソッドを呼び出すこともできます。

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

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

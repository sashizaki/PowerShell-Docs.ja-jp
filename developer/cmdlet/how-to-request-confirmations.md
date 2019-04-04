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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058829"
---
# <a name="how-to-request-confirmations"></a>確認を要求する方法

この例では、呼び出し、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)から確認を要求する方法、ユーザー アクションが行われる前にします。

> [!IMPORTANT]
> Windows PowerShell でこれらの要求を処理する方法の詳細については、[確認を要求する](./requesting-confirmation-from-cmdlets.md)を参照してください。

## <a name="to-request-confirmation"></a>確認を要求するには

1. いることを確認、`SupportsShouldProcess`コマンドレット属性のパラメーターに設定されている`true`します。 (関数のこのは CmdletBinding 属性のパラメーター) です。

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. 追加、`Force`パラメーターをコマンドレットに、ユーザーが確認要求をオーバーライドできるようにします。

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. 追加、`if`の戻り値を使用するステートメント、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)かを判断するメソッド、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドが呼び出されます。

4. 1 秒あたりの追加`if`の戻り値を使用するステートメント、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドとの値、`Force`操作をするかどうかを決定するパラメーター実行されます。

## <a name="example"></a>例

次のコード例で、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドがオーバーライド内から呼び出されます[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。 ただし、これらのメソッドは、他の入力処理メソッドからも呼び出すことができます。

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

---
title: コマンドレット内のコマンドレットを呼び出す方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efa4dc9c-ddee-46a3-978a-9dbb61e9bb6f
caps.latest.revision: 12
ms.openlocfilehash: 57543a88d04eb66c9d109249a99ddd272b02ef9d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067826"
---
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a>コマンドレット内からコマンドレットを呼び出す方法

この例では、別のコマンドレットが呼び出されたコマンドレットの機能を開発しているコマンドレットに追加することができます内からコマンドレットを呼び出す方法を示します。 この例で、`Get-Process`ローカル コンピューターで実行されているプロセスを取得するコマンドレットが呼び出されます。 呼び出し、`Get-Process`コマンドレットは、次のコマンドに相当します。 このコマンドは、"a"から"t"の文字で名前が始まるすべてのプロセスを取得します。

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> 直接派生したコマンドレットのみを呼び出すことができます、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラス。 派生したコマンドレットを呼び出すことはできません、 [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラス。

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a>コマンドレット内のコマンドレットを呼び出す

1. 呼び出されるコマンドレットを定義するアセンブリが参照されていることを確認して、適切な`using`ステートメントが追加されます。 この例では、次の名前空間が追加されます。

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. コマンドレットのメソッドの処理、入力では、呼び出されるコマンドレットの新しいインスタンスを作成します。 この例では、型のオブジェクトで[Microsoft.PowerShell.Commands.Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand)と共に、コマンドレットが呼び出されたときに使用される引数を格納する文字列が作成されます。

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. 呼び出す、 [System.Management.Automation.Cmdlet.Invoke*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドを呼び出す、`Get-Process`コマンドレット。

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a>例

この例で、`Get-Process`コマンドレットは、内から呼び出される、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)コマンドレットのメソッド。

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;   // Windows PowerShell assembly.
using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify an
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "GreetingInvoke")]
  public class SendGreetingInvokeCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the BeginProcessing method to invoke
    // the Get-Process cmdlet.
    protected override void BeginProcessing()
    {
      GetProcessCommand gp = new GetProcessCommand();
      gp.Name = new string[] { "[a-t]*" };
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

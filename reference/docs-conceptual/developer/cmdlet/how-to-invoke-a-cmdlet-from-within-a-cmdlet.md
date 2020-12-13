---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレット内からコマンドレットを呼び出す方法
description: コマンドレット内からコマンドレットを呼び出す方法
ms.openlocfilehash: d137ac895f66000329de76a2c16a74b02c0e82ca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667047"
---
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="86c75-103">コマンドレット内からコマンドレットを呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="86c75-103">How to Invoke a Cmdlet from Within a Cmdlet</span></span>

<span data-ttu-id="86c75-104">この例では、別のコマンドレット内からコマンドレットを呼び出す方法を示します。このコマンドレットを使用すると、開発中のコマンドレットに、呼び出されたコマンドレットの機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="86c75-104">This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span> <span data-ttu-id="86c75-105">この例では、 `Get-Process` コマンドレットを呼び出して、ローカルコンピューター上で実行されているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="86c75-105">In this example, the `Get-Process` cmdlet is invoked to get the processes that are running on the local computer.</span></span> <span data-ttu-id="86c75-106">コマンドレットの呼び出し `Get-Process` は、次のコマンドと同じです。</span><span class="sxs-lookup"><span data-stu-id="86c75-106">The call to the `Get-Process` cmdlet is equivalent to the following command.</span></span> <span data-ttu-id="86c75-107">このコマンドは、名前が "a" ~ "t" で始まるすべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="86c75-107">This command retrieves all the processes whose names start with the characters "a" through "t".</span></span>

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> <span data-ttu-id="86c75-108">を呼び出すことができるのは、 [system.servicemodel クラスから直接派生した](/dotnet/api/System.Management.Automation.Cmdlet) コマンドレットだけです。</span><span class="sxs-lookup"><span data-stu-id="86c75-108">You can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="86c75-109">[PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラスから派生したコマンドレットを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="86c75-109">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="86c75-110">コマンドレット内からコマンドレットを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="86c75-110">To invoke a cmdlet from within a cmdlet</span></span>

1. <span data-ttu-id="86c75-111">呼び出すコマンドレットを定義するアセンブリが参照されていること、および適切なステートメントが追加されていることを確認し `using` ます。</span><span class="sxs-lookup"><span data-stu-id="86c75-111">Ensure that the assembly that defines the cmdlet to be invoked is referenced and that the appropriate `using` statement is added.</span></span> <span data-ttu-id="86c75-112">この例では、次の名前空間が追加されています。</span><span class="sxs-lookup"><span data-stu-id="86c75-112">In this example, the following namespaces are added.</span></span>

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. <span data-ttu-id="86c75-113">コマンドレットの入力処理メソッドで、呼び出すコマンドレットの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="86c75-113">In the input processing method of the cmdlet, create a new instance of the cmdlet to be invoked.</span></span> <span data-ttu-id="86c75-114">この例では、コマンドレットが呼び出されたときに使用される引数を含む文字列と共に、型を指定すると、 [Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) という型のオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="86c75-114">In this example, an object of type [Microsoft.PowerShell.Commands.Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) is created along with the string that contains the arguments that are used when the cmdlet is invoked.</span></span>

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. <span data-ttu-id="86c75-115">コマンドレットを呼び出すには、system.servicemodel [\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke)メソッドを呼び出します。 `Get-Process`</span><span class="sxs-lookup"><span data-stu-id="86c75-115">Call the [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method to invoke the `Get-Process` cmdlet.</span></span>

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a><span data-ttu-id="86c75-116">例</span><span class="sxs-lookup"><span data-stu-id="86c75-116">Example</span></span>

<span data-ttu-id="86c75-117">この例では、コマンドレットは、コマンド `Get-Process` レットの System.servicemodel [処理](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) メソッド内から呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="86c75-117">In this example, the `Get-Process` cmdlet is invoked from within the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method of a cmdlet.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="86c75-118">参照</span><span class="sxs-lookup"><span data-stu-id="86c75-118">See Also</span></span>

[<span data-ttu-id="86c75-119">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="86c75-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

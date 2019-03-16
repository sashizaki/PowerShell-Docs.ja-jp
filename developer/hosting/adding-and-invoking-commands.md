---
title: 追加して、コマンドを起動 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62be8432-28c1-4ca2-bcdb-d0350163fa8c
caps.latest.revision: 5
ms.openlocfilehash: 9a01f948c5b474b4f9068030907601543e13cc7e
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057656"
---
# <a name="adding-and-invoking-commands"></a><span data-ttu-id="07231-102">コマンドを追加し、呼び出す</span><span class="sxs-lookup"><span data-stu-id="07231-102">Adding and invoking commands</span></span>

<span data-ttu-id="07231-103">実行空間を作成した後は、パイプラインに Windows PowerShellcommands とスクリプトを追加し、同期または非同期パイプラインを呼び出すできます。</span><span class="sxs-lookup"><span data-stu-id="07231-103">After creating a runspace, you can add Windows PowerShellcommands and scripts to a pipeline, and then invoke the pipeline synchronously or asynchronously.</span></span>

## <a name="creating-a-pipeline"></a><span data-ttu-id="07231-104">パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="07231-104">Creating a pipeline</span></span>

 <span data-ttu-id="07231-105">[System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)クラスは、パイプラインにコマンド、パラメーター、およびスクリプトを追加するいくつかのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="07231-105">The [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class provides several methods to add commands, parameters, and scripts to the pipeline.</span></span> <span data-ttu-id="07231-106">オーバー ロードを呼び出すことによって、パイプラインを同期的に呼び出すことができます、 [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドのオーバー ロードを呼び出すことによって非同期的にまたは、 [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke)をクリックし、 [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッド。</span><span class="sxs-lookup"><span data-stu-id="07231-106">You can invoke the pipeline synchronously by calling an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, or asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) and then the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

### <a name="addcommand"></a><span data-ttu-id="07231-107">AddCommand</span><span class="sxs-lookup"><span data-stu-id="07231-107">AddCommand</span></span>

1. <span data-ttu-id="07231-108">作成、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="07231-108">Create a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="07231-109">実行するコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="07231-109">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="07231-110">コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="07231-110">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

 <span data-ttu-id="07231-111">呼び出す場合、 [System.Management.Automation.Powershell.Addcommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)メソッドを呼び出す前に 2 回以上、 [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドは、の結果、最初のコマンドは、2 番目にパイプします。</span><span class="sxs-lookup"><span data-stu-id="07231-111">If you call the [System.Management.Automation.Powershell.Addcommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="07231-112">前のコマンドをコマンドの結果をパイプ処理したくない場合は呼び出すことによって追加、 [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="07231-112">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="07231-113">AddParameter</span><span class="sxs-lookup"><span data-stu-id="07231-113">AddParameter</span></span>

 <span data-ttu-id="07231-114">前の例では、パラメーターなしの 1 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="07231-114">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="07231-115">使用して、コマンドにパラメーターを追加することができます、 [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)メソッドを次のコードがという名前のプロセスのすべての一覧を取得など`PowerShell`で実行されている、マシン。</span><span class="sxs-lookup"><span data-stu-id="07231-115">You can add parameters to the command by using the [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

 <span data-ttu-id="07231-116">追加のパラメーターを追加するには呼び出すことによって[System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)繰り返し。</span><span class="sxs-lookup"><span data-stu-id="07231-116">You can add additional parameters by calling [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

 <span data-ttu-id="07231-117">呼び出すことによって、パラメーターの名前と値のディクショナリを追加することも、 [System.Management.Automation.Powershell.Addparameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters)メソッド。</span><span class="sxs-lookup"><span data-stu-id="07231-117">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.Powershell.Addparameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="07231-118">AddStatement</span><span class="sxs-lookup"><span data-stu-id="07231-118">AddStatement</span></span>

 <span data-ttu-id="07231-119">使用してバッチ処理をシミュレートすることができます、 [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)メソッドで、次のコードは、名前の実行中のプロセスの一覧を取得します。 パイプラインの末尾に追加のステートメントを追加します。`PowerShell`、し、実行中のサービスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="07231-119">You can simulate batching by using the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="07231-120">AddScript</span><span class="sxs-lookup"><span data-stu-id="07231-120">AddScript</span></span>

 <span data-ttu-id="07231-121">既存のスクリプトを実行するには呼び出すことによって、 [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)メソッド。</span><span class="sxs-lookup"><span data-stu-id="07231-121">You can run an existing script by calling the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="07231-122">次の例では、パイプラインにスクリプトを追加し、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="07231-122">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="07231-123">この例では、という名前のスクリプトが既に存在`MyScript.ps1`という名前のフォルダーで`D:\PSScripts`します。</span><span class="sxs-lookup"><span data-stu-id="07231-123">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

 <span data-ttu-id="07231-124">バージョンがあります、 [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)というブール型パラメーターを受け取るメソッド`useLocalScope`します。</span><span class="sxs-lookup"><span data-stu-id="07231-124">There is also a version of the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="07231-125">このパラメーターに設定されている場合`true`、し、スクリプトはローカル スコープで実行します。</span><span class="sxs-lookup"><span data-stu-id="07231-125">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="07231-126">次のコードは、スクリプトをローカル スコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="07231-126">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a><span data-ttu-id="07231-127">パイプラインを同期的に呼び出す</span><span class="sxs-lookup"><span data-stu-id="07231-127">Invoking a pipeline synchronously</span></span>

 <span data-ttu-id="07231-128">パイプラインに要素を追加した後、そのことを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="07231-128">After you add elements to the pipeline, you invoke it.</span></span> <span data-ttu-id="07231-129">オーバー ロードを呼び出すことに、パイプラインを同期的に呼び出す、 [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッド。</span><span class="sxs-lookup"><span data-stu-id="07231-129">To invoke the pipeline synchronously, you call an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method.</span></span> <span data-ttu-id="07231-130">次の例では、同期的にパイプラインを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="07231-130">The following example shows how to synchronously invoke a pipeline.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS1e
{
  class HostPS1e
  {
    static void Main(string[] args)
    {
      // Using the PowerShell.Create and AddCommand
      // methods, create a command pipeline.
      PowerShell ps = PowerShell.Create().AddCommand ("Sort-Object");

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the supplied input.
      foreach (PSObject result in ps.Invoke(new int[] { 3, 1, 6, 2, 5, 4 }))
      {
          Console.WriteLine("{0}", result);
      } // End foreach.
    } // End Main.
  } // End HostPS1e.
}
```

### <a name="invoking-a-pipeline-asynchronously"></a><span data-ttu-id="07231-131">パイプラインを非同期的に呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="07231-131">Invoking a pipeline asynchronously</span></span>

 <span data-ttu-id="07231-132">オーバー ロードを呼び出すことでパイプラインを非同期的に呼び出す、 [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke)を作成する、 [IAsyncResult](http://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx)オブジェクト、および呼び出し、 [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッド。</span><span class="sxs-lookup"><span data-stu-id="07231-132">You invoke a pipeline asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) to create an [IAsyncResult](http://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx) object, and then calling the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

 <span data-ttu-id="07231-133">次の例では、パイプラインを非同期的に呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="07231-133">The following example shows how to invoke a pipeline asynchronously.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS3
{
  class HostPS3
  {
    static void Main(string[] args)
    {
      // Use the PowerShell.Create and PowerShell.AddCommand
      // methods to create a command pipeline that includes
      // Get-Process cmdlet. Do not include spaces immediately
      // before or after the cmdlet name as that will cause
      // the command to fail.
      PowerShell ps = PowerShell.Create().AddCommand("Get-Process");

      // Create an IAsyncResult object and call the
      // BeginInvoke method to start running the
      // command pipeline asynchronously.
      IAsyncResult async = ps.BeginInvoke();

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the default runspace.
      foreach (PSObject result in ps.EndInvoke(async))
      {
        Console.WriteLine("{0,-20}{1}",
                result.Members["ProcessName"].Value,
                result.Members["Id"].Value);
      } // End foreach.
      System.Console.WriteLine("Hit any key to exit.");
      System.Console.ReadKey();
    } // End Main.
  } // End HostPS3.
}
```

## <a name="see-also"></a><span data-ttu-id="07231-134">参照</span><span class="sxs-lookup"><span data-stu-id="07231-134">See Also</span></span>

 [<span data-ttu-id="07231-135">InitialSessionState を作成します。</span><span class="sxs-lookup"><span data-stu-id="07231-135">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

 [<span data-ttu-id="07231-136">制約付き実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="07231-136">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

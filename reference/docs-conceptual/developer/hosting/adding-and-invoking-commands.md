---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドを追加し、呼び出す
description: コマンドを追加し、呼び出す
ms.openlocfilehash: c30cb15d473c344e40b96938c355d77c059fe2d5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "96616031"
---
# <a name="adding-and-invoking-commands"></a><span data-ttu-id="66fb5-103">コマンドを追加し、呼び出す</span><span class="sxs-lookup"><span data-stu-id="66fb5-103">Adding and invoking commands</span></span>

<span data-ttu-id="66fb5-104">実行空間を作成した後、Windows PowerShellcommands とスクリプトをパイプラインに追加し、同期または非同期でパイプラインを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="66fb5-104">After creating a runspace, you can add Windows PowerShellcommands and scripts to a pipeline, and then invoke the pipeline synchronously or asynchronously.</span></span>

## <a name="creating-a-pipeline"></a><span data-ttu-id="66fb5-105">パイプラインを作成する</span><span class="sxs-lookup"><span data-stu-id="66fb5-105">Creating a pipeline</span></span>

<span data-ttu-id="66fb5-106">[System. Automation. Powershell](/dotnet/api/system.management.automation.powershell)クラスには、コマンド、パラメーター、およびスクリプトをパイプラインに追加するためのメソッドがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="66fb5-106">The [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class provides several methods to add commands, parameters, and scripts to the pipeline.</span></span> <span data-ttu-id="66fb5-107">パイプラインを同期的に呼び出すには、 [システム](/dotnet/api/System.Management.Automation.PowerShell.Invoke) のオーバーロードを呼び出すか、または、システムのオーバーロードを呼び出して非同期的に呼び出します。また [は、次](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) に、その後に、システムの呼び出しを実行して、その後で、 [このメソッドを](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) 呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-107">You can invoke the pipeline synchronously by calling an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, or asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) and then the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

### <a name="addcommand"></a><span data-ttu-id="66fb5-108">AddCommand</span><span class="sxs-lookup"><span data-stu-id="66fb5-108">AddCommand</span></span>

1. <span data-ttu-id="66fb5-109">システムの [管理. Powershell](/dotnet/api/system.management.automation.powershell) オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-109">Create a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="66fb5-110">実行するコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-110">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="66fb5-111">コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-111">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

<span data-ttu-id="66fb5-112">System. powershell. powershell. [powershell. Invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドを呼び出す前に、[このメソッドを](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)複数回呼び出した場合、最初のコマンドの結果がパイプ処理され、次のようになります (以降同様)。</span><span class="sxs-lookup"><span data-stu-id="66fb5-112">If you call the [System.Management.Automation.Powershell.Addcommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="66fb5-113">パイプを使用して前のコマンドの結果をコマンドに渡したくない場合は [、代わりに system.object](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) を呼び出して追加してください。</span><span class="sxs-lookup"><span data-stu-id="66fb5-113">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="66fb5-114">AddParameter</span><span class="sxs-lookup"><span data-stu-id="66fb5-114">AddParameter</span></span>

 <span data-ttu-id="66fb5-115">前の例では、パラメーターを指定せずに1つのコマンドを実行しています。</span><span class="sxs-lookup"><span data-stu-id="66fb5-115">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="66fb5-116">コマンドにパラメーターを追加するに [は、次](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) のコード例のように、 `PowerShell` コンピューター上で実行されているという名前のすべてのプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-116">You can add parameters to the command by using the [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

<span data-ttu-id="66fb5-117">追加のパラメーターを追加するには、さらにパラメーターを追加します。 [Addparameter \*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-117">You can add additional parameters by calling [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Command")
                   .AddParameter("Name", "Get-VM")
                   .AddParameter("Module", "Hyper-V")
                   .Invoke();
```

<span data-ttu-id="66fb5-118">また、パラメーターの名前と値のディクショナリを追加するには、 [System. Powershell. Addparameters \*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-118">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.Powershell.Addparameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "Get-VM");

parameters.Add("Module", "Hyper-V");
PowerShell.Create().AddCommand("Get-Command")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="66fb5-119">AddStatement</span><span class="sxs-lookup"><span data-stu-id="66fb5-119">AddStatement</span></span>

<span data-ttu-id="66fb5-120">バッチ処理をシミュレートするには[](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) 、次のコードで実行中のプロセスの一覧を名前で取得し、 `PowerShell` 実行中のサービスの一覧を取得します。このメソッドを使用して、パイプラインの末尾にステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-120">You can simulate batching by using the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="66fb5-121">AddScript</span><span class="sxs-lookup"><span data-stu-id="66fb5-121">AddScript</span></span>

<span data-ttu-id="66fb5-122">既存のスクリプトを実行するには、 [System. Powershell. Addscript \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-122">You can run an existing script by calling the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="66fb5-123">次の例では、パイプラインにスクリプトを追加して実行します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-123">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="66fb5-124">この例では、という名前のフォルダーにという名前のスクリプトが既に存在することを前提としてい `MyScript.ps1` `D:\PSScripts` ます。</span><span class="sxs-lookup"><span data-stu-id="66fb5-124">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

<span data-ttu-id="66fb5-125">また、という名前のブール型パラメーターを受け取る、バージョンの system.string. [Addscript \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) メソッドもあり `useLocalScope` ます。</span><span class="sxs-lookup"><span data-stu-id="66fb5-125">There is also a version of the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="66fb5-126">このパラメーターがに設定されている場合、 `true` スクリプトはローカルスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="66fb5-126">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="66fb5-127">次のコードでは、スクリプトがローカルスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="66fb5-127">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a><span data-ttu-id="66fb5-128">パイプラインの同期的な呼び出し</span><span class="sxs-lookup"><span data-stu-id="66fb5-128">Invoking a pipeline synchronously</span></span>

<span data-ttu-id="66fb5-129">パイプラインに要素を追加したら、それを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-129">After you add elements to the pipeline, you invoke it.</span></span> <span data-ttu-id="66fb5-130">パイプラインを同期的に呼び出すには、 [System. Powershell. invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) メソッドのオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66fb5-130">To invoke the pipeline synchronously, you call an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method.</span></span> <span data-ttu-id="66fb5-131">次の例は、パイプラインを同期的に呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="66fb5-131">The following example shows how to synchronously invoke a pipeline.</span></span>

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

### <a name="invoking-a-pipeline-asynchronously"></a><span data-ttu-id="66fb5-132">パイプラインの非同期呼び出し</span><span class="sxs-lookup"><span data-stu-id="66fb5-132">Invoking a pipeline asynchronously</span></span>

<span data-ttu-id="66fb5-133">パイプラインを非同期的に呼び出すには、 [システム](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) のオーバーロードを呼び出して、 [IAsyncResult](/dotnet/api/system.iasyncresult) オブジェクトを作成し、次に、その後に system.servicemodel [\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="66fb5-133">You invoke a pipeline asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) to create an [IAsyncResult](/dotnet/api/system.iasyncresult) object, and then calling the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

 <span data-ttu-id="66fb5-134">次の例は、パイプラインを非同期的に呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="66fb5-134">The following example shows how to invoke a pipeline asynchronously.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="66fb5-135">参照</span><span class="sxs-lookup"><span data-stu-id="66fb5-135">See Also</span></span>

 [<span data-ttu-id="66fb5-136">InitialSessionState を作成する</span><span class="sxs-lookup"><span data-stu-id="66fb5-136">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

 [<span data-ttu-id="66fb5-137">制約付き実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="66fb5-137">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

---
title: コマンドの追加と呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62be8432-28c1-4ca2-bcdb-d0350163fa8c
caps.latest.revision: 5
ms.openlocfilehash: f776f13fe743a3f5f67de0d94883e3f754040ffc
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367641"
---
# <a name="adding-and-invoking-commands"></a><span data-ttu-id="fc294-102">コマンドを追加し、呼び出す</span><span class="sxs-lookup"><span data-stu-id="fc294-102">Adding and invoking commands</span></span>

<span data-ttu-id="fc294-103">実行空間を作成した後、Windows PowerShellcommands とスクリプトをパイプラインに追加し、同期または非同期でパイプラインを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fc294-103">After creating a runspace, you can add Windows PowerShellcommands and scripts to a pipeline, and then invoke the pipeline synchronously or asynchronously.</span></span>

## <a name="creating-a-pipeline"></a><span data-ttu-id="fc294-104">パイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="fc294-104">Creating a pipeline</span></span>

 <span data-ttu-id="fc294-105">[System. Automation. Powershell](/dotnet/api/system.management.automation.powershell)クラスには、コマンド、パラメーター、およびスクリプトをパイプラインに追加するためのメソッドがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="fc294-105">The [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class provides several methods to add commands, parameters, and scripts to the pipeline.</span></span> <span data-ttu-id="fc294-106">パイプラインを同期的に呼び出すには、[システム](/dotnet/api/System.Management.Automation.PowerShell.Invoke)のオーバーロードを呼び出すか、または、[システム](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke)のオーバーロードを呼び出すことによって非同期的に呼び出します。次に、「」と入力し[ます。](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)</span><span class="sxs-lookup"><span data-stu-id="fc294-106">You can invoke the pipeline synchronously by calling an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, or asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) and then the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

### <a name="addcommand"></a><span data-ttu-id="fc294-107">AddCommand</span><span class="sxs-lookup"><span data-stu-id="fc294-107">AddCommand</span></span>

1. <span data-ttu-id="fc294-108">システムの[管理. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc294-108">Create a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="fc294-109">実行するコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="fc294-109">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="fc294-110">コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fc294-110">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

 <span data-ttu-id="fc294-111">System. powershell. powershell. [powershell. Invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドを呼び出す前に、[このメソッドを](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)複数回呼び出した場合、最初のコマンドの結果がパイプ処理され、次のようになります (以降同様)。</span><span class="sxs-lookup"><span data-stu-id="fc294-111">If you call the [System.Management.Automation.Powershell.Addcommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="fc294-112">パイプを使用して前のコマンドの結果をコマンドに渡したくない場合は[、代わりに system.object](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)を呼び出して追加してください。</span><span class="sxs-lookup"><span data-stu-id="fc294-112">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="fc294-113">AddParameter</span><span class="sxs-lookup"><span data-stu-id="fc294-113">AddParameter</span></span>

 <span data-ttu-id="fc294-114">前の例では、パラメーターを指定せずに1つのコマンドを実行しています。</span><span class="sxs-lookup"><span data-stu-id="fc294-114">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="fc294-115">コマンドにパラメーターを追加するに[は、次](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)のコードを使用します。たとえば、次のコードは、コンピューター上で実行されている `PowerShell` という名前のすべてのプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="fc294-115">You can add parameters to the command by using the [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

 <span data-ttu-id="fc294-116">追加のパラメーターを追加するには、さらにパラメーターを追加します。 [Addparameter \*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fc294-116">You can add additional parameters by calling [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

 <span data-ttu-id="fc294-117">また、パラメーターの名前と値のディクショナリを追加するには、 [System. Powershell. Addparameters \*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fc294-117">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.Powershell.Addparameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="fc294-118">AddStatement</span><span class="sxs-lookup"><span data-stu-id="fc294-118">AddStatement</span></span>

 <span data-ttu-id="fc294-119">バッチ処理をシミュレートするには、次のコードでは、パイプラインの末尾にステートメントを追加する、 [System. Powershell. Addstatement \*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)メソッドを使用します。次のコードは、`PowerShell` という名前の実行中のプロセスの一覧を取得し、実行中のサービスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="fc294-119">You can simulate batching by using the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="fc294-120">AddScript</span><span class="sxs-lookup"><span data-stu-id="fc294-120">AddScript</span></span>

 <span data-ttu-id="fc294-121">既存のスクリプトを実行するには、 [System. Powershell. Addscript \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fc294-121">You can run an existing script by calling the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="fc294-122">次の例では、パイプラインにスクリプトを追加して実行します。</span><span class="sxs-lookup"><span data-stu-id="fc294-122">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="fc294-123">この例では、`D:\PSScripts` という名前のフォルダーに `MyScript.ps1` という名前のスクリプトが既に存在することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="fc294-123">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

 <span data-ttu-id="fc294-124">また、`useLocalScope` という名前のブール型パラメーターを受け取るバージョンの[System. Powershell. Addscript \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)メソッドもあります。</span><span class="sxs-lookup"><span data-stu-id="fc294-124">There is also a version of the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="fc294-125">このパラメーターを `true` に設定すると、スクリプトはローカルスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fc294-125">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="fc294-126">次のコードでは、スクリプトがローカルスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fc294-126">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a><span data-ttu-id="fc294-127">パイプラインの同期的な呼び出し</span><span class="sxs-lookup"><span data-stu-id="fc294-127">Invoking a pipeline synchronously</span></span>

 <span data-ttu-id="fc294-128">パイプラインに要素を追加したら、それを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fc294-128">After you add elements to the pipeline, you invoke it.</span></span> <span data-ttu-id="fc294-129">パイプラインを同期的に呼び出すには、 [System. Powershell. invoke \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドのオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fc294-129">To invoke the pipeline synchronously, you call an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method.</span></span> <span data-ttu-id="fc294-130">次の例は、パイプラインを同期的に呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fc294-130">The following example shows how to synchronously invoke a pipeline.</span></span>

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

### <a name="invoking-a-pipeline-asynchronously"></a><span data-ttu-id="fc294-131">パイプラインの非同期呼び出し</span><span class="sxs-lookup"><span data-stu-id="fc294-131">Invoking a pipeline asynchronously</span></span>

 <span data-ttu-id="fc294-132">パイプラインを非同期的に呼び出すには、[システム](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke)のオーバーロードを呼び出して[IAsyncResult](https://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx)オブジェクトを作成し、次に、その後に system.servicemodel を呼び出します。これには、次のように入力します。 [\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fc294-132">You invoke a pipeline asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) to create an [IAsyncResult](https://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx) object, and then calling the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

 <span data-ttu-id="fc294-133">次の例は、パイプラインを非同期的に呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fc294-133">The following example shows how to invoke a pipeline asynchronously.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="fc294-134">参照</span><span class="sxs-lookup"><span data-stu-id="fc294-134">See Also</span></span>

 [<span data-ttu-id="fc294-135">InitialSessionState の作成</span><span class="sxs-lookup"><span data-stu-id="fc294-135">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

 [<span data-ttu-id="fc294-136">制約付き実行空間の作成</span><span class="sxs-lookup"><span data-stu-id="fc294-136">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

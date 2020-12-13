---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace09 サンプル
description: Runspace09 サンプル
ms.openlocfilehash: 8dedc3e2ee7c1d41f7b7ad367d8cebeb5f58b8e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657618"
---
# <a name="runspace09-sample"></a><span data-ttu-id="c7acf-103">Runspace09 サンプル</span><span class="sxs-lookup"><span data-stu-id="c7acf-103">Runspace09 Sample</span></span>

<span data-ttu-id="c7acf-104">このサンプルでは、スクリプトを [システム](/dotnet/api/system.management.automation.powershell) のパイプラインに追加する方法と、スクリプトを非同期で実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c7acf-104">This sample shows how to add a script to the pipeline of a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object and how to run the script asynchronously.</span></span> <span data-ttu-id="c7acf-105">イベントはスクリプトの出力を処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7acf-105">Events are used to handle the output of the script.</span></span>

## <a name="requirements"></a><span data-ttu-id="c7acf-106">要件</span><span class="sxs-lookup"><span data-stu-id="c7acf-106">Requirements</span></span>

<span data-ttu-id="c7acf-107">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="c7acf-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="c7acf-108">対象</span><span class="sxs-lookup"><span data-stu-id="c7acf-108">Demonstrates</span></span>

<span data-ttu-id="c7acf-109">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="c7acf-109">This sample demonstrates the following.</span></span>

- <span data-ttu-id="c7acf-110">実行空間 [を使用](/dotnet/api/system.management.automation.powershell) する、system.string オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7acf-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="c7acf-111">スクリプトを追加して、 [システムの管理. Powershell](/dotnet/api/system.management.automation.powershell) オブジェクトのパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7acf-111">Adding a script the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="c7acf-112">パイプラインを非同期的に実行するために、 [このメソッドを](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) 使用します。</span><span class="sxs-lookup"><span data-stu-id="c7acf-112">Using the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) method to run the pipeline asynchronously.</span></span>

- <span data-ttu-id="c7acf-113">[システム管理](/dotnet/api/system.management.automation.powershell)オブジェクトのイベントを使用して、スクリプトの出力を処理します。</span><span class="sxs-lookup"><span data-stu-id="c7acf-113">Using the events of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to process the output of the script.</span></span>

- <span data-ttu-id="c7acf-114">パイプラインの呼び出しを中断するに [は、「」のよう](/dotnet/api/System.Management.Automation.PowerShell.Stop) にします。</span><span class="sxs-lookup"><span data-stu-id="c7acf-114">Using the [System.Management.Automation.Powershell.Stop\*](/dotnet/api/System.Management.Automation.PowerShell.Stop) method to interrupt the invocation of the pipeline.</span></span>

## <a name="example"></a><span data-ttu-id="c7acf-115">例</span><span class="sxs-lookup"><span data-stu-id="c7acf-115">Example</span></span>

<span data-ttu-id="c7acf-116">このサンプルを実行すると、1 ~ 10 の数値を生成するスクリプトが実行され、各数値の間に遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="c7acf-116">This sample runs to run a script that generates the numbers from 1 to 10 with delays between each number.</span></span> <span data-ttu-id="c7acf-117">スクリプトは非同期に実行され、イベントを使用して出力が処理されます。</span><span class="sxs-lookup"><span data-stu-id="c7acf-117">The script is run asynchronously and events are used to handle the output.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.Generic;
  using System.Collections.ObjectModel;
  using System.Diagnostics;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace09
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run a
    /// script that generates the numbers from 1 to 10 with delays
    /// between each number. The pipeline of the PowerShell object
    /// is run asynchronously and events are used to handle the output.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object.
    /// 2. Adding a script to the pipeline of the PowerShell object.
    /// 3. Using the BeginInvoke method to run the pipeline asynchronously.
    /// 4. Using the events of the PowerShell object to process the
    ///    output of the script.
    /// 5. Using the PowerShell.Stop() method to interrupt the invocation of
    ///    the pipeline.
    /// </remarks>
    private static void Main(string[] args)
    {
      Console.WriteLine("Print the numbers from 1 to 10. Hit any key to halt processing\n");

      using (PowerShell powershell = PowerShell.Create())
      {
        // Add a script to the PowerShell object. The script generates the
        // numbers from 1 to 10 in half second intervals.
        powershell.AddScript("1..10 | foreach {$_ ; start-sleep -milli 500}");

        // Add the event handlers.  If we did not care about hooking the DataAdded
        // event, we would let BeginInvoke create the output stream for us.
        PSDataCollection<PSObject> output = new PSDataCollection<PSObject>();
        output.DataAdded += new EventHandler<DataAddedEventArgs>(Output_DataAdded);
        powershell.InvocationStateChanged += new EventHandler<PSInvocationStateChangedEventArgs>(Powershell_InvocationStateChanged);

        // Invoke the pipeline asynchronously.
        IAsyncResult asyncResult = powershell.BeginInvoke<PSObject, PSObject>(null, output);

        // Wait for things to happen. If the user hits a key before the
        // script has completed, then call the PowerShell Stop() method
        // to halt processing.
        Console.ReadKey();
        if (powershell.InvocationStateInfo.State != PSInvocationState.Completed)
        {
          // Stop the invocation of the pipeline.
          Console.WriteLine("\nStopping the pipeline!\n");
          powershell.Stop();

          // Wait for the Windows PowerShell state change messages to be displayed.
          System.Threading.Thread.Sleep(500);
          Console.WriteLine("\nPress a key to exit");
          Console.ReadKey();
        }
      }
    }

    /// <summary>
    /// The output data added event handler. This event is called when
    /// data is added to the output pipe. It reads the data that is
    /// available and displays it on the console.
    /// </summary>
    /// <param name="sender">The output pipe this event is associated with.</param>
    /// <param name="e">Parameter is not used.</param>
    private static void Output_DataAdded(object sender, DataAddedEventArgs e)
    {
      PSDataCollection<PSObject> myp = (PSDataCollection<PSObject>)sender;

      Collection<PSObject> results = myp.ReadAll();
      foreach (PSObject result in results)
      {
        Console.WriteLine(result.ToString());
      }
    }

    /// <summary>
    /// This event handler is called when the pipeline state is changed.
    /// If the state change is to Completed, the handler issues a message
    /// asking the user to exit the program.
    /// </summary>
    /// <param name="sender">This parameter is not used.</param>
    /// <param name="e">The PowerShell state information.</param>
    private static void Powershell_InvocationStateChanged(object sender, PSInvocationStateChangedEventArgs e)
    {
      Console.WriteLine("PowerShell object state changed: state: {0}\n", e.InvocationStateInfo.State);
      if (e.InvocationStateInfo.State == PSInvocationState.Completed)
      {
        Console.WriteLine("Processing completed, press a key to exit!");
      }
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="c7acf-118">参照</span><span class="sxs-lookup"><span data-stu-id="c7acf-118">See Also</span></span>

[<span data-ttu-id="c7acf-119">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="c7acf-119">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)

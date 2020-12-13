---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace10 サンプル
description: Runspace10 サンプル
ms.openlocfilehash: fd58cea553e6b830a56df7edfa7901d39f46a06c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657582"
---
# <a name="runspace10-sample"></a><span data-ttu-id="e405d-103">Runspace10 サンプル</span><span class="sxs-lookup"><span data-stu-id="e405d-103">Runspace10 Sample</span></span>

<span data-ttu-id="e405d-104">このサンプルでは、既定の初期セッション状態を作成する方法、コマンドレットを[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)に追加する方法、初期セッション状態を使用する実行空間を作成する方法、およびオブジェクトを使用してコマンドを実行する方法を示し[ます。](/dotnet/api/system.management.automation.powershell)</span><span class="sxs-lookup"><span data-stu-id="e405d-104">This sample shows how to create a default initial session state, how to add a cmdlet to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState), how to create a runspace that uses the initial session state, and how to run the command by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="e405d-105">要件</span><span class="sxs-lookup"><span data-stu-id="e405d-105">Requirements</span></span>

<span data-ttu-id="e405d-106">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e405d-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e405d-107">対象</span><span class="sxs-lookup"><span data-stu-id="e405d-107">Demonstrates</span></span>

<span data-ttu-id="e405d-108">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="e405d-108">This sample demonstrates the following.</span></span>

- <span data-ttu-id="e405d-109">[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="e405d-109">Creating an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="e405d-110">(ホストアプリケーションによって定義された) コマンドレットを [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) オブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e405d-110">Adding a cmdlet (defined by the Host application) to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="e405d-111">オブジェクトを使用する、 [system.string オブジェクトを](/dotnet/api/System.Management.Automation.Runspaces.Runspace) 作成します。</span><span class="sxs-lookup"><span data-stu-id="e405d-111">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object that uses the object.</span></span>

- <span data-ttu-id="e405d-112">System.object オブジェクトを使用する、 [システムの管理](/dotnet/api/system.management.automation.powershell) ........... [...](/dotnet/api/System.Management.Automation.Runspaces.Runspace) .................</span><span class="sxs-lookup"><span data-stu-id="e405d-112">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>

- <span data-ttu-id="e405d-113">コマンド [を、system.servicemodel オブジェクトの](/dotnet/api/system.management.automation.powershell) パイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="e405d-113">Adding the command to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="e405d-114">コマンドによって返された、 [システムの管理](/dotnet/api/System.Management.Automation.PSObject) オブジェクトからプロパティを抽出しています。</span><span class="sxs-lookup"><span data-stu-id="e405d-114">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="e405d-115">例</span><span class="sxs-lookup"><span data-stu-id="e405d-115">Example</span></span>

<span data-ttu-id="e405d-116">このサンプルでは、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) オブジェクトを使用して、実行空間を開いたときに使用可能な要素を定義する実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="e405d-116">This sample creates a runspace that uses an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to define the elements that are available when the runspace is opened.</span></span> <span data-ttu-id="e405d-117">このサンプルでは、(ホストアプリケーションによって定義される) Get-Proc コマンドレットが初期セッション状態に追加され、コマンドレットは、 [System. Powershell](/dotnet/api/system.management.automation.powershell) オブジェクトを使用して同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e405d-117">In this sample, the Get-Proc cmdlet (defined by the Host application) is added to the initial session state, and the cmdlet is run synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

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

  #region GetProcCommand

  /// <summary>
  /// Class that implements the GetProcCommand.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Cmdlet Overrides

    /// <summary>
    /// For each of the requested process names, retrieve and write
    /// the associated processes.
    /// </summary>
    protected override void ProcessRecord()
    {
      // Get the current processes.
      Process[] processes = Process.GetProcesses();

      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument (true) tells the
      // system to enumerate the array, and send one process object
      // at a time to the pipeline.
      WriteObject(processes, true);
    }

    #endregion Overrides
  } // End GetProcCommand class.

  #endregion GetProcCommand

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace10
  {
    /// <summary>
    /// This sample shows how to create a default initial session state, how to add
    /// add a cmdlet to the InitialSessionState object, and then how to create
    /// a Runspace object.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    /// This sample demonstrates:
    /// 1. Creating an InitialSessionState object.
    /// 2. Adding a cmdlet to the InitialSessionState object.
    /// 3. Creating a runspace that uses the InitialSessionState object.
    /// 4. Creating a PowerShell object that uses the Runspace object.
    /// 5. Running the added command synchronously.
    /// 6. Working with PSObject objects to extract properties
    ///    from the objects returned by the pipeline.
    private static void Main(string[] args)
    {
      // Create a default InitialSessionState object. The default
      // InitialSessionState object contains all the elements provided
      // by Windows PowerShell.
      InitialSessionState iss = InitialSessionState.CreateDefault();

      // Add the get-proc cmdlet to the InitialSessionState object.
      SessionStateCmdletEntry ssce = new SessionStateCmdletEntry("get-proc", typeof(GetProcCommand), null);
      iss.Commands.Add(ssce);

      // Create a Runspace object that uses the InitialSessionState object.
      // Notice that no PSHost object is specified, so the default host is used.
      // See the Hosting samples for information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = myRunSpace;

          // Add the get-proc cmdlet to the pipeline of the PowerShell object.
          powershell.AddCommand("get-proc");

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the output of the pipeline.
          foreach (PSObject result in results)
          {
             Console.WriteLine(
                               "{0,-20} {1}",
                               result.Members["ProcessName"].Value,
                               result.Members["HandleCount"].Value);
          }
        }

        // Close the runspace to release resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="e405d-118">参照</span><span class="sxs-lookup"><span data-stu-id="e405d-118">See Also</span></span>

[<span data-ttu-id="e405d-119">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="e405d-119">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)

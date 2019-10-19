---
title: 複数の実行空間を作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42c40c7f-1ee7-4021-950c-2e013c8f2a4a
caps.latest.revision: 4
ms.openlocfilehash: 606a2ee4e70d303bf1b1d69b7523eb8649f9be0c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367611"
---
# <a name="creating-multiple-runspaces"></a><span data-ttu-id="b9dc3-102">複数の実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="b9dc3-102">Creating multiple runspaces</span></span>

<span data-ttu-id="b9dc3-103">多数の実行空間を作成する場合は、実行空間プールを作成することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b9dc3-103">If you create a large number of runspaces, you might consider creating a runspace pool.</span></span> <span data-ttu-id="b9dc3-104">同じ特性を持つ多数の個別の実行空間を作成するのではなく、 [Runspacepool](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool)オブジェクトを使用すると、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="b9dc3-104">Using a [System.Management.Automation.Runspaces.Runspacepool](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool) object, rather than creating a large number of individual runspaces with the same characteristics, can improve performance.</span></span>

## <a name="creating-and-using-a-runspace-pool"></a><span data-ttu-id="b9dc3-105">実行空間プールを作成して使用する。</span><span class="sxs-lookup"><span data-stu-id="b9dc3-105">Creating and using a runspace pool.</span></span>

 <span data-ttu-id="b9dc3-106">次の例は、実行空間プールを作成する方法と、プールの実行空間でコマンドを非同期的に実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b9dc3-106">The following example shows how to create a runspace pool and how to run a command asynchronously in a runspace of the pool.</span></span>

```csharp
namespace HostRunspacePool
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  /// <summary>
  /// This class provides the Main entry point for the Host application.
  /// </summary>
  internal class HostRunspacePool
  {
    /// <summary>
    /// This sample demonstrates the following.
    /// 1. Creating and opening a runspace pool.
    /// 2. Creating a PowerShell object.
    /// 3. Adding commands and arguments to the PowerShell object.
    /// 4. Running the commands asynchronously using the runspace
    ///    of the runspace pool.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    private static void Main(string[] args)
    {
      // Create a pool of runspaces.
      using (RunspacePool rsp = RunspaceFactory.CreateRunspacePool())
      {
        rsp.Open();

        // Create a PowerShell object to run the following command.
        //  get-process wmi*
        PowerShell gpc = PowerShell.Create();
        // Specify the runspace to use and add commands.
        gpc.RunspacePool = rsp;
        gpc.AddCommand("Get-Process").AddArgument("wmi*");

        // Invoke the command asynchronously.
        IAsyncResult gpcAsyncResult = gpc.BeginInvoke();
        // Get the results of running the command.
        PSDataCollection<PSObject> gpcOutput = gpc.EndInvoke(gpcAsyncResult);

        // Process the output.
        Console.WriteLine("The output from running the command: get-process wmi*");
        for (int i= 0; i < gpcOutput.Count; i++)
        {
         Console.WriteLine(
                           "Process Name: {0} Process Id: {1}",
                           gpcOutput[i].Properties["ProcessName"].Value,
                           gpcOutput[i].Properties["Id"].Value);
        }
      } // End using.
    } // End Main entry point.
  } // End HostPs5 class.
}
```

## <a name="see-also"></a><span data-ttu-id="b9dc3-107">参照</span><span class="sxs-lookup"><span data-stu-id="b9dc3-107">See Also</span></span>

 [<span data-ttu-id="b9dc3-108">InitialSessionState の作成</span><span class="sxs-lookup"><span data-stu-id="b9dc3-108">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)
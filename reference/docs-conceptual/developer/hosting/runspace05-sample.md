---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace05 サンプル
description: Runspace05 サンプル
ms.openlocfilehash: 67a372eecba30452587471328412e8a2bdd9ec5a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657725"
---
# <a name="runspace05-sample"></a><span data-ttu-id="35c5a-103">Runspace05 サンプル</span><span class="sxs-lookup"><span data-stu-id="35c5a-103">Runspace05 Sample</span></span>

<span data-ttu-id="35c5a-104">このサンプルでは、 [ tialsessionstate オブジェクトSystem.Management.Automation.Runspaces.Ini](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) にスナップインを追加して、実行空間を開いたときにスナップインのコマンドレットを使用できるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="35c5a-104">This sample shows how to add a snap-in to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the cmdlet of the snap-in is available when the runspace is opened.</span></span> <span data-ttu-id="35c5a-105">スナップインには、 [GetProcessSample01 サンプル](../cmdlet/getprocesssample01-sample.md)で定義されている Get-Proc コマンドレットが用意されています。これ [は、オブジェクトを](/dotnet/api/system.management.automation.powershell) 使用して同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="35c5a-105">The snap-in provides a Get-Proc cmdlet (defined by the [GetProcessSample01 Sample](../cmdlet/getprocesssample01-sample.md)) that is run synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="35c5a-106">要件</span><span class="sxs-lookup"><span data-stu-id="35c5a-106">Requirements</span></span>

<span data-ttu-id="35c5a-107">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="35c5a-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="35c5a-108">対象</span><span class="sxs-lookup"><span data-stu-id="35c5a-108">Demonstrates</span></span>

<span data-ttu-id="35c5a-109">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="35c5a-109">This sample demonstrates the following.</span></span>

- <span data-ttu-id="35c5a-110">[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="35c5a-110">Creating an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="35c5a-111">スナップインを [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) オブジェクトに追加しています。</span><span class="sxs-lookup"><span data-stu-id="35c5a-111">Adding the snap-in to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="35c5a-112">[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを使用する、 [system.string オブジェクトを](/dotnet/api/System.Management.Automation.Runspaces.Runspace)作成します。</span><span class="sxs-lookup"><span data-stu-id="35c5a-112">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object that uses the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="35c5a-113">実行空間 [を使用](/dotnet/api/system.management.automation.powershell) する、system.string オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="35c5a-113">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="35c5a-114">スナップインの get proc コマンドレットを、 [System. Powershell](/dotnet/api/system.management.automation.powershell) オブジェクトのパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="35c5a-114">Adding the snap-in's get-proc cmdlet to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="35c5a-115">コマンドを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="35c5a-115">Running the command synchronously.</span></span>

- <span data-ttu-id="35c5a-116">コマンドによって返された、 [システムの管理](/dotnet/api/System.Management.Automation.PSObject) オブジェクトからプロパティを抽出しています。</span><span class="sxs-lookup"><span data-stu-id="35c5a-116">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="35c5a-117">例</span><span class="sxs-lookup"><span data-stu-id="35c5a-117">Example</span></span>

<span data-ttu-id="35c5a-118">このサンプルでは、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) オブジェクトを使用して、実行空間を開いたときに使用可能な要素を定義する実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="35c5a-118">This sample creates a runspace that uses an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to define the elements that are available when the runspace is opened.</span></span> <span data-ttu-id="35c5a-119">このサンプルでは、Get-Proc コマンドレットを定義するスナップインを初期セッション状態に追加します。</span><span class="sxs-lookup"><span data-stu-id="35c5a-119">In this sample, a snap-in that defines a Get-Proc cmdlet is added to the initial session state.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace05
  {
    /// <summary>
    /// This sample shows how to define an initial session state that is
    /// used when creating a runspace. The sample invokes a command from
    /// a Windows PowerShell snap-in that is present in the console file.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample assumes that user has coppied the GetProcessSample01.dll
    /// that is produced by the GetProcessSample01 sample to the current
    /// directory.
    /// This sample demonstrates the following:
    /// 1. Creating a default initial session state.
    /// 2. Adding a snap-in to the initial session state.
    /// 3. Creating a runspace that uses the initial session state.
    /// 4. Creating a PowerShell object that uses the runspace.
    /// 5. Adding the snap-in's get-proc cmdlet to the PowerShell object.
    /// 6. Using PSObject objects to extract and display properties from
    ///    the objects returned by the cmdlet.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create the default initial session state. The default initial
      // session state contains all the elements provided by Windows
      // PowerShell.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      PSSnapInException warning;
      iss.ImportPSSnapIn("GetProcPSSnapIn01", out warning);

      // Create a runspace. Notice that no PSHost object is supplied to the
      // CreateRunspace method so the default host is used. See the Host
      // samples for more information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        // Create a PowerShell object.
        using (PowerShell powershell = PowerShell.Create())
        {
          // Add the snap-in cmdlet and specify the runspace.
          powershell.AddCommand("GetProcPSSnapIn01\\get-proc");
          powershell.Runspace = myRunSpace;

          // Run the cmdlet synchronously.
          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the results.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                              "{0,-20} {1}",
                              result.Members["ProcessName"].Value,
                              result.Members["HandleCount"].Value);
          }
        }

        // Close the runspace to release any resources.
        myRunSpace.Close();
      }
      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="35c5a-120">参照</span><span class="sxs-lookup"><span data-stu-id="35c5a-120">See Also</span></span>

[<span data-ttu-id="35c5a-121">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="35c5a-121">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)

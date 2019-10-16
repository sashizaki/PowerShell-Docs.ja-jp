---
title: Runspace05 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1685cfc4-b32c-4bed-b221-e0c4482db955
caps.latest.revision: 9
ms.openlocfilehash: eb227b5fa5e91f59b6fc99981ff5affca1cf63fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360881"
---
# <a name="runspace05-sample"></a><span data-ttu-id="7ca55-102">Runspace05 サンプル</span><span class="sxs-lookup"><span data-stu-id="7ca55-102">Runspace05 Sample</span></span>

<span data-ttu-id="7ca55-103">このサンプルでは、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトにスナップインを追加して、実行空間を開いたときにスナップインのコマンドレットを使用できるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7ca55-103">This sample shows how to add a snap-in to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the cmdlet of the snap-in is available when the runspace is opened.</span></span> <span data-ttu-id="7ca55-104">スナップインには、 [GetProcessSample01 サンプル](../cmdlet/getprocesssample01-sample.md)で定義されている Get Proc コマンドレットが用意されています。このコマンドレットは、 [System. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトを使用して同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="7ca55-104">The snap-in provides a Get-Proc cmdlet (defined by the [GetProcessSample01 Sample](../cmdlet/getprocesssample01-sample.md)) that is run synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ca55-105">要件</span><span class="sxs-lookup"><span data-stu-id="7ca55-105">Requirements</span></span>

<span data-ttu-id="7ca55-106">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="7ca55-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="7ca55-107">サンプル</span><span class="sxs-lookup"><span data-stu-id="7ca55-107">Demonstrates</span></span>

<span data-ttu-id="7ca55-108">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="7ca55-108">This sample demonstrates the following.</span></span>

- <span data-ttu-id="7ca55-109">[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="7ca55-109">Creating an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="7ca55-110">[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトにスナップインを追加していません。</span><span class="sxs-lookup"><span data-stu-id="7ca55-110">Adding the snap-in to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="7ca55-111">[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを使用[する、system.string オブジェクトを作成](/dotnet/api/System.Management.Automation.Runspaces.Runspace)していますを使用しています。</span><span class="sxs-lookup"><span data-stu-id="7ca55-111">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object that uses the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="7ca55-112">実行空間[を使用](/dotnet/api/system.management.automation.powershell)する、system.string オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7ca55-112">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="7ca55-113">スナップインの get proc コマンドレットを、 [System. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトのパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="7ca55-113">Adding the snap-in's get-proc cmdlet to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="7ca55-114">コマンドを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="7ca55-114">Running the command synchronously.</span></span>

- <span data-ttu-id="7ca55-115">コマンドによって返された、[システムの管理](/dotnet/api/System.Management.Automation.PSObject)オブジェクトからプロパティを抽出しています。</span><span class="sxs-lookup"><span data-stu-id="7ca55-115">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="7ca55-116">例</span><span class="sxs-lookup"><span data-stu-id="7ca55-116">Example</span></span>

<span data-ttu-id="7ca55-117">このサンプルでは、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを使用して、実行空間を開いたときに使用可能な要素を定義する実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="7ca55-117">This sample creates a runspace that uses an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to define the elements that are available when the runspace is opened.</span></span> <span data-ttu-id="7ca55-118">このサンプルでは、Get Proc コマンドレットを定義するスナップインを初期セッション状態に追加します。</span><span class="sxs-lookup"><span data-stu-id="7ca55-118">In this sample, a snap-in that defines a Get-Proc cmdlet is added to the initial session state.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7ca55-119">参照</span><span class="sxs-lookup"><span data-stu-id="7ca55-119">See Also</span></span>

[<span data-ttu-id="7ca55-120">Windows PowerShell ホストアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="7ca55-120">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
---
title: Runspace06 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 471c85f3-9287-45c2-b4bc-833caa1b7634
caps.latest.revision: 8
ms.openlocfilehash: 3850aec88bc800718a82f51c91fbd0cb3c705089
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367591"
---
# <a name="runspace06-sample"></a><span data-ttu-id="14a3a-102">Runspace06 サンプル</span><span class="sxs-lookup"><span data-stu-id="14a3a-102">Runspace06 Sample</span></span>

<span data-ttu-id="14a3a-103">このサンプルでは、実行空間が開かれたときにモジュールが読み込まれるように、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトにモジュールを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14a3a-103">This sample shows how to add a module to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the module is loaded when the runspace is opened.</span></span> <span data-ttu-id="14a3a-104">このモジュールは、 [GetProcessSample02 サンプル](../cmdlet/getprocesssample02-sample.md)で定義されている Get Proc コマンドレットを提供します。このコマンドレットは、 [System. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトを使用して同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="14a3a-104">The module provides a Get-Proc cmdlet (defined by the [GetProcessSample02 Sample](../cmdlet/getprocesssample02-sample.md)) that is run synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="14a3a-105">要件</span><span class="sxs-lookup"><span data-stu-id="14a3a-105">Requirements</span></span>

<span data-ttu-id="14a3a-106">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="14a3a-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="14a3a-107">サンプル</span><span class="sxs-lookup"><span data-stu-id="14a3a-107">Demonstrates</span></span>

<span data-ttu-id="14a3a-108">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="14a3a-108">This sample demonstrates the following.</span></span>

- <span data-ttu-id="14a3a-109">[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="14a3a-109">Creating an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="14a3a-110">[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトにモジュールを追加しています。</span><span class="sxs-lookup"><span data-stu-id="14a3a-110">Adding the module to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="14a3a-111">[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを使用[する、system.string オブジェクトを作成](/dotnet/api/System.Management.Automation.Runspaces.Runspace)していますを使用しています。</span><span class="sxs-lookup"><span data-stu-id="14a3a-111">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object that uses the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="14a3a-112">実行空間[を使用](/dotnet/api/system.management.automation.powershell)する、system.string オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="14a3a-112">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="14a3a-113">モジュールの get proc コマンドレットを、 [System. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトのパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="14a3a-113">Adding the module's get-proc cmdlet to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="14a3a-114">コマンドを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="14a3a-114">Running the command synchronously.</span></span>

- <span data-ttu-id="14a3a-115">コマンドによって返された、[システムの管理](/dotnet/api/System.Management.Automation.PSObject)オブジェクトからプロパティを抽出しています。</span><span class="sxs-lookup"><span data-stu-id="14a3a-115">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="14a3a-116">例</span><span class="sxs-lookup"><span data-stu-id="14a3a-116">Example</span></span>

<span data-ttu-id="14a3a-117">このサンプルでは、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを使用して、実行空間を開いたときに使用可能な要素を定義する実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="14a3a-117">This sample creates a runspace that uses an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to define the elements that are available when the runspace is opened.</span></span> <span data-ttu-id="14a3a-118">このサンプルでは、Get Proc コマンドレットを定義するモジュールが、初期セッション状態に追加されます。</span><span class="sxs-lookup"><span data-stu-id="14a3a-118">In this sample, a module that defines a Get-Proc cmdlet is added to the initial session state.</span></span>

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
  internal class Runspace06
  {
    /// <summary>
    /// This sample shows how to define an initial session state that is
    /// used when creating a runspace. The sample invokes a command from
    /// a binary module that is loaded by the initial session state.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample assumes that user has coppied the GetProcessSample02.dll
    /// that is produced by the GetProcessSample02 sample to the current
    /// directory.
    /// This sample demonstrates the following:
    /// 1. Creating a default initial session state.
    /// 2. Adding a module to the initial session state.
    /// 3. Creating a runspace that uses the initial session state.
    /// 4. Creating a PowerShell object that uses the runspace.
    /// 5. Adding the module's get-proc cmdlet to the PowerShell object.
    /// 6. Running the command synchronously.
    /// 7. Using PSObject objects to extract and display properties from
    ///    the objects returned by the cmdlet.
    /// </remarks>
    private static void Main(string[] args)
    {
        // Create the default initial session state and add the module.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      iss.ImportPSModule(new string[] { @".\GetProcessSample02.dll" });

      // Create a runspace. Notice that no PSHost object is supplied to the
      // CreateRunspace method so the default host is used. See the Host
      // samples for more information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        // Create a PowerShell object.
        using (PowerShell powershell = PowerShell.Create())
        {
          // Add the cmdlet and specify the runspace.
          powershell.AddCommand(@"GetProcessSample02\get-proc");
          powershell.Runspace = myRunSpace;

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

## <a name="see-also"></a><span data-ttu-id="14a3a-119">参照</span><span class="sxs-lookup"><span data-stu-id="14a3a-119">See Also</span></span>

[<span data-ttu-id="14a3a-120">Windows PowerShell ホストアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="14a3a-120">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
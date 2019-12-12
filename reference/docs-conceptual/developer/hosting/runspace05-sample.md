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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360881"
---
# <a name="runspace05-sample"></a>Runspace05 サンプル

このサンプルでは、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトにスナップインを追加して、実行空間を開いたときにスナップインのコマンドレットを使用できるようにする方法を示します。 スナップインには、 [GetProcessSample01 サンプル](../cmdlet/getprocesssample01-sample.md)で定義されている Get Proc コマンドレットが用意されています。このコマンドレットは、 [System. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトを使用して同期的に実行されます。

## <a name="requirements"></a>要件

このサンプルには、Windows PowerShell 2.0 が必要です。

## <a name="demonstrates"></a>使用例

このサンプルでは、次のことを示します。

- [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを作成しています。

- [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトにスナップインを追加していません。

- [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを使用[する、system.string オブジェクトを作成](/dotnet/api/System.Management.Automation.Runspaces.Runspace)していますを使用しています。

- 実行空間[を使用](/dotnet/api/system.management.automation.powershell)する、system.string オブジェクトを作成します。

- スナップインの get proc コマンドレットを、 [System. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトのパイプラインに追加します。

- コマンドを同期的に実行します。

- コマンドによって返された、[システムの管理](/dotnet/api/System.Management.Automation.PSObject)オブジェクトからプロパティを抽出しています。

## <a name="example"></a>例

このサンプルでは、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを使用して、実行空間を開いたときに使用可能な要素を定義する実行空間を作成します。 このサンプルでは、Get Proc コマンドレットを定義するスナップインを初期セッション状態に追加します。

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

## <a name="see-also"></a>参照

[Windows PowerShell ホストアプリケーションの作成](./writing-a-windows-powershell-host-application.md)
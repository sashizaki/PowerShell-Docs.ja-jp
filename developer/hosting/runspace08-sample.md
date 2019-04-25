---
title: Runspace08 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1100d91d-249d-4af7-9854-2d6a423ac2f4
caps.latest.revision: 7
ms.openlocfilehash: 70577a6a42ce26e9791360fa30baae9d7a492daf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082638"
---
# <a name="runspace08-sample"></a>Runspace08 サンプル

このサンプルのパイプラインにコマンドと引数を追加する方法を示しています、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトと同期的に、コマンドを実行する方法。

## <a name="requirements"></a>要件

このサンプルでは、Windows PowerShell 2.0 が必要です。

## <a name="demonstrates"></a>使用例

このサンプルは、次を示します。

- 作成、 [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace)オブジェクトを使用して、 [System.Management.Automation.Runspaces.Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory)クラス。

- 作成、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)実行空間を使用するオブジェクト。

- パイプラインにコマンドレットを追加、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。

- コマンドレットを同期的に実行します。

- プロパティからの抽出、 [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject)コマンドによって返されるオブジェクト。

## <a name="example"></a>例

このサンプルの実行、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)と[Sort-object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object)コマンドレットを使用して、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.Generic;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace08
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands. The
    /// PowerShell object builds a pipeline that include the get-process cmdlet,
    /// which is then piped to the sort-object cmdlet. Parameters are added to the
    /// sort-object cmdlet to sort the HandleCount property in descending order.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates:
    /// 1. Creating a PowerShell object
    /// 2. Adding individual commands to the PowerShell object.
    /// 3. Adding parameters to the commands.
    /// 4. Running the pipeline of the PowerShell object synchronously.
    /// 5. Working with PSObject objects to extract properties
    ///    from the objects returned by the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      Collection<PSObject> results; // Holds the result of the pipeline execution.

      // Create the PowerShell object. Notice that no runspace is specified so a
      // new default runspace is used.
      PowerShell powershell = PowerShell.Create();

      // Use the using statement so that we can dispose of the PowerShell object
      // when we are done.
      using (powershell)
      {
        // Add the get-process cmdlet to the pipeline of the PowerShell object.
        powershell.AddCommand("get-process");

        // Add the sort-object cmdlet and its parameters to the pipeline of
        // the PowerShell object so that we can sort the HandleCount property
        //  in descending order.
        powershell.AddCommand("sort-object").AddParameter("descending").AddParameter("property", "handlecount");

        // Run the commands of the pipeline synchronously.
        results = powershell.Invoke();
      }

      // Even after disposing of the PowerShell object, we still
      // need to set the powershell variable to null so that the
      // garbage collector can clean it up.
      powershell = null;

      Console.WriteLine("Process              HandleCount");
      Console.WriteLine("--------------------------------");

      // Display the results returned by the commands.
      foreach (PSObject result in results)
      {
        Console.WriteLine(
                          "{0,-20} {1}",
                          result.Members["ProcessName"].Value,
                          result.Members["HandleCount"].Value);
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a>参照

[Windows PowerShell ホスト アプリケーションの作成](./writing-a-windows-powershell-host-application.md)
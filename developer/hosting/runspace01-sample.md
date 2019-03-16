---
title: Runspace01 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42c1c59c-6da5-4cda-9562-e8059177fee1
caps.latest.revision: 11
ms.openlocfilehash: eec9c616fc6d5240db185f764a3ea2c8f9575d03
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057911"
---
# <a name="runspace01-sample"></a>Runspace01 サンプル

このサンプルは、使用する方法を示します、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)を実行するクラス、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレット同期的にします。 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットが返す[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)ローカル コンピューターで実行されている各プロセスのオブジェクト。 値、 [System.Diagnostics.Process.Processname*](/dotnet/api/System.Diagnostics.Process.ProcessName)と[System.Diagnostics.Process.Handlecount*](/dotnet/api/System.Diagnostics.Process.Handlecount)プロパティが、返されたオブジェクトから抽出され、コンソールに表示されます。ウィンドウです。

## <a name="requirements"></a>要件

 このサンプルでは、Windows PowerShell 2.0 が必要です。

## <a name="demonstrates"></a>使用例

- 作成、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)コマンドを実行するオブジェクト。

- パイプラインにコマンドの追加、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。

- 同期的にコマンドを実行します。

- 使用して[System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject)コマンドによって返されるオブジェクトからプロパティを抽出するオブジェクト。

## <a name="example"></a>例

 このサンプルの実行、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットは同期的に Windows PowerShell によって提供される既定の実行空間。

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace01
  {
    /// <summary>
    /// This sample uses the PowerShell class to execute
    /// the get-process cmdlet synchronously. The name and
    /// handlecount are then extracted from the PSObjects
    /// returned and displayed.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run a command.
    /// 2. Adding a command to the pipeline of the PowerShell object.
    /// 3. Running the command synchronously.
    /// 4. Using PSObject objects to extract properties from the objects
    ///    returned by the command.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create().AddCommand("get-process"))
      {
        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the command synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke())
        {
          Console.WriteLine(
                      "{0,-20} {1}",
                      result.Members["ProcessName"].Value,
                      result.Members["HandleCount"].Value);
        }
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a>参照

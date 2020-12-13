---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace03 サンプル
description: Runspace03 サンプル
ms.openlocfilehash: fff699bf0545bb1419aa45b8c46bbd9c2cf0a99e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657857"
---
# <a name="runspace03-sample"></a><span data-ttu-id="e481a-103">Runspace03 サンプル</span><span class="sxs-lookup"><span data-stu-id="e481a-103">Runspace03 Sample</span></span>

<span data-ttu-id="e481a-104">このサンプルでは、 [System. Powershell](/dotnet/api/system.management.automation.powershell) クラスを使用してスクリプトを同期的に実行する方法と、終了しないエラーを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e481a-104">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run a script synchronously, and how to handle non-terminating errors.</span></span> <span data-ttu-id="e481a-105">このスクリプトはプロセス名の一覧を受信し、これらのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e481a-105">The script receives a list of process names and then retrieves those processes.</span></span> <span data-ttu-id="e481a-106">スクリプトの実行時に生成された終了しないエラーを含む、スクリプトの結果がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e481a-106">The results of the script, including any non-terminating errors that were generated when running the script, are displayed in a console window.</span></span>

## <a name="requirements"></a><span data-ttu-id="e481a-107">要件</span><span class="sxs-lookup"><span data-stu-id="e481a-107">Requirements</span></span>

<span data-ttu-id="e481a-108">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e481a-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e481a-109">対象</span><span class="sxs-lookup"><span data-stu-id="e481a-109">Demonstrates</span></span>

<span data-ttu-id="e481a-110">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="e481a-110">This sample demonstrates the following.</span></span>

- <span data-ttu-id="e481a-111">スクリプトを実行するための、 [システムの管理. Powershell](/dotnet/api/system.management.automation.powershell) オブジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="e481a-111">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run a script.</span></span>

- <span data-ttu-id="e481a-112">[システムの管理](/dotnet/api/system.management.automation.powershell)オブジェクトのパイプラインにスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="e481a-112">Adding a script to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="e481a-113">呼び出し元のプログラムからスクリプトに入力オブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="e481a-113">Passing input objects to the script from the calling program.</span></span>

- <span data-ttu-id="e481a-114">スクリプトを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="e481a-114">Running the script synchronously.</span></span>

- <span data-ttu-id="e481a-115">スクリプトによって返されるオブジェクトのプロパティを抽出して表示するには、[を使用します。](/dotnet/api/System.Management.Automation.PSObject)</span><span class="sxs-lookup"><span data-stu-id="e481a-115">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the script.</span></span>

- <span data-ttu-id="e481a-116">スクリプトの実行時に生成されたエラーレコードを取得して表示します。</span><span class="sxs-lookup"><span data-stu-id="e481a-116">Retrieving and displaying error records that were generated when the script was run.</span></span>

## <a name="example"></a><span data-ttu-id="e481a-117">例</span><span class="sxs-lookup"><span data-stu-id="e481a-117">Example</span></span>

<span data-ttu-id="e481a-118">このサンプルでは、Windows PowerShell によって提供される既定の実行空間でスクリプトを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="e481a-118">This sample runs a script synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="e481a-119">スクリプトの出力と生成された終了しないエラーは、コンソールウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e481a-119">The output of the script and any non-terminating errors that were generated are displayed in a console window.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace03
  {
    /// <summary>
    /// This sample shows how to use the PowerShell class to run a
    /// script that retrieves process information for the list of
    /// process names passed to the script. It shows how to pass input
    /// objects to a script and how to retrieve error objects as well
    /// as the output objects.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerSHell object to run a script.
    /// 2. Adding a script to the pipeline of the PowerShell object.
    /// 3. Passing input objects to the script from the calling program.
    /// 4. Running the script synchronously.
    /// 5. Using PSObject objects to extract and display properties from
    ///    the objects returned by the script.
    /// 6. Retrieving and displaying error records that were generated
    ///    when the script was run.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Define a list of processes to look for.
      string[] processNames = new string[]
      {
        "lsass", "nosuchprocess", "services", "nosuchprocess2"
      };

      // The script to run to get these processes. Input passed
      // to the script will be available in the $input variable.
      string script = "$input | get-process -name {$_}";

      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the script.
      using (PowerShell powershell = PowerShell.Create())
      {
        powershell.AddScript(script);

        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the script synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke(processNames))
        {
          Console.WriteLine(
                            "{0,-20} {1}",
                            result.Members["ProcessName"].Value,
                            result.Members["HandleCount"].Value);
        }

        // Process any error records that were generated while running
        //  the script.
        Console.WriteLine("\nThe following non-terminating errors occurred:\n");
        PSDataCollection<ErrorRecord> errors = powershell.Streams.Error;
        if (errors != null && errors.Count > 0)
        {
          foreach (ErrorRecord err in errors)
          {
            System.Console.WriteLine("    error: {0}", err.ToString());
          }
        }
      }

      System.Console.WriteLine("\nHit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="e481a-120">参照</span><span class="sxs-lookup"><span data-stu-id="e481a-120">See Also</span></span>

[<span data-ttu-id="e481a-121">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="e481a-121">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)

---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace04 サンプル
description: Runspace04 サンプル
ms.openlocfilehash: 5a2e1137963e02def419bb924c63b0d651b0fdfa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657748"
---
# <a name="runspace04-sample"></a><span data-ttu-id="5aad8-103">Runspace04 サンプル</span><span class="sxs-lookup"><span data-stu-id="5aad8-103">Runspace04 Sample</span></span>

<span data-ttu-id="5aad8-104">このサンプルでは、 [Powershell](/dotnet/api/system.management.automation.powershell) クラスを使用してコマンドを実行する方法と、コマンドの実行時にスローされる終了エラーをキャッチする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5aad8-104">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span> <span data-ttu-id="5aad8-105">2 つのコマンドが実行され、最後のコマンドには無効なパラメーターの引数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="5aad8-105">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span> <span data-ttu-id="5aad8-106">結果として、オブジェクトは返されず、終了するエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="5aad8-106">As a result, no objects are returned and a terminating error is thrown.</span></span>

## <a name="requirements"></a><span data-ttu-id="5aad8-107">要件</span><span class="sxs-lookup"><span data-stu-id="5aad8-107">Requirements</span></span>

<span data-ttu-id="5aad8-108">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="5aad8-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="5aad8-109">対象</span><span class="sxs-lookup"><span data-stu-id="5aad8-109">Demonstrates</span></span>

<span data-ttu-id="5aad8-110">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="5aad8-110">This sample demonstrates the following.</span></span>

- <span data-ttu-id="5aad8-111">システムの [管理](/dotnet/api/system.management.automation.powershell) .... Powershell オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5aad8-111">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="5aad8-112">System.servicemodel オブジェクトのパイプラインにコマンドを追加 [してい](/dotnet/api/system.management.automation.powershell) ます。</span><span class="sxs-lookup"><span data-stu-id="5aad8-112">Adding commands to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="5aad8-113">パイプラインにパラメーター引数を追加しています。</span><span class="sxs-lookup"><span data-stu-id="5aad8-113">Adding parameter arguments to the pipeline.</span></span>

- <span data-ttu-id="5aad8-114">コマンドを同期的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5aad8-114">Invoking the commands synchronously.</span></span>

- <span data-ttu-id="5aad8-115">コマンドによって返されるオブジェクトのプロパティを抽出して表示するには、[を使用します。](/dotnet/api/System.Management.Automation.PSObject)</span><span class="sxs-lookup"><span data-stu-id="5aad8-115">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the commands.</span></span>

- <span data-ttu-id="5aad8-116">コマンドの実行中に生成されたエラーレコードを取得して表示します。</span><span class="sxs-lookup"><span data-stu-id="5aad8-116">Retrieving and displaying error records that were generated during the running of the commands.</span></span>

- <span data-ttu-id="5aad8-117">コマンドによってスローされた終了例外をキャッチして表示します。</span><span class="sxs-lookup"><span data-stu-id="5aad8-117">Catching and displaying terminating exceptions thrown by the commands.</span></span>

## <a name="example"></a><span data-ttu-id="5aad8-118">例</span><span class="sxs-lookup"><span data-stu-id="5aad8-118">Example</span></span>

<span data-ttu-id="5aad8-119">このサンプルでは、Windows PowerShell によって提供される既定の実行空間でコマンドを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="5aad8-119">This sample runs commands synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="5aad8-120">最後のコマンドは、無効なパラメーター引数がコマンドに渡されるため、終了エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="5aad8-120">The last command throws a terminating error because a parameter argument that is not valid is passed to the command.</span></span> <span data-ttu-id="5aad8-121">終了エラーがトラップされて表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aad8-121">The terminating error is trapped and displayed.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace04
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands.
    /// The commands generate a terminating exception that the caller
    /// should catch and process.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run commands.
    /// 2. Adding commands to the pipeline of  the PowerShell object.
    /// 3. Passing input objects to the commands from the calling program.
    /// 4. Using PSObject objects to extract and display properties from the
    ///    objects returned by the commands.
    /// 5. Retrieving and displaying error records that were generated
    ///    while running the commands.
    /// 6. Catching and displaying terminating exceptions generated
    ///    while running the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object.
      using (PowerShell powershell = PowerShell.Create())
      {
        // Add the commands to the PowerShell object.
        powershell.AddCommand("Get-ChildItem").AddCommand("Select-String").AddArgument("*");

        // Run the commands synchronously. Because of the bad regular expression,
        // no objects will be returned. Instead, an exception will be thrown.
        try
        {
          foreach (PSObject result in powershell.Invoke())
          {
            Console.WriteLine("'{0}'", result.ToString());
          }

          // Process any error records that were generated while running the commands.
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
        catch (RuntimeException runtimeException)
        {
          // Trap any exception generated by the commands. These exceptions
          // will all be derived from the RuntimeException exception.
          System.Console.WriteLine(
                        "Runtime exception: {0}: {1}\n{2}",
                        runtimeException.ErrorRecord.InvocationInfo.InvocationName,
                        runtimeException.Message,
                        runtimeException.ErrorRecord.InvocationInfo.PositionMessage);
        }
      }

      System.Console.WriteLine("\nHit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="5aad8-122">参照</span><span class="sxs-lookup"><span data-stu-id="5aad8-122">See Also</span></span>

[<span data-ttu-id="5aad8-123">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="5aad8-123">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)

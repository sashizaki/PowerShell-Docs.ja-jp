---
ms.date: 09/13/2016
ms.topic: reference
title: 制約付き実行空間を作成する
description: 制約付き実行空間を作成する
ms.openlocfilehash: 53fee3cc7d8625425bc6a73196aee9eee7f17ed6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651172"
---
# <a name="creating-a-constrained-runspace"></a><span data-ttu-id="981f6-103">制約付き実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="981f6-103">Creating a constrained runspace</span></span>

<span data-ttu-id="981f6-104">パフォーマンスまたはセキュリティ上の理由により、ホストアプリケーションで使用できる Windows PowerShell コマンドを制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="981f6-104">For performance or security reasons, you might want to restrict the Windows PowerShell commands available to your host application.</span></span> <span data-ttu-id="981f6-105">これを行うには、System.Management.Automation.Runspaces.Initialsessionstate を呼び出して、空の [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) を作成し [ ます。\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) メソッドを作成し、使用可能なコマンドのみを追加します。</span><span class="sxs-lookup"><span data-stu-id="981f6-105">To do this you create an empty [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) by calling the [System.Management.Automation.Runspaces.Initialsessionstate.Create\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method, and then add only the commands you want available.</span></span>

 <span data-ttu-id="981f6-106">指定したコマンドのみを読み込む実行空間を使用すると、パフォーマンスが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="981f6-106">Using a runspace that loads only the commands that you specify provides significantly improved performance.</span></span>

 <span data-ttu-id="981f6-107">最初のセッション状態のコマンドレットを定義するには、system.servicemodel. [Sessionstatecmd・ entry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) クラスのメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="981f6-107">You use the methods of the [System.Management.Automation.Runspaces.Sessionstatecmdletentry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) class to define cmdlets for the initial session state.</span></span>

 <span data-ttu-id="981f6-108">コマンドをプライベートにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="981f6-108">You can also make commands private.</span></span> <span data-ttu-id="981f6-109">プライベートコマンドはホストアプリケーションで使用できますが、アプリケーションのユーザーは使用できません。</span><span class="sxs-lookup"><span data-stu-id="981f6-109">Private commands can be used by the host application, but not by users of the application.</span></span>

## <a name="adding-commands-to-an-empty-runspace"></a><span data-ttu-id="981f6-110">空の実行空間にコマンドを追加する</span><span class="sxs-lookup"><span data-stu-id="981f6-110">Adding commands to an empty runspace</span></span>

 <span data-ttu-id="981f6-111">次の例は、空の InitialSessionState を作成してコマンドを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="981f6-111">The following example demonstrates how to create an empty InitialSessionState and add commands to it.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using Microsoft.PowerShell.Commands;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for the application.
  /// </summary>
  internal class Runspace10b
  {
    /// <summary>
    /// This sample shows how to create an empty initial session state,
    /// how to add commands to the session state, and then how to create a
    /// runspace that has only those two commands. A PowerShell object
    /// is used to run the Get-Command cmdlet to show that only two commands
    /// are available.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    private static void Main(string[] args)
    {
      // Create an empty InitialSessionState and then add two commands.
      InitialSessionState iss = InitialSessionState.Create();

      // Add the Get-Process and Get-Command cmdlets to the session state.
      SessionStateCmdletEntry ssce1 = new SessionStateCmdletEntry(
                                                            "get-process",
                                                            typeof(GetProcessCommand),
                                                            null);
      iss.Commands.Add(ssce1);

      SessionStateCmdletEntry ssce2 = new SessionStateCmdletEntry(
                                                            "get-command",
                                                            typeof(GetCommandCommand),
                                                            null);
      iss.Commands.Add(ssce2);

      // Create a runspace.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();
        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = myRunSpace;

          // Create a pipeline with the Get-Command command.
          powershell.AddCommand("get-command");

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Verb                 Noun");
          Console.WriteLine("----------------------------");

          // Display each result object.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                             "{0,-20} {1}",
                             result.Members["verb"].Value,
                             result.Members["Noun"].Value);
          }
        }

        // Close the runspace and release any resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="making-commands-private"></a><span data-ttu-id="981f6-112">コマンドをプライベートにする</span><span class="sxs-lookup"><span data-stu-id="981f6-112">Making commands private</span></span>

 <span data-ttu-id="981f6-113">また、コマンド **をプライベートに** 設定することも [できます。](/dotnet/api/System.Management.Automation.CommandInfo.Visibility)これを行うには、SessionStateEntryVisibility プロパティを [system](/dotnet/api/System.Management.Automation.SessionStateEntryVisibility)に設定します。</span><span class="sxs-lookup"><span data-stu-id="981f6-113">You can also make a command private, by setting it's [System.Management.Automation.Commandinfo.Visibility](/dotnet/api/System.Management.Automation.CommandInfo.Visibility) property to [System.Management.Automation.SessionStateEntryVisibility](/dotnet/api/System.Management.Automation.SessionStateEntryVisibility) **Private**.</span></span> <span data-ttu-id="981f6-114">ホストアプリケーションやその他のコマンドは、そのコマンドを呼び出すことができますが、アプリケーションのユーザーは呼び出せません。</span><span class="sxs-lookup"><span data-stu-id="981f6-114">The host application and other commands can call that command, but the user of the application cannot.</span></span> <span data-ttu-id="981f6-115">次の例では、 [get-childitem](/powershell/module/Microsoft.PowerShell.Management/Get-ChildItem) コマンドはプライベートです。</span><span class="sxs-lookup"><span data-stu-id="981f6-115">In the following example, the [Get-ChildItem](/powershell/module/Microsoft.PowerShell.Management/Get-ChildItem) command is private.</span></span>

```csharp
defaultSessionState = InitialSessionState.CreateDefault();
commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
defaultSessionState.Commands[commandIndex].Visibility = SessionStateEntryVisibility.Private;

this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
this.runspace.Open();
```

## <a name="see-also"></a><span data-ttu-id="981f6-116">参照</span><span class="sxs-lookup"><span data-stu-id="981f6-116">See Also</span></span>

 [<span data-ttu-id="981f6-117">InitialSessionState を作成する</span><span class="sxs-lookup"><span data-stu-id="981f6-117">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

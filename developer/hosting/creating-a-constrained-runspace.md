---
title: 制約付き実行空間を作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59125e65-7030-40bb-9926-756120b2d952
caps.latest.revision: 5
ms.openlocfilehash: 29f1be6a1215219ddd16367a31f528a4f0dbc2e3
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795132"
---
# <a name="creating-a-constrained-runspace"></a>制約付き実行空間を作成する

パフォーマンスまたはセキュリティ上の理由では、ホスト アプリケーションに使用できる Windows PowerShell コマンドを制限する可能性があります。 これを行うには、空を作成[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)呼び出すことによって、 [System.Management.Automation.Runspaces.Initialsessionstate.Create*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create)メソッド利用コマンドのみを追加します。

 指定したコマンドのみを読み込みの実行空間を使用して大幅に向上したパフォーマンスを提供します。

 メソッドを使用する、 [System.Management.Automation.Runspaces.Sessionstatecmdletentry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry)最初のセッション状態用のコマンドレットを定義するクラス。

 行うことができますもコマンド プライベートです。 ホスト アプリケーションによっては、アプリケーションのユーザーではなく、プライベートのコマンドを使用できます。

## <a name="adding-commands-to-an-empty-runspace"></a>空の実行空間にコマンドを追加します。

 次の例では、空の InitialSessionState を作成し、コマンドを追加する方法を示します。

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

## <a name="making-commands-private"></a>コマンドをプライベートにします。

 行うことができますもコマンドをプライベートに設定することでの[System.Management.Automation.Commandinfo.Visibility*](/dotnet/api/System.Management.Automation.CommandInfo.Visibility)プロパティを[System.Management.Automation.Sessionstateentryvisibility.Private](/dotnet/api/System.Management.Automation.SessionStateEntryVisibility.Private). ホスト アプリケーションとその他のコマンドは、そのコマンドを呼び出すことができますが、アプリケーションのユーザーのことはできません。 次の例では、 [Get-childitem](/powershell/module/Microsoft.PowerShell.Management/Get-ChildItem)コマンドはプライベートです。

```csharp
defaultSessionState = InitialSessionState.CreateDefault();
commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
defaultSessionState.Commands[commandIndex].Visibility = SessionStateEntryVisibility.Private;

this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
this.runspace.Open();
```

## <a name="see-also"></a>参照

 [InitialSessionState を作成します。](./creating-an-initialsessionstate.md)

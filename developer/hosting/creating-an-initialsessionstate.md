---
title: 作成、InitialSessionState |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ae707db-52e0-408c-87fa-b35c42eaaab1
caps.latest.revision: 5
ms.openlocfilehash: c23640b69d1e71a343e2bef2c6b3f8ffe19826d7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855688"
---
# <a name="creating-an-initialsessionstate"></a>InitialSessionState を作成する

Windows PowerShell のコマンドは、実行空間で実行されます。 Windows PowerShell をホストするには、アプリケーションで、作成する必要があります、 [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace)オブジェクト。 すべての実行空間が、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)関連付けられているオブジェクト。 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)などのコマンド、変数、およびモジュールがその実行空間の使用可能な実行空間の特性を指定します。

## <a name="create-a-default-initialsessionstate"></a>InitialSessionState デフォルトを作成します。

 [System.Management.Automation.Runspaces.Initialsessionstate.Createdefault*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault)と[System.Management.Automation.Runspaces.Initialsessionstate.Createdefault2*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2)メソッドを使用することができます作成する[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクト。 [System.Management.Automation.Runspaces.Initialsessionstate.Createdefault*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault)中に、読み込まれたすべての組み込みコマンドで、InitialSessionState を作成[System.Management.Automation.Runspaces.Initialsessionstate.Createdefault2*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) Windows PowerShell を (Microsoft.PowerShell.Core モジュールからコマンド ホストするために必要なコマンドのみを読み込みます。

 さらに、ホスト アプリケーションで使用できるコマンドを制限する場合は、制約付き実行空間を作成する必要があります。 については、制約付き実行空間を作成するを参照してください。

 次のコードは、InitialSessionState を作成、実行空間に割り当てる、コマンド、その実行空間でパイプラインを追加、および、コマンドを呼び出す方法を示します。 追加して、コマンドを起動する方法の詳細については、コマンドを呼び出すと追加を参照してください。

```csharp

namespace SampleHost
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  class HostP4b
  {
    static void Main(string[] args)
    {
      // Call the InitailSessionState.CreateDefault method to create
      // an empty InitialSessionState object, and then add the
      // elements that will be available when the runspace is opened.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      SessionStateVariableEntry var1 = new
          SessionStateVariableEntry("test1",
                                    "MyVar1",
                                    "Initial session state MyVar1 test");
      iss.Variables.Add(var1);

      SessionStateVariableEntry var2 = new
          SessionStateVariableEntry("test2",
                                    "MyVar2",
                                    "Initial session state MyVar2 test");
      iss.Variables.Add(var2);

      // Call the RunspaceFactory.CreateRunspace(InitialSessionState)
      // method to create the runspace where the pipeline is run.
      Runspace rs = RunspaceFactory.CreateRunspace(iss);
      rs.Open();

      // Call the PowerShell.Create() method to create the PowerShell
      // object,and then specify the runspace and commands to the pipeline.
      // and  create the command pipeline.
      PowerShell ps = PowerShell.Create();
      ps.Runspace = rs;
      ps.AddCommand("Get-Variable");
      ps.AddArgument("test*");

      Console.WriteLine("Variable             Value");
      Console.WriteLine("--------------------------");

      // Call the PowerShell.Invoke() method to run
      // the pipeline synchronously.
        foreach (PSObject result in ps.Invoke())
        {
          Console.WriteLine("{0,-20}{1}",
                  result.Members["Name"].Value,
                  result.Members["Value"].Value);
        } // End foreach.

        // Close the runspace to free resources.
        rs.Close();

    } // End Main.
  } // End SampleHost.
}
```

## <a name="see-also"></a>参照

 [制約付き実行空間を作成します。](./creating-a-constrained-runspace.md)

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
ms.openlocfilehash: 9140d03e046def2fbbcc2a842b9ea1b9e1fa2985
ms.sourcegitcommit: 13f24786ed39ca1c07eff2b73a1974c366e31cb8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2019
ms.locfileid: "67263838"
---
# <a name="creating-an-initialsessionstate"></a>InitialSessionState を作成する

PowerShell のコマンドは、実行空間で実行されます。
PowerShell をホストするには、アプリケーションで、作成する必要があります、 [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace)オブジェクト。
すべての実行空間が、 [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)関連付けられているオブジェクト。
InitialSessionState などのコマンド、変数、およびモジュールがその実行空間の使用可能な実行空間の特性を指定します。

## <a name="create-a-default-initialsessionstate"></a>InitialSessionState デフォルトを作成します。

[CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault)と[CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2)のメソッド、 **InitialSessionState**クラスは、作成に使用できる、 **InitialSessionState**オブジェクト。
**CreateDefault**メソッドを作成、 **InitialSessionState**ですべての組み込みコマンドの中に、アンロード、 **CreateDefault2**メソッドは、コマンドのみを読み込みます。PowerShell (Microsoft.PowerShell.Core モジュールからコマンド) をホストに必要です。

さらに、ホスト アプリケーションで使用できるコマンドを制限する場合は、制約付き実行空間を作成する必要があります。
詳しくは、次を参照してください。[制約付き実行空間を作成する](creating-a-constrained-runspace.md)します。

次のコードを作成する方法を示しています、 **InitialSessionState**、実行空間に割り当てる、コマンド、その実行空間でパイプラインを追加およびコマンドを呼び出します。
追加して、コマンドを起動する方法の詳細についてを参照してください。[と追加のコマンドを呼び出す](adding-and-invoking-commands.md)します。

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
      // Call the InitialSessionState.CreateDefault method to create
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

      // Call the PowerShell.Create() method to create the PowerShell object,
      // and then specify the runspace and commands to the pipeline.
      // and create the command pipeline.
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

[制約付き実行空間を作成します。](creating-a-constrained-runspace.md)

[追加して、コマンドを起動](adding-and-invoking-commands.md)

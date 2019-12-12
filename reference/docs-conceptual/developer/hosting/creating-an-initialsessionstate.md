---
title: InitialSessionState | を作成するMicrosoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ae707db-52e0-408c-87fa-b35c42eaaab1
caps.latest.revision: 5
ms.openlocfilehash: 9140d03e046def2fbbcc2a842b9ea1b9e1fa2985
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367621"
---
# <a name="creating-an-initialsessionstate"></a><span data-ttu-id="7011f-102">InitialSessionState を作成する</span><span class="sxs-lookup"><span data-stu-id="7011f-102">Creating an InitialSessionState</span></span>

<span data-ttu-id="7011f-103">PowerShell コマンドは実行空間で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7011f-103">PowerShell commands run in a runspace.</span></span>
<span data-ttu-id="7011f-104">アプリケーションで PowerShell をホストする[には、system.servicemodel オブジェクトを](/dotnet/api/System.Management.Automation.Runspaces.Runspace)作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7011f-104">To host PowerShell in your application, you must create a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>
<span data-ttu-id="7011f-105">すべての実行空間には、 [InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="7011f-105">Every runspace has an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object associated with it.</span></span>
<span data-ttu-id="7011f-106">InitialSessionState は、その実行空間で使用できるコマンド、変数、モジュールなどの実行空間の特性を指定します。</span><span class="sxs-lookup"><span data-stu-id="7011f-106">The InitialSessionState specifies characteristics of the runspace, such as which commands, variables, and modules are available for that runspace.</span></span>

## <a name="create-a-default-initialsessionstate"></a><span data-ttu-id="7011f-107">既定の InitialSessionState を作成する</span><span class="sxs-lookup"><span data-stu-id="7011f-107">Create a default InitialSessionState</span></span>

<span data-ttu-id="7011f-108">**InitialSessionState**クラスの[Createdefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault)メソッドと[CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2)メソッドを使用して、 **InitialSessionState**オブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7011f-108">The [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) and [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) methods of the **InitialSessionState** class can be used to create an **InitialSessionState** object.</span></span>
<span data-ttu-id="7011f-109">**Createdefault**メソッドは、すべての組み込みコマンドが読み込まれた**InitialSessionState**を作成します。一方、CreateDefault2 メソッドは、powershell をホストするために必要なコマンド (モジュールのコマンド) のみを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="7011f-109">The **CreateDefault** method creates an **InitialSessionState** with all of the built-in commands loaded, while the **CreateDefault2** method loads only the commands required to host PowerShell (the commands from the Microsoft.PowerShell.Core module).</span></span>

<span data-ttu-id="7011f-110">ホストアプリケーションで使用できるコマンドをさらに制限する場合は、制約付き実行空間を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7011f-110">If you want to further limit the commands available in your host application you need to create a constrained runspace.</span></span>
<span data-ttu-id="7011f-111">詳細については、「[制約付き実行空間の作成](creating-a-constrained-runspace.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7011f-111">For information, see [Creating a constrained runspace](creating-a-constrained-runspace.md).</span></span>

<span data-ttu-id="7011f-112">次のコードは、 **InitialSessionState**を作成して、実行空間に割り当て、その実行空間のパイプラインにコマンドを追加し、コマンドを呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7011f-112">The following code shows how to create an **InitialSessionState**, assign it to a runspace, add commands to the pipeline in that runspace, and invoke the commands.</span></span>
<span data-ttu-id="7011f-113">コマンドの追加と呼び出しの詳細については、「[コマンドの追加と呼び出し](adding-and-invoking-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7011f-113">For more information about adding and invoking commands, see [Adding and invoking commands](adding-and-invoking-commands.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7011f-114">参照</span><span class="sxs-lookup"><span data-stu-id="7011f-114">See Also</span></span>

[<span data-ttu-id="7011f-115">制約付き実行空間の作成</span><span class="sxs-lookup"><span data-stu-id="7011f-115">Creating a constrained runspace</span></span>](creating-a-constrained-runspace.md)

[<span data-ttu-id="7011f-116">コマンドの追加と呼び出し</span><span class="sxs-lookup"><span data-stu-id="7011f-116">Adding and invoking commands</span></span>](adding-and-invoking-commands.md)

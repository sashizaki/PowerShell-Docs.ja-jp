---
title: Windows PowerShell ホストのクイック スタート |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a134b81-bd0c-4e1c-a2f0-9acbe852745a
caps.latest.revision: 9
ms.openlocfilehash: cc014487a680747ad59437052f79d4576154a1cb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082551"
---
# <a name="windows-powershell-host-quickstart"></a><span data-ttu-id="bbb6c-102">Windows PowerShell ホスト クイック スタート</span><span class="sxs-lookup"><span data-stu-id="bbb6c-102">Windows PowerShell Host Quickstart</span></span>

<span data-ttu-id="bbb6c-103">Windows PowerShell をホストするには、アプリケーションで、使用する、 [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)クラス。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-103">To host Windows PowerShell in your application, you use the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class.</span></span> <span data-ttu-id="bbb6c-104">このクラスは、コマンドのパイプラインを作成し、実行空間でこれらのコマンドを実行するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-104">This class provides methods that create a pipeline of commands and then execute those commands in a runspace.</span></span> <span data-ttu-id="bbb6c-105">ホスト アプリケーションを作成する最も簡単な方法では、既定の実行空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-105">The simplest way to create a host application is to use the default runspace.</span></span> <span data-ttu-id="bbb6c-106">既定の実行空間には、すべてのコア Windows PowerShell コマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-106">The default runspace contains all of the core Windows PowerShell commands.</span></span> <span data-ttu-id="bbb6c-107">アプリケーション、Windows PowerShell コマンドのサブセットのみを公開する場合は、カスタム実行空間を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-107">If you want your application to expose only a subset of the Windows PowerShell commands, you must create a custom runspace.</span></span>

## <a name="using-the-default-runspace"></a><span data-ttu-id="bbb6c-108">既定の実行空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-108">Using the default runspace</span></span>

<span data-ttu-id="bbb6c-109">を開始するには、既定の実行空間を使用して、のメソッドを使用しましたします、 [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)コマンド、パラメーター、ステートメント、およびスクリプトをパイプラインに追加するクラス。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-109">To start, we'll use the default runspace, and use the methods of the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class to add commands, parameters, statements, and scripts to a pipeline.</span></span>

### <a name="addcommand"></a><span data-ttu-id="bbb6c-110">AddCommand</span><span class="sxs-lookup"><span data-stu-id="bbb6c-110">AddCommand</span></span>

<span data-ttu-id="bbb6c-111">使用する、 [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)のメソッド、 [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)パイプラインにコマンドを追加するクラス。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-111">You use the [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method of the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class to add commands to the pipeline.</span></span> <span data-ttu-id="bbb6c-112">たとえば、コンピューターで実行中のプロセスの一覧を取得したいとします。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-112">For example, suppose you want to get the list of running processes on the machine.</span></span> <span data-ttu-id="bbb6c-113">このコマンドを実行する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-113">The way to run this command is as follows.</span></span>

1. <span data-ttu-id="bbb6c-114">作成、 [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-114">Create a [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="bbb6c-115">実行するコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-115">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="bbb6c-116">コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-116">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

<span data-ttu-id="bbb6c-117">呼び出す場合、 [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)メソッドを呼び出す前に 2 回以上、 [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドは、の結果、最初のコマンドは、2 番目にパイプします。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-117">If you call the [System.Management.Automation.Powershell.AddCommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="bbb6c-118">前のコマンドをコマンドの結果をパイプ処理したくない場合は呼び出すことによって追加、 [System.Management.Automation.Powershell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-118">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="bbb6c-119">AddParameter</span><span class="sxs-lookup"><span data-stu-id="bbb6c-119">AddParameter</span></span>

<span data-ttu-id="bbb6c-120">前の例では、パラメーターなしの 1 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-120">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="bbb6c-121">使用して、コマンドにパラメーターを追加することができます、 [System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)メソッドを次のコードがという名前のプロセスのすべての一覧を取得など`PowerShell`で実行されている、マシン。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-121">You can add parameters to the command by using the [System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

<span data-ttu-id="bbb6c-122">追加のパラメーターを追加するには呼び出すことによって[System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)繰り返し。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-122">You can add additional parameters by calling [System.Management.Automation.PSCommand.AddParameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

<span data-ttu-id="bbb6c-123">呼び出すことによって、パラメーターの名前と値のディクショナリを追加することも、 [System.Management.Automation.PowerShell.AddParameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters)メソッド。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-123">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.PowerShell.AddParameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="bbb6c-124">AddStatement</span><span class="sxs-lookup"><span data-stu-id="bbb6c-124">AddStatement</span></span>

<span data-ttu-id="bbb6c-125">使用してバッチ処理をシミュレートすることができます、 [System.Management.Automation.PowerShell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)メソッドで、次のコードは、名前の実行中のプロセスの一覧を取得します。 パイプラインの末尾に追加のステートメントを追加します。`PowerShell`、し、実行中のサービスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-125">You can simulate batching by using the [System.Management.Automation.PowerShell.AddStatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="bbb6c-126">AddScript</span><span class="sxs-lookup"><span data-stu-id="bbb6c-126">AddScript</span></span>

<span data-ttu-id="bbb6c-127">既存のスクリプトを実行するには呼び出すことによって、 [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)メソッド。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-127">You can run an existing script by calling the [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="bbb6c-128">次の例では、パイプラインにスクリプトを追加し、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-128">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="bbb6c-129">この例では、という名前のスクリプトが既に存在`MyScript.ps1`という名前のフォルダーで`D:\PSScripts`します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-129">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

<span data-ttu-id="bbb6c-130">バージョンがあります、 [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)というブール型パラメーターを受け取るメソッド`useLocalScope`します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-130">There is also a version of the [System.Management.Automation.PowerShell.AddScript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="bbb6c-131">このパラメーターに設定されている場合`true`、し、スクリプトはローカル スコープで実行します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-131">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="bbb6c-132">次のコードは、スクリプトをローカル スコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-132">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a><span data-ttu-id="bbb6c-133">カスタムの実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-133">Creating a custom runspace</span></span>

<span data-ttu-id="bbb6c-134">前の例で使用される既定の実行空間が読み込まれるすべてのコア Windows PowerShell コマンドを指定したすべてのコマンドのサブセットのみを読み込むカスタム実行空間を作成できます。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-134">While the default runspace used in the previous examples loads all of the core Windows PowerShell commands, you can create a custom runspace that loads only a specified subset of all commands.</span></span> <span data-ttu-id="bbb6c-135">パフォーマンスを向上させるためにこれを実行する場合があります (読み込みより多くのコマンドは、パフォーマンスに影響が)、またはユーザーの操作を実行する機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-135">You might want to do this to improve performance (loading a larger number of commands is a performance hit), or to restrict the capability of the user to perform operations.</span></span> <span data-ttu-id="bbb6c-136">コマンドの限られた数のみを公開する実行空間には、制約付き実行空間が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-136">A runspace that exposes only a limited number of commands is called a constrained runspace.</span></span> <span data-ttu-id="bbb6c-137">使用して制約付き実行空間を作成する、 [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace)と[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)クラス。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-137">To create a constrained runspace, you use the [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) and [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) classes.</span></span>

### <a name="creating-an-initialsessionstate-object"></a><span data-ttu-id="bbb6c-138">InitialSessionState オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-138">Creating an InitialSessionState object</span></span>

<span data-ttu-id="bbb6c-139">カスタムの実行空間を作成する必要があります最初に作成する、 [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-139">To create a custom runspace, you must first create an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span> <span data-ttu-id="bbb6c-140">次の例では使用して、 [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) 、既定値を作成した後、実行空間を作成する[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-140">In the following example, we use the [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) to create a runspace after creating a default [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a><span data-ttu-id="bbb6c-141">実行空間を制限します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-141">Constraining the runspace</span></span>

<span data-ttu-id="bbb6c-142">前の例で、既定値を作成しました[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)組み込みコア Windows PowerShell のすべてをロードするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-142">In the previous example, we created a default [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object that loads all of the built-in core Windows PowerShell.</span></span> <span data-ttu-id="bbb6c-143">私たちも呼び出すことができます、 [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) Microsoft.PowerShell.Core コマンドのみを読み込むよう InitialSessionState オブジェクトを作成する方法スナップイン。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-143">We could also have called the [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) method to create an InitialSessionState object that would load only the commands in the Microsoft.PowerShell.Core snapin.</span></span> <span data-ttu-id="bbb6c-144">複数の制約付き実行空間を作成するには、空を作成する必要があります[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを呼び出すことによって、 [System.Management.Automation.Runspaces.InitialSessionState.Create\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create)メソッド、InitialSessionState にコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-144">To create a more constrained runspace, you must create an empty [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object by calling the [System.Management.Automation.Runspaces.InitialSessionState.Create\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method, and then add commands to the InitialSessionState.</span></span>

<span data-ttu-id="bbb6c-145">指定したコマンドのみを読み込みの実行空間を使用して大幅に向上したパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-145">Using a runspace that loads only the commands that you specify provides significantly improved performance.</span></span>

<span data-ttu-id="bbb6c-146">メソッドを使用する、 [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry)最初のセッション状態用のコマンドレットを定義するクラス。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-146">You use the methods of the [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) class to define cmdlets for the initial session state.</span></span> <span data-ttu-id="bbb6c-147">次の例では、最初の空のセッション状態を作成しますを定義し、追加、、`Get-Command`と`Import-Module`最初のセッション状態をコマンド。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-147">The following example creates an empty initial session state, then defines and adds the `Get-Command` and `Import-Module` commands to the initial session state.</span></span> <span data-ttu-id="bbb6c-148">その最初のセッション状態で制約付き実行空間を作成し、その実行空間でのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-148">We then create a runspace constrained by that initial session state, and execute the commands in that runspace.</span></span>

<span data-ttu-id="bbb6c-149">最初のセッション状態を作成します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-149">Create the initial session state.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

<span data-ttu-id="bbb6c-150">定義し、最初のセッション状態にコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-150">Define and add commands to the initial session state.</span></span>

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

<span data-ttu-id="bbb6c-151">作成し、実行空間を開きます。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-151">Create and open the runspace.</span></span>

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

<span data-ttu-id="bbb6c-152">コマンドを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-152">Execute a command and show the result.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
Collection<CommandInfo> result = ps.Invoke<CommandInfo>();
foreach (var entry in result)
{
       Console.WriteLine(entry.Name);
}
```

<span data-ttu-id="bbb6c-153">実行すると、このコードの出力はようになります。</span><span class="sxs-lookup"><span data-stu-id="bbb6c-153">When run, the output of this code will look as follows.</span></span>

```powershell
Get-Command
Import-Module
```

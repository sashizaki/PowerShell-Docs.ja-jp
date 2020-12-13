---
ms.date: 09/12/2016
ms.topic: reference
title: Windows PowerShell ホスト クイック スタート
description: Windows PowerShell ホスト クイック スタート
ms.openlocfilehash: 4cb7dae60342abb40bd7a989a27a692826b360e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657418"
---
# <a name="windows-powershell-host-quickstart"></a><span data-ttu-id="dc385-103">Windows PowerShell ホスト クイック スタート</span><span class="sxs-lookup"><span data-stu-id="dc385-103">Windows PowerShell Host Quickstart</span></span>

<span data-ttu-id="dc385-104">アプリケーションで Windows PowerShell をホストするには、 [System. powershell](/dotnet/api/System.Management.Automation.PowerShell) クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc385-104">To host Windows PowerShell in your application, you use the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class.</span></span>
<span data-ttu-id="dc385-105">このクラスには、コマンドのパイプラインを作成し、そのコマンドを実行空間で実行するメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dc385-105">This class provides methods that create a pipeline of commands and then execute those commands in a runspace.</span></span>
<span data-ttu-id="dc385-106">ホストアプリケーションを作成する最も簡単な方法は、既定の実行空間を使用することです。</span><span class="sxs-lookup"><span data-stu-id="dc385-106">The simplest way to create a host application is to use the default runspace.</span></span>
<span data-ttu-id="dc385-107">既定の実行空間には、Windows PowerShell のコアコマンドがすべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc385-107">The default runspace contains all of the core Windows PowerShell commands.</span></span>
<span data-ttu-id="dc385-108">アプリケーションで Windows PowerShell コマンドのサブセットのみを公開する場合は、カスタム実行空間を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc385-108">If you want your application to expose only a subset of the Windows PowerShell commands, you must create a custom runspace.</span></span>

## <a name="using-the-default-runspace"></a><span data-ttu-id="dc385-109">既定の実行空間の使用</span><span class="sxs-lookup"><span data-stu-id="dc385-109">Using the default runspace</span></span>

<span data-ttu-id="dc385-110">最初に、既定の実行空間を使用します。また、コマンド、パラメーター、ステートメント、およびスクリプトをパイプラインに追加する [には、このクラスの](/dotnet/api/System.Management.Automation.PowerShell) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc385-110">To start, we'll use the default runspace, and use the methods of the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class to add commands, parameters, statements, and scripts to a pipeline.</span></span>

### <a name="addcommand"></a><span data-ttu-id="dc385-111">AddCommand</span><span class="sxs-lookup"><span data-stu-id="dc385-111">AddCommand</span></span>

<span data-ttu-id="dc385-112">パイプラインにコマンドを追加するには、. [Powershell. AddCommand](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc385-112">You use the [System.Management.Automation.Powershell.AddCommand](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method to add commands to the pipeline.</span></span>
<span data-ttu-id="dc385-113">たとえば、コンピューター上で実行中のプロセスの一覧を取得するとします。</span><span class="sxs-lookup"><span data-stu-id="dc385-113">For example, suppose you want to get the list of running processes on the machine.</span></span>
<span data-ttu-id="dc385-114">このコマンドを実行する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc385-114">The way to run this command is as follows.</span></span>

1. <span data-ttu-id="dc385-115">システムの [管理. PowerShell](/dotnet/api/System.Management.Automation.PowerShell) オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc385-115">Create a [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="dc385-116">実行するコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="dc385-116">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="dc385-117">コマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dc385-117">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

<span data-ttu-id="dc385-118">AddCommand メソッドを複数回呼び出す前に、 [このメソッドを](/dotnet/api/System.Management.Automation.PowerShell.Invoke) 呼び出すと、最初のコマンドの結果が2番目のコマンドにパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="dc385-118">If you call the AddCommand method more than once before you call the [System.Management.Automation.Powershell.Invoke](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span>
<span data-ttu-id="dc385-119">パイプを使用して前のコマンドの結果をコマンドに渡したくない場合は [、代わりに system.object を呼び出し](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) て追加します。</span><span class="sxs-lookup"><span data-stu-id="dc385-119">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="dc385-120">AddParameter</span><span class="sxs-lookup"><span data-stu-id="dc385-120">AddParameter</span></span>

<span data-ttu-id="dc385-121">前の例では、パラメーターを指定せずに1つのコマンドを実行しています。</span><span class="sxs-lookup"><span data-stu-id="dc385-121">The previous example executes a single command without any parameters.</span></span>
<span data-ttu-id="dc385-122">コマンドにパラメーターを追加するには、を使用します。そのためには、 [AddParameter](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc385-122">You can add parameters to the command by using the [System.Management.Automation.PSCommand.AddParameter](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method.</span></span>
<span data-ttu-id="dc385-123">たとえば、次のコードは、 `PowerShell` コンピューター上で実行されているという名前のすべてのプロセスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc385-123">For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

<span data-ttu-id="dc385-124">AddParameter メソッドを繰り返し呼び出すことで、追加のパラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="dc385-124">You can add additional parameters by calling the AddParameter method repeatedly.</span></span>

```csharp                   
PowerShell.Create().AddCommand("Get-ChildItem")
                   .AddParameter("Path", @"c:\Windows")
                   .AddParameter("Filter", "*.exe")
                   .Invoke();
```

<span data-ttu-id="dc385-125">また、パラメーターの名前と値のディクショナリを追加するには、 [system.string メソッドを呼び出します。](/dotnet/api/System.Management.Automation.PowerShell.AddParameters)</span><span class="sxs-lookup"><span data-stu-id="dc385-125">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.PowerShell.AddParameters](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Path", @"c:\Windows");
parameters.Add("Filter", "*.exe");

PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="dc385-126">AddStatement</span><span class="sxs-lookup"><span data-stu-id="dc385-126">AddStatement</span></span>

<span data-ttu-id="dc385-127">バッチ処理をシミュレートするには、追加のステートメントをパイプラインの末尾に追加する、 [addstatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc385-127">You can simulate batching by using the [System.Management.Automation.PowerShell.AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline.</span></span>
<span data-ttu-id="dc385-128">次のコードでは、という名前の実行中のプロセスの一覧を取得 `PowerShell` し、実行中のサービスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc385-128">The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="dc385-129">AddScript</span><span class="sxs-lookup"><span data-stu-id="dc385-129">AddScript</span></span>

<span data-ttu-id="dc385-130">既存のスクリプトを実行するには、. [PowerShell. AddScript](/dotnet/api/System.Management.Automation.PowerShell.AddScript) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dc385-130">You can run an existing script by calling the [System.Management.Automation.PowerShell.AddScript](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span>
<span data-ttu-id="dc385-131">次の例では、パイプラインにスクリプトを追加して実行します。</span><span class="sxs-lookup"><span data-stu-id="dc385-131">The following example adds a script to the pipeline and runs it.</span></span>
<span data-ttu-id="dc385-132">この例では、という名前のフォルダーにという名前のスクリプトが既に存在することを前提としてい `MyScript.ps1` `D:\PSScripts` ます。</span><span class="sxs-lookup"><span data-stu-id="dc385-132">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

<span data-ttu-id="dc385-133">また、という名前のブール型パラメーターを受け取る AddScript メソッドのバージョンもあり `useLocalScope` ます。</span><span class="sxs-lookup"><span data-stu-id="dc385-133">There is also a version of the AddScript method that takes a boolean parameter named `useLocalScope`.</span></span>
<span data-ttu-id="dc385-134">このパラメーターがに設定されている場合、 `true` スクリプトはローカルスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="dc385-134">If this parameter is set to `true`, then the script is run in the local scope.</span></span>
<span data-ttu-id="dc385-135">次のコードでは、スクリプトがローカルスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="dc385-135">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a><span data-ttu-id="dc385-136">カスタム実行空間の作成</span><span class="sxs-lookup"><span data-stu-id="dc385-136">Creating a custom runspace</span></span>

<span data-ttu-id="dc385-137">前の例で使用した既定の実行空間は、すべてのコア Windows PowerShell コマンドを読み込みますが、指定されたすべてのコマンドのサブセットのみを読み込むカスタム実行空間を作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc385-137">While the default runspace used in the previous examples loads all of the core Windows PowerShell commands, you can create a custom runspace that loads only a specified subset of all commands.</span></span>
<span data-ttu-id="dc385-138">これを行うと、パフォーマンスを向上させることができます (多数のコマンドを読み込むとパフォーマンスが低下します)。または、ユーザーの機能を制限して操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc385-138">You might want to do this to improve performance (loading a larger number of commands is a performance hit), or to restrict the capability of the user to perform operations.</span></span>
<span data-ttu-id="dc385-139">限られた数のコマンドのみを公開する実行空間は、制約付き実行空間と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="dc385-139">A runspace that exposes only a limited number of commands is called a constrained runspace.</span></span>
<span data-ttu-id="dc385-140">制約付き実行空間を作成する [には、tialSessionState クラスと](/dotnet/api/System.Management.Automation.Runspaces.Runspace) [System.Management.Automation.Runspaces.Ini](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc385-140">To create a constrained runspace, you use the [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) and [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) classes.</span></span>

### <a name="creating-an-initialsessionstate-object"></a><span data-ttu-id="dc385-141">InitialSessionState オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="dc385-141">Creating an InitialSessionState object</span></span>

<span data-ttu-id="dc385-142">カスタム実行空間を作成するには、最初に [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc385-142">To create a custom runspace, you must first create an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>
<span data-ttu-id="dc385-143">次の例では、 [RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) を使用して、既定の InitialSessionState オブジェクトを作成した後に実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="dc385-143">In the following example, we use the [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) to create a runspace after creating a default InitialSessionState object.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a><span data-ttu-id="dc385-144">実行空間の制約</span><span class="sxs-lookup"><span data-stu-id="dc385-144">Constraining the runspace</span></span>

<span data-ttu-id="dc385-145">前の例では、組み込みのコア Windows PowerShell をすべて読み込む既定の [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) オブジェクトを作成しました。</span><span class="sxs-lookup"><span data-stu-id="dc385-145">In the previous example, we created a default [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object that loads all of the built-in core Windows PowerShell.</span></span>
<span data-ttu-id="dc385-146">また、tialSessionState メソッドをSystem.Management.Automation.Runspaces.Ini呼び出して、 [ CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) スナップインのコマンドのみを読み込む InitialSessionState オブジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc385-146">We could also have called the [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) method to create an InitialSessionState object that would load only the commands in the Microsoft.PowerShell.Core snapin.</span></span>
<span data-ttu-id="dc385-147">より制約のある実行空間を作成するには、 [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) メソッドを呼び出し、InitialSessionState にコマンドを追加することによって、空の InitialSessionState オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc385-147">To create a more constrained runspace, you must create an empty InitialSessionState object by calling the [System.Management.Automation.Runspaces.InitialSessionState.Create](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method, and then add commands to the InitialSessionState.</span></span>

<span data-ttu-id="dc385-148">指定したコマンドのみを読み込む実行空間を使用すると、パフォーマンスが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="dc385-148">Using a runspace that loads only the commands that you specify provides significantly improved performance.</span></span>

<span data-ttu-id="dc385-149">最初のセッション状態のコマンドレットを定義するには、system.servicemodel. [Sessionstatecmd・ entry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) クラスのメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc385-149">You use the methods of the [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) class to define cmdlets for the initial session state.</span></span>
<span data-ttu-id="dc385-150">次の例では、空の初期セッション状態を作成し、を定義して、 `Get-Command` `Import-Module` コマンドとコマンドを初期セッション状態に追加します。</span><span class="sxs-lookup"><span data-stu-id="dc385-150">The following example creates an empty initial session state, then defines and adds the `Get-Command` and `Import-Module` commands to the initial session state.</span></span>
<span data-ttu-id="dc385-151">その後、その最初のセッション状態によって制約された実行空間を作成し、その実行空間でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc385-151">We then create a runspace constrained by that initial session state, and execute the commands in that runspace.</span></span>

<span data-ttu-id="dc385-152">初期セッション状態を作成します。</span><span class="sxs-lookup"><span data-stu-id="dc385-152">Create the initial session state.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

<span data-ttu-id="dc385-153">コマンドを定義し、初期セッション状態に追加します。</span><span class="sxs-lookup"><span data-stu-id="dc385-153">Define and add commands to the initial session state.</span></span>

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

<span data-ttu-id="dc385-154">実行空間を作成して開きます。</span><span class="sxs-lookup"><span data-stu-id="dc385-154">Create and open the runspace.</span></span>

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

<span data-ttu-id="dc385-155">コマンドを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="dc385-155">Execute a command and show the result.</span></span>

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

<span data-ttu-id="dc385-156">実行すると、このコードの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dc385-156">When run, the output of this code will look as follows.</span></span>

```powershell
Get-Command
Import-Module
```

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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059679"
---
# <a name="windows-powershell-host-quickstart"></a>Windows PowerShell ホスト クイック スタート

Windows PowerShell をホストするには、アプリケーションで、使用する、 [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)クラス。 このクラスは、コマンドのパイプラインを作成し、実行空間でこれらのコマンドを実行するメソッドを提供します。 ホスト アプリケーションを作成する最も簡単な方法では、既定の実行空間を使用します。 既定の実行空間には、すべてのコア Windows PowerShell コマンドが含まれています。 アプリケーション、Windows PowerShell コマンドのサブセットのみを公開する場合は、カスタム実行空間を作成する必要があります。

## <a name="using-the-default-runspace"></a>既定の実行空間を使用します。

を開始するには、既定の実行空間を使用して、のメソッドを使用しましたします、 [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)コマンド、パラメーター、ステートメント、およびスクリプトをパイプラインに追加するクラス。

### <a name="addcommand"></a>AddCommand

使用する、 [System.Management.Automation.Powershell.AddCommand*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)のメソッド、 [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)パイプラインにコマンドを追加するクラス。 たとえば、コンピューターで実行中のプロセスの一覧を取得したいとします。 このコマンドを実行する方法は次のとおりです。

1. 作成、 [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell)オブジェクト。

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. 実行するコマンドを追加します。

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. コマンドを呼び出します。

   ```csharp
   ps.Invoke();
   ```

呼び出す場合、 [System.Management.Automation.Powershell.AddCommand*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)メソッドを呼び出す前に 2 回以上、 [System.Management.Automation.Powershell.Invoke*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドは、の結果、最初のコマンドは、2 番目にパイプします。 前のコマンドをコマンドの結果をパイプ処理したくない場合は呼び出すことによって追加、 [System.Management.Automation.Powershell.AddStatement*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)代わりにします。

### <a name="addparameter"></a>AddParameter

前の例では、パラメーターなしの 1 つのコマンドを実行します。 使用して、コマンドにパラメーターを追加することができます、 [System.Management.Automation.PSCommand.AddParameter*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)メソッドを次のコードがという名前のプロセスのすべての一覧を取得など`PowerShell`で実行されている、マシン。

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

追加のパラメーターを追加するには呼び出すことによって[System.Management.Automation.PSCommand.AddParameter*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)繰り返し。

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

呼び出すことによって、パラメーターの名前と値のディクショナリを追加することも、 [System.Management.Automation.PowerShell.AddParameters*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters)メソッド。

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>AddStatement

使用してバッチ処理をシミュレートすることができます、 [System.Management.Automation.PowerShell.AddStatement*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)メソッドで、次のコードは、名前の実行中のプロセスの一覧を取得します。 パイプラインの末尾に追加のステートメントを追加します。`PowerShell`、し、実行中のサービスの一覧を取得します。

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>AddScript

既存のスクリプトを実行するには呼び出すことによって、 [System.Management.Automation.PowerShell.AddScript*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)メソッド。 次の例では、パイプラインにスクリプトを追加し、それを実行します。 この例では、という名前のスクリプトが既に存在`MyScript.ps1`という名前のフォルダーで`D:\PSScripts`します。

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

バージョンがあります、 [System.Management.Automation.PowerShell.AddScript*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)というブール型パラメーターを受け取るメソッド`useLocalScope`します。 このパラメーターに設定されている場合`true`、し、スクリプトはローカル スコープで実行します。 次のコードは、スクリプトをローカル スコープで実行されます。

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a>カスタムの実行空間を作成します。

前の例で使用される既定の実行空間が読み込まれるすべてのコア Windows PowerShell コマンドを指定したすべてのコマンドのサブセットのみを読み込むカスタム実行空間を作成できます。 パフォーマンスを向上させるためにこれを実行する場合があります (読み込みより多くのコマンドは、パフォーマンスに影響が)、またはユーザーの操作を実行する機能を制限します。 コマンドの限られた数のみを公開する実行空間には、制約付き実行空間が呼び出されます。 使用して制約付き実行空間を作成する、 [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace)と[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)クラス。

### <a name="creating-an-initialsessionstate-object"></a>InitialSessionState オブジェクトを作成します。

カスタムの実行空間を作成する必要があります最初に作成する、 [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクト。 次の例では使用して、 [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) 、既定値を作成した後、実行空間を作成する[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクト。

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a>実行空間を制限します。

前の例で、既定値を作成しました[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)組み込みコア Windows PowerShell のすべてをロードするオブジェクト。 私たちも呼び出すことができます、 [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) Microsoft.PowerShell.Core コマンドのみを読み込むよう InitialSessionState オブジェクトを作成する方法スナップイン。 複数の制約付き実行空間を作成するには、空を作成する必要があります[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを呼び出すことによって、 [System.Management.Automation.Runspaces.InitialSessionState.Create*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create)メソッド、InitialSessionState にコマンドを追加します。

指定したコマンドのみを読み込みの実行空間を使用して大幅に向上したパフォーマンスを提供します。

メソッドを使用する、 [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry)最初のセッション状態用のコマンドレットを定義するクラス。 次の例では、最初の空のセッション状態を作成しますを定義し、追加、、`Get-Command`と`Import-Module`最初のセッション状態をコマンド。 その最初のセッション状態で制約付き実行空間を作成し、その実行空間でのコマンドを実行します。

最初のセッション状態を作成します。

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

定義し、最初のセッション状態にコマンドを追加します。

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

作成し、実行空間を開きます。

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

コマンドを実行し、結果を表示します。

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

実行すると、このコードの出力はようになります。

```powershell
Get-Command
Import-Module
```

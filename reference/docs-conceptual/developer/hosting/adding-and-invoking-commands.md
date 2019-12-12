---
title: コマンドの追加と呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62be8432-28c1-4ca2-bcdb-d0350163fa8c
caps.latest.revision: 5
ms.openlocfilehash: f776f13fe743a3f5f67de0d94883e3f754040ffc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367641"
---
# <a name="adding-and-invoking-commands"></a>コマンドを追加し、呼び出す

実行空間を作成した後、Windows PowerShellcommands とスクリプトをパイプラインに追加し、同期または非同期でパイプラインを呼び出すことができます。

## <a name="creating-a-pipeline"></a>パイプラインを作成する

 [System. Automation. Powershell](/dotnet/api/system.management.automation.powershell)クラスには、コマンド、パラメーター、およびスクリプトをパイプラインに追加するためのメソッドがいくつか用意されています。 パイプラインを同期的に呼び出すには、[システム](/dotnet/api/System.Management.Automation.PowerShell.Invoke)のオーバーロードを呼び出すか、または、システムのオーバーロードを呼び出して非同期的に呼び出します。また[は、次](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke)に、その後に、システムの呼び出しを実行して、その後で、[このメソッドを](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)呼び出します。

### <a name="addcommand"></a>AddCommand

1. システムの[管理. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトを作成します。

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

 System. powershell. powershell. [powershell. Invoke *](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドを呼び出す前に、[このメソッドを](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)複数回呼び出した場合、最初のコマンドの結果がパイプ処理され、次のようになります (以降同様)。 パイプを使用して前のコマンドの結果をコマンドに渡したくない場合は[、代わりに system.object](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)を呼び出して追加してください。

### <a name="addparameter"></a>AddParameter

 前の例では、パラメーターを指定せずに1つのコマンドを実行しています。 コマンドにパラメーターを追加するに[は、次](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)のコードを使用します。たとえば、次のコードは、コンピューター上で実行されている `PowerShell` という名前のすべてのプロセスの一覧を取得します。

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

 追加のパラメーターを追加するには、さらにパラメーターを追加します。 [Addparameter *](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)を繰り返します。

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

 また、パラメーターの名前と値のディクショナリを追加するには、 [System. Powershell. Addparameters *](/dotnet/api/System.Management.Automation.PowerShell.AddParameters)メソッドを呼び出します。

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>AddStatement

 バッチ処理をシミュレートするには、次のコードで実行中のプロセスの一覧を名前`PowerShell`で取得します。このメソッドを使用して、パイプラインの末尾にステートメントを追加します。 [System.Management.Automation.Powershell.Addstatement*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)次に、実行中のサービスの一覧を取得します。

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>AddScript

 既存のスクリプトを実行するには、 [System. Powershell. Addscript *](/dotnet/api/System.Management.Automation.PowerShell.AddScript)メソッドを呼び出します。 次の例では、パイプラインにスクリプトを追加して実行します。 この例では、`D:\PSScripts`という名前のフォルダーに `MyScript.ps1` という名前のスクリプトが既に存在することを前提としています。

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

 また、`useLocalScope`という名前のブール型パラメーターを受け取るバージョンの[System. Powershell. Addscript *](/dotnet/api/System.Management.Automation.PowerShell.AddScript)メソッドもあります。 このパラメーターが `true`に設定されている場合、スクリプトはローカルスコープで実行されます。 次のコードでは、スクリプトがローカルスコープで実行されます。

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a>パイプラインの同期的な呼び出し

 パイプラインに要素を追加したら、それを呼び出します。 パイプラインを同期的に呼び出すには、 [System. Powershell. invoke *](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドのオーバーロードを呼び出します。 次の例は、パイプラインを同期的に呼び出す方法を示しています。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS1e
{
  class HostPS1e
  {
    static void Main(string[] args)
    {
      // Using the PowerShell.Create and AddCommand
      // methods, create a command pipeline.
      PowerShell ps = PowerShell.Create().AddCommand ("Sort-Object");

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the supplied input.
      foreach (PSObject result in ps.Invoke(new int[] { 3, 1, 6, 2, 5, 4 }))
      {
          Console.WriteLine("{0}", result);
      } // End foreach.
    } // End Main.
  } // End HostPS1e.
}
```

### <a name="invoking-a-pipeline-asynchronously"></a>パイプラインの非同期呼び出し

 パイプラインを非同期的に呼び出すには、[システム](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke)のオーバーロードを呼び出して、 [IAsyncResult](https://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx)オブジェクトを作成し、次に、その後に system.servicemodel [*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッドを呼び出す必要があります。

 次の例は、パイプラインを非同期的に呼び出す方法を示しています。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS3
{
  class HostPS3
  {
    static void Main(string[] args)
    {
      // Use the PowerShell.Create and PowerShell.AddCommand
      // methods to create a command pipeline that includes
      // Get-Process cmdlet. Do not include spaces immediately
      // before or after the cmdlet name as that will cause
      // the command to fail.
      PowerShell ps = PowerShell.Create().AddCommand("Get-Process");

      // Create an IAsyncResult object and call the
      // BeginInvoke method to start running the
      // command pipeline asynchronously.
      IAsyncResult async = ps.BeginInvoke();

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the default runspace.
      foreach (PSObject result in ps.EndInvoke(async))
      {
        Console.WriteLine("{0,-20}{1}",
                result.Members["ProcessName"].Value,
                result.Members["Id"].Value);
      } // End foreach.
      System.Console.WriteLine("Hit any key to exit.");
      System.Console.ReadKey();
    } // End Main.
  } // End HostPS3.
}
```

## <a name="see-also"></a>参照

 [InitialSessionState の作成](./creating-an-initialsessionstate.md)

 [制約付き実行空間の作成](./creating-a-constrained-runspace.md)

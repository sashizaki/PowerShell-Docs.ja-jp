---
title: 追加して、コマンドを起動 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62be8432-28c1-4ca2-bcdb-d0350163fa8c
caps.latest.revision: 5
ms.openlocfilehash: 9a01f948c5b474b4f9068030907601543e13cc7e
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057656"
---
# <a name="adding-and-invoking-commands"></a>コマンドを追加し、呼び出す

実行空間を作成した後は、パイプラインに Windows PowerShellcommands とスクリプトを追加し、同期または非同期パイプラインを呼び出すできます。

## <a name="creating-a-pipeline"></a>パイプラインを作成します。

 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)クラスは、パイプラインにコマンド、パラメーター、およびスクリプトを追加するいくつかのメソッドを提供します。 オーバー ロードを呼び出すことによって、パイプラインを同期的に呼び出すことができます、 [System.Management.Automation.Powershell.Invoke*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドのオーバー ロードを呼び出すことによって非同期的にまたは、 [System.Management.Automation.Powershell.Begininvoke*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke)をクリックし、 [System.Management.Automation.Powershell.Endinvoke*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッド。

### <a name="addcommand"></a>AddCommand

1. 作成、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。

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

 呼び出す場合、 [System.Management.Automation.Powershell.Addcommand*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand)メソッドを呼び出す前に 2 回以上、 [System.Management.Automation.Powershell.Invoke*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッドは、の結果、最初のコマンドは、2 番目にパイプします。 前のコマンドをコマンドの結果をパイプ処理したくない場合は呼び出すことによって追加、 [System.Management.Automation.Powershell.Addstatement*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)代わりにします。

### <a name="addparameter"></a>AddParameter

 前の例では、パラメーターなしの 1 つのコマンドを実行します。 使用して、コマンドにパラメーターを追加することができます、 [System.Management.Automation.Pscommand.Addparameter*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)メソッドを次のコードがという名前のプロセスのすべての一覧を取得など`PowerShell`で実行されている、マシン。

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

 追加のパラメーターを追加するには呼び出すことによって[System.Management.Automation.Pscommand.Addparameter*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter)繰り返し。

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .AddParameter("Id", "12768")
                   .Invoke();
```

 呼び出すことによって、パラメーターの名前と値のディクショナリを追加することも、 [System.Management.Automation.Powershell.Addparameters*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters)メソッド。

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "PowerShell");

parameters.Add("Id", "12768");
PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>AddStatement

 使用してバッチ処理をシミュレートすることができます、 [System.Management.Automation.Powershell.Addstatement*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement)メソッドで、次のコードは、名前の実行中のプロセスの一覧を取得します。 パイプラインの末尾に追加のステートメントを追加します。`PowerShell`、し、実行中のサービスの一覧を取得します。

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>AddScript

 既存のスクリプトを実行するには呼び出すことによって、 [System.Management.Automation.Powershell.Addscript*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)メソッド。 次の例では、パイプラインにスクリプトを追加し、それを実行します。 この例では、という名前のスクリプトが既に存在`MyScript.ps1`という名前のフォルダーで`D:\PSScripts`します。

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

 バージョンがあります、 [System.Management.Automation.Powershell.Addscript*](/dotnet/api/System.Management.Automation.PowerShell.AddScript)というブール型パラメーターを受け取るメソッド`useLocalScope`します。 このパラメーターに設定されている場合`true`、し、スクリプトはローカル スコープで実行します。 次のコードは、スクリプトをローカル スコープで実行されます。

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a>パイプラインを同期的に呼び出す

 パイプラインに要素を追加した後、そのことを呼び出します。 オーバー ロードを呼び出すことに、パイプラインを同期的に呼び出す、 [System.Management.Automation.Powershell.Invoke*](/dotnet/api/System.Management.Automation.PowerShell.Invoke)メソッド。 次の例では、同期的にパイプラインを呼び出す方法を示します。

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

### <a name="invoking-a-pipeline-asynchronously"></a>パイプラインを非同期的に呼び出してください。

 オーバー ロードを呼び出すことでパイプラインを非同期的に呼び出す、 [System.Management.Automation.Powershell.Begininvoke*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke)を作成する、 [IAsyncResult](http://msdn.microsoft.com/library/system.iasyncresult\(v=vs.110\).aspx)オブジェクト、および呼び出し、 [System.Management.Automation.Powershell.Endinvoke*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッド。

 次の例では、パイプラインを非同期的に呼び出す方法を示します。

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

 [InitialSessionState を作成します。](./creating-an-initialsessionstate.md)

 [制約付き実行空間を作成します。](./creating-a-constrained-runspace.md)

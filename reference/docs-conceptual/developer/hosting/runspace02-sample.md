---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace02 サンプル
description: Runspace02 サンプル
ms.openlocfilehash: 0206e1a80f3e5488fd2dd5628985756a5ca343c8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657892"
---
# <a name="runspace02-sample"></a><span data-ttu-id="d1465-103">Runspace02 サンプル</span><span class="sxs-lookup"><span data-stu-id="d1465-103">Runspace02 Sample</span></span>

<span data-ttu-id="d1465-104">このサンプル [では、system.servicemodel クラスを](/dotnet/api/system.management.automation.powershell) 使用して、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) および [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) コマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d1465-104">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously.</span></span> <span data-ttu-id="d1465-105">[Get process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットは、ローカルコンピューター上で実行[されて](/dotnet/api/System.Diagnostics.Process)いる各プロセスの System.Diagnostics.Process.Id オブジェクトを返し、はそれらのオブジェクトをその `Sort-Object` [\*](/dotnet/api/System.Diagnostics.Process.Id)プロパティに基づいて並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="d1465-105">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects for each process running on the local computer, and the `Sort-Object` sorts the objects based on their [System.Diagnostics.Process.Id\*](/dotnet/api/System.Diagnostics.Process.Id) property.</span></span> <span data-ttu-id="d1465-106">これらのコマンドの結果 [は、system.string コントロールを](/dotnet/api/System.Windows.Forms.DataGridView) 使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1465-106">The results of these commands is displayed by using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

## <a name="requirements"></a><span data-ttu-id="d1465-107">要件</span><span class="sxs-lookup"><span data-stu-id="d1465-107">Requirements</span></span>

<span data-ttu-id="d1465-108">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1465-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="d1465-109">対象</span><span class="sxs-lookup"><span data-stu-id="d1465-109">Demonstrates</span></span>

<span data-ttu-id="d1465-110">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="d1465-110">This sample demonstrates the following.</span></span>

- <span data-ttu-id="d1465-111">コマンドを実行するため [の、system.servicemodel](/dotnet/api/system.management.automation.powershell) オブジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="d1465-111">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run commands.</span></span>

- <span data-ttu-id="d1465-112">System.servicemodel オブジェクトのパイプラインにコマンドを追加してい[ます。](/dotnet/api/system.management.automation.powershell)</span><span class="sxs-lookup"><span data-stu-id="d1465-112">Adding commands to the pipeline of [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="d1465-113">コマンドを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="d1465-113">Running the commands synchronously.</span></span>

- <span data-ttu-id="d1465-114">Windows フォームアプリケーションのコマンドの出力を表示する [には、system.string コントロールを](/dotnet/api/System.Windows.Forms.DataGridView) 使用します。</span><span class="sxs-lookup"><span data-stu-id="d1465-114">Using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control to display the output of the commands in a Windows Forms application.</span></span>

## <a name="example"></a><span data-ttu-id="d1465-115">例</span><span class="sxs-lookup"><span data-stu-id="d1465-115">Example</span></span>

<span data-ttu-id="d1465-116">このサンプルでは、Windows PowerShell によって提供される既定の実行空間で、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) および [Sort オブジェクト](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) のコマンドレットを同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="d1465-116">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="d1465-117">出力は、 [システム](/dotnet/api/System.Windows.Forms.DataGridView) のコントロールを使用してフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1465-117">The output is displayed in a form using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using System.Windows.Forms;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace02
  {
    /// <summary>
    /// This method creates the form where the output is displayed.
    /// </summary>
    private static void CreateForm()
    {
      Form form = new Form();
      DataGridView grid = new DataGridView();
      form.Controls.Add(grid);
      grid.Dock = DockStyle.Fill;

      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create())
      {
        powershell.AddCommand("get-process").AddCommand("sort-object").AddArgument("ID");
        if (Runspace.DefaultRunspace == null)
        {
          Runspace.DefaultRunspace = powershell.Runspace;
        }

        Collection<PSObject> results = powershell.Invoke();

        // The generic collection needs to be re-wrapped in an ArrayList
        // for data-binding to work.
        ArrayList objects = new ArrayList();
        objects.AddRange(results);

        // The DataGridView will use the PSObjectTypeDescriptor type
        // to retrieve the properties.
        grid.DataSource = objects;
      }

      form.ShowDialog();
    }

    /// <summary>
    /// This sample uses a PowerShell object to run the Get-Process
    /// and Sort-Object cmdlets synchronously. Windows Forms and
    /// data binding are then used to display the results in a
    /// DataGridView control.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object.
    /// 2. Adding commands and arguments to the pipeline of
    ///    the PowerShell object.
    /// 3. Running the commands synchronously.
    /// 4. Using a DataGridView control to display the output
    ///    of the commands in a Windows Forms application.
    /// </remarks>
    private static void Main(string[] args)
    {
      Runspace02.CreateForm();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="d1465-118">参照</span><span class="sxs-lookup"><span data-stu-id="d1465-118">See Also</span></span>

[<span data-ttu-id="d1465-119">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="d1465-119">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)

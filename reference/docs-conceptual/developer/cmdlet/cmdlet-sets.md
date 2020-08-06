---
title: コマンドレットの設定 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9595c9ca09148de05c69d60a2ede5688c3db61b0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774815"
---
# <a name="cmdlet-sets"></a><span data-ttu-id="a2ca3-102">コマンドレット セット</span><span class="sxs-lookup"><span data-stu-id="a2ca3-102">Cmdlet Sets</span></span>

<span data-ttu-id="a2ca3-103">コマンドレットを設計するときに、同じデータに対して複数の操作を実行することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-103">When you design your cmdlets, you might encounter cases in which you need to perform several actions on the same piece of data.</span></span> <span data-ttu-id="a2ca3-104">たとえば、データの取得と設定、またはプロセスの開始と停止が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-104">For example, you might need to get and set data or start and stop a process.</span></span> <span data-ttu-id="a2ca3-105">各アクションを実行するために個別のコマンドレットを作成する必要がありますが、コマンドレットの設計には、個々のコマンドレットのクラスの派生元である基本クラスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-105">Although you will need to create separate cmdlets to perform each action, your cmdlet design should include a base class from which the classes for the individual cmdlets are derived.</span></span>

<span data-ttu-id="a2ca3-106">基底クラスを実装する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-106">Keep the following things in mind when implementing a base class.</span></span>

- <span data-ttu-id="a2ca3-107">基底クラスのすべての派生コマンドレットで使用される共通パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-107">Declare any common parameters used by all the derived cmdlets in the base class.</span></span>

- <span data-ttu-id="a2ca3-108">コマンドレット固有のパラメーターを適切なコマンドレットクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-108">Add cmdlet-specific parameters to the appropriate cmdlet class.</span></span>

- <span data-ttu-id="a2ca3-109">基底クラスの適切な入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-109">Override the appropriate input processing method in the base class.</span></span>

- <span data-ttu-id="a2ca3-110">すべてのコマンドレットクラスで[system.servicemodel 属性を](/dotnet/api/System.Management.Automation.CmdletAttribute)宣言しますが、基底クラスでは宣言しません。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-110">Declare the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute on all cmdlet classes, but do not declare it on the base class.</span></span>

- <span data-ttu-id="a2ca3-111">コマンドレットのセットを反映した名前と説明を持つ[add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)または[Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-111">Implement a [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class whose name and description reflects the set of cmdlets.</span></span>

## <a name="example"></a><span data-ttu-id="a2ca3-112">例</span><span class="sxs-lookup"><span data-stu-id="a2ca3-112">Example</span></span>

<span data-ttu-id="a2ca3-113">次の例は、同じ基本クラスから派生した、Get Proc と Stop Proc コマンドレットによって使用される基底クラスの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="a2ca3-113">The following example shows the implementation of a base class that is used by Get-Proc and Stop-Proc cmdlet that derive from the same base class.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace.

namespace Microsoft.Samples.PowerShell.Commands
{

  #region ProcessCommands

  /// <summary>
  /// This class implements a Stop-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>
  [Cmdlet(VerbsLifecycle.Stop, "Proc", SupportsShouldProcess = true)]
  public class StopProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      if (ShouldProcess(process.ProcessName, "Stop-Proc"))
      {
        process.Kill();
      }
    }
  }

  /// <summary>
  /// This class implements a Get-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>

  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      WriteObject(process);
    }
  }

  /// <summary>
  /// This class is the base class that defines the common
  /// functionality used by the Get-Proc and Stop-Proc
  /// cmdlets.
  /// </summary>
  public class BaseProcCommand : Cmdlet
  {
    #region Parameters

    // Defines the Name parameter that is used to
    // specify a process by its name.
    [Parameter(
               Position = 0,
               Mandatory = true,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true
    )]
    public string[] Name
    {
      get { return processNames; }
      set { processNames = value; }
    }
    private string[] processNames;

    // Defines the Exclude parameter that is used to
    // specify which processes should be excluded when
    // the cmdlet performs its action.
    [Parameter()]
    public string[] Exclude
    {
      get { return excludeNames; }
      set { excludeNames = value; }
    }
    private string[] excludeNames = new string[0];
    #endregion Parameters

    public virtual void ProcessObject(Process process)
    {
      throw new NotImplementedException("This method should be overridden.");
    }

    #region Cmdlet Overrides
    // <summary>
    // For each of the requested process names, retrieve and write
    // the associated processes.
    // </summary>
    protected override void ProcessRecord()
    {
      // Set up the wildcard characters used in resolving
      // the process names.
      WildcardOptions options = WildcardOptions.IgnoreCase |
                                WildcardOptions.Compiled;

      WildcardPattern[] include = new WildcardPattern[Name.Length];
      for (int i = 0; i < Name.Length; i++)
      {
        include[i] = new WildcardPattern(Name[i], options);
      }

      WildcardPattern[] exclude = new WildcardPattern[Exclude.Length];
      for (int i = 0; i < Exclude.Length; i++)
      {
        exclude[i] = new WildcardPattern(Exclude[i], options);
      }

      foreach (Process p in Process.GetProcesses())
      {
        foreach (WildcardPattern wIn in include)
        {
          if (wIn.IsMatch(p.ProcessName))
          {
            bool processThisOne = true;
            foreach (WildcardPattern wOut in exclude)
            {
              if (wOut.IsMatch(p.ProcessName))
              {
                processThisOne = false;
                break;
              }
            }
            if (processThisOne)
            {
              ProcessObject(p);
            }
            break;
          }
        }
      }
    }
    #endregion Cmdlet Overrides
  }
    #endregion ProcessCommands
}
```

## <a name="see-also"></a><span data-ttu-id="a2ca3-114">参照</span><span class="sxs-lookup"><span data-stu-id="a2ca3-114">See Also</span></span>

[<span data-ttu-id="a2ca3-115">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="a2ca3-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

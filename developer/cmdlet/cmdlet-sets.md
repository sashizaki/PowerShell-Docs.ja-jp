---
title: コマンドレットのセット |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcf0739e-920e-4dd8-afca-2c6d6927bc2a
caps.latest.revision: 10
ms.openlocfilehash: ef3b5bab5dcafc578397bcb4f071776bbdeaced1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068387"
---
# <a name="cmdlet-sets"></a><span data-ttu-id="73b59-102">コマンドレット セット</span><span class="sxs-lookup"><span data-stu-id="73b59-102">Cmdlet Sets</span></span>

<span data-ttu-id="73b59-103">コマンドレットを設計するときは、データの同じ部分に対していくつかの操作を実行する必要がある場合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73b59-103">When you design your cmdlets, you might encounter cases in which you need to perform several actions on the same piece of data.</span></span> <span data-ttu-id="73b59-104">たとえば、取得データを設定または開始時刻とプロセスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73b59-104">For example, you might need to get and set data or start and stop a process.</span></span> <span data-ttu-id="73b59-105">各アクションを実行するための別のコマンドレットを作成する必要がありますが、コマンドレットのデザインは、個々 のコマンドレットについては、クラスの派生元の基本クラスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="73b59-105">Although you will need to create separate cmdlets to perform each action, your cmdlet design should include a base class from which the classes for the individual cmdlets are derived.</span></span>

<span data-ttu-id="73b59-106">基本クラスを実装するときに、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="73b59-106">Keep the following things in mind when implementing a base class.</span></span>

- <span data-ttu-id="73b59-107">基本クラスのすべての派生コマンドレットで使用される共通パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="73b59-107">Declare any common parameters used by all the derived cmdlets in the base class.</span></span>

- <span data-ttu-id="73b59-108">コマンドレットの適切なクラスに固有コマンドレットのパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="73b59-108">Add cmdlet-specific parameters to the appropriate cmdlet class.</span></span>

- <span data-ttu-id="73b59-109">基本クラスのメソッドを処理する適切な入力をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="73b59-109">Override the appropriate input processing method in the base class.</span></span>

- <span data-ttu-id="73b59-110">宣言、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)コマンドレットのすべてのクラスに属性しますが、基本クラスで宣言しないでください。</span><span class="sxs-lookup"><span data-stu-id="73b59-110">Declare the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute on all cmdlet classes, but do not declare it on the base class.</span></span>

- <span data-ttu-id="73b59-111">実装を[System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn)または[System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラスの名前と説明には、一連のコマンドレットが反映されます。</span><span class="sxs-lookup"><span data-stu-id="73b59-111">Implement a [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class whose name and description reflects the set of cmdlets.</span></span>

## <a name="example"></a><span data-ttu-id="73b59-112">例</span><span class="sxs-lookup"><span data-stu-id="73b59-112">Example</span></span>

<span data-ttu-id="73b59-113">次の例では、Get プロシージャによって使用される基本クラスと同じ基本クラスから派生する停止 Proc コマンドレットの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="73b59-113">The following example shows the implementation of a base class that is used by Get-Proc and Stop-Proc cmdlet that derive from the same base class.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="73b59-114">参照</span><span class="sxs-lookup"><span data-stu-id="73b59-114">See Also</span></span>

[<span data-ttu-id="73b59-115">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="73b59-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

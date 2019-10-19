---
title: System | を変更するコマンドレットを作成するMicrosoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- should process [PowerShell Programmer's Guide]
- should continue [PowerShell Programmer's Guide]
- user feedback [PowerShell Programmer's Guide]
- confirm impact [PowerShell Programmer's Guide]
ms.assetid: 59be4120-1700-4d92-a308-ef4a32ccf11a
caps.latest.revision: 8
ms.openlocfilehash: 8a65915b88a04e36e773853b903528a65fe11e99
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365761"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a><span data-ttu-id="d3614-102">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="d3614-102">Creating a Cmdlet that Modifies the System</span></span>

<span data-ttu-id="d3614-103">コマンドレットは、Windows PowerShell ランタイムの状態だけでなく、システムの実行状態を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-103">Sometimes a cmdlet must modify the running state of the system, not just the state of the Windows PowerShell runtime.</span></span> <span data-ttu-id="d3614-104">このような場合は、コマンドレットを使用して、変更を行うかどうかを確認する機会をユーザーに許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-104">In these cases, the cmdlet should allow the user a chance to confirm whether or not to make the change.</span></span>

<span data-ttu-id="d3614-105">確認をサポートするには、コマンドレットで2つの処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-105">To support confirmation a cmdlet must do two things.</span></span>

- <span data-ttu-id="d3614-106">Supportsを指定するときに、このコマンドレットでの確認がサポートされていることを宣言します。 `true` に設定し[ます。](/dotnet/api/System.Management.Automation.CmdletAttribute)</span><span class="sxs-lookup"><span data-stu-id="d3614-106">Declare that the cmdlet supports confirmation when you specify the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute by setting the SupportsShouldProcess keyword to `true`.</span></span>

- <span data-ttu-id="d3614-107">コマンドレットの実行中に、次の例に示すように、「」というコマンドレット[を呼び出します](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)。</span><span class="sxs-lookup"><span data-stu-id="d3614-107">Call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) during the execution of the cmdlet (as shown in the following example).</span></span>

<span data-ttu-id="d3614-108">確認をサポートすることで、コマンドレットは、Windows PowerShell によって提供される @no__t 0 および `WhatIf` パラメーターを公開します。また、コマンドレットの開発ガイドラインにも適合します (コマンドレット開発ガイドラインの詳細については、「コマンドレット」を参照してください)。 [開発ガイドライン](./cmdlet-development-guidelines.md)。)。</span><span class="sxs-lookup"><span data-stu-id="d3614-108">By supporting confirmation, a cmdlet exposes the `Confirm` and `WhatIf` parameters that are provided by Windows PowerShell, and also meets the development guidelines for cmdlets (For more information about cmdlet development guidelines, see [Cmdlet Development Guidelines](./cmdlet-development-guidelines.md).).</span></span>

## <a name="changing-the-system"></a><span data-ttu-id="d3614-109">システムの変更</span><span class="sxs-lookup"><span data-stu-id="d3614-109">Changing the System</span></span>

<span data-ttu-id="d3614-110">"システムの変更" の動作は、Windows PowerShell の外部でシステムの状態を変更する可能性のあるすべてのコマンドレットを指します。</span><span class="sxs-lookup"><span data-stu-id="d3614-110">The act of "changing the system" refers to any cmdlet that potentially changes the state of the system outside Windows PowerShell.</span></span> <span data-ttu-id="d3614-111">たとえば、プロセスを停止したり、ユーザーアカウントを有効または無効にしたり、データベーステーブルに行を追加したりすると、システムに対するすべての変更が確認されます。</span><span class="sxs-lookup"><span data-stu-id="d3614-111">For example, stopping a process, enabling or disabling a user account, or adding a row to a database table are all changes to the system that should be confirmed.</span></span> <span data-ttu-id="d3614-112">これに対して、データの読み取りまたは一時的な接続の確立を行う操作は、システムを変更するのではなく、通常は確認を必要としません。</span><span class="sxs-lookup"><span data-stu-id="d3614-112">In contrast, operations that read data or establish transient connections do not change the system and generally do not require confirmation.</span></span> <span data-ttu-id="d3614-113">@No__t-0 など、Windows PowerShell ランタイム内で効果が制限されている操作についても、確認は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d3614-113">Confirmation is also not needed for actions whose effect is limited to inside the Windows PowerShell runtime, such as `set-variable`.</span></span> <span data-ttu-id="d3614-114">永続的な変更を行う可能性のあるコマンドレットは、`SupportsShouldProcess` を宣言し、[を呼び出します](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)。これは、永続的な変更を行う場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-114">Cmdlets that might or might not make a persistent change should declare `SupportsShouldProcess` and call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) only if they are about to make a persistent change.</span></span>

> [!NOTE]
> <span data-ttu-id="d3614-115">"プロセスの確認" はコマンドレットにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3614-115">ShouldProcess confirmation applies only to cmdlets.</span></span> <span data-ttu-id="d3614-116">コマンドまたはスクリプトが、.NET のメソッドまたはプロパティを直接呼び出すか、Windows PowerShell の外部でアプリケーションを呼び出すことによって、システムの実行状態を変更した場合、この形式の確認は使用できません。</span><span class="sxs-lookup"><span data-stu-id="d3614-116">If a command or script modifies the running state of a system by directly calling .NET methods or properties, or by calling applications outside of Windows PowerShell, this form of confirmation will not be available.</span></span>

## <a name="the-stopproc-cmdlet"></a><span data-ttu-id="d3614-117">StopProc コマンドレット</span><span class="sxs-lookup"><span data-stu-id="d3614-117">The StopProc Cmdlet</span></span>

<span data-ttu-id="d3614-118">このトピックでは、Get Proc コマンドレットを使用して取得したプロセスを停止しようとする Stop Proc コマンドレットについて説明します (「[最初のコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="d3614-118">This topic describes a Stop-Proc cmdlet that attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="d3614-119">コマンドレットの定義</span><span class="sxs-lookup"><span data-stu-id="d3614-119">Defining the Cmdlet</span></span>

<span data-ttu-id="d3614-120">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="d3614-120">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="d3614-121">システムを変更するためのコマンドレットを記述しているので、それに応じた名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-121">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="d3614-122">このコマンドレットはシステムプロセスを停止するため、ここで選択した動詞名は "Stop" で、 [Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスで定義されます。これは、コマンドレットがプロセスを停止することを示す "Proc" という名詞です。</span><span class="sxs-lookup"><span data-stu-id="d3614-122">This cmdlet stops system processes, so the verb name chosen here is "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate that the cmdlet stops processes.</span></span> <span data-ttu-id="d3614-123">承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-123">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="d3614-124">この Stop Proc コマンドレットのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d3614-124">The following is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

<span data-ttu-id="d3614-125">@No__t- [1 属性の宣言で](/dotnet/api/System.Management.Automation.CmdletAttribute)は、コマンドレットが system.object の呼び出しを行うことができるように、-1 attribute キーワードが @no__t に設定されていることに注意して[ください。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) [このコマンドレットは続行](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)します。</span><span class="sxs-lookup"><span data-stu-id="d3614-125">Be aware that in the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration, the `SupportsShouldProcess` attribute keyword is set to `true` to enable the cmdlet to make calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span> <span data-ttu-id="d3614-126">このキーワードが設定されていない場合、ユーザーは `Confirm` および `WhatIf` パラメーターを使用できません。</span><span class="sxs-lookup"><span data-stu-id="d3614-126">Without this keyword set, the `Confirm` and `WhatIf` parameters will not be available to the user.</span></span>

### <a name="extremely-destructive-actions"></a><span data-ttu-id="d3614-127">非常に破壊的操作</span><span class="sxs-lookup"><span data-stu-id="d3614-127">Extremely Destructive Actions</span></span>

<span data-ttu-id="d3614-128">操作の中には、アクティブなハードディスクパーティションの再フォーマットなど、非常に破壊的なものがあります。</span><span class="sxs-lookup"><span data-stu-id="d3614-128">Some operations are extremely destructive, such as reformatting an active hard disk partition.</span></span> <span data-ttu-id="d3614-129">このような場合は、 [no__t 属性を](/dotnet/api/System.Management.Automation.CmdletAttribute)宣言するときに、コマンドレットで `ConfirmImpact` @ no__t を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-129">In these cases, the cmdlet should set `ConfirmImpact` = `ConfirmImpact.High` when declaring the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute.</span></span> <span data-ttu-id="d3614-130">この設定により、ユーザーが `Confirm` パラメーターを指定していない場合でも、コマンドレットはユーザー確認を要求します。</span><span class="sxs-lookup"><span data-stu-id="d3614-130">This setting forces the cmdlet to request user confirmation even when the user has not specified the `Confirm` parameter.</span></span> <span data-ttu-id="d3614-131">ただし、コマンドレットの開発者は、ユーザーアカウントの削除など、破壊的な可能性がある操作については、乱用 `ConfirmImpact` を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-131">However, cmdlet developers should avoid overusing `ConfirmImpact` for operations that are just potentially destructive, such as deleting a user account.</span></span> <span data-ttu-id="d3614-132">@No__t-0 が " [System. Automation. ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **high"** に設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-132">Remember that if `ConfirmImpact` is set to [System.Management.Automation.ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **High**.</span></span>

<span data-ttu-id="d3614-133">同様に、一部の操作は破壊的になる可能性はほとんどありませんが、理論的には Windows PowerShell の外部でシステムの実行状態を変更します。</span><span class="sxs-lookup"><span data-stu-id="d3614-133">Similarly, some operations are unlikely to be destructive, although they do in theory modify the running state of a system outside Windows PowerShell.</span></span> <span data-ttu-id="d3614-134">このようなコマンドレットでは、`ConfirmImpact` から[system.string に設定できます。](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0)</span><span class="sxs-lookup"><span data-stu-id="d3614-134">Such cmdlets can set `ConfirmImpact` to [System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0).</span></span> <span data-ttu-id="d3614-135">これにより、ユーザーが中程度の影響と大きな影響を与える操作のみを確認するように求められた場合に、確認要求がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="d3614-135">This will bypass confirmation requests where the user has asked to confirm only medium-impact and high-impact operations.</span></span>

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="d3614-136">システム変更のパラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="d3614-136">Defining Parameters for System Modification</span></span>

<span data-ttu-id="d3614-137">このセクションでは、システムの変更をサポートするために必要なコマンドレットなど、コマンドレットのパラメーターの定義方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3614-137">This section describes how to define the cmdlet parameters, including those that are needed to support system modification.</span></span> <span data-ttu-id="d3614-138">パラメーターの定義に関する全般的な情報が必要な場合は、「[コマンドライン入力を処理するパラメーターを追加](./adding-parameters-that-process-command-line-input.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-138">See [Adding Parameters that Process CommandLine Input](./adding-parameters-that-process-command-line-input.md) if you need general information about defining parameters.</span></span>

<span data-ttu-id="d3614-139">Stop Proc コマンドレットは、3つのパラメーター (`Name`、`Force`、`PassThru`) を定義します。</span><span class="sxs-lookup"><span data-stu-id="d3614-139">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span>

<span data-ttu-id="d3614-140">@No__t-0 パラメーターは、プロセス入力オブジェクトの `Name` プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="d3614-140">The `Name` parameter corresponds to the `Name` property of the process input object.</span></span> <span data-ttu-id="d3614-141">このサンプルの `Name` パラメーターは必須であることに注意してください。停止する名前付きプロセスがない場合、コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d3614-141">Be aware that the `Name` parameter in this sample is mandatory, as the cmdlet will fail if it does not have a named process to stop.</span></span>

<span data-ttu-id="d3614-142">@No__t-0 パラメーターを指定すると、ユーザーは、このコマンドレットの呼び出しをオーバーライドでき[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="d3614-142">The `Force` parameter allows the user to override calls to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span> <span data-ttu-id="d3614-143">実際、@no__t- [2 を指定](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)すると、コマンドレットによって system.object の呼び出しがスキップされるように、@no__t を呼び出すコマンドレットには、1つのパラメーターが必要に[なります。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)操作を続行します。</span><span class="sxs-lookup"><span data-stu-id="d3614-143">In fact, any cmdlet that calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) should have a `Force` parameter so that when `Force` is specified, the cmdlet skips the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) and proceeds with the operation.</span></span> <span data-ttu-id="d3614-144">これは、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出しには影響しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-144">Be aware that this does not affect calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span></span>

<span data-ttu-id="d3614-145">@No__t-0 パラメーターを使用すると、コマンドレットがパイプライン (この場合はプロセスが停止した後) を介して出力オブジェクトを渡すかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d3614-145">The `PassThru` parameter allows the user to indicate whether the cmdlet passes an output object through the pipeline, in this case, after a process is stopped.</span></span> <span data-ttu-id="d3614-146">このパラメーターは、入力オブジェクトのプロパティではなく、コマンドレット自体に関連付けられていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-146">Be aware that this parameter is tied to the cmdlet itself instead of to a property of the input object.</span></span>

<span data-ttu-id="d3614-147">Stop Proc コマンドレットのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d3614-147">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

```csharp
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

/// <summary>
/// Specify the Force parameter that allows the user to override
/// the ShouldContinue call to force the stop operation. This
/// parameter should always be used with caution.
/// </summary>
[Parameter]
public SwitchParameter Force
{
  get { return force; }
  set { force = value; }
}
private bool force;

/// <summary>
/// Specify the PassThru parameter that allows the user to specify
/// that the cmdlet should pass the process object down the pipeline
/// after the process has been stopped.
/// </summary>
[Parameter]
public SwitchParameter PassThru
{
  get { return passThru; }
  set { passThru = value; }
}
private bool passThru;
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="d3614-148">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="d3614-148">Overriding an Input Processing Method</span></span>

<span data-ttu-id="d3614-149">コマンドレットでは、入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-149">The cmdlet must override an input processing method.</span></span> <span data-ttu-id="d3614-150">次のコードは、サンプルの Stop Proc コマンドレットで使用される、system.object[のオーバーライドを](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)示しています。</span><span class="sxs-lookup"><span data-stu-id="d3614-150">The following code illustrates the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override used in the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="d3614-151">このメソッドは、要求されたプロセス名ごとに、プロセスが特別なプロセスではないことを保証し、プロセスを停止し、`PassThru` パラメーターが指定されている場合は出力オブジェクトを送信します。</span><span class="sxs-lookup"><span data-stu-id="d3614-151">For each requested process name, this method ensures that the process is not a special process, tries to stop the process, and then sends an output object if the `PassThru` parameter is specified.</span></span>

```csharp
protected override void ProcessRecord()
{
  foreach (string name in processNames)
  {
    // For every process name passed to the cmdlet, get the associated
    // process(es). For failures, write a non-terminating error
    Process[] processes;

    try
    {
      processes = Process.GetProcessesByName(name);
    }
    catch (InvalidOperationException ioe)
    {
      WriteError(new ErrorRecord(ioe,"Unable to access the target process by name",
                 ErrorCategory.InvalidOperation, name));
      continue;
    }

    // Try to stop the process(es) that have been retrieved for a name
    foreach (Process process in processes)
    {
      string processName;

      try
      {
        processName = process.ProcessName;
      }

      catch (Win32Exception e)
        {
          WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                     ErrorCategory.ReadError, process));
          continue;
        }

        // Call Should Process to confirm the operation first.
        // This is always false if WhatIf is set.
        if (!ShouldProcess(string.Format("{0} ({1})", processName,
                           process.Id)))
        {
          continue;
        }
        // Call ShouldContinue to make sure the user really does want
        // to stop a critical process that could possibly stop the computer.
        bool criticalProcess =
             criticalProcessNames.Contains(processName.ToLower());

        if (criticalProcess &&!force)
        {
          string message = String.Format
                ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                processName);

          // It is possible that ProcessRecord is called multiple times
          // when the Name parameter receives objects as input from the
          // pipeline. So to retain YesToAll and NoToAll input that the
          // user may enter across multiple calls to ProcessRecord, this
          // information is stored as private members of the cmdlet.
          if (!ShouldContinue(message, "Warning!",
                              ref yesToAll,
                              ref noToAll))
          {
            continue;
          }
        } // if (criticalProcess...
        // Stop the named process.
        try
        {
          process.Kill();
        }
        catch (Exception e)
        {
          if ((e is Win32Exception) || (e is SystemException) ||
              (e is InvalidOperationException))
          {
            // This process could not be stopped so write
            // a non-terminating error.
            string message = String.Format("{0} {1} {2}",
                             "Could not stop process \"", processName,
                             "\".");
            WriteError(new ErrorRecord(e, message,
                       ErrorCategory.CloseError, process));
                       continue;
          } // if ((e is...
          else throw;
        } // catch

        // If the PassThru parameter argument is
        // True, pass the terminated process on.
        if (passThru)
        {
          WriteObject(process);
        }
    } // foreach (Process...
  } // foreach (string...
} // ProcessRecord
```

## <a name="calling-the-shouldprocess-method"></a><span data-ttu-id="d3614-152">メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="d3614-152">Calling the ShouldProcess Method</span></span>

<span data-ttu-id="d3614-153">コマンドレットの入力処理方法では、変更 (ファイルの削除など) がシステムの実行状態になる前に、操作の実行を確認するために、 [system.string メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-153">The input processing method of your cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to confirm execution of an operation before a change (for example, deleting files) is made to the running state of the system.</span></span> <span data-ttu-id="d3614-154">これにより、Windows PowerShell ランタイムはシェル内で適切な "WhatIf" および "Confirm" 動作を提供できます。</span><span class="sxs-lookup"><span data-stu-id="d3614-154">This allows the Windows PowerShell runtime to supply the correct "WhatIf" and "Confirm" behavior within the shell.</span></span>

> [!NOTE]
> <span data-ttu-id="d3614-155">コマンドレットによって処理される必要があることが示され、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出しに失敗した場合は、ユーザーがシステムを予期せず変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-155">If a cmdlet states that it supports should process and fails to make the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call, the user might modify the system unexpectedly.</span></span>

<span data-ttu-id="d3614-156">この呼び出しでは、変更するリソースの名前がユーザーに送信され[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) Windows PowerShell ランタイムでは、コマンドライン設定またはユーザー設定変数を考慮して、次の項目を決定します。ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3614-156">The call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command-line settings or preference variables in determining what should be displayed to the user.</span></span>

<span data-ttu-id="d3614-157">次の例は、サンプルの Stop Proc コマンドレットでの、 [system](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .................................................. [...](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)</span><span class="sxs-lookup"><span data-stu-id="d3614-157">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="d3614-158">"メソッドの続行" メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="d3614-158">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="d3614-159">システムの呼び出しによって、ユーザーにセカンダリメッセージが送信されるように[なり](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ます。</span><span class="sxs-lookup"><span data-stu-id="d3614-159">The call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method sends a secondary message to the user.</span></span> <span data-ttu-id="d3614-160">この呼び出しは、@no__t の呼び出しが[返され](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)た後、-1 を返し、@no__t パラメーターが `true` に設定されていない場合に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d3614-160">This call is made after the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) returns `true` and if the `Force` parameter was not set to `true`.</span></span> <span data-ttu-id="d3614-161">ユーザーは、操作を続行する必要があるかどうかを伝えるフィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="d3614-161">The user can then provide feedback to say whether the operation should be continued.</span></span> <span data-ttu-id="d3614-162">コマンドレットでは、system.object を呼び出し[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)危険性の高いシステム変更については、追加のチェックとして続行するか、すべてのオプションをユーザーに提供する必要があるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-162">Your cmdlet calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) as an additional check for potentially dangerous system modifications or when you want to provide yes-to-all and no-to-all options to the user.</span></span>

<span data-ttu-id="d3614-163">次の例では、System... コマンドレットの呼び出しを示して[います。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)サンプルの Stop Proc コマンドレット[で、このメソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドから続行します。</span><span class="sxs-lookup"><span data-stu-id="d3614-163">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

```csharp
if (criticalProcess &&!force)
{
  string message = String.Format
        ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
        processName);

  // It is possible that ProcessRecord is called multiple times
  // when the Name parameter receives objects as input from the
  // pipeline. So to retain YesToAll and NoToAll input that the
  // user may enter across multiple calls to ProcessRecord, this
  // information is stored as private members of the cmdlet.
  if (!ShouldContinue(message, "Warning!",
                      ref yesToAll,
                      ref noToAll))
  {
    continue;
  }
} // if (criticalProcess...
```

## <a name="stopping-input-processing"></a><span data-ttu-id="d3614-164">入力処理の停止</span><span class="sxs-lookup"><span data-stu-id="d3614-164">Stopping Input Processing</span></span>

<span data-ttu-id="d3614-165">システムの変更を行うコマンドレットの入力処理メソッドでは、入力の処理を停止する方法が提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-165">The input processing method of a cmdlet that makes system modifications must provide a way of stopping the processing of input.</span></span> <span data-ttu-id="d3614-166">この Stop Proc コマンドレットの場合は[、system.](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) [..](/dotnet/api/System.Diagnostics.Process.Kill) .......................................................</span><span class="sxs-lookup"><span data-stu-id="d3614-166">In the case of this Stop-Proc cmdlet, a call is made from the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to the [System.Diagnostics.Process.Kill\*](/dotnet/api/System.Diagnostics.Process.Kill) method.</span></span> <span data-ttu-id="d3614-167">@No__t-0 パラメーターが `true` に設定されているため、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)は、プロセスオブジェクトをパイプラインに送信するために、そのプロセスオブジェクトを送信するため[にも呼び出さ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)れます。</span><span class="sxs-lookup"><span data-stu-id="d3614-167">Because the `PassThru` parameter is set to `true`, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) also calls [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) to send the process object to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="d3614-168">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="d3614-168">Code Sample</span></span>

<span data-ttu-id="d3614-169">完全なC#サンプルコードについては、「 [StopProcessSample01 sample](./stopprocesssample01-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-169">For the complete C# sample code, see [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="d3614-170">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="d3614-170">Defining Object Types and Formatting</span></span>

<span data-ttu-id="d3614-171">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="d3614-171">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="d3614-172">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-172">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="d3614-173">新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-173">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="d3614-174">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="d3614-174">Building the Cmdlet</span></span>

<span data-ttu-id="d3614-175">コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3614-175">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="d3614-176">コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-176">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="d3614-177">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="d3614-177">Testing the Cmdlet</span></span>

<span data-ttu-id="d3614-178">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="d3614-178">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="d3614-179">ここでは、Stop Proc コマンドレットをテストするいくつかのテストについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d3614-179">Here are several tests that test the Stop-Proc cmdlet.</span></span> <span data-ttu-id="d3614-180">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-180">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="d3614-181">次に示すように、Windows PowerShell を起動し、Stop-Proc コマンドレットを使用して処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="d3614-181">Start Windows PowerShell and use the Stop-Proc cmdlet to stop processing as shown below.</span></span> <span data-ttu-id="d3614-182">コマンドレットでは `Name` パラメーターを必須と指定しているので、コマンドレットはパラメーターを照会します。</span><span class="sxs-lookup"><span data-stu-id="d3614-182">Because the cmdlet specifies the `Name` parameter as mandatory, the cmdlet queries for the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

<span data-ttu-id="d3614-183">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3614-183">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- <span data-ttu-id="d3614-184">次に、コマンドレットを使用して、"NOTEPAD" という名前のプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="d3614-184">Now let's use the cmdlet to stop the process named "NOTEPAD".</span></span> <span data-ttu-id="d3614-185">コマンドレットでは、操作を確認するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d3614-185">The cmdlet asks you to confirm the action.</span></span>

    ```powershell
    PS> stop-proc -Name notepad
    ```

<span data-ttu-id="d3614-186">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3614-186">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="d3614-187">以下に示すように Stop-Proc を使用して、"WINLOGON" という名前の重要なプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="d3614-187">Use Stop-Proc as shown to stop the critical process named "WINLOGON".</span></span> <span data-ttu-id="d3614-188">オペレーティングシステムが再起動されるため、この操作の実行についての警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3614-188">You are prompted and warned about performing this action because it will cause the operating system to reboot.</span></span>

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

<span data-ttu-id="d3614-189">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3614-189">The following output appears.</span></span>

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- <span data-ttu-id="d3614-190">ここで、警告を受信せずに WINLOGON プロセスを停止してみましょう。</span><span class="sxs-lookup"><span data-stu-id="d3614-190">Let's now try to stop the WINLOGON process without receiving a warning.</span></span> <span data-ttu-id="d3614-191">このコマンドの入力では、`Force` パラメーターを使用して警告を上書きすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d3614-191">Be aware that this command entry uses the `Force` parameter to override the warning.</span></span>

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

<span data-ttu-id="d3614-192">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3614-192">The following output appears.</span></span>

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="d3614-193">参照</span><span class="sxs-lookup"><span data-stu-id="d3614-193">See Also</span></span>

[<span data-ttu-id="d3614-194">コマンドライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="d3614-194">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

<span data-ttu-id="d3614-195">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="d3614-195">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="d3614-196">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="d3614-196">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="d3614-197">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="d3614-197">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="d3614-198">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="d3614-198">Cmdlet Samples</span></span>](./cmdlet-samples.md)
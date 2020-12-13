---
ms.date: 09/13/2016
ms.topic: reference
title: システムを変更するコマンドレットを作成する
description: システムを変更するコマンドレットを作成する
ms.openlocfilehash: 757f2c97bb4b5dcf2fb633cd35fe52bc5f6c5cf9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355546"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a><span data-ttu-id="34579-103">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="34579-103">Creating a Cmdlet that Modifies the System</span></span>

<span data-ttu-id="34579-104">コマンドレットは、Windows PowerShell ランタイムの状態だけでなく、システムの実行状態を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="34579-104">Sometimes a cmdlet must modify the running state of the system, not just the state of the Windows PowerShell runtime.</span></span> <span data-ttu-id="34579-105">このような場合は、コマンドレットを使用して、変更を行うかどうかを確認する機会をユーザーに許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34579-105">In these cases, the cmdlet should allow the user a chance to confirm whether or not to make the change.</span></span>

<span data-ttu-id="34579-106">確認をサポートするには、コマンドレットで2つの処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="34579-106">To support confirmation a cmdlet must do two things.</span></span>

- <span data-ttu-id="34579-107">Supportsをに設定するキーワードをに設定することによっ [て、この](/dotnet/api/System.Management.Automation.CmdletAttribute) コマンドレットでの確認がサポートされていることを宣言 `true` します。</span><span class="sxs-lookup"><span data-stu-id="34579-107">Declare that the cmdlet supports confirmation when you specify the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute by setting the SupportsShouldProcess keyword to `true`.</span></span>

- <span data-ttu-id="34579-108">コマンドレットの実行中に、次の例に示すように、「」というコマンドレット [を呼び出します](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 。</span><span class="sxs-lookup"><span data-stu-id="34579-108">Call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) during the execution of the cmdlet (as shown in the following example).</span></span>

<span data-ttu-id="34579-109">確認をサポートすることで、コマンドレットは、 `Confirm` `WhatIf` Windows PowerShell によって提供されるパラメーターとパラメーターを公開します。また、コマンドレットの開発ガイドラインにも適合します (コマンドレット開発ガイドラインの詳細については、「 [コマンドレット開発ガイドライン](./cmdlet-development-guidelines.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="34579-109">By supporting confirmation, a cmdlet exposes the `Confirm` and `WhatIf` parameters that are provided by Windows PowerShell, and also meets the development guidelines for cmdlets (For more information about cmdlet development guidelines, see [Cmdlet Development Guidelines](./cmdlet-development-guidelines.md).).</span></span>

## <a name="changing-the-system"></a><span data-ttu-id="34579-110">システムの変更</span><span class="sxs-lookup"><span data-stu-id="34579-110">Changing the System</span></span>

<span data-ttu-id="34579-111">"システムの変更" の動作は、Windows PowerShell の外部でシステムの状態を変更する可能性のあるすべてのコマンドレットを指します。</span><span class="sxs-lookup"><span data-stu-id="34579-111">The act of "changing the system" refers to any cmdlet that potentially changes the state of the system outside Windows PowerShell.</span></span> <span data-ttu-id="34579-112">たとえば、プロセスを停止したり、ユーザーアカウントを有効または無効にしたり、データベーステーブルに行を追加したりすると、システムに対するすべての変更が確認されます。</span><span class="sxs-lookup"><span data-stu-id="34579-112">For example, stopping a process, enabling or disabling a user account, or adding a row to a database table are all changes to the system that should be confirmed.</span></span>
<span data-ttu-id="34579-113">これに対して、データの読み取りまたは一時的な接続の確立を行う操作は、システムを変更するのではなく、通常は確認を必要としません。</span><span class="sxs-lookup"><span data-stu-id="34579-113">In contrast, operations that read data or establish transient connections do not change the system and generally do not require confirmation.</span></span> <span data-ttu-id="34579-114">また、などの Windows PowerShell ランタイム内で効果が制限されている操作についても、確認は必要ありません `set-variable` 。</span><span class="sxs-lookup"><span data-stu-id="34579-114">Confirmation is also not needed for actions whose effect is limited to inside the Windows PowerShell runtime, such as `set-variable`.</span></span> <span data-ttu-id="34579-115">永続的な変更を行う可能性があるかどうかにかかわらず、コマンドレットが永続的な変更を行う場合にのみ、変更を宣言して呼び出す必要があり `SupportsShouldProcess` [ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)</span><span class="sxs-lookup"><span data-stu-id="34579-115">Cmdlets that might or might not make a persistent change should declare `SupportsShouldProcess` and call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) only if they are about to make a persistent change.</span></span>

> [!NOTE]
> <span data-ttu-id="34579-116">"プロセスの確認" はコマンドレットにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="34579-116">ShouldProcess confirmation applies only to cmdlets.</span></span> <span data-ttu-id="34579-117">コマンドまたはスクリプトが、.NET のメソッドまたはプロパティを直接呼び出すか、Windows PowerShell の外部でアプリケーションを呼び出すことによって、システムの実行状態を変更した場合、この形式の確認は使用できません。</span><span class="sxs-lookup"><span data-stu-id="34579-117">If a command or script modifies the running state of a system by directly calling .NET methods or properties, or by calling applications outside of Windows PowerShell, this form of confirmation will not be available.</span></span>

## <a name="the-stopproc-cmdlet"></a><span data-ttu-id="34579-118">StopProc コマンドレット</span><span class="sxs-lookup"><span data-stu-id="34579-118">The StopProc Cmdlet</span></span>

<span data-ttu-id="34579-119">このトピックでは、Get-Proc コマンドレットを使用して取得したプロセスを停止しようとする Stop-Proc コマンドレットについて説明します (「 [最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)」で説明)。</span><span class="sxs-lookup"><span data-stu-id="34579-119">This topic describes a Stop-Proc cmdlet that attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="34579-120">コマンドレットの定義</span><span class="sxs-lookup"><span data-stu-id="34579-120">Defining the Cmdlet</span></span>

<span data-ttu-id="34579-121">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="34579-121">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="34579-122">システムを変更するためのコマンドレットを記述しているので、それに応じた名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="34579-122">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="34579-123">このコマンドレットはシステムプロセスを停止するため、ここで選択した動詞名は "Stop" で、 [Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) クラスで定義されます。これは、コマンドレットがプロセスを停止することを示す "Proc" という名詞です。</span><span class="sxs-lookup"><span data-stu-id="34579-123">This cmdlet stops system processes, so the verb name chosen here is "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate that the cmdlet stops processes.</span></span> <span data-ttu-id="34579-124">承認されたコマンドレット動詞の詳細については、「 [コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34579-124">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="34579-125">この Stop-Proc コマンドレットのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="34579-125">The following is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

<span data-ttu-id="34579-126">この[場合、](/dotnet/api/System.Management.Automation.CmdletAttribute)属性キーワードがに設定されていることに注意してください。これにより、このコマンドレットでは、.................................... コマンドレット `SupportsShouldProcess` `true` の[](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)呼び出しを行う[](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ことができます。</span><span class="sxs-lookup"><span data-stu-id="34579-126">Be aware that in the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration, the `SupportsShouldProcess` attribute keyword is set to `true` to enable the cmdlet to make calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>
<span data-ttu-id="34579-127">このキーワードが設定されていない場合、 `Confirm` および `WhatIf` パラメーターはユーザーが使用できません。</span><span class="sxs-lookup"><span data-stu-id="34579-127">Without this keyword set, the `Confirm` and `WhatIf` parameters will not be available to the user.</span></span>

### <a name="extremely-destructive-actions"></a><span data-ttu-id="34579-128">非常に破壊的操作</span><span class="sxs-lookup"><span data-stu-id="34579-128">Extremely Destructive Actions</span></span>

<span data-ttu-id="34579-129">操作の中には、アクティブなハードディスクパーティションの再フォーマットなど、非常に破壊的なものがあります。</span><span class="sxs-lookup"><span data-stu-id="34579-129">Some operations are extremely destructive, such as reformatting an active hard disk partition.</span></span> <span data-ttu-id="34579-130">このような場合は、コマンドレットを設定して、system.servicemodel 属性を `ConfirmImpact`  =  `ConfirmImpact.High` 宣言する[](/dotnet/api/System.Management.Automation.CmdletAttribute)必要があります。</span><span class="sxs-lookup"><span data-stu-id="34579-130">In these cases, the cmdlet should set `ConfirmImpact` = `ConfirmImpact.High` when declaring the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute.</span></span> <span data-ttu-id="34579-131">この設定により、ユーザーがパラメーターを指定していない場合でも、コマンドレットはユーザー確認を要求し `Confirm` ます。</span><span class="sxs-lookup"><span data-stu-id="34579-131">This setting forces the cmdlet to request user confirmation even when the user has not specified the `Confirm` parameter.</span></span> <span data-ttu-id="34579-132">ただし、コマンドレットの開発者は、 `ConfirmImpact` ユーザーアカウントの削除など、破壊的な可能性がある操作の乱用を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="34579-132">However, cmdlet developers should avoid overusing `ConfirmImpact` for operations that are just potentially destructive, such as deleting a user account.</span></span> <span data-ttu-id="34579-133">`ConfirmImpact`が " [System. Automation. confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact) 
 **high"** に設定されている場合は注意してください。</span><span class="sxs-lookup"><span data-stu-id="34579-133">Remember that if `ConfirmImpact` is set to [System.Management.Automation.ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact)
**High**.</span></span>

<span data-ttu-id="34579-134">同様に、一部の操作は破壊的になる可能性はほとんどありませんが、理論的には Windows PowerShell の外部でシステムの実行状態を変更します。</span><span class="sxs-lookup"><span data-stu-id="34579-134">Similarly, some operations are unlikely to be destructive, although they do in theory modify the running state of a system outside Windows PowerShell.</span></span> <span data-ttu-id="34579-135">このようなコマンドレットは `ConfirmImpact` 、 ["system.object"](/dotnet/api/system.management.automation.confirmimpact)に設定できます。</span><span class="sxs-lookup"><span data-stu-id="34579-135">Such cmdlets can set `ConfirmImpact` to [System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact).</span></span>
<span data-ttu-id="34579-136">これにより、ユーザーが中程度の影響と大きな影響を与える操作のみを確認するように求められた場合に、確認要求がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="34579-136">This will bypass confirmation requests where the user has asked to confirm only medium-impact and high-impact operations.</span></span>

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="34579-137">システム変更のパラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="34579-137">Defining Parameters for System Modification</span></span>

<span data-ttu-id="34579-138">このセクションでは、システムの変更をサポートするために必要なコマンドレットなど、コマンドレットのパラメーターの定義方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="34579-138">This section describes how to define the cmdlet parameters, including those that are needed to support system modification.</span></span> <span data-ttu-id="34579-139">パラメーターの定義に関する全般的な情報が必要な場合は、「 [コマンドライン入力を処理するパラメーターを追加](./adding-parameters-that-process-command-line-input.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34579-139">See [Adding Parameters that Process CommandLine Input](./adding-parameters-that-process-command-line-input.md) if you need general information about defining parameters.</span></span>

<span data-ttu-id="34579-140">Stop-Proc コマンドレットは、、、およびの3つのパラメーターを定義し `Name` `Force` `PassThru` ます。</span><span class="sxs-lookup"><span data-stu-id="34579-140">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span>

<span data-ttu-id="34579-141">パラメーターは、 `Name` `Name` プロセス入力オブジェクトのプロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="34579-141">The `Name` parameter corresponds to the `Name` property of the process input object.</span></span> <span data-ttu-id="34579-142">`Name`このサンプルのパラメーターは必須であることに注意してください。停止する名前付きプロセスがない場合、コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="34579-142">Be aware that the `Name` parameter in this sample is mandatory, as the cmdlet will fail if it does not have a named process to stop.</span></span>

<span data-ttu-id="34579-143">パラメーターを使用すると `Force` 、ユーザーは、システムの呼び出しをオーバーライドでき[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="34579-143">The `Force` parameter allows the user to override calls to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>
<span data-ttu-id="34579-144">実際には、を指定すると、コマンドレットによって、が指定されたときに、コマンドレットによって、その呼び出しがスキップされ、操作が続行されるように、パラメーターが設定されて[いる必要があります](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) `Force` `Force` [。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="34579-144">In fact, any cmdlet that calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) should have a `Force` parameter so that when `Force` is specified, the cmdlet skips the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) and proceeds with the operation.</span></span> <span data-ttu-id="34579-145">これは、 [システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の呼び出しには影響しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="34579-145">Be aware that this does not affect calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span></span>

<span data-ttu-id="34579-146">`PassThru`パラメーターを使用すると、コマンドレットがパイプライン (この場合はプロセスが停止した後) を介して出力オブジェクトを渡すかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="34579-146">The `PassThru` parameter allows the user to indicate whether the cmdlet passes an output object through the pipeline, in this case, after a process is stopped.</span></span> <span data-ttu-id="34579-147">このパラメーターは、入力オブジェクトのプロパティではなく、コマンドレット自体に関連付けられていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="34579-147">Be aware that this parameter is tied to the cmdlet itself instead of to a property of the input object.</span></span>

<span data-ttu-id="34579-148">Stop-Proc コマンドレットのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="34579-148">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="34579-149">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="34579-149">Overriding an Input Processing Method</span></span>

<span data-ttu-id="34579-150">コマンドレットでは、入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34579-150">The cmdlet must override an input processing method.</span></span> <span data-ttu-id="34579-151">次のコードは、サンプルの Stop-Proc コマンドレットで使用される、system.servicemodel [レコード](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) のオーバーライドを示しています。</span><span class="sxs-lookup"><span data-stu-id="34579-151">The following code illustrates the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override used in the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="34579-152">このメソッドは、要求されたプロセス名ごとに、プロセスが特別なプロセスではないことを確認し、そのプロセスを停止して、パラメーターが指定されている場合は出力オブジェクトを送信し `PassThru` ます。</span><span class="sxs-lookup"><span data-stu-id="34579-152">For each requested process name, this method ensures that the process is not a special process, tries to stop the process, and then sends an output object if the `PassThru` parameter is specified.</span></span>

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

## <a name="calling-the-shouldprocess-method"></a><span data-ttu-id="34579-153">メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="34579-153">Calling the ShouldProcess Method</span></span>

<span data-ttu-id="34579-154">コマンドレットの入力処理方法では、変更 (ファイルの削除など) がシステムの実行状態になる前に、操作の実行を確認するために、 [system.string メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="34579-154">The input processing method of your cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to confirm execution of an operation before a change (for example, deleting files) is made to the running state of the system.</span></span> <span data-ttu-id="34579-155">これにより、Windows PowerShell ランタイムはシェル内で適切な "WhatIf" および "Confirm" 動作を提供できます。</span><span class="sxs-lookup"><span data-stu-id="34579-155">This allows the Windows PowerShell runtime to supply the correct "WhatIf" and "Confirm" behavior within the shell.</span></span>

> [!NOTE]
> <span data-ttu-id="34579-156">コマンドレットによって処理される必要があることが示され、 [システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) の呼び出しに失敗した場合は、ユーザーがシステムを予期せず変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34579-156">If a cmdlet states that it supports should process and fails to make the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call, the user might modify the system unexpectedly.</span></span>

<span data-ttu-id="34579-157">この呼び出しは、変更するリソースの名前をユーザーに送信し [ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) Windows PowerShell ランタイムは、ユーザーに表示される内容を決定する際に、コマンドライン設定またはユーザー設定変数を考慮しています。</span><span class="sxs-lookup"><span data-stu-id="34579-157">The call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command-line settings or preference variables in determining what should be displayed to the user.</span></span>

<span data-ttu-id="34579-158">次の例では、サンプルの Stop-Proc コマンドレットで、 [system](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) ..................................................... [...](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)</span><span class="sxs-lookup"><span data-stu-id="34579-158">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="34579-159">"メソッドの続行" メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="34579-159">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="34579-160">システムの呼び出しによって、ユーザーにセカンダリメッセージが送信されるように [なり](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) ます。</span><span class="sxs-lookup"><span data-stu-id="34579-160">The call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method sends a secondary message to the user.</span></span> <span data-ttu-id="34579-161">この呼び出しは、system.object の呼び出しが [返された後に行わ](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) れ、 `true` パラメーターが `Force` に設定されていない場合 `true` はになります。</span><span class="sxs-lookup"><span data-stu-id="34579-161">This call is made after the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) returns `true` and if the `Force` parameter was not set to `true`.</span></span> <span data-ttu-id="34579-162">ユーザーは、操作を続行する必要があるかどうかを伝えるフィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="34579-162">The user can then provide feedback to say whether the operation should be continued.</span></span> <span data-ttu-id="34579-163">コマンドレットでは、system.object を呼び出し [ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 危険性の高いシステム変更については、追加のチェックとして続行するか、すべてのオプションをユーザーに提供する必要があるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="34579-163">Your cmdlet calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) as an additional check for potentially dangerous system modifications or when you want to provide yes-to-all and no-to-all options to the user.</span></span>

<span data-ttu-id="34579-164">次の例では、例の Stop-Proc コマンドレットを使用 [し](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) て [、system.](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .................................................</span><span class="sxs-lookup"><span data-stu-id="34579-164">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

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

## <a name="stopping-input-processing"></a><span data-ttu-id="34579-165">入力処理の停止</span><span class="sxs-lookup"><span data-stu-id="34579-165">Stopping Input Processing</span></span>

<span data-ttu-id="34579-166">システムの変更を行うコマンドレットの入力処理メソッドでは、入力の処理を停止する方法が提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="34579-166">The input processing method of a cmdlet that makes system modifications must provide a way of stopping the processing of input.</span></span> <span data-ttu-id="34579-167">この Stop-Proc コマンドレットの場合は、 [system](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) [..](/dotnet/api/System.Diagnostics.Process.Kill) .......................................................</span><span class="sxs-lookup"><span data-stu-id="34579-167">In the case of this Stop-Proc cmdlet, a call is made from the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to the [System.Diagnostics.Process.Kill\*](/dotnet/api/System.Diagnostics.Process.Kill) method.</span></span> <span data-ttu-id="34579-168">`PassThru`パラメーターがに設定されているので `true` 、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)も呼び出されて、プロセスオブジェクトがパイプラインに送信されるように[](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)なっています。</span><span class="sxs-lookup"><span data-stu-id="34579-168">Because the `PassThru` parameter is set to `true`, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) also calls [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) to send the process object to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="34579-169">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="34579-169">Code Sample</span></span>

<span data-ttu-id="34579-170">完全な C# サンプルコードについては、「 [StopProcessSample01 sample](./stopprocesssample01-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34579-170">For the complete C# sample code, see [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="34579-171">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="34579-171">Defining Object Types and Formatting</span></span>

<span data-ttu-id="34579-172">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="34579-172">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="34579-173">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="34579-173">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="34579-174">新しい型を定義する、または既存の型を拡張する方法の詳細については、「 [オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34579-174">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="34579-175">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="34579-175">Building the Cmdlet</span></span>

<span data-ttu-id="34579-176">コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34579-176">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="34579-177">コマンドレットの登録の詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34579-177">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="34579-178">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="34579-178">Testing the Cmdlet</span></span>

<span data-ttu-id="34579-179">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="34579-179">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="34579-180">ここでは、Stop-Proc コマンドレットをテストするいくつかのテストについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34579-180">Here are several tests that test the Stop-Proc cmdlet.</span></span> <span data-ttu-id="34579-181">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34579-181">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="34579-182">次に示すように、Windows PowerShell を起動し、Stop-Proc コマンドレットを使用して処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="34579-182">Start Windows PowerShell and use the Stop-Proc cmdlet to stop processing as shown below.</span></span> <span data-ttu-id="34579-183">コマンドレットではパラメーターを必須と指定しているので、 `Name` コマンドレットはパラメーターを照会します。</span><span class="sxs-lookup"><span data-stu-id="34579-183">Because the cmdlet specifies the `Name` parameter as mandatory, the cmdlet queries for the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

    <span data-ttu-id="34579-184">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34579-184">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- <span data-ttu-id="34579-185">次に、コマンドレットを使用して、"NOTEPAD" という名前のプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="34579-185">Now let's use the cmdlet to stop the process named "NOTEPAD".</span></span> <span data-ttu-id="34579-186">コマンドレットでは、操作を確認するように求められます。</span><span class="sxs-lookup"><span data-stu-id="34579-186">The cmdlet asks you to confirm the action.</span></span>

    ```powershell
    PS> stop-proc -Name notepad
    ```

    <span data-ttu-id="34579-187">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34579-187">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="34579-188">以下に示すように Stop-Proc を使用して、"WINLOGON" という名前の重要なプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="34579-188">Use Stop-Proc as shown to stop the critical process named "WINLOGON".</span></span> <span data-ttu-id="34579-189">オペレーティングシステムが再起動されるため、この操作の実行についての警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34579-189">You are prompted and warned about performing this action because it will cause the operating system to reboot.</span></span>

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

    <span data-ttu-id="34579-190">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34579-190">The following output appears.</span></span>

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- <span data-ttu-id="34579-191">ここで、警告を受信せずに WINLOGON プロセスを停止してみましょう。</span><span class="sxs-lookup"><span data-stu-id="34579-191">Let's now try to stop the WINLOGON process without receiving a warning.</span></span> <span data-ttu-id="34579-192">このコマンドの入力では、パラメーターを使用して警告を上書きすることに注意 `Force` してください。</span><span class="sxs-lookup"><span data-stu-id="34579-192">Be aware that this command entry uses the `Force` parameter to override the warning.</span></span>

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

    <span data-ttu-id="34579-193">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34579-193">The following output appears.</span></span>

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="34579-194">参照</span><span class="sxs-lookup"><span data-stu-id="34579-194">See Also</span></span>

[<span data-ttu-id="34579-195">Command-Line 入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="34579-195">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

<span data-ttu-id="34579-196">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="34579-196">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="34579-197">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="34579-197">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="34579-198">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="34579-198">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="34579-199">コマンドレット サンプル</span><span class="sxs-lookup"><span data-stu-id="34579-199">Cmdlet Samples</span></span>](./cmdlet-samples.md)

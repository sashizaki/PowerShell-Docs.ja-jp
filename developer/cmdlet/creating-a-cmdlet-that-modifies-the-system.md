---
title: システムを変更するコマンドレットを作成する |Microsoft Docs
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
ms.sourcegitcommit: f60fa420bdc81db174e6168d3aeb11371e483162
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "67301399"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a><span data-ttu-id="068d6-102">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="068d6-102">Creating a Cmdlet that Modifies the System</span></span>

<span data-ttu-id="068d6-103">場合によってコマンドレットは、Windows PowerShell ランタイムの状態だけでなく、システムの実行中の状態を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="068d6-103">Sometimes a cmdlet must modify the running state of the system, not just the state of the Windows PowerShell runtime.</span></span> <span data-ttu-id="068d6-104">このような場合は、コマンドレットは、する必要がある、ユーザー、変更するかどうかを確認する機会が。</span><span class="sxs-lookup"><span data-stu-id="068d6-104">In these cases, the cmdlet should allow the user a chance to confirm whether or not to make the change.</span></span>

<span data-ttu-id="068d6-105">確認をサポートするには、コマンドレットは、2 つの処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="068d6-105">To support confirmation a cmdlet must do two things.</span></span>

- <span data-ttu-id="068d6-106">宣言を指定する場合は、コマンドレットが確認をサポートしている、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)属性 SupportsShouldProcess キーワードを設定して`true`します。</span><span class="sxs-lookup"><span data-stu-id="068d6-106">Declare that the cmdlet supports confirmation when you specify the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute by setting the SupportsShouldProcess keyword to `true`.</span></span>

- <span data-ttu-id="068d6-107">呼び出す[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) (次の例で説明) とコマンドレットの実行中にします。</span><span class="sxs-lookup"><span data-stu-id="068d6-107">Call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) during the execution of the cmdlet (as shown in the following example).</span></span>

<span data-ttu-id="068d6-108">コマンドレットを公開の確認をサポートすることによって、`Confirm`と`WhatIf`は、Windows PowerShell によって提供され、コマンドレットの開発のガイドラインにも対応するパラメーター (コマンドレットの開発のガイドラインの詳細についてを参照してください[コマンドレットの開発ガイドライン](./cmdlet-development-guidelines.md)。)。</span><span class="sxs-lookup"><span data-stu-id="068d6-108">By supporting confirmation, a cmdlet exposes the `Confirm` and `WhatIf` parameters that are provided by Windows PowerShell, and also meets the development guidelines for cmdlets (For more information about cmdlet development guidelines, see [Cmdlet Development Guidelines](./cmdlet-development-guidelines.md).).</span></span>

## <a name="changing-the-system"></a><span data-ttu-id="068d6-109">システムを変更します。</span><span class="sxs-lookup"><span data-stu-id="068d6-109">Changing the System</span></span>

<span data-ttu-id="068d6-110">「システムの変更」の動作は、Windows PowerShell の外部システムの状態を変更する可能性のあるすべてのコマンドレットを参照します。</span><span class="sxs-lookup"><span data-stu-id="068d6-110">The act of "changing the system" refers to any cmdlet that potentially changes the state of the system outside Windows PowerShell.</span></span> <span data-ttu-id="068d6-111">たとえば、プロセスを有効にするか、ユーザー アカウントを無効にするまたはデータベース テーブルに行がすべての変更を確認する必要がありますシステムの追加を停止しています。</span><span class="sxs-lookup"><span data-stu-id="068d6-111">For example, stopping a process, enabling or disabling a user account, or adding a row to a database table are all changes to the system that should be confirmed.</span></span> <span data-ttu-id="068d6-112">これに対し、データの読み取り、一時的な接続を確立したりする操作を使用して、システムは変更されず、一般に、確認を要求されません。</span><span class="sxs-lookup"><span data-stu-id="068d6-112">In contrast, operations that read data or establish transient connections do not change the system and generally do not require confirmation.</span></span> <span data-ttu-id="068d6-113">アクションが影響を制限する、Windows PowerShell ランタイム内でなどの 確認は必要ありませんも`set-variable`します。</span><span class="sxs-lookup"><span data-stu-id="068d6-113">Confirmation is also not needed for actions whose effect is limited to inside the Windows PowerShell runtime, such as `set-variable`.</span></span> <span data-ttu-id="068d6-114">可能性がある永続的な変更を加える可能性がありますいないコマンドレットを宣言する必要があります`SupportsShouldProcess`を呼び出すと[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)永続的な変更を加えるしようとしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="068d6-114">Cmdlets that might or might not make a persistent change should declare `SupportsShouldProcess` and call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) only if they are about to make a persistent change.</span></span>

> [!NOTE]
> <span data-ttu-id="068d6-115">ShouldProcess 確認は、コマンドレットにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="068d6-115">ShouldProcess confirmation applies only to cmdlets.</span></span> <span data-ttu-id="068d6-116">コマンドまたはスクリプトは、.NET メソッドまたはプロパティを直接呼び出すことによって、または Windows PowerShell の外部で呼び出し元のアプリケーション、システムの実行中の状態を変更します、この形式の確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="068d6-116">If a command or script modifies the running state of a system by directly calling .NET methods or properties, or by calling applications outside of Windows PowerShell, this form of confirmation will not be available.</span></span>

## <a name="the-stopproc-cmdlet"></a><span data-ttu-id="068d6-117">StopProc コマンドレット</span><span class="sxs-lookup"><span data-stu-id="068d6-117">The StopProc Cmdlet</span></span>

<span data-ttu-id="068d6-118">このトピックでは Get-proc コマンドレットを使用して取得するプロセスを停止しようとする停止 Proc コマンドレットの説明 (で説明されている[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md))。</span><span class="sxs-lookup"><span data-stu-id="068d6-118">This topic describes a Stop-Proc cmdlet that attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="068d6-119">コマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="068d6-119">Defining the Cmdlet</span></span>

<span data-ttu-id="068d6-120">コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="068d6-120">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="068d6-121">システムを変更するコマンドレットを記述するため、それに応じて名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="068d6-121">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="068d6-122">このコマンドレットが停止システム プロセス、ため、ここで選択した動詞名が"Stop"がによって定義された、 [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスの名詞コマンドレットは、プロセスを停止することを示すには、"Proc"とします。</span><span class="sxs-lookup"><span data-stu-id="068d6-122">This cmdlet stops system processes, so the verb name chosen here is "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate that the cmdlet stops processes.</span></span> <span data-ttu-id="068d6-123">承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="068d6-123">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="068d6-124">この停止 Proc コマンドレットのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="068d6-124">The following is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

<span data-ttu-id="068d6-125">注意してくださいで、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)宣言、`SupportsShouldProcess`属性のキーワードに設定されている`true`に呼び出しを実行するコマンドレットを有効にする[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)します。</span><span class="sxs-lookup"><span data-stu-id="068d6-125">Be aware that in the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration, the `SupportsShouldProcess` attribute keyword is set to `true` to enable the cmdlet to make calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span> <span data-ttu-id="068d6-126">このキーワードを設定することがなく、`Confirm`と`WhatIf`パラメーターは、ユーザーには使用できません。</span><span class="sxs-lookup"><span data-stu-id="068d6-126">Without this keyword set, the `Confirm` and `WhatIf` parameters will not be available to the user.</span></span>

### <a name="extremely-destructive-actions"></a><span data-ttu-id="068d6-127">非常に破壊的な操作</span><span class="sxs-lookup"><span data-stu-id="068d6-127">Extremely Destructive Actions</span></span>

<span data-ttu-id="068d6-128">一部の操作は、アクティブなハード ディスク パーティションを再フォーマットなどの非常に破壊的なです。</span><span class="sxs-lookup"><span data-stu-id="068d6-128">Some operations are extremely destructive, such as reformatting an active hard disk partition.</span></span> <span data-ttu-id="068d6-129">このような場合は、コマンドレットを設定する必要があります`ConfirmImpact`  =  `ConfirmImpact.High`を宣言するとき、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="068d6-129">In these cases, the cmdlet should set `ConfirmImpact` = `ConfirmImpact.High` when declaring the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute.</span></span> <span data-ttu-id="068d6-130">この設定では、ユーザーが指定されていない場合でも要求をユーザーが確認するコマンドレットを強制、`Confirm`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="068d6-130">This setting forces the cmdlet to request user confirmation even when the user has not specified the `Confirm` parameter.</span></span> <span data-ttu-id="068d6-131">ただし、コマンドレットの開発者が過剰な使用を回避する必要があります`ConfirmImpact`のユーザー アカウントを削除するなど、だけ可能性がある破壊的な操作の場合。</span><span class="sxs-lookup"><span data-stu-id="068d6-131">However, cmdlet developers should avoid overusing `ConfirmImpact` for operations that are just potentially destructive, such as deleting a user account.</span></span> <span data-ttu-id="068d6-132">ある`ConfirmImpact`に設定されている[System.Management.Automation.ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **高**します。</span><span class="sxs-lookup"><span data-stu-id="068d6-132">Remember that if `ConfirmImpact` is set to [System.Management.Automation.ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact) **High**.</span></span>

<span data-ttu-id="068d6-133">同様に、いくつかの操作は、これらは理論的に変更が Windows PowerShell の外部システムの実行中の状態を破壊する可能性がありますではありません。</span><span class="sxs-lookup"><span data-stu-id="068d6-133">Similarly, some operations are unlikely to be destructive, although they do in theory modify the running state of a system outside Windows PowerShell.</span></span> <span data-ttu-id="068d6-134">このようなコマンドレットを設定できます`ConfirmImpact`に[System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0)します。</span><span class="sxs-lookup"><span data-stu-id="068d6-134">Such cmdlets can set `ConfirmImpact` to [System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact?view=powershellsdk-1.1.0).</span></span> <span data-ttu-id="068d6-135">これにより、確認要求が、ユーザーがメディアへの影響と、影響の大きいだけの操作を確認する要求されましたが省略されます。</span><span class="sxs-lookup"><span data-stu-id="068d6-135">This will bypass confirmation requests where the user has asked to confirm only medium-impact and high-impact operations.</span></span>

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="068d6-136">システムの変更のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="068d6-136">Defining Parameters for System Modification</span></span>

<span data-ttu-id="068d6-137">このセクションでは、サポート システムの変更に必要なものも含め、このコマンドレットのパラメーターを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="068d6-137">This section describes how to define the cmdlet parameters, including those that are needed to support system modification.</span></span> <span data-ttu-id="068d6-138">参照してください[そのプロセスのコマンドラインの入力パラメーターを追加する](./adding-parameters-that-process-command-line-input.md)パラメーターの定義に関する一般的な情報が必要な場合。</span><span class="sxs-lookup"><span data-stu-id="068d6-138">See [Adding Parameters that Process CommandLine Input](./adding-parameters-that-process-command-line-input.md) if you need general information about defining parameters.</span></span>

<span data-ttu-id="068d6-139">停止 Proc コマンドレットは、3 つのパラメーターを定義します。 `Name`、 `Force`、および`PassThru`します。</span><span class="sxs-lookup"><span data-stu-id="068d6-139">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span>

<span data-ttu-id="068d6-140">`Name`パラメーターに対応、`Name`プロセスの入力オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="068d6-140">The `Name` parameter corresponds to the `Name` property of the process input object.</span></span> <span data-ttu-id="068d6-141">注意を`Name`を停止する名前付きプロセスがあるない場合、コマンドレットが失敗すると、このサンプルではパラメーターが必須では。</span><span class="sxs-lookup"><span data-stu-id="068d6-141">Be aware that the `Name` parameter in this sample is mandatory, as the cmdlet will fail if it does not have a named process to stop.</span></span>

<span data-ttu-id="068d6-142">`Force`パラメーターにより、ユーザーへの呼び出しをオーバーライドする[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)します。</span><span class="sxs-lookup"><span data-stu-id="068d6-142">The `Force` parameter allows the user to override calls to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span> <span data-ttu-id="068d6-143">実際には、いずれかのコマンドレットを呼び出す[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)する必要がありますが、`Force`パラメーターようにとき`Force`を指定すると、コマンドレットの呼び出しをスキップします[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)操作を続行します。</span><span class="sxs-lookup"><span data-stu-id="068d6-143">In fact, any cmdlet that calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) should have a `Force` parameter so that when `Force` is specified, the cmdlet skips the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) and proceeds with the operation.</span></span> <span data-ttu-id="068d6-144">この影響を及ぼさないようにへの呼び出しに注意してください[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)します。</span><span class="sxs-lookup"><span data-stu-id="068d6-144">Be aware that this does not affect calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span></span>

<span data-ttu-id="068d6-145">`PassThru`パラメーターを示すかどうか、コマンドレット オブジェクトを渡します出力、パイプラインを介してこの場合、プロセスが停止したら、ユーザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="068d6-145">The `PassThru` parameter allows the user to indicate whether the cmdlet passes an output object through the pipeline, in this case, after a process is stopped.</span></span> <span data-ttu-id="068d6-146">このパラメーターが、入力オブジェクトのプロパティに自体の代わりにコマンドレットに関連付けられていることに注意します。</span><span class="sxs-lookup"><span data-stu-id="068d6-146">Be aware that this parameter is tied to the cmdlet itself instead of to a property of the input object.</span></span>

<span data-ttu-id="068d6-147">停止 Proc コマンドレットのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="068d6-147">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="068d6-148">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="068d6-148">Overriding an Input Processing Method</span></span>

<span data-ttu-id="068d6-149">コマンドレットは、入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="068d6-149">The cmdlet must override an input processing method.</span></span> <span data-ttu-id="068d6-150">次のコードは、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)上書きサンプル停止 Proc コマンドレットで使用します。</span><span class="sxs-lookup"><span data-stu-id="068d6-150">The following code illustrates the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override used in the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="068d6-151">プロセス名を要求された各のこのメソッドにより、こと、プロセスは特殊なプロセスではありません、プロセスを停止しようとする場合に出力オブジェクトを送信、`PassThru`パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="068d6-151">For each requested process name, this method ensures that the process is not a special process, tries to stop the process, and then sends an output object if the `PassThru` parameter is specified.</span></span>

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

## <a name="calling-the-shouldprocess-method"></a><span data-ttu-id="068d6-152">ShouldProcess メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="068d6-152">Calling the ShouldProcess Method</span></span>

<span data-ttu-id="068d6-153">入力処理、コマンドレットのメソッドを呼び出す必要があります、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドが実行状態を変更 (たとえば、ファイルの削除) が行われる前に、操作の実行を確認するにはシステムです。</span><span class="sxs-lookup"><span data-stu-id="068d6-153">The input processing method of your cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to confirm execution of an operation before a change (for example, deleting files) is made to the running state of the system.</span></span> <span data-ttu-id="068d6-154">これにより、シェル内で正しい"WhatIf"と「確認」の動作を指定する Windows PowerShell ランタイムです。</span><span class="sxs-lookup"><span data-stu-id="068d6-154">This allows the Windows PowerShell runtime to supply the correct "WhatIf" and "Confirm" behavior within the shell.</span></span>

> [!NOTE]
> <span data-ttu-id="068d6-155">処理する必要がありに失敗したコマンドレットの状態をサポートしている場合、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を呼び出すには、ユーザーは、システムを予期せず変更可能性があります。</span><span class="sxs-lookup"><span data-stu-id="068d6-155">If a cmdlet states that it supports should process and fails to make the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call, the user might modify the system unexpectedly.</span></span>

<span data-ttu-id="068d6-156">呼び出し[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)コマンドライン設定やユーザー設定変数を考慮して、Windows PowerShell ランタイムで、ユーザーに変更するリソースの名前を送信します。何をユーザーに表示するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="068d6-156">The call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command-line settings or preference variables in determining what should be displayed to the user.</span></span>

<span data-ttu-id="068d6-157">次の例では、呼び出し[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)のオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)サンプル メソッド停止 Proc コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="068d6-157">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="068d6-158">ShouldContinue メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="068d6-158">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="068d6-159">呼び出し、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドは、ユーザーにセカンダリのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="068d6-159">The call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method sends a secondary message to the user.</span></span> <span data-ttu-id="068d6-160">呼び出しの後にこの呼び出しが行われた[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)返します`true`場合に、`Force`にパラメーターが設定されませんでした`true`します。</span><span class="sxs-lookup"><span data-stu-id="068d6-160">This call is made after the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) returns `true` and if the `Force` parameter was not set to `true`.</span></span> <span data-ttu-id="068d6-161">ユーザーは、操作を続行するかどうかにフィードバックを提供し、できます。</span><span class="sxs-lookup"><span data-stu-id="068d6-161">The user can then provide feedback to say whether the operation should be continued.</span></span> <span data-ttu-id="068d6-162">コマンドレットの呼び出し[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)危険性のあるシステムの変更、ユーザーに [はい] ですべてとなしですべてのオプションを提供する場合、追加のチェックとして。</span><span class="sxs-lookup"><span data-stu-id="068d6-162">Your cmdlet calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) as an additional check for potentially dangerous system modifications or when you want to provide yes-to-all and no-to-all options to the user.</span></span>

<span data-ttu-id="068d6-163">次の例では、呼び出し[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)のオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)サンプル メソッド停止 Proc コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="068d6-163">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

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

## <a name="stopping-input-processing"></a><span data-ttu-id="068d6-164">入力の処理を停止しています</span><span class="sxs-lookup"><span data-stu-id="068d6-164">Stopping Input Processing</span></span>

<span data-ttu-id="068d6-165">入力システムの変更は、コマンドレットのメソッドの処理には、入力の処理を停止する方法を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="068d6-165">The input processing method of a cmdlet that makes system modifications must provide a way of stopping the processing of input.</span></span> <span data-ttu-id="068d6-166">この停止 Proc コマンドレットの呼び出しが行われます、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドを[System.Diagnostics.Process.Kill\*](/dotnet/api/System.Diagnostics.Process.Kill)メソッド。</span><span class="sxs-lookup"><span data-stu-id="068d6-166">In the case of this Stop-Proc cmdlet, a call is made from the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to the [System.Diagnostics.Process.Kill\*](/dotnet/api/System.Diagnostics.Process.Kill) method.</span></span> <span data-ttu-id="068d6-167">`PassThru`にパラメーターが設定されている`true`、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)も呼び出して[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)を送信するにはパイプラインにプロセス オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="068d6-167">Because the `PassThru` parameter is set to `true`, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) also calls [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) to send the process object to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="068d6-168">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="068d6-168">Code Sample</span></span>

<span data-ttu-id="068d6-169">完全なC#サンプル コードは、「 [StopProcessSample01 サンプル](./stopprocesssample01-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="068d6-169">For the complete C# sample code, see [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="068d6-170">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="068d6-170">Defining Object Types and Formatting</span></span>

<span data-ttu-id="068d6-171">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="068d6-171">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="068d6-172">その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="068d6-172">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="068d6-173">新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](/previous-versions//ms714665(v=vs.85))します。</span><span class="sxs-lookup"><span data-stu-id="068d6-173">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="068d6-174">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="068d6-174">Building the Cmdlet</span></span>

<span data-ttu-id="068d6-175">コマンドレットを実装するには、後にする必要があります登録する必要が Windows PowerShell を使用した Windows PowerShell スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="068d6-175">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="068d6-176">コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](/previous-versions//ms714644(v=vs.85))します。</span><span class="sxs-lookup"><span data-stu-id="068d6-176">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="068d6-177">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="068d6-177">Testing the Cmdlet</span></span>

<span data-ttu-id="068d6-178">コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="068d6-178">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="068d6-179">ここでは、停止 Proc コマンドレットをテストするいくつかのテストです。</span><span class="sxs-lookup"><span data-stu-id="068d6-179">Here are several tests that test the Stop-Proc cmdlet.</span></span> <span data-ttu-id="068d6-180">詳細については、コマンドラインからコマンドレットを使用して、次を参照してください。、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="068d6-180">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="068d6-181">Windows PowerShell を起動し、停止 Proc コマンドレットを使用して、次に示すように処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="068d6-181">Start Windows PowerShell and use the Stop-Proc cmdlet to stop processing as shown below.</span></span> <span data-ttu-id="068d6-182">コマンドレットは、指定されているので、`Name`として必須パラメーターでは、コマンドレットのクエリ パラメーター。</span><span class="sxs-lookup"><span data-stu-id="068d6-182">Because the cmdlet specifies the `Name` parameter as mandatory, the cmdlet queries for the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

<span data-ttu-id="068d6-183">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="068d6-183">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- <span data-ttu-id="068d6-184">ここで"NOTEPAD"という名前のプロセスを停止するコマンドレットを使用してみましょう。</span><span class="sxs-lookup"><span data-stu-id="068d6-184">Now let's use the cmdlet to stop the process named "NOTEPAD".</span></span> <span data-ttu-id="068d6-185">コマンドレットでは、アクションの確認が求められます。</span><span class="sxs-lookup"><span data-stu-id="068d6-185">The cmdlet asks you to confirm the action.</span></span>

    ```powershell
    PS> stop-proc -Name notepad
    ```

<span data-ttu-id="068d6-186">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="068d6-186">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="068d6-187">"WINLOGON"という名前の重要なプロセスを停止するよう停止プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="068d6-187">Use Stop-Proc as shown to stop the critical process named "WINLOGON".</span></span> <span data-ttu-id="068d6-188">メッセージが表示され、オペレーティング システムの再起動が発生するために、このアクションを実行する警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="068d6-188">You are prompted and warned about performing this action because it will cause the operating system to reboot.</span></span>

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

<span data-ttu-id="068d6-189">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="068d6-189">The following output appears.</span></span>

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- <span data-ttu-id="068d6-190">警告を表示せず、WINLOGON プロセスを停止するようになりました試してみましょう。</span><span class="sxs-lookup"><span data-stu-id="068d6-190">Let's now try to stop the WINLOGON process without receiving a warning.</span></span> <span data-ttu-id="068d6-191">このコマンドの入力が使用することに注意してください、`Force`パラメーターを警告を無視します。</span><span class="sxs-lookup"><span data-stu-id="068d6-191">Be aware that this command entry uses the `Force` parameter to override the warning.</span></span>

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

<span data-ttu-id="068d6-192">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="068d6-192">The following output appears.</span></span>

    ```output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="068d6-193">参照</span><span class="sxs-lookup"><span data-stu-id="068d6-193">See Also</span></span>

[<span data-ttu-id="068d6-194">コマンドライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="068d6-194">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

<span data-ttu-id="068d6-195">[オブジェクトの種類を拡張して、書式設定](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="068d6-195">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="068d6-196">[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="068d6-196">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="068d6-197">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="068d6-197">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="068d6-198">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="068d6-198">Cmdlet Samples</span></span>](./cmdlet-samples.md)
---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレットにユーザー メッセージを追加する
description: コマンドレットにユーザー メッセージを追加する
ms.openlocfilehash: de6fcc093af1d01287eed1eb8cc7b81cf5d2fdd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668339"
---
# <a name="adding-user-messages-to-your-cmdlet"></a><span data-ttu-id="3aeeb-103">コマンドレットにユーザー メッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="3aeeb-103">Adding User Messages to Your Cmdlet</span></span>

<span data-ttu-id="3aeeb-104">コマンドレットでは、Windows PowerShell ランタイムによってユーザーに表示できるいくつかの種類のメッセージを書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-104">Cmdlets can write several kinds of messages that can be displayed to the user by the Windows PowerShell runtime.</span></span> <span data-ttu-id="3aeeb-105">これらのメッセージには、次の種類があります。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-105">These messages include the following types:</span></span>

- <span data-ttu-id="3aeeb-106">一般的なユーザー情報を含む詳細なメッセージ。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-106">Verbose messages that contain general user information.</span></span>

- <span data-ttu-id="3aeeb-107">トラブルシューティング情報を含むメッセージをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-107">Debug messages that contain troubleshooting information.</span></span>

- <span data-ttu-id="3aeeb-108">コマンドレットが予期しない結果になる可能性のある操作を実行しようとしていることを示す通知を含む警告メッセージ。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-108">Warning messages that contain a notification that the cmdlet is about to perform an operation that can have unexpected results.</span></span>

- <span data-ttu-id="3aeeb-109">実行時間が長い操作を実行するときにコマンドレットが完了した作業量に関する情報を含む進行状況レポートメッセージ。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-109">Progress report messages that contain information about how much work the cmdlet has completed when performing an operation that takes a long time.</span></span>

<span data-ttu-id="3aeeb-110">コマンドレットで書き込むことができるメッセージの数や、コマンドレットが書き込むメッセージの種類に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-110">There are no limits to the number of messages that your cmdlet can write or the type of messages that your cmdlet writes.</span></span> <span data-ttu-id="3aeeb-111">各メッセージは、コマンドレットの入力処理メソッド内から特定の呼び出しを行うことによって書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-111">Each message is written by making a specific call from within the input processing method of your cmdlet.</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="3aeeb-112">コマンドレットの定義</span><span class="sxs-lookup"><span data-stu-id="3aeeb-112">Defining the Cmdlet</span></span>

<span data-ttu-id="3aeeb-113">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-113">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="3aeeb-114">任意の種類のコマンドレットは、入力処理メソッドからユーザー通知を書き込むことができます。そのため、一般に、このコマンドレットには、コマンドレットで実行されるシステム変更を示す動詞を使用して名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-114">Any sort of cmdlet can write user notifications from its input processing methods; so, in general, you can name this cmdlet using any verb that indicates what system modifications the cmdlet performs.</span></span> <span data-ttu-id="3aeeb-115">承認されたコマンドレット動詞の詳細については、「 [コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-115">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="3aeeb-116">Stop-Proc コマンドレットは、システムを変更するように設計されています。したがって、.NET クラスの[system.string 宣言には、](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute キーワードを含め、をに設定する必要があり `SupportsShouldProcess` ます。 `true`</span><span class="sxs-lookup"><span data-stu-id="3aeeb-116">The Stop-Proc cmdlet is designed to modify the system; therefore, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration for the .NET class must include the `SupportsShouldProcess` attribute keyword and be set to `true`.</span></span>

<span data-ttu-id="3aeeb-117">次のコードは、この Stop-Proc コマンドレットクラスの定義です。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-117">The following code is the definition for this Stop-Proc cmdlet class.</span></span> <span data-ttu-id="3aeeb-118">この定義の詳細については、「 [システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-118">For more information about this definition, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="3aeeb-119">システム変更のパラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="3aeeb-119">Defining Parameters for System Modification</span></span>

<span data-ttu-id="3aeeb-120">Stop-Proc コマンドレットは、、、およびの3つのパラメーターを定義し `Name` `Force` `PassThru` ます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-120">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span> <span data-ttu-id="3aeeb-121">これらのパラメーターの定義の詳細については、「 [システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-121">For more information about defining these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

<span data-ttu-id="3aeeb-122">Stop-Proc コマンドレットのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-122">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="3aeeb-123">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="3aeeb-123">Overriding an Input Processing Method</span></span>

<span data-ttu-id="3aeeb-124">コマンドレットは、入力処理メソッドをオーバーライドする必要があります。ほとんどの場合、この [コマンドレットは](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、system.object を変更します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-124">Your cmdlet must override an input processing method, most often it will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="3aeeb-125">この Stop-Proc コマンドレットは、 [システム管理](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) の入力処理方法をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-125">This Stop-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) input processing method.</span></span> <span data-ttu-id="3aeeb-126">この Stop-Proc コマンドレットの実装では、詳細メッセージ、デバッグメッセージ、および警告メッセージを書き込む呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-126">In this implementation of the Stop-Proc cmdlet, calls are made to write verbose messages, debug messages, and warning messages.</span></span>

> [!NOTE]
> <span data-ttu-id="3aeeb-127">この[メソッドの呼び出し](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法の詳細については、「システムを[変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。[このメソッドは](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-127">For more information about how this method calls the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="writing-a-verbose-message"></a><span data-ttu-id="3aeeb-128">詳細メッセージを書き込んでいます</span><span class="sxs-lookup"><span data-stu-id="3aeeb-128">Writing a Verbose Message</span></span>

<span data-ttu-id="3aeeb-129">特定 [のエラー](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) 条件に関連しない一般的なユーザーレベル情報を書き込むには、system.string メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-129">The [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method is used to write general user-level information that is unrelated to specific error conditions.</span></span> <span data-ttu-id="3aeeb-130">システム管理者は、その情報を使用して、他のコマンドの処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-130">The system administrator can then use that information to continue processing other commands.</span></span> <span data-ttu-id="3aeeb-131">また、このメソッドを使用して記述された情報は、必要に応じてローカライズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-131">In addition, any information written using this method should be localized as needed.</span></span>

<span data-ttu-id="3aeeb-132">この Stop-Proc コマンドレットの次のコードでは [、system.](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) . [...](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .....................................................</span><span class="sxs-lookup"><span data-stu-id="3aeeb-132">The following code from this Stop-Proc cmdlet shows two calls to the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a><span data-ttu-id="3aeeb-133">デバッグメッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="3aeeb-133">Writing a Debug Message</span></span>

<span data-ttu-id="3aeeb-134">コマンドレットの操作のトラブルシューティングに使用できるデバッグメッセージを記述するには、このメソッドを [使用します](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) 。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-134">The [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method is used to write debug messages that can be used to troubleshoot the operation of the cmdlet.</span></span> <span data-ttu-id="3aeeb-135">この呼び出しは、入力処理メソッドによって行われます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-135">The call is made from an input processing method.</span></span>

> [!NOTE]
> <span data-ttu-id="3aeeb-136">Windows PowerShell では、 `Debug` 詳細情報とデバッグ情報の両方を表示するパラメーターも定義されています。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-136">Windows PowerShell also defines a `Debug` parameter that presents both verbose and debug information.</span></span> <span data-ttu-id="3aeeb-137">コマンド [レットでこの](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) パラメーターがサポートされている場合は、 [system](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).......................................................</span><span class="sxs-lookup"><span data-stu-id="3aeeb-137">If your cmdlet supports this parameter, it does not need to call [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) in the same code that calls [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span></span>

<span data-ttu-id="3aeeb-138">Sample Stop-Proc コマンドレットの次の2つのセクションでは、system......................................[コマンド](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)レットのオーバーライドから、[システム](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)の呼び出しを示します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-138">The following two sections of code from the sample Stop-Proc cmdlet show calls to the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="3aeeb-139">このデバッグメッセージは、システムの [管理](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) が呼び出される直前に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-139">This debug message is written immediately before [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) is called.</span></span>

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

<span data-ttu-id="3aeeb-140">このデバッグメッセージは、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) が呼び出される直前に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-140">This debug message is written immediately before [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) is called.</span></span>

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

<span data-ttu-id="3aeeb-141">Windows PowerShell は、トレースインフラストラクチャとコマンドレットに対して、すべての [システム](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) の呼び出しを自動的にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-141">Windows PowerShell automatically routes any [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) calls to the tracing infrastructure and cmdlets.</span></span> <span data-ttu-id="3aeeb-142">これにより、メソッド呼び出しをホストアプリケーション、ファイル、またはデバッガーにトレースできます。コマンドレット内で追加の開発作業を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-142">This allows the method calls to be traced to the hosting application, a file, or a debugger without your having to do any extra development work within the cmdlet.</span></span> <span data-ttu-id="3aeeb-143">次のコマンドラインエントリは、トレース操作を実装します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-143">The following command-line entry implements a tracing operation.</span></span>

<span data-ttu-id="3aeeb-144">**PS> トレース-式の停止-proc-file proc .log-command stop-proc notepad**</span><span class="sxs-lookup"><span data-stu-id="3aeeb-144">**PS> trace-expression stop-proc -file proc.log -command stop-proc notepad**</span></span>

## <a name="writing-a-warning-message"></a><span data-ttu-id="3aeeb-145">警告メッセージを書き込んでいます</span><span class="sxs-lookup"><span data-stu-id="3aeeb-145">Writing a Warning Message</span></span>

<span data-ttu-id="3aeeb-146">コマンドレットで、予期しない結果 (読み取り専用ファイルの上書きなど) が発生する可能性がある操作を実行しようとしているときに、 [このメソッドを使用して](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) 警告を記述します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-146">The [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method is used to write a warning when the cmdlet is about to perform an operation that might have an unexpected result, for example, overwriting a read-only file.</span></span>

<span data-ttu-id="3aeeb-147">Sample Stop-Proc コマンドレットの次のコードでは [、system.](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) . [...](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) ......................................................</span><span class="sxs-lookup"><span data-stu-id="3aeeb-147">The following code from the sample Stop-Proc cmdlet shows the call to the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a><span data-ttu-id="3aeeb-148">進行状況メッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="3aeeb-148">Writing a Progress Message</span></span>

<span data-ttu-id="3aeeb-149">コマンドレット操作の完了に時間がかかる場合は、進行状況を示すメッセージを書き込むために、 [システム管理の進行状況](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-149">The [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) is used to write progress messages when cmdlet operations take an extended amount of time to complete.</span></span> <span data-ttu-id="3aeeb-150">System.servicemodel の呼び出しは、ユーザーに表示するためにホストアプリケーションに送信される、[システムの管理](/dotnet/api/System.Management.Automation.ProgressRecord)...... [progress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)レコードオブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-150">A call to [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passes a [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) object that is sent to the hosting application for rendering to the user.</span></span>

> [!NOTE]
> <span data-ttu-id="3aeeb-151">この Stop-Proc コマンドレットには、 [system.servicemodel メソッドの](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) 呼び出しが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-151">This Stop-Proc cmdlet does not include a call to the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

<span data-ttu-id="3aeeb-152">次のコードは、項目をコピーしようとしているコマンドレットによって作成された進行状況メッセージの例です。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-152">The following code is an example of a progress message written by a cmdlet that is attempting to copy an item.</span></span>

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a><span data-ttu-id="3aeeb-153">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="3aeeb-153">Code Sample</span></span>

<span data-ttu-id="3aeeb-154">完全な C# サンプルコードについては、「 [StopProcessSample02 sample](./stopprocesssample02-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-154">For the complete C# sample code, see [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="3aeeb-155">オブジェクトの種類と書式を定義する</span><span class="sxs-lookup"><span data-stu-id="3aeeb-155">Define Object Types and Formatting</span></span>

<span data-ttu-id="3aeeb-156">Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-156">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="3aeeb-157">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-157">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="3aeeb-158">新しい型を定義する、または既存の型を拡張する方法の詳細については、「 [オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-158">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="3aeeb-159">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="3aeeb-159">Building the Cmdlet</span></span>

<span data-ttu-id="3aeeb-160">コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-160">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="3aeeb-161">コマンドレットの登録の詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-161">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="3aeeb-162">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="3aeeb-162">Testing the Cmdlet</span></span>

<span data-ttu-id="3aeeb-163">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-163">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="3aeeb-164">サンプル Stop-Proc コマンドレットをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-164">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="3aeeb-165">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-165">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="3aeeb-166">次のコマンドラインエントリは、Stop-Proc を使用して、"NOTEPAD" という名前のプロセスを停止し、詳細通知を提供し、デバッグ情報を出力します。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-166">The following command-line entry uses Stop-Proc to stop the process named "NOTEPAD", provide verbose notifications, and print debug information.</span></span>

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

    <span data-ttu-id="3aeeb-167">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aeeb-167">The following output appears.</span></span>

    ```
    VERBOSE: Attempting to stop process " notepad ".
    DEBUG: Acquired name for pid 5584 : "notepad"

    Confirm
    Continue with this operation?
    [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): Y

    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (5584)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    VERBOSE: Stopped process "notepad", pid 5584.
    ```

## <a name="see-also"></a><span data-ttu-id="3aeeb-168">参照</span><span class="sxs-lookup"><span data-stu-id="3aeeb-168">See Also</span></span>

[<span data-ttu-id="3aeeb-169">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="3aeeb-169">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="3aeeb-170">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="3aeeb-170">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="3aeeb-171">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="3aeeb-171">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="3aeeb-172">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="3aeeb-172">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="3aeeb-173">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3aeeb-173">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

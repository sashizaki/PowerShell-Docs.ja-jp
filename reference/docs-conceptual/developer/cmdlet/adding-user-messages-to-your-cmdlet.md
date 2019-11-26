---
title: コマンドレットにユーザーメッセージを追加する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WriteWarning
- notifications, writing
- progress notification
- WriteVerbose
- Stop-Proc
- WriteProgress
- WriteDebug
- notifications, debug
- ProgressRecord
- samples, Stop-Proc cmdlet
- notifications, progress
- notifications, warning
- WriteObject
- WriteError
- verbose notification
- ProcessRecord
- notifications, verbose
- debug notification
- cmdlet, writing notifications
- warning
- code sample, user notifications
- user notifications
ms.assetid: 14c13acb-f0b7-4613-bc7d-c361d14da1a2
caps.latest.revision: 8
ms.openlocfilehash: 9079f40e75dae86c22fd8b4f8a45d501c6125498
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416031"
---
# <a name="adding-user-messages-to-your-cmdlet"></a><span data-ttu-id="ec7a0-102">コマンドレットにユーザー メッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="ec7a0-102">Adding User Messages to Your Cmdlet</span></span>

<span data-ttu-id="ec7a0-103">コマンドレットでは、Windows PowerShell ランタイムによってユーザーに表示できるいくつかの種類のメッセージを書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-103">Cmdlets can write several kinds of messages that can be displayed to the user by the Windows PowerShell runtime.</span></span> <span data-ttu-id="ec7a0-104">これらのメッセージには、次の種類があります。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-104">These messages include the following types:</span></span>

- <span data-ttu-id="ec7a0-105">一般的なユーザー情報を含む詳細なメッセージ。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-105">Verbose messages that contain general user information.</span></span>

- <span data-ttu-id="ec7a0-106">トラブルシューティング情報を含むメッセージをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-106">Debug messages that contain troubleshooting information.</span></span>

- <span data-ttu-id="ec7a0-107">コマンドレットが予期しない結果になる可能性のある操作を実行しようとしていることを示す通知を含む警告メッセージ。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-107">Warning messages that contain a notification that the cmdlet is about to perform an operation that can have unexpected results.</span></span>

- <span data-ttu-id="ec7a0-108">実行時間が長い操作を実行するときにコマンドレットが完了した作業量に関する情報を含む進行状況レポートメッセージ。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-108">Progress report messages that contain information about how much work the cmdlet has completed when performing an operation that takes a long time.</span></span>

<span data-ttu-id="ec7a0-109">コマンドレットで書き込むことができるメッセージの数や、コマンドレットが書き込むメッセージの種類に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-109">There are no limits to the number of messages that your cmdlet can write or the type of messages that your cmdlet writes.</span></span> <span data-ttu-id="ec7a0-110">各メッセージは、コマンドレットの入力処理メソッド内から特定の呼び出しを行うことによって書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-110">Each message is written by making a specific call from within the input processing method of your cmdlet.</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="ec7a0-111">コマンドレットの定義</span><span class="sxs-lookup"><span data-stu-id="ec7a0-111">Defining the Cmdlet</span></span>

<span data-ttu-id="ec7a0-112">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-112">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="ec7a0-113">任意の種類のコマンドレットは、入力処理メソッドからユーザー通知を書き込むことができます。そのため、一般に、このコマンドレットには、コマンドレットで実行されるシステム変更を示す動詞を使用して名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-113">Any sort of cmdlet can write user notifications from its input processing methods; so, in general, you can name this cmdlet using any verb that indicates what system modifications the cmdlet performs.</span></span> <span data-ttu-id="ec7a0-114">承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-114">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="ec7a0-115">Stop Proc コマンドレットは、システムを変更するように設計されています。したがって、.NET クラスの system.servicemodel[属性](/dotnet/api/System.Management.Automation.CmdletAttribute)宣言には、`SupportsShouldProcess` attribute キーワードを含め、`true`に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-115">The Stop-Proc cmdlet is designed to modify the system; therefore, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration for the .NET class must include the `SupportsShouldProcess` attribute keyword and be set to `true`.</span></span>

<span data-ttu-id="ec7a0-116">次のコードは、この Stop Proc コマンドレットクラスの定義です。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-116">The following code is the definition for this Stop-Proc cmdlet class.</span></span> <span data-ttu-id="ec7a0-117">この定義の詳細については、「[システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-117">For more information about this definition, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="ec7a0-118">システム変更のパラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="ec7a0-118">Defining Parameters for System Modification</span></span>

<span data-ttu-id="ec7a0-119">Stop Proc コマンドレットは、`Name`、`Force`、および `PassThru`の3つのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-119">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span> <span data-ttu-id="ec7a0-120">これらのパラメーターの定義の詳細については、「[システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-120">For more information about defining these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

<span data-ttu-id="ec7a0-121">Stop Proc コマンドレットのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-121">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="ec7a0-122">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="ec7a0-122">Overriding an Input Processing Method</span></span>

<span data-ttu-id="ec7a0-123">コマンドレットは、入力処理メソッドをオーバーライドする必要があります。ほとんどの場合、この[コマンドレットは](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、system.object を変更します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-123">Your cmdlet must override an input processing method, most often it will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="ec7a0-124">この Stop Proc コマンドレットは、[システム管理](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)の入力処理方法をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-124">This Stop-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) input processing method.</span></span> <span data-ttu-id="ec7a0-125">この Stop Proc コマンドレットの実装では、詳細メッセージ、デバッグメッセージ、および警告メッセージを書き込む呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-125">In this implementation of the Stop-Proc cmdlet, calls are made to write verbose messages, debug messages, and warning messages.</span></span>

> [!NOTE]
> <span data-ttu-id="ec7a0-126">この[メソッドの呼び出し](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法の詳細については、「システムを[変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。[このメソッドは](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-126">For more information about how this method calls the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="writing-a-verbose-message"></a><span data-ttu-id="ec7a0-127">詳細メッセージを書き込んでいます</span><span class="sxs-lookup"><span data-stu-id="ec7a0-127">Writing a Verbose Message</span></span>

<span data-ttu-id="ec7a0-128">特定[のエラー](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)条件に関連しない一般的なユーザーレベル情報を書き込むには、system.string メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-128">The [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method is used to write general user-level information that is unrelated to specific error conditions.</span></span> <span data-ttu-id="ec7a0-129">システム管理者は、その情報を使用して、他のコマンドの処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-129">The system administrator can then use that information to continue processing other commands.</span></span> <span data-ttu-id="ec7a0-130">また、このメソッドを使用して記述された情報は、必要に応じてローカライズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-130">In addition, any information written using this method should be localized as needed.</span></span>

<span data-ttu-id="ec7a0-131">この Stop Proc コマンドレットの次のコードでは[、system.](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) . [...](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .......................................................</span><span class="sxs-lookup"><span data-stu-id="ec7a0-131">The following code from this Stop-Proc cmdlet shows two calls to the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a><span data-ttu-id="ec7a0-132">デバッグメッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="ec7a0-132">Writing a Debug Message</span></span>

<span data-ttu-id="ec7a0-133">コマンドレットの操作のトラブルシューティングに使用できるデバッグメッセージを記述するには、このメソッドを[使用します](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-133">The [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method is used to write debug messages that can be used to troubleshoot the operation of the cmdlet.</span></span> <span data-ttu-id="ec7a0-134">この呼び出しは、入力処理メソッドによって行われます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-134">The call is made from an input processing method.</span></span>

> [!NOTE]
> <span data-ttu-id="ec7a0-135">Windows PowerShell では、詳細情報とデバッグ情報の両方を表示する `Debug` パラメーターも定義されています。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-135">Windows PowerShell also defines a `Debug` parameter that presents both verbose and debug information.</span></span> <span data-ttu-id="ec7a0-136">コマンド[レットでこの](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)パラメーターがサポートされている場合は、 [system](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).......................................................</span><span class="sxs-lookup"><span data-stu-id="ec7a0-136">If your cmdlet supports this parameter, it does not need to call [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) in the same code that calls [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span></span>

<span data-ttu-id="ec7a0-137">次のサンプルの Stop Proc コマンドレットのコードの2つのセクションでは、system............................... [. コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)のオーバーライドから、[システム](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)の呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-137">The following two sections of code from the sample Stop-Proc cmdlet show calls to the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="ec7a0-138">このデバッグメッセージは、システムの[管理](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)が呼び出される直前に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-138">This debug message is written immediately before [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) is called.</span></span>

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

<span data-ttu-id="ec7a0-139">このデバッグメッセージは、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)が呼び出される直前に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-139">This debug message is written immediately before [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) is called.</span></span>

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

<span data-ttu-id="ec7a0-140">Windows PowerShell は、トレースインフラストラクチャとコマンドレットに対して、すべての[システム](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)の呼び出しを自動的にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-140">Windows PowerShell automatically routes any [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) calls to the tracing infrastructure and cmdlets.</span></span> <span data-ttu-id="ec7a0-141">これにより、メソッド呼び出しをホストアプリケーション、ファイル、またはデバッガーにトレースできます。コマンドレット内で追加の開発作業を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-141">This allows the method calls to be traced to the hosting application, a file, or a debugger without your having to do any extra development work within the cmdlet.</span></span> <span data-ttu-id="ec7a0-142">次のコマンドラインエントリは、トレース操作を実装します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-142">The following command-line entry implements a tracing operation.</span></span>

<span data-ttu-id="ec7a0-143">**PS > トレース-式の停止-proc-file proc .log-command stop-proc notepad**</span><span class="sxs-lookup"><span data-stu-id="ec7a0-143">**PS> trace-expression stop-proc -file proc.log -command stop-proc notepad**</span></span>

## <a name="writing-a-warning-message"></a><span data-ttu-id="ec7a0-144">警告メッセージを書き込んでいます</span><span class="sxs-lookup"><span data-stu-id="ec7a0-144">Writing a Warning Message</span></span>

<span data-ttu-id="ec7a0-145">コマンドレットで、予期しない結果 (読み取り専用ファイルの上書きなど) が発生する可能性がある操作を実行しようとしているときに、[このメソッドを使用して](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)警告を記述します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-145">The [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method is used to write a warning when the cmdlet is about to perform an operation that might have an unexpected result, for example, overwriting a read-only file.</span></span>

<span data-ttu-id="ec7a0-146">次のサンプルの Stop Proc コマンドレットのコードでは[、system.](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) . [...](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) ......................................................</span><span class="sxs-lookup"><span data-stu-id="ec7a0-146">The following code from the sample Stop-Proc cmdlet shows the call to the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a><span data-ttu-id="ec7a0-147">進行状況メッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="ec7a0-147">Writing a Progress Message</span></span>

<span data-ttu-id="ec7a0-148">コマンドレット操作の完了に時間がかかる場合は、進行状況を示すメッセージを書き込むために、[システム管理の進行状況](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-148">The [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) is used to write progress messages when cmdlet operations take an extended amount of time to complete.</span></span> <span data-ttu-id="ec7a0-149">System.servicemodel の呼び出しは、ユーザーに表示するためにホストアプリケーションに送信される、[システムの管理](/dotnet/api/System.Management.Automation.ProgressRecord)...... [progress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)レコードオブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-149">A call to [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passes a [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) object that is sent to the hosting application for rendering to the user.</span></span>

> [!NOTE]
> <span data-ttu-id="ec7a0-150">この Stop Proc コマンドレットには、 [system.servicemodel メソッドの](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)呼び出しが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-150">This Stop-Proc cmdlet does not include a call to the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

<span data-ttu-id="ec7a0-151">次のコードは、項目をコピーしようとしているコマンドレットによって作成された進行状況メッセージの例です。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-151">The following code is an example of a progress message written by a cmdlet that is attempting to copy an item.</span></span>

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a><span data-ttu-id="ec7a0-152">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="ec7a0-152">Code Sample</span></span>

<span data-ttu-id="ec7a0-153">完全なC#サンプルコードについては、「 [StopProcessSample02 sample](./stopprocesssample02-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-153">For the complete C# sample code, see [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="ec7a0-154">オブジェクトの種類と書式を定義する</span><span class="sxs-lookup"><span data-stu-id="ec7a0-154">Define Object Types and Formatting</span></span>

<span data-ttu-id="ec7a0-155">Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-155">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="ec7a0-156">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-156">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="ec7a0-157">新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-157">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="ec7a0-158">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="ec7a0-158">Building the Cmdlet</span></span>

<span data-ttu-id="ec7a0-159">コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-159">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="ec7a0-160">コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-160">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="ec7a0-161">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="ec7a0-161">Testing the Cmdlet</span></span>

<span data-ttu-id="ec7a0-162">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-162">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="ec7a0-163">Stop-Proc コマンドレットのサンプルをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-163">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="ec7a0-164">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-164">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="ec7a0-165">次のコマンドラインエントリは、Stop-Proc を使用して、"NOTEPAD" という名前のプロセスを停止し、詳細通知を提供し、デバッグ情報を出力します。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-165">The following command-line entry uses Stop-Proc to stop the process named "NOTEPAD", provide verbose notifications, and print debug information.</span></span>

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

<span data-ttu-id="ec7a0-166">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec7a0-166">The following output appears.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ec7a0-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec7a0-167">See Also</span></span>

[<span data-ttu-id="ec7a0-168">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="ec7a0-168">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="ec7a0-169">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ec7a0-169">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="ec7a0-170">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ec7a0-170">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="ec7a0-171">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ec7a0-171">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="ec7a0-172">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="ec7a0-172">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

---
title: コマンドレットへのユーザー メッセージの追加 |Microsoft Docs
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
ms.openlocfilehash: 5b3a5f5d5d02c7d5a3c1d622ec1a3740739c694f
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055038"
---
# <a name="adding-user-messages-to-your-cmdlet"></a><span data-ttu-id="a3ead-102">コマンドレットにユーザー メッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="a3ead-102">Adding User Messages to Your Cmdlet</span></span>

<span data-ttu-id="a3ead-103">コマンドレットは、いくつかの種類の Windows PowerShell ランタイムによって、ユーザーに表示できるメッセージを記述できます。</span><span class="sxs-lookup"><span data-stu-id="a3ead-103">Cmdlets can write several kinds of messages that can be displayed to the user by the Windows PowerShell runtime.</span></span> <span data-ttu-id="a3ead-104">これらのメッセージには、次の種類があります。</span><span class="sxs-lookup"><span data-stu-id="a3ead-104">These messages include the following types:</span></span>

- <span data-ttu-id="a3ead-105">全般的なユーザー情報を含む詳細メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a3ead-105">Verbose messages that contain general user information.</span></span>

- <span data-ttu-id="a3ead-106">トラブルシューティングの情報を含むメッセージをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="a3ead-106">Debug messages that contain troubleshooting information.</span></span>

- <span data-ttu-id="a3ead-107">警告メッセージを含むことができる操作を実行しようとして、コマンドレットである通知予期しない結果。</span><span class="sxs-lookup"><span data-stu-id="a3ead-107">Warning messages that contain a notification that the cmdlet is about to perform an operation that can have unexpected results.</span></span>

- <span data-ttu-id="a3ead-108">メッセージ量に関する情報が含まれているコマンドレットの作業の進行状況レポートは、時間がかかる操作を実行するときに完了しました。</span><span class="sxs-lookup"><span data-stu-id="a3ead-108">Progress report messages that contain information about how much work the cmdlet has completed when performing an operation that takes a long time.</span></span>

<span data-ttu-id="a3ead-109">コマンドレットの書き込みのメッセージの種類のコマンドレットが書き込むことのできるメッセージの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="a3ead-109">There are no limits to the number of messages that your cmdlet can write or the type of messages that your cmdlet writes.</span></span> <span data-ttu-id="a3ead-110">処理方法、コマンドレットの入力の中から特定を呼び出すことによって、各メッセージが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a3ead-110">Each message is written by making a specific call from within the input processing method of your cmdlet.</span></span>

## <a name="the-stopproc-cmdlet"></a><span data-ttu-id="a3ead-111">StopProc コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a3ead-111">The StopProc Cmdlet</span></span>

<span data-ttu-id="a3ead-112">このセクションのトピックで、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a3ead-112">Topics in this section include the following:</span></span>

- [<span data-ttu-id="a3ead-113">コマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-113">Defining the Cmdlet</span></span>](#Defining-the-Cmdlet)

- [<span data-ttu-id="a3ead-114">システムの変更のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-114">Defining Parameters for System Modification</span></span>](#Defining-Parameters-for-System-Modification)

- [<span data-ttu-id="a3ead-115">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a3ead-115">Overriding an Input Processing Method</span></span>](#Overriding-an-Input-Processing-Method)

- [<span data-ttu-id="a3ead-116">詳細なメッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="a3ead-116">Writing a Verbose Message</span></span>](#Writing-a-Verbose-Message)

- [<span data-ttu-id="a3ead-117">デバッグ メッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="a3ead-117">Writing a Debug Message</span></span>](#Writing-a-Debug-Message)

- [<span data-ttu-id="a3ead-118">警告メッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="a3ead-118">Writing a Warning Message</span></span>](#Writing-a-Warning-Message)

- [<span data-ttu-id="a3ead-119">進行状況メッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="a3ead-119">Writing a Progress Message</span></span>](#Writing-a-Progress-Message)

- [<span data-ttu-id="a3ead-120">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="a3ead-120">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="a3ead-121">オブジェクトの種類と書式設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-121">Define Object Types and Formatting</span></span>](#Define-Object-Types-and-Formatting)

- [<span data-ttu-id="a3ead-122">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="a3ead-122">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="a3ead-123">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a3ead-123">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet"></a><span data-ttu-id="a3ead-124">コマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-124">Defining the Cmdlet</span></span>

<span data-ttu-id="a3ead-125">コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-125">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="a3ead-126">コマンドレットの任意の並べ替えは、入力処理メソッド; からユーザーへの通知を記述できます。そのため、一般に、できる名前をコマンドレットを実行します。 どのようなシステムの変更を示すすべての動詞を使用してこのコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="a3ead-126">Any sort of cmdlet can write user notifications from its input processing methods; so, in general, you can name this cmdlet using any verb that indicates what system modifications the cmdlet performs.</span></span> <span data-ttu-id="a3ead-127">承認されたコマンドレット動詞の詳細については、[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3ead-127">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="a3ead-128">停止 Proc コマンドレットが、システムを変更するように設計します。そのため、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) .NET クラスの宣言を含める必要があります、`SupportsShouldProcess`キーワードを属性し、に設定する`true`します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-128">The Stop-Proc cmdlet is designed to modify the system; therefore, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration for the .NET class must include the `SupportsShouldProcess` attribute keyword and be set to `true`.</span></span>

<span data-ttu-id="a3ead-129">次のコードは、この停止 Proc コマンドレット クラスの定義です。</span><span class="sxs-lookup"><span data-stu-id="a3ead-129">The following code is the definition for this Stop-Proc cmdlet class.</span></span> <span data-ttu-id="a3ead-130">この定義の詳細については、[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3ead-130">For more information about this definition, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="a3ead-131">システムの変更のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-131">Defining Parameters for System Modification</span></span>

<span data-ttu-id="a3ead-132">停止 Proc コマンドレットは、3 つのパラメーターを定義します。 `Name`、 `Force`、および`PassThru`します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-132">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span> <span data-ttu-id="a3ead-133">これらのパラメーターの定義の詳細については、[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3ead-133">For more information about defining these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

<span data-ttu-id="a3ead-134">停止 Proc コマンドレットのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-134">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="a3ead-135">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a3ead-135">Overriding an Input Processing Method</span></span>

<span data-ttu-id="a3ead-136">コマンドレットは、入力処理メソッドをオーバーライドする必要があります、最もよくなります[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-136">Your cmdlet must override an input processing method, most often it will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="a3ead-137">この停止 Proc コマンドレットよりも優先、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)処理方法を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-137">This Stop-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) input processing method.</span></span> <span data-ttu-id="a3ead-138">停止 Proc コマンドレットのこの実装では、呼び出しは詳細メッセージ、デバッグ メッセージ、警告メッセージを記述する行われます。</span><span class="sxs-lookup"><span data-stu-id="a3ead-138">In this implementation of the Stop-Proc cmdlet, calls are made to write verbose messages, debug messages, and warning messages.</span></span>

> [!NOTE]
> <span data-ttu-id="a3ead-139">このメソッドを呼び出す方法の詳細については、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッド、を参照してください[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-139">For more information about how this method calls the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="writing-a-verbose-message"></a><span data-ttu-id="a3ead-140">詳細なメッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="a3ead-140">Writing a Verbose Message</span></span>

<span data-ttu-id="a3ead-141">[System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)が特定のエラー条件に関連付けられていない一般的なユーザー レベルの情報を記述するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-141">The [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method is used to write general user-level information that is unrelated to specific error conditions.</span></span> <span data-ttu-id="a3ead-142">システム管理者はその情報を使用して、その他のコマンドの処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-142">The system administrator can then use that information to continue processing other commands.</span></span> <span data-ttu-id="a3ead-143">さらに、必要に応じて、このメソッドを使用して書き込まれた情報をローカライズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ead-143">In addition, any information written using this method should be localized as needed.</span></span>

<span data-ttu-id="a3ead-144">この停止 Proc コマンドレットから次のコードは、2 つの呼び出しを示しています、 [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)メソッドのオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a3ead-144">The following code from this Stop-Proc cmdlet shows two calls to the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a><span data-ttu-id="a3ead-145">デバッグ メッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="a3ead-145">Writing a Debug Message</span></span>

<span data-ttu-id="a3ead-146">[System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)コマンドレットの操作のトラブルシューティングに使用できるデバッグ メッセージを記述するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-146">The [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method is used to write debug messages that can be used to troubleshoot the operation of the cmdlet.</span></span> <span data-ttu-id="a3ead-147">入力処理メソッドから呼び出し。</span><span class="sxs-lookup"><span data-stu-id="a3ead-147">The call is made from an input processing method.</span></span>

> [!NOTE]
> <span data-ttu-id="a3ead-148">Windows PowerShell も定義、`Debug`パラメーターを両方の詳細を表示し、デバッグ情報。</span><span class="sxs-lookup"><span data-stu-id="a3ead-148">Windows PowerShell also defines a `Debug` parameter that presents both verbose and debug information.</span></span> <span data-ttu-id="a3ead-149">呼び出す必要はありません、コマンドレットは、このパラメーターをサポートする場合[System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)を呼び出すのと同じコードで[System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span><span class="sxs-lookup"><span data-stu-id="a3ead-149">If your cmdlet supports this parameter, it does not need to call [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) in the same code that calls [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span></span>

<span data-ttu-id="a3ead-150">サンプルの停止 Proc コマンドレットからのコードの次の 2 つのセクションへの呼び出しを表示する、 [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)メソッドのオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a3ead-150">The following two sections of code from the sample Stop-Proc cmdlet show calls to the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="a3ead-151">このデバッグ メッセージが直前に書き込まれる[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a3ead-151">This debug message is written immediately before [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) is called.</span></span>

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

<span data-ttu-id="a3ead-152">このデバッグ メッセージが直前に書き込まれる[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a3ead-152">This debug message is written immediately before [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) is called.</span></span>

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

<span data-ttu-id="a3ead-153">いずれかは、Windows PowerShell が自動的にルーティング[System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug)トレース インフラストラクチャとコマンドレットの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="a3ead-153">Windows PowerShell automatically routes any [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) calls to the tracing infrastructure and cmdlets.</span></span> <span data-ttu-id="a3ead-154">これにより、コマンドレットの開発に余分な作業を行うことがなく、ホスト アプリケーション、ファイル、またはデバッガーをトレースするメソッドの呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="a3ead-154">This allows the method calls to be traced to the hosting application, a file, or a debugger without your having to do any extra development work within the cmdlet.</span></span> <span data-ttu-id="a3ead-155">次のコマンド ライン エントリは、トレース操作を実装します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-155">The following command-line entry implements a tracing operation.</span></span>

<span data-ttu-id="a3ead-156">**PS > トレース式停止インプロセス-proc.log ファイル-停止 proc メモ帳のコマンド**</span><span class="sxs-lookup"><span data-stu-id="a3ead-156">**PS> trace-expression stop-proc -file proc.log -command stop-proc notepad**</span></span>

## <a name="writing-a-warning-message"></a><span data-ttu-id="a3ead-157">警告メッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="a3ead-157">Writing a Warning Message</span></span>

<span data-ttu-id="a3ead-158">[System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)コマンドレットが予期しない結果が、たとえば、読み取り専用ファイルを上書きする可能性がある操作を実行するときに警告を記述するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-158">The [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method is used to write a warning when the cmdlet is about to perform an operation that might have an unexpected result, for example, overwriting a read-only file.</span></span>

<span data-ttu-id="a3ead-159">サンプルの停止 Proc コマンドレットから次のコードに呼び出しを示しています、 [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)メソッドのオーバーライドから、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a3ead-159">The following code from the sample Stop-Proc cmdlet shows the call to the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a><span data-ttu-id="a3ead-160">進行状況メッセージの書き込み</span><span class="sxs-lookup"><span data-stu-id="a3ead-160">Writing a Progress Message</span></span>

<span data-ttu-id="a3ead-161">[System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)コマンドレットの操作を完了するに非常に長い時間を取得すると、進行状況メッセージを書き込むために使用します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-161">The [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) is used to write progress messages when cmdlet operations take an extended amount of time to complete.</span></span> <span data-ttu-id="a3ead-162">呼び出し[System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)渡します、 [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord)レンダリングするまで、ユーザーに、ホスト アプリケーションに送信されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a3ead-162">A call to [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passes a [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) object that is sent to the hosting application for rendering to the user.</span></span>

> [!NOTE]
> <span data-ttu-id="a3ead-163">この停止 Proc コマンドレットへの呼び出しを含まない、 [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a3ead-163">This Stop-Proc cmdlet does not include a call to the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

<span data-ttu-id="a3ead-164">次のコードは、項目をコピーしようとするコマンドレットによって作成された進行状況メッセージの例です。</span><span class="sxs-lookup"><span data-stu-id="a3ead-164">The following code is an example of a progress message written by a cmdlet that is attempting to copy an item.</span></span>

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a><span data-ttu-id="a3ead-165">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="a3ead-165">Code Sample</span></span>

<span data-ttu-id="a3ead-166">完全なC#サンプル コードは、「 [StopProcessSample02 サンプル](./stopprocesssample02-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-166">For the complete C# sample code, see [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="a3ead-167">オブジェクトの種類と書式設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-167">Define Object Types and Formatting</span></span>

<span data-ttu-id="a3ead-168">Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-168">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="a3ead-169">その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ead-169">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="a3ead-170">新しい型を定義するか、既存の型の拡張の詳細については、[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3ead-170">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="a3ead-171">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="a3ead-171">Building the Cmdlet</span></span>

<span data-ttu-id="a3ead-172">コマンドレットを実装するには、後にする必要があります登録する必要が Windows PowerShell を使用した Windows PowerShell スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-172">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="a3ead-173">コマンドレットの登録の詳細については、[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3ead-173">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="a3ead-174">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a3ead-174">Testing the Cmdlet</span></span>

<span data-ttu-id="a3ead-175">コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="a3ead-175">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="a3ead-176">サンプルの停止 Proc コマンドレットをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="a3ead-176">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="a3ead-177">詳細については、コマンドラインからコマンドレットを使用して、、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3ead-177">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="a3ead-178">次のコマンド ライン エントリは、"NOTEPAD"という名前のプロセスを停止し、詳細の通知を提供し、デバッグ情報を印刷する停止プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-178">The following command-line entry uses Stop-Proc to stop the process named "NOTEPAD", provide verbose notifications, and print debug information.</span></span>

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

<span data-ttu-id="a3ead-179">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3ead-179">The following output appears.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a3ead-180">参照</span><span class="sxs-lookup"><span data-stu-id="a3ead-180">See Also</span></span>

[<span data-ttu-id="a3ead-181">システムを変更するコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="a3ead-181">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="a3ead-182">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="a3ead-182">How to Create a Windows PowerShell Cmdlet</span></span>](http://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="a3ead-183">オブジェクトの種類を拡張して、書式設定</span><span class="sxs-lookup"><span data-stu-id="a3ead-183">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="a3ead-184">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="a3ead-184">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="a3ead-185">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="a3ead-185">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

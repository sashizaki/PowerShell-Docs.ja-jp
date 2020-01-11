---
title: コマンドレットに終了しないエラー報告を追加する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a1531a-a92a-4606-9d54-c5df80d34f33
caps.latest.revision: 8
ms.openlocfilehash: ec29d1cffa083e4cce667d3e1efbd4eeecbffb51
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870117"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a><span data-ttu-id="e40c2-102">終了しないエラーのレポートをコマンドレットに追加する</span><span class="sxs-lookup"><span data-stu-id="e40c2-102">Adding Non-Terminating Error Reporting to Your Cmdlet</span></span>

<span data-ttu-id="e40c2-103">コマンドレットは、 [WriteError (システム管理)][]メソッドを呼び出すことによって終了しないエラーを報告し、引き続き現在の入力オブジェクトまたはその他の受信パイプラインオブジェクトで操作を続行できます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-103">Cmdlets can report nonterminating errors by calling the [System.Management.Automation.Cmdlet.WriteError][] method and still continue to operate on the current input object or on further incoming pipeline objects.</span></span> <span data-ttu-id="e40c2-104">このセクションでは、入力処理メソッドから終了しないエラーを報告するコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-104">This section explains how to create a cmdlet that reports nonterminating errors from its input processing methods.</span></span>

<span data-ttu-id="e40c2-105">終了しないエラー (および終了エラー) については、コマンドレットはエラーを識別する system.servicemodel[システムの管理. ErrorRecord][]オブジェクトを渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-105">For nonterminating errors (as well as terminating errors), the cmdlet must pass an [System.Management.Automation.ErrorRecord][] object identifying the error.</span></span> <span data-ttu-id="e40c2-106">各エラーレコードは、"エラー識別子" と呼ばれる一意の文字列によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-106">Each error record is identified by a unique string called the "error identifier".</span></span> <span data-ttu-id="e40c2-107">識別子に加えて、各エラーのカテゴリは[ErrorCategory (システム管理)][]列挙型によって定義された定数によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-107">In addition to the identifier, the category of each error is specified by constants defined by a [System.Management.Automation.ErrorCategory][] enumeration.</span></span> <span data-ttu-id="e40c2-108">ユーザーは、`$ErrorView` 変数を "category View" に設定することにより、カテゴリに基づいてエラーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-108">The user can view errors based on their category by setting the `$ErrorView` variable to "CategoryView".</span></span>

<span data-ttu-id="e40c2-109">エラーレコードの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-109">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="e40c2-110">コマンドレットの定義</span><span class="sxs-lookup"><span data-stu-id="e40c2-110">Defining the Cmdlet</span></span>

<span data-ttu-id="e40c2-111">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-111">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="e40c2-112">このコマンドレットはプロセス情報を取得するため、ここで選択した動詞名は "Get" です。</span><span class="sxs-lookup"><span data-stu-id="e40c2-112">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="e40c2-113">(情報を取得できるほとんどすべての種類のコマンドレットは、コマンドライン入力を処理できます)。承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-113">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="e40c2-114">この `Get-Proc` コマンドレットの定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-114">The following is the definition for this `Get-Proc` cmdlet.</span></span> <span data-ttu-id="e40c2-115">この定義の詳細につい[ては、最初のコマンドレットの作成](creating-a-cmdlet-without-parameters.md)に関する説明をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-115">Details of this definition are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-parameters"></a><span data-ttu-id="e40c2-116">パラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="e40c2-116">Defining Parameters</span></span>

<span data-ttu-id="e40c2-117">必要に応じて、コマンドレットで入力を処理するためのパラメーターを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-117">If necessary, your cmdlet must define parameters for processing input.</span></span> <span data-ttu-id="e40c2-118">この Get Proc コマンドレットは、「[コマンドライン入力を処理するパラメーターの追加](adding-parameters-that-process-command-line-input.md)」で説明されているように、 **Name**パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-118">This Get-Proc cmdlet defines a **Name** parameter as described in [Adding Parameters that Process Command-Line Input](adding-parameters-that-process-command-line-input.md).</span></span>

<span data-ttu-id="e40c2-119">この Get Proc コマンドレットの**Name**パラメーターのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-119">Here is the parameter declaration for the **Name** parameter of this Get-Proc cmdlet.</span></span>

```csharp
[Parameter(
           Position = 0,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
[ValidateNotNullOrEmpty]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

```vb
<Parameter(Position:=0, ValueFromPipeline:=True, _
ValueFromPipelineByPropertyName:=True), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

## <a name="overriding-input-processing-methods"></a><span data-ttu-id="e40c2-120">オーバーライド (入力処理メソッドを)</span><span class="sxs-lookup"><span data-stu-id="e40c2-120">Overriding Input Processing Methods</span></span>

<span data-ttu-id="e40c2-121">すべてのコマンドレットで、[System. Automation. コマンドレット][]1 つの入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-121">All cmdlets must override at least one of the input processing methods provided by the [System.Management.Automation.Cmdlet][] class.</span></span> <span data-ttu-id="e40c2-122">これらのメソッドについ[ては、最初のコマンドレットの作成](creating-a-cmdlet-without-parameters.md)に関するセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-122">These methods are discussed in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e40c2-123">コマンドレットでは、各レコードを可能な限り個別に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-123">Your cmdlet should handle each record as independently as possible.</span></span>

<span data-ttu-id="e40c2-124">この Get Proc コマンドレットは、ユーザーまたはスクリプトによって提供される入力の**Name**パラメーターを処理するために、 [system.servicemodel メソッドを][]オーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="e40c2-124">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord][] method to handle the **Name** parameter for input provided by the user or a script.</span></span> <span data-ttu-id="e40c2-125">このメソッドは、要求された各プロセス名のプロセスを取得します。名前が指定されていない場合は、すべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-125">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="e40c2-126">この上書きの詳細につい[ては、最初のコマンドレットの作成](creating-a-cmdlet-without-parameters.md)に関する説明をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-126">Details of this override are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

### <a name="things-to-remember-when-reporting-errors"></a><span data-ttu-id="e40c2-127">エラーを報告する際の注意事項</span><span class="sxs-lookup"><span data-stu-id="e40c2-127">Things to Remember When Reporting Errors</span></span>

<span data-ttu-id="e40c2-128">エラーの書き込み時にコマンドレットによって渡される、[システムの管理. ErrorRecord][]オブジェクトには、コアで例外が必要です。</span><span class="sxs-lookup"><span data-stu-id="e40c2-128">The [System.Management.Automation.ErrorRecord][] object that the cmdlet passes when writing an error requires an exception at its core.</span></span> <span data-ttu-id="e40c2-129">使用する例外を決定するときは、.NET ガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-129">Follow the .NET guidelines when determining the exception to use.</span></span>
<span data-ttu-id="e40c2-130">基本的に、エラーの意味が既存の例外と同じである場合、コマンドレットはその例外を使用するか、その例外から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-130">Basically, if the error is semantically the same as an existing exception, the cmdlet should use or derive from that exception.</span></span> <span data-ttu-id="e40c2-131">それ以外の場合は、新しい例外または例外の階層を[system.exception][]クラスから直接派生させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-131">Otherwise, it should derive a new exception or exception hierarchy directly from the [System.Exception][] class.</span></span>

<span data-ttu-id="e40c2-132">エラー識別子 (ErrorRecord クラスの FullyQualifiedErrorId プロパティを通じてアクセスされる) を作成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-132">When creating error identifiers (accessed through the FullyQualifiedErrorId property of the ErrorRecord class) keep the following in mind.</span></span>

- <span data-ttu-id="e40c2-133">診断を目的とした文字列を使用して、完全修飾識別子を調べるときにエラーの内容とエラーの発生元を特定できます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-133">Use strings that are targeted for diagnostic purposes so that when inspecting the fully qualified identifier you can determine what the error is and where the error came from.</span></span>

- <span data-ttu-id="e40c2-134">正しい形式の完全修飾エラー識別子は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-134">A well formed fully qualified error identifier might be as follows.</span></span>

  `CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand`

<span data-ttu-id="e40c2-135">前の例では、エラー識別子 (最初のトークン) はエラーの内容を指定し、残りの部分はエラーの発生元を示しています。</span><span class="sxs-lookup"><span data-stu-id="e40c2-135">Notice that in the previous example, the error identifier (the first token) designates what the error is and the remaining part indicates where the error came from.</span></span>

- <span data-ttu-id="e40c2-136">より複雑なシナリオでは、エラー識別子を、検査時に解析できるドット区切りのトークンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-136">For more complex scenarios, the error identifier can be a dot separated token that can be parsed on inspection.</span></span> <span data-ttu-id="e40c2-137">これにより、エラー識別子とエラーカテゴリの両方の部分を分岐することができます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-137">This allows you too branch on the parts of the error identifier as well as the error identifier and error category.</span></span>

<span data-ttu-id="e40c2-138">コマンドレットでは、特定のエラー識別子を異なるコードパスに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-138">The cmdlet should assign specific error identifiers to different code paths.</span></span> <span data-ttu-id="e40c2-139">エラー識別子の割り当てについては、次の情報を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-139">Keep the following information in mind for assignment of error identifiers:</span></span>

- <span data-ttu-id="e40c2-140">エラー識別子は、コマンドレットのライフサイクル全体で一定のままである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-140">An error identifier should remain constant throughout the cmdlet life cycle.</span></span> <span data-ttu-id="e40c2-141">コマンドレットのバージョン間でエラー識別子のセマンティクスを変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-141">Do not change the semantics of an error identifier between cmdlet versions.</span></span>
- <span data-ttu-id="e40c2-142">Tersely が報告されているエラーに対応するエラー識別子には、テキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-142">Use text for an error identifier that tersely corresponds to the error being reported.</span></span> <span data-ttu-id="e40c2-143">空白や句読点は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-143">Do not use white space or punctuation.</span></span>
- <span data-ttu-id="e40c2-144">コマンドレットで、再現可能なエラー識別子だけを生成するようにします。</span><span class="sxs-lookup"><span data-stu-id="e40c2-144">Have your cmdlet generate only error identifiers that are reproducible.</span></span> <span data-ttu-id="e40c2-145">たとえば、プロセス識別子を含む識別子を生成しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-145">For example, it should not generate an identifier that includes a process identifier.</span></span> <span data-ttu-id="e40c2-146">エラー識別子は、同じ問題が発生している他のユーザーによって認識される識別子に対応している場合にのみ、ユーザーにとって役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-146">Error identifiers are useful to a user only when they correspond to identifiers that are seen by other users experiencing the same problem.</span></span>

<span data-ttu-id="e40c2-147">次の状況では、PowerShell でハンドルされない例外はキャッチされません。</span><span class="sxs-lookup"><span data-stu-id="e40c2-147">Unhandled exceptions are not caught by PowerShell in the following conditions:</span></span>

- <span data-ttu-id="e40c2-148">コマンドレットが新しいスレッドを作成し、そのスレッドで実行されているコードがハンドルされない例外をスローした場合、PowerShell はエラーをキャッチせず、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-148">If a cmdlet creates a new thread and code running in that thread throws an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>
- <span data-ttu-id="e40c2-149">オブジェクトのデストラクターにコードが含まれているか、ハンドルされない例外の原因となった Dispose メソッドがある場合、PowerShell はエラーをキャッチせずにプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-149">If an object has code in its destructor or Dispose methods that causes an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>

## <a name="reporting-nonterminating-errors"></a><span data-ttu-id="e40c2-150">終了しないエラーの報告</span><span class="sxs-lookup"><span data-stu-id="e40c2-150">Reporting Nonterminating Errors</span></span>

<span data-ttu-id="e40c2-151">いずれかの入力処理方法では、 [WriteError (システム管理)][]メソッドを使用して、出力ストリームに終了しないエラーを報告できます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-151">Any one of the input processing methods can report a nonterminating error to the output stream using the [System.Management.Automation.Cmdlet.WriteError][] method.</span></span>

<span data-ttu-id="e40c2-152">次に示すのは、 [WriteError (システム管理)][]コマンドレットからのコード例です。このコマンドレットでは、 [system.servicemodel メソッドを][] ...................................................</span><span class="sxs-lookup"><span data-stu-id="e40c2-152">Here is a code example from this Get-Proc cmdlet that illustrates the call to [System.Management.Automation.Cmdlet.WriteError][] from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord][] method.</span></span> <span data-ttu-id="e40c2-153">この場合、指定されたプロセス識別子のプロセスがコマンドレットで見つからない場合、呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-153">In this case, the call is made if the cmdlet cannot find a process for a specified process identifier.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no name parameter passed to cmdlet, get all processes.
  if (processNames == null)
  {
    WriteObject(Process.GetProcesses(), true);
  }
    else
    {
      // If a name parameter is passed to cmdlet, get and write
      // the associated processes.
      // Write a nonterminating error for failure to retrieve
      // a process.
      foreach (string name in processNames)
      {
        Process[] processes;

        try
        {
          processes = Process.GetProcessesByName(name);
        }
        catch (InvalidOperationException ex)
        {
          WriteError(new ErrorRecord(
                     ex,
                     "NameNotFound",
                     ErrorCategory.InvalidOperation,
                     name));
          continue;
        }

        WriteObject(processes, true);
      } // foreach (...
    } // else
  }
```

### <a name="things-to-remember-about-writing-nonterminating-errors"></a><span data-ttu-id="e40c2-154">終了しないエラーの書き込みに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="e40c2-154">Things to Remember About Writing Nonterminating Errors</span></span>

<span data-ttu-id="e40c2-155">終了しないエラーの場合、コマンドレットは、特定の入力オブジェクトごとに特定のエラー識別子を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-155">For a nonterminating error, the cmdlet must generate a specific error identifier for each specific input object.</span></span>

<span data-ttu-id="e40c2-156">コマンドレットでは、終了しないエラーによって生成される PowerShell アクションを頻繁に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-156">A cmdlet frequently needs to modify the PowerShell action produced by a nonterminating error.</span></span> <span data-ttu-id="e40c2-157">これを行うには、`ErrorAction` パラメーターと `ErrorVariable` パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-157">It can do this by defining the `ErrorAction` and `ErrorVariable` parameters.</span></span> <span data-ttu-id="e40c2-158">`ErrorAction` パラメーターを定義すると、コマンドレットによって[システムの管理. ActionPreference][][system.servicemodel] が表示されます。また、`$ErrorActionPreference` 変数を設定して、アクションに直接影響を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-158">If defining the `ErrorAction` parameter, the cmdlet presents the user options [System.Management.Automation.ActionPreference][], you can also directly influence the action by setting the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="e40c2-159">コマンドレットでは、`ErrorVariable` パラメーターを使用して、終了しないエラーを変数に保存できます。このパラメーターは、`ErrorAction`の設定の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="e40c2-159">The cmdlet can save nonterminating errors to a variable using the `ErrorVariable` parameter, which is not affected by the setting of `ErrorAction`.</span></span> <span data-ttu-id="e40c2-160">エラーは、変数名の前にプラス記号 (+) を追加することによって、既存のエラー変数に追加できます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-160">Failures can be appended to an existing error variable by adding a plus sign (+) to the front of the variable name.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e40c2-161">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="e40c2-161">Code Sample</span></span>

<span data-ttu-id="e40c2-162">完全なC#サンプルコードについては、「 [GetProcessSample04 sample](./getprocesssample04-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-162">For the complete C# sample code, see [GetProcessSample04 Sample](./getprocesssample04-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="e40c2-163">オブジェクトの種類と書式を定義する</span><span class="sxs-lookup"><span data-stu-id="e40c2-163">Define Object Types and Formatting</span></span>

<span data-ttu-id="e40c2-164">PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-164">PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="e40c2-165">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-165">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="e40c2-166">新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions/ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-166">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="e40c2-167">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="e40c2-167">Building the Cmdlet</span></span>

<span data-ttu-id="e40c2-168">コマンドレットを実装した後、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40c2-168">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="e40c2-169">コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40c2-169">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="e40c2-170">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="e40c2-170">Testing the Cmdlet</span></span>

<span data-ttu-id="e40c2-171">コマンドレットが PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-171">When your cmdlet has been registered with PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="e40c2-172">サンプルの Get Proc コマンドレットをテストして、エラーが報告されているかどうかを確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="e40c2-172">Let's test the sample Get-Proc cmdlet to see whether it reports an error:</span></span>

- <span data-ttu-id="e40c2-173">PowerShell を起動し、Get Proc コマンドレットを使用して "TEST" という名前のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e40c2-173">Start PowerShell, and use the Get-Proc cmdlet to retrieve the processes named "TEST".</span></span>

  ```powershell
  get-proc -name test
  ```

  <span data-ttu-id="e40c2-174">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e40c2-174">The following output appears.</span></span>

  ```
  get-proc : Operation is not valid due to the current state of the object.
  At line:1 char:9
  + get-proc  <<<< -name test
  ```

## <a name="see-also"></a><span data-ttu-id="e40c2-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="e40c2-175">See Also</span></span>

[<span data-ttu-id="e40c2-176">パイプライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="e40c2-176">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="e40c2-177">コマンドライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="e40c2-177">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="e40c2-178">最初のコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="e40c2-178">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="e40c2-179">[オブジェクトの種類と書式設定の拡張](/previous-versions/ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e40c2-179">[Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85))</span></span>

<span data-ttu-id="e40c2-180">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e40c2-180">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="e40c2-181">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="e40c2-181">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="e40c2-182">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="e40c2-182">Cmdlet Samples</span></span>](./cmdlet-samples.md)

[System.exception]: /dotnet/api/System.Exception
[System.Exception]: /dotnet/api/System.Exception
[システムの管理. ActionPreference]: /dotnet/api/System.Management.Automation.ActionPreference
[System.Management.Automation.ActionPreference]: /dotnet/api/System.Management.Automation.ActionPreference
[system.servicemodel メソッドを]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System.Management.Automation.Cmdlet.ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[WriteError (システム管理)]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System.Management.Automation.Cmdlet.WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System. Automation. コマンドレット]: /dotnet/api/System.Management.Automation.Cmdlet
[System.Management.Automation.Cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[ErrorCategory (システム管理)]: /dotnet/api/System.Management.Automation.ErrorCategory
[System.Management.Automation.ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[システムの管理. ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord
[System.Management.Automation.ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord

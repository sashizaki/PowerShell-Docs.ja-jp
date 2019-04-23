---
title: 未終了エラー レポート、コマンドレットに追加する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a1531a-a92a-4606-9d54-c5df80d34f33
caps.latest.revision: 8
ms.openlocfilehash: 3741982f81efa04d8fe7ab448fba5f2fdf4b0c01
ms.sourcegitcommit: f4bd4e116e22c8b5bfcb61680a7c42e58b4da93e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59984240"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a><span data-ttu-id="36593-102">終了しないエラーのレポートをコマンドレットに追加する</span><span class="sxs-lookup"><span data-stu-id="36593-102">Adding Non-Terminating Error Reporting to Your Cmdlet</span></span>

<span data-ttu-id="36593-103">コマンドレットは、呼び出すことで終了しないエラーを報告できる、 [System.Management.Automation.Cmdlet.WriteError][]メソッドと、引き続き現在の入力オブジェクトまたはそれ以上の受信を操作するオブジェクトをパイプラインします。</span><span class="sxs-lookup"><span data-stu-id="36593-103">Cmdlets can report nonterminating errors by calling the [System.Management.Automation.Cmdlet.WriteError][] method and still continue to operate on the current input object or on further incoming pipeline objects.</span></span>
<span data-ttu-id="36593-104">このセクションでは、その入力処理メソッドから終了しないエラーを報告するコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36593-104">This section explains how to create a cmdlet that reports nonterminating errors from its input processing methods.</span></span>

<span data-ttu-id="36593-105">終了しないエラー (だけでなく終了するエラー) のコマンドレットを渡す必要があります、 [System.Management.Automation.ErrorRecord][]エラーを識別するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="36593-105">For nonterminating errors (as well as terminating errors), the cmdlet must pass an [System.Management.Automation.ErrorRecord][] object identifying the error.</span></span>
<span data-ttu-id="36593-106">各 error レコードには、「エラー識別子」と呼ばれる一意の文字列によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="36593-106">Each error record is identified by a unique string called the "error identifier".</span></span>
<span data-ttu-id="36593-107">識別子、だけでなく、各エラーのカテゴリがによって定義される定数で指定された、 [System.Management.Automation.ErrorCategory][]列挙体。</span><span class="sxs-lookup"><span data-stu-id="36593-107">In addition to the identifier, the category of each error is specified by constants defined by a [System.Management.Automation.ErrorCategory][] enumeration.</span></span>
<span data-ttu-id="36593-108">ユーザーが設定して、カテゴリに基づいてエラーを表示できます、`$ErrorView`変数を"CategoryView"にします。</span><span class="sxs-lookup"><span data-stu-id="36593-108">The user can view errors based on their category by setting the `$ErrorView` variable to "CategoryView".</span></span>

<span data-ttu-id="36593-109">エラー レコードの詳細については、次を参照してください。 [Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="36593-109">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="36593-110">コマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="36593-110">Defining the Cmdlet</span></span>

<span data-ttu-id="36593-111">コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="36593-111">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span>
<span data-ttu-id="36593-112">このコマンドレットは、ため、ここで選択した動詞名は"Get"プロセスの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="36593-112">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span>
<span data-ttu-id="36593-113">(ほぼあらゆる種類の情報を取得するのに対応しているコマンドレットは、コマンドラインの入力を処理できます)承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="36593-113">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="36593-114">この Get-proc コマンドレットの定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="36593-114">The following is the definition for this Get-Proc cmdlet.</span></span>
<span data-ttu-id="36593-115">この定義の詳細が記載[最初のコマンドレットを作成](creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="36593-115">Details of this definition are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-parameters"></a><span data-ttu-id="36593-116">パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="36593-116">Defining Parameters</span></span>

<span data-ttu-id="36593-117">必要に応じて、コマンドレットは、入力を処理するためのパラメーターを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36593-117">If necessary, your cmdlet must define parameters for processing input.</span></span>
<span data-ttu-id="36593-118">この Get-proc コマンドレットを定義、**名前**パラメーター」の説明に従って[プロセス コマンド ライン入力パラメーターを追加する](adding-parameters-that-process-command-line-input.md)します。</span><span class="sxs-lookup"><span data-stu-id="36593-118">This Get-Proc cmdlet defines a **Name** parameter as described in [Adding Parameters that Process Command-Line Input](adding-parameters-that-process-command-line-input.md).</span></span>

<span data-ttu-id="36593-119">パラメーター宣言を次に示します、**名前**この Get-proc コマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="36593-119">Here is the parameter declaration for the **Name** parameter of this Get-Proc cmdlet.</span></span>

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

## <a name="overriding-input-processing-methods"></a><span data-ttu-id="36593-120">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="36593-120">Overriding Input Processing Methods</span></span>

<span data-ttu-id="36593-121">すべてのコマンドレットは、少なくとも 1 つの入力によって提供されるメソッドの処理をオーバーライドする必要があります、 [System.Management.Automation.Cmdlet][]クラス。</span><span class="sxs-lookup"><span data-stu-id="36593-121">All cmdlets must override at least one of the input processing methods provided by the [System.Management.Automation.Cmdlet][] class.</span></span>
<span data-ttu-id="36593-122">これらのメソッドは、後ほど[最初のコマンドレットを作成](creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="36593-122">These methods are discussed in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="36593-123">コマンドレットが処理されない各レコードできるだけ独立しています。</span><span class="sxs-lookup"><span data-stu-id="36593-123">Your cmdlet should handle each record as independently as possible.</span></span>

<span data-ttu-id="36593-124">この Get-proc コマンドレットよりも優先、 [System.Management.Automation.Cmdlet.ProcessRecord][]を処理するメソッド、**名前**ユーザーまたはスクリプトによって提供される入力パラメーター。</span><span class="sxs-lookup"><span data-stu-id="36593-124">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord][] method to handle the **Name** parameter for input provided by the user or a script.</span></span>
<span data-ttu-id="36593-125">名前が指定されていない場合、このメソッドは各要求のプロセス名またはすべてのプロセスのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="36593-125">This method will get the processes for each requested process name or all processes if no name is provided.</span></span>
<span data-ttu-id="36593-126">この上書きの詳細が記載[最初のコマンドレットを作成](creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="36593-126">Details of this override are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

### <a name="things-to-remember-when-reporting-errors"></a><span data-ttu-id="36593-127">エラーを報告する際の注意点</span><span class="sxs-lookup"><span data-stu-id="36593-127">Things to Remember When Reporting Errors</span></span>

<span data-ttu-id="36593-128">[System.Management.Automation.ErrorRecord][]コマンドレットが根本的に、例外エラーを書き込む必要がある場合に合格するオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="36593-128">The [System.Management.Automation.ErrorRecord][] object that the cmdlet passes when writing an error requires an exception at its core.</span></span>
<span data-ttu-id="36593-129">使用して例外を決定する際に、.NET のガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="36593-129">Follow the .NET guidelines when determining the exception to use.</span></span>
<span data-ttu-id="36593-130">基本的に、エラーは、既存の例外と同じである意味場合、コマンドレットを使用またはその例外から派生します。</span><span class="sxs-lookup"><span data-stu-id="36593-130">Basically, if the error is semantically the same as an existing exception, the cmdlet should use or derive from that exception.</span></span>
<span data-ttu-id="36593-131">それ以外の場合、新しい例外またはから直接例外階層を派生する必要がありますが、 [System.Exception][]クラス。</span><span class="sxs-lookup"><span data-stu-id="36593-131">Otherwise, it should derive a new exception or exception hierarchy directly from the [System.Exception][] class.</span></span>

<span data-ttu-id="36593-132">エラーの識別子 (ErrorRecord クラスの FullyQualifiedErrorId プロパティからアクセスする) を作成するときに、次に注意してください。</span><span class="sxs-lookup"><span data-stu-id="36593-132">When creating error identifiers (accessed through the FullyQualifiedErrorId property of the ErrorRecord class) keep the following in mind.</span></span>

- <span data-ttu-id="36593-133">対象となるは、エラーの入手元とは完全修飾識別子を検査する際に、どのようなエラーを確認できるように診断目的で使用して文字列。</span><span class="sxs-lookup"><span data-stu-id="36593-133">Use strings that are targeted for diagnostic purposes so that when inspecting the fully qualified identifier you can determine what the error is and where the error came from.</span></span>

- <span data-ttu-id="36593-134">適切な形式の完全修飾エラー識別子は、ようになります可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36593-134">A well formed fully qualified error identifier might be as follows.</span></span>

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand`

<span data-ttu-id="36593-135">前の例では、エラー識別子 (最初のトークン) を指定エラーを確認し、残りの部分では、エラーの出所を示します。</span><span class="sxs-lookup"><span data-stu-id="36593-135">Notice that in the previous example, the error identifier (the first token) designates what the error is and the remaining part indicates where the error came from.</span></span>

- <span data-ttu-id="36593-136">複雑なシナリオは、エラーの識別子は検査で解析できるドット区切りトークンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="36593-136">For more complex scenarios, the error identifier can be a dot separated token that can be parsed on inspection.</span></span>
  <span data-ttu-id="36593-137">これにより、エラーの識別子と、エラーの識別子、エラー カテゴリの部分にも分岐します。</span><span class="sxs-lookup"><span data-stu-id="36593-137">This allows you too branch on the parts of the error identifier as well as the error identifier and error category.</span></span>

<span data-ttu-id="36593-138">コマンドレットは、異なるコード パスを特定のエラー識別子を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="36593-138">The cmdlet should assign specific error identifiers to different code paths.</span></span>
<span data-ttu-id="36593-139">次の情報に注意してエラーの識別子の割り当てのために注意してください。</span><span class="sxs-lookup"><span data-stu-id="36593-139">Keep the following information in mind for assignment of error identifiers:</span></span>

- <span data-ttu-id="36593-140">エラー識別子は、コマンドレットのライフ サイクル全体で一定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36593-140">An error identifier should remain constant throughout the cmdlet life cycle.</span></span>
  <span data-ttu-id="36593-141">コマンドレットのバージョン間でのエラー識別子のセマンティクスは変更されません。</span><span class="sxs-lookup"><span data-stu-id="36593-141">Do not change the semantics of an error identifier between cmdlet versions.</span></span>

- <span data-ttu-id="36593-142">答えました報告されるエラーに対応するエラーの識別子のテキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="36593-142">Use text for an error identifier that tersely corresponds to the error being reported.</span></span>
  <span data-ttu-id="36593-143">空白や句読点を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="36593-143">Do not use white space or punctuation.</span></span>

- <span data-ttu-id="36593-144">再現可能なエラー識別子のみを生成するコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="36593-144">Have your cmdlet generate only error identifiers that are reproducible.</span></span>
  <span data-ttu-id="36593-145">たとえば、プロセス識別子を含む識別子は生成しません。</span><span class="sxs-lookup"><span data-stu-id="36593-145">For example, it should not generate an identifier that includes a process identifier.</span></span>
  <span data-ttu-id="36593-146">エラー識別子は、同じ問題が発生している他のユーザーに表示される識別子に対応する場合にのみ、ユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="36593-146">Error identifiers are useful to a user only when they correspond to identifiers that are seen by other users experiencing the same problem.</span></span>

<span data-ttu-id="36593-147">次の条件では、PowerShell によってハンドルされない例外はキャッチしません。</span><span class="sxs-lookup"><span data-stu-id="36593-147">Unhandled exceptions are not caught by PowerShell in the following conditions:</span></span>

- <span data-ttu-id="36593-148">コマンドレットは、新しいスレッドおよびスレッド ハンドルされない例外をスローすることで実行されているコードを作成する場合、PowerShell は、エラーはキャッチできないと、プロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="36593-148">If a cmdlet creates a new thread and code running in that thread throws an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>

- <span data-ttu-id="36593-149">オブジェクトは、そのデストラクターまたは Dispose メソッドでハンドルされない例外を発生させるコードが、PowerShell は、エラーはキャッチできないと、プロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="36593-149">If an object has code in its destructor or Dispose methods that causes an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>

## <a name="reporting-nonterminating-errors"></a><span data-ttu-id="36593-150">終了しないエラーの報告</span><span class="sxs-lookup"><span data-stu-id="36593-150">Reporting Nonterminating Errors</span></span>

<span data-ttu-id="36593-151">入力処理メソッドのいずれかが終了しないエラーを報告、出力ストリームを使用して、 [System.Management.Automation.Cmdlet.WriteError][]メソッド。</span><span class="sxs-lookup"><span data-stu-id="36593-151">Any one of the input processing methods can report a nonterminating error to the output stream using the [System.Management.Automation.Cmdlet.WriteError][] method.</span></span>

<span data-ttu-id="36593-152">呼び出しを示しますこの Get-proc コマンドレットからのコード例を次に示します[System.Management.Automation.Cmdlet.WriteError][]からのオーバーライドの中で、 [System.Management.Automation.Cmdlet.ProcessRecord][]メソッド。</span><span class="sxs-lookup"><span data-stu-id="36593-152">Here is a code example from this Get-Proc cmdlet that illustrates the call to [System.Management.Automation.Cmdlet.WriteError][] from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord][] method.</span></span>
<span data-ttu-id="36593-153">ここで、呼び出しには、コマンドレットは、指定されたプロセスの識別子のプロセスを見つけられない場合が行われます。</span><span class="sxs-lookup"><span data-stu-id="36593-153">In this case, the call is made if the cmdlet cannot find a process for a specified process identifier.</span></span>

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

### <a name="things-to-remember-about-writing-nonterminating-errors"></a><span data-ttu-id="36593-154">終了しないエラーの記述に関する注意点</span><span class="sxs-lookup"><span data-stu-id="36593-154">Things to Remember About Writing Nonterminating Errors</span></span>

<span data-ttu-id="36593-155">終了しないエラーでは、このコマンドレットは、各入力オブジェクトの特定のエラー識別子を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36593-155">For a nonterminating error, the cmdlet must generate a specific error identifier for each specific input object.</span></span>

<span data-ttu-id="36593-156">コマンドレットは頻繁に終了しないエラーによって生成された PowerShell アクションを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36593-156">A cmdlet frequently needs to modify the PowerShell action produced by a nonterminating error.</span></span>
<span data-ttu-id="36593-157">これを行うこと、`ErrorAction`と`ErrorVariable`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="36593-157">It can do this by defining the `ErrorAction` and `ErrorVariable` parameters.</span></span>
<span data-ttu-id="36593-158">定義する場合、`ErrorAction`パラメーター、コマンドレットは、ユーザー オプションを表示します[System.Management.Automation.ActionPreference][]を設定して、アクションも直接影響、`$ErrorActionPreference`変数。</span><span class="sxs-lookup"><span data-stu-id="36593-158">If defining the `ErrorAction` parameter, the cmdlet presents the user options [System.Management.Automation.ActionPreference][], you can also directly influence the action by setting the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="36593-159">終了しないエラーを保存、変数を使用して、コマンドレット、`ErrorVariable`パラメーターの設定の影響を受けません`ErrorAction`します。</span><span class="sxs-lookup"><span data-stu-id="36593-159">The cmdlet can save nonterminating errors to a variable using the `ErrorVariable` parameter, which is not affected by the setting of `ErrorAction`.</span></span>
<span data-ttu-id="36593-160">エラーは、変数名の前にプラス記号 (+) を追加することで、既存のエラー変数に追加できます。</span><span class="sxs-lookup"><span data-stu-id="36593-160">Failures can be appended to an existing error variable by adding a plus sign (+) to the front of the variable name.</span></span>

## <a name="code-sample"></a><span data-ttu-id="36593-161">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="36593-161">Code Sample</span></span>

<span data-ttu-id="36593-162">完全なC#サンプル コードは、「 [GetProcessSample04 サンプル](./getprocesssample04-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="36593-162">For the complete C# sample code, see [GetProcessSample04 Sample](./getprocesssample04-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="36593-163">オブジェクトの種類と書式設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="36593-163">Define Object Types and Formatting</span></span>

<span data-ttu-id="36593-164">PowerShell では、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="36593-164">PowerShell passes information between cmdlets using .NET objects.</span></span>
<span data-ttu-id="36593-165">その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36593-165">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span>
<span data-ttu-id="36593-166">新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。</span><span class="sxs-lookup"><span data-stu-id="36593-166">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="36593-167">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="36593-167">Building the Cmdlet</span></span>

<span data-ttu-id="36593-168">コマンドレットを実装するには、後にする必要がありますに登録する Windows PowerShell Windows PowerShell スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="36593-168">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span>
<span data-ttu-id="36593-169">コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。</span><span class="sxs-lookup"><span data-stu-id="36593-169">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="36593-170">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="36593-170">Testing the Cmdlet</span></span>

<span data-ttu-id="36593-171">PowerShell を使用した、コマンドレットを登録しているときに、コマンドラインで実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="36593-171">When your cmdlet has been registered with PowerShell, you can test it by running it on the command line.</span></span>
<span data-ttu-id="36593-172">エラーを報告するかどうかを確認するサンプル Get-proc コマンドレットをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="36593-172">Let's test the sample Get-Proc cmdlet to see whether it reports an error:</span></span>

- <span data-ttu-id="36593-173">PowerShell を起動し、Get-proc コマンドレットを使用して"TEST"という名前のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="36593-173">Start PowerShell, and use the Get-Proc cmdlet to retrieve the processes named "TEST".</span></span>

    ```powershell
    PS> get-proc -name test
    ```

<span data-ttu-id="36593-174">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="36593-174">The following output appears.</span></span>

    ```
    get-proc : Operation is not valid due to the current state of the object.
    At line:1 char:9
    + get-proc  <<<< -name test
    ```

## <a name="see-also"></a><span data-ttu-id="36593-175">参照</span><span class="sxs-lookup"><span data-stu-id="36593-175">See Also</span></span>

[<span data-ttu-id="36593-176">プロセス パイプラインの入力パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="36593-176">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="36593-177">コマンドライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="36593-177">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="36593-178">初めてのコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="36593-178">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="36593-179">オブジェクトの種類を拡張して、書式設定</span><span class="sxs-lookup"><span data-stu-id="36593-179">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="36593-180">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="36593-180">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="36593-181">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="36593-181">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="36593-182">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="36593-182">Cmdlet Samples</span></span>](./cmdlet-samples.md)

[System.Exception]: /dotnet/api/System.Exception
[System.Management.Automation.ActionPreference]: /dotnet/api/System.Management.Automation.ActionPreference
[System.Management.Automation.Cmdlet.ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System.Management.Automation.Cmdlet.WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System.Management.Automation.Cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[System.Management.Automation.ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System.Management.Automation.ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord

---
title: パイプライン入力を処理するパラメーターを追加する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], pipeline input
- parameters [PowerShell Programmer's Guide], pipeline input
ms.assetid: 09bf70a9-7c76-4ffe-b3f0-a1d5f10a0931
caps.latest.revision: 8
ms.openlocfilehash: 9ecb73a4138a5853fa5fb378874da2d81c5dbdba
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364601"
---
# <a name="adding-parameters-that-process-pipeline-input"></a><span data-ttu-id="984d3-102">パイプライン入力を処理するパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="984d3-102">Adding Parameters that Process Pipeline Input</span></span>

<span data-ttu-id="984d3-103">コマンドレットの1つの入力ソースは、上流のコマンドレットで発生したパイプライン上のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="984d3-103">One source of input for a cmdlet is an object on the pipeline that originates from an upstream cmdlet.</span></span> <span data-ttu-id="984d3-104">このセクションでは、コマンドレットがパイプラインオブジェクトを処理できるように、Get Proc コマンドレット ([最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関するページで説明) にパラメーターを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="984d3-104">This section describes how to add a parameter to the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process pipeline objects.</span></span>

<span data-ttu-id="984d3-105">この Get Proc コマンドレットは、パイプラインオブジェクトからの入力を受け入れ、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、コマンドラインでプロセスに関する情報を表示する `Name` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="984d3-105">This Get-Proc cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="984d3-106">コマンドレットクラスの定義</span><span class="sxs-lookup"><span data-stu-id="984d3-106">Defining the Cmdlet Class</span></span>

<span data-ttu-id="984d3-107">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="984d3-107">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="984d3-108">このコマンドレットはプロセス情報を取得するため、ここで選択した動詞名は "Get" です。</span><span class="sxs-lookup"><span data-stu-id="984d3-108">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="984d3-109">(情報を取得できるほとんどすべての種類のコマンドレットは、コマンドライン入力を処理できます)。承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="984d3-109">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="984d3-110">この Get Proc コマンドレットの定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="984d3-110">The following is the definition for this Get-Proc cmdlet.</span></span> <span data-ttu-id="984d3-111">この定義の詳細につい[ては、最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関する説明をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="984d3-111">Details of this definition are given in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a><span data-ttu-id="984d3-112">パイプラインからの入力の定義</span><span class="sxs-lookup"><span data-stu-id="984d3-112">Defining Input from the Pipeline</span></span>

<span data-ttu-id="984d3-113">このセクションでは、コマンドレットのパイプラインからの入力を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="984d3-113">This section describes how to define input from the pipeline for a cmdlet.</span></span> <span data-ttu-id="984d3-114">この Get Proc コマンドレットは、「[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)」で説明されているように、`Name` パラメーターを表すプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="984d3-114">This Get-Proc cmdlet defines a property that represents the `Name` parameter as described in [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span> <span data-ttu-id="984d3-115">(パラメーターの宣言に関する一般的な情報については、「」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="984d3-115">(See that topic for general information about declaring parameters.)</span></span>

<span data-ttu-id="984d3-116">ただし、コマンドレットでパイプラインの入力を処理する必要がある場合は、Windows PowerShell ランタイムによって入力値にバインドされたパラメーターを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="984d3-116">However, when a cmdlet needs to process pipeline input, it must have its parameters bound to input values by the Windows PowerShell runtime.</span></span> <span data-ttu-id="984d3-117">これを行うには、`ValueFromPipeline` キーワードを追加するか、または `ValueFromPipelineByProperty` キーワードを[system.object 属性宣言](/dotnet/api/System.Management.Automation.ParameterAttribute)に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="984d3-117">To do this, you must add the `ValueFromPipeline` keyword or add the `ValueFromPipelineByProperty` keyword to the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="984d3-118">コマンドレットが入力オブジェクト全体にアクセスする場合は、`ValueFromPipeline` キーワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="984d3-118">Specify the `ValueFromPipeline` keyword if the cmdlet accesses the complete input object.</span></span> <span data-ttu-id="984d3-119">コマンドレットがオブジェクトのプロパティのみにアクセスする場合は、`ValueFromPipelineByProperty` を指定します。</span><span class="sxs-lookup"><span data-stu-id="984d3-119">Specify the `ValueFromPipelineByProperty` if the cmdlet accesses only a property of the object.</span></span>

<span data-ttu-id="984d3-120">パイプライン入力を受け入れるこの Get Proc コマンドレットの `Name` パラメーターのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="984d3-120">Here is the parameter declaration for the `Name` parameter of this Get-Proc cmdlet that accepts pipeline input.</span></span>

[!code-csharp[GetProcessSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L35-L44 "GetProcessSample03.cs")]

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

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#GetProc03VBNameParameter](Msh_samplesgetproc03#GetProc03VBNameParameter)]  -->

<span data-ttu-id="984d3-121">前の宣言では、`ValueFromPipeline` キーワードを `true` に設定しています。これにより、オブジェクトがパラメーターと同じ型である場合、または同じ型に強制的に変換できる場合は、Windows PowerShell ランタイムがパラメーターを受信オブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="984d3-121">The previous declaration sets the `ValueFromPipeline` keyword to `true` so that the Windows PowerShell runtime will bind the parameter to the incoming object if the object is the same type as the parameter, or if it can be coerced to the same type.</span></span> <span data-ttu-id="984d3-122">`ValueFromPipelineByPropertyName` キーワードも `true` に設定されます。これにより、Windows PowerShell ランタイムは `Name` プロパティの受信オブジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="984d3-122">The `ValueFromPipelineByPropertyName` keyword is also set to `true` so that the Windows PowerShell runtime will check the incoming object for a `Name` property.</span></span> <span data-ttu-id="984d3-123">受信オブジェクトにこのようなプロパティがある場合、ランタイムは、受信オブジェクトの `Name` プロパティに `Name` パラメーターをバインドします。</span><span class="sxs-lookup"><span data-stu-id="984d3-123">If the incoming object has such a property, the runtime will bind the `Name` parameter to the `Name` property of the incoming object.</span></span>

> [!NOTE]
> <span data-ttu-id="984d3-124">パラメーターの `ValueFromPipeline` attribute キーワードの設定は、`ValueFromPipelineByPropertyName` キーワードの設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="984d3-124">The setting of the `ValueFromPipeline` attribute keyword for a parameter takes precedence over the setting for the `ValueFromPipelineByPropertyName` keyword.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="984d3-125">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="984d3-125">Overriding an Input Processing Method</span></span>

<span data-ttu-id="984d3-126">コマンドレットがパイプライン入力を処理する場合は、適切な入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="984d3-126">If your cmdlet is to handle pipeline input, it needs to override the appropriate input processing methods.</span></span> <span data-ttu-id="984d3-127">基本的な入力処理方法は、[最初のコマンドレットを作成するとき](./creating-a-cmdlet-without-parameters.md)に導入されます。</span><span class="sxs-lookup"><span data-stu-id="984d3-127">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="984d3-128">この Get Proc コマンドレットは、ユーザーまたはスクリプトによって指定された `Name` パラメーターの入力を処理するために、 [system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="984d3-128">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="984d3-129">このメソッドは、要求された各プロセス名のプロセスを取得します。名前が指定されていない場合は、すべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="984d3-129">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="984d3-130">[WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)の呼び出しが、出力オブジェクトをパイプラインに送信するための出力機構として使用されていることに注意し[てください。](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)</span><span class="sxs-lookup"><span data-stu-id="984d3-130">Notice that within [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="984d3-131">この呼び出しの2番目のパラメーターである `enumerateCollection`は `true` に設定され、プロセスオブジェクトの配列を列挙し、一度に1つのプロセスをコマンドラインに書き込むように Windows PowerShell ランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="984d3-131">The second parameter of this call, `enumerateCollection`, is set to `true` to tell the Windows PowerShell runtime to enumerate the array of process objects, and write one process at a time to the command line.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument of this call tells
      // PowerShell to enumerate the array, and send one process at a
      // time to the pipeline.
      WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    } // End foreach (string name...).
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()
    Dim processes As Process()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        processes = Process.GetProcesses()
    Else

        '/ If process names are specified, write the processes to the
        '/ pipeline to display them or make them available to the next cmdlet.
        For Each name As String In processNames
            '/ The second parameter of this call tells PowerShell to enumerate the
            '/ array, and send one process at a time to the pipeline.
            WriteObject(Process.GetProcessesByName(name), True)
        Next
    End If

End Sub 'ProcessRecord
```

## <a name="code-sample"></a><span data-ttu-id="984d3-132">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="984d3-132">Code Sample</span></span>

<span data-ttu-id="984d3-133">完全なC#サンプルコードについては、「 [GetProcessSample03 sample](./getprocesssample03-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="984d3-133">For the complete C# sample code, see [GetProcessSample03 Sample](./getprocesssample03-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="984d3-134">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="984d3-134">Defining Object Types and Formatting</span></span>

<span data-ttu-id="984d3-135">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="984d3-135">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="984d3-136">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="984d3-136">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="984d3-137">新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="984d3-137">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="984d3-138">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="984d3-138">Building the Cmdlet</span></span>

<span data-ttu-id="984d3-139">コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="984d3-139">After implementing a cmdlet it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="984d3-140">コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="984d3-140">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="984d3-141">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="984d3-141">Testing the Cmdlet</span></span>

<span data-ttu-id="984d3-142">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行してテストします。</span><span class="sxs-lookup"><span data-stu-id="984d3-142">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="984d3-143">たとえば、サンプルコマンドレットのコードをテストします。</span><span class="sxs-lookup"><span data-stu-id="984d3-143">For example, test the code for the sample cmdlet.</span></span> <span data-ttu-id="984d3-144">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="984d3-144">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="984d3-145">Windows PowerShell プロンプトで、次のコマンドを入力して、パイプラインを介してプロセス名を取得します。</span><span class="sxs-lookup"><span data-stu-id="984d3-145">At the Windows PowerShell prompt, enter the following commands to retrieve the process names through the pipeline.</span></span>

    ```powershell
    PS> type ProcessNames | get-proc
    ```

<span data-ttu-id="984d3-146">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="984d3-146">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----   ----- -----   ------    --  -----------
        809      21  40856    4448    147    9.50  2288  iexplore
        737      21  26036   16348    144   22.03  3860  iexplore
         39       2   1024     388     30    0.08  3396  notepad
       3927      62  71836   26984    467  195.19  1848  OUTLOOK
    ```

- <span data-ttu-id="984d3-147">次の行を入力して、"IEXPLORE.EXE" というプロセスから `Name` プロパティを持つプロセスオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="984d3-147">Enter the following lines to get the process objects that have a `Name` property from the processes called "IEXPLORE".</span></span> <span data-ttu-id="984d3-148">この例では、(Windows PowerShell によって提供される) `Get-Process` コマンドレットを上流のコマンドとして使用して、"IEXPLORE.EXE" プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="984d3-148">This example uses the `Get-Process` cmdlet (provided by Windows PowerShell) as an upstream command to retrieve the "IEXPLORE" processes.</span></span>

    ```powershell
    PS> get-process iexplore | get-proc
    ```

<span data-ttu-id="984d3-149">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="984d3-149">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----      ----- -----   ------     -- -----------
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
    ```

## <a name="see-also"></a><span data-ttu-id="984d3-150">参照</span><span class="sxs-lookup"><span data-stu-id="984d3-150">See Also</span></span>

[<span data-ttu-id="984d3-151">コマンドライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="984d3-151">Adding Parameters that Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="984d3-152">最初のコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="984d3-152">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="984d3-153">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="984d3-153">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="984d3-154">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="984d3-154">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="984d3-155">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="984d3-155">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="984d3-156">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="984d3-156">Cmdlet Samples</span></span>](./cmdlet-samples.md)

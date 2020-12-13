---
ms.date: 09/13/2016
ms.topic: reference
title: パイプライン入力を処理するパラメーターを追加する
description: パイプライン入力を処理するパラメーターを追加する
ms.openlocfilehash: b150d5be93207d9c010a6d2d4de901b4526f1d79
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668356"
---
# <a name="adding-parameters-that-process-pipeline-input"></a><span data-ttu-id="aad74-103">パイプライン入力を処理するパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="aad74-103">Adding Parameters that Process Pipeline Input</span></span>

<span data-ttu-id="aad74-104">コマンドレットの1つの入力ソースは、上流のコマンドレットで発生したパイプライン上のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="aad74-104">One source of input for a cmdlet is an object on the pipeline that originates from an upstream cmdlet.</span></span> <span data-ttu-id="aad74-105">このセクションでは、コマンドレットがパイプラインオブジェクトを処理できるように、Get-Proc コマンドレット ( [最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関するページで説明) にパラメーターを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aad74-105">This section describes how to add a parameter to the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process pipeline objects.</span></span>

<span data-ttu-id="aad74-106">この Get-Proc コマンドレットは、 `Name` パイプラインオブジェクトからの入力を受け入れるパラメーターを使用し、指定された名前に基づいてローカルコンピューターからプロセス情報を取得し、コマンドラインでプロセスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="aad74-106">This Get-Proc cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="aad74-107">コマンドレットクラスの定義</span><span class="sxs-lookup"><span data-stu-id="aad74-107">Defining the Cmdlet Class</span></span>

<span data-ttu-id="aad74-108">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="aad74-108">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="aad74-109">このコマンドレットはプロセス情報を取得するため、ここで選択した動詞名は "Get" です。</span><span class="sxs-lookup"><span data-stu-id="aad74-109">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="aad74-110">(情報を取得できるほとんどすべての種類のコマンドレットは、コマンドライン入力を処理できます)。承認されたコマンドレット動詞の詳細については、「 [コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aad74-110">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="aad74-111">この Get-Proc コマンドレットの定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aad74-111">The following is the definition for this Get-Proc cmdlet.</span></span> <span data-ttu-id="aad74-112">この定義の詳細につい [ては、最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関する説明をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="aad74-112">Details of this definition are given in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a><span data-ttu-id="aad74-113">パイプラインからの入力の定義</span><span class="sxs-lookup"><span data-stu-id="aad74-113">Defining Input from the Pipeline</span></span>

<span data-ttu-id="aad74-114">このセクションでは、コマンドレットのパイプラインからの入力を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aad74-114">This section describes how to define input from the pipeline for a cmdlet.</span></span> <span data-ttu-id="aad74-115">この Get-Proc コマンドレットは、 `Name` 「 [コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)」で説明されているように、パラメーターを表すプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="aad74-115">This Get-Proc cmdlet defines a property that represents the `Name` parameter as described in [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>
<span data-ttu-id="aad74-116">(パラメーターの宣言に関する一般的な情報については、「」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="aad74-116">(See that topic for general information about declaring parameters.)</span></span>

<span data-ttu-id="aad74-117">ただし、コマンドレットでパイプラインの入力を処理する必要がある場合は、Windows PowerShell ランタイムによって入力値にバインドされたパラメーターを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="aad74-117">However, when a cmdlet needs to process pipeline input, it must have its parameters bound to input values by the Windows PowerShell runtime.</span></span> <span data-ttu-id="aad74-118">これを行うには、キーワードを追加するか、またはキーワードを system.string 属性宣言に追加する必要があり `ValueFromPipeline` `ValueFromPipelineByProperty` ます。 [](/dotnet/api/System.Management.Automation.ParameterAttribute)</span><span class="sxs-lookup"><span data-stu-id="aad74-118">To do this, you must add the `ValueFromPipeline` keyword or add the `ValueFromPipelineByProperty` keyword to the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="aad74-119">`ValueFromPipeline`コマンドレットが入力オブジェクト全体にアクセスする場合は、キーワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="aad74-119">Specify the `ValueFromPipeline` keyword if the cmdlet accesses the complete input object.</span></span> <span data-ttu-id="aad74-120">`ValueFromPipelineByProperty`コマンドレットがオブジェクトのプロパティのみにアクセスする場合は、を指定します。</span><span class="sxs-lookup"><span data-stu-id="aad74-120">Specify the `ValueFromPipelineByProperty` if the cmdlet accesses only a property of the object.</span></span>

<span data-ttu-id="aad74-121">`Name`パイプラインの入力を受け入れるこの Get-Proc コマンドレットのパラメーターのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aad74-121">Here is the parameter declaration for the `Name` parameter of this Get-Proc cmdlet that accepts pipeline input.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="35-44":::

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

<span data-ttu-id="aad74-122">前の宣言では、 `ValueFromPipeline` キーワードをに設定します `true` 。これにより、オブジェクトがパラメーターと同じ型である場合、または同じ型に強制的に変換できる場合は、Windows PowerShell ランタイムによってパラメーターが受信オブジェクトにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="aad74-122">The previous declaration sets the `ValueFromPipeline` keyword to `true` so that the Windows PowerShell runtime will bind the parameter to the incoming object if the object is the same type as the parameter, or if it can be coerced to the same type.</span></span> <span data-ttu-id="aad74-123">`ValueFromPipelineByPropertyName`キーワードは、 `true` Windows PowerShell ランタイムがプロパティの受信オブジェクトを確認するようににも設定されてい `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="aad74-123">The `ValueFromPipelineByPropertyName` keyword is also set to `true` so that the Windows PowerShell runtime will check the incoming object for a `Name` property.</span></span> <span data-ttu-id="aad74-124">受信オブジェクトにこのようなプロパティがある場合、ランタイムは、 `Name` 受信したオブジェクトのプロパティにパラメーターをバインドし `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="aad74-124">If the incoming object has such a property, the runtime will bind the `Name` parameter to the `Name` property of the incoming object.</span></span>

> [!NOTE]
> <span data-ttu-id="aad74-125">`ValueFromPipeline`パラメーターの属性キーワードの設定は、キーワードの設定よりも優先され `ValueFromPipelineByPropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="aad74-125">The setting of the `ValueFromPipeline` attribute keyword for a parameter takes precedence over the setting for the `ValueFromPipelineByPropertyName` keyword.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="aad74-126">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="aad74-126">Overriding an Input Processing Method</span></span>

<span data-ttu-id="aad74-127">コマンドレットがパイプライン入力を処理する場合は、適切な入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aad74-127">If your cmdlet is to handle pipeline input, it needs to override the appropriate input processing methods.</span></span> <span data-ttu-id="aad74-128">基本的な入力処理方法は、 [最初のコマンドレットを作成するとき](./creating-a-cmdlet-without-parameters.md)に導入されます。</span><span class="sxs-lookup"><span data-stu-id="aad74-128">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="aad74-129">この Get-Proc コマンドレットは [、](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) `Name` ユーザーまたはスクリプトによって指定されたパラメーター入力を処理するために、system.object メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="aad74-129">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="aad74-130">このメソッドは、要求された各プロセス名のプロセスを取得します。名前が指定されていない場合は、すべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="aad74-130">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="aad74-131">[WriteObject (system.object, system.string)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)の呼び出しが、出力オブジェクトをパイプラインに送信するための出力機構として使用されていることに注意し[てください。](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)</span><span class="sxs-lookup"><span data-stu-id="aad74-131">Notice that within [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="aad74-132">この呼び出しの2番目のパラメーターは、をに設定して、 `enumerateCollection` `true` プロセスオブジェクトの配列を列挙し、一度に1つのプロセスをコマンドラインに書き込むように Windows PowerShell ランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="aad74-132">The second parameter of this call, `enumerateCollection`, is set to `true` to tell the Windows PowerShell runtime to enumerate the array of process objects, and write one process at a time to the command line.</span></span>

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

## <a name="code-sample"></a><span data-ttu-id="aad74-133">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="aad74-133">Code Sample</span></span>

<span data-ttu-id="aad74-134">完全な C# サンプルコードについては、「 [GetProcessSample03 sample](./getprocesssample03-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aad74-134">For the complete C# sample code, see [GetProcessSample03 Sample](./getprocesssample03-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="aad74-135">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="aad74-135">Defining Object Types and Formatting</span></span>

<span data-ttu-id="aad74-136">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="aad74-136">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="aad74-137">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="aad74-137">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="aad74-138">新しい型を定義する、または既存の型を拡張する方法の詳細については、「 [オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aad74-138">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="aad74-139">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="aad74-139">Building the Cmdlet</span></span>

<span data-ttu-id="aad74-140">コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aad74-140">After implementing a cmdlet it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="aad74-141">コマンドレットの登録の詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aad74-141">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="aad74-142">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="aad74-142">Testing the Cmdlet</span></span>

<span data-ttu-id="aad74-143">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行してテストします。</span><span class="sxs-lookup"><span data-stu-id="aad74-143">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="aad74-144">たとえば、サンプルコマンドレットのコードをテストします。</span><span class="sxs-lookup"><span data-stu-id="aad74-144">For example, test the code for the sample cmdlet.</span></span> <span data-ttu-id="aad74-145">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aad74-145">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="aad74-146">Windows PowerShell プロンプトで、次のコマンドを入力して、パイプラインを介してプロセス名を取得します。</span><span class="sxs-lookup"><span data-stu-id="aad74-146">At the Windows PowerShell prompt, enter the following commands to retrieve the process names through the pipeline.</span></span>

  ```powershell
  PS> type ProcessNames | get-proc
  ```

  <span data-ttu-id="aad74-147">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aad74-147">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      809      21  40856    4448    147    9.50  2288  iexplore
      737      21  26036   16348    144   22.03  3860  iexplore
       39       2   1024     388     30    0.08  3396  notepad
     3927      62  71836   26984    467  195.19  1848  OUTLOOK
  ```

- <span data-ttu-id="aad74-148">次の行を入力して、 `Name` "iexplore.exe" というプロセスのプロパティを持つプロセスオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="aad74-148">Enter the following lines to get the process objects that have a `Name` property from the processes called "IEXPLORE".</span></span> <span data-ttu-id="aad74-149">この例では、 `Get-Process` コマンドレット (Windows PowerShell によって提供) をアップストリームコマンドとして使用して、"iexplore.exe" プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="aad74-149">This example uses the `Get-Process` cmdlet (provided by Windows PowerShell) as an upstream command to retrieve the "IEXPLORE" processes.</span></span>

  ```powershell
  PS> get-process iexplore | get-proc
  ```

  <span data-ttu-id="aad74-150">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aad74-150">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
  ```

## <a name="see-also"></a><span data-ttu-id="aad74-151">参照</span><span class="sxs-lookup"><span data-stu-id="aad74-151">See Also</span></span>

[<span data-ttu-id="aad74-152">コマンドライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="aad74-152">Adding Parameters that Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="aad74-153">最初のコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="aad74-153">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="aad74-154">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="aad74-154">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="aad74-155">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="aad74-155">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="aad74-156">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="aad74-156">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="aad74-157">コマンドレット サンプル</span><span class="sxs-lookup"><span data-stu-id="aad74-157">Cmdlet Samples</span></span>](./cmdlet-samples.md)

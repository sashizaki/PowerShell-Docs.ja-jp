---
title: パイプラインの入力を処理するパラメーターの追加 |Microsoft Docs
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
ms.openlocfilehash: 34643d20c16f8cc45e7fb20dc2a87d78b18bbf10
ms.sourcegitcommit: f60fa420bdc81db174e6168d3aeb11371e483162
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "67298642"
---
# <a name="adding-parameters-that-process-pipeline-input"></a><span data-ttu-id="b1c9c-102">パイプライン入力を処理するパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="b1c9c-102">Adding Parameters that Process Pipeline Input</span></span>

<span data-ttu-id="b1c9c-103">コマンドレットの入力の 1 つのソースは、アップ ストリームのコマンドレットから発信されたパイプラインにオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-103">One source of input for a cmdlet is an object on the pipeline that originates from an upstream cmdlet.</span></span> <span data-ttu-id="b1c9c-104">ここが Get-proc コマンドレットにパラメーターを追加する方法について説明します (で説明されている[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)) コマンドレットは、パイプライン オブジェクトを処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-104">This section describes how to add a parameter to the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process pipeline objects.</span></span>

<span data-ttu-id="b1c9c-105">この Get-proc コマンドレットを使用して、`Name`パイプライン オブジェクトからの入力を受け付けるパラメーターは、指定された名前に基づいて、ローカル コンピューターからプロセス情報を取得し、コマンドラインでのプロセスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-105">This Get-Proc cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="b1c9c-106">コマンドレット クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-106">Defining the Cmdlet Class</span></span>

<span data-ttu-id="b1c9c-107">コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-107">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="b1c9c-108">このコマンドレットは、ため、ここで選択した動詞名は"Get"プロセスの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-108">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="b1c9c-109">(ほぼあらゆる種類の情報を取得するのに対応しているコマンドレットは、コマンドラインの入力を処理できます)承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-109">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="b1c9c-110">この Get-proc コマンドレットの定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-110">The following is the definition for this Get-Proc cmdlet.</span></span> <span data-ttu-id="b1c9c-111">この定義の詳細が記載[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-111">Details of this definition are given in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a><span data-ttu-id="b1c9c-112">パイプラインから入力を定義します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-112">Defining Input from the Pipeline</span></span>

<span data-ttu-id="b1c9c-113">このセクションでは、コマンドレットのパイプラインからの入力を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-113">This section describes how to define input from the pipeline for a cmdlet.</span></span> <span data-ttu-id="b1c9c-114">この Get-proc コマンドレットを表すプロパティの定義、`Name`パラメーター」の説明に従って[そのプロセスのコマンドラインの入力パラメーターを追加する](./adding-parameters-that-process-command-line-input.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-114">This Get-Proc cmdlet defines a property that represents the `Name` parameter as described in [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span> <span data-ttu-id="b1c9c-115">(パラメーターの宣言に関する全般情報のトピックを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-115">(See that topic for general information about declaring parameters.)</span></span>

<span data-ttu-id="b1c9c-116">ただし、コマンドレットは、パイプラインの入力を処理する必要がある、ときに、Windows PowerShell ランタイムによって入力値にバインドされたパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-116">However, when a cmdlet needs to process pipeline input, it must have its parameters bound to input values by the Windows PowerShell runtime.</span></span> <span data-ttu-id="b1c9c-117">これを行うには、追加する必要があります、`ValueFromPipeline`キーワードを追加または、`ValueFromPipelineByProperty`キーワードを[System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性宣言。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-117">To do this, you must add the `ValueFromPipeline` keyword or add the `ValueFromPipelineByProperty` keyword to the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="b1c9c-118">指定、`ValueFromPipeline`コマンドレットは、完全な入力オブジェクトにアクセスする場合は、キーワード。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-118">Specify the `ValueFromPipeline` keyword if the cmdlet accesses the complete input object.</span></span> <span data-ttu-id="b1c9c-119">指定、`ValueFromPipelineByProperty`コマンドレットは、オブジェクトのプロパティのみにアクセスする場合。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-119">Specify the `ValueFromPipelineByProperty` if the cmdlet accesses only a property of the object.</span></span>

<span data-ttu-id="b1c9c-120">パラメーター宣言を次に示します、`Name`パイプライン入力を受け付けるこの Get-proc コマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-120">Here is the parameter declaration for the `Name` parameter of this Get-Proc cmdlet that accepts pipeline input.</span></span>

[!code-csharp[GetProcessSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L35-L44 "GetProcessSample03.cs")]

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

<span data-ttu-id="b1c9c-121">前の宣言のセット、`ValueFromPipeline`キーワードを`true`Windows PowerShell ランタイムは、オブジェクトが、パラメーターと同じ型である場合に、受信オブジェクトへのパラメーターをバインドはまたは場合に、同じ型に強制的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-121">The previous declaration sets the `ValueFromPipeline` keyword to `true` so that the Windows PowerShell runtime will bind the parameter to the incoming object if the object is the same type as the parameter, or if it can be coerced to the same type.</span></span> <span data-ttu-id="b1c9c-122">`ValueFromPipelineByPropertyName`キーワードの設定も`true`、Windows PowerShell ランタイムは、受信オブジェクトを確認できるように、`Name`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-122">The `ValueFromPipelineByPropertyName` keyword is also set to `true` so that the Windows PowerShell runtime will check the incoming object for a `Name` property.</span></span> <span data-ttu-id="b1c9c-123">受信のオブジェクトは、このようなプロパティを持っている場合、ランタイムはバインド、`Name`パラメーターを`Name`受信オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-123">If the incoming object has such a property, the runtime will bind the `Name` parameter to the `Name` property of the incoming object.</span></span>

> [!NOTE]
> <span data-ttu-id="b1c9c-124">設定、`ValueFromPipeline`キーワード属性パラメーターの設定よりも優先、`ValueFromPipelineByPropertyName`キーワード。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-124">The setting of the `ValueFromPipeline` attribute keyword for a parameter takes precedence over the setting for the `ValueFromPipelineByPropertyName` keyword.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="b1c9c-125">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-125">Overriding an Input Processing Method</span></span>

<span data-ttu-id="b1c9c-126">コマンドレットをパイプラインの入力を処理する場合は、その適切な入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-126">If your cmdlet is to handle pipeline input, it needs to override the appropriate input processing methods.</span></span> <span data-ttu-id="b1c9c-127">基本的な入力処理メソッドがで導入された[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-127">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="b1c9c-128">この Get-proc コマンドレットよりも優先、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)を処理するメソッド、`Name`ユーザーまたはスクリプトによって提供されるパラメーターの入力。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-128">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="b1c9c-129">名前が指定されていない場合、このメソッドは各要求のプロセス名またはすべてのプロセスのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-129">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="b1c9c-130">わかります[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)への呼び出し[WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)に出力オブジェクトを送信するための出力機構は、パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-130">Notice that within [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="b1c9c-131">この呼び出しの 2 番目のパラメーター`enumerateCollection`に設定されている`true`、プロセス オブジェクトの配列を列挙し、コマンドラインに、一度に 1 つのプロセスを記述する Windows PowerShell ランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-131">The second parameter of this call, `enumerateCollection`, is set to `true` to tell the Windows PowerShell runtime to enumerate the array of process objects, and write one process at a time to the command line.</span></span>

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

## <a name="code-sample"></a><span data-ttu-id="b1c9c-132">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="b1c9c-132">Code Sample</span></span>

<span data-ttu-id="b1c9c-133">完全なC#サンプル コードは、「 [GetProcessSample03 サンプル](./getprocesssample03-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-133">For the complete C# sample code, see [GetProcessSample03 Sample](./getprocesssample03-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="b1c9c-134">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="b1c9c-134">Defining Object Types and Formatting</span></span>

<span data-ttu-id="b1c9c-135">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-135">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="b1c9c-136">その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-136">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="b1c9c-137">新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](/previous-versions//ms714665(v=vs.85))します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-137">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="b1c9c-138">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="b1c9c-138">Building the Cmdlet</span></span>

<span data-ttu-id="b1c9c-139">Windows PowerShell を使って Windows PowerShell を使用した登録する必要がありますコマンドレットの実装後にスナップインです。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-139">After implementing a cmdlet it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="b1c9c-140">コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](/previous-versions//ms714644(v=vs.85))します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-140">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="b1c9c-141">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="b1c9c-141">Testing the Cmdlet</span></span>

<span data-ttu-id="b1c9c-142">Windows PowerShell コマンドレットが登録されて、コマンドラインで実行してテストします。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-142">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="b1c9c-143">たとえば、サンプルのコマンドレットのコードをテストします。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-143">For example, test the code for the sample cmdlet.</span></span> <span data-ttu-id="b1c9c-144">詳細については、コマンドラインからコマンドレットを使用して、次を参照してください。、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-144">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="b1c9c-145">Windows PowerShell プロンプトで、パイプラインを介してプロセス名を取得する次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-145">At the Windows PowerShell prompt, enter the following commands to retrieve the process names through the pipeline.</span></span>

    ```powershell
    PS> type ProcessNames | get-proc
    ```

<span data-ttu-id="b1c9c-146">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-146">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----   ----- -----   ------    --  -----------
        809      21  40856    4448    147    9.50  2288  iexplore
        737      21  26036   16348    144   22.03  3860  iexplore
         39       2   1024     388     30    0.08  3396  notepad
       3927      62  71836   26984    467  195.19  1848  OUTLOOK
    ```

- <span data-ttu-id="b1c9c-147">次の行を取得しているプロセス オブジェクトを入力してください、 `Name` "IEXPLORE"と呼ばれるプロセスからのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-147">Enter the following lines to get the process objects that have a `Name` property from the processes called "IEXPLORE".</span></span> <span data-ttu-id="b1c9c-148">この例では、`Get-Process`コマンドレットが (Windows PowerShell によって提供される)"と、IEXPLORE"プロセスを取得するアップ ストリームのコマンドとして。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-148">This example uses the `Get-Process` cmdlet (provided by Windows PowerShell) as an upstream command to retrieve the "IEXPLORE" processes.</span></span>

    ```powershell
    PS> get-process iexplore | get-proc
    ```

<span data-ttu-id="b1c9c-149">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-149">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----      ----- -----   ------     -- -----------
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
    ```

## <a name="see-also"></a><span data-ttu-id="b1c9c-150">参照</span><span class="sxs-lookup"><span data-stu-id="b1c9c-150">See Also</span></span>

[<span data-ttu-id="b1c9c-151">コマンドラインの入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="b1c9c-151">Adding Parameters that Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="b1c9c-152">初めてのコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1c9c-152">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="b1c9c-153">[オブジェクトの種類を拡張して、書式設定](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="b1c9c-153">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="b1c9c-154">[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="b1c9c-154">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="b1c9c-155">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="b1c9c-155">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="b1c9c-156">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="b1c9c-156">Cmdlet Samples</span></span>](./cmdlet-samples.md)

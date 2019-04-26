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
ms.openlocfilehash: bd52dc8aee7975d0899083a5c2f595b17690dc33
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068761"
---
# <a name="adding-parameters-that-process-pipeline-input"></a><span data-ttu-id="18791-102">パイプライン入力を処理するパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="18791-102">Adding Parameters that Process Pipeline Input</span></span>

<span data-ttu-id="18791-103">コマンドレットの入力の 1 つのソースは、アップ ストリームのコマンドレットから発信されたパイプラインにオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="18791-103">One source of input for a cmdlet is an object on the pipeline that originates from an upstream cmdlet.</span></span> <span data-ttu-id="18791-104">ここが Get-proc コマンドレットにパラメーターを追加する方法について説明します (で説明されている[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)) コマンドレットは、パイプライン オブジェクトを処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="18791-104">This section describes how to add a parameter to the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process pipeline objects.</span></span>

<span data-ttu-id="18791-105">この Get-proc コマンドレットを使用して、`Name`パイプライン オブジェクトからの入力を受け付けるパラメーターは、指定された名前に基づいて、ローカル コンピューターからプロセス情報を取得し、コマンドラインでのプロセスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="18791-105">This Get-Proc cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

<span data-ttu-id="18791-106">このセクションのトピックで、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="18791-106">Topics in this section include the following:</span></span>

- [<span data-ttu-id="18791-107">コマンドレット クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="18791-107">Defining the Cmdlet Class</span></span>](#Defining-the-Cmdlet-Class)

- [<span data-ttu-id="18791-108">パイプラインから入力を定義します。</span><span class="sxs-lookup"><span data-stu-id="18791-108">Defining Input from the Pipeline</span></span>](#Defining-Input-from-the-Pipeline)

- [<span data-ttu-id="18791-109">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="18791-109">Overriding an Input Processing Method</span></span>](#Overriding-an-Input-Processing-Method)

- [<span data-ttu-id="18791-110">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="18791-110">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="18791-111">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="18791-111">Defining Object Types and Formatting</span></span>](#Defining-Object-Types-and-Formatting)

- [<span data-ttu-id="18791-112">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="18791-112">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="18791-113">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="18791-113">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="18791-114">コマンドレット クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="18791-114">Defining the Cmdlet Class</span></span>

<span data-ttu-id="18791-115">コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="18791-115">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="18791-116">このコマンドレットは、ため、ここで選択した動詞名は"Get"プロセスの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="18791-116">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="18791-117">(ほぼあらゆる種類の情報を取得するのに対応しているコマンドレットは、コマンドラインの入力を処理できます)承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="18791-117">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="18791-118">この Get-proc コマンドレットの定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="18791-118">The following is the definition for this Get-Proc cmdlet.</span></span> <span data-ttu-id="18791-119">この定義の詳細が記載[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="18791-119">Details of this definition are given in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a><span data-ttu-id="18791-120">パイプラインから入力を定義します。</span><span class="sxs-lookup"><span data-stu-id="18791-120">Defining Input from the Pipeline</span></span>

<span data-ttu-id="18791-121">このセクションでは、コマンドレットのパイプラインからの入力を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18791-121">This section describes how to define input from the pipeline for a cmdlet.</span></span> <span data-ttu-id="18791-122">この Get-proc コマンドレットを表すプロパティの定義、`Name`パラメーター」の説明に従って[そのプロセスのコマンドラインの入力パラメーターを追加する](./adding-parameters-that-process-command-line-input.md)します。</span><span class="sxs-lookup"><span data-stu-id="18791-122">This Get-Proc cmdlet defines a property that represents the `Name` parameter as described in [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span> <span data-ttu-id="18791-123">(パラメーターの宣言に関する全般情報のトピックを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="18791-123">(See that topic for general information about declaring parameters.)</span></span>

<span data-ttu-id="18791-124">ただし、コマンドレットは、パイプラインの入力を処理する必要がある、ときに、Windows PowerShell ランタイムによって入力値にバインドされたパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="18791-124">However, when a cmdlet needs to process pipeline input, it must have its parameters bound to input values by the Windows PowerShell runtime.</span></span> <span data-ttu-id="18791-125">これを行うには、追加する必要があります、`ValueFromPipeline`キーワードを追加または、`ValueFromPipelineByProperty`キーワードを[System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性宣言。</span><span class="sxs-lookup"><span data-stu-id="18791-125">To do this, you must add the `ValueFromPipeline` keyword or add the `ValueFromPipelineByProperty` keyword to the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="18791-126">指定、`ValueFromPipeline`コマンドレットは、完全な入力オブジェクトにアクセスする場合は、キーワード。</span><span class="sxs-lookup"><span data-stu-id="18791-126">Specify the `ValueFromPipeline` keyword if the cmdlet accesses the complete input object.</span></span> <span data-ttu-id="18791-127">指定、`ValueFromPipelineByProperty`コマンドレットは、オブジェクトのプロパティのみにアクセスする場合。</span><span class="sxs-lookup"><span data-stu-id="18791-127">Specify the `ValueFromPipelineByProperty` if the cmdlet accesses only a property of the object.</span></span>

<span data-ttu-id="18791-128">パラメーター宣言を次に示します、`Name`パイプライン入力を受け付けるこの Get-proc コマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="18791-128">Here is the parameter declaration for the `Name` parameter of this Get-Proc cmdlet that accepts pipeline input.</span></span>

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

<span data-ttu-id="18791-129">前の宣言のセット、`ValueFromPipeline`キーワードを`true`Windows PowerShell ランタイムは、オブジェクトが、パラメーターと同じ型である場合に、受信オブジェクトへのパラメーターをバインドはまたは場合に、同じ型に強制的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="18791-129">The previous declaration sets the `ValueFromPipeline` keyword to `true` so that the Windows PowerShell runtime will bind the parameter to the incoming object if the object is the same type as the parameter, or if it can be coerced to the same type.</span></span> <span data-ttu-id="18791-130">`ValueFromPipelineByPropertyName`キーワードの設定も`true`、Windows PowerShell ランタイムは、受信オブジェクトを確認できるように、`Name`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="18791-130">The `ValueFromPipelineByPropertyName` keyword is also set to `true` so that the Windows PowerShell runtime will check the incoming object for a `Name` property.</span></span> <span data-ttu-id="18791-131">受信のオブジェクトは、このようなプロパティを持っている場合、ランタイムはバインド、`Name`パラメーターを`Name`受信オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="18791-131">If the incoming object has such a property, the runtime will bind the `Name` parameter to the `Name` property of the incoming object.</span></span>

> [!NOTE]
> <span data-ttu-id="18791-132">設定、`ValueFromPipeline`キーワード属性パラメーターの設定よりも優先、`ValueFromPipelineByPropertyName`キーワード。</span><span class="sxs-lookup"><span data-stu-id="18791-132">The setting of the `ValueFromPipeline` attribute keyword for a parameter takes precedence over the setting for the `ValueFromPipelineByPropertyName` keyword.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="18791-133">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="18791-133">Overriding an Input Processing Method</span></span>

<span data-ttu-id="18791-134">コマンドレットをパイプラインの入力を処理する場合は、その適切な入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18791-134">If your cmdlet is to handle pipeline input, it needs to override the appropriate input processing methods.</span></span> <span data-ttu-id="18791-135">基本的な入力処理メソッドがで導入された[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="18791-135">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="18791-136">この Get-proc コマンドレットよりも優先、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)を処理するメソッド、`Name`ユーザーまたはスクリプトによって提供されるパラメーターの入力。</span><span class="sxs-lookup"><span data-stu-id="18791-136">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="18791-137">名前が指定されていない場合、このメソッドは各要求のプロセス名またはすべてのプロセスのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="18791-137">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="18791-138">わかります[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)への呼び出し[System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29)出力出力を送信するためのメカニズムは、パイプラインにオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="18791-138">Notice that within [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="18791-139">この呼び出しの 2 番目のパラメーター`enumerateCollection`に設定されている`true`、プロセス オブジェクトの配列を列挙し、コマンドラインに、一度に 1 つのプロセスを記述する Windows PowerShell ランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="18791-139">The second parameter of this call, `enumerateCollection`, is set to `true` to tell the Windows PowerShell runtime to enumerate the array of process objects, and write one process at a time to the command line.</span></span>

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

## <a name="code-sample"></a><span data-ttu-id="18791-140">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="18791-140">Code Sample</span></span>

<span data-ttu-id="18791-141">完全なC#サンプル コードは、「 [GetProcessSample03 サンプル](./getprocesssample03-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="18791-141">For the complete C# sample code, see [GetProcessSample03 Sample](./getprocesssample03-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="18791-142">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="18791-142">Defining Object Types and Formatting</span></span>

<span data-ttu-id="18791-143">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="18791-143">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="18791-144">その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18791-144">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="18791-145">新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。</span><span class="sxs-lookup"><span data-stu-id="18791-145">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="18791-146">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="18791-146">Building the Cmdlet</span></span>

<span data-ttu-id="18791-147">Windows PowerShell を使って Windows PowerShell を使用した登録する必要がありますコマンドレットの実装後にスナップインです。</span><span class="sxs-lookup"><span data-stu-id="18791-147">After implementing a cmdlet it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="18791-148">コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。</span><span class="sxs-lookup"><span data-stu-id="18791-148">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="18791-149">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="18791-149">Testing the Cmdlet</span></span>

<span data-ttu-id="18791-150">Windows PowerShell コマンドレットが登録されて、コマンドラインで実行してテストします。</span><span class="sxs-lookup"><span data-stu-id="18791-150">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="18791-151">たとえば、サンプルのコマンドレットのコードをテストします。</span><span class="sxs-lookup"><span data-stu-id="18791-151">For example, test the code for the sample cmdlet.</span></span> <span data-ttu-id="18791-152">詳細については、コマンドラインからコマンドレットを使用して、次を参照してください。、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="18791-152">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="18791-153">Windows PowerShell プロンプトで、パイプラインを介してプロセス名を取得する次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="18791-153">At the Windows PowerShell prompt, enter the following commands to retrieve the process names through the pipeline.</span></span>

    ```powershell
    PS> type ProcessNames | get-proc
    ```

<span data-ttu-id="18791-154">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18791-154">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----   ----- -----   ------    --  -----------
        809      21  40856    4448    147    9.50  2288  iexplore
        737      21  26036   16348    144   22.03  3860  iexplore
         39       2   1024     388     30    0.08  3396  notepad
       3927      62  71836   26984    467  195.19  1848  OUTLOOK
    ```

- <span data-ttu-id="18791-155">次の行を取得しているプロセス オブジェクトを入力してください、 `Name` "IEXPLORE"と呼ばれるプロセスからのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="18791-155">Enter the following lines to get the process objects that have a `Name` property from the processes called "IEXPLORE".</span></span> <span data-ttu-id="18791-156">この例では、`Get-Process`コマンドレットが (Windows PowerShell によって提供される)"と、IEXPLORE"プロセスを取得するアップ ストリームのコマンドとして。</span><span class="sxs-lookup"><span data-stu-id="18791-156">This example uses the `Get-Process` cmdlet (provided by Windows PowerShell) as an upstream command to retrieve the "IEXPLORE" processes.</span></span>

    ```powershell
    PS> get-process iexplore | get-proc
    ```

<span data-ttu-id="18791-157">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18791-157">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----      ----- -----   ------     -- -----------
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
    ```

## <a name="see-also"></a><span data-ttu-id="18791-158">参照</span><span class="sxs-lookup"><span data-stu-id="18791-158">See Also</span></span>

[<span data-ttu-id="18791-159">コマンドラインの入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="18791-159">Adding Parameters that Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="18791-160">初めてのコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="18791-160">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="18791-161">オブジェクトの種類を拡張して、書式設定</span><span class="sxs-lookup"><span data-stu-id="18791-161">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="18791-162">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="18791-162">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="18791-163">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="18791-163">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="18791-164">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="18791-164">Cmdlet Samples</span></span>](./cmdlet-samples.md)

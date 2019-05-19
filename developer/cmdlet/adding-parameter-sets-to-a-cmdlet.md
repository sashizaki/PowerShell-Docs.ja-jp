---
title: コマンドレットにパラメーターを追加すると設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameter sets [PowerShell Programmer's Guide]
ms.assetid: a6131db4-fd6e-45f1-bd47-17e7174afd56
caps.latest.revision: 8
ms.openlocfilehash: 6a3b592c5f85c1f065ad4b5b0290cf44dcef484e
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854863"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a><span data-ttu-id="5194a-102">コマンドレットにパラメーター セットを追加する</span><span class="sxs-lookup"><span data-stu-id="5194a-102">Adding Parameter Sets to a Cmdlet</span></span>

## <a name="things-to-know-about-parameter-sets"></a><span data-ttu-id="5194a-103">パラメーターのセットについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="5194a-103">Things to Know About Parameter Sets</span></span>

<span data-ttu-id="5194a-104">Windows PowerShell では、同時に動作するパラメーターのグループとして設定パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="5194a-104">Windows PowerShell defines a parameter set as a group of parameters that operate together.</span></span> <span data-ttu-id="5194a-105">コマンドレットのパラメーターをグループ化には、ユーザーがどのような一連のパラメーターを指定に基づいて、その機能を変更できる 1 つのコマンドレットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5194a-105">By grouping the parameters of a cmdlet, you can create a single cmdlet that can change its functionality based on what group of parameters the user specifies.</span></span>

<span data-ttu-id="5194a-106">さまざまな機能を定義する 2 つのパラメーター セットを使用するコマンドレットの例は、`Get-EventLog`コマンドレットは Windows PowerShell によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="5194a-106">An example of a cmdlet that uses two parameter sets to define different functionalities is the `Get-EventLog` cmdlet that is provided by Windows PowerShell.</span></span> <span data-ttu-id="5194a-107">このコマンドレットは、ユーザーを指定すると、さまざまな情報を返します、`List`または`LogName`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5194a-107">This cmdlet returns different information when the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="5194a-108">場合、`LogName`パラメーターを指定すると、コマンドレットは、特定のイベント ログで、イベントに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="5194a-108">If the `LogName` parameter is specified, the cmdlet returns information about the events in a given event log.</span></span> <span data-ttu-id="5194a-109">場合、`List`パラメーターを指定すると、コマンドレットは、ログに関する情報をファイル自体 (イベントが含まれている情報以外) を返します。</span><span class="sxs-lookup"><span data-stu-id="5194a-109">If the `List` parameter is specified, the cmdlet returns information about the log files themselves (not the event information they contain).</span></span> <span data-ttu-id="5194a-110">ここで、`List`と`LogName`パラメーターが 2 つの個別のパラメーター セットを識別します。</span><span class="sxs-lookup"><span data-stu-id="5194a-110">In this case, the `List` and `LogName` parameters identify two separate parameter sets.</span></span>

<span data-ttu-id="5194a-111">パラメーターのセットに関して記憶して 2 つの重要な点は、Windows PowerShell ランタイムは、1 つだけのパラメーターが特定の入力セットを使用して、各パラメーター セットが少なくとも 1 つのパラメーターを持つ必要があるをそのパラメーターのセットの一意。</span><span class="sxs-lookup"><span data-stu-id="5194a-111">Two important things to remember about parameter sets is that the Windows PowerShell runtime uses only one parameter set for a particular input, and that each parameter set must have at least one parameter that is unique for that parameter set.</span></span>

<span data-ttu-id="5194a-112">この停止 Proc コマンドレットが次の 3 つのパラメーター セットを使用するにはその最後のポイントを示すためには、: `ProcessName`、 `ProcessId`、および`InputObject`します。</span><span class="sxs-lookup"><span data-stu-id="5194a-112">To illustrate that last point, this Stop-Proc cmdlet uses three parameter sets: `ProcessName`, `ProcessId`, and `InputObject`.</span></span> <span data-ttu-id="5194a-113">それぞれのパラメーター セットは、他のパラメーター セットではない 1 つのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="5194a-113">Each of these parameter sets has one parameter that is not in the other parameter sets.</span></span> <span data-ttu-id="5194a-114">パラメーター セットは、他のパラメーターを共有でしたが、コマンドレットは、固有のパラメーターを使用して`ProcessName`、 `ProcessId`、および`InputObject`Windows PowerShell ランタイムが使用されるパラメーターのセットを識別するためにします。</span><span class="sxs-lookup"><span data-stu-id="5194a-114">The parameter sets could share other parameters, but the cmdlet uses the unique parameters `ProcessName`, `ProcessId`, and `InputObject` to identify which set of parameters that the Windows PowerShell runtime should use.</span></span>

## <a name="declaring-the-cmdlet-class"></a><span data-ttu-id="5194a-115">コマンドレット クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5194a-115">Declaring the Cmdlet Class</span></span>

<span data-ttu-id="5194a-116">コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5194a-116">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="5194a-117">このコマンドレットでは、"Stop"ライフ サイクルの動詞はコマンドレットは、システム プロセスを停止するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5194a-117">For this cmdlet, the life-cycle verb "Stop" is used because the cmdlet stops system processes.</span></span> <span data-ttu-id="5194a-118">"Proc"名詞形式の名前は、コマンドレットは、プロセスで機能するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5194a-118">The noun name "Proc" is used because the cmdlet works on processes.</span></span> <span data-ttu-id="5194a-119">次の宣言では、コマンドレット クラスの名前、コマンドレットの動詞と名詞の名前が反映されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5194a-119">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span>

> [!NOTE]
> <span data-ttu-id="5194a-120">承認されたコマンドレット動詞名の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="5194a-120">For more information about approved cmdlet verb names, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="5194a-121">次のコードは、このコマンドレットで停止 Proc クラス定義です。</span><span class="sxs-lookup"><span data-stu-id="5194a-121">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        DefaultParameterSetName = "ProcessId",
        SupportsShouldProcess = true)]
public class StopProcCommand : PSCmdlet
```

```vb
<Cmdlet(VerbsLifecycle.Stop, "Proc", DefaultParameterSetName:="ProcessId", _
SupportsShouldProcess:=True)> _
Public Class StopProcCommand
    Inherits PSCmdlet
```

## <a name="declaring-the-parameters-of-the-cmdlet"></a><span data-ttu-id="5194a-122">コマンドレットのパラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5194a-122">Declaring the Parameters of the Cmdlet</span></span>

<span data-ttu-id="5194a-123">このコマンドレットは、コマンドレットが (これらのパラメーターは、パラメーター セットも定義) への入力として必要な 3 つのパラメーターを定義と同様に、`Force`コマンドレットが何を管理するパラメーターと`PassThru`コマンドレットに送信するかどうかを決定するパラメーター、オブジェクトをパイプラインを通じてに出力します。</span><span class="sxs-lookup"><span data-stu-id="5194a-123">This cmdlet defines three parameters needed as input to the cmdlet (these parameters also define the parameter sets), as well as a `Force` parameter that manages what the cmdlet does and a `PassThru` parameter that determines whether the cmdlet sends an output object through the pipeline.</span></span> <span data-ttu-id="5194a-124">既定では、このコマンドレットは、パイプラインを通じてオブジェクトを通過しません。</span><span class="sxs-lookup"><span data-stu-id="5194a-124">By default, this cmdlet does not pass an object through the pipeline.</span></span> <span data-ttu-id="5194a-125">これらの最後の 2 つのパラメーターの詳細については、次を参照してください。[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="5194a-125">For more information about these last two parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

### <a name="declaring-the-name-parameter"></a><span data-ttu-id="5194a-126">Name パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5194a-126">Declaring the Name Parameter</span></span>

<span data-ttu-id="5194a-127">この入力パラメーターは、停止するプロセスの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5194a-127">This input parameter allows the user to specify the names of the processes to be stopped.</span></span> <span data-ttu-id="5194a-128">なお、`ParameterSetName`属性のキーワード、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性を指定します、`ProcessName`パラメーターは、このパラメーターに設定します。</span><span class="sxs-lookup"><span data-stu-id="5194a-128">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessName` parameter set for this parameter.</span></span>

[!code-csharp[StopProcessSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L44-L58 "StopProcessSample04.cs")]

```vb
<Parameter(Position:=0, ParameterSetName:="ProcessName", _
Mandatory:=True, _
ValueFromPipeline:=True, ValueFromPipelineByPropertyName:=True, _
HelpMessage:="The name of one or more processes to stop. " & _
    "Wildcards are permitted."), [Alias]("ProcessName")> _
Public Property Name() As String()
    Get
        Return processNames
    End Get
    Set(ByVal value As String())
        processNames = value
    End Set
End Property

Private processNames() As String
```

<span data-ttu-id="5194a-129">このパラメーターにエイリアス"ProcessName"が与えられているにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="5194a-129">Note also that the alias "ProcessName" is given to this parameter.</span></span>

### <a name="declaring-the-id-parameter"></a><span data-ttu-id="5194a-130">Id パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5194a-130">Declaring the Id Parameter</span></span>

<span data-ttu-id="5194a-131">この入力パラメーターは、停止するプロセスの識別子を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5194a-131">This input parameter allows the user to specify the identifiers of the processes to be stopped.</span></span> <span data-ttu-id="5194a-132">なお、`ParameterSetName`属性のキーワード、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性を指定します、`ProcessId`パラメーターのセット。</span><span class="sxs-lookup"><span data-stu-id="5194a-132">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessId` parameter set.</span></span>

```csharp
[Parameter(
           ParameterSetName = "ProcessId",
           Mandatory = true,
           ValueFromPipelineByPropertyName = true,
           ValueFromPipeline = true
)]
[Alias("ProcessId")]
public int[] Id
{
  get { return processIds; }
  set { processIds = value; }
}
private int[] processIds;
```

```vb
<Parameter(ParameterSetName:="ProcessId", _
Mandatory:=True, _
ValueFromPipelineByPropertyName:=True, _
ValueFromPipeline:=True), [Alias]("ProcessId")> _
Public Property Id() As Integer()
    Get
        Return processIds
    End Get
    Set(ByVal value As Integer())
        processIds = value
    End Set
End Property
Private processIds() As Integer
```

<span data-ttu-id="5194a-133">このパラメーターにエイリアス"ProcessId"が与えられているにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="5194a-133">Note also that the alias "ProcessId" is given to this parameter.</span></span>

### <a name="declaring-the-inputobject-parameter"></a><span data-ttu-id="5194a-134">InputObject パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5194a-134">Declaring the InputObject Parameter</span></span>

<span data-ttu-id="5194a-135">この入力パラメーターは、停止するプロセスに関する情報を格納している入力オブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5194a-135">This input parameter allows the user to specify an input object that contains information about the processes to be stopped.</span></span> <span data-ttu-id="5194a-136">なお、`ParameterSetName`属性のキーワード、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性を指定します、`InputObject`パラメーターは、このパラメーターに設定します。</span><span class="sxs-lookup"><span data-stu-id="5194a-136">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `InputObject` parameter set for this parameter.</span></span>

```csharp
[Parameter(
           ParameterSetName = "InputObject",
           Mandatory = true,
           ValueFromPipeline = true)]
public Process[] InputObject
{
  get { return inputObject; }
  set { inputObject = value; }
}
private Process[] inputObject;
```

```vb
<Parameter(ParameterSetName:="InputObject", _
Mandatory:=True, ValueFromPipeline:=True)> _
Public Property InputObject() As Process()
    Get
        Return myInputObject
    End Get
    Set(ByVal value As Process())
        myInputObject = value
    End Set
End Property
Private myInputObject() As Process
```

<span data-ttu-id="5194a-137">このパラメーターにエイリアスがないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="5194a-137">Note also that this parameter has no alias.</span></span>

### <a name="declaring-parameters-in-multiple-parameter-sets"></a><span data-ttu-id="5194a-138">複数のパラメーター セット内のパラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5194a-138">Declaring Parameters in Multiple Parameter Sets</span></span>

<span data-ttu-id="5194a-139">パラメーターのセットごとに一意のパラメーターは必要ありませんが、パラメーターが 1 つ以上のパラメーターのセットに属することができます。</span><span class="sxs-lookup"><span data-stu-id="5194a-139">Although there must be a unique parameter for each parameter set, parameters can belong to more than one parameter set.</span></span> <span data-ttu-id="5194a-140">このような場合は、共有パラメーターを与える、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)にそのパラメーターを設定それぞれが属する属性の宣言。</span><span class="sxs-lookup"><span data-stu-id="5194a-140">In these cases, give the shared parameter a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration for each set to which that the parameter belongs.</span></span> <span data-ttu-id="5194a-141">パラメーターがすべてのパラメーター セットの場合は、するパラメーターの属性を 1 回宣言する必要があるのみとパラメーター セット名を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5194a-141">If a parameter is in all parameter sets, you only have to declare the parameter attribute once and do not need to specify the parameter set name.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="5194a-142">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="5194a-142">Overriding an Input Processing Method</span></span>

<span data-ttu-id="5194a-143">すべてのコマンドレットは、入力処理メソッドをオーバーライドする必要があります、これは最も頻繁になります、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド。</span><span class="sxs-lookup"><span data-stu-id="5194a-143">Every cmdlet must override an input processing method, most often this will be the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="5194a-144">このコマンドレットで、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)コマンドレットは、任意の数のプロセスを処理できるように、メソッドはオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="5194a-144">In this cmdlet, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden so that the cmdlet can process any number of processes.</span></span> <span data-ttu-id="5194a-145">どのパラメーター セットで、ユーザー ベースのさまざまなメソッドの呼び出しが指定されている Select ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5194a-145">It contains a Select statement that calls a different method based on which parameter set the user has specified.</span></span>

```csharp
protected override void ProcessRecord()
{
  switch (ParameterSetName)
  {
    case "ProcessName":
         ProcessByName();
         break;

    case "ProcessId":
         ProcessById();
         break;

    case "InputObject":
         foreach (Process process in inputObject)
         {
           SafeStopProcess(process);
         }
         break;

    default:
         throw new ArgumentException("Bad ParameterSet Name");
  } // switch (ParameterSetName...
} // ProcessRecord
```

```vb
Protected Overrides Sub ProcessRecord()
    Select Case ParameterSetName
        Case "ProcessName"
            ProcessByName()

        Case "ProcessId"
            ProcessById()

        Case "InputObject"
            Dim process As Process
            For Each process In myInputObject
                SafeStopProcess(process)
            Next process

        Case Else
            Throw New ArgumentException("Bad ParameterSet Name")
    End Select

End Sub 'ProcessRecord ' ProcessRecord
```

<span data-ttu-id="5194a-146">Select ステートメントによって呼び出されるヘルパー メソッドが、ここで説明できませんが、次のセクションで完全なコード サンプルでは、その実装を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5194a-146">The Helper methods called by the Select statement are not described here, but you can see their implementation in the complete code sample in the next section.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5194a-147">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="5194a-147">Code Sample</span></span>

<span data-ttu-id="5194a-148">完全なC#サンプル コードは、「 [StopProcessSample04 サンプル](./stopprocesssample04-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="5194a-148">For the complete C# sample code, see [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="5194a-149">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="5194a-149">Defining Object Types and Formatting</span></span>

<span data-ttu-id="5194a-150">Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="5194a-150">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="5194a-151">その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5194a-151">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="5194a-152">新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。</span><span class="sxs-lookup"><span data-stu-id="5194a-152">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="5194a-153">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="5194a-153">Building the Cmdlet</span></span>

<span data-ttu-id="5194a-154">コマンドレットを実装するには、後にする必要がありますに登録する Windows PowerShell Windows PowerShell スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="5194a-154">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="5194a-155">コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。</span><span class="sxs-lookup"><span data-stu-id="5194a-155">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="5194a-156">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5194a-156">Testing the Cmdlet</span></span>

<span data-ttu-id="5194a-157">Windows PowerShell コマンドレットが登録されて、コマンドラインで実行してテストします。</span><span class="sxs-lookup"><span data-stu-id="5194a-157">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="5194a-158">示すいくつかのテストをここでは、どのように`ProcessId`と`InputObject`パラメーターは、テストのプロセスを停止するには、そのパラメーター セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5194a-158">Here are some tests that show how the `ProcessId` and `InputObject` parameters can be used to test their parameter sets to stop a process.</span></span>

- <span data-ttu-id="5194a-159">Windows PowerShell が起動、実行停止 Proc コマンドレットと、 `ProcessId` id に基づいてプロセスを停止するパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="5194a-159">With Windows PowerShell started, run the Stop-Proc cmdlet with the `ProcessId` parameter set to stop a process based on its identifier.</span></span> <span data-ttu-id="5194a-160">この場合、コマンドレットを使用して、`ProcessId`プロセスを停止するパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="5194a-160">In this case, the cmdlet is using the `ProcessId` parameter set to stop the process.</span></span>

    ```
    PS> stop-proc -Id 444
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="5194a-161">Windows PowerShell が起動、実行停止 Proc コマンドレットと、`InputObject`で取得したメモ帳オブジェクトのプロセスを停止するパラメーターの設定、`Get-Process`コマンド。</span><span class="sxs-lookup"><span data-stu-id="5194a-161">With Windows PowerShell started, run the Stop-Proc cmdlet with the `InputObject` parameter set to stop processes on the Notepad object retrieved by the `Get-Process` command.</span></span>

    ```
    PS> get-process notepad | stop-proc
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="5194a-162">参照</span><span class="sxs-lookup"><span data-stu-id="5194a-162">See Also</span></span>

[<span data-ttu-id="5194a-163">システムを変更するコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5194a-163">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="5194a-164">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="5194a-164">How to Create a Windows PowerShell Cmdlet</span></span>](http://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="5194a-165">オブジェクトの種類を拡張して、書式設定</span><span class="sxs-lookup"><span data-stu-id="5194a-165">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="5194a-166">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="5194a-166">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="5194a-167">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="5194a-167">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

---
title: コマンドレットにパラメーターセットを追加する |Microsoft Docs
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
ms.openlocfilehash: c9c0b9a7a587e856efc82b4d277cee373e3f8b38
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74416313"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a><span data-ttu-id="3601d-102">コマンドレットにパラメーター セットを追加する</span><span class="sxs-lookup"><span data-stu-id="3601d-102">Adding Parameter Sets to a Cmdlet</span></span>

## <a name="things-to-know-about-parameter-sets"></a><span data-ttu-id="3601d-103">パラメーターセットについて理解しておくべきこと</span><span class="sxs-lookup"><span data-stu-id="3601d-103">Things to Know About Parameter Sets</span></span>

<span data-ttu-id="3601d-104">Windows PowerShell では、パラメーターセットを、一緒に動作するパラメーターのグループとして定義します。</span><span class="sxs-lookup"><span data-stu-id="3601d-104">Windows PowerShell defines a parameter set as a group of parameters that operate together.</span></span> <span data-ttu-id="3601d-105">コマンドレットのパラメーターをグループ化することによって、ユーザーが指定するパラメーターのグループに基づいて機能を変更できる単一のコマンドレットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3601d-105">By grouping the parameters of a cmdlet, you can create a single cmdlet that can change its functionality based on what group of parameters the user specifies.</span></span>

<span data-ttu-id="3601d-106">2つのパラメーターセットを使用して異なる機能を定義するコマンドレットの例として、Windows PowerShell によって提供される `Get-EventLog` コマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="3601d-106">An example of a cmdlet that uses two parameter sets to define different functionalities is the `Get-EventLog` cmdlet that is provided by Windows PowerShell.</span></span> <span data-ttu-id="3601d-107">このコマンドレットは、ユーザーが `List` または `LogName` パラメーターを指定すると、異なる情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3601d-107">This cmdlet returns different information when the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="3601d-108">`LogName` パラメーターが指定されている場合、コマンドレットは、特定のイベントログ内のイベントに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3601d-108">If the `LogName` parameter is specified, the cmdlet returns information about the events in a given event log.</span></span> <span data-ttu-id="3601d-109">`List` パラメーターが指定されている場合、コマンドレットは、ログファイル自体に関する情報 (含まれるイベント情報ではありません) を返します。</span><span class="sxs-lookup"><span data-stu-id="3601d-109">If the `List` parameter is specified, the cmdlet returns information about the log files themselves (not the event information they contain).</span></span> <span data-ttu-id="3601d-110">この場合、`List` パラメーターと `LogName` パラメーターによって、2つの異なるパラメーターセットが識別されます。</span><span class="sxs-lookup"><span data-stu-id="3601d-110">In this case, the `List` and `LogName` parameters identify two separate parameter sets.</span></span>

<span data-ttu-id="3601d-111">パラメーターセットについて覚えておく必要がある2つの重要な点は、Windows PowerShell ランタイムでは特定の入力に対して1つのパラメーターセットだけを使用し、各パラメーターセットには、そのパラメーターセットに対して一意のパラメーターを1つ以上含める必要があることです。</span><span class="sxs-lookup"><span data-stu-id="3601d-111">Two important things to remember about parameter sets is that the Windows PowerShell runtime uses only one parameter set for a particular input, and that each parameter set must have at least one parameter that is unique for that parameter set.</span></span>

<span data-ttu-id="3601d-112">最後の点を示すために、この Stop Proc コマンドレットは、`ProcessName`、`ProcessId`、および `InputObject`の3つのパラメーターセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3601d-112">To illustrate that last point, this Stop-Proc cmdlet uses three parameter sets: `ProcessName`, `ProcessId`, and `InputObject`.</span></span> <span data-ttu-id="3601d-113">これらの各パラメーターセットには、他のパラメーターセットに含まれていないパラメーターが1つあります。</span><span class="sxs-lookup"><span data-stu-id="3601d-113">Each of these parameter sets has one parameter that is not in the other parameter sets.</span></span> <span data-ttu-id="3601d-114">パラメーターセットは他のパラメーターを共有できますが、コマンドレットは、一意のパラメーター `ProcessName`、`ProcessId`、および `InputObject` を使用して、Windows PowerShell ランタイムが使用するパラメーターのセットを識別します。</span><span class="sxs-lookup"><span data-stu-id="3601d-114">The parameter sets could share other parameters, but the cmdlet uses the unique parameters `ProcessName`, `ProcessId`, and `InputObject` to identify which set of parameters that the Windows PowerShell runtime should use.</span></span>

## <a name="declaring-the-cmdlet-class"></a><span data-ttu-id="3601d-115">コマンドレットクラスの宣言</span><span class="sxs-lookup"><span data-stu-id="3601d-115">Declaring the Cmdlet Class</span></span>

<span data-ttu-id="3601d-116">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="3601d-116">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="3601d-117">このコマンドレットでは、コマンドレットがシステムプロセスを停止するため、ライフサイクルの動詞 "Stop" が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3601d-117">For this cmdlet, the life-cycle verb "Stop" is used because the cmdlet stops system processes.</span></span> <span data-ttu-id="3601d-118">名詞名 "Proc" が使用されるのは、コマンドレットがプロセスで動作するためです。</span><span class="sxs-lookup"><span data-stu-id="3601d-118">The noun name "Proc" is used because the cmdlet works on processes.</span></span> <span data-ttu-id="3601d-119">次の宣言では、コマンドレット動詞と名詞名がコマンドレットクラスの名前に反映されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-119">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span>

> [!NOTE]
> <span data-ttu-id="3601d-120">承認されたコマンドレットの動詞名の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-120">For more information about approved cmdlet verb names, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="3601d-121">次のコードは、この Stop Proc コマンドレットのクラス定義です。</span><span class="sxs-lookup"><span data-stu-id="3601d-121">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

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

## <a name="declaring-the-parameters-of-the-cmdlet"></a><span data-ttu-id="3601d-122">コマンドレットのパラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="3601d-122">Declaring the Parameters of the Cmdlet</span></span>

<span data-ttu-id="3601d-123">このコマンドレットは、コマンドレットへの入力として必要な3つのパラメーター (これらのパラメーターもパラメーターセットを定義します `Force`) と、コマンドレットがパイプラインを介して出力オブジェクトを送信するかどうかを決定する `PassThru` パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="3601d-123">This cmdlet defines three parameters needed as input to the cmdlet (these parameters also define the parameter sets), as well as a `Force` parameter that manages what the cmdlet does and a `PassThru` parameter that determines whether the cmdlet sends an output object through the pipeline.</span></span> <span data-ttu-id="3601d-124">既定では、このコマンドレットはパイプラインを介してオブジェクトを渡しません。</span><span class="sxs-lookup"><span data-stu-id="3601d-124">By default, this cmdlet does not pass an object through the pipeline.</span></span> <span data-ttu-id="3601d-125">これらの最後の2つのパラメーターの詳細については、「[システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-125">For more information about these last two parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

### <a name="declaring-the-name-parameter"></a><span data-ttu-id="3601d-126">Name パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="3601d-126">Declaring the Name Parameter</span></span>

<span data-ttu-id="3601d-127">この入力パラメーターを使用すると、停止するプロセスの名前をユーザーが指定できます。</span><span class="sxs-lookup"><span data-stu-id="3601d-127">This input parameter allows the user to specify the names of the processes to be stopped.</span></span> <span data-ttu-id="3601d-128">このパラメーターに対して設定されている `ProcessName` パラメーターを指定するのは、 [`ParameterSetName` attribute キーワード](/dotnet/api/System.Management.Automation.ParameterAttribute)であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-128">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessName` parameter set for this parameter.</span></span>

[!code-csharp[StopProcessSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L44-L58 "StopProcessSample04.cs")]

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

<span data-ttu-id="3601d-129">また、エイリアス "ProcessName" がこのパラメーターに指定されていることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-129">Note also that the alias "ProcessName" is given to this parameter.</span></span>

### <a name="declaring-the-id-parameter"></a><span data-ttu-id="3601d-130">Id パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="3601d-130">Declaring the Id Parameter</span></span>

<span data-ttu-id="3601d-131">この入力パラメーターを使用すると、停止するプロセスの識別子をユーザーが指定できます。</span><span class="sxs-lookup"><span data-stu-id="3601d-131">This input parameter allows the user to specify the identifiers of the processes to be stopped.</span></span> <span data-ttu-id="3601d-132">System.object[属性の](/dotnet/api/System.Management.Automation.ParameterAttribute)`ParameterSetName` attribute キーワードは、`ProcessId` パラメーターセットを指定していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-132">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessId` parameter set.</span></span>

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

<span data-ttu-id="3601d-133">また、エイリアス "ProcessId" がこのパラメーターに指定されていることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-133">Note also that the alias "ProcessId" is given to this parameter.</span></span>

### <a name="declaring-the-inputobject-parameter"></a><span data-ttu-id="3601d-134">InputObject パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="3601d-134">Declaring the InputObject Parameter</span></span>

<span data-ttu-id="3601d-135">この入力パラメーターを使用すると、停止するプロセスに関する情報を含む入力オブジェクトをユーザーが指定できます。</span><span class="sxs-lookup"><span data-stu-id="3601d-135">This input parameter allows the user to specify an input object that contains information about the processes to be stopped.</span></span> <span data-ttu-id="3601d-136">このパラメーターに対して設定されている `InputObject` パラメーターを指定するのは、 [`ParameterSetName` attribute キーワード](/dotnet/api/System.Management.Automation.ParameterAttribute)であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-136">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `InputObject` parameter set for this parameter.</span></span>

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

<span data-ttu-id="3601d-137">また、このパラメーターにエイリアスが含まれていないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-137">Note also that this parameter has no alias.</span></span>

### <a name="declaring-parameters-in-multiple-parameter-sets"></a><span data-ttu-id="3601d-138">複数のパラメーターセットでのパラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="3601d-138">Declaring Parameters in Multiple Parameter Sets</span></span>

<span data-ttu-id="3601d-139">パラメーターセットごとに一意のパラメーターが必要ですが、パラメーターは複数のパラメーターセットに属することができます。</span><span class="sxs-lookup"><span data-stu-id="3601d-139">Although there must be a unique parameter for each parameter set, parameters can belong to more than one parameter set.</span></span> <span data-ttu-id="3601d-140">このような場合は、共有パラメーターに、パラメーターが属している各セットの system.object 属性[宣言を指定](/dotnet/api/System.Management.Automation.ParameterAttribute)します。</span><span class="sxs-lookup"><span data-stu-id="3601d-140">In these cases, give the shared parameter a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration for each set to which that the parameter belongs.</span></span> <span data-ttu-id="3601d-141">パラメーターがすべてのパラメーターセットに含まれている場合は、パラメーター属性を1回だけ宣言するだけで、パラメーターセット名を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3601d-141">If a parameter is in all parameter sets, you only have to declare the parameter attribute once and do not need to specify the parameter set name.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="3601d-142">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="3601d-142">Overriding an Input Processing Method</span></span>

<span data-ttu-id="3601d-143">すべてのコマンドレットは、入力処理メソッドをオーバーライドする必要があります。これは、[ほとんどの場合、この](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドになります。</span><span class="sxs-lookup"><span data-stu-id="3601d-143">Every cmdlet must override an input processing method, most often this will be the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="3601d-144">このコマンドレットでは、コマンドレットが任意の数のプロセスを処理できるよう[に、system.string メソッドが](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="3601d-144">In this cmdlet, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden so that the cmdlet can process any number of processes.</span></span> <span data-ttu-id="3601d-145">これには、ユーザーが指定したパラメーターセットに基づいて別の方法を呼び出す Select ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3601d-145">It contains a Select statement that calls a different method based on which parameter set the user has specified.</span></span>

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

<span data-ttu-id="3601d-146">ここでは、Select ステートメントによって呼び出されるヘルパーメソッドについては説明しませんが、次のセクションの完全なコードサンプルで実装を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3601d-146">The Helper methods called by the Select statement are not described here, but you can see their implementation in the complete code sample in the next section.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3601d-147">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="3601d-147">Code Sample</span></span>

<span data-ttu-id="3601d-148">完全なC#サンプルコードについては、「 [StopProcessSample04 sample](./stopprocesssample04-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-148">For the complete C# sample code, see [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="3601d-149">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="3601d-149">Defining Object Types and Formatting</span></span>

<span data-ttu-id="3601d-150">Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="3601d-150">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="3601d-151">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3601d-151">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="3601d-152">新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-152">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="3601d-153">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="3601d-153">Building the Cmdlet</span></span>

<span data-ttu-id="3601d-154">コマンドレットを実装した後、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3601d-154">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="3601d-155">コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3601d-155">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="3601d-156">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="3601d-156">Testing the Cmdlet</span></span>

<span data-ttu-id="3601d-157">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行してテストします。</span><span class="sxs-lookup"><span data-stu-id="3601d-157">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="3601d-158">ここでは、`ProcessId` パラメーターと `InputObject` パラメーターを使用してパラメーターセットをテストしてプロセスを停止する方法を示すテストをいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="3601d-158">Here are some tests that show how the `ProcessId` and `InputObject` parameters can be used to test their parameter sets to stop a process.</span></span>

- <span data-ttu-id="3601d-159">Windows PowerShell を起動したら、`ProcessId` パラメーターを設定して Stop Proc コマンドレットを実行し、その識別子に基づいてプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="3601d-159">With Windows PowerShell started, run the Stop-Proc cmdlet with the `ProcessId` parameter set to stop a process based on its identifier.</span></span> <span data-ttu-id="3601d-160">この場合、コマンドレットは `ProcessId` パラメーターセットを使用してプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="3601d-160">In this case, the cmdlet is using the `ProcessId` parameter set to stop the process.</span></span>

    ```
    PS> stop-proc -Id 444
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="3601d-161">Windows PowerShell を起動したら、`InputObject` パラメーターを設定して Stop Proc コマンドレットを実行し、`Get-Process` コマンドによって取得されるメモ帳オブジェクトのプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="3601d-161">With Windows PowerShell started, run the Stop-Proc cmdlet with the `InputObject` parameter set to stop processes on the Notepad object retrieved by the `Get-Process` command.</span></span>

    ```
    PS> get-process notepad | stop-proc
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="3601d-162">参照</span><span class="sxs-lookup"><span data-stu-id="3601d-162">See Also</span></span>

[<span data-ttu-id="3601d-163">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="3601d-163">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="3601d-164">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="3601d-164">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="3601d-165">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="3601d-165">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="3601d-166">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="3601d-166">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="3601d-167">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3601d-167">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

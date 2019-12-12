---
title: パラメーターを指定せずにコマンドレットを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmers Guide], creating
- cmdlets [PowerShell Programmers Guide], basic cmdlet
ms.assetid: 54236ef3-82db-45f8-9114-1ecb7ff65d3e
caps.latest.revision: 8
ms.openlocfilehash: af41c2c9855310d047404114a07b27180a7aa8fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74415674"
---
# <a name="creating-a-cmdlet-without-parameters"></a><span data-ttu-id="614bc-102">パラメーターなしでコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="614bc-102">Creating a Cmdlet without Parameters</span></span>

<span data-ttu-id="614bc-103">このセクションでは、パラメーターを使用せずにローカルコンピューターから情報を取得するコマンドレットを作成し、その情報をパイプラインに書き込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="614bc-103">This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span> <span data-ttu-id="614bc-104">ここで説明するコマンドレットは、ローカルコンピューターのプロセスに関する情報を取得し、コマンドラインでその情報を表示する Get Proc コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="614bc-104">The cmdlet described here is a Get-Proc cmdlet that retrieves information about the processes of the local computer, and then displays that information at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="614bc-105">コマンドレットを記述するときは、Windows PowerShell®参照アセンブリがディスクにダウンロードされることに注意してください (既定では C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0 にあります)。</span><span class="sxs-lookup"><span data-stu-id="614bc-105">Be aware that when writing cmdlets, the Windows PowerShell® reference assemblies are downloaded onto disk (by default at C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).</span></span> <span data-ttu-id="614bc-106">グローバルアセンブリキャッシュ (GAC) にはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="614bc-106">They are not installed in the Global Assembly Cache (GAC).</span></span>

## <a name="naming-the-cmdlet"></a><span data-ttu-id="614bc-107">コマンドレットの名前付け</span><span class="sxs-lookup"><span data-stu-id="614bc-107">Naming the Cmdlet</span></span>

<span data-ttu-id="614bc-108">コマンドレット名は、コマンドレットによって実行されるアクションを示す動詞と、コマンドレットが処理する項目を示す名詞で構成されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-108">A cmdlet name consists of a verb that indicates the action the cmdlet takes and a noun that indicates the items that the cmdlet acts upon.</span></span> <span data-ttu-id="614bc-109">このサンプルの Get Proc コマンドレットはプロセスオブジェクトを取得するので、 [Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon)列挙型によって定義された動詞 "Get" を使用し、"Proc" という名詞を使用して、コマンドレットがプロセス項目で動作することを示します。</span><span class="sxs-lookup"><span data-stu-id="614bc-109">Because this sample Get-Proc cmdlet retrieves process objects, it uses the verb "Get", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) enumeration, and the noun "Proc" to indicate that the cmdlet works on process items.</span></span>

<span data-ttu-id="614bc-110">コマンドレットに名前を付けるときは、#、() {} [] &-/\ $; のいずれの文字も使用しないでください。: "' < > &#124;ですか?</span><span class="sxs-lookup"><span data-stu-id="614bc-110">When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ?</span></span> <span data-ttu-id="614bc-111">@ \` .</span><span class="sxs-lookup"><span data-stu-id="614bc-111">@ \` .</span></span>

### <a name="choosing-a-noun"></a><span data-ttu-id="614bc-112">名詞の選択</span><span class="sxs-lookup"><span data-stu-id="614bc-112">Choosing a Noun</span></span>

<span data-ttu-id="614bc-113">固有の名詞を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-113">You should choose a noun that is specific.</span></span> <span data-ttu-id="614bc-114">製品名の短縮版をプレフィックスとして使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="614bc-114">It is best to use a singular noun prefixed with a shortened version of the product name.</span></span> <span data-ttu-id="614bc-115">この種類のコマンドレット名の例としては、"`Get-SQLServer`" があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-115">An example cmdlet name of this type is "`Get-SQLServer`".</span></span>

### <a name="choosing-a-verb"></a><span data-ttu-id="614bc-116">動詞の選択</span><span class="sxs-lookup"><span data-stu-id="614bc-116">Choosing a Verb</span></span>

<span data-ttu-id="614bc-117">一連の承認されたコマンドレット動詞名から動詞を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-117">You should use a verb from the set of approved cmdlet verb names.</span></span> <span data-ttu-id="614bc-118">承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-118">For more information about the approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="614bc-119">コマンドレットクラスの定義</span><span class="sxs-lookup"><span data-stu-id="614bc-119">Defining the Cmdlet Class</span></span>

<span data-ttu-id="614bc-120">コマンドレット名を選択したら、コマンドレットを実装する .NET クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="614bc-120">Once you have chosen a cmdlet name, define a .NET class to implement the cmdlet.</span></span> <span data-ttu-id="614bc-121">このサンプルの Get Proc コマンドレットのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="614bc-121">Here is the class definition for this sample Get-Proc cmdlet:</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

<span data-ttu-id="614bc-122">クラス定義の前に、このクラスをコマンドレットとして識別するために、`[Cmdlet(verb, noun, ...)]`構文を使用して、このクラスが使用されていることに[注意して](/dotnet/api/System.Management.Automation.CmdletAttribute)ください。</span><span class="sxs-lookup"><span data-stu-id="614bc-122">Notice that previous to the class definition, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute, with the syntax `[Cmdlet(verb, noun, ...)]`, is used to identify this class as a cmdlet.</span></span> <span data-ttu-id="614bc-123">これは、すべてのコマンドレットに必要な唯一の属性であり、Windows PowerShell ランタイムでそれらを正しく呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="614bc-123">This is the only required attribute for all cmdlets, and it allows the Windows PowerShell runtime to call them correctly.</span></span> <span data-ttu-id="614bc-124">必要に応じて、クラスをさらに宣言する属性キーワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="614bc-124">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="614bc-125">サンプルの Getproc コマンドクラスの属性宣言では、Get Proc コマンドレットの名詞と動詞の名前のみが宣言されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-125">Be aware that the attribute declaration for our sample GetProcCommand class declares only the noun and verb names for the Get-Proc cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="614bc-126">すべての Windows PowerShell 属性クラスに対して設定できるキーワードは、属性クラスのプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="614bc-126">For all Windows PowerShell attribute classes, the keywords that you can set correspond to properties of the attribute class.</span></span>

<span data-ttu-id="614bc-127">コマンドレットのクラスに名前を付けるときは、クラス名にコマンドレット名を反映することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="614bc-127">When naming the class of the cmdlet, it is a good practice to reflect the cmdlet name in the class name.</span></span> <span data-ttu-id="614bc-128">これを行うには、"VerbNounCommand" という形式を使用し、"Verb" と "名詞" をコマンドレット名に使用されている動詞と名詞に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="614bc-128">To do this, use the form "VerbNounCommand" and replace "Verb" and "Noun" with the verb and noun used in the cmdlet name.</span></span> <span data-ttu-id="614bc-129">前のクラス定義に示されているように、サンプルの Get Proc コマンドレットでは、Getによって実行されるクラスを定義します。このクラスは、 [system.servicemodel 基本クラス](/dotnet/api/System.Management.Automation.Cmdlet)から派生します。</span><span class="sxs-lookup"><span data-stu-id="614bc-129">As is shown in the previous class definition, the sample Get-Proc cmdlet defines a class called GetProcCommand, which derives from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) base class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="614bc-130">Windows PowerShell ランタイムに直接アクセスするコマンドレットを定義する場合は、.NET クラスを[PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)基底クラスから派生させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-130">If you want to define a cmdlet that accesses the Windows PowerShell runtime directly, your .NET class should derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span> <span data-ttu-id="614bc-131">このクラスの詳細については、「[パラメーターセットを定義するコマンドレットを作成](./adding-parameter-sets-to-a-cmdlet.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-131">For more information about this class, see [Creating a Cmdlet that Defines Parameter Sets](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

> [!NOTE]
> <span data-ttu-id="614bc-132">コマンドレットのクラスは、明示的にパブリックとしてマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-132">The class for a cmdlet must be explicitly marked as public.</span></span> <span data-ttu-id="614bc-133">パブリックとしてマークされていないクラスは、既定で内部に設定され、Windows PowerShell ランタイムによって検出されません。</span><span class="sxs-lookup"><span data-stu-id="614bc-133">Classes that are not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="614bc-134">Windows PowerShell では、コマンドレットのクラスとして、 [powershell](/dotnet/api/Microsoft.PowerShell.Commands)の名前空間が使用されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-134">Windows PowerShell uses the [Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) namespace for its cmdlet classes.</span></span> <span data-ttu-id="614bc-135">コマンドレットクラスを API 名前空間のコマンド名前空間に配置することをお勧めします (例、xxx. .PS. コマンド)。</span><span class="sxs-lookup"><span data-stu-id="614bc-135">It is recommended to place your cmdlet classes in a Commands namespace of your API namespace, for example, xxx.PS.Commands.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="614bc-136">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="614bc-136">Overriding an Input Processing Method</span></span>

<span data-ttu-id="614bc-137">System.servicemodel[クラスには、3](/dotnet/api/System.Management.Automation.Cmdlet)つの主要な入力処理メソッドが用意されています。少なくとも1つはコマンドレットがオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-137">The [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class provides three main input processing methods, at least one of which your cmdlet must override.</span></span> <span data-ttu-id="614bc-138">Windows PowerShell がレコードを処理する方法の詳細については、「 [Windows powershell のしくみ](/previous-versions//ms714658(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-138">For more information about how Windows PowerShell processes records, see [How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85)).</span></span>

<span data-ttu-id="614bc-139">すべての種類の入力について、Windows PowerShell ランタイムは、処理を有効にするために、system.string[を呼び出します。](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)</span><span class="sxs-lookup"><span data-stu-id="614bc-139">For all types of input, the Windows PowerShell runtime calls [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) to enable processing.</span></span> <span data-ttu-id="614bc-140">コマンドレットでいくつかの前処理またはセットアップを実行する必要がある場合は、このメソッドをオーバーライドすることによってこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="614bc-140">If your cmdlet must perform some preprocessing or setup, it can do this by overriding this method.</span></span>

> [!NOTE]
> <span data-ttu-id="614bc-141">Windows PowerShell では、コマンドレットが呼び出されたときに指定されるパラメーター値のセットを記述するために "レコード" という用語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-141">Windows PowerShell uses the term "record" to describe the set of parameter values supplied when a cmdlet is called.</span></span>

<span data-ttu-id="614bc-142">コマンドレットがパイプライン入力を受け入れる場合は、この[メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドする必要があります。また、[必要に応じて、](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) system.object メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-142">If your cmdlet accepts pipeline input, it must override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, and optionally the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="614bc-143">たとえば、コマンドレット[を使用してすべて](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)の入力を収集し、`Sort-Object` 一度に1つの要素ではなく1つの要素として入力を操作すると、コマンドレットの実行時に両方のメソッドがオーバーライドされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-143">For example, a cmdlet might override both methods if it gathers all input using [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) and then operates on the input as a whole rather than one element at a time, as the `Sort-Object` cmdlet does.</span></span>

<span data-ttu-id="614bc-144">コマンドレットがパイプライン入力を受け取らない場合[は、このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)オーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-144">If your cmdlet does not take pipeline input, it should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="614bc-145">このメソッドは、並べ替えコマンドレットの場合と同様に、一度に1つの要素に対してコマンドレットを実行できない場合に、その代わりに使用されることに注意して[ください](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)。</span><span class="sxs-lookup"><span data-stu-id="614bc-145">Be aware that this method is frequently used in place of [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) when the cmdlet cannot operate on one element at a time, as is the case for a sorting cmdlet.</span></span>

<span data-ttu-id="614bc-146">このサンプルの Get Proc コマンドレットは、パイプラインの入力を受け取る必要があるため、[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)このメソッドをオーバーライドして、システムの既定の実装を使用します。 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)と共に、を行います[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)。</span><span class="sxs-lookup"><span data-stu-id="614bc-146">Because this sample Get-Proc cmdlet must receive pipeline input, it overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method and uses the default implementations for [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) and [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span></span> <span data-ttu-id="614bc-147">[WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを使用して、プロセスを取得し、コマンドラインに書き込むプロセスを取得するために、[このオーバーライドが](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)実行されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-147">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override retrieves processes and writes them to the command line using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Get the current processes
  Process[] processes = Process.GetProcesses();

  // Write the processes to the pipeline making them available
  // to the next cmdlet. The second parameter of this call tells
  // PowerShell to enumerate the array, and send one process at a
  // time to the pipeline.
  WriteObject(processes, true);
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ Get the current processes.
    Dim processes As Process()
    processes = Process.GetProcesses()

    '/ Write the processes to the pipeline making them available
    '/ to the next cmdlet. The second parameter of this call tells
    '/ PowerShell to enumerate the array, and send one process at a
    '/ time to the pipeline.
    WriteObject(processes, True)

End Sub 'ProcessRecord
```

#### <a name="things-to-remember-about-input-processing"></a><span data-ttu-id="614bc-148">入力処理に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="614bc-148">Things to Remember About Input Processing</span></span>

- <span data-ttu-id="614bc-149">入力の既定のソースは、コマンドラインでユーザーによって指定された明示的なオブジェクト (文字列など) です。</span><span class="sxs-lookup"><span data-stu-id="614bc-149">The default source for input is an explicit object (for example, a string) provided by the user on the command line.</span></span> <span data-ttu-id="614bc-150">詳細については、「[コマンドライン入力を処理するためのコマンドレットの作成](./adding-parameters-that-process-command-line-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-150">For more information, see [Creating a Cmdlet to Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

- <span data-ttu-id="614bc-151">入力処理メソッドは、パイプラインの上流コマンドレットの出力オブジェクトから入力を受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="614bc-151">An input processing method can also receive input from the output object of an upstream cmdlet on the pipeline.</span></span> <span data-ttu-id="614bc-152">詳細については、「[パイプライン入力を処理するためのコマンドレットの作成](./adding-parameters-that-process-pipeline-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-152">For more information, see [Creating a Cmdlet to Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="614bc-153">コマンドレットは、コマンドラインとパイプラインのソースの組み合わせから入力を受け取ることができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-153">Be aware that your cmdlet can receive input from a combination of command-line and pipeline sources.</span></span>

- <span data-ttu-id="614bc-154">ダウンストリームのコマンドレットは、長い間、またはまったく返さない場合があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-154">The downstream cmdlet might not return for a long time, or not at all.</span></span> <span data-ttu-id="614bc-155">そのため、コマンドレットの入力処理メソッドは、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)の呼び出し中にロックを保持しないようにする必要があります。特に、スコープがコマンドレットインスタンスの範囲を超えているロックです。</span><span class="sxs-lookup"><span data-stu-id="614bc-155">For that reason, the input processing method in your cmdlet should not hold locks during calls to [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especially locks for which the scope extends beyond the cmdlet instance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="614bc-156">コマンドレットは、system.string [\*](/dotnet/api/System.Console.WriteLine)またはそれと同等のものを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="614bc-156">Cmdlets should never call [System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine) or its equivalent.</span></span>

- <span data-ttu-id="614bc-157">コマンドレットは、処理が完了したときにクリーンアップするオブジェクト変数を持つ場合があります (たとえば、ファイルハンドルが[システム](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)によって開かれている場合は、そのハンドルを開いたままにして[、プロセスが](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)開かれます。</span><span class="sxs-lookup"><span data-stu-id="614bc-157">Your cmdlet might have object variables to clean up when it is finished processing (for example, if it opens a file handle in the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span></span> <span data-ttu-id="614bc-158">Windows PowerShell ランタイムでは、オブジェクトのクリーンアップを実行する必要があるため、必ずしも必ず[system.object メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)呼び出さないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-158">It is important to remember that the Windows PowerShell runtime does not always call the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method, which should perform object cleanup.</span></span>

<span data-ttu-id="614bc-159">たとえば、コマンドレットが途中で取り消された場合、またはコマンドレットのいずれかの部分で終了エラーが発生した場合[は、を](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="614bc-159">For example, [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) might not be called if the cmdlet is canceled midway or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="614bc-160">したがって、オブジェクトのクリーンアップを必要とするコマンドレットは、ファイナライザーを含む完全な[IDisposable](/dotnet/api/System.IDisposable)パターンを実装する必要があります。これにより、処理の[終了時に](/dotnet/api/System.IDisposable.Dispose)ランタイム[が両方の](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)を呼び出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="614bc-160">Therefore, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including the finalizer, so that the runtime can call both [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) at the end of processing.</span></span>

## <a name="code-sample"></a><span data-ttu-id="614bc-161">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="614bc-161">Code Sample</span></span>

<span data-ttu-id="614bc-162">完全なC#サンプルコードについては、「 [GetProcessSample01 sample](./getprocesssample01-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-162">For the complete C# sample code, see [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="614bc-163">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="614bc-163">Defining Object Types and Formatting</span></span>

<span data-ttu-id="614bc-164">Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="614bc-164">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="614bc-165">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-165">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="614bc-166">新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-166">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="614bc-167">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="614bc-167">Building the Cmdlet</span></span>

<span data-ttu-id="614bc-168">コマンドレットを実装した後、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="614bc-168">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="614bc-169">コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-169">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="614bc-170">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="614bc-170">Testing the Cmdlet</span></span>

<span data-ttu-id="614bc-171">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="614bc-171">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="614bc-172">サンプルの Get Proc コマンドレットのコードは小さいですが、Windows PowerShell ランタイムと既存の .NET オブジェクトが引き続き使用されます。これは、これを有効にするのに十分なものです。</span><span class="sxs-lookup"><span data-stu-id="614bc-172">The code for our sample Get-Proc cmdlet is small, but it still uses the Windows PowerShell runtime and an existing .NET object, which is enough to make it useful.</span></span> <span data-ttu-id="614bc-173">これをテストして、Get 処理可能な処理とその出力の使用方法をより深く理解してみましょう。</span><span class="sxs-lookup"><span data-stu-id="614bc-173">Let's test it to better understand what Get-Proc can do and how its output can be used.</span></span> <span data-ttu-id="614bc-174">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614bc-174">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

1. <span data-ttu-id="614bc-175">Windows PowerShell を起動し、コンピューターで現在実行されているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="614bc-175">Start Windows PowerShell, and get the current processes running on the computer.</span></span>

    ```powershell
    get-proc
    ```

    <span data-ttu-id="614bc-176">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-176">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. <span data-ttu-id="614bc-177">操作を容易にするために、コマンドレットの結果に変数を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="614bc-177">Assign a variable to the cmdlet results for easier manipulation.</span></span>

    ```powershell
    $p=get-proc
    ```

3. <span data-ttu-id="614bc-178">プロセスの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="614bc-178">Get the number of processes.</span></span>

    ```powershell
    $p.length
    ```

    <span data-ttu-id="614bc-179">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-179">The following output appears.</span></span>

    ```output
    63
    ```

4. <span data-ttu-id="614bc-180">特定のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="614bc-180">Retrieve a specific process.</span></span>

    ```powershell
    $p[6]
    ```

    <span data-ttu-id="614bc-181">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-181">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. <span data-ttu-id="614bc-182">このプロセスの開始時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="614bc-182">Get the start time of this process.</span></span>

    ```powershell
    $p[6].starttime
    ```

    <span data-ttu-id="614bc-183">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-183">The following output appears.</span></span>

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. <span data-ttu-id="614bc-184">ハンドル数が500より大きいプロセスを取得し、結果を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="614bc-184">Get the processes for which the handle count is greater than 500, and sort the result.</span></span>

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    <span data-ttu-id="614bc-185">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-185">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. <span data-ttu-id="614bc-186">`Get-Member` コマンドレットを使用して、各プロセスで使用可能なプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="614bc-186">Use the `Get-Member` cmdlet to list the properties available for each process.</span></span>

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    <span data-ttu-id="614bc-187">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614bc-187">The following output appears.</span></span>

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a><span data-ttu-id="614bc-188">参照</span><span class="sxs-lookup"><span data-stu-id="614bc-188">See Also</span></span>

[<span data-ttu-id="614bc-189">コマンドライン入力を処理するコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="614bc-189">Creating a Cmdlet to Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="614bc-190">パイプラインの入力を処理するコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="614bc-190">Creating a Cmdlet to Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="614bc-191">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="614bc-191">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="614bc-192">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="614bc-192">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="614bc-193">[Windows PowerShell の動作](/previous-versions//ms714658(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="614bc-193">[How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85))</span></span>

<span data-ttu-id="614bc-194">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="614bc-194">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="614bc-195">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="614bc-195">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="614bc-196">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="614bc-196">Cmdlet Samples</span></span>](./cmdlet-samples.md)

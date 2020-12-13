---
ms.date: 09/13/2016
ms.topic: reference
title: パラメーターなしでコマンドレットを作成する
description: パラメーターなしでコマンドレットを作成する
ms.openlocfilehash: 5df27ac4c1f6dfcc3e7596d93f8db0f97aae71c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646548"
---
# <a name="creating-a-cmdlet-without-parameters"></a><span data-ttu-id="a3625-103">パラメーターなしでコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="a3625-103">Creating a Cmdlet without Parameters</span></span>

<span data-ttu-id="a3625-104">このセクションでは、パラメーターを使用せずにローカルコンピューターから情報を取得するコマンドレットを作成し、その情報をパイプラインに書き込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3625-104">This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span> <span data-ttu-id="a3625-105">ここで説明するコマンドレットは、ローカルコンピューターのプロセスに関する情報を取得し、その情報をコマンドラインに表示する Get-Proc コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="a3625-105">The cmdlet described here is a Get-Proc cmdlet that retrieves information about the processes of the local computer, and then displays that information at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="a3625-106">コマンドレットを記述するときは、Windows PowerShell®参照アセンブリがディスクにダウンロードされることに注意してください (既定では C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0 にあります)。</span><span class="sxs-lookup"><span data-stu-id="a3625-106">Be aware that when writing cmdlets, the Windows PowerShell® reference assemblies are downloaded onto disk (by default at C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).</span></span> <span data-ttu-id="a3625-107">グローバルアセンブリキャッシュ (GAC) にはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="a3625-107">They are not installed in the Global Assembly Cache (GAC).</span></span>

## <a name="naming-the-cmdlet"></a><span data-ttu-id="a3625-108">コマンドレットの名前付け</span><span class="sxs-lookup"><span data-stu-id="a3625-108">Naming the Cmdlet</span></span>

<span data-ttu-id="a3625-109">コマンドレット名は、コマンドレットによって実行されるアクションを示す動詞と、コマンドレットが処理する項目を示す名詞で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-109">A cmdlet name consists of a verb that indicates the action the cmdlet takes and a noun that indicates the items that the cmdlet acts upon.</span></span> <span data-ttu-id="a3625-110">このサンプル Get-Proc コマンドレットはプロセスオブジェクトを取得するので、 [Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) 列挙型によって定義された動詞 "Get" を使用し、"Proc" という名詞を使用して、コマンドレットがプロセス項目で動作することを示します。</span><span class="sxs-lookup"><span data-stu-id="a3625-110">Because this sample Get-Proc cmdlet retrieves process objects, it uses the verb "Get", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) enumeration, and the noun "Proc" to indicate that the cmdlet works on process items.</span></span>

<span data-ttu-id="a3625-111">コマンドレットに名前を付けるときは、#、() {} [] &-/\ $;: "' <> &#124;  のいずれの文字も使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3625-111">When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ?</span></span> <span data-ttu-id="a3625-112">@ \` .</span><span class="sxs-lookup"><span data-stu-id="a3625-112">@ \` .</span></span>

### <a name="choosing-a-noun"></a><span data-ttu-id="a3625-113">名詞の選択</span><span class="sxs-lookup"><span data-stu-id="a3625-113">Choosing a Noun</span></span>

<span data-ttu-id="a3625-114">固有の名詞を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-114">You should choose a noun that is specific.</span></span> <span data-ttu-id="a3625-115">製品名の短縮版をプレフィックスとして使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3625-115">It is best to use a singular noun prefixed with a shortened version of the product name.</span></span> <span data-ttu-id="a3625-116">この種類のコマンドレット名の例は、" `Get-SQLServer` " です。</span><span class="sxs-lookup"><span data-stu-id="a3625-116">An example cmdlet name of this type is "`Get-SQLServer`".</span></span>

### <a name="choosing-a-verb"></a><span data-ttu-id="a3625-117">動詞の選択</span><span class="sxs-lookup"><span data-stu-id="a3625-117">Choosing a Verb</span></span>

<span data-ttu-id="a3625-118">一連の承認されたコマンドレット動詞名から動詞を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-118">You should use a verb from the set of approved cmdlet verb names.</span></span> <span data-ttu-id="a3625-119">承認されたコマンドレット動詞の詳細については、「 [コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-119">For more information about the approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="a3625-120">コマンドレットクラスの定義</span><span class="sxs-lookup"><span data-stu-id="a3625-120">Defining the Cmdlet Class</span></span>

<span data-ttu-id="a3625-121">コマンドレット名を選択したら、コマンドレットを実装する .NET クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="a3625-121">Once you have chosen a cmdlet name, define a .NET class to implement the cmdlet.</span></span> <span data-ttu-id="a3625-122">このサンプル Get-Proc コマンドレットのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3625-122">Here is the class definition for this sample Get-Proc cmdlet:</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

<span data-ttu-id="a3625-123">クラス定義の前に、構文を使用[](/dotnet/api/System.Management.Automation.CmdletAttribute)して、 `[Cmdlet(verb, noun, ...)]` このクラスをコマンドレットとして指定することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-123">Notice that previous to the class definition, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute, with the syntax `[Cmdlet(verb, noun, ...)]`, is used to identify this class as a cmdlet.</span></span> <span data-ttu-id="a3625-124">これは、すべてのコマンドレットに必要な唯一の属性であり、Windows PowerShell ランタイムでそれらを正しく呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a3625-124">This is the only required attribute for all cmdlets, and it allows the Windows PowerShell runtime to call them correctly.</span></span> <span data-ttu-id="a3625-125">必要に応じて、クラスをさらに宣言する属性キーワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a3625-125">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="a3625-126">サンプルの Getのコマンドクラスの属性宣言では、Get-Proc コマンドレットの名詞と動詞の名前のみを宣言することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-126">Be aware that the attribute declaration for our sample GetProcCommand class declares only the noun and verb names for the Get-Proc cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a3625-127">すべての Windows PowerShell 属性クラスに対して設定できるキーワードは、属性クラスのプロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a3625-127">For all Windows PowerShell attribute classes, the keywords that you can set correspond to properties of the attribute class.</span></span>

<span data-ttu-id="a3625-128">コマンドレットのクラスに名前を付けるときは、クラス名にコマンドレット名を反映することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3625-128">When naming the class of the cmdlet, it is a good practice to reflect the cmdlet name in the class name.</span></span> <span data-ttu-id="a3625-129">これを行うには、"VerbNounCommand" という形式を使用し、"Verb" と "名詞" をコマンドレット名に使用されている動詞と名詞に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a3625-129">To do this, use the form "VerbNounCommand" and replace "Verb" and "Noun" with the verb and noun used in the cmdlet name.</span></span> <span data-ttu-id="a3625-130">前のクラス定義に示されているように、サンプルの Get-Proc コマンドレットは、Getによって実行されるクラスを定義 [します。](/dotnet/api/System.Management.Automation.Cmdlet) このクラスは、system.servicemodel 基本クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="a3625-130">As is shown in the previous class definition, the sample Get-Proc cmdlet defines a class called GetProcCommand, which derives from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) base class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3625-131">Windows PowerShell ランタイムに直接アクセスするコマンドレットを定義する場合は、.NET クラスを [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) 基底クラスから派生させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-131">If you want to define a cmdlet that accesses the Windows PowerShell runtime directly, your .NET class should derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span> <span data-ttu-id="a3625-132">このクラスの詳細については、「 [パラメーターセットを定義するコマンドレットを作成](./adding-parameter-sets-to-a-cmdlet.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-132">For more information about this class, see [Creating a Cmdlet that Defines Parameter Sets](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3625-133">コマンドレットのクラスは、明示的にパブリックとしてマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-133">The class for a cmdlet must be explicitly marked as public.</span></span> <span data-ttu-id="a3625-134">パブリックとしてマークされていないクラスは、既定で内部に設定され、Windows PowerShell ランタイムによって検出されません。</span><span class="sxs-lookup"><span data-stu-id="a3625-134">Classes that are not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="a3625-135">Windows PowerShell では、コマンドレットのクラスとして、 [powershell](/dotnet/api/Microsoft.PowerShell.Commands) の名前空間が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-135">Windows PowerShell uses the [Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) namespace for its cmdlet classes.</span></span> <span data-ttu-id="a3625-136">コマンドレットクラスを API 名前空間のコマンド名前空間に配置することをお勧めします (例、xxx. .PS. コマンド)。</span><span class="sxs-lookup"><span data-stu-id="a3625-136">It is recommended to place your cmdlet classes in a Commands namespace of your API namespace, for example, xxx.PS.Commands.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="a3625-137">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="a3625-137">Overriding an Input Processing Method</span></span>

<span data-ttu-id="a3625-138">System.servicemodel [クラスには、3](/dotnet/api/System.Management.Automation.Cmdlet) つの主要な入力処理メソッドが用意されています。少なくとも1つはコマンドレットがオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-138">The [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class provides three main input processing methods, at least one of which your cmdlet must override.</span></span> <span data-ttu-id="a3625-139">Windows PowerShell がレコードを処理する方法の詳細については、「 [Windows powershell のしくみ](/previous-versions//ms714658(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-139">For more information about how Windows PowerShell processes records, see [How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85)).</span></span>

<span data-ttu-id="a3625-140">すべての種類の入力について、Windows PowerShell ランタイムは、処理を有効にするために、system.string[を呼び出します。](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)</span><span class="sxs-lookup"><span data-stu-id="a3625-140">For all types of input, the Windows PowerShell runtime calls [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) to enable processing.</span></span> <span data-ttu-id="a3625-141">コマンドレットでいくつかの前処理またはセットアップを実行する必要がある場合は、このメソッドをオーバーライドすることによってこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a3625-141">If your cmdlet must perform some preprocessing or setup, it can do this by overriding this method.</span></span>

> [!NOTE]
> <span data-ttu-id="a3625-142">Windows PowerShell では、コマンドレットが呼び出されたときに指定されるパラメーター値のセットを記述するために "レコード" という用語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-142">Windows PowerShell uses the term "record" to describe the set of parameter values supplied when a cmdlet is called.</span></span>

<span data-ttu-id="a3625-143">コマンドレットがパイプライン入力を受け入れる場合は、この [メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) オーバーライドする必要があります。また、 [必要に応じて、](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) system.object メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-143">If your cmdlet accepts pipeline input, it must override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, and optionally the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="a3625-144">たとえば、コマンドレットを使用してすべての入力を [収集し、](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) コマンドレットの実行時に、一度に1つの要素ではなく全体として入力を操作すると、両方のメソッドがオーバーライドされる可能性があり `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="a3625-144">For example, a cmdlet might override both methods if it gathers all input using [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) and then operates on the input as a whole rather than one element at a time, as the `Sort-Object` cmdlet does.</span></span>

<span data-ttu-id="a3625-145">コマンドレットがパイプライン入力を受け取らない場合 [は、このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) オーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-145">If your cmdlet does not take pipeline input, it should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="a3625-146">このメソッドは、並べ替えコマンドレットの場合と同様に、一度に1つの要素に対してコマンドレットを実行できない場合に、その代わりに使用されることに注意して [ください](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 。</span><span class="sxs-lookup"><span data-stu-id="a3625-146">Be aware that this method is frequently used in place of [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) when the cmdlet cannot operate on one element at a time, as is the case for a sorting cmdlet.</span></span>

<span data-ttu-id="a3625-147">このサンプル Get-Proc コマンドレットはパイプライン入力を受け取る必要があるため、[このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドして、system........................................... コマンド[レットの既定](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)の実装を使用[します。](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)</span><span class="sxs-lookup"><span data-stu-id="a3625-147">Because this sample Get-Proc cmdlet must receive pipeline input, it overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method and uses the default implementations for [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) and [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span></span> <span data-ttu-id="a3625-148">[WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを使用して、プロセスを取得し、コマンドラインに書き込むプロセスを取得するために、[このオーバーライドが](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)実行されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-148">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override retrieves processes and writes them to the command line using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span>

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

#### <a name="things-to-remember-about-input-processing"></a><span data-ttu-id="a3625-149">入力処理に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="a3625-149">Things to Remember About Input Processing</span></span>

- <span data-ttu-id="a3625-150">入力の既定のソースは、コマンドラインでユーザーによって指定された明示的なオブジェクト (文字列など) です。</span><span class="sxs-lookup"><span data-stu-id="a3625-150">The default source for input is an explicit object (for example, a string) provided by the user on the command line.</span></span> <span data-ttu-id="a3625-151">詳細については、「 [コマンドライン入力を処理するためのコマンドレットの作成](./adding-parameters-that-process-command-line-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-151">For more information, see [Creating a Cmdlet to Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

- <span data-ttu-id="a3625-152">入力処理メソッドは、パイプラインの上流コマンドレットの出力オブジェクトから入力を受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="a3625-152">An input processing method can also receive input from the output object of an upstream cmdlet on the pipeline.</span></span> <span data-ttu-id="a3625-153">詳細については、「 [パイプライン入力を処理するためのコマンドレットの作成](./adding-parameters-that-process-pipeline-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-153">For more information, see [Creating a Cmdlet to Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="a3625-154">コマンドレットは、コマンドラインとパイプラインのソースの組み合わせから入力を受け取ることができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-154">Be aware that your cmdlet can receive input from a combination of command-line and pipeline sources.</span></span>

- <span data-ttu-id="a3625-155">ダウンストリームのコマンドレットは、長い間、またはまったく返さない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-155">The downstream cmdlet might not return for a long time, or not at all.</span></span> <span data-ttu-id="a3625-156">そのため、コマンドレットの入力処理メソッドは、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)の呼び出し中にロックを保持しないようにする必要があります。特に、スコープがコマンドレットインスタンスの範囲を超えているロックです。</span><span class="sxs-lookup"><span data-stu-id="a3625-156">For that reason, the input processing method in your cmdlet should not hold locks during calls to [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especially locks for which the scope extends beyond the cmdlet instance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3625-157">コマンドレットは、system.string [\*](/dotnet/api/System.Console.WriteLine) またはそれと同等のものを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a3625-157">Cmdlets should never call [System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine) or its equivalent.</span></span>

- <span data-ttu-id="a3625-158">コマンドレットは、処理が完了したときにクリーンアップするオブジェクト変数を持つ場合があります (たとえば、ファイルハンドルが [システム](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) によって開かれている場合は、そのハンドルを開いたままにして [、プロセスが](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)開かれます。</span><span class="sxs-lookup"><span data-stu-id="a3625-158">Your cmdlet might have object variables to clean up when it is finished processing (for example, if it opens a file handle in the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span></span> <span data-ttu-id="a3625-159">Windows PowerShell ランタイムでは、オブジェクトのクリーンアップを実行する必要があるため、必ずしも必ず [system.object メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 呼び出さないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-159">It is important to remember that the Windows PowerShell runtime does not always call the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method, which should perform object cleanup.</span></span>

<span data-ttu-id="a3625-160">たとえば、コマンドレットが途中で取り消された場合、またはコマンドレットのいずれかの部分で終了エラーが発生した場合 [は、を](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a3625-160">For example, [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) might not be called if the cmdlet is canceled midway or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="a3625-161">したがって、オブジェクトのクリーンアップを必要とするコマンドレットは、ファイナライザーを含む完全な[IDisposable](/dotnet/api/System.IDisposable)パターンを実装する必要があります。これにより、処理の[終了時に](/dotnet/api/System.IDisposable.Dispose)ランタイム[が両方の](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)を呼び出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="a3625-161">Therefore, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including the finalizer, so that the runtime can call both [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) at the end of processing.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a3625-162">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="a3625-162">Code Sample</span></span>

<span data-ttu-id="a3625-163">完全な C# サンプルコードについては、「 [GetProcessSample01 sample](./getprocesssample01-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-163">For the complete C# sample code, see [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="a3625-164">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="a3625-164">Defining Object Types and Formatting</span></span>

<span data-ttu-id="a3625-165">Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="a3625-165">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="a3625-166">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-166">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="a3625-167">新しい型を定義する、または既存の型を拡張する方法の詳細については、「 [オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-167">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="a3625-168">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="a3625-168">Building the Cmdlet</span></span>

<span data-ttu-id="a3625-169">コマンドレットを実装した後、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3625-169">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="a3625-170">コマンドレットの登録の詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-170">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="a3625-171">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="a3625-171">Testing the Cmdlet</span></span>

<span data-ttu-id="a3625-172">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="a3625-172">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="a3625-173">サンプル Get-Proc コマンドレットのコードは小さいですが、Windows PowerShell ランタイムと既存の .NET オブジェクトが引き続き使用されます。これにより、これが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="a3625-173">The code for our sample Get-Proc cmdlet is small, but it still uses the Windows PowerShell runtime and an existing .NET object, which is enough to make it useful.</span></span> <span data-ttu-id="a3625-174">これをテストして、Get-Proc できることと、その出力を使用する方法について理解を深めてみましょう。</span><span class="sxs-lookup"><span data-stu-id="a3625-174">Let's test it to better understand what Get-Proc can do and how its output can be used.</span></span> <span data-ttu-id="a3625-175">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3625-175">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

1. <span data-ttu-id="a3625-176">Windows PowerShell を起動し、コンピューターで現在実行されているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a3625-176">Start Windows PowerShell, and get the current processes running on the computer.</span></span>

    ```powershell
    get-proc
    ```

    <span data-ttu-id="a3625-177">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-177">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. <span data-ttu-id="a3625-178">操作を容易にするために、コマンドレットの結果に変数を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a3625-178">Assign a variable to the cmdlet results for easier manipulation.</span></span>

    ```powershell
    $p=get-proc
    ```

3. <span data-ttu-id="a3625-179">プロセスの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a3625-179">Get the number of processes.</span></span>

    ```powershell
    $p.length
    ```

    <span data-ttu-id="a3625-180">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-180">The following output appears.</span></span>

    ```output
    63
    ```

4. <span data-ttu-id="a3625-181">特定のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a3625-181">Retrieve a specific process.</span></span>

    ```powershell
    $p[6]
    ```

    <span data-ttu-id="a3625-182">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-182">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. <span data-ttu-id="a3625-183">このプロセスの開始時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="a3625-183">Get the start time of this process.</span></span>

    ```powershell
    $p[6].starttime
    ```

    <span data-ttu-id="a3625-184">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-184">The following output appears.</span></span>

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. <span data-ttu-id="a3625-185">ハンドル数が500より大きいプロセスを取得し、結果を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="a3625-185">Get the processes for which the handle count is greater than 500, and sort the result.</span></span>

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    <span data-ttu-id="a3625-186">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-186">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. <span data-ttu-id="a3625-187">`Get-Member`各プロセスで使用可能なプロパティを一覧表示するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3625-187">Use the `Get-Member` cmdlet to list the properties available for each process.</span></span>

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    <span data-ttu-id="a3625-188">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3625-188">The following output appears.</span></span>

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a><span data-ttu-id="a3625-189">参照</span><span class="sxs-lookup"><span data-stu-id="a3625-189">See Also</span></span>

[<span data-ttu-id="a3625-190">コマンドライン入力を処理するコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="a3625-190">Creating a Cmdlet to Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="a3625-191">パイプラインの入力を処理するコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="a3625-191">Creating a Cmdlet to Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="a3625-192">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="a3625-192">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="a3625-193">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="a3625-193">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="a3625-194">[Windows PowerShell の動作](/previous-versions//ms714658(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="a3625-194">[How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85))</span></span>

<span data-ttu-id="a3625-195">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="a3625-195">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="a3625-196">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="a3625-196">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="a3625-197">コマンドレット サンプル</span><span class="sxs-lookup"><span data-stu-id="a3625-197">Cmdlet Samples</span></span>](./cmdlet-samples.md)

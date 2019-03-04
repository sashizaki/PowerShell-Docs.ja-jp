---
title: パラメーターを指定しないでコマンドレットを作成する |Microsoft Docs
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
ms.openlocfilehash: 75a45e539b45b50714951f2b992d9ecf69de4664
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860648"
---
# <a name="creating-a-cmdlet-without-parameters"></a><span data-ttu-id="49659-102">パラメーターなしでコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="49659-102">Creating a Cmdlet without Parameters</span></span>

<span data-ttu-id="49659-103">このセクションでは、パラメーターを使用せず、ローカル コンピューターから情報を取得し、パイプラインに情報を書き込みますコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49659-103">This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span> <span data-ttu-id="49659-104">ここで説明するコマンドレットは、ローカル コンピューターのプロセスに関する情報を取得し、コマンドラインでその情報を表示する Get-proc コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="49659-104">The cmdlet described here is a Get-Proc cmdlet that retrieves information about the processes of the local computer, and then displays that information at the command line.</span></span>

<span data-ttu-id="49659-105">このセクションのトピックで、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49659-105">Topics in this section include the following:</span></span>

- [<span data-ttu-id="49659-106">コマンドレットの名前を付ける</span><span class="sxs-lookup"><span data-stu-id="49659-106">Naming the Cmdlet</span></span>](#Naming-the-Cmdlet)

- [<span data-ttu-id="49659-107">コマンドレット クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="49659-107">Defining the Cmdlet Class</span></span>](#Defining-the-Cmdlet-Class)

- [<span data-ttu-id="49659-108">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="49659-108">Overriding an Input Processing Method</span></span>](#Overriding-an-Input-Processing-Method)

- [<span data-ttu-id="49659-109">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="49659-109">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="49659-110">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="49659-110">Defining Object Types and Formatting</span></span>](#Defining-Object-Types-and-Formatting)

- [<span data-ttu-id="49659-111">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="49659-111">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="49659-112">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="49659-112">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

> [!NOTE]
> <span data-ttu-id="49659-113">コマンドレットを記述する場合、Windows PowerShell® 参照アセンブリがダウンロードされるディスク上に (既定で C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0 など) を認識します。グローバル アセンブリ キャッシュ (GAC) には未インストールします。</span><span class="sxs-lookup"><span data-stu-id="49659-113">Be aware that when writing cmdlets, the Windows PowerShell® reference assemblies are downloaded onto disk (by default at C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).They are not installed in the Global Assembly Cache (GAC).</span></span>

## <a name="naming-the-cmdlet"></a><span data-ttu-id="49659-114">コマンドレットの名前を付ける</span><span class="sxs-lookup"><span data-stu-id="49659-114">Naming the Cmdlet</span></span>

<span data-ttu-id="49659-115">コマンドレット名は、コマンドレットは、アクションを示す動詞と名詞コマンドレットが実行される項目を示すで構成されます。</span><span class="sxs-lookup"><span data-stu-id="49659-115">A cmdlet name consists of a verb that indicates the action the cmdlet takes and a noun that indicates the items that the cmdlet acts upon.</span></span> <span data-ttu-id="49659-116">"Get,"で定義されている動詞を使用、このサンプル Get-proc コマンドレットは、プロセス オブジェクトを取得するため、 [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon)列挙、およびプロセスの項目に、コマンドレットが動作するかを示すには、"Proc"という名詞の部分。</span><span class="sxs-lookup"><span data-stu-id="49659-116">Because this sample Get-Proc cmdlet retrieves process objects, it uses the verb "Get", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) enumeration, and the noun "Proc" to indicate that the cmdlet works on process items.</span></span>

<span data-ttu-id="49659-117">When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ?</span><span class="sxs-lookup"><span data-stu-id="49659-117">When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ?</span></span> <span data-ttu-id="49659-118">@ \` .</span><span class="sxs-lookup"><span data-stu-id="49659-118">@ \` .</span></span>

### <a name="choosing-a-noun"></a><span data-ttu-id="49659-119">名詞を選択します。</span><span class="sxs-lookup"><span data-stu-id="49659-119">Choosing a Noun</span></span>

<span data-ttu-id="49659-120">固有名詞を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49659-120">You should choose a noun that is specific.</span></span> <span data-ttu-id="49659-121">短縮バージョン、製品名の付いた名詞の単数形を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49659-121">It is best to use a singular noun prefixed with a shortened version of the product name.</span></span> <span data-ttu-id="49659-122">この型の例のコマンドレットの名前は"`Get-SQLServer`"。</span><span class="sxs-lookup"><span data-stu-id="49659-122">An example cmdlet name of this type is "`Get-SQLServer`".</span></span>

### <a name="choosing-a-verb"></a><span data-ttu-id="49659-123">動詞を選択します。</span><span class="sxs-lookup"><span data-stu-id="49659-123">Choosing a Verb</span></span>

<span data-ttu-id="49659-124">承認されたコマンドレット動詞名のセットからの動詞を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49659-124">You should use a verb from the set of approved cmdlet verb names.</span></span> <span data-ttu-id="49659-125">承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="49659-125">For more information about the approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="49659-126">コマンドレット クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="49659-126">Defining the Cmdlet Class</span></span>

<span data-ttu-id="49659-127">コマンドレット名を選択すると、コマンドレットを実装する .NET クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="49659-127">Once you have chosen a cmdlet name, define a .NET class to implement the cmdlet.</span></span> <span data-ttu-id="49659-128">このサンプル Get-proc コマンドレットのクラス定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="49659-128">Here is the class definition for this sample Get-Proc cmdlet:</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

<span data-ttu-id="49659-129">クラスの定義の前にあることに注意して、 [System.Management.Automation.Cmdletattribute](/dotnet/api/System.Management.Automation.CmdletAttribute)属性構文と`[Cmdlet(verb, noun, ...)]`、コマンドレットとしては、このクラスを識別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="49659-129">Notice that previous to the class definition, the [System.Management.Automation.Cmdletattribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute, with the syntax `[Cmdlet(verb, noun, ...)]`, is used to identify this class as a cmdlet.</span></span> <span data-ttu-id="49659-130">これは、すべてのコマンドレットの唯一の必須属性でき、これらを正しく呼び出す Windows PowerShell ランタイム。</span><span class="sxs-lookup"><span data-stu-id="49659-130">This is the only required attribute for all cmdlets, and it allows the Windows PowerShell runtime to call them correctly.</span></span> <span data-ttu-id="49659-131">必要に応じてさらに、クラスを宣言する属性のキーワードを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="49659-131">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="49659-132">サンプル GetProcCommand クラスの属性の宣言が Get-proc コマンドレットの名詞と動詞名だけを宣言することに注意します。</span><span class="sxs-lookup"><span data-stu-id="49659-132">Be aware that the attribute declaration for our sample GetProcCommand class declares only the noun and verb names for the Get-Proc cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="49659-133">設定できるキーワードは、Windows PowerShell のすべての属性クラスの属性クラスのプロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="49659-133">For all Windows PowerShell attribute classes, the keywords that you can set correspond to properties of the attribute class.</span></span>

<span data-ttu-id="49659-134">コマンドレットのクラスの名前を付けるときは、クラス名でコマンドレット名を反映することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49659-134">When naming the class of the cmdlet, it is a good practice to reflect the cmdlet name in the class name.</span></span> <span data-ttu-id="49659-135">これを行うには、"VerbNounCommand"の形式を使用し、動詞と名詞を使用、コマンドレット名を「動詞」と「名詞」を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="49659-135">To do this, use the form "VerbNounCommand" and replace "Verb" and "Noun" with the verb and noun used in the cmdlet name.</span></span> <span data-ttu-id="49659-136">サンプルの Get-proc コマンドレットがという GetProcCommand から派生するクラスを定義しますが示すように、前のクラス定義で、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="49659-136">As is shown in the previous class definition, the sample Get-Proc cmdlet defines a class called GetProcCommand, which derives from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) base class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49659-137">Windows PowerShell ランタイムに直接アクセスするためのコマンドレットを定義する場合は、.NET クラスの派生元、 [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="49659-137">If you want to define a cmdlet that accesses the Windows PowerShell runtime directly, your .NET class should derive from the [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span> <span data-ttu-id="49659-138">このクラスの詳細については、次を参照してください。[コマンドレットにその定義のパラメーター セットを作成する](./adding-parameter-sets-to-a-cmdlet.md)します。</span><span class="sxs-lookup"><span data-stu-id="49659-138">For more information about this class, see [Creating a Cmdlet that Defines Parameter Sets](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

> [!NOTE]
> <span data-ttu-id="49659-139">コマンドレットのクラスする必要があります明示的にパブリックと指定します。</span><span class="sxs-lookup"><span data-stu-id="49659-139">The class for a cmdlet must be explicitly marked as public.</span></span> <span data-ttu-id="49659-140">Public としてマークされていないクラスは、内部には既定でと、Windows PowerShell ランタイムでは検出されません。</span><span class="sxs-lookup"><span data-stu-id="49659-140">Classes that are not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="49659-141">Windows PowerShell を使用して、 [Microsoft.Powershell.Commands](/dotnet/api/Microsoft.PowerShell.Commands)コマンドレット クラスの名前空間。</span><span class="sxs-lookup"><span data-stu-id="49659-141">Windows PowerShell uses the [Microsoft.Powershell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) namespace for its cmdlet classes.</span></span> <span data-ttu-id="49659-142">API 名前空間、xxx.PS.Commands などのコマンドの名前空間に、コマンドレット クラスを配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49659-142">It is recommended to place your cmdlet classes in a Commands namespace of your API namespace, for example, xxx.PS.Commands.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="49659-143">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="49659-143">Overriding an Input Processing Method</span></span>

<span data-ttu-id="49659-144">[System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラスは、コマンドレットをオーバーライドする必要がありますが少なくとも 1 つ、3 つの主な入力処理メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="49659-144">The [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class provides three main input processing methods, at least one of which your cmdlet must override.</span></span> <span data-ttu-id="49659-145">Windows PowerShell がレコードを処理する方法の詳細については、次を参照してください。 [Windows PowerShell のしくみ](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)します。</span><span class="sxs-lookup"><span data-stu-id="49659-145">For more information about how Windows PowerShell processes records, see [How Windows PowerShell Works](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).</span></span>

<span data-ttu-id="49659-146">Windows PowerShell ランタイムが呼び出すすべての種類の入力では、 [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="49659-146">For all types of input, the Windows PowerShell runtime calls [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) to enable processing.</span></span> <span data-ttu-id="49659-147">コマンドレットは、前処理またはセットアップを実行する必要がある場合、このメソッドをオーバーライドすることでこれが実行できます。</span><span class="sxs-lookup"><span data-stu-id="49659-147">If your cmdlet must perform some preprocessing or setup, it can do this by overriding this method.</span></span>

> [!NOTE]
> <span data-ttu-id="49659-148">Windows PowerShell では、"record"という用語を使用して、コマンドレットが呼び出されたときに指定されたパラメーター値のセットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49659-148">Windows PowerShell uses the term "record" to describe the set of parameter values supplied when a cmdlet is called.</span></span>

<span data-ttu-id="49659-149">これをオーバーライドする必要があります、コマンドレットがパイプラインの入力を受け入れる場合、 [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッド、および必要に応じて、 [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="49659-149">If your cmdlet accepts pipeline input, it must override the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, and optionally the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="49659-150">たとえば、コマンドレットの方が優先両方のメソッドを使用して、すべての入力を収集する場合[System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)し、入力に 1 つの要素ではなく、全体として、一度にとして動作し、 `Sort-Object`コマンドレットでは。</span><span class="sxs-lookup"><span data-stu-id="49659-150">For example, a cmdlet might override both methods if it gathers all input using [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) and then operates on the input as a whole rather than one element at a time, as the `Sort-Object` cmdlet does.</span></span>

<span data-ttu-id="49659-151">これをオーバーライドする必要があります、コマンドレットがパイプラインの入力を受け取らない場合、 [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。</span><span class="sxs-lookup"><span data-stu-id="49659-151">If your cmdlet does not take pipeline input, it should override the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="49659-152">このメソッドは、の代わりに頻繁に使用されるかどうかを注意[System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)ときコマンドレットは操作できません。 1 つの要素、時に、並べ替えコマンドレットの場合と同様です。</span><span class="sxs-lookup"><span data-stu-id="49659-152">Be aware that this method is frequently used in place of [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) when the cmdlet cannot operate on one element at a time, as is the case for a sorting cmdlet.</span></span>

<span data-ttu-id="49659-153">このサンプル Get-proc コマンドレットは、パイプラインの入力を受け取る必要があります、ため、オーバーライド、 [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドの既定の実装を使用して[System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)と[System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)します。</span><span class="sxs-lookup"><span data-stu-id="49659-153">Because this sample Get-Proc cmdlet must receive pipeline input, it overrides the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method and uses the default implementations for [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) and [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span></span> <span data-ttu-id="49659-154">[System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override キーワードを使用して、コマンドラインに書き込むし、プロセスを取得します、 [System.Management.Automation.Cmdlet.Writeobject\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッド。</span><span class="sxs-lookup"><span data-stu-id="49659-154">The [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override retrieves processes and writes them to the command line using the [System.Management.Automation.Cmdlet.Writeobject\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span>

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

#### <a name="things-to-remember-about-input-processing"></a><span data-ttu-id="49659-155">入力の処理に関する注意点</span><span class="sxs-lookup"><span data-stu-id="49659-155">Things to Remember About Input Processing</span></span>

- <span data-ttu-id="49659-156">入力の既定のソースは、コマンドラインでユーザーによって提供される明示的なオブジェクト (たとえば、文字列) です。</span><span class="sxs-lookup"><span data-stu-id="49659-156">The default source for input is an explicit object (for example, a string) provided by the user on the command line.</span></span> <span data-ttu-id="49659-157">詳細については、次を参照してください。[コマンドライン入力データを処理するコマンドレットを作成する](./adding-parameters-that-process-command-line-input.md)します。</span><span class="sxs-lookup"><span data-stu-id="49659-157">For more information, see [Creating a Cmdlet to Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

- <span data-ttu-id="49659-158">メソッドの処理の入力では、パイプラインのアップ ストリームのコマンドレットの出力オブジェクトからの入力も受信できます。</span><span class="sxs-lookup"><span data-stu-id="49659-158">An input processing method can also receive input from the output object of an upstream cmdlet on the pipeline.</span></span> <span data-ttu-id="49659-159">詳細については、次を参照してください。[プロセス パイプラインの入力にコマンドレットを作成する](./adding-parameters-that-process-pipeline-input.md)します。</span><span class="sxs-lookup"><span data-stu-id="49659-159">For more information, see [Creating a Cmdlet to Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="49659-160">対応するコマンドレットはコマンド ラインの組み合わせから入力を受け取るし、パイプラインのソースします。</span><span class="sxs-lookup"><span data-stu-id="49659-160">Be aware that your cmdlet can receive input from a combination of command-line and pipeline sources.</span></span>

- <span data-ttu-id="49659-161">長い間、またはまったく、ダウン ストリームのコマンドレットを返しません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="49659-161">The downstream cmdlet might not return for a long time, or not at all.</span></span> <span data-ttu-id="49659-162">そのため、入力、コマンドレットでメソッドを処理する必要がありますロックが保持されない呼び出し中に[System.Management.Automation.Cmdlet.Writeobject\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)、特にロックが、スコープがコマンドレットのインスタンスを超えて拡張されます。</span><span class="sxs-lookup"><span data-stu-id="49659-162">For that reason, the input processing method in your cmdlet should not hold locks during calls to [System.Management.Automation.Cmdlet.Writeobject\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especially locks for which the scope extends beyond the cmdlet instance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49659-163">コマンドレットは呼び出さないで[System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine)またはそれと同等です。</span><span class="sxs-lookup"><span data-stu-id="49659-163">Cmdlets should never call [System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine) or its equivalent.</span></span>

- <span data-ttu-id="49659-164">コマンドレットはオブジェクト変数が完了したら、クリーンアップする必要がありますの処理 (ファイル ハンドルが開く場合など、 [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッドと保持で使用するためのハンドルを開く[System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord))。</span><span class="sxs-lookup"><span data-stu-id="49659-164">Your cmdlet might have object variables to clean up when it is finished processing (for example, if it opens a file handle in the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span></span> <span data-ttu-id="49659-165">Windows PowerShell ランタイムが常に呼び出していないことに注意してください、 [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッドで、オブジェクトのクリーンアップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49659-165">It is important to remember that the Windows PowerShell runtime does not always call the [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method, which should perform object cleanup.</span></span>

<span data-ttu-id="49659-166">たとえば、 [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)途中、コマンドレットが取り消されたかコマンドレットのすべての部分でエラーが発生した場合は、終了が呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="49659-166">For example, [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) might not be called if the cmdlet is canceled midway or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="49659-167">したがって、オブジェクトのクリーンアップが必要なコマンドレットを完全に実装[System.Idisposable](/dotnet/api/System.IDisposable)パターン、ランタイムは、両方を呼び出すことができますができるように、ファイナライザーを含む[System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)と[System.Idisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose)処理の最後にします。</span><span class="sxs-lookup"><span data-stu-id="49659-167">Therefore, a cmdlet that requires object cleanup should implement the complete [System.Idisposable](/dotnet/api/System.IDisposable) pattern, including the finalizer, so that the runtime can call both [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.Idisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) at the end of processing.</span></span>

## <a name="code-sample"></a><span data-ttu-id="49659-168">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="49659-168">Code Sample</span></span>

<span data-ttu-id="49659-169">完全なC#サンプル コードは、「 [GetProcessSample01 サンプル](./getprocesssample01-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="49659-169">For the complete C# sample code, see [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="49659-170">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="49659-170">Defining Object Types and Formatting</span></span>

<span data-ttu-id="49659-171">Windows PowerShell は、.NET オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="49659-171">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="49659-172">その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49659-172">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="49659-173">新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。</span><span class="sxs-lookup"><span data-stu-id="49659-173">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="49659-174">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="49659-174">Building the Cmdlet</span></span>

<span data-ttu-id="49659-175">コマンドレットを実装するには、後にする必要がありますに登録する Windows PowerShell Windows PowerShell スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="49659-175">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="49659-176">コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。</span><span class="sxs-lookup"><span data-stu-id="49659-176">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="49659-177">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="49659-177">Testing the Cmdlet</span></span>

<span data-ttu-id="49659-178">コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="49659-178">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="49659-179">サンプル Get-proc コマンドレットのコードは小さいが、Windows PowerShell ランタイムとこれには、既存の .NET オブジェクトを引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="49659-179">The code for our sample Get-Proc cmdlet is small, but it still uses the Windows PowerShell runtime and an existing .NET object, which is enough to make it useful.</span></span> <span data-ttu-id="49659-180">Get プロシージャが実行できる内容とその出力を使用する方法を理解することをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="49659-180">Let's test it to better understand what Get-Proc can do and how its output can be used.</span></span> <span data-ttu-id="49659-181">詳細については、コマンドラインからコマンドレットを使用して、次を参照してください。、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="49659-181">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

1. <span data-ttu-id="49659-182">Windows PowerShell を起動し、コンピューターで実行されている現在のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="49659-182">Start Windows PowerShell, and get the current processes running on the computer.</span></span>

    ```powershell
    get-proc
    ```

    <span data-ttu-id="49659-183">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49659-183">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. <span data-ttu-id="49659-184">コマンドレットの結果を簡単に操作するには、変数を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="49659-184">Assign a variable to the cmdlet results for easier manipulation.</span></span>

    ```powershell
    $p=get-proc
    ```

3. <span data-ttu-id="49659-185">プロセスの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="49659-185">Get the number of processes.</span></span>

    ```powershell
    $p.length
    ```

    <span data-ttu-id="49659-186">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49659-186">The following output appears.</span></span>

    ```output
    63
    ```

4. <span data-ttu-id="49659-187">特定のプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="49659-187">Retrieve a specific process.</span></span>

    ```powershell
    $p[6]
    ```

    <span data-ttu-id="49659-188">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49659-188">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. <span data-ttu-id="49659-189">このプロセスの開始時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="49659-189">Get the start time of this process.</span></span>

    ```powershell
    $p[6].starttime
    ```

    <span data-ttu-id="49659-190">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49659-190">The following output appears.</span></span>

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. <span data-ttu-id="49659-191">ハンドル数は 500 より大きいプロセスを取得し、結果を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="49659-191">Get the processes for which the handle count is greater than 500, and sort the result.</span></span>

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    <span data-ttu-id="49659-192">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49659-192">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. <span data-ttu-id="49659-193">使用して、`Get-Member`コマンドレットをそれぞれのプロセスで使用できるプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="49659-193">Use the `Get-Member` cmdlet to list the properties available for each process.</span></span>

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    <span data-ttu-id="49659-194">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49659-194">The following output appears.</span></span>

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a><span data-ttu-id="49659-195">参照</span><span class="sxs-lookup"><span data-stu-id="49659-195">See Also</span></span>

[<span data-ttu-id="49659-196">コマンドラインの入力を処理するコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="49659-196">Creating a Cmdlet to Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="49659-197">パイプラインの入力を処理するコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="49659-197">Creating a Cmdlet to Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="49659-198">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="49659-198">How to Create a Windows PowerShell Cmdlet</span></span>](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="49659-199">オブジェクトの種類を拡張して、書式設定</span><span class="sxs-lookup"><span data-stu-id="49659-199">Extending Object Types and Formatting</span></span>](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="49659-200">Windows PowerShell の動作</span><span class="sxs-lookup"><span data-stu-id="49659-200">How Windows PowerShell Works</span></span>](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[<span data-ttu-id="49659-201">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="49659-201">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="49659-202">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="49659-202">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="49659-203">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="49659-203">Cmdlet Samples</span></span>](./cmdlet-samples.md)
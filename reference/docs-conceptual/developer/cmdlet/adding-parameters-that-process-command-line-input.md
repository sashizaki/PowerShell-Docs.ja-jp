---
title: コマンドライン入力を処理するパラメーターを追加する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], parameters
- Get-Proc cmdlet [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], command line input
- command line input [PowerShell Programmer's Guide]
- parameters [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], creating
ms.assetid: da0b32f8-7b51-440e-a061-3177b5759e0e
caps.latest.revision: 9
ms.openlocfilehash: b8ade5607595fd4453b2a4d69a6345880e58192b
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870457"
---
# <a name="adding-parameters-that-process-command-line-input"></a><span data-ttu-id="e8f83-102">コマンドライン入力を処理するパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="e8f83-102">Adding Parameters That Process Command-Line Input</span></span>

<span data-ttu-id="e8f83-103">コマンドレットの1つの入力ソースは、コマンドラインです。</span><span class="sxs-lookup"><span data-stu-id="e8f83-103">One source of input for a cmdlet is the command line.</span></span> <span data-ttu-id="e8f83-104">このトピックでは、コマンドレットに渡された明示的なオブジェクトに基づいてローカルコンピューターからの入力を処理できるように、`Get-Proc` コマンドレット ([最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関するページで説明) にパラメーターを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-104">This topic describes how to add a parameter to the `Get-Proc` cmdlet (which is described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process input from the local computer based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="e8f83-105">ここで説明する `Get-Proc` コマンドレットは、名前に基づいてプロセスを取得し、コマンドプロンプトでプロセスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-105">The `Get-Proc` cmdlet described here retrieves processes based on their names, and then displays information about the processes at a command prompt.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="e8f83-106">コマンドレットクラスの定義</span><span class="sxs-lookup"><span data-stu-id="e8f83-106">Defining the Cmdlet Class</span></span>

<span data-ttu-id="e8f83-107">コマンドレットの作成の最初の手順は、コマンドレットの名前付けと、コマンドレットを実装する .NET Framework クラスの宣言です。</span><span class="sxs-lookup"><span data-stu-id="e8f83-107">The first step in cmdlet creation is cmdlet naming and the declaration of the .NET Framework class that implements the cmdlet.</span></span> <span data-ttu-id="e8f83-108">このコマンドレットはプロセス情報を取得するため、ここで選択した動詞名は "Get" です。</span><span class="sxs-lookup"><span data-stu-id="e8f83-108">This cmdlet retrieves process information, so the verb name chosen here is "Get."</span></span> <span data-ttu-id="e8f83-109">(情報を取得できるほとんどすべての種類のコマンドレットは、コマンドライン入力を処理できます)。承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f83-109">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="e8f83-110">`Get-Proc` コマンドレットのクラス宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-110">Here's the class declaration for the `Get-Proc` cmdlet.</span></span> <span data-ttu-id="e8f83-111">この定義の詳細については[、最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関する説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8f83-111">Details about this definition are provided in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a><span data-ttu-id="e8f83-112">パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="e8f83-112">Declaring Parameters</span></span>

<span data-ttu-id="e8f83-113">コマンドレットパラメーターを使用すると、ユーザーはコマンドレットに入力を提供できます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-113">A cmdlet parameter enables the user to provide input to the cmdlet.</span></span> <span data-ttu-id="e8f83-114">次の例では、`Get-Proc` と `Get-Member` がパイプラインのコマンドレットの名前であり、`MemberType` は `Get-Member` コマンドレットのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e8f83-114">In the following example, `Get-Proc` and `Get-Member` are the names of pipelined cmdlets, and `MemberType` is a parameter for the `Get-Member` cmdlet.</span></span> <span data-ttu-id="e8f83-115">パラメーターには、"property" という引数があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-115">The parameter has the argument "property."</span></span>

<span data-ttu-id="e8f83-116">**PS > get-proc;`get-member` membertype プロパティ**</span><span class="sxs-lookup"><span data-stu-id="e8f83-116">**PS> get-proc ; `get-member` -membertype property**</span></span>

<span data-ttu-id="e8f83-117">コマンドレットのパラメーターを宣言するには、パラメーターを表すプロパティを最初に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-117">To declare parameters for a cmdlet, you must first define the properties that represent the parameters.</span></span> <span data-ttu-id="e8f83-118">`Get-Proc` コマンドレットでは、唯一のパラメーターは `Name`です。この例では、取得する .NET Framework process オブジェクトの名前を表します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-118">In the `Get-Proc` cmdlet, the only parameter is `Name`, which in this case represents the name of the .NET Framework process object to retrieve.</span></span> <span data-ttu-id="e8f83-119">このため、コマンドレットクラスは、名前の配列を受け入れる文字列型のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-119">Therefore, the cmdlet class defines a property of type string to accept an array of names.</span></span>

<span data-ttu-id="e8f83-120">`Get-Proc` コマンドレットの `Name` パラメーターのパラメーター宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-120">Here's the parameter declaration for the `Name` parameter of the `Get-Proc` cmdlet.</span></span>

```csharp
/// <summary>
/// Specify the cmdlet Name parameter.
/// </summary>
  [Parameter(Position = 0)]
  [ValidateNotNullOrEmpty]
  public string[] Name
  {
    get { return processNames; }
    set { processNames = value; }
  }
  private string[] processNames;

  #endregion Parameters
```

```vb
<Parameter(Position:=0), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

<span data-ttu-id="e8f83-121">このプロパティが `Name` パラメーターであることを Windows PowerShell ランタイムに通知するには、プロパティ定義に[system.string 属性を](/dotnet/api/System.Management.Automation.ParameterAttribute)追加します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-121">To inform the Windows PowerShell runtime that this property is the `Name` parameter, a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute is added to the property definition.</span></span> <span data-ttu-id="e8f83-122">この属性を宣言するための基本構文は `[Parameter()]`です。</span><span class="sxs-lookup"><span data-stu-id="e8f83-122">The basic syntax for declaring this attribute is `[Parameter()]`.</span></span>

> [!NOTE]
> <span data-ttu-id="e8f83-123">パラメーターは、明示的にパブリックとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-123">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="e8f83-124">既定でパブリックに設定されていないパラメーターは、Windows PowerShell ランタイムによって検出されません。</span><span class="sxs-lookup"><span data-stu-id="e8f83-124">Parameters that are not marked as public default to internal and are not found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="e8f83-125">このコマンドレットは、`Name` パラメーターに文字列の配列を使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-125">This cmdlet uses an array of strings for the `Name` parameter.</span></span> <span data-ttu-id="e8f83-126">可能であれば、コマンドレットでパラメーターを配列として定義する必要もあります。これにより、コマンドレットでは複数の項目を受け入れることができるためです。</span><span class="sxs-lookup"><span data-stu-id="e8f83-126">If possible, your cmdlet should also define a parameter as an array, because this allows the cmdlet to accept more than one item.</span></span>

#### <a name="things-to-remember-about-parameter-definitions"></a><span data-ttu-id="e8f83-127">パラメーター定義に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="e8f83-127">Things to Remember About Parameter Definitions</span></span>

- <span data-ttu-id="e8f83-128">コマンドレットが Windows PowerShell コマンドレットと互換性があることを確認するために、定義済みの Windows PowerShell パラメーター名とデータ型をできるだけ再利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-128">Predefined Windows PowerShell parameter names and data types should be reused as much as possible to ensure that your cmdlet is compatible with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e8f83-129">たとえば、すべてのコマンドレットが定義済みの `Id` パラメーター名を使用してリソースを識別する場合、ユーザーは使用しているコマンドレットに関係なく、パラメーターの意味を簡単に理解できます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-129">For example, if all cmdlets use the predefined `Id` parameter name to identify a resource, user will easily understand the meaning of the parameter, regardless of what cmdlet they are using.</span></span> <span data-ttu-id="e8f83-130">基本的に、パラメーター名は、共通言語ランタイム (CLR) の変数名に使用される規則と同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="e8f83-130">Basically, parameter names follow the same rules as those used for variable names in the common language runtime (CLR).</span></span> <span data-ttu-id="e8f83-131">パラメーターの名前付けの詳細については、「[コマンドレットパラメーター名](/previous-versions/ms714468(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f83-131">For more information about parameter naming, see [Cmdlet Parameter Names](/previous-versions/ms714468(v=vs.85)).</span></span>

- <span data-ttu-id="e8f83-132">Windows PowerShell では、一貫したユーザーエクスペリエンスを提供するために、いくつかのパラメーター名が予約されています。</span><span class="sxs-lookup"><span data-stu-id="e8f83-132">Windows PowerShell reserves a few parameter names to provide a consistent user experience.</span></span> <span data-ttu-id="e8f83-133">これらのパラメーター名は使用しないでください。 `WhatIf`、`Confirm`、`Verbose`、`Debug`、`Warn`、`ErrorAction`、`ErrorVariable`、`OutVariable`、`OutBuffer`です。</span><span class="sxs-lookup"><span data-stu-id="e8f83-133">Do not use these parameter names: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`, and `OutBuffer`.</span></span> <span data-ttu-id="e8f83-134">また、これらのパラメーター名のエイリアスとして、`vb`、`db`、`ea`、`ev`、`ov`、および `ob`が予約されています。</span><span class="sxs-lookup"><span data-stu-id="e8f83-134">Additionally, the following aliases for these parameter names are reserved: `vb`, `db`, `ea`, `ev`, `ov`, and `ob`.</span></span>

- <span data-ttu-id="e8f83-135">`Name` は、コマンドレットで使用するために推奨される単純なパラメーター名です。</span><span class="sxs-lookup"><span data-stu-id="e8f83-135">`Name` is a simple and common parameter name, recommended for use in your cmdlets.</span></span> <span data-ttu-id="e8f83-136">このようなパラメーター名は、特定のコマンドレットに固有であり、覚えにくい複合名として選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e8f83-136">It is better to choose a parameter name like this than a complex name that is unique to a specific cmdlet and hard to remember.</span></span>

- <span data-ttu-id="e8f83-137">Windows PowerShell ではパラメーターの大文字と小文字は区別されませんが、既定では、シェルは大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-137">Parameters are case-insensitive in Windows PowerShell, although by default the shell preserves case.</span></span> <span data-ttu-id="e8f83-138">引数の大文字と小文字の区別は、コマンドレットの操作によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-138">Case-sensitivity of the arguments depends on the operation of the cmdlet.</span></span> <span data-ttu-id="e8f83-139">引数は、コマンドラインで指定されたパラメーターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-139">Arguments are passed to a parameter as specified at the command line.</span></span>

- <span data-ttu-id="e8f83-140">その他のパラメーター宣言の例については、「[コマンドレットパラメーター](./cmdlet-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f83-140">For examples of other parameter declarations, see [Cmdlet Parameters](./cmdlet-parameters.md).</span></span>

## <a name="declaring-parameters-as-positional-or-named"></a><span data-ttu-id="e8f83-141">位置指定または名前付きパラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="e8f83-141">Declaring Parameters as Positional or Named</span></span>

<span data-ttu-id="e8f83-142">コマンドレットでは、各パラメーターを位置指定パラメーターまたは名前付きパラメーターのどちらかとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-142">A cmdlet must set each parameter as either a positional or named parameter.</span></span> <span data-ttu-id="e8f83-143">どちらの種類のパラメーターも、1つの引数、コンマで区切られた複数の引数、およびブール値の設定を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-143">Both kinds of parameters accept single arguments, multiple arguments separated by commas, and Boolean settings.</span></span> <span data-ttu-id="e8f83-144">ブール型パラメーター (*スイッチ*とも呼ばれます) は、ブール値の設定のみを処理します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-144">A Boolean parameter, also called a *switch*, handles only Boolean settings.</span></span> <span data-ttu-id="e8f83-145">スイッチは、パラメーターの存在を確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-145">The switch is used to determine the presence of the parameter.</span></span> <span data-ttu-id="e8f83-146">推奨される既定値は `false`です。</span><span class="sxs-lookup"><span data-stu-id="e8f83-146">The recommended default is `false`.</span></span>

<span data-ttu-id="e8f83-147">Sample `Get-Proc` コマンドレットは、位置指定パラメーターとして `Name` パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-147">The sample `Get-Proc` cmdlet defines the `Name` parameter as a positional parameter with position</span></span>
0. <span data-ttu-id="e8f83-148">これは、ユーザーがコマンドラインに入力した最初の引数が、このパラメーターに自動的に挿入されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-148">This means that the first argument the user enters on the command line is automatically inserted for this parameter.</span></span> <span data-ttu-id="e8f83-149">ユーザーがコマンドラインからパラメーター名を指定する必要のある名前付きパラメーターを定義する場合は、`Position` キーワードを属性宣言の外に残します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-149">If you want to define a named parameter, for which the user must specify the parameter name from the command line, leave the `Position` keyword out of the attribute declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="e8f83-150">パラメーターの名前を指定する必要がない限り、最も使用されているパラメーターを設定して、ユーザーがパラメーター名を入力する必要がないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e8f83-150">Unless parameters must be named, we recommend that you make the most-used parameters positional so that users will not have to type the parameter name.</span></span>

## <a name="declaring-parameters-as-mandatory-or-optional"></a><span data-ttu-id="e8f83-151">必須またはオプションとしてのパラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="e8f83-151">Declaring Parameters as Mandatory or Optional</span></span>

<span data-ttu-id="e8f83-152">コマンドレットでは、各パラメーターを省略可能なパラメーターまたは必須パラメーターのいずれかとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-152">A cmdlet must set each parameter as either an optional or a mandatory parameter.</span></span> <span data-ttu-id="e8f83-153">Sample `Get-Proc` コマンドレットでは、`Mandatory` キーワードが属性宣言で設定されていないため、`Name` パラメーターはオプションとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-153">In the sample `Get-Proc` cmdlet, the `Name` parameter is defined as optional because the `Mandatory` keyword is not set in the attribute declaration.</span></span>

## <a name="supporting-parameter-validation"></a><span data-ttu-id="e8f83-154">パラメーター検証のサポート</span><span class="sxs-lookup"><span data-stu-id="e8f83-154">Supporting Parameter Validation</span></span>

<span data-ttu-id="e8f83-155">Sample `Get-Proc` コマンドレットは、入力の検証属性[である](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute)system.string を `Name` パラメーターに追加して、入力が `null` も空でもないことを検証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e8f83-155">The sample `Get-Proc` cmdlet adds an input validation attribute, [System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), to the `Name` parameter to enable validation that the input is neither `null` nor empty.</span></span> <span data-ttu-id="e8f83-156">この属性は、Windows PowerShell によって提供されるいくつかの検証属性の1つです。</span><span class="sxs-lookup"><span data-stu-id="e8f83-156">This attribute is one of several validation attributes provided by Windows PowerShell.</span></span> <span data-ttu-id="e8f83-157">その他の検証属性の例については、「[パラメーター入力の検証](./validating-parameter-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f83-157">For examples of other validation attributes, see [Validating Parameter Input](./validating-parameter-input.md).</span></span>

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="e8f83-158">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="e8f83-158">Overriding an Input Processing Method</span></span>

<span data-ttu-id="e8f83-159">コマンドレットがコマンドライン入力を処理する場合は、適切な入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-159">If your cmdlet is to handle command-line input, it must override the appropriate input processing methods.</span></span> <span data-ttu-id="e8f83-160">基本的な入力処理方法は、[最初のコマンドレットを作成するとき](./creating-a-cmdlet-without-parameters.md)に導入されます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-160">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="e8f83-161">`Get-Proc` コマンドレットは、ユーザーまたはスクリプトによって指定された `Name` パラメーターの入力を処理するために、 [system.servicemodel メソッドを](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="e8f83-161">The `Get-Proc` cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="e8f83-162">このメソッドは、要求された各プロセス名のプロセスを取得します。名前が指定されていない場合は、すべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-162">This method gets the processes for each requested process name, or all for processes if no name is provided.</span></span> <span data-ttu-id="e8f83-163">[WriteObject% 2csystem.string %29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)の呼び出しは、出力オブジェクトをパイプラインに送信するための出力機構として使用されていることに注意してください。[processrecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)</span><span class="sxs-lookup"><span data-stu-id="e8f83-163">Notice that in [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="e8f83-164">この呼び出しの2番目のパラメーターである `enumerateCollection`は `true` に設定され、プロセスオブジェクトの出力配列を列挙し、一度に1つのプロセスをコマンドラインに書き込むように Windows PowerShell ランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-164">The second parameter of this call, `enumerateCollection`, is set to `true` to inform the Windows PowerShell runtime to enumerate the output array of process objects and write one process at a time to the command line.</span></span>

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
    }
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        Dim processes As Process()
        processes = Process.GetProcesses()
    End If

    '/ If process names are specified, write the processes to the
    '/ pipeline to display them or make them available to the next cmdlet.

    For Each name As String In processNames
        '/ The second parameter of this call tells PowerShell to enumerate the
        '/ array, and send one process at a time to the pipeline.
        WriteObject(Process.GetProcessesByName(name), True)
    Next

End Sub 'ProcessRecord
```

## <a name="code-sample"></a><span data-ttu-id="e8f83-165">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="e8f83-165">Code Sample</span></span>

<span data-ttu-id="e8f83-166">完全なC#サンプルコードについては、「 [GetProcessSample02 sample](./getprocesssample02-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f83-166">For the complete C# sample code, see [GetProcessSample02 Sample](./getprocesssample02-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="e8f83-167">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="e8f83-167">Defining Object Types and Formatting</span></span>

<span data-ttu-id="e8f83-168">Windows PowerShell は、.NET Framework オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-168">Windows PowerShell passes information between cmdlets by using .NET Framework objects.</span></span> <span data-ttu-id="e8f83-169">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-169">Consequently, a cmdlet might need to define its own type, or a cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="e8f83-170">新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions/ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f83-170">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="e8f83-171">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="e8f83-171">Building the Cmdlet</span></span>

<span data-ttu-id="e8f83-172">コマンドレットを実装したら、Windows PowerShell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-172">After you implement a cmdlet, you must register it with Windows PowerShell by using a Windows PowerShell snap-in.</span></span> <span data-ttu-id="e8f83-173">コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f83-173">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="e8f83-174">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="e8f83-174">Testing the Cmdlet</span></span>

<span data-ttu-id="e8f83-175">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-175">When your cmdlet is registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="e8f83-176">サンプルコマンドレットのコードをテストするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="e8f83-176">Here are two ways to test the code for the sample cmdlet.</span></span> <span data-ttu-id="e8f83-177">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f83-177">For more information about using cmdlets from the command line, see [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="e8f83-178">Windows PowerShell プロンプトで、次のコマンドを使用して、"IEXPLORE.EXE" という名前の Internet Explorer のプロセスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-178">At the Windows PowerShell prompt, use the following command to list the Internet Explorer process, which is named "IEXPLORE."</span></span>

  ```powershell
  get-proc -name iexplore
  ```

  <span data-ttu-id="e8f83-179">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-179">The following output appears.</span></span>

  ```Output
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----   ------ --   -----------
      354      11  10036   18992    85   0.67   3284   iexplore
  ```

- <span data-ttu-id="e8f83-180">Internet Explorer、Outlook、および "IEXPLORE.EXE"、"OUTLOOK"、および "NOTEPAD" という名前のプロセスを一覧表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f83-180">To list the Internet Explorer, Outlook, and Notepad processes named "IEXPLORE," "OUTLOOK," and "NOTEPAD," use the following command.</span></span> <span data-ttu-id="e8f83-181">複数のプロセスがある場合は、すべてのプロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-181">If there are multiple processes, all of them are displayed.</span></span>

  ```powershell
  get-proc -name iexplore, outlook, notepad
  ```

  <span data-ttu-id="e8f83-182">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8f83-182">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----  ------   --   -----------
      732      21  24696    5000    138   2.25  2288   iexplore
      715      19  20556   14116    136   1.78  3860   iexplore
     3917      62  74096   58112    468 191.56  1848   OUTLOOK
       39       2   1024    3280     30   0.09  1444   notepad
       39       2   1024     356     30   0.08  3396   notepad
  ```

## <a name="see-also"></a><span data-ttu-id="e8f83-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8f83-183">See Also</span></span>

[<span data-ttu-id="e8f83-184">パイプライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="e8f83-184">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="e8f83-185">最初のコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="e8f83-185">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="e8f83-186">[オブジェクトの種類と書式設定の拡張](/previous-versions/ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e8f83-186">[Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85))</span></span>

<span data-ttu-id="e8f83-187">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e8f83-187">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="e8f83-188">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="e8f83-188">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="e8f83-189">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="e8f83-189">Cmdlet Samples</span></span>](./cmdlet-samples.md)

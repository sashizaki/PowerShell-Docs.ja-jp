---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドライン入力を処理するパラメーターを追加する
description: コマンドライン入力を処理するパラメーターを追加する
ms.openlocfilehash: f20469d366330aa787fbc16e4f0a76e67fc7c6db
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93354611"
---
# <a name="adding-parameters-that-process-command-line-input"></a><span data-ttu-id="80696-103">コマンドライン入力を処理するパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="80696-103">Adding Parameters That Process Command-Line Input</span></span>

<span data-ttu-id="80696-104">コマンドレットの1つの入力ソースは、コマンドラインです。</span><span class="sxs-lookup"><span data-stu-id="80696-104">One source of input for a cmdlet is the command line.</span></span> <span data-ttu-id="80696-105">このトピックでは、コマンドレットに `Get-Proc` 渡された明示的なオブジェクトに基づいてローカルコンピューターからの入力を処理できるように、コマンドレットにパラメーターを追加する方法について説明します ( [最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関するページを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="80696-105">This topic describes how to add a parameter to the `Get-Proc` cmdlet (which is described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process input from the local computer based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="80696-106">`Get-Proc`ここで説明するコマンドレットは、名前に基づいてプロセスを取得し、コマンドプロンプトでプロセスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="80696-106">The `Get-Proc` cmdlet described here retrieves processes based on their names, and then displays information about the processes at a command prompt.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="80696-107">コマンドレットクラスの定義</span><span class="sxs-lookup"><span data-stu-id="80696-107">Defining the Cmdlet Class</span></span>

<span data-ttu-id="80696-108">コマンドレットの作成の最初の手順は、コマンドレットの名前付けと、コマンドレットを実装する .NET Framework クラスの宣言です。</span><span class="sxs-lookup"><span data-stu-id="80696-108">The first step in cmdlet creation is cmdlet naming and the declaration of the .NET Framework class that implements the cmdlet.</span></span> <span data-ttu-id="80696-109">このコマンドレットはプロセス情報を取得するため、ここで選択した動詞名は "Get" です。</span><span class="sxs-lookup"><span data-stu-id="80696-109">This cmdlet retrieves process information, so the verb name chosen here is "Get."</span></span> <span data-ttu-id="80696-110">(情報を取得できるほとんどすべての種類のコマンドレットは、コマンドライン入力を処理できます)。承認されたコマンドレット動詞の詳細については、「 [コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80696-110">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="80696-111">コマンドレットのクラス宣言を次に示し `Get-Proc` ます。</span><span class="sxs-lookup"><span data-stu-id="80696-111">Here's the class declaration for the `Get-Proc` cmdlet.</span></span> <span data-ttu-id="80696-112">この定義の詳細については [、最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)に関する説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="80696-112">Details about this definition are provided in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a><span data-ttu-id="80696-113">パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="80696-113">Declaring Parameters</span></span>

<span data-ttu-id="80696-114">コマンドレットパラメーターを使用すると、ユーザーはコマンドレットに入力を提供できます。</span><span class="sxs-lookup"><span data-stu-id="80696-114">A cmdlet parameter enables the user to provide input to the cmdlet.</span></span> <span data-ttu-id="80696-115">次の例では、 `Get-Proc` と `Get-Member` はパイプラインコマンドレットの名前であり、 `MemberType` はコマンドレットのパラメーターです `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="80696-115">In the following example, `Get-Proc` and `Get-Member` are the names of pipelined cmdlets, and `MemberType` is a parameter for the `Get-Member` cmdlet.</span></span> <span data-ttu-id="80696-116">パラメーターには、"property" という引数があります。</span><span class="sxs-lookup"><span data-stu-id="80696-116">The parameter has the argument "property."</span></span>

<span data-ttu-id="80696-117">**PS> get-proc; `get-member` -membertype プロパティ**</span><span class="sxs-lookup"><span data-stu-id="80696-117">**PS> get-proc ; `get-member` -membertype property**</span></span>

<span data-ttu-id="80696-118">コマンドレットのパラメーターを宣言するには、最初にパラメーターを表すプロパティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80696-118">To declare parameters for a cmdlet, you must first define the properties that represent the parameters.</span></span> <span data-ttu-id="80696-119">`Get-Proc`コマンドレットでは、唯一のパラメーターはです `Name` 。この例では、取得する .NET Framework process オブジェクトの名前を表します。</span><span class="sxs-lookup"><span data-stu-id="80696-119">In the `Get-Proc` cmdlet, the only parameter is `Name`, which in this case represents the name of the .NET Framework process object to retrieve.</span></span> <span data-ttu-id="80696-120">このため、コマンドレットクラスは、名前の配列を受け入れる文字列型のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="80696-120">Therefore, the cmdlet class defines a property of type string to accept an array of names.</span></span>

<span data-ttu-id="80696-121">コマンドレットのパラメーターのパラメーター宣言を次に示し `Name` `Get-Proc` ます。</span><span class="sxs-lookup"><span data-stu-id="80696-121">Here's the parameter declaration for the `Name` parameter of the `Get-Proc` cmdlet.</span></span>

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

<span data-ttu-id="80696-122">このプロパティがパラメーターであることを Windows PowerShell ランタイムに通知するには、 `Name` プロパティ定義に system.string [属性を](/dotnet/api/System.Management.Automation.ParameterAttribute) 追加します。</span><span class="sxs-lookup"><span data-stu-id="80696-122">To inform the Windows PowerShell runtime that this property is the `Name` parameter, a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute is added to the property definition.</span></span> <span data-ttu-id="80696-123">この属性を宣言するための基本構文は `[Parameter()]` です。</span><span class="sxs-lookup"><span data-stu-id="80696-123">The basic syntax for declaring this attribute is `[Parameter()]`.</span></span>

> [!NOTE]
> <span data-ttu-id="80696-124">パラメーターは、明示的にパブリックとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80696-124">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="80696-125">既定でパブリックに設定されていないパラメーターは、Windows PowerShell ランタイムによって検出されません。</span><span class="sxs-lookup"><span data-stu-id="80696-125">Parameters that are not marked as public default to internal and are not found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="80696-126">このコマンドレットは、パラメーターに文字列の配列を使用 `Name` します。</span><span class="sxs-lookup"><span data-stu-id="80696-126">This cmdlet uses an array of strings for the `Name` parameter.</span></span> <span data-ttu-id="80696-127">可能であれば、コマンドレットでパラメーターを配列として定義する必要もあります。これにより、コマンドレットでは複数の項目を受け入れることができるためです。</span><span class="sxs-lookup"><span data-stu-id="80696-127">If possible, your cmdlet should also define a parameter as an array, because this allows the cmdlet to accept more than one item.</span></span>

#### <a name="things-to-remember-about-parameter-definitions"></a><span data-ttu-id="80696-128">パラメーター定義に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="80696-128">Things to Remember About Parameter Definitions</span></span>

- <span data-ttu-id="80696-129">コマンドレットが Windows PowerShell コマンドレットと互換性があることを確認するために、定義済みの Windows PowerShell パラメーター名とデータ型をできるだけ再利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80696-129">Predefined Windows PowerShell parameter names and data types should be reused as much as possible to ensure that your cmdlet is compatible with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="80696-130">たとえば、すべてのコマンドレットが定義済みのパラメーター名を使用し `Id` てリソースを識別する場合、ユーザーは、使用しているコマンドレットに関係なく、パラメーターの意味を簡単に理解できます。</span><span class="sxs-lookup"><span data-stu-id="80696-130">For example, if all cmdlets use the predefined `Id` parameter name to identify a resource, user will easily understand the meaning of the parameter, regardless of what cmdlet they are using.</span></span> <span data-ttu-id="80696-131">基本的に、パラメーター名は、共通言語ランタイム (CLR) の変数名に使用される規則と同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="80696-131">Basically, parameter names follow the same rules as those used for variable names in the common language runtime (CLR).</span></span> <span data-ttu-id="80696-132">パラメーターの名前付けの詳細については、「 [コマンドレットパラメーター名](/previous-versions/ms714468(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80696-132">For more information about parameter naming, see [Cmdlet Parameter Names](/previous-versions/ms714468(v=vs.85)).</span></span>

- <span data-ttu-id="80696-133">Windows PowerShell では、一貫したユーザーエクスペリエンスを提供するために、いくつかのパラメーター名が予約されています。</span><span class="sxs-lookup"><span data-stu-id="80696-133">Windows PowerShell reserves a few parameter names to provide a consistent user experience.</span></span> <span data-ttu-id="80696-134">、、、、、、、、およびの各パラメーター名は使用しないでください `WhatIf` `Confirm` `Verbose` `Debug` `Warn` `ErrorAction` `ErrorVariable` `OutVariable` `OutBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="80696-134">Do not use these parameter names: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`, and `OutBuffer`.</span></span> <span data-ttu-id="80696-135">また、これらのパラメーター名には、、、 `vb` 、、 `db` `ea` `ev` `ov` 、および `ob` の各エイリアスが予約されています。</span><span class="sxs-lookup"><span data-stu-id="80696-135">Additionally, the following aliases for these parameter names are reserved: `vb`, `db`, `ea`, `ev`, `ov`, and `ob`.</span></span>

- <span data-ttu-id="80696-136">`Name` は、コマンドレットで使用するために推奨される単純なパラメーター名です。</span><span class="sxs-lookup"><span data-stu-id="80696-136">`Name` is a simple and common parameter name, recommended for use in your cmdlets.</span></span> <span data-ttu-id="80696-137">このようなパラメーター名は、特定のコマンドレットに固有であり、覚えにくい複合名として選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80696-137">It is better to choose a parameter name like this than a complex name that is unique to a specific cmdlet and hard to remember.</span></span>

- <span data-ttu-id="80696-138">Windows PowerShell ではパラメーターの大文字と小文字は区別されませんが、既定では、シェルは大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="80696-138">Parameters are case-insensitive in Windows PowerShell, although by default the shell preserves case.</span></span> <span data-ttu-id="80696-139">引数の大文字と小文字の区別は、コマンドレットの操作によって異なります。</span><span class="sxs-lookup"><span data-stu-id="80696-139">Case-sensitivity of the arguments depends on the operation of the cmdlet.</span></span> <span data-ttu-id="80696-140">引数は、コマンドラインで指定されたパラメーターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="80696-140">Arguments are passed to a parameter as specified at the command line.</span></span>

- <span data-ttu-id="80696-141">その他のパラメーター宣言の例については、「 [コマンドレットパラメーター](./cmdlet-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80696-141">For examples of other parameter declarations, see [Cmdlet Parameters](./cmdlet-parameters.md).</span></span>

## <a name="declaring-parameters-as-positional-or-named"></a><span data-ttu-id="80696-142">位置指定または名前付きパラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="80696-142">Declaring Parameters as Positional or Named</span></span>

<span data-ttu-id="80696-143">コマンドレットでは、各パラメーターを位置指定パラメーターまたは名前付きパラメーターのどちらかとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80696-143">A cmdlet must set each parameter as either a positional or named parameter.</span></span> <span data-ttu-id="80696-144">どちらの種類のパラメーターも、1つの引数、コンマで区切られた複数の引数、およびブール値の設定を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="80696-144">Both kinds of parameters accept single arguments, multiple arguments separated by commas, and Boolean settings.</span></span> <span data-ttu-id="80696-145">ブール型パラメーター ( *スイッチ* とも呼ばれます) は、ブール値の設定のみを処理します。</span><span class="sxs-lookup"><span data-stu-id="80696-145">A Boolean parameter, also called a *switch*, handles only Boolean settings.</span></span> <span data-ttu-id="80696-146">スイッチは、パラメーターの存在を確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="80696-146">The switch is used to determine the presence of the parameter.</span></span> <span data-ttu-id="80696-147">推奨される既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="80696-147">The recommended default is `false`.</span></span>

<span data-ttu-id="80696-148">このサンプル `Get-Proc` コマンドレットでは、 `Name` position を使用してパラメーターを位置指定パラメーターとして定義します。</span><span class="sxs-lookup"><span data-stu-id="80696-148">The sample `Get-Proc` cmdlet defines the `Name` parameter as a positional parameter with position</span></span>
0. <span data-ttu-id="80696-149">これは、ユーザーがコマンドラインに入力した最初の引数が、このパラメーターに自動的に挿入されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="80696-149">This means that the first argument the user enters on the command line is automatically inserted for this parameter.</span></span> <span data-ttu-id="80696-150">ユーザーがコマンドラインからパラメーター名を指定する必要のある名前付きパラメーターを定義する場合は、 `Position` キーワードを属性宣言の外に残します。</span><span class="sxs-lookup"><span data-stu-id="80696-150">If you want to define a named parameter, for which the user must specify the parameter name from the command line, leave the `Position` keyword out of the attribute declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="80696-151">パラメーターの名前を指定する必要がない限り、最も使用されているパラメーターを設定して、ユーザーがパラメーター名を入力する必要がないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80696-151">Unless parameters must be named, we recommend that you make the most-used parameters positional so that users will not have to type the parameter name.</span></span>

## <a name="declaring-parameters-as-mandatory-or-optional"></a><span data-ttu-id="80696-152">必須またはオプションとしてのパラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="80696-152">Declaring Parameters as Mandatory or Optional</span></span>

<span data-ttu-id="80696-153">コマンドレットでは、各パラメーターを省略可能なパラメーターまたは必須パラメーターのいずれかとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80696-153">A cmdlet must set each parameter as either an optional or a mandatory parameter.</span></span> <span data-ttu-id="80696-154">このサンプルコマンドレットでは、 `Get-Proc` `Name` キーワードが `Mandatory` 属性宣言で設定されていないため、パラメーターはオプションとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="80696-154">In the sample `Get-Proc` cmdlet, the `Name` parameter is defined as optional because the `Mandatory` keyword is not set in the attribute declaration.</span></span>

## <a name="supporting-parameter-validation"></a><span data-ttu-id="80696-155">パラメーター検証のサポート</span><span class="sxs-lookup"><span data-stu-id="80696-155">Supporting Parameter Validation</span></span>

<span data-ttu-id="80696-156">サンプル `Get-Proc` コマンドレット [は、](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute)入力検証属性である system.string をパラメーターに追加して、 `Name` 入力がでも空でもないことを検証できるようにします `null` 。</span><span class="sxs-lookup"><span data-stu-id="80696-156">The sample `Get-Proc` cmdlet adds an input validation attribute, [System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), to the `Name` parameter to enable validation that the input is neither `null` nor empty.</span></span> <span data-ttu-id="80696-157">この属性は、Windows PowerShell によって提供されるいくつかの検証属性の1つです。</span><span class="sxs-lookup"><span data-stu-id="80696-157">This attribute is one of several validation attributes provided by Windows PowerShell.</span></span> <span data-ttu-id="80696-158">その他の検証属性の例については、「 [パラメーター入力の検証](./validating-parameter-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80696-158">For examples of other validation attributes, see [Validating Parameter Input](./validating-parameter-input.md).</span></span>

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="80696-159">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="80696-159">Overriding an Input Processing Method</span></span>

<span data-ttu-id="80696-160">コマンドレットがコマンドライン入力を処理する場合は、適切な入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80696-160">If your cmdlet is to handle command-line input, it must override the appropriate input processing methods.</span></span> <span data-ttu-id="80696-161">基本的な入力処理方法は、 [最初のコマンドレットを作成するとき](./creating-a-cmdlet-without-parameters.md)に導入されます。</span><span class="sxs-lookup"><span data-stu-id="80696-161">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="80696-162">`Get-Proc`コマンドレットは、 [](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) `Name` ユーザーまたはスクリプトによって指定されたパラメーター入力を処理するために、system.object メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="80696-162">The `Get-Proc` cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="80696-163">このメソッドは、要求された各プロセス名のプロセスを取得します。名前が指定されていない場合は、すべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="80696-163">This method gets the processes for each requested process name, or all for processes if no name is provided.</span></span> <span data-ttu-id="80696-164">[WriteObject% 2csystem.string %29](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)の呼び出しは、出力オブジェクトをパイプラインに送信するための出力機構として使用されていることに注意してください。........................ [processrecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="80696-164">Notice that in [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="80696-165">この呼び出しの2番目のパラメーターで `enumerateCollection` あるは、をに設定して、 `true` プロセスオブジェクトの出力配列を列挙し、一度に1つのプロセスをコマンドラインに書き込むように Windows PowerShell ランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="80696-165">The second parameter of this call, `enumerateCollection`, is set to `true` to inform the Windows PowerShell runtime to enumerate the output array of process objects and write one process at a time to the command line.</span></span>

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

## <a name="code-sample"></a><span data-ttu-id="80696-166">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="80696-166">Code Sample</span></span>

<span data-ttu-id="80696-167">完全な C# サンプルコードについては、「 [GetProcessSample02 sample](./getprocesssample02-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80696-167">For the complete C# sample code, see [GetProcessSample02 Sample](./getprocesssample02-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="80696-168">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="80696-168">Defining Object Types and Formatting</span></span>

<span data-ttu-id="80696-169">Windows PowerShell は、.NET Framework オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="80696-169">Windows PowerShell passes information between cmdlets by using .NET Framework objects.</span></span> <span data-ttu-id="80696-170">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="80696-170">Consequently, a cmdlet might need to define its own type, or a cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="80696-171">新しい型を定義する、または既存の型を拡張する方法の詳細については、「 [オブジェクトの型と書式設定の拡張](/previous-versions/ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80696-171">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="80696-172">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="80696-172">Building the Cmdlet</span></span>

<span data-ttu-id="80696-173">コマンドレットを実装したら、Windows PowerShell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80696-173">After you implement a cmdlet, you must register it with Windows PowerShell by using a Windows PowerShell snap-in.</span></span> <span data-ttu-id="80696-174">コマンドレットの登録の詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80696-174">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="80696-175">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="80696-175">Testing the Cmdlet</span></span>

<span data-ttu-id="80696-176">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="80696-176">When your cmdlet is registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="80696-177">サンプルコマンドレットのコードをテストするには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="80696-177">Here are two ways to test the code for the sample cmdlet.</span></span> <span data-ttu-id="80696-178">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80696-178">For more information about using cmdlets from the command line, see [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="80696-179">Windows PowerShell プロンプトで、次のコマンドを使用して、"IEXPLORE.EXE" という名前の Internet Explorer のプロセスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="80696-179">At the Windows PowerShell prompt, use the following command to list the Internet Explorer process, which is named "IEXPLORE."</span></span>

  ```powershell
  get-proc -name iexplore
  ```

  <span data-ttu-id="80696-180">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80696-180">The following output appears.</span></span>

  ```Output
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----   ------ --   -----------
      354      11  10036   18992    85   0.67   3284   iexplore
  ```

- <span data-ttu-id="80696-181">Internet Explorer、Outlook、および "IEXPLORE.EXE"、"OUTLOOK"、および "NOTEPAD" という名前のプロセスを一覧表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="80696-181">To list the Internet Explorer, Outlook, and Notepad processes named "IEXPLORE," "OUTLOOK," and "NOTEPAD," use the following command.</span></span> <span data-ttu-id="80696-182">複数のプロセスがある場合は、すべてのプロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80696-182">If there are multiple processes, all of them are displayed.</span></span>

  ```powershell
  get-proc -name iexplore, outlook, notepad
  ```

  <span data-ttu-id="80696-183">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80696-183">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----  ------   --   -----------
      732      21  24696    5000    138   2.25  2288   iexplore
      715      19  20556   14116    136   1.78  3860   iexplore
     3917      62  74096   58112    468 191.56  1848   OUTLOOK
       39       2   1024    3280     30   0.09  1444   notepad
       39       2   1024     356     30   0.08  3396   notepad
  ```

## <a name="see-also"></a><span data-ttu-id="80696-184">参照</span><span class="sxs-lookup"><span data-stu-id="80696-184">See Also</span></span>

[<span data-ttu-id="80696-185">パイプライン入力を処理するパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="80696-185">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="80696-186">最初のコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="80696-186">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="80696-187">[オブジェクトの種類と書式設定の拡張](/previous-versions/ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="80696-187">[Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85))</span></span>

<span data-ttu-id="80696-188">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="80696-188">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="80696-189">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="80696-189">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="80696-190">コマンドレット サンプル</span><span class="sxs-lookup"><span data-stu-id="80696-190">Cmdlet Samples</span></span>](./cmdlet-samples.md)

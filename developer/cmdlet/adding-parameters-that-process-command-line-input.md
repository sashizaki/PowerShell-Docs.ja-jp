---
title: コマンドライン入力を処理するパラメーターの追加 |Microsoft Docs
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
ms.openlocfilehash: c9ad84c5bcb6826fcf51db9a1f1a578a65a1f275
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854945"
---
# <a name="adding-parameters-that-process-command-line-input"></a><span data-ttu-id="5d9fe-102">コマンドライン入力を処理するパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="5d9fe-102">Adding Parameters That Process Command-Line Input</span></span>

<span data-ttu-id="5d9fe-103">コマンドレットの入力の 1 つのソースは、コマンド ラインです。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-103">One source of input for a cmdlet is the command line.</span></span> <span data-ttu-id="5d9fe-104">このトピックでは、パラメーターを追加する方法を説明します、 **Get-proc**コマンドレット (に記載されている[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)) コマンドレットは、明示的に基づき、ローカル コンピューターからの入力を処理できるようにオブジェクトは、コマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-104">This topic describes how to add a parameter to the **Get-Proc** cmdlet (which is described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process input from the local computer based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="5d9fe-105">**Get-proc**説明されているコマンドレットは、ここで、その名前に基づいてプロセスを取得し、コマンド プロンプトで、プロセスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-105">The **Get-Proc** cmdlet described here retrieves processes based on their names, and then displays information about the processes at a command prompt.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="5d9fe-106">コマンドレット クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-106">Defining the Cmdlet Class</span></span>

<span data-ttu-id="5d9fe-107">コマンドレットの作成の最初の手順では、コマンドレットの名前付けと、コマンドレットを実装する .NET Framework クラスの宣言です。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-107">The first step in cmdlet creation is cmdlet naming and the declaration of the .NET Framework class that implements the cmdlet.</span></span> <span data-ttu-id="5d9fe-108">このコマンドレットは、ため、ここで選択した動詞名が"Get"にプロセスの情報を取得します</span><span class="sxs-lookup"><span data-stu-id="5d9fe-108">This cmdlet retrieves process information, so the verb name chosen here is "Get."</span></span> <span data-ttu-id="5d9fe-109">(ほぼあらゆる種類の情報を取得するのに対応しているコマンドレットは、コマンドラインの入力を処理できます)承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-109">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="5d9fe-110">クラス宣言を次に示します、 **Get-proc**コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-110">Here's the class declaration for the **Get-Proc** cmdlet.</span></span> <span data-ttu-id="5d9fe-111">この定義に関する詳細情報が記載[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-111">Details about this definition are provided in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a><span data-ttu-id="5d9fe-112">パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="5d9fe-112">Declaring Parameters</span></span>

<span data-ttu-id="5d9fe-113">コマンドレット パラメーターには、コマンドレットへの入力を提供するユーザーが可能になります。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-113">A cmdlet parameter enables the user to provide input to the cmdlet.</span></span> <span data-ttu-id="5d9fe-114">次の例では、 **Get-proc**と`Get-Member`パイプラインのコマンドレットの名前と`MemberType`パラメーターです、`Get-Member`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-114">In the following example, **Get-Proc** and `Get-Member` are the names of pipelined cmdlets, and `MemberType` is a parameter for the `Get-Member` cmdlet.</span></span> <span data-ttu-id="5d9fe-115">パラメーターが、引数「プロパティです」</span><span class="sxs-lookup"><span data-stu-id="5d9fe-115">The parameter has the argument "property."</span></span>

<span data-ttu-id="5d9fe-116">**PS > get proc です。`get-member` -membertype プロパティ**</span><span class="sxs-lookup"><span data-stu-id="5d9fe-116">**PS> get-proc ; `get-member` -membertype property**</span></span>

<span data-ttu-id="5d9fe-117">コマンドレットのパラメーターを宣言するには、最初にパラメーターを表すプロパティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-117">To declare parameters for a cmdlet, you must first define the properties that represent the parameters.</span></span> <span data-ttu-id="5d9fe-118">**Get-proc**コマンドレット、唯一のパラメーターは`Name`をここで取得する .NET Framework のプロセス オブジェクトの名前を表します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-118">In the **Get-Proc** cmdlet, the only parameter is `Name`, which in this case represents the name of the .NET Framework process object to retrieve.</span></span> <span data-ttu-id="5d9fe-119">そのため、コマンドレット クラスでは、名前の配列を受け入れるように文字列型のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-119">Therefore, the cmdlet class defines a property of type string to accept an array of names.</span></span>

<span data-ttu-id="5d9fe-120">パラメーター宣言を次に示します、`Name`のパラメーター、 **Get-proc**コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-120">Here's the parameter declaration for the `Name` parameter of the **Get-Proc** cmdlet.</span></span>

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

<span data-ttu-id="5d9fe-121">このプロパティである Windows PowerShell ランタイムを通知するために、`Name`パラメーター、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性は、プロパティ定義に追加します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-121">To inform the Windows PowerShell runtime that this property is the `Name` parameter, a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute is added to the property definition.</span></span> <span data-ttu-id="5d9fe-122">この属性を宣言するための基本構文は`[Parameter()]`します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-122">The basic syntax for declaring this attribute is `[Parameter()]`.</span></span>

> [!NOTE]
> <span data-ttu-id="5d9fe-123">パラメーターをする必要があります明示的にパブリックと指定します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-123">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="5d9fe-124">内部にパブリックの既定としてマークされていないと、Windows PowerShell ランタイムでは検出できないパラメーター。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-124">Parameters that are not marked as public default to internal and are not found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="5d9fe-125">このコマンドレットは、文字列の配列を使用して、`Name`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-125">This cmdlet uses an array of strings for the `Name` parameter.</span></span> <span data-ttu-id="5d9fe-126">可能であれば、コマンドレットする必要がありますもパラメーターを定義、配列としてため、これにより、1 つ以上の項目をそのまま使用するコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-126">If possible, your cmdlet should also define a parameter as an array, because this allows the cmdlet to accept more than one item.</span></span>

#### <a name="things-to-remember-about-parameter-definitions"></a><span data-ttu-id="5d9fe-127">パラメーターの定義に関する注意点</span><span class="sxs-lookup"><span data-stu-id="5d9fe-127">Things to Remember About Parameter Definitions</span></span>

- <span data-ttu-id="5d9fe-128">定義済み Windows PowerShell パラメーター名とデータ型は、コマンドレットが Windows PowerShell コマンドレットと互換性があることを確認することを可能な限り再利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-128">Predefined Windows PowerShell parameter names and data types should be reused as much as possible to ensure that your cmdlet is compatible with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5d9fe-129">たとえば、すべてのコマンドレットを使用して、定義済み`Id`ユーザーは、リソースを簡単に識別するためにパラメーター名は、どのようなコマンドレットを使用しているに関係なく、パラメーターの意味を理解します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-129">For example, if all cmdlets use the predefined `Id` parameter name to identify a resource, user will easily understand the meaning of the parameter, regardless of what cmdlet they are using.</span></span> <span data-ttu-id="5d9fe-130">基本的に、パラメーター名には、共通言語ランタイム (CLR) 内の変数名に使用されるものと同じ規則に従ってください。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-130">Basically, parameter names follow the same rules as those used for variable names in the common language runtime (CLR).</span></span> <span data-ttu-id="5d9fe-131">パラメーターの名前付けの詳細については、次を参照してください。[コマンドレットのパラメーター名](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb)します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-131">For more information about parameter naming, see [Cmdlet Parameter Names](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb).</span></span>

- <span data-ttu-id="5d9fe-132">Windows PowerShell では、一貫性のあるユーザー エクスペリエンスを提供するいくつかのパラメーター名を予約します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-132">Windows PowerShell reserves a few parameter names to provide a consistent user experience.</span></span> <span data-ttu-id="5d9fe-133">これらのパラメーター名を使用しない: `WhatIf`、 `Confirm`、 `Verbose`、 `Debug`、 `Warn`、 `ErrorAction`、 `ErrorVariable`、 `OutVariable`、および`OutBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-133">Do not use these parameter names: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`, and `OutBuffer`.</span></span> <span data-ttu-id="5d9fe-134">さらに、これらのパラメーター名の次のエイリアスは予約されています: `vb`、 `db`、 `ea`、 `ev`、 `ov`、および`ob`します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-134">Additionally, the following aliases for these parameter names are reserved: `vb`, `db`, `ea`, `ev`, `ov`, and `ob`.</span></span>

- <span data-ttu-id="5d9fe-135">`Name` コマンドレットで使用するための推奨、単純で一般的なパラメーターの名前です。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-135">`Name` is a simple and common parameter name, recommended for use in your cmdlets.</span></span> <span data-ttu-id="5d9fe-136">次のようにより、特定のコマンドレットに一意で覚えにくい複雑な名前のパラメーター名を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-136">It is better to choose a parameter name like this than a complex name that is unique to a specific cmdlet and hard to remember.</span></span>

- <span data-ttu-id="5d9fe-137">パラメーターは、シェルが大文字小文字を保持する既定では、Windows PowerShell では大文字です。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-137">Parameters are case-insensitive in Windows PowerShell, although by default the shell preserves case.</span></span> <span data-ttu-id="5d9fe-138">引数の大文字小文字の区別は、コマンドレットの操作に依存します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-138">Case-sensitivity of the arguments depends on the operation of the cmdlet.</span></span> <span data-ttu-id="5d9fe-139">引数は、コマンドラインで指定されたパラメーターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-139">Arguments are passed to a parameter as specified at the command line.</span></span>

- <span data-ttu-id="5d9fe-140">その他のパラメーター宣言の例については、次を参照してください。[コマンドレット パラメーター](./cmdlet-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-140">For examples of other parameter declarations, see [Cmdlet Parameters](./cmdlet-parameters.md).</span></span>

## <a name="declaring-parameters-as-positional-or-named"></a><span data-ttu-id="5d9fe-141">位置指定または名前付きパラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="5d9fe-141">Declaring Parameters as Positional or Named</span></span>

<span data-ttu-id="5d9fe-142">コマンドレットをする必要があります各パラメーターとして設定か位置指定か名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-142">A cmdlet must set each parameter as either a positional or named parameter.</span></span> <span data-ttu-id="5d9fe-143">パラメーターの両方の種類は、1 つの引数、コンマ、およびブール値の設定で区切られた複数の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-143">Both kinds of parameters accept single arguments, multiple arguments separated by commas, and Boolean settings.</span></span> <span data-ttu-id="5d9fe-144">呼ばれる、ブール型パラメーター、*切り替える*、ブール型設定のみを処理します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-144">A Boolean parameter, also called a *switch*, handles only Boolean settings.</span></span> <span data-ttu-id="5d9fe-145">パラメーターの存在を検出するスイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-145">The switch is used to determine the presence of the parameter.</span></span> <span data-ttu-id="5d9fe-146">推奨される既定値は`false`します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-146">The recommended default is `false`.</span></span>

<span data-ttu-id="5d9fe-147">サンプル**Get-proc**コマンドレットを定義、`Name`位置 0 の位置指定パラメーターとしてパラメーター。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-147">The sample **Get-Proc** cmdlet defines the `Name` parameter as a positional parameter with position 0.</span></span> <span data-ttu-id="5d9fe-148">これは、コマンドラインで、ユーザーが入力した最初の引数がこのパラメーターに自動的に挿入されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-148">This means that the first argument the user enters on the command line is automatically inserted for this parameter.</span></span> <span data-ttu-id="5d9fe-149">名前付きパラメーターを定義する場合は、ユーザーが指定する必要があります、コマンドラインからパラメーター名のままに、`Position`属性の宣言からキーワード。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-149">If you want to define a named parameter, for which the user must specify the parameter name from the command line, leave the `Position` keyword out of the attribute declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="5d9fe-150">パラメーターを指定する必要があります、されない限り、ユーザーは、パラメーター名を入力する必要があるないように、最も使用頻度のパラメーターを位置指定して行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-150">Unless parameters must be named, we recommend that you make the most-used parameters positional so that users will not have to type the parameter name.</span></span>

## <a name="declaring-parameters-as-mandatory-or-optional"></a><span data-ttu-id="5d9fe-151">必須または省略可能パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-151">Declaring Parameters as Mandatory or Optional</span></span>

<span data-ttu-id="5d9fe-152">コマンドレットは、省略可能または必須のパラメーターとして各パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-152">A cmdlet must set each parameter as either an optional or a mandatory parameter.</span></span> <span data-ttu-id="5d9fe-153">サンプルの**Get-proc**コマンドレット、`Name`ために、オプションとしてパラメーターが定義されている、`Mandatory`属性宣言でキーワードが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-153">In the sample **Get-Proc** cmdlet, the `Name` parameter is defined as optional because the `Mandatory` keyword is not set in the attribute declaration.</span></span>

## <a name="supporting-parameter-validation"></a><span data-ttu-id="5d9fe-154">パラメーターの検証のサポート</span><span class="sxs-lookup"><span data-stu-id="5d9fe-154">Supporting Parameter Validation</span></span>

<span data-ttu-id="5d9fe-155">サンプル**Get-proc**コマンドレットは、入力の検証属性を追加します[System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute)を、`Name`検証を有効にするパラメーターを、。入力がどちらも`null`も空でも。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-155">The sample **Get-Proc** cmdlet adds an input validation attribute, [System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), to the `Name` parameter to enable validation that the input is neither `null` nor empty.</span></span> <span data-ttu-id="5d9fe-156">この属性では、Windows PowerShell によって提供されるいくつかの検証属性の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-156">This attribute is one of several validation attributes provided by Windows PowerShell.</span></span> <span data-ttu-id="5d9fe-157">その他の検証属性の例については、次を参照してください。[パラメーター入力の検証](./validating-parameter-input.md)です。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-157">For examples of other validation attributes, see [Validating Parameter Input](./validating-parameter-input.md).</span></span>

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="5d9fe-158">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-158">Overriding an Input Processing Method</span></span>

<span data-ttu-id="5d9fe-159">コマンドレットは、コマンドライン入力を処理するためには、適切な入力処理メソッドをオーバーライドにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-159">If your cmdlet is to handle command-line input, it must override the appropriate input processing methods.</span></span> <span data-ttu-id="5d9fe-160">基本的な入力処理メソッドがで導入された[最初のコマンドレットを作成](./creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-160">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="5d9fe-161">**Get-proc**コマンドレットよりも優先、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)を処理するメソッド、`Name`ユーザーまたはスクリプトによって提供されるパラメーターの入力。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-161">The **Get-Proc** cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="5d9fe-162">このメソッドは、名前が指定されていない場合、各要求プロセス名またはプロセスのすべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-162">This method gets the processes for each requested process name, or all for processes if no name is provided.</span></span> <span data-ttu-id="5d9fe-163">ある[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)への呼び出し[System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)出力出力を送信するためのメカニズムは、パイプラインにオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-163">Notice that in [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="5d9fe-164">この呼び出しの 2 番目のパラメーター`enumerateCollection`に設定されている`true`プロセス オブジェクトの出力配列を列挙し、コマンドラインに、一度に 1 つのプロセスを記述する Windows PowerShell ランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-164">The second parameter of this call, `enumerateCollection`, is set to `true` to inform the Windows PowerShell runtime to enumerate the output array of process objects and write one process at a time to the command line.</span></span>

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

## <a name="code-sample"></a><span data-ttu-id="5d9fe-165">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="5d9fe-165">Code Sample</span></span>

<span data-ttu-id="5d9fe-166">完全なC#サンプル コードは、「 [GetProcessSample02 サンプル](./getprocesssample02-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-166">For the complete C# sample code, see [GetProcessSample02 Sample](./getprocesssample02-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="5d9fe-167">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="5d9fe-167">Defining Object Types and Formatting</span></span>

<span data-ttu-id="5d9fe-168">Windows PowerShell は、.NET Framework オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-168">Windows PowerShell passes information between cmdlets by using .NET Framework objects.</span></span> <span data-ttu-id="5d9fe-169">そのため、コマンドレットは、独自の型を定義する必要があります。 またはコマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-169">Consequently, a cmdlet might need to define its own type, or a cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="5d9fe-170">新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-170">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="5d9fe-171">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="5d9fe-171">Building the Cmdlet</span></span>

<span data-ttu-id="5d9fe-172">コマンドレットを実装した後は、Windows PowerShell スナップインを使用して Windows PowerShell を使用した登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-172">After you implement a cmdlet, you must register it with Windows PowerShell by using a Windows PowerShell snap-in.</span></span> <span data-ttu-id="5d9fe-173">コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-173">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="5d9fe-174">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5d9fe-174">Testing the Cmdlet</span></span>

<span data-ttu-id="5d9fe-175">コマンドレットが Windows PowerShell に登録されたときに、コマンドラインで実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-175">When your cmdlet is registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="5d9fe-176">サンプル コマンドレットのコードをテストする 2 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-176">Here are two ways to test the code for the sample cmdlet.</span></span> <span data-ttu-id="5d9fe-177">詳細については、コマンドラインからコマンドレットを使用して、次を参照してください。 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-177">For more information about using cmdlets from the command line, see [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="5d9fe-178">Windows PowerShell プロンプトで次のコマンドを使用、Internet Explorer プロセスは、"IEXPLORE"という名前の一覧を表示するには</span><span class="sxs-lookup"><span data-stu-id="5d9fe-178">At the Windows PowerShell prompt, use the following command to list the Internet Explorer process, which is named "IEXPLORE."</span></span>

    ```powershell
    PS> get-proc -name iexplore
    ```

<span data-ttu-id="5d9fe-179">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-179">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----   ------ --   -----------
        354      11  10036   18992    85   0.67   3284   iexplore
    ```

- <span data-ttu-id="5d9fe-180">Internet Explorer、Outlook、およびメモ帳のプロセスの"と、IEXPLORE"という名前を一覧表示するには、"OUTLOOK"と「メモ帳」は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-180">To list the Internet Explorer, Outlook, and Notepad processes named "IEXPLORE," "OUTLOOK," and "NOTEPAD," use the following command.</span></span> <span data-ttu-id="5d9fe-181">複数のプロセスがある場合は、それらのすべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-181">If there are multiple processes, all of them are displayed.</span></span>

    ```powershell
    PS> get-proc -name iexplore, outlook, notepad
    ```

<span data-ttu-id="5d9fe-182">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-182">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----  ------   --    -----------
        732      21  24696    5000    138   2.25  2288   iexplore
        715      19  20556   14116    136   1.78  3860   iexplore
       3917      62  74096   58112    468 191.56  1848   OUTLOOK
         39       2   1024    3280     30   0.09  1444   notepad
         39       2   1024     356     30   0.08  3396   notepad
    ```

## <a name="see-also"></a><span data-ttu-id="5d9fe-183">参照</span><span class="sxs-lookup"><span data-stu-id="5d9fe-183">See Also</span></span>

[<span data-ttu-id="5d9fe-184">プロセス パイプラインの入力パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-184">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="5d9fe-185">初めてのコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d9fe-185">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="5d9fe-186">オブジェクトの種類を拡張して、書式設定</span><span class="sxs-lookup"><span data-stu-id="5d9fe-186">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="5d9fe-187">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="5d9fe-187">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="5d9fe-188">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="5d9fe-188">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="5d9fe-189">コマンドレットのサンプル</span><span class="sxs-lookup"><span data-stu-id="5d9fe-189">Cmdlet Samples</span></span>](./cmdlet-samples.md)

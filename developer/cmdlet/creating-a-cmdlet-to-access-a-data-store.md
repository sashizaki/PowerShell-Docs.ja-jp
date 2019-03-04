---
title: データ ストアへのアクセスのコマンドレットを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea15e00e-20dc-4209-9e97-9ffd763e5d97
caps.latest.revision: 8
ms.openlocfilehash: 6171f96d66d0b2aa0fd9cb2a939768287c4bcb87
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859388"
---
# <a name="creating-a-cmdlet-to-access-a-data-store"></a><span data-ttu-id="390dd-102">データ ストアにアクセスするためのコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="390dd-102">Creating a Cmdlet to Access a Data Store</span></span>

<span data-ttu-id="390dd-103">このセクションでは、Windows PowerShell プロバイダーを介した保存されているデータにアクセスするためのコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="390dd-103">This section describes how to create a cmdlet that accesses stored data by way of a Windows PowerShell provider.</span></span> <span data-ttu-id="390dd-104">このコマンドレットの種類は、Windows PowerShell ランタイムの Windows PowerShell プロバイダーのインフラストラクチャを使用して、そのため、コマンドレット クラスはから派生する必要があります、 [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="390dd-104">This type of cmdlet uses the Windows PowerShell provider infrastructure of the Windows PowerShell runtime and, therefore, the cmdlet class must derive from the [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span>

<span data-ttu-id="390dd-105">ここで説明されている選択 Str コマンドレットは、検索し、ファイルまたはオブジェクトの文字列を選択できます。</span><span class="sxs-lookup"><span data-stu-id="390dd-105">The Select-Str cmdlet described here can locate and select strings in a file or object.</span></span> <span data-ttu-id="390dd-106">文字列を識別するために使用されるパターンをを通じて明示的に指定することができます、`Path`または暗黙的にコマンドレットのパラメーター、`Script`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="390dd-106">The patterns used to identify the string can be specified explicitly through the `Path` parameter of the cmdlet or implicitly through the `Script` parameter.</span></span>

<span data-ttu-id="390dd-107">コマンドレットがから派生した任意の Windows PowerShell プロバイダーを使用するように設計[System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-107">The cmdlet is designed to use any Windows PowerShell provider that derives from [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider).</span></span> <span data-ttu-id="390dd-108">たとえば、コマンドレットでは、FileSystem プロバイダーまたは Variable プロバイダーは Windows PowerShell によって提供されるを指定できます。</span><span class="sxs-lookup"><span data-stu-id="390dd-108">For example, the cmdlet can specify the FileSystem provider or the Variable provider that is provided by Windows PowerShell.</span></span> <span data-ttu-id="390dd-109">詳細については aboutWindows PowerShell プロバイダーを参照してください。 [Windows PowerShell の設計プロバイダー](../prog-guide/designing-your-windows-powershell-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-109">For more information aboutWindows PowerShell providers, see [Designing Your Windows PowerShell provider](../prog-guide/designing-your-windows-powershell-provider.md).</span></span>

<span data-ttu-id="390dd-110">このセクションのトピックで、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="390dd-110">Topics in this section include the following:</span></span>

- [<span data-ttu-id="390dd-111">コマンドレット クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="390dd-111">Defining the Cmdlet Class</span></span>](#Defining-the-Cmdlet-Class)

- [<span data-ttu-id="390dd-112">データ アクセスのためのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="390dd-112">Defining Parameters for Data Access</span></span>](#Declaring-the-Path-Parameter)

- [<span data-ttu-id="390dd-113">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="390dd-113">Overriding Input Processing Methods</span></span>](#Overriding-Input-Processing-Methods)

- [<span data-ttu-id="390dd-114">コンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="390dd-114">Accessing Content</span></span>](#Accessing-Content)

- [<span data-ttu-id="390dd-115">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="390dd-115">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="390dd-116">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="390dd-116">Defining Object Types and Formatting</span></span>](#Declaring-Search-Support-Parameters)

- [<span data-ttu-id="390dd-117">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="390dd-117">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="390dd-118">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="390dd-118">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="390dd-119">コマンドレット クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="390dd-119">Defining the Cmdlet Class</span></span>

<span data-ttu-id="390dd-120">コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="390dd-120">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="390dd-121">このコマンドレットは、特定の文字列では、ここで選択した動詞名は"Select"で定義が検出した、 [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon)クラス。</span><span class="sxs-lookup"><span data-stu-id="390dd-121">This cmdlet detects certain strings, so the verb name chosen here is "Select", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) class.</span></span> <span data-ttu-id="390dd-122">"Str"名詞形式の名前は、コマンドレットは、文字列には動作するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="390dd-122">The noun name "Str" is used because the cmdlet acts upon strings.</span></span> <span data-ttu-id="390dd-123">次の宣言では、コマンドレット クラスの名前、コマンドレットの動詞と名詞の名前が反映されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="390dd-123">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span> <span data-ttu-id="390dd-124">承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-124">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="390dd-125">このコマンドレットの .NET クラスがから派生する必要があります、 [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) Windows PowerShell プロバイダーを公開する、Windows PowerShell ランタイムに必要なサポートを提供するための基本クラスインフラストラクチャ。</span><span class="sxs-lookup"><span data-stu-id="390dd-125">The .NET class for this cmdlet must derive from the [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class, because it provides the support needed by the Windows PowerShell runtime to expose the Windows PowerShell provider infrastructure.</span></span> <span data-ttu-id="390dd-126">このコマンドレットはまた、メモなどの .NET Framework の正規表現クラスの使用[System.Text.Regularexpressions.Regex](/dotnet/api/System.Text.RegularExpressions.Regex)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-126">Note that this cmdlet also makes use of the .NET Framework regular expressions classes, such as [System.Text.Regularexpressions.Regex](/dotnet/api/System.Text.RegularExpressions.Regex).</span></span>

<span data-ttu-id="390dd-127">次のコードは、この選択 Str コマンドレットのクラス定義です。</span><span class="sxs-lookup"><span data-stu-id="390dd-127">The following code is the class definition for this Select-Str cmdlet.</span></span>

```csharp
[Cmdlet(VerbsCommon.Select, "Str", DefaultParameterSetName="PatternParameterSet")]
public class SelectStringCommand : PSCmdlet
```

<span data-ttu-id="390dd-128">このコマンドレットは、既定のパラメーターを追加することで設定を定義、`DefaultParameterSetName`キーワードをクラス宣言に属性します。</span><span class="sxs-lookup"><span data-stu-id="390dd-128">This cmdlet defines a default parameter set by adding the `DefaultParameterSetName` attribute keyword to the class declaration.</span></span> <span data-ttu-id="390dd-129">既定のパラメーター セット`PatternParameterSet`ときに使用される、`Script`パラメーターが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="390dd-129">The default parameter set `PatternParameterSet` is used when the `Script` parameter is not specified.</span></span> <span data-ttu-id="390dd-130">このパラメーターのセットについての詳細については、次を参照してください。、`Pattern`と`Script`パラメーターについては、次のセクション。</span><span class="sxs-lookup"><span data-stu-id="390dd-130">For more information about this parameter set, see the `Pattern` and `Script` parameter discussion in the following section.</span></span>

## <a name="defining-parameters-for-data-access"></a><span data-ttu-id="390dd-131">データ アクセスのためのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="390dd-131">Defining Parameters for Data Access</span></span>

<span data-ttu-id="390dd-132">このコマンドレットは、ユーザーがアクセスして格納されたデータを確認できるようにいくつかのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="390dd-132">This cmdlet defines several parameters that allow the user to access and examine stored data.</span></span> <span data-ttu-id="390dd-133">これらのパラメーターを含める、`Path`パラメーター、データ ストアの場所を示す、`Pattern`検索に使用するパターンを指定するパラメーターと、検索を実行する方法をサポートするその他のいくつかのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="390dd-133">These parameters include a `Path` parameter that indicates the location of the data store, a `Pattern` parameter that specifies the pattern to be used in the search, and several other parameters that support how the search is performed.</span></span>

> [!NOTE]
> <span data-ttu-id="390dd-134">パラメーターの定義の基本についての詳細については、次を参照してください。[そのプロセスのコマンドラインの入力パラメーターを追加する](./adding-parameters-that-process-command-line-input.md)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-134">For more information about the basics of defining parameters, see [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

### <a name="declaring-the-path-parameter"></a><span data-ttu-id="390dd-135">パス パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="390dd-135">Declaring the Path Parameter</span></span>

<span data-ttu-id="390dd-136">データ ストアを検索するには、このコマンドレットは、データ ストアにアクセスするのにように設計された Windows PowerShell プロバイダーを識別するために、Windows PowerShell パスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="390dd-136">To locate the data store, this cmdlet must use a Windows PowerShell path to identify the Windows PowerShell provider that is designed to access the data store.</span></span> <span data-ttu-id="390dd-137">そのため、定義、`Path`プロバイダーの場所を示す文字列配列の型のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="390dd-137">Therefore, it defines a `Path` parameter of type string array to indicate the location of the provider.</span></span>

```csharp
[Parameter(
           Position = 0,
           ParameterSetName = "ScriptParameterSet",
           Mandatory = true)]
[Parameter(
           Position = 0,
           ParameterSetName = "PatternParameterSet",
           ValueFromPipeline = true,
           Mandatory = true)]
           [Alias("PSPath")]
public string[] Path
{
  get { return paths; }
  set { paths = value; }
}
private string[] paths;
```

<span data-ttu-id="390dd-138">このパラメーターが 2 つの異なるパラメーター セットに属していることと、エイリアスがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="390dd-138">Note that this parameter belongs to two different parameter sets and that it has an alias.</span></span>

<span data-ttu-id="390dd-139">2 つ[System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性を宣言する、`Path`パラメーターが属する、 `ScriptParameterSet` 、`PatternParameterSet`します。</span><span class="sxs-lookup"><span data-stu-id="390dd-139">Two [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attributes declare that the `Path` parameter belongs to the `ScriptParameterSet` and the `PatternParameterSet`.</span></span> <span data-ttu-id="390dd-140">パラメーター セットの詳細については、次を参照してください。[パラメーター セットをコマンドレットに追加](./adding-parameter-sets-to-a-cmdlet.md)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-140">For more information about parameter sets, see [Adding Parameter Sets to a Cmdlet](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

<span data-ttu-id="390dd-141">[System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute)属性宣言を`PSPath`のエイリアス、`Path`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="390dd-141">The [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute declares a `PSPath` alias for the `Path` parameter.</span></span> <span data-ttu-id="390dd-142">このエイリアスを宣言することは、Windows PowerShell プロバイダーにアクセスする他のコマンドレットとの整合性強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="390dd-142">Declaring this alias is strongly recommended for consistency with other cmdlets that access Windows PowerShell providers.</span></span> <span data-ttu-id="390dd-143">詳細については aboutWindows PowerShell パスの「PowerShell パスの概念」を参照してください[Windows PowerShell のしくみ](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-143">For more information aboutWindows PowerShell paths, see "PowerShell Path Concepts" in [How Windows PowerShell Works](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).</span></span>

### <a name="declaring-the-pattern-parameter"></a><span data-ttu-id="390dd-144">パターン パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="390dd-144">Declaring the Pattern Parameter</span></span>

<span data-ttu-id="390dd-145">このコマンドレットの宣言を検索するパターンを指定する、`Pattern`パラメーターが文字列の配列。</span><span class="sxs-lookup"><span data-stu-id="390dd-145">To specify the patterns to search for, this cmdlet declares a `Pattern` parameter that is an array of strings.</span></span> <span data-ttu-id="390dd-146">データ ストア内のパターンのいずれかにある陽性の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="390dd-146">A positive result is returned when any of the patterns are found in the data store.</span></span> <span data-ttu-id="390dd-147">コンパイルされた正規表現の配列または配列リテラルの検索に使用されるワイルドカード パターンにこれらのパターンをコンパイルできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="390dd-147">Note that these patterns can be compiled into an array of compiled regular expressions or an array of wildcard patterns used for literal searches.</span></span>

```csharp
[Parameter(
           Position = 1,
           ParameterSetName = "PatternParameterSet",
           Mandatory = true)]
public string[] Pattern
{
  get { return patterns; }
  set { patterns = value; }
}
private string[] patterns;
private Regex[] regexPattern;
private WildcardPattern[] wildcardPattern;
```

<span data-ttu-id="390dd-148">コマンドレットは既定のパラメーター セットを使用してこのパラメーターを指定すると、`PatternParameterSet`します。</span><span class="sxs-lookup"><span data-stu-id="390dd-148">When this parameter is specified, the cmdlet uses the default parameter set `PatternParameterSet`.</span></span> <span data-ttu-id="390dd-149">ここでは、コマンドレットは、ここで指定した文字列を選択するパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="390dd-149">In this case, the cmdlet uses the patterns specified here to select strings.</span></span> <span data-ttu-id="390dd-150">これに対し、`Script`パラメーターがパターンを格納するスクリプトを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="390dd-150">In contrast, the `Script` parameter could also be used to provide a script that contains the patterns.</span></span> <span data-ttu-id="390dd-151">`Script`と`Pattern`相互に排他的なので、パラメーターが 2 つの個別のパラメーター セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="390dd-151">The `Script` and `Pattern` parameters define two separate parameter sets, so they are mutually exclusive.</span></span>

### <a name="declaring-search-support-parameters"></a><span data-ttu-id="390dd-152">サポートの検索パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="390dd-152">Declaring Search Support Parameters</span></span>

<span data-ttu-id="390dd-153">このコマンドレットは、次のコマンドレットの検索機能を変更するために使用できるサポート パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="390dd-153">This cmdlet defines the following support parameters that can be used to modify the search capabilities of the cmdlet.</span></span>

<span data-ttu-id="390dd-154">`Script`パラメーターをコマンドレットの代替の検索メカニズムを提供するために使用するスクリプト ブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="390dd-154">The `Script` parameter specifies a script block that can be used to provide an alternate search mechanism for the cmdlet.</span></span> <span data-ttu-id="390dd-155">スクリプトの照合に使用するパターンが含まれてし、返す必要があります、、 [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="390dd-155">The script must contain the patterns used for matching and return a [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject) object.</span></span> <span data-ttu-id="390dd-156">このパラメーターを識別する一意のパラメーターも、`ScriptParameterSet`パラメーターのセット。</span><span class="sxs-lookup"><span data-stu-id="390dd-156">Note that this parameter is also the unique parameter that identifies the `ScriptParameterSet` parameter set.</span></span> <span data-ttu-id="390dd-157">属しているパラメーターのみを使用して、Windows PowerShell ランタイムでは、このパラメーターを見て、`ScriptParameterSet`パラメーターのセット。</span><span class="sxs-lookup"><span data-stu-id="390dd-157">When the Windows PowerShell runtime sees this parameter, it uses only parameters that belong to the `ScriptParameterSet` parameter set.</span></span>

```csharp
[Parameter(
           Position = 1,
           ParameterSetName = "ScriptParameterSet",
           Mandatory = true)]
public ScriptBlock Script
{
  set { script = value; }
  get { return script; }
}
ScriptBlock script;
```

<span data-ttu-id="390dd-158">`SimpleMatch`パラメーターは、コマンドレットが明示的に指定された、パターンに一致するかどうかを示す、スイッチ パラメーター。</span><span class="sxs-lookup"><span data-stu-id="390dd-158">The `SimpleMatch` parameter is a switch parameter that indicates whether the cmdlet is to explicitly match the patterns as they are supplied.</span></span> <span data-ttu-id="390dd-159">ユーザーがコマンド ライン パラメーターを指定します (`true`)、コマンドレットは、指定されたように、パターンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="390dd-159">When the user specifies the parameter at the command line (`true`), the cmdlet uses the patterns as they are supplied.</span></span> <span data-ttu-id="390dd-160">パラメーターが指定されていない場合 (`false`)、コマンドレットは、正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="390dd-160">If the parameter is not specified (`false`), the cmdlet uses regular expressions.</span></span> <span data-ttu-id="390dd-161">このパラメーターの既定値は`false`します。</span><span class="sxs-lookup"><span data-stu-id="390dd-161">The default for this parameter is `false`.</span></span>

```csharp
[Parameter]
public SwitchParameter SimpleMatch
{
  get { return simpleMatch; }
  set { simpleMatch = value; }
}
private bool simpleMatch;
```

<span data-ttu-id="390dd-162">`CaseSensitive`パラメーターは大文字と小文字を実行するかどうかを示す、スイッチ パラメーター。</span><span class="sxs-lookup"><span data-stu-id="390dd-162">The `CaseSensitive` parameter is a switch parameter that indicates whether a case-sensitive search is performed.</span></span> <span data-ttu-id="390dd-163">ユーザーがコマンド ライン パラメーターを指定します (`true`) パターンを比較するときに文字の小文字、大文字のコマンドレットを確認します。</span><span class="sxs-lookup"><span data-stu-id="390dd-163">When the user specifies the parameter at the command line (`true`), the cmdlet checks for the uppercase and lowercase of characters when comparing patterns.</span></span> <span data-ttu-id="390dd-164">パラメーターが指定されていない場合 (`false`)、コマンドレットが大文字と小文字の区別されません。</span><span class="sxs-lookup"><span data-stu-id="390dd-164">If the parameter is not specified (`false`), the cmdlet does not distinguish between uppercase and lowercase.</span></span> <span data-ttu-id="390dd-165">たとえば"MyFile"および"myfile"は両方として返されます正のヒット数。</span><span class="sxs-lookup"><span data-stu-id="390dd-165">For example "MyFile" and "myfile" would both be returned as positive hits.</span></span> <span data-ttu-id="390dd-166">このパラメーターの既定値は`false`します。</span><span class="sxs-lookup"><span data-stu-id="390dd-166">The default for this parameter is `false`.</span></span>

```csharp
[Parameter]
public SwitchParameter CaseSensitive
{
  get { return caseSensitive; }
  set { caseSensitive = value; }
}
private bool caseSensitive;
```

<span data-ttu-id="390dd-167">`Exclude`と`Include`パラメーターが明示的にから除外するか、検索に含めるアイテムを識別します。</span><span class="sxs-lookup"><span data-stu-id="390dd-167">The `Exclude` and `Include` parameters identify items that are explicitly excluded from or included in the search.</span></span> <span data-ttu-id="390dd-168">既定では、コマンドレットは、データ ストアに、すべての項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="390dd-168">By default, the cmdlet will search all items in the data store.</span></span> <span data-ttu-id="390dd-169">ただし、コマンドレットによって実行された検索を制限するをこれらのパラメーターに検索に含める項目を明示的に指定するために使用または省略するとすることができます。</span><span class="sxs-lookup"><span data-stu-id="390dd-169">However, to limit the search performed by the cmdlet, these parameters can be used to explicitly indicate items to be included in the search or omitted.</span></span>

```csharp
[Parameter]
public SwitchParameter CaseSensitive
{
  get { return caseSensitive; }
  set { caseSensitive = value; }
}
private bool caseSensitive;
```

```csharp
[Parameter]
[ValidateNotNullOrEmpty]
public string[] Include
{
  get
  {
    return includeStrings;
  }
  set
  {
    includeStrings = value;

    this.include = new WildcardPattern[includeStrings.Length];
    for (int i = 0; i < includeStrings.Length; i++)
    {
      this.include[i] = new WildcardPattern(includeStrings[i], WildcardOptions.IgnoreCase);
    }
  }
}

internal string[] includeStrings = null;
internal WildcardPattern[] include = null;
```

### <a name="declaring-parameter-sets"></a><span data-ttu-id="390dd-170">パラメーター セットを宣言します。</span><span class="sxs-lookup"><span data-stu-id="390dd-170">Declaring Parameter Sets</span></span>

<span data-ttu-id="390dd-171">このコマンドレットは、2 つのパラメーター セットを使用して (`ScriptParameterSet`と`PatternParameterSet`デフォルトである) データ アクセスで使用される 2 つのパラメーター セットの名前として。</span><span class="sxs-lookup"><span data-stu-id="390dd-171">This cmdlet uses two parameter sets (`ScriptParameterSet` and `PatternParameterSet`, which is thedefault) as the names of two parameter sets used in data access.</span></span> <span data-ttu-id="390dd-172">`PatternParameterSet` 既定のパラメーター セットは、使用するは、`Pattern`パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="390dd-172">`PatternParameterSet` is the default parameter set and is used when the `Pattern` parameter is specified.</span></span> <span data-ttu-id="390dd-173">`ScriptParameterSet` ユーザーが、別の検索のメカニズムを指定する場合に使用、`Script`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="390dd-173">`ScriptParameterSet` is used when the user specifies an alternate search mechanism through the `Script` parameter.</span></span> <span data-ttu-id="390dd-174">パラメーター セットの詳細については、次を参照してください。[パラメーター セットをコマンドレットに追加](./adding-parameter-sets-to-a-cmdlet.md)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-174">For more information about parameter sets, see [Adding Parameter Sets to a Cmdlet](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

## <a name="overriding-input-processing-methods"></a><span data-ttu-id="390dd-175">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="390dd-175">Overriding Input Processing Methods</span></span>

<span data-ttu-id="390dd-176">コマンドレットは 1 つ以上の入力処理メソッドをオーバーライドする必要があります、 [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラス。</span><span class="sxs-lookup"><span data-stu-id="390dd-176">Cmdlets must override one or more of the input processing methods for the [System.Management.Automation.Pscmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span> <span data-ttu-id="390dd-177">入力の処理方法の詳細については、次を参照してください。[最初のコマンドレットを、作成](./creating-a-cmdlet-without-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="390dd-177">For more information about the input processing methods, see [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="390dd-178">このコマンドレットのオーバーライド、 [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)の配列を構築するメソッドは、起動時に正規表現をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="390dd-178">This cmdlet overrides the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method to build an array of compiled regular expressions at startup.</span></span> <span data-ttu-id="390dd-179">これにより、単純な一致を使用しない検索中にパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="390dd-179">This increases performance during searches that do not use simple matching.</span></span>

```csharp
protected override void BeginProcessing()
{
  WriteDebug("Validating patterns.");
  if (patterns != null)
  {
    foreach(string pattern in patterns)
    {
      if (pattern == null)
      ThrowTerminatingError(new ErrorRecord(
                            new ArgumentNullException(
                            "Search pattern cannot be null."),
                            "NullSearchPattern",
                            ErrorCategory.InvalidArgument,
                            pattern)
                            );
    }

    WriteVerbose("Search pattern(s) are valid.");

    // If a simple match is not specified, then
    // compile the regular expressions once.
    if (!simpleMatch)
    {
      WriteDebug("Compiling search regular expressions.");

      RegexOptions regexOptions = RegexOptions.Compiled;
      if (!caseSensitive)
         regexOptions |= RegexOptions.Compiled;
      regexPattern = new Regex[patterns.Length];

      for (int i = 0; i < patterns.Length; i++)
      {
        try
        {
          regexPattern[i] = new Regex(patterns[i], regexOptions);
        }
        catch (ArgumentException ex)
        {
          ThrowTerminatingError(new ErrorRecord(
                        ex,
                        "InvalidRegularExpression",
                        ErrorCategory.InvalidArgument,
                        patterns[i]
                     ));
        }
      } //Loop through patterns to create RegEx objects.

      WriteVerbose("Pattern(s) compiled into regular expressions.");
    }// If not a simple match.

    // If a simple match is specified, then compile the
    // wildcard patterns once.
    else
    {
      WriteDebug("Compiling search wildcards.");

      WildcardOptions wildcardOptions = WildcardOptions.Compiled;

      if (!caseSensitive)
      {
        wildcardOptions |= WildcardOptions.IgnoreCase;
      }

      wildcardPattern = new WildcardPattern[patterns.Length];
      for (int i = 0; i < patterns.Length; i++)
      {
        wildcardPattern[i] =
                     new WildcardPattern(patterns[i], wildcardOptions);
      }

      WriteVerbose("Pattern(s) compiled into wildcard expressions.");
    }// If match is a simple match.
  }// If valid patterns are available.
}// End of function BeginProcessing().
```

<span data-ttu-id="390dd-180">このコマンドレットもオーバーライド、 [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)ユーザーがコマンド ライン オプションの文字列を処理するメソッド。</span><span class="sxs-lookup"><span data-stu-id="390dd-180">This cmdlet also overrides the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to process the string selections that the user makes on the command line.</span></span> <span data-ttu-id="390dd-181">プライベートを呼び出すことによって、カスタム オブジェクトの形式で文字列の選択の結果を書き込みます**MatchString**メソッド。</span><span class="sxs-lookup"><span data-stu-id="390dd-181">It writes the results of string selection in the form of a custom object by calling a private **MatchString** method.</span></span>

```csharp
protected override void ProcessRecord()
{
  UInt64 lineNumber = 0;
  MatchInfo result;
  ArrayList nonMatches = new ArrayList();

  // Walk the list of paths and search the contents for
  // any of the specified patterns.
  foreach (string psPath in paths)
  {
    // Once the filepaths are expanded, we may have more than one
    // path, so process all referenced paths.
    foreach(PathInfo path in
            SessionState.Path.GetResolvedPSPathFromPSPath(psPath)
           )
    {
      WriteVerbose("Processing path " + path.Path);

      // Check if the path represens one of the items to be
      // excluded. If so, continue to next path.
      if (!MeetsIncludeExcludeCriteria(path.ProviderPath))
         continue;

      // Get the content reader for the item(s) at the
      // specified path.
      Collection<IContentReader> readerCollection = null;
      try
      {
        readerCollection =
                    this.InvokeProvider.Content.GetReader(path.Path);
      }
      catch (PSNotSupportedException ex)
      {
        WriteError(new ErrorRecord(ex,
                   "ContentAccessNotSupported",
                    ErrorCategory.NotImplemented,
                    path.Path)
                   );
        return;
      }

      foreach(IContentReader reader in readerCollection)
      {
        // Reset the line number for this path.
        lineNumber = 0;

        // Read in a single block (line in case of a file)
        // from the object.
        IList items = reader.Read(1);

        // Read and process one block(line) at a time until
        // no more blocks(lines) exist.
        while (items != null && items.Count == 1)
        {
          // Increment the line number each time a line is
          // processed.
          lineNumber++;

          String message = String.Format("Testing line {0} : {1}",
                                        lineNumber, items[0]);

          WriteDebug(message);

          result = SelectString(items[0]);

          if (result != null)
          {
            result.Path = path.Path;
            result.LineNumber = lineNumber;

            WriteObject(result);
          }
          else
          {
            // Add the block(line) that did notmatch to the
            // collection of non matches , which will be stored
            // in the SessionState variable $NonMatches
            nonMatches.Add(items[0]);
          }

          // Get the next line from the object.
          items = reader.Read(1);

        }// While loop for reading one line at a time.
      }// Foreach loop for reader collection.
    }// Foreach loop for processing referenced paths.
  }// Foreach loop for walking of path list.

  // Store the list of non-matches in the
  // session state variable $NonMatches.
  try
  {
    this.SessionState.PSVariable.Set("NonMatches", nonMatches);
  }
  catch (SessionStateUnauthorizedAccessException ex)
  {
    WriteError(new ErrorRecord(ex,
               "CannotWriteVariableNonMatches",
               ErrorCategory.InvalidOperation,
               nonMatches)
              );
  }

}// End of protected override void ProcessRecord().
```

## <a name="accessing-content"></a><span data-ttu-id="390dd-182">コンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="390dd-182">Accessing Content</span></span>

<span data-ttu-id="390dd-183">コマンドレットは、データにアクセスできるように、Windows PowerShell パスで示される、プロバイダーを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="390dd-183">Your cmdlet must open the provider indicated by the Windows PowerShell path so that it can access the data.</span></span> <span data-ttu-id="390dd-184">[System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState)オブジェクト実行空間を使用するには、プロバイダーにアクセスするため、while、 [System.Management.Automation.Pscmdlet.Invokeprovider\*](/dotnet/api/System.Management.Automation.PSCmdlet.InvokeProvider)のプロパティ、コマンドレットは、プロバイダーを開くために使用します。</span><span class="sxs-lookup"><span data-stu-id="390dd-184">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) object for the runspace is used for access to the provider, while the [System.Management.Automation.Pscmdlet.Invokeprovider\*](/dotnet/api/System.Management.Automation.PSCmdlet.InvokeProvider) property of the cmdlet is used to open the provider.</span></span> <span data-ttu-id="390dd-185">取得によってコンテンツへのアクセスが提供される、 [System.Management.Automation.Providerintrinsics](/dotnet/api/System.Management.Automation.ProviderIntrinsics)プロバイダーのオブジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="390dd-185">Access to content is provided by retrieval of the [System.Management.Automation.Providerintrinsics](/dotnet/api/System.Management.Automation.ProviderIntrinsics) object for the provider  opened.</span></span>

<span data-ttu-id="390dd-186">このサンプルの Select Str コマンドレットを使用して、 [System.Management.Automation.Providerintrinsics.Content\*](/dotnet/api/System.Management.Automation.ProviderIntrinsics.Content)をスキャンするコンテンツを公開するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="390dd-186">This sample Select-Str cmdlet uses the [System.Management.Automation.Providerintrinsics.Content\*](/dotnet/api/System.Management.Automation.ProviderIntrinsics.Content) property to expose the content to scan.</span></span> <span data-ttu-id="390dd-187">呼び出して、 [System.Management.Automation.Contentcmdletproviderintrinsics.Getreader\*](/dotnet/api/System.Management.Automation.ContentCmdletProviderIntrinsics.GetReader)メソッド、必要な Windows PowerShell のパスを渡します。</span><span class="sxs-lookup"><span data-stu-id="390dd-187">It can then call the [System.Management.Automation.Contentcmdletproviderintrinsics.Getreader\*](/dotnet/api/System.Management.Automation.ContentCmdletProviderIntrinsics.GetReader) method, passing the required Windows PowerShell path.</span></span>

## <a name="code-sample"></a><span data-ttu-id="390dd-188">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="390dd-188">Code Sample</span></span>

<span data-ttu-id="390dd-189">次のコードでは、この選択 Str コマンドレットのこのバージョンの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="390dd-189">The following code shows the implementation of this version of this Select-Str cmdlet.</span></span> <span data-ttu-id="390dd-190">このコードには、コマンドレット クラス、コマンドレットで使用されるプライベート メソッドおよび Windows PowerShell、スナップイン コードは、コマンドレットを登録するために使用が含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="390dd-190">Note that this code includes the cmdlet class, private methods used by the cmdlet, and the Windows PowerShell snap-in code used to register the cmdlet.</span></span> <span data-ttu-id="390dd-191">コマンドレットの登録の詳細については、次を参照してください。[コマンドレットを構築](#Building-the-Cmdlet)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-191">For more information about registering the cmdlet, see [Building the Cmdlet](#Building-the-Cmdlet).</span></span>

```csharp
//
// Copyright (c) 2006 Microsoft Corporation. All rights reserved.
//
// THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF
// ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO
// THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A
// PARTICULAR PURPOSE.
//
using System;
using System.Text.RegularExpressions;
using System.Collections;
using System.Collections.ObjectModel;
using System.Management.Automation;
using System.Management.Automation.Provider;
using System.ComponentModel;

namespace Microsoft.Samples.PowerShell.Commands
{
  #region SelectStringCommand
  /// <summary>
  /// This cmdlet searches through PSObjects for particular patterns.
  /// </summary>
  /// <remarks>
  /// This cmdlet can be used to search any object, such as a file or a
  /// variable, whose provider exposes methods for reading and writing
  /// content.
  /// </remarks>
  [Cmdlet(VerbsCommon.Select, "Str", DefaultParameterSetName="PatternParameterSet")]
  public class SelectStringCommand : PSCmdlet
  {
    #region Parameters
    /// <summary>
    /// Declare a Path parameter that specifies where the data is stored.
    /// This parameter must specify a PowerShell that indicates the
    /// PowerShell provider that is used to access the objects to be
    /// searched for matching patterns. This parameter should also have
    /// a PSPath alias to provide consistancy with other cmdlets that use
    /// PowerShell providers.
    /// </summary>
    /// <value>Path of the object(s) to search.</value>
    [Parameter(
               Position = 0,
               ParameterSetName = "ScriptParameterSet",
               Mandatory = true)]
    [Parameter(
               Position = 0,
               ParameterSetName = "PatternParameterSet",
               ValueFromPipeline = true,
               Mandatory = true)]
               [Alias("PSPath")]
    public string[] Path
    {
      get { return paths; }
      set { paths = value; }
    }
    private string[] paths;

    /// <summary>
    /// Declare a Pattern parameter that specifies the pattern(s)
    /// used to find matching patterns in the string representation
    /// of the objects. A positive result will be returned
    /// if any of the patterns are found in the objects.
    /// </summary>
    /// <remarks>
    /// The patterns will be compiled into an array of wildcard
    /// patterns for a simple match (literal string matching),
    /// or the patterns will be converted into an array of compiled
    /// regular expressions.
    /// </remarks>
    /// <value>Array of patterns to search.</value>
    [Parameter(
               Position = 1,
               ParameterSetName = "PatternParameterSet",
               Mandatory = true)]
    public string[] Pattern
    {
      get { return patterns; }
      set { patterns = value; }
    }
    private string[] patterns;
    private Regex[] regexPattern;
    private WildcardPattern[] wildcardPattern;

    /// <summary>
    /// Declare a Script parameter that specifies a script block
    /// that is called to perform the matching operations
    /// instead of the matching performed by the cmdlet.
    /// </summary>
    /// <value>Script block that will be called for matching</value>
    [Parameter(
               Position = 1,
               ParameterSetName = "ScriptParameterSet",
               Mandatory = true)]
    public ScriptBlock Script
    {
      set { script = value; }
      get { return script; }
    }
    ScriptBlock script;

    /// <summary>
    /// Declare a switch parameter that specifies if the pattern(s) are used
    /// literally. If not (default), searching is
    /// done using regular expressions.
    /// </summary>
    /// <value>If True, a literal pattern is used.</value>
    [Parameter]
    public SwitchParameter SimpleMatch
    {
      get { return simpleMatch; }
      set { simpleMatch = value; }
    }
    private bool simpleMatch;

    /// <summary>
    /// Declare a switch parameter that specifies if a case-sensitive
    /// search is performed.  If not (default), a case-insensitive search
    /// is perfored.
    /// </summary>
    /// <value>If True, a case-sensitive search is made.</value>
    [Parameter]
    public SwitchParameter CaseSensitive
    {
      get { return caseSensitive; }
      set { caseSensitive = value; }
    }
    private bool caseSensitive;

    /// <summary>
    /// Declare an Include parameter that species which
    /// specific items are searched.  When this parameter
    /// is used, items that are not listed here are omitted
    /// from the search.
    /// </summary>
    [Parameter]
    [ValidateNotNullOrEmpty]
    public string[] Include
    {
      get
      {
        return includeStrings;
      }
      set
      {
        includeStrings = value;

        this.include = new WildcardPattern[includeStrings.Length];
        for (int i = 0; i < includeStrings.Length; i++)
        {
          this.include[i] = new WildcardPattern(includeStrings[i], WildcardOptions.IgnoreCase);
        }
      }
    }

    internal string[] includeStrings = null;
    internal WildcardPattern[] include = null;

    /// <summary>
    /// Declare an Exclude parameter that species which
    /// specific items are omitted from the search.
    /// </summary>
    ///
    [Parameter]
    [ValidateNotNullOrEmpty]
    public string[] Exclude
    {
      get
      {
        return excludeStrings;
      }
      set
      {
        excludeStrings = value;

        this.exclude = new WildcardPattern[excludeStrings.Length];
        for (int i = 0; i < excludeStrings.Length; i++)
        {
          this.exclude[i] = new WildcardPattern(excludeStrings[i], WildcardOptions.IgnoreCase);
        }
      }
    }
    internal string[] excludeStrings;
    internal WildcardPattern[] exclude;

    #endregion Parameters

    #region Overrides
    /// <summary>
    /// If regular expressions are used for pattern matching,
    /// then build an array of compiled regular expressions
    /// at startup. This increases performance during scanning
    /// operations when simple matching is not used.
    /// </summary>
    protected override void BeginProcessing()
    {
      WriteDebug("Validating patterns.");
      if (patterns != null)
      {
        foreach(string pattern in patterns)
        {
          if (pattern == null)
          ThrowTerminatingError(new ErrorRecord(
                                new ArgumentNullException(
                                "Search pattern cannot be null."),
                                "NullSearchPattern",
                                ErrorCategory.InvalidArgument,
                                pattern)
                                );
        }

        WriteVerbose("Search pattern(s) are valid.");

        // If a simple match is not specified, then
        // compile the regular expressions once.
        if (!simpleMatch)
        {
          WriteDebug("Compiling search regular expressions.");

          RegexOptions regexOptions = RegexOptions.Compiled;
          if (!caseSensitive)
             regexOptions |= RegexOptions.Compiled;
          regexPattern = new Regex[patterns.Length];

          for (int i = 0; i < patterns.Length; i++)
          {
            try
            {
              regexPattern[i] = new Regex(patterns[i], regexOptions);
            }
            catch (ArgumentException ex)
            {
              ThrowTerminatingError(new ErrorRecord(
                            ex,
                            "InvalidRegularExpression",
                            ErrorCategory.InvalidArgument,
                            patterns[i]
                         ));
            }
          } //Loop through patterns to create RegEx objects.

          WriteVerbose("Pattern(s) compiled into regular expressions.");
        }// If not a simple match.

        // If a simple match is specified, then compile the
        // wildcard patterns once.
        else
        {
          WriteDebug("Compiling search wildcards.");

          WildcardOptions wildcardOptions = WildcardOptions.Compiled;

          if (!caseSensitive)
          {
            wildcardOptions |= WildcardOptions.IgnoreCase;
          }

          wildcardPattern = new WildcardPattern[patterns.Length];
          for (int i = 0; i < patterns.Length; i++)
          {
            wildcardPattern[i] =
                         new WildcardPattern(patterns[i], wildcardOptions);
          }

          WriteVerbose("Pattern(s) compiled into wildcard expressions.");
        }// If match is a simple match.
      }// If valid patterns are available.
    }// End of function BeginProcessing().

    /// <summary>
    /// Process the input and search for the specified patterns.
    /// </summary>
    protected override void ProcessRecord()
    {
      UInt64 lineNumber = 0;
      MatchInfo result;
      ArrayList nonMatches = new ArrayList();

      // Walk the list of paths and search the contents for
      // any of the specified patterns.
      foreach (string psPath in paths)
      {
        // Once the filepaths are expanded, we may have more than one
        // path, so process all referenced paths.
        foreach(PathInfo path in
                SessionState.Path.GetResolvedPSPathFromPSPath(psPath)
               )
        {
          WriteVerbose("Processing path " + path.Path);

          // Check if the path represens one of the items to be
          // excluded. If so, continue to next path.
          if (!MeetsIncludeExcludeCriteria(path.ProviderPath))
             continue;

          // Get the content reader for the item(s) at the
          // specified path.
          Collection<IContentReader> readerCollection = null;
          try
          {
            readerCollection =
                        this.InvokeProvider.Content.GetReader(path.Path);
          }
          catch (PSNotSupportedException ex)
          {
            WriteError(new ErrorRecord(ex,
                       "ContentAccessNotSupported",
                        ErrorCategory.NotImplemented,
                        path.Path)
                       );
            return;
          }

          foreach(IContentReader reader in readerCollection)
          {
            // Reset the line number for this path.
            lineNumber = 0;

            // Read in a single block (line in case of a file)
            // from the object.
            IList items = reader.Read(1);

            // Read and process one block(line) at a time until
            // no more blocks(lines) exist.
            while (items != null && items.Count == 1)
            {
              // Increment the line number each time a line is
              // processed.
              lineNumber++;

              String message = String.Format("Testing line {0} : {1}",
                                            lineNumber, items[0]);

              WriteDebug(message);

              result = SelectString(items[0]);

              if (result != null)
              {
                result.Path = path.Path;
                result.LineNumber = lineNumber;

                WriteObject(result);
              }
              else
              {
                // Add the block(line) that did notmatch to the
                // collection of non matches , which will be stored
                // in the SessionState variable $NonMatches
                nonMatches.Add(items[0]);
              }

              // Get the next line from the object.
              items = reader.Read(1);

            }// While loop for reading one line at a time.
          }// Foreach loop for reader collection.
        }// Foreach loop for processing referenced paths.
      }// Foreach loop for walking of path list.

      // Store the list of non-matches in the
      // session state variable $NonMatches.
      try
      {
        this.SessionState.PSVariable.Set("NonMatches", nonMatches);
      }
      catch (SessionStateUnauthorizedAccessException ex)
      {
        WriteError(new ErrorRecord(ex,
                   "CannotWriteVariableNonMatches",
                   ErrorCategory.InvalidOperation,
                   nonMatches)
                  );
      }

    }// End of protected override void ProcessRecord().
    #endregion Overrides

    #region PrivateMethods
    /// <summary>
    /// Check for a match using the input string and the pattern(s)
    /// specified.
    /// </summary>
    /// <param name="input">The string to test.</param>
    /// <returns>MatchInfo object containing information about
    /// result of a match</returns>
    private MatchInfo SelectString(object input)
    {
      string line = null;

      try
      {
        // Convert the object to a string type
        // safely using language support methods
        line = (string)LanguagePrimitives.ConvertTo(
                                                    input,
                                                    typeof(string)
                                                    );
        line = line.Trim(' ','\t');
      }
      catch (PSInvalidCastException ex)
      {
        WriteError(new ErrorRecord(
                   ex,
                   "CannotCastObjectToString",
                   ErrorCategory.InvalidOperation,
                   input)
                   );

        return null;
      }

      MatchInfo result = null;

      // If a scriptblock has been specified, call it
      // with the path for processing.  It will return
      // one object.
      if (script != null)
      {
        WriteDebug("Executing script block.");

        Collection<PSObject> psObjects =
                             script.Invoke(
                                           line,
                                           simpleMatch,
                                           caseSensitive
                                          );

        foreach (PSObject psObject in psObjects)
        {
          if (LanguagePrimitives.IsTrue(psObject))
          {
            result = new MatchInfo();
            result.Line = line;
            result.IgnoreCase = !caseSensitive;

            break;
          } //End of If.
        } //End ForEach loop.
      } // End of If if script exists.

      // If script block exists, see if this line matches any
      // of the match patterns.
      else
      {
        int patternIndex = 0;

        while (patternIndex < patterns.Length)
        {
          if ((simpleMatch &&
              wildcardPattern[patternIndex].IsMatch(line))
              || (regexPattern != null
              && regexPattern[patternIndex].IsMatch(line))
             )
          {
            result = new MatchInfo();
            result.IgnoreCase = !caseSensitive;
            result.Line = line;
            result.Pattern = patterns[patternIndex];

            break;
          }

          patternIndex++;

        }// While loop through patterns.
      }// Else for no script block specified.

      return result;

    }// End of SelectString

    /// <summary>
    /// Check whether the supplied name meets the include/exclude criteria.
    /// That is - it's on the include list if the include list was
    /// specified, and not on the exclude list if the explude list was specified.
    /// </summary>
    /// <param name="path">path to validate</param>
    /// <returns>True if the path is acceptable.</returns>
    private bool MeetsIncludeExcludeCriteria(string path)
    {
      bool ok = false;

      // See if the file is on the include list.
      if (this.include != null)
      {
        foreach (WildcardPattern patternItem in this.include)
        {
          if (patternItem.IsMatch(path))
          {
            ok = true;
            break;
          }
        }
      }
      else
      {
        ok = true;
      }

      if (!ok)
         return false;

      // See if the file is on the exclude list.
      if (this.exclude != null)
      {
        foreach (WildcardPattern patternItem in this.exclude)
        {
          if (patternItem.IsMatch(path))
          {
            ok = false;
            break;
          }
        }
      }

      return ok;
    } //MeetsIncludeExcludeCriteria
    #endregion Private Methods

  }// class SelectStringCommand

  #endregion SelectStringCommand

  #region MatchInfo

  /// <summary>
  /// Class representing the result of a pattern/literal match
  /// that is passed through the pipeline by the Select-Str cmdlet.
  /// </summary>
  public class MatchInfo
  {
    /// <summary>
    /// Indicates if the match was done ignoring case.
    /// </summary>
    /// <value>True if case was ignored.</value>
    public bool IgnoreCase
    {
      get { return ignoreCase; }
      set { ignoreCase = value; }
    }
    private bool ignoreCase;

    /// <summary>
    /// Specifies the number of the matching line.
    /// </summary>
    /// <value>The number of the matching line.</value>
    public UInt64 LineNumber
    {
      get { return lineNumber; }
      set { lineNumber = value; }
    }
    private UInt64 lineNumber;

    /// <summary>
    /// Specifies the text of the matching line.
    /// </summary>
    /// <value>The text of the matching line.</value>
    public string Line
    {
      get { return line; }
      set { line = value; }
    }
    private string line;

    /// <summary>
    /// Specifies the full path of the object(file) containing the
    /// matching line.
    /// </summary>
    /// <remarks>
    /// It will be "inputStream" if the object came from the input
    /// stream.
    /// </remarks>
    /// <value>The path name</value>
    public string Path
    {
      get { return path; }
      set
      {
        pathSet = true;
        path = value;
      }
    }
    private string path;
    private bool pathSet;

    /// <summary>
    /// Specifies the pattern that was used in the match.
    /// </summary>
    /// <value>The pattern string</value>
    public string Pattern
    {
      get { return pattern; }
      set { pattern = value; }
    }
    private string pattern;

    private const string MatchFormat = "{0}:{1}:{2}";

    /// <summary>
    /// Returns the string representation of this object. The format
    /// depends on whether a path has been set for this object or
    /// not.
    /// </summary>
    /// <remarks>
    /// If the path component is set, as would be the case when
    /// matching in a file, ToString() returns the path, line
    /// number and line text.  If path is not set, then just the
    /// line text is presented.
    /// </remarks>
    /// <returns>The string representation of the match object.</returns>
    public override string ToString()
    {
      if (pathSet)
         return String.Format(
         System.Threading.Thread.CurrentThread.CurrentCulture,
         MatchFormat,
         this.path,
         this.lineNumber,
         this.line
         );
      else
         return this.line;
    }
  }// End class MatchInfo

  #endregion

  #region PowerShell snap-in

  /// <summary>
  /// Create a PowerShell snap-in for the Select-Str cmdlet.
  /// </summary>
  [RunInstaller(true)]
  public class SelectStringPSSnapIn : PSSnapIn
  {
    /// <summary>
    /// Create an instance of the SelectStrPSSnapin class.
    /// </summary>
    public SelectStringPSSnapIn()
           : base()
    {
    }

    /// <summary>
    /// Specify the name of the PowerShell snap-in.
    /// </summary>
    public override string Name
    {
      get
      {
        return "SelectStrPSSnapIn";
      }
    }

    /// <summary>
    /// Specify the vendor of the PowerShell snap-in.
    /// </summary>
    public override string Vendor
    {
      get
      {
        return "Microsoft";
      }
    }

    /// <summary>
    /// Specify the localization resource information for the vendor.
    /// Use the format: SnapinName,VendorName.
    /// </summary>
    public override string VendorResource
    {
      get
      {
        return "SelectStrSnapIn,Microsoft";
      }
    }

    /// <summary>
    /// Specifiy the description of the PowerShell snap-in.
    /// </summary>
    public override string Description
    {
      get
        {
          return "This is a PowerShell snap-in for the Select-Str cmdlet.";
        }
    }

    /// <summary>
    /// Specify the localization resource information for the description.
    /// Use the format: SnapinName,Description.

    /// </summary>
    public override string DescriptionResource
    {
      get
      {
          return "SelectStrSnapIn,This is a PowerShell snap-in for the Select-Str cmdlet.";
      }
    }
  }
  #endregion PowerShell snap-in

} //namespace Microsoft.Samples.PowerShell.Commands;
```

## <a name="building-the-cmdlet"></a><span data-ttu-id="390dd-192">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="390dd-192">Building the Cmdlet</span></span>

<span data-ttu-id="390dd-193">コマンドレットを実装するには、後にする必要がありますに登録する Windows PowerShell Windows PowerShell スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="390dd-193">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="390dd-194">コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)します。</span><span class="sxs-lookup"><span data-stu-id="390dd-194">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="390dd-195">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="390dd-195">Testing the Cmdlet</span></span>

<span data-ttu-id="390dd-196">コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="390dd-196">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="390dd-197">次の手順を使用して、サンプルの Select Str コマンドレットをテストできます。</span><span class="sxs-lookup"><span data-stu-id="390dd-197">The following procedure can be used to test the sample Select-Str cmdlet.</span></span>

1. <span data-ttu-id="390dd-198">Windows PowerShell を起動し、ノート ファイルの".NET"の式に行を検索します。</span><span class="sxs-lookup"><span data-stu-id="390dd-198">Start Windows PowerShell, and search the Notes file for occurrences of lines with the expression ".NET".</span></span> <span data-ttu-id="390dd-199">1 つ以上の単語のパスが構成されている場合にのみ、パスの名前を囲む引用符が必要なことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="390dd-199">Note that the quotation marks around the name of the path are required only if the path consists of more than one word.</span></span>

    ```powershell
    select-str -Path "notes" -Pattern ".NET" -SimpleMatch=$false
    ```

    <span data-ttu-id="390dd-200">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="390dd-200">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 8
    Line         : Because Windows PowerShell works directly with .NET objects, there is often a .NET object
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : .NET
    IgnoreCase   : True
    LineNumber   : 21
    Line         : You should normally define the class for a cmdlet in a .NET namespace
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : .NET
    ```

2. <span data-ttu-id="390dd-201">他のテキストに続く「で」という単語がある行の出現箇所のノート ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="390dd-201">Search the Notes file for occurrences of lines with the word "over", followed by any other text.</span></span> <span data-ttu-id="390dd-202">`SimpleMatch`パラメーターがの既定値を使用して`false`します。</span><span class="sxs-lookup"><span data-stu-id="390dd-202">The `SimpleMatch` parameter is using the default value of `false`.</span></span> <span data-ttu-id="390dd-203">検索は大文字と小文字ため、`CaseSensitive`にパラメーターが設定されている`false`します。</span><span class="sxs-lookup"><span data-stu-id="390dd-203">The search is case-insensitive because the `CaseSensitive` parameter is set to `false`.</span></span>

    ```powershell
    select-str -Path notes -Pattern "over*" -SimpleMatch -CaseSensitive:$false
    ```

    <span data-ttu-id="390dd-204">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="390dd-204">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 45
    Line         : Override StopProcessing
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : over*
    IgnoreCase   : True
    LineNumber   : 49
    Line         : overriding the StopProcessing method
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : over*
    ```

3. <span data-ttu-id="390dd-205">パターンと正規表現を使用して、ノート ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="390dd-205">Search the Notes file using a regular expression as the pattern.</span></span> <span data-ttu-id="390dd-206">コマンドレットは、アルファベット文字とかっこで囲まれた空白文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="390dd-206">The cmdlet searches for alphabetical characters and blank spaces enclosed in parentheses.</span></span>

    ```powershell
    select-str -Path notes -Pattern "\([A-Za-z:blank:]" -SimpleMatch:$false
    ```

    <span data-ttu-id="390dd-207">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="390dd-207">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 1
    Line         : Advisory Guidelines (Consider Following)
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : \([A-Za-z:blank:]
    IgnoreCase   : True
    LineNumber   : 53
    Line         : If your cmdlet has objects that are not disposed of (written to the pipeline)
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : \([A-Za-z:blank:]
    ```

4. <span data-ttu-id="390dd-208">「パラメーター」という単語の出現回数のノート ファイルの検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="390dd-208">Perform a case-sensitive search of the Notes file for occurrences of the word "Parameter".</span></span>

    ```powershell
    select-str -Path notes -Pattern Parameter -CaseSensitive
    ```

    <span data-ttu-id="390dd-209">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="390dd-209">The following output appears.</span></span>

    ```output
    IgnoreCase   : False
    LineNumber   : 6
    Line         : Support an InputObject Parameter
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : Parameter
    IgnoreCase   : False
    LineNumber   : 30
    Line         : Support Force Parameter
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : Parameter
    ```

5. <span data-ttu-id="390dd-210">検索変数プロバイダーは、0 ~ 9 の数値を持つ変数に対して Windows PowerShell に付属します。</span><span class="sxs-lookup"><span data-stu-id="390dd-210">Search the variable provider shipped with Windows PowerShell for variables that have numerical values from 0 through 9.</span></span>

    ```powershell
    select-str -Path * -Pattern "[0-9]"
    ```

    <span data-ttu-id="390dd-211">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="390dd-211">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 1
    Line         : 64
    Path         : Variable:\MaximumHistoryCount
    Pattern      : [0-9]
    ```

6. <span data-ttu-id="390dd-212">スクリプト ブロックを使用して、文字列"Pos"SelectStrCommandSample.cs ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="390dd-212">Use a script block to search the file SelectStrCommandSample.cs for the string "Pos".</span></span> <span data-ttu-id="390dd-213">**Cmatch**関数のスクリプトは、大文字のパターン マッチングを実行します。</span><span class="sxs-lookup"><span data-stu-id="390dd-213">The **cmatch** function for the script performs a case-insensitive pattern match.</span></span>

    ```powershell
    select-str -Path "SelectStrCommandSample.cs" -Script { if ($args[0] -cmatch "Pos"){ return $true } return $false }
    ```

    <span data-ttu-id="390dd-214">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="390dd-214">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 37
    Line         :    Position = 0.
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\SelectStrCommandSample.cs
    Pattern      :
    ```

## <a name="see-also"></a><span data-ttu-id="390dd-215">参照</span><span class="sxs-lookup"><span data-stu-id="390dd-215">See Also</span></span>

[<span data-ttu-id="390dd-216">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="390dd-216">How to Create a Windows PowerShell Cmdlet</span></span>](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="390dd-217">初めてのコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="390dd-217">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="390dd-218">システムを変更するコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="390dd-218">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="390dd-219">Windows PowerShell プロバイダーを設計します。</span><span class="sxs-lookup"><span data-stu-id="390dd-219">Design Your Windows PowerShell Provider</span></span>](../prog-guide/designing-your-windows-powershell-provider.md)

[<span data-ttu-id="390dd-220">Windows PowerShell の動作</span><span class="sxs-lookup"><span data-stu-id="390dd-220">How Windows PowerShell Works</span></span>](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[<span data-ttu-id="390dd-221">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="390dd-221">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="390dd-222">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="390dd-222">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

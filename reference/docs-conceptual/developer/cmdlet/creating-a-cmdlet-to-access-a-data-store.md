---
title: データ ストアにアクセスするためのコマンドレットを作成する
ms.date: 09/13/2016
ms.openlocfilehash: a595805a820c355937e581f0e00fa2a9a9fc3df0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782142"
---
# <a name="creating-a-cmdlet-to-access-a-data-store"></a><span data-ttu-id="37465-102">データ ストアにアクセスするためのコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="37465-102">Creating a Cmdlet to Access a Data Store</span></span>

<span data-ttu-id="37465-103">このセクションでは、Windows PowerShell プロバイダーを介して格納されたデータにアクセスするコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="37465-103">This section describes how to create a cmdlet that accesses stored data by way of a Windows PowerShell provider.</span></span> <span data-ttu-id="37465-104">この種類のコマンドレットは、Windows PowerShell ランタイムの Windows PowerShell プロバイダーインフラストラクチャを使用するため、コマンドレットクラスは[PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)基底クラスから派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37465-104">This type of cmdlet uses the Windows PowerShell provider infrastructure of the Windows PowerShell runtime and, therefore, the cmdlet class must derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span>

<span data-ttu-id="37465-105">ここで説明する Select-Str コマンドレットは、ファイルまたはオブジェクト内の文字列を検索して選択できます。</span><span class="sxs-lookup"><span data-stu-id="37465-105">The Select-Str cmdlet described here can locate and select strings in a file or object.</span></span> <span data-ttu-id="37465-106">文字列を識別するために使用されるパターンは、コマンドレットのパラメーターを使用して明示的に指定することも、パラメーターを使用して暗黙的に指定することもでき `Path` `Script` ます。</span><span class="sxs-lookup"><span data-stu-id="37465-106">The patterns used to identify the string can be specified explicitly through the `Path` parameter of the cmdlet or implicitly through the `Script` parameter.</span></span>

<span data-ttu-id="37465-107">コマンドレットは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)から派生した任意の Windows PowerShell プロバイダーを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="37465-107">The cmdlet is designed to use any Windows PowerShell provider that derives from [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider).</span></span> <span data-ttu-id="37465-108">たとえば、コマンドレットでは、Windows PowerShell によって提供されるファイルシステムプロバイダーまたは変数プロバイダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="37465-108">For example, the cmdlet can specify the FileSystem provider or the Variable provider that is provided by Windows PowerShell.</span></span> <span data-ttu-id="37465-109">Windows PowerShell プロバイダーの詳細については、「 [Windows powershell プロバイダーの設計](../prog-guide/designing-your-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37465-109">For more information aboutWindows PowerShell providers, see [Designing Your Windows PowerShell provider](../prog-guide/designing-your-windows-powershell-provider.md).</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="37465-110">コマンドレットクラスの定義</span><span class="sxs-lookup"><span data-stu-id="37465-110">Defining the Cmdlet Class</span></span>

<span data-ttu-id="37465-111">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="37465-111">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="37465-112">このコマンドレットは特定の文字列を検出するため、ここで選択した動詞名は "Select" で、 [Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon)クラスで定義されています。</span><span class="sxs-lookup"><span data-stu-id="37465-112">This cmdlet detects certain strings, so the verb name chosen here is "Select", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) class.</span></span> <span data-ttu-id="37465-113">名詞名 "Str" は、コマンドレットが文字列に対して動作するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="37465-113">The noun name "Str" is used because the cmdlet acts upon strings.</span></span> <span data-ttu-id="37465-114">次の宣言では、コマンドレット動詞と名詞名がコマンドレットクラスの名前に反映されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="37465-114">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span> <span data-ttu-id="37465-115">承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37465-115">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="37465-116">このコマンドレットの .NET クラスは、windows powershell プロバイダーのインフラストラクチャを公開するために Windows PowerShell ランタイムが必要とするサポートを提供するため、 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)基底クラスから派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37465-116">The .NET class for this cmdlet must derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class, because it provides the support needed by the Windows PowerShell runtime to expose the Windows PowerShell provider infrastructure.</span></span> <span data-ttu-id="37465-117">このコマンドレットは、 [system.text.regularexpressions.regexoptions](/dotnet/api/System.Text.RegularExpressions.Regex)などの .NET Framework 正規表現クラスを使用することにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="37465-117">Note that this cmdlet also makes use of the .NET Framework regular expressions classes, such as [System.Text.Regularexpressions.Regex](/dotnet/api/System.Text.RegularExpressions.Regex).</span></span>

<span data-ttu-id="37465-118">次のコードは、この Select-Str コマンドレットのクラス定義です。</span><span class="sxs-lookup"><span data-stu-id="37465-118">The following code is the class definition for this Select-Str cmdlet.</span></span>

```csharp
[Cmdlet(VerbsCommon.Select, "Str", DefaultParameterSetName="PatternParameterSet")]
public class SelectStringCommand : PSCmdlet
```

<span data-ttu-id="37465-119">このコマンドレットは、 `DefaultParameterSetName` class 宣言に attribute キーワードを追加することによって、既定のパラメーターセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="37465-119">This cmdlet defines a default parameter set by adding the `DefaultParameterSetName` attribute keyword to the class declaration.</span></span> <span data-ttu-id="37465-120">パラメーターが指定されていない場合は、既定のパラメーターセット `PatternParameterSet` が使用され `Script` ます。</span><span class="sxs-lookup"><span data-stu-id="37465-120">The default parameter set `PatternParameterSet` is used when the `Script` parameter is not specified.</span></span> <span data-ttu-id="37465-121">このパラメーターセットの詳細については、 `Pattern` 次のセクションのおよびパラメーターの説明を参照してください `Script` 。</span><span class="sxs-lookup"><span data-stu-id="37465-121">For more information about this parameter set, see the `Pattern` and `Script` parameter discussion in the following section.</span></span>

## <a name="defining-parameters-for-data-access"></a><span data-ttu-id="37465-122">データアクセスのためのパラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="37465-122">Defining Parameters for Data Access</span></span>

<span data-ttu-id="37465-123">このコマンドレットは、ユーザーが格納されたデータにアクセスして確認できるようにするいくつかのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="37465-123">This cmdlet defines several parameters that allow the user to access and examine stored data.</span></span> <span data-ttu-id="37465-124">これらのパラメーターには、 `Path` データストアの場所を示すパラメーター、 `Pattern` 検索で使用するパターンを指定するパラメーター、および検索の実行方法をサポートするその他のいくつかのパラメーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="37465-124">These parameters include a `Path` parameter that indicates the location of the data store, a `Pattern` parameter that specifies the pattern to be used in the search, and several other parameters that support how the search is performed.</span></span>

> [!NOTE]
> <span data-ttu-id="37465-125">パラメーターの定義の基本の詳細については、「[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37465-125">For more information about the basics of defining parameters, see [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

### <a name="declaring-the-path-parameter"></a><span data-ttu-id="37465-126">Path パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="37465-126">Declaring the Path Parameter</span></span>

<span data-ttu-id="37465-127">データストアを検索するには、このコマンドレットで Windows PowerShell のパスを使用して、データストアにアクセスするように設計されている Windows PowerShell プロバイダーを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37465-127">To locate the data store, this cmdlet must use a Windows PowerShell path to identify the Windows PowerShell provider that is designed to access the data store.</span></span> <span data-ttu-id="37465-128">したがって、 `Path` プロバイダーの場所を示す文字列配列型のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="37465-128">Therefore, it defines a `Path` parameter of type string array to indicate the location of the provider.</span></span>

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

<span data-ttu-id="37465-129">このパラメーターは、2つの異なるパラメーターセットに属しており、別名を持っていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="37465-129">Note that this parameter belongs to two different parameter sets and that it has an alias.</span></span>

<span data-ttu-id="37465-130">2[つの system.object 属性は](/dotnet/api/System.Management.Automation.ParameterAttribute)、パラメーターがとに属していることを宣言します。 `Path` `ScriptParameterSet` `PatternParameterSet`</span><span class="sxs-lookup"><span data-stu-id="37465-130">Two [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attributes declare that the `Path` parameter belongs to the `ScriptParameterSet` and the `PatternParameterSet`.</span></span> <span data-ttu-id="37465-131">パラメーターセットの詳細については、「[コマンドレットへのパラメーターセットの追加](./adding-parameter-sets-to-a-cmdlet.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37465-131">For more information about parameter sets, see [Adding Parameter Sets to a Cmdlet](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

<span data-ttu-id="37465-132">System.string[属性は、](/dotnet/api/System.Management.Automation.AliasAttribute) `PSPath` パラメーターの別名を宣言します。 `Path`</span><span class="sxs-lookup"><span data-stu-id="37465-132">The [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute declares a `PSPath` alias for the `Path` parameter.</span></span> <span data-ttu-id="37465-133">Windows PowerShell プロバイダーにアクセスする他のコマンドレットとの一貫性を確保するために、このエイリアスを宣言することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37465-133">Declaring this alias is strongly recommended for consistency with other cmdlets that access Windows PowerShell providers.</span></span> <span data-ttu-id="37465-134">Windows PowerShell パスの詳細については、「 [Windows powershell の動作](/previous-versions//ms714658(v=vs.85))のしくみ」の「PowerShell パスの概念」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37465-134">For more information aboutWindows PowerShell paths, see "PowerShell Path Concepts" in [How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85)).</span></span>

### <a name="declaring-the-pattern-parameter"></a><span data-ttu-id="37465-135">Pattern パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="37465-135">Declaring the Pattern Parameter</span></span>

<span data-ttu-id="37465-136">検索するパターンを指定するために、このコマンドレット `Pattern` は文字列の配列であるパラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="37465-136">To specify the patterns to search for, this cmdlet declares a `Pattern` parameter that is an array of strings.</span></span> <span data-ttu-id="37465-137">データストアにパターンが見つかった場合は、正の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="37465-137">A positive result is returned when any of the patterns are found in the data store.</span></span> <span data-ttu-id="37465-138">これらのパターンは、コンパイル済みの正規表現の配列、またはリテラル検索に使用されるワイルドカードパターンの配列にコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="37465-138">Note that these patterns can be compiled into an array of compiled regular expressions or an array of wildcard patterns used for literal searches.</span></span>

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

<span data-ttu-id="37465-139">このパラメーターを指定すると、コマンドレットは既定のパラメーターセットを使用し `PatternParameterSet` ます。</span><span class="sxs-lookup"><span data-stu-id="37465-139">When this parameter is specified, the cmdlet uses the default parameter set `PatternParameterSet`.</span></span> <span data-ttu-id="37465-140">この場合、コマンドレットは、ここで指定されたパターンを使用して文字列を選択します。</span><span class="sxs-lookup"><span data-stu-id="37465-140">In this case, the cmdlet uses the patterns specified here to select strings.</span></span> <span data-ttu-id="37465-141">これに対し `Script` て、パラメーターを使用して、パターンを含むスクリプトを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="37465-141">In contrast, the `Script` parameter could also be used to provide a script that contains the patterns.</span></span> <span data-ttu-id="37465-142">`Script`パラメーターと `Pattern` パラメーターは2つの異なるパラメーターセットを定義するため、相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="37465-142">The `Script` and `Pattern` parameters define two separate parameter sets, so they are mutually exclusive.</span></span>

### <a name="declaring-search-support-parameters"></a><span data-ttu-id="37465-143">検索サポートパラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="37465-143">Declaring Search Support Parameters</span></span>

<span data-ttu-id="37465-144">このコマンドレットは、コマンドレットの検索機能を変更するために使用できる次のサポートパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="37465-144">This cmdlet defines the following support parameters that can be used to modify the search capabilities of the cmdlet.</span></span>

<span data-ttu-id="37465-145">パラメーターは、 `Script` コマンドレットの代替検索メカニズムを提供するために使用できるスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="37465-145">The `Script` parameter specifies a script block that can be used to provide an alternate search mechanism for the cmdlet.</span></span> <span data-ttu-id="37465-146">このスクリプトには、照合に使用されるパターンが含まれている必要があります。[また、このオブジェクトを](/dotnet/api/System.Management.Automation.PSObject)返します。</span><span class="sxs-lookup"><span data-stu-id="37465-146">The script must contain the patterns used for matching and return a [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) object.</span></span> <span data-ttu-id="37465-147">このパラメーターは、パラメーターセットを識別する一意のパラメーターでもあることに注意して `ScriptParameterSet` ください。</span><span class="sxs-lookup"><span data-stu-id="37465-147">Note that this parameter is also the unique parameter that identifies the `ScriptParameterSet` parameter set.</span></span> <span data-ttu-id="37465-148">Windows PowerShell ランタイムは、このパラメーターを認識すると、パラメーターセットに属するパラメーターのみを使用し `ScriptParameterSet` ます。</span><span class="sxs-lookup"><span data-stu-id="37465-148">When the Windows PowerShell runtime sees this parameter, it uses only parameters that belong to the `ScriptParameterSet` parameter set.</span></span>

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

<span data-ttu-id="37465-149">パラメーターは、 `SimpleMatch` 指定されたパターンをコマンドレットが明示的に一致させるかどうかを示すスイッチパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="37465-149">The `SimpleMatch` parameter is a switch parameter that indicates whether the cmdlet is to explicitly match the patterns as they are supplied.</span></span> <span data-ttu-id="37465-150">ユーザーがコマンドライン () でパラメーターを指定すると、コマンド `true` レットは、指定されたパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="37465-150">When the user specifies the parameter at the command line (`true`), the cmdlet uses the patterns as they are supplied.</span></span> <span data-ttu-id="37465-151">パラメーターが指定されていない場合 ( `false` )、コマンドレットは正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="37465-151">If the parameter is not specified (`false`), the cmdlet uses regular expressions.</span></span> <span data-ttu-id="37465-152">このパラメーターの既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="37465-152">The default for this parameter is `false`.</span></span>

```csharp
[Parameter]
public SwitchParameter SimpleMatch
{
  get { return simpleMatch; }
  set { simpleMatch = value; }
}
private bool simpleMatch;
```

<span data-ttu-id="37465-153">パラメーターは、 `CaseSensitive` 大文字と小文字を区別する検索を実行するかどうかを示すスイッチパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="37465-153">The `CaseSensitive` parameter is a switch parameter that indicates whether a case-sensitive search is performed.</span></span> <span data-ttu-id="37465-154">ユーザーがコマンドライン () でパラメーターを指定すると、パターンを比較するときに、コマンドレットによって `true` 大文字と小文字がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="37465-154">When the user specifies the parameter at the command line (`true`), the cmdlet checks for the uppercase and lowercase of characters when comparing patterns.</span></span> <span data-ttu-id="37465-155">パラメーターが指定されていない場合 ( `false` )、このコマンドレットでは大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="37465-155">If the parameter is not specified (`false`), the cmdlet does not distinguish between uppercase and lowercase.</span></span> <span data-ttu-id="37465-156">たとえば、"MyFile" と "myfile" は、両方とも正のヒットとして返されます。</span><span class="sxs-lookup"><span data-stu-id="37465-156">For example "MyFile" and "myfile" would both be returned as positive hits.</span></span> <span data-ttu-id="37465-157">このパラメーターの既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="37465-157">The default for this parameter is `false`.</span></span>

```csharp
[Parameter]
public SwitchParameter CaseSensitive
{
  get { return caseSensitive; }
  set { caseSensitive = value; }
}
private bool caseSensitive;
```

<span data-ttu-id="37465-158">`Exclude`およびパラメーターは、 `Include` 検索に明示的に除外されている項目または検索に含まれる項目を識別します。</span><span class="sxs-lookup"><span data-stu-id="37465-158">The `Exclude` and `Include` parameters identify items that are explicitly excluded from or included in the search.</span></span> <span data-ttu-id="37465-159">既定では、このコマンドレットはデータストア内のすべての項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="37465-159">By default, the cmdlet will search all items in the data store.</span></span> <span data-ttu-id="37465-160">ただし、コマンドレットによって実行される検索を制限するために、これらのパラメーターを使用して、検索に含める項目を明示的に指定することも、省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="37465-160">However, to limit the search performed by the cmdlet, these parameters can be used to explicitly indicate items to be included in the search or omitted.</span></span>

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

### <a name="declaring-parameter-sets"></a><span data-ttu-id="37465-161">パラメーターセットの宣言</span><span class="sxs-lookup"><span data-stu-id="37465-161">Declaring Parameter Sets</span></span>

<span data-ttu-id="37465-162">このコマンドレットは `ScriptParameterSet` `PatternParameterSet` 、データアクセスで使用される2つのパラメーターセットの名前として、2つのパラメーターセット (既定) を使用します。</span><span class="sxs-lookup"><span data-stu-id="37465-162">This cmdlet uses two parameter sets (`ScriptParameterSet` and `PatternParameterSet`, which is the default) as the names of two parameter sets used in data access.</span></span> <span data-ttu-id="37465-163">`PatternParameterSet`は既定のパラメーターセットであり、パラメーターが指定されている場合に使用され `Pattern` ます。</span><span class="sxs-lookup"><span data-stu-id="37465-163">`PatternParameterSet` is the default parameter set and is used when the `Pattern` parameter is specified.</span></span> <span data-ttu-id="37465-164">`ScriptParameterSet`は、ユーザーがパラメーターを使用して代替検索機構を指定するときに使用され `Script` ます。</span><span class="sxs-lookup"><span data-stu-id="37465-164">`ScriptParameterSet` is used when the user specifies an alternate search mechanism through the `Script` parameter.</span></span> <span data-ttu-id="37465-165">パラメーターセットの詳細については、「[コマンドレットへのパラメーターセットの追加](./adding-parameter-sets-to-a-cmdlet.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37465-165">For more information about parameter sets, see [Adding Parameter Sets to a Cmdlet](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

## <a name="overriding-input-processing-methods"></a><span data-ttu-id="37465-166">オーバーライド (入力処理メソッドを)</span><span class="sxs-lookup"><span data-stu-id="37465-166">Overriding Input Processing Methods</span></span>

<span data-ttu-id="37465-167">コマンドレットは、 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラスの1つ以上の入力処理メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37465-167">Cmdlets must override one or more of the input processing methods for the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span> <span data-ttu-id="37465-168">入力処理方法の詳細については、「[最初のコマンドレットの作成](./creating-a-cmdlet-without-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37465-168">For more information about the input processing methods, see [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="37465-169">このコマンドレットは、起動時にコンパイルされた正規表現の配列を構築するために、[システム管理](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="37465-169">This cmdlet overrides the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method to build an array of compiled regular expressions at startup.</span></span> <span data-ttu-id="37465-170">これにより、単純一致を使用しない検索時のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="37465-170">This increases performance during searches that do not use simple matching.</span></span>

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

<span data-ttu-id="37465-171">また、このコマンドレットは、コマンドラインでユーザーが選択した文字列を処理するため[に、system.string メソッドも](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)オーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="37465-171">This cmdlet also overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to process the string selections that the user makes on the command line.</span></span> <span data-ttu-id="37465-172">プライベート**matchstring**メソッドを呼び出すことにより、カスタムオブジェクトの形式で文字列選択の結果を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="37465-172">It writes the results of string selection in the form of a custom object by calling a private **MatchString** method.</span></span>

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

      // Check if the path represents one of the items to be
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
            // Add the block(line) that did not match to the
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

## <a name="accessing-content"></a><span data-ttu-id="37465-173">コンテンツへのアクセス</span><span class="sxs-lookup"><span data-stu-id="37465-173">Accessing Content</span></span>

<span data-ttu-id="37465-174">コマンドレットは、Windows PowerShell パスによって示されるプロバイダーを開いて、データにアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37465-174">Your cmdlet must open the provider indicated by the Windows PowerShell path so that it can access the data.</span></span> <span data-ttu-id="37465-175">実行空間の[Sessionstate](/dotnet/api/System.Management.Automation.SessionState)オブジェクトは、プロバイダーへのアクセスに使用されます。また、コマンドレットの[PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet.InvokeProvider)プロパティは、プロバイダーを開くために使用されていますが、</span><span class="sxs-lookup"><span data-stu-id="37465-175">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) object for the runspace is used for access to the provider, while the [System.Management.Automation.PSCmdlet.Invokeprovider\*](/dotnet/api/System.Management.Automation.PSCmdlet.InvokeProvider) property of the cmdlet is used to open the provider.</span></span> <span data-ttu-id="37465-176">コンテンツへのアクセスは、開いているプロバイダーの[システムの管理](/dotnet/api/System.Management.Automation.ProviderIntrinsics)オブジェクトを取得することによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="37465-176">Access to content is provided by retrieval of the [System.Management.Automation.Providerintrinsics](/dotnet/api/System.Management.Automation.ProviderIntrinsics) object for the provider opened.</span></span>

<span data-ttu-id="37465-177">このサンプルの Select-Str コマンドレットは、スキャンするコンテンツを公開するために、system.string [\*](/dotnet/api/System.Management.Automation.ProviderIntrinsics.Content)プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="37465-177">This sample Select-Str cmdlet uses the [System.Management.Automation.Providerintrinsics.Content\*](/dotnet/api/System.Management.Automation.ProviderIntrinsics.Content) property to expose the content to scan.</span></span> <span data-ttu-id="37465-178">次に、必要な Windows PowerShell のパスを渡して、 [System.](/dotnet/api/System.Management.Automation.ContentCmdletProviderIntrinsics.GetReader) ...... というメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="37465-178">It can then call the [System.Management.Automation.Contentcmdletproviderintrinsics.Getreader\*](/dotnet/api/System.Management.Automation.ContentCmdletProviderIntrinsics.GetReader) method, passing the required Windows PowerShell path.</span></span>

## <a name="code-sample"></a><span data-ttu-id="37465-179">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="37465-179">Code Sample</span></span>

<span data-ttu-id="37465-180">次のコードは、この Select-Str コマンドレットのこのバージョンの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="37465-180">The following code shows the implementation of this version of this Select-Str cmdlet.</span></span> <span data-ttu-id="37465-181">このコードには、コマンドレットによって使用されるプライベートメソッドと、コマンドレットの登録に使用される Windows PowerShell スナップインコードが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="37465-181">Note that this code includes the cmdlet class, private methods used by the cmdlet, and the Windows PowerShell snap-in code used to register the cmdlet.</span></span> <span data-ttu-id="37465-182">コマンドレットの登録の詳細については、「[コマンドレットのビルド](#defining-the-cmdlet-class)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37465-182">For more information about registering the cmdlet, see [Building the Cmdlet](#defining-the-cmdlet-class).</span></span>

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
    /// a PSPath alias to provide consistency with other cmdlets that use
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
    /// is performed.
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

          // Check if the path represents one of the items to be
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
                // Add the block(line) that did not match to the
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
    /// specified, and not on the exclude list if the exclude list was specified.
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
    /// Specify the description of the PowerShell snap-in.
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

## <a name="building-the-cmdlet"></a><span data-ttu-id="37465-183">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="37465-183">Building the Cmdlet</span></span>

<span data-ttu-id="37465-184">コマンドレットを実装した後、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37465-184">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="37465-185">コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37465-185">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="37465-186">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="37465-186">Testing the Cmdlet</span></span>

<span data-ttu-id="37465-187">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="37465-187">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="37465-188">次の手順は、サンプルの Select-Str コマンドレットをテストするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="37465-188">The following procedure can be used to test the sample Select-Str cmdlet.</span></span>

1. <span data-ttu-id="37465-189">Windows PowerShell を起動し、".NET" という式が含まれている行を検索します。</span><span class="sxs-lookup"><span data-stu-id="37465-189">Start Windows PowerShell, and search the Notes file for occurrences of lines with the expression ".NET".</span></span> <span data-ttu-id="37465-190">パスが複数の単語で構成されている場合にのみ、パス名を引用符で囲む必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="37465-190">Note that the quotation marks around the name of the path are required only if the path consists of more than one word.</span></span>

    ```powershell
    select-str -Path "notes" -Pattern ".NET" -SimpleMatch=$false
    ```

    <span data-ttu-id="37465-191">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37465-191">The following output appears.</span></span>

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

2. <span data-ttu-id="37465-192">メモファイルで、"over" という単語が続き、その後に他のテキストが含まれている行を検索します。</span><span class="sxs-lookup"><span data-stu-id="37465-192">Search the Notes file for occurrences of lines with the word "over", followed by any other text.</span></span> <span data-ttu-id="37465-193">パラメーターは、 `SimpleMatch` の既定値を使用し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="37465-193">The `SimpleMatch` parameter is using the default value of `false`.</span></span> <span data-ttu-id="37465-194">`CaseSensitive`パラメーターがに設定されているため、検索では大文字と小文字が区別され `false` ません。</span><span class="sxs-lookup"><span data-stu-id="37465-194">The search is case-insensitive because the `CaseSensitive` parameter is set to `false`.</span></span>

    ```powershell
    select-str -Path notes -Pattern "over*" -SimpleMatch -CaseSensitive:$false
    ```

    <span data-ttu-id="37465-195">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37465-195">The following output appears.</span></span>

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

3. <span data-ttu-id="37465-196">パターンとして正規表現を使用して、メモファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="37465-196">Search the Notes file using a regular expression as the pattern.</span></span> <span data-ttu-id="37465-197">コマンドレットでは、かっこで囲まれた英文字と空白文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="37465-197">The cmdlet searches for alphabetical characters and blank spaces enclosed in parentheses.</span></span>

    ```powershell
    select-str -Path notes -Pattern "\([A-Za-z:blank:]" -SimpleMatch:$false
    ```

    <span data-ttu-id="37465-198">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37465-198">The following output appears.</span></span>

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

4. <span data-ttu-id="37465-199">"Parameter" という単語が出現する場合に、大文字と小文字を区別してメモファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="37465-199">Perform a case-sensitive search of the Notes file for occurrences of the word "Parameter".</span></span>

    ```powershell
    select-str -Path notes -Pattern Parameter -CaseSensitive
    ```

    <span data-ttu-id="37465-200">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37465-200">The following output appears.</span></span>

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

5. <span data-ttu-id="37465-201">Windows PowerShell に付属している変数プロバイダーで、0 ~ 9 の数値を持つ変数を検索します。</span><span class="sxs-lookup"><span data-stu-id="37465-201">Search the variable provider shipped with Windows PowerShell for variables that have numerical values from 0 through 9.</span></span>

    ```powershell
    select-str -Path * -Pattern "[0-9]"
    ```

    <span data-ttu-id="37465-202">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37465-202">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 1
    Line         : 64
    Path         : Variable:\MaximumHistoryCount
    Pattern      : [0-9]
    ```

6. <span data-ttu-id="37465-203">スクリプトブロックを使用して、ファイル SelectStrCommandSample.cs で文字列 "Pos" を検索します。</span><span class="sxs-lookup"><span data-stu-id="37465-203">Use a script block to search the file SelectStrCommandSample.cs for the string "Pos".</span></span> <span data-ttu-id="37465-204">スクリプトの**cmatch**関数は、大文字と小文字を区別しないパターン一致を実行します。</span><span class="sxs-lookup"><span data-stu-id="37465-204">The **cmatch** function for the script performs a case-insensitive pattern match.</span></span>

    ```powershell
    select-str -Path "SelectStrCommandSample.cs" -Script { if ($args[0] -cmatch "Pos"){ return $true } return $false }
    ```

    <span data-ttu-id="37465-205">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37465-205">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 37
    Line         :    Position = 0.
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\SelectStrCommandSample.cs
    Pattern      :
    ```

## <a name="see-also"></a><span data-ttu-id="37465-206">参照</span><span class="sxs-lookup"><span data-stu-id="37465-206">See Also</span></span>

[<span data-ttu-id="37465-207">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="37465-207">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[<span data-ttu-id="37465-208">最初のコマンドレットの作成</span><span class="sxs-lookup"><span data-stu-id="37465-208">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="37465-209">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="37465-209">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="37465-210">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="37465-210">Design Your Windows PowerShell Provider</span></span>](../prog-guide/designing-your-windows-powershell-provider.md)

<span data-ttu-id="37465-211">[Windows PowerShell の動作](/previous-versions//ms714658(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="37465-211">[How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85))</span></span>

<span data-ttu-id="37465-212">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="37465-212">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="37465-213">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="37465-213">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

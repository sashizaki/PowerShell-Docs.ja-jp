---
ms.date: 09/13/2016
ms.topic: reference
title: エイリアス、ワイルドカード展開、ヘルプをコマンドレット パラメーターに追加する
description: エイリアス、ワイルドカード展開、ヘルプをコマンドレット パラメーターに追加する
ms.openlocfilehash: f0f07796370b4613b1ca0ad17b16c6598bfa438d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660653"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a><span data-ttu-id="a76db-103">エイリアス、ワイルドカード展開、ヘルプをコマンドレット パラメーターに追加する</span><span class="sxs-lookup"><span data-stu-id="a76db-103">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>

<span data-ttu-id="a76db-104">このセクションでは、Stop-Proc コマンドレットのパラメーターにエイリアス、ワイルドカード拡張、およびヘルプメッセージを追加する方法について説明します (「 [システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a76db-104">This section describes how to add aliases, wildcard expansion, and Help messages to the parameters of the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span>

<span data-ttu-id="a76db-105">この Stop-Proc コマンドレットは、Get-Proc コマンドレットを使用して取得されたプロセスを停止しようとします (「 [最初のコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="a76db-105">This Stop-Proc cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="a76db-106">コマンドレットの定義</span><span class="sxs-lookup"><span data-stu-id="a76db-106">Defining the Cmdlet</span></span>

<span data-ttu-id="a76db-107">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a76db-107">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="a76db-108">システムを変更するためのコマンドレットを記述しているので、それに応じた名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76db-108">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="a76db-109">このコマンドレットはシステムプロセスを停止するため、プロセスを示すために "Proc" という名詞を使用して、 [Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) クラスで定義された動詞 "Stop" を使用します。</span><span class="sxs-lookup"><span data-stu-id="a76db-109">Because this cmdlet stops system processes, it uses the verb "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate process.</span></span> <span data-ttu-id="a76db-110">承認されたコマンドレット動詞の詳細については、「 [コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76db-110">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="a76db-111">次のコードは、この Stop-Proc コマンドレットのクラス定義です。</span><span class="sxs-lookup"><span data-stu-id="a76db-111">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="a76db-112">システム変更のパラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="a76db-112">Defining Parameters for System Modification</span></span>

<span data-ttu-id="a76db-113">コマンドレットでは、システムの変更とユーザーフィードバックをサポートするパラメーターを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76db-113">Your cmdlet needs to define parameters that support system modifications and user feedback.</span></span> <span data-ttu-id="a76db-114">コマンドレットでは、 `Name` パラメーターまたは同等のものを定義して、コマンドレットが何らかの種類の識別子でシステムを変更できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76db-114">The cmdlet should define a `Name` parameter or equivalent so that the cmdlet will be able to modify the system by some sort of identifier.</span></span> <span data-ttu-id="a76db-115">さらに、コマンドレットでは、パラメーターとパラメーターを定義する必要があり `Force` `PassThru` ます。</span><span class="sxs-lookup"><span data-stu-id="a76db-115">In addition, the cmdlet should define the `Force` and `PassThru` parameters.</span></span> <span data-ttu-id="a76db-116">これらのパラメーターの詳細については、「 [システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76db-116">For more information about these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="defining-a-parameter-alias"></a><span data-ttu-id="a76db-117">パラメーターの別名の定義</span><span class="sxs-lookup"><span data-stu-id="a76db-117">Defining a Parameter Alias</span></span>

<span data-ttu-id="a76db-118">パラメーターエイリアスは、コマンドレットパラメーターの代替名または適切に定義された1文字または2文字の短い名前にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a76db-118">A parameter alias can be an alternate name or a well-defined 1-letter or 2-letter short name for a cmdlet parameter.</span></span> <span data-ttu-id="a76db-119">どちらの場合も、エイリアスを使用する目的は、コマンドラインからのユーザーエントリを簡略化することです。</span><span class="sxs-lookup"><span data-stu-id="a76db-119">In both cases, the goal of using aliases is to simplify user entry from the command line.</span></span> <span data-ttu-id="a76db-120">Windows PowerShell では、宣言構文 [Alias ()] を使用する、system.string [属性のパラメーター](/dotnet/api/System.Management.Automation.AliasAttribute) エイリアスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a76db-120">Windows PowerShell supports parameter aliases through the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, which uses the declaration syntax [Alias()].</span></span>

<span data-ttu-id="a76db-121">次のコードは、パラメーターにエイリアスを追加する方法を示して `Name` います。</span><span class="sxs-lookup"><span data-stu-id="a76db-121">The following code shows how an alias is added to the `Name` parameter.</span></span>

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
[Alias("ProcessName")]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

<span data-ttu-id="a76db-122">Windows PowerShell ランタイムでは、 [alias 属性を](/dotnet/api/System.Management.Automation.AliasAttribute) 使用するだけでなく、別名が指定されていない場合でも、部分的な名前の一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a76db-122">In addition to using the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, the Windows PowerShell runtime performs partial name matching, even if no aliases are specified.</span></span> <span data-ttu-id="a76db-123">たとえば、コマンドレットにパラメーターがあり、 `FileName` で始まる唯一のパラメーターである場合、 `F` ユーザーは、、、 `Filename` `Filenam` `File` `Fi` 、、またはを入力 `F` しても、パラメーターとしてエントリを認識でき `FileName` ます。</span><span class="sxs-lookup"><span data-stu-id="a76db-123">For example, if your cmdlet has a `FileName` parameter and that is the only parameter that starts with `F`, the user could enter `Filename`, `Filenam`, `File`, `Fi`, or `F` and still recognize the entry as the `FileName` parameter.</span></span>

## <a name="creating-help-for-parameters"></a><span data-ttu-id="a76db-124">パラメーターのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="a76db-124">Creating Help for Parameters</span></span>

<span data-ttu-id="a76db-125">Windows PowerShell では、コマンドレットパラメーターのヘルプを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a76db-125">Windows PowerShell allows you to create Help for cmdlet parameters.</span></span> <span data-ttu-id="a76db-126">この操作は、システムの変更やユーザーフィードバックに使用される任意のパラメーターに対して行います。</span><span class="sxs-lookup"><span data-stu-id="a76db-126">Do this for any parameter used for system modification and user feedback.</span></span> <span data-ttu-id="a76db-127">ヘルプをサポートする各パラメーターに対して、属性キーワードを設定することができます。この属性は、属性 `HelpMessage` 宣言で[](/dotnet/api/System.Management.Automation.ParameterAttribute)指定します。</span><span class="sxs-lookup"><span data-stu-id="a76db-127">For each parameter to support Help, you can set the `HelpMessage` attribute keyword in the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="a76db-128">このキーワードは、パラメーターを使用する際の参考としてユーザーに表示するテキストを定義します。</span><span class="sxs-lookup"><span data-stu-id="a76db-128">This keyword defines the text to display to the user for assistance in using the parameter.</span></span> <span data-ttu-id="a76db-129">また、キーワードを設定して、 `HelpMessageBaseName` メッセージに使用するリソースの基本名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a76db-129">You can also set the `HelpMessageBaseName` keyword to identify the base name of a resource to use for the message.</span></span> <span data-ttu-id="a76db-130">このキーワードを設定する場合は、 `HelpMessageResourceId` リソース識別子を指定するようにキーワードも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76db-130">If you set this keyword, you must also set the `HelpMessageResourceId` keyword to specify the resource identifier.</span></span>

<span data-ttu-id="a76db-131">この Stop-Proc コマンドレットの次のコードは、 `HelpMessage` パラメーターの属性キーワードを定義し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="a76db-131">The following code from this Stop-Proc cmdlet defines the `HelpMessage` attribute keyword for the `Name` parameter.</span></span>

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="a76db-132">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="a76db-132">Overriding an Input Processing Method</span></span>

<span data-ttu-id="a76db-133">コマンドレットでは、入力処理メソッドをオーバーライドする必要があります。これは、ほとんどの場合、このコマンド [レット](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a76db-133">Your cmdlet must override an input processing method, most often this will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="a76db-134">システムを変更する場合、コマンドレットは、変更を加える前にユーザーがフィードバックを提供できるようにするために、コマンドレットに[よってメソッド](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を呼び出す必要があり[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="a76db-134">When modifying the system, the cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to allow the user to provide feedback before a change is made.</span></span> <span data-ttu-id="a76db-135">これらの方法の詳細については、「 [システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76db-135">For more information about these methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="supporting-wildcard-expansion"></a><span data-ttu-id="a76db-136">ワイルドカード拡張のサポート</span><span class="sxs-lookup"><span data-stu-id="a76db-136">Supporting Wildcard Expansion</span></span>

<span data-ttu-id="a76db-137">複数のオブジェクトを選択できるようにするには、コマンドレットで [Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) クラスと [Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) クラスを使用して、パラメーター入力のワイルドカード拡張サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="a76db-137">To allow the selection of multiple objects, your cmdlet can use the [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) and [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes to provide wildcard expansion support for parameter input.</span></span> <span data-ttu-id="a76db-138">ワイルドカードパターンの例としては、lsa \*、 \* .txt、および [a-c] が \* あります。</span><span class="sxs-lookup"><span data-stu-id="a76db-138">Examples of wildcard patterns are lsa\*, \*.txt, and [a-c]\*.</span></span> <span data-ttu-id="a76db-139">パターンに文字どおりに使用する必要がある文字が含まれている場合は、二重引用符文字 (') をエスケープ文字として使用します。</span><span class="sxs-lookup"><span data-stu-id="a76db-139">Use the back-quote character (\`) as an escape character when the pattern contains a character that should be used literally.</span></span>

<span data-ttu-id="a76db-140">ファイル名とパス名のワイルドカードによる展開は、複数のオブジェクトを選択する必要がある場合に、コマンドレットでパス入力のサポートを許可する一般的なシナリオの例です。</span><span class="sxs-lookup"><span data-stu-id="a76db-140">Wildcard expansions of file and path names are examples of common scenarios where the cmdlet may want to allow support for path inputs when the selection of multiple objects is required.</span></span> <span data-ttu-id="a76db-141">通常、ファイルシステムには、現在のフォルダーに存在するすべてのファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76db-141">A common case is in the file system, where a user wants to see all files residing in the current folder.</span></span>

<span data-ttu-id="a76db-142">カスタマイズされたワイルドカードパターン一致の実装が必要になることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="a76db-142">You should need a customized wildcard pattern matching implementation only rarely.</span></span> <span data-ttu-id="a76db-143">この場合、コマンドレットは、完全な POSIX 1003.2、3.13 のワイルドカードの展開、または次の簡略化されたサブセットのいずれかをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76db-143">In this case, your cmdlet should support either the full POSIX 1003.2, 3.13 specification for wildcard expansion or the following simplified subset:</span></span>

- <span data-ttu-id="a76db-144">**疑問符 (?)。**</span><span class="sxs-lookup"><span data-stu-id="a76db-144">**Question mark (?).**</span></span> <span data-ttu-id="a76db-145">指定した位置にある任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="a76db-145">Matches any character at the specified location.</span></span>

- <span data-ttu-id="a76db-146">**アスタリスク ( \* )。**</span><span class="sxs-lookup"><span data-stu-id="a76db-146">**Asterisk (\*).**</span></span> <span data-ttu-id="a76db-147">指定した位置から始まる0個以上の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="a76db-147">Matches zero or more characters starting at the specified location.</span></span>

- <span data-ttu-id="a76db-148">**角かっこ ([) を開きます。**</span><span class="sxs-lookup"><span data-stu-id="a76db-148">**Open bracket ([).**</span></span> <span data-ttu-id="a76db-149">文字または文字の範囲を含めることができるパターン角かっこ式を導入します。</span><span class="sxs-lookup"><span data-stu-id="a76db-149">Introduces a pattern bracket expression that can contain characters or a range of characters.</span></span> <span data-ttu-id="a76db-150">範囲が必要な場合は、範囲を示すためにハイフン (-) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a76db-150">If a range is required, a hyphen (-) is used to indicate the range.</span></span>

- <span data-ttu-id="a76db-151">**閉じかっこ (])。**</span><span class="sxs-lookup"><span data-stu-id="a76db-151">**Close bracket (]).**</span></span> <span data-ttu-id="a76db-152">パターン角かっこ表現を終了します。</span><span class="sxs-lookup"><span data-stu-id="a76db-152">Ends a pattern bracket expression.</span></span>

- <span data-ttu-id="a76db-153">**バッククォートエスケープ文字 (')。**</span><span class="sxs-lookup"><span data-stu-id="a76db-153">**Back-quote escape character (\`).**</span></span> <span data-ttu-id="a76db-154">次の文字を文字どおりに取得する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="a76db-154">Indicates that the next character should be taken literally.</span></span> <span data-ttu-id="a76db-155">プログラムによって指定するのではなく、コマンドラインからバッククォート文字を指定する場合は、バッククォートのエスケープ文字を2回指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a76db-155">Be aware that when specifying the back-quote character from the command line (as opposed to specifying it programmatically), the back-quote escape character must be specified twice.</span></span>

> [!NOTE]
> <span data-ttu-id="a76db-156">ワイルドカードパターンの詳細については、「 [コマンドレットパラメーターでのワイルドカードのサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76db-156">For more information about wildcard patterns, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span></span>

<span data-ttu-id="a76db-157">次のコードは、ワイルドカードオプションを設定し、このコマンドレットのパラメーターの解決に使用するワイルドカードパターンを定義する方法を示して `Name` います。</span><span class="sxs-lookup"><span data-stu-id="a76db-157">The following code shows how to set wildcard options and define the wildcard pattern used for resolving the `Name` parameter for this cmdlet.</span></span>

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

<span data-ttu-id="a76db-158">次のコードは、プロセス名が定義されたワイルドカードパターンに一致するかどうかをテストする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a76db-158">The following code shows how to test whether the process name matches the defined wildcard pattern.</span></span> <span data-ttu-id="a76db-159">この場合、プロセス名がパターンと一致しない場合、コマンドレットは次のプロセス名を取得し続けます。</span><span class="sxs-lookup"><span data-stu-id="a76db-159">Notice that, in this case, if the process name does not match the pattern, the cmdlet continues on to get the next process name.</span></span>

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a><span data-ttu-id="a76db-160">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="a76db-160">Code Sample</span></span>

<span data-ttu-id="a76db-161">完全な C# サンプルコードについては、「 [StopProcessSample03 sample](./stopprocesssample03-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76db-161">For the complete C# sample code, see [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="a76db-162">オブジェクトの種類と書式を定義する</span><span class="sxs-lookup"><span data-stu-id="a76db-162">Define Object Types and Formatting</span></span>

<span data-ttu-id="a76db-163">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="a76db-163">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="a76db-164">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a76db-164">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="a76db-165">新しい型を定義する、または既存の型を拡張する方法の詳細については、「 [オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76db-165">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="a76db-166">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="a76db-166">Building the Cmdlet</span></span>

<span data-ttu-id="a76db-167">コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76db-167">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="a76db-168">コマンドレットの登録の詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76db-168">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="a76db-169">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="a76db-169">Testing the Cmdlet</span></span>

<span data-ttu-id="a76db-170">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="a76db-170">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="a76db-171">サンプル Stop-Proc コマンドレットをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="a76db-171">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="a76db-172">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76db-172">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="a76db-173">Windows PowerShell を起動し、Stop-Proc を使用して、パラメーターの ProcessName エイリアスを使用してプロセスを停止し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="a76db-173">Start Windows PowerShell and use Stop-Proc to stop a process using the ProcessName alias for the `Name` parameter.</span></span>

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

    <span data-ttu-id="a76db-174">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76db-174">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="a76db-175">コマンドラインで次のエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a76db-175">Make the following entry on the command line.</span></span> <span data-ttu-id="a76db-176">Name パラメーターは必須であるため、入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="a76db-176">Because the Name parameter is mandatory, you are prompted for it.</span></span> <span data-ttu-id="a76db-177">「!?」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a76db-177">Entering "!?"</span></span> <span data-ttu-id="a76db-178">パラメーターに関連付けられたヘルプテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="a76db-178">brings up the help text associated with the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

    <span data-ttu-id="a76db-179">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76db-179">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- <span data-ttu-id="a76db-180">ここで、ワイルドカードパターン "\* note" に一致するすべてのプロセスを停止するには、次のエントリを作成し \* ます。</span><span class="sxs-lookup"><span data-stu-id="a76db-180">Now make the following entry to stop all processes that match the wildcard pattern "\*note\*".</span></span> <span data-ttu-id="a76db-181">パターンに一致する各プロセスを停止する前に、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76db-181">You are prompted before stopping each process that matches the pattern.</span></span>

    ```powershell
    PS> stop-proc -Name *note*
    ```

    <span data-ttu-id="a76db-182">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76db-182">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

    <span data-ttu-id="a76db-183">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76db-183">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

    <span data-ttu-id="a76db-184">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76db-184">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="a76db-185">参照</span><span class="sxs-lookup"><span data-stu-id="a76db-185">See Also</span></span>

[<span data-ttu-id="a76db-186">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="a76db-186">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="a76db-187">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="a76db-187">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="a76db-188">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="a76db-188">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="a76db-189">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="a76db-189">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="a76db-190">コマンドレットパラメーターでのワイルドカードのサポート</span><span class="sxs-lookup"><span data-stu-id="a76db-190">Supporting Wildcards in Cmdlet Parameters</span></span>](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[<span data-ttu-id="a76db-191">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="a76db-191">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

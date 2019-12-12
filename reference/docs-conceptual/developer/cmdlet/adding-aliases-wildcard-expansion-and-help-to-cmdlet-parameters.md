---
title: エイリアス、ワイルドカードの展開、およびコマンドレットパラメーターへのヘルプの追加Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 931ccace-c565-4a98-8dcc-df00f86394b1
caps.latest.revision: 8
ms.openlocfilehash: d210a852a90d94df2ab360dd86f0b83a396330e3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74415648"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a><span data-ttu-id="e1a5b-102">エイリアス、ワイルドカード展開、ヘルプをコマンドレット パラメーターに追加する</span><span class="sxs-lookup"><span data-stu-id="e1a5b-102">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>

<span data-ttu-id="e1a5b-103">ここでは、Stop-Proc コマンドレットのパラメーターにエイリアス、ワイルドカード拡張、およびヘルプメッセージを追加する方法について説明します (「[システムを変更するコマンドレットの作成](./creating-a-cmdlet-that-modifies-the-system.md)」で説明)。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-103">This section describes how to add aliases, wildcard expansion, and Help messages to the parameters of the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span>

<span data-ttu-id="e1a5b-104">この Stop Proc コマンドレットは、Get Proc コマンドレットを使用して取得されたプロセスを停止しようとします (「[最初のコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-104">This Stop-Proc cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="e1a5b-105">コマンドレットの定義</span><span class="sxs-lookup"><span data-stu-id="e1a5b-105">Defining the Cmdlet</span></span>

<span data-ttu-id="e1a5b-106">コマンドレットの作成の最初の手順では、常にコマンドレットに名前を付け、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-106">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="e1a5b-107">システムを変更するためのコマンドレットを記述しているので、それに応じた名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-107">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="e1a5b-108">このコマンドレットはシステムプロセスを停止するため、プロセスを示すために "Proc" という名詞を使用して、 [Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスで定義された動詞 "Stop" を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-108">Because this cmdlet stops system processes, it uses the verb "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate process.</span></span> <span data-ttu-id="e1a5b-109">承認されたコマンドレット動詞の詳細については、「[コマンドレットの動詞名](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-109">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="e1a5b-110">次のコードは、この Stop Proc コマンドレットのクラス定義です。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-110">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="e1a5b-111">システム変更のパラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="e1a5b-111">Defining Parameters for System Modification</span></span>

<span data-ttu-id="e1a5b-112">コマンドレットでは、システムの変更とユーザーフィードバックをサポートするパラメーターを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-112">Your cmdlet needs to define parameters that support system modifications and user feedback.</span></span> <span data-ttu-id="e1a5b-113">コマンドレットでは、`Name` パラメーターまたはそれと同等のものを定義して、コマンドレットが何らかの種類の識別子でシステムを変更できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-113">The cmdlet should define a `Name` parameter or equivalent so that the cmdlet will be able to modify the system by some sort of identifier.</span></span> <span data-ttu-id="e1a5b-114">さらに、コマンドレットでは、`Force` パラメーターと `PassThru` パラメーターを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-114">In addition, the cmdlet should define the `Force` and `PassThru` parameters.</span></span> <span data-ttu-id="e1a5b-115">これらのパラメーターの詳細については、「[システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-115">For more information about these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="defining-a-parameter-alias"></a><span data-ttu-id="e1a5b-116">パラメーターの別名の定義</span><span class="sxs-lookup"><span data-stu-id="e1a5b-116">Defining a Parameter Alias</span></span>

<span data-ttu-id="e1a5b-117">パラメーターエイリアスは、コマンドレットパラメーターの代替名または適切に定義された1文字または2文字の短い名前にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-117">A parameter alias can be an alternate name or a well-defined 1-letter or 2-letter short name for a cmdlet parameter.</span></span> <span data-ttu-id="e1a5b-118">どちらの場合も、エイリアスを使用する目的は、コマンドラインからのユーザーエントリを簡略化することです。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-118">In both cases, the goal of using aliases is to simplify user entry from the command line.</span></span> <span data-ttu-id="e1a5b-119">Windows PowerShell では、宣言構文 [Alias ()] を使用する、system.string[属性のパラメーター](/dotnet/api/System.Management.Automation.AliasAttribute)エイリアスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-119">Windows PowerShell supports parameter aliases through the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, which uses the declaration syntax [Alias()].</span></span>

<span data-ttu-id="e1a5b-120">次のコードは、`Name` パラメーターにエイリアスを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-120">The following code shows how an alias is added to the `Name` parameter.</span></span>

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

<span data-ttu-id="e1a5b-121">Windows PowerShell ランタイムでは、 [alias 属性を](/dotnet/api/System.Management.Automation.AliasAttribute)使用するだけでなく、別名が指定されていない場合でも、部分的な名前の一致が実行されます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-121">In addition to using the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, the Windows PowerShell runtime performs partial name matching, even if no aliases are specified.</span></span> <span data-ttu-id="e1a5b-122">たとえば、コマンドレットに `FileName` パラメーターがあり、それが `F`で始まる唯一のパラメーターである場合、ユーザーは `Filename`、`Filenam`、`File`、`Fi`、`F` を入力しても、エントリを `FileName` パラメーターとして認識できます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-122">For example, if your cmdlet has a `FileName` parameter and that is the only parameter that starts with `F`, the user could enter `Filename`, `Filenam`, `File`, `Fi`, or `F` and still recognize the entry as the `FileName` parameter.</span></span>

## <a name="creating-help-for-parameters"></a><span data-ttu-id="e1a5b-123">パラメーターのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="e1a5b-123">Creating Help for Parameters</span></span>

<span data-ttu-id="e1a5b-124">Windows PowerShell では、コマンドレットパラメーターのヘルプを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-124">Windows PowerShell allows you to create Help for cmdlet parameters.</span></span> <span data-ttu-id="e1a5b-125">この操作は、システムの変更やユーザーフィードバックに使用される任意のパラメーターに対して行います。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-125">Do this for any parameter used for system modification and user feedback.</span></span> <span data-ttu-id="e1a5b-126">ヘルプをサポートする各パラメーターに対して、`HelpMessage` attribute キーワード[を、この](/dotnet/api/System.Management.Automation.ParameterAttribute)属性宣言で設定できます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-126">For each parameter to support Help, you can set the `HelpMessage` attribute keyword in the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="e1a5b-127">このキーワードは、パラメーターを使用する際の参考としてユーザーに表示するテキストを定義します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-127">This keyword defines the text to display to the user for assistance in using the parameter.</span></span> <span data-ttu-id="e1a5b-128">また、`HelpMessageBaseName` キーワードを設定して、メッセージに使用するリソースの基本名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-128">You can also set the `HelpMessageBaseName` keyword to identify the base name of a resource to use for the message.</span></span> <span data-ttu-id="e1a5b-129">このキーワードを設定する場合は、`HelpMessageResourceId` キーワードを設定してリソース識別子を指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-129">If you set this keyword, you must also set the `HelpMessageResourceId` keyword to specify the resource identifier.</span></span>

<span data-ttu-id="e1a5b-130">この Stop Proc コマンドレットの次のコードは、`Name` パラメーターの `HelpMessage` attribute キーワードを定義します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-130">The following code from this Stop-Proc cmdlet defines the `HelpMessage` attribute keyword for the `Name` parameter.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="e1a5b-131">入力処理メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="e1a5b-131">Overriding an Input Processing Method</span></span>

<span data-ttu-id="e1a5b-132">コマンドレットでは、入力処理メソッドをオーバーライドする必要があります。これは、ほとんどの場合、このコマンド[レット](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-132">Your cmdlet must override an input processing method, most often this will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="e1a5b-133">システムを変更する場合、コマンドレットは、変更を加える前にユーザーがフィードバックを提供できるようにするために、コマンドレットに[よってメソッド](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)を呼び出す必要があり[ます。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="e1a5b-133">When modifying the system, the cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to allow the user to provide feedback before a change is made.</span></span> <span data-ttu-id="e1a5b-134">これらの方法の詳細については、「[システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-134">For more information about these methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="supporting-wildcard-expansion"></a><span data-ttu-id="e1a5b-135">ワイルドカード拡張のサポート</span><span class="sxs-lookup"><span data-stu-id="e1a5b-135">Supporting Wildcard Expansion</span></span>

<span data-ttu-id="e1a5b-136">複数のオブジェクトを選択できるようにするには、コマンドレットで[Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern)クラスと[Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions)クラスを使用して、パラメーター入力のワイルドカード拡張サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-136">To allow the selection of multiple objects, your cmdlet can use the [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) and [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes to provide wildcard expansion support for parameter input.</span></span> <span data-ttu-id="e1a5b-137">ワイルドカードパターンの例としては、lsa \*、\*.txt、および [a-c]\*があります。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-137">Examples of wildcard patterns are lsa\*, \*.txt, and [a-c]\*.</span></span> <span data-ttu-id="e1a5b-138">パターンに文字どおりに使用する必要がある文字が含まれている場合は、二重引用符文字 (') をエスケープ文字として使用します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-138">Use the back-quote character (\`) as an escape character when the pattern contains a character that should be used literally.</span></span>

<span data-ttu-id="e1a5b-139">ファイル名とパス名のワイルドカードによる展開は、複数のオブジェクトを選択する必要がある場合に、コマンドレットでパス入力のサポートを許可する一般的なシナリオの例です。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-139">Wildcard expansions of file and path names are examples of common scenarios where the cmdlet may want to allow support for path inputs when the selection of multiple objects is required.</span></span> <span data-ttu-id="e1a5b-140">通常、ファイルシステムには、現在のフォルダーに存在するすべてのファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-140">A common case is in the file system, where a user wants to see all files residing in the current folder.</span></span>

<span data-ttu-id="e1a5b-141">カスタマイズされたワイルドカードパターン一致の実装が必要になることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-141">You should need a customized wildcard pattern matching implementation only rarely.</span></span> <span data-ttu-id="e1a5b-142">この場合、コマンドレットは、完全な POSIX 1003.2、3.13 のワイルドカードの展開、または次の簡略化されたサブセットのいずれかをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-142">In this case, your cmdlet should support either the full POSIX 1003.2, 3.13 specification for wildcard expansion or the following simplified subset:</span></span>

- <span data-ttu-id="e1a5b-143">**疑問符 (?)。**</span><span class="sxs-lookup"><span data-stu-id="e1a5b-143">**Question mark (?).**</span></span> <span data-ttu-id="e1a5b-144">指定した位置にある任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-144">Matches any character at the specified location.</span></span>

- <span data-ttu-id="e1a5b-145">**アスタリスク (\*)。**</span><span class="sxs-lookup"><span data-stu-id="e1a5b-145">**Asterisk (\*).**</span></span> <span data-ttu-id="e1a5b-146">指定した位置から始まる0個以上の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-146">Matches zero or more characters starting at the specified location.</span></span>

- <span data-ttu-id="e1a5b-147">**角かっこ ([) を開きます。**</span><span class="sxs-lookup"><span data-stu-id="e1a5b-147">**Open bracket ([).**</span></span> <span data-ttu-id="e1a5b-148">文字または文字の範囲を含めることができるパターン角かっこ式を導入します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-148">Introduces a pattern bracket expression that can contain characters or a range of characters.</span></span> <span data-ttu-id="e1a5b-149">範囲が必要な場合は、範囲を示すためにハイフン (-) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-149">If a range is required, a hyphen (-) is used to indicate the range.</span></span>

- <span data-ttu-id="e1a5b-150">**閉じかっこ (])。**</span><span class="sxs-lookup"><span data-stu-id="e1a5b-150">**Close bracket (]).**</span></span> <span data-ttu-id="e1a5b-151">パターン角かっこ表現を終了します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-151">Ends a pattern bracket expression.</span></span>

- <span data-ttu-id="e1a5b-152">**バッククォートエスケープ文字 (')。**</span><span class="sxs-lookup"><span data-stu-id="e1a5b-152">**Back-quote escape character (\`).**</span></span> <span data-ttu-id="e1a5b-153">次の文字を文字どおりに取得する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-153">Indicates that the next character should be taken literally.</span></span> <span data-ttu-id="e1a5b-154">プログラムによって指定するのではなく、コマンドラインからバッククォート文字を指定する場合は、バッククォートのエスケープ文字を2回指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-154">Be aware that when specifying the back-quote character from the command line (as opposed to specifying it programmatically), the back-quote escape character must be specified twice.</span></span>

> [!NOTE]
> <span data-ttu-id="e1a5b-155">ワイルドカードパターンの詳細については、「[コマンドレットパラメーターでのワイルドカードのサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-155">For more information about wildcard patterns, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span></span>

<span data-ttu-id="e1a5b-156">次のコードは、ワイルドカードオプションを設定し、このコマンドレットの `Name` パラメーターの解決に使用するワイルドカードパターンを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-156">The following code shows how to set wildcard options and define the wildcard pattern used for resolving the `Name` parameter for this cmdlet.</span></span>

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

<span data-ttu-id="e1a5b-157">次のコードは、プロセス名が定義されたワイルドカードパターンに一致するかどうかをテストする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-157">The following code shows how to test whether the process name matches the defined wildcard pattern.</span></span> <span data-ttu-id="e1a5b-158">この場合、プロセス名がパターンと一致しない場合、コマンドレットは次のプロセス名を取得し続けます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-158">Notice that, in this case, if the process name does not match the pattern, the cmdlet continues on to get the next process name.</span></span>

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a><span data-ttu-id="e1a5b-159">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="e1a5b-159">Code Sample</span></span>

<span data-ttu-id="e1a5b-160">完全なC#サンプルコードについては、「 [StopProcessSample03 sample](./stopprocesssample03-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-160">For the complete C# sample code, see [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="e1a5b-161">オブジェクトの種類と書式を定義する</span><span class="sxs-lookup"><span data-stu-id="e1a5b-161">Define Object Types and Formatting</span></span>

<span data-ttu-id="e1a5b-162">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-162">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="e1a5b-163">そのため、コマンドレットで独自の型を定義する必要がある場合や、コマンドレットで別のコマンドレットによって提供される既存の型を拡張する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-163">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="e1a5b-164">新しい型を定義する、または既存の型を拡張する方法の詳細については、「[オブジェクトの型と書式設定の拡張](/previous-versions//ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-164">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="e1a5b-165">コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="e1a5b-165">Building the Cmdlet</span></span>

<span data-ttu-id="e1a5b-166">コマンドレットを実装した後は、Windows powershell スナップインを使用して Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-166">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="e1a5b-167">コマンドレットの登録の詳細については、「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-167">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="e1a5b-168">コマンドレットのテスト</span><span class="sxs-lookup"><span data-stu-id="e1a5b-168">Testing the Cmdlet</span></span>

<span data-ttu-id="e1a5b-169">コマンドレットが Windows PowerShell に登録されている場合は、コマンドラインで実行することでテストできます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-169">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="e1a5b-170">Stop-Proc コマンドレットのサンプルをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-170">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="e1a5b-171">コマンドラインからコマンドレットを使用する方法の詳細については、「 [Windows PowerShell を使用したはじめに](/powershell/scripting/getting-started/getting-started-with-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-171">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="e1a5b-172">Windows PowerShell を起動し、`Name` パラメーターの ProcessName エイリアスを使用してプロセスを停止するには、Stop Proc を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-172">Start Windows PowerShell and use Stop-Proc to stop a process using the ProcessName alias for the `Name` parameter.</span></span>

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

<span data-ttu-id="e1a5b-173">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-173">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="e1a5b-174">コマンドラインで次のエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-174">Make the following entry on the command line.</span></span> <span data-ttu-id="e1a5b-175">Name パラメーターは必須であるため、入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-175">Because the Name parameter is mandatory, you are prompted for it.</span></span> <span data-ttu-id="e1a5b-176">「!?」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-176">Entering "!?"</span></span> <span data-ttu-id="e1a5b-177">パラメーターに関連付けられたヘルプテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-177">brings up the help text associated with the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

<span data-ttu-id="e1a5b-178">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-178">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- <span data-ttu-id="e1a5b-179">ここで、次のエントリを作成して、ワイルドカードパターン "\* note\*" に一致するすべてのプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-179">Now make the following entry to stop all processes that match the wildcard pattern "\*note\*".</span></span> <span data-ttu-id="e1a5b-180">パターンに一致する各プロセスを停止する前に、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-180">You are prompted before stopping each process that matches the pattern.</span></span>

    ```powershell
    PS> stop-proc -Name *note*
    ```

<span data-ttu-id="e1a5b-181">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-181">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

<span data-ttu-id="e1a5b-182">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-182">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

<span data-ttu-id="e1a5b-183">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1a5b-183">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="e1a5b-184">参照</span><span class="sxs-lookup"><span data-stu-id="e1a5b-184">See Also</span></span>

[<span data-ttu-id="e1a5b-185">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="e1a5b-185">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="e1a5b-186">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e1a5b-186">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="e1a5b-187">[オブジェクトの種類と書式設定の拡張](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e1a5b-187">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="e1a5b-188">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e1a5b-188">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="e1a5b-189">コマンドレットパラメーターでのワイルドカードのサポート</span><span class="sxs-lookup"><span data-stu-id="e1a5b-189">Supporting Wildcards in Cmdlet Parameters</span></span>](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[<span data-ttu-id="e1a5b-190">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="e1a5b-190">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

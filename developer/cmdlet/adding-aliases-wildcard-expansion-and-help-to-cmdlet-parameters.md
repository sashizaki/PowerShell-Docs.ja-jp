---
title: ワイルドカードの展開のエイリアスを追加し、コマンドレットのパラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 931ccace-c565-4a98-8dcc-df00f86394b1
caps.latest.revision: 8
ms.openlocfilehash: bc921537062e35aa203fa3ee95d3b7211c89cb28
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67733852"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a><span data-ttu-id="dc791-102">エイリアス、ワイルドカード展開、ヘルプをコマンドレット パラメーターに追加する</span><span class="sxs-lookup"><span data-stu-id="dc791-102">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>

<span data-ttu-id="dc791-103">エイリアス、ワイルドカードの展開を追加する方法について説明およびヘルプ メッセージの停止 Proc コマンドレットのパラメーター (で説明されている[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md))。</span><span class="sxs-lookup"><span data-stu-id="dc791-103">This section describes how to add aliases, wildcard expansion, and Help messages to the parameters of the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span>

<span data-ttu-id="dc791-104">この停止 Proc コマンドレットは Get-proc コマンドレットを使用して取得するプロセスを停止しようとしました。 (で説明されている[最初のコマンドレットを、作成](./creating-a-cmdlet-without-parameters.md))。</span><span class="sxs-lookup"><span data-stu-id="dc791-104">This Stop-Proc cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="dc791-105">コマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="dc791-105">Defining the Cmdlet</span></span>

<span data-ttu-id="dc791-106">コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="dc791-106">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="dc791-107">システムを変更するコマンドレットを記述するため、それに応じて名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc791-107">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="dc791-108">このコマンドレットは、システム プロセスを停止、ために、"Stop"で定義されている、動詞を使用、 [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスの名詞をプロセスを示すために"Proc"とします。</span><span class="sxs-lookup"><span data-stu-id="dc791-108">Because this cmdlet stops system processes, it uses the verb "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate process.</span></span> <span data-ttu-id="dc791-109">承認されたコマンドレット動詞の詳細については、次を参照してください。[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc791-109">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="dc791-110">次のコードは、このコマンドレットで停止 Proc クラス定義です。</span><span class="sxs-lookup"><span data-stu-id="dc791-110">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="dc791-111">システムの変更のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="dc791-111">Defining Parameters for System Modification</span></span>

<span data-ttu-id="dc791-112">コマンドレットは、そのサポート システムの変更やユーザー フィードバック パラメーターを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc791-112">Your cmdlet needs to define parameters that support system modifications and user feedback.</span></span> <span data-ttu-id="dc791-113">コマンドレットを定義する必要があります、`Name`パラメーターまたはそれと同等、コマンドレットは、システムに何らかの識別子を変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dc791-113">The cmdlet should define a `Name` parameter or equivalent so that the cmdlet will be able to modify the system by some sort of identifier.</span></span> <span data-ttu-id="dc791-114">また、コマンドレットを定義する必要があります、`Force`と`PassThru`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dc791-114">In addition, the cmdlet should define the `Force` and `PassThru` parameters.</span></span> <span data-ttu-id="dc791-115">これらのパラメーターの詳細については、次を参照してください。[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc791-115">For more information about these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="defining-a-parameter-alias"></a><span data-ttu-id="dc791-116">パラメーター エイリアスを定義します。</span><span class="sxs-lookup"><span data-stu-id="dc791-116">Defining a Parameter Alias</span></span>

<span data-ttu-id="dc791-117">パラメーター エイリアスには代替名またはコマンドレット パラメーターの適切に定義された 1 文字または 2 文字短い名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc791-117">A parameter alias can be an alternate name or a well-defined 1-letter or 2-letter short name for a cmdlet parameter.</span></span> <span data-ttu-id="dc791-118">どちらの場合も、エイリアスを使用する目的は、コマンドラインからのユーザー入力を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="dc791-118">In both cases, the goal of using aliases is to simplify user entry from the command line.</span></span> <span data-ttu-id="dc791-119">Windows PowerShell からのパラメーターのエイリアスをサポートしている、 [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute)属性には、宣言の構文 [Alias()] を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc791-119">Windows PowerShell supports parameter aliases through the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, which uses the declaration syntax [Alias()].</span></span>

<span data-ttu-id="dc791-120">次のコードにエイリアスを追加する方法を示しています、`Name`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dc791-120">The following code shows how an alias is added to the `Name` parameter.</span></span>

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

<span data-ttu-id="dc791-121">使用するだけでなく、 [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute)属性、Windows PowerShell ランタイムによって実行される部分的な名前が一致する別名が指定されていない場合でもです。</span><span class="sxs-lookup"><span data-stu-id="dc791-121">In addition to using the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, the Windows PowerShell runtime performs partial name matching, even if no aliases are specified.</span></span> <span data-ttu-id="dc791-122">たとえば、次のコマンドレットがある、`FileName`パラメーターとは、唯一のパラメーターで始まる`F`、ユーザーが入力`Filename`、 `Filenam`、 `File`、 `Fi`、または`F`も認識し、エントリとして、`FileName`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dc791-122">For example, if your cmdlet has a `FileName` parameter and that is the only parameter that starts with `F`, the user could enter `Filename`, `Filenam`, `File`, `Fi`, or `F` and still recognize the entry as the `FileName` parameter.</span></span>

## <a name="creating-help-for-parameters"></a><span data-ttu-id="dc791-123">パラメーターのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="dc791-123">Creating Help for Parameters</span></span>

<span data-ttu-id="dc791-124">Windows PowerShell コマンドレットのパラメーターのヘルプを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dc791-124">Windows PowerShell allows you to create Help for cmdlet parameters.</span></span> <span data-ttu-id="dc791-125">このシステムの変更とユーザーのフィードバックに使用される任意のパラメーターに対して行います。</span><span class="sxs-lookup"><span data-stu-id="dc791-125">Do this for any parameter used for system modification and user feedback.</span></span> <span data-ttu-id="dc791-126">ヘルプをサポートするには、各パラメーターの設定することができます、`HelpMessage`属性内のキーワード、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性宣言。</span><span class="sxs-lookup"><span data-stu-id="dc791-126">For each parameter to support Help, you can set the `HelpMessage` attribute keyword in the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="dc791-127">このキーワードは、パラメーターを使用してで支援をユーザーに表示するテキストを定義します。</span><span class="sxs-lookup"><span data-stu-id="dc791-127">This keyword defines the text to display to the user for assistance in using the parameter.</span></span> <span data-ttu-id="dc791-128">設定することも、`HelpMessageBaseName`メッセージで使用するリソースのベース名を識別するためにキーワード。</span><span class="sxs-lookup"><span data-stu-id="dc791-128">You can also set the `HelpMessageBaseName` keyword to identify the base name of a resource to use for the message.</span></span> <span data-ttu-id="dc791-129">設定する必要があるこのキーワードを設定した場合、`HelpMessageResourceId`リソース識別子を指定するキーワード。</span><span class="sxs-lookup"><span data-stu-id="dc791-129">If you set this keyword, you must also set the `HelpMessageResourceId` keyword to specify the resource identifier.</span></span>

<span data-ttu-id="dc791-130">この停止 Proc コマンドレットから次のコードを定義、`HelpMessage`属性のキーワード、`Name`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dc791-130">The following code from this Stop-Proc cmdlet defines the `HelpMessage` attribute keyword for the `Name` parameter.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="dc791-131">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="dc791-131">Overriding an Input Processing Method</span></span>

<span data-ttu-id="dc791-132">コマンドレットは、入力処理メソッドをオーバーライドする必要があります、これは最も頻繁になります[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)します。</span><span class="sxs-lookup"><span data-stu-id="dc791-132">Your cmdlet must override an input processing method, most often this will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="dc791-133">コマンドレットを呼び出す必要があります、システムを変更するときに、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ユーザーを許可する方法変更が行われる前に、フィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc791-133">When modifying the system, the cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to allow the user to provide feedback before a change is made.</span></span> <span data-ttu-id="dc791-134">これらのメソッドの詳細については、次を参照してください。[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc791-134">For more information about these methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="supporting-wildcard-expansion"></a><span data-ttu-id="dc791-135">ワイルドカードの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dc791-135">Supporting Wildcard Expansion</span></span>

<span data-ttu-id="dc791-136">複数のオブジェクトの選択を許可する、コマンドレットを使用できます、 [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern)と[System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions)クラスを提供するには入力パラメーターのワイルドカードの拡張サポート。</span><span class="sxs-lookup"><span data-stu-id="dc791-136">To allow the selection of multiple objects, your cmdlet can use the [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) and [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes to provide wildcard expansion support for parameter input.</span></span> <span data-ttu-id="dc791-137">ワイルドカードのパターンの例は、lsa \* \*.txt、および [c]、\*します。</span><span class="sxs-lookup"><span data-stu-id="dc791-137">Examples of wildcard patterns are lsa\*, \*.txt, and [a-c]\*.</span></span> <span data-ttu-id="dc791-138">パターンには、そのまま使用する文字が含まれている場合は、エスケープ文字として逆引用符 (') を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc791-138">Use the back-quote character (\`) as an escape character when the pattern contains a character that should be used literally.</span></span>

<span data-ttu-id="dc791-139">ファイルとパス名のワイルドカードの展開では、コマンドレットは、複数のオブジェクトの選択が必要な場合は、パスの入力のサポートを許可する必要のある一般的なシナリオの例を示します。</span><span class="sxs-lookup"><span data-stu-id="dc791-139">Wildcard expansions of file and path names are examples of common scenarios where the cmdlet may want to allow support for path inputs when the selection of multiple objects is required.</span></span> <span data-ttu-id="dc791-140">一般的なケースが、ユーザーが、現在のフォルダー内に存在するすべてのファイルを表示するが、ファイル システムです。</span><span class="sxs-lookup"><span data-stu-id="dc791-140">A common case is in the file system, where a user wants to see all files residing in the current folder.</span></span>

<span data-ttu-id="dc791-141">まれに、カスタマイズされたワイルドカードのパターン一致の実装を必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc791-141">You should need a customized wildcard pattern matching implementation only rarely.</span></span> <span data-ttu-id="dc791-142">この場合、コマンドレットでは、いずれかの完全な POSIX 1003.2、ワイルドカードの展開の 3.13 仕様または、次の簡略化されたサブセットをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc791-142">In this case, your cmdlet should support either the full POSIX 1003.2, 3.13 specification for wildcard expansion or the following simplified subset:</span></span>

- <span data-ttu-id="dc791-143">**疑問符 (?)。**</span><span class="sxs-lookup"><span data-stu-id="dc791-143">**Question mark (?).**</span></span> <span data-ttu-id="dc791-144">指定した位置に任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="dc791-144">Matches any character at the specified location.</span></span>

- <span data-ttu-id="dc791-145">**アスタリスク (\*)。**</span><span class="sxs-lookup"><span data-stu-id="dc791-145">**Asterisk (\*).**</span></span> <span data-ttu-id="dc791-146">指定した場所から始まる 0 個以上の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="dc791-146">Matches zero or more characters starting at the specified location.</span></span>

- <span data-ttu-id="dc791-147">**角かっこ ([) を開きます。**</span><span class="sxs-lookup"><span data-stu-id="dc791-147">**Open bracket ([).**</span></span> <span data-ttu-id="dc791-148">文字または文字の範囲に格納できるパターンの角かっこ表現が導入されています。</span><span class="sxs-lookup"><span data-stu-id="dc791-148">Introduces a pattern bracket expression that can contain characters or a range of characters.</span></span> <span data-ttu-id="dc791-149">範囲が必要な場合は、ハイフン (-) が、範囲を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc791-149">If a range is required, a hyphen (-) is used to indicate the range.</span></span>

- <span data-ttu-id="dc791-150">**終了の角かっこ (]) です。**</span><span class="sxs-lookup"><span data-stu-id="dc791-150">**Close bracket (]).**</span></span> <span data-ttu-id="dc791-151">パターンの角かっこ表現を終了します。</span><span class="sxs-lookup"><span data-stu-id="dc791-151">Ends a pattern bracket expression.</span></span>

- <span data-ttu-id="dc791-152">**バックアップ-引用符のエスケープ文字 (')。**</span><span class="sxs-lookup"><span data-stu-id="dc791-152">**Back-quote escape character (\`).**</span></span> <span data-ttu-id="dc791-153">次の文字がそのまま使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="dc791-153">Indicates that the next character should be taken literally.</span></span> <span data-ttu-id="dc791-154">(プログラムで指定) ではなくコマンドラインから逆引用符を指定するときに、背面引用符のエスケープ文字が指定することは 2 回あります。</span><span class="sxs-lookup"><span data-stu-id="dc791-154">Be aware that when specifying the back-quote character from the command line (as opposed to specifying it programmatically), the back-quote escape character must be specified twice.</span></span>

> [!NOTE]
> <span data-ttu-id="dc791-155">ワイルドカードのパターンの詳細については、次を参照してください。[コマンドレットのパラメーターにワイルドカードをサポートしている](./supporting-wildcard-characters-in-cmdlet-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc791-155">For more information about wildcard patterns, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span></span>

<span data-ttu-id="dc791-156">次のコードは、ワイルドカードのオプションを設定し、解決するために使用するワイルドカード パターンを定義する方法を示しています、`Name`このコマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="dc791-156">The following code shows how to set wildcard options and define the wildcard pattern used for resolving the `Name` parameter for this cmdlet.</span></span>

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

<span data-ttu-id="dc791-157">次のコードでは、プロセス名が定義されているワイルドカードのパターンと一致するかどうかをテストする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dc791-157">The following code shows how to test whether the process name matches the defined wildcard pattern.</span></span> <span data-ttu-id="dc791-158">、ここでは、プロセス名にパターンが一致しない場合、コマンドレットに続くこと、次のプロセス名を取得することを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc791-158">Notice that, in this case, if the process name does not match the pattern, the cmdlet continues on to get the next process name.</span></span>

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a><span data-ttu-id="dc791-159">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="dc791-159">Code Sample</span></span>

<span data-ttu-id="dc791-160">完全なC#サンプル コードは、「 [StopProcessSample03 サンプル](./stopprocesssample03-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc791-160">For the complete C# sample code, see [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="dc791-161">オブジェクトの種類と書式設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="dc791-161">Define Object Types and Formatting</span></span>

<span data-ttu-id="dc791-162">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="dc791-162">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="dc791-163">その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc791-163">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="dc791-164">新しい型を定義するか、既存の型の拡張の詳細については、次を参照してください。[を拡張するオブジェクトの種類と書式](/previous-versions//ms714665(v=vs.85))します。</span><span class="sxs-lookup"><span data-stu-id="dc791-164">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="dc791-165">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="dc791-165">Building the Cmdlet</span></span>

<span data-ttu-id="dc791-166">コマンドレットを実装するには、後にする必要があります登録する必要が Windows PowerShell を使用した Windows PowerShell スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc791-166">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="dc791-167">コマンドレットの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](/previous-versions//ms714644(v=vs.85))します。</span><span class="sxs-lookup"><span data-stu-id="dc791-167">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="dc791-168">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dc791-168">Testing the Cmdlet</span></span>

<span data-ttu-id="dc791-169">コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="dc791-169">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="dc791-170">サンプルの停止 Proc コマンドレットをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="dc791-170">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="dc791-171">詳細については、コマンドラインからコマンドレットを使用して、次を参照してください。、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="dc791-171">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="dc791-172">Windows PowerShell を起動し、ProcessName エイリアスを使用してプロセスを停止する停止プロシージャを使用して、`Name`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="dc791-172">Start Windows PowerShell and use Stop-Proc to stop a process using the ProcessName alias for the `Name` parameter.</span></span>

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

<span data-ttu-id="dc791-173">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc791-173">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="dc791-174">コマンドラインでは、次のエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc791-174">Make the following entry on the command line.</span></span> <span data-ttu-id="dc791-175">Name パラメーターは必須であるために、そのように求められます。</span><span class="sxs-lookup"><span data-stu-id="dc791-175">Because the Name parameter is mandatory, you are prompted for it.</span></span> <span data-ttu-id="dc791-176">入力"!?"</span><span class="sxs-lookup"><span data-stu-id="dc791-176">Entering "!?"</span></span> <span data-ttu-id="dc791-177">パラメーターに関連付けられているヘルプ テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc791-177">brings up the help text associated with the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

<span data-ttu-id="dc791-178">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc791-178">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- <span data-ttu-id="dc791-179">今すぐワイルドカード パターンに一致するすべてのプロセスを停止する次のエントリを作成する"\* 注\*"。</span><span class="sxs-lookup"><span data-stu-id="dc791-179">Now make the following entry to stop all processes that match the wildcard pattern "\*note\*".</span></span> <span data-ttu-id="dc791-180">各パターンに一致するプロセスを停止する前に求められます。</span><span class="sxs-lookup"><span data-stu-id="dc791-180">You are prompted before stopping each process that matches the pattern.</span></span>

    ```powershell
    PS> stop-proc -Name *note*
    ```

<span data-ttu-id="dc791-181">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc791-181">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

<span data-ttu-id="dc791-182">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc791-182">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

<span data-ttu-id="dc791-183">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc791-183">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="dc791-184">参照</span><span class="sxs-lookup"><span data-stu-id="dc791-184">See Also</span></span>

[<span data-ttu-id="dc791-185">システムを変更するコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc791-185">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="dc791-186">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="dc791-186">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="dc791-187">[オブジェクトの種類を拡張して、書式設定](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="dc791-187">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="dc791-188">[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="dc791-188">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="dc791-189">コマンドレットのパラメーターでのワイルドカードのサポート</span><span class="sxs-lookup"><span data-stu-id="dc791-189">Supporting Wildcards in Cmdlet Parameters</span></span>](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[<span data-ttu-id="dc791-190">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="dc791-190">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

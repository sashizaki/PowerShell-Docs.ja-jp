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
ms.openlocfilehash: db664e589f625855b5a33a02c522d6b238ad2810
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054879"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a><span data-ttu-id="f3e02-102">エイリアス、ワイルドカード展開、ヘルプをコマンドレット パラメーターに追加する</span><span class="sxs-lookup"><span data-stu-id="f3e02-102">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>

<span data-ttu-id="f3e02-103">エイリアス、ワイルドカードの展開を追加する方法について説明およびヘルプ メッセージの停止 Proc コマンドレットのパラメーター (で説明されている[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md))。</span><span class="sxs-lookup"><span data-stu-id="f3e02-103">This section describes how to add aliases, wildcard expansion, and Help messages to the parameters of the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span>

<span data-ttu-id="f3e02-104">この停止 Proc コマンドレットは Get-proc コマンドレットを使用して取得するプロセスを停止しようとしました。 (で説明されている[最初のコマンドレットを、作成](./creating-a-cmdlet-without-parameters.md))。</span><span class="sxs-lookup"><span data-stu-id="f3e02-104">This Stop-Proc cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

<span data-ttu-id="f3e02-105">このセクションのトピックで、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f3e02-105">Topics in this section include the following:</span></span>

- [<span data-ttu-id="f3e02-106">コマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-106">Defining the Cmdlet</span></span>](#Defining-the-Cmdlet)

- [<span data-ttu-id="f3e02-107">システムの変更のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-107">Defining Parameters for System Modification</span></span>](#Defining-Parameters-for-System-Modification)

- [<span data-ttu-id="f3e02-108">パラメーター エイリアスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-108">Defining a Parameter Alias</span></span>](#Defining-a-Parameter-Alias)

- [<span data-ttu-id="f3e02-109">パラメーターのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="f3e02-109">Creating Help for Parameters</span></span>](#Creating-Help-for-Parameters)

- [<span data-ttu-id="f3e02-110">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f3e02-110">Overriding an Input Processing Method</span></span>](#Overriding-an-Input-Processing-Method)

- [<span data-ttu-id="f3e02-111">ワイルドカードの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f3e02-111">Supporting Wildcard Expansion</span></span>](#Supporting-Wildcard-Expansion)

- [<span data-ttu-id="f3e02-112">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="f3e02-112">Code Sample</span></span>](#Defining-a-Parameter-Alias)

- [<span data-ttu-id="f3e02-113">オブジェクトの種類を定義して、書式設定</span><span class="sxs-lookup"><span data-stu-id="f3e02-113">Defining Object Types and Formatting</span></span>](#Define-Object-Types-and-Formatting)

- [<span data-ttu-id="f3e02-114">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="f3e02-114">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="f3e02-115">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f3e02-115">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet"></a><span data-ttu-id="f3e02-116">コマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-116">Defining the Cmdlet</span></span>

<span data-ttu-id="f3e02-117">コマンドレットの作成の最初の手順は常に、コマンドレットの名前を付けると、コマンドレットを実装する .NET クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-117">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="f3e02-118">システムを変更するコマンドレットを記述するため、それに応じて名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3e02-118">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="f3e02-119">このコマンドレットは、システム プロセスを停止、ために、"Stop"で定義されている、動詞を使用、 [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスの名詞をプロセスを示すために"Proc"とします。</span><span class="sxs-lookup"><span data-stu-id="f3e02-119">Because this cmdlet stops system processes, it uses the verb "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate process.</span></span> <span data-ttu-id="f3e02-120">承認されたコマンドレット動詞の詳細については、[コマンドレット動詞名](./approved-verbs-for-windows-powershell-commands.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3e02-120">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="f3e02-121">次のコードは、このコマンドレットで停止 Proc クラス定義です。</span><span class="sxs-lookup"><span data-stu-id="f3e02-121">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="f3e02-122">システムの変更のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-122">Defining Parameters for System Modification</span></span>

<span data-ttu-id="f3e02-123">コマンドレットは、そのサポート システムの変更やユーザー フィードバック パラメーターを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3e02-123">Your cmdlet needs to define parameters that support system modifications and user feedback.</span></span> <span data-ttu-id="f3e02-124">コマンドレットを定義する必要があります、`Name`パラメーターまたはそれと同等、コマンドレットは、システムに何らかの識別子を変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f3e02-124">The cmdlet should define a `Name` parameter or equivalent so that the cmdlet will be able to modify the system by some sort of identifier.</span></span> <span data-ttu-id="f3e02-125">また、コマンドレットを定義する必要があります、`Force`と`PassThru`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f3e02-125">In addition, the cmdlet should define the `Force` and `PassThru` parameters.</span></span> <span data-ttu-id="f3e02-126">これらのパラメーターの詳細については、[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3e02-126">For more information about these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="defining-a-parameter-alias"></a><span data-ttu-id="f3e02-127">パラメーター エイリアスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-127">Defining a Parameter Alias</span></span>

<span data-ttu-id="f3e02-128">パラメーター エイリアスには代替名またはコマンドレット パラメーターの適切に定義された 1 文字または 2 文字短い名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-128">A parameter alias can be an alternate name or a well-defined 1-letter or 2-letter short name for a cmdlet parameter.</span></span> <span data-ttu-id="f3e02-129">どちらの場合も、エイリアスを使用する目的は、コマンドラインからのユーザー入力を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-129">In both cases, the goal of using aliases is to simplify user entry from the command line.</span></span> <span data-ttu-id="f3e02-130">Windows PowerShell からのパラメーターのエイリアスをサポートしている、 [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute)属性には、宣言の構文 [Alias()] を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-130">Windows PowerShell supports parameter aliases through the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, which uses the declaration syntax [Alias()].</span></span>

<span data-ttu-id="f3e02-131">次のコードにエイリアスを追加する方法を示しています、`Name`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f3e02-131">The following code shows how an alias is added to the `Name` parameter.</span></span>

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

<span data-ttu-id="f3e02-132">使用するだけでなく、 [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute)属性、Windows PowerShell ランタイムによって実行される部分的な名前が一致する別名が指定されていない場合でもです。</span><span class="sxs-lookup"><span data-stu-id="f3e02-132">In addition to using the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, the Windows PowerShell runtime performs partial name matching, even if no aliases are specified.</span></span> <span data-ttu-id="f3e02-133">たとえば、次のコマンドレットがある、`FileName`パラメーターとは、唯一のパラメーターで始まる`F`、ユーザーが入力`Filename`、 `Filenam`、 `File`、 `Fi`、または`F`も認識し、エントリとして、`FileName`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f3e02-133">For example, if your cmdlet has a `FileName` parameter and that is the only parameter that starts with `F`, the user could enter `Filename`, `Filenam`, `File`, `Fi`, or `F` and still recognize the entry as the `FileName` parameter.</span></span>

## <a name="creating-help-for-parameters"></a><span data-ttu-id="f3e02-134">パラメーターのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="f3e02-134">Creating Help for Parameters</span></span>

<span data-ttu-id="f3e02-135">Windows PowerShell コマンドレットのパラメーターのヘルプを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-135">Windows PowerShell allows you to create Help for cmdlet parameters.</span></span> <span data-ttu-id="f3e02-136">このシステムの変更とユーザーのフィードバックに使用される任意のパラメーターに対して行います。</span><span class="sxs-lookup"><span data-stu-id="f3e02-136">Do this for any parameter used for system modification and user feedback.</span></span> <span data-ttu-id="f3e02-137">ヘルプをサポートするには、各パラメーターの設定することができます、`HelpMessage`属性内のキーワード、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)属性宣言。</span><span class="sxs-lookup"><span data-stu-id="f3e02-137">For each parameter to support Help, you can set the `HelpMessage` attribute keyword in the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="f3e02-138">このキーワードは、パラメーターを使用してで支援をユーザーに表示するテキストを定義します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-138">This keyword defines the text to display to the user for assistance in using the parameter.</span></span> <span data-ttu-id="f3e02-139">設定することも、`HelpMessageBaseName`メッセージで使用するリソースのベース名を識別するためにキーワード。</span><span class="sxs-lookup"><span data-stu-id="f3e02-139">You can also set the `HelpMessageBaseName` keyword to identify the base name of a resource to use for the message.</span></span> <span data-ttu-id="f3e02-140">設定する必要があるこのキーワードを設定した場合、`HelpMessageResourceId`リソース識別子を指定するキーワード。</span><span class="sxs-lookup"><span data-stu-id="f3e02-140">If you set this keyword, you must also set the `HelpMessageResourceId` keyword to specify the resource identifier.</span></span>

<span data-ttu-id="f3e02-141">この停止 Proc コマンドレットから次のコードを定義、`HelpMessage`属性のキーワード、`Name`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f3e02-141">The following code from this Stop-Proc cmdlet defines the `HelpMessage` attribute keyword for the `Name` parameter.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="f3e02-142">入力処理メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f3e02-142">Overriding an Input Processing Method</span></span>

<span data-ttu-id="f3e02-143">コマンドレットは、入力処理メソッドをオーバーライドする必要があります、これは最も頻繁になります[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-143">Your cmdlet must override an input processing method, most often this will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="f3e02-144">コマンドレットを呼び出す必要があります、システムを変更するときに、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)ユーザーを許可する方法変更が行われる前に、フィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-144">When modifying the system, the cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to allow the user to provide feedback before a change is made.</span></span> <span data-ttu-id="f3e02-145">これらのメソッドの詳細については、[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3e02-145">For more information about these methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="supporting-wildcard-expansion"></a><span data-ttu-id="f3e02-146">ワイルドカードの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f3e02-146">Supporting Wildcard Expansion</span></span>

<span data-ttu-id="f3e02-147">複数のオブジェクトの選択を許可する、コマンドレットを使用できます、 [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern)と[System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions)クラスを提供するには入力パラメーターのワイルドカードの拡張サポート。</span><span class="sxs-lookup"><span data-stu-id="f3e02-147">To allow the selection of multiple objects, your cmdlet can use the [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) and [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes to provide wildcard expansion support for parameter input.</span></span> <span data-ttu-id="f3e02-148">ワイルドカードのパターンの例は、lsa \* \*.txt、および [c]、\*します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-148">Examples of wildcard patterns are lsa\*, \*.txt, and [a-c]\*.</span></span> <span data-ttu-id="f3e02-149">パターンには、そのまま使用する文字が含まれている場合は、エスケープ文字として逆引用符 (') を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-149">Use the back-quote character (\`) as an escape character when the pattern contains a character that should be used literally.</span></span>

<span data-ttu-id="f3e02-150">ファイルとパス名のワイルドカードの展開では、コマンドレットは、複数のオブジェクトの選択が必要な場合は、パスの入力のサポートを許可する必要のある一般的なシナリオの例を示します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-150">Wildcard expansions of file and path names are examples of common scenarios where the cmdlet may want to allow support for path inputs when the selection of multiple objects is required.</span></span> <span data-ttu-id="f3e02-151">一般的なケースが、ユーザーが、現在のフォルダー内に存在するすべてのファイルを表示するが、ファイル システムです。</span><span class="sxs-lookup"><span data-stu-id="f3e02-151">A common case is in the file system, where a user wants to see all files residing in the current folder.</span></span>

<span data-ttu-id="f3e02-152">まれに、カスタマイズされたワイルドカードのパターン一致の実装を必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3e02-152">You should need a customized wildcard pattern matching implementation only rarely.</span></span> <span data-ttu-id="f3e02-153">この場合、コマンドレットでは、いずれかの完全な POSIX 1003.2、ワイルドカードの展開の 3.13 仕様または、次の簡略化されたサブセットをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3e02-153">In this case, your cmdlet should support either the full POSIX 1003.2, 3.13 specification for wildcard expansion or the following simplified subset:</span></span>

- <span data-ttu-id="f3e02-154">**疑問符 (?)。**</span><span class="sxs-lookup"><span data-stu-id="f3e02-154">**Question mark (?).**</span></span> <span data-ttu-id="f3e02-155">指定した位置に任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-155">Matches any character at the specified location.</span></span>

- <span data-ttu-id="f3e02-156">**アスタリスク (\*)。**</span><span class="sxs-lookup"><span data-stu-id="f3e02-156">**Asterisk (\*).**</span></span> <span data-ttu-id="f3e02-157">指定した場所から始まる 0 個以上の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-157">Matches zero or more characters starting at the specified location.</span></span>

- <span data-ttu-id="f3e02-158">**角かっこ ([) を開きます。**</span><span class="sxs-lookup"><span data-stu-id="f3e02-158">**Open bracket ([).**</span></span> <span data-ttu-id="f3e02-159">文字または文字の範囲に格納できるパターンの角かっこ表現が導入されています。</span><span class="sxs-lookup"><span data-stu-id="f3e02-159">Introduces a pattern bracket expression that can contain characters or a range of characters.</span></span> <span data-ttu-id="f3e02-160">範囲が必要な場合は、ハイフン (-) が、範囲を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-160">If a range is required, a hyphen (-) is used to indicate the range.</span></span>

- <span data-ttu-id="f3e02-161">**終了の角かっこ (]) です。**</span><span class="sxs-lookup"><span data-stu-id="f3e02-161">**Close bracket (]).**</span></span> <span data-ttu-id="f3e02-162">パターンの角かっこ表現を終了します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-162">Ends a pattern bracket expression.</span></span>

- <span data-ttu-id="f3e02-163">**バックアップ-引用符のエスケープ文字 (')。**</span><span class="sxs-lookup"><span data-stu-id="f3e02-163">**Back-quote escape character (\`).**</span></span> <span data-ttu-id="f3e02-164">次の文字がそのまま使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-164">Indicates that the next character should be taken literally.</span></span> <span data-ttu-id="f3e02-165">(プログラムで指定) ではなくコマンドラインから逆引用符を指定するときに、背面引用符のエスケープ文字が指定することは 2 回あります。</span><span class="sxs-lookup"><span data-stu-id="f3e02-165">Be aware that when specifying the back-quote character from the command line (as opposed to specifying it programmatically), the back-quote escape character must be specified twice.</span></span>

> [!NOTE]
> <span data-ttu-id="f3e02-166">ワイルドカードのパターンの詳細については、[コマンドレットのパラメーターにワイルドカードをサポートしている](./supporting-wildcard-characters-in-cmdlet-parameters.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3e02-166">For more information about wildcard patterns, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span></span>

<span data-ttu-id="f3e02-167">次のコードは、ワイルドカードのオプションを設定し、解決するために使用するワイルドカード パターンを定義する方法を示しています、`Name`このコマンドレットのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="f3e02-167">The following code shows how to set wildcard options and define the wildcard pattern used for resolving the `Name` parameter for this cmdlet.</span></span>

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

<span data-ttu-id="f3e02-168">次のコードでは、プロセス名が定義されているワイルドカードのパターンと一致するかどうかをテストする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-168">The following code shows how to test whether the process name matches the defined wildcard pattern.</span></span> <span data-ttu-id="f3e02-169">、ここでは、プロセス名にパターンが一致しない場合、コマンドレットに続くこと、次のプロセス名を取得することを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-169">Notice that, in this case, if the process name does not match the pattern, the cmdlet continues on to get the next process name.</span></span>

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a><span data-ttu-id="f3e02-170">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="f3e02-170">Code Sample</span></span>

<span data-ttu-id="f3e02-171">完全なC#サンプル コードは、「 [StopProcessSample03 サンプル](./stopprocesssample03-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-171">For the complete C# sample code, see [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="f3e02-172">オブジェクトの種類と書式設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-172">Define Object Types and Formatting</span></span>

<span data-ttu-id="f3e02-173">Windows PowerShell は、.Net オブジェクトを使用してコマンドレット間で情報を渡します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-173">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="f3e02-174">その結果、コマンドレットは、独自の型を定義する必要がありますか、コマンドレットは、別のコマンドレットによって提供される既存の型を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3e02-174">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="f3e02-175">新しい型を定義するか、既存の型の拡張の詳細については、[を拡張するオブジェクトの種類と書式](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3e02-175">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="f3e02-176">コマンドレットを構築</span><span class="sxs-lookup"><span data-stu-id="f3e02-176">Building the Cmdlet</span></span>

<span data-ttu-id="f3e02-177">コマンドレットを実装するには、後にする必要があります登録する必要が Windows PowerShell を使用した Windows PowerShell スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-177">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="f3e02-178">コマンドレットの登録の詳細については、[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3e02-178">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="f3e02-179">テスト コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f3e02-179">Testing the Cmdlet</span></span>

<span data-ttu-id="f3e02-180">コマンドレットは、Windows PowerShell を使用した登録しているときに、コマンドラインで実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-180">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="f3e02-181">サンプルの停止 Proc コマンドレットをテストしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="f3e02-181">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="f3e02-182">詳細については、コマンドラインからコマンドレットを使用して、、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3e02-182">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="f3e02-183">Windows PowerShell を起動し、ProcessName エイリアスを使用してプロセスを停止する停止プロシージャを使用して、`Name`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f3e02-183">Start Windows PowerShell and use Stop-Proc to stop a process using the ProcessName alias for the `Name` parameter.</span></span>

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

<span data-ttu-id="f3e02-184">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-184">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="f3e02-185">コマンドラインでは、次のエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-185">Make the following entry on the command line.</span></span> <span data-ttu-id="f3e02-186">Name パラメーターは必須であるために、そのように求められます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-186">Because the Name parameter is mandatory, you are prompted for it.</span></span> <span data-ttu-id="f3e02-187">入力"!?"</span><span class="sxs-lookup"><span data-stu-id="f3e02-187">Entering "!?"</span></span> <span data-ttu-id="f3e02-188">パラメーターに関連付けられているヘルプ テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-188">brings up the help text associated with the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

<span data-ttu-id="f3e02-189">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-189">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- <span data-ttu-id="f3e02-190">今すぐワイルドカード パターンに一致するすべてのプロセスを停止する次のエントリを作成する"\* 注\*"。</span><span class="sxs-lookup"><span data-stu-id="f3e02-190">Now make the following entry to stop all processes that match the wildcard pattern "\*note\*".</span></span> <span data-ttu-id="f3e02-191">各パターンに一致するプロセスを停止する前に求められます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-191">You are prompted before stopping each process that matches the pattern.</span></span>

    ```powershell
    PS> stop-proc -Name *note*
    ```

<span data-ttu-id="f3e02-192">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-192">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

<span data-ttu-id="f3e02-193">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-193">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

<span data-ttu-id="f3e02-194">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3e02-194">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="f3e02-195">参照</span><span class="sxs-lookup"><span data-stu-id="f3e02-195">See Also</span></span>

[<span data-ttu-id="f3e02-196">システムを変更するコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3e02-196">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="f3e02-197">Windows PowerShell コマンドレットを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f3e02-197">How to Create a Windows PowerShell Cmdlet</span></span>](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="f3e02-198">オブジェクトの種類を拡張して、書式設定</span><span class="sxs-lookup"><span data-stu-id="f3e02-198">Extending Object Types and Formatting</span></span>](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="f3e02-199">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="f3e02-199">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="f3e02-200">コマンドレットのパラメーターでのワイルドカードのサポート</span><span class="sxs-lookup"><span data-stu-id="f3e02-200">Supporting Wildcards in Cmdlet Parameters</span></span>](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[<span data-ttu-id="f3e02-201">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f3e02-201">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

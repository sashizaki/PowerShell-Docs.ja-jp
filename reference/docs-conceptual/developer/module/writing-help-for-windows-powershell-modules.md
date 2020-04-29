---
title: PowerShell モジュールのヘルプの作成
ms.date: 04/10/2020
ms.openlocfilehash: 496b7e6cadff4d2db15b6452e9d38efcdf1739ec
ms.sourcegitcommit: 8f55c0157280afa4598fe385a706faf330e723a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "81219661"
---
# <a name="writing-help-for-powershell-modules"></a><span data-ttu-id="c5352-102">PowerShell モジュールのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="c5352-102">Writing Help for PowerShell Modules</span></span>

<span data-ttu-id="c5352-103">PowerShell モジュールには、モジュールに関するヘルプトピックや、コマンドレット、プロバイダー、関数、スクリプトなどのモジュールメンバーに関するヘルプトピックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c5352-103">PowerShell modules can include Help topics about the module and about the module members, such as cmdlets, providers, functions and scripts.</span></span> <span data-ttu-id="c5352-104">コマンド`Get-Help`レットは、他の PowerShell 項目のヘルプを表示するのと同じ形式のモジュールヘルプトピックを表示し`Get-Help` 、ユーザーは標準のコマンドを使用してヘルプトピックを取得します。</span><span class="sxs-lookup"><span data-stu-id="c5352-104">The `Get-Help` cmdlet displays the module Help topics in the same format as it displays Help for other PowerShell items, and users use standard `Get-Help` commands to get the Help topics.</span></span>

<span data-ttu-id="c5352-105">このドキュメントでは、モジュールのヘルプトピックの形式と適切な配置について説明し、モジュールのヘルプコンテンツに関するガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="c5352-105">This document explains the format and correct placement of module Help topics, and it suggests guidelines for module Help content.</span></span>

## <a name="types-of-module-help"></a><span data-ttu-id="c5352-106">モジュールのヘルプの種類</span><span class="sxs-lookup"><span data-stu-id="c5352-106">Types of Module Help</span></span>

<span data-ttu-id="c5352-107">モジュールには、次の種類のヘルプを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c5352-107">A module can include the following types of Help.</span></span>

- <span data-ttu-id="c5352-108">**コマンドレットのヘルプを参照**してください。</span><span class="sxs-lookup"><span data-stu-id="c5352-108">**Cmdlet Help**.</span></span> <span data-ttu-id="c5352-109">モジュール内のコマンドレットについて説明するヘルプトピックは、コマンドヘルプスキーマを使用する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c5352-109">The Help topics that describe cmdlets in a module are XML files that use the command help schema</span></span>

- <span data-ttu-id="c5352-110">**プロバイダーのヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="c5352-110">**Provider Help**.</span></span> <span data-ttu-id="c5352-111">モジュール内のプロバイダーについて説明するヘルプトピックは、プロバイダーヘルプスキーマを使用する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c5352-111">The Help topics that describe providers in a module are XML files that use the provider help schema.</span></span>

- <span data-ttu-id="c5352-112">**関数のヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="c5352-112">**Function Help**.</span></span> <span data-ttu-id="c5352-113">モジュール内の関数について説明するヘルプトピックは、関数内のコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることも、スクリプトまたはスクリプトモジュールで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5352-113">The Help topics that describe functions in a module can be XML files that use the command help schema or comment-based Help topics within the function, or the script or script module</span></span>

- <span data-ttu-id="c5352-114">**スクリプトのヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="c5352-114">**Script Help**.</span></span> <span data-ttu-id="c5352-115">モジュール内のスクリプトを記述するヘルプトピックは、スクリプトまたはスクリプトモジュールでコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c5352-115">The Help topics that describe scripts in a module can be XML files that use the command help schema or comment-based Help topics in the script or script module.</span></span>

- <span data-ttu-id="c5352-116">**概念 ("About") のヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="c5352-116">**Conceptual ("About") Help**.</span></span> <span data-ttu-id="c5352-117">概念 ("about") ヘルプトピックを使用して、モジュールとそのメンバーを記述したり、メンバーを組み合わせてタスクを実行する方法を説明したりできます。</span><span class="sxs-lookup"><span data-stu-id="c5352-117">You can use a conceptual ("about") Help topic to describe the module and its members and to explain how the members can be used together to perform tasks.</span></span>
  <span data-ttu-id="c5352-118">概念説明ヘルプトピックは、Unicode (UTF-8) エンコードを使用したテキストファイルです。</span><span class="sxs-lookup"><span data-stu-id="c5352-118">Conceptual Help topics are text files with Unicode (UTF-8) encoding.</span></span> <span data-ttu-id="c5352-119">ファイル名には、の`about_<name>.help.txt`ような形式を`about_MyModule.help.txt`使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5352-119">The file name must use the `about_<name>.help.txt` format, such as `about_MyModule.help.txt`.</span></span> <span data-ttu-id="c5352-120">既定では、PowerShell には、次の例のように、これらの概念に関するヘルプトピックが100以上含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5352-120">By default, PowerShell includes over 100 of these conceptual About Help topics, and they are formatted like the following example.</span></span>

  ```
  TOPIC
      about_<subject or module name>

  SHORT DESCRIPTION
      A short, one-line description of the topic contents.

  LONG DESCRIPTION
      A detailed, full description of the subject or purpose of the module.

  EXAMPLES
      Examples of how to use the module or how the subject feature works in practice.

  KEYWORDS
      Terms or titles on which you might expect your users to search for the information in this topic.

  SEE ALSO
      Text-only references for further reading. Hyperlinks cannot work in the PowerShell console.

  ```

<span data-ttu-id="c5352-121">すべてのスキーマファイルは、 `$PSHOME\Schemas\PSMaml`フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="c5352-121">All of the schema files can be found in the `$PSHOME\Schemas\PSMaml` folder.</span></span>

## <a name="placement-of-module-help"></a><span data-ttu-id="c5352-122">モジュールヘルプの配置</span><span class="sxs-lookup"><span data-stu-id="c5352-122">Placement of Module Help</span></span>

<span data-ttu-id="c5352-123">この`Get-Help`コマンドレットは、モジュールディレクトリの言語固有のサブディレクトリにあるモジュールヘルプトピックファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="c5352-123">The `Get-Help` cmdlet looks for module Help topic files in language-specific subdirectories of the module directory.</span></span>

<span data-ttu-id="c5352-124">たとえば、次のディレクトリ構造の図は、SampleModule モジュールのヘルプトピックの場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="c5352-124">For example, the following directory structure diagram shows the location of the Help topics for the SampleModule module.</span></span>

```
<ModulePath>
         \SampleModule
               \<en-US>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml
               \<fr-FR>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml

```

> [!NOTE]
> <span data-ttu-id="c5352-125">この例では、 `<ModulePath>`プレースホルダーは`$HOME\Documents\Modules`、、 `$PSHOME\Modules`、またはユーザー `PSModulePath`が指定するカスタムパスなど、環境変数内のパスの1つを表します。</span><span class="sxs-lookup"><span data-stu-id="c5352-125">In the example, the `<ModulePath>` placeholder represents one of the paths in the `PSModulePath` environment variable, such as `$HOME\Documents\Modules`, `$PSHOME\Modules`, or a custom path that the user specifies.</span></span>

## <a name="getting-module-help"></a><span data-ttu-id="c5352-126">モジュールのヘルプを取得する</span><span class="sxs-lookup"><span data-stu-id="c5352-126">Getting Module Help</span></span>

<span data-ttu-id="c5352-127">ユーザーがモジュールをセッションにインポートすると、そのモジュールのヘルプトピックがモジュールと共にセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c5352-127">When a user imports a module into a session, the Help topics for that module are imported into the session along with the module.</span></span> <span data-ttu-id="c5352-128">モジュールマニフェストの FileList キーの値にヘルプトピックファイルを一覧表示することはできますが、ヘルプトピックはコマンドレットの`Export-ModuleMember`影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="c5352-128">You can list the Help topic files in the value of the FileList key in the module manifest, but Help topics are not affected by the `Export-ModuleMember` cmdlet.</span></span>

<span data-ttu-id="c5352-129">さまざまな言語でモジュールのヘルプトピックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="c5352-129">You can provide module Help topics in different languages.</span></span> <span data-ttu-id="c5352-130">この`Get-Help`コマンドレットは、コントロールパネルの [地域と言語のオプション] 項目で、現在のユーザーに対して指定されている言語のモジュールヘルプトピックを自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="c5352-130">The `Get-Help` cmdlet automatically displays module Help topics in the language that is specified for the current user in the Regional and Language Options item in Control Panel.</span></span> <span data-ttu-id="c5352-131">Windows Vista 以降のバージョンの Windows では`Get-Help` 、は、windows 用に設定された言語フォールバック標準に従って、モジュールディレクトリの言語固有のサブディレクトリにあるヘルプトピックを検索します。</span><span class="sxs-lookup"><span data-stu-id="c5352-131">In Windows Vista and later versions of Windows, `Get-Help` searches for the Help topics in language-specific subdirectories of the module directory in accordance with the language fallback standards established for Windows.</span></span>

<span data-ttu-id="c5352-132">PowerShell 3.0 以降では、コマンド`Get-Help`レットまたは関数に対してコマンドを実行すると、モジュールの自動インポートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="c5352-132">Beginning in PowerShell 3.0, running a `Get-Help` command for a cmdlet or function triggers automatic importing of the module.</span></span> <span data-ttu-id="c5352-133">この`Get-Help`コマンドレットは、モジュール内のヘルプトピックの内容をすぐに表示します。</span><span class="sxs-lookup"><span data-stu-id="c5352-133">The `Get-Help` cmdlet immediately displays the contents of the help topics in the module.</span></span>

<span data-ttu-id="c5352-134">モジュールにヘルプトピックが含まれておらず、ユーザーのコンピューターのモジュール内のコマンドに関するヘルプトピックがない場合`Get-Help`は、自動生成されたヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="c5352-134">If the module does not contain help topics and there are no help topics for the commands in the module on the user's computer, `Get-Help` displays auto-generated help.</span></span> <span data-ttu-id="c5352-135">自動生成されたヘルプには、コマンドの構文、パラメーター、および入力と出力の型が含まれていますが、説明は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="c5352-135">The auto-generated help includes the command syntax, parameters, and input and output types, but does not include any descriptions.</span></span> <span data-ttu-id="c5352-136">自動生成されたヘルプには、コマンド`Update-Help`レットを使用して、インターネットまたはファイル共有からコマンドのヘルプをダウンロードするように指示するテキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5352-136">The auto-generated help includes text that directs the user to try to use the `Update-Help` cmdlet to download help for the command from the Internet or a file share.</span></span> <span data-ttu-id="c5352-137">また、 `Get-Help`コマンドレットの**online**パラメーターを使用して、ヘルプトピックのオンラインバージョンを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c5352-137">It also recommends using the **Online** parameter of the `Get-Help` cmdlet to get the online version of the help topic.</span></span>

## <a name="supporting-updatable-help"></a><span data-ttu-id="c5352-138">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="c5352-138">Supporting Updatable Help</span></span>

<span data-ttu-id="c5352-139">Powershell 3.0 およびそれ以降のバージョンの PowerShell を使用するユーザーは、モジュールの更新されたヘルプファイルをインターネットまたはローカルファイル共有からダウンロードしてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c5352-139">Users of PowerShell 3.0 and later versions of PowerShell can download and install updated help files for a module from the Internet or from a local file share.</span></span> <span data-ttu-id="c5352-140">コマンド`Update-Help`レット`Save-Help`およびコマンドレットは、ユーザーからの管理の詳細を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="c5352-140">The `Update-Help` and `Save-Help` cmdlets hide the management details from the user.</span></span> <span data-ttu-id="c5352-141">ユーザーは`Update-Help`コマンドレットを実行し、 `Get-Help`コマンドレットを使用して、PowerShell コマンドプロンプトでモジュールの最新のヘルプファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="c5352-141">Users run the `Update-Help` cmdlet and then use the `Get-Help` cmdlet to read the newest help files for the module at the PowerShell command prompt.</span></span>
<span data-ttu-id="c5352-142">ユーザーは、Windows または PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5352-142">Users do not need to restart Windows or PowerShell.</span></span>

<span data-ttu-id="c5352-143">ファイアウォールの背後にあるユーザーやインターネットにアクセスできないユーザーも、更新可能なヘルプを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5352-143">Users behind firewalls and those without Internet access can use Updatable Help, as well.</span></span>
<span data-ttu-id="c5352-144">インターネットアクセスが可能な管理`Save-Help`者は、コマンドレットを使用して、最新のヘルプファイルをダウンロードしてファイル共有にインストールします。</span><span class="sxs-lookup"><span data-stu-id="c5352-144">Administrators with Internet access use the `Save-Help` cmdlet to download and install the newest help files to a file share.</span></span> <span data-ttu-id="c5352-145">次に、 `Update-Help`コマンドレットの**Path**パラメーターを使用して、ファイル共有から最新のヘルプファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="c5352-145">Then, users use the **Path** parameter of the `Update-Help` cmdlet to get the newest help files from the file share.</span></span>

<span data-ttu-id="c5352-146">モジュールの作成者は、モジュールにヘルプファイルを含めたり、更新可能なヘルプを使用してヘルプファイルを更新したり、モジュールからヘルプファイルを除外したり、更新可能なヘルプを使用してインストールしたり更新したりできます。</span><span class="sxs-lookup"><span data-stu-id="c5352-146">Module authors can include help files in the module and use Updatable Help to update the help files, or omit help files from the module and use Updatable Help both to install and to update them.</span></span>

<span data-ttu-id="c5352-147">更新可能なヘルプの詳細については、「[更新可能なヘルプのサポート](./supporting-updatable-help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5352-147">For more information about Updatable Help, see [Supporting Updatable Help](./supporting-updatable-help.md).</span></span>

## <a name="supporting-online-help"></a><span data-ttu-id="c5352-148">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="c5352-148">Supporting Online Help</span></span>

<span data-ttu-id="c5352-149">更新されたヘルプファイルをコンピューターにインストールできない、またはインストールしないユーザーは、多くの場合、オンラインバージョンのモジュールヘルプトピックに依存しています。</span><span class="sxs-lookup"><span data-stu-id="c5352-149">Users who cannot or do not install updated help files on their computers often rely on the online version of module help topics.</span></span> <span data-ttu-id="c5352-150">コマンドレットの Online パラメーターは、既定のインターネットブラウザーでユーザーのコマンドレットまたは高度な関数のヘルプトピックを開きます。 **Online** `Get-Help`</span><span class="sxs-lookup"><span data-stu-id="c5352-150">The **Online** parameter of the `Get-Help` cmdlet opens the online version of a cmdlet or advanced function help topic for the user in their default Internet browser.</span></span>

<span data-ttu-id="c5352-151">コマンド`Get-Help`レットでは、コマンドレットまたは関数**の "/" プロパティの値**を使用して、ヘルプトピックのオンラインバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="c5352-151">The `Get-Help` cmdlet uses the value of the **HelpUri** property of the cmdlet or function to find the online version of the help topic.</span></span>

<span data-ttu-id="c5352-152">PowerShell 3.0 以降では、コマンドレットと関数のヘルプトピックのオンラインバージョンを検索するために、コマンドレットクラスまたはコマンドレット**バインド**属性の **"/" プロパティ**を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="c5352-152">Beginning in PowerShell 3.0, you can help users find the online version of cmdlet and function help topics by defining the HelpUri attribute on the cmdlet class or the **HelpUri** property of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="c5352-153">属性の値は、コマンドレットまたは関数のすべて**のプロパティの**値です。</span><span class="sxs-lookup"><span data-stu-id="c5352-153">The value of the attribute is the value of the **HelpUri** property of the cmdlet or function.</span></span>

<span data-ttu-id="c5352-154">詳細については、「[オンラインヘルプのサポート](./supporting-online-help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5352-154">For more information, see [Supporting Online Help](./supporting-online-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c5352-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5352-155">See Also</span></span>

[<span data-ttu-id="c5352-156">PowerShell モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="c5352-156">Writing a PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="c5352-157">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="c5352-157">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)

[<span data-ttu-id="c5352-158">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="c5352-158">Supporting Online Help</span></span>](./supporting-online-help.md)

---
ms.date: 04/10/2020
ms.topic: reference
title: PowerShell モジュールのヘルプの記述
description: PowerShell モジュールのヘルプの記述
ms.openlocfilehash: 3bef45c0dd8a7e63bc419bb3e5a7a1783810105b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654653"
---
# <a name="writing-help-for-powershell-modules"></a><span data-ttu-id="d497c-103">PowerShell モジュールのヘルプの記述</span><span class="sxs-lookup"><span data-stu-id="d497c-103">Writing Help for PowerShell Modules</span></span>

<span data-ttu-id="d497c-104">PowerShell モジュールには、モジュールに関するヘルプトピックや、コマンドレット、プロバイダー、関数、スクリプトなどのモジュールメンバーに関するヘルプトピックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d497c-104">PowerShell modules can include Help topics about the module and about the module members, such as cmdlets, providers, functions and scripts.</span></span> <span data-ttu-id="d497c-105">`Get-Help`コマンドレットは、他の PowerShell 項目のヘルプを表示するのと同じ形式のモジュールヘルプトピックを表示し、ユーザーは標準のコマンドを使用して `Get-Help` ヘルプトピックを取得します。</span><span class="sxs-lookup"><span data-stu-id="d497c-105">The `Get-Help` cmdlet displays the module Help topics in the same format as it displays Help for other PowerShell items, and users use standard `Get-Help` commands to get the Help topics.</span></span>

<span data-ttu-id="d497c-106">このドキュメントでは、モジュールのヘルプトピックの形式と適切な配置について説明し、モジュールのヘルプコンテンツに関するガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="d497c-106">This document explains the format and correct placement of module Help topics, and it suggests guidelines for module Help content.</span></span>

## <a name="types-of-module-help"></a><span data-ttu-id="d497c-107">モジュールのヘルプの種類</span><span class="sxs-lookup"><span data-stu-id="d497c-107">Types of Module Help</span></span>

<span data-ttu-id="d497c-108">モジュールには、次の種類のヘルプを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d497c-108">A module can include the following types of Help.</span></span>

- <span data-ttu-id="d497c-109">**コマンドレットのヘルプを参照** してください。</span><span class="sxs-lookup"><span data-stu-id="d497c-109">**Cmdlet Help**.</span></span> <span data-ttu-id="d497c-110">モジュール内のコマンドレットについて説明するヘルプトピックは、コマンドヘルプスキーマを使用する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d497c-110">The Help topics that describe cmdlets in a module are XML files that use the command help schema</span></span>

- <span data-ttu-id="d497c-111">**プロバイダーのヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="d497c-111">**Provider Help**.</span></span> <span data-ttu-id="d497c-112">モジュール内のプロバイダーについて説明するヘルプトピックは、プロバイダーヘルプスキーマを使用する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d497c-112">The Help topics that describe providers in a module are XML files that use the provider help schema.</span></span>

- <span data-ttu-id="d497c-113">**関数のヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="d497c-113">**Function Help**.</span></span> <span data-ttu-id="d497c-114">モジュール内の関数について説明するヘルプトピックは、関数内のコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることも、スクリプトまたはスクリプトモジュールで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d497c-114">The Help topics that describe functions in a module can be XML files that use the command help schema or comment-based Help topics within the function, or the script or script module</span></span>

- <span data-ttu-id="d497c-115">**スクリプトのヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="d497c-115">**Script Help**.</span></span> <span data-ttu-id="d497c-116">モジュール内のスクリプトを記述するヘルプトピックは、スクリプトまたはスクリプトモジュールでコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d497c-116">The Help topics that describe scripts in a module can be XML files that use the command help schema or comment-based Help topics in the script or script module.</span></span>

- <span data-ttu-id="d497c-117">**概念 ("About") のヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="d497c-117">**Conceptual ("About") Help**.</span></span> <span data-ttu-id="d497c-118">概念 ("about") ヘルプトピックを使用して、モジュールとそのメンバーを記述したり、メンバーを組み合わせてタスクを実行する方法を説明したりできます。</span><span class="sxs-lookup"><span data-stu-id="d497c-118">You can use a conceptual ("about") Help topic to describe the module and its members and to explain how the members can be used together to perform tasks.</span></span>
  <span data-ttu-id="d497c-119">概念説明ヘルプトピックは、Unicode (UTF-8) エンコードを使用したテキストファイルです。</span><span class="sxs-lookup"><span data-stu-id="d497c-119">Conceptual Help topics are text files with Unicode (UTF-8) encoding.</span></span> <span data-ttu-id="d497c-120">ファイル名には、のような形式を使用する必要があり `about_<name>.help.txt` `about_MyModule.help.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="d497c-120">The filename must use the `about_<name>.help.txt` format, such as `about_MyModule.help.txt`.</span></span> <span data-ttu-id="d497c-121">既定では、PowerShell には、次の例のように、これらの概念に関するヘルプトピックが100以上含まれています。</span><span class="sxs-lookup"><span data-stu-id="d497c-121">By default, PowerShell includes over 100 of these conceptual About Help topics, and they are formatted like the following example.</span></span>

  ```Output
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

<span data-ttu-id="d497c-122">すべてのスキーマファイルは、フォルダーにあり `$PSHOME\Schemas\PSMaml` ます。</span><span class="sxs-lookup"><span data-stu-id="d497c-122">All of the schema files can be found in the `$PSHOME\Schemas\PSMaml` folder.</span></span>

## <a name="placement-of-module-help"></a><span data-ttu-id="d497c-123">モジュールヘルプの配置</span><span class="sxs-lookup"><span data-stu-id="d497c-123">Placement of Module Help</span></span>

<span data-ttu-id="d497c-124">この `Get-Help` コマンドレットは、モジュールディレクトリの言語固有のサブディレクトリにあるモジュールヘルプトピックファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="d497c-124">The `Get-Help` cmdlet looks for module Help topic files in language-specific subdirectories of the module directory.</span></span>

<span data-ttu-id="d497c-125">たとえば、次のディレクトリ構造の図は、SampleModule モジュールのヘルプトピックの場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="d497c-125">For example, the following directory structure diagram shows the location of the Help topics for the SampleModule module.</span></span>

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
> <span data-ttu-id="d497c-126">この例では、 `<ModulePath>` プレースホルダーは `PSModulePath` `$HOME\Documents\Modules` 、、 `$PSHOME\Modules` 、またはユーザーが指定するカスタムパスなど、環境変数内のパスの1つを表します。</span><span class="sxs-lookup"><span data-stu-id="d497c-126">In the example, the `<ModulePath>` placeholder represents one of the paths in the `PSModulePath` environment variable, such as `$HOME\Documents\Modules`, `$PSHOME\Modules`, or a custom path that the user specifies.</span></span>

## <a name="getting-module-help"></a><span data-ttu-id="d497c-127">モジュールのヘルプを取得する</span><span class="sxs-lookup"><span data-stu-id="d497c-127">Getting Module Help</span></span>

<span data-ttu-id="d497c-128">ユーザーがモジュールをセッションにインポートすると、そのモジュールのヘルプトピックがモジュールと共にセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="d497c-128">When a user imports a module into a session, the Help topics for that module are imported into the session along with the module.</span></span> <span data-ttu-id="d497c-129">モジュールマニフェストの FileList キーの値にヘルプトピックファイルを一覧表示することはできますが、ヘルプトピックはコマンドレットの影響を受けません `Export-ModuleMember` 。</span><span class="sxs-lookup"><span data-stu-id="d497c-129">You can list the Help topic files in the value of the FileList key in the module manifest, but Help topics are not affected by the `Export-ModuleMember` cmdlet.</span></span>

<span data-ttu-id="d497c-130">さまざまな言語でモジュールのヘルプトピックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="d497c-130">You can provide module Help topics in different languages.</span></span> <span data-ttu-id="d497c-131">この `Get-Help` コマンドレットは、コントロールパネルの [地域と言語のオプション] 項目で、現在のユーザーに対して指定されている言語のモジュールヘルプトピックを自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="d497c-131">The `Get-Help` cmdlet automatically displays module Help topics in the language that is specified for the current user in the Regional and Language Options item in Control Panel.</span></span> <span data-ttu-id="d497c-132">Windows Vista 以降のバージョンの Windows では、は、Windows 用に設定された `Get-Help` 言語フォールバック標準に従って、モジュールディレクトリの言語固有のサブディレクトリにあるヘルプトピックを検索します。</span><span class="sxs-lookup"><span data-stu-id="d497c-132">In Windows Vista and later versions of Windows, `Get-Help` searches for the Help topics in language-specific subdirectories of the module directory in accordance with the language fallback standards established for Windows.</span></span>

<span data-ttu-id="d497c-133">PowerShell 3.0 以降で `Get-Help` は、コマンドレットまたは関数に対してコマンドを実行すると、モジュールの自動インポートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="d497c-133">Beginning in PowerShell 3.0, running a `Get-Help` command for a cmdlet or function triggers automatic importing of the module.</span></span> <span data-ttu-id="d497c-134">この `Get-Help` コマンドレットは、モジュール内のヘルプトピックの内容をすぐに表示します。</span><span class="sxs-lookup"><span data-stu-id="d497c-134">The `Get-Help` cmdlet immediately displays the contents of the help topics in the module.</span></span>

<span data-ttu-id="d497c-135">モジュールにヘルプトピックが含まれておらず、ユーザーのコンピューターのモジュール内のコマンドに関するヘルプトピックがない場合は、 `Get-Help` 自動生成されたヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="d497c-135">If the module does not contain help topics and there are no help topics for the commands in the module on the user's computer, `Get-Help` displays auto-generated help.</span></span> <span data-ttu-id="d497c-136">自動生成されたヘルプには、コマンドの構文、パラメーター、および入力と出力の型が含まれていますが、説明は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d497c-136">The auto-generated help includes the command syntax, parameters, and input and output types, but does not include any descriptions.</span></span> <span data-ttu-id="d497c-137">自動生成されたヘルプには、コマンドレットを使用して、 `Update-Help` インターネットまたはファイル共有からコマンドのヘルプをダウンロードするように指示するテキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d497c-137">The auto-generated help includes text that directs the user to try to use the `Update-Help` cmdlet to download help for the command from the internet or a file share.</span></span> <span data-ttu-id="d497c-138">また、コマンドレットの **online** パラメーターを使用して、 `Get-Help` ヘルプトピックのオンラインバージョンを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d497c-138">It also recommends using the **Online** parameter of the `Get-Help` cmdlet to get the online version of the help topic.</span></span>

## <a name="supporting-updatable-help"></a><span data-ttu-id="d497c-139">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="d497c-139">Supporting Updatable Help</span></span>

<span data-ttu-id="d497c-140">Powershell 3.0 およびそれ以降のバージョンの PowerShell を使用するユーザーは、モジュールの更新されたヘルプファイルをインターネットまたはローカルファイル共有からダウンロードしてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d497c-140">Users of PowerShell 3.0 and later versions of PowerShell can download and install updated help files for a module from the internet or from a local file share.</span></span> <span data-ttu-id="d497c-141">`Update-Help` `Save-Help` コマンドレットおよびコマンドレットは、ユーザーからの管理の詳細を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="d497c-141">The `Update-Help` and `Save-Help` cmdlets hide the management details from the user.</span></span> <span data-ttu-id="d497c-142">ユーザーはコマンドレットを実行し、コマンドレットを使用して、 `Update-Help` `Get-Help` PowerShell コマンドプロンプトでモジュールの最新のヘルプファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d497c-142">Users run the `Update-Help` cmdlet and then use the `Get-Help` cmdlet to read the newest help files for the module at the PowerShell command prompt.</span></span>
<span data-ttu-id="d497c-143">ユーザーは、Windows または PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d497c-143">Users do not need to restart Windows or PowerShell.</span></span>

<span data-ttu-id="d497c-144">ファイアウォールの背後にあるユーザーやインターネットにアクセスできないユーザーも、更新可能なヘルプを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d497c-144">Users behind firewalls and those without internet access can use Updatable Help, as well.</span></span>
<span data-ttu-id="d497c-145">インターネットアクセスが可能な管理者は、コマンドレットを使用して、 `Save-Help` 最新のヘルプファイルをダウンロードしてファイル共有にインストールします。</span><span class="sxs-lookup"><span data-stu-id="d497c-145">Administrators with internet access use the `Save-Help` cmdlet to download and install the newest help files to a file share.</span></span> <span data-ttu-id="d497c-146">次に、コマンドレットの **Path** パラメーターを使用して、 `Update-Help` ファイル共有から最新のヘルプファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="d497c-146">Then, users use the **Path** parameter of the `Update-Help` cmdlet to get the newest help files from the file share.</span></span>

<span data-ttu-id="d497c-147">モジュールの作成者は、モジュールにヘルプファイルを含めたり、更新可能なヘルプを使用してヘルプファイルを更新したり、モジュールからヘルプファイルを除外したり、更新可能なヘルプを使用してインストールしたり更新したりできます。</span><span class="sxs-lookup"><span data-stu-id="d497c-147">Module authors can include help files in the module and use Updatable Help to update the help files, or omit help files from the module and use Updatable Help both to install and to update them.</span></span>

<span data-ttu-id="d497c-148">更新可能なヘルプの詳細については、「 [更新可能なヘルプのサポート](./supporting-updatable-help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d497c-148">For more information about Updatable Help, see [Supporting Updatable Help](./supporting-updatable-help.md).</span></span>

## <a name="supporting-online-help"></a><span data-ttu-id="d497c-149">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="d497c-149">Supporting Online Help</span></span>

<span data-ttu-id="d497c-150">更新されたヘルプファイルをコンピューターにインストールできない、またはインストールしないユーザーは、多くの場合、オンラインバージョンのモジュールヘルプトピックに依存しています。</span><span class="sxs-lookup"><span data-stu-id="d497c-150">Users who cannot or do not install updated help files on their computers often rely on the online version of module help topics.</span></span> <span data-ttu-id="d497c-151">コマンドレットの **online** パラメーターは、 `Get-Help` 既定のインターネットブラウザーでユーザーのコマンドレットまたは高度な関数のヘルプトピックを開きます。</span><span class="sxs-lookup"><span data-stu-id="d497c-151">The **Online** parameter of the `Get-Help` cmdlet opens the online version of a cmdlet or advanced function help topic for the user in their default internet browser.</span></span>

<span data-ttu-id="d497c-152">コマンドレットでは、 `Get-Help` コマンドレットまたは関数の "/" プロパティの値を使用して、ヘルプトピックのオンラインバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="d497c-152">The `Get-Help` cmdlet uses the value of the **HelpUri** property of the cmdlet or function to find the online version of the help topic.</span></span>

<span data-ttu-id="d497c-153">PowerShell 3.0 以降では、コマンドレットと関数のヘルプトピックのオンラインバージョンを検索するために、コマンドレットクラスまたはコマンドレット **バインド** 属性の **"/" プロパティ** を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="d497c-153">Beginning in PowerShell 3.0, you can help users find the online version of cmdlet and function help topics by defining the HelpUri attribute on the cmdlet class or the **HelpUri** property of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="d497c-154">属性の値は、コマンドレットまたは関数のすべて **のプロパティの** 値です。</span><span class="sxs-lookup"><span data-stu-id="d497c-154">The value of the attribute is the value of the **HelpUri** property of the cmdlet or function.</span></span>

<span data-ttu-id="d497c-155">詳細については、「 [オンラインヘルプのサポート](./supporting-online-help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d497c-155">For more information, see [Supporting Online Help](./supporting-online-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d497c-156">参照</span><span class="sxs-lookup"><span data-stu-id="d497c-156">See Also</span></span>

[<span data-ttu-id="d497c-157">PowerShell モジュールの記述</span><span class="sxs-lookup"><span data-stu-id="d497c-157">Writing a PowerShell Module</span></span>](../module/writing-a-windows-powershell-module.md)

[<span data-ttu-id="d497c-158">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="d497c-158">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)

[<span data-ttu-id="d497c-159">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="d497c-159">Supporting Online Help</span></span>](./supporting-online-help.md)

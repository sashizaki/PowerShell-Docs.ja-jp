---
title: Windows PowerShell モジュールのヘルプを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b58fa5-01bc-426c-a043-5c700d6578e9
caps.latest.revision: 16
ms.openlocfilehash: 443bf5f693d2ab161668de25a1097347826cb5c2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360561"
---
# <a name="writing-help-for-windows-powershell-modules"></a><span data-ttu-id="52263-102">Windows PowerShell モジュールのヘルプを記述する</span><span class="sxs-lookup"><span data-stu-id="52263-102">Writing Help for Windows PowerShell Modules</span></span>

<span data-ttu-id="52263-103">Windows PowerShell モジュールには、モジュールに関するヘルプトピックや、コマンドレット、プロバイダー、関数、スクリプトなどのモジュールメンバーに関するヘルプトピックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="52263-103">Windows PowerShell modules can include Help topics about the module and about the module members, such as cmdlets, providers, functions and scripts.</span></span> <span data-ttu-id="52263-104">`Get-Help` コマンドレットは、他の Windows PowerShell 項目のヘルプを表示するのと同じ形式のモジュールヘルプトピックを表示し、ユーザーは標準の `Get-Help` コマンドを使用してヘルプトピックを取得します。</span><span class="sxs-lookup"><span data-stu-id="52263-104">The `Get-Help` cmdlet displays the module Help topics in the same format as it displays Help for other Windows PowerShell items, and users use standard `Get-Help` commands to get the Help topics.</span></span>

<span data-ttu-id="52263-105">このドキュメントでは、モジュールのヘルプトピックの形式と適切な配置について説明し、モジュールのヘルプコンテンツに関するガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="52263-105">This document explains the format and correct placement of module Help topics, and it suggests guidelines for module Help content.</span></span>

## <a name="types-of-module-help"></a><span data-ttu-id="52263-106">モジュールのヘルプの種類</span><span class="sxs-lookup"><span data-stu-id="52263-106">Types of Module Help</span></span>

<span data-ttu-id="52263-107">モジュールには、次の種類のヘルプを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="52263-107">A module can include the following types of Help.</span></span>

- <span data-ttu-id="52263-108">**コマンドレットのヘルプを参照**してください。</span><span class="sxs-lookup"><span data-stu-id="52263-108">**Cmdlet Help**.</span></span> <span data-ttu-id="52263-109">モジュール内のコマンドレットについて説明するヘルプトピックは、コマンドヘルプスキーマを使用する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="52263-109">The Help topics that describe cmdlets in a module are XML files that use the command help schema</span></span>

- <span data-ttu-id="52263-110">**プロバイダーのヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="52263-110">**Provider Help**.</span></span> <span data-ttu-id="52263-111">モジュール内のプロバイダーについて説明するヘルプトピックは、プロバイダーヘルプスキーマを使用する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="52263-111">The Help topics that describe providers in a module are XML files that use the provider help schema.</span></span>

- <span data-ttu-id="52263-112">**関数のヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="52263-112">**Function Help**.</span></span> <span data-ttu-id="52263-113">モジュール内の関数について説明するヘルプトピックは、関数内のコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることも、スクリプトまたはスクリプトモジュールで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="52263-113">The Help topics that describe functions in a module can be XML files that use the command help schema or comment-based Help topics within the function, or the script or script module</span></span>

- <span data-ttu-id="52263-114">**スクリプトのヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="52263-114">**Script Help**.</span></span> <span data-ttu-id="52263-115">モジュール内のスクリプトを記述するヘルプトピックは、スクリプトまたはスクリプトモジュールでコマンドヘルプスキーマまたはコメントベースのヘルプトピックを使用する XML ファイルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="52263-115">The Help topics that describe scripts in a module can be XML files that use the command help schema or comment-based Help topics in the script or script module.</span></span>

- <span data-ttu-id="52263-116">**概念 ("About") のヘルプ**。</span><span class="sxs-lookup"><span data-stu-id="52263-116">**Conceptual ("About") Help**.</span></span> <span data-ttu-id="52263-117">概念 ("about") ヘルプトピックを使用して、モジュールとそのメンバーを記述したり、メンバーを組み合わせてタスクを実行する方法を説明したりできます。</span><span class="sxs-lookup"><span data-stu-id="52263-117">You can use a conceptual ("about") Help topic to describe the module and its members and to explain how the members can be used together to perform tasks.</span></span> <span data-ttu-id="52263-118">概念説明ヘルプトピックは、Unicode (UTF-8) エンコードを使用したテキストファイルです。</span><span class="sxs-lookup"><span data-stu-id="52263-118">Conceptual Help topics are text files with Unicode (UTF-8) encoding.</span></span> <span data-ttu-id="52263-119">ファイル名には、about_MyModule などの `about_<name>.help.txt` 形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52263-119">The file name must use the `about_<name>.help.txt` format, such as about_MyModule.help.txt.</span></span> <span data-ttu-id="52263-120">既定では、Windows PowerShell には、次の例のように、これらの概念に関するヘルプトピックが100以上含まれています。</span><span class="sxs-lookup"><span data-stu-id="52263-120">By default, Windows PowerShell includes over 100 of these conceptual About Help topics, and they are formatted like the following example.</span></span>

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
      Text-only references for further reading. Hyperlinks cannot work in the Windows PowerShell console.

  ```

## <a name="placement-of-module-help"></a><span data-ttu-id="52263-121">モジュールヘルプの配置</span><span class="sxs-lookup"><span data-stu-id="52263-121">Placement of Module Help</span></span>

<span data-ttu-id="52263-122">`Get-Help` コマンドレットは、モジュールディレクトリの言語固有のサブディレクトリにあるモジュールヘルプトピックファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="52263-122">The `Get-Help` cmdlet looks for module Help topic files in language-specific subdirectories of the module directory.</span></span>

<span data-ttu-id="52263-123">たとえば、次のディレクトリ構造の図は、SampleModule モジュールのヘルプトピックの場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="52263-123">For example, the following directory structure diagram shows the location of the Help topics for the SampleModule module.</span></span>

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
> <span data-ttu-id="52263-124">この例では、 *\<ModulePath >* プレースホルダーは `PSModulePath` 環境変数内のいずれかのパス ($home \documents\modules、$pshome \ モジュール、ユーザーが指定したカスタムパスなど) を表します。</span><span class="sxs-lookup"><span data-stu-id="52263-124">In the example, the *\<ModulePath>* placeholder represents one of the paths in the `PSModulePath` environment variable, such as $home\Documents\Modules, $pshome\Modules, or a custom path that the user specifies.</span></span>

## <a name="getting-module-help"></a><span data-ttu-id="52263-125">モジュールのヘルプを取得する</span><span class="sxs-lookup"><span data-stu-id="52263-125">Getting Module Help</span></span>

<span data-ttu-id="52263-126">ユーザーがモジュールをセッションにインポートすると、そのモジュールのヘルプトピックがモジュールと共にセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="52263-126">When a user imports a module into a session, the Help topics for that module are imported into the session along with the module.</span></span> <span data-ttu-id="52263-127">モジュールマニフェストの FileList キーの値にヘルプトピックファイルを一覧表示することはできますが、ヘルプトピックは `Export-ModuleMember` コマンドレットの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="52263-127">You can list the Help topic files in the value of the FileList key in the module manifest, but Help topics are not affected by the `Export-ModuleMember` cmdlet.</span></span>

<span data-ttu-id="52263-128">さまざまな言語でモジュールのヘルプトピックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="52263-128">You can provide module Help topics in different languages.</span></span> <span data-ttu-id="52263-129">`Get-Help` コマンドレットは、コントロールパネルの [地域と言語のオプション] 項目で、現在のユーザーに対して指定されている言語のモジュールヘルプトピックを自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="52263-129">The `Get-Help` cmdlet automatically displays module Help topics in the language that is specified for the current user in the Regional and Language Options item in Control Panel.</span></span> <span data-ttu-id="52263-130">Windows Vista 以降のバージョンの Windows では、`Get-Help` は、Windows 用に設定された言語フォールバック標準に従って、モジュールディレクトリの言語固有のサブディレクトリにあるヘルプトピックを検索します。</span><span class="sxs-lookup"><span data-stu-id="52263-130">In Windows Vista and later versions of Windows, `Get-Help` searches for the Help topics in language-specific subdirectories of the module directory in accordance with the language fallback standards established for Windows.</span></span>

<span data-ttu-id="52263-131">Windows PowerShell 3.0 以降では、コマンドレットまたは関数に対して `Get-Help` コマンドを実行すると、モジュールの自動インポートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="52263-131">Beginning in Windows PowerShell 3.0, running a `Get-Help` command for a cmdlet or function triggers automatic importing of the module.</span></span> <span data-ttu-id="52263-132">`Get-Help` コマンドレットは、モジュールのヘルプトピックの内容をすぐに表示します。</span><span class="sxs-lookup"><span data-stu-id="52263-132">The `Get-Help` cmdlet immediately displays the contents of the help topics in the module.</span></span>

<span data-ttu-id="52263-133">モジュールにヘルプトピックが含まれておらず、ユーザーのコンピューターのモジュールのコマンドに関するヘルプトピックがない場合、`Get-Help` には自動生成されたヘルプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52263-133">If the module does not contain help topics and there are no help topics for the commands in the module on the user's computer, `Get-Help` displays auto-generated help.</span></span> <span data-ttu-id="52263-134">自動生成されたヘルプには、コマンドの構文、パラメーター、および入力と出力の型が含まれていますが、説明は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="52263-134">The auto-generated help includes the command syntax, parameters, and input and output types, but does not include any descriptions.</span></span> <span data-ttu-id="52263-135">自動生成されたヘルプには、`Update-Help` コマンドレットを使用して、インターネットまたはファイル共有からコマンドのヘルプをダウンロードするように指示するテキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="52263-135">The auto-generated help includes text that directs the user to try to use the `Update-Help` cmdlet to download help for the command from the Internet or a file share.</span></span> <span data-ttu-id="52263-136">また、`Get-Help` コマンドレットの**online**パラメーターを使用して、ヘルプトピックのオンラインバージョンを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="52263-136">It also recommends using the **Online** parameter of the `Get-Help` cmdlet to get the online version of the help topic.</span></span>

## <a name="supporting-updatable-help"></a><span data-ttu-id="52263-137">更新可能ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="52263-137">Supporting Updatable Help</span></span>

<span data-ttu-id="52263-138">Windows powershell 3.0 以降のバージョンの Windows PowerShell では、モジュールの更新されたヘルプファイルをインターネットまたはローカルファイル共有からダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="52263-138">Users of Windows PowerShell 3.0 and later versions of Windows PowerShell can download and install updated help files for a module from the Internet or from a local file share.</span></span> <span data-ttu-id="52263-139">`Update-Help` と `Save-Help` のコマンドレットにより、管理の詳細がユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="52263-139">The `Update-Help` and `Save-Help` cmdlets hide the management details from the user.</span></span> <span data-ttu-id="52263-140">ユーザーは `Update-Help` コマンドレットを実行した後、`Get-Help` コマンドレットを使用して、Windows PowerShell コマンドプロンプトでモジュールの最新のヘルプファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="52263-140">Users run the `Update-Help` cmdlet and then use the `Get-Help` cmdlet to read the newest help files for the module at the Windows PowerShell command prompt.</span></span> <span data-ttu-id="52263-141">ユーザーは、Windows または Windows PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="52263-141">Users do not need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="52263-142">ファイアウォールの背後にあるユーザーやインターネットにアクセスできないユーザーも、更新可能なヘルプを使用できます。</span><span class="sxs-lookup"><span data-stu-id="52263-142">Users behind firewalls and those without Internet access can use Updatable Help, as well.</span></span> <span data-ttu-id="52263-143">インターネットアクセス権を持つ管理者は、`Save-Help` コマンドレットを使用して、最新のヘルプファイルをダウンロードしてファイル共有にインストールします。</span><span class="sxs-lookup"><span data-stu-id="52263-143">Administrators with Internet access use the `Save-Help` cmdlet to download and install the newest help files to a file share.</span></span> <span data-ttu-id="52263-144">次に、`Update-Help` コマンドレットの**Path**パラメーターを使用して、ファイル共有から最新のヘルプファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="52263-144">Then, users use the **Path** parameter of the `Update-Help` cmdlet to get the newest help files from the file share.</span></span>

<span data-ttu-id="52263-145">モジュールの作成者は、モジュールにヘルプファイルを含めたり、更新可能なヘルプを使用してヘルプファイルを更新したり、モジュールからヘルプファイルを除外したり、更新可能なヘルプを使用してインストールしたり更新したりできます。</span><span class="sxs-lookup"><span data-stu-id="52263-145">Module authors can include help files in the module and use Updatable Help to update the help files, or omit help files from the module and use Updatable Help both to install and to update them.</span></span>

<span data-ttu-id="52263-146">更新可能なヘルプの詳細については、「[更新可能なヘルプのサポート](./supporting-updatable-help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52263-146">For more information about Updatable Help, see [Supporting Updatable Help](./supporting-updatable-help.md).</span></span>

## <a name="supporting-online-help"></a><span data-ttu-id="52263-147">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="52263-147">Supporting Online Help</span></span>

<span data-ttu-id="52263-148">更新されたヘルプファイルをコンピューターにインストールできない、またはインストールしないユーザーは、多くの場合、オンラインバージョンのモジュールヘルプトピックに依存しています。</span><span class="sxs-lookup"><span data-stu-id="52263-148">Users who cannot or do not install updated help files on their computers often rely on the online version of module help topics.</span></span> <span data-ttu-id="52263-149">`Get-Help` コマンドレットの**online**パラメーターは、既定のインターネットブラウザーでユーザーのコマンドレットまたは高度な関数のヘルプトピックのオンラインバージョンを開きます。</span><span class="sxs-lookup"><span data-stu-id="52263-149">The **Online** parameter of the `Get-Help` cmdlet opens the online version of a cmdlet or advanced function help topic for the user in their default Internet browser.</span></span>

<span data-ttu-id="52263-150">`Get-Help` コマンドレットは、コマンドレットまたは関数**の "/" プロパティの値**を使用して、ヘルプトピックのオンラインバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="52263-150">The `Get-Help` cmdlet uses the value of the **HelpUri** property of the cmdlet or function to find the online version of the help topic.</span></span>

<span data-ttu-id="52263-151">Windows PowerShell 3.0 以降では、コマンドレットと関数のヘルプトピックのオンラインバージョンを検索するために、コマンドレットクラスまたはコマンドレット**バインド**属性の **"/" プロパティ**を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="52263-151">Beginning in Windows PowerShell 3.0, you can help users find the online version of cmdlet and function help topics by defining the HelpUri attribute on the cmdlet class or the **HelpUri** property of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="52263-152">属性の値は、コマンドレットまたは関数のすべて**のプロパティの**値です。</span><span class="sxs-lookup"><span data-stu-id="52263-152">The value of the attribute is the value of the **HelpUri** property of the cmdlet or function.</span></span>

<span data-ttu-id="52263-153">詳細については、「[オンラインヘルプのサポート](./supporting-online-help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52263-153">For more information, see [Supporting Online Help](./supporting-online-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52263-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="52263-154">See Also</span></span>

[<span data-ttu-id="52263-155">Windows PowerShell モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="52263-155">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="52263-156">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="52263-156">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)

[<span data-ttu-id="52263-157">オンラインヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="52263-157">Supporting Online Help</span></span>](./supporting-online-help.md)
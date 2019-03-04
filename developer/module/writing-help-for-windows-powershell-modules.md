---
title: Windows PowerShell モジュールのヘルプの記述 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b58fa5-01bc-426c-a043-5c700d6578e9
caps.latest.revision: 16
ms.openlocfilehash: 443bf5f693d2ab161668de25a1097347826cb5c2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854068"
---
# <a name="writing-help-for-windows-powershell-modules"></a><span data-ttu-id="170f7-102">Windows PowerShell モジュールのヘルプを記述する</span><span class="sxs-lookup"><span data-stu-id="170f7-102">Writing Help for Windows PowerShell Modules</span></span>

<span data-ttu-id="170f7-103">Windows PowerShell モジュールには、モジュールとコマンドレット、プロバイダー、関数およびスクリプトなど、モジュール メンバーについてのヘルプ トピックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="170f7-103">Windows PowerShell modules can include Help topics about the module and about the module members, such as cmdlets, providers, functions and scripts.</span></span> <span data-ttu-id="170f7-104">`Get-Help` 、他の Windows PowerShell 項目のヘルプが表示され、ユーザーが標準を使用、コマンドレットに同じ形式でモジュールのヘルプ トピックが表示されます`Get-Help`ヘルプ トピックを取得するコマンド。</span><span class="sxs-lookup"><span data-stu-id="170f7-104">The `Get-Help` cmdlet displays the module Help topics in the same format as it displays Help for other Windows PowerShell items, and users use standard `Get-Help` commands to get the Help topics.</span></span>

<span data-ttu-id="170f7-105">このドキュメントは、形式とモジュールのヘルプ トピックの正しい配置について説明し、モジュールのヘルプ コンテンツに関するガイドラインが推奨されています。</span><span class="sxs-lookup"><span data-stu-id="170f7-105">This document explains the format and correct placement of module Help topics, and it suggests guidelines for module Help content.</span></span>

## <a name="types-of-module-help"></a><span data-ttu-id="170f7-106">種類のモジュールのヘルプ</span><span class="sxs-lookup"><span data-stu-id="170f7-106">Types of Module Help</span></span>

<span data-ttu-id="170f7-107">モジュールは、次の種類のヘルプを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="170f7-107">A module can include the following types of Help.</span></span>

- <span data-ttu-id="170f7-108">**コマンドレットのヘルプ**します。</span><span class="sxs-lookup"><span data-stu-id="170f7-108">**Cmdlet Help**.</span></span> <span data-ttu-id="170f7-109">モジュールのコマンドレットを説明するヘルプ トピックは、コマンドを使用する XML ファイルのスキーマのヘルプ</span><span class="sxs-lookup"><span data-stu-id="170f7-109">The Help topics that describe cmdlets in a module are XML files that use the command help schema</span></span>

- <span data-ttu-id="170f7-110">**プロバイダーのヘルプ**します。</span><span class="sxs-lookup"><span data-stu-id="170f7-110">**Provider Help**.</span></span> <span data-ttu-id="170f7-111">モジュール内のプロバイダーについて説明するヘルプ トピックは、プロバイダーを使用する XML ファイルがスキーマを支援します。</span><span class="sxs-lookup"><span data-stu-id="170f7-111">The Help topics that describe providers in a module are XML files that use the provider help schema.</span></span>

- <span data-ttu-id="170f7-112">**関数のヘルプ**します。</span><span class="sxs-lookup"><span data-stu-id="170f7-112">**Function Help**.</span></span> <span data-ttu-id="170f7-113">モジュールの関数を説明するヘルプ トピックは、コマンドを使用する XML ファイルのスキーマまたは関数、または、スクリプトまたはスクリプト モジュール内のヘルプ トピックのコメント ベースのヘルプ</span><span class="sxs-lookup"><span data-stu-id="170f7-113">The Help topics that describe functions in a module can be XML files that use the command help schema or comment-based Help topics within the function, or the script or script module</span></span>

- <span data-ttu-id="170f7-114">**スクリプトのヘルプ**します。</span><span class="sxs-lookup"><span data-stu-id="170f7-114">**Script Help**.</span></span> <span data-ttu-id="170f7-115">モジュール内のスクリプトを説明するヘルプ トピックでは、コマンドを使用する XML ファイルのスキーマまたはスクリプトまたはスクリプト モジュールのヘルプ トピックのコメント ベースのヘルプを指定できます。</span><span class="sxs-lookup"><span data-stu-id="170f7-115">The Help topics that describe scripts in a module can be XML files that use the command help schema or comment-based Help topics in the script or script module.</span></span>

- <span data-ttu-id="170f7-116">**(「About」) ヘルプ概念**します。</span><span class="sxs-lookup"><span data-stu-id="170f7-116">**Conceptual ("About") Help**.</span></span> <span data-ttu-id="170f7-117">モジュールとそのメンバーについて説明し、タスクを実行するメンバーを組み合わせて使用する方法について説明に (「about」) ヘルプ トピックの概念を使用できます。 します</span><span class="sxs-lookup"><span data-stu-id="170f7-117">You can use a conceptual ("about") Help topic to describe the module and its members and to explain how the members can be used together to perform tasks.</span></span> <span data-ttu-id="170f7-118">概念説明ヘルプ トピックは、Unicode (utf-8) エンコーディングを持つテキスト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="170f7-118">Conceptual Help topics are text files with Unicode (UTF-8) encoding.</span></span> <span data-ttu-id="170f7-119">ファイル名を使用する必要があります、 `about_<name>.help.txt` about_MyModule.help.txt などの形式。</span><span class="sxs-lookup"><span data-stu-id="170f7-119">The file name must use the `about_<name>.help.txt` format, such as about_MyModule.help.txt.</span></span> <span data-ttu-id="170f7-120">既定では、Windows PowerShell にはこれらの概念に関するヘルプ トピック、100 を超えると、次の例のように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="170f7-120">By default, Windows PowerShell includes over 100 of these conceptual About Help topics, and they are formatted like the following example.</span></span>

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

## <a name="placement-of-module-help"></a><span data-ttu-id="170f7-121">モジュールのヘルプの配置</span><span class="sxs-lookup"><span data-stu-id="170f7-121">Placement of Module Help</span></span>

<span data-ttu-id="170f7-122">`Get-Help`コマンドレットは、モジュール ディレクトリの言語固有のサブディレクトリでモジュールのヘルプ トピック ファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="170f7-122">The `Get-Help` cmdlet looks for module Help topic files in language-specific subdirectories of the module directory.</span></span>

<span data-ttu-id="170f7-123">たとえば、次のディレクトリ構造の図は、SampleModule モジュールのヘルプ トピックの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="170f7-123">For example, the following directory structure diagram shows the location of the Help topics for the SampleModule module.</span></span>

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
> <span data-ttu-id="170f7-124">この例で、  *\<ModulePath >* パスのいずれかを表すプレース ホルダー、 `PSModulePath` $home\Documents\Modules や $pshome \modules、ユーザーが指定したカスタム パスなどの環境変数。</span><span class="sxs-lookup"><span data-stu-id="170f7-124">In the example, the *\<ModulePath>* placeholder represents one of the paths in the `PSModulePath` environment variable, such as $home\Documents\Modules, $pshome\Modules, or a custom path that the user specifies.</span></span>

## <a name="getting-module-help"></a><span data-ttu-id="170f7-125">モジュールのヘルプの取得</span><span class="sxs-lookup"><span data-stu-id="170f7-125">Getting Module Help</span></span>

<span data-ttu-id="170f7-126">ユーザーがセッションにモジュールをインポート、ときに、そのモジュールのヘルプ トピックは、モジュールとのセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="170f7-126">When a user imports a module into a session, the Help topics for that module are imported into the session along with the module.</span></span> <span data-ttu-id="170f7-127">モジュール マニフェストに FileList キーの値でヘルプ トピック ファイルを一覧表示できますが、ヘルプ トピックの影響を受けない、`Export-ModuleMember`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="170f7-127">You can list the Help topic files in the value of the FileList key in the module manifest, but Help topics are not affected by the `Export-ModuleMember` cmdlet.</span></span>

<span data-ttu-id="170f7-128">異なる言語でモジュールのヘルプ トピックを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="170f7-128">You can provide module Help topics in different languages.</span></span> <span data-ttu-id="170f7-129">`Get-Help`コマンドレットは、コントロール パネルの 地域と言語のオプション項目の現在のユーザーに対して指定されている言語でのモジュールのヘルプ トピックを自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="170f7-129">The `Get-Help` cmdlet automatically displays module Help topics in the language that is specified for the current user in the Regional and Language Options item in Control Panel.</span></span> <span data-ttu-id="170f7-130">Windows Vista および以降のバージョンの Windows、 `Get-Help` Windows 用に確立された言語フォールバック標準に従って、モジュール ディレクトリの言語固有のサブディレクトリにヘルプ トピックを検索します。</span><span class="sxs-lookup"><span data-stu-id="170f7-130">In Windows Vista and later versions of Windows, `Get-Help` searches for the Help topics in language-specific subdirectories of the module directory in accordance with the language fallback standards established for Windows.</span></span>

<span data-ttu-id="170f7-131">実行している Windows PowerShell 3.0 以降では、`Get-Help`コマンドレットまたは関数のコマンドは、モジュールの自動インポートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="170f7-131">Beginning in Windows PowerShell 3.0, running a `Get-Help` command for a cmdlet or function triggers automatic importing of the module.</span></span> <span data-ttu-id="170f7-132">`Get-Help`コマンドレットは、モジュール内のヘルプ トピックの内容をすぐに表示します。</span><span class="sxs-lookup"><span data-stu-id="170f7-132">The `Get-Help` cmdlet immediately displays the contents of the help topics in the module.</span></span>

<span data-ttu-id="170f7-133">モジュールにヘルプ トピックが含まれていないと、ユーザーのコンピューターには、モジュール内のコマンドのヘルプ トピックがない場合`Get-Help`自動生成されたヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="170f7-133">If the module does not contain help topics and there are no help topics for the commands in the module on the user's computer, `Get-Help` displays auto-generated help.</span></span> <span data-ttu-id="170f7-134">自動生成されたヘルプは、コマンド構文、パラメーター、および入力と出力の型が含まれていますが、任意の説明には含まれません。</span><span class="sxs-lookup"><span data-stu-id="170f7-134">The auto-generated help includes the command syntax, parameters, and input and output types, but does not include any descriptions.</span></span> <span data-ttu-id="170f7-135">自動生成されたヘルプには使用しようとするユーザーを誘導するテキストが含まれています、`Update-Help`にインターネットまたはファイル共有から、コマンドのヘルプをダウンロードするコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="170f7-135">The auto-generated help includes text that directs the user to try to use the `Update-Help` cmdlet to download help for the command from the Internet or a file share.</span></span> <span data-ttu-id="170f7-136">使用することをお勧めすることも、**オンライン**のパラメーター、`Get-Help`コマンドレット ヘルプ トピックのオンライン バージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="170f7-136">It also recommends using the **Online** parameter of the `Get-Help` cmdlet to get the online version of the help topic.</span></span>

## <a name="supporting-updatable-help"></a><span data-ttu-id="170f7-137">更新可能ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="170f7-137">Supporting Updatable Help</span></span>

<span data-ttu-id="170f7-138">Windows PowerShell 3.0 のユーザーと以降のバージョンの Windows PowerShell は、ダウンロードして、モジュールの更新されたヘルプ ファイルをインターネットまたはローカルのファイル共有からインストールします。</span><span class="sxs-lookup"><span data-stu-id="170f7-138">Users of Windows PowerShell 3.0 and later versions of Windows PowerShell can download and install updated help files for a module from the Internet or from a local file share.</span></span> <span data-ttu-id="170f7-139">`Update-Help`と`Save-Help`コマンドレットは、ユーザーからの管理の詳細を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="170f7-139">The `Update-Help` and `Save-Help` cmdlets hide the management details from the user.</span></span> <span data-ttu-id="170f7-140">ユーザーが実行、`Update-Help`コマンドレットしを使用して、`Get-Help`コマンドレットを Windows PowerShell コマンド プロンプトで、モジュールの最新のヘルプ ファイルを読み取る。</span><span class="sxs-lookup"><span data-stu-id="170f7-140">Users run the `Update-Help` cmdlet and then use the `Get-Help` cmdlet to read the newest help files for the module at the Windows PowerShell command prompt.</span></span> <span data-ttu-id="170f7-141">ユーザーは、Windows または Windows PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="170f7-141">Users do not need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="170f7-142">ファイアウォールとインターネットへのアクセスなしの背後にあるユーザーも使用できます、更新可能なヘルプします。</span><span class="sxs-lookup"><span data-stu-id="170f7-142">Users behind firewalls and those without Internet access can use Updatable Help, as well.</span></span> <span data-ttu-id="170f7-143">インターネットと管理者のアクセスの使用、`Save-Help`コマンドレットをダウンロードしてファイル共有に最新のヘルプ ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="170f7-143">Administrators with Internet access use the `Save-Help` cmdlet to download and install the newest help files to a file share.</span></span> <span data-ttu-id="170f7-144">次に、ユーザーが使用して、**パス**のパラメーター、`Update-Help`ファイル共有から最新のヘルプ ファイルを取得するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="170f7-144">Then, users use the **Path** parameter of the `Update-Help` cmdlet to get the newest help files from the file share.</span></span>

<span data-ttu-id="170f7-145">モジュールの作成者は、モジュールのヘルプ ファイルを含めるし、更新可能なヘルプを使用して、ヘルプ ファイルを更新またはモジュールからヘルプ ファイルを省略し、インストールして、それらを更新する更新可能なヘルプを使用、します。</span><span class="sxs-lookup"><span data-stu-id="170f7-145">Module authors can include help files in the module and use Updatable Help to update the help files, or omit help files from the module and use Updatable Help both to install and to update them.</span></span>

<span data-ttu-id="170f7-146">更新可能なヘルプについては、次を参照してください。[更新可能なヘルプをサポートしている](./supporting-updatable-help.md)します。</span><span class="sxs-lookup"><span data-stu-id="170f7-146">For more information about Updatable Help, see [Supporting Updatable Help](./supporting-updatable-help.md).</span></span>

## <a name="supporting-online-help"></a><span data-ttu-id="170f7-147">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="170f7-147">Supporting Online Help</span></span>

<span data-ttu-id="170f7-148">インストールしないことはできません、またはユーザーには、自分のコンピューター上のファイルは、多くの場合、モジュールのヘルプ トピックのオンライン バージョンに依存のヘルプが更新されます。</span><span class="sxs-lookup"><span data-stu-id="170f7-148">Users who cannot or do not install updated help files on their computers often rely on the online version of module help topics.</span></span> <span data-ttu-id="170f7-149">**オンライン**のパラメーター、`Get-Help`コマンドレットは、既定のインターネット ブラウザーでコマンドレットまたはユーザーの高度な関数のヘルプ トピックのオンライン バージョンを開きます。</span><span class="sxs-lookup"><span data-stu-id="170f7-149">The **Online** parameter of the `Get-Help` cmdlet opens the online version of a cmdlet or advanced function help topic for the user in their default Internet browser.</span></span>

<span data-ttu-id="170f7-150">`Get-Help`コマンドレットの値を使用して、 **HelpUri**コマンドレットまたは関数には、ヘルプ トピックのオンライン バージョンの検索のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="170f7-150">The `Get-Help` cmdlet uses the value of the **HelpUri** property of the cmdlet or function to find the online version of the help topic.</span></span>

<span data-ttu-id="170f7-151">Windows PowerShell 3.0 以降で、コマンドレット クラスで HelpUri 属性を定義することで、コマンドレットと関数のヘルプ トピックのオンライン バージョンを検索するユーザーを支援することができます、または**HelpUri**のプロパティ、 **CmdletBinding**属性。</span><span class="sxs-lookup"><span data-stu-id="170f7-151">Beginning in Windows PowerShell 3.0, you can help users find the online version of cmdlet and function help topics by defining the HelpUri attribute on the cmdlet class or the **HelpUri** property of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="170f7-152">属性の値は、の値、 **HelpUri**コマンドレットまたは関数のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="170f7-152">The value of the attribute is the value of the **HelpUri** property of the cmdlet or function.</span></span>

<span data-ttu-id="170f7-153">詳細については、次を参照してください。[オンライン ヘルプのサポート](./supporting-online-help.md)します。</span><span class="sxs-lookup"><span data-stu-id="170f7-153">For more information, see [Supporting Online Help](./supporting-online-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="170f7-154">参照</span><span class="sxs-lookup"><span data-stu-id="170f7-154">See Also</span></span>

[<span data-ttu-id="170f7-155">Windows PowerShell モジュールの記述</span><span class="sxs-lookup"><span data-stu-id="170f7-155">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="170f7-156">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="170f7-156">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)

[<span data-ttu-id="170f7-157">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="170f7-157">Supporting Online Help</span></span>](./supporting-online-help.md)
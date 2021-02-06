---
description: PowerShell の更新可能なヘルプシステムについて説明します。
Locale: en-US
ms.date: 08/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_updatable_help?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Updatable_Help
ms.openlocfilehash: d688448b5aab8ec35ab5d57b444ad9902b8e8ecd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601424"
---
# <a name="about-updatable-help"></a><span data-ttu-id="a60e4-103">更新可能なヘルプについて</span><span class="sxs-lookup"><span data-stu-id="a60e4-103">About Updatable Help</span></span>

## <a name="short-description"></a><span data-ttu-id="a60e4-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="a60e4-104">Short description</span></span>
<span data-ttu-id="a60e4-105">PowerShell の更新可能なヘルプシステムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-105">Describes the updatable help system in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a60e4-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="a60e4-106">Long description</span></span>

<span data-ttu-id="a60e4-107">Powershell には、PowerShell コマンドレットと概念に関する最新のヘルプトピックにアクセスするためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a60e4-107">PowerShell provides several different ways to access the most up-to-date help topics for PowerShell cmdlets and concepts.</span></span>

<span data-ttu-id="a60e4-108">PowerShell 3.0 で導入された更新可能なヘルプシステムは、コマンドラインから読み取ることができるように、ローカルコンピューターに常に最新のヘルプトピックがあることを保証するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a60e4-108">The Updatable Help system, introduced in PowerShell 3.0, is designed to assure that you always have the newest help topics on your local computer so that you can read them at the command line.</span></span> <span data-ttu-id="a60e4-109">これにより、ヘルプファイルをダウンロードしてインストールしたり、新しいヘルプファイルが使用可能になるたびに更新したりすることが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="a60e4-109">It makes it easy to download and install help files and to update them whenever newer help files become available.</span></span>

<span data-ttu-id="a60e4-110">企業内の複数のコンピューター、およびインターネットにアクセスできないコンピューターの更新されたヘルプを提供するために、更新可能なヘルプを使用して、ファイルシステムディレクトリまたはファイル共有にヘルプファイルをダウンロードし、ファイル共有からヘルプファイルをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-110">To provide updated help for multiple computers in an enterprise and for computers that do not have access to the internet, Updatable Help lets you download help files to a filesystem directory or file share, and then install the help files from the file share.</span></span>

<span data-ttu-id="a60e4-111">PowerShell 4.0 では、 **Helpinfouri** プロパティは Windows PowerShell リモート処理を介して保持されます。これにより、は `Save-Help` リモートコンピューターにインストールされているモジュールで動作しますが、必ずしもローカルコンピューターにインストールされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-111">In PowerShell 4.0, the **HelpInfoUri** property is preserved over Windows PowerShell remoting, which allows `Save-Help` to work for modules that are installed on a remote computer, but are not necessarily installed on the local computer.</span></span> <span data-ttu-id="a60e4-112">インターネットにアクセスできないコンピューター上でを実行して、 **PSModuleInfo** オブジェクトをディスクまたはリムーバブルメディア (USB ドライブなど) に保存することができます。その場合、 `Export-Clixml` インターネットにアクセスできるコンピューターに **PSModuleInfo** オブジェクトをインポートし、 `Save-Help` **PSModuleInfo** オブジェクトで実行します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-112">You can save a **PSModuleInfo** object to disk or removable media (such as a USB drive) by running `Export-Clixml` on a computer that does not have internet access, importing the **PSModuleInfo** object on a computer that does have internet access, and then running `Save-Help` on the **PSModuleInfo** object.</span></span> <span data-ttu-id="a60e4-113">保存されているヘルプは、リムーバブルメディアを使用してリモートの切断されたコンピューターにコピーしてから、を実行してインストールすることができ `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-113">The saved help can be copied to the remote, disconnected computer by using removable media, and then installed by running `Update-Help`.</span></span> <span data-ttu-id="a60e4-114">これらの機能強化により、 `Save-Help` ネットワークアクセスのないコンピューターにヘルプをインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a60e4-114">These improvements in `Save-Help` functionality let you install help on computers that are without any kind of network access.</span></span> <span data-ttu-id="a60e4-115">新しい機能を使用する方法の例につい `Save-Help` ては、このトピックの「 [ファイル共有からヘルプを更新する方法](#how-to-update-help-from-a-file-share) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a60e4-115">For an example of how to use the new `Save-Help` functionality, see [How to update help from a file share](#how-to-update-help-from-a-file-share) in this topic.</span></span>

<span data-ttu-id="a60e4-116">更新可能なヘルプは、コンピューター上にヘルプファイルがない場合でも、最新のヘルプトピックへのオンラインアクセスとコマンドレットの基本的なヘルプをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-116">Updatable Help also supports online access to the newest help topics and basic help for cmdlets, even when there are no help files on the computer.</span></span>

<span data-ttu-id="a60e4-117">PowerShell 3.0 にはヘルプファイルが付属していません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-117">PowerShell 3.0 does not come with Help files.</span></span> <span data-ttu-id="a60e4-118">更新可能なヘルプ機能を使用して、PowerShell およびすべての Windows モジュールに既定で含まれているすべてのコマンドのヘルプファイルをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-118">You can use the Updatable Help feature to install the help files for all of the commands that are included by default in PowerShell and for all Windows modules.</span></span>

## <a name="updatable-help-cmdlets"></a><span data-ttu-id="a60e4-119">更新可能なヘルプコマンドレット</span><span class="sxs-lookup"><span data-stu-id="a60e4-119">Updatable help cmdlets</span></span>

- <span data-ttu-id="a60e4-120">`Update-Help`: インターネットまたはファイル共有から最新のヘルプファイルをダウンロードし、ローカルコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-120">`Update-Help`: Downloads the newest help files from the internet or a file share, and installs them on the local computer.</span></span>

- <span data-ttu-id="a60e4-121">`Save-Help`: インターネットから最新のヘルプファイルをダウンロードし、ファイルシステムディレクトリまたはファイル共有に保存します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-121">`Save-Help`: Downloads the newest help files from the internet and saves them in a filesystem directory or file share.</span></span> <span data-ttu-id="a60e4-122">ヘルプファイルをコンピューターにインストールするには、を使用 `Update-Help` します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-122">To install the help files on computers, use `Update-Help`.</span></span>

- <span data-ttu-id="a60e4-123">`Get-Help`: コマンドラインにヘルプトピックを表示します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-123">`Get-Help`: Displays help topics at the command line.</span></span> <span data-ttu-id="a60e4-124">コンピューター上のヘルプファイルからヘルプを取得します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-124">Gets help from the help files on the computer.</span></span> <span data-ttu-id="a60e4-125">ヘルプファイルのないコマンドレットと関数の自動生成されたヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-125">Displays auto-generated help for cmdlets and functions that do not have help files.</span></span> <span data-ttu-id="a60e4-126">既定のインターネットブラウザーでコマンドレット、関数、スクリプト、およびワークフローのオンラインヘルプトピックを開きます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-126">Opens online help topics for cmdlets, functions, scripts, and workflows in your default internet browser.</span></span>

## <a name="auto-generated-help-help-without-help-files"></a><span data-ttu-id="a60e4-127">自動生成ヘルプ: ヘルプファイルなしのヘルプ</span><span class="sxs-lookup"><span data-stu-id="a60e4-127">Auto-generated help: help without help files</span></span>

<span data-ttu-id="a60e4-128">コマンドレット、関数、またはワークフローのヘルプファイルがコンピューター上にない場合、 `Get-Help` コマンドレットは自動生成されたヘルプを表示し、ヘルプファイルをダウンロードするか、オンラインで読み取るかを確認するメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-128">If you do not have the help file for a cmdlet, function, or workflow on the computer, the `Get-Help` cmdlet displays auto-generated help and prompts you to download the help files or read them online.</span></span>

<span data-ttu-id="a60e4-129">自動生成されたヘルプには、構文とエイリアス、および更新可能なヘルプコマンドレットの使用方法とオンラインヘルプトピックへのアクセス方法を説明するコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a60e4-129">Auto-generated help includes syntax and aliases, and remarks that explain how to use the Updatable Help cmdlets and to access the online help topics.</span></span>

<span data-ttu-id="a60e4-130">たとえば、次のコマンドは、コマンドレットの基本的なヘルプを取得し `Get-Culture` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-130">For example, the following command gets basic help for the `Get-Culture` cmdlet.</span></span> <span data-ttu-id="a60e4-131">出力には、 `Get-Help` コンピューターにヘルプファイルがない場合の表示が示されます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-131">The output shows the `Get-Help` display when there are no help files on the computer.</span></span>

```powershell
Get-Help Get-Culture
```

```output
NAME
    Get-Culture

SYNTAX
    Get-Culture [<CommonParameters>]

ALIASES
    None

REMARKS
    To get the latest Help content including descriptions and examples
    type: Update-Help.
```

## <a name="help-files-for-modules"></a><span data-ttu-id="a60e4-132">モジュールのヘルプファイル</span><span class="sxs-lookup"><span data-stu-id="a60e4-132">Help files for modules</span></span>

<span data-ttu-id="a60e4-133">更新可能なヘルプの最小単位は、モジュールのヘルプです。</span><span class="sxs-lookup"><span data-stu-id="a60e4-133">The smallest unit of Updatable Help is help for a module.</span></span> <span data-ttu-id="a60e4-134">モジュールヘルプには、モジュールのすべてのコマンドレット、関数、ワークフロー、プロバイダー、スクリプト、および概念のヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a60e4-134">Module help includes help for all of the cmdlets, functions, workflows, providers, scripts, and concepts in a module.</span></span> <span data-ttu-id="a60e4-135">現在のセッションにインポートされていない場合でも、コンピューターにインストールされているすべてのモジュールのヘルプを更新できます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-135">You can update help for all modules that are installed on the computer, even if they are not imported into the current session.</span></span>

<span data-ttu-id="a60e4-136">モジュール全体のヘルプを更新できますが、個々のコマンドレットのヘルプは更新できません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-136">You can update help for the entire module, but you cannot update help for individual cmdlets.</span></span>

<span data-ttu-id="a60e4-137">特定のコマンドレットを含むモジュールを見つけるには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-137">To find the module that contains a particular cmdlet, use the following command format:</span></span>

```powershell
(Get-Command <cmdlet-name>).ModuleName
```

<span data-ttu-id="a60e4-138">たとえば、コマンドレットを含むモジュールを検索するには、次のように `Set-ExecutionPolicy` 入力します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-138">For example, to find the module that contains the `Set-ExecutionPolicy` cmdlet, type:</span></span>

```powershell
(Get-Command Set-ExecutionPolicy).ModuleName
```

<span data-ttu-id="a60e4-139">特定のモジュールのヘルプを更新するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-139">To update help for a particular module, type:</span></span>

```powershell
Update-Help -Module <ModuleName>
```

<span data-ttu-id="a60e4-140">たとえば、Set-ExecutionPolicy コマンドレットを含むモジュールのヘルプを更新するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-140">For example, to update help for the module that contains the Set-ExecutionPolicy cmdlet, type:</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Security
```

## <a name="permissions-for-updatable-help"></a><span data-ttu-id="a60e4-141">更新可能なヘルプのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a60e4-141">Permissions for updatable help</span></span>

<span data-ttu-id="a60e4-142">ディレクトリ内のモジュールのヘルプを更新するに `$pshome/Modules` は、コンピューターの Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a60e4-142">To update help for the modules in the directory `$pshome/Modules`, you must be member of the Administrators group on the computer.</span></span>

<span data-ttu-id="a60e4-143">Administrators グループのメンバーでない場合は、これらのモジュールのヘルプを更新することはできません。しかし、インターネットにアクセスできる場合は、オンラインでヘルプを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-143">If you are not a member of the Administrators group, you cannot update help for these modules; but if you have internet access, you can view help online.</span></span>

<span data-ttu-id="a60e4-144">ディレクトリ `$home/Documents/PowerShell/Modules` またはディレクトリの他のサブディレクトリ内のモジュールのヘルプを更新 `$home` するには、特別なアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-144">Updating help for modules in the directory `$home/Documents/PowerShell/Modules` or modules in other subdirectories of the `$home` directory does not require special permissions.</span></span>

<span data-ttu-id="a60e4-145">`Update-Help`およびコマンドレットには、 `Save-Help` 現在のユーザーの明示的な資格情報を提供する **UseDefaultCredentials** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="a60e4-145">The `Update-Help` and `Save-Help` cmdlets have a **UseDefaultCredentials** parameter that provides the explicit credentials of the current user.</span></span> <span data-ttu-id="a60e4-146">このパラメーターは、セキュリティで保護されたインターネット上の場所にアクセスするために設計されて</span><span class="sxs-lookup"><span data-stu-id="a60e4-146">This parameter is designed for accessing secure internet locations.</span></span>

<span data-ttu-id="a60e4-147">`Update-Help`およびコマンドレットには、 `Save-Help` リモートコンピューターでコマンドを実行し、3番目のコンピューターのファイル共有にアクセスするための **資格情報** パラメーターもあります。</span><span class="sxs-lookup"><span data-stu-id="a60e4-147">The `Update-Help` and `Save-Help` cmdlets also have a **Credential** parameter that allows you to run the command on a remote computer and access a file share on a third computer.</span></span> <span data-ttu-id="a60e4-148">**Credential** パラメーターは、の SourcePath パラメーターまたは **LiteralPath** パラメーター、 `Update-Help` およびの **DestinationPath** パラメーターまたは **LiteralPath** パラメーターを使用する場合にのみ有効です `Save-Help` 。</span><span class="sxs-lookup"><span data-stu-id="a60e4-148">The **Credential** parameter is valid only when you use the SourcePath or **LiteralPath** parameters of `Update-Help` and the **DestinationPath** or **LiteralPath** parameters of `Save-Help`.</span></span>

## <a name="how-to-install-and-update-help-files"></a><span data-ttu-id="a60e4-149">ヘルプファイルをインストールおよび更新する方法</span><span class="sxs-lookup"><span data-stu-id="a60e4-149">How to install and update help files</span></span>

<span data-ttu-id="a60e4-150">ヘルプファイルを初めてダウンロードしてインストールする場合、またはコンピューター上のヘルプファイルを更新する場合は、コマンドレットを使用し `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-150">To download and install help files for the first time, or to update the help files on your computer, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="a60e4-151">`Update-Help`コマンドレットは、次のタスクを含む、すべてのハード機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-151">The `Update-Help` cmdlet does all of the hard work for you, including the following tasks.</span></span>

- <span data-ttu-id="a60e4-152">更新可能なヘルプをサポートするモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-152">Determines which modules support Updatable Help.</span></span>
- <span data-ttu-id="a60e4-153">各モジュールが更新可能なヘルプファイルを格納するインターネット上の場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-153">Finds the internet location where each module stores its Updatable Help files.</span></span>
- <span data-ttu-id="a60e4-154">コンピューター上の各モジュールのヘルプファイルを、各モジュールで使用可能な最新のヘルプファイルと比較します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-154">Compares the help files for each module on your computer to the newest help files that are available for each module.</span></span>
- <span data-ttu-id="a60e4-155">インターネットから新しいファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-155">Downloads the new files from the internet.</span></span>
- <span data-ttu-id="a60e4-156">ヘルプファイルパッケージのラップを解除します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-156">Unwraps the help file package.</span></span>
- <span data-ttu-id="a60e4-157">ファイルが有効なヘルプファイルであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-157">Verifies that the files are valid help files.</span></span>
- <span data-ttu-id="a60e4-158">モジュールディレクトリの言語固有のサブディレクトリにヘルプファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-158">Installs the help files in the language-specific subdirectory of the module directory.</span></span>

<span data-ttu-id="a60e4-159">新しいヘルプトピックにアクセスするには、 `Get-Help` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-159">To access the new help topics, use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="a60e4-160">PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-160">You do not need to restart PowerShell.</span></span>

<span data-ttu-id="a60e4-161">更新可能なヘルプをサポートするコンピュータ上のすべてのモジュールのヘルプをインストールまたは更新するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-161">To install or update help for all modules on the computer that supports Updatable Help, type:</span></span>

```powershell
Update-Help
```

<span data-ttu-id="a60e4-162">特定のモジュールのヘルプを更新するには、の **Module** パラメーターを追加し `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-162">To update help for particular modules, add the **Module** parameter of `Update-Help`.</span></span> <span data-ttu-id="a60e4-163">モジュール名にはワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-163">Wildcard characters are permitted in the module name.</span></span>

<span data-ttu-id="a60e4-164">たとえば、ServerManager モジュールのヘルプを更新するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-164">For example, to update help for the ServerManager module, type:</span></span>

```powershell
Update-Help -Module ServerManager
```

<span data-ttu-id="a60e4-165">パラメーターを指定しない場合、は、 `Update-Help` セッション内のすべてのモジュールと、更新可能なヘルプをサポートするすべてのインストール済みモジュールのヘルプを更新します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-165">Without parameters, `Update-Help` updates help for all modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="a60e4-166">これを含めるには、PSModulePath 環境変数の値に示されているディレクトリにモジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a60e4-166">To be included, modules must be installed in directories that are listed in the value of the PSModulePath environment variable.</span></span> <span data-ttu-id="a60e4-167">これらは、"Get-help-ListAvailable" コマンドによって返されるモジュールでもあります。</span><span class="sxs-lookup"><span data-stu-id="a60e4-167">These are also modules that are returned by a "Get-Help -ListAvailable" command.</span></span>

<span data-ttu-id="a60e4-168">**Module** パラメーターの値が `*` (すべて) の場合、では、更新 `Update-Help` 可能なヘルプをサポートしていないモジュールを含め、インストールされているすべてのモジュールのヘルプを更新しようとします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-168">If the value of the **Module** parameter is `*` (all), `Update-Help` attempts to update help for all installed modules, including modules that do not support Updatable Help.</span></span> <span data-ttu-id="a60e4-169">このコマンドは、通常、更新可能なヘルプをサポートしていないモジュールをコマンドレットが検出したときに多くのエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-169">This command typically generates many errors as the cmdlet encounters modules that do not support Updatable Help.</span></span>

## <a name="how-to-update-help-from-a-file-share"></a><span data-ttu-id="a60e4-170">ファイル共有からヘルプを更新する方法</span><span class="sxs-lookup"><span data-stu-id="a60e4-170">How to update help from a file share</span></span>

<span data-ttu-id="a60e4-171">インターネットに接続されていないコンピューターをサポートする、または企業内での更新を制御または合理化するには、コマンドレットを使用し `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-171">To support computers that are not connected to the internet, or to control or streamline help updating in an enterprise, use the `Save-Help` cmdlet.</span></span> <span data-ttu-id="a60e4-172">`Save-Help`コマンドレットは、インターネットからヘルプファイルをダウンロードし、指定したファイルシステムディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-172">The `Save-Help` cmdlet downloads help files from the internet and saves them in a filesystem directory that you specify.</span></span>

<span data-ttu-id="a60e4-173">`Save-Help` 指定したディレクトリ内のヘルプファイルを、各モジュールで使用可能な最新のヘルプファイルと比較します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-173">`Save-Help` compares the help files in the specified directory to the newest help files that are available for each module.</span></span> <span data-ttu-id="a60e4-174">ディレクトリにヘルプファイルがない場合、または新しいヘルプファイルがモジュールに使用できる場合、 `Save-Help` コマンドレットはインターネットから新しいファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-174">If the directory has no help files or newer help files are available for the module, the `Save-Help` cmdlet downloads the new files from the internet.</span></span> <span data-ttu-id="a60e4-175">ただし、ヘルプファイルのラップを解除したりインストールしたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-175">However, it does not unwrap or install the help files.</span></span>

<span data-ttu-id="a60e4-176">ファイルシステムディレクトリに保存されたヘルプファイルからコンピューターのヘルプファイルをインストールまたは更新するには、コマンドレットの **SourcePath** パラメーターを使用し `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-176">To install or update the help files on a computer from help files that were saved to a filesystem directory, use the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="a60e4-177">`Update-Help`コマンドレットは、最新のヘルプファイルを識別し、ラップを解除して検証し、モジュールディレクトリの言語固有のサブディレクトリにインストールします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-177">The `Update-Help` cmdlet identifies the newest help files, unwraps and validates them, and installs them in the language-specific subdirectories of the module directories.</span></span>

<span data-ttu-id="a60e4-178">たとえば、インストールされているすべてのモジュールのヘルプをディレクトリに保存するには、次のように `\\Server\Share` 入力します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-178">For example, to save help for all installed modules to the `\\Server\Share` directory, type:</span></span>

```powershell
Save-Help -DestinationPath \\Server\Share
```

<span data-ttu-id="a60e4-179">次に、ディレクトリからヘルプを更新するには、次のように `\\Server\Share` 入力します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-179">Then, to update help from the `\\Server\Share` directory, type:</span></span>

```powershell
Update-Help -SourcePath \\Server\Share
```

<span data-ttu-id="a60e4-180">次の例は、を使用し `Save-Help` て、ローカルコンピューターにインストールされていないモジュールのヘルプを保存する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a60e4-180">The following examples show the use of `Save-Help` to save help for modules that are not installed on the local computer.</span></span> <span data-ttu-id="a60e4-181">この例では、管理者がを実行して、 `Save-Help` ローカルコンピューターに DhcpServer モジュールまたは DHCP サーバーの役割をインストールせずに、インターネットに接続されたクライアントコンピューターから DhcpServer モジュールのヘルプを保存します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-181">In this example, the administrator runs `Save-Help` to save the help for the DhcpServer module from an internet-connected client computer, without installing the DhcpServer module or DHCP Server role on the local computer.</span></span>

<span data-ttu-id="a60e4-182">オプション 1: を実行して `Invoke-Command` リモートモジュールの **PSModuleInfo** オブジェクトを取得し、それを変数に保存 `$m` します。次に、 `Save-Help` モジュール名として変数を指定して、 **PSModuleInfo** オブジェクトに対してを実行し `$m` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-182">Option 1: Run `Invoke-Command` to get the **PSModuleInfo** object for the remote module, save it in a variable, `$m`, and then run `Save-Help` on the **PSModuleInfo** object by specifying the variable `$m` as the module name.</span></span>

```powershell
$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock
{ Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="a60e4-183">オプション 2: DHCP サーバーモジュールを実行しているコンピューターを対象とする PSSession を開き、モジュールの **PSModuleInfo** オブジェクトを取得し、変数に保存して、 `$m` `Save-Help` 変数に保存されているオブジェクトでを実行し `$m` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-183">Option 2: Open a PSSession targeted at the computer that is running the DHCP Server module, to get the **PSModuleInfo** object for the module, save it in a variable `$m`, and then run `Save-Help` on the object that is saved in the `$m` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName RemoteServer
$m = Get-Module -PSSession $s -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="a60e4-184">オプション 3: DHCP サーバーモジュールを実行しているコンピューターを対象とする CIM セッションを開き、モジュールの **PSModuleInfo** オブジェクトを取得し、変数に保存して、 `$m` `Save-Help` 変数に保存されているオブジェクトでを実行し `$m` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-184">Option 3: Open a CIM session, targeted at the computer that is running the DHCP Server module, to get the **PSModuleInfo** object for the module, save it in a variable `$m`, and then run `Save-Help` on the object that is saved in the `$m` variable.</span></span>

```powershell
$c = New-CimSession -ComputerName RemoteServer
$m = Get-Module -CimSession $c -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="a60e4-185">次の例では、管理者がネットワークにアクセスできないコンピューターに DHCP サーバーモジュールのヘルプをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-185">In the following example, the administrator installs help for the DHCP Server module on a computer that does not have network access.</span></span>

<span data-ttu-id="a60e4-186">まず、を実行し `Export-Clixml` て、 **PSModuleInfo** オブジェクトを共有フォルダーまたはリムーバブルメディアにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-186">First, run `Export-Clixml` to export the **PSModuleInfo** object to a shared folder or to removable media.</span></span>

```powershell
$m = Get-Module -Name DhcpServer -ListAvailable
Export-Clixml -Path E:\UsbFlashDrive\DhcpModule.xml -InputObject $m
```

<span data-ttu-id="a60e4-187">次に、インターネットにアクセスできるコンピューターにリムーバブルメディアを転送し、を使用して **PSModuleInfo** オブジェクトをインポートし `Import-Clixml` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-187">Next, transport the removable media to a computer that has internet access, and then import the **PSModuleInfo** object with `Import-Clixml`.</span></span> <span data-ttu-id="a60e4-188">を実行して、インポートした `Save-Help` DhcpServer Module **PSModuleInfo** オブジェクトのヘルプを保存します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-188">Run `Save-Help` to save the Help for the imported DhcpServer module **PSModuleInfo** object.</span></span>

```powershell
$deserialized_m = Import-Clixml E:\UsbFlashDrive\DhcpModule.xml
Save-Help -Module $deserialized_m -DestinationPath E:\UsbFlashDrive\SavedHelp
```

<span data-ttu-id="a60e4-189">最後に、リムーバブルメディアをネットワークにアクセスできないコンピューターに転送してから、を実行してヘルプをインストールし `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-189">Finally, transport the removable media back to the computer that does not have network access, and then install the help by running `Update-Help`.</span></span>

```powershell
Update-Help -Module DhcpServer -SourcePath E:\UsbFlashDrive\SavedHelp
```

<span data-ttu-id="a60e4-190">パラメーターを指定しない場合、は、 `Save-Help` セッション内のすべてのモジュールと、更新可能なヘルプをサポートするすべてのインストール済みモジュールのヘルプをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-190">Without parameters, `Save-Help` downloads help for all modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="a60e4-191">モジュールを含めるには、 `$env:PSModulePath` ローカルコンピューターまたはヘルプを保存するリモートコンピューターで、環境変数の値に一覧表示されているディレクトリにモジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a60e4-191">To be included, modules must be installed in directories that are listed in the value of the `$env:PSModulePath` environment variable, on either the local computer or on a remote computer for which you want to save help.</span></span> <span data-ttu-id="a60e4-192">これらは、コマンドの実行によって返されるモジュールでもあり `Get-Help -ListAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-192">These are also modules that are returned by running a `Get-Help -ListAvailable` command.</span></span>

## <a name="how-to-update-help-files-in-different-languages"></a><span data-ttu-id="a60e4-193">さまざまな言語のヘルプファイルを更新する方法</span><span class="sxs-lookup"><span data-stu-id="a60e4-193">How to update help files in different languages</span></span>

<span data-ttu-id="a60e4-194">既定では、 `Update-Help` および `Save-Help` コマンドレットは、ローカルコンピューターの Windows に設定されている UI カルチャおよび言語のヘルプをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-194">By default, the `Update-Help` and `Save-Help` cmdlets download help in the UI culture and language that is set for Windows on the local computer.</span></span> <span data-ttu-id="a60e4-195">指定したモジュールのヘルプファイルがローカル UI カルチャで使用できない場合は、 `Update-Help` `Save-Help` Windows 言語フォールバック規則を使用して、サポートされている言語を検索します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-195">If help files for the specified modules are not available in the local UI culture, `Update-Help` and `Save-Help` use the Windows language fallback rules to find the best supported language.</span></span>

<span data-ttu-id="a60e4-196">ただし、およびコマンドレットの **UICulture** パラメーターを使用して、 `Update-Help` `Save-Help` 使用可能な任意の UI カルチャでヘルプファイルをダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-196">However, you can use the **UICulture** parameters of the `Update-Help` and `Save-Help` cmdlets to download and install help files in any UI cultures in which they are available.</span></span>

<span data-ttu-id="a60e4-197">たとえば、セッションのすべてのモジュールの最新のヘルプファイルを日本語 (Ja-jp) とフランス語 (fr-fr) で保存するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-197">For example, to save the newest help files for all modules on the session in Japanese (Ja-jp) and French (fr-FR), type:</span></span>

```powershell
Save-Help -Path \Server\Share -UICulture ja-jp, fr-fr
```

<span data-ttu-id="a60e4-198">指定した言語でモジュールのヘルプファイルを使用できない場合、 `Update-Help` `Save-Help` コマンドレットとコマンドレットは、各モジュールのヘルプが使用可能な言語を示すエラーメッセージを返します。これにより、ニーズに最も合った代替手段を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-198">If help files for the modules are not available in the languages that you specified, the `Update-Help` and `Save-Help` cmdlets return an error message that lists the languages in which help for each module is available so you can choose the alternative that best meets your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="a60e4-199">現在、更新可能なヘルプコンテンツは英語 (en-us) でのみ公開されています。</span><span class="sxs-lookup"><span data-stu-id="a60e4-199">Currently, Updateable Help content is only published in English (en-US).</span></span> <span data-ttu-id="a60e4-200">Windows 以外のシステムでは、 **UICulture** パラメーターを使用して、コンテンツを明示的に要求する必要があり `en-US` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-200">On some non-Windows systems you must use the **UICulture** parameter to explicitly request the `en-US` content.</span></span>

## <a name="how-to-use-online-help"></a><span data-ttu-id="a60e4-201">オンラインヘルプの使用方法</span><span class="sxs-lookup"><span data-stu-id="a60e4-201">How to use online help</span></span>

<span data-ttu-id="a60e4-202">ローカルコンピューターのヘルプファイルを更新できない場合、または更新しない場合でも、最新のヘルプファイルをオンラインで取得できます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-202">If you cannot or choose not to update the help files on your local computer, you can still get the newest help files online.</span></span>

<span data-ttu-id="a60e4-203">コマンドレットまたは関数のオンラインヘルプトピックを開くには、コマンドレットの **online** パラメーターを使用し `Get-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-203">To open the online help topic for any cmdlet or function, use the **Online** parameter of the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="a60e4-204">たとえば、次のコマンドは、 `Get-Job` 既定のインターネットブラウザーでコマンドレットのオンラインヘルプトピックを開きます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-204">For example, the following command opens the online help topic for the `Get-Job` cmdlet in your default internet browser:</span></span>

```powershell
Get-Help Get-Job -Online
```

<span data-ttu-id="a60e4-205">スクリプトのオンラインヘルプを表示するには、 **online** パラメーターとスクリプトへの完全なパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-205">To get online help for a script, use the **Online** parameter and the full path to the script.</span></span>

<span data-ttu-id="a60e4-206">**Online** パラメーターは、About トピックでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-206">The **Online** parameter does not work with About topics.</span></span> <span data-ttu-id="a60e4-207">Powershell 言語に関するヘルプトピックを含む、PowerShell の概要に関するトピックについては、 [powershell の概要に](about.md)関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a60e4-207">To see the about topics for PowerShell, including help topics about the PowerShell language, see [PowerShell About Topics](about.md).</span></span>

## <a name="how-to-minimize-or-prevent-internet-downloads"></a><span data-ttu-id="a60e4-208">インターネットのダウンロードを最小化または禁止する方法</span><span class="sxs-lookup"><span data-stu-id="a60e4-208">How to minimize or prevent internet downloads</span></span>

<span data-ttu-id="a60e4-209">インターネットに接続されていないユーザーに、インターネットのダウンロードを最小限にし、更新可能なヘルプを提供するには、コマンドレットを使用し `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-209">To minimize internet downloads and provide Updatable Help to users who are not connected to the internet, use the `Save-Help` cmdlet.</span></span> <span data-ttu-id="a60e4-210">インターネットからヘルプをダウンロードし、ネットワーク共有に保存します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-210">Download help from the internet and save it to a network share.</span></span> <span data-ttu-id="a60e4-211">次に、 `Update-Help` すべてのコンピューターでコマンドを実行するグループポリシー設定またはスケジュールされたジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-211">Then, create a Group Policy setting or scheduled job that runs an `Update-Help` command on all computers.</span></span> <span data-ttu-id="a60e4-212">コマンドレットの **SourcePath** パラメーターの値 `Update-Help` をネットワーク共有に設定します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-212">Set the value of the **SourcePath** parameter of the `Update-Help` cmdlet to the network share.</span></span>

<span data-ttu-id="a60e4-213">インターネットアクセス権を持つユーザーがインターネットから更新可能なヘルプをダウンロードできないようにするには、[ **update-help グループポリシーの既定のソースパスを設定** する] 設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-213">To prevent users who have internet access from downloading Updatable Help from the internet, use the **Set the default source path for Update-Help** Group Policy setting.</span></span>

<span data-ttu-id="a60e4-214">このグループポリシー設定では、影響を受けるすべてのコンピューター上のすべてのコマンドに、指定したファイルシステムの場所を持つ **SourcePath** パラメーターが暗黙的に追加され `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-214">This Group Policy setting implicitly adds the **SourcePath** parameter, with the filesystem location that you specify, to every `Update-Help` command on every affected computer.</span></span> <span data-ttu-id="a60e4-215">ユーザーは **sourcepath** パラメーターを明示的に使用して別のファイルシステムの場所を指定できますが、 **sourcepath** パラメーターを除外して、インターネットからヘルプをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-215">Users can use the **SourcePath** parameter explicitly to specify a different filesystem location, but they cannot exclude the **SourcePath** parameter and download help from the internet.</span></span>

> [!NOTE]
> <span data-ttu-id="a60e4-216">[**コンピューターの構成** と **ユーザーの構成**] の下に、[**更新プログラムの既定のソースパスを設定** してください] ポリシー設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-216">The **Set the default source path for Update-Help** group policy setting appears under **Computer Configuration** and **User Configuration**.</span></span> <span data-ttu-id="a60e4-217">ただし、[ **コンピューターの構成** ] の下のポリシー設定のみが有効です。</span><span class="sxs-lookup"><span data-stu-id="a60e4-217">However, only the policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="a60e4-218">[ **ユーザーの構成** ] のポリシー設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-218">The policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="a60e4-219">詳細については、「[about_Group_Policy_Settings](about_Group_Policy_Settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a60e4-219">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="how-to-update-help-for-non-standard-modules"></a><span data-ttu-id="a60e4-220">標準以外のモジュールのヘルプを更新する方法</span><span class="sxs-lookup"><span data-stu-id="a60e4-220">How to update help for non-standard modules</span></span>

<span data-ttu-id="a60e4-221">コマンドレットの **ListAvailable** パラメーターによって返されないモジュールのヘルプを更新または保存するに `Get-Module` は、またはコマンドを実行する前に、現在のセッションにモジュールをインポートし `Update-Help` `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-221">To update or save help for a module that is not returned by the **ListAvailable** parameter of the `Get-Module` cmdlet, import the module into the current session before running an `Update-Help` or `Save-Help` command.</span></span> <span data-ttu-id="a60e4-222">リモートコンピューターで、コマンドを実行する前に、 `Save-Help` `Invoke-Command` リモートコンピューターに接続されている現在のセッションまたはスクリプトブロックにモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a60e4-222">On a remote computer, before running the `Save-Help` command, import the module into the current Session, or `Invoke-Command` script block, that is connected to the remote computer.</span></span>

<span data-ttu-id="a60e4-223">モジュールが現在のセッション内にある場合は、 `Update-Help` `Save-Help` パラメーターを指定せずにまたはコマンドレットを実行するか、 **module** パラメーターを使用してモジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a60e4-223">When the module is in the current session, run the `Update-Help` or `Save-Help` cmdlets without parameters, or use the **Module** parameter to specify the module name.</span></span>

<span data-ttu-id="a60e4-224">およびコマンドレットの **モジュール** パラメーターには、 `Update-Help` `Save-Help` モジュール名のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-224">The **Module** parameters of the `Update-Help` and `Save-Help` cmdlets accept only a module name.</span></span> <span data-ttu-id="a60e4-225">モジュールファイルのパスを受け取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-225">They do not accept the path to a module file.</span></span>

<span data-ttu-id="a60e4-226">この手法は、コマンドレットの **ListAvailable** パラメーターによって返されないモジュール (環境変数に一覧表示されていない場所にインストールされているモジュールや、適切な形式ではないモジュールなど) のヘルプを更新または保存するために使用し `Get-Module` `$env:PSModulePath` ます (モジュールディレクトリには、ディレクトリ名と同じ名前のファイルが少なくとも1つ含まれ</span><span class="sxs-lookup"><span data-stu-id="a60e4-226">Use this technique to update or save help for any module that is not returned by the **ListAvailable** parameter of the `Get-Module` cmdlet, such as a module that is installed in a location that is not listed in the `$env:PSModulePath` environment variable, or a module that is not well-formed (the module directory does not contain at least one file whose basename is the same as the directory name).</span></span>

## <a name="how-to-support-updatable-help"></a><span data-ttu-id="a60e4-227">更新可能なヘルプをサポートする方法</span><span class="sxs-lookup"><span data-stu-id="a60e4-227">How to support updatable help</span></span>

<span data-ttu-id="a60e4-228">モジュールを作成する場合は、モジュールのオンラインヘルプと更新可能なヘルプをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="a60e4-228">If you author a module, you can support online help and Updatable Help for your modules.</span></span> <span data-ttu-id="a60e4-229">詳細については、「Microsoft Docs の [更新可能なヘルプ](/powershell/scripting/developer/help/supporting-updatable-help) と [サポートオンラインヘルプ](/powershell/scripting/developer/module/supporting-online-help) のサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a60e4-229">For more information, see [Supporting Updatable Help](/powershell/scripting/developer/help/supporting-updatable-help) and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help) in the Microsoft Docs.</span></span>

<span data-ttu-id="a60e4-230">更新可能なヘルプは、PowerShell スナップインやコメントベースのヘルプには使用できません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-230">Updatable help not available for PowerShell snap-ins or comment-based help.</span></span>

## <a name="remarks"></a><span data-ttu-id="a60e4-231">解説</span><span class="sxs-lookup"><span data-stu-id="a60e4-231">Remarks</span></span>

<span data-ttu-id="a60e4-232">`Update-Help`および `Save-Help` コマンドレットは、Windows Preinstallation Environment (Windows PE) ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a60e4-232">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <a name="see-also"></a><span data-ttu-id="a60e4-233">関連項目</span><span class="sxs-lookup"><span data-stu-id="a60e4-233">See also</span></span>

[<span data-ttu-id="a60e4-234">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a60e4-234">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="a60e4-235">Save-Help</span><span class="sxs-lookup"><span data-stu-id="a60e4-235">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

[<span data-ttu-id="a60e4-236">Update-Help</span><span class="sxs-lookup"><span data-stu-id="a60e4-236">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)

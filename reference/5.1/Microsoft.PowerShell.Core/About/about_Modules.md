---
description: PowerShell モジュールをインストール、インポート、および使用する方法について説明します。
Locale: en-US
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: 30af4ed84e2332aecd60838f3bcd7741965c2ba1
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564341"
---
# <a name="about-modules"></a><span data-ttu-id="462d0-103">モジュールについて</span><span class="sxs-lookup"><span data-stu-id="462d0-103">About Modules</span></span>

## <a name="short-description"></a><span data-ttu-id="462d0-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="462d0-104">Short Description</span></span>
<span data-ttu-id="462d0-105">PowerShell モジュールをインストール、インポート、および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="462d0-105">Explains how to install, import, and use PowerShell modules.</span></span>

## <a name="long-description"></a><span data-ttu-id="462d0-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="462d0-106">Long Description</span></span>

<span data-ttu-id="462d0-107">モジュールは、コマンドレット、プロバイダー、関数、ワークフロー、変数、エイリアスなどの PowerShell メンバーを含むパッケージです。</span><span class="sxs-lookup"><span data-stu-id="462d0-107">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span>

<span data-ttu-id="462d0-108">コマンドを記述するとき、モジュールを利用してコマンドを整理したり、他者と共有したりできます。</span><span class="sxs-lookup"><span data-stu-id="462d0-108">People who write commands can use modules to organize their commands and share them with others.</span></span> <span data-ttu-id="462d0-109">モジュールを受け取るユーザーは、モジュール内のコマンドを PowerShell セッションに追加し、組み込みコマンドと同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="462d0-109">People who receive modules can add the commands in the modules to their PowerShell sessions and use them just like the built-in commands.</span></span>

<span data-ttu-id="462d0-110">このトピックでは、PowerShell モジュールの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="462d0-110">This topic explains how to use PowerShell modules.</span></span> <span data-ttu-id="462d0-111">PowerShell モジュールの作成方法の詳細については、「 [Powershell モジュールの記述](/powershell/scripting/developer/module/writing-a-windows-powershell-module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-111">For information about how to write PowerShell modules, see [Writing a PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="what-is-a-module"></a><span data-ttu-id="462d0-112">モジュールとは</span><span class="sxs-lookup"><span data-stu-id="462d0-112">What Is a Module?</span></span>

<span data-ttu-id="462d0-113">モジュールは、コマンドレット、プロバイダー、関数、ワークフロー、変数、エイリアスなどの PowerShell メンバーを含むパッケージです。</span><span class="sxs-lookup"><span data-stu-id="462d0-113">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span> <span data-ttu-id="462d0-114">このパッケージのメンバーは、PowerShell スクリプト、コンパイルされた DLL、またはその両方の組み合わせで実装できます。</span><span class="sxs-lookup"><span data-stu-id="462d0-114">The members of this package can be implemented in a PowerShell script, a compiled DLL, or a combination of both.</span></span> <span data-ttu-id="462d0-115">これらのファイルは通常、1つのディレクトリにまとめられます。</span><span class="sxs-lookup"><span data-stu-id="462d0-115">These files are usually grouped together in a single directory.</span></span> <span data-ttu-id="462d0-116">詳細については、SDK ドキュメントの「 [Windows PowerShell モジュールについ](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-116">For more information, see [Understanding a Windows PowerShell Module](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) in the SDK documentation.</span></span>

## <a name="module-auto-loading"></a><span data-ttu-id="462d0-117">モジュールの自動読み込み</span><span class="sxs-lookup"><span data-stu-id="462d0-117">Module Auto-Loading</span></span>

<span data-ttu-id="462d0-118">PowerShell 3.0 以降では、インストールされているモジュールで任意のコマンドを初めて実行したときに、PowerShell は自動的にモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="462d0-118">Beginning in PowerShell 3.0, PowerShell imports modules automatically the first time that you run any command in an installed module.</span></span> <span data-ttu-id="462d0-119">今後は設定やプロファイル構成なしでモジュールのコマンドを使用できます。そのため、コンピューターにモジュールをインストールした後はモジュールを管理する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="462d0-119">You can now use the commands in a module without any set-up or profile configuration, so there's no need to manage modules after you install them on your computer.</span></span>

<span data-ttu-id="462d0-120">また、モジュールのコマンドが見つけやすくなりました。</span><span class="sxs-lookup"><span data-stu-id="462d0-120">The commands in a module are also easier to find.</span></span> <span data-ttu-id="462d0-121">`Get-Command`コマンドレットは、インストールされているすべてのモジュールのすべてのコマンドを取得するようになりました。セッションにまだ含まれていない場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="462d0-121">The `Get-Command` cmdlet now gets all commands in all installed modules, even if they are not yet in the session.</span></span> <span data-ttu-id="462d0-122">最初にモジュールをインポートしなくても、コマンドを見つけて使用することができます。</span><span class="sxs-lookup"><span data-stu-id="462d0-122">You can find a command and use it without importing needing to import the module first.</span></span>

<span data-ttu-id="462d0-123">次の各例では、を含む CimCmdlets モジュールが `Get-CimInstance` セッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="462d0-123">Each of the following examples cause the CimCmdlets module, which contains `Get-CimInstance`, to be imported into your session.</span></span>

- <span data-ttu-id="462d0-124">コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="462d0-124">Run the Command</span></span>

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- <span data-ttu-id="462d0-125">コマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="462d0-125">Get the Command</span></span>

  ```powershell
  Get-Command Get-CimInstance
  ```

- <span data-ttu-id="462d0-126">コマンドのヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="462d0-126">Get Help for the Command</span></span>

  ```powershell
  Get-Help Get-CimInstance
  ```

<span data-ttu-id="462d0-127">`Get-Command` ワイルドカード文字 () を含むコマンド `*` は、検出用であり、使用しないと見なされ、モジュールをインポートしません。</span><span class="sxs-lookup"><span data-stu-id="462d0-127">`Get-Command` commands that include a wildcard character (`*`) are considered to be for discovery, not use, and do not import any modules.</span></span>

<span data-ttu-id="462d0-128">PSModulePath 環境変数によって指定された場所に格納されているモジュールのみが自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="462d0-128">Only modules that are stored in the location specified by the PSModulePath environment variable are automatically imported.</span></span> <span data-ttu-id="462d0-129">他の場所のモジュールは、コマンドレットを実行してインポートする必要があり `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-129">Modules in other locations must be imported by running the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="462d0-130">また、PowerShell プロバイダーを使用するコマンドでは、モジュールは自動的にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="462d0-130">Also, commands that use PowerShell providers do not automatically import a module.</span></span> <span data-ttu-id="462d0-131">たとえば、コマンドレットなど、WSMan: ドライブを必要とするコマンドを使用する場合は、コマンドレットを実行して、 `Get-PSSessionConfiguration` `Import-Module` ドライブを含む **Microsoft の wsman. 管理** モジュールをインポートする必要があり `WSMan:` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-131">For example, if you use a command that requires the WSMan: drive, such as the `Get-PSSessionConfiguration` cmdlet, you might need to run the `Import-Module` cmdlet to import the **Microsoft.WSMan.Management** module that includes the `WSMan:` drive.</span></span>

<span data-ttu-id="462d0-132">コマンドを実行し `Import-Module` てモジュールをインポートし、変数を使用して `$PSModuleAutoloadingPreference` モジュールの自動インポートを有効化、無効化、および構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="462d0-132">You can still run the `Import-Module` command to import a module and use the `$PSModuleAutoloadingPreference` variable to enable, disable and configure automatic importing of modules.</span></span> <span data-ttu-id="462d0-133">詳細については、「 [about_Preference_Variables](about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-133">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="how-to-use-a-module"></a><span data-ttu-id="462d0-134">モジュールを使用する方法</span><span class="sxs-lookup"><span data-stu-id="462d0-134">How to Use a Module</span></span>

<span data-ttu-id="462d0-135">モジュールを使用するには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="462d0-135">To use a module, perform the following tasks:</span></span>

1. <span data-ttu-id="462d0-136">モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="462d0-136">Install the module.</span></span> <span data-ttu-id="462d0-137">(多くの場合、これは自動的に行われます。)</span><span class="sxs-lookup"><span data-stu-id="462d0-137">(This is often done for you.)</span></span>
1. <span data-ttu-id="462d0-138">モジュールにより追加されたコマンドを見つけます。</span><span class="sxs-lookup"><span data-stu-id="462d0-138">Find the commands that the module added.</span></span>
1. <span data-ttu-id="462d0-139">モジュールにより追加されたコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-139">Use the commands that the module added.</span></span>

<span data-ttu-id="462d0-140">このトピックでは、これらのタスクの実行方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="462d0-140">This topic explains how to perform these tasks.</span></span> <span data-ttu-id="462d0-141">モジュールの管理に関して役に立つその他の情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="462d0-141">It also includes other useful information about managing modules.</span></span>

## <a name="how-to-install-a-module"></a><span data-ttu-id="462d0-142">モジュールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="462d0-142">How to Install a Module</span></span>

<span data-ttu-id="462d0-143">ファイルが含まれているフォルダーとしてモジュールを受け取った場合は、PowerShell で使用する前に、コンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="462d0-143">If you receive a module as a folder with files in it, you need to install it on your computer before you can use it in PowerShell.</span></span>

<span data-ttu-id="462d0-144">ほとんどのモジュールは自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="462d0-144">Most modules are installed for you.</span></span> <span data-ttu-id="462d0-145">PowerShell には、いくつかのプレインストールモジュール ( _コア_ モジュールと呼ばれることもあります) が付属しています。</span><span class="sxs-lookup"><span data-stu-id="462d0-145">PowerShell comes with several preinstalled modules, sometimes called the _core_ modules.</span></span> <span data-ttu-id="462d0-146">Windows ベースのコンピューターでは、オペレーティングシステムに含まれている機能に、それらを管理するためのコマンドレットがある場合、これらのモジュールはプレインストールされています。</span><span class="sxs-lookup"><span data-stu-id="462d0-146">On Windows-based computers, if features that are included with the operating system have cmdlets to manage them, those modules are preinstalled.</span></span> <span data-ttu-id="462d0-147">Windows の機能をインストールすると、たとえば、サーバーマネージャーの役割と機能の追加ウィザード、コントロールパネルの [Windows の機能の有効化または無効化] ダイアログボックス、機能の一部である PowerShell モジュールがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="462d0-147">When you install a Windows feature, by using, for example, the Add Roles and Features Wizard in Server Manager, or the Turn Windows features on or off dialog box in Control Panel, any PowerShell modules that are part of the feature are installed.</span></span> <span data-ttu-id="462d0-148">他にも多くのモジュールがモジュールをインストールするインストーラーまたは設定プログラムで提供されます。</span><span class="sxs-lookup"><span data-stu-id="462d0-148">Many other modules come in an installer or Setup program that installs the module.</span></span>

<span data-ttu-id="462d0-149">次のコマンドを使用して、現在のユーザーの **モジュール** ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="462d0-149">Use the following command to create a **Modules** directory for the current user:</span></span>

```powershell
New-Item -Type Directory -Path $HOME\Documents\WindowsPowerShell\Modules
```

<span data-ttu-id="462d0-150">モジュール フォルダー全体をモジュール ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="462d0-150">Copy the entire module folder into the Modules directory.</span></span> <span data-ttu-id="462d0-151">Windows Explorer と Cmd.exe、PowerShell を含むフォルダーをコピーするには、任意の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="462d0-151">You can use any method to copy the folder, including Windows Explorer and Cmd.exe, as well as PowerShell.</span></span> <span data-ttu-id="462d0-152">PowerShell では、 `Copy-Item` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-152">In PowerShell use the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="462d0-153">たとえば、MyModule フォルダーをから Modules ディレクトリにコピーするには、次のように `C:\ps-test\MyModule` 入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-153">For example, to copy the MyModule folder from `C:\ps-test\MyModule` to the Modules directory, type:</span></span>

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\WindowsPowerShell\Modules
```

<span data-ttu-id="462d0-154">モジュールはどこにインストールしても構いませんが、モジュールの既定の場所にモジュールをインストールすれば、管理しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="462d0-154">You can install a module in any location, but installing your modules in a default module location makes them easier to manage.</span></span> <span data-ttu-id="462d0-155">既定のモジュールの場所の詳細については、 [モジュールと DSC リソースの場所、および PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-155">For more information about the default module locations, see the [Module and DSC Resource Locations, and PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) section.</span></span>

## <a name="how-to-find-installed-modules"></a><span data-ttu-id="462d0-156">インストールされているモジュールを検索する方法</span><span class="sxs-lookup"><span data-stu-id="462d0-156">How to Find Installed Modules</span></span>

<span data-ttu-id="462d0-157">モジュールの既定の場所にインストールしたが、まだセッションにインポートしていないモジュールを見つけるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-157">To find modules that are installed in a default module location, but not yet imported into your session, type:</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="462d0-158">セッションに既にインポートされているモジュールを見つけるには、PowerShell プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-158">To find the modules that have already been imported into your session, at the PowerShell prompt, type:</span></span>

```powershell
Get-Module
```

<span data-ttu-id="462d0-159">コマンドレットの詳細につい `Get-Module` ては、「 [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-159">For more information about the `Get-Module` cmdlet, see [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

## <a name="how-to-find-the-commands-in-a-module"></a><span data-ttu-id="462d0-160">モジュール内のコマンドを検索する方法</span><span class="sxs-lookup"><span data-stu-id="462d0-160">How to Find the Commands in a Module</span></span>

<span data-ttu-id="462d0-161">使用 `Get-Command` 可能なすべてのコマンドを検索するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-161">Use the `Get-Command` cmdlet to find all available commands.</span></span> <span data-ttu-id="462d0-162">コマンドレットのパラメーターを使用し `Get-Command` て、モジュール、名前、名詞などのコマンドをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="462d0-162">You can use the parameters of the `Get-Command` cmdlet to filter commands such as by module, name, and noun.</span></span>

<span data-ttu-id="462d0-163">モジュールのすべてのコマンドを見つけるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-163">To find all commands in a module, type:</span></span>

```powershell
Get-Command -Module <module-name>
```

<span data-ttu-id="462d0-164">たとえば、BitsTransfer モジュール内のコマンドを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-164">For example, to find the commands in the BitsTransfer module, type:</span></span>

```powershell
Get-Command -Module BitsTransfer
```

<span data-ttu-id="462d0-165">コマンドレットの詳細につい `Get-Command` ては、「 [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-165">For more information about the `Get-Command` cmdlet, see [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span></span>

## <a name="how-to-get-help-for-the-commands-in-a-module"></a><span data-ttu-id="462d0-166">モジュール内のコマンドのヘルプを取得する方法</span><span class="sxs-lookup"><span data-stu-id="462d0-166">How to Get Help for the Commands in a Module</span></span>

<span data-ttu-id="462d0-167">モジュールにエクスポートするコマンドのヘルプファイルが含まれている場合は、コマンドレットによって `Get-Help` ヘルプトピックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="462d0-167">If the module contains Help files for the commands that it exports, the `Get-Help` cmdlet will display the Help topics.</span></span> <span data-ttu-id="462d0-168">`Get-Help`PowerShell で任意のコマンドのヘルプを取得するために使用するのと同じコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-168">Use the same `Get-Help` command format that you would use to get help for any command in PowerShell.</span></span>

<span data-ttu-id="462d0-169">PowerShell 3.0 以降では、モジュールのヘルプファイルをダウンロードし、ヘルプファイルに更新プログラムをダウンロードして、互換性が残されていないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="462d0-169">Beginning in PowerShell 3.0, you can download Help files for a module and download updates to the Help files so they are never obsolete.</span></span>

<span data-ttu-id="462d0-170">モジュールのコマンドのヘルプを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-170">To get help for a commands in a module, type:</span></span>

```powershell
Get-Help <command-name>
```

<span data-ttu-id="462d0-171">モジュール内のコマンドのヘルプをオンラインで取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-171">To get help online for command in a module, type:</span></span>

```powershell
Get-Help <command-name> -Online
```

<span data-ttu-id="462d0-172">モジュール内のコマンドのヘルプファイルをダウンロードしてインストールするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-172">To download and install the help files for the commands in a module, type:</span></span>

```powershell
Update-Help -Module <module-name>
```

<span data-ttu-id="462d0-173">詳細については、「 [get-help](xref:Microsoft.PowerShell.Core.Get-Help) and [update-help](xref:Microsoft.PowerShell.Core.Update-Help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-173">For more information, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span></span>

## <a name="how-to-import-a-module"></a><span data-ttu-id="462d0-174">モジュールをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="462d0-174">How to Import a Module</span></span>

<span data-ttu-id="462d0-175">場合によっては、モジュールまたはモジュール ファイルをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="462d0-175">You might have to import a module or import a module file.</span></span> <span data-ttu-id="462d0-176">インポートは、 **PSModulePath** 環境変数で指定された場所にモジュールがインストールされていない場合、 `$env:PSModulePath` またはフォルダーとして配信される一般的なモジュールではなく、.dll や hbase-runner.psm1 ファイルなどのファイルでモジュールが構成されている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="462d0-176">Importing is required when a module is not installed in the locations specified by the **PSModulePath** environment variable, `$env:PSModulePath`, or the module consists of file, such as a .dll or .psm1 file, instead of typical module that is delivered as a folder.</span></span>

<span data-ttu-id="462d0-177">また、コマンドのパラメーターを使用できるように、モジュールをインポートすることもできます。これにより、インポートされた `Import-Module` すべてのコマンドの名詞名に特徴的なプレフィックスが追加されます。または、 **NoClobber** パラメーターによって、セッション内の既存のコマンドを非表示にしたり、置き換えたりするコマンドをモジュールで追加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="462d0-177">You might also choose to import a module so that you can use the parameters of the `Import-Module` command, such as the Prefix parameter, which adds a distinctive prefix to the noun names of all imported commands, or the **NoClobber** parameter, which prevents the module from adding commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="462d0-178">モジュールをインポートするには、コマンドレットを使用し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-178">To import modules, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="462d0-179">場所 PSModulePath にあるモジュールを現在のセッションにインポートするには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-179">To import modules in a PSModulePath location into the current session, use the following command format.</span></span>

```powershell
Import-Module <module-name>
```

<span data-ttu-id="462d0-180">たとえば、次のコマンドは、BitsTransfer モジュールを現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="462d0-180">For example, the following command imports the BitsTransfer module into the current session.</span></span>

```powershell
Import-Module BitsTransfer
```

<span data-ttu-id="462d0-181">モジュールの既定の場所にないモジュールをインポートするには、コマンドでモジュール フォルダーの完全修飾パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-181">To import a module that is not in a default module location, use the fully qualified path to the module folder in the command.</span></span>

<span data-ttu-id="462d0-182">たとえば、ディレクトリの TestCmdlets モジュールをセッションに追加するには、次のように `C:\ps-test` 入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-182">For example, to add the TestCmdlets module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets
```

<span data-ttu-id="462d0-183">モジュール フォルダーに含まれていないモジュール ファイルをインポートするには、コマンドでモジュール ファイルの完全修飾パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-183">To import a module file that is not contained in a module folder, use the fully qualified path to the module file in the command.</span></span>

<span data-ttu-id="462d0-184">たとえば、ディレクトリ内の TestCmdlets.dll モジュールをセッションに追加するには、次のように `C:\ps-test` 入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-184">For example, to add the TestCmdlets.dll module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

<span data-ttu-id="462d0-185">セッションにモジュールを追加する方法の詳細については、「 [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-185">For more information about adding modules to your session, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="how-to-import-a-module-into-every-session"></a><span data-ttu-id="462d0-186">モジュールをすべてのセッションにインポートする方法</span><span class="sxs-lookup"><span data-stu-id="462d0-186">How to Import a Module into Every Session</span></span>

<span data-ttu-id="462d0-187">コマンドは、 `Import-Module` 現在の PowerShell セッションにモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="462d0-187">The `Import-Module` command imports modules into your current PowerShell session.</span></span> <span data-ttu-id="462d0-188">開始するすべての PowerShell セッションにモジュールをインポートするには、 `Import-Module` powershell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="462d0-188">To import a module into every PowerShell session that you start, add the `Import-Module` command to your PowerShell profile.</span></span>

<span data-ttu-id="462d0-189">プロファイルの詳細については、「[about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-189">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="how-to-remove-a-module"></a><span data-ttu-id="462d0-190">モジュールを削除する方法</span><span class="sxs-lookup"><span data-stu-id="462d0-190">How to Remove a Module</span></span>

<span data-ttu-id="462d0-191">モジュールを削除すると、モジュールが追加したコマンドがセッションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="462d0-191">When you remove a module, the commands that the module added are deleted from the session.</span></span>

<span data-ttu-id="462d0-192">セッションからモジュールを削除するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-192">To remove a module from your session, use the following command format.</span></span>

```powershell
Remove-Module <module-name>
```

<span data-ttu-id="462d0-193">たとえば、次のコマンドは、現在のセッションから BitsTransfer モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="462d0-193">For example, the following command removes the BitsTransfer module from the current session.</span></span>

```powershell
Remove-Module BitsTransfer
```

<span data-ttu-id="462d0-194">モジュールを削除では、モジュールのインポートの反対の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="462d0-194">Removing a module reverses the operation of importing a module.</span></span> <span data-ttu-id="462d0-195">モジュールを削除してもモジュールはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="462d0-195">Removing a module does not uninstall the module.</span></span> <span data-ttu-id="462d0-196">詳細については、「 [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-196">For more information, see [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span></span>

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a><span data-ttu-id="462d0-197">モジュールと DSC リソースの場所、および PSModulePath</span><span class="sxs-lookup"><span data-stu-id="462d0-197">Module and DSC Resource Locations, and PSModulePath</span></span>

<span data-ttu-id="462d0-198">環境変数には、 `$env:PSModulePath` モジュールとリソースを検索するために検索されるフォルダーの場所の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="462d0-198">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="462d0-199">既定では、に割り当てられて `$env:PSModulePath` いる有効な場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="462d0-199">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="462d0-200">システム全体の場所: `$PSHOME\Modules`</span><span class="sxs-lookup"><span data-stu-id="462d0-200">System-wide locations: `$PSHOME\Modules`</span></span>

  <span data-ttu-id="462d0-201">これらのフォルダーには、Windows と PowerShell に付属しているモジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="462d0-201">These folders contain modules that ship with Windows and PowerShell.</span></span>

  <span data-ttu-id="462d0-202">PowerShell に含まれる DSC リソースは、フォルダーに格納され `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-202">DSC resources that are included with PowerShell are stored in the `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` folder.</span></span>

- <span data-ttu-id="462d0-203">ユーザー固有のモジュール: ユーザーによってユーザーのスコープにインストールされたモジュールです。</span><span class="sxs-lookup"><span data-stu-id="462d0-203">User-specific modules: These are modules installed by the user in the user's scope.</span></span> <span data-ttu-id="462d0-204">`Install-Module` には、現在のユーザーまたはすべてのユーザーに対してモジュールがインストールされているかどうかを指定できる **スコープ** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="462d0-204">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="462d0-205">詳細については、「 [Install-Module](xref:PowerShellGet.Install-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-205">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  <span data-ttu-id="462d0-206">Windows 上のユーザー固有の **CurrentUser** の場所は、 `PowerShell\Modules` ユーザープロファイル内の **ドキュメント** の場所にあるフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="462d0-206">The user-specific **CurrentUser** location on Windows is the `PowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="462d0-207">その場所の特定のパスは、Windows のバージョンと、フォルダーリダイレクトを使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="462d0-207">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="462d0-208">Microsoft OneDrive では、 **ドキュメント** フォルダーの場所を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="462d0-208">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span>

  <span data-ttu-id="462d0-209">既定では、Windows 10 の場合、その場所は `$HOME\Documents\PowerShell\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="462d0-209">By default, on Windows 10, that location is `$HOME\Documents\PowerShell\Modules`.</span></span> <span data-ttu-id="462d0-210">Linux または Mac では、 **CurrentUser** の場所は `$HOME/.local/share/powershell/Modules` です。</span><span class="sxs-lookup"><span data-stu-id="462d0-210">On Linux or Mac, the **CurrentUser** location is `$HOME/.local/share/powershell/Modules`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="462d0-211">次のコマンドを使用して、 **ドキュメント** フォルダーの場所を確認でき `[Environment]::GetFolderPath('MyDocuments')` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-211">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

- <span data-ttu-id="462d0-212">**AllUsers** の場所は `$env:PROGRAMFILES\PowerShell\Modules` Windows 上にあります。</span><span class="sxs-lookup"><span data-stu-id="462d0-212">The **AllUsers** location is `$env:PROGRAMFILES\PowerShell\Modules` on Windows.</span></span> <span data-ttu-id="462d0-213">Linux または Mac では、モジュールはに格納され `/usr/local/share/powershell/Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-213">On Linux or Mac the modules are stored at `/usr/local/share/powershell/Modules`.</span></span>

> [!NOTE]
> <span data-ttu-id="462d0-214">ディレクトリ内のファイルを追加または変更するには、 `$env:Windir\System32` [ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="462d0-214">To add or change files in the `$env:Windir\System32` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="462d0-215">**PSModulePath** 環境変数の値を変更することで、システム上の既定のモジュールの場所を変更でき `$Env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-215">You can change the default module locations on your system by changing the value of the **PSModulePath** environment variable, `$Env:PSModulePath`.</span></span> <span data-ttu-id="462d0-216">**PSModulePath** 環境変数は Path 環境変数でモデル化されており、同じ形式です。</span><span class="sxs-lookup"><span data-stu-id="462d0-216">The **PSModulePath** environment variable is modeled on the Path environment variable and has the same format.</span></span>

<span data-ttu-id="462d0-217">モジュールの既定の場所を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-217">To view the default module locations, type:</span></span>

```powershell
$Env:PSModulePath
```

<span data-ttu-id="462d0-218">モジュールの既定の場所を追加するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-218">To add a default module location, use the following command format.</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

<span data-ttu-id="462d0-219">コマンドのセミコロン () は、 `;` 新しいパスをリスト内でその前にあるパスと分離します。</span><span class="sxs-lookup"><span data-stu-id="462d0-219">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="462d0-220">たとえば、ディレクトリを追加するには、次のように `C:\ps-test\Modules` 入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-220">For example, to add the `C:\ps-test\Modules` directory, type:</span></span>

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

<span data-ttu-id="462d0-221">パスを **PSModulePath** に追加すると、 `Get-Module` コマンドには `Import-Module` そのパスのモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="462d0-221">When you add a path to **PSModulePath**, `Get-Module` and `Import-Module` commands include modules in that path.</span></span>

<span data-ttu-id="462d0-222">設定した値は現在のセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="462d0-222">The value that you set affects only the current session.</span></span> <span data-ttu-id="462d0-223">変更を永続化するには、PowerShell プロファイルにコマンドを追加するか、コントロールパネルの [システム] を使用して、レジストリの **PSModulePath** 環境変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="462d0-223">To make the change persistent, add the command to your PowerShell profile or use System in Control Panel to change the value of the **PSModulePath** environment variable in the registry.</span></span>

<span data-ttu-id="462d0-224">また、変更を永続化するために、SetEnvironmentVariable クラスのメソッドを使用して、 **PSModulePath** 環境変数にパスを追加することもでき **ます。**</span><span class="sxs-lookup"><span data-stu-id="462d0-224">Also, to make the change persistent, you can also use the **SetEnvironmentVariable** method of the **System.Environment** class to add a Path to the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="462d0-225">**PSModulePath** 変数の詳細については、「 [about_Environment_Variables](about_Environment_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-225">For more information about the **PSModulePath** variable, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

## <a name="modules-and-name-conflicts"></a><span data-ttu-id="462d0-226">モジュールと名前の競合</span><span class="sxs-lookup"><span data-stu-id="462d0-226">Modules and Name Conflicts</span></span>

<span data-ttu-id="462d0-227">名前の競合は、セッションの複数のコマンドの名前が同じときに発生します。</span><span class="sxs-lookup"><span data-stu-id="462d0-227">Name conflicts occur when more than one command in the session has the same name.</span></span> <span data-ttu-id="462d0-228">モジュールのコマンドの名前がセッションのコマンドまたはアイテムの名前と同じとき、モジュールをインポートすると名前の競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="462d0-228">Importing a module causes a name conflict when commands in the module have the same names as commands or items in the session.</span></span>

<span data-ttu-id="462d0-229">名前が競合していると、コマンドが隠されたり、置換されたりします。</span><span class="sxs-lookup"><span data-stu-id="462d0-229">Name conflicts can result in commands being hidden or replaced.</span></span>

### <a name="hidden"></a><span data-ttu-id="462d0-230">[非表示]</span><span class="sxs-lookup"><span data-stu-id="462d0-230">Hidden</span></span>

<span data-ttu-id="462d0-231">コマンド名を入力して実行されるコマンドと違う場合、コマンドが隠されています。ただし、別の方法でコマンドを実行できます。たとえば、出所のモジュールまたはスナップインの名前でコマンド名を修飾します。</span><span class="sxs-lookup"><span data-stu-id="462d0-231">A command is hidden when it is not the command that runs when you type the command name, but you can run it by using another method, such as by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

### <a name="replaced"></a><span data-ttu-id="462d0-232">置換後</span><span class="sxs-lookup"><span data-stu-id="462d0-232">Replaced</span></span>

<span data-ttu-id="462d0-233">実行できなければコマンドは置換されています。同じ名前のコマンドで上書きされたためです。</span><span class="sxs-lookup"><span data-stu-id="462d0-233">A command is replaced when you cannot run it because it has been overwritten by a command with the same name.</span></span> <span data-ttu-id="462d0-234">競合を引き起こしたモジュールを削除しても、セッションを再起動しなければ、置換されたコマンドは実行できません。</span><span class="sxs-lookup"><span data-stu-id="462d0-234">Even when you remove the module that caused the conflict, you cannot run a replaced command unless you restart the session.</span></span>

<span data-ttu-id="462d0-235">`Import-Module` では、現在のセッションのコマンドを非表示にしたり置換したりするコマンドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="462d0-235">`Import-Module` might add commands that hide and replace commands in the current session.</span></span> <span data-ttu-id="462d0-236">また、セッションのコマンドはモジュールが追加したコマンドを隠すことがあります。</span><span class="sxs-lookup"><span data-stu-id="462d0-236">Also, commands in your session can hide commands that the module added.</span></span>

<span data-ttu-id="462d0-237">名前の競合を検出するには、コマンドレットの **All** パラメーターを使用し `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-237">To detect name conflicts, use the **All** parameter of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="462d0-238">PowerShell 3.0 以降では、コマンド名を入力したときに実行される `Get-Command` コマンドのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="462d0-238">Beginning in PowerShell 3.0, `Get-Command` gets only that commands that run when you type the command name.</span></span> <span data-ttu-id="462d0-239">**All** パラメーターは、セッション内の特定の名前を持つすべてのコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="462d0-239">The **All** parameter gets all commands with the specific name in the session.</span></span>

<span data-ttu-id="462d0-240">名前の競合を回避するには、コマンドレットの **NoClobber** パラメーターまたは **Prefix** パラメーターを使用し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-240">To prevent name conflicts, use the **NoClobber** or **Prefix** parameters of the `Import-Module` cmdlet.</span></span> <span data-ttu-id="462d0-241">**Prefix** パラメーターは、インポートされたコマンドの名前にプレフィックスを追加して、セッション内で一意になるようにします。</span><span class="sxs-lookup"><span data-stu-id="462d0-241">The **Prefix** parameter adds a prefix to the names of imported commands so that they are unique in the session.</span></span> <span data-ttu-id="462d0-242">**NoClobber** パラメーターでは、セッションの既存のコマンドを非表示にしたり、置き換えたりするコマンドはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="462d0-242">The **NoClobber** parameter does not import any commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="462d0-243">また、の **Alias**、 **コマンドレット**、 **関数**、および **Variable** パラメーターを使用して、 `Import-Module` インポートするコマンドだけを選択したり、セッションで名前の競合を引き起こすコマンドを除外したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="462d0-243">You can also use the **Alias**, **Cmdlet**, **Function**, and **Variable** parameters of `Import-Module` to select only the commands that you want to import, and you can exclude commands that cause name conflicts in your session.</span></span>

<span data-ttu-id="462d0-244">モジュールの作成者は、モジュールマニフェストの **Defaultcommandprefix** プロパティを使用して、すべてのコマンド名に既定のプレフィックスを追加することで、名前の競合を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="462d0-244">Module authors can prevent name conflicts by using the **DefaultCommandPrefix** property of the module manifest to add a default prefix to all command names.</span></span>
<span data-ttu-id="462d0-245">**Prefix** パラメーターの値は、 **defaultcommandprefix** の値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="462d0-245">The value of the **Prefix** parameter takes precedence over the value of **DefaultCommandPrefix**.</span></span>

<span data-ttu-id="462d0-246">コマンドが隠れているとしても、出所のモジュールまたはスナップインの名前でコマンド名を修飾すればコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="462d0-246">Even if a command is hidden, you can run it by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

<span data-ttu-id="462d0-247">PowerShell コマンドの優先順位規則は、セッションに同じ名前のコマンドが含まれている場合に実行されるコマンドを決定します。</span><span class="sxs-lookup"><span data-stu-id="462d0-247">The PowerShell command precedence rules determine which command runs when the session includes commands with the same name.</span></span>

<span data-ttu-id="462d0-248">たとえば、セッションに同じ名前の関数とコマンドレットが含まれている場合、PowerShell は既定で関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="462d0-248">For example, when a session includes a function and a cmdlet with the same name, PowerShell runs the function by default.</span></span> <span data-ttu-id="462d0-249">セッションに種類と名前が同じコマンドが含まれるとき、たとえば、2 つのコマンドレットの名前が同じ場合、既定では追加された日が新しいほうのコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="462d0-249">When the session includes commands of the same type with the same name, such as two cmdlets with the same name, by default, it runs the most recently added command.</span></span>

<span data-ttu-id="462d0-250">優先順位の規則の説明や、非表示のコマンドを実行する手順などの詳細については、「 [about_Command_Precedence](about_Command_Precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-250">For more information, including an explanation of the precedence rules and instructions for running hidden commands, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

## <a name="modules-and-snap-ins"></a><span data-ttu-id="462d0-251">モジュールとスナップイン</span><span class="sxs-lookup"><span data-stu-id="462d0-251">Modules and Snap-ins</span></span>

<span data-ttu-id="462d0-252">モジュールとスナップインからセッションにコマンドを追加できます。モジュールでは、コマンドレット、プロバイダー、関数、変数、エイリアス、PowerShell ドライブなどの項目を含む、すべての種類のコマンドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="462d0-252">You can add commands to your session from modules and snap-ins. Modules can add all types of commands, including cmdlets, providers, and functions, and items, such as variables, aliases, and PowerShell drives.</span></span> <span data-ttu-id="462d0-253">スナップインはコマンドレットとプロバイダーのみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="462d0-253">Snap-ins can add only cmdlets and providers.</span></span>

<span data-ttu-id="462d0-254">モジュールまたはスナップインをセッションから削除する前に、次のコマンドを利用し、削除するコマンドを決定します。</span><span class="sxs-lookup"><span data-stu-id="462d0-254">Before removing a module or snap-in from your session, use the following commands to determine which commands will be removed.</span></span>

<span data-ttu-id="462d0-255">セッション内のコマンドレットのソースを検索するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="462d0-255">To find the source of a cmdlet in your session, use the following command format:</span></span>

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

<span data-ttu-id="462d0-256">たとえば、コマンドレットのソースを検索するには、次のように `Get-Date` 入力します。</span><span class="sxs-lookup"><span data-stu-id="462d0-256">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

<span data-ttu-id="462d0-257">PowerShell スナップインの詳細については、「 [about_PSSnapins](about_PSSnapins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-257">For more information about PowerShell snap-ins, see [about_PSSnapins](about_PSSnapins.md).</span></span>

## <a name="module-related-warnings-and-errors"></a><span data-ttu-id="462d0-258">モジュール関連の警告とエラー</span><span class="sxs-lookup"><span data-stu-id="462d0-258">Module-related Warnings and Errors</span></span>

<span data-ttu-id="462d0-259">モジュールによってエクスポートされるコマンドは、PowerShell コマンドの名前付け規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="462d0-259">The commands that a module exports should follow the PowerShell command naming rules.</span></span> <span data-ttu-id="462d0-260">インポートしたモジュールが、名前に許可されていない動詞を持つコマンドレットまたは関数をエクスポートすると、 `Import-Module` コマンドレットは次の警告メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="462d0-260">If the module that you import exports cmdlets or functions that have unapproved verbs in their names, the `Import-Module` cmdlet displays the following warning message.</span></span>

> <span data-ttu-id="462d0-261">警告: インポートされたコマンド名には、検出できない可能性がある未承認の動詞が含まれています。</span><span class="sxs-lookup"><span data-stu-id="462d0-261">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="462d0-262">詳細については Verbose パラメーターを使用するか、「Get-Verb」と入力して承認されている動詞の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-262">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="462d0-263">このメッセージは、単なる警告です。</span><span class="sxs-lookup"><span data-stu-id="462d0-263">This message is only a warning.</span></span> <span data-ttu-id="462d0-264">実際には、非準拠のコマンドを含む、すべてのモジュールがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="462d0-264">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="462d0-265">モジュール ユーザーにメッセージが表示されますが、名前付けの問題はモジュール作成者が解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="462d0-265">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

<span data-ttu-id="462d0-266">警告メッセージを表示しないようにするには、コマンドレットの **DisableNameChecking** パラメーターを使用し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-266">To suppress the warning message, use the **DisableNameChecking** parameter of the `Import-Module` cmdlet.</span></span>

## <a name="built-in-modules-and-snap-ins"></a><span data-ttu-id="462d0-267">組み込みのモジュールおよびスナップイン</span><span class="sxs-lookup"><span data-stu-id="462d0-267">Built-in Modules and Snap-ins</span></span>

<span data-ttu-id="462d0-268">Powershell 2.0 および powershell 3.0 以降の旧形式のホストプログラムでは、powershell と共にインストールされるコアコマンドは、すべての PowerShell セッションに自動的に追加されるスナップインにパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="462d0-268">In PowerShell 2.0 and in older-style host programs in PowerShell 3.0 and later, the core commands that are installed with PowerShell are packaged in snap-ins that are added automatically to every PowerShell session.</span></span>

<span data-ttu-id="462d0-269">PowerShell 3.0 以降では、初期セッション状態 API を実装するホストプログラムに対して、 `InitialSessionState.CreateDefault2` 既定ではすべてのセッションに対して、powershell が追加されます。</span><span class="sxs-lookup"><span data-stu-id="462d0-269">Beginning in PowerShell 3.0, for host programs that implement the `InitialSessionState.CreateDefault2` initial session state API the Microsoft.PowerShell.Core snap-in is added to every session by default.</span></span> <span data-ttu-id="462d0-270">モジュールは最初の使用で自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="462d0-270">Modules are loaded automatically on first-use.</span></span>

> [!NOTE]
> <span data-ttu-id="462d0-271">コマンドレットを使用して開始されたセッションを含むリモートセッション `New-PSSession` は、組み込みのコマンドがスナップインにパッケージ化されている古い形式のセッションです。</span><span class="sxs-lookup"><span data-stu-id="462d0-271">Remote sessions, including sessions that are started by using the `New-PSSession` cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="462d0-272">次のモジュール (またはスナップイン) は、PowerShell と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="462d0-272">The following modules (or snap-ins) are installed with PowerShell.</span></span>

- <span data-ttu-id="462d0-273">CimCmdlets</span><span class="sxs-lookup"><span data-stu-id="462d0-273">CimCmdlets</span></span>
- <span data-ttu-id="462d0-274">Microsoft.PowerShell.Archive</span><span class="sxs-lookup"><span data-stu-id="462d0-274">Microsoft.PowerShell.Archive</span></span>
- <span data-ttu-id="462d0-275">Microsoft.PowerShell.Core</span><span class="sxs-lookup"><span data-stu-id="462d0-275">Microsoft.PowerShell.Core</span></span>
- <span data-ttu-id="462d0-276">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="462d0-276">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="462d0-277">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="462d0-277">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="462d0-278">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="462d0-278">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="462d0-279">Microsoft.PowerShell.ODataUtils</span><span class="sxs-lookup"><span data-stu-id="462d0-279">Microsoft.PowerShell.ODataUtils</span></span>
- <span data-ttu-id="462d0-280">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="462d0-280">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="462d0-281">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="462d0-281">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="462d0-282">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="462d0-282">Microsoft.WSMan.Management</span></span>
- <span data-ttu-id="462d0-283">PackageManagement</span><span class="sxs-lookup"><span data-stu-id="462d0-283">PackageManagement</span></span>
- <span data-ttu-id="462d0-284">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="462d0-284">PowerShellGet</span></span>
- <span data-ttu-id="462d0-285">PSDesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="462d0-285">PSDesiredStateConfiguration</span></span>
- <span data-ttu-id="462d0-286">PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="462d0-286">PSDiagnostics</span></span>
- <span data-ttu-id="462d0-287">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="462d0-287">PSScheduledJob</span></span>
- <span data-ttu-id="462d0-288">PSWorkflow</span><span class="sxs-lookup"><span data-stu-id="462d0-288">PSWorkflow</span></span>
- <span data-ttu-id="462d0-289">PSWorkflowUtility</span><span class="sxs-lookup"><span data-stu-id="462d0-289">PSWorkflowUtility</span></span>
- <span data-ttu-id="462d0-290">ISE</span><span class="sxs-lookup"><span data-stu-id="462d0-290">ISE</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="462d0-291">モジュールイベントのログ記録</span><span class="sxs-lookup"><span data-stu-id="462d0-291">Logging Module Events</span></span>

<span data-ttu-id="462d0-292">PowerShell 3.0 以降では、PowerShell モジュールおよびスナップイン内のコマンドレットと関数の実行イベントを記録できます。これを行うには、モジュールとスナップインの **Logpipelineexecutiondetails** プロパティをに設定し `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="462d0-292">Beginning in PowerShell 3.0, you can record execution events for the cmdlets and functions in PowerShell modules and snap-ins by setting the **LogPipelineExecutionDetails** property of modules and snap-ins to `$True`.</span></span>
<span data-ttu-id="462d0-293">また、グループポリシー設定を使用してモジュールのログ記録を有効にし、すべての PowerShell セッションでモジュールのログ記録を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="462d0-293">You can also use a Group Policy setting, Turn on Module Logging, to enable module logging in all PowerShell sessions.</span></span> <span data-ttu-id="462d0-294">詳細については、「 [about_EventLogs](about_EventLogs.md) 」および「 [about_Group_Policy_Settings](about_Group_Policy_Settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462d0-294">For more information, see [about_EventLogs](about_EventLogs.md) and [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="462d0-295">参照</span><span class="sxs-lookup"><span data-stu-id="462d0-295">See Also</span></span>

[<span data-ttu-id="462d0-296">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="462d0-296">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="462d0-297">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="462d0-297">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="462d0-298">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="462d0-298">about_PSSnapins</span></span>](about_PSSnapins.md)

[<span data-ttu-id="462d0-299">Get-Command</span><span class="sxs-lookup"><span data-stu-id="462d0-299">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="462d0-300">Get-Help</span><span class="sxs-lookup"><span data-stu-id="462d0-300">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="462d0-301">Get-Module</span><span class="sxs-lookup"><span data-stu-id="462d0-301">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="462d0-302">Import-Module</span><span class="sxs-lookup"><span data-stu-id="462d0-302">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="462d0-303">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="462d0-303">Remove-Module</span></span>](xref:Microsoft.PowerShell.Core.Remove-Module)

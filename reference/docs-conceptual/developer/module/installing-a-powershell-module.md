---
title: PowerShell モジュールのインストール |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb82827e-fdb7-4cbf-b3d4-093e72b3ff0e
caps.latest.revision: 28
ms.openlocfilehash: 60ac4bf9089232a9fa879e835e32da53422489fd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367071"
---
# <a name="installing-a-powershell-module"></a><span data-ttu-id="249fd-102">PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="249fd-102">Installing a PowerShell Module</span></span>

<span data-ttu-id="249fd-103">PowerShell モジュールを作成した後は、システムにモジュールをインストールして、自分や他のユーザーが使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="249fd-103">After you have created your PowerShell module, you will likely want to install the module on a system, so that you or others may use it.</span></span> <span data-ttu-id="249fd-104">一般に、これは、モジュールファイル (ie、hbase-runner.psm1、バイナリアセンブリ、モジュールマニフェスト、およびその他の関連ファイル) をそのコンピューター上のディレクトリにコピーすることで構成されます。</span><span class="sxs-lookup"><span data-stu-id="249fd-104">Generally speaking, this consists of copying the module files (ie, the .psm1, or the binary assembly, the module manifest, and any other associated files) onto a directory on that computer.</span></span> <span data-ttu-id="249fd-105">非常に小さなプロジェクトでは、Windows エクスプローラーを使用して1台のリモートコンピューターにファイルをコピーして貼り付けるのと同じように簡単に行うことができます。ただし、大規模なソリューションの場合は、より高度なインストールプロセスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="249fd-105">For a very small project, this may be as simple as copying and pasting the files with Windows Explorer onto a single remote computer; however, for larger solutions you may wish to use a more sophisticated installation process.</span></span> <span data-ttu-id="249fd-106">モジュールをシステムに取り込む方法に関係なく、PowerShell では、ユーザーがモジュールを見つけて使用できるようにするさまざまな手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="249fd-106">Regardless of how you get your module onto the system, PowerShell can use a number of techniques that will let users find and use your modules.</span></span> <span data-ttu-id="249fd-107">そのため、インストールの主な問題は、PowerShell がモジュールを検出できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="249fd-107">Therefore, the main issue for installation is ensuring that PowerShell will be able to find your module.</span></span> <span data-ttu-id="249fd-108">詳細については、「 [PowerShell モジュールのインポート](./importing-a-powershell-module.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="249fd-108">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="rules-for-installing-modules"></a><span data-ttu-id="249fd-109">モジュールをインストールするための規則</span><span class="sxs-lookup"><span data-stu-id="249fd-109">Rules for Installing Modules</span></span>

<span data-ttu-id="249fd-110">次の情報は、自分で使用するために作成したモジュール、他のパーティから取得したモジュール、他のユーザーに配布するモジュールなど、すべてのモジュールに関連しています。</span><span class="sxs-lookup"><span data-stu-id="249fd-110">The following information pertains to all modules, including modules that you create for your own use, modules that you get from other parties, and modules that you distribute to others.</span></span>

### <a name="install-modules-in-psmodulepath"></a><span data-ttu-id="249fd-111">PSModulePath にモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="249fd-111">Install Modules in PSModulePath</span></span>

<span data-ttu-id="249fd-112">可能な限り、 **PSModulePath**環境変数に記載されているパスにすべてのモジュールをインストールするか、 **PSModulePath**環境変数の値にモジュールパスを追加します。</span><span class="sxs-lookup"><span data-stu-id="249fd-112">Whenever possible, install all modules in a path that is listed in the **PSModulePath** environment variable or add the module path to the **PSModulePath** environment variable value.</span></span>

<span data-ttu-id="249fd-113">**PSModulePath**環境変数 ($Env:P SModulePath) には、Windows PowerShell モジュールの場所が含まれています。</span><span class="sxs-lookup"><span data-stu-id="249fd-113">The **PSModulePath** environment variable ($Env:PSModulePath) contains the locations of Windows PowerShell modules.</span></span> <span data-ttu-id="249fd-114">コマンドレットは、この環境変数の値に依存してモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="249fd-114">Cmdlets rely on the value of this environment variable to find modules.</span></span>

<span data-ttu-id="249fd-115">既定では、 **PSModulePath**環境変数の値には、次のシステムおよびユーザーモジュールのディレクトリが含まれていますが、値を追加して編集することができます。</span><span class="sxs-lookup"><span data-stu-id="249fd-115">By default, the **PSModulePath** environment variable value contains the following system and user module directories, but you can add to and edit the value.</span></span>

- <span data-ttu-id="249fd-116">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span><span class="sxs-lookup"><span data-stu-id="249fd-116">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span></span>

  > [!WARNING]
  > <span data-ttu-id="249fd-117">この場所は、Windows に付属するモジュール用に予約されています。</span><span class="sxs-lookup"><span data-stu-id="249fd-117">This location is reserved for modules that ship with Windows.</span></span> <span data-ttu-id="249fd-118">この場所にモジュールをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="249fd-118">Do not install modules to this location.</span></span>

- <span data-ttu-id="249fd-119">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="249fd-119">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span></span>

- <span data-ttu-id="249fd-120">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="249fd-120">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span></span>

  <span data-ttu-id="249fd-121">**PSModulePath**環境変数の値を取得するには、次のいずれかのコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="249fd-121">To get the value of the **PSModulePath** environment variable, use either of the following commands.</span></span>

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  <span data-ttu-id="249fd-122">**PSModulePath**環境変数の値の値にモジュールパスを追加するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="249fd-122">To add a module path to value of the **PSModulePath** environment variable value, use the following command format.</span></span> <span data-ttu-id="249fd-123">この形式で**は、SetEnvironmentVariable クラスの**メソッドを使用して、 **PSModulePath**環境変数に対するセッションに依存しない変更を行います。</span><span class="sxs-lookup"><span data-stu-id="249fd-123">This format uses the **SetEnvironmentVariable** method of the **System.Environment** class to make a session-independent change to the **PSModulePath** environment variable.</span></span>

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > <span data-ttu-id="249fd-124">パスを**PSModulePath**に追加したら、変更に関する環境メッセージをブロードキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="249fd-124">Once you have added the path to **PSModulePath**, you should broadcast an environment message about the change.</span></span> <span data-ttu-id="249fd-125">変更をブロードキャストすると、シェルなどの他のアプリケーションが変更を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="249fd-125">Broadcasting the change allows other applications, such as the shell, to pick up the change.</span></span> <span data-ttu-id="249fd-126">変更をブロードキャストするには、製品のインストールコードで、`lParam` が文字列 "Environment" に設定された**WM_SETTINGCHANGE**メッセージを送信するようにします。</span><span class="sxs-lookup"><span data-stu-id="249fd-126">To broadcast the change, have your product installation code send a **WM_SETTINGCHANGE** message with `lParam` set to the string "Environment".</span></span> <span data-ttu-id="249fd-127">モジュールのインストールコードが**PSModulePath**を更新した後に、必ずメッセージを送信してください。</span><span class="sxs-lookup"><span data-stu-id="249fd-127">Be sure to send the message after your module installation code has updated **PSModulePath**.</span></span>

### <a name="use-the-correct-module-directory-name"></a><span data-ttu-id="249fd-128">正しいモジュールディレクトリ名を使用する</span><span class="sxs-lookup"><span data-stu-id="249fd-128">Use the Correct Module Directory Name</span></span>

<span data-ttu-id="249fd-129">適切な形式のモジュールは、モジュールディレクトリ内の少なくとも1つのファイルの基本名と同じ名前のディレクトリに格納されているモジュールです。</span><span class="sxs-lookup"><span data-stu-id="249fd-129">A well-formed module is a module that is stored in a directory that has the same name as the base name of at least one file in the module directory.</span></span> <span data-ttu-id="249fd-130">モジュールが整形式でない場合、Windows PowerShell はそれをモジュールとして認識しません。</span><span class="sxs-lookup"><span data-stu-id="249fd-130">If a module is not well-formed, Windows PowerShell does not recognize it as a module.</span></span>

<span data-ttu-id="249fd-131">ファイルの "ベース名" は、ファイル名拡張子のない名前です。</span><span class="sxs-lookup"><span data-stu-id="249fd-131">The "base name" of a file is the name without the file name extension.</span></span> <span data-ttu-id="249fd-132">適切な形式のモジュールでは、モジュールファイルが格納されているディレクトリの名前が、モジュール内の少なくとも1つのファイルの基本名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="249fd-132">In a well-formed module, the name of the directory that contains the module files must match the base name of at least one file in the module.</span></span>

<span data-ttu-id="249fd-133">たとえば、サンプルの Fabrikam モジュールでは、モジュールファイルを含むディレクトリの名前は "Fabrikam" で、少なくとも1つのファイルには "Fabrikam" という基本名があります。</span><span class="sxs-lookup"><span data-stu-id="249fd-133">For example, in the sample Fabrikam module, the directory that contains the module files is named "Fabrikam" and at least one file has the "Fabrikam" base name.</span></span> <span data-ttu-id="249fd-134">この場合、.psd1 と Fabrikam の両方に "Fabrikam" という基本名があります。</span><span class="sxs-lookup"><span data-stu-id="249fd-134">In this case, both Fabrikam.psd1 and Fabrikam.dll have the "Fabrikam" base name.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a><span data-ttu-id="249fd-135">不適切なインストールの影響</span><span class="sxs-lookup"><span data-stu-id="249fd-135">Effect of Incorrect Installation</span></span>

<span data-ttu-id="249fd-136">モジュールが整形式ではなく、その場所が**PSModulePath**環境変数の値に含まれていない場合、次のような Windows PowerShell の基本的な検出機能は機能しません。</span><span class="sxs-lookup"><span data-stu-id="249fd-136">If the module is not well-formed and its location is not included in the value of the **PSModulePath** environment variable, basic discovery features of Windows PowerShell, such as the following, do not work.</span></span>

- <span data-ttu-id="249fd-137">モジュールの自動読み込み機能では、モジュールを自動的にインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="249fd-137">The Module Auto-Loading feature cannot import the module automatically.</span></span>

- <span data-ttu-id="249fd-138">[Get モジュール](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットの `ListAvailable` パラメーターがモジュールを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="249fd-138">The `ListAvailable` parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet cannot find the module.</span></span>

- <span data-ttu-id="249fd-139">モジュールの[インポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットがモジュールを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="249fd-139">The [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet cannot find the module.</span></span> <span data-ttu-id="249fd-140">モジュールをインポートするには、ルートモジュールファイルまたはモジュールマニフェストファイルへの完全パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249fd-140">To import the module, you must provide the full path to the root module file or module manifest file.</span></span>

  <span data-ttu-id="249fd-141">次のような追加機能は、モジュールがセッションにインポートされない限り機能しません。</span><span class="sxs-lookup"><span data-stu-id="249fd-141">Additional features, such as the following, do not work unless the module is imported into the session.</span></span> <span data-ttu-id="249fd-142">**PSModulePath**環境変数の適切な形式のモジュールでは、モジュールがセッションにインポートされていない場合でも、これらの機能は機能します。</span><span class="sxs-lookup"><span data-stu-id="249fd-142">In well-formed modules in the **PSModulePath** environment variable, these features work even when the module is not imported into the session.</span></span>

- <span data-ttu-id="249fd-143">[Get Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command)コマンドレットは、モジュール内のコマンドを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="249fd-143">The [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet cannot find commands in the module.</span></span>

- <span data-ttu-id="249fd-144">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)および update-help コマンドレットは、モジュールの[ヘルプを更新](/powershell/module/Microsoft.PowerShell.Core/Save-Help)したり、保存したりできません。</span><span class="sxs-lookup"><span data-stu-id="249fd-144">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets cannot update or save help for the module.</span></span>

- <span data-ttu-id="249fd-145">[コマンド](/powershell/module/Microsoft.PowerShell.Utility/Show-Command)レットでは、モジュール内のコマンドを見つけて表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="249fd-145">The [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet cannot find and display the commands in the module.</span></span>

  <span data-ttu-id="249fd-146">モジュール内のコマンドが、Windows PowerShell Integrated Scripting Environment (ISE) の [`Show-Command`] ウィンドウに表示されていません。</span><span class="sxs-lookup"><span data-stu-id="249fd-146">The commands in the module are missing from the `Show-Command` window in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="where-to-install-modules"></a><span data-ttu-id="249fd-147">モジュールをインストールする場所</span><span class="sxs-lookup"><span data-stu-id="249fd-147">Where to Install Modules</span></span>

<span data-ttu-id="249fd-148">このセクションでは、Windows PowerShell モジュールをインストールするファイルシステム内の場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="249fd-148">This section explains where in the file system to install Windows PowerShell modules.</span></span> <span data-ttu-id="249fd-149">場所は、モジュールの使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="249fd-149">The location depends on how the module is used.</span></span>

### <a name="installing-modules-for-a-specific-user"></a><span data-ttu-id="249fd-150">特定のユーザーのモジュールのインストール</span><span class="sxs-lookup"><span data-stu-id="249fd-150">Installing Modules for a Specific User</span></span>

<span data-ttu-id="249fd-151">独自のモジュールを作成する場合、または Windows PowerShell コミュニティ web サイトなどの別のパーティからモジュールを取得し、そのモジュールをユーザーアカウントでのみ使用できるようにする場合は、ユーザー固有の Modules ディレクトリにモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="249fd-151">If you create your own module or get a module from another party, such as a Windows PowerShell community website, and you want the module to be available for your user account only, install the module in your user-specific Modules directory.</span></span>

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

<span data-ttu-id="249fd-152">既定では、ユーザー固有の Modules ディレクトリが**PSModulePath**環境変数の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="249fd-152">The user-specific Modules directory is added to the value of the **PSModulePath** environment variable by default.</span></span>

### <a name="installing-modules-for-all-users-in-program-files"></a><span data-ttu-id="249fd-153">プログラムファイル内のすべてのユーザーのモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="249fd-153">Installing Modules for all Users in Program Files</span></span>

<span data-ttu-id="249fd-154">コンピューター上のすべてのユーザーアカウントでモジュールを使用できるようにするには、プログラムファイルの場所にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="249fd-154">If you want a module to be available to all user accounts on the computer, install the module in the Program Files location.</span></span>

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> <span data-ttu-id="249fd-155">Windows PowerShell 4.0 以降では、Program Files の場所は既定で PSModulePath 環境変数の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="249fd-155">The Program Files location is added to the value of the PSModulePath environment variable by default in Windows PowerShell 4.0 and later.</span></span> <span data-ttu-id="249fd-156">以前のバージョンの Windows PowerShell では、プログラムファイルの場所 (%ProgramFiles%\WindowsPowerShell\Modules) を手動で作成し、前述のように PSModulePath 環境変数にこのパスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="249fd-156">For earlier versions of Windows PowerShell, you can manually create the Program Files location ((%ProgramFiles%\WindowsPowerShell\Modules) and add this path to your PSModulePath environment variable as described above.</span></span>

### <a name="installing-modules-in-a-product-directory"></a><span data-ttu-id="249fd-157">製品ディレクトリへのモジュールのインストール</span><span class="sxs-lookup"><span data-stu-id="249fd-157">Installing Modules in a Product Directory</span></span>

<span data-ttu-id="249fd-158">他のパーティにモジュールを配布する場合は、上記の既定のプログラムファイルの場所を使用するか、% ProgramFiles% ディレクトリの会社固有または製品固有のサブディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="249fd-158">If you are distributing the module to other parties, use the default Program Files location described above, or create your own company-specific or product-specific subdirectory of the %ProgramFiles% directory.</span></span>

<span data-ttu-id="249fd-159">たとえば、架空の企業である Fabrikam テクノロジは、Fabrikam Manager 製品用の Windows PowerShell モジュールを出荷しています。</span><span class="sxs-lookup"><span data-stu-id="249fd-159">For example, Fabrikam Technologies, a fictitious company, is shipping a Windows PowerShell module for their Fabrikam Manager product.</span></span> <span data-ttu-id="249fd-160">モジュールインストーラーによって、Fabrikam Manager 製品サブディレクトリに Modules サブディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="249fd-160">Their module installer creates a Modules subdirectory in the Fabrikam Manager product subdirectory.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

<span data-ttu-id="249fd-161">Windows PowerShell モジュール検出機能を有効にして Fabrikam モジュールを見つけるには、Fabrikam モジュールインストーラーによって、モジュールの場所が**PSModulePath**環境変数の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="249fd-161">To enable the Windows PowerShell module discovery features to find the Fabrikam module, the Fabrikam module installer adds the module location to the value of the **PSModulePath** environment variable.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a><span data-ttu-id="249fd-162">Common Files ディレクトリへのモジュールのインストール</span><span class="sxs-lookup"><span data-stu-id="249fd-162">Installing Modules in the Common Files Directory</span></span>

<span data-ttu-id="249fd-163">1つの製品の複数のコンポーネントまたは複数のバージョンの製品でモジュールが使用されている場合は、%ProgramFiles%\Common Files\Modules サブディレクトリのモジュール固有のサブディレクトリにモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="249fd-163">If a module is used by multiple components of a product or by multiple versions of a product, install the module in a module-specific subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span>

<span data-ttu-id="249fd-164">次の例では、Fabrikam モジュールは `%ProgramFiles%\Common Files\Modules` サブディレクトリの Fabrikam サブディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="249fd-164">In the following example, the Fabrikam module is installed in a Fabrikam subdirectory of the `%ProgramFiles%\Common Files\Modules` subdirectory.</span></span> <span data-ttu-id="249fd-165">各モジュールは Modules サブディレクトリ内の独自のサブディレクトリに存在することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="249fd-165">Note that each module resides in its own subdirectory in the Modules subdirectory.</span></span>

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

<span data-ttu-id="249fd-166">次に、インストーラーによって、 **PSModulePath**環境変数の値に common files modules サブディレクトリのパスが確実に含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="249fd-166">Then, the installer assures the value of the **PSModulePath** environment variable includes the path of the common files modules subdirectory.</span></span>

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a><span data-ttu-id="249fd-167">モジュールの複数のバージョンのインストール</span><span class="sxs-lookup"><span data-stu-id="249fd-167">Installing Multiple Versions of a Module</span></span>

<span data-ttu-id="249fd-168">同じモジュールの複数のバージョンをインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="249fd-168">To install multiple versions of the same module, use the following procedure.</span></span>

1. <span data-ttu-id="249fd-169">モジュールのバージョンごとにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="249fd-169">Create a directory for each version of the module.</span></span> <span data-ttu-id="249fd-170">ディレクトリ名にバージョン番号を含めます。</span><span class="sxs-lookup"><span data-stu-id="249fd-170">Include the version number in the directory name.</span></span>
2. <span data-ttu-id="249fd-171">モジュールのバージョンごとにモジュールマニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="249fd-171">Create a module manifest for each version of the module.</span></span> <span data-ttu-id="249fd-172">マニフェストの**ModuleVersion**キーの値に、モジュールのバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="249fd-172">In the value of the **ModuleVersion** key in the manifest, enter the module version number.</span></span> <span data-ttu-id="249fd-173">マニフェストファイル (.psd1) をモジュールのバージョン固有のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="249fd-173">Save the manifest file (.psd1) in the version-specific directory for the module.</span></span>
3. <span data-ttu-id="249fd-174">次の例に示すように、モジュールルートフォルダーのパスを**PSModulePath**環境変数の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="249fd-174">Add the module root folder path to the value of the **PSModulePath** environment variable, as shown in the following examples.</span></span>

<span data-ttu-id="249fd-175">モジュールの特定のバージョンをインポートするために、エンドユーザーは、[モジュールのインポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットの `MinimumVersion` パラメーターまたは `RequiredVersion` パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="249fd-175">To import a particular version of the module, the end-user can use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="249fd-176">たとえば、Fabrikam モジュールをバージョン8.0 および9.0 で使用できる場合、Fabrikam モジュールのディレクトリ構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="249fd-176">For example, if the Fabrikam module is available in versions 8.0 and 9.0, the Fabrikam module directory structure might resemble the following.</span></span>

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

<span data-ttu-id="249fd-177">インストーラーによって、両方のモジュールパスが**PSModulePath**環境変数の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="249fd-177">The installer adds both of the module paths to the **PSModulePath** environment variable value.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

<span data-ttu-id="249fd-178">これらの手順が完了すると、 [Get Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットの**ListAvailable**パラメーターは、両方の Fabrikam モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="249fd-178">When these steps are complete, the **ListAvailable** parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet gets both of the Fabrikam modules.</span></span> <span data-ttu-id="249fd-179">特定のモジュールをインポートするには、[モジュールのインポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットの `MinimumVersion` パラメーターまたは `RequiredVersion` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="249fd-179">To import a particular module, use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="249fd-180">両方のモジュールが同じセッションにインポートされ、モジュールに同じ名前のコマンドレットが含まれている場合、最後にインポートされたコマンドレットはセッションで有効になります。</span><span class="sxs-lookup"><span data-stu-id="249fd-180">If both modules are imported into the same session, and the modules contain cmdlets with the same names, the cmdlets that are imported last are effective in the session.</span></span>

## <a name="handling-command-name-conflicts"></a><span data-ttu-id="249fd-181">コマンド名の競合の処理</span><span class="sxs-lookup"><span data-stu-id="249fd-181">Handling Command Name Conflicts</span></span>

<span data-ttu-id="249fd-182">コマンド名の競合は、モジュールがエクスポートするコマンドの名前がユーザーのセッションのコマンドと同じである場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="249fd-182">Command name conflicts can occur when the commands that a module exports have the same name as commands in the user's session.</span></span>

<span data-ttu-id="249fd-183">セッションに同じ名前の2つのコマンドが含まれている場合、Windows PowerShell は、優先されるコマンドの種類を実行します。</span><span class="sxs-lookup"><span data-stu-id="249fd-183">When a session contains two commands that have the same name, Windows PowerShell runs the command type that takes precedence.</span></span> <span data-ttu-id="249fd-184">セッションに同じ名前と同じ種類の2つのコマンドが含まれている場合、Windows PowerShell は、直前にセッションに追加されたコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="249fd-184">When a session contains two commands that have the same name and the same type, Windows PowerShell runs the command that was added to the session most recently.</span></span> <span data-ttu-id="249fd-185">既定では実行されないコマンドを実行する場合、ユーザーはコマンド名をモジュール名で修飾できます。</span><span class="sxs-lookup"><span data-stu-id="249fd-185">To run a command that is not run by default, users can qualify the command name with the module name.</span></span>

<span data-ttu-id="249fd-186">たとえば、セッションに `Get-Date` 関数と `Get-Date` コマンドレットが含まれている場合、Windows PowerShell は既定で関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="249fd-186">For example, if the session contains a `Get-Date` function and the `Get-Date` cmdlet, Windows PowerShell runs the function by default.</span></span> <span data-ttu-id="249fd-187">コマンドレットを実行するには、次のように、コマンドの先頭にモジュール名を付けます。</span><span class="sxs-lookup"><span data-stu-id="249fd-187">To run the cmdlet, preface the command with the module name, such as:</span></span>

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

<span data-ttu-id="249fd-188">名前の競合を防ぐために、モジュールの作成者はモジュールマニフェストの**Defaultcommandprefix**キーを使用して、モジュールからエクスポートされたすべてのコマンドの名詞プレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="249fd-188">To prevent name conflicts, module authors can use the **DefaultCommandPrefix** key in the module manifest to specify a noun prefix for all commands exported from the module.</span></span>

<span data-ttu-id="249fd-189">ユーザーは、`Import-Module` コマンドレットの**prefix**パラメーターを使用して、代替のプレフィックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="249fd-189">Users can use the **Prefix** parameter of the `Import-Module` cmdlet to use an alternate prefix.</span></span> <span data-ttu-id="249fd-190">**Prefix**パラメーターの値は、 **defaultcommandprefix**キーの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="249fd-190">The value of the **Prefix** parameter takes precedence over the value of the **DefaultCommandPrefix** key.</span></span>

## <a name="see-also"></a><span data-ttu-id="249fd-191">参照</span><span class="sxs-lookup"><span data-stu-id="249fd-191">See Also</span></span>

[<span data-ttu-id="249fd-192">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="249fd-192">about_Command_Precedence</span></span>](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[<span data-ttu-id="249fd-193">Windows PowerShell モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="249fd-193">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

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
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229457"
---
# <a name="installing-a-powershell-module"></a><span data-ttu-id="84e2b-102">PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="84e2b-102">Installing a PowerShell Module</span></span>

<span data-ttu-id="84e2b-103">PowerShell モジュールを作成した後は可能性がありますするシステムでは、モジュールをインストールするか他者が使用可能性がありますようにします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-103">After you have created your PowerShell module, you will likely want to install the module on a system, so that you or others may use it.</span></span> <span data-ttu-id="84e2b-104">一般に、このファイルをコピー モジュール (ie、.psm1 またはバイナリ アセンブリ、モジュール マニフェストおよび他の関連ファイル) をディレクトリにそのコンピューター上で構成されます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-104">Generally speaking, this consists of copying the module files (ie, the .psm1, or the binary assembly, the module manifest, and any other associated files) onto a directory on that computer.</span></span> <span data-ttu-id="84e2b-105">非常に小さいプロジェクトでは、コピーして、単一のリモート コンピューター上に Windows エクスプ ローラーでファイルを貼り付けるだけでこの可能性があります。ただし、大規模なソリューションのより高度なインストール プロセスを使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="84e2b-105">For a very small project, this may be as simple as copying and pasting the files with Windows Explorer onto a single remote computer; however, for larger solutions you may wish to use a more sophisticated installation process.</span></span> <span data-ttu-id="84e2b-106">PowerShell は、システム上に、モジュールを取得する方法に関係なく、さまざまな手法は、ユーザーを検索して、モジュールを使用できるを使用できます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-106">Regardless of how you get your module onto the system, PowerShell can use a number of techniques that will let users find and use your modules.</span></span> <span data-ttu-id="84e2b-107">そのため、インストールの主な問題では、PowerShell がモジュールを検索できることが確認します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-107">Therefore, the main issue for installation is ensuring that PowerShell will be able to find your module.</span></span> <span data-ttu-id="84e2b-108">詳細については、次を参照してください。 [PowerShell モジュールをインポートする](./importing-a-powershell-module.md)します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-108">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="rules-for-installing-modules"></a><span data-ttu-id="84e2b-109">モジュールをインストールするための規則</span><span class="sxs-lookup"><span data-stu-id="84e2b-109">Rules for Installing Modules</span></span>

<span data-ttu-id="84e2b-110">次の情報は、独自の使用、他のパーティから取得したモジュールや他のユーザーに配布するモジュールを作成するモジュールを含む、すべてのモジュールに関連します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-110">The following information pertains to all modules, including modules that you create for your own use, modules that you get from other parties, and modules that you distribute to others.</span></span>

### <a name="install-modules-in-psmodulepath"></a><span data-ttu-id="84e2b-111">Psmodulepath 環境変数でモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-111">Install Modules in PSModulePath</span></span>

<span data-ttu-id="84e2b-112">可能であればに記載されているパスにすべてのモジュールをインストール、 **PSModulePath**環境変数またはモジュールのパスを追加、 **PSModulePath**環境変数の値。</span><span class="sxs-lookup"><span data-stu-id="84e2b-112">Whenever possible, install all modules in a path that is listed in the **PSModulePath** environment variable or add the module path to the **PSModulePath** environment variable value.</span></span>

<span data-ttu-id="84e2b-113">**PSModulePath**環境変数 ($env:path: PSModulePath) Windows PowerShell モジュールの場所が格納されます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-113">The **PSModulePath** environment variable ($Env:PSModulePath) contains the locations of Windows PowerShell modules.</span></span> <span data-ttu-id="84e2b-114">コマンドレットは、モジュールを検索するには、この環境変数の値に依存します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-114">Cmdlets rely on the value of this environment variable to find modules.</span></span>

<span data-ttu-id="84e2b-115">既定で、 **PSModulePath**環境変数の値には、次のシステムとユーザー モジュール ディレクトリが含まれていますに追加し、値を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-115">By default, the **PSModulePath** environment variable value contains the following system and user module directories, but you can add to and edit the value.</span></span>

- <span data-ttu-id="84e2b-116">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span><span class="sxs-lookup"><span data-stu-id="84e2b-116">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span></span>

  > [!WARNING]
  > <span data-ttu-id="84e2b-117">この場所は、Windows に付属するモジュールの予約されています。</span><span class="sxs-lookup"><span data-stu-id="84e2b-117">This location is reserved for modules that ship with Windows.</span></span> <span data-ttu-id="84e2b-118">この場所にモジュールをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="84e2b-118">Do not install modules to this location.</span></span>

- <span data-ttu-id="84e2b-119">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="84e2b-119">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span></span>

- <span data-ttu-id="84e2b-120">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="84e2b-120">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span></span>

  <span data-ttu-id="84e2b-121">値を取得する、 **PSModulePath**環境変数では、次のコマンドのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-121">To get the value of the **PSModulePath** environment variable, use either of the following commands.</span></span>

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  <span data-ttu-id="84e2b-122">値にモジュールのパスを追加する、 **PSModulePath**環境変数値には、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-122">To add a module path to value of the **PSModulePath** environment variable value, use the following command format.</span></span> <span data-ttu-id="84e2b-123">この形式を使用して、 **SetEnvironmentVariable**のメソッド、 **System.Environment**クラスを変更するセッションに依存しない、 **PSModulePath**環境変数。</span><span class="sxs-lookup"><span data-stu-id="84e2b-123">This format uses the **SetEnvironmentVariable** method of the **System.Environment** class to make a session-independent change to the **PSModulePath** environment variable.</span></span>

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > <span data-ttu-id="84e2b-124">パスを追加した後**PSModulePath**、変更に関する、環境のメッセージをブロードキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84e2b-124">Once you have added the path to **PSModulePath**, you should broadcast an environment message about the change.</span></span> <span data-ttu-id="84e2b-125">他のアプリケーション、シェルなど、変更を認識するを変更をブロードキャストできます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-125">Broadcasting the change allows other applications, such as the shell, to pick up the change.</span></span> <span data-ttu-id="84e2b-126">変更をブロードキャストする送信製品インストール コードがある、 **WM_SETTINGCHANGE**メッセージである`lParam`文字列「環境」に設定します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-126">To broadcast the change, have your product installation code send a **WM_SETTINGCHANGE** message with `lParam` set to the string "Environment".</span></span> <span data-ttu-id="84e2b-127">モジュールのインストール コードが更新された後にメッセージを送信することを確認する**PSModulePath**します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-127">Be sure to send the message after your module installation code has updated **PSModulePath**.</span></span>

### <a name="use-the-correct-module-directory-name"></a><span data-ttu-id="84e2b-128">適切なモジュールのディレクトリ名を使用して、</span><span class="sxs-lookup"><span data-stu-id="84e2b-128">Use the Correct Module Directory Name</span></span>

<span data-ttu-id="84e2b-129">整形式のモジュールとは、モジュール ディレクトリ内の少なくとも 1 つのファイルの基本名と同じ名前を持つディレクトリに格納されているモジュールです。</span><span class="sxs-lookup"><span data-stu-id="84e2b-129">A well-formed module is a module that is stored in a directory that has the same name as the base name of at least one file in the module directory.</span></span> <span data-ttu-id="84e2b-130">モジュールが適切な形式でない場合は、Windows PowerShell で認識されませんをモジュールとして。</span><span class="sxs-lookup"><span data-stu-id="84e2b-130">If a module is not well-formed, Windows PowerShell does not recognize it as a module.</span></span>

<span data-ttu-id="84e2b-131">ファイルの「基本名」は、ファイル名拡張子を除いた名前です。</span><span class="sxs-lookup"><span data-stu-id="84e2b-131">The "base name" of a file is the name without the file name extension.</span></span> <span data-ttu-id="84e2b-132">整形式のモジュールでモジュール ファイルを含むディレクトリの名前がモジュール内の少なくとも 1 つのファイルの基本名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84e2b-132">In a well-formed module, the name of the directory that contains the module files must match the base name of at least one file in the module.</span></span>

<span data-ttu-id="84e2b-133">たとえば、サンプル Fabrikam モジュールで、"Fabrikam"という名前のモジュール ファイルを含むディレクトリし、を少なくとも 1 つのファイルは、"Fabrikam"基本名前。</span><span class="sxs-lookup"><span data-stu-id="84e2b-133">For example, in the sample Fabrikam module, the directory that contains the module files is named "Fabrikam" and at least one file has the "Fabrikam" base name.</span></span> <span data-ttu-id="84e2b-134">この場合、Fabrikam.psd1 と Fabrikam.dll の両方には、"Fabrikam"ベース名があります。</span><span class="sxs-lookup"><span data-stu-id="84e2b-134">In this case, both Fabrikam.psd1 and Fabrikam.dll have the "Fabrikam" base name.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a><span data-ttu-id="84e2b-135">あったり、インストールの影響</span><span class="sxs-lookup"><span data-stu-id="84e2b-135">Effect of Incorrect Installation</span></span>

<span data-ttu-id="84e2b-136">モジュールが整形式ではなくの値にその場所が含まれていない場合、 **PSModulePath**環境変数に次のよう Windows PowerShell での探索の基本的な機能が機能しません。</span><span class="sxs-lookup"><span data-stu-id="84e2b-136">If the module is not well-formed and its location is not included in the value of the **PSModulePath** environment variable, basic discovery features of Windows PowerShell, such as the following, do not work.</span></span>

- <span data-ttu-id="84e2b-137">モジュールの自動読み込み機能は、自動的にモジュールをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="84e2b-137">The Module Auto-Loading feature cannot import the module automatically.</span></span>

- <span data-ttu-id="84e2b-138">`ListAvailable`のパラメーター、 [Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットは、モジュールを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="84e2b-138">The `ListAvailable` parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet cannot find the module.</span></span>

- <span data-ttu-id="84e2b-139">[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットは、モジュールを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="84e2b-139">The [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet cannot find the module.</span></span> <span data-ttu-id="84e2b-140">モジュールをインポートするには、ルート モジュール ファイルまたはモジュール マニフェスト ファイルへの完全パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84e2b-140">To import the module, you must provide the full path to the root module file or module manifest file.</span></span>

  <span data-ttu-id="84e2b-141">モジュールがセッションにインポートしない限り、次などの追加機能が機能しません。</span><span class="sxs-lookup"><span data-stu-id="84e2b-141">Additional features, such as the following, do not work unless the module is imported into the session.</span></span> <span data-ttu-id="84e2b-142">整形式のモジュールで、 **PSModulePath**モジュールは、セッションにインポートされていない場合でもに環境変数では、これらの機能の動作します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-142">In well-formed modules in the **PSModulePath** environment variable, these features work even when the module is not imported into the session.</span></span>

- <span data-ttu-id="84e2b-143">[Get-command](/powershell/module/Microsoft.PowerShell.Core/Get-Command)コマンドレットは、モジュールのコマンドを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="84e2b-143">The [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet cannot find commands in the module.</span></span>

- <span data-ttu-id="84e2b-144">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)コマンドレットを更新またはモジュールのヘルプを保存できません。</span><span class="sxs-lookup"><span data-stu-id="84e2b-144">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets cannot update or save help for the module.</span></span>

- <span data-ttu-id="84e2b-145">[Show-command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command)コマンドレットは、検索し、モジュールのコマンドを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="84e2b-145">The [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet cannot find and display the commands in the module.</span></span>

  <span data-ttu-id="84e2b-146">モジュールのコマンドは表示されない、`Show-Command`ウィンドウで Windows PowerShell Integrated Scripting Environment (ISE)。</span><span class="sxs-lookup"><span data-stu-id="84e2b-146">The commands in the module are missing from the `Show-Command` window in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="where-to-install-modules"></a><span data-ttu-id="84e2b-147">モジュールをインストールする場所</span><span class="sxs-lookup"><span data-stu-id="84e2b-147">Where to Install Modules</span></span>

<span data-ttu-id="84e2b-148">このセクションでは、Windows PowerShell モジュールをインストールするファイル システムで場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-148">This section explains where in the file system to install Windows PowerShell modules.</span></span> <span data-ttu-id="84e2b-149">場所は、モジュールの使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="84e2b-149">The location depends on how the module is used.</span></span>

### <a name="installing-modules-for-a-specific-user"></a><span data-ttu-id="84e2b-150">特定のユーザーのモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-150">Installing Modules for a Specific User</span></span>

<span data-ttu-id="84e2b-151">独自のモジュールを作成するか、Windows PowerShell コミュニティ web サイトなどの別のパーティからモジュールを取得するユーザー アカウントのみで使用できるモジュールをする場合は、ユーザー固有の Modules ディレクトリで、モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-151">If you create your own module or get a module from another party, such as a Windows PowerShell community website, and you want the module to be available for your user account only, install the module in your user-specific Modules directory.</span></span>

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

<span data-ttu-id="84e2b-152">ユーザー固有のモジュール ディレクトリがの値に追加、 **PSModulePath**既定の環境変数。</span><span class="sxs-lookup"><span data-stu-id="84e2b-152">The user-specific Modules directory is added to the value of the **PSModulePath** environment variable by default.</span></span>

### <a name="installing-modules-for-all-users-in-program-files"></a><span data-ttu-id="84e2b-153">すべてのユーザーのプログラム ファイルのモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-153">Installing Modules for all Users in Program Files</span></span>

<span data-ttu-id="84e2b-154">モジュールをコンピューター上のすべてのユーザー アカウントに使用可能な場合は、プログラム ファイルの場所にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-154">If you want a module to be available to all user accounts on the computer, install the module in the Program Files location.</span></span>

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> <span data-ttu-id="84e2b-155">プログラム ファイルの場所は、既定では Windows PowerShell 4.0 以降、PSModulePath 環境変数の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-155">The Program Files location is added to the value of the PSModulePath environment variable by default in Windows PowerShell 4.0 and later.</span></span> <span data-ttu-id="84e2b-156">以前のバージョンの Windows PowerShell は、手動でプログラム ファイルの場所の ((%ProgramFiles%\WindowsPowerShell\Modules) を作成し、前述のように、このパスを PSModulePath 環境変数に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-156">For earlier versions of Windows PowerShell, you can manually create the Program Files location ((%ProgramFiles%\WindowsPowerShell\Modules) and add this path to your PSModulePath environment variable as described above.</span></span>

### <a name="installing-modules-in-a-product-directory"></a><span data-ttu-id="84e2b-157">製品ディレクトリ内のモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-157">Installing Modules in a Product Directory</span></span>

<span data-ttu-id="84e2b-158">他の当事者にモジュールを配布する場合は、上記で説明した既定のプログラム ファイルの場所を使用して、または %programfiles% ディレクトリの独自に固有の会社または製品に固有のサブディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-158">If you are distributing the module to other parties, use the default Program Files location described above, or create your own company-specific or product-specific subdirectory of the %ProgramFiles% directory.</span></span>

<span data-ttu-id="84e2b-159">たとえば、Fabrikam テクノロジ、架空の会社では、Fabrikam Manager 製品用の Windows PowerShell モジュールは出荷します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-159">For example, Fabrikam Technologies, a fictitious company, is shipping a Windows PowerShell module for their Fabrikam Manager product.</span></span> <span data-ttu-id="84e2b-160">そのモジュール インストーラーには、Fabrikam Manager 製品のサブディレクトリでモジュールのサブディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-160">Their module installer creates a Modules subdirectory in the Fabrikam Manager product subdirectory.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

<span data-ttu-id="84e2b-161">Fabrikam モジュールを検索する Windows PowerShell モジュールの検出機能を有効にするには、Fabrikam モジュール インストーラーでは、値にモジュールの場所を追加、 **PSModulePath**環境変数。</span><span class="sxs-lookup"><span data-stu-id="84e2b-161">To enable the Windows PowerShell module discovery features to find the Fabrikam module, the Fabrikam module installer adds the module location to the value of the **PSModulePath** environment variable.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a><span data-ttu-id="84e2b-162">一般的なファイルのディレクトリにモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-162">Installing Modules in the Common Files Directory</span></span>

<span data-ttu-id="84e2b-163">製品の複数のコンポーネントまたは製品の複数のバージョン、モジュールを使用する場合は、%ProgramFiles%\Common Files\Modules サブディレクトリのモジュールに固有のサブディレクトリに、モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-163">If a module is used by multiple components of a product or by multiple versions of a product, install the module in a module-specific subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span>

<span data-ttu-id="84e2b-164">Fabrikam のサブディレクトリに次の例では、Fabrikam のモジュールがインストールされている、`%ProgramFiles%\Common Files\Modules`サブディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="84e2b-164">In the following example, the Fabrikam module is installed in a Fabrikam subdirectory of the `%ProgramFiles%\Common Files\Modules` subdirectory.</span></span> <span data-ttu-id="84e2b-165">各モジュールがモジュールのサブディレクトリでは、そのサブディレクトリに格納されているに注意してください。</span><span class="sxs-lookup"><span data-stu-id="84e2b-165">Note that each module resides in its own subdirectory in the Modules subdirectory.</span></span>

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

<span data-ttu-id="84e2b-166">インストーラーがの値を保証し、 **PSModulePath**環境変数には、一般的なファイル モジュールのサブディレクトリのパスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="84e2b-166">Then, the installer assures the value of the **PSModulePath** environment variable includes the path of the common files modules subdirectory.</span></span>

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

## <a name="installing-multiple-versions-of-a-module"></a><span data-ttu-id="84e2b-167">モジュールの複数のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-167">Installing Multiple Versions of a Module</span></span>

<span data-ttu-id="84e2b-168">同じモジュールの複数のバージョンをインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-168">To install multiple versions of the same module, use the following procedure.</span></span>

1. <span data-ttu-id="84e2b-169">モジュールの各バージョン用のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-169">Create a directory for each version of the module.</span></span> <span data-ttu-id="84e2b-170">ディレクトリ名にバージョン番号を含めます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-170">Include the version number in the directory name.</span></span>
2. <span data-ttu-id="84e2b-171">モジュールの各バージョンのモジュール マニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-171">Create a module manifest for each version of the module.</span></span> <span data-ttu-id="84e2b-172">値で、 **ModuleVersion**マニフェストでキーに、モジュールのバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-172">In the value of the **ModuleVersion** key in the manifest, enter the module version number.</span></span> <span data-ttu-id="84e2b-173">モジュールのバージョン固有のディレクトリでマニフェスト ファイル (.psd1) を保存します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-173">Save the manifest file (.psd1) in the version-specific directory for the module.</span></span>
3. <span data-ttu-id="84e2b-174">値にモジュールのルート フォルダーのパスを追加、 **PSModulePath**環境変数は、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-174">Add the module root folder path to the value of the **PSModulePath** environment variable, as shown in the following examples.</span></span>

<span data-ttu-id="84e2b-175">特定のバージョンのモジュールをインポートする、エンドユーザーが使用できます、`MinimumVersion`または`RequiredVersion`のパラメーター、 [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="84e2b-175">To import a particular version of the module, the end-user can use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="84e2b-176">たとえば、Fabrikam モジュールをバージョン 8.0、9.0 で使用できる場合、Fabrikam のモジュールのディレクトリ構造は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84e2b-176">For example, if the Fabrikam module is available in versions 8.0 and 9.0, the Fabrikam module directory structure might resemble the following.</span></span>

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

<span data-ttu-id="84e2b-177">インストーラーの追加モジュールのパスの両方、 **PSModulePath**環境変数の値。</span><span class="sxs-lookup"><span data-stu-id="84e2b-177">The installer adds both of the module paths to the **PSModulePath** environment variable value.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

<span data-ttu-id="84e2b-178">これらの手順の完了時に、 **ListAvailable**のパラメーター、 [Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットは、Fabrikam のモジュールの両方を取得します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-178">When these steps are complete, the **ListAvailable** parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet gets both of the Fabrikam modules.</span></span> <span data-ttu-id="84e2b-179">特定のモジュールをインポートするには、使用、`MinimumVersion`または`RequiredVersion`のパラメーター、 [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="84e2b-179">To import a particular module, use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="84e2b-180">両方のモジュールは、同じセッションでインポート モジュールにはと同じ名前では、コマンドレットが含まれて、最後にインポートされているコマンドレットは、セッションで有効です。</span><span class="sxs-lookup"><span data-stu-id="84e2b-180">If both modules are imported into the same session, and the modules contain cmdlets with the same names, the cmdlets that are imported last are effective in the session.</span></span>

## <a name="handling-command-name-conflicts"></a><span data-ttu-id="84e2b-181">コマンド名の競合の処理</span><span class="sxs-lookup"><span data-stu-id="84e2b-181">Handling Command Name Conflicts</span></span>

<span data-ttu-id="84e2b-182">モジュールがエクスポートするコマンドがユーザーのセッションでコマンドと同じ名前を指定、コマンド名の競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-182">Command name conflicts can occur when the commands that a module exports have the same name as commands in the user's session.</span></span>

<span data-ttu-id="84e2b-183">セッションに同じ名前を持つ 2 つのコマンドが含まれている場合、Windows PowerShell には、優先するコマンドの種類が実行されます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-183">When a session contains two commands that have the same name, Windows PowerShell runs the command type that takes precedence.</span></span> <span data-ttu-id="84e2b-184">セッションに同じ名前と同じ型を持つ 2 つのコマンドが含まれている場合、Windows PowerShell は、最も最近のセッションに追加されたコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-184">When a session contains two commands that have the same name and the same type, Windows PowerShell runs the command that was added to the session most recently.</span></span> <span data-ttu-id="84e2b-185">既定では、実行されないコマンドを実行するには、ユーザーは、モジュール名でコマンド名を修飾できます。</span><span class="sxs-lookup"><span data-stu-id="84e2b-185">To run a command that is not run by default, users can qualify the command name with the module name.</span></span>

<span data-ttu-id="84e2b-186">セッションに含まれる場合など、`Get-Date`関数と`Get-Date`コマンドレットでは、Windows PowerShell は、既定では、関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-186">For example, if the session contains a `Get-Date` function and the `Get-Date` cmdlet, Windows PowerShell runs the function by default.</span></span> <span data-ttu-id="84e2b-187">コマンドレットを実行するには、など、モジュールの名前を持つコマンドを前します。</span><span class="sxs-lookup"><span data-stu-id="84e2b-187">To run the cmdlet, preface the command with the module name, such as:</span></span>

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

<span data-ttu-id="84e2b-188">名前の競合を防ぐためには、モジュールの作成者が使用できる、 **DefaultCommandPrefix**モジュールからすべてのコマンドの名詞プレフィックスを指定するモジュール マニフェストでキーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="84e2b-188">To prevent name conflicts, module authors can use the **DefaultCommandPrefix** key in the module manifest to specify a noun prefix for all commands exported from the module.</span></span>

<span data-ttu-id="84e2b-189">ユーザーが使用できる、**プレフィックス**のパラメーター、`Import-Module`代替プレフィックスを使用するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="84e2b-189">Users can use the **Prefix** parameter of the `Import-Module` cmdlet to use an alternate prefix.</span></span> <span data-ttu-id="84e2b-190">値、**プレフィックス**パラメーターの値よりも優先、 **DefaultCommandPrefix**キー。</span><span class="sxs-lookup"><span data-stu-id="84e2b-190">The value of the **Prefix** parameter takes precedence over the value of the **DefaultCommandPrefix** key.</span></span>

## <a name="see-also"></a><span data-ttu-id="84e2b-191">参照</span><span class="sxs-lookup"><span data-stu-id="84e2b-191">See Also</span></span>

[<span data-ttu-id="84e2b-192">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="84e2b-192">about_Command_Precedence</span></span>](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[<span data-ttu-id="84e2b-193">Windows PowerShell モジュールの記述</span><span class="sxs-lookup"><span data-stu-id="84e2b-193">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

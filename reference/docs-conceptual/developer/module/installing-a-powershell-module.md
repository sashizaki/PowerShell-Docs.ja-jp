---
ms.date: 09/13/2016
ms.topic: reference
title: PowerShell モジュールをインストールする
description: PowerShell モジュールをインストールする
ms.openlocfilehash: 3c7a4413168934ca4de1912c9615a6ae0fc45788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645329"
---
# <a name="installing-a-powershell-module"></a><span data-ttu-id="f0dc5-103">PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="f0dc5-103">Installing a PowerShell Module</span></span>

<span data-ttu-id="f0dc5-104">PowerShell モジュールを作成した後は、システムにモジュールをインストールして、自分や他のユーザーが使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-104">After you have created your PowerShell module, you will likely want to install the module on a system, so that you or others may use it.</span></span> <span data-ttu-id="f0dc5-105">一般に、その手順はモジュール ファイル (つまり、.psm1 またはバイナリ アセンブリ、モジュール マニフェスト、その他の関連ファイル) をそのコンピューター上のディレクトリにコピーすることで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-105">Generally speaking, this consists of copying the module files (ie, the .psm1, or the binary assembly, the module manifest, and any other associated files) onto a directory on that computer.</span></span> <span data-ttu-id="f0dc5-106">非常に小さなプロジェクトでは、Windows エクスプローラーを使用して 1 台のリモート コンピューター上にファイルをコピーして貼り付けるだけで済みます。ただし、大規模なソリューションの場合は、より高度なインストール プロセスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-106">For a very small project, this may be as simple as copying and pasting the files with Windows Explorer onto a single remote computer; however, for larger solutions you may wish to use a more sophisticated installation process.</span></span> <span data-ttu-id="f0dc5-107">モジュールをシステムに導入する方法に関係なく、PowerShell ではさまざまな手法を使用してモジュールを検索し、使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-107">Regardless of how you get your module onto the system, PowerShell can use a number of techniques that will let users find and use your modules.</span></span> <span data-ttu-id="f0dc5-108">そのため、インストールに関する主な問題は、PowerShell でモジュールを検索できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-108">Therefore, the main issue for installation is ensuring that PowerShell will be able to find your module.</span></span> <span data-ttu-id="f0dc5-109">詳細については、「[PowerShell モジュールをインポートする](./importing-a-powershell-module.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-109">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="rules-for-installing-modules"></a><span data-ttu-id="f0dc5-110">モジュールをインストールするための規則</span><span class="sxs-lookup"><span data-stu-id="f0dc5-110">Rules for Installing Modules</span></span>

<span data-ttu-id="f0dc5-111">以下の情報はすべてのモジュールに該当します。これには、自分で使用するために作成したモジュールや、他のパーティから取得したモジュール、他のユーザーに配布するモジュールなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-111">The following information pertains to all modules, including modules that you create for your own use, modules that you get from other parties, and modules that you distribute to others.</span></span>

### <a name="install-modules-in-psmodulepath"></a><span data-ttu-id="f0dc5-112">PSModulePath にモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="f0dc5-112">Install Modules in PSModulePath</span></span>

<span data-ttu-id="f0dc5-113">可能な場合は常に、すべてのモジュールを **PSModulePath** 環境変数に記載されているパスにインストールするか、**PSModulePath** 環境変数の値にモジュールのパスを追加します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-113">Whenever possible, install all modules in a path that is listed in the **PSModulePath** environment variable or add the module path to the **PSModulePath** environment variable value.</span></span>

<span data-ttu-id="f0dc5-114">**PSModulePath** 環境変数 ($Env:PSModulePath) には、Windows PowerShell モジュールの場所が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-114">The **PSModulePath** environment variable ($Env:PSModulePath) contains the locations of Windows PowerShell modules.</span></span> <span data-ttu-id="f0dc5-115">コマンドレットでは、この環境変数の値に依存してモジュールが検索されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-115">Cmdlets rely on the value of this environment variable to find modules.</span></span>

<span data-ttu-id="f0dc5-116">既定では、**PSModulePath** 環境変数の値には次のシステムおよびユーザー モジュールのディレクトリが含まれていますが、追加したり値を編集したりできます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-116">By default, the **PSModulePath** environment variable value contains the following system and user module directories, but you can add to and edit the value.</span></span>

- <span data-ttu-id="f0dc5-117">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span><span class="sxs-lookup"><span data-stu-id="f0dc5-117">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span></span>

  > [!WARNING]
  > <span data-ttu-id="f0dc5-118">この場所は Windows に付属するモジュール用に予約されています。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-118">This location is reserved for modules that ship with Windows.</span></span> <span data-ttu-id="f0dc5-119">この場所にモジュールをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-119">Do not install modules to this location.</span></span>

- <span data-ttu-id="f0dc5-120">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="f0dc5-120">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span></span>

- <span data-ttu-id="f0dc5-121">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="f0dc5-121">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span></span>

  <span data-ttu-id="f0dc5-122">**PSModulePath** 環境変数の値を取得するには、次のいずれかのコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-122">To get the value of the **PSModulePath** environment variable, use either of the following commands.</span></span>

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  <span data-ttu-id="f0dc5-123">**PSModulePath** 環境変数の値にモジュール パスを追加するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-123">To add a module path to value of the **PSModulePath** environment variable value, use the following command format.</span></span> <span data-ttu-id="f0dc5-124">この形式では、**System.Environment** クラスの **SetEnvironmentVariable** メソッドを使用して、**PSModulePath** 環境変数に対してセッションに依存しない変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-124">This format uses the **SetEnvironmentVariable** method of the **System.Environment** class to make a session-independent change to the **PSModulePath** environment variable.</span></span>

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > <span data-ttu-id="f0dc5-125">**PSModulePath** にパスを追加したら、その変更に関する環境メッセージを配信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-125">Once you have added the path to **PSModulePath**, you should broadcast an environment message about the change.</span></span> <span data-ttu-id="f0dc5-126">変更内容を配信することによって、シェルなどの他のアプリケーションで変更を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-126">Broadcasting the change allows other applications, such as the shell, to pick up the change.</span></span> <span data-ttu-id="f0dc5-127">変更内容を配信するには、製品のインストール コードによって、`lParam` が文字列 "Environment" に設定された **WM_SETTINGCHANGE** メッセージを送信させます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-127">To broadcast the change, have your product installation code send a **WM_SETTINGCHANGE** message with `lParam` set to the string "Environment".</span></span> <span data-ttu-id="f0dc5-128">モジュールのインストール コードによって **PSModulePath** が更新された後にメッセージを送信してください。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-128">Be sure to send the message after your module installation code has updated **PSModulePath**.</span></span>

### <a name="use-the-correct-module-directory-name"></a><span data-ttu-id="f0dc5-129">正しいモジュール ディレクトリ名を使用する</span><span class="sxs-lookup"><span data-stu-id="f0dc5-129">Use the Correct Module Directory Name</span></span>

<span data-ttu-id="f0dc5-130">適切な形式のモジュールは、モジュール ディレクトリ内の少なくとも 1 つのファイルのベース名と同じ名前を持つディレクトリに格納されているモジュールです。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-130">A well-formed module is a module that is stored in a directory that has the same name as the base name of at least one file in the module directory.</span></span> <span data-ttu-id="f0dc5-131">モジュールの形式が適切でない場合は、Windows PowerShell によってモジュールとして認識されません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-131">If a module is not well-formed, Windows PowerShell does not recognize it as a module.</span></span>

<span data-ttu-id="f0dc5-132">ファイルの "ベース名" とは、ファイル名の拡張子を除いた名前です。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-132">The "base name" of a file is the name without the file name extension.</span></span> <span data-ttu-id="f0dc5-133">適切な形式のモジュールでは、モジュール ファイルを含むディレクトリの名前が、モジュール内の少なくとも 1 つのファイルのベース名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-133">In a well-formed module, the name of the directory that contains the module files must match the base name of at least one file in the module.</span></span>

<span data-ttu-id="f0dc5-134">たとえば、サンプルの Fabrikam モジュールでは、モジュール ファイルを含むディレクトリの名前は "Fabrikam" であり、少なくとも 1 つのファイルが "Fabrikam" というベース名を持っています。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-134">For example, in the sample Fabrikam module, the directory that contains the module files is named "Fabrikam" and at least one file has the "Fabrikam" base name.</span></span> <span data-ttu-id="f0dc5-135">この場合、Fabrikam.psd1 と Fabrikam.dll の両方が "Fabrikam" というベース名を持っています。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-135">In this case, both Fabrikam.psd1 and Fabrikam.dll have the "Fabrikam" base name.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a><span data-ttu-id="f0dc5-136">不適切なインストールの影響</span><span class="sxs-lookup"><span data-stu-id="f0dc5-136">Effect of Incorrect Installation</span></span>

<span data-ttu-id="f0dc5-137">モジュールの形式が適切でなく、その場所が **PSModulePath** 環境変数の値に含まれていない場合、次のような Windows PowerShell の基本的な検出機能が機能しません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-137">If the module is not well-formed and its location is not included in the value of the **PSModulePath** environment variable, basic discovery features of Windows PowerShell, such as the following, do not work.</span></span>

- <span data-ttu-id="f0dc5-138">モジュールの自動読み込み機能で、モジュールを自動的にインポートすることができません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-138">The Module Auto-Loading feature cannot import the module automatically.</span></span>

- <span data-ttu-id="f0dc5-139">[Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) コマンドレットの `ListAvailable` パラメーターでモジュールを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-139">The `ListAvailable` parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet cannot find the module.</span></span>

- <span data-ttu-id="f0dc5-140">[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) コマンドレットでモジュールを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-140">The [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet cannot find the module.</span></span> <span data-ttu-id="f0dc5-141">モジュールをインポートするには、ルート モジュール ファイルまたはモジュール マニフェスト ファイルへの完全なパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-141">To import the module, you must provide the full path to the root module file or module manifest file.</span></span>

  <span data-ttu-id="f0dc5-142">次のような追加機能は、モジュールがセッションにインポートされない限り機能しません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-142">Additional features, such as the following, do not work unless the module is imported into the session.</span></span> <span data-ttu-id="f0dc5-143">**PSModulePath** 環境変数に含まれている適切な形式のモジュールでは、モジュールがセッションにインポートされていない場合でも、これらの機能は動作します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-143">In well-formed modules in the **PSModulePath** environment variable, these features work even when the module is not imported into the session.</span></span>

- <span data-ttu-id="f0dc5-144">[Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) コマンドレットでモジュール内のコマンドを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-144">The [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet cannot find commands in the module.</span></span>

- <span data-ttu-id="f0dc5-145">[Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) および [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) コマンドレットで、モジュールのヘルプを更新または保存できません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-145">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets cannot update or save help for the module.</span></span>

- <span data-ttu-id="f0dc5-146">[Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) コマンドレットで、モジュール内のコマンドを検索して表示することができません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-146">The [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet cannot find and display the commands in the module.</span></span>

  <span data-ttu-id="f0dc5-147">モジュール内のコマンドは、Windows PowerShell Integrated Scripting Environment (ISE) の [`Show-Command`] ウィンドウに表示されません。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-147">The commands in the module are missing from the `Show-Command` window in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="where-to-install-modules"></a><span data-ttu-id="f0dc5-148">モジュールをインストールする場所</span><span class="sxs-lookup"><span data-stu-id="f0dc5-148">Where to Install Modules</span></span>

<span data-ttu-id="f0dc5-149">このセクションでは、ファイル システム内のどこに Windows PowerShell モジュールをインストールするかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-149">This section explains where in the file system to install Windows PowerShell modules.</span></span> <span data-ttu-id="f0dc5-150">その場所はモジュールの使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-150">The location depends on how the module is used.</span></span>

### <a name="installing-modules-for-a-specific-user"></a><span data-ttu-id="f0dc5-151">特定のユーザー用にモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="f0dc5-151">Installing Modules for a Specific User</span></span>

<span data-ttu-id="f0dc5-152">独自のモジュールを作成したり、Windows PowerShell コミュニティ Web サイトなどの他のパーティからモジュールを取得したりして、そのモジュールを自分のユーザー アカウントでのみ使用できるようにしたい場合は、ユーザー固有の Modules ディレクトリにモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-152">If you create your own module or get a module from another party, such as a Windows PowerShell community website, and you want the module to be available for your user account only, install the module in your user-specific Modules directory.</span></span>

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

<span data-ttu-id="f0dc5-153">ユーザー固有の Modules ディレクトリは、既定で **PSModulePath** 環境変数の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-153">The user-specific Modules directory is added to the value of the **PSModulePath** environment variable by default.</span></span>

### <a name="installing-modules-for-all-users-in-program-files"></a><span data-ttu-id="f0dc5-154">すべてのユーザー用に Program Files にモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="f0dc5-154">Installing Modules for all Users in Program Files</span></span>

<span data-ttu-id="f0dc5-155">コンピューター上のすべてのユーザー アカウントでモジュールを使用できるようにするには、Program Files の場所にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-155">If you want a module to be available to all user accounts on the computer, install the module in the Program Files location.</span></span>

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> <span data-ttu-id="f0dc5-156">Windows PowerShell 4.0 以降では、Program Files の場所は既定で PSModulePath 環境変数の値に追加されています。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-156">The Program Files location is added to the value of the PSModulePath environment variable by default in Windows PowerShell 4.0 and later.</span></span> <span data-ttu-id="f0dc5-157">以前のバージョンの Windows PowerShell では、Program Files の場所 (%ProgramFiles%\WindowsPowerShell\Modules) を手動で作成し、前述のように PSModulePath 環境変数にこのパスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-157">For earlier versions of Windows PowerShell, you can manually create the Program Files location (%ProgramFiles%\WindowsPowerShell\Modules) and add this path to your PSModulePath environment variable as described above.</span></span>

### <a name="installing-modules-in-a-product-directory"></a><span data-ttu-id="f0dc5-158">製品ディレクトリにモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="f0dc5-158">Installing Modules in a Product Directory</span></span>

<span data-ttu-id="f0dc5-159">他のパーティにモジュールを配布する場合は、上で説明した既定の Program Files の場所を使用するか、%ProgramFiles% ディレクトリに対して独自の会社固有または製品固有のサブディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-159">If you are distributing the module to other parties, use the default Program Files location described above, or create your own company-specific or product-specific subdirectory of the %ProgramFiles% directory.</span></span>

<span data-ttu-id="f0dc5-160">たとえば、架空の企業である Fabrikam Technologies では、Fabrikam Manager 製品用の Windows PowerShell モジュールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-160">For example, Fabrikam Technologies, a fictitious company, is shipping a Windows PowerShell module for their Fabrikam Manager product.</span></span> <span data-ttu-id="f0dc5-161">そのモジュールのインストーラーによって、Fabrikam Manager 製品サブディレクトリ内に Modules サブディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-161">Their module installer creates a Modules subdirectory in the Fabrikam Manager product subdirectory.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

<span data-ttu-id="f0dc5-162">Windows PowerShell のモジュール検出機能で Fabrikam モジュールを検索できるようにするために、Fabrikam モジュールのインストーラーによってモジュールの場所が **PSModulePath** 環境変数の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-162">To enable the Windows PowerShell module discovery features to find the Fabrikam module, the Fabrikam module installer adds the module location to the value of the **PSModulePath** environment variable.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a><span data-ttu-id="f0dc5-163">Common Files ディレクトリにモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="f0dc5-163">Installing Modules in the Common Files Directory</span></span>

<span data-ttu-id="f0dc5-164">製品の複数のコンポーネント、または製品の複数のバージョンでモジュールが使用される場合は、%ProgramFiles%\Common Files\Modules サブディレクトリのモジュール固有のサブディレクトリにモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-164">If a module is used by multiple components of a product or by multiple versions of a product, install the module in a module-specific subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span>

<span data-ttu-id="f0dc5-165">次の例では、Fabrikam モジュールは `%ProgramFiles%\Common Files\Modules` サブディレクトリの Fabrikam サブディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-165">In the following example, the Fabrikam module is installed in a Fabrikam subdirectory of the `%ProgramFiles%\Common Files\Modules` subdirectory.</span></span> <span data-ttu-id="f0dc5-166">各モジュールが Modules サブディレクトリ内の独自のサブディレクトリ内にあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-166">Note that each module resides in its own subdirectory in the Modules subdirectory.</span></span>

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

<span data-ttu-id="f0dc5-167">次に、インストーラーによって、**PSModulePath** 環境変数の値に Common Files の Modules サブディレクトリのパスが含まれていることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-167">Then, the installer assures the value of the **PSModulePath** environment variable includes the path of the common files modules subdirectory.</span></span>

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

## <a name="installing-multiple-versions-of-a-module"></a><span data-ttu-id="f0dc5-168">複数のバージョンのモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="f0dc5-168">Installing Multiple Versions of a Module</span></span>

<span data-ttu-id="f0dc5-169">同じモジュールの複数のバージョンをインストールするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-169">To install multiple versions of the same module, use the following procedure.</span></span>

1. <span data-ttu-id="f0dc5-170">モジュールのバージョンごとにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-170">Create a directory for each version of the module.</span></span> <span data-ttu-id="f0dc5-171">ディレクトリ名にバージョン番号を含めます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-171">Include the version number in the directory name.</span></span>
2. <span data-ttu-id="f0dc5-172">モジュールのバージョンごとにモジュール マニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-172">Create a module manifest for each version of the module.</span></span> <span data-ttu-id="f0dc5-173">マニフェストの **ModuleVersion** キーの値に、モジュールのバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-173">In the value of the **ModuleVersion** key in the manifest, enter the module version number.</span></span> <span data-ttu-id="f0dc5-174">マニフェスト ファイル (.psd1) をモジュールのバージョン固有のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-174">Save the manifest file (.psd1) in the version-specific directory for the module.</span></span>
3. <span data-ttu-id="f0dc5-175">次の例に示すように、モジュールのルート フォルダーのパスを **PSModulePath** 環境変数の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-175">Add the module root folder path to the value of the **PSModulePath** environment variable, as shown in the following examples.</span></span>

<span data-ttu-id="f0dc5-176">エンド ユーザーは、[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) コマンドレットの `MinimumVersion` または `RequiredVersion` パラメーターを使用して、モジュールの特定のバージョンをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-176">To import a particular version of the module, the end-user can use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="f0dc5-177">たとえば、Fabrikam モジュールのバージョン 8.0 と 9.0 を使用できる場合は、Fabrikam モジュールのディレクトリ構造は次のようになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-177">For example, if the Fabrikam module is available in versions 8.0 and 9.0, the Fabrikam module directory structure might resemble the following.</span></span>

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

<span data-ttu-id="f0dc5-178">インストーラーによって、両方のモジュール パスが **PSModulePath** 環境変数の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-178">The installer adds both of the module paths to the **PSModulePath** environment variable value.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

<span data-ttu-id="f0dc5-179">これらの手順が完了すると、[Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) コマンドレットの **ListAvailable** パラメーターによって、両方の Fabrikam モジュールが取得されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-179">When these steps are complete, the **ListAvailable** parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet gets both of the Fabrikam modules.</span></span> <span data-ttu-id="f0dc5-180">特定のモジュールをインポートするには、[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) コマンドレットの `MinimumVersion` または `RequiredVersion` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-180">To import a particular module, use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="f0dc5-181">両方のモジュールが同じセッションにインポートされ、モジュールに同じ名前のコマンドレットが含まれている場合は、最後にインポートされたコマンドレットがそのセッションで有効になります。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-181">If both modules are imported into the same session, and the modules contain cmdlets with the same names, the cmdlets that are imported last are effective in the session.</span></span>

## <a name="handling-command-name-conflicts"></a><span data-ttu-id="f0dc5-182">コマンド名の競合を処理する</span><span class="sxs-lookup"><span data-stu-id="f0dc5-182">Handling Command Name Conflicts</span></span>

<span data-ttu-id="f0dc5-183">モジュールによってエクスポートされたコマンドがユーザーのセッション内のコマンドと同じ名前を持つ場合、コマンド名の競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-183">Command name conflicts can occur when the commands that a module exports have the same name as commands in the user's session.</span></span>

<span data-ttu-id="f0dc5-184">セッションに同じ名前を持つコマンドが 2 つ含まれている場合、Windows PowerShell では優先されるコマンドの種類が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-184">When a session contains two commands that have the same name, Windows PowerShell runs the command type that takes precedence.</span></span> <span data-ttu-id="f0dc5-185">セッションに同じ名前と同じ種類を持つコマンドが 2 つ含まれている場合、Windows PowerShell では、最後にセッションに追加されたコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-185">When a session contains two commands that have the same name and the same type, Windows PowerShell runs the command that was added to the session most recently.</span></span> <span data-ttu-id="f0dc5-186">既定では実行されないコマンドを実行する場合、ユーザーはコマンド名をモジュール名で修飾できます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-186">To run a command that is not run by default, users can qualify the command name with the module name.</span></span>

<span data-ttu-id="f0dc5-187">たとえば、セッションに `Get-Date` 関数と `Get-Date` コマンドレットが含まれている場合、Windows PowerShell では既定で関数が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-187">For example, if the session contains a `Get-Date` function and the `Get-Date` cmdlet, Windows PowerShell runs the function by default.</span></span> <span data-ttu-id="f0dc5-188">コマンドレットを実行するには、次のように、コマンドの前にモジュール名を付けます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-188">To run the cmdlet, preface the command with the module name, such as:</span></span>

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

<span data-ttu-id="f0dc5-189">名前の競合を防ぐために、モジュールの作成者はモジュール マニフェストの **DefaultCommandPrefix** キーを使用して、モジュールからエクスポートされるすべてのコマンドに対する名詞プレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-189">To prevent name conflicts, module authors can use the **DefaultCommandPrefix** key in the module manifest to specify a noun prefix for all commands exported from the module.</span></span>

<span data-ttu-id="f0dc5-190">ユーザーは、`Import-Module` コマンドレットの **Prefix** パラメーターを使用して代替プレフィックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-190">Users can use the **Prefix** parameter of the `Import-Module` cmdlet to use an alternate prefix.</span></span> <span data-ttu-id="f0dc5-191">**Prefix** パラメーターの値は、**DefaultCommandPrefix** キーの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f0dc5-191">The value of the **Prefix** parameter takes precedence over the value of the **DefaultCommandPrefix** key.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0dc5-192">参照</span><span class="sxs-lookup"><span data-stu-id="f0dc5-192">See Also</span></span>

[<span data-ttu-id="f0dc5-193">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="f0dc5-193">about_Command_Precedence</span></span>](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[<span data-ttu-id="f0dc5-194">Windows PowerShell モジュールを記述する</span><span class="sxs-lookup"><span data-stu-id="f0dc5-194">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

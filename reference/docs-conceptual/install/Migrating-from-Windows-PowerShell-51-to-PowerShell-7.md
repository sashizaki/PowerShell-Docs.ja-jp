---
title: Windows PowerShell 5.1 から PowerShell 7 への移行
description: Windows プラットフォームで PowerShell 5.1 から PowerShell 7 に更新します。
ms.date: 03/25/2020
ms.openlocfilehash: cb14a4f159b6dc33f31386da4264c0ebb640aef8
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809208"
---
# <a name="migrating-from-windows-powershell-51-to-powershell-7"></a><span data-ttu-id="f5b54-103">Windows PowerShell 5.1 から PowerShell 7 への移行</span><span class="sxs-lookup"><span data-stu-id="f5b54-103">Migrating from Windows PowerShell 5.1 to PowerShell 7</span></span>

<span data-ttu-id="f5b54-104">クラウド、オンプレミス、およびハイブリッド環境向けに設計された PowerShell 7 には、強化された機能と[新機能](../whats-new/What-s-New-in-PowerShell-70.md)が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-104">Designed for cloud, on-premises, and hybrid environments, PowerShell 7 is packed with enhancements and [new features](../whats-new/What-s-New-in-PowerShell-70.md).</span></span>

- <span data-ttu-id="f5b54-105">Windows PowerShell とのサイド バイ サイドのインストールおよび実行</span><span class="sxs-lookup"><span data-stu-id="f5b54-105">Installs and runs side-by-side with Windows PowerShell</span></span>
- <span data-ttu-id="f5b54-106">既存の Windows PowerShell モジュールとの強化された互換性</span><span class="sxs-lookup"><span data-stu-id="f5b54-106">Improved compatibility with existing Windows PowerShell modules</span></span>
- <span data-ttu-id="f5b54-107">三項演算子や `ForEach-Object -Parallel` などの新しい言語機能</span><span class="sxs-lookup"><span data-stu-id="f5b54-107">New language features, like ternary operators and `ForEach-Object -Parallel`</span></span>
- <span data-ttu-id="f5b54-108">パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="f5b54-108">Improved performance</span></span>
- <span data-ttu-id="f5b54-109">SSH ベースのリモート処理</span><span class="sxs-lookup"><span data-stu-id="f5b54-109">SSH-based remoting</span></span>
- <span data-ttu-id="f5b54-110">クロス プラットフォームの相互運用性</span><span class="sxs-lookup"><span data-stu-id="f5b54-110">Cross-platform interoperability</span></span>
- <span data-ttu-id="f5b54-111">Docker コンテナーのサポート</span><span class="sxs-lookup"><span data-stu-id="f5b54-111">Support for Docker containers</span></span>

<span data-ttu-id="f5b54-112">PowerShell 7 は Windows PowerShell とサイド バイ サイドで動作するため、簡単にテストを行い、展開前にエディション間で比較することができます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-112">PowerShell 7 works side-by-side with Windows PowerShell letting you easily test and compare between editions before deployment.</span></span> <span data-ttu-id="f5b54-113">簡単に、すばやく、安全に移行できます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-113">Migration is simple, quick, and safe.</span></span>

<span data-ttu-id="f5b54-114">PowerShell 7 は、次の Windows オペレーティング システムでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-114">PowerShell 7 is supported on the following Windows operating systems:</span></span>

- <span data-ttu-id="f5b54-115">Windows 8.1 および 10</span><span class="sxs-lookup"><span data-stu-id="f5b54-115">Windows 8.1 and 10</span></span>
- <span data-ttu-id="f5b54-116">Windows Server 2012、2012 R2、2016、2019</span><span class="sxs-lookup"><span data-stu-id="f5b54-116">Windows Server 2012, 2012 R2, 2016, and 2019</span></span>

<span data-ttu-id="f5b54-117">PowerShell 7 は、macOS と、いくつかの Linux ディストリビューションでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-117">PowerShell 7 also runs on macOS and several Linux distributions.</span></span> <span data-ttu-id="f5b54-118">サポートされているオペレーティング システムの一覧と、サポート ライフサイクルの詳細については、「[PowerShell のサポート ライフサイクル](/powershell/scripting/powershell-support-lifecycle)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-118">For a list of supported operating systems and information about the support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle).</span></span>

## <a name="installing-powershell-7"></a><span data-ttu-id="f5b54-119">PowerShell 7 のインストール</span><span class="sxs-lookup"><span data-stu-id="f5b54-119">Installing PowerShell 7</span></span>

<span data-ttu-id="f5b54-120">柔軟性を確保し、IT、DevOps エンジニア、および開発者のニーズに対応するために、PowerShell 7 のインストールにはいくつかのオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-120">For flexibility and to support the needs of IT, DevOps engineers, and developers, there are several options available to install PowerShell 7.</span></span> <span data-ttu-id="f5b54-121">ほとんどの場合、インストール オプションは次の方法に絞ることができます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-121">In most cases, the installation options can be reduced to the following methods:</span></span>

- <span data-ttu-id="f5b54-122">[MSI パッケージ](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package)を使用して PowerShell を展開する</span><span class="sxs-lookup"><span data-stu-id="f5b54-122">Deploy PowerShell using the [MSI package](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package)</span></span>
- <span data-ttu-id="f5b54-123">[ZIP パッケージ](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package)を使用して PowerShell を展開する</span><span class="sxs-lookup"><span data-stu-id="f5b54-123">Deploy PowerShell using the [ZIP package](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package)</span></span>

> [!NOTE]
> <span data-ttu-id="f5b54-124">MSI パッケージは、[System Center Configuration Manager (SCCM)](/configmgr/apps/) などの管理製品を使用して展開および更新できます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-124">The MSI package can be deployed and updated with management products such as [System Center Configuration Manager (SCCM)](/configmgr/apps/).</span></span> <span data-ttu-id="f5b54-125">[GitHub リリース ページ](https://github.com/PowerShell/PowerShell/releases)からパッケージをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-125">Download the packages from [GitHub Release page](https://github.com/PowerShell/PowerShell/releases).</span></span>

<span data-ttu-id="f5b54-126">MSI パッケージを展開するには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="f5b54-126">Deploying the MSI package requires Administrator permission.</span></span> <span data-ttu-id="f5b54-127">ZIP パッケージは、任意のユーザーが展開できます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-127">The ZIP package can be deployed by any user.</span></span> <span data-ttu-id="f5b54-128">ZIP パッケージは、完全インストールを実行する前にテスト用の PowerShell 7 をインストールするための最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="f5b54-128">The ZIP package is the easiest way to install PowerShell 7 for testing, before committing to a full installation.</span></span>

## <a name="using-powershell-7-side-by-side-with-windows-powershell-51"></a><span data-ttu-id="f5b54-129">PowerShell 7 を Windows PowerShell 5.1 とサイド バイ サイドで使用する</span><span class="sxs-lookup"><span data-stu-id="f5b54-129">Using PowerShell 7 side-by-side with Windows PowerShell 5.1</span></span>

<span data-ttu-id="f5b54-130">PowerShell 7 は、Windows PowerShell 5.1 と共存するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-130">PowerShell 7 is designed to coexist with Windows PowerShell 5.1.</span></span> <span data-ttu-id="f5b54-131">次の機能により、ユーザーの PowerShell への投資が確実に保護され、PowerShell 7 への移行が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-131">The following features ensure that your investment in PowerShell is protected and your migration to PowerShell 7 is simple.</span></span>

- <span data-ttu-id="f5b54-132">個別のインストール パスと実行可能ファイル名</span><span class="sxs-lookup"><span data-stu-id="f5b54-132">Separate installation path and executable name</span></span>
- <span data-ttu-id="f5b54-133">個別の PSModulePath</span><span class="sxs-lookup"><span data-stu-id="f5b54-133">Separate PSModulePath</span></span>
- <span data-ttu-id="f5b54-134">バージョンごとに個別のプロファイル</span><span class="sxs-lookup"><span data-stu-id="f5b54-134">Separate profiles for each version</span></span>
- <span data-ttu-id="f5b54-135">強化されたモジュールの互換性</span><span class="sxs-lookup"><span data-stu-id="f5b54-135">Improved module compatibility</span></span>
- <span data-ttu-id="f5b54-136">新しいリモート処理エンドポイント</span><span class="sxs-lookup"><span data-stu-id="f5b54-136">New remoting endpoints</span></span>
- <span data-ttu-id="f5b54-137">グループ ポリシーのサポート</span><span class="sxs-lookup"><span data-stu-id="f5b54-137">Group policy support</span></span>
- <span data-ttu-id="f5b54-138">個別のイベント ログ</span><span class="sxs-lookup"><span data-stu-id="f5b54-138">Separate Event logs</span></span>

### <a name="separate-installation-path-and-executable-name"></a><span data-ttu-id="f5b54-139">個別のインストール パスと実行可能ファイル名</span><span class="sxs-lookup"><span data-stu-id="f5b54-139">Separate installation path and executable name</span></span>

<span data-ttu-id="f5b54-140">PowerShell 7 は新しいディレクトリにインストールされ、Windows PowerShell 5.1 とのサイド バイ サイド実行が可能になります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-140">PowerShell 7 installs to a new directory, enabling side-by-side execution with Windows PowerShell 5.1.</span></span>

<span data-ttu-id="f5b54-141">バージョン別のインストール場所:</span><span class="sxs-lookup"><span data-stu-id="f5b54-141">Install locations by version:</span></span>

- <span data-ttu-id="f5b54-142">Windows PowerShell 5.1: `$env:WINDIR\System32\WindowsPowerShell\v1.0`</span><span class="sxs-lookup"><span data-stu-id="f5b54-142">Windows PowerShell 5.1: `$env:WINDIR\System32\WindowsPowerShell\v1.0`</span></span>
- <span data-ttu-id="f5b54-143">PowerShell Core 6.x: `$env:ProgramFiles\PowerShell\6`</span><span class="sxs-lookup"><span data-stu-id="f5b54-143">PowerShell Core 6.x: `$env:ProgramFiles\PowerShell\6`</span></span>
- <span data-ttu-id="f5b54-144">PowerShell 7: `$env:ProgramFiles\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="f5b54-144">PowerShell 7: `$env:ProgramFiles\PowerShell\7`</span></span>

<span data-ttu-id="f5b54-145">新しい場所が PATH に追加され、Windows PowerShell 5.1 と PowerShell 7 の両方を実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-145">The new location is added to your PATH allowing you to run both Windows PowerShell 5.1 and PowerShell 7.</span></span> <span data-ttu-id="f5b54-146">Powershell Core 6.x から PowerShell 7 に移行する場合は、PowerShell 6 が削除され、PATH が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-146">If you're migrating from PowerShell Core 6.x to PowerShell 7, PowerShell 6 is removed and the PATH replaced.</span></span>

<span data-ttu-id="f5b54-147">Windows PowerShell では、PowerShell の実行可能ファイルには `powershell.exe` という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-147">In Windows PowerShell, the PowerShell executable is named `powershell.exe`.</span></span> <span data-ttu-id="f5b54-148">バージョン 6 以降では、実行可能ファイルには `pwsh.exe` という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-148">In version 6 and above, the executable is named `pwsh.exe`.</span></span> <span data-ttu-id="f5b54-149">新しい名前を使用すると、両方のバージョンのサイド バイ サイド実行をサポートしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-149">The new name makes it easy to support side-by-side execution of both versions.</span></span>

### <a name="separate-psmodulepath"></a><span data-ttu-id="f5b54-150">個別の PSModulePath</span><span class="sxs-lookup"><span data-stu-id="f5b54-150">Separate PSModulePath</span></span>

<span data-ttu-id="f5b54-151">既定では、Windows PowerShell と PowerShell 7 では異なる場所にモジュールが格納されます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-151">By default, Windows PowerShell and PowerShell 7 store modules in different locations.</span></span> <span data-ttu-id="f5b54-152">PowerShell 7 では、これらの場所を組み合わせたものが `$Env:PSModulePath` 環境変数に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-152">PowerShell 7 combines those locations in the `$Env:PSModulePath` environment variable.</span></span> <span data-ttu-id="f5b54-153">モジュールを名前でインポートする場合、PowerShell では `$Env:PSModulePath` で指定された場所がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-153">When importing a module by name, PowerShell checks the location specified by `$Env:PSModulePath`.</span></span> <span data-ttu-id="f5b54-154">これにより、PowerShell 7 では Core モジュールと Desktop モジュールの両方を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-154">This allows PowerShell 7 to load both Core and Desktop modules.</span></span>

|            <span data-ttu-id="f5b54-155">インストール スコープ</span><span class="sxs-lookup"><span data-stu-id="f5b54-155">Install Scope</span></span>            |                <span data-ttu-id="f5b54-156">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="f5b54-156">Windows PowerShell 5.1</span></span>                 |             <span data-ttu-id="f5b54-157">PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="f5b54-157">PowerShell 7.0</span></span>             |
| ----------------------------------- | ----------------------------------------------------- | -------------------------------------- |
| <span data-ttu-id="f5b54-158">PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="f5b54-158">PowerShell modules</span></span>                  | `$env:WINDIR\system32\WindowsPowerShell\v1.0\Modules` | `$PSHOME\Modules`                      |
| <span data-ttu-id="f5b54-159">ユーザー インストール</span><span class="sxs-lookup"><span data-stu-id="f5b54-159">User installed</span></span><br><span data-ttu-id="f5b54-160">AllUsers スコープ</span><span class="sxs-lookup"><span data-stu-id="f5b54-160">AllUsers scope</span></span>    | `$env:ProgramFiles\WindowsPowerShell\Modules`         | `$env:ProgramFiles\PowerShell\Modules` |
| <span data-ttu-id="f5b54-161">ユーザー インストール</span><span class="sxs-lookup"><span data-stu-id="f5b54-161">User installed</span></span><br><span data-ttu-id="f5b54-162">CurrentUser スコープ</span><span class="sxs-lookup"><span data-stu-id="f5b54-162">CurrentUser scope</span></span> | `$HOME\Documents\WindowsPowerShell\Modules`           | `$HOME\Documents\PowerShell\Modules`   |

<span data-ttu-id="f5b54-163">次の例では、各バージョンの `$Env:PSModulePath` の既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-163">The following examples show the default values of `$Env:PSModulePath` for each version.</span></span>

- <span data-ttu-id="f5b54-164">Windows PowerShell 5.1 の場合:</span><span class="sxs-lookup"><span data-stu-id="f5b54-164">For Windows PowerShell 5.1:</span></span>

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\WindowsPowerShell\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

- <span data-ttu-id="f5b54-165">PowerShell 7 の場合:</span><span class="sxs-lookup"><span data-stu-id="f5b54-165">For PowerShell 7:</span></span>

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\PowerShell\Modules
  C:\Program Files\PowerShell\Modules
  C:\Program Files\PowerShell\7\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

<span data-ttu-id="f5b54-166">PowerShell 7 では、モジュールの自動読み込みを行うために、Windows PowerShell のパスと PowerShell 7 のパスが含まれていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-166">Notice that PowerShell 7 includes the Windows PowerShell paths and the PowerShell 7 paths to provide autoloading of modules.</span></span>

> [!NOTE]
> <span data-ttu-id="f5b54-167">PSModulePath 環境変数を変更した場合、またはカスタムのモジュールかアプリケーションをインストールした場合は、追加のパスが存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-167">Additional paths may exist if you have changed the PSModulePath environment variable or installed custom modules or applications.</span></span>

<span data-ttu-id="f5b54-168">詳細については、[環境変数の概要](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences)に関する記事の `PSModulePath` を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-168">For more information, see `PSModulePath` in [about_Environment_Variables](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences).</span></span>

<span data-ttu-id="f5b54-169">モジュールの詳細については、「[about_Modules](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-169">For more information about Modules, see [about_Modules](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules).</span></span>

### <a name="separate-profiles"></a><span data-ttu-id="f5b54-170">個別のプロファイル</span><span class="sxs-lookup"><span data-stu-id="f5b54-170">Separate profiles</span></span>

<span data-ttu-id="f5b54-171">PowerShell プロファイルは、PowerShell の起動時に実行されるスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="f5b54-171">A PowerShell profile is a script that executes when PowerShell starts.</span></span> <span data-ttu-id="f5b54-172">このスクリプトでは、コマンド、エイリアス、関数、変数、モジュール、PowerShell ドライブを追加して、環境をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-172">This script customizes your environment by adding commands, aliases, functions, variables, modules, and PowerShell drives.</span></span> <span data-ttu-id="f5b54-173">プロファイル スクリプトを使用すると、すべてのセッションでこれらのカスタマイズを利用できるようになり、手動で再作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-173">The profile script makes these customizations available in every session without having to manually recreate them.</span></span>

<span data-ttu-id="f5b54-174">PowerShell 7 では、プロファイルの場所へのパスが変更されています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-174">The path to the location of the profile has changed in PowerShell 7.</span></span>

- <span data-ttu-id="f5b54-175">Windows PowerShell 5.1 では、プロファイルの場所は `$HOME\Documents\WindowsPowerShell` です。</span><span class="sxs-lookup"><span data-stu-id="f5b54-175">In Windows PowerShell 5.1, the location of the profile is `$HOME\Documents\WindowsPowerShell`.</span></span>
- <span data-ttu-id="f5b54-176">PowerShell 7 では、プロファイルの場所は `$HOME\Documents\PowerShell` です。</span><span class="sxs-lookup"><span data-stu-id="f5b54-176">In PowerShell 7, the location of the profile is `$HOME\Documents\PowerShell`.</span></span>

<span data-ttu-id="f5b54-177">プロファイルのファイル名も変更されています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-177">The profile filenames have also changed:</span></span>

   ```powershell
   PS> $PROFILE | Select-Object *Host* | Format-List

   AllUsersAllHosts       : C:\Program Files\PowerShell\7\profile.ps1
   AllUsersCurrentHost    : C:\Program Files\PowerShell\7\Microsoft.PowerShell_profile.ps1
   CurrentUserAllHosts    : C:\Users\<user>\Documents\PowerShell\profile.ps1
   CurrentUserCurrentHost : C:\Users\<user>\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
   ```

<span data-ttu-id="f5b54-178">詳細については、「[about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-178">For more information [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

### <a name="powershell-7-compatibility-with-windows-powershell-51-modules"></a><span data-ttu-id="f5b54-179">PowerShell 7 の Windows PowerShell 5.1 モジュールとの互換性</span><span class="sxs-lookup"><span data-stu-id="f5b54-179">PowerShell 7 compatibility with Windows PowerShell 5.1 modules</span></span>

<span data-ttu-id="f5b54-180">Windows PowerShell 5.1 でお使いのほとんどのモジュールは、Azure PowerShell と Active Directory を含めて、既に PowerShell 7 で動作しています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-180">Most of the modules you use in Windows PowerShell 5.1 already work with PowerShell 7, including Azure PowerShell and Active Directory.</span></span> <span data-ttu-id="f5b54-181">私たちは、他のチームと協力して、Microsoft Graph、Office 365 などを始めとする、さらに多くのモジュールの PowerShell 7 ネイティブ サポートを追加する作業を続けています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-181">We're continuing to work with other teams to add native PowerShell 7 support for more modules including Microsoft Graph, Office 365, and others.</span></span> <span data-ttu-id="f5b54-182">サポートされているモジュールの最新の一覧については、「[PowerShell 7 モジュールの互換性](/powershell/scripting/whats-new/module-compatibility)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-182">For the current list of supported modules, see [PowerShell 7 module compatibility](/powershell/scripting/whats-new/module-compatibility).</span></span>

> [!NOTE]
> <span data-ttu-id="f5b54-183">Windows では、`Import-Module` に **UseWindowsPowerShell** スイッチも追加されており、互換性のないモジュールを使用するユーザーが簡単に PowerShell 7 に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-183">On Windows, we've also added a **UseWindowsPowerShell** switch to `Import-Module` to ease the transition to PowerShell 7 for those using incompatible modules.</span></span> <span data-ttu-id="f5b54-184">この機能の詳細については、「[about_Windows_PowerShell_Compatibility](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-184">For more information on this functionality, see [about_Windows_PowerShell_Compatibility](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility).</span></span>

### <a name="powershell-remoting"></a><span data-ttu-id="f5b54-185">PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="f5b54-185">PowerShell Remoting</span></span>

<span data-ttu-id="f5b54-186">PowerShell リモート処理を使用すると、1 台以上のリモート コンピューター上で任意の PowerShell コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-186">PowerShell remoting lets you run any PowerShell command on one or more remote computers.</span></span> <span data-ttu-id="f5b54-187">永続的な接続の確立、対話型のセッションの開始、およびリモート コンピューターでのスクリプトの実行が可能です。</span><span class="sxs-lookup"><span data-stu-id="f5b54-187">You can establish persistent connections, start interactive sessions, and run scripts on remote computers.</span></span>

#### <a name="ws-management-remoting"></a><span data-ttu-id="f5b54-188">WS-Management リモート処理</span><span class="sxs-lookup"><span data-stu-id="f5b54-188">WS-Management remoting</span></span>

<span data-ttu-id="f5b54-189">Windows PowerShell 5.1 以前では、接続ネゴシエーションとデータ転送のために WS-Management (WSMAN) プロトコルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-189">Windows PowerShell 5.1 and below use the WS-Management (WSMAN) protocol for connection negotiation and data transport.</span></span> <span data-ttu-id="f5b54-190">Windows リモート管理 (WinRM) では、WSMAN プロトコルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-190">Windows Remote Management (WinRM) uses the WSMAN protocol.</span></span> <span data-ttu-id="f5b54-191">WinRM が有効になっている場合、PowerShell 7 では、リモート接続のために `Microsoft.PowerShell` という名前の既存の Windows PowerShell 5.1 エンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-191">If WinRM has been enabled, PowerShell 7 uses the existing Windows PowerShell 5.1 endpoint named `Microsoft.PowerShell` for remoting connections.</span></span> <span data-ttu-id="f5b54-192">PowerShell 7 を更新して独自のエンドポイントを追加するには、`Enable-PSRemoting` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-192">To update PowerShell 7 to include its own endpoint, run the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="f5b54-193">特定のエンドポイントへの接続について詳しくは、[PowerShell Core の WS-Management リモート処理](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core)に関する記事をご覧ください</span><span class="sxs-lookup"><span data-stu-id="f5b54-193">For information about connecting to specific endpoints, see [WS-Management Remoting in PowerShell Core](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core)</span></span>

<span data-ttu-id="f5b54-194">Windows PowerShell のリモート処理を使用するには、リモート管理のためにリモート コンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-194">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span>
<span data-ttu-id="f5b54-195">手順を含む詳細については、「[about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-195">For more information, including instructions, see [About Remote Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span></span>

<span data-ttu-id="f5b54-196">リモート処理の使用について詳しくは、「[リモートについて](/powershell/module/microsoft.powershell.core/about/about_remote)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-196">For more information about working with remoting, see [About Remote](/powershell/module/microsoft.powershell.core/about/about_remote)</span></span>

#### <a name="ssh-based-remoting"></a><span data-ttu-id="f5b54-197">SSH ベースのリモート処理</span><span class="sxs-lookup"><span data-stu-id="f5b54-197">SSH-based remoting</span></span>

<span data-ttu-id="f5b54-198">SSH ベースのリモート処理は、**WinRM** のような Windows ネイティブ コンポーネントを使用できない他のオペレーティング システムをサポートするために、PowerShell Core 6.x に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f5b54-198">SSH-based remoting was added in PowerShell Core 6.x to support other operating systems that can't use Windows native components like **WinRM**.</span></span> <span data-ttu-id="f5b54-199">SSH リモート処理で、SSH サブシステムとしてターゲット コンピューター上に PowerShell ホスティング プロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-199">SSH remoting creates a PowerShell host process on the target computer as an SSH subsystem.</span></span> <span data-ttu-id="f5b54-200">Windows または Linux で SSH ベースのリモート処理を設定する方法の詳細と例については、次を参照してください:「[SSH 経由の PowerShell リモート処理](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)」。</span><span class="sxs-lookup"><span data-stu-id="f5b54-200">For details and examples on setting up SSH-based remoting on Windows or Linux, see: [PowerShell remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

> [!NOTE]
> <span data-ttu-id="f5b54-201">PowerShell ギャラリー (PSGallery) には、SSH ベースのリモート処理を自動的に構成するモジュールとコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-201">The PowerShell Gallery (PSGallery) contains a module and cmdlet that automatically configures SSH-based remoting.</span></span> <span data-ttu-id="f5b54-202">[PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) から `Microsoft.PowerShell.RemotingTools` モジュールをインストールし、`Enable-SSH` コマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-202">Install the `Microsoft.PowerShell.RemotingTools` module from the [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) and run the `Enable-SSH` cmdlet.</span></span>

<span data-ttu-id="f5b54-203">`New-PSSession`、`Enter-PSSession`、および `Invoke-Command` コマンドレットには、SSH 接続をサポートする新しいパラメーター セットがあります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-203">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets have new parameter sets to support SSH connections.</span></span>

```powershell
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="f5b54-204">リモート セッションを作成するには、**HostName** パラメーターでターゲット コンピューターを指定し、**UserName** でユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-204">To create a remote session, specify the target computer with the **HostName** parameter and provide the user name with **UserName**.</span></span> <span data-ttu-id="f5b54-205">コマンドレットを対話的に実行する場合は、パスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-205">When running the cmdlets interactively, you're prompted for a password.</span></span>

```powershell
Enter-PSSession -HostName <Computer> -UserName <Username>
```

<span data-ttu-id="f5b54-206">または、**HostName** パラメーターを使用する場合は、ユーザー名の情報に続けてアットマーク (`@`) を入力し、続けてコンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-206">Alternatively, when using the **HostName** parameter, provide the username information followed by the at sign (`@`), followed by the computer name.</span></span>

```powershell
Enter-PSSession -HostName <Username>@<Computer>
```

<span data-ttu-id="f5b54-207">**KeyFilePath** パラメーターを指定して、プライベート キー ファイルを使用する SSH キー認証を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-207">You may set up SSH key authentication using a private key file with the **KeyFilePath** parameter.</span></span>
<span data-ttu-id="f5b54-208">詳細については、「[OpenSSH キーの管理](/windows-server/administration/openssh/openssh_keymanagement)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-208">For more information, see [OpenSSH Key Management](/windows-server/administration/openssh/openssh_keymanagement).</span></span>

### <a name="group-policy-supported"></a><span data-ttu-id="f5b54-209">グループ ポリシーのサポート</span><span class="sxs-lookup"><span data-stu-id="f5b54-209">Group Policy supported</span></span>

<span data-ttu-id="f5b54-210">PowerShell には、エンタープライズ環境内の各サーバーに対して一貫したオプション値を定義するのに役立つ、グループ ポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-210">PowerShell includes Group Policy settings to help you define consistent option values for servers in an enterprise environment.</span></span> <span data-ttu-id="f5b54-211">これらの設定には、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-211">These settings include:</span></span>

- <span data-ttu-id="f5b54-212">コンソール セッションの構成:PowerShell を実行する構成エンドポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-212">Console session configuration: Sets a configuration endpoint in which PowerShell is run.</span></span>
- <span data-ttu-id="f5b54-213">モジュール ログを有効にする:モジュールの LogPipelineExecutionDetails プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-213">Turn on Module Logging: Sets the LogPipelineExecutionDetails property of modules.</span></span>
- <span data-ttu-id="f5b54-214">PowerShell スクリプト ブロックのログ記録を有効にする:すべての PowerShell スクリプトの詳細なログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f5b54-214">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="f5b54-215">スクリプトの実行を有効にする:PowerShell 実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-215">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="f5b54-216">PowerShell トランスクリプションを有効にする: PowerShell コマンドの入出力をテキスト ベースのトランスクリプトにキャプチャできるようにします。</span><span class="sxs-lookup"><span data-stu-id="f5b54-216">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="f5b54-217">Update-Help の既定のソース パスを設定する:更新可能なヘルプのソースを、インターネットではなく、ディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-217">Set the default source path for Update-Help: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="f5b54-218">詳細については、「[about_Group_Policy_Settings](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-218">For more information, see [about_Group_Policy_Settings](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings).</span></span>

<span data-ttu-id="f5b54-219">PowerShell 7 では、グループ ポリシーのテンプレートとインストール スクリプトが `$PSHOME` に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-219">PowerShell 7 includes Group Policy templates and an installation script in `$PSHOME`.</span></span>

<span data-ttu-id="f5b54-220">グループ ポリシー ツールでは、管理用テンプレート ファイル (`.admx`、`.adml`) を使用して、ユーザー インターフェイスにポリシー設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-220">Group Policy tools use administrative template files (`.admx`, `.adml`) to populate policy settings in the user interface.</span></span> <span data-ttu-id="f5b54-221">これにより、管理者はレジストリ ベースのポリシー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-221">This allows administrators to manage registry-based policy settings.</span></span> <span data-ttu-id="f5b54-222">`InstallPSCorePolicyDefinitions.ps1` スクリプトを使用すると、ローカル コンピューターに PowerShell Core 管理用テンプレートがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-222">The `InstallPSCorePolicyDefinitions.ps1` script installs PowerShell Core Administrative Templates on the local machine.</span></span>

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/27/2020 12:38 AM          15861 InstallPSCorePolicyDefinitions.ps1
-a---           2/27/2020 12:28 AM           9675 PowerShellCoreExecutionPolicy.adml
-a---           2/27/2020 12:28 AM           6201 PowerShellCoreExecutionPolicy.admx
```

### <a name="separate-event-logs"></a><span data-ttu-id="f5b54-223">個別のイベント ログ</span><span class="sxs-lookup"><span data-stu-id="f5b54-223">Separate Event Logs</span></span>

<span data-ttu-id="f5b54-224">Windows PowerShell と PowerShell 7 では、個別のイベント ログにイベントのログが記録されます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-224">Windows PowerShell and PowerShell 7 log events to separate event logs.</span></span> <span data-ttu-id="f5b54-225">PowerShell ログの一覧を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-225">Use the following command to get a list of the PowerShell logs.</span></span>

```powershell
Get-WinEvent -ListLog *PowerShell*
```

<span data-ttu-id="f5b54-226">詳細については、「[about_Logging_Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5b54-226">For more information, see [about_Logging_Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows).</span></span>

## <a name="improved-editing-experience-with-visual-studio-code"></a><span data-ttu-id="f5b54-227">Visual Studio Code を使用した編集エクスペリエンスの向上</span><span class="sxs-lookup"><span data-stu-id="f5b54-227">Improved editing experience with Visual Studio Code</span></span>

<span data-ttu-id="f5b54-228">[PowerShell 拡張機能](https://code.visualstudio.com/docs/languages/powershell)を使用した [Visual Studio Code (VSCode)](https://code.visualstudio.com/) は、PowerShell 7 でサポートされているスクリプト環境です。</span><span class="sxs-lookup"><span data-stu-id="f5b54-228">[Visual Studio Code (VSCode)](https://code.visualstudio.com/) with the [PowerShell Extension](https://code.visualstudio.com/docs/languages/powershell) is the supported scripting environment for PowerShell 7.</span></span> <span data-ttu-id="f5b54-229">Windows PowerShell Integrated Scripting Environment (ISE) では、Windows PowerShell のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-229">The Windows PowerShell Integrated Scripting Environment (ISE) only supports Windows PowerShell.</span></span>

<span data-ttu-id="f5b54-230">更新された PowerShell 拡張機能には、次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-230">The updated PowerShell extension includes:</span></span>

- <span data-ttu-id="f5b54-231">新しい ISE 互換モード</span><span class="sxs-lookup"><span data-stu-id="f5b54-231">New ISE compatibility mode</span></span>
- <span data-ttu-id="f5b54-232">統合コンソールでの PSReadLine (構文の強調表示、複数行の編集、バック検索を含む)</span><span class="sxs-lookup"><span data-stu-id="f5b54-232">PSReadLine in the Integrated Console, including syntax highlighting, multi-line editing, and back search</span></span>
- <span data-ttu-id="f5b54-233">安定性とパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="f5b54-233">Stability and performance improvements</span></span>
- <span data-ttu-id="f5b54-234">新しい CodeLens 統合</span><span class="sxs-lookup"><span data-stu-id="f5b54-234">New CodeLens integration</span></span>
- <span data-ttu-id="f5b54-235">パスのオートコンプリートの向上</span><span class="sxs-lookup"><span data-stu-id="f5b54-235">Improved path auto-completion</span></span>

<span data-ttu-id="f5b54-236">簡単に Visual Studio Code への移行を行うには、**コマンド パレット**で使用できる **ISE モードの有効化**機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b54-236">To make the transition to Visual Studio Code easier, use the **Enable ISE Mode** function available in the **Command Palette**.</span></span> <span data-ttu-id="f5b54-237">この機能を使うと、VSCode が ISE スタイルのレイアウトに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="f5b54-237">This function switches VSCode into an ISE-style layout.</span></span> <span data-ttu-id="f5b54-238">ISE スタイルのレイアウトでは、使い慣れたユーザー エクスペリエンスで、PowerShell のすべての新機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5b54-238">The ISE-style layout gives you all the new features and capabilities of PowerShell in a familiar user experience.</span></span>

<span data-ttu-id="f5b54-239">新しい ISE レイアウトに切り替えるには、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> キーを押して**コマンド パレット**を開き、「`PowerShell`」と入力して次を選択します: **[PowerShell:Enable ISE Mode]\(PowerShell: ISE モードの有効化\)**。</span><span class="sxs-lookup"><span data-stu-id="f5b54-239">To switch to the new ISE layout, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> to open the **Command Palette**, type `PowerShell` and select **PowerShell: Enable ISE Mode**.</span></span>

<span data-ttu-id="f5b54-240">レイアウトを元のレイアウトに設定するには、**コマンド パレット**を開き、次を選択します: **[PowerShell:Disable ISE Mode (restore to defaults)]\(PowerShell: ISE モードの無効化 (既定値に戻す)\)**。</span><span class="sxs-lookup"><span data-stu-id="f5b54-240">To set the layout to the original layout, open the **Command Palette**, select **PowerShell: Disable ISE Mode (restore to defaults)**.</span></span>

<span data-ttu-id="f5b54-241">VSCode のレイアウトを ISE にカスタマイズする方法の詳細については、「[Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="f5b54-241">For details about customizing the VSCode layout to ISE, see [How to Replicate the ISE Experience in Visual Studio Code](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode)</span></span>

> [!NOTE]
> <span data-ttu-id="f5b54-242">新しい機能で ISE を更新する予定はありません。</span><span class="sxs-lookup"><span data-stu-id="f5b54-242">There no plans to update the ISE with new features.</span></span> <span data-ttu-id="f5b54-243">最新バージョンの Windows 10 および Windows Server では、ISE はユーザーがアンインストール可能な機能になりました。</span><span class="sxs-lookup"><span data-stu-id="f5b54-243">The ISE is now a user-uninstallable feature in the latest versions of Windows 10 and Windows Server.</span></span> <span data-ttu-id="f5b54-244">ISE を完全に削除する予定はありません。</span><span class="sxs-lookup"><span data-stu-id="f5b54-244">There are no plans to permanently remove the ISE.</span></span> <span data-ttu-id="f5b54-245">PowerShell チームとそのパートナーは、Visual Studio Code 用の PowerShell 拡張機能におけるスクリプト作成エクスペリエンスの改善に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="f5b54-245">The PowerShell Team and its partners are focused on improving the scripting experience in the PowerShell extension for Visual Studio Code.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5b54-246">次の手順</span><span class="sxs-lookup"><span data-stu-id="f5b54-246">Next Steps</span></span>

<span data-ttu-id="f5b54-247">効率的に移行を行うための知識が身に付いたら、すぐに [PowerShell 7 をインストール](/powershell/scripting/install/installing-powershell-core-on-windows)しましょう。</span><span class="sxs-lookup"><span data-stu-id="f5b54-247">Armed with the knowledge to effectively migrate, [install PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows) now!</span></span>

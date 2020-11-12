---
description: PSModulePath 環境変数には、モジュールとリソースを検索するために検索されるフォルダーの場所の一覧が含まれています。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_PSModulePath?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSModulePath
ms.openlocfilehash: c3a64cf3602d1a2c3acd1c4478cd61943c0f020f
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524372"
---
# <a name="about-psmodulepath"></a><span data-ttu-id="f403d-104">PSModulePath について</span><span class="sxs-lookup"><span data-stu-id="f403d-104">About PSModulePath</span></span>

<span data-ttu-id="f403d-105">環境変数には、 `$env:PSModulePath` モジュールとリソースを検索するために検索されるフォルダーの場所の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f403d-105">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span> <span data-ttu-id="f403d-106">PowerShell は、各フォルダーでモジュール ( `.psd1` または) ファイルを再帰的に検索 `.psm1` します。</span><span class="sxs-lookup"><span data-stu-id="f403d-106">PowerShell recursively searches each folder for module (`.psd1` or `.psm1`) files.</span></span>

<span data-ttu-id="f403d-107">既定では、に割り当てられて `$env:PSModulePath` いる有効な場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f403d-107">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="f403d-108">システム全体の場所: これらのフォルダーには、PowerShell に付属しているモジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f403d-108">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="f403d-109">これらのモジュールは、フォルダーに格納されてい `$PSHOME\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-109">These modules are store in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="f403d-110">これは、Windows 管理モジュールがインストールされている場所でもあります。</span><span class="sxs-lookup"><span data-stu-id="f403d-110">This is also the location where the Windows management modules are installed.</span></span>

- <span data-ttu-id="f403d-111">ユーザーがインストールしたモジュール: これらはユーザーによってインストールされたモジュールです。</span><span class="sxs-lookup"><span data-stu-id="f403d-111">User-installed modules: These are modules installed by the user.</span></span>
  <span data-ttu-id="f403d-112">`Install-Module` には、現在のユーザーまたはすべてのユーザーに対してモジュールがインストールされているかどうかを指定できる **スコープ** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="f403d-112">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="f403d-113">詳細については、「 [Install-Module](xref:PowerShellGet.Install-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f403d-113">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  - <span data-ttu-id="f403d-114">Windows では、ユーザー固有の **CurrentUser** スコープの場所は `$HOME\Documents\PowerShell\Modules` フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="f403d-114">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="f403d-115">**AllUsers** スコープの場所は `$env:ProgramFiles\PowerShell\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="f403d-115">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
  - <span data-ttu-id="f403d-116">Windows 以外のシステムでは、ユーザー固有の **CurrentUser** スコープの場所は `$HOME/.local/share/powershell/Modules` フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="f403d-116">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="f403d-117">**AllUsers** スコープの場所は `/usr/local/share/powershell/Modules` です。</span><span class="sxs-lookup"><span data-stu-id="f403d-117">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

<span data-ttu-id="f403d-118">また、Program Files ディレクトリなど、他のディレクトリにモジュールをインストールするセットアッププログラムでは、の値にその場所を追加でき `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-118">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

> [!NOTE]
> <span data-ttu-id="f403d-119">Windows では、ユーザー固有の場所は、 `PowerShell\Modules` ユーザープロファイルの **Documents** フォルダーにあるフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="f403d-119">On Windows, the user-specific location is the `PowerShell\Modules` folder located in the **Documents** folder in your user profile.</span></span> <span data-ttu-id="f403d-120">その場所の特定のパスは、Windows のバージョンと、フォルダーリダイレクトを使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f403d-120">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="f403d-121">Microsoft OneDrive では、 **ドキュメント** フォルダーの場所を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="f403d-121">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span> <span data-ttu-id="f403d-122">次のコマンドを使用して、 **ドキュメント** フォルダーの場所を確認でき `[Environment]::GetFolderPath('MyDocuments')` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-122">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

## <a name="modifying-psmodulepath"></a><span data-ttu-id="f403d-123">PSModulePath の変更</span><span class="sxs-lookup"><span data-stu-id="f403d-123">Modifying PSModulePath</span></span>

<span data-ttu-id="f403d-124">現在のセッションの既定のモジュールディレクトリを変更するには、次のコマンド形式を使用して環境変数の値を変更し `PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-124">To change the default module directories for the current session, use the following command format to change the value of the `PSModulePath` environment variable.</span></span>

<span data-ttu-id="f403d-125">たとえば、 `C:\Program Files\Fabrikam\Modules` PSModulePath 環境変数の値にディレクトリを追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f403d-125">For example, to add the `C:\Program Files\Fabrikam\Modules` directory to the value of the PSModulePath environment variable, type:</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath+";C:\Program Files\Fabrikam\Modules"
```

<span data-ttu-id="f403d-126">コマンドのセミコロン () は、 `;` 新しいパスをリスト内でその前にあるパスと分離します。</span><span class="sxs-lookup"><span data-stu-id="f403d-126">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span> <span data-ttu-id="f403d-127">Windows 以外のプラットフォームでは、コロン () によって `:` 環境変数内のパスの場所が分離されます。</span><span class="sxs-lookup"><span data-stu-id="f403d-127">On non-Windows platforms, the colon (`:`) separates the path locations in the environment variable.</span></span>

<span data-ttu-id="f403d-128">すべてのセッションでの値を変更するに `PSModulePath` は、前のコマンドを PowerShell プロファイルに追加するか、 **環境** クラスの **SetEnvironmentVariable** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f403d-128">To change the value of `PSModulePath` in every session, add the previous command to your PowerShell profile or use the **SetEnvironmentVariable** method of the **Environment** class.</span></span>

<span data-ttu-id="f403d-129">次のコマンドは、 **GetEnvironmentVariable** メソッドを使用してコンピューターの設定を取得し、SetEnvironmentVariable メソッドを使用してその `PSModulePath` パスを値に追加し **SetEnvironmentVariable** `C:\Program Files\Fabrikam\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-129">The following command uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'Machine')
```

<span data-ttu-id="f403d-130">ユーザー設定のパスを追加するには、ターゲットの値を **user** に変更します。</span><span class="sxs-lookup"><span data-stu-id="f403d-130">To add a path to the user setting, change the target value to **User**.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'User')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'User')
```

<span data-ttu-id="f403d-131">System.object クラスのメソッドの詳細については、「 [環境メソッド](/dotnet/api/system.environment)」を参照して **ください。**</span><span class="sxs-lookup"><span data-stu-id="f403d-131">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="powershell-psmodulepath-construction"></a><span data-ttu-id="f403d-132">PowerShell PSModulePath の構築</span><span class="sxs-lookup"><span data-stu-id="f403d-132">PowerShell PSModulePath construction</span></span>

<span data-ttu-id="f403d-133">の値は、 `$env:PSModulePath` PowerShell が開始されるたびに構築されます。</span><span class="sxs-lookup"><span data-stu-id="f403d-133">The value of `$env:PSModulePath` is constructed each time PowerShell starts.</span></span>
<span data-ttu-id="f403d-134">値は PowerShell のバージョンと起動方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f403d-134">The value varies by version of PowerShell and how it is launched.</span></span>

### <a name="windows-powershell-startup"></a><span data-ttu-id="f403d-135">Windows PowerShell の起動</span><span class="sxs-lookup"><span data-stu-id="f403d-135">Windows PowerShell startup</span></span>

<span data-ttu-id="f403d-136">Windows PowerShell は、起動時にを構築するために次のロジックを使用し `PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-136">Windows PowerShell uses the following logic to construct the `PSModulePath` at startup:</span></span>

- <span data-ttu-id="f403d-137">が存在しない場合は、 `PSModulePath` **CurrentUser** 、 **AllUsers** 、および modules の各パスを結合します。 `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="f403d-137">If `PSModulePath` doesn't exist, combine **CurrentUser** , **AllUsers** , and the `$PSHOME` modules paths</span></span>
- <span data-ttu-id="f403d-138">`PSModulePath`が存在する場合:</span><span class="sxs-lookup"><span data-stu-id="f403d-138">If `PSModulePath` does exist:</span></span>
  - <span data-ttu-id="f403d-139">に `PSModulePath` モジュールパスが含まれている場合 `$PSHOME` :</span><span class="sxs-lookup"><span data-stu-id="f403d-139">If `PSModulePath` contains `$PSHOME` modules path:</span></span>
    - <span data-ttu-id="f403d-140">モジュールパスの前に **AllUsers** モジュールパスが挿入されます `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="f403d-140">**AllUsers** modules path is inserted before `$PSHOME` modules path</span></span>
  - <span data-ttu-id="f403d-141">さも</span><span class="sxs-lookup"><span data-stu-id="f403d-141">else:</span></span>
    - <span data-ttu-id="f403d-142">`PSModulePath`ユーザーが意図的に場所を削除した後に定義されたを使用する `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="f403d-142">Just use `PSModulePath` as defined since the user deliberately removed the `$PSHOME` location</span></span>

<span data-ttu-id="f403d-143">**CurrentUser** モジュールパスは、ユーザースコープが存在しない場合にのみプレフィックスが付けられ `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-143">The **CurrentUser** module path is prefixed only if User scope `$env:PSModulePath` doesn't exist.</span></span> <span data-ttu-id="f403d-144">それ以外の場合 `$env:PSModulePath` は、定義に従ってユーザースコープが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f403d-144">Otherwise, the User scope `$env:PSModulePath` is used as defined.</span></span>

### <a name="powershell-core-6-startup"></a><span data-ttu-id="f403d-145">PowerShell Core 6 スタートアップ</span><span class="sxs-lookup"><span data-stu-id="f403d-145">PowerShell Core 6 startup</span></span>

<span data-ttu-id="f403d-146">Powershell Core 6 は `$env:PSModulePath` 、powershell から開始されたことを検出すると、の内容を使用しません。</span><span class="sxs-lookup"><span data-stu-id="f403d-146">PowerShell Core 6 doesn't use contents of `$env:PSModulePath` if it detects it was started from PowerShell.</span></span> <span data-ttu-id="f403d-147">次のように上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f403d-147">It overwrites it with:</span></span>

- <span data-ttu-id="f403d-148">**CurrentUser** モジュールパス + **AllUsers** モジュールパス + `$PSHOME` モジュールパス + Windows PowerShell `$PSHOME` モジュールパス。</span><span class="sxs-lookup"><span data-stu-id="f403d-148">**CurrentUser** modules path + **AllUsers** modules path + `$PSHOME` modules path + Windows PowerShell `$PSHOME` modules path.</span></span>

### <a name="powershell-7-startup"></a><span data-ttu-id="f403d-149">PowerShell 7 スタートアップ</span><span class="sxs-lookup"><span data-stu-id="f403d-149">PowerShell 7 startup</span></span>

<span data-ttu-id="f403d-150">Windows では、ほとんどの環境変数で、ユーザースコープ変数が存在する場合、同じ名前のマシンスコープ変数が存在する場合でも、新しいプロセスでその値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f403d-150">In Windows, for most environment variables, if the User-scoped variable exists, a new process uses that value only even if a Machine-scoped variable of the same name exists.</span></span>

<span data-ttu-id="f403d-151">PowerShell 7 で `PSModulePath` は、は、 `Path` 環境変数が Windows でどのように扱われるかと同様に扱われます。</span><span class="sxs-lookup"><span data-stu-id="f403d-151">In PowerShell 7, `PSModulePath` is treated similar to how the `Path` environment variable is treated on Windows.</span></span> <span data-ttu-id="f403d-152">Windows で `Path` は、は他の環境変数とは異なる方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="f403d-152">On Windows, `Path` is treated differently from other environment variables.</span></span> <span data-ttu-id="f403d-153">プロセスが開始されると、Windows はユーザースコープ `Path` とコンピュータースコープを組み合わせ `Path` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-153">When a process is started, Windows combines the User-scoped `Path` with the Machine-scoped `Path`.</span></span>

- <span data-ttu-id="f403d-154">ユーザースコープを取得します。 `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="f403d-154">Retrieve the User-scoped `PSModulePath`</span></span>
- <span data-ttu-id="f403d-155">プロセス継承環境変数との比較 `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="f403d-155">Compare to process inherited `PSModulePath` environment variable</span></span>
  - <span data-ttu-id="f403d-156">同じ場合:</span><span class="sxs-lookup"><span data-stu-id="f403d-156">If the same:</span></span>
    - <span data-ttu-id="f403d-157">**AllUsers** `PSModulePath` 環境変数のセマンティクスに従って、最後に AllUsers を追加します。 `Path`</span><span class="sxs-lookup"><span data-stu-id="f403d-157">Append the **AllUsers** `PSModulePath` to the end following the semantics of the `Path` environment variable</span></span>
    - <span data-ttu-id="f403d-158">Windows パスは、 `System32` 定義されたコンピューターから取得さ `PSModulePath` れるため、明示的に追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f403d-158">The Windows `System32` path comes from the machine defined `PSModulePath` so does not need to be added explicitly</span></span>
  - <span data-ttu-id="f403d-159">異なる場合は、ユーザーが明示的に変更したものとして扱い、 **AllUsers** を追加しません。 `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="f403d-159">If different, treat as though user explicitly modified it and don't append **AllUsers** `PSModulePath`</span></span>
- <span data-ttu-id="f403d-160">PS7 User、System、および path を `$PSHOME` その順序でプレフィックスとして使用する</span><span class="sxs-lookup"><span data-stu-id="f403d-160">Prefix with PS7 User, System, and `$PSHOME` paths in that order</span></span>
  - <span data-ttu-id="f403d-161">に `powershell.config.json` ユーザースコープが含まれている場合は、 `PSModulePath` ユーザーの既定値の代わりにこれを使用します。</span><span class="sxs-lookup"><span data-stu-id="f403d-161">If `powershell.config.json` contains a user scoped `PSModulePath`, use that instead of the default for the user</span></span>
  - <span data-ttu-id="f403d-162">に `powershell.config.json` スコープのあるシステムが含まれている場合は、 `PSModulePath` システムの既定のではなく、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="f403d-162">If `powershell.config.json` contains a system scoped `PSModulePath`, use that instead of the default for the system</span></span>

<span data-ttu-id="f403d-163">Unix システムでは、ユーザー環境変数とシステム環境変数が分離されていません。</span><span class="sxs-lookup"><span data-stu-id="f403d-163">Unix systems don't have a separation of User and System environment variables.</span></span>
<span data-ttu-id="f403d-164">`PSModulePath` が継承され、まだ定義されていない場合は、PS7 固有のパスにプレフィックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="f403d-164">`PSModulePath` is inherited and the PS7-specific paths are prefixed if not already defined.</span></span>

### <a name="starting-windows-powershell-from-powershell-7"></a><span data-ttu-id="f403d-165">PowerShell 7 から Windows PowerShell を開始する</span><span class="sxs-lookup"><span data-stu-id="f403d-165">Starting Windows PowerShell from PowerShell 7</span></span>

<span data-ttu-id="f403d-166">この説明では、 _Windows PowerShell_ はとの両方を意味し `powershell.exe` `powershell_ise.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-166">For this discussion, _Windows PowerShell_ means both `powershell.exe` and `powershell_ise.exe`.</span></span>

<span data-ttu-id="f403d-167">の値 `$env:PSModulePath` は、 `WinPSModulePath` 次の変更によってにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="f403d-167">The value of `$env:PSModulePath` is copied to `WinPSModulePath` with the following modifications:</span></span>

- <span data-ttu-id="f403d-168">ユーザーモジュールパスの PS7 を削除します。</span><span class="sxs-lookup"><span data-stu-id="f403d-168">Remove PS7 the User module path</span></span>
- <span data-ttu-id="f403d-169">システムモジュールパスの PS7 を削除します。</span><span class="sxs-lookup"><span data-stu-id="f403d-169">Remove PS7 the System module path</span></span>
- <span data-ttu-id="f403d-170">モジュールパスの PS7 を削除します。 `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="f403d-170">Remove PS7 the `$PSHOME` module path</span></span>

<span data-ttu-id="f403d-171">PS7 モジュールが Windows PowerShell に読み込まれないように、PS7 パスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="f403d-171">The PS7 paths are removed so that PS7 modules don't get loaded in Windows PowerShell.</span></span> <span data-ttu-id="f403d-172">この `WinPSModulePath` 値は、Windows PowerShell を起動するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f403d-172">The `WinPSModulePath` value is used when starting Windows PowerShell.</span></span>

### <a name="starting-powershell-7-from-windows-powershell"></a><span data-ttu-id="f403d-173">Windows PowerShell から PowerShell 7 を開始する</span><span class="sxs-lookup"><span data-stu-id="f403d-173">Starting PowerShell 7 from Windows PowerShell</span></span>

<span data-ttu-id="f403d-174">PowerShell 7 のスタートアップは、Windows PowerShell によって追加された継承パスを追加することでそのままの状態で続行されます。</span><span class="sxs-lookup"><span data-stu-id="f403d-174">The PowerShell 7 startup continues as-is with the addition of inheriting paths that Windows PowerShell added.</span></span> <span data-ttu-id="f403d-175">PS7 固有のパスにはプレフィックスが付いているため、機能上の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="f403d-175">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

### <a name="starting-powershell-6-from-powershell-7"></a><span data-ttu-id="f403d-176">Powershell 7 から PowerShell 6 を開始する</span><span class="sxs-lookup"><span data-stu-id="f403d-176">Starting PowerShell 6 from PowerShell 7</span></span>

<span data-ttu-id="f403d-177">PowerShell Core 6 は上書きさ `$env:PSModulePath` れます。</span><span class="sxs-lookup"><span data-stu-id="f403d-177">PowerShell Core 6 overwrites `$env:PSModulePath`.</span></span> <span data-ttu-id="f403d-178">変更は行われません。</span><span class="sxs-lookup"><span data-stu-id="f403d-178">No changes are made.</span></span>

### <a name="starting-powershell-7-from-powershell-6"></a><span data-ttu-id="f403d-179">Powershell 6 から powershell 7 を開始する</span><span class="sxs-lookup"><span data-stu-id="f403d-179">Starting PowerShell 7 from PowerShell 6</span></span>

<span data-ttu-id="f403d-180">Powershell 7 のスタートアップは、PowerShell Core 6 によって追加された継承パスを追加することでそのままの状態で続行されます。</span><span class="sxs-lookup"><span data-stu-id="f403d-180">The PowerShell 7 startup continues as-is with the addition of inheriting paths that PowerShell Core 6 added.</span></span> <span data-ttu-id="f403d-181">PS7 固有のパスにはプレフィックスが付いているため、機能上の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="f403d-181">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

## <a name="module-search-behavior"></a><span data-ttu-id="f403d-182">モジュールの検索動作</span><span class="sxs-lookup"><span data-stu-id="f403d-182">Module search behavior</span></span>

<span data-ttu-id="f403d-183">PowerShell は、 **PSModulePath** のモジュール ( `.psd1` または) ファイルの各フォルダーを再帰的に検索し `.psm1` ます。</span><span class="sxs-lookup"><span data-stu-id="f403d-183">PowerShell recursively searches each folder in the **PSModulePath** for module (`.psd1` or `.psm1`) files.</span></span> <span data-ttu-id="f403d-184">この検索パターンを使用すると、同じモジュールの複数のバージョンを異なるフォルダーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f403d-184">This search pattern allows multiple versions of the same module to be installed in different folders.</span></span> <span data-ttu-id="f403d-185">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f403d-185">For example:</span></span>

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules\PowerShellGet

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----           8/14/2020  5:56 PM                1.0.0.1
d----           9/13/2019  3:53 PM                2.1.2
```

<span data-ttu-id="f403d-186">既定では、複数のバージョンが検出されると、PowerShell はモジュールの最大バージョン番号を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f403d-186">By default, PowerShell loads the highest version number of a module when multiple versions are found.</span></span> <span data-ttu-id="f403d-187">特定のバージョンを読み込むには、FullyQualifiedName パラメーターを指定してを使用し `Import-Module` ます。 **FullyQualifiedName**</span><span class="sxs-lookup"><span data-stu-id="f403d-187">To load a specific version, use `Import-Module` with the **FullyQualifiedName** parameter.</span></span> <span data-ttu-id="f403d-188">詳細については、「[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f403d-188">For more information, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="see-also"></a><span data-ttu-id="f403d-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="f403d-189">See also</span></span>

- [<span data-ttu-id="f403d-190">about_Modules</span><span class="sxs-lookup"><span data-stu-id="f403d-190">about_Modules</span></span>](about_Modules.md)
- [<span data-ttu-id="f403d-191">環境メソッド</span><span class="sxs-lookup"><span data-stu-id="f403d-191">Environment Methods</span></span>](/dotnet/api/system.environment)

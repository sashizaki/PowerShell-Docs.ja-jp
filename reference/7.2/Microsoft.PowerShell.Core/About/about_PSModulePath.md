---
description: PSModulePath 環境変数には、モジュールとリソースを検索するために検索されるフォルダーの場所の一覧が含まれています。
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_PSModulePath?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSModulePath
ms.openlocfilehash: ce77005d816f49c0a6353bd7b3e0580293b05d23
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604941"
---
# <a name="about-psmodulepath"></a><span data-ttu-id="60638-103">PSModulePath について</span><span class="sxs-lookup"><span data-stu-id="60638-103">About PSModulePath</span></span>

<span data-ttu-id="60638-104">環境変数には、 `$env:PSModulePath` モジュールとリソースを検索するために検索されるフォルダーの場所の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="60638-104">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span> <span data-ttu-id="60638-105">PowerShell は、各フォルダーでモジュール ( `.psd1` または) ファイルを再帰的に検索 `.psm1` します。</span><span class="sxs-lookup"><span data-stu-id="60638-105">PowerShell recursively searches each folder for module (`.psd1` or `.psm1`) files.</span></span>

<span data-ttu-id="60638-106">既定では、に割り当てられて `$env:PSModulePath` いる有効な場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="60638-106">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="60638-107">システム全体の場所: これらのフォルダーには、PowerShell に付属しているモジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="60638-107">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="60638-108">これらのモジュールは、フォルダーに格納されてい `$PSHOME\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-108">These modules are store in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="60638-109">これは、Windows 管理モジュールがインストールされている場所でもあります。</span><span class="sxs-lookup"><span data-stu-id="60638-109">This is also the location where the Windows management modules are installed.</span></span>

- <span data-ttu-id="60638-110">ユーザーがインストールしたモジュール: これらはユーザーによってインストールされたモジュールです。</span><span class="sxs-lookup"><span data-stu-id="60638-110">User-installed modules: These are modules installed by the user.</span></span>
  <span data-ttu-id="60638-111">`Install-Module` には、現在のユーザーまたはすべてのユーザーに対してモジュールがインストールされているかどうかを指定できる **スコープ** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="60638-111">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="60638-112">詳細については、「 [Install-Module](xref:PowerShellGet.Install-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60638-112">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  - <span data-ttu-id="60638-113">Windows では、ユーザー固有の **CurrentUser** スコープの場所は `$HOME\Documents\PowerShell\Modules` フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="60638-113">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="60638-114">**AllUsers** スコープの場所は `$env:ProgramFiles\PowerShell\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="60638-114">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
  - <span data-ttu-id="60638-115">Windows 以外のシステムでは、ユーザー固有の **CurrentUser** スコープの場所は `$HOME/.local/share/powershell/Modules` フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="60638-115">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="60638-116">**AllUsers** スコープの場所は `/usr/local/share/powershell/Modules` です。</span><span class="sxs-lookup"><span data-stu-id="60638-116">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

<span data-ttu-id="60638-117">また、Program Files ディレクトリなど、他のディレクトリにモジュールをインストールするセットアッププログラムでは、の値にその場所を追加でき `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-117">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

> [!NOTE]
> <span data-ttu-id="60638-118">Windows では、ユーザー固有の場所は、 `PowerShell\Modules` ユーザープロファイルの **Documents** フォルダーにあるフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="60638-118">On Windows, the user-specific location is the `PowerShell\Modules` folder located in the **Documents** folder in your user profile.</span></span> <span data-ttu-id="60638-119">その場所の特定のパスは、Windows のバージョンと、フォルダーリダイレクトを使用しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="60638-119">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="60638-120">Microsoft OneDrive では、 **ドキュメント** フォルダーの場所を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="60638-120">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span> <span data-ttu-id="60638-121">次のコマンドを使用して、 **ドキュメント** フォルダーの場所を確認でき `[Environment]::GetFolderPath('MyDocuments')` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-121">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

## <a name="modifying-psmodulepath"></a><span data-ttu-id="60638-122">PSModulePath の変更</span><span class="sxs-lookup"><span data-stu-id="60638-122">Modifying PSModulePath</span></span>

<span data-ttu-id="60638-123">現在のセッションの既定のモジュールディレクトリを変更するには、次のコマンド形式を使用して環境変数の値を変更し `PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-123">To change the default module directories for the current session, use the following command format to change the value of the `PSModulePath` environment variable.</span></span>

<span data-ttu-id="60638-124">たとえば、 `C:\Program Files\Fabrikam\Modules` PSModulePath 環境変数の値にディレクトリを追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="60638-124">For example, to add the `C:\Program Files\Fabrikam\Modules` directory to the value of the PSModulePath environment variable, type:</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath+";C:\Program Files\Fabrikam\Modules"
```

<span data-ttu-id="60638-125">コマンドのセミコロン () は、 `;` 新しいパスをリスト内でその前にあるパスと分離します。</span><span class="sxs-lookup"><span data-stu-id="60638-125">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span> <span data-ttu-id="60638-126">Windows 以外のプラットフォームでは、コロン () によって `:` 環境変数内のパスの場所が分離されます。</span><span class="sxs-lookup"><span data-stu-id="60638-126">On non-Windows platforms, the colon (`:`) separates the path locations in the environment variable.</span></span>

<span data-ttu-id="60638-127">すべてのセッションでの値を変更するに `PSModulePath` は、前のコマンドを PowerShell プロファイルに追加するか、**環境** クラスの **SetEnvironmentVariable** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60638-127">To change the value of `PSModulePath` in every session, add the previous command to your PowerShell profile or use the **SetEnvironmentVariable** method of the **Environment** class.</span></span>

<span data-ttu-id="60638-128">次のコマンドは、 **GetEnvironmentVariable** メソッドを使用してコンピューターの設定を取得し、SetEnvironmentVariable メソッドを使用してその `PSModulePath` パスを値に追加し `C:\Program Files\Fabrikam\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-128">The following command uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'Machine')
```

<span data-ttu-id="60638-129">ユーザー設定のパスを追加するには、ターゲットの値を **user** に変更します。</span><span class="sxs-lookup"><span data-stu-id="60638-129">To add a path to the user setting, change the target value to **User**.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'User')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'User')
```

<span data-ttu-id="60638-130">System.object クラスのメソッドの詳細については、「[環境メソッド](/dotnet/api/system.environment)」を参照して **ください。**</span><span class="sxs-lookup"><span data-stu-id="60638-130">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="powershell-psmodulepath-construction"></a><span data-ttu-id="60638-131">PowerShell PSModulePath の構築</span><span class="sxs-lookup"><span data-stu-id="60638-131">PowerShell PSModulePath construction</span></span>

<span data-ttu-id="60638-132">の値は、 `$env:PSModulePath` PowerShell が開始されるたびに構築されます。</span><span class="sxs-lookup"><span data-stu-id="60638-132">The value of `$env:PSModulePath` is constructed each time PowerShell starts.</span></span>
<span data-ttu-id="60638-133">値は PowerShell のバージョンと起動方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="60638-133">The value varies by version of PowerShell and how it is launched.</span></span>

### <a name="windows-powershell-startup"></a><span data-ttu-id="60638-134">Windows PowerShell の起動</span><span class="sxs-lookup"><span data-stu-id="60638-134">Windows PowerShell startup</span></span>

<span data-ttu-id="60638-135">Windows PowerShell は、起動時にを構築するために次のロジックを使用し `PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-135">Windows PowerShell uses the following logic to construct the `PSModulePath` at startup:</span></span>

- <span data-ttu-id="60638-136">が存在しない場合は、 `PSModulePath` **CurrentUser**、 **AllUsers**、および modules の各パスを結合します。 `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="60638-136">If `PSModulePath` doesn't exist, combine **CurrentUser**, **AllUsers**, and the `$PSHOME` modules paths</span></span>
- <span data-ttu-id="60638-137">`PSModulePath`が存在する場合:</span><span class="sxs-lookup"><span data-stu-id="60638-137">If `PSModulePath` does exist:</span></span>
  - <span data-ttu-id="60638-138">に `PSModulePath` モジュールパスが含まれている場合 `$PSHOME` :</span><span class="sxs-lookup"><span data-stu-id="60638-138">If `PSModulePath` contains `$PSHOME` modules path:</span></span>
    - <span data-ttu-id="60638-139">モジュールパスの前に **AllUsers** モジュールパスが挿入されます `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="60638-139">**AllUsers** modules path is inserted before `$PSHOME` modules path</span></span>
  - <span data-ttu-id="60638-140">さも</span><span class="sxs-lookup"><span data-stu-id="60638-140">else:</span></span>
    - <span data-ttu-id="60638-141">`PSModulePath`ユーザーが意図的に場所を削除した後に定義されたを使用する `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="60638-141">Just use `PSModulePath` as defined since the user deliberately removed the `$PSHOME` location</span></span>

<span data-ttu-id="60638-142">**CurrentUser** モジュールパスは、ユーザースコープが存在しない場合にのみプレフィックスが付けられ `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-142">The **CurrentUser** module path is prefixed only if User scope `$env:PSModulePath` doesn't exist.</span></span> <span data-ttu-id="60638-143">それ以外の場合 `$env:PSModulePath` は、定義に従ってユーザースコープが使用されます。</span><span class="sxs-lookup"><span data-stu-id="60638-143">Otherwise, the User scope `$env:PSModulePath` is used as defined.</span></span>

### <a name="powershell-core-6-startup"></a><span data-ttu-id="60638-144">PowerShell Core 6 スタートアップ</span><span class="sxs-lookup"><span data-stu-id="60638-144">PowerShell Core 6 startup</span></span>

<span data-ttu-id="60638-145">Powershell Core 6 は `$env:PSModulePath` 、powershell から開始されたことを検出すると、の内容を使用しません。</span><span class="sxs-lookup"><span data-stu-id="60638-145">PowerShell Core 6 doesn't use contents of `$env:PSModulePath` if it detects it was started from PowerShell.</span></span> <span data-ttu-id="60638-146">次のように上書きされます。</span><span class="sxs-lookup"><span data-stu-id="60638-146">It overwrites it with:</span></span>

- <span data-ttu-id="60638-147">**CurrentUser** モジュールパス + **AllUsers** モジュールパス + `$PSHOME` モジュールパス + Windows PowerShell `$PSHOME` モジュールパス。</span><span class="sxs-lookup"><span data-stu-id="60638-147">**CurrentUser** modules path + **AllUsers** modules path + `$PSHOME` modules path + Windows PowerShell `$PSHOME` modules path.</span></span>

### <a name="powershell-7-startup"></a><span data-ttu-id="60638-148">PowerShell 7 スタートアップ</span><span class="sxs-lookup"><span data-stu-id="60638-148">PowerShell 7 startup</span></span>

<span data-ttu-id="60638-149">Windows では、ほとんどの環境変数で、ユーザースコープ変数が存在する場合、同じ名前のマシンスコープ変数が存在する場合でも、新しいプロセスでその値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="60638-149">In Windows, for most environment variables, if the User-scoped variable exists, a new process uses that value only even if a Machine-scoped variable of the same name exists.</span></span>

<span data-ttu-id="60638-150">PowerShell 7 で `PSModulePath` は、は、 `Path` 環境変数が Windows でどのように扱われるかと同様に扱われます。</span><span class="sxs-lookup"><span data-stu-id="60638-150">In PowerShell 7, `PSModulePath` is treated similar to how the `Path` environment variable is treated on Windows.</span></span> <span data-ttu-id="60638-151">Windows で `Path` は、は他の環境変数とは異なる方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="60638-151">On Windows, `Path` is treated differently from other environment variables.</span></span> <span data-ttu-id="60638-152">プロセスが開始されると、Windows はユーザースコープ `Path` とコンピュータースコープを組み合わせ `Path` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-152">When a process is started, Windows combines the User-scoped `Path` with the Machine-scoped `Path`.</span></span>

- <span data-ttu-id="60638-153">ユーザースコープを取得します。 `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="60638-153">Retrieve the User-scoped `PSModulePath`</span></span>
- <span data-ttu-id="60638-154">プロセス継承環境変数との比較 `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="60638-154">Compare to process inherited `PSModulePath` environment variable</span></span>
  - <span data-ttu-id="60638-155">同じ場合:</span><span class="sxs-lookup"><span data-stu-id="60638-155">If the same:</span></span>
    - <span data-ttu-id="60638-156"> `PSModulePath` 環境変数のセマンティクスに従って、最後に AllUsers を追加します。 `Path`</span><span class="sxs-lookup"><span data-stu-id="60638-156">Append the **AllUsers** `PSModulePath` to the end following the semantics of the `Path` environment variable</span></span>
    - <span data-ttu-id="60638-157">Windows パスは、 `System32` 定義されたコンピューターから取得さ `PSModulePath` れるため、明示的に追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="60638-157">The Windows `System32` path comes from the machine defined `PSModulePath` so does not need to be added explicitly</span></span>
  - <span data-ttu-id="60638-158">異なる場合は、ユーザーが明示的に変更したものとして扱い、 **AllUsers** を追加しません。 `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="60638-158">If different, treat as though user explicitly modified it and don't append **AllUsers** `PSModulePath`</span></span>
- <span data-ttu-id="60638-159">PS7 User、System、および path を `$PSHOME` その順序でプレフィックスとして使用する</span><span class="sxs-lookup"><span data-stu-id="60638-159">Prefix with PS7 User, System, and `$PSHOME` paths in that order</span></span>
  - <span data-ttu-id="60638-160">に `powershell.config.json` ユーザースコープが含まれている場合は、 `PSModulePath` ユーザーの既定値の代わりにこれを使用します。</span><span class="sxs-lookup"><span data-stu-id="60638-160">If `powershell.config.json` contains a user scoped `PSModulePath`, use that instead of the default for the user</span></span>
  - <span data-ttu-id="60638-161">に `powershell.config.json` スコープのあるシステムが含まれている場合は、 `PSModulePath` システムの既定のではなく、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="60638-161">If `powershell.config.json` contains a system scoped `PSModulePath`, use that instead of the default for the system</span></span>

<span data-ttu-id="60638-162">Unix システムでは、ユーザー環境変数とシステム環境変数が分離されていません。</span><span class="sxs-lookup"><span data-stu-id="60638-162">Unix systems don't have a separation of User and System environment variables.</span></span>
<span data-ttu-id="60638-163">`PSModulePath` が継承され、まだ定義されていない場合は、PS7 固有のパスにプレフィックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="60638-163">`PSModulePath` is inherited and the PS7-specific paths are prefixed if not already defined.</span></span>

### <a name="starting-windows-powershell-from-powershell-7"></a><span data-ttu-id="60638-164">PowerShell 7 から Windows PowerShell を開始する</span><span class="sxs-lookup"><span data-stu-id="60638-164">Starting Windows PowerShell from PowerShell 7</span></span>

<span data-ttu-id="60638-165">この説明では、 _Windows PowerShell_ はとの両方を意味し `powershell.exe` `powershell_ise.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-165">For this discussion, _Windows PowerShell_ means both `powershell.exe` and `powershell_ise.exe`.</span></span>

<span data-ttu-id="60638-166">の値 `$env:PSModulePath` は、 `WinPSModulePath` 次の変更によってにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="60638-166">The value of `$env:PSModulePath` is copied to `WinPSModulePath` with the following modifications:</span></span>

- <span data-ttu-id="60638-167">ユーザーモジュールパスの PS7 を削除します。</span><span class="sxs-lookup"><span data-stu-id="60638-167">Remove PS7 the User module path</span></span>
- <span data-ttu-id="60638-168">システムモジュールパスの PS7 を削除します。</span><span class="sxs-lookup"><span data-stu-id="60638-168">Remove PS7 the System module path</span></span>
- <span data-ttu-id="60638-169">モジュールパスの PS7 を削除します。 `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="60638-169">Remove PS7 the `$PSHOME` module path</span></span>

<span data-ttu-id="60638-170">PS7 モジュールが Windows PowerShell に読み込まれないように、PS7 パスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="60638-170">The PS7 paths are removed so that PS7 modules don't get loaded in Windows PowerShell.</span></span> <span data-ttu-id="60638-171">この `WinPSModulePath` 値は、Windows PowerShell を起動するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="60638-171">The `WinPSModulePath` value is used when starting Windows PowerShell.</span></span>

### <a name="starting-powershell-7-from-windows-powershell"></a><span data-ttu-id="60638-172">Windows PowerShell から PowerShell 7 を開始する</span><span class="sxs-lookup"><span data-stu-id="60638-172">Starting PowerShell 7 from Windows PowerShell</span></span>

<span data-ttu-id="60638-173">PowerShell 7 のスタートアップは、Windows PowerShell によって追加された継承パスを追加することでそのままの状態で続行されます。</span><span class="sxs-lookup"><span data-stu-id="60638-173">The PowerShell 7 startup continues as-is with the addition of inheriting paths that Windows PowerShell added.</span></span> <span data-ttu-id="60638-174">PS7 固有のパスにはプレフィックスが付いているため、機能上の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="60638-174">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

### <a name="starting-powershell-6-from-powershell-7"></a><span data-ttu-id="60638-175">Powershell 7 から PowerShell 6 を開始する</span><span class="sxs-lookup"><span data-stu-id="60638-175">Starting PowerShell 6 from PowerShell 7</span></span>

<span data-ttu-id="60638-176">PowerShell Core 6 は上書きさ `$env:PSModulePath` れます。</span><span class="sxs-lookup"><span data-stu-id="60638-176">PowerShell Core 6 overwrites `$env:PSModulePath`.</span></span> <span data-ttu-id="60638-177">変更は行われません。</span><span class="sxs-lookup"><span data-stu-id="60638-177">No changes are made.</span></span>

### <a name="starting-powershell-7-from-powershell-6"></a><span data-ttu-id="60638-178">Powershell 6 から powershell 7 を開始する</span><span class="sxs-lookup"><span data-stu-id="60638-178">Starting PowerShell 7 from PowerShell 6</span></span>

<span data-ttu-id="60638-179">Powershell 7 のスタートアップは、PowerShell Core 6 によって追加された継承パスを追加することでそのままの状態で続行されます。</span><span class="sxs-lookup"><span data-stu-id="60638-179">The PowerShell 7 startup continues as-is with the addition of inheriting paths that PowerShell Core 6 added.</span></span> <span data-ttu-id="60638-180">PS7 固有のパスにはプレフィックスが付いているため、機能上の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="60638-180">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

## <a name="module-search-behavior"></a><span data-ttu-id="60638-181">モジュールの検索動作</span><span class="sxs-lookup"><span data-stu-id="60638-181">Module search behavior</span></span>

<span data-ttu-id="60638-182">PowerShell は、 **PSModulePath** のモジュール ( `.psd1` または) ファイルの各フォルダーを再帰的に検索し `.psm1` ます。</span><span class="sxs-lookup"><span data-stu-id="60638-182">PowerShell recursively searches each folder in the **PSModulePath** for module (`.psd1` or `.psm1`) files.</span></span> <span data-ttu-id="60638-183">この検索パターンを使用すると、同じモジュールの複数のバージョンを異なるフォルダーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="60638-183">This search pattern allows multiple versions of the same module to be installed in different folders.</span></span> <span data-ttu-id="60638-184">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="60638-184">For example:</span></span>

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules\PowerShellGet

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----           8/14/2020  5:56 PM                1.0.0.1
d----           9/13/2019  3:53 PM                2.1.2
```

<span data-ttu-id="60638-185">既定では、複数のバージョンが検出されると、PowerShell はモジュールの最大バージョン番号を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="60638-185">By default, PowerShell loads the highest version number of a module when multiple versions are found.</span></span> <span data-ttu-id="60638-186">特定のバージョンを読み込むには、FullyQualifiedName パラメーターを指定してを使用し `Import-Module` ます。 </span><span class="sxs-lookup"><span data-stu-id="60638-186">To load a specific version, use `Import-Module` with the **FullyQualifiedName** parameter.</span></span> <span data-ttu-id="60638-187">詳細については、「[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60638-187">For more information, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="see-also"></a><span data-ttu-id="60638-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="60638-188">See also</span></span>

- [<span data-ttu-id="60638-189">about_Modules</span><span class="sxs-lookup"><span data-stu-id="60638-189">about_Modules</span></span>](about_Modules.md)
- [<span data-ttu-id="60638-190">環境メソッド</span><span class="sxs-lookup"><span data-stu-id="60638-190">Environment Methods</span></span>](/dotnet/api/system.environment)

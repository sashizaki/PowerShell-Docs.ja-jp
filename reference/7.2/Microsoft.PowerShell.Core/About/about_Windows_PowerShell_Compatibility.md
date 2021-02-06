---
description: PowerShell 7 の Windows PowerShell 互換性機能について説明します。
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_Compatibility
ms.openlocfilehash: 3a7605765da8c17bad2d98a1d3fc3f7cc96f57b8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605442"
---
# <a name="about-windows-powershell-compatibility"></a><span data-ttu-id="97d49-103">Windows PowerShell の互換性について</span><span class="sxs-lookup"><span data-stu-id="97d49-103">About Windows PowerShell compatibility</span></span>

## <a name="short-description"></a><span data-ttu-id="97d49-104">概要</span><span class="sxs-lookup"><span data-stu-id="97d49-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="97d49-105">PowerShell 7 の Windows PowerShell 互換性機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="97d49-105">Describes the Windows PowerShell Compatibility functionality for PowerShell 7.</span></span>

## <a name="long-description"></a><span data-ttu-id="97d49-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="97d49-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="97d49-107">モジュールマニフェストによってモジュールが PowerShell Core と互換性があることが示されていない限り、フォルダー内のモジュール `%windir%\system32\WindowsPowerShell\v1.0\Modules` は windows powershell の互換性機能によってバックグラウンドの Windows powershell 5.1 プロセスで読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="97d49-107">Unless the module manifest indicates that module is compatible with PowerShell Core, modules in the `%windir%\system32\WindowsPowerShell\v1.0\Modules` folder are loaded in a background Windows PowerShell 5.1 process by Windows PowerShell Compatibility feature.</span></span>

### <a name="using-the-compatibility-feature"></a><span data-ttu-id="97d49-108">互換性機能の使用</span><span class="sxs-lookup"><span data-stu-id="97d49-108">Using the Compatibility feature</span></span>

<span data-ttu-id="97d49-109">Windows PowerShell の互換性機能を使用して最初のモジュールをインポートすると、PowerShell によって、 `WinPSCompatSession` バックグラウンドの Windows powershell 5.1 プロセスで実行されているという名前のリモートセッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="97d49-109">When the first module is imported using Windows PowerShell Compatibility feature, PowerShell creates a remote session named `WinPSCompatSession` that is running in a background Windows PowerShell 5.1 process.</span></span> <span data-ttu-id="97d49-110">このプロセスは、互換性機能が最初のモジュールをインポートするときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="97d49-110">This process is created when the Compatibility feature imports the first module.</span></span> <span data-ttu-id="97d49-111">このプロセスは、最後のモジュールが削除されたとき (を使用 `Remove-Module` )、または PowerShell プロセスが終了したときに閉じられます。</span><span class="sxs-lookup"><span data-stu-id="97d49-111">The process is closed when the last such module is removed (using `Remove-Module`) or when PowerShell process exits.</span></span>

<span data-ttu-id="97d49-112">セッションに読み込まれたモジュール `WinPSCompatSession` は、暗黙的なリモート処理によって使用され、現在の PowerShell セッションに反映されます。</span><span class="sxs-lookup"><span data-stu-id="97d49-112">The modules loaded in the `WinPSCompatSession` session are used via implicit remoting and reflected into current PowerShell session.</span></span> <span data-ttu-id="97d49-113">これは、PowerShell ジョブで使用されるトランスポート方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="97d49-113">This is the same transport method used for PowerShell jobs.</span></span>

<span data-ttu-id="97d49-114">モジュールをセッションにインポートすると `WinPSCompatSession` 、暗黙的なリモート処理によってユーザーのディレクトリにプロキシモジュールが生成され、 `$env:Temp` このプロキシモジュールが現在の PowerShell セッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="97d49-114">When a module is imported into the `WinPSCompatSession` session, implicit remoting generates a proxy module in the user's `$env:Temp` directory and imports this proxy module into current PowerShell session.</span></span> <span data-ttu-id="97d49-115">これにより、PowerShell は、Windows PowerShell の互換性機能を使用してモジュールが読み込まれたことを検出できます。</span><span class="sxs-lookup"><span data-stu-id="97d49-115">This allows PowerShell to detect that the module was loaded using Windows PowerShell Compatibility functionality.</span></span>

<span data-ttu-id="97d49-116">セッションが作成されると、逆シリアル化されたオブジェクトで正しく動作しない操作に対して使用できます。</span><span class="sxs-lookup"><span data-stu-id="97d49-116">Once the session is created, it can be used for operations that don't work correctly on deserialized objects.</span></span> <span data-ttu-id="97d49-117">パイプライン全体が Windows PowerShell で実行され、最終的な結果だけが返されます。</span><span class="sxs-lookup"><span data-stu-id="97d49-117">The entire pipeline is executed in Windows PowerShell and only the final result is returned.</span></span> <span data-ttu-id="97d49-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="97d49-118">For example:</span></span>

```powershell
$s = Get-PSSession -Name WinPSCompatSession
Invoke-Command -Session $s -ScriptBlock {
  "Running in Windows PowerShell version $($PSVersionTable.PSVersion)"
}
```

<span data-ttu-id="97d49-119">互換性機能は、次の2つの方法で呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="97d49-119">The Compatibility feature can be invoked in two ways:</span></span>

- <span data-ttu-id="97d49-120">**Usewindowspowershell** パラメーターを使用してモジュールを明示的にインポートする</span><span class="sxs-lookup"><span data-stu-id="97d49-120">Explicitly by importing a module using the **UseWindowsPowerShell** parameter</span></span>

   ```powershell
   Import-Module -Name ScheduledTasks -UseWindowsPowerShell
   ```

- <span data-ttu-id="97d49-121">Windows PowerShell モジュールをモジュール名、パス、またはコマンド検出による自動読み込みによって暗黙的にインポートします。</span><span class="sxs-lookup"><span data-stu-id="97d49-121">Implicitly by importing a Windows PowerShell module by module name, path, or autoloading via command discovery.</span></span>

   ```powershell
   Import-Module -Name ServerManager
   Get-AppLockerPolicy -Local
   ```

   <span data-ttu-id="97d49-122">まだ読み込まれていない場合は、を実行すると、AppLocker モジュールが自動読み込みされ  `Get-AppLockerPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="97d49-122">If not already loaded, the AppLocker module is autoloaded when you run  `Get-AppLockerPolicy`.</span></span>

<span data-ttu-id="97d49-123">Windows PowerShell 互換性ブロックは、PowerShell 構成ファイルの設定に一覧表示されているモジュールの読み込みをブロック `WindowsPowerShellCompatibilityModuleDenyList` します。</span><span class="sxs-lookup"><span data-stu-id="97d49-123">Windows PowerShell Compatibility blocks loading of modules that are listed in the `WindowsPowerShellCompatibilityModuleDenyList` setting in PowerShell configuration file.</span></span>

<span data-ttu-id="97d49-124">この設定の既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="97d49-124">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityModuleDenyList":  [
   "PSScheduledJob","BestPractices","UpdateServices"
]
```

### <a name="managing-implicit-module-loading"></a><span data-ttu-id="97d49-125">暗黙的なモジュール読み込みの管理</span><span class="sxs-lookup"><span data-stu-id="97d49-125">Managing implicit module loading</span></span>

<span data-ttu-id="97d49-126">Windows PowerShell の互換性機能の暗黙的なインポート動作を無効にするには、 `DisableImplicitWinCompat` powershell 構成ファイルの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="97d49-126">To disable implicit import behavior of the Windows PowerShell Compatibility feature, use the `DisableImplicitWinCompat` setting in a PowerShell configuration file.</span></span> <span data-ttu-id="97d49-127">この設定をファイルに追加でき `powershell.config.json` ます。</span><span class="sxs-lookup"><span data-stu-id="97d49-127">This setting can be added to the `powershell.config.json` file.</span></span> <span data-ttu-id="97d49-128">詳細については、「 [about_powershell_config](about_powershell_config.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97d49-128">For more information, see [about_powershell_config](about_powershell_config.md).</span></span>

<span data-ttu-id="97d49-129">この例では、Windows PowerShell の互換性に関するモジュール読み込みの暗黙的な機能を無効にする構成ファイルを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="97d49-129">This example shows how to create a configuration file that disables the implicit module-loading feature of Windows PowerShell Compatibility.</span></span>

```powershell
$ConfigPath = "$PSHOME\DisableWinCompat.powershell.config.json"
$ConfigJSON = ConvertTo-Json -InputObject @{
  "DisableImplicitWinCompat" = $true
  "Microsoft.PowerShell:ExecutionPolicy" = "RemoteSigned"
}
$ConfigJSON | Out-File -Force $ConfigPath
pwsh -settingsFile $ConfigPath
```

<span data-ttu-id="97d49-130">モジュールの互換性に関する最新情報については、 [PowerShell 7 モジュールの互換性](https://aka.ms/PSModuleCompat) リストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97d49-130">For more the latest information about module compatibility, see the [PowerShell 7 module compatibility](https://aka.ms/PSModuleCompat) list.</span></span>

### <a name="managing-cmdlet-clobbering"></a><span data-ttu-id="97d49-131">コマンドレット clobbering の管理</span><span class="sxs-lookup"><span data-stu-id="97d49-131">Managing cmdlet clobbering</span></span>

<span data-ttu-id="97d49-132">Windows PowerShell の互換性機能は、暗黙的なリモート処理を使用してモジュールを互換モードで読み込みます。</span><span class="sxs-lookup"><span data-stu-id="97d49-132">The Windows PowerShell Compatibility feature uses implicit remoting to load modules in compatibility mode.</span></span> <span data-ttu-id="97d49-133">その結果、モジュールによってエクスポートされたコマンドは、現在の PowerShell 7 セッションで同じ名前のコマンドよりも優先されるようになります。</span><span class="sxs-lookup"><span data-stu-id="97d49-133">The result is that commands exported by the module take precedence over commands of the same name in the current PowerShell 7 session.</span></span> <span data-ttu-id="97d49-134">PowerShell 7.0.0 リリースでは、PowerShell に付属するコアモジュールがこれに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="97d49-134">In the PowerShell 7.0.0 release, this included the core modules that ship with PowerShell.</span></span>

<span data-ttu-id="97d49-135">PowerShell 7.1 では、次のコア PowerShell モジュールが上書きされないように動作が変更されました。</span><span class="sxs-lookup"><span data-stu-id="97d49-135">In PowerShell 7.1, the behavior was changed so that the following core PowerShell modules are not clobbered:</span></span>

- <span data-ttu-id="97d49-136">Microsoft. PowerShell ホスト</span><span class="sxs-lookup"><span data-stu-id="97d49-136">Microsoft.PowerShell.ConsoleHost</span></span>
- <span data-ttu-id="97d49-137">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="97d49-137">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="97d49-138">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="97d49-138">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="97d49-139">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="97d49-139">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="97d49-140">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="97d49-140">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="97d49-141">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="97d49-141">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="97d49-142">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="97d49-142">Microsoft.WSMan.Management</span></span>

<span data-ttu-id="97d49-143">また、PowerShell 7.1 では、互換性モードで上書きできない追加のモジュールを一覧表示する機能も追加されました。</span><span class="sxs-lookup"><span data-stu-id="97d49-143">PowerShell 7.1 also added the ability to list additional modules that should not be clobbered by compatibility mode.</span></span>

<span data-ttu-id="97d49-144">`WindowsPowerShellCompatibilityNoClobberModuleList`PowerShell 構成ファイルに設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="97d49-144">You can add the `WindowsPowerShellCompatibilityNoClobberModuleList` setting to PowerShell configuration file.</span></span> <span data-ttu-id="97d49-145">この設定の値は、モジュール名のコンマ区切りのリストです。</span><span class="sxs-lookup"><span data-stu-id="97d49-145">The value of this setting is a comma-separated list of module names.</span></span> <span data-ttu-id="97d49-146">この設定の既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="97d49-146">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityNoClobberModuleList": [ ]
```

## <a name="limitations"></a><span data-ttu-id="97d49-147">制限事項</span><span class="sxs-lookup"><span data-stu-id="97d49-147">Limitations</span></span>

<span data-ttu-id="97d49-148">Windows PowerShell の互換性機能:</span><span class="sxs-lookup"><span data-stu-id="97d49-148">The Windows PowerShell Compatibility functionality:</span></span>

1. <span data-ttu-id="97d49-149">Windows コンピューターでのみローカルに機能する</span><span class="sxs-lookup"><span data-stu-id="97d49-149">Only works locally on Windows computers</span></span>
1. <span data-ttu-id="97d49-150">Windows PowerShell 5.1 が必要です。</span><span class="sxs-lookup"><span data-stu-id="97d49-150">Requires that Windows PowerShell 5.1</span></span>
1. <span data-ttu-id="97d49-151">ライブオブジェクトではなく、シリアル化されたコマンドレットパラメーターと戻り値を操作します。</span><span class="sxs-lookup"><span data-stu-id="97d49-151">Operates on serialized cmdlet parameters and return values, not on live objects</span></span>
1. <span data-ttu-id="97d49-152">Windows PowerShell リモート処理セッションにインポートされたすべてのモジュールは、同じ実行空間を共有します。</span><span class="sxs-lookup"><span data-stu-id="97d49-152">All modules imported into the Windows PowerShell remoting session share the same runspace.</span></span>

## <a name="keywords"></a><span data-ttu-id="97d49-153">Keywords</span><span class="sxs-lookup"><span data-stu-id="97d49-153">Keywords</span></span>

<span data-ttu-id="97d49-154">about_Windows_PowerShell_Compatibility</span><span class="sxs-lookup"><span data-stu-id="97d49-154">about_Windows_PowerShell_Compatibility</span></span>

## <a name="see-also"></a><span data-ttu-id="97d49-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="97d49-155">See also</span></span>

[<span data-ttu-id="97d49-156">about_Modules</span><span class="sxs-lookup"><span data-stu-id="97d49-156">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="97d49-157">Import-Module</span><span class="sxs-lookup"><span data-stu-id="97d49-157">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)


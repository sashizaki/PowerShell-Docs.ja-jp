---
description: レジストリ構成を置き換える PowerShell Core の構成ファイル。
keywords: powershell
Locale: en-US
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Config
ms.openlocfilehash: 88e2f5fc5eaaf3ffffd5ceb3df0632866eee705e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223088"
---
# <a name="about-powershell-config"></a><span data-ttu-id="ebaa0-104">PowerShell の構成について</span><span class="sxs-lookup"><span data-stu-id="ebaa0-104">About PowerShell Config</span></span>

## <a name="short-description"></a><span data-ttu-id="ebaa0-105">概要</span><span class="sxs-lookup"><span data-stu-id="ebaa0-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ebaa0-106">レジストリ構成を置き換える PowerShell Core の構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-106">Configuration files for PowerShell Core, replacing Registry configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="ebaa0-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="ebaa0-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ebaa0-108">このファイルには、 `powershell.config.json` PowerShell Core の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-108">The `powershell.config.json` file contains configuration settings for PowerShell Core.</span></span> <span data-ttu-id="ebaa0-109">PowerShell は起動時にこの構成を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-109">PowerShell loads this configuration at startup.</span></span> <span data-ttu-id="ebaa0-110">設定は、実行時に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-110">The settings can also be modified at runtime.</span></span> <span data-ttu-id="ebaa0-111">以前は、これらの設定は PowerShell 用の Windows レジストリに格納されていましたが、macOS と Linux での構成を可能にするためにファイルに含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-111">Previously, these settings were stored in the Windows Registry for PowerShell, but are now contained in a file to enable configuration on macOS and Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="ebaa0-112">ファイルに `powershell.config.json` 無効な JSON が含まれている場合は、対話型セッションを開始できません。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-112">If the `powershell.config.json` file contains invalid JSON PowerShell cannot start an interactive session.</span></span>
> <span data-ttu-id="ebaa0-113">この問題が発生した場合は、構成ファイルを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-113">If this occurs, you must fix the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="ebaa0-114">認識されないキーまたは構成ファイル内の無効な値は、警告なしで無視されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-114">Unrecognized keys or invalid values in the configuration file will be silently ignored.</span></span>

### <a name="allusers-shared-configuration"></a><span data-ttu-id="ebaa0-115">AllUsers (共有) 構成</span><span class="sxs-lookup"><span data-stu-id="ebaa0-115">AllUsers (shared) configuration</span></span>

<span data-ttu-id="ebaa0-116">`powershell.config.json`ディレクトリ内のファイルは、 `$PSHOME` その powershell コアインストールから実行されているすべての powershell コアセッションの構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-116">A `powershell.config.json` file in the `$PSHOME` directory defines the configuration for all PowerShell Core sessions running from that PowerShell Core installation.</span></span>

> [!NOTE]
> <span data-ttu-id="ebaa0-117">この `$PSHOME` 場所は、実行中の System.Management.Automation.dll アセンブリと同じディレクトリとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-117">The `$PSHOME` location is defined as the same directory as the executing System.Management.Automation.dll assembly.</span></span> <span data-ttu-id="ebaa0-118">これは、ホストされている PowerShell SDK インスタンスにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-118">This applies to hosted PowerShell SDK instances as well.</span></span>

### <a name="currentuser-per-user-configurations"></a><span data-ttu-id="ebaa0-119">CurrentUser (ユーザー単位) の構成</span><span class="sxs-lookup"><span data-stu-id="ebaa0-119">CurrentUser (per-user) configurations</span></span>

<span data-ttu-id="ebaa0-120">ユーザースコープの構成ディレクトリにファイルを配置することで、ユーザーごとに PowerShell を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-120">You can also configure PowerShell on a per-user basis by placing the file in the user-scope configuration directory.</span></span> <span data-ttu-id="ebaa0-121">ユーザー構成ディレクトリは、コマンドを使用してプラットフォーム間で検出でき `Split-Path $PROFILE.CurrentUserCurrentHost` ます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-121">The user configuration directory can be found across platforms with the command `Split-Path $PROFILE.CurrentUserCurrentHost`.</span></span>

## <a name="general-configuration-settings"></a><span data-ttu-id="ebaa0-122">全般構成設定</span><span class="sxs-lookup"><span data-stu-id="ebaa0-122">General configuration settings</span></span>

### <a name="executionpolicy"></a><span data-ttu-id="ebaa0-123">ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ebaa0-123">ExecutionPolicy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebaa0-124">この構成は、Windows プラットフォームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-124">This configuration only applies on Windows platforms.</span></span>

<span data-ttu-id="ebaa0-125">PowerShell セッションの実行ポリシーを構成し、実行できるスクリプトを決定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-125">Configures the execution policy for PowerShell sessions, determining what scripts can be run.</span></span> <span data-ttu-id="ebaa0-126">既定では、PowerShell は既存の実行ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-126">By default, PowerShell uses the existing execution policy.</span></span>

<span data-ttu-id="ebaa0-127">AllUsers 構成の場合、これによって **LocalMachine** 実行ポリシーが設定されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-127">For AllUsers configurations, this sets the **LocalMachine** execution policy.</span></span>
<span data-ttu-id="ebaa0-128">CurrentUser 構成の場合、 **currentuser** 実行ポリシーが設定されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-128">For CurrentUser configurations, this sets the **CurrentUser** execution policy.</span></span>

> [!NOTE]
> <span data-ttu-id="ebaa0-129">[`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)コマンドレットは、を使用して呼び出されたときに AllUsers 構成ファイル内のこの設定を変更 `-Scope LocalMachine` し、で呼び出されたときに CurrentUser 構成ファイルでこの設定を変更し `-Scope CurrentUser` ます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-129">The [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) cmdlet modifies this setting in the AllUsers configuration file when invoked with `-Scope LocalMachine`, and modifies this setting in the CurrentUser configuration file when invoked with `-Scope CurrentUser`.</span></span>

```Schema
"<shell-id>:ExecutionPolicy": "<execution-policy>"
```

<span data-ttu-id="ebaa0-130">各値の説明:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-130">Where:</span></span>

- <span data-ttu-id="ebaa0-131">`<shell-id>` 現在の PowerShell ホストの ID を参照します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-131">`<shell-id>` refers to the ID of the current PowerShell host.</span></span>
  <span data-ttu-id="ebaa0-132">通常の PowerShell Core の場合、これは `Microsoft.PowerShell` です。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-132">For normal PowerShell Core, this is `Microsoft.PowerShell`.</span></span>
  <span data-ttu-id="ebaa0-133">任意の PowerShell セッションで、を使用して検出でき `$ShellId` ます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-133">In any PowerShell session, you can discover it with `$ShellId`.</span></span>
- <span data-ttu-id="ebaa0-134">`<execution-policy>` 有効な実行ポリシー名を参照します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-134">`<execution-policy>` refers to a valid execution policy name.</span></span>

<span data-ttu-id="ebaa0-135">次の例では、PowerShell の実行ポリシーをに設定し `RemoteSigned` ます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-135">The following example sets the execution policy of PowerShell to `RemoteSigned`.</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "RemoteSigned"
}
```

<span data-ttu-id="ebaa0-136">Windows では、同等のレジストリキーがおよびの `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` 下にあり `HKEY_LOCAL_MACHINE` `HKEY_CURRENT_USER` ます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-136">In Windows, the equivalent registry keys can be found in `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` under `HKEY_LOCAL_MACHINE` and `HKEY_CURRENT_USER`.</span></span>

### <a name="psmodulepath"></a><span data-ttu-id="ebaa0-137">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="ebaa0-137">PSModulePath</span></span>

<span data-ttu-id="ebaa0-138">この PowerShell セッションの PSModulePath コンポーネントをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-138">Overrides a PSModulePath component for this PowerShell session.</span></span> <span data-ttu-id="ebaa0-139">現在のユーザーの構成である場合は、CurrentUser モジュールのパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-139">If the configuration is for the current user, sets the CurrentUser module path.</span></span> <span data-ttu-id="ebaa0-140">構成がすべてのユーザーを対象としている場合は、AllUser モジュールパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-140">If the configuration is for all users, sets the AllUser module path.</span></span>

> [!WARNING]
> <span data-ttu-id="ebaa0-141">ここで AllUsers または CurrentUser モジュールパスを構成しても、 [インストールモジュール](/powershell/module/powershellget/install-module)のような PowerShellGet モジュールの対象となるインストール場所は変更されません。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-141">Configuring an AllUsers or CurrentUser module path here will not change the scoped installation location for PowerShellGet modules like [Install-Module](/powershell/module/powershellget/install-module).</span></span>
> <span data-ttu-id="ebaa0-142">これらのコマンドレットは、常に *既定* のモジュールパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-142">These cmdlets always use the *default* module paths.</span></span>

<span data-ttu-id="ebaa0-143">値が設定されていない場合は、それぞれのモジュールパスコンポーネントの既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-143">If no value is set, the default value for the respective module path component will be used.</span></span> <span data-ttu-id="ebaa0-144">これらの既定の詳細については、「 [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-144">See [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) for more details on these defaults.</span></span>

<span data-ttu-id="ebaa0-145">この設定により、CMD で許可され `%` `"%HOME%\Documents\PowerShell\Modules"` ているのと同じように、環境変数を文字間に埋め込むことによって使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-145">This setting allows environment variables to be used by embedding them between `%` characters, like `"%HOME%\Documents\PowerShell\Modules"`, in the same way as CMD allows.</span></span> <span data-ttu-id="ebaa0-146">この構文は、Linux と macOS でも適用されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-146">This syntax also applies on Linux and macOS.</span></span> <span data-ttu-id="ebaa0-147">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-147">See below for examples.</span></span>

```Schema
"PSModulePath": "<ps-module-path>"
```

<span data-ttu-id="ebaa0-148">各値の説明:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-148">Where:</span></span>

- <span data-ttu-id="ebaa0-149">`<ps-module-path>` は、モジュールディレクトリへの絶対パスです。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-149">`<ps-module-path>` is the absolute path to a module directory.</span></span> <span data-ttu-id="ebaa0-150">すべてのユーザー構成について、これは AllUsers 共有モジュールディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-150">For all user configurations, this is the AllUsers shared module directory.</span></span> <span data-ttu-id="ebaa0-151">現在のユーザー構成では、CurrentUser モジュールディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-151">For current user configurations, this is CurrentUser module directory.</span></span>

<span data-ttu-id="ebaa0-152">次の例は、Windows 環境の PSModulePath 構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-152">This example shows a PSModulePath configuration for a Windows environment:</span></span>

```json
{
  "PSModulePath": "C:\\Program Files\\PowerShell\\6\\Modules"
}
```

<span data-ttu-id="ebaa0-153">次の例は、macOS または Linux 環境の PSModulePath 構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-153">This example shows a PSModulePath configuration for a macOS or Linux environment:</span></span>

```json
{
  "PSModulePath": "/opt/powershell/6/Modules"
}
```

<span data-ttu-id="ebaa0-154">この例では、PSModulePath 構成に環境変数を埋め込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-154">This example shows embedding an environment variable in a PSModulePath configuration.</span></span> <span data-ttu-id="ebaa0-155">`HOME`環境変数とディレクトリの区切り記号を使用すると `/` 、Windows、MacOS、Linux で動作することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-155">Note that using the `HOME` environment variable and the `/` directory separator, this will work on Windows, macOS and Linux.</span></span>

```json
{
  "PSModulePath": "%HOME%/Documents/PowerShell/Modules"
}
```

<span data-ttu-id="ebaa0-156">この例では、macOS と Linux でのみ機能する PSModulePath 構成に環境変数を埋め込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-156">This example shows embedding an environment variable in a PSModulePath configuration that will only work on macOS and Linux:</span></span>

```json
{
  "PSModulePath": "%XDG_CONFIG_HOME%/powershell/Modules"
}
```

> [!NOTE]
> <span data-ttu-id="ebaa0-157">PowerShell 変数は、PSModulePath 構成に埋め込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-157">PowerShell variables cannot be embedded in PSModulePath configurations.</span></span>
> <span data-ttu-id="ebaa0-158">Linux と macOS での PSModulePath の構成では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-158">PSModulePath configurations on Linux and macOS are case-sensitive.</span></span> <span data-ttu-id="ebaa0-159">PSModulePath 構成では、プラットフォームに有効なディレクトリ区切り記号を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-159">A PSModulePath configuration must use valid directory separators for the platform.</span></span> <span data-ttu-id="ebaa0-160">MacOS と Linux では、これは `/` です。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-160">On macOS and Linux, this means `/`.</span></span> <span data-ttu-id="ebaa0-161">Windows では、 `/` との両方 `\` が動作します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-161">On Windows, both `/` and `\` will work.</span></span>

### <a name="experimentalfeatures"></a><span data-ttu-id="ebaa0-162">ExperimentalFeatures</span><span class="sxs-lookup"><span data-stu-id="ebaa0-162">ExperimentalFeatures</span></span>

<span data-ttu-id="ebaa0-163">PowerShell で有効にする試験的な機能の名前。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-163">The names of the experimental features to enable in PowerShell.</span></span>
<span data-ttu-id="ebaa0-164">既定では、試験的な機能は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-164">By default, no experimental features are enabled.</span></span>
<span data-ttu-id="ebaa0-165">既定値は空の配列です。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-165">The default value is an empty array.</span></span>

```Schema
"ExperimentalFeatures": ["<experimental-feature-name>", ...]
```

<span data-ttu-id="ebaa0-166">各値の説明:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-166">Where:</span></span>

- <span data-ttu-id="ebaa0-167">`<experimental-feature-name>` 有効にする試験的な機能の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-167">`<experimental-feature-name>` is the name of an experimental feature to enable.</span></span>

<span data-ttu-id="ebaa0-168">次の例では、PowerShell の起動時に **PSImplicitRemoting** と **PSUseAbbreviationExpansion** の試験的な機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-168">The following example enables the **PSImplicitRemoting** and **PSUseAbbreviationExpansion** experimental features when PowerShell starts up.</span></span>

```json
{
  "ExperimentalFeatures": [
    "PSImplicitRemotingBatching",
    "PSUseAbbreviationExpansion"
  ]
}
```

<span data-ttu-id="ebaa0-169">試験的な機能の詳細については、「 [POWERSHELL RFC 29][RFC0029]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-169">For more information on experimental features, see [PowerShell RFC 29][RFC0029].</span></span>

## <a name="non-windows-logging-configuration"></a><span data-ttu-id="ebaa0-170">Windows 以外のログの構成</span><span class="sxs-lookup"><span data-stu-id="ebaa0-170">Non-Windows logging configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebaa0-171">このセクションの構成オプションは、macOS と Linux にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-171">The configuration options in this section only apply to macOS and Linux.</span></span>
> <span data-ttu-id="ebaa0-172">Windows のログは、Windows イベントビューアーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-172">Logging for Windows is managed by the Windows Event Viewer.</span></span>

<span data-ttu-id="ebaa0-173">Powershell の macOS と Linux でのログ記録は、PowerShell 構成ファイルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-173">PowerShell's logging on macOS and Linux can be configured in the PowerShell configuration file.</span></span> <span data-ttu-id="ebaa0-174">Windows 以外のシステムの PowerShell ログの詳細については、「 [ログ記録につい](./about_Logging_Non-Windows.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-174">For a full description of PowerShell logging for non-Windows systems, see [About Logging](./about_Logging_Non-Windows.md).</span></span>

### <a name="logidentity"></a><span data-ttu-id="ebaa0-175">LogIdentity</span><span class="sxs-lookup"><span data-stu-id="ebaa0-175">LogIdentity</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebaa0-176">この設定は、macOS と Linux でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-176">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="ebaa0-177">システムログへの書き込みに使用する id 名を設定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-177">Sets the identity name used to write to the system log.</span></span> <span data-ttu-id="ebaa0-178">既定値は "powershell" です。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-178">The default value is "powershell".</span></span>

```Schema
"LogIdentity": "<log-identity>"
```

<span data-ttu-id="ebaa0-179">各値の説明:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-179">Where:</span></span>

- <span data-ttu-id="ebaa0-180">`<log-identity>` は、PowerShell が syslog に書き込むために使用する文字列 id です。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-180">`<log-identity>` is the string identity that PowerShell should use for writing to syslog.</span></span>

> [!NOTE]
> <span data-ttu-id="ebaa0-181">インストールした PowerShell のインスタンスごとに異なる **Logidentity** 値を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-181">You may want to have different **LogIdentity** values for each different instance of PowerShell you have installed.</span></span>

<span data-ttu-id="ebaa0-182">この例では、PowerShell のプレビューリリースの **Logidentity** を構成しています。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-182">In this example, we are configuring the **LogIdentity** for a preview release of PowerShell.</span></span>

```json
{
  "LogIdentity": "powershell-preview"
}
```

### <a name="loglevel"></a><span data-ttu-id="ebaa0-183">LogLevel</span><span class="sxs-lookup"><span data-stu-id="ebaa0-183">LogLevel</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebaa0-184">この設定は、macOS と Linux でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-184">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="ebaa0-185">PowerShell がログに記録する必要がある最小重大度レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-185">Specifies the minimum severity level at which PowerShell should log.</span></span>

```Schema
"LogLevel": "<log-level>|default"
```

<span data-ttu-id="ebaa0-186">各値の説明:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-186">Where:</span></span>

- <span data-ttu-id="ebaa0-187">`<log-level>` 次のいずれか:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-187">`<log-level>` is one of:</span></span>
  - <span data-ttu-id="ebaa0-188">Always</span><span class="sxs-lookup"><span data-stu-id="ebaa0-188">Always</span></span>
  - <span data-ttu-id="ebaa0-189">Critical</span><span class="sxs-lookup"><span data-stu-id="ebaa0-189">Critical</span></span>
  - <span data-ttu-id="ebaa0-190">エラー</span><span class="sxs-lookup"><span data-stu-id="ebaa0-190">Error</span></span>
  - <span data-ttu-id="ebaa0-191">警告</span><span class="sxs-lookup"><span data-stu-id="ebaa0-191">Warning</span></span>
  - <span data-ttu-id="ebaa0-192">Informational</span><span class="sxs-lookup"><span data-stu-id="ebaa0-192">Informational</span></span>
  - <span data-ttu-id="ebaa0-193">"詳細"</span><span class="sxs-lookup"><span data-stu-id="ebaa0-193">Verbose</span></span>
  - <span data-ttu-id="ebaa0-194">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ebaa0-194">Debug</span></span>

> [!NOTE]
> <span data-ttu-id="ebaa0-195">ログレベルを設定すると、その上にあるすべてのログレベルが有効になります。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-195">Setting a the log level enables all log levels above it.</span></span>

<span data-ttu-id="ebaa0-196">この設定を **default** に設定すると、既定値として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-196">Setting this setting to **default** will be interpreted as the default value.</span></span>
<span data-ttu-id="ebaa0-197">既定値は **情報** です。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-197">The default value is **Informational**.</span></span>

<span data-ttu-id="ebaa0-198">次の例では、値を **Verbose** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-198">The following example sets the value to **Verbose**.</span></span>

```json
{
  "LogLevel": "Verbose"
}
```

### <a name="logchannels"></a><span data-ttu-id="ebaa0-199">LogChannels</span><span class="sxs-lookup"><span data-stu-id="ebaa0-199">LogChannels</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebaa0-200">この設定は、macOS と Linux でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-200">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="ebaa0-201">有効にするログチャネルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-201">Determines which logging channels are enabled.</span></span>

```Schema
"LogChannels": "<log-channel>,..."
```

<span data-ttu-id="ebaa0-202">各値の説明:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-202">Where:</span></span>

- <span data-ttu-id="ebaa0-203">`<log-channel>` 次のいずれか:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-203">`<log-channel>` is one of:</span></span>
  - <span data-ttu-id="ebaa0-204">操作ログ PowerShell アクティビティに関する基本情報</span><span class="sxs-lookup"><span data-stu-id="ebaa0-204">Operational - logs basic information about PowerShell activities</span></span>
  - <span data-ttu-id="ebaa0-205">分析-より詳細な診断情報をログに記録します</span><span class="sxs-lookup"><span data-stu-id="ebaa0-205">Analytic - logs more detailed diagnostic information</span></span>

<span data-ttu-id="ebaa0-206">既定値は **Operational** です。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-206">The default value is **Operational**.</span></span> <span data-ttu-id="ebaa0-207">両方のチャネルを有効にするには、両方の値を1つのコンマ区切りの文字列として指定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-207">To enable both channels, include both values as a single comma-separated string.</span></span> <span data-ttu-id="ebaa0-208">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-208">For example:</span></span>

```json
{
  "LogChannels": "Operational,Analytic"
}
```

### <a name="logkeywords"></a><span data-ttu-id="ebaa0-209">LogKeywords</span><span class="sxs-lookup"><span data-stu-id="ebaa0-209">LogKeywords</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebaa0-210">この設定は、macOS と Linux でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-210">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="ebaa0-211">PowerShell のどの部分がログに記録されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-211">Determines which parts of PowerShell are logged.</span></span> <span data-ttu-id="ebaa0-212">既定では、すべてのログキーワードが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-212">By default, all log keywords are enabled.</span></span> <span data-ttu-id="ebaa0-213">複数のキーワードを有効にするには、1つのコンマ区切りの文字列で値を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-213">To enable multiple keywords, list the values in a single comma-separated string.</span></span>

```Schema
"LogKeywords": "<log-keyword>,..."
```

<span data-ttu-id="ebaa0-214">各値の説明:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-214">Where:</span></span>

- <span data-ttu-id="ebaa0-215">`<log-keyword>` 次のいずれか:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-215">`<log-keyword>` is one of:</span></span>
  - <span data-ttu-id="ebaa0-216">実行空間-実行空間の管理</span><span class="sxs-lookup"><span data-stu-id="ebaa0-216">Runspace - runspace management</span></span>
  - <span data-ttu-id="ebaa0-217">パイプラインパイプライン操作</span><span class="sxs-lookup"><span data-stu-id="ebaa0-217">Pipeline - pipeline operations</span></span>
  - <span data-ttu-id="ebaa0-218">プロトコル通信プロトコルの処理 (PSRP など)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-218">Protocol - communication protocol handling, such as PSRP</span></span>
  - <span data-ttu-id="ebaa0-219">トランスポート-トランスポート層のサポート (SSH など)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-219">Transport - transport layer support, such as SSH</span></span>
  - <span data-ttu-id="ebaa0-220">ホスト-PowerShell ホストの機能 (コンソールの相互作用など)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-220">Host - PowerShell host functionality, for example console interaction</span></span>
  - <span data-ttu-id="ebaa0-221">コマンドレット-PowerShell の組み込みコマンドレット</span><span class="sxs-lookup"><span data-stu-id="ebaa0-221">Cmdlets -PowerShell builtin cmdlets</span></span>
  - <span data-ttu-id="ebaa0-222">シリアライザー-シリアル化ロジック</span><span class="sxs-lookup"><span data-stu-id="ebaa0-222">Serializer - serialization logic</span></span>
  - <span data-ttu-id="ebaa0-223">セッション-PowerShell セッションの状態</span><span class="sxs-lookup"><span data-stu-id="ebaa0-223">Session - PowerShell session state</span></span>
  - <span data-ttu-id="ebaa0-224">ManagedPlugin-WSMan プラグイン</span><span class="sxs-lookup"><span data-stu-id="ebaa0-224">ManagedPlugin - WSMan plugin</span></span>

> [!NOTE]
> <span data-ttu-id="ebaa0-225">一般的に、PowerShell の既知の部分で特定の動作を診断する場合を除き、この値を設定しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-225">It is generally advised to leave this value unset unless you are trying to diagnose a specific behavior in a known part of PowerShell.</span></span>
> <span data-ttu-id="ebaa0-226">この値を変更すると、ログに記録される情報の量が減少します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-226">Changing this value only decreases the amount of information logged.</span></span>

<span data-ttu-id="ebaa0-227">この例では、実行空間操作、パイプラインロジック、およびコマンドレットの使用に対するログ記録を制限します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-227">This example limits the logging to runspace operations, pipeline logic, and cmdlet use.</span></span> <span data-ttu-id="ebaa0-228">その他のすべてのログは省略されます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-228">All other logging will be omitted.</span></span>

```json
"LogKeywords": "Runspace,Pipeline,Cmdlets"
```

<!--

## Group policy configuration

### ScriptExecution

### ScriptBlockLogging

### ProtectedEventLogging

### Transcription

### UpdateableHelp

### ConsoleSessionConfiguration

-->

## <a name="more-example-configurations"></a><span data-ttu-id="ebaa0-229">その他の構成の例</span><span class="sxs-lookup"><span data-stu-id="ebaa0-229">More example configurations</span></span>

### <a name="example-windows-configuration"></a><span data-ttu-id="ebaa0-230">Windows の構成例</span><span class="sxs-lookup"><span data-stu-id="ebaa0-230">Example Windows configuration</span></span>

<span data-ttu-id="ebaa0-231">この構成では、より多くの設定が明示的に設定されています。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-231">This configuration has more settings explicitly set:</span></span>

- <span data-ttu-id="ebaa0-232">この PowerShell インストールの実行ポリシーは次のようになります。 `AllSigned`</span><span class="sxs-lookup"><span data-stu-id="ebaa0-232">Execution policy for this PowerShell installation is `AllSigned`</span></span>
- <span data-ttu-id="ebaa0-233">CurrentUser モジュールパスは、共有ドライブ上のモジュールディレクトリに設定されています</span><span class="sxs-lookup"><span data-stu-id="ebaa0-233">The CurrentUser module path is set to a module directory on a shared drive</span></span>
- <span data-ttu-id="ebaa0-234">`PSImplicitRemotingBatching`試験的な機能が有効になっている</span><span class="sxs-lookup"><span data-stu-id="ebaa0-234">The `PSImplicitRemotingBatching` experimental feature is enabled</span></span>

> [!NOTE]
> <span data-ttu-id="ebaa0-235">`ExecutionPolicy`ここでの設定との設定は、 `PSModulePath` Windows プラットフォームでのみ機能します。モジュールパスで `\` 区切り文字が使用され `;` ており、実行ポリシーが `Unrestricted` (UNIX に似たプラットフォームでのみ許可されている) であるためです。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-235">The `ExecutionPolicy` and `PSModulePath` settings here would only work on a Windows platform, since the module path uses `\` and `;` separator characters and the execution policy is not `Unrestricted` (the only policy allowed on UNIX-like platforms).</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "AllSigned",
  "PSModulePath": "Z:\\Marisol's Shared Drive\\Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
}
```

### <a name="example-non-windows-configuration"></a><span data-ttu-id="ebaa0-236">Windows 以外の構成の例</span><span class="sxs-lookup"><span data-stu-id="ebaa0-236">Example non-Windows configuration</span></span>

<span data-ttu-id="ebaa0-237">この構成では、macOS または Linux でのみ機能するいくつかのオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-237">This configuration sets a number of options that only work in macOS or Linux:</span></span>

- <span data-ttu-id="ebaa0-238">CurrentUser モジュールパスは、のカスタムモジュールディレクトリに設定されます。 `$HOME`</span><span class="sxs-lookup"><span data-stu-id="ebaa0-238">The CurrentUser module path is set to a custom module directory in `$HOME`</span></span>
- <span data-ttu-id="ebaa0-239">**PSImplicitRemotingBatching** の試験的な機能が有効になっている</span><span class="sxs-lookup"><span data-stu-id="ebaa0-239">The **PSImplicitRemotingBatching** experimental feature is enabled</span></span>
- <span data-ttu-id="ebaa0-240">ログ記録の詳細については、PowerShell のログ記録レベルを **Verbose** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-240">The PowerShell logging level is set to **Verbose** , for more logging</span></span>
- <span data-ttu-id="ebaa0-241">この PowerShell インストールでは、 **ホーム-PowerShell** id を使用してログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-241">This PowerShell installation writes to the logs using the **home-powershell** identity.</span></span>

```json
{
  "PSModulePath": "%HOME%/.powershell/Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
  "LogLevel": "Verbose",
  "LogIdentity": "home-powershell"
}
```

## <a name="see-also"></a><span data-ttu-id="ebaa0-242">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebaa0-242">See also</span></span>

[<span data-ttu-id="ebaa0-243">実行ポリシーについて</span><span class="sxs-lookup"><span data-stu-id="ebaa0-243">About Execution Policies</span></span>](./about_Execution_Policies.md)

[<span data-ttu-id="ebaa0-244">自動変数について</span><span class="sxs-lookup"><span data-stu-id="ebaa0-244">About Automatic Variables</span></span>](./about_Automatic_Variables.md)

[RFC0029]: https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md

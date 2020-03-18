---
title: PowerShell 7.0 の新機能
description: PowerShell 7.0 でリリースされた新機能と変更
ms.date: 03/04/2020
ms.openlocfilehash: 6915bb70d6e54da86d2b935e3feed8d7f3770ba9
ms.sourcegitcommit: 4a26c05f162c4fa347a9d67e339f8a33e230b9ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78404993"
---
# <a name="whats-new-in-powershell-70"></a><span data-ttu-id="dbb1f-103">PowerShell 7.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="dbb1f-103">What's New in PowerShell 7.0</span></span>

<span data-ttu-id="dbb1f-104">PowerShell 7.0 は、異種環境とハイブリッド クラウドを管理するために構築された、PowerShell のオープン ソースのクロスプラットフォーム (Windows、macOS、Linux) エディションです。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-104">PowerShell 7.0 is an open-source, cross-platform (Windows, macOS, and Linux) edition of PowerShell, built to manage heterogeneous environments and hybrid cloud.</span></span>

<span data-ttu-id="dbb1f-105">このリリースでは、次のような新機能がいくつか導入されました。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-105">In this release, we're introducing a number of new features, including:</span></span>

- <span data-ttu-id="dbb1f-106">パイプラインの並列化 (`ForEach-Object -Parallel` を使用)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-106">Pipeline parallelization with `ForEach-Object -Parallel`</span></span>
- <span data-ttu-id="dbb1f-107">新しい演算子:</span><span class="sxs-lookup"><span data-stu-id="dbb1f-107">New operators:</span></span>
  - <span data-ttu-id="dbb1f-108">三項演算子: `a ? b : c`</span><span class="sxs-lookup"><span data-stu-id="dbb1f-108">Ternary operator: `a ? b : c`</span></span>
  - <span data-ttu-id="dbb1f-109">パイプライン チェーン演算子: `||` と `&&`</span><span class="sxs-lookup"><span data-stu-id="dbb1f-109">Pipeline chain operators: `||` and `&&`</span></span>
  - <span data-ttu-id="dbb1f-110">null 条件演算: `??` と `??=`</span><span class="sxs-lookup"><span data-stu-id="dbb1f-110">Null conditional operators: `??` and `??=`</span></span>
- <span data-ttu-id="dbb1f-111">簡略化された動的エラー ビューと `Get-Error` コマンドレット。エラーの調査が容易になります</span><span class="sxs-lookup"><span data-stu-id="dbb1f-111">A simplified and dynamic error view and `Get-Error` cmdlet for easier investigation of errors</span></span>
- <span data-ttu-id="dbb1f-112">暗黙的な Windows PowerShell セッションでのユーザーによるモジュール インポートを可能にする互換性レイヤー</span><span class="sxs-lookup"><span data-stu-id="dbb1f-112">A compatibility layer that enables users to import modules in an implicit Windows PowerShell session</span></span>
- <span data-ttu-id="dbb1f-113">新しいバージョンの自動通知</span><span class="sxs-lookup"><span data-stu-id="dbb1f-113">Automatic new version notifications</span></span>
- <span data-ttu-id="dbb1f-114">PowerShell 7 からの DSC リソースの自動呼び出し機能 (試験段階)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-114">The ability to invoke DSC resources directly from PowerShell 7 (experimental)</span></span>

<span data-ttu-id="dbb1f-115">機能と修正プログラムの完全な一覧については、[変更ログ](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.0.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-115">To see a full list of features and fixes, see the [changelogs](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.0.md).</span></span>

## <a name="where-can-i-install-powershell"></a><span data-ttu-id="dbb1f-116">PowerShell をインストールできる場所</span><span class="sxs-lookup"><span data-stu-id="dbb1f-116">Where can I install PowerShell?</span></span>

<span data-ttu-id="dbb1f-117">現在 PowerShell 7 では、x64 上で次のオペレーティング システムがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-117">PowerShell 7 currently supports the following operating systems on x64, including:</span></span>

- <span data-ttu-id="dbb1f-118">Windows 8.1、10</span><span class="sxs-lookup"><span data-stu-id="dbb1f-118">Windows 8.1, and 10</span></span>
- <span data-ttu-id="dbb1f-119">Windows Server 2012、2012 R2、2016、2019</span><span class="sxs-lookup"><span data-stu-id="dbb1f-119">Windows Server 2012, 2012 R2, 2016, and 2019</span></span>
- <span data-ttu-id="dbb1f-120">macOS 10.13 以降</span><span class="sxs-lookup"><span data-stu-id="dbb1f-120">macOS 10.13+</span></span>
- <span data-ttu-id="dbb1f-121">Red Hat Enterprise Linux (RHEL)/CentOS 7</span><span class="sxs-lookup"><span data-stu-id="dbb1f-121">Red Hat Enterprise Linux (RHEL) / CentOS 7</span></span>
- <span data-ttu-id="dbb1f-122">Fedora 30 以降</span><span class="sxs-lookup"><span data-stu-id="dbb1f-122">Fedora 30+</span></span>
- <span data-ttu-id="dbb1f-123">Debian 9</span><span class="sxs-lookup"><span data-stu-id="dbb1f-123">Debian 9</span></span>
- <span data-ttu-id="dbb1f-124">Ubuntu LTS 16.04 以降</span><span class="sxs-lookup"><span data-stu-id="dbb1f-124">Ubuntu LTS 16.04+</span></span>
- <span data-ttu-id="dbb1f-125">Alpine Linux 3.8 以降</span><span class="sxs-lookup"><span data-stu-id="dbb1f-125">Alpine Linux 3.8+</span></span>

<span data-ttu-id="dbb1f-126">さらに、PowerShell 7.0 では、Debian、Ubuntu、ARM64 Alpine Linux の ARM32 および ARM64 フレーバーもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-126">Additionally, PowerShell 7.0 supports ARM32 and ARM64 flavors of Debian, Ubuntu, and ARM64 Alpine Linux.</span></span>

<span data-ttu-id="dbb1f-127">お使いのオペレーティング システム [Windows](/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7)、[macOS](/powershell/scripting/install/installing-powershell-core-on-macos?view=powershell-7)、または [Linux](/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7) のインストール手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-127">Check the installation instructions for your preferred operating system [Windows](/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7), [macOS](/powershell/scripting/install/installing-powershell-core-on-macos?view=powershell-7), or [Linux](/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7).</span></span>

<span data-ttu-id="dbb1f-128">公式にはサポートされていませんが、コミュニティでは、[Arch](https://aur.archlinux.org/packages/powershell/) および Kali Linux 用のパッケージも提供しています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-128">While not officially supported, the community has also provided packages for [Arch](https://aur.archlinux.org/packages/powershell/) and Kali Linux.</span></span>

> [!NOTE]
> <span data-ttu-id="dbb1f-129">現在、Debian 10 および CentOS 8 では、WinRM リモート処理はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-129">Debian 10 and CentOS 8 currently do not support WinRM remoting.</span></span> <span data-ttu-id="dbb1f-130">SSH ベースのリモート処理設定の詳細については、「[SSH 経由の PowerShell リモート処理](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-130">For details on setting up SSH-based remoting, see [PowerShell Remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core?view=powershell-7).</span></span>

<span data-ttu-id="dbb1f-131">サポートされているオペレーティング システムとサポート ライフサイクルの最新情報については、[PowerShell サポート ライフサイクル](/powershell/scripting/powershell-support-lifecycle?view=powershell-7)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-131">For more up-to-date information about supported operating systems and support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle?view=powershell-7).</span></span>

## <a name="running-powershell-7"></a><span data-ttu-id="dbb1f-132">PowerShell 7 の実行</span><span class="sxs-lookup"><span data-stu-id="dbb1f-132">Running PowerShell 7</span></span>

<span data-ttu-id="dbb1f-133">PowerShell 7 は新しいディレクトリにインストールされ、Windows PowerShell 5.1 と side-by-side 実行されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-133">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="dbb1f-134">PowerShell Core 6.x の場合、PowerShell 7 インプレース アップグレードで、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-134">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>

- <span data-ttu-id="dbb1f-135">PowerShell 7 は `%programfiles%\PowerShell\7` にインストールされます</span><span class="sxs-lookup"><span data-stu-id="dbb1f-135">PowerShell 7 is installed to `%programfiles%\PowerShell\7`</span></span>
- <span data-ttu-id="dbb1f-136">`%programfiles%\PowerShell\7` フォルダーは `$env:PATH` に追加されます</span><span class="sxs-lookup"><span data-stu-id="dbb1f-136">The `%programfiles%\PowerShell\7` folder is added to `$env:PATH`</span></span>

<span data-ttu-id="dbb1f-137">PowerShell 7 インストーラー パッケージにより、以前のバージョンの PowerShell Core 6.x がアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-137">The PowerShell 7 installer packages upgrade previous versions of PowerShell Core 6.x:</span></span>

- <span data-ttu-id="dbb1f-138">Windows 上の PowerShell Core 6.x: `%programfiles%\PowerShell\6` が `%programfiles%\PowerShell\7` に置き換えられます</span><span class="sxs-lookup"><span data-stu-id="dbb1f-138">PowerShell Core 6.x on Windows: `%programfiles%\PowerShell\6` is replaced by `%programfiles%\PowerShell\7`</span></span>
- <span data-ttu-id="dbb1f-139">Linux: `/opt/microsoft/powershell/6` が `/opt/microsoft/powershell/7` に置き換えられます</span><span class="sxs-lookup"><span data-stu-id="dbb1f-139">Linux: `/opt/microsoft/powershell/6` is replaced by `/opt/microsoft/powershell/7`</span></span>
- <span data-ttu-id="dbb1f-140">macOS: `/usr/local/microsoft/powershell/6` が `/usr/local/microsoft/powershell/7` に置き換えられます</span><span class="sxs-lookup"><span data-stu-id="dbb1f-140">macOS: `/usr/local/microsoft/powershell/6` is replaced by `/usr/local/microsoft/powershell/7`</span></span>

> [!NOTE]
> <span data-ttu-id="dbb1f-141">Windows PowerShell では、PowerShell を起動する実行可能ファイルには `powershell.exe` という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-141">In Windows PowerShell, the executable to launch PowerShell is named `powershell.exe`.</span></span> <span data-ttu-id="dbb1f-142">バージョン 6 以降、この実行可能ファイルは、side-by-side 実行をサポートするように変更されています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-142">In version 6 and above, the executable is changed to support side-by-side execution.</span></span> <span data-ttu-id="dbb1f-143">PowerShell 7 を起動する新しい実行可能ファイルは `pwsh.exe` です。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-143">The new executable to launch PowerShell 7 is `pwsh.exe`.</span></span> <span data-ttu-id="dbb1f-144">プレビュー ビルドは、7-preview ディレクトリで `pwsh` ではなく `pwsh-preview` としてインプレースのままです。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-144">Preview builds will remain in-place as `pwsh-preview` instead of `pwsh` under the 7-preview directory.</span></span>

## <a name="improved-backwards-compatibility-with-windows-powershell"></a><span data-ttu-id="dbb1f-145">Windows PowerShell との下位互換性の向上</span><span class="sxs-lookup"><span data-stu-id="dbb1f-145">Improved backwards compatibility with Windows PowerShell</span></span>

<span data-ttu-id="dbb1f-146">PowerShell 7.0 では .NET Core 3.1 への移行がマークされ、既存の Windows PowerShell モジュールとの下位互換性が大幅に向上しています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-146">PowerShell 7.0 marks a move a to .NET Core 3.1, enabling significantly more backwards compatibility with existing Windows PowerShell modules.</span></span> <span data-ttu-id="dbb1f-147">これには、`Out-GridView`、`Show-Command` などの GUI 機能を必要とする Windows 上の多くのモジュール、および Windows の一部として出荷される多くの役割管理モジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-147">This includes many modules on Windows that require GUI functionality like `Out-GridView` and `Show-Command`, as well as many role management modules that ship as part of Windows.</span></span>

<span data-ttu-id="dbb1f-148">Windows の場合、新しいスイッチ パラメーター **UseWindowsPowerShell** が `Import-Module` に追加されています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-148">For Windows, a new switch parameter **UseWindowsPowerShell** is added to `Import-Module`.</span></span> <span data-ttu-id="dbb1f-149">このスイッチにより、PowerShell 7 にプロキシ モジュールが作成されます。このモジュールは、ローカルの Windows PowerShell プロセスを使用して、そのモジュールに含まれる任意のコマンドレットを暗黙的に実行します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-149">This switch creates a proxy module in PowerShell 7 that uses a local Windows PowerShell process to implicitly run any cmdlets contained in that module.</span></span> <span data-ttu-id="dbb1f-150">詳細については、「[Import-Module](/powershell/module/microsoft.powershell.core/import-module?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-150">For more information on [Import-Module](/powershell/module/microsoft.powershell.core/import-module?view=powershell-7).</span></span>

<span data-ttu-id="dbb1f-151">PowerShell 7.0 で動作する Microsoft モジュールの詳細については、[モジュールの互換性に関する表](https://aka.ms/PSModuleCompat)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-151">For more information on which Microsoft modules work with PowerShell 7.0, see the [Module Compatibility Table](https://aka.ms/PSModuleCompat).</span></span>

## <a name="parallel-execution-added-to-foreach-object"></a><span data-ttu-id="dbb1f-152">ForEach-Object に追加された並列実行</span><span class="sxs-lookup"><span data-stu-id="dbb1f-152">Parallel execution added to ForEach-Object</span></span>

<span data-ttu-id="dbb1f-153">コレクション内の項目を反復する `ForEach-Object` コマンドレットに、新しい **Parallel** パラメーターを持つ組み込みの並列処理が追加されました。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-153">The `ForEach-Object` cmdlet, which iterates items in a collection, now has built-in parallelism with the new **Parallel** parameter.</span></span>

<span data-ttu-id="dbb1f-154">既定では、並列スクリプト ブロックは、並列タスクを開始した呼び出し元の現在の作業ディレクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-154">By default, parallel script blocks use the current working directory of the caller that started the parallel tasks.</span></span>

<span data-ttu-id="dbb1f-155">この例は、ローカルの Windows マシンで、5 つのシステム ログから 50,000 個のログ エントリを取得しています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-155">This example retrieves 50,000 log entries from 5 system logs on a local Windows machine:</span></span>

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count

50000
```

<span data-ttu-id="dbb1f-156">**Parallel** パラメーターは、入力ログ名ごとに並列実行されるスクリプト ブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-156">The **Parallel** parameter specifies the script block that is run in parallel for each input log name.</span></span>

<span data-ttu-id="dbb1f-157">新しい **ThrottleLimit** パラメーターによって、指定した時間に並列実行されるスクリプト ブロックの数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-157">The new **ThrottleLimit** parameter limits the number of script blocks running in parallel at a given time.</span></span> <span data-ttu-id="dbb1f-158">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-158">The default is 5.</span></span>

<span data-ttu-id="dbb1f-159">`$_` 変数を使用して、スクリプト ブロックで現在の入力オブジェクトを表すします。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-159">Use the `$_` variable to represent the current input object in the script block.</span></span> <span data-ttu-id="dbb1f-160">`$using:` スコープを使用して、変数参照を実行中のスクリプト ブロックに渡します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-160">Use the `$using:` scope to pass variable references to the running script block.</span></span>

<span data-ttu-id="dbb1f-161">詳細については、「[ForEach-Object](/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-161">For more information about [ForEach-Object](/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7).</span></span>

## <a name="ternary-operator"></a><span data-ttu-id="dbb1f-162">三項演算子</span><span class="sxs-lookup"><span data-stu-id="dbb1f-162">Ternary operator</span></span>

<span data-ttu-id="dbb1f-163">PowerShell 7.0 には、簡略化された `if-else` ステートメントのように動作する三項演算子が導入されています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-163">PowerShell 7.0 introduces a ternary operator which behaves like a simplified `if-else` statement.</span></span>
<span data-ttu-id="dbb1f-164">PowerShell の三項演算子は、C# 三項演算子構文に基づく類似のモデルです。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-164">PowerShell's ternary operator is closely modeled from the C# ternary operator syntax:</span></span>

```
<condition> ? <if-true> : <if-false>
```

<span data-ttu-id="dbb1f-165">常に条件式が評価され、その結果は、次の評価対象となる分岐を判断するために**ブール値**に変換されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-165">The condition-expression is always evaluated and its result converted to a **Boolean** to determine which branch is evaluated next:</span></span>

- <span data-ttu-id="dbb1f-166">`<if-true>` 式は、`<condition>` 式が true の場合に実行されます</span><span class="sxs-lookup"><span data-stu-id="dbb1f-166">The `<if-true>` expression is executed if the `<condition>` expression is true</span></span>
- <span data-ttu-id="dbb1f-167">`<if-false>` 式は、`<condition>` 式が false の場合に実行されます</span><span class="sxs-lookup"><span data-stu-id="dbb1f-167">The `<if-false>` expression is executed if the `<condition>` expression is false</span></span>

<span data-ttu-id="dbb1f-168">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-168">For example:</span></span>

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

<span data-ttu-id="dbb1f-169">この例では、パスが存在すると、**Path exists** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-169">In this example, if the path exists, then **Path exists** is displayed.</span></span> <span data-ttu-id="dbb1f-170">パスが存在しない場合は、**Path not found** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-170">If the path does not exist, then **Path not found** is displayed.</span></span>

<span data-ttu-id="dbb1f-171">詳細については、「[About If](/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-171">For more information [About If](/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7).</span></span>

## <a name="pipeline-chain-operators"></a><span data-ttu-id="dbb1f-172">パイプライン チェーン演算子</span><span class="sxs-lookup"><span data-stu-id="dbb1f-172">Pipeline chain operators</span></span>

<span data-ttu-id="dbb1f-173">PowerShell 7 では、`&&` 演算子と `||` 演算子が実装され、条件に応じてパイプラインがチェーンされます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-173">PowerShell 7 implements the `&&` and `||` operators to conditionally chain pipelines.</span></span> <span data-ttu-id="dbb1f-174">これらの演算子は、PowerShell では "パイプライン チェーン演算子" として知られ、**Bash**、**Zsh** などのシェルにある AND リストと OR リスト、および Windows コマンド シェル (**cmd.exe**) の条件付き処理シンボルと似ています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-174">These operators are known in PowerShell as "pipeline chain operators", and are similar to AND and OR lists in shells like **Bash** and **Zsh**, as well as conditional processing symbols in the Windows Command Shell (**cmd.exe**).</span></span>

<span data-ttu-id="dbb1f-175">`&&` 演算子では、左側のパイプラインが成功した場合に、右側のパイプラインが実行されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-175">The `&&` operator executes the right-hand pipeline, if the left-hand pipeline succeeded.</span></span> <span data-ttu-id="dbb1f-176">反対に、`||` 演算子では、左側のパイプラインが失敗した場合に、右側のパイプラインが実行されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-176">Conversely, the `||` operator executes the right-hand pipeline if the left-hand pipeline failed.</span></span>

> [!NOTE]
> <span data-ttu-id="dbb1f-177">これらの演算子では `$?` 変数と `$LASTEXITCODE` の変数を使用して、パイプラインが失敗したかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-177">These operators use the `$?` and `$LASTEXITCODE` variables to determine if a pipeline failed.</span></span> <span data-ttu-id="dbb1f-178">これにより、コマンドレットや関数だけでなく、ネイティブ コマンドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-178">This allows you to use them with native commands and not just with cmdlets or functions.</span></span>

<span data-ttu-id="dbb1f-179">次の場合、最初のコマンドは成功し、2 番目のコマンドは実行されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-179">Here, the first command succeeds and the second command is executed:</span></span>

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

<span data-ttu-id="dbb1f-180">次の場合、最初のコマンドは失敗し、2 番目のコマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-180">Here, the first command fails, the second is not executed:</span></span>

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

<span data-ttu-id="dbb1f-181">次の場合、最初のコマンドは成功し、2 番目のコマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-181">Here, the first command succeeds, the second command is not executed:</span></span>

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

<span data-ttu-id="dbb1f-182">次の場合、最初のコマンドは失敗し、2 番目のコマンドは実行されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-182">Here, the first command fails, so the second command is executed:</span></span>

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error 'Bad'
Second
```

<span data-ttu-id="dbb1f-183">詳細については、「[パイプライン チェーン演算子の概要](/powershell/module/microsoft.powershell.core/about/about_pipeline_chain_operators?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-183">For more information [About Pipeline Chain Operators](/powershell/module/microsoft.powershell.core/about/about_pipeline_chain_operators?view=powershell-7).</span></span>

## <a name="null-coalescing-assignment-and-conditional-operators"></a><span data-ttu-id="dbb1f-184">null 合体演算子、代入演算子、および条件演算子</span><span class="sxs-lookup"><span data-stu-id="dbb1f-184">Null-coalescing, assignment, and conditional operators</span></span>

<span data-ttu-id="dbb1f-185">PowerShell 7 には、null 合体演算子 `??`、null 条件付き代入演算子 `??=`、および null 条件メンバー アクセス演算子 `?.` および `?[]` があります。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-185">PowerShell 7 includes Null coalescing operator `??`, Null conditional assignment `??=`, and Null conditional member access operators `?.` and `?[]`.</span></span>

### <a name="null-coalescing-operator-"></a><span data-ttu-id="dbb1f-186">null 合体演算子 ??</span><span class="sxs-lookup"><span data-stu-id="dbb1f-186">Null-coalescing Operator ??</span></span>

<span data-ttu-id="dbb1f-187">null 合体演算子 `??` は、左側のオペランドが null でない場合に、左側のオペランドの値を返します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-187">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't null.</span></span>
<span data-ttu-id="dbb1f-188">それ以外の場合は、右側のオペランドを評価し、その結果を返します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-188">Otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="dbb1f-189">左側のオペランドが null 以外に評価された場合、`??` 演算子は右側のオペランドを評価しません。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-189">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ?? 100
100
```

<span data-ttu-id="dbb1f-190">次の例では、右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-190">In the following example, the right-hand operand won't be evaluated:</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-assignment-operator-"></a><span data-ttu-id="dbb1f-191">null 条件付き代入演算子 ??=</span><span class="sxs-lookup"><span data-stu-id="dbb1f-191">Null conditional assignment operator ??=</span></span>

<span data-ttu-id="dbb1f-192">null 条件付き代入演算子 `??=` は、左側のオペランドが null と評価された場合にのみ、右側のオペランドの値を左側のオペランドに代入します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-192">The null conditional assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to null.</span></span> <span data-ttu-id="dbb1f-193">左側のオペランドが null 以外に評価された場合、`??=` 演算子は右側のオペランドを評価しません。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-193">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ??= 100
$x
100
```

<span data-ttu-id="dbb1f-194">次の例では、右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-194">In the following example, the right-hand operand won't be evaluated:</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-member-access-operators--and--experimental"></a><span data-ttu-id="dbb1f-195">null 条件付きメンバー アクセス演算子 ?.</span><span class="sxs-lookup"><span data-stu-id="dbb1f-195">Null conditional member access operators ?.</span></span> <span data-ttu-id="dbb1f-196">および ?[] (試験段階)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-196">and ?[] (Experimental)</span></span>

> [!NOTE]
> <span data-ttu-id="dbb1f-197">これは **PSNullConditionalOperators** という試験的な機能です。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-197">This is an experimental feature named **PSNullConditionalOperators**.</span></span> <span data-ttu-id="dbb1f-198">詳細については、[試験的な機能](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-198">Learn more [About Experimental Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span></span>

<span data-ttu-id="dbb1f-199">null 条件演算子は、そのオペランドが null 以外に評価される場合にのみ、メンバー アクセス `?.`、または要素アクセス `?[]` をそのオペランドに許可します。それ以外の場合は、null を返します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-199">A null conditional operator permits member access, `?.`, or element access, `?[]`, to its operand only if that operand evaluates to non-null; otherwise, it returns null.</span></span>

> [!NOTE]
> <span data-ttu-id="dbb1f-200">PowerShell では、変数名の一部として `?` が許可されるため、これらの演算子を使用するには、変数名の正式な仕様が必要です。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-200">Since PowerShell allows `?` to be part of the variable name, formal specification of the variable name is required for using these operators.</span></span> <span data-ttu-id="dbb1f-201">したがって、変数名は、`${a}` や、`?` が変数名 `${a?}` に含まれる場合のように、`{}` で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-201">So it is required to use `{}` around the variable names like `${a}` or when `?` is part of the variable name `${a?}`.</span></span>

<span data-ttu-id="dbb1f-202">次の例では、メンバー プロパティ **Status** の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-202">In the following example, the value of the member property **Status** is returned:</span></span>

```powershell
$Service = Get-Service -Name 'bits'
${Service}?.status
Stopped
```

<span data-ttu-id="dbb1f-203">次の例では、メンバー名 **Status** へのアクセスを試みずに、null が返されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-203">The following example will return null, without trying to access the member name **Status**:</span></span>

```powershell
$service = $Null
${Service}?.status
```

<span data-ttu-id="dbb1f-204">同様に、`?[]` を使用すると、要素の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-204">Similarly, using `?[]`, the value of the element will be returned:</span></span>

```powershell
$a = 1..10
${a}?[0]
1
```

<span data-ttu-id="dbb1f-205">オペランドが null の場合、要素にはアクセスされず、null が返されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-205">And when the operand is null, the element isn't accessed and null is returned:</span></span>

```powershell
$a = $null
${a}?[0]
```

<span data-ttu-id="dbb1f-206">詳細については、「[About_Operators](/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-206">For more information [About_Operators](/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7).</span></span>

## <a name="new-view-conciseview-and-cmdlet-get-error"></a><span data-ttu-id="dbb1f-207">新しい ConciseView ビューと Get-Error コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dbb1f-207">New view ConciseView and cmdlet Get-Error</span></span>

<span data-ttu-id="dbb1f-208">エラー メッセージの表示が改善され、対話型エラーとスクリプト エラーの読みやすさが向上し、新しい既定のビュー **ConciseView** を利用できます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-208">The display of error messages has been improved to enhance the readability of interactive and script errors with a new default view **ConciseView**.</span></span> <span data-ttu-id="dbb1f-209">ビューは、ユーザー設定変数 `$ErrorView` を使用してユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-209">The views are user-selectable through the preference variable `$ErrorView`.</span></span>

<span data-ttu-id="dbb1f-210">**ConciseView** を使用すると、スクリプトのエラーまたはパーサー エラーでない場合、エラー メッセージは 1 行になります。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-210">With **ConciseView**, if an error is not from a script or parser error, then it's a single line error message:</span></span>

```powershell
Get-Childitem -Path c:\NotReal
```

```Output
Get-ChildItem: Cannot find path 'C:\NotReal' because it does not exist
```

<span data-ttu-id="dbb1f-211">スクリプトの実行中にエラーが発生した場合、または解析エラーの場合は、PowerShell によって複数行のエラー メッセージが返されます。そのエラー メッセージには、エラー、ポインター、およびエラーの場所を示すエラー メッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-211">If the error occurs during script execution or is a parsing error, PowerShell returns a multiline error message that contains the error, a pointer and error message showing where the error is in that line.</span></span> <span data-ttu-id="dbb1f-212">ターミナルで ANSI カラー エスケープ シーケンス (VT100) がサポートされていない場合、色は表示されません。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-212">If the terminal doesn't support ANSI color escape sequences (VT100), then colors are not displayed.</span></span>

![スクリプトからのエラー表示](./media/What-s-New-in-PowerShell-70/myscript-error.png)

<span data-ttu-id="dbb1f-214">PowerShell 7 の既定のビューは **ConciseView** です。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-214">The default view in PowerShell 7 is **ConciseView**.</span></span> <span data-ttu-id="dbb1f-215">前の既定のビューは **NormalView** で、ユーザー設定変数 `$ErrorView` を設定して、ユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-215">The previous default view was **NormalView** and is user selectable by setting the preference variable `$ErrorView`.</span></span>

```powershell
$ErrorView = 'NormalView' # Sets the error view to NormalView
$ErrorView = 'ConciseView' # Sets the error view to ConciseView
```

> [!NOTE]
> <span data-ttu-id="dbb1f-216">エラー メッセージのアクセント カラーの変更をサポートするために、新しいプロパティ **ErrorAccentColor** が `$Host.PrivateData` に追加されています。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-216">A new property **ErrorAccentColor** is added to `$Host.PrivateData` to support changing the accent color of the error message.</span></span>

<span data-ttu-id="dbb1f-217">新しいコマンドレット `Get-Error` は、必要に応じて、完全修飾エラーの完全な詳細ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-217">A new cmdlet `Get-Error` provides complete detailed view of the fully qualified error when desired.</span></span>
<span data-ttu-id="dbb1f-218">既定では、このコマンドレットによって、最後に発生したエラーの詳細 (内部例外を含む) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-218">By default the cmdlet displays the full details, including inner exceptions, of the last error that occurred.</span></span>

![Get-Error からの表示](./media/What-s-New-in-PowerShell-70/myscript-geterror.png)

<span data-ttu-id="dbb1f-220">`Get-Error` コマンドレットは、組み込み変数 `$Error` を使用して、パイプラインからの入力をサポートします。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-220">The `Get-Error` cmdlet supports input from the pipeline using the built-in variable `$Error`.</span></span>
<span data-ttu-id="dbb1f-221">`Get-Error` によって、パイプ処理されたすべてのエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-221">`Get-Error` displays all piped errors.</span></span>

```powershell
$Error | Get-Error
```

<span data-ttu-id="dbb1f-222">`Get-Error` コマンドレットでは、**最新**のパラメーターがサポートされているため、現在のセッションから表示するエラーの数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-222">The `Get-Error` cmdlet supports the **Newest** parameter, allowing you to specify how many errors from the current session you wish displayed.</span></span>

```powershell
Get-Error -Newest 3 # Displays the lst three errors that occurred in the session
```

<span data-ttu-id="dbb1f-223">詳細については、「[Get-Error](/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-223">For more information about [Get-Error](/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7).</span></span>

## <a name="new-version-notification"></a><span data-ttu-id="dbb1f-224">新しいバージョンの通知</span><span class="sxs-lookup"><span data-stu-id="dbb1f-224">New version notification</span></span>

<span data-ttu-id="dbb1f-225">PowerShell 7 では、更新通知を使用して、PowerShell に更新プログラムがあることをユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-225">PowerShell 7 uses update notifications to alert users to the existence of updates to PowerShell.</span></span>
<span data-ttu-id="dbb1f-226">PowerShell は、新しいバージョンが利用可能かどうかを、1 日に 1 回オンライン サービスに問い合わせます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-226">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="dbb1f-227">更新チェックは、指定した 24 時間の期間の最初のセッション中に実行されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-227">The update check happens during the first session in a given 24-hour period.</span></span> <span data-ttu-id="dbb1f-228">パフォーマンス上の理由から、更新チェックはセッションが開始してから 3 秒後に開始されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-228">For performance reasons, the update check starts 3 seconds after the session begins.</span></span> <span data-ttu-id="dbb1f-229">通知は、以降のセッションの開始時にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-229">The notification is shown only on the start of subsequent sessions.</span></span>

<span data-ttu-id="dbb1f-230">既定では、PowerShell は、そのバージョン/分岐に応じて、2 つの異なる通知チャネルのいずれかをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-230">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="dbb1f-231">サポートされている一般公開 (GA) バージョンの PowerShell では、更新された GA リリースの通知のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-231">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="dbb1f-232">プレビューおよびリリース候補 (RC) リリースでは、プレビュー、RC、GA リリースに対する更新プログラムが通知されます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-232">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="dbb1f-233">更新通知動作は、`$Env:POWERSHELL_UPDATECHECK` 環境変数を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-233">The update notification behavior can be changed using the `$Env:POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="dbb1f-234">サポートされている値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-234">The following values are supported:</span></span>

- <span data-ttu-id="dbb1f-235">**Default** は、`$Env:POWERSHELL_UPDATECHECK` を定義しない場合と同じです</span><span class="sxs-lookup"><span data-stu-id="dbb1f-235">**Default** is the same as not defining `$Env:POWERSHELL_UPDATECHECK`</span></span>
  - <span data-ttu-id="dbb1f-236">GA リリースでは、GA リリースに対する更新プログラムが通知されます</span><span class="sxs-lookup"><span data-stu-id="dbb1f-236">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="dbb1f-237">プレビュー/RC リリースでは、GA およびプレビュー リリースに対する更新プログラムが通知されます</span><span class="sxs-lookup"><span data-stu-id="dbb1f-237">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="dbb1f-238">**Off** により、更新通知機能が無効になります</span><span class="sxs-lookup"><span data-stu-id="dbb1f-238">**Off** turns off the update notification feature</span></span>
- <span data-ttu-id="dbb1f-239">**LTS** は、長期サービス (LTS) GA リリースの更新についてのみ通知します</span><span class="sxs-lookup"><span data-stu-id="dbb1f-239">**LTS** only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

> [!NOTE]
> <span data-ttu-id="dbb1f-240">環境変数 `$Env:POWERSHELL_UPDATECHECK` は、最初に設定されるまで存在しません。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-240">The environment variable `$Env:POWERSHELL_UPDATECHECK` does not exist until it is set for the first time.</span></span>

<span data-ttu-id="dbb1f-241">`LTS` リリースについてのみバージョン通知を設定するには:</span><span class="sxs-lookup"><span data-stu-id="dbb1f-241">To set the version notification for `LTS` releases only:</span></span>

```powershell
$Env:POWERSHELL_UPDATECHECK = 'LTS'
```

<span data-ttu-id="dbb1f-242">バージョン通知を `Default` 動作に設定するには:</span><span class="sxs-lookup"><span data-stu-id="dbb1f-242">To set the version notification to the `Default` behavior:</span></span>

```powershell
$Env:POWERSHELL_UPDATECHECK = 'Default'
```

<span data-ttu-id="dbb1f-243">詳細については、「[更新通知](/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-243">For more information [About Update Notifications](/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7).</span></span>

## <a name="new-dsc-resource-support-with-invoke-dscresource-experimental"></a><span data-ttu-id="dbb1f-244">Invoke-DSCResource を使用した新しい DSC リソースのサポート (試験段階)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-244">New DSC Resource support with Invoke-DSCResource (Experimental)</span></span>

> [!NOTE]
> <span data-ttu-id="dbb1f-245">これは **PSDesiredStateConfiguration.InvokeDscResource** という試験的な機能です。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-245">This is an experimental feature named **PSDesiredStateConfiguration.InvokeDscResource**.</span></span> <span data-ttu-id="dbb1f-246">詳細については、[試験的な機能](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-246">Learn more [About Experimental Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7).</span></span>

<span data-ttu-id="dbb1f-247">`Invoke-DscResource` コマンドレットは、指定された PowerShell Desired State Configuration (DSC) リソースのメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-247">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="dbb1f-248">このコマンドレットは、構成ドキュメントを作成せずに、DSC リソースを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-248">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="dbb1f-249">このコマンドレットを使用すると、構成管理製品で DSC リソースを使って Windows または Linux を管理できます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-249">Using this cmdlet, configuration management products can manage Windows or Linux by using DSC resources.</span></span> <span data-ttu-id="dbb1f-250">DSC エンジンの実行中、デバッグが有効になっている場合は、このコマンドレットでリソースのデバッグを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-250">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

<span data-ttu-id="dbb1f-251">このコマンドは、Log という名前のリソースの **Set** メソッドを呼び出して、**Message** プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-251">This command invokes the **Set** method of a resource named Log and specifies a **Message** property.</span></span>

```powershell
Invoke-DscResource -Name Log -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Message = 'Hello World'
}
```

<span data-ttu-id="dbb1f-252">詳細については、「[Invoke-DSCResource](/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb1f-252">For more information about [Invoke-DSCResource](/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7).</span></span>

## <a name="breaking-changes-and-improvements"></a><span data-ttu-id="dbb1f-253">破壊的変更と機能強化</span><span class="sxs-lookup"><span data-stu-id="dbb1f-253">Breaking Changes and Improvements</span></span>

### <a name="breaking-changes"></a><span data-ttu-id="dbb1f-254">重大な変更</span><span class="sxs-lookup"><span data-stu-id="dbb1f-254">Breaking Changes</span></span>

- <span data-ttu-id="dbb1f-255">更新通知での LTS と既定のチャネルをサポートを追加 (#11132)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-255">Make update notification support LTS and default channels (#11132)</span></span>
- <span data-ttu-id="dbb1f-256">Windows PowerShell の Test-Connection と同じように動作するよう Test-Connection を更新 (#10697) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-256">Update Test-Connection to work more like the one in Windows PowerShell (#10697) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="dbb1f-257">次の式に対して $? を保持:</span><span class="sxs-lookup"><span data-stu-id="dbb1f-257">Preserve $?</span></span> <span data-ttu-id="dbb1f-258">ParenExpression、SubExpression、および ArrayExpression (#11040)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-258">for ParenExpression, SubExpression and ArrayExpression (#11040)</span></span>
- <span data-ttu-id="dbb1f-259">作業ディレクトリを Start-Job の現在のディレクトリに設定 (#10920) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-259">Set working directory to current directory in Start-Job (#10920) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-260">$PSCulture にセッション内カルチャの変更を一貫して反映 (#10138) (@iSazonovに感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-260">Make $PSCulture consistently reflect in-session culture changes (#10138) (Thanks @iSazonov!)</span></span>

### <a name="engine-updates-and-fixes"></a><span data-ttu-id="dbb1f-261">エンジンの更新と修正</span><span class="sxs-lookup"><span data-stu-id="dbb1f-261">Engine Updates and Fixes</span></span>

- <span data-ttu-id="dbb1f-262">リモート シナリオのブレークポイント API の機能強化 (#11312)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-262">Improvements in breakpoint APIs for remote scenarios (#11312)</span></span>
- <span data-ttu-id="dbb1f-263">別の実行空間にリークしている PowerShell クラス定義を修正 (#11273)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-263">Fix PowerShell class definition leaking into another Runspace (#11273)</span></span>
- <span data-ttu-id="dbb1f-264">7\.0.0-Preview1 に追加された FirstOrDefault プリミティブによって発生する書式設定の回帰を修正 (#11258)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-264">Fix a regression in formatting caused by the FirstOrDefault primitive added in 7.0.0-Preview1 (#11258)</span></span>
- <span data-ttu-id="dbb1f-265">PS7 テレメトリで追跡する追加の Microsoft モジュール (#10751)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-265">Additional Microsoft Modules to track in PS7 Telemetry (#10751)</span></span>
- <span data-ttu-id="dbb1f-266">承認済み機能を試験的ではない機能として指定 (#11303)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-266">Make approved features non-experimental (#11303)</span></span>
- <span data-ttu-id="dbb1f-267">TargetObject を使用するように ConciseView を更新 (該当する場合) (#11075)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-267">Update ConciseView to use TargetObject if applicable (#11075)</span></span>
- <span data-ttu-id="dbb1f-268">CompletionCompleters パブリック メソッドの NullReferenceException を修正 (#11274)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-268">Fix NullReferenceException in CompletionCompleters public methods (#11274)</span></span>
- <span data-ttu-id="dbb1f-269">Windows 以外のプラットフォームでのアパートメント スレッド状態チェックを修正 (#11301)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-269">Fix apartment thread state check on non-Windows platforms (#11301)</span></span>
- <span data-ttu-id="dbb1f-270">プロセスとマシンの環境変数を連結するように設定 PSModulePath を更新 (#11276)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-270">Update setting PSModulePath to concatenate the process and machine environment variables (#11276)</span></span>
- <span data-ttu-id="dbb1f-271">.NET Core を 3.1.0 にバージョンアップ (#11260)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-271">Bump .NET Core to 3.1.0 (#11260)</span></span>
- <span data-ttu-id="dbb1f-272">$env:PATH の前にある $PSHOME の検出を修正 (#11141)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-272">Fix detection of $PSHOME in front of $env:PATH (#11141)</span></span>
- <span data-ttu-id="dbb1f-273">pwsh による $env:PSModulePath の継承を許可し、powershell.exe の適切な起動を実現 (#11057)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-273">Allow pwsh to inherit $env:PSModulePath and enable powershell.exe to start correctly (#11057)</span></span>
- <span data-ttu-id="dbb1f-274">.NET Core 3.1 プレビュー 1 への移行 (#10798)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-274">Move to .NET Core 3.1 preview 1 (#10798)</span></span>
- <span data-ttu-id="dbb1f-275">ファイル システムプロバイダーでの再解析タグ チェックをリファクター (#10431) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-275">Refactor reparse tag checks in file system provider (#10431) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-276">スクリプト ログ記録で CR と改行を 0x23CE 文字に置換 (#10616)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-276">Replace CR and new line with a 0x23CE character in script logging (#10616)</span></span>
- <span data-ttu-id="dbb1f-277">AppDomain.CurrentDomain.ProcessExit から イベントハンドラーの登録を解除して、リソース リークを修正 (#10626)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-277">Fix a resource leak by unregistering the event handler from AppDomain.CurrentDomain.ProcessExit (#10626)</span></span>
- <span data-ttu-id="dbb1f-278">ActionPreference.Break にサポートを追加して、デバッグ、エラー、情報、進行状況、詳細、または警告メッセージの生成時にデバッガーを起動 (#8205) (@KirkMunroに感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-278">Add support to ActionPreference.Break to break into debugger when Debug, Error, Information, Progress, Verbose or Warning messages are generated (#8205) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="dbb1f-279">CPL 拡張機能を指定せずに、PowerShell Core 内でコントロール パネルのアドイン起動を有効化</span><span class="sxs-lookup"><span data-stu-id="dbb1f-279">Enable starting control panel add-ins within PowerShell Core without specifying .CPL extension.</span></span> <span data-ttu-id="dbb1f-280">(#9828)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-280">(#9828)</span></span>

### <a name="general-cmdlet-updates-and-fixes"></a><span data-ttu-id="dbb1f-281">一般的なコマンドレットの更新と修正</span><span class="sxs-lookup"><span data-stu-id="dbb1f-281">General Cmdlet Updates and Fixes</span></span>

- <span data-ttu-id="dbb1f-282">UnixStat の試験的な機能のファイル変更日を設定するための Raspbian に関する問題を修正(#11313)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-282">Fix for issue on Raspbian for setting date of file changes in UnixStat Experimental Feature (#11313)</span></span>
- <span data-ttu-id="dbb1f-283">-AsPlainText を ConvertFrom-SecureString に追加 (#11142)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-283">Add -AsPlainText to ConvertFrom-SecureString (#11142)</span></span>
- <span data-ttu-id="dbb1f-284">WinCompat の WindowsPS バージョン チェックを追加 (#11148)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-284">Added WindowsPS version check for WinCompat (#11148)</span></span>
- <span data-ttu-id="dbb1f-285">一部の WinCompat シナリオでのエラー報告を修正 (#11259)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-285">Fix error-reporting in some WinCompat scenarios (#11259)</span></span>
- <span data-ttu-id="dbb1f-286">ネイティブ バイナリ リゾルバー (#11032) を追加 (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-286">Add native binary resolver (#11032) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-287">CJK 文字が正しく考慮されるよう文字幅の計算を更新 (#11262)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-287">Update calculation of char width to respect CJK chars correctly (#11262)</span></span>
- <span data-ttu-id="dbb1f-288">macOS 用の Unblock-File を追加 (#11137)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-288">Add Unblock-File for macOS (#11137)</span></span>
- <span data-ttu-id="dbb1f-289">Get-PSCallStack の回帰を修正 (#11210) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-289">Fix regression in Get-PSCallStack (#11210) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-290">Job コマンドレットを使用しているときの ScheduledJob モジュールの自動読み込みを削除 (#11194)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-290">Remove autoloading of the ScheduledJob module when using Job cmdlets (#11194)</span></span>
- <span data-ttu-id="dbb1f-291">OutputType を Get-Error コマンドレットに追加し、元の typenames を保持 (#10856)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-291">Add OutputType to Get-Error cmdlet and preserve original typenames (#10856)</span></span>
- <span data-ttu-id="dbb1f-292">SupportsVirtualTerminal プロパティの null 参照を修正 (#11105)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-292">Fix null reference in SupportsVirtualTerminal property (#11105)</span></span>
- <span data-ttu-id="dbb1f-293">Get-WinEvent (#10648) で制限チェックを追加 (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-293">Add limit check in Get-WinEvent (#10648) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-294">StopUpstreamCommandsException が -ErrorVariable に設定されないようにコマンド ランタイムを修正 (#10840)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-294">Fix command runtime so StopUpstreamCommandsException doesn't get populated in -ErrorVariable (#10840)</span></span>
- <span data-ttu-id="dbb1f-295">出力エンコードを、ネイティブ コマンド用の [Console]:: OutputEncoding に設定 (#10824)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-295">Set the output encoding to [Console]::OutputEncoding for native commands (#10824)</span></span>
- <span data-ttu-id="dbb1f-296">例で使用されている複数行のコード ブロックをサポート (#10776) (@Greg-Smulko に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-296">Support multi-line code blocks in examples (#10776) (Thanks @Greg-Smulko!)</span></span>
- <span data-ttu-id="dbb1f-297">Culture パラメーターを Select-String コマンドレットに追加 (#10943) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-297">Add Culture parameter to Select-String cmdlet (#10943) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-298">末尾に円記号が付いている Start-Job 作業ディレクトリ パスを修正 (#11041)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-298">Fix Start-Job working directory path with trailing backslash (#11041)</span></span>
- <span data-ttu-id="dbb1f-299">ConvertFrom-Json: 既定でコレクションの折り返しを解除 (#10861) (@danstur に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-299">ConvertFrom-Json: Unwrap collections by default (#10861) (Thanks @danstur!)</span></span>
- <span data-ttu-id="dbb1f-300">大文字と小文字を区別するハッシュテーブルを、CaseSensitive スイッチおよび -AsHashtable スイッチと共に Group-Object コマンドレットに対して使用 (#11030) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-300">Use case-sensitive Hashtable for Group-Object cmdlet with -CaseSensitive and -AsHashtable switches (#11030) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="dbb1f-301">大文字と小文字が正しく区別されるようにパスを再構築するとき、ファイル列挙が失敗した場合に例外を処理 (#11014)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-301">Handle exception if enumerating files fails when rebuilding path to have correct casing (#11014)</span></span>
- <span data-ttu-id="dbb1f-302">myCommand ではなく Activity が表示されるように ConciseView を修正 (#11007)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-302">Fix ConciseView to show Activity instead of myCommand (#11007)</span></span>
- <span data-ttu-id="dbb1f-303">Web コマンドレットが HTTP エラー状態を無視することを許可 (#10466) (@vdamewood に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-303">Allow web cmdlets to ignore HTTP error statuses (#10466) (Thanks @vdamewood!)</span></span>
- <span data-ttu-id="dbb1f-304">Get-Command に対する複数の CommandInfo のパイプ処理を修正 (#10929)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-304">Fix piping of more than one CommandInfo to Get-Command (#10929)</span></span>
- <span data-ttu-id="dbb1f-305">Windows 用 Get Counter コマンドレットを再度追加 (#10933)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-305">Add back Get-Counter cmdlet for Windows (#10933)</span></span>
- <span data-ttu-id="dbb1f-306">ConvertTo-Json が [AutomationNull]::Value と [NullString]::Value を $null として処理するように指定 (#10957)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-306">Make ConvertTo-Json treat [AutomationNull]::Value and [NullString]::Value as $null (#10957)</span></span>
- <span data-ttu-id="dbb1f-307">SSH リモート処理の ipv6 アドレスから角かっこを削除 (#10968)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-307">Remove brackets from ipv6 address for SSH remoting (#10968)</span></span>
- <span data-ttu-id="dbb1f-308">pwsh に送信されたコマンドが空白の場合に発生するクラッシュを修正 (#10977)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-308">Fix crash if command sent to pwsh is just whitespace (#10977)</span></span>
- <span data-ttu-id="dbb1f-309">クロスプラットフォームの Get-Clipboard と Set-Clipboard を追加 (#10340)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-309">Added cross-platform Get-Clipboard and Set-Clipboard (#10340)</span></span>
- <span data-ttu-id="dbb1f-310">ファイルシステム オブジェクトの元のパスに、余分な末尾のスラッシュが付かないように修正 (#10959)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-310">Fix setting original path of filesystem object to not have extra trailing slash (#10959)</span></span>
- <span data-ttu-id="dbb1f-311">ConvertTo-Json で $null をサポート (#10947)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-311">Support $null for ConvertTo-Json (#10947)</span></span>
- <span data-ttu-id="dbb1f-312">Windows で Out-Printer コマンドを再度追加 (#10906)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-312">Add back Out-Printer command on Windows (#10906)</span></span>
- <span data-ttu-id="dbb1f-313">空白が含まれる Start-Job -WorkingDirectory の開始を修正 (#10951)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-313">Fix Start-Job -WorkingDirectory with whitespace (#10951)</span></span>
- <span data-ttu-id="dbb1f-314">PSConfiguration.cs の設定に対して null を取得するときに既定値を返す (#10963) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-314">Return default value when getting null for a setting in PSConfiguration.cs (#10963) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-315">IO 例外を終了しない例外として処理 (#10950)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-315">Handle IO exception as non-terminating (#10950)</span></span>
- <span data-ttu-id="dbb1f-316">GraphicalHost アセンブリを追加して、Out-GridView、Show-Command、および Get-Help -ShowWindow を有効化 (#10899)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-316">Add GraphicalHost assembly to enable Out-GridView, Show-Command, and Get-Help -ShowWindow (#10899)</span></span>
- <span data-ttu-id="dbb1f-317">Get-HotFix のパイプラインを使用して ComputerName を取得 (#10852) (@kvprasoon に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-317">Take ComputerName via pipeline in Get-HotFix (#10852) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="dbb1f-318">共通パラメーターが使用可能として表示されるようにパラメーターのタブ補完を修正 (#10850)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-318">Fix tab completion for parameters so that it shows common parameters as available (#10850)</span></span>
- <span data-ttu-id="dbb1f-319">First() を呼び出す前に、システム ファイル エントリが返されていないかどうかを最初に確認するように GetCorrectCasedPath() を修正 (#10930)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-319">Fix GetCorrectCasedPath() to first check if any system file entries is returned before calling First() (#10930)</span></span>
- <span data-ttu-id="dbb1f-320">作業ディレクトリを Start-Job の現在のディレクトリに設定 (#10920) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-320">Set working directory to current directory in Start-Job (#10920) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-321">TabExpansion2 を、-CursorColumn を必要としないように変更し、$InputScript.Length として処理 (#10849)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-321">Change TabExpansion2 to not require -CursorColumn and treat as $InputScript.Length (#10849)</span></span>
- <span data-ttu-id="dbb1f-322">ホストが画面の行または列を返さないかもしれないケースを処理 (#10938)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-322">Handle case where Host may not return Rows or Columns of screen (#10938)</span></span>
- <span data-ttu-id="dbb1f-323">アクセント カラーをサポートしていないホストについて、そのアクセント カラーの使用を修正 (#10937)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-323">Fix use of accent colors for hosts that don't support them (#10937)</span></span>
- <span data-ttu-id="dbb1f-324">Update-List コマンドを再度追加 (#10922)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-324">Add back Update-List command (#10922)</span></span>
- <span data-ttu-id="dbb1f-325">Clear-RecycleBin の FWLink ID を更新 (#10925)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-325">Update FWLink Id for Clear-RecycleBin (#10925)</span></span>
- <span data-ttu-id="dbb1f-326">タブ補完中、ファイル属性を読み取ることができない場合はファイルをスキップ (#10910)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-326">During tab completion, skip file if can't read file attributes (#10910)</span></span>
- <span data-ttu-id="dbb1f-327">Windows 用 Clear-RecycleBin を再度追加 (#10909)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-327">Add back Clear-RecycleBin for Windows (#10909)</span></span>
- <span data-ttu-id="dbb1f-328">`$env:__SuppressAnsiEscapeSequences` を追加して VT エスケープ シーケンスを出力に含めるかどうかを制御 (#10814)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-328">Add `$env:__SuppressAnsiEscapeSequences` to control whether to have VT escape sequence in output (#10814)</span></span>
- <span data-ttu-id="dbb1f-329">-NoEmphasize パラメーターを追加して、Select-String 出力を色分け (#8963) (@derek-xia に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-329">Add -NoEmphasize parameter to colorize Select-String output (#8963) (Thanks @derek-xia!)</span></span>
- <span data-ttu-id="dbb1f-330">Get-HotFix コマンドレットを再度追加 (#10740)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-330">Add back Get-HotFix cmdlet (#10740)</span></span>
- <span data-ttu-id="dbb1f-331">PowerShell をホストするアプリケーションで Add-Type を使用可能に指定 (#10587)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-331">Make Add-Type usable in applications that host PowerShell (#10587)</span></span>
- <span data-ttu-id="dbb1f-332">LanguagePrimitives.IsNullLike() でより効果的な評価順序を使用 (#10781) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-332">Use more effective evaluation order in LanguagePrimitives.IsNullLike() (#10781) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="dbb1f-333">パイプ処理された mixed-collection 入力と Format-Hex のパイプ処理された入力ストリームの処理を改善 (#8674) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-333">Improve handling of mixed-collection piped input and piped streams of input in Format-Hex (#8674) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="dbb1f-334">想定されている型と値が一致しないときに SSHConnection ハッシュテーブルの型変換を使用 (#10720) (@SeeminglyScience に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-334">Use type conversion in SSHConnection hashtables when value doesn't match expected type (#10720) (Thanks @SeeminglyScience!)</span></span>
- <span data-ttu-id="dbb1f-335">-TotalCount が設定されているときに Get-Content -ReadCount 0 動作を修正 (#10749) (@eugenesmlv に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-335">Fix Get-Content -ReadCount 0 behavior when -TotalCount is set (#10749) (Thanks @eugenesmlv!)</span></span>
- <span data-ttu-id="dbb1f-336">Get-WinEvent でアクセス拒否エラー メッセージを言い換え (#10639) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-336">Reword access denied error message in Get-WinEvent (#10639) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-337">列挙型または型制約の変数代入に対してタブ補完を有効化 (#10646)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-337">Enable tab completion for variable assignment that is enum or type constrained (#10646)</span></span>
- <span data-ttu-id="dbb1f-338">書式設定の問題を引き起こしている未使用の SourceLength リモート処理プロパティを削除 (#10765)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-338">Remove unused SourceLength remoting property causing formatting issues (#10765)</span></span>
- <span data-ttu-id="dbb1f-339">-Delimiter パラメーターを ConvertFrom-StringData に追加 (#10665) (@steviecoaster に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-339">Add -Delimiter parameter to ConvertFrom-StringData (#10665) (Thanks @steviecoaster!)</span></span>
- <span data-ttu-id="dbb1f-340">SSH で Invoke-Command を使用しているときに ScriptBlock の位置指定パラメーターを追加 (#10721) (@machgo に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-340">Add positional parameter for ScriptBlock when using Invoke-Command with SSH (#10721) (Thanks @machgo!)</span></span>
- <span data-ttu-id="dbb1f-341">ConciseView で複数行なのにスクリプト名がない場合に行のコンテキスト情報を表示 (#10746)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-341">Show line context information if multiple lines but no script name for ConciseView (#10746)</span></span>
- <span data-ttu-id="dbb1f-342">\\wsl$\ パスのサポートを ファイル システム プロバイダーに追加 (#10674)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-342">Add support for \\wsl$\ paths to file system provider (#10674)</span></span>
- <span data-ttu-id="dbb1f-343">パーサーで TokenKind.QuestionMark に不足しているトークン テキストを追加 (#10706)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-343">Add the missing token text for TokenKind.QuestionMark in parser (#10706)</span></span>
- <span data-ttu-id="dbb1f-344">呼び出しスクリプトの結果として同じ場所へのスクリプトを実行している各 ForEach-Object -Parallel に現在の作業ディレクトリを設定</span><span class="sxs-lookup"><span data-stu-id="dbb1f-344">Set current working directory of each ForEach-Object -Parallel running script to the same location as the calling script.</span></span> <span data-ttu-id="dbb1f-345">(#10672)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-345">(#10672)</span></span>
- <span data-ttu-id="dbb1f-346">FindFirstStreamW と FindNextStreamW API について api-ms-win-core-file-l1-2-2.dll を Kernell32.dll に置換 (#10680) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-346">Replace api-ms-win-core-file-l1-2-2.dll with Kernell32.dll for FindFirstStreamW and FindNextStreamW APIs (#10680) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-347">StrictMode 耐性を高めるためにヘルプの書式設定スクリプトを調整 (#10563)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-347">Tweak help formatting script to be more StrictMode tolerant (#10563)</span></span>
- <span data-ttu-id="dbb1f-348">-SecurityDescriptorSDDL パラメーターを New-Service に追加 (#10483) (@kvprasoon に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-348">Add -SecurityDescriptorSDDL parameter to New-Service (#10483) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="dbb1f-349">情報出力を削除し、Test-Connection で ping の使用を統合 (#10478) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-349">Remove informational output, consolidate ping usage in Test-Connection (#10478) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="dbb1f-350">再解析ポイントをアクセスしないで読み取る (#10662) (@iSazonovに感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-350">Read special reparse points without accessing them (#10662) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-351">Clear-Host をターミナルに直接出力 (#10681) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-351">Direct Clear-Host output to terminal (#10681) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-352">Format-Table と -Property を使用してグループ化のために改行を再度追加 (#10653)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-352">Add back newline for grouping with Format-Table and -Property (#10653)</span></span>
- <span data-ttu-id="dbb1f-353">Get-Random で -InputObject から [ValidateNotNullOrEmpty] を削除して空の文字列を許可 (#10644)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-353">Remove [ValidateNotNullOrEmpty] from -InputObject on Get-Random to allow empty string (#10644)</span></span>
- <span data-ttu-id="dbb1f-354">提案システム文字列の距離アルゴリズムで大文字と小文字を区別しない (#10549) (@iSazonovに感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-354">Make suggestion system string distance algorithm case-insensitive (#10549) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-355">ForEach-Object -Parallel 入力処理の null 参照例外を修正 (#10577)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-355">Fix null reference exception in ForEach-Object -Parallel input processing (#10577)</span></span>
- <span data-ttu-id="dbb1f-356">PowerShell Core グループ ポリシー定義を追加 (#10468)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-356">Add PowerShell Core group policy definitions (#10468)</span></span>
- <span data-ttu-id="dbb1f-357">構成可能性のシナリオで使用される XTPUSHSGR/XTPOPSGR VT 制御シーケンスをサポートするようにコンソール ホストを更新</span><span class="sxs-lookup"><span data-stu-id="dbb1f-357">Update console host to support XTPUSHSGR/XTPOPSGR VT control sequences that are used in composability scenarios.</span></span> <span data-ttu-id="dbb1f-358">(#10208)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-358">(#10208)</span></span>
- <span data-ttu-id="dbb1f-359">WorkingDirectory パラメーターを Start-Job に追加 (#10324) (@davinci26 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-359">Add WorkingDirectory parameter to Start-Job (#10324) (Thanks @davinci26!)</span></span>
- <span data-ttu-id="dbb1f-360">ブレークポイントの変更がホスト実行空間デバッガーに誤ってレプリケートされる原因となっていたイベント ハンドラーを削除 (#10503) (@KirkMunroに感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-360">Remove the event handler that was causing breakpoint changes to be erroneously replicated to the host runspace debugger (#10503) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="dbb1f-361">Microsoft.PowerShell.Commands.NativeMethods P/Invoke API で api-ms-win-core-job-12-1-0.dll を Kernell32.dll に置換 (#10417) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-361">Replace api-ms-win-core-job-12-1-0.dll with Kernell32.dll in Microsoft.PowerShell.Commands.NativeMethods P/Invoke API(#10417) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-362">変数代入および -OutVariable で New-Service の誤った出力を修正 (#10444) (@kvprasoon に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-362">Fix wrong output for New-Service in variable assignment and -OutVariable (#10444) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="dbb1f-363">終了コード、コマンド ライン パラメーター、およびスペースを含むパスに関するグローバル ツールの問題を修正 (#10461)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-363">Fix global tool issues around exit code, command line parameters and path with spaces (#10461)</span></span>
- <span data-ttu-id="dbb1f-364">OneDrive への再帰を修正 - SafeFindHandle 型 を使用するように FindFirstFileEx() を変更(#10405)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-364">Fix recursion into OneDrive - change FindFirstFileEx() to use SafeFindHandle type (#10405)</span></span>
- <span data-ttu-id="dbb1f-365">NVDA スクリーン リーダーがアクティブの場合、Windows で PSReadLine の自動読み込みをスキップ (#10385)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-365">Skip auto-loading PSReadLine on Windows if the NVDA screen reader is active (#10385)</span></span>
- <span data-ttu-id="dbb1f-366">組み込み PowerShell モジュールを 7.0.0.0 にバージョンアップ (#10356)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-366">Increase built-with-PowerShell module versions to 7.0.0.0 (#10356)</span></span>
- <span data-ttu-id="dbb1f-367">同じ名前の型が既に存在する場合の Add-Type でのエラーのスローを追加 (#9609) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-367">Add throwing an error in Add-Type if a type with the same name already exists (#9609) (Thanks @iSazonov!)</span></span>

### <a name="performance"></a><span data-ttu-id="dbb1f-368">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="dbb1f-368">Performance</span></span>

- <span data-ttu-id="dbb1f-369">Parser.SaveError でのクロージャの使用を回避 (#11006)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-369">Avoid using closure in Parser.SaveError (#11006)</span></span>
- <span data-ttu-id="dbb1f-370">新しい Regex インスタンス作成時のキャッシュを改善 (#10657) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-370">Improve the caching when creating new Regex instances (#10657) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-371">types.ps1xml、typesV3.ps1xml、および GetEvent.types.ps1xml からの PowerShell 組み込み型データの処理を改善 (#10898)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-371">Improve processing of the PowerShell built-in type data from types.ps1xml, typesV3.ps1xml and GetEvent.types.ps1xml (#10898)</span></span>
- <span data-ttu-id="dbb1f-372">PSConfiguration.ReadValueFromFile を更新して、高速化とメモリ効率の改善を実現 (#10839)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-372">Update PSConfiguration.ReadValueFromFile to make it faster and more memory efficient (#10839)</span></span>
- <span data-ttu-id="dbb1f-373">実行空間の初期化のパフォーマンスを若干改善 (#10569) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-373">Add minor performance improvements for runspace initialization (#10569) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-374">一般的に使用されるシナリオの ForEach-Object を高速化 (#10454)。また、多数の実行空間によって ForEach-Object -Parallel のパフォーマンスに関する問題を修正 (#10455)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-374">Make ForEach-Object faster for its commonly used scenarios (#10454) and fix ForEach-Object -Parallel performance problem with many runspaces (#10455)</span></span>

### <a name="code-cleanup"></a><span data-ttu-id="dbb1f-375">コードのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="dbb1f-375">Code Cleanup</span></span>

- <span data-ttu-id="dbb1f-376">Microsoft 標準に合わせてコメントおよび要素テキストを変更 (#11304)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-376">Change comment and element text to meet Microsoft standards (#11304)</span></span>
- <span data-ttu-id="dbb1f-377">Compiler.cs のスタイルに関する問題をクリーンアップ (#10368) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-377">Cleanup style issues in Compiler.cs (#10368) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-378">CommaDelimitedStringCollection の未使用の型コンバーターを削除 (#11000) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-378">Remove the unused type converter for CommaDelimitedStringCollection (#11000) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-379">InitialSessionState.cs のスタイルをクリーンアップ (#10865) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-379">Cleanup style in InitialSessionState.cs (#10865) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-380">PSSession クラスのコードをクリーンアップ (#11001)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-380">Code clean up for PSSession class (#11001)</span></span>
- <span data-ttu-id="dbb1f-381">動作していない "Get-Help の初回実行時に Get-Help から Update-Help を実行する" 機能を削除 (#10974)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-381">Remove the not-working 'run Update-Help from Get-Help when Get-Help runs for the first time' feature (#10974)</span></span>
- <span data-ttu-id="dbb1f-382">スタイルの問題を修正 (#10998) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-382">Fix style issues (#10998) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-383">クリーンアップ: 組み込み型エイリアスを使用 (#10882) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-383">Cleanup: use the built-in type alias (#10882) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-384">使用されていない設定キー ConsolePrompting を削除し、ExecutionPolicy 設定にクエリを実行するときの不要な文字列作成を回避 (#10985)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-384">Remove the unused setting key ConsolePrompting and avoid unnecessary string creation when querying ExecutionPolicy setting (#10985)</span></span>
- <span data-ttu-id="dbb1f-385">デイリー ビルドに対する更新通知チェックを無効化 (#10903) (@bergmeister に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-385">Disable update notification check for daily builds (#10903) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="dbb1f-386">#10338 で失われたデバッグ API を復帰 (#10808)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-386">Reinstate debugging API lost in #10338 (#10808)</span></span>
- <span data-ttu-id="dbb1f-387">使用されなくなった WorkflowJobSourceAdapter 参照を削除 (#10326) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-387">Remove WorkflowJobSourceAdapter reference that is no longer used (#10326) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="dbb1f-388">PreserveSig 属性を修正して、ジャンプ リスト コードの COM インターフェイスをクリーンアップ (#9899) (@weltkante に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-388">Cleanup COM interfaces in jump list code by fixing PreserveSig attributes (#9899) (Thanks @weltkante!)</span></span>
- <span data-ttu-id="dbb1f-389">Add a comment describing why -ia が -InformationAction 共通パラメーターのエイリアスではない理由を説明するコメントを追加 (#10703) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-389">Add a comment describing why -ia is not the alias for -InformationAction common parameter (#10703) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="dbb1f-390">InvokeCommandCmdlet.cs を InvokeExpressionCommand.cs に名前変更(#10659) (@kilasuit に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-390">Rename InvokeCommandCmdlet.cs to InvokeExpressionCommand.cs (#10659) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="dbb1f-391">更新通知に関連する小さなコード クリーンアップを追加 (#10698)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-391">Add minor code cleanups related to update notifications (#10698)</span></span>
- <span data-ttu-id="dbb1f-392">非推奨のワークフロー ロジックをリモート処理設定スクリプトから削除 (#10320) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-392">Remove deprecated workflow logic from the remoting setup scripts (#10320) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="dbb1f-393">適切なケースを使用するようにヘルプ形式を更新 (#10678) (@tnieto88 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-393">Update help format to use proper case (#10678) (Thanks @tnieto88!)</span></span>
- <span data-ttu-id="dbb1f-394">先月のコミットで発生する CodeFactor スタイルの問題をクリーンアップ (#10591) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-394">Clean up CodeFactor style issues coming in commits for the last month (#10591) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-395">試験的な PSTernaryOperator 機能の説明の入力ミスを修正 (#10586) (@bergmeister に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-395">Fix typo in description of PSTernaryOperator experimental feature (#10586) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="dbb1f-396">ActionPreference.Suspend 列挙値をサポートされていない予約済み状態に変換し、ユーザー設定変数で ActionPreference.Ignore を使用するときの制限を削除 (#10317) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-396">Convert ActionPreference.Suspend enumeration value into a non-supported, reserved state, and remove restriction on using ActionPreference.Ignore in preference variables (#10317) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="dbb1f-397">機能を変更することなくコードの読みやすさと信頼性を高めるために ArrayList を List<T> に置換 (#10333) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-397">Replace ArrayList with List<T> to get more readable and reliable code without changing functionality (#10333) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-398">TestConnectionCommand へのコード スタイルの修正 (#10439) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-398">Make code style fixes to TestConnectionCommand (#10439) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="dbb1f-399">AutomationEngine をクリーンアップし、余分な SetSessionStateDrive メソッド呼び出しを削除 (#10416) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-399">Cleanup AutomationEngine and remove extra SetSessionStateDrive method call (#10416) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-400">既定の ParameterSetName の名前を ConvertTo-Csv および ConvertFrom-Csv の Delimiter に再度変更 (#10425)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-400">Rename default ParameterSetName back to Delimiter for ConvertTo-Csv and ConvertFrom-Csv (#10425)</span></span>

### <a name="tools"></a><span data-ttu-id="dbb1f-401">ツール</span><span class="sxs-lookup"><span data-stu-id="dbb1f-401">Tools</span></span>

- <span data-ttu-id="dbb1f-402">VS でビルドが行われるように SDKToUse プロパティの既定の設定を追加 (#11085)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-402">Add default setting for the SDKToUse property so that it builds in VS (#11085)</span></span>
- <span data-ttu-id="dbb1f-403">Install-Powershell.ps1: MSI インストールが使用されるようにパラメーターを追加 (#10921) (@MJECloud に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-403">Install-Powershell.ps1: Add parameter to use MSI installation (#10921) (Thanks @MJECloud!)</span></span>
- <span data-ttu-id="dbb1f-404">install-powershell.ps1 の基本的な例を追加 (#10914) (@kilasuit に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-404">Add basic examples for install-powershell.ps1 (#10914) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="dbb1f-405">Install-PowerShellRemoting.ps1 による PowerShellHome パラメーターの空の文字列の処理を実現 (#10526) (@Orca88 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-405">Make Install-PowerShellRemoting.ps1 handle empty string in PowerShellHome parameter (#10526) (Thanks @Orca88!)</span></span>
- <span data-ttu-id="dbb1f-406">Install-powershell.sh で /etc/lsb-release から /etc/os-release に切り替え (#10773) (@Himura2la に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-406">Switch from /etc/lsb-release to /etc/os-release in install-powershell.sh (#10773) (Thanks @Himura2la!)</span></span>
- <span data-ttu-id="dbb1f-407">Windows で pwsh.exe と pwsh のデイリー バージョンを確認 (#10738) (@centreboard に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-407">Check pwsh.exe and pwsh in daily version on Windows (#10738) (Thanks @centreboard!)</span></span>
- <span data-ttu-id="dbb1f-408">installpsh-osx.sh で不要なタップを削除 (#10752)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-408">Remove unneeded tap in installpsh-osx.sh (#10752)</span></span>
- <span data-ttu-id="dbb1f-409">既にインストールされているデイリー ビルド チェックのために install-powershell.ps1 を更新 (#10489)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-409">Update install-powershell.ps1 to check for already installed daily build (#10489)</span></span>

### <a name="tests"></a><span data-ttu-id="dbb1f-410">テスト</span><span class="sxs-lookup"><span data-stu-id="dbb1f-410">Tests</span></span>

- <span data-ttu-id="dbb1f-411">信頼性の低い DSC テストを保留 (#11131)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-411">Make unreliable DSC test pending (#11131)</span></span>
- <span data-ttu-id="dbb1f-412">ハッシュテーブルのキーが正しく検証されるように stringdata テストを修正 (#10810)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-412">Fix stringdata test to correctly validate keys of hashtables (#10810)</span></span>
- <span data-ttu-id="dbb1f-413">テスト モジュールをアンロード (#11061) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-413">Unload test modules (#11061) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-414">URL テストの再試行間隔を長くする (#11015)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-414">Increase time between retries of testing URL (#11015)</span></span>
- <span data-ttu-id="dbb1f-415">テスト アクションが正確に記述されるようにテストを更新</span><span class="sxs-lookup"><span data-stu-id="dbb1f-415">Update tests to accurately describe test actions.</span></span> <span data-ttu-id="dbb1f-416">(#10928) (@romero126 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-416">(#10928) (Thanks @romero126!)</span></span>
- <span data-ttu-id="dbb1f-417">不安定なテスト TestAppDomainProcessExitEvenHandlerNotLeaking を一時的にスキップ (#10827)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-417">Temporary skip the flaky test TestAppDomainProcessExitEvenHandlerNotLeaking (#10827)</span></span>
- <span data-ttu-id="dbb1f-418">イベント ハンドラー リーク テストの安定化 (#10790)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-418">Make the event handler leaking test stable (#10790)</span></span>
- <span data-ttu-id="dbb1f-419">CI YAML の大文字と小文字の区別を同期 (#10767) (@RDIL に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-419">Sync capitalization in CI YAML (#10767) (Thanks @RDIL!)</span></span>
- <span data-ttu-id="dbb1f-420">イベント ハンドラー リーク修正のテストを追加 (#10768)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-420">Add test for the event handler leaking fix (#10768)</span></span>
- <span data-ttu-id="dbb1f-421">Get-ChildItem テストを追加 (#10507) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-421">Add Get-ChildItem test (#10507) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-422">正確性を高めるためにテストのあいまいな言語をスイッチからパラメーターに置換 (#10666) (@romero126 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-422">Replace ambiguous language for tests from switch to parameter for accuracy (#10666) (Thanks @romero126!)</span></span>
- <span data-ttu-id="dbb1f-423">試験的なチェックを ForEach-Object -Parallel テストに追加 (#10354) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-423">Add experimental check to ForEach-Object -Parallel tests (#10354) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="dbb1f-424">Alpine 検証のテストを更新 (#10428)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-424">Update tests for Alpine validation (#10428)</span></span>

### <a name="build-and-package-improvements"></a><span data-ttu-id="dbb1f-425">ビルドとパッケージの機能強化</span><span class="sxs-lookup"><span data-stu-id="dbb1f-425">Build and Package Improvements</span></span>

- <span data-ttu-id="dbb1f-426">調整済みパッケージ ビルドの Nuget パッケージ署名を修正 (#11316)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-426">Fix Nuget package signing for Coordinated Package build (#11316)</span></span>
- <span data-ttu-id="dbb1f-427">PowerShell ギャラリーと NuGet からの依存関係を更新 (#11323)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-427">Update dependencies from PowerShell Gallery and NuGet (#11323)</span></span>
- <span data-ttu-id="dbb1f-428">Microsoft.ApplicationInsights を 2.11.0 から 2.12.0 にバージョンアップ (#11305)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-428">Bump Microsoft.ApplicationInsights from 2.11.0 to 2.12.0 (#11305)</span></span>
- <span data-ttu-id="dbb1f-429">Microsoft.CodeAnalysis.CSharp を 3.3.1 から 3.4.0 にバージョンアップ (#11265)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-429">Bump Microsoft.CodeAnalysis.CSharp from 3.3.1 to 3.4.0 (#11265)</span></span>
- <span data-ttu-id="dbb1f-430">Debian 10 および 11 のパッケージを更新 (#11236)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-430">Updates packages for Debian 10 and 11 (#11236)</span></span>
- <span data-ttu-id="dbb1f-431">RC より前の試験的な機能のみを有効化 (#11162)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-431">Only enable experimental features prior to RC (#11162)</span></span>
- <span data-ttu-id="dbb1f-432">macOS の最小バージョンを更新 (#11163)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-432">Update macOS minimum version (#11163)</span></span>
- <span data-ttu-id="dbb1f-433">NJsonSchema を 10.0.27 から 10.0.28 にバージョンアップ (#11170)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-433">Bump NJsonSchema from 10.0.27 to 10.0.28 (#11170)</span></span>
- <span data-ttu-id="dbb1f-434">Preview.5 の README.md および metadata.json のリンクを更新 (#10854)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-434">Updating links in README.md and metadata.json for Preview.5 (#10854)</span></span>
- <span data-ttu-id="dbb1f-435">PowerShell 所有のコンプライアンス テストのファイルを選択 (#10837)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-435">Select the files for compliance tests which are owned by PowerShell (#10837)</span></span>
- <span data-ttu-id="dbb1f-436">win7x86 msix パッケージによるビルドを許可</span><span class="sxs-lookup"><span data-stu-id="dbb1f-436">Allow win7x86 msix package to build.</span></span> <span data-ttu-id="dbb1f-437">(内部 10515)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-437">(Internal 10515)</span></span>
- <span data-ttu-id="dbb1f-438">セマンティク バージョンを NormalizeVersion 関数に渡すことを許可 (#11087)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-438">Allow semantic versions to be passed to NormalizeVersion function (#11087)</span></span>
- <span data-ttu-id="dbb1f-439">.NET Core Framework を 3.1-preview.3 にバージョンアップ (#11079)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-439">Bump .NET core framework to 3.1-preview.3 (#11079)</span></span>
- <span data-ttu-id="dbb1f-440">/src/Modules で PSReadLine を 2.0.0-beta5 から 2.0.0-beta6 にバージョンアップ (#11078)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-440">Bump PSReadLine from 2.0.0-beta5 to 2.0.0-beta6 in /src/Modules (#11078)</span></span>
- <span data-ttu-id="dbb1f-441">Newtonsoft.Json を 12.0.2 から 12.0.3 にバージョンアップ (#11037) (#11038)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-441">Bump Newtonsoft.Json from 12.0.2 to 12.0.3 (#11037) (#11038)</span></span>
- <span data-ttu-id="dbb1f-442">Debian 10、11、および CentOS 8 パッケージを追加 (#11028)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-442">Add Debian 10, 11 and CentOS 8 packages (#11028)</span></span>
- <span data-ttu-id="dbb1f-443">ReleaseDate フィールドを含む Build-Info Json ファイルをアップロード (#10986)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-443">Upload Build-Info Json file with the ReleaseDate field (#10986)</span></span>
- <span data-ttu-id="dbb1f-444">.NET Core Framework を 3.1-preview.2 にバージョンアップ (#10993)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-444">Bump .NET core framework to 3.1-preview.2 (#10993)</span></span>
- <span data-ttu-id="dbb1f-445">x86 MSIX パッケージのビルドを有効化 (#10934)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-445">Enable build of x86 MSIX package (#10934)</span></span>
- <span data-ttu-id="dbb1f-446">build.psm1 の dotnet SDK インストール スクリプト URL を更新 (#10927)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-446">Update the dotnet SDK install script URL in build.psm1 (#10927)</span></span>
- <span data-ttu-id="dbb1f-447">Markdig.Signed を 0.17.1 から 0.18.0 にバージョンアップ (#10887)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-447">Bump Markdig.Signed from 0.17.1 to 0.18.0 (#10887)</span></span>
- <span data-ttu-id="dbb1f-448">ThreadJob を 2.0.1 から 2.0.2 にバージョンアップ (#10886)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-448">Bump ThreadJob from 2.0.1 to 2.0.2 (#10886)</span></span>
- <span data-ttu-id="dbb1f-449">MS Store の要件を満たすように AppX マニフェストおよびパッケージ モジュールを更新 (#10878)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-449">Update AppX Manifest and Packaging module to conform to MS Store requirements (#10878)</span></span>
- <span data-ttu-id="dbb1f-450">PowerShell SDK のパッケージ参照を preview.5 に更新 (内部 10295)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-450">Update package reference for PowerShell SDK to preview.5 (Internal 10295)</span></span>
- <span data-ttu-id="dbb1f-451">ThirdPartyNotices.txt を更新 (#10834)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-451">Update ThirdPartyNotices.txt (#10834)</span></span>
- <span data-ttu-id="dbb1f-452">Microsoft.PowerShell.Native を 7.0.0-preview.3 にバージョンアップ (#10826)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-452">Bump Microsoft.PowerShell.Native to 7.0.0-preview.3 (#10826)</span></span>
- <span data-ttu-id="dbb1f-453">Microsoft.ApplicationInsights を 2.10.0 から 2.11.0 にバージョンアップ (#10608)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-453">Bump Microsoft.ApplicationInsights from 2.10.0 to 2.11.0 (#10608)</span></span>
- <span data-ttu-id="dbb1f-454">NJsonSchema を 10.0.24 から 10.0.27 にバージョンアップ (#10756)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-454">Bump NJsonSchema from 10.0.24 to 10.0.27 (#10756)</span></span>
- <span data-ttu-id="dbb1f-455">MacPorts サポートをビルド システムに追加 (#10736) (@Lucius-Q-User に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-455">Add MacPorts support to the build system (#10736) (Thanks @Lucius-Q-User!)</span></span>
- <span data-ttu-id="dbb1f-456">PackageManagement を 1.4.4 から 1.4.5 にバージョンアップ (#10728)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-456">Bump PackageManagement from 1.4.4 to 1.4.5 (#10728)</span></span>
- <span data-ttu-id="dbb1f-457">NJsonSchema を 10.0.23 から 10.0.24 にバージョンアップ (#10635)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-457">Bump NJsonSchema from 10.0.23 to 10.0.24 (#10635)</span></span>
- <span data-ttu-id="dbb1f-458">MSI でクライアント/サーバーのテレメトリを区別できるように環境変数を追加 (#10612)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-458">Add environment variable to differentiate client/server telemetry in MSI (#10612)</span></span>
- <span data-ttu-id="dbb1f-459">PSDesiredStateConfiguration を 2.0.3 から 2.0.4 にバージョンアップ (#10603)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-459">Bump PSDesiredStateConfiguration from 2.0.3 to 2.0.4 (#10603)</span></span>
- <span data-ttu-id="dbb1f-460">Microsoft.CodeAnalysis.CSharp を 3.2.1 から 3.3.1 にバージョンアップ (#10607)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-460">Bump Microsoft.CodeAnalysis.CSharp from 3.2.1 to 3.3.1 (#10607)</span></span>
- <span data-ttu-id="dbb1f-461">.Net Core 3.0 RTM に更新 (#10604) (@bergmeister に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-461">Update to .Net Core 3.0 RTM (#10604) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="dbb1f-462">Windows ストアの要件に対応するように MSIX パッケージを更新 (#10588)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-462">Update MSIX packaging so the version to Windows Store requirements (#10588)</span></span>
- <span data-ttu-id="dbb1f-463">PowerShellGet を 2.2 から 2.2.1 にバージョンアップ (#10382)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-463">Bump PowerShellGet version from 2.2 to 2.2.1 (#10382)</span></span>
- <span data-ttu-id="dbb1f-464">PackageManagement を 1.4.3 から 1.4.4 にバージョンアップ (#10383)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-464">Bump PackageManagement version from 1.4.3 to 1.4.4 (#10383)</span></span>
- <span data-ttu-id="dbb1f-465">7\.0.0-preview.4 の README.md および metadata.json を更新 (内部 10011)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-465">Update README.md and metadata.json for 7.0.0-preview.4 (Internal 10011)</span></span>
- <span data-ttu-id="dbb1f-466">.Net Core 3.0 バージョンを Preview 9 から RC1 にアップグレード (#10552) (@bergmeister に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-466">Upgrade .Net Core 3.0 version from Preview 9 to RC1 (#10552) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="dbb1f-467">ExperimentalFeature リスト生成を修正 (内部 9996)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-467">Fix ExperimentalFeature list generation (Internal 9996)</span></span>
- <span data-ttu-id="dbb1f-468">PSReadLine を 2.0.0-beta4 から 2.0.0-beta5 にバージョンアップ (#10536)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-468">Bump PSReadLine version from 2.0.0-beta4 to 2.0.0-beta5 (#10536)</span></span>
- <span data-ttu-id="dbb1f-469">リリース タグが設定されるようにリリース ビルド スクリプトを修正</span><span class="sxs-lookup"><span data-stu-id="dbb1f-469">Fix release build script to set release tag</span></span>
- <span data-ttu-id="dbb1f-470">Microsoft.PowerShell.Native のバージョンを 7.0.0-preview.2 に更新 (#10519)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-470">Update version of Microsoft.PowerShell.Native to 7.0.0-preview.2 (#10519)</span></span>
- <span data-ttu-id="dbb1f-471">Netcoreapp3.0 preview9 をアップグレード (#10484) (@bergmeister に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-471">Upgrade to Netcoreapp3.0 preview9 (#10484) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="dbb1f-472">調整済みデイリー ビルドがデイリー ビルドであることを確実に認識 (#10464)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-472">Make sure the daily coordinated build, knows it is a daily build (#10464)</span></span>
- <span data-ttu-id="dbb1f-473">デイリー ビルドをリリースするように結合パッケージ ビルドを更新 (#10449)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-473">Update the combined package build to release the daily builds (#10449)</span></span>
- <span data-ttu-id="dbb1f-474">appveyor 参照を削除 (#10445) (@RDIL に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-474">Remove appveyor reference (#10445) (Thanks @RDIL!)</span></span>
- <span data-ttu-id="dbb1f-475">NJsonSchema を 10.0.22 から 10.0.23 にバージョンアップ (#10421)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-475">Bump NJsonSchema version from 10.0.22 to 10.0.23 (#10421)</span></span>
- <span data-ttu-id="dbb1f-476">Alpine の依存関係の一部で必要とされるため linux-x64 ビルド フォルダーの削除を削除 (#10407)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-476">Remove the deletion of linux-x64 build folder because some dependencies for Alpine need it (#10407)</span></span>

### <a name="documentation-and-help-content"></a><span data-ttu-id="dbb1f-477">ドキュメントとヘルプ コンテンツ</span><span class="sxs-lookup"><span data-stu-id="dbb1f-477">Documentation and Help Content</span></span>

- <span data-ttu-id="dbb1f-478">変更ログをリリースごとに 1 つのログにリファクター (#11165)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-478">Refactor change logs into one log per release (#11165)</span></span>
- <span data-ttu-id="dbb1f-479">PowerShell 7 オンライン ヘルプ ドキュメントの FWLink を修正 (#11071)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-479">Fix FWLinks for PowerShell 7 online help documents (#11071)</span></span>
- <span data-ttu-id="dbb1f-480">CONTRIBUTING.md を更新 (#11096) (@mklement0 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-480">Update CONTRIBUTING.md (#11096) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="dbb1f-481">README.md のインストール ドキュメントのリンクを修正 (#11083)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-481">Fix installation doc links in README.md (#11083)</span></span>
- <span data-ttu-id="dbb1f-482">install-powershell.ps1 スクリプトに例を追加 (#11024) (@kilasuit に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-482">Adds examples to install-powershell.ps1 script (#11024) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="dbb1f-483">CHANGELOG.md の Select-String 強調および Import-DscResource への修正 (#10890)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-483">Fix to Select-String emphasis and Import-DscResource in CHANGELOG.md (#10890)</span></span>
- <span data-ttu-id="dbb1f-484">powershell-beginners-guide.md から古いリンクを削除 (#10926)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-484">Remove the stale link from powershell-beginners-guide.md (#10926)</span></span>
- <span data-ttu-id="dbb1f-485">安定したサービス変更ログの統合 (#10527)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-485">Merge stable and servicing change logs (#10527)</span></span>
- <span data-ttu-id="dbb1f-486">ビルド ドキュメントの使用されている .NET バージョンを更新 (#10775) (@Greg-Smulko に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-486">Update used .NET version in build docs (#10775) (Thanks @Greg-Smulko!)</span></span>
- <span data-ttu-id="dbb1f-487">powershell-beginners-guide.md で MSDN のリンクを docs.microsoft.com に置換 (#10778) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-487">Replace links from MSDN to docs.microsoft.com in powershell-beginners-guide.md (#10778) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="dbb1f-488">破損した DSC 概要リンクを修正 (#10702)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-488">Fix broken DSC overview link (#10702)</span></span>
- <span data-ttu-id="dbb1f-489">Support_Question.md を更新して、Stack Overflow に別のコミュニティ リソースとしてリンク (#10638) (@mklement0 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-489">Update Support_Question.md to link to Stack Overflow as another community resource (#10638) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="dbb1f-490">プロセッサ アーキテクチャをディストリビューション要求テンプレートに追加 (#10661)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-490">Add processor architecture to distribution request template (#10661)</span></span>
- <span data-ttu-id="dbb1f-491">新しい PowerShell MoL ブックを学習用の PowerShell ドキュメントに追加 (#10602)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-491">Add new PowerShell MoL book to learning PowerShell docs (#10602)</span></span>
- <span data-ttu-id="dbb1f-492">v6.1.6 および v6.2.3 リリースの README.md およびメタデータを更新 (#10523)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-492">Update README.md and metadata for v6.1.6 and v6.2.3 releases (#10523)</span></span>
- <span data-ttu-id="dbb1f-493">README.md の入力ミスを修正 (#10465) (@vedhasp に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-493">Fix a typo in README.md (#10465) (Thanks @vedhasp!)</span></span>
- <span data-ttu-id="dbb1f-494">PSKoans モジュールへの参照を学習用のリソース ドキュメントに追加 (#10369) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-494">Add a reference to PSKoans module to Learning Resources documentation (#10369) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="dbb1f-495">7\.0.0-preview.3 の README.md および metadata.json を更新 (#10393)</span><span class="sxs-lookup"><span data-stu-id="dbb1f-495">Update README.md and metadata.json for 7.0.0-preview.3 (#10393)</span></span>

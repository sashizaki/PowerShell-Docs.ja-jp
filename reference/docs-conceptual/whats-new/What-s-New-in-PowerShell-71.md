---
title: PowerShell 7.1 の新機能
description: PowerShell 7.1 でリリースされた新機能と変更
ms.date: 12/15/2020
ms.openlocfilehash: 6bbeccd07dd696ee019828bdcd68ce3f6ee627e3
ms.sourcegitcommit: 1628fd2a1f50aec2f31ffb1c451a3ce77c08983c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "97577209"
---
# <a name="whats-new-in-powershell-71"></a><span data-ttu-id="d09a0-103">PowerShell 7.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="d09a0-103">What's New in PowerShell 7.1</span></span>

<span data-ttu-id="d09a0-104">2020 年 11 月 11 日に、PowerShell 7.1 の一般提供を[発表しました](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/)。</span><span class="sxs-lookup"><span data-stu-id="d09a0-104">On November 11, 2020 we [announced](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/) the general availability of PowerShell 7.1.</span></span> <span data-ttu-id="d09a0-105">PowerShell 7.0 において確立された基盤が基になっており、コミュニティの問題に関する作業が重点的に行われ、さまざまな改善と修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d09a0-105">Building on the foundation established in PowerShell 7.0, our efforts focused on community issues and include a number of improvements and fixes.</span></span> <span data-ttu-id="d09a0-106">PowerShell が安定した高性能なプラットフォームとして維持されるよう取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-106">We are committed to ensuring that PowerShell remains a stable and performant platform.</span></span>

<span data-ttu-id="d09a0-107">PowerShell 7.1 には、次の機能、更新プログラム、破壊的変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d09a0-107">PowerShell 7.1 includes the following features, updates, and breaking changes.</span></span>

- <span data-ttu-id="d09a0-108">予測 IntelliSense を含む PSReadLine 2.1.0</span><span class="sxs-lookup"><span data-stu-id="d09a0-108">PSReadLine 2.1.0, which includes Predictive IntelliSense</span></span>
- <span data-ttu-id="d09a0-109">PowerShell 7.1 が Microsoft Store に公開されています</span><span class="sxs-lookup"><span data-stu-id="d09a0-109">PowerShell 7.1 has been published to the Microsoft Store</span></span>
- <span data-ttu-id="d09a0-110">ARM64 をサポートする新しい OS バージョン用に更新されたインストーラー パッケージ</span><span class="sxs-lookup"><span data-stu-id="d09a0-110">Installer packages updated for new OS versions with support for ARM64</span></span>
- <span data-ttu-id="d09a0-111">メインストリームに昇格した 4 つの新しい試験的機能と 2 つの試験的機能</span><span class="sxs-lookup"><span data-stu-id="d09a0-111">4 new experimental features and 2 experimental features promoted to mainstream</span></span>
- <span data-ttu-id="d09a0-112">使いやすさ向上のためのいくつかの破壊的変更</span><span class="sxs-lookup"><span data-stu-id="d09a0-112">Several breaking changes to improve usability</span></span>

<span data-ttu-id="d09a0-113">詳細な変更一覧については、GitHub リポジトリの[変更ログ](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d09a0-113">For a complete list of changes, see the [CHANGELOG](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) in the GitHub repository.</span></span>

## <a name="psreadline-210"></a><span data-ttu-id="d09a0-114">PSReadLine 2.1.0</span><span class="sxs-lookup"><span data-stu-id="d09a0-114">PSReadLine 2.1.0</span></span>

<span data-ttu-id="d09a0-115">PowerShell 7.1 には、PSReadLine 2.1.0 も組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="d09a0-115">PowerShell 7.1 also include PSReadLine 2.1.0.</span></span> <span data-ttu-id="d09a0-116">このバージョンには、Predictive IntelliSense が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d09a0-116">This version includes Predictive IntelliSense.</span></span> <span data-ttu-id="d09a0-117">Predictive IntelliSense 機能の詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d09a0-117">For more information about the Predictive IntelliSense feature, see the [announcement](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/) in the PowerShell blog.</span></span>

## <a name="microsoft-store-installer-package"></a><span data-ttu-id="d09a0-118">Microsoft Store インストーラー パッケージ</span><span class="sxs-lookup"><span data-stu-id="d09a0-118">Microsoft Store installer package</span></span>

<span data-ttu-id="d09a0-119">PowerShell 7.1 が Microsoft Store に公開されています。</span><span class="sxs-lookup"><span data-stu-id="d09a0-119">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="d09a0-120">PowerShell リリースは [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) Web サイトまたは Windows の Store アプリケーションで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-120">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="d09a0-121">Microsoft Store パッケージの利点:</span><span class="sxs-lookup"><span data-stu-id="d09a0-121">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="d09a0-122">Windows 10 に直接組み込まれた自動更新</span><span class="sxs-lookup"><span data-stu-id="d09a0-122">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="d09a0-123">Intune や SCCM など、他のソフトウェア配布メカニズムとの統合</span><span class="sxs-lookup"><span data-stu-id="d09a0-123">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

> [!NOTE]
> <span data-ttu-id="d09a0-124">`$PSHOME` に格納されているシステムレベルの構成設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="d09a0-124">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="d09a0-125">これには WSMAN 構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-125">This includes the WSMAN configuration.</span></span> <span data-ttu-id="d09a0-126">これにより、リモート セッションが PowerShell のストアベース インストールに接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d09a0-126">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="d09a0-127">ユーザーレベル構成と SSH リモート処理がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d09a0-127">User-level configurations and SSH remoting are supported.</span></span>

## <a name="other-installers"></a><span data-ttu-id="d09a0-128">その他のインストーラー</span><span class="sxs-lookup"><span data-stu-id="d09a0-128">Other installers</span></span>

<span data-ttu-id="d09a0-129">サポートされているオペレーティング システムとサポート ライフサイクルの最新情報については、[PowerShell サポート ライフサイクル](/powershell/scripting/powershell-support-lifecycle)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d09a0-129">For more up-to-date information about supported operating systems and support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle).</span></span>

<span data-ttu-id="d09a0-130">任意のオペレーティング システムのインストール手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d09a0-130">Check the installation instructions for your preferred operating system:</span></span>

- [<span data-ttu-id="d09a0-131">Windows</span><span class="sxs-lookup"><span data-stu-id="d09a0-131">Windows</span></span>](/powershell/scripting/install/installing-powershell-core-on-windows)
- [<span data-ttu-id="d09a0-132">macOS</span><span class="sxs-lookup"><span data-stu-id="d09a0-132">macOS</span></span>](/powershell/scripting/install/installing-powershell-core-on-macos)
- [<span data-ttu-id="d09a0-133">Linux</span><span class="sxs-lookup"><span data-stu-id="d09a0-133">Linux</span></span>](/powershell/scripting/install/installing-powershell-core-on-linux)

<span data-ttu-id="d09a0-134">さらに、PowerShell 7.1 では、Debian、Ubuntu、ARM64 Alpine Linux の ARM32 および ARM64 フレーバーもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d09a0-134">Additionally, PowerShell 7.1 supports ARM32 and ARM64 flavors of Debian, Ubuntu, and ARM64 Alpine Linux.</span></span>

<span data-ttu-id="d09a0-135">公式にはサポートされていませんが、コミュニティでは、[Arch](https://aur.archlinux.org/packages/powershell/) および Kali Linux 用のパッケージも提供しています。</span><span class="sxs-lookup"><span data-stu-id="d09a0-135">While not officially supported, the community has also provided packages for [Arch](https://aur.archlinux.org/packages/powershell/) and Kali Linux.</span></span>

> [!NOTE]
> <span data-ttu-id="d09a0-136">Debian 10 以降、CentOS 8 以降、Ubuntu 20.04、Alpine、Arm では、WinRM リモート処理はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d09a0-136">Debian 10+, CentOS 8+, Ubuntu 20.04, Alpine and Arm currently do not support WinRM remoting.</span></span> <span data-ttu-id="d09a0-137">SSH ベースのリモート処理設定の詳細については、「[SSH 経由の PowerShell リモート処理](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d09a0-137">For details on setting up SSH-based remoting, see [PowerShell Remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <a name="experimental-features"></a><span data-ttu-id="d09a0-138">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="d09a0-138">Experimental Features</span></span>

<span data-ttu-id="d09a0-139">試験的な機能の詳細については、[試験的機能の使用](../learn/experimental-features.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d09a0-139">For more information about the Experimental Features, see [Using Experimental Features](../learn/experimental-features.md).</span></span>

<span data-ttu-id="d09a0-140">このリリースでは、次の試験的機能がメインストリーム機能になりました。</span><span class="sxs-lookup"><span data-stu-id="d09a0-140">The following experimental features are now mainstream features in this release:</span></span>

- [<span data-ttu-id="d09a0-141">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="d09a0-141">PSNullConditionalOperators</span></span>](../learn/experimental-features.md#psnullconditionaloperators)
- [<span data-ttu-id="d09a0-142">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="d09a0-142">PSUnixFileStat</span></span>](../learn/experimental-features.md#psunixfilestat)

<span data-ttu-id="d09a0-143">このリリースでは、次の試験的機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="d09a0-143">The following experimental features were added in this release:</span></span>

- [<span data-ttu-id="d09a0-144">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="d09a0-144">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>](../learn/experimental-features.md#microsoftpowershellutilitypsmanagebreakpointsinrunspace)
  - <span data-ttu-id="d09a0-145">PowerShell 7.1 では、この試験的機能が拡張され、すべての `*-PSBreakpoint` コマンドレットに **Runspace** パラメーターが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-145">PowerShell 7.1 extends this experimental feature to add the **Runspace** parameter to all `*-PSBreakpoint` cmdlets.</span></span> <span data-ttu-id="d09a0-146">**Runspace** パラメーターによって、**Runspace** オブジェクトを指定し、指定した実行空間内のブレークポイントと対話できます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-146">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

- <span data-ttu-id="d09a0-147">[PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution) - この機能を使用すると、Powershell のパス構文をサポートしていないネイティブ コマンドに PowerShell プロバイダーのパスを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-147">[PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution) - This feature allows you to pass PowerShell provider paths to native commands that don't support PowerShell path syntax.</span></span>

- <span data-ttu-id="d09a0-148">[PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator) - `-replace` 演算子ステートメントの左側のオペランドが文字列でない場合、そのオペランドは文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-148">[PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator) - When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span> <span data-ttu-id="d09a0-149">機能が有効になっている場合、この変換によって、文字列変換にカルチャ設定が使用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d09a0-149">With the feature enabled, the conversion does not use Culture settings for string conversion.</span></span>

- <span data-ttu-id="d09a0-150">[PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) は、今後の予測 IntelliSense プラグインをサポートするための基礎となります。</span><span class="sxs-lookup"><span data-stu-id="d09a0-150">[PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) lays the groundwork to support future Predictive IntelliSense plug-ins.</span></span>

## <a name="breaking-changes-and-improvements"></a><span data-ttu-id="d09a0-151">破壊的変更と機能強化</span><span class="sxs-lookup"><span data-stu-id="d09a0-151">Breaking Changes and Improvements</span></span>

- <span data-ttu-id="d09a0-152">ネイティブ コマンドによって `stderr` に書き込まれるときに、`$?` が `$false` にならないように修正されました ([#13395](https://github.com/PowerShell/PowerShell/pull/13395))</span><span class="sxs-lookup"><span data-stu-id="d09a0-152">Fix `$?` to not be `$false` when native command writes to `stderr` ([#13395](https://github.com/PowerShell/PowerShell/pull/13395))</span></span>

  <span data-ttu-id="d09a0-153">ネイティブ コマンドは、一般的に、エラーを示すことなく `stderr` に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-153">It is common for native commands to write to `stderr` without intending to indicate a failure.</span></span>
  <span data-ttu-id="d09a0-154">この変更によって `$?` が `$false` に設定されるのは、ネイティブ コマンドに 0 以外の終了コードが含まれている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="d09a0-154">With this change `$?` is set to `$false` only when the native command also has a non-zero exit code.</span></span> <span data-ttu-id="d09a0-155">この変更は、試験的機能 `PSNotApplyErrorActionToStderr` とは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="d09a0-155">This change is unrelated to the experimental feature `PSNotApplyErrorActionToStderr`.</span></span>

- <span data-ttu-id="d09a0-156">`$ErrorActionPreference` がネイティブ コマンドの `stderr` 出力に影響を与えないようになりました ([#13361](https://github.com/PowerShell/PowerShell/pull/13361))</span><span class="sxs-lookup"><span data-stu-id="d09a0-156">Make `$ErrorActionPreference` not affect `stderr` output of native commands ([#13361](https://github.com/PowerShell/PowerShell/pull/13361))</span></span>

  <span data-ttu-id="d09a0-157">ネイティブ コマンドは、一般的に、エラーを示すことなく `stderr` に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-157">It is common for native commands to write to `stderr` without intending to indicate a failure.</span></span>
  <span data-ttu-id="d09a0-158">この変更があっても、`stderr` の出力は **ErrorRecord** オブジェクトで引き続きキャプチャされますが、**ErrorRecord** がネイティブ コマンドから取得された場合、ランタイムによって `$ErrorActionPreference` が適用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d09a0-158">With this change, `stderr` output is still captured in **ErrorRecord** objects, but the runtime no longer applies `$ErrorActionPreference` if the **ErrorRecord** comes from a native command.</span></span>

- <span data-ttu-id="d09a0-159">Unix 時間を入力できるように、`Get-Date` で `-FromUnixTime` の名前が `-UnixTimeSeconds` に変更されました ([#13084](https://github.com/PowerShell/PowerShell/pull/13084)) (@aetos382 に感謝します)</span><span class="sxs-lookup"><span data-stu-id="d09a0-159">Rename `-FromUnixTime` to `-UnixTimeSeconds` on `Get-Date` to allow Unix time input ([#13084](https://github.com/PowerShell/PowerShell/pull/13084)) (Thanks @aetos382!)</span></span>

  <span data-ttu-id="d09a0-160">`-FromUnixTime` パラメーターが 7.1-preview.2 の間に追加されました。</span><span class="sxs-lookup"><span data-stu-id="d09a0-160">The `-FromUnixTime` parameter was added during 7.1-preview.2.</span></span> <span data-ttu-id="d09a0-161">パラメーターの名前が、よりデータ型と一致するように変更されました。</span><span class="sxs-lookup"><span data-stu-id="d09a0-161">The parameter was renamed to better match the data type.</span></span> <span data-ttu-id="d09a0-162">このパラメーターは、1970 年 1 月 1 日 0 時 00 分 00 秒以降の秒数を表す整数値を取ります。</span><span class="sxs-lookup"><span data-stu-id="d09a0-162">This parameter takes an integer value that represents in seconds since January 1, 1970, 0:00:00.</span></span>

  <span data-ttu-id="d09a0-163">この例では、Unix 時間 (1970-01-01 0:00:00 以降の秒数で表されます) を DateTime に変換します。</span><span class="sxs-lookup"><span data-stu-id="d09a0-163">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

  ```powershell
  Get-Date -UnixTimeSeconds 1577836800

  Wednesday, January 01, 2020 12:00:00 AM
  ```

- <span data-ttu-id="d09a0-164">明示的に指定された名前付きパラメーターで、ハッシュテーブル スプラッティングからの同じものを置き換えることができるようになりました (#13162)</span><span class="sxs-lookup"><span data-stu-id="d09a0-164">Allow explicitly specified named parameter to supersede the same one from hashtable splatting (#13162)</span></span>

  <span data-ttu-id="d09a0-165">この変更により、スプラッティングからの名前付きパラメーターは、明示的に指定されたすべての名前付きパラメーターがバインドされた後にバインドされるように、パラメーター リストの末尾に移動されます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-165">With this change, the named parameters from splatting are moved to the end of the parameter list so that they are bound after all explicitly specified named parameters are bound.</span></span> <span data-ttu-id="d09a0-166">単純な関数のパラメーター バインドでは、指定された名前付きパラメーターが見つからない場合のエラーはスローされません。</span><span class="sxs-lookup"><span data-stu-id="d09a0-166">Parameter binding for simple functions doesn't throw an error when a specified named parameter cannot be found.</span></span> <span data-ttu-id="d09a0-167">不明な名前付きパラメーターは、単純な関数の `$args` パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-167">Unknown named parameters are bound to the `$args` parameter of the simple function.</span></span> <span data-ttu-id="d09a0-168">スプラッティングを引数リストの末尾に移動すると、パラメーターが `$args` に表示される順序が変わります。</span><span class="sxs-lookup"><span data-stu-id="d09a0-168">Moving splatting to the end of the argument list changes the order the parameters appears in `$args`.</span></span>

  <span data-ttu-id="d09a0-169">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d09a0-169">For example:</span></span>

  ```powershell
  function SimpleTest {
      param(
          $Name,
          $Path
      )
      "Name: $Name; Path: $Path; Args: $args"
  }
  ```

  <span data-ttu-id="d09a0-170">以前の動作では、**MyPath** が `-Path` にバインドされていません。これは、引数リストの 3 番目の引数であるためです。</span><span class="sxs-lookup"><span data-stu-id="d09a0-170">In the previous behavior, **MyPath** is not bound to `-Path` because it's the third argument in the argument list.</span></span> <span data-ttu-id="d09a0-171">## そのため、`Blah = "World"` と共に '$args' に埋め込まれて終了します</span><span class="sxs-lookup"><span data-stu-id="d09a0-171">## So it ends up being stuffed into '$args' along with `Blah = "World"`</span></span>

  ```powershell
  PS> $hash = @{ Name = "Hello"; Blah = "World" }
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: ; Args: -Blah: World MyPath
  ```

  <span data-ttu-id="d09a0-172">この変更により、`@hash` の引数は引数リストの末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="d09a0-172">With this change, the arguments from `@hash` are moved to the end of the argument list.</span></span> <span data-ttu-id="d09a0-173">**MyPath** がリストの最初の引数になるため、`-Path` にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-173">**MyPath** becomes the first argument in the list, so it is bound to `-Path`.</span></span>

  ```powershell
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: MyPath; Args: -Blah: World
  ```

- <span data-ttu-id="d09a0-174">`Split-Path` でスイッチ パラメーター `-Qualifier` が位置指定ではなくなりました ([#12960](https://github.com/PowerShell/PowerShell/pull/12960)) (@yecril71pl に感謝します)</span><span class="sxs-lookup"><span data-stu-id="d09a0-174">Make the switch parameter `-Qualifier` not positional for `Split-Path` ([#12960](https://github.com/PowerShell/PowerShell/pull/12960)) (Thanks @yecril71pl!)</span></span>

- <span data-ttu-id="d09a0-175">`Start-Process` で、作業ディレクトリが指定されていない場合はリテラル パスとして解決されるようになりました ([#11946](https://github.com/PowerShell/PowerShell/pull/11946)) (@NoMoreFood に感謝します)</span><span class="sxs-lookup"><span data-stu-id="d09a0-175">Resolve the working directory as literal path for `Start-Process` when it's not specified ([#11946](https://github.com/PowerShell/PowerShell/pull/11946)) (Thanks @NoMoreFood!)</span></span>

- <span data-ttu-id="d09a0-176">Web コマンドレットの `-OutFile` パラメーターが `-LiteralPath` のように機能するようになりました ([#11701](https://github.com/PowerShell/PowerShell/pull/11701)) (@iSazonov に感謝します)</span><span class="sxs-lookup"><span data-stu-id="d09a0-176">Make `-OutFile` parameter in web cmdlets to work like `-LiteralPath` ([#11701](https://github.com/PowerShell/PowerShell/pull/11701)) (Thanks @iSazonov!)</span></span>

- <span data-ttu-id="d09a0-177">`BigInteger` 数値リテラルに対する文字列パラメーターのバインドが修正されました ([#11634](https://github.com/PowerShell/PowerShell/pull/11634)) (@vexx32 に感謝します)</span><span class="sxs-lookup"><span data-stu-id="d09a0-177">Fix string parameter binding for `BigInteger` numeric literals ([#11634](https://github.com/PowerShell/PowerShell/pull/11634)) (Thanks @vexx32!)</span></span>

- <span data-ttu-id="d09a0-178">Windows では、`Start-Process` により現在のセッションからのすべての環境変数を使用してプロセス環境が作成され、`-UseNewEnvironment` を使用すると新しい既定のプロセス環境が作成されるようになりました ([#10830](https://github.com/PowerShell/PowerShell/pull/10830)) (@iSazonov に感謝します)</span><span class="sxs-lookup"><span data-stu-id="d09a0-178">On Windows, `Start-Process` creates a process environment with all the environment variables from current session, using `-UseNewEnvironment` creates a new default process environment ([#10830](https://github.com/PowerShell/PowerShell/pull/10830)) (Thanks @iSazonov!)</span></span>

- <span data-ttu-id="d09a0-179">`ScriptBlock` をデリゲートに変換するときに、`PSObject` の戻り値の結果が折り返されなくなりました ([#10619](https://github.com/PowerShell/PowerShell/pull/10619))</span><span class="sxs-lookup"><span data-stu-id="d09a0-179">Do not wrap return result in `PSObject` when converting a `ScriptBlock` to a delegate ([#10619](https://github.com/PowerShell/PowerShell/pull/10619))</span></span>

  <span data-ttu-id="d09a0-180">`ScriptBlock` が C# コンテキストで使用されるデリゲート型に変換されるときに `PSObject` の結果を折り返すと、次のような望まない問題が生じます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-180">When a `ScriptBlock` is converted to a delegate type to be used in C# context, wrapping the result in a `PSObject` brings unneeded troubles:</span></span>

  - <span data-ttu-id="d09a0-181">値がデリゲートの戻り値の型に変換されると、基本的に `PSObject` の折り返しが解除されます。</span><span class="sxs-lookup"><span data-stu-id="d09a0-181">When the value is converted to the delegate return type, the `PSObject` essentially gets unwrapped.</span></span> <span data-ttu-id="d09a0-182">そのため、`PSObject` は不要です。</span><span class="sxs-lookup"><span data-stu-id="d09a0-182">So the `PSObject` is unneeded.</span></span>
  - <span data-ttu-id="d09a0-183">デリゲートの戻り値の型が `object` の場合、`PSObject` で折り返され、C# コード内での操作が困難になります。</span><span class="sxs-lookup"><span data-stu-id="d09a0-183">When the delegate return type is `object`, it gets wrapped in a `PSObject` making it hard to work with in C# code.</span></span>

  <span data-ttu-id="d09a0-184">この変更後、返されるオブジェクトが基になるオブジェクトになります。</span><span class="sxs-lookup"><span data-stu-id="d09a0-184">After this change, the returned object is the underlying object.</span></span>

---
ms.date: 02/03/2020
keywords: powershell、core
title: PowerShell Core 6.0 の重要な変更
ms.openlocfilehash: 47ed14cceed86e4dd04a8e0079af00f6a98988ea
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "76995459"
---
# <a name="breaking-changes-for-powershell-6x"></a><span data-ttu-id="80920-103">PowerShell 6.x の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="80920-103">Breaking Changes for PowerShell 6.x</span></span>

## <a name="features-no-longer-available-in-powershell-core"></a><span data-ttu-id="80920-104">PowerShell Core で使用できなくなった機能</span><span class="sxs-lookup"><span data-stu-id="80920-104">Features no longer available in PowerShell Core</span></span>

### <a name="modules-not-shipped-for-powershell-6x"></a><span data-ttu-id="80920-105">PowerShell 6.x に付属しないモジュール</span><span class="sxs-lookup"><span data-stu-id="80920-105">Modules not shipped for PowerShell 6.x</span></span>

<span data-ttu-id="80920-106">互換性に関するさまざまな理由から、次のモジュールは PowerShell 6 には含まれません。</span><span class="sxs-lookup"><span data-stu-id="80920-106">For various compatibility reasons, the following modules are not included in PowerShell 6.</span></span>

- <span data-ttu-id="80920-107">ISE</span><span class="sxs-lookup"><span data-stu-id="80920-107">ISE</span></span>
- <span data-ttu-id="80920-108">Microsoft.PowerShell.LocalAccounts</span><span class="sxs-lookup"><span data-stu-id="80920-108">Microsoft.PowerShell.LocalAccounts</span></span>
- <span data-ttu-id="80920-109">Microsoft.PowerShell.ODataUtils</span><span class="sxs-lookup"><span data-stu-id="80920-109">Microsoft.PowerShell.ODataUtils</span></span>
- <span data-ttu-id="80920-110">Microsoft.PowerShell.Operation.Validation</span><span class="sxs-lookup"><span data-stu-id="80920-110">Microsoft.PowerShell.Operation.Validation</span></span>
- <span data-ttu-id="80920-111">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="80920-111">PSScheduledJob</span></span>
- <span data-ttu-id="80920-112">PSWorkflow</span><span class="sxs-lookup"><span data-stu-id="80920-112">PSWorkflow</span></span>
- <span data-ttu-id="80920-113">PSWorkflowUtility</span><span class="sxs-lookup"><span data-stu-id="80920-113">PSWorkflowUtility</span></span>

### <a name="powershell-workflow"></a><span data-ttu-id="80920-114">PowerShell ワークフロー</span><span class="sxs-lookup"><span data-stu-id="80920-114">PowerShell Workflow</span></span>

<span data-ttu-id="80920-115">[PowerShell ワークフロー][workflow]は、[Windows Workflow Foundation (WF)][workflow-foundation] をベースに構築された Windows PowerShell の機能です。これを使うと、実行時間の長いタスクや並列化されたタスクのための堅牢な Runbook を作成できます。</span><span class="sxs-lookup"><span data-stu-id="80920-115">[PowerShell Workflow][workflow] is a feature in Windows PowerShell that builds on top of [Windows Workflow Foundation (WF)][workflow-foundation] that enables the creation of robust runbooks for long-running or parallelized tasks.</span></span>

<span data-ttu-id="80920-116">.NET Core では Windows Workflow Foundation がサポートされていないため、PowerShell Core では PowerShell ワークフローはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="80920-116">Due to the lack of support for Windows Workflow Foundation in .NET Core, we are not supporting PowerShell Workflow in PowerShell Core.</span></span>

<span data-ttu-id="80920-117">今後、PowerShell ワークフローを必要としない、PowerShell 言語でのネイティブの並列処理とコンカレンシーが可能になる予定です。</span><span class="sxs-lookup"><span data-stu-id="80920-117">In the future, we would like to enable native parallelism/concurrency in the PowerShell language without the need for PowerShell Workflow.</span></span>

<span data-ttu-id="80920-118">OS の再起動後にチェックポイントを使ってスクリプトを再開する必要がある場合は、タスク スケジューラを使って OS の起動時にスクリプトを実行することをお勧めします。ただし、そのスクリプトでそれ自体の状態を維持する必要があります (ファイルに保持するなど)。</span><span class="sxs-lookup"><span data-stu-id="80920-118">If there is a need to use checkpoints to resume a script after the OS restarts, we recommend using Task Scheduler to run a script on OS startup, but the script would need to maintain its own state (like persisting it to a file).</span></span>

[workflow]: /powershell/scripting/components/workflows-guide
[workflow-foundation]: https://docs.microsoft.com/dotnet/framework/windows-workflow-foundation/

### <a name="custom-snap-ins"></a><span data-ttu-id="80920-119">カスタム スナップイン</span><span class="sxs-lookup"><span data-stu-id="80920-119">Custom snap-ins</span></span>

<span data-ttu-id="80920-120">[PowerShell スナップイン][snapin]は、PowerShell モジュールの前身ですが、PowerShell コミュニティではあまり使用されていません。</span><span class="sxs-lookup"><span data-stu-id="80920-120">[PowerShell snap-ins][snapin] are a predecessor to PowerShell modules that do not have widespread adoption in the PowerShell community.</span></span>

<span data-ttu-id="80920-121">スナップインのサポートは複雑であり、コミュニティ内での普及率が低いことから、PowerShell Core でのカスタム スナップインのサポートを終了します。</span><span class="sxs-lookup"><span data-stu-id="80920-121">Due to the complexity of supporting snap-ins and their lack of usage in the community, we no longer support custom snap-ins in PowerShell Core.</span></span>

<span data-ttu-id="80920-122">現時点では、Windows および Windows Server 内の `ActiveDirectory` および `DnsClient` モジュールに影響します。</span><span class="sxs-lookup"><span data-stu-id="80920-122">Today, this breaks the `ActiveDirectory` and `DnsClient` modules in Windows and Windows Server.</span></span>

[snapin]: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins

### <a name="wmi-v1-cmdlets"></a><span data-ttu-id="80920-123">WMI v1 コマンドレット</span><span class="sxs-lookup"><span data-stu-id="80920-123">WMI v1 cmdlets</span></span>

<span data-ttu-id="80920-124">WMI ベースの 2 つのモジュール セットをサポートすることは複雑になるため、PowerShell Core から WMI v1 コマンドレットが削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-124">Due to the complexity of supporting two sets of WMI-based modules, we removed the WMI v1 cmdlets from PowerShell Core:</span></span>

- `Register-WmiEvent`
- `Set-WmiInstance`
- `Invoke-WmiMethod`
- `Get-WmiObject`
- `Remove-WmiObject`

<span data-ttu-id="80920-125">これに代わり、新しい機能や再設計された構文を含み、同じ機能を提供する CIM (別名 WMI v2) コマンドレットを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80920-125">Instead, we recommend that you the use the CIM (aka WMI v2) cmdlets which provide the same functionality with new functionality and a redesigned syntax:</span></span>

- `Get-CimAssociatedInstance`
- `Get-CimClass`
- `Get-CimInstance`
- `Get-CimSession`
- `Invoke-CimMethod`
- `New-CimInstance`
- `New-CimSession`
- `New-CimSessionOption`
- `Register-CimIndicationEvent`
- `Remove-CimInstance`
- `Remove-CimSession`
- `Set-CimInstance`

### <a name="microsoftpowershelllocalaccounts"></a><span data-ttu-id="80920-126">Microsoft.PowerShell.LocalAccounts</span><span class="sxs-lookup"><span data-stu-id="80920-126">Microsoft.PowerShell.LocalAccounts</span></span>

<span data-ttu-id="80920-127">サポートされていない API を使用していることから、より優れたソリューションが提供されるまで、PowerShell Core から `Microsoft.PowerShell.LocalAccounts` コマンドレットを削除します。</span><span class="sxs-lookup"><span data-stu-id="80920-127">Due to the use of unsupported APIs, `Microsoft.PowerShell.LocalAccounts` has been removed from PowerShell Core until a better solution is found.</span></span>

### <a name="new-webserviceproxy-cmdlet-removed"></a><span data-ttu-id="80920-128">`New-WebServiceProxy` コマンドレットが削除された</span><span class="sxs-lookup"><span data-stu-id="80920-128">`New-WebServiceProxy` cmdlet removed</span></span>

<span data-ttu-id="80920-129">.NET Core では、SOAP プロトコルを使用するためのサービスを提供する Windows Communication Framework はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="80920-129">.NET Core does not support the Windows Communication Framework, which provide services for using the SOAP protocol.</span></span> <span data-ttu-id="80920-130">このコマンドレットは、SOAP を必要とするため削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-130">This cmdlet was removed because it requires SOAP.</span></span>

### <a name="-transaction-cmdlets-removed"></a><span data-ttu-id="80920-131">`*-Transaction` コマンドレットの削除</span><span class="sxs-lookup"><span data-stu-id="80920-131">`*-Transaction` cmdlets removed</span></span>

<span data-ttu-id="80920-132">以下のコマンドレットの使用方法は非常に限られていました。</span><span class="sxs-lookup"><span data-stu-id="80920-132">These cmdlets had very limited usage.</span></span> <span data-ttu-id="80920-133">これらのサポートを中止することが決定されました。</span><span class="sxs-lookup"><span data-stu-id="80920-133">The decision was made to discontinue support for them.</span></span>

- `Complete-Transaction`
- `Get-Transaction`
- `Start-Transaction`
- `Undo-Transaction`
- `Use-Transaction`

### <a name="security-cmdlets-not-available-on-non-windows-platforms"></a><span data-ttu-id="80920-134">Windows 以外のプラットフォームで使用できないセキュリティ コマンドレット</span><span class="sxs-lookup"><span data-stu-id="80920-134">Security cmdlets not available on non-Windows platforms</span></span>

- `Get-Acl`
- `Set-Acl`
- `Get-AuthenticodeSignature`
- `Set-AuthenticodeSignature`
- `Get-CmsMessage`
- `Protect-CmsMessage`
- `Unprotect-CmsMessage`
- `New-FileCatalog`
- `Test-FileCatalog`

### <a name="-computerand-other-windows-specific-cmdlets"></a><span data-ttu-id="80920-135">`*-Computer` およびその他の Windows 専用コマンドレット</span><span class="sxs-lookup"><span data-stu-id="80920-135">`*-Computer`and other Windows-specific cmdlets</span></span>

<span data-ttu-id="80920-136">以下のコマンドレットは、サポートされていない API が使われているため、より優れたソリューションが提供されるまで PowerShell Core から削除されます。</span><span class="sxs-lookup"><span data-stu-id="80920-136">Due to the use of unsupported APIs, the following cmdlets have been removed from PowerShell Core until a better solution is found.</span></span>

- `Get-Clipboard`
- `Set-Clipboard`
- `Add-Computer`
- `Checkpoint-Computer`
- `Remove-Computer`
- `Restore-Computer`
- `Reset-ComputerMachinePassword`
- `Disable-ComputerRestore`
- `Enable-ComputerRestore`
- `Get-ComputerRestorePoint`
- `Test-ComputerSecureChannel`
- `Get-ControlPanelItem`
- `Show-ControlPanelItem`
- `Get-HotFix`
- `Clear-RecycleBin`
- `Update-List`
- `Out-Printer`
- `ConvertFrom-String`
- `Convert-String`

### <a name="-counter-cmdlets"></a><span data-ttu-id="80920-137">`*-Counter` コマンドレット</span><span class="sxs-lookup"><span data-stu-id="80920-137">`*-Counter` cmdlets</span></span>

<span data-ttu-id="80920-138">サポートされていない API を使用していることから、より優れたソリューションが提供されるまで、PowerShell Core から `*-Counter` コマンドレットを削除します。</span><span class="sxs-lookup"><span data-stu-id="80920-138">Due to the use of unsupported APIs, the `*-Counter` has been removed from PowerShell Core until a better solution is found.</span></span>

### <a name="-eventlog-cmdlets"></a><span data-ttu-id="80920-139">`*-EventLog` コマンドレット</span><span class="sxs-lookup"><span data-stu-id="80920-139">`*-EventLog` cmdlets</span></span>

<span data-ttu-id="80920-140">サポートされていない API を使用しているため、より優れたソリューションが提供されるまで、PowerShell Core から `*-EventLog` コマンドレットを削除しています</span><span class="sxs-lookup"><span data-stu-id="80920-140">Due to the use of unsupported APIs, the `*-EventLog` has been removed from PowerShell Core.</span></span> <span data-ttu-id="80920-141">。</span><span class="sxs-lookup"><span data-stu-id="80920-141">until a better solution is found.</span></span> <span data-ttu-id="80920-142">`Get-WinEvent` と `Create-WinEvent` を使用すると、Windows でイベントを取得および作成することができます。</span><span class="sxs-lookup"><span data-stu-id="80920-142">`Get-WinEvent` and `Create-WinEvent` are available to get and create events on Windows.</span></span>

### <a name="cmdlets-that-use-wpf-removed"></a><span data-ttu-id="80920-143">WPF を使用するコマンドレットの削除</span><span class="sxs-lookup"><span data-stu-id="80920-143">Cmdlets that use WPF removed</span></span>

<span data-ttu-id="80920-144">Windows Presentation Framework は、CoreCLR ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="80920-144">The Windows Presentation Framework is not supported on CoreCLR.</span></span> <span data-ttu-id="80920-145">以下のコマンドレットが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="80920-145">The following cmdlets are affected:</span></span>

- `Show-Command`
- `Out-GridView`
- <span data-ttu-id="80920-146">`Get-Help` の **showwindow** パラメーター</span><span class="sxs-lookup"><span data-stu-id="80920-146">The **showwindow** parameter of `Get-Help`</span></span>

### <a name="some-dsc-cmdlets-removed"></a><span data-ttu-id="80920-147">一部の DSC コマンドレットの削除</span><span class="sxs-lookup"><span data-stu-id="80920-147">Some DSC cmdlets removed</span></span>

- `Get-DscConfiguration`
- `Publish-DscConfiguration`
- `Restore-DscConfiguration`
- `Start-DscConfiguration`
- `Stop-DscConfiguration`
- `Test-DscConfiguration`
- `Update-DscConfiguration`
- `Remove-DscConfigurationDocument`
- `Get-DscConfigurationStatus`
- `Disable-DscDebug`
- `Enable-DscDebug`
- `Get-DscLocalConfigurationManager`
- `Set-DscLocalConfigurationManager`
- `Invoke-DscResource`

## <a name="enginelanguage-changes"></a><span data-ttu-id="80920-148">エンジンおよび言語の変更</span><span class="sxs-lookup"><span data-stu-id="80920-148">Engine/language changes</span></span>

### <a name="rename-powershellexe-to-pwshexe-5101"></a><span data-ttu-id="80920-149">`powershell.exe` から `pwsh.exe` への名前変更 [#5101](https://github.com/PowerShell/PowerShell/issues/5101)</span><span class="sxs-lookup"><span data-stu-id="80920-149">Rename `powershell.exe` to `pwsh.exe` [#5101](https://github.com/PowerShell/PowerShell/issues/5101)</span></span>

<span data-ttu-id="80920-150">ユーザーが (Windows PowerShell ではなく) Windows 上で PowerShell Core を確実な方法で呼び出せるよう、PowerShell Core のバイナリが Windows では `pwsh.exe` に、Windows 以外のプラットフォームでは `pwsh` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-150">In order to give users a deterministic way to call PowerShell Core on Windows (as opposed to Windows PowerShell), the PowerShell Core binary was changed to `pwsh.exe` on Windows and `pwsh` on non-Windows platforms.</span></span>

<span data-ttu-id="80920-151">短い形式の名前も、Windows 以外のプラットフォーム上のシェルの名前形式と同じになるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="80920-151">The shortened name is also consistent with naming of shells on non-Windows platforms.</span></span>

### <a name="dont-insert-line-breaks-to-output-except-for-tables-5193"></a><span data-ttu-id="80920-152">出力 (テーブル以外) に改行を挿入できない。[#5193](https://github.com/PowerShell/PowerShell/issues/5193)</span><span class="sxs-lookup"><span data-stu-id="80920-152">Don't insert line breaks to output (except for tables) [#5193](https://github.com/PowerShell/PowerShell/issues/5193)</span></span>

<span data-ttu-id="80920-153">以前は、コンソールの幅に合わせて出力が調整され、コンソールの幅の終端に改行が追加されていたため、ターミナルのサイズが変更されると、想定外の形式になることがありました。</span><span class="sxs-lookup"><span data-stu-id="80920-153">Previously, output was aligned to the width of the console and line breaks were added at the end width of the console, meaning the output didn't get reformatted as expected if the terminal was resized.</span></span> <span data-ttu-id="80920-154">今回の変更は、列の整列に改行が必要なため、テーブルには適用されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="80920-154">This change was not applied to tables, as the line breaks are necessary to keep the columns aligned.</span></span>

### <a name="skip-null-element-check-for-collections-with-a-value-type-element-type-5432"></a><span data-ttu-id="80920-155">要素の型が値型のコレクションの null 要素チェックを省略 [#5432](https://github.com/PowerShell/PowerShell/issues/5432)</span><span class="sxs-lookup"><span data-stu-id="80920-155">Skip null-element check for collections with a value-type element type [#5432](https://github.com/PowerShell/PowerShell/issues/5432)</span></span>

<span data-ttu-id="80920-156">`Mandatory`パラメーターと `ValidateNotNull` および `ValidateNotNullOrEmpty` 属性について、コレクションの要素の型が値型の場合に null 要素チェックを省略します。</span><span class="sxs-lookup"><span data-stu-id="80920-156">For the `Mandatory` parameter and `ValidateNotNull` and `ValidateNotNullOrEmpty` attributes, skip the null-element check if the collection's element type is value type.</span></span>

### <a name="change-outputencoding-to-use-utf-8-nobom-encoding-rather-than-ascii-5369"></a><span data-ttu-id="80920-157">ASCIIではなく `UTF-8 NoBOM` エンコードを使用するよう `$OutputEncoding` を変更 [#5369](https://github.com/PowerShell/PowerShell/issues/5369)</span><span class="sxs-lookup"><span data-stu-id="80920-157">Change `$OutputEncoding` to use `UTF-8 NoBOM` encoding rather than ASCII [#5369](https://github.com/PowerShell/PowerShell/issues/5369)</span></span>

<span data-ttu-id="80920-158">以前のエンコード、ASCII (7 ビット) を使用すると、出力が不適切に変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="80920-158">The previous encoding, ASCII (7-bit), would result in incorrect alteration of the output in some cases.</span></span> <span data-ttu-id="80920-159">今回の変更では、`UTF-8 NoBOM` が既定値となり、ほとんどのツールおよびオペレーティング システムでサポートされているエンコードを使用して Unicode 出力を保持します。</span><span class="sxs-lookup"><span data-stu-id="80920-159">This change is to make `UTF-8 NoBOM` default, which preserves Unicode output with an encoding supported by most tools and operating systems.</span></span>

### <a name="remove-allscope-from-most-default-aliases-5268"></a><span data-ttu-id="80920-160">大部分の既定エイリアスから `AllScope` を削除 [#5268](https://github.com/PowerShell/PowerShell/issues/5268)</span><span class="sxs-lookup"><span data-stu-id="80920-160">Remove `AllScope` from most default aliases [#5268](https://github.com/PowerShell/PowerShell/issues/5268)</span></span>

<span data-ttu-id="80920-161">スコープの作成を高速化するために、大部分の既定エイリアスから `AllScope` が削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-161">To speed up scope creation, `AllScope` was removed from most default aliases.</span></span> <span data-ttu-id="80920-162">検索が高速化できる使用頻度の高いいくつかのエイリアスでは `AllScope` のままになっています。</span><span class="sxs-lookup"><span data-stu-id="80920-162">`AllScope` was left for a few frequently used aliases where the lookup was faster.</span></span>

### <a name="-verbose-and--debug-no-longer-overrides-erroractionpreference-5113"></a><span data-ttu-id="80920-163">`-Verbose` および `-Debug` による `$ErrorActionPreference` のオーバーライドの終了 [#5113](https://github.com/PowerShell/PowerShell/issues/5113)</span><span class="sxs-lookup"><span data-stu-id="80920-163">`-Verbose` and `-Debug` no longer overrides `$ErrorActionPreference` [#5113](https://github.com/PowerShell/PowerShell/issues/5113)</span></span>

<span data-ttu-id="80920-164">以前は、`-Verbose` または `-Debug` が指定された場合、それにより `$ErrorActionPreference` の動作がオーバーライドされていました。</span><span class="sxs-lookup"><span data-stu-id="80920-164">Previously, if `-Verbose` or `-Debug` were specified, it overrode the behavior of `$ErrorActionPreference`.</span></span> <span data-ttu-id="80920-165">今回の変更により、`-Verbose` および `-Debug` が `$ErrorActionPreference` の動作に影響を与えることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="80920-165">With this change, `-Verbose` and `-Debug` no longer affect the behavior of `$ErrorActionPreference`.</span></span>

## <a name="cmdlet-changes"></a><span data-ttu-id="80920-166">コマンドレットの変更</span><span class="sxs-lookup"><span data-stu-id="80920-166">Cmdlet changes</span></span>

### <a name="invoke-restmethod-doesnt-return-useful-info-when-no-data-is-returned-5320"></a><span data-ttu-id="80920-167">データが返されない場合、Invoke-RestMethod により、有益な情報が返されない</span><span class="sxs-lookup"><span data-stu-id="80920-167">Invoke-RestMethod doesn't return useful info when no data is returned.</span></span> [<span data-ttu-id="80920-168">#5320</span><span class="sxs-lookup"><span data-stu-id="80920-168">#5320</span></span>](https://github.com/PowerShell/PowerShell/issues/5320)

<span data-ttu-id="80920-169">API が `null` のみを返す場合、Invoke-restmethod は、これを `$null` ではなく、文字列 `"null"` としてシリアル化していました。</span><span class="sxs-lookup"><span data-stu-id="80920-169">When an API returns just `null`, Invoke-RestMethod was serializing this as the string `"null"` instead of `$null`.</span></span> <span data-ttu-id="80920-170">今回の変更により、有効なシングル値 JSON `null` がリテラル `$null` として正しくシリアル化されるよう、`Invoke-RestMethod` のロジックが修正されました。</span><span class="sxs-lookup"><span data-stu-id="80920-170">This change fixes the logic in `Invoke-RestMethod` to properly serialize a valid single value JSON `null` literal as `$null`.</span></span>

### <a name="remove--protocol-from--computer-cmdlets-5277"></a><span data-ttu-id="80920-171">`*-Computer` コマンドレットから `-Protocol` を削除 [#5277](https://github.com/PowerShell/PowerShell/issues/5277)</span><span class="sxs-lookup"><span data-stu-id="80920-171">Remove `-Protocol` from `*-Computer` cmdlets [#5277](https://github.com/PowerShell/PowerShell/issues/5277)</span></span>

<span data-ttu-id="80920-172">CoreFX の RPC リモート処理 (特に Windows 以外のプラットフォームで) の問題と、PowerShell で一貫性のあるリモート処理エクスペリエンスを保証するため、`\*-Computer` コマンドレットから `-Protocol` パラメーターが削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-172">Due to issues with RPC remoting in CoreFX (particularly on non-Windows platforms) and ensuring a consistent remoting experience in PowerShell, the `-Protocol` parameter was removed from the `\*-Computer` cmdlets.</span></span> <span data-ttu-id="80920-173">リモート処理では DCOM がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="80920-173">DCOM is no longer supported for remoting.</span></span> <span data-ttu-id="80920-174">次のコマンドレットでは、WSMAN リモート処理のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="80920-174">The following cmdlets only support WSMAN remoting:</span></span>

- <span data-ttu-id="80920-175">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="80920-175">Rename-Computer</span></span>
- <span data-ttu-id="80920-176">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="80920-176">Restart-Computer</span></span>
- <span data-ttu-id="80920-177">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="80920-177">Stop-Computer</span></span>

### <a name="remove--computername-from--service-cmdlets-5090"></a><span data-ttu-id="80920-178">`*-Service` コマンドレットから `-ComputerName` を削除 [#5090](https://github.com/PowerShell/PowerShell/issues/5094)</span><span class="sxs-lookup"><span data-stu-id="80920-178">Remove `-ComputerName` from `*-Service` cmdlets [#5090](https://github.com/PowerShell/PowerShell/issues/5094)</span></span>

<span data-ttu-id="80920-179">一貫性のある PSRP の使用を促進するために、`*-Service` コマンドレットから `-ComputerName` パラメーターが削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-179">In order to encourage the consistent use of PSRP, the `-ComputerName` parameter was removed from `*-Service` cmdlets.</span></span>

### <a name="fix-get-item--literalpath-ab-if-ab-doesnt-actually-exist-to-return-error-5197"></a><span data-ttu-id="80920-180">`a*b` が実際に存在しない場合は、エラーを返すよう `Get-Item -LiteralPath a*b` を修正 [#5197](https://github.com/PowerShell/PowerShell/issues/5197)</span><span class="sxs-lookup"><span data-stu-id="80920-180">Fix `Get-Item -LiteralPath a*b` if `a*b` doesn't actually exist to return error [#5197](https://github.com/PowerShell/PowerShell/issues/5197)</span></span>

<span data-ttu-id="80920-181">以前は、ワイルドカードを渡された `-LiteralPath` は `-Path` と同様に処理され、ワイルドカードを使ってファイルが検出されない場合は、何も返さず終了していました。</span><span class="sxs-lookup"><span data-stu-id="80920-181">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="80920-182">正しい動作として、ファイルが存在しない場合はエラーを返すには、`-LiteralPath` はリテラルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="80920-182">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="80920-183">`-Literal` にワイルドカードを使用した場合、リテラルとして処理するよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-183">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="import-csv-should-apply-pstypenames-upon-import-when-type-information-is-present-in-the-csv-5134"></a><span data-ttu-id="80920-184">インポート時に CSV に型情報が存在する場合、`Import-Csv` が `PSTypeNames` を適用 [#5134](https://github.com/PowerShell/PowerShell/issues/5134)</span><span class="sxs-lookup"><span data-stu-id="80920-184">`Import-Csv` should apply `PSTypeNames` upon import when type information is present in the CSV [#5134](https://github.com/PowerShell/PowerShell/issues/5134)</span></span>

<span data-ttu-id="80920-185">以前は、`ConvertFrom-Csv` を使用してインポートされた `TypeInformation` を含む `Export-CSV` を使用してオブジェクトをエクスポートすると、型情報が保持されませんでした。</span><span class="sxs-lookup"><span data-stu-id="80920-185">Previously, objects exported using `Export-CSV` with `TypeInformation` imported with `ConvertFrom-Csv` were not retaining the type information.</span></span> <span data-ttu-id="80920-186">今回の変更により、CSV ファイルから使用可能な場合は `PSTypeNames` メンバーに型情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="80920-186">This change adds the type information to `PSTypeNames` member if available from the CSV file.</span></span>

### <a name="-notypeinformation-should-be-default-on-export-csv-5131"></a><span data-ttu-id="80920-187">`-NoTypeInformation` の既定値を `Export-Csv` に設定 [#5131](https://github.com/PowerShell/PowerShell/issues/5131)</span><span class="sxs-lookup"><span data-stu-id="80920-187">`-NoTypeInformation` should be default on `Export-Csv` [#5131](https://github.com/PowerShell/PowerShell/issues/5131)</span></span>

<span data-ttu-id="80920-188">お客様からの声を反映して、`Export-CSV` の既定の動作として型情報を含めるよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-188">This change was made to address customer feedback on the default behavior of `Export-CSV` to include type information.</span></span>

<span data-ttu-id="80920-189">以前は、コマンドレットから、オブジェクトの型名を含む最初の行としてコメントが出力されていました。</span><span class="sxs-lookup"><span data-stu-id="80920-189">Previously, the cmdlet would output a comment as the first line containing the type name of the object.</span></span> <span data-ttu-id="80920-190">ほとんどのツールでは認識されないため、既定ではこれを抑制されるよう変更されています。</span><span class="sxs-lookup"><span data-stu-id="80920-190">The change is to suppress this by default as it's not understood by most tools.</span></span> <span data-ttu-id="80920-191">以前の動作のままにするには、`-IncludeTypeInformation` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="80920-191">Use `-IncludeTypeInformation` to retain the previous behavior.</span></span>

### <a name="web-cmdlets-should-warn-when--credential-is-sent-over-unencrypted-connections-5112"></a><span data-ttu-id="80920-192">暗号化されていない接続経由で `-Credential` が送信された場合に、Web コマンドレットが警告 [#5112](https://github.com/PowerShell/PowerShell/issues/5112)</span><span class="sxs-lookup"><span data-stu-id="80920-192">Web Cmdlets should warn when `-Credential` is sent over unencrypted connections [#5112](https://github.com/PowerShell/PowerShell/issues/5112)</span></span>

<span data-ttu-id="80920-193">HTTP を使用する場合、パスワードなどのコンテンツはクリア テキストとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="80920-193">When using HTTP, content including passwords are sent as clear-text.</span></span> <span data-ttu-id="80920-194">今回の変更は、これを既定で許可しないようにするもので、資格情報が安全でない方法で渡されると、エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="80920-194">This change is to not allow this by default and return an error if credentials are being passed in an insecure manner.</span></span> <span data-ttu-id="80920-195">`-AllowUnencryptedAuthentication` スイッチを使用すると、この動作を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="80920-195">Users can bypass this by using the `-AllowUnencryptedAuthentication` switch.</span></span>

## <a name="api-changes"></a><span data-ttu-id="80920-196">API の変更</span><span class="sxs-lookup"><span data-stu-id="80920-196">API changes</span></span>

### <a name="remove-addtypecommandbase-class-5407"></a><span data-ttu-id="80920-197">`AddTypeCommandBase` クラスを削除 [#5407](https://github.com/PowerShell/PowerShell/issues/5407)</span><span class="sxs-lookup"><span data-stu-id="80920-197">Remove `AddTypeCommandBase` class [#5407](https://github.com/PowerShell/PowerShell/issues/5407)</span></span>

<span data-ttu-id="80920-198">パフォーマンス向上のため、`Add-Type` から `AddTypeCommandBase` クラスが削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-198">The `AddTypeCommandBase` class was removed from `Add-Type` to improve performance.</span></span> <span data-ttu-id="80920-199">このクラスは、Add-Type コマンドレットでのみ使用されており、ユーザーに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="80920-199">This class is only used by the Add-Type cmdlet and should not impact users.</span></span>

### <a name="unify-cmdlets-with-parameter--encoding-to-be-of-type-systemtextencoding-5080"></a><span data-ttu-id="80920-200">コマンドレットと `-Encoding` パラメーターを `System.Text.Encoding` 型に統合 [#5080](https://github.com/PowerShell/PowerShell/issues/5080)</span><span class="sxs-lookup"><span data-stu-id="80920-200">Unify cmdlets with parameter `-Encoding` to be of type `System.Text.Encoding` [#5080](https://github.com/PowerShell/PowerShell/issues/5080)</span></span>

<span data-ttu-id="80920-201">`-Encoding` の値 `Byte`はファイルシステム プロバイダーのコマンドレットから削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-201">The `-Encoding` value `Byte` has been removed from the filesystem provider cmdlets.</span></span> <span data-ttu-id="80920-202">新しいパラメーター `-AsByteStream` を使用して、入力としてバイト ストリームが必要なこと、あるいは出力がバイト ストリームであることを指定してください。</span><span class="sxs-lookup"><span data-stu-id="80920-202">A new parameter, `-AsByteStream`, is now used to specify that a byte stream is required as input or that the output is a stream of bytes.</span></span>

### <a name="add-better-error-message-for-empty-and-null--uformat-parameter-5055"></a><span data-ttu-id="80920-203">`-UFormat` パラメーターが空または null の場合に、改善されたエラー メッセージを追加 [#5055](https://github.com/PowerShell/PowerShell/issues/5055)</span><span class="sxs-lookup"><span data-stu-id="80920-203">Add better error message for empty and null `-UFormat` parameter [#5055](https://github.com/PowerShell/PowerShell/issues/5055)</span></span>

<span data-ttu-id="80920-204">以前は、`-UFormat` に空の形式の文字列が渡されると、有益でないエラー メッセージが表示されていました。</span><span class="sxs-lookup"><span data-stu-id="80920-204">Previously, when passing an empty format string to `-UFormat`, an unhelpful error message would appear.</span></span> <span data-ttu-id="80920-205">よりわかりやすいエラーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="80920-205">A more descriptive error has been added.</span></span>

### <a name="clean-up-console-code-4995"></a><span data-ttu-id="80920-206">コンソール コードをクリーンアップ [#4995](https://github.com/PowerShell/PowerShell/issues/4995)</span><span class="sxs-lookup"><span data-stu-id="80920-206">Clean up console code [#4995](https://github.com/PowerShell/PowerShell/issues/4995)</span></span>

<span data-ttu-id="80920-207">`-psconsolefile` スイッチおよびコード、`-importsystemmodules` スイッチおよびコード、およびフォントの変更コードは、レガシーの Windows PowerShell のために存在し、PowerShell Core でサポートされておらず、今後もサポートを追加する予定がないため、削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-207">The following features were removed as they are not supported in PowerShell Core, and there are no plans to add support as they exist for legacy reasons for Windows PowerShell: `-psconsolefile` switch and code, `-importsystemmodules` switch and code, and font changing code.</span></span>

### <a name="removed-runspaceconfiguration-support-4942"></a><span data-ttu-id="80920-208">`RunspaceConfiguration` のサポートを終了 [#4942](https://github.com/PowerShell/PowerShell/issues/4942)</span><span class="sxs-lookup"><span data-stu-id="80920-208">Removed `RunspaceConfiguration` support [#4942](https://github.com/PowerShell/PowerShell/issues/4942)</span></span>

<span data-ttu-id="80920-209">以前は、API を使用してプログラムで PowerShell 実行空間を作成する場合、従来の [`RunspaceConfiguration`][runspaceconfig] か新しい [`InitialSessionState`][iss] を使用できました。</span><span class="sxs-lookup"><span data-stu-id="80920-209">Previously, when creating a PowerShell runspace programmatically using the API you could use the legacy [`RunspaceConfiguration`][runspaceconfig] or the newer [`InitialSessionState`][iss].</span></span> <span data-ttu-id="80920-210">今回の変更により `RunspaceConfiguration` のサポートが終了し、`InitialSessionState` のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="80920-210">This change removed support for `RunspaceConfiguration` and only supports `InitialSessionState`.</span></span>

[runspaceconfig]: https://docs.microsoft.com/dotnet/api/system.management.automation.runspaces.runspaceconfiguration
[iss]: https://docs.microsoft.com/dotnet/api/system.management.automation.runspaces.initialsessionstate

### <a name="commandinvocationintrinsicsinvokescript-bind-arguments-to-input-instead-of-args-4923"></a><span data-ttu-id="80920-211">`CommandInvocationIntrinsics.InvokeScript` が引数を `$input` ではなく `$args` にバインド [#4923](https://github.com/PowerShell/PowerShell/issues/4923)</span><span class="sxs-lookup"><span data-stu-id="80920-211">`CommandInvocationIntrinsics.InvokeScript` bind arguments to `$input` instead of `$args` [#4923](https://github.com/PowerShell/PowerShell/issues/4923)</span></span>

<span data-ttu-id="80920-212">引数内のパラメーターの位置が正しくないため、引数ではなく入力として渡されていました。</span><span class="sxs-lookup"><span data-stu-id="80920-212">An incorrect position of a parameter resulted in the args passed as input instead of as args.</span></span>

### <a name="remove-unsupported--showwindow-switch-from-get-help-4903"></a><span data-ttu-id="80920-213">サポートされていなかった `-showwindow` スイッチを `Get-Help` から削除 [#4903](https://github.com/PowerShell/PowerShell/issues/4903)</span><span class="sxs-lookup"><span data-stu-id="80920-213">Remove unsupported `-showwindow` switch from `Get-Help` [#4903](https://github.com/PowerShell/PowerShell/issues/4903)</span></span>

<span data-ttu-id="80920-214">`-showwindow` では、CoreCLR でサポートされていない、WPF を使用します。</span><span class="sxs-lookup"><span data-stu-id="80920-214">`-showwindow` relies on WPF, which is not supported on CoreCLR.</span></span>

### <a name="allow--to-be-used-in-registry-path-for-remove-item-4866"></a><span data-ttu-id="80920-215">`Remove-Item` のレジストリ パスで \* が使用可能に [#4866](https://github.com/PowerShell/PowerShell/issues/4866)</span><span class="sxs-lookup"><span data-stu-id="80920-215">Allow \* to be used in registry path for `Remove-Item` [#4866](https://github.com/PowerShell/PowerShell/issues/4866)</span></span>

<span data-ttu-id="80920-216">以前は、ワイルドカードを渡された `-LiteralPath` は `-Path` と同様に処理され、ワイルドカードを使ってファイルが検出されない場合は、何も返さず終了していました。</span><span class="sxs-lookup"><span data-stu-id="80920-216">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="80920-217">正しい動作として、ファイルが存在しない場合はエラーを返すには、`-LiteralPath` はリテラルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="80920-217">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="80920-218">`-Literal` にワイルドカードを使用した場合、リテラルとして処理するよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-218">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="fix-set-service-failing-test-4802"></a><span data-ttu-id="80920-219">テストで失敗していた `Set-Service` を修正 [#4802](https://github.com/PowerShell/PowerShell/issues/4802)</span><span class="sxs-lookup"><span data-stu-id="80920-219">Fix `Set-Service` failing test [#4802](https://github.com/PowerShell/PowerShell/issues/4802)</span></span>

<span data-ttu-id="80920-220">以前は、`New-Service -StartupType foo` を使用している場合、`foo` は無視され、既定のスタートアップ タイプを使用して、サービスが作成されていました。</span><span class="sxs-lookup"><span data-stu-id="80920-220">Previously, if `New-Service -StartupType foo` was used, `foo` was ignored and the service was created with some default startup type.</span></span> <span data-ttu-id="80920-221">今回の変更により、無効なスタートアップ タイプの場合は、エラーが明示的にスローされます。</span><span class="sxs-lookup"><span data-stu-id="80920-221">This change is to explicitly throw an error for an invalid startup type.</span></span>

### <a name="rename-isosx-to-ismacos-4700"></a><span data-ttu-id="80920-222">`$IsOSX` の名前を `$IsMacOS` に変更 [#4700](https://github.com/PowerShell/PowerShell/issues/4700)</span><span class="sxs-lookup"><span data-stu-id="80920-222">Rename `$IsOSX` to `$IsMacOS` [#4700](https://github.com/PowerShell/PowerShell/issues/4700)</span></span>

<span data-ttu-id="80920-223">PowerShell の名前付けが Microsoft の名前規則に準拠し、OSX ではなく Apple の macOS が使用する名前付け規則に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="80920-223">The naming in PowerShell should be consistent with our naming and conform to Apple's use of macOS instead of OSX.</span></span> <span data-ttu-id="80920-224">ただし、読みやすさと整合性の目的で、引き続き Pascal の形式に従っています。</span><span class="sxs-lookup"><span data-stu-id="80920-224">However, for readability and consistently we are staying with Pascal casing.</span></span>

### <a name="make-error-message-consistent-when-invalid-script-is-passed-to--file-better-error-when-passed-ambiguous-argument-4573"></a><span data-ttu-id="80920-225">無効なスクリプトがファイルに渡されたときに一貫性のあるエラー メッセージを生成。あいまいな引数 が渡されたときのエラー表示を改善 [#4573](https://github.com/PowerShell/PowerShell/issues/4573)</span><span class="sxs-lookup"><span data-stu-id="80920-225">Make error message consistent when invalid script is passed to -File, better error when passed ambiguous argument [#4573](https://github.com/PowerShell/PowerShell/issues/4573)</span></span>

<span data-ttu-id="80920-226">`pwsh.exe` の終了コードを Unix の規則と一致するよう変更</span><span class="sxs-lookup"><span data-stu-id="80920-226">Change the exit codes of `pwsh.exe` to align with Unix conventions</span></span>

### <a name="removal-of-localaccount-and-cmdlets-from--diagnostics-modules-4302-4303"></a><span data-ttu-id="80920-227">`Diagnostics` モジュールから `LocalAccount` およびコマンドレットを削除</span><span class="sxs-lookup"><span data-stu-id="80920-227">Removal of `LocalAccount` and cmdlets from  `Diagnostics` modules.</span></span> <span data-ttu-id="80920-228">[#4302](https://github.com/PowerShell/PowerShell/issues/4302) [#4303](https://github.com/PowerShell/PowerShell/issues/4303)</span><span class="sxs-lookup"><span data-stu-id="80920-228">[#4302](https://github.com/PowerShell/PowerShell/issues/4302) [#4303](https://github.com/PowerShell/PowerShell/issues/4303)</span></span>

<span data-ttu-id="80920-229">API がサポートされていないため、改善されたソリューションが発表されるまで、`LocalAccounts` モジュールと `Diagnostics` モジュールの `Counter`コマンドレットが削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-229">Due to unsupported APIs, the `LocalAccounts` module and the `Counter` cmdlets in the `Diagnostics` module were removed until a better solution is found.</span></span>

### <a name="executing-powershell-script-with-bool-parameter-does-not-work-4036"></a><span data-ttu-id="80920-230">ブール値のパラメーターを使用する PowerShell スクリプトが正しく動作しない [#4036](https://github.com/PowerShell/PowerShell/issues/4036)</span><span class="sxs-lookup"><span data-stu-id="80920-230">Executing PowerShell script with bool parameter does not work [#4036](https://github.com/PowerShell/PowerShell/issues/4036)</span></span>

<span data-ttu-id="80920-231">以前は、**powershell.exe** (現在は **pwsh.exe**) で `-File` を使用して PowerShell スクリプトを実行する場合、`$true`/`$false` をパラメーター値として渡すことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="80920-231">Previously, using **powershell.exe** (now **pwsh.exe**) to execute a PowerShell script using `-File` provided no way to pass `$true`/`$false` as parameter values.</span></span> <span data-ttu-id="80920-232">解析された値としての `$true`/`$false` パラメーターのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="80920-232">Support for `$true`/`$false` as parsed values to parameters was added.</span></span> <span data-ttu-id="80920-233">現在、ドキュメントに記載されている構文が機能しないため、スイッチの値もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="80920-233">Switch values are also supported as currently documented syntax doesn't work.</span></span>

### <a name="remove-clrversion-property-from-psversiontable-4027"></a><span data-ttu-id="80920-234">`ClrVersion` から `$PSVersionTable` プロパティを削除 [#4027](https://github.com/PowerShell/PowerShell/issues/4027)</span><span class="sxs-lookup"><span data-stu-id="80920-234">Remove `ClrVersion` property from `$PSVersionTable` [#4027](https://github.com/PowerShell/PowerShell/issues/4027)</span></span>

<span data-ttu-id="80920-235">`$PSVersionTable` の `ClrVersion` プロパティは CoreCLR では有用でないため、エンドユーザーは、互換性を判定するためにこの値を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="80920-235">The `ClrVersion` property of `$PSVersionTable` is not useful with CoreCLR, end users should not be using that value to determine compatibility.</span></span>

### <a name="change-positional-parameter-for-powershellexe-from--command-to--file-4019"></a><span data-ttu-id="80920-236">`powershell.exe` の位置指定パラメーターを `-Command` から `-File` に変更 [#4019](https://github.com/PowerShell/PowerShell/issues/4019)</span><span class="sxs-lookup"><span data-stu-id="80920-236">Change positional parameter for `powershell.exe` from `-Command` to `-File` [#4019](https://github.com/PowerShell/PowerShell/issues/4019)</span></span>

<span data-ttu-id="80920-237">Windows 以外のプラットフォームでの PowerShell のシバン使用を有効化します。</span><span class="sxs-lookup"><span data-stu-id="80920-237">Enable shebang use of PowerShell on non-Windows platforms.</span></span> <span data-ttu-id="80920-238">Unix ベースのシステムでは、`pwsh` を明示的に呼び出すのではなく、自動的に PowerShell を起動するスクリプト実行可能ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="80920-238">This means on Unix based systems, you can make a script executable that would invoke PowerShell automatically rather than explicitly invoking `pwsh`.</span></span> <span data-ttu-id="80920-239">また、`-File` を指定せずに `powershell foo.ps1` または `powershell fooScript` のようなコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="80920-239">This also means that you can now do things like `powershell foo.ps1` or `powershell fooScript` without specifying `-File`.</span></span> <span data-ttu-id="80920-240">ただし、今回の変更後、`powershell.exe Get-Command` などのコマンドを実行しようとする場合は `-c` または `-Command` を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80920-240">However, this change now requires that you explicitly specify `-c` or `-Command` when trying to do things like `powershell.exe Get-Command`.</span></span>

### <a name="implement-unicode-escape-parsing-3958"></a><span data-ttu-id="80920-241">Unicode エスケープ解析の実装 [#3958](https://github.com/PowerShell/PowerShell/issues/3958)</span><span class="sxs-lookup"><span data-stu-id="80920-241">Implement Unicode escape parsing [#3958](https://github.com/PowerShell/PowerShell/issues/3958)</span></span>

<span data-ttu-id="80920-242">`` `u####`` または `` `u{####}`` は対応する Unicode 文字に変換されます。</span><span class="sxs-lookup"><span data-stu-id="80920-242">`` `u####`` or `` `u{####}`` is converted to the corresponding Unicode character.</span></span> <span data-ttu-id="80920-243">`` `u`` リテラルを出力するには、``` ``u``` のように、グラーブ文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="80920-243">To output a literal `` `u``, escape the backtick: ``` ``u```.</span></span>

### <a name="change-new-modulemanifest-encoding-to-utf8nobom-on-non-windows-platforms-3940"></a><span data-ttu-id="80920-244">Windows 以外のプラットフォームの `New-ModuleManifest` エンコーディングを `UTF8NoBOM` に変更 [#3940](https://github.com/PowerShell/PowerShell/issues/3940)</span><span class="sxs-lookup"><span data-stu-id="80920-244">Change `New-ModuleManifest` encoding to `UTF8NoBOM` on non-Windows platforms [#3940](https://github.com/PowerShell/PowerShell/issues/3940)</span></span>

<span data-ttu-id="80920-245">以前は、`New-ModuleManifest` は、BOM を使用して UTF-16 で psd1 マニフェストを作成しており、Linux ツールで問題が発生していました。</span><span class="sxs-lookup"><span data-stu-id="80920-245">Previously, `New-ModuleManifest` creates psd1 manifests in UTF-16 with BOM, creating a problem for Linux tools.</span></span> <span data-ttu-id="80920-246">今回の重要な変更により、Windows 以外のプラットフォーム上の エンコーディング `New-ModuleManifest` が UTF (BOM なし) に変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-246">This breaking change changes the encoding of `New-ModuleManifest` to be UTF (no BOM) in non-Windows platforms.</span></span>

### <a name="prevent-get-childitem-from-recursing-into-symlinks-1875-3780"></a><span data-ttu-id="80920-247">`Get-ChildItem` のシンボリック リンクへ反復を防止 (#1875)</span><span class="sxs-lookup"><span data-stu-id="80920-247">Prevent `Get-ChildItem` from recursing into symlinks (#1875).</span></span> [<span data-ttu-id="80920-248">#3780</span><span class="sxs-lookup"><span data-stu-id="80920-248">#3780</span></span>](https://github.com/PowerShell/PowerShell/issues/3780)

<span data-ttu-id="80920-249">今回の変更により、`Get-ChildItem` と Unix の `ls -r` や Windows の `dir /s` ネイティブ コマンドとの連携度が向上しました。</span><span class="sxs-lookup"><span data-stu-id="80920-249">This change brings `Get-ChildItem` more in line with the Unix `ls -r` and the Windows `dir /s` native commands.</span></span> <span data-ttu-id="80920-250">上記のコマンドと同様、このコマンドレットでは、反復中に特定されたディレクトリへのシンボリック リンクが表示されますが、反復はされません。</span><span class="sxs-lookup"><span data-stu-id="80920-250">Like the mentioned commands, the cmdlet displays symbolic links to directories found during recursion, but does not recurse into them.</span></span>

### <a name="fix-get-content--delimiter-to-not-include-the-delimiter-in-the-returned-lines-3706"></a><span data-ttu-id="80920-251">返された行に区切り文字が含まれないように `Get-Content -Delimiter` を修正 [#3706](https://github.com/PowerShell/PowerShell/issues/3706)</span><span class="sxs-lookup"><span data-stu-id="80920-251">Fix `Get-Content -Delimiter` to not include the delimiter in the returned lines [#3706](https://github.com/PowerShell/PowerShell/issues/3706)</span></span>

<span data-ttu-id="80920-252">以前は、`Get-Content -Delimiter` を使用したときの出力に一貫性がなく、区切り記号を削除するために追加のデータ処理が必要になり不便でした。</span><span class="sxs-lookup"><span data-stu-id="80920-252">Previously, the output while using `Get-Content -Delimiter` was inconsistent and inconvenient as it required further processing of the data to remove the delimiter.</span></span> <span data-ttu-id="80920-253">今回の変更により、返される行の区切り記号が削除されます。</span><span class="sxs-lookup"><span data-stu-id="80920-253">This change removes the delimiter in returned lines.</span></span>

### <a name="implement-format-hex-in-c-3320"></a><span data-ttu-id="80920-254">Format-hex を C# で実装 [#3320](https://github.com/PowerShell/PowerShell/issues/3320)</span><span class="sxs-lookup"><span data-stu-id="80920-254">Implement Format-Hex in C# [#3320](https://github.com/PowerShell/PowerShell/issues/3320)</span></span>

<span data-ttu-id="80920-255">`-Raw` パラメーターは "no-op" になりました (なにも動作はしません)。</span><span class="sxs-lookup"><span data-stu-id="80920-255">The `-Raw` parameter is now a "no-op" (in that it does nothing).</span></span> <span data-ttu-id="80920-256">今後は、その種類の数字のすべてのバイトを含め、数字がすべての出力に忠実に表示されます (今回の変更前は、`-Raw` パラメーターが正式にこの動作を実行していました)。</span><span class="sxs-lookup"><span data-stu-id="80920-256">Going forward all of the output will be displayed with a true representation of numbers that includes all of the bytes for its type (what the `-Raw` parameter was formally doing prior to this change).</span></span>

### <a name="powershell-as-a-default-shell-doesnt-work-with-script-command-3319"></a><span data-ttu-id="80920-257">既定シェルの PowerShell でスクリプト コマンドが正しく動作しない [#3319](https://github.com/PowerShell/PowerShell/issues/3319)</span><span class="sxs-lookup"><span data-stu-id="80920-257">PowerShell as a default shell doesn't work with script command [#3319](https://github.com/PowerShell/PowerShell/issues/3319)</span></span>

<span data-ttu-id="80920-258">Unix では、対話型のシェルで `-i` の入力を受け付けることが通常で、多くのツールでこの動作が前提とされ、スイッチ `-i` を使ってシェルを呼び出します (たとえば `script` や、PowerShell が既定のシェルに設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="80920-258">On Unix, it is a convention for shells to accept `-i` for an interactive shell and many tools expect this behavior (`script` for example, and when setting PowerShell as the default shell) and calls the shell with the `-i` switch.</span></span> <span data-ttu-id="80920-259">以前は `-inputformat` と一致する便利な方法として `-i` を使用できましたが、この重要な変更後は `-in` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80920-259">This change is breaking in that `-i` previously could be used as short hand to match `-inputformat`, which now needs to be `-in`.</span></span>

### <a name="typo-fix-in-get-computerinfo-property-name-3167"></a><span data-ttu-id="80920-260">Get-computerinfo プロパティ名の入力ミスを修正 [#3167](https://github.com/PowerShell/PowerShell/issues/3167)</span><span class="sxs-lookup"><span data-stu-id="80920-260">Typo fix in Get-ComputerInfo property name [#3167](https://github.com/PowerShell/PowerShell/issues/3167)</span></span>

<span data-ttu-id="80920-261">`BiosSerialNumber` が `BiosSeralNumber` と誤記されていましたが、正しいスペルに変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-261">`BiosSerialNumber` was misspelled as `BiosSeralNumber` and has been changed to the correct spelling.</span></span>

### <a name="add-get-stringhash-and-get-filehash-cmdlets-3024"></a><span data-ttu-id="80920-262">`Get-StringHash` および `Get-FileHash` コマンドレットを追加 [#3024](https://github.com/PowerShell/PowerShell/issues/3024)</span><span class="sxs-lookup"><span data-stu-id="80920-262">Add `Get-StringHash` and `Get-FileHash` cmdlets [#3024](https://github.com/PowerShell/PowerShell/issues/3024)</span></span>

<span data-ttu-id="80920-263">CoreFX でサポートされていないハッシュ アルゴリズムがありましたが、今回の変更により、使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="80920-263">This change is that some hash algorithms are not supported by CoreFX, therefore they are no longer available:</span></span>

- `MACTripleDES`
- `RIPEMD160`

### <a name="add-validation-on-get--cmdlets-where-passing-null-returns-all-objects-instead-of-error-2672"></a><span data-ttu-id="80920-264">$null を渡した場合、エラーではなくすべてのオブジェクトが返されるよう、`Get-*` コマンドレットに検証機能を追加 [#2672](https://github.com/PowerShell/PowerShell/issues/2672)</span><span class="sxs-lookup"><span data-stu-id="80920-264">Add validation on `Get-*` cmdlets where passing $null returns all objects instead of error [#2672](https://github.com/PowerShell/PowerShell/issues/2672)</span></span>

<span data-ttu-id="80920-265">次のコマンドに `$null` を渡すと、エラーがスローされるよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-265">Passing `$null` to any of the following now throws an error:</span></span>

- `Get-Credential -UserName`
- `Get-Event -SourceIdentifier`
- `Get-EventSubscriber -SourceIdentifier`
- `Get-Help -Name`
- `Get-PSBreakpoint -Script`
- `Get-PSProvider -PSProvider`
- `Get-PSSessionConfiguration -Name`
- `Get-PSSnapin -Name`
- `Get-Runspace -Name`
- `Get-RunspaceDebug -RunspaceName`
- `Get-Service -Name`
- `Get-TraceSource -Name`
- `Get-Variable -Name`
- `Get-WmiObject -Class`
- `Get-WmiObject -Property`

### <a name="add-support-w3c-extended-log-file-format-in-import-csv-2482"></a><span data-ttu-id="80920-266">`Import-Csv` に W3C 拡張ログ ファイル形式のサポートを追加 [#2482](https://github.com/PowerShell/PowerShell/issues/2482)</span><span class="sxs-lookup"><span data-stu-id="80920-266">Add support W3C Extended Log File Format in `Import-Csv` [#2482](https://github.com/PowerShell/PowerShell/issues/2482)</span></span>

<span data-ttu-id="80920-267">以前は、`Import-Csv` コマンドレットを使用して、W3C 拡張ログ形式でログ ファイルを直接インポートできず、追加の操作が必要でした。</span><span class="sxs-lookup"><span data-stu-id="80920-267">Previously, the `Import-Csv` cmdlet cannot be used to directly import the log files in W3C extended log format and additional action would be required.</span></span> <span data-ttu-id="80920-268">今回の変更により、W3C 拡張ログ形式がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="80920-268">With this change, W3C extended log format is supported.</span></span>

### <a name="parameter-binding-problem-with-valuefromremainingarguments-in-ps-functions-2035"></a><span data-ttu-id="80920-269">PS 関数の `ValueFromRemainingArguments` でのパラメーター バインドの問題 [#2035](https://github.com/PowerShell/PowerShell/issues/2035)</span><span class="sxs-lookup"><span data-stu-id="80920-269">Parameter binding problem with `ValueFromRemainingArguments` in PS functions [#2035](https://github.com/PowerShell/PowerShell/issues/2035)</span></span>

<span data-ttu-id="80920-270">`ValueFromRemainingArguments` は、それ自体が配列である単一の値ではなく、値を配列として返すよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-270">`ValueFromRemainingArguments` now returns the values as an array instead of a single value which itself is an array.</span></span>

### <a name="buildversion-is-removed-from-psversiontable-1415"></a><span data-ttu-id="80920-271">`BuildVersion` を `$PSVersionTable` から削除 [#1415](https://github.com/PowerShell/PowerShell/issues/1415)</span><span class="sxs-lookup"><span data-stu-id="80920-271">`BuildVersion` is removed from `$PSVersionTable` [#1415](https://github.com/PowerShell/PowerShell/issues/1415)</span></span>

<span data-ttu-id="80920-272">`$PSVersionTable` から `BuildVersion` プロパティを削除してください。</span><span class="sxs-lookup"><span data-stu-id="80920-272">Remove the `BuildVersion` property from `$PSVersionTable`.</span></span> <span data-ttu-id="80920-273">このプロパティは、Windows のビルド バージョンと関連付けられていました。</span><span class="sxs-lookup"><span data-stu-id="80920-273">This property was tied to the Windows build version.</span></span> <span data-ttu-id="80920-274">代わりに、`GitCommitId` を使用して、PowerShell Core の正確なビルド バージョンを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80920-274">Instead, we recommend that you use `GitCommitId` to retrieve the exact build version of PowerShell Core.</span></span>

### <a name="changes-to-web-cmdlets"></a><span data-ttu-id="80920-275">Web のコマンドレットへの変更</span><span class="sxs-lookup"><span data-stu-id="80920-275">Changes to Web Cmdlets</span></span>

<span data-ttu-id="80920-276">Web コマンドレットの基となる .NET API が `System.Net.Http.HttpClient` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-276">The underlying .NET API of the Web Cmdlets has been changed to `System.Net.Http.HttpClient`.</span></span> <span data-ttu-id="80920-277">この変更は、多くのメリットを提供します。</span><span class="sxs-lookup"><span data-stu-id="80920-277">This change provides many benefits.</span></span> <span data-ttu-id="80920-278">ただし、この変更と、Internet Explorer での相互運用性がないことを理由として、`Invoke-WebRequest` と `Invoke-RestMethod`に重要な変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="80920-278">However, this change along with a lack of interoperability with Internet Explorer have resulted in several breaking changes within `Invoke-WebRequest` and `Invoke-RestMethod`.</span></span>

- <span data-ttu-id="80920-279">`Invoke-WebRequest` では、基本的な HTML 解析のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="80920-279">`Invoke-WebRequest` now supports basic HTML Parsing only.</span></span> <span data-ttu-id="80920-280">`Invoke-WebRequest` は常に `BasicHtmlWebResponseObject` オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="80920-280">`Invoke-WebRequest` always returns a `BasicHtmlWebResponseObject` object.</span></span> <span data-ttu-id="80920-281">`ParsedHtml` および `Forms` プロパティが削除されました。</span><span class="sxs-lookup"><span data-stu-id="80920-281">The `ParsedHtml` and `Forms` properties have been removed.</span></span>
- <span data-ttu-id="80920-282">`BasicHtmlWebResponseObject.Headers` の値は `String` から `String[]` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-282">`BasicHtmlWebResponseObject.Headers` values are now `String[]` instead of `String`.</span></span>
- <span data-ttu-id="80920-283">`BasicHtmlWebResponseObject.BaseResponse` は、`System.Net.Http.HttpResponseMessage` オブジェクトに変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-283">`BasicHtmlWebResponseObject.BaseResponse` is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="80920-284">Web コマンドレットの例外の `Response` プロパティが、`System.Net.Http.HttpResponseMessage` オブジェクトに変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-284">The `Response` property on Web Cmdlet exceptions is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="80920-285">`-Headers` および `-UserAgent` パラメーターの既定設定が、Strict RFC ヘッダー解析に変更されました。</span><span class="sxs-lookup"><span data-stu-id="80920-285">Strict RFC header parsing is now default for the `-Headers` and `-UserAgent` parameter.</span></span> <span data-ttu-id="80920-286">これは、`-SkipHeaderValidation` を使用して無効にできます。</span><span class="sxs-lookup"><span data-stu-id="80920-286">This can be bypassed with `-SkipHeaderValidation`.</span></span>
- <span data-ttu-id="80920-287">`file://` および `ftp://` URI スキームのサポートは終了しました。</span><span class="sxs-lookup"><span data-stu-id="80920-287">`file://` and `ftp://` URI schemes are no longer supported.</span></span>
- <span data-ttu-id="80920-288">`System.Net.ServicePointManager` 設定は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="80920-288">`System.Net.ServicePointManager` settings are no longer honored.</span></span>
- <span data-ttu-id="80920-289">現在、macOS では、証明書を使用した認証は使用できません。</span><span class="sxs-lookup"><span data-stu-id="80920-289">There is currently no certificate based authentication available on macOS.</span></span>
- <span data-ttu-id="80920-290">`http://` URI 経由で `-Credential` を使用するとエラーになります。</span><span class="sxs-lookup"><span data-stu-id="80920-290">Use of `-Credential` over an `http://` URI will result in an error.</span></span> <span data-ttu-id="80920-291">`https://` URI を使用するか、または `-AllowUnencryptedAuthentication`パラメーターを指定してエラーを回避してください。</span><span class="sxs-lookup"><span data-stu-id="80920-291">Use an `https://` URI or supply the `-AllowUnencryptedAuthentication` parameter to suppress the error.</span></span>
- <span data-ttu-id="80920-292">`-MaximumRedirection` では、指定された制限を超えようとすると、最後のリダイレクトの結果を返す代わりに、終了エラーが生成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="80920-292">`-MaximumRedirection` now produces a terminating error when redirection attempts exceed the provided limit instead of returning the results of the last redirection.</span></span>
- <span data-ttu-id="80920-293">PowerShell 6.2 では、JSON 応答に対して規定値が UTF-8 エンコードになるように変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="80920-293">In PowerShell 6.2, a change was made to default to UTF-8 encoding for JSON responses.</span></span> <span data-ttu-id="80920-294">JSON 応答に文字セットが指定されていない場合、既定のエンコードは RFC 8259 に従って UTF-8 にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80920-294">When a charset is not supplied for a JSON response, the default encoding should be UTF-8 per RFC 8259.</span></span>

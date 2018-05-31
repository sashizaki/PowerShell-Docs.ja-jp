---
ms.date: 05/17/2018
keywords: powershell、core
title: PowerShell Core 6.0 の重要な変更
ms.openlocfilehash: 60ce7a1676403bb08b57bf852ba725acde86a30c
ms.sourcegitcommit: 2d9cf1ccb9a653db7726a408ebcb65530dcb1522
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2018
ms.locfileid: "34309616"
---
# <a name="breaking-changes-for-powershell-60"></a><span data-ttu-id="c8e2a-103">PowerShell Core 6.0 の重要な変更</span><span class="sxs-lookup"><span data-stu-id="c8e2a-103">Breaking Changes for PowerShell 6.0</span></span>

## <a name="features-no-longer-available-in-powershell-core"></a><span data-ttu-id="c8e2a-104">PowerShell Core で使用できなくなった機能</span><span class="sxs-lookup"><span data-stu-id="c8e2a-104">Features no longer available in PowerShell Core</span></span>

### <a name="powershell-workflow"></a><span data-ttu-id="c8e2a-105">PowerShell ワークフロー</span><span class="sxs-lookup"><span data-stu-id="c8e2a-105">PowerShell Workflow</span></span>

<span data-ttu-id="c8e2a-106">[PowerShell ワークフロー][workflow]は、実行時間の長い、または並列化されたタスクための堅牢な Runbook の作成を可能にする [Windows Workflow Foundation (WF)][workflow-foundation] の上に構築される Windows PowerShell の機能です。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-106">[PowerShell Workflow][workflow] is a feature in Windows PowerShell that builds on top of [Windows Workflow Foundation (WF)][workflow-foundation] that enables the creation of robust runbooks for long-running or parallelized tasks.</span></span>

<span data-ttu-id="c8e2a-107">.NET Core では Windows Workflow Foundation がサポートされていないため、PowerShell Core の PowerShell ワークフローのサポートを終了します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-107">Due to the lack of support for Windows Workflow Foundation in .NET Core, we will not continue to support PowerShell Workflow in PowerShell Core.</span></span>

<span data-ttu-id="c8e2a-108">今後、PowerShell ワークフローを必要としない、PowerShell 言語でのネイティブの並列処理と同時実行が可能になる予定です。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-108">In the future, we would like to enable native parallelism/concurrency in the PowerShell language without the need for PowerShell Workflow.</span></span>

[workflow]: https://docs.microsoft.com/powershell/scripting/core-powershell/workflows-guide
[workflow-foundation]: https://docs.microsoft.com/dotnet/framework/windows-workflow-foundation/

### <a name="custom-snap-ins"></a><span data-ttu-id="c8e2a-109">カスタム スナップイン</span><span class="sxs-lookup"><span data-stu-id="c8e2a-109">Custom snap-ins</span></span>

<span data-ttu-id="c8e2a-110">[PowerShell スナップイン][snapin]は、PowerShell モジュールの前身ですが、PowerShell コミュニティではあまり使用されていません。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-110">[PowerShell snap-ins][snapin] are a predecessor to PowerShell modules that do not have widespread adoption in the PowerShell community.</span></span>

<span data-ttu-id="c8e2a-111">スナップインのサポートは複雑であり、コミュニティ内での普及率が低いことから、PowerShell Core でのカスタム スナップインのサポートを終了します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-111">Due to the complexity of supporting snap-ins and their lack of usage in the community, we no longer support custom snap-ins in PowerShell Core.</span></span>

<span data-ttu-id="c8e2a-112">現時点では、Windows および Windows Server 内の `ActiveDirectory` および `DnsClient` モジュールに影響します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-112">Today, this breaks the `ActiveDirectory` and `DnsClient` modules in Windows and Windows Server.</span></span>

[snapin]: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins

### <a name="wmi-v1-cmdlets"></a><span data-ttu-id="c8e2a-113">WMI v1 コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c8e2a-113">WMI v1 cmdlets</span></span>

<span data-ttu-id="c8e2a-114">WMI ベースの 2 つのモジュール セットをサポートすることは複雑になるため、PowerShell Core から WMI v1 コマンドレットが削除されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-114">Due to the complexity of supporting two sets of WMI-based modules, we removed the WMI v1 cmdlets from PowerShell Core:</span></span>

- `Get-WmiObject`
- `Invoke-WmiMethod`
- `Register-WmiEvent`
- `Set-WmiInstance`

<span data-ttu-id="c8e2a-115">これに代わり、新しい機能や再設計された構文を含み、同じ機能を提供する CIM (別名 WMI v2) コマンドレットを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-115">Instead, we recommend that you the use the CIM (aka WMI v2) cmdlets which provide the same functionality with new functionality and a redesigned syntax:</span></span>

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

### <a name="microsoftpowershelllocalaccounts"></a><span data-ttu-id="c8e2a-116">Microsoft.PowerShell.LocalAccounts</span><span class="sxs-lookup"><span data-stu-id="c8e2a-116">Microsoft.PowerShell.LocalAccounts</span></span>

<span data-ttu-id="c8e2a-117">サポートされていない API を使用していることから、より優れたソリューションが提供されるまで、PowerShell Core から `Microsoft.PowerShell.LocalAccounts` コマンドレットを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-117">Due to the use of unsupported APIs, `Microsoft.PowerShell.LocalAccounts` has been removed from PowerShell Core until a better solution is found.</span></span>

### <a name="-counter-cmdlets"></a><span data-ttu-id="c8e2a-118">`*-Counter` コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c8e2a-118">`*-Counter` cmdlets</span></span>

<span data-ttu-id="c8e2a-119">サポートされていない API を使用していることから、より優れたソリューションが提供されるまで、PowerShell Core から `*-Counter` コマンドレットを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-119">Due to the use of unsupported APIs, the `*-Counter` has been removed from PowerShell Core until a better solution is found.</span></span>

## <a name="enginelanguage-changes"></a><span data-ttu-id="c8e2a-120">エンジンおよび言語の変更</span><span class="sxs-lookup"><span data-stu-id="c8e2a-120">Engine/language changes</span></span>

### <a name="rename-powershellexe-to-pwshexe-5101httpsgithubcompowershellpowershellissues5101"></a><span data-ttu-id="c8e2a-121">名前 `powershell.exe` を `pwsh.exe` に変更 [#5101](https://github.com/PowerShell/PowerShell/issues/5101)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-121">Rename `powershell.exe` to `pwsh.exe` [#5101](https://github.com/PowerShell/PowerShell/issues/5101)</span></span>

<span data-ttu-id="c8e2a-122">ユーザーが (Windows PowerShell ではなく) Windows 上で PowerShell Core を確実な方法で呼び出せるよう、PowerShell Core のバイナリが Windows では `pwsh.exe` に、Windows 以外のプラットフォームでは `pwsh` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-122">In order to give users a deterministic way to call PowerShell Core on Windows (as opposed to Windows PowerShell), the PowerShell Core binary was changed to `pwsh.exe` on Windows and `pwsh` on non-Windows platforms.</span></span>

<span data-ttu-id="c8e2a-123">短い形式の名前も、Windows 以外のプラットフォーム上のシェルの名前形式と同じになるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-123">The shortened name is also consistent with naming of shells on non-Windows platforms.</span></span>

### <a name="dont-insert-line-breaks-to-output-except-for-tables-5193httpsgithubcompowershellpowershellissues5193"></a><span data-ttu-id="c8e2a-124">出力 (テーブル以外) に改行を挿入できない。[#5193](https://github.com/PowerShell/PowerShell/issues/5193)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-124">Don't insert line breaks to output (except for tables) [#5193](https://github.com/PowerShell/PowerShell/issues/5193)</span></span>

<span data-ttu-id="c8e2a-125">以前は、コンソールの幅に合わせて出力が調整され、コンソールの幅の終端に改行が追加されていたため、ターミナルのサイズが変更されると、想定外の形式になることがありました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-125">Previously, output was aligned to the width of the console and line breaks were added at the end width of the console, meaning the output didn't get reformatted as expected if the terminal was resized.</span></span> <span data-ttu-id="c8e2a-126">今回の変更は、列の整列に改行が必要なため、テーブルには適用されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-126">This change was not applied to tables, as the line breaks are necessary to keep the columns aligned.</span></span>

### <a name="skip-null-element-check-for-collections-with-a-value-type-element-type-5432httpsgithubcompowershellpowershellissues5432"></a><span data-ttu-id="c8e2a-127">要素の型が値型のコレクションの null 要素チェックを省略 [#5432](https://github.com/PowerShell/PowerShell/issues/5432)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-127">Skip null-element check for collections with a value-type element type [#5432](https://github.com/PowerShell/PowerShell/issues/5432)</span></span>

<span data-ttu-id="c8e2a-128">`Mandatory`パラメーターと `ValidateNotNull` および `ValidateNotNullOrEmpty` 属性について、コレクションの要素の型が値型の場合に null 要素チェックを省略します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-128">For the `Mandatory` parameter and `ValidateNotNull` and `ValidateNotNullOrEmpty` attributes, skip the null-element check if the collection's element type is value type.</span></span>

### <a name="change-outputencoding-to-use-utf-8-nobom-encoding-rather-than-ascii-5369httpsgithubcompowershellpowershellissues5369"></a><span data-ttu-id="c8e2a-129">ASCIIではなく `UTF-8 NoBOM` エンコードを使用するよう `$OutputEncoding` を変更 [#5369](https://github.com/PowerShell/PowerShell/issues/5369)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-129">Change `$OutputEncoding` to use `UTF-8 NoBOM` encoding rather than ASCII [#5369](https://github.com/PowerShell/PowerShell/issues/5369)</span></span>

<span data-ttu-id="c8e2a-130">以前のエンコード、ASCII (7 ビット) を使用すると、出力が不適切に変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-130">The previous encoding, ASCII (7-bit), would result in incorrect alteration of the output in some cases.</span></span> <span data-ttu-id="c8e2a-131">今回の変更では、`UTF-8 NoBOM` が既定値となり、ほとんどのツールおよびオペレーティング システムでサポートされているエンコードを使用して Unicode 出力を保持します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-131">This change is to make `UTF-8 NoBOM` default, which preserves Unicode output with an encoding supported by most tools and operating systems.</span></span>

### <a name="remove-allscope-from-most-default-aliases-5268httpsgithubcompowershellpowershellissues5268"></a><span data-ttu-id="c8e2a-132">大部分の既定エイリアスから `AllScope` を削除 [#5268](https://github.com/PowerShell/PowerShell/issues/5268)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-132">Remove `AllScope` from most default aliases [#5268](https://github.com/PowerShell/PowerShell/issues/5268)</span></span>

<span data-ttu-id="c8e2a-133">スコープの作成を高速化するために、大部分の既定エイリアスから `AllScope` が削除されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-133">To speed up scope creation, `AllScope` was removed from most default aliases.</span></span> <span data-ttu-id="c8e2a-134">検索が高速化できる使用頻度の高いいくつかのエイリアスでは `AllScope` のままになっています。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-134">`AllScope` was left for a few frequently used aliases where the lookup was faster.</span></span>

### <a name="-verbose-and--debug-no-longer-overrides-erroractionpreference-5113httpsgithubcompowershellpowershellissues5113"></a><span data-ttu-id="c8e2a-135">`-Verbose` および `-Debug` による `$ErrorActionPreference` のオーバーライドの終了 [#5113](https://github.com/PowerShell/PowerShell/issues/5113)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-135">`-Verbose` and `-Debug` no longer overrides `$ErrorActionPreference` [#5113](https://github.com/PowerShell/PowerShell/issues/5113)</span></span>

<span data-ttu-id="c8e2a-136">以前は、`-Verbose` または `-Debug` が指定された場合、それにより `$ErrorActionPreference` の動作がオーバーライドされていました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-136">Previously, if `-Verbose` or `-Debug` were specified, it overrode the behavior of `$ErrorActionPreference`.</span></span> <span data-ttu-id="c8e2a-137">今回の変更により、`-Verbose` および `-Debug` が `$ErrorActionPreference` の動作に影響を与えることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-137">With this change, `-Verbose` and `-Debug` no longer affect the behavior of `$ErrorActionPreference`.</span></span>

## <a name="cmdlet-changes"></a><span data-ttu-id="c8e2a-138">コマンドレットの変更</span><span class="sxs-lookup"><span data-stu-id="c8e2a-138">Cmdlet changes</span></span>

### <a name="invoke-restmethod-doesnt-return-useful-info-when-no-data-is-returned-5320httpsgithubcompowershellpowershellissues5320"></a><span data-ttu-id="c8e2a-139">データが返されない場合、Invoke-RestMethod により、有益な情報が返されない</span><span class="sxs-lookup"><span data-stu-id="c8e2a-139">Invoke-RestMethod doesn't return useful info when no data is returned.</span></span> [<span data-ttu-id="c8e2a-140">#5320</span><span class="sxs-lookup"><span data-stu-id="c8e2a-140">#5320</span></span>](https://github.com/PowerShell/PowerShell/issues/5320)

<span data-ttu-id="c8e2a-141">API が `null` のみを返す場合、Invoke-restmethod は、これを `$null` ではなく、文字列 `"null"` としてシリアル化していました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-141">When an API returns just `null`, Invoke-RestMethod was serializing this as the string `"null"` instead of `$null`.</span></span> <span data-ttu-id="c8e2a-142">今回の変更により、有効なシングル値 JSON `null` がリテラル `$null` として正しくシリアル化されるよう、`Invoke-RestMethod` のロジックが修正されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-142">This change fixes the logic in `Invoke-RestMethod` to properly serialize a valid single value JSON `null` literal as `$null`.</span></span>

### <a name="remove--computername-from--computer-cmdlets-5277httpsgithubcompowershellpowershellissues5277"></a><span data-ttu-id="c8e2a-143">`*-Computer` コマンドレットから `-ComputerName` を削除 [#5277](https://github.com/PowerShell/PowerShell/issues/5277)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-143">Remove `-ComputerName` from `*-Computer` cmdlets [#5277](https://github.com/PowerShell/PowerShell/issues/5277)</span></span>

<span data-ttu-id="c8e2a-144">CoreFX の RPC リモート処理 (特に Windows 以外のプラットフォームで) の問題と、PowerShell で一貫性のあるリモート処理エクスペリエンスを保証するため、`\*-Computer` コマンドレットから `-ComputerName` パラメーターが削除されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-144">Due to issues with RPC remoting in CoreFX (particularly on non-Windows platforms) and ensuring a consistent remoting experience in PowerShell, the `-ComputerName` parameter was removed from the `\*-Computer` cmdlets.</span></span> <span data-ttu-id="c8e2a-145">コマンドレットをリモートで実行するには、代わりに `Invoke-Command` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-145">Use `Invoke-Command` instead as the way to execute cmdlets remotely.</span></span>

### <a name="remove--computername-from--service-cmdlets-5090httpsgithubcompowershellpowershellissues5094"></a><span data-ttu-id="c8e2a-146">`*-Service` コマンドレットから `-ComputerName` を削除 [#5090](https://github.com/PowerShell/PowerShell/issues/5094)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-146">Remove `-ComputerName` from `*-Service` cmdlets [#5090](https://github.com/PowerShell/PowerShell/issues/5094)</span></span>

<span data-ttu-id="c8e2a-147">一貫性のある PSRP の使用を促進するために、`*-Service` コマンドレットから `-ComputerName` パラメーターが削除されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-147">In order to encourage the consistent use of PSRP, the `-ComputerName` parameter was removed from `*-Service` cmdlets.</span></span>

### <a name="fix-get-item--literalpath-ab-if-ab-doesnt-actually-exist-to-return-error-5197httpsgithubcompowershellpowershellissues5197"></a><span data-ttu-id="c8e2a-148">`a*b` が実際に存在しない場合は、エラーを返すよう `Get-Item -LiteralPath a*b` を修正 [#5197](https://github.com/PowerShell/PowerShell/issues/5197)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-148">Fix `Get-Item -LiteralPath a*b` if `a*b` doesn't actually exist to return error [#5197](https://github.com/PowerShell/PowerShell/issues/5197)</span></span>

<span data-ttu-id="c8e2a-149">以前は、ワイルドカードを渡された `-LiteralPath` は `-Path` と同様に処理され、ワイルドカードを使ってファイルが検出されない場合は、何も返さず終了していました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-149">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="c8e2a-150">正しい動作として、ファイルが存在しない場合はエラーを返すには、`-LiteralPath` はリテラルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-150">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="c8e2a-151">`-Literal` にワイルドカードを使用した場合、リテラルとして処理するよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-151">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="import-csv-should-apply-pstypenames-upon-import-when-type-information-is-present-in-the-csv-5134httpsgithubcompowershellpowershellissues5134"></a><span data-ttu-id="c8e2a-152">インポート時に CSV に型情報が存在する場合、`Import-Csv` が `PSTypeNames` を適用 [#5134](https://github.com/PowerShell/PowerShell/issues/5134)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-152">`Import-Csv` should apply `PSTypeNames` upon import when type information is present in the CSV [#5134](https://github.com/PowerShell/PowerShell/issues/5134)</span></span>

<span data-ttu-id="c8e2a-153">以前は、`ConvertFrom-Csv` を使用してインポートされた `TypeInformation` を含む `Export-CSV` を使用してオブジェクトをエクスポートすると、型情報が保持されませんでした。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-153">Previously, objects exported using `Export-CSV` with `TypeInformation` imported with `ConvertFrom-Csv` were not retaining the type information.</span></span> <span data-ttu-id="c8e2a-154">今回の変更により、CSV ファイルから使用可能な場合は `PSTypeNames` メンバーに型情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-154">This change adds the type information to `PSTypeNames` member if available from the CSV file.</span></span>

### <a name="-notypeinformation-should-be-default-on-export-csv-5131httpsgithubcompowershellpowershellissues5131"></a><span data-ttu-id="c8e2a-155">`-NoTypeInformation` の既定値を `Export-Csv` に設定 [#5131](https://github.com/PowerShell/PowerShell/issues/5131)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-155">`-NoTypeInformation` should be default on `Export-Csv` [#5131](https://github.com/PowerShell/PowerShell/issues/5131)</span></span>

<span data-ttu-id="c8e2a-156">お客様からの声を反映して、`Export-CSV` の既定の動作として型情報を含めるよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-156">This change was made to address customer feedback on the default behavior of `Export-CSV` to include type information.</span></span>

<span data-ttu-id="c8e2a-157">以前は、コマンドレットから、オブジェクトの型名を含む最初の行としてコメントが出力されていました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-157">Previously, the cmdlet would output a comment as the first line containing the type name of the object.</span></span> <span data-ttu-id="c8e2a-158">ほとんどのツールでは認識されないため、既定ではこれを抑制されるよう変更されています。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-158">The change is to suppress this by default as it's not understood by most tools.</span></span> <span data-ttu-id="c8e2a-159">以前の動作のままにするには、`-IncludeTypeInformation` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-159">Use `-IncludeTypeInformation` to retain the previous behavior.</span></span>

### <a name="web-cmdlets-should-warn-when--credential-is-sent-over-unencrypted-connections-5112httpsgithubcompowershellpowershellissues5112"></a><span data-ttu-id="c8e2a-160">暗号化されていない接続経由で `-Credential` が送信された場合に、Web コマンドレットが警告 [#5112](https://github.com/PowerShell/PowerShell/issues/5112)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-160">Web Cmdlets should warn when `-Credential` is sent over unencrypted connections [#5112](https://github.com/PowerShell/PowerShell/issues/5112)</span></span>

<span data-ttu-id="c8e2a-161">HTTP を使用する場合、パスワードなどのコンテンツはクリア テキストとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-161">When using HTTP, content including passwords are sent as clear-text.</span></span> <span data-ttu-id="c8e2a-162">今回の変更は、これを既定で許可しないようにするもので、資格情報が安全でない方法で渡されると、エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-162">This change is to not allow this by default and return an error if credentials are being passed in an insecure manner.</span></span> <span data-ttu-id="c8e2a-163">`-AllowUnencryptedAuthentication` スイッチを使用すると、この動作を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-163">Users can bypass this by using the `-AllowUnencryptedAuthentication` switch.</span></span>

## <a name="api-changes"></a><span data-ttu-id="c8e2a-164">API の変更</span><span class="sxs-lookup"><span data-stu-id="c8e2a-164">API changes</span></span>

### <a name="remove-addtypecommandbase-class-5407httpsgithubcompowershellpowershellissues5407"></a><span data-ttu-id="c8e2a-165">`AddTypeCommandBase` クラスを削除 [#5407](https://github.com/PowerShell/PowerShell/issues/5407)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-165">Remove `AddTypeCommandBase` class [#5407](https://github.com/PowerShell/PowerShell/issues/5407)</span></span>

<span data-ttu-id="c8e2a-166">パフォーマンス向上のため、`Add-Type` から `AddTypeCommandBase` クラスが削除されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-166">The `AddTypeCommandBase` class was removed from `Add-Type` to improve performance.</span></span> <span data-ttu-id="c8e2a-167">このクラスは、Add-Type コマンドレットでのみ使用されており、ユーザーに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-167">This class is only used by the Add-Type cmdlet and should not impact users.</span></span>

### <a name="unify-cmdlets-with-parameter--encoding-to-be-of-type-systemtextencoding-5080httpsgithubcompowershellpowershellissues5080"></a><span data-ttu-id="c8e2a-168">コマンドレットと `-Encoding` パラメーターを `System.Text.Encoding` 型に統合 [#5080](https://github.com/PowerShell/PowerShell/issues/5080)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-168">Unify cmdlets with parameter `-Encoding` to be of type `System.Text.Encoding` [#5080](https://github.com/PowerShell/PowerShell/issues/5080)</span></span>

<span data-ttu-id="c8e2a-169">`-Encoding` の値 `Byte`はファイルシステム プロバイダーのコマンドレットから削除されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-169">The `-Encoding` value `Byte` has been removed from the filesystem provider cmdlets.</span></span> <span data-ttu-id="c8e2a-170">新しいパラメーター `-AsByteStream` を使用して、入力としてバイト ストリームが必要なこと、あるいは出力がバイト ストリームであることを指定してください。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-170">A new parameter, `-AsByteStream`, is now used to specify that a byte stream is required as input or that the output is a stream of bytes.</span></span>

### <a name="add-better-error-message-for-empty-and-null--uformat-parameter-5055httpsgithubcompowershellpowershellissues5055"></a><span data-ttu-id="c8e2a-171">`-UFormat` パラメーターが空または null の場合に、改善されたエラー メッセージを追加 [#5055](https://github.com/PowerShell/PowerShell/issues/5055)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-171">Add better error message for empty and null `-UFormat` parameter [#5055](https://github.com/PowerShell/PowerShell/issues/5055)</span></span>

<span data-ttu-id="c8e2a-172">以前は、`-UFormat` に空の形式の文字列が渡されると、有益でないエラー メッセージが表示されていました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-172">Previously, when passing an empty format string to `-UFormat`, an unhelpful error message would appear.</span></span> <span data-ttu-id="c8e2a-173">よりわかりやすいエラーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-173">A more descriptive error has been added.</span></span>

### <a name="clean-up-console-code-4995httpsgithubcompowershellpowershellissues4995"></a><span data-ttu-id="c8e2a-174">コンソール コードをクリーンアップ [#4995](https://github.com/PowerShell/PowerShell/issues/4995)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-174">Clean up console code [#4995](https://github.com/PowerShell/PowerShell/issues/4995)</span></span>

<span data-ttu-id="c8e2a-175">`-psconsolefile` スイッチおよびコード、`-importsystemmodules` スイッチおよびコード、およびフォントの変更コードは、レガシーの Windows PowerShell のために存在し、PowerShell Core でサポートされておらず、今後もサポートを追加する予定がないため、削除されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-175">The following features were removed as they are not supported in PowerShell Core, and there are no plans to add support as they exist for legacy reasons for Windows PowerShell: `-psconsolefile` switch and code, `-importsystemmodules` switch and code, and font changing code.</span></span>

### <a name="removed-runspaceconfiguration-support-4942httpsgithubcompowershellpowershellissues4942"></a><span data-ttu-id="c8e2a-176">`RunspaceConfiguration` のサポートを終了 [#4942](https://github.com/PowerShell/PowerShell/issues/4942)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-176">Removed `RunspaceConfiguration` support [#4942](https://github.com/PowerShell/PowerShell/issues/4942)</span></span>

<span data-ttu-id="c8e2a-177">以前は、API を使用してプログラミングによって PowerShell 実行空間を作成する場合、レガシー の [`RunspaceConfiguration`][runspaceconfig] と新しい [`InitialSessionState`][iss] のいずれかを使用できました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-177">Previously, when creating a PowerShell runspace programmatically using the API you could use the legacy [`RunspaceConfiguration`][runspaceconfig] or the newer [`InitialSessionState`][iss].</span></span> <span data-ttu-id="c8e2a-178">今回の変更により `RunspaceConfiguration` のサポートが終了し、`InitialSessionState` のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-178">This change removed support for `RunspaceConfiguration` and only supports `InitialSessionState`.</span></span>

[runspaceconfig]: https://docs.microsoft.com/dotnet/api/system.management.automation.runspaces.runspaceconfiguration
[iss]: https://docs.microsoft.com/dotnet/api/system.management.automation.runspaces.initialsessionstate

### <a name="commandinvocationintrinsicsinvokescript-bind-arguments-to-input-instead-of-args-4923httpsgithubcompowershellpowershellissues4923"></a><span data-ttu-id="c8e2a-179">`CommandInvocationIntrinsics.InvokeScript` が引数を `$args` ではなく `$input` にバインド [#4923](https://github.com/PowerShell/PowerShell/issues/4923)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-179">`CommandInvocationIntrinsics.InvokeScript` bind arguments to `$input` instead of `$args` [#4923](https://github.com/PowerShell/PowerShell/issues/4923)</span></span>

<span data-ttu-id="c8e2a-180">引数内のパラメーターの位置が正しくないため、引数ではなく入力として渡されていました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-180">An incorrect position of a parameter resulted in the args passed as input instead of as args.</span></span>

### <a name="remove-unsupported--showwindow-switch-from-get-help-4903httpsgithubcompowershellpowershellissues4903"></a><span data-ttu-id="c8e2a-181">サポートされていなかった `-showwindow` スイッチを `Get-Help` から削除 [#4903](https://github.com/PowerShell/PowerShell/issues/4903)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-181">Remove unsupported `-showwindow` switch from `Get-Help` [#4903](https://github.com/PowerShell/PowerShell/issues/4903)</span></span>

<span data-ttu-id="c8e2a-182">`-showwindow` では、CoreCLR でサポートされていない、WPF を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-182">`-showwindow` relies on WPF, which is not supported on CoreCLR.</span></span>

### <a name="allow--to-be-used-in-registry-path-for-remove-item-4866httpsgithubcompowershellpowershellissues4866"></a><span data-ttu-id="c8e2a-183">`Remove-Item` のレジストリ パスで \* が使用可能に [#4866](https://github.com/PowerShell/PowerShell/issues/4866)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-183">Allow \* to be used in registry path for `Remove-Item` [#4866](https://github.com/PowerShell/PowerShell/issues/4866)</span></span>

<span data-ttu-id="c8e2a-184">以前は、ワイルドカードを渡された `-LiteralPath` は `-Path` と同様に処理され、ワイルドカードを使ってファイルが検出されない場合は、何も返さず終了していました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-184">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="c8e2a-185">正しい動作として、ファイルが存在しない場合はエラーを返すには、`-LiteralPath` はリテラルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-185">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="c8e2a-186">`-Literal` にワイルドカードを使用した場合、リテラルとして処理するよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-186">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="fix-set-service-failing-test-4802httpsgithubcompowershellpowershellissues4802"></a><span data-ttu-id="c8e2a-187">テストで失敗していた `Set-Service` を修正 [#4802](https://github.com/PowerShell/PowerShell/issues/4802)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-187">Fix `Set-Service` failing test [#4802](https://github.com/PowerShell/PowerShell/issues/4802)</span></span>

<span data-ttu-id="c8e2a-188">以前は、`New-Service -StartupType foo` を使用している場合、`foo` は無視され、既定のスタートアップ タイプを使用して、サービスが作成されていました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-188">Previously, if `New-Service -StartupType foo` was used, `foo` was ignored and the service was created with some default startup type.</span></span> <span data-ttu-id="c8e2a-189">今回の変更により、無効なスタートアップ タイプの場合は、エラーが明示的にスローされます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-189">This change is to explicitly throw an error for an invalid startup type.</span></span>

### <a name="rename-isosx-to-ismacos-4700httpsgithubcompowershellpowershellissues4700"></a><span data-ttu-id="c8e2a-190">`$IsOSX` の名前を `$IsMacOS` に変更 [#4700](https://github.com/PowerShell/PowerShell/issues/4700)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-190">Rename `$IsOSX` to `$IsMacOS` [#4700](https://github.com/PowerShell/PowerShell/issues/4700)</span></span>

<span data-ttu-id="c8e2a-191">PowerShell の名前付けが Microsoft の名前規則に準拠し、OSX ではなく Apple の macOS が使用する名前付け規則に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-191">The naming in PowerShell should be consistent with our naming and conform to Apple's use of macOS instead of OSX.</span></span> <span data-ttu-id="c8e2a-192">ただし、読みやすさと整合性の目的で、引き続き Pascal の形式に従っています。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-192">However, for readability and consistently we are staying with Pascal casing.</span></span>

### <a name="make-error-message-consistent-when-invalid-script-is-passed-to--file-better-error-when-passed-ambiguous-argument-4573httpsgithubcompowershellpowershellissues4573"></a><span data-ttu-id="c8e2a-193">無効なスクリプトがファイルに渡されたときに一貫性のあるエラー メッセージを生成。あいまいな引数 が渡されたときのエラー表示を改善 [#4573](https://github.com/PowerShell/PowerShell/issues/4573)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-193">Make error message consistent when invalid script is passed to -File, better error when passed ambiguous argument [#4573](https://github.com/PowerShell/PowerShell/issues/4573)</span></span>

<span data-ttu-id="c8e2a-194">`pwsh.exe` の終了コードを Unix の規則と一致するよう変更</span><span class="sxs-lookup"><span data-stu-id="c8e2a-194">Change the exit codes of `pwsh.exe` to align with Unix conventions</span></span>

### <a name="removal-of-localaccount-and-cmdlets-from--diagnostics-modules-4302httpsgithubcompowershellpowershellissues4302-4303httpsgithubcompowershellpowershellissues4303"></a><span data-ttu-id="c8e2a-195">`Diagnostics` モジュールから `LocalAccount` およびコマンドレットを削除</span><span class="sxs-lookup"><span data-stu-id="c8e2a-195">Removal of `LocalAccount` and cmdlets from  `Diagnostics` modules.</span></span> <span data-ttu-id="c8e2a-196">[#4302](https://github.com/PowerShell/PowerShell/issues/4302) [#4303](https://github.com/PowerShell/PowerShell/issues/4303)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-196">[#4302](https://github.com/PowerShell/PowerShell/issues/4302) [#4303](https://github.com/PowerShell/PowerShell/issues/4303)</span></span>

<span data-ttu-id="c8e2a-197">API がサポートされていないため、改善されたソリューションが発表されるまで、`LocalAccounts` モジュールと `Diagnostics` モジュールの `Counter`コマンドレットが削除されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-197">Due to unsupported APIs, the `LocalAccounts` module and the `Counter` cmdlets in the `Diagnostics` module were removed until a better solution is found.</span></span>

### <a name="executing-powershell-script-with-bool-parameter-does-not-work-4036httpsgithubcompowershellpowershellissues4036"></a><span data-ttu-id="c8e2a-198">ブール値のパラメーターを使用する Powershell スクリプトが正しく動作しない [#4036](https://github.com/PowerShell/PowerShell/issues/4036)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-198">Executing powershell script with bool parameter does not work [#4036](https://github.com/PowerShell/PowerShell/issues/4036)</span></span>

<span data-ttu-id="c8e2a-199">以前は、powershell.exe (現在は `pwsh.exe`) で `-File` を使用して PowerShell スクリプトを実行する場合、$true/$false をパラメーター値として渡すことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-199">Previously, using powershell.exe (now `pwsh.exe`) to execute a PowerShell script using `-File` provided no way to pass $true/$false as parameter values.</span></span> <span data-ttu-id="c8e2a-200">解析された値としての $true/$false パラメーターのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-200">Support for $true/$false as parsed values to parameters was added.</span></span> <span data-ttu-id="c8e2a-201">現在、ドキュメントに記載されている構文が機能しないため、スイッチの値もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-201">Switch values are also supported as currently documented syntax doesn't work.</span></span>

### <a name="remove-clrversion-property-from-psversiontable-4027httpsgithubcompowershellpowershellissues4027"></a><span data-ttu-id="c8e2a-202">`$PSVersionTable` から `ClrVersion` プロパティを削除 [#4027](https://github.com/PowerShell/PowerShell/issues/4027)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-202">Remove `ClrVersion` property from `$PSVersionTable` [#4027](https://github.com/PowerShell/PowerShell/issues/4027)</span></span>

<span data-ttu-id="c8e2a-203">`$PSVersionTable` の `ClrVersion` プロパティは CoreCLR では有用でないため、エンドユーザーは、互換性を判定するためにこの値を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-203">The `ClrVersion` property of `$PSVersionTable` is not useful with CoreCLR, end users should not be using that value to determine compatibility.</span></span>

### <a name="change-positional-parameter-for-powershellexe-from--command-to--file-4019httpsgithubcompowershellpowershellissues4019"></a><span data-ttu-id="c8e2a-204">`powershell.exe` の位置指定パラメーターを `-Command` から `-File` に変更 [#4019](https://github.com/PowerShell/PowerShell/issues/4019)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-204">Change positional parameter for `powershell.exe` from `-Command` to `-File` [#4019](https://github.com/PowerShell/PowerShell/issues/4019)</span></span>

<span data-ttu-id="c8e2a-205">Windows 以外のプラットフォームでの PowerShell のシバン使用を有効化します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-205">Enable shebang use of PowerShell on non-Windows platforms.</span></span> <span data-ttu-id="c8e2a-206">Unix ベースのシステムでは、`pwsh` を明示的に呼び出すのではなく、自動的に PowerShell を起動するスクリプト実行可能ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-206">This means on Unix based systems, you can make a script executable that would invoke PowerShell automatically rather than explicitly invoking `pwsh`.</span></span> <span data-ttu-id="c8e2a-207">また、`-File` を指定せずに `powershell foo.ps1` または `powershell fooScript` のようなコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-207">This also means that you can now do things like `powershell foo.ps1` or `powershell fooScript` without specifying `-File`.</span></span> <span data-ttu-id="c8e2a-208">ただし、今回の変更後、`powershell.exe Get-Command` などのコマンドを実行しようとする場合は `-c` または `-Command` を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-208">However, this change now requires that you explicitly specify `-c` or `-Command` when trying to do things like `powershell.exe Get-Command`.</span></span>

### <a name="implement-unicode-escape-parsing-3958httpsgithubcompowershellpowershellissues3958"></a><span data-ttu-id="c8e2a-209">Unicode エスケープ解析の実装 [#3958](https://github.com/PowerShell/PowerShell/issues/3958)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-209">Implement Unicode escape parsing [#3958](https://github.com/PowerShell/PowerShell/issues/3958)</span></span>

<span data-ttu-id="c8e2a-210">`` `u#### `` または `` `u{####} `` は対応する Unicode 文字に変換されます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-210">`` `u#### `` or `` `u{####} `` is converted to the corresponding Unicode character.</span></span> <span data-ttu-id="c8e2a-211">`` `u `` リテラルを出力するには、``` ``u ``` のように、グラーブ文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-211">To output a literal `` `u ``, escape the backtick: ``` ``u ```.</span></span>

### <a name="change-new-modulemanifest-encoding-to-utf8nobom-on-non-windows-platforms-3940httpsgithubcompowershellpowershellissues3940"></a><span data-ttu-id="c8e2a-212">Windows 以外のプラットフォームの `New-ModuleManifest` エンコーディングを `UTF8NoBOM` に変更 [#3940](https://github.com/PowerShell/PowerShell/issues/3940)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-212">Change `New-ModuleManifest` encoding to `UTF8NoBOM` on non-Windows platforms [#3940](https://github.com/PowerShell/PowerShell/issues/3940)</span></span>

<span data-ttu-id="c8e2a-213">以前は、`New-ModuleManifest` は、BOM を使用して UTF-16 で psd1 マニフェストを作成しており、Linux ツールで問題が発生していました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-213">Previously, `New-ModuleManifest` creates psd1 manifests in UTF-16 with BOM, creating a problem for Linux tools.</span></span> <span data-ttu-id="c8e2a-214">今回の重要な変更により、Windows 以外のプラットフォーム上の エンコーディング `New-ModuleManifest` が UTF (BOM なし) に変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-214">This breaking change changes the encoding of `New-ModuleManifest` to be UTF (no BOM) in non-Windows platforms.</span></span>

### <a name="prevent-get-childitem-from-recursing-into-symlinks-1875-3780httpsgithubcompowershellpowershellissues3780"></a><span data-ttu-id="c8e2a-215">`Get-ChildItem` のシンボリック リンクへ反復を防止 (#1875)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-215">Prevent `Get-ChildItem` from recursing into symlinks (#1875).</span></span> [<span data-ttu-id="c8e2a-216">#3780</span><span class="sxs-lookup"><span data-stu-id="c8e2a-216">#3780</span></span>](https://github.com/PowerShell/PowerShell/issues/3780)

<span data-ttu-id="c8e2a-217">今回の変更により、`Get-ChildItem` と Unix の `ls -r` や Windows の `dir /s` ネイティブ コマンドとの連携度が向上しました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-217">This change brings `Get-ChildItem` more in line with the Unix `ls -r` and the Windows `dir /s` native commands.</span></span> <span data-ttu-id="c8e2a-218">上記のコマンドと同様、このコマンドレットでは、反復中に特定されたディレクトリへのシンボリック リンクが表示されますが、反復はされません。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-218">Like the mentioned commands, the cmdlet displays symbolic links to directories found during recursion, but does not recurse into them.</span></span>

### <a name="fix-get-content--delimiter-to-not-include-the-delimiter-in-the-returned-lines-3706httpsgithubcompowershellpowershellissues3706"></a><span data-ttu-id="c8e2a-219">返された行に区切り文字が含まれないように `Get-Content -Delimiter` を修正 [#3706](https://github.com/PowerShell/PowerShell/issues/3706)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-219">Fix `Get-Content -Delimiter` to not include the delimiter in the returned lines [#3706](https://github.com/PowerShell/PowerShell/issues/3706)</span></span>

<span data-ttu-id="c8e2a-220">以前は、`Get-Content -Delimiter` を使用したときの出力に一貫性がなく、区切り記号を削除するために追加のデータ処理が必要になり不便でした。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-220">Previously, the output while using `Get-Content -Delimiter` was inconsistent and inconvenient as it required further processing of the data to remove the delimiter.</span></span> <span data-ttu-id="c8e2a-221">今回の変更により、返される行の区切り記号が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-221">This change removes the delimiter in returned lines.</span></span>

### <a name="implement-format-hex-in-c-3320httpsgithubcompowershellpowershellissues3320"></a><span data-ttu-id="c8e2a-222">Format-hex を C# で実装 [#3320](https://github.com/PowerShell/PowerShell/issues/3320)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-222">Implement Format-Hex in C# [#3320](https://github.com/PowerShell/PowerShell/issues/3320)</span></span>

<span data-ttu-id="c8e2a-223">`-Raw` パラメーターは "no-op" になりました (なにも動作はしません)。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-223">The `-Raw` parameter is now a "no-op" (in that it does nothing).</span></span> <span data-ttu-id="c8e2a-224">今後は、その種類の数字のすべてのバイトを含め、数字がすべての出力に忠実に表示されます (今回の変更前は、`-Raw` パラメーターが正式にこの動作を実行していました)。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-224">Going forward all of the output will be displayed with a true representation of numbers that includes all of the bytes for its type (what the `-Raw` parameter was formally doing prior to this change).</span></span>

### <a name="powershell-as-a-default-shell-doesnt-work-with-script-command-3319httpsgithubcompowershellpowershellissues3319"></a><span data-ttu-id="c8e2a-225">既定シェルの PowerShell でスクリプト コマンドが正しく動作しない [#3319](https://github.com/PowerShell/PowerShell/issues/3319)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-225">PowerShell as a default shell doesn't work with script command [#3319](https://github.com/PowerShell/PowerShell/issues/3319)</span></span>

<span data-ttu-id="c8e2a-226">Unix では、対話型のシェルで `-i` の入力を受け付けることが通常で、多くのツールでこの動作が前提とされ、スイッチ `-i` を使ってシェルを呼び出します (たとえば `script` や、PowerShell が既定のシェルに設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-226">On Unix, it is a convention for shells to accept `-i` for an interactive shell and many tools expect this behavior (`script` for example, and when setting PowerShell as the default shell) and calls the shell with the `-i` switch.</span></span> <span data-ttu-id="c8e2a-227">以前は `-inputformat` と一致する便利な方法として `-i` を使用できましたが、この重要な変更後は `-in` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-227">This change is breaking in that `-i` previously could be used as short hand to match `-inputformat`, which now needs to be `-in`.</span></span>

### <a name="typo-fix-in-get-computerinfo-property-name-3167httpsgithubcompowershellpowershellissues3167"></a><span data-ttu-id="c8e2a-228">Get-computerinfo プロパティ名の入力ミスを修正 [#3167](https://github.com/PowerShell/PowerShell/issues/3167)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-228">Typo fix in Get-ComputerInfo property name [#3167](https://github.com/PowerShell/PowerShell/issues/3167)</span></span>

<span data-ttu-id="c8e2a-229">`BiosSerialNumber` が `BiosSeralNumber` と誤記されていましたが、正しいスペルに変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-229">`BiosSerialNumber` was misspelled as `BiosSeralNumber` and has been changed to the correct spelling.</span></span>

### <a name="add-get-stringhash-and-get-filehash-cmdlets-3024httpsgithubcompowershellpowershellissues3024"></a><span data-ttu-id="c8e2a-230">`Get-StringHash` および `Get-FileHash` コマンドレットを追加 [#3024](https://github.com/PowerShell/PowerShell/issues/3024)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-230">Add `Get-StringHash` and `Get-FileHash` cmdlets [#3024](https://github.com/PowerShell/PowerShell/issues/3024)</span></span>

<span data-ttu-id="c8e2a-231">CoreFX でサポートされていないハッシュ アルゴリズムがありましたが、今回の変更により、使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-231">This change is that some hash algorithms are not supported by CoreFX, therefore they are no longer available:</span></span>

- `MACTripleDES`
- `RIPEMD160`

### <a name="add-validation-on-get--cmdlets-where-passing-null-returns-all-objects-instead-of-error-2672httpsgithubcompowershellpowershellissues2672"></a><span data-ttu-id="c8e2a-232">$null を渡した場合、エラーではなくすべてのオブジェクトが返されるよう、`Get-*` コマンドレットに検証機能を追加 [#2672](https://github.com/PowerShell/PowerShell/issues/2672)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-232">Add validation on `Get-*` cmdlets where passing $null returns all objects instead of error [#2672](https://github.com/PowerShell/PowerShell/issues/2672)</span></span>

<span data-ttu-id="c8e2a-233">次のコマンドに `$null` を渡すと、エラーがスローされるよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-233">Passing `$null` to any of the following now throws an error:</span></span>

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

### <a name="add-support-w3c-extended-log-file-format-in-import-csv-2482httpsgithubcompowershellpowershellissues2482"></a><span data-ttu-id="c8e2a-234">`Import-Csv` に W3C 拡張ログ ファイル形式のサポートを追加 [#2482](https://github.com/PowerShell/PowerShell/issues/2482)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-234">Add support W3C Extended Log File Format in `Import-Csv` [#2482](https://github.com/PowerShell/PowerShell/issues/2482)</span></span>

<span data-ttu-id="c8e2a-235">以前は、`Import-Csv` コマンドレットを使用して、W3C 拡張ログ形式でログ ファイルを直接インポートできず、追加の操作が必要でした。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-235">Previously, the `Import-Csv` cmdlet cannot be used to directly import the log files in W3C extended log format and additional action would be required.</span></span> <span data-ttu-id="c8e2a-236">今回の変更により、W3C 拡張ログ形式がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-236">With this change, W3C extended log format is supported.</span></span>

### <a name="parameter-binding-problem-with-valuefromremainingarguments-in-ps-functions-2035httpsgithubcompowershellpowershellissues2035"></a><span data-ttu-id="c8e2a-237">PS 関数の `ValueFromRemainingArguments` でのパラメーター バインドの問題 [#2035](https://github.com/PowerShell/PowerShell/issues/2035)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-237">Parameter binding problem with `ValueFromRemainingArguments` in PS functions [#2035](https://github.com/PowerShell/PowerShell/issues/2035)</span></span>

<span data-ttu-id="c8e2a-238">`ValueFromRemainingArguments` は、それ自体が配列である単一の値ではなく、値を配列として返すよう変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-238">`ValueFromRemainingArguments` now returns the values as an array instead of a single value which itself is an array.</span></span>

### <a name="buildversion-is-removed-from-psversiontable-1415httpsgithubcompowershellpowershellissues1415"></a><span data-ttu-id="c8e2a-239">`$PSVersionTable` から `BuildVersion` が削除されました。[#1415](https://github.com/PowerShell/PowerShell/issues/1415)</span><span class="sxs-lookup"><span data-stu-id="c8e2a-239">`BuildVersion` is removed from `$PSVersionTable` [#1415](https://github.com/PowerShell/PowerShell/issues/1415)</span></span>

<span data-ttu-id="c8e2a-240">`$PSVersionTable` から `BuildVersion` プロパティを削除してください。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-240">Remove the `BuildVersion` property from `$PSVersionTable`.</span></span> <span data-ttu-id="c8e2a-241">このプロパティは、Windows のビルド バージョンと関連付けられていました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-241">This property was tied to the Windows build version.</span></span> <span data-ttu-id="c8e2a-242">代わりに、`GitCommitId` を使用して、PowerShell Core の正確なビルド バージョンを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-242">Instead, we recommend that you use `GitCommitId` to retrieve the exact build version of PowerShell Core.</span></span>

### <a name="changes-to-web-cmdlets"></a><span data-ttu-id="c8e2a-243">Web のコマンドレットへの変更</span><span class="sxs-lookup"><span data-stu-id="c8e2a-243">Changes to Web Cmdlets</span></span>

<span data-ttu-id="c8e2a-244">Web コマンドレットの基となる .NET API が `System.Net.Http.HttpClient` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-244">The underlying .NET API of the Web Cmdlets has been changed to `System.Net.Http.HttpClient`.</span></span> <span data-ttu-id="c8e2a-245">この変更は、多くのメリットを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-245">This change provides many benefits.</span></span> <span data-ttu-id="c8e2a-246">ただし、この変更と、Internet Explorer での相互運用性がないことを理由として、`Invoke-WebRequest` と `Invoke-RestMethod`に重要な変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-246">However, this change along with a lack of interoperability with Internet Explorer have resulted in several breaking changes within `Invoke-WebRequest` and `Invoke-RestMethod`.</span></span>

- <span data-ttu-id="c8e2a-247">`Invoke-WebRequest` では、基本的な HTML 解析のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-247">`Invoke-WebRequest` now supports basic HTML Parsing only.</span></span> <span data-ttu-id="c8e2a-248">`Invoke-WebRequest` は常に `BasicHtmlWebResponseObject` オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-248">`Invoke-WebRequest` always returns a `BasicHtmlWebResponseObject` object.</span></span> <span data-ttu-id="c8e2a-249">`ParsedHtml` および `Forms` プロパティが削除されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-249">The `ParsedHtml` and `Forms` properties have been removed.</span></span>
- <span data-ttu-id="c8e2a-250">`BasicHtmlWebResponseObject.Headers` の値は `String` から `String[]` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-250">`BasicHtmlWebResponseObject.Headers` values are now `String[]` instead of `String`.</span></span>
- <span data-ttu-id="c8e2a-251">`BasicHtmlWebResponseObject.BaseResponse` は、`System.Net.Http.HttpResponseMessage` オブジェクトに変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-251">`BasicHtmlWebResponseObject.BaseResponse` is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="c8e2a-252">Web コマンドレットの例外の `Response` プロパティが、`System.Net.Http.HttpResponseMessage` オブジェクトに変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-252">The `Response` property on Web Cmdlet exceptions is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="c8e2a-253">`-Headers` および `-UserAgent` パラメーターの既定設定が、Strict RFC ヘッダー解析に変更されました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-253">Strict RFC header parsing is now default for the `-Headers` and `-UserAgent` parameter.</span></span> <span data-ttu-id="c8e2a-254">これは、`-SkipHeaderValidation` を使用して無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-254">This can be bypassed with `-SkipHeaderValidation`.</span></span>
- <span data-ttu-id="c8e2a-255">`file://` および `ftp://` URI スキームのサポートは終了しました。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-255">`file://` and `ftp://` URI schemes are no longer supported.</span></span>
- <span data-ttu-id="c8e2a-256">`System.Net.ServicePointManager` 設定は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-256">`System.Net.ServicePointManager` settings are no longer honored.</span></span>
- <span data-ttu-id="c8e2a-257">現在、macOS では、証明書を使用した認証は使用できません。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-257">There is currently no certificate based authentication available on macOS.</span></span>
- <span data-ttu-id="c8e2a-258">`http://` URI 経由で `-Credential` を使用するとエラーになります。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-258">Use of `-Credential` over an `http://` URI will result in an error.</span></span> <span data-ttu-id="c8e2a-259">`https://` URI を使用するか、または `-AllowUnencryptedAuthentication`パラメーターを指定してエラーを回避してください。</span><span class="sxs-lookup"><span data-stu-id="c8e2a-259">Use an `https://` URI or supply the `-AllowUnencryptedAuthentication` parameter to suppress the error.</span></span>

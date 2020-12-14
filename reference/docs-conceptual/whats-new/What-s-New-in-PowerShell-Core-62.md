---
title: PowerShell Core 6.2 の新機能
description: PowerShell Core 6.2 でリリースされた新機能と変更
ms.date: 03/28/2019
ms.openlocfilehash: 98dd97b064e11509bf97e68e0a312e6b34b5d2bc
ms.sourcegitcommit: f9d855dd73b916559a22e337672dea3fbb11c634
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2020
ms.locfileid: "96833814"
---
# <a name="whats-new-in-powershell-core-62"></a><span data-ttu-id="20ff1-103">PowerShell Core 6.2 の新機能</span><span class="sxs-lookup"><span data-stu-id="20ff1-103">What's New in PowerShell Core 6.2</span></span>

<span data-ttu-id="20ff1-104">PowerShell Core 6.2 リリースでは、パフォーマンスの向上、バグ修正、品質を向上するためのコマンドレットと言語の軽微な強化に焦点を置いています。</span><span class="sxs-lookup"><span data-stu-id="20ff1-104">The PowerShell Core 6.2 release focused on performance improvements, bug fixes, and smaller cmdlet and language enhancements that improve the quality.</span></span> <span data-ttu-id="20ff1-105">すべての機能強化一覧については、GitHub で詳細な[変更ログ](https://github.com/PowerShell/PowerShell/releases)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20ff1-105">To see a full list of improvements, check out our detailed [changelogs](https://github.com/PowerShell/PowerShell/releases) on GitHub.</span></span>

## <a name="experimental-features"></a><span data-ttu-id="20ff1-106">試験的な機能</span><span class="sxs-lookup"><span data-stu-id="20ff1-106">Experimental Features</span></span>

<span data-ttu-id="20ff1-107">以前のバージョンで[試験的機能][]のサポートが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="20ff1-107">Previously, we enabled support for [Experimental Features][].</span></span> <span data-ttu-id="20ff1-108">6\.2 リリースでは、4 つの試験的機能を試すことができます。その機能を改善し、主流の機能に昇格させる価値があるかどうかを判断できるように、フィードバックを提供してください。</span><span class="sxs-lookup"><span data-stu-id="20ff1-108">In the 6.2 release, we have four experimental features to try out. Please provide feedback so we can make improvements and to decide whether the feature is worth promoting to mainstream status.</span></span>

<span data-ttu-id="20ff1-109">使用できる試験的機能の一覧を取得するには、`Get-ExperimentalFeature` を使います。</span><span class="sxs-lookup"><span data-stu-id="20ff1-109">Use `Get-ExperimentalFeature` to get a list of available experimental features.</span></span> <span data-ttu-id="20ff1-110">これらの機能は、`Enable-ExperimentalFeature` および `Disable-ExperimentalFeature` で有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-110">You can enable or disable these features with `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature`.</span></span>

### <a name="command-not-found-suggestions"></a><span data-ttu-id="20ff1-111">コマンドが見つからない場合の候補</span><span class="sxs-lookup"><span data-stu-id="20ff1-111">Command Not Found Suggestions</span></span>

<span data-ttu-id="20ff1-112">この機能では、あいまい一致を使用して、誤入力された可能性があるコマンドやコマンドレットの候補を見つけます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-112">This feature uses fuzzy matching to find suggestions for commands or cmdlets you may have mistyped.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSCommandNotFoundSuggestion
```

#### <a name="example"></a><span data-ttu-id="20ff1-113">例</span><span class="sxs-lookup"><span data-stu-id="20ff1-113">Example</span></span>

<span data-ttu-id="20ff1-114">この例では、スペルが正しくないコマンドレット名に対して、あいまい一致で可能性が高い候補から低い候補の順にいくつかの候補が検出されます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-114">In this example, the misspelled cmdlet name is fuzzy matched to several suggestions from most likely to least likely.</span></span>

```powershell
Get-Commnd
```

```Output
Get-Commnd : The term 'Get-Commnd' is not recognized as the name of a cmdlet, function, script file, or operable program.
Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-Commnd
+ ~~~~~~~~~~
+ CategoryInfo          : ObjectNotFound: (Get-Commnd:String) [], CommandNotFoundException
+ FullyQualifiedErrorId : CommandNotFoundException


Suggestion [4,General]: The most similar commands are: Get-Command, Get-Content, Get-Job, Get-Module, Get-Event, Get-Host, Get-Member, Get-Item, Set-Content.
```

### <a name="implicit-remoting-batching"></a><span data-ttu-id="20ff1-115">暗黙的なリモート バッチ処理</span><span class="sxs-lookup"><span data-stu-id="20ff1-115">Implicit Remoting Batching</span></span>

<span data-ttu-id="20ff1-116">パイプラインで[暗黙的なリモート処理](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/)を使用すると、PowerShell ではパイプライン内の各コマンドが個別に処理されます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-116">When using [implicit remoting](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/) in a pipeline, PowerShell treats each command in the pipeline independently.</span></span> <span data-ttu-id="20ff1-117">パイプラインの実行中、クライアントとリモート システムの間でオブジェクトのシリアル化と `de-serialized` が繰り返し行われます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-117">Objects are repeatedly serialized and `de-serialized` between the client and remote system over the execution of the pipeline.</span></span>

<span data-ttu-id="20ff1-118">この機能により、PowerShell ではパイプラインが分析され、コマンドを実行しても安全であり、コマンドがターゲット システム上に存在するかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-118">With this feature, PowerShell analyzes the pipeline to determine if the command is safe to run and it exists on the target system.</span></span> <span data-ttu-id="20ff1-119">true の場合、PowerShell ではパイプライン全体がリモートで実行され、クライアントに対して結果のシリアル化と `de-serializes` のみが行われます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-119">When true, PowerShell executes the entire pipeline remotely and only serializes and `de-serializes` the results back to the client.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSImplicitRemotingBatching
```

<span data-ttu-id="20ff1-120">localhost 上での `Get-Process | Sort-Object` の実際のテストは、10 - 15 秒から 20 - 30 **ミリ秒** に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-120">A real-world test of `Get-Process | Sort-Object` over localhost decreases from 10-15 seconds to 20-30 **milliseconds**.</span></span> <span data-ttu-id="20ff1-121">この機能は、クライアント上でのみ有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20ff1-121">The feature only needs to be enabled on the client.</span></span> <span data-ttu-id="20ff1-122">サーバー上で変更の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="20ff1-122">No changes are required on the server.</span></span>

### <a name="temp-drive"></a><span data-ttu-id="20ff1-123">一時ドライブ</span><span class="sxs-lookup"><span data-stu-id="20ff1-123">Temp Drive</span></span>

```powershell
Enable-ExperimentalFeature -Name PSTempDrive
```

<span data-ttu-id="20ff1-124">PowerShell Core をさまざまなオペレーティング システムで使用している場合、一時ディレクトリを見つけるための環境変数が Windows、macOS、Linux で異なることがわかります。</span><span class="sxs-lookup"><span data-stu-id="20ff1-124">If you're using PowerShell Core on different operating systems, you'll discover that the environment variable for finding the temporary directory is different on Windows, macOS, and Linux!</span></span> <span data-ttu-id="20ff1-125">この機能を使用すると、`Temp:` という [PSDrive][] が自動的に使用しているオペレーティング システムの一時フォルダーにマップされます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-125">With this feature, you get a [PSDrive][] called `Temp:` that is automatically mapped to the temporary folder for the operating system you are using.</span></span>

#### <a name="example"></a><span data-ttu-id="20ff1-126">例</span><span class="sxs-lookup"><span data-stu-id="20ff1-126">Example</span></span>

```powershell
PS> "Hello World!" > Temp:/hello.txt
PS> Get-Content Temp:/hello.txt
Hello World!
```

<span data-ttu-id="20ff1-127">ネイティブ ファイル コマンド (Linux 上の `ls` など) では PSDrive が認識されないため、この `Temp:` ドライブが表示されない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="20ff1-127">Be aware that native file commands (like `ls` on Linux) are not aware of PSDrives and won't see this `Temp:` drive.</span></span>

### <a name="abbreviation-expansion"></a><span data-ttu-id="20ff1-128">短縮形の展開</span><span class="sxs-lookup"><span data-stu-id="20ff1-128">Abbreviation Expansion</span></span>

<span data-ttu-id="20ff1-129">PowerShell コマンドレットには、わかりやすい名詞が用意されています。</span><span class="sxs-lookup"><span data-stu-id="20ff1-129">PowerShell cmdlets are expected to have descriptive nouns.</span></span> <span data-ttu-id="20ff1-130">その結果、長い名前は入力がより困難になっています。</span><span class="sxs-lookup"><span data-stu-id="20ff1-130">This results in long names that are more difficult to type.</span></span> <span data-ttu-id="20ff1-131">この機能を使用すると、コマンドレットの大文字を入力し、タブ補完を使用して一致を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-131">This feature allows you to just type the uppercase characters of the cmdlet and use tab-completion to find a match.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSUseAbbreviationExpansion
```

#### <a name="example"></a><span data-ttu-id="20ff1-132">例</span><span class="sxs-lookup"><span data-stu-id="20ff1-132">Example</span></span>

```powershell
PS> i-arsavsf
```

<span data-ttu-id="20ff1-133">Tab キーを押し、Azure PowerShell [Az](https://www.powershellgallery.com/packages/Az) モジュールをインストールしている場合は、次のようにオートコンプリートされます。</span><span class="sxs-lookup"><span data-stu-id="20ff1-133">If you hit tab, and have the Azure PowerShell [Az](https://www.powershellgallery.com/packages/Az) module installed, it will autocomplete to:</span></span>

```Output
PS> Import-AzRecoveryServicesAsrVaultSettingsFile
```

> [!NOTE]
> <span data-ttu-id="20ff1-134">この機能は、対話的に使用するためのものです。</span><span class="sxs-lookup"><span data-stu-id="20ff1-134">This feature is intended to be used interactively.</span></span> <span data-ttu-id="20ff1-135">短縮形のコマンドレットは実行できません。</span><span class="sxs-lookup"><span data-stu-id="20ff1-135">Abbreviated forms of cmdlets can't be executed.</span></span>
> <span data-ttu-id="20ff1-136">この機能はエイリアスに代わるものではありません。</span><span class="sxs-lookup"><span data-stu-id="20ff1-136">This feature is not a replacement for aliases.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="20ff1-137">重大な変更</span><span class="sxs-lookup"><span data-stu-id="20ff1-137">Breaking Changes</span></span>

- <span data-ttu-id="20ff1-138">Windows PowerShell に合わせて `Write-Output` の `-NoEnumerate` の動作を修正します。</span><span class="sxs-lookup"><span data-stu-id="20ff1-138">Fix `-NoEnumerate` behavior in `Write-Output` to be consistent with Windows PowerShell.</span></span> <span data-ttu-id="20ff1-139">(#9069)</span><span class="sxs-lookup"><span data-stu-id="20ff1-139">(#9069)</span></span>
- <span data-ttu-id="20ff1-140">`Join-String -InputObject 1,2,3` の結果を `1,2,3 | Join-String` の結果と同じにします (#8611) (@sethvs に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-140">Make `Join-String -InputObject 1,2,3` result equal to `1,2,3 | Join-String` result (#8611) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="20ff1-141">`-Stable` を `Sort-Object` と関連するテストに追加します (#7862) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-141">Add `-Stable` to `Sort-Object` and related tests (#7862) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="20ff1-142">小数部の秒を受け入れるように `Start-Sleep` コマンドレットを改善します (#8537) (@Prototyyppi に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-142">Improve `Start-Sleep` cmdlet to accept fractional seconds (#8537) (Thanks @Prototyyppi!)</span></span>
- <span data-ttu-id="20ff1-143">すべてのカルチャで `case-insensitive` の OrdinalIgnoreCase を使用するようにハッシュテーブルを変更します (#8566)</span><span class="sxs-lookup"><span data-stu-id="20ff1-143">Change hashtable to use OrdinalIgnoreCase to be `case-insensitive` in all Cultures (#8566)</span></span>
- <span data-ttu-id="20ff1-144">`Import-Csv` の **LiteralPath** を `Get-ChildItem` 出力にバインドするように修正します (#8277) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-144">Fix **LiteralPath** in `Import-Csv` to bind to `Get-ChildItem` output (#8277) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="20ff1-145">`Import-Csv` で二重引用符の区切り記号が使用されている場合に、名前なしの列をスキップしなくなります (#7899) (@Topping に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-145">No longer skips a column without name if double quote delimiter is used in `Import-Csv` (#7899) (Thanks @Topping!)</span></span>
- <span data-ttu-id="20ff1-146">`Get-ExperimentalFeature` に `-ListAvailable` スイッチがなくなります (#8318)</span><span class="sxs-lookup"><span data-stu-id="20ff1-146">`Get-ExperimentalFeature` no longer has `-ListAvailable` switch (#8318)</span></span>
- <span data-ttu-id="20ff1-147">デバッグ パラメーターで、`$DebugPreference` が **Inquire** ではなく **Continue** に設定されるようになります (#8195) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-147">Debug parameter now sets `$DebugPreference` to **Continue** instead of **Inquire** (#8195) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="20ff1-148">pwsh で使用される非対話型のリダイレクトされ、エンコードされたコマンドで指定されている場合は、`-OutputFormat` を適用します (#8115)</span><span class="sxs-lookup"><span data-stu-id="20ff1-148">Honor `-OutputFormat` if specified in non-interactive, redirected, encoded command used with pwsh (#8115)</span></span>
- <span data-ttu-id="20ff1-149">GAC から読み込む前に、モジュール ベース パスからアセンブリを読み込みます (#8073)</span><span class="sxs-lookup"><span data-stu-id="20ff1-149">Load assembly from module base path before trying to load from the GAC (#8073)</span></span>
- <span data-ttu-id="20ff1-150">Linux プレビュー パッケージからチルダを削除します (#8244)</span><span class="sxs-lookup"><span data-stu-id="20ff1-150">Remove tilde from Linux preview packages (#8244)</span></span>
- <span data-ttu-id="20ff1-151">プロファイルの処理の前に `-WorkingDirectory` の処理を移動します (#8079)</span><span class="sxs-lookup"><span data-stu-id="20ff1-151">Move processing of `-WorkingDirectory` before processing of profiles (#8079)</span></span>
- <span data-ttu-id="20ff1-152">Unix 上では `PATHEXT` 環境変数を追加しません (#7697) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-152">Do not add `PATHEXT` environment variable on Unix (#7697) (Thanks @iSazonov!)</span></span>

## <a name="known-issues"></a><span data-ttu-id="20ff1-153">既知の問題</span><span class="sxs-lookup"><span data-stu-id="20ff1-153">Known Issues</span></span>

- <span data-ttu-id="20ff1-154">Windows IOT ARM プラットフォーム上のリモート処理には、モジュールの読み込みに関する問題があります。</span><span class="sxs-lookup"><span data-stu-id="20ff1-154">Remoting on Windows IOT ARM platforms has an issue loading modules.</span></span> <span data-ttu-id="20ff1-155">(#8053) を参照してください</span><span class="sxs-lookup"><span data-stu-id="20ff1-155">See (#8053)</span></span>

## <a name="general-updates-and-fixes"></a><span data-ttu-id="20ff1-156">一般的な更新と修正</span><span class="sxs-lookup"><span data-stu-id="20ff1-156">General Updates and Fixes</span></span>

- <span data-ttu-id="20ff1-157">大文字と小文字を区別するファイルシステム上で、ファイルとフォルダーの大文字と小文字を区別しないタブ補完を有効にします (#8128)</span><span class="sxs-lookup"><span data-stu-id="20ff1-157">Enable case-insensitive tab completion for files and folders on case-sensitive filesystem (#8128)</span></span>
- <span data-ttu-id="20ff1-158">PSVersionInfo.PSVersion と PSVersionInfo.PSEdition を公開します (#8054) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-158">Make PSVersionInfo.PSVersion and PSVersionInfo.PSEdition public (#8054) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="20ff1-159">`catch{ }` ブロック内の `$_` / `$PSItem` に型の推定を追加します (#8020) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-159">Add Type Inference for `$_` / `$PSItem` in `catch{ }` blocks (#8020) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="20ff1-160">静的メソッド呼び出しの型の推定を修正します (#8018) (@SeeminglyScience に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-160">Fix static method invocation type inference (#8018) (Thanks @SeeminglyScience!)</span></span>
- <span data-ttu-id="20ff1-161">`Select-Object`、`Group-Object`、**PSObject**、**ハッシュテーブル** に推定された型を作成します (#7231) (@powercode に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-161">Create inferred types for `Select-Object`, `Group-Object`, **PSObject** and **Hashtable** (#7231) (Thanks @powercode!)</span></span>
- <span data-ttu-id="20ff1-162">`ByRef-like` 型パラメーターを使用した呼び出し方法をサポートします (#7721)</span><span class="sxs-lookup"><span data-stu-id="20ff1-162">Support calling method with `ByRef-like` type parameters (#7721)</span></span>
- <span data-ttu-id="20ff1-163">Windows PowerShell モジュールのパスが環境の PSModulePath に既に含まれている場合を処理します (#7727)</span><span class="sxs-lookup"><span data-stu-id="20ff1-163">Handle the case where the Windows PowerShell module path is already in the environment's PSModulePath (#7727)</span></span>
- <span data-ttu-id="20ff1-164">プレーン テキストを格納することで非 Windows 向けに `SecureString` コマンドレットを有効にします (#9199)</span><span class="sxs-lookup"><span data-stu-id="20ff1-164">Enable `SecureString` cmdlets for non-Windows by storing the plain text (#9199)</span></span>
- <span data-ttu-id="20ff1-165">securestring を使用して clixml をインポートするときの非 Windows 上のエラー メッセージを改善します (#7997)</span><span class="sxs-lookup"><span data-stu-id="20ff1-165">Improve error message on non-Windows when importing clixml with securestring (#7997)</span></span>
- <span data-ttu-id="20ff1-166">パラメーター ReplyTo を `Send-MailMessage` に追加します (#8727) (@replicaJunction に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-166">Adding parameter ReplyTo to `Send-MailMessage` (#8727) (Thanks @replicaJunction!)</span></span>
- <span data-ttu-id="20ff1-167">現在不使用のメッセージを `Send-MailMessage` に追加します (#9178)</span><span class="sxs-lookup"><span data-stu-id="20ff1-167">Add Obsolete message to `Send-MailMessage` (#9178)</span></span>
- <span data-ttu-id="20ff1-168">WinRM が存在しないときに `localhost` 上で動作するよう `Restart-Computer` を修正します (#9160)</span><span class="sxs-lookup"><span data-stu-id="20ff1-168">Fix `Restart-Computer` to work on `localhost` when WinRM is not present (#9160)</span></span>
- <span data-ttu-id="20ff1-169">PowerShell のホスト中に `Start-Job` から終了エラーをスローするようにします (#9128)</span><span class="sxs-lookup"><span data-stu-id="20ff1-169">Make `Start-Job` throw terminating error when PowerShell is being hosted (#9128)</span></span>
- <span data-ttu-id="20ff1-170">ushort、uint、ulong、short リテラルに C# スタイルの型のアクセラレータとサフィックスを追加します (#7813) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-170">Add C# style type accelerators and suffixes for ushort, uint, ulong, and short literals (#7813) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="20ff1-171">数値リテラルに新しいサフィックスを追加します - [about_Numeric_Literals][] を参照してください (#7901) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-171">Added new suffixes for numeric literals - see [about_Numeric_Literals][] (#7901) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="20ff1-172">SupportsShouldProcess が 'true' に設定されていない場合の影響レベルを正しく報告します (#8209) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-172">Correctly Report impact level when SupportsShouldProcess is not set to 'true' (#8209) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="20ff1-173">Web コマンドレットの要求文字セットの問題を修正しました (#8742) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-173">Fix Request Charset Issues in Web Cmdlets (#8742) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="20ff1-174">Web コマンドレットの期待値 `100-continue` の問題を修正します (#8679) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-174">Fix Expect `100-continue` issue with Web Cmdlets (#8679) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="20ff1-175">Web コマンドレットに関するファイル ブロックの問題を修正します (#7676) (@Claustn に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-175">Fix file blocking issue with web cmdlets (#7676) (Thanks @Claustn!)</span></span>
- <span data-ttu-id="20ff1-176">`Invoke-RestMethod` のコード ページ解析の問題を修正します (#8694) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-176">Fix code page parsing issue in `Invoke-RestMethod` (#8694) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="20ff1-177">JsonObject.ConvertToJson をパブリック API として公開するように `ConvertTo-Json` をリファクタリングします (#8682)</span><span class="sxs-lookup"><span data-stu-id="20ff1-177">Refactor `ConvertTo-Json` to expose JsonObject.ConvertToJson as a public API (#8682)</span></span>
- <span data-ttu-id="20ff1-178">-Depth を使用して構成できる最大深度を `ConvertFrom-Json` に追加します (#8199) (@louistio に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-178">Add configurable maximum depth in `ConvertFrom-Json` with -Depth (#8199) (Thanks @louistio!)</span></span>
- <span data-ttu-id="20ff1-179">`ConvertTo-Json` コマンドレットに EscapeHandling パラメーターを追加します (#7775) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-179">Add EscapeHandling parameter in `ConvertTo-Json` cmdlet (#7775) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="20ff1-180">pwsh と `Enter-PSHostProcess` に `-CustomPipeName` を追加します (#8889)</span><span class="sxs-lookup"><span data-stu-id="20ff1-180">Add `-CustomPipeName` to pwsh and `Enter-PSHostProcess` (#8889)</span></span>
- <span data-ttu-id="20ff1-181">Windows 上で `New-Item` を使用して相対シンボリック リンクを作成できるようにします (#8783)</span><span class="sxs-lookup"><span data-stu-id="20ff1-181">Enable creating relative symbolic links on Windows with `New-Item` (#8783)</span></span>
- <span data-ttu-id="20ff1-182">開発者モードの Windows ユーザーが昇格なしでシンボリック リンクを作成できるようにします (#8534)</span><span class="sxs-lookup"><span data-stu-id="20ff1-182">Allow Windows users in developer mode to create symlinks without elevation (#8534)</span></span>
- <span data-ttu-id="20ff1-183">`Write-Information` で `$null` を受け付けるようにします (#8774)</span><span class="sxs-lookup"><span data-stu-id="20ff1-183">Enable `Write-Information` to accept `$null` (#8774)</span></span>
- <span data-ttu-id="20ff1-184">MAML ヘルプ コンテンツを含め、高度な関数の `Get-Help` を修正します (#8353)</span><span class="sxs-lookup"><span data-stu-id="20ff1-184">Fix `Get-Help` for advanced functions with MAML help content (#8353)</span></span>
- <span data-ttu-id="20ff1-185">1 つのパラメーターのみが宣言されいる場合の -Parameter に関する `Get-Help` PSTypeName の問題を修正します (#8754) (@pougetat に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-185">Fix `Get-Help` PSTypeName issue with -Parameter when only one parameter is declared (#8754) (Thanks @pougetat!)</span></span>
- <span data-ttu-id="20ff1-186">コメントのヘルプとして ScriptBlock で実行された `Get-Help` のトークン計算の修正。</span><span class="sxs-lookup"><span data-stu-id="20ff1-186">Token calculation fix for `Get-Help` executed on ScriptBlock for comment help.</span></span> <span data-ttu-id="20ff1-187">(#8238) (@hubuk に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-187">(#8238) (Thanks @hubuk!)</span></span>
- <span data-ttu-id="20ff1-188">文字列配列を受け付けるように `Get-Help` コマンドレットの -Parameter パラメーターを変更します (#8454) (@sethvs に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-188">Change `Get-Help` cmdlet -Parameter parameter so it accepts string arrays (#8454) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="20ff1-189">パスにスペースが含まれている場合は PAGER を解決します (#8571) (@pougetat に感謝)。</span><span class="sxs-lookup"><span data-stu-id="20ff1-189">Resolve PAGER if its path contains spaces (#8571) (Thanks @pougetat!)</span></span>
- <span data-ttu-id="20ff1-190">関数 'help' の `less` の使用に、ユーザーに終了方法を指示するプロンプトを追加します (#7998)</span><span class="sxs-lookup"><span data-stu-id="20ff1-190">Add prompt to the use of `less` in the function 'help' to instruct user how to quit (#7998)</span></span>
- <span data-ttu-id="20ff1-191">`Format-Hex` コマンドレットに enum 型と char 型のサポートを追加します (#8191) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-191">Add support enum and char types in `Format-Hex` cmdlet (#8191) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="20ff1-192">`Format-Hex` から ShouldProcess を削除します (#8178)</span><span class="sxs-lookup"><span data-stu-id="20ff1-192">Remove ShouldProcess from `Format-Hex` (#8178)</span></span>
- <span data-ttu-id="20ff1-193">新しい Offset および Count パラメーターを `Format-Hex` に追加し、コマンドレットをリファクターリングします (#7877) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-193">Add new Offset and Count parameters to `Format-Hex` and refactor the cmdlet (#7877) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="20ff1-194">`ConvertTo-Html` で 'label' のエイリアス キーとして 'name' を許可し、'width' エントリを整数にすることを許可します (#8426) (@mklement0 に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-194">Allow 'name' as an alias key for 'label' in `ConvertTo-Html`, allow the 'width' entry to be an integer (#8426) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="20ff1-195">`ConvertTo-Html` でスクリプトブロック ベースの計算プロパティを再び機能するようにします (#8427) (@mklement0 に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-195">Make scriptblock based calculated properties work again in `ConvertTo-Html` (#8427) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="20ff1-196">パイプライン入力からテキストを作成するコマンドレット `Join-String` を追加します (#7660) (@powercode に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-196">Add cmdlet `Join-String` for creating text from pipeline input (#7660) (Thanks @powercode!)</span></span>
- <span data-ttu-id="20ff1-197">`Join-String` コマンドレットの FormatString パラメーターのロジックを修正します (#8449) (@sethvs に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-197">Fix `Join-String` cmdlet FormatString parameter logic (#8449) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="20ff1-198">`$RAWUI` を使用するように `Clear-Host` を変更し、リモート処理のやり直しを許可します (#8609)</span><span class="sxs-lookup"><span data-stu-id="20ff1-198">Change `Clear-Host` back to using `$RAWUI` and clear to work over remoting (#8609)</span></span>
- <span data-ttu-id="20ff1-199">`Clear-Host` を単に `[console]::clear` という名前に変更し、Unix から clear エイリアスを削除します (#8603)</span><span class="sxs-lookup"><span data-stu-id="20ff1-199">Change `Clear-Host` to simply called `[console]::clear` and remove clear alias from Unix (#8603)</span></span>
- <span data-ttu-id="20ff1-200">`Import-Csv` の LiteralPath を `Get-ChildItem` 出力にバインドするように修正します (#8277) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-200">Fix LiteralPath in `Import-Csv` to bind to `Get-ChildItem` output (#8277) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="20ff1-201">AliasHelpInfo のヘルプ関数でポケットベルを使用しないようにします (#8552)</span><span class="sxs-lookup"><span data-stu-id="20ff1-201">help function shouldn't use pager for AliasHelpInfo (#8552)</span></span>
- <span data-ttu-id="20ff1-202">トランスクリプト ヘッダーを最小化する `-UseMinimalHeader` を `Start-Transcript` に追加します (#8402) (@lukexjeremy に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-202">Add `-UseMinimalHeader` to `Start-Transcript` to minimize transcript header (#8402) (Thanks @lukexjeremy!)</span></span>
- <span data-ttu-id="20ff1-203">`Enable-ExperimentalFeature` および `Disable-ExperimentalFeature` コマンドレットを追加します (#8318)</span><span class="sxs-lookup"><span data-stu-id="20ff1-203">Add `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature` cmdlets (#8318)</span></span>
- <span data-ttu-id="20ff1-204">logman.exe を使用できる場合、**PSDiagnostics** のすべてのコマンドレットを公開します (#8366)</span><span class="sxs-lookup"><span data-stu-id="20ff1-204">Expose all cmdlets from **PSDiagnostics** if logman.exe is available (#8366)</span></span>
- <span data-ttu-id="20ff1-205">`non-Windows` プラットフォームの `New-PSDrive` から **Persist** パラメーターを削除します (#8291) (@lukexjeremy に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-205">Remove **Persist** parameter from `New-PSDrive` on `non-Windows` platform (#8291) (Thanks @lukexjeremy!)</span></span>
- <span data-ttu-id="20ff1-206">`cd +` のサポートを追加します (#7206) (@bergmeister に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-206">Add support for `cd +` (#7206) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="20ff1-207">`Set-Location -LiteralPath` を - および+という名前のフォルダーで機能するようにします (#8089)</span><span class="sxs-lookup"><span data-stu-id="20ff1-207">Enable `Set-Location -LiteralPath` to work with folders named - and + (#8089)</span></span>
- <span data-ttu-id="20ff1-208">空または `$null` のパス値を指定すると、`Test-Path` は `$false` を返します (#8080) (@vexx32 に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-208">`Test-Path` returns `$false` when given an empty or `$null` path value (#8080) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="20ff1-209">パスがどのプロバイダーと一致しない場合でも、動的パラメーターが返されるようにします (#7957)</span><span class="sxs-lookup"><span data-stu-id="20ff1-209">Allow dynamic parameter to be returned even if path does not match any provider (#7957)</span></span>
- <span data-ttu-id="20ff1-210">Unix プラットフォーム上で `Get-PSHostProcessInfo` と `Enter-PSHostProcess` をサポートします (#8232)</span><span class="sxs-lookup"><span data-stu-id="20ff1-210">Support `Get-PSHostProcessInfo` and `Enter-PSHostProcess` on Unix platforms (#8232)</span></span>
- <span data-ttu-id="20ff1-211">`Get-Content` コマンドレットの割り当てを減らします (#8103) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-211">Reduce allocations in `Get-Content` cmdlet (#8103) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="20ff1-212">コンテンツの書き込み中に `Add-Content` が他のツールと読み取りアクセスを共有できるようにします (#8091)</span><span class="sxs-lookup"><span data-stu-id="20ff1-212">Enable `Add-Content` to share read access with other tools while writing content (#8091)</span></span>
- <span data-ttu-id="20ff1-213">コンテナーをターゲットにするときに `Get/Add-Content` から返されるエラーを改善します (#7823) (@kvprasoon に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-213">`Get/Add-Content` throws improved error when targeting a container (#7823) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="20ff1-214">`-Name`、`-NoUserOverrides`、`-ListAvailable` パラメーターを `Get-Culture` コマンドレットに追加します (#7702) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-214">Add `-Name`, `-NoUserOverrides` and `-ListAvailable` parameters to `Get-Culture` cmdlet (#7702) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="20ff1-215">**Encoding** パラメーターの補完用に統一された属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="20ff1-215">Add unified attribute for completion for **Encoding** parameter.</span></span> <span data-ttu-id="20ff1-216">(#7732) (@ThreeFive-O に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-216">(#7732) (Thanks @ThreeFive-O!)</span></span>
- <span data-ttu-id="20ff1-217">数値 ID と登録済みコード ページの名前を **Encoding** パラメーターで許可します (#7636) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-217">Allow numeric Ids and name of registered code pages in **Encoding** parameters (#7636) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="20ff1-218">ワイルドカード文字を使用する `Rename-Item -Path` を修正します (#7398) (@kwkam に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-218">Fix `Rename-Item -Path` with wildcard char (#7398) (Thanks @kwkam!)</span></span>
- <span data-ttu-id="20ff1-219">`Start-Transcript` を使用してファイルが存在する場合、ファイルを削除するのではなく、ファイルを空にします (#8131) (@paalbra に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-219">When using `Start-Transcript` and file exists, empty file rather than deleting (#8131) (Thanks @paalbra!)</span></span>
- <span data-ttu-id="20ff1-220">明示的に **FileAccess.Read** と **FileShare.Read** を指定して `Add-Type` をオープン ソース ファイルにします (#7915) (@IISResetMe に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-220">Make `Add-Type` open source files with **FileAccess.Read** and **FileShare.Read** explicitly (#7915) (Thanks @IISResetMe!)</span></span>
- <span data-ttu-id="20ff1-221">最新の Windows に合わせて `Enter-PSSession -ContainerId` を修正します (#7883)</span><span class="sxs-lookup"><span data-stu-id="20ff1-221">Fix `Enter-PSSession -ContainerId` for the latest Windows (#7883)</span></span>
- <span data-ttu-id="20ff1-222">**NestedModules** プロパティに `Test-ModuleManifest` が設定されるようにします (#7859)</span><span class="sxs-lookup"><span data-stu-id="20ff1-222">Ensure **NestedModules** property gets populated by `Test-ModuleManifest` (#7859)</span></span>
- <span data-ttu-id="20ff1-223">`Get-Date` -UFormat に `%F` のケースを追加します (#7630) (@britishben に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-223">Add `%F` case to `Get-Date` -UFormat (#7630) (Thanks @britishben!)</span></span>
- <span data-ttu-id="20ff1-224">依存関係のあるサービスを停止するように `Set-Service -Status Stopped` を修正します (#5525) (@zhenggu に感謝)</span><span class="sxs-lookup"><span data-stu-id="20ff1-224">Fix `Set-Service -Status Stopped` to stop services with dependencies (#5525) (Thanks @zhenggu!)</span></span>

<!-- Link references -->
[about_Numeric_Literals]: /powershell/module/Microsoft.PowerShell.Core/About/about_numeric_literals
[試験的機能]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[Experimental Features]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[PSDrive]: /powershell/module/microsoft.powershell.management/new-psdrive

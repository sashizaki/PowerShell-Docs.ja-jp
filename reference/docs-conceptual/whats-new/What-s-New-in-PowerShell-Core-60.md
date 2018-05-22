# <a name="whats-new-in-powershell-core-60"></a><span data-ttu-id="82b16-101">PowerShell Core 6.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="82b16-101">What's New in PowerShell Core 6.0</span></span>

<span data-ttu-id="82b16-102">[PowerShell Core 6.0][github] は、異機種混合環境とハイブリッド クラウド用に構築されたオープン ソースのクロスプラットフォーム (Windows、macOS、Linux) である、PowerShell の新しいエディションです。</span><span class="sxs-lookup"><span data-stu-id="82b16-102">[PowerShell Core 6.0][github] is a new edition of PowerShell that is cross-platform (Windows, macOS, and Linux), open-source, and built for heterogeneous environments and the hybrid cloud.</span></span>

## <a name="moved-from-net-framework-to-net-core"></a><span data-ttu-id="82b16-103">.NET Framework から .NET Core への移行</span><span class="sxs-lookup"><span data-stu-id="82b16-103">Moved from .NET Framework to .NET Core</span></span>

<span data-ttu-id="82b16-104">PowerShell Core では、ランタイムとして [.NET Core 2.0][] を使用します。</span><span class="sxs-lookup"><span data-stu-id="82b16-104">PowerShell Core uses [.NET Core 2.0][] as its runtime.</span></span>
<span data-ttu-id="82b16-105">.NET core 2.0 を使用することで、PowerShell Core を複数のプラットフォーム (Windows、macOS、Linux) で動作させることができます。</span><span class="sxs-lookup"><span data-stu-id="82b16-105">.NET Core 2.0 enables PowerShell Core to work on multiple platforms (Windows, macOS, and Linux).</span></span>
<span data-ttu-id="82b16-106">PowerShell Core では、PowerShell のコマンドレットとスクリプトで使用される、.NET Core 2.0 によって提供される API セットも公開します。</span><span class="sxs-lookup"><span data-stu-id="82b16-106">PowerShell Core also exposes the API set offered by .NET Core 2.0 to be used in PowerShell cmdlets and scripts.</span></span>

<span data-ttu-id="82b16-107">Windows PowerShell では、.NET Framework ランタイムを使用して PowerShell エンジンをホストしていました。</span><span class="sxs-lookup"><span data-stu-id="82b16-107">Windows PowerShell used the .NET Framework runtime to host the PowerShell engine.</span></span>
<span data-ttu-id="82b16-108">これは、Windows PowerShell が .NET Framework によって提供される API セットを公開することを意味します。</span><span class="sxs-lookup"><span data-stu-id="82b16-108">This means that Windows PowerShell exposes the API set offered by .NET Framework.</span></span>

<span data-ttu-id="82b16-109">.NET Core と .NET Framework の間で共有される API は、[.NET Standard][] の一部として定義されています。</span><span class="sxs-lookup"><span data-stu-id="82b16-109">The APIs shared between .NET Core and .NET Framework are defined as part of [.NET Standard][].</span></span>

<span data-ttu-id="82b16-110">PowerShell Core と Windows PowerShell の間のモジュール/スクリプトの互換性に与える影響の詳細については、[Windows PowerShell との後方互換性](#backwards-compatibility-with-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="82b16-110">For more information on how this affects module/script compatibility between PowerShell Core and Windows PowerShell, see [Backwards compatibility with Windows PowerShell](#backwards-compatibility-with-windows-powershell).</span></span>

## <a name="support-for-macos-and-linux"></a><span data-ttu-id="82b16-111">macOS と Linux のサポート</span><span class="sxs-lookup"><span data-stu-id="82b16-111">Support for macOS and Linux</span></span>

<span data-ttu-id="82b16-112">PowerShell では、次のように、macOS と Linux が正式にサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-112">PowerShell now officially supports macOS and Linux, including:</span></span>

- <span data-ttu-id="82b16-113">Windows 7、8.1、10</span><span class="sxs-lookup"><span data-stu-id="82b16-113">Windows 7, 8.1, and 10</span></span>
- <span data-ttu-id="82b16-114">Windows Server 2008 R2、2012 R2、2016</span><span class="sxs-lookup"><span data-stu-id="82b16-114">Windows Server 2008 R2, 2012 R2, 2016</span></span>
- <span data-ttu-id="82b16-115">[Windows Server 半期チャネル][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="82b16-115">[Windows Server Semi-Annual Channel][semi-annual]</span></span>
- <span data-ttu-id="82b16-116">Ubuntu 14.04、16.04、17.04</span><span class="sxs-lookup"><span data-stu-id="82b16-116">Ubuntu 14.04, 16.04, and 17.04</span></span>
- <span data-ttu-id="82b16-117">Debian 8.7 以降および 9</span><span class="sxs-lookup"><span data-stu-id="82b16-117">Debian 8.7+, and 9</span></span>
- <span data-ttu-id="82b16-118">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="82b16-118">CentOS 7</span></span>
- <span data-ttu-id="82b16-119">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="82b16-119">Red Hat Enterprise Linux 7</span></span>
- <span data-ttu-id="82b16-120">OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="82b16-120">OpenSUSE 42.2</span></span>
- <span data-ttu-id="82b16-121">Fedora 25、26</span><span class="sxs-lookup"><span data-stu-id="82b16-121">Fedora 25, 26</span></span>
- <span data-ttu-id="82b16-122">macOS 10.12 以降</span><span class="sxs-lookup"><span data-stu-id="82b16-122">macOS 10.12+</span></span>

<span data-ttu-id="82b16-123">弊社のコミュニティでは、次のプラットフォーム用のパッケージも提供していますが、正式にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="82b16-123">Our community has also contributed packages for the following platforms, but they are not officially supported:</span></span>

- <span data-ttu-id="82b16-124">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="82b16-124">Arch Linux</span></span>
- <span data-ttu-id="82b16-125">Kali Linux</span><span class="sxs-lookup"><span data-stu-id="82b16-125">Kali Linux</span></span>
- <span data-ttu-id="82b16-126">AppImage (複数の Linux プラットフォームで機能)</span><span class="sxs-lookup"><span data-stu-id="82b16-126">AppImage (works on multiple Linux platforms)</span></span>

<span data-ttu-id="82b16-127">また、次のプラットフォーム用の試験的な (サポートされていない) リリースがあります。</span><span class="sxs-lookup"><span data-stu-id="82b16-127">We also have experimental (unsupported) releases for the following platforms:</span></span>

- <span data-ttu-id="82b16-128">Windows on ARM32/ARM64</span><span class="sxs-lookup"><span data-stu-id="82b16-128">Windows on ARM32/ARM64</span></span>
- <span data-ttu-id="82b16-129">Raspbian (Stretch)</span><span class="sxs-lookup"><span data-stu-id="82b16-129">Raspbian (Stretch)</span></span>

<span data-ttu-id="82b16-130">Windows 以外のシステムでより適切に機能するように、PowerShell Core 6.0 には多くの変更が行われました。</span><span class="sxs-lookup"><span data-stu-id="82b16-130">A number of changes were made to in PowerShell Core 6.0 to make it work better on non-Windows systems.</span></span>
<span data-ttu-id="82b16-131">これらのいくつかは重大な変更であり、Windows にも影響します。</span><span class="sxs-lookup"><span data-stu-id="82b16-131">Some of these are breaking changes, which also affect Windows.</span></span>
<span data-ttu-id="82b16-132">その他の変更は、PowerShell Core の Windows 以外のインストールにのみ存在するか適用されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-132">Others are only present or applicable in non-Windows installations of PowerShell Core.</span></span>

- <span data-ttu-id="82b16-133">Unix プラットフォームでのネイティブ コマンドのグロビング サポートを追加しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-133">Added support for native command globbing on Unix platforms.</span></span>
- <span data-ttu-id="82b16-134">`more` 機能は Linux `$PAGER` に対応し、既定で `less` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-134">The `more` functionality respects the Linux `$PAGER` and defaults to `less`.</span></span>
  <span data-ttu-id="82b16-135">これは、ネイティブ バイナリ/コマンドでワイルドカードを使用できるようになったことを意味します (例: `ls *.txt`)。</span><span class="sxs-lookup"><span data-stu-id="82b16-135">This means you can now use wildcards with native binaries/commands (for example, `ls *.txt`).</span></span> <span data-ttu-id="82b16-136">(#3463)</span><span class="sxs-lookup"><span data-stu-id="82b16-136">(#3463)</span></span>
- <span data-ttu-id="82b16-137">末尾の円記号は、ネイティブ コマンド引数を処理するときに自動的にエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="82b16-137">Trailing backslash is automatically escaped when dealing with native command arguments.</span></span> <span data-ttu-id="82b16-138">(#4965)</span><span class="sxs-lookup"><span data-stu-id="82b16-138">(#4965)</span></span>
- <span data-ttu-id="82b16-139">スクリプト エンジンは現在サポートされていないため、Windows 以外のプラットフォームで PowerShell を実行するときは `-ExecutionPolicy` スイッチを無視します。</span><span class="sxs-lookup"><span data-stu-id="82b16-139">Ignore the `-ExecutionPolicy` switch when running PowerShell on non-Windows platforms because script signing is not currently supported.</span></span> <span data-ttu-id="82b16-140">(#3481)</span><span class="sxs-lookup"><span data-stu-id="82b16-140">(#3481)</span></span>
- <span data-ttu-id="82b16-141">Unix プラットフォームで `NoEcho` を受け入れるために ConsoleHost を修正しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-141">Fixed ConsoleHost to honor `NoEcho` on Unix platforms.</span></span> <span data-ttu-id="82b16-142">(#3801)</span><span class="sxs-lookup"><span data-stu-id="82b16-142">(#3801)</span></span>
- <span data-ttu-id="82b16-143">Unix プラットフォームで大文字と小文字を区別しないパターン マッチングをサポートするために `Get-Help` を修正しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-143">Fixed `Get-Help` to support case insensitive pattern matching on Unix platforms.</span></span> <span data-ttu-id="82b16-144">(#3852)</span><span class="sxs-lookup"><span data-stu-id="82b16-144">(#3852)</span></span>
- <span data-ttu-id="82b16-145">パッケージに `powershell` man ページが追加されました。</span><span class="sxs-lookup"><span data-stu-id="82b16-145">`powershell` man-page added to package</span></span>

### <a name="logging"></a><span data-ttu-id="82b16-146">ログ</span><span class="sxs-lookup"><span data-stu-id="82b16-146">Logging</span></span>

<span data-ttu-id="82b16-147">macOS では、PowerShell はネイティブ `os_log` API を使用して、Apple の[統合ログシステム][os_log]にログを記録します。</span><span class="sxs-lookup"><span data-stu-id="82b16-147">On macOS, PowerShell uses the native `os_log` APIs to log to Apple's [unified logging system][os_log].</span></span>
<span data-ttu-id="82b16-148">Linux では、PowerShell は、ユビキタス ログ ソリューションである [Syslog][] を使用します。</span><span class="sxs-lookup"><span data-stu-id="82b16-148">On Linux, PowerShell uses [Syslog][], a ubiquitous logging solution.</span></span>

### <a name="filesystem"></a><span data-ttu-id="82b16-149">ファイル システム</span><span class="sxs-lookup"><span data-stu-id="82b16-149">Filesystem</span></span>

<span data-ttu-id="82b16-150">従来、Windows ではサポートされていなかったファイル名の文字をサポートするために、macOS と Linux について多くの変更が行われました。</span><span class="sxs-lookup"><span data-stu-id="82b16-150">A number of changes have been made on macOS and Linux to support filename characters not traditionally supported on Windows:</span></span>

- <span data-ttu-id="82b16-151">コマンドレットに指定されるパスがスラッシュに依存しなくなりました (/ と \ の両方がディレクトリの区切り記号として機能)。</span><span class="sxs-lookup"><span data-stu-id="82b16-151">Paths given to cmdlets are now slash-agnostic (both / and \ work as directory separator)</span></span>
- <span data-ttu-id="82b16-152">XDG Base Directory Specification に準拠するようになり、既定では次のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-152">XDG Base Directory Specification is now respected and used by default:</span></span>
  - <span data-ttu-id="82b16-153">Linux/macOS プロファイルのパスは `~/.config/powershell/profile.ps1` にあります。</span><span class="sxs-lookup"><span data-stu-id="82b16-153">The Linux/macOS profile path is located at `~/.config/powershell/profile.ps1`</span></span>
  - <span data-ttu-id="82b16-154">履歴保存パスは `~/.local/share/powershell/PSReadline/ConsoleHost_history.txt` にあります。</span><span class="sxs-lookup"><span data-stu-id="82b16-154">The history save path is located at `~/.local/share/powershell/PSReadline/ConsoleHost_history.txt`</span></span>
  - <span data-ttu-id="82b16-155">ユーザー モジュール パスは `~/.local/share/powershell/Modules` にあります。</span><span class="sxs-lookup"><span data-stu-id="82b16-155">The user module path is located at `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="82b16-156">Unix では、コロン文字を含むファイルとフォルダーの名前がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="82b16-156">Support for file and folder names containing the colon character on Unix.</span></span> <span data-ttu-id="82b16-157">(#4959)</span><span class="sxs-lookup"><span data-stu-id="82b16-157">(#4959)</span></span>
- <span data-ttu-id="82b16-158">コンマを含むスクリプトの名前または完全パスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="82b16-158">Support for script names or full paths that have commas.</span></span> <span data-ttu-id="82b16-159">(#4136) (@TimCurwick に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-159">(#4136) (Thanks to @TimCurwick!)</span></span>
- <span data-ttu-id="82b16-160">ナビゲーション コマンドレットのワイルドカードの展開を抑制するために `-LiteralPath` が使用されるタイミングを検出します。</span><span class="sxs-lookup"><span data-stu-id="82b16-160">Detect when `-LiteralPath` is used to suppress wildcard expansion for navigation cmdlets.</span></span> <span data-ttu-id="82b16-161">(#5038)</span><span class="sxs-lookup"><span data-stu-id="82b16-161">(#5038)</span></span>
- <span data-ttu-id="82b16-162">\*nix `ls -R` や Windows の `DIR /S` ネイティブ コマンドのように動作するよう `Get-ChildItem` を更新しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-162">Updated `Get-ChildItem` to work more like the \*nix `ls -R` and the Windows `DIR /S` native commands.</span></span>
  <span data-ttu-id="82b16-163">`Get-ChildItem` では、再帰的検索時に発生するシンボリック リンクを返し、これらのリンク先のディレクトリは検索しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-163">`Get-ChildItem` now returns the symbolic links encountered during a recursive search and does not search the directories that those links target.</span></span> <span data-ttu-id="82b16-164">(#3780)</span><span class="sxs-lookup"><span data-stu-id="82b16-164">(#3780)</span></span>

### <a name="case-sensitivity"></a><span data-ttu-id="82b16-165">大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="82b16-165">Case sensitivity</span></span>

<span data-ttu-id="82b16-166">Linux と macOS では大文字と小文字を区別する傾向があります。一方、Windows では大文字と小文字は区別されませんが、大文字と小文字は保持されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-166">Linux and macOS tend to be case-sensitive while Windows is case-insensitive while preserving case.</span></span>
<span data-ttu-id="82b16-167">一般に、PowerShell では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="82b16-167">In general, PowerShell is case insensitive.</span></span>

<span data-ttu-id="82b16-168">たとえば、macOS と Linux では環境変数の大文字と小文字が区別されるため、`PSModulePath` 環境変数の大文字と小文字の区別が標準化されています。</span><span class="sxs-lookup"><span data-stu-id="82b16-168">For example, environment variables are case-sensitive on macOS and Linux, so the casing of the `PSModulePath` environment variable has been standardized.</span></span> <span data-ttu-id="82b16-169">(#3255) モジュールの名前を判別するためにファイル パスを使用する場合は、`Import-Module` の大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="82b16-169">(#3255) `Import-Module` is case insensitive when it's using a file path to determine the module's name.</span></span> <span data-ttu-id="82b16-170">(#5097)</span><span class="sxs-lookup"><span data-stu-id="82b16-170">(#5097)</span></span>

## <a name="support-for-side-by-side-installations"></a><span data-ttu-id="82b16-171">サイド バイ サイド インストールのサポート</span><span class="sxs-lookup"><span data-stu-id="82b16-171">Support for side-by-side installations</span></span>

<span data-ttu-id="82b16-172">PowerShell Core は、Windows PowerShell とは別にインストール、構成、実行されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-172">PowerShell Core is installed, configured, and executed separately from Windows PowerShell.</span></span>
<span data-ttu-id="82b16-173">PowerShell Core には "ポータブル" ZIP パッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="82b16-173">PowerShell Core has a "portable" ZIP package.</span></span>
<span data-ttu-id="82b16-174">ZIP パッケージを使用して、PowerShell を依存関係と見なすアプリケーションに対して局所的なものを含む、ディスクの任意の位置に任意の数のバージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="82b16-174">Using the ZIP package, you can install any number of versions anywhere on disk, including local to an application that takes PowerShell as a dependency.</span></span>
<span data-ttu-id="82b16-175">サイド バイ サイド インストールでは、新しいバージョンの PowerShell のテストと既存のスクリプトの段階的な移行がより容易になります。</span><span class="sxs-lookup"><span data-stu-id="82b16-175">Side-by-side installation makes it easier to test new versions of PowerShell and migrating existing scripts over time.</span></span>
<span data-ttu-id="82b16-176">また、サイド バイ サイドでは、スクリプトを必要な特定のバージョンにピン留めできるため、後方互換性が有効になります。</span><span class="sxs-lookup"><span data-stu-id="82b16-176">Side-by-side also enables backwards compatibility as scripts can be pinned to specific versions that they require.</span></span>

> [!NOTE]
> <span data-ttu-id="82b16-177">既定では、Windows 上の MSI ベースのインストーラーはインプレース更新インストールを行います。</span><span class="sxs-lookup"><span data-stu-id="82b16-177">By default, the MSI-based installer on Windows does an in-place update install.</span></span>
>

## <a name="renamed-powershellexe-to-pwshexe"></a><span data-ttu-id="82b16-178">`powershell(.exe)` から `pwsh(.exe)` への名前変更</span><span class="sxs-lookup"><span data-stu-id="82b16-178">Renamed `powershell(.exe)` to `pwsh(.exe)`</span></span>

<span data-ttu-id="82b16-179">PowerShell Core のバイナリ名が `powershell(.exe)` から `pwsh(.exe)` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="82b16-179">The binary name for PowerShell Core has been changed from `powershell(.exe)` to `pwsh(.exe)`.</span></span>
<span data-ttu-id="82b16-180">この変更により、Windows PowerShell と PowerShell Core のサイド バイ サイドのインストールをサポートするために、ユーザーがコンピューター上で PowerShell Core を実行する場合に決定的な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-180">This change provides a deterministic way for users to run PowerShell Core on machines to support side-by-side Windows PowerShell and PowerShell Core installations.</span></span>
<span data-ttu-id="82b16-181">また、`pwsh` は短いため、入力しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="82b16-181">`pwsh` is also much shorter and easier to type.</span></span>

<span data-ttu-id="82b16-182">`powershell.exe` から `pwsh(.exe)` への変更以外の変更点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82b16-182">Additional changes to `pwsh(.exe)` from `powershell.exe`:</span></span>

- <span data-ttu-id="82b16-183">最初の位置指定パラメーターが `-Command` から `-File` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="82b16-183">Changed the first positional parameter from `-Command` to `-File`.</span></span>
  <span data-ttu-id="82b16-184">この変更により、Windows 以外のプラットフォームの PowerShell 以外のシェルから実行されている PowerShell スクリプトの `#!` (シバンともいう) 使用方法が修正されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-184">This change fixes the usage of `#!` (aka as a shebang) in PowerShell scripts that are being executed from non-PowerShell shells on non-Windows platforms.</span></span>
  <span data-ttu-id="82b16-185">これは、`-File` を指定せずに `pwsh foo.ps1` または `pwsh fooScript` のようなコマンドを実行できることも意味します。</span><span class="sxs-lookup"><span data-stu-id="82b16-185">It also means that you can run commands like `pwsh foo.ps1` or `pwsh fooScript` without specifying `-File`.</span></span>
  <span data-ttu-id="82b16-186">ただし、この変更では、`pwsh.exe -Command Get-Command` などのコマンドの実行を試みる場合に `-c` または `-Command` を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b16-186">However, this change requires that you explicitly specify `-c` or `-Command` when trying to run commands like `pwsh.exe -Command Get-Command`.</span></span> <span data-ttu-id="82b16-187">(#4019)</span><span class="sxs-lookup"><span data-stu-id="82b16-187">(#4019)</span></span>
- <span data-ttu-id="82b16-188">PowerShell Core は `-i` (または `-Interactive`) スイッチを受け入れ、対話型シェルを示します。</span><span class="sxs-lookup"><span data-stu-id="82b16-188">PowerShell Core accepts the `-i` (or `-Interactive`) switch to indicate an interactive shell.</span></span> <span data-ttu-id="82b16-189">(# 3558) これにより、Unix プラットフォームで既定のシェルとして PowerShell を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="82b16-189">(#3558) This allows PowerShell to be used as a default shell on Unix platforms.</span></span>
- <span data-ttu-id="82b16-190">パラメーターの `-importsystemmodules` と `-psconsoleFile` を `pwsh.exe` から削除しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-190">Removed parameters `-importsystemmodules` and `-psconsoleFile` from `pwsh.exe`.</span></span> <span data-ttu-id="82b16-191">(#4995)</span><span class="sxs-lookup"><span data-stu-id="82b16-191">(#4995)</span></span>
- <span data-ttu-id="82b16-192">他のネイティブ ツールに合わせて `pwsh -version` と `pwsh.exe` の組み込みヘルプを変更しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-192">Changed `pwsh -version` and built-in help for `pwsh.exe` to align with other native tools.</span></span> <span data-ttu-id="82b16-193">(#4958 & #4931) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-193">(#4958 & #4931) (Thanks @iSazonov)</span></span>
- <span data-ttu-id="82b16-194">`-File` と `-Command` の無効な引数エラー メッセージと終了コードの Unix 標準への準拠 (#4573)</span><span class="sxs-lookup"><span data-stu-id="82b16-194">Invalid argument error messages for `-File` and `-Command` and exit codes consistent with Unix standards (#4573)</span></span>
- <span data-ttu-id="82b16-195">Windows の `-WindowStyle` パラメーターを追加しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-195">Added `-WindowStyle` parameter on Windows.</span></span> <span data-ttu-id="82b16-196">(#4573) 同様に、Windows 以外のプラットフォームのパッケージ ベースのインストール更新はインプレース更新となります。</span><span class="sxs-lookup"><span data-stu-id="82b16-196">(#4573) Similarly, package-based installations updates on non-Windows platforms are in-place updates.</span></span>

## <a name="backwards-compatibility-with-windows-powershell"></a><span data-ttu-id="82b16-197">Windows PowerShell との後方互換性</span><span class="sxs-lookup"><span data-stu-id="82b16-197">Backwards compatibility with Windows PowerShell</span></span>

<span data-ttu-id="82b16-198">PowerShell Core の目的は、Windows PowerShell との互換性をできる限り維持することです。</span><span class="sxs-lookup"><span data-stu-id="82b16-198">The goal of PowerShell Core is to remain as compatible as possible with Windows PowerShell.</span></span>
<span data-ttu-id="82b16-199">PowerShell Core では [.NET Standard][] 2.0 を使用して、既存の .NET アセンブリとのバイナリの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="82b16-199">PowerShell Core uses [.NET Standard][] 2.0 to provide binary compatibility with existing .NET assemblies.</span></span>
<span data-ttu-id="82b16-200">多くの PowerShell モジュールはこれらのアセンブリ (多くの場合、Dll) に依存するため、.NET Standard では .NET Core を引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="82b16-200">Many PowerShell modules depend on these assemblies (often times DLLs), so .NET Standard allows them to continue working with .NET Core.</span></span>
<span data-ttu-id="82b16-201">PowerShell Core には、.NET Framework DLL の依存関係を検索するための既知のフォルダー (通常、ディスク上のグローバル アセンブリ キャッシュが存在する場所など) を調べるヒューリスティックも含まれます。</span><span class="sxs-lookup"><span data-stu-id="82b16-201">PowerShell Core also includes a heuristic to look in well-known folders--like where the Global Assembly Cache typically resides on disk--to find .NET Framework DLL dependencies.</span></span>

<span data-ttu-id="82b16-202">.NET Standard の詳細については、[.NET ブログ][]、この [YouTube][] ビデオ、および GitHub のこの [FAQ][] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b16-202">You can learn more about .NET Standard on the [.NET Blog][], in this [YouTube][] video, and via this [FAQ][] on GitHub.</span></span>

<span data-ttu-id="82b16-203">PowerShell 言語と "組み込み" モジュール (`Microsoft.PowerShell.Management`、`Microsoft.PowerShell.Utility` など) が Windows PowerShell の場合と同じように機能するように最善を尽くしました。</span><span class="sxs-lookup"><span data-stu-id="82b16-203">Best efforts have been made to ensure that the PowerShell language and "built-in" modules (like `Microsoft.PowerShell.Management`, `Microsoft.PowerShell.Utility`, etc.) work the same as they do in Windows PowerShell.</span></span>
<span data-ttu-id="82b16-204">多くの場合、コミュニティを利用して、これらのコマンドレットに新しい機能とバグの修正が追加されています。</span><span class="sxs-lookup"><span data-stu-id="82b16-204">In many cases, with the help of the community, we've added new capabilities and bug fixes to those cmdlets.</span></span>
<span data-ttu-id="82b16-205">場合によっては、基になる .NET レイヤーとの依存関係がないため、機能が削除されているか、使用できなくなっています。</span><span class="sxs-lookup"><span data-stu-id="82b16-205">In some cases, due to a missing dependency in underlying .NET layers, functionality was removed or is unavailable.</span></span>

<span data-ttu-id="82b16-206">Windows の一部として出荷されるモジュールのほとんど (`DnsClient`、`Hyper-V`、`NetTCPIP`、`Storage` など) と、Azure と Office を含むその他の Microsoft 製品はまだ .NET Core には*明示的に*移植されていません。</span><span class="sxs-lookup"><span data-stu-id="82b16-206">Most of the modules that ship as part of Windows (for example, `DnsClient`, `Hyper-V`, `NetTCPIP`, `Storage`, etc.) and other Microsoft products including Azure and Office have not been *explicitly* ported to .NET Core yet.</span></span>
<span data-ttu-id="82b16-207">PowerShell チームはこれらの製品グループとチームと協力して既存のモジュールを検証し、PowerShell Core に移植しています。</span><span class="sxs-lookup"><span data-stu-id="82b16-207">The PowerShell team is working with these product groups and teams to validate and port their existing modules to PowerShell Core.</span></span>
<span data-ttu-id="82b16-208">.NET Standard と [CDXML][] を使用すると、これらの従来の Windows PowerShell モジュールの多くが PowerShell Core で機能するようですが、正式には検証されておらず、また、正式にサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="82b16-208">With .NET Standard and [CDXML][], many of these traditional Windows PowerShell modules do seem to work in PowerShell Core, but they have not been formally validated, and they are not formally supported.</span></span>

<span data-ttu-id="82b16-209">[`WindowsPSModulePath`][windowspsmodulepath] モジュールをインストールして、Windows PowerShell `PSModulePath` をご利用の PowerShell Core `PSModulePath` に追加することで、Windows PowerShell モジュールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82b16-209">By installing the [`WindowsPSModulePath`][windowspsmodulepath] module, you can use Windows PowerShell modules by appending the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="82b16-210">最初に、PowerShell ギャラリーから `WindowsPSModulePath` モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="82b16-210">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="82b16-211">このモジュールをインストールしたら、次のように `Add-WindowsPSModulePath` コマンドレットを実行して、Windows PowerShell `PSModulePath` を PowerShell Core に追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-211">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="docker-support"></a><span data-ttu-id="82b16-212">Docker サポート</span><span class="sxs-lookup"><span data-stu-id="82b16-212">Docker support</span></span>

<span data-ttu-id="82b16-213">PowerShell Core には、弊社がサポートする主なすべてのプラットフォーム (複数の Linux ディストリビューション、Windows Server Core、Nano Server を含む) 用の Docker コンテナーのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="82b16-213">PowerShell Core adds support for Docker containers for all the major platforms we support (including multiple Linux distros, Windows Server Core, and Nano Server).</span></span>

<span data-ttu-id="82b16-214">完全なリストについては、[Docker Hub の `microsoft/powershell`][docker-hub] のタグを確認してください。</span><span class="sxs-lookup"><span data-stu-id="82b16-214">For a complete list, check out the tags on [`microsoft/powershell` on Docker Hub][docker-hub].</span></span>
<span data-ttu-id="82b16-215">Docker と PowerShell Core の詳細については、GitHub の「[Docker][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b16-215">For more information on Docker and PowerShell Core, see [Docker][] on GitHub.</span></span>

## <a name="ssh-based-powershell-remoting"></a><span data-ttu-id="82b16-216">SSH ベースの PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="82b16-216">SSH-based PowerShell Remoting</span></span>

<span data-ttu-id="82b16-217">PowerShell リモート処理プロトコル (PSRP) が、従来の WinRM ベースの PSRP に加えて、SSH (Secure Shell) プロトコルでも機能するようになりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-217">The PowerShell Remoting Protocol (PSRP) now works with the Secure Shell (SSH) protocol in addition to the traditional WinRM-based PSRP.</span></span>

<span data-ttu-id="82b16-218">これは、`Enter-PSSession` や `New-PSSession` などのコマンドレットを使用し、SSH を使用して認証できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="82b16-218">This means that you can use cmdlets like `Enter-PSSession` and `New-PSSession` and authenticate using SSH.</span></span>
<span data-ttu-id="82b16-219">OpenSSH ベースの SSH サーバーにサブシステムとして PowerShell を登録するだけで、従来の `PSSession` セマンティクスで既存の SSH ベースの認証メカニズム (パスワードや秘密キーなど) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="82b16-219">All you have to do is register PowerShell as a subsystem with an OpenSSH-based SSH server, and you can use your existing SSH-based authenticate mechanisms (like passwords or private keys) with the traditional `PSSession` semantics.</span></span>

<span data-ttu-id="82b16-220">SSH ベースのリモート処理の構成と使用の詳細については、「[SSH 経由の PowerShell リモート処理][ssh-remoting]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b16-220">For more information on configuring and using SSH-based remoting, see [PowerShell Remoting over SSH][ssh-remoting].</span></span>

## <a name="default-encoding-is-utf-8-without-a-bom-except-for-new-modulemanifest"></a><span data-ttu-id="82b16-221">New-ModuleManifest を除き、既定のエンコードは BOM なしの UTF-8 です</span><span class="sxs-lookup"><span data-stu-id="82b16-221">Default encoding is UTF-8 without a BOM except for New-ModuleManifest</span></span>

<span data-ttu-id="82b16-222">これまでは、`Get-Content`、`Set-Content` のような Windows PowerShell コマンドレットでは、ASCII や UTF-16 などの異なるエンコードを使用していました。</span><span class="sxs-lookup"><span data-stu-id="82b16-222">In the past, Windows PowerShell cmdlets like `Get-Content`, `Set-Content` used different encodings, such as ASCII and UTF-16.</span></span>
<span data-ttu-id="82b16-223">エンコードを指定せずにコマンドレットを混在させると、エンコード既定値の変数により問題が生じていました。</span><span class="sxs-lookup"><span data-stu-id="82b16-223">The variance in encoding defaults created problems when mixing cmdlets without specifying an encoding.</span></span>

<span data-ttu-id="82b16-224">従来、Windows 以外のプラットフォームでは、テキスト ファイルの既定のエンコードとして BOM (バイト オーダー マーク) なしで UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="82b16-224">Non-Windows platforms traditionally use UTF-8 without a Byte Order Mark (BOM) as the default encoding for text files.</span></span>
<span data-ttu-id="82b16-225">より多くの Windows アプリケーションとツールが UTF-16 から BOM なしの UTF-8 エンコードに移行しつつあります。</span><span class="sxs-lookup"><span data-stu-id="82b16-225">More Windows applications and tools are moving away from UTF-16 and towards BOM-less UTF-8 encoding.</span></span>
<span data-ttu-id="82b16-226">PowerShell Core では、より広範囲のエコシステムに準拠するために既定のエンコードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="82b16-226">PowerShell Core changes the default encoding to conform with the broader ecosystems.</span></span>

<span data-ttu-id="82b16-227">つまり、`-Encoding` パラメーターを使用するすべての組み込みコマンドレットでは、既定で `UTF8NoBOM` 値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-227">This means that all built-in cmdlets that use the `-Encoding` parameter use the `UTF8NoBOM` value by default.</span></span>
<span data-ttu-id="82b16-228">以下のコマンドレットがこの変更の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="82b16-228">The following cmdlets are affected by this change:</span></span>

- <span data-ttu-id="82b16-229">Add-Content</span><span class="sxs-lookup"><span data-stu-id="82b16-229">Add-Content</span></span>
- <span data-ttu-id="82b16-230">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="82b16-230">Export-Clixml</span></span>
- <span data-ttu-id="82b16-231">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="82b16-231">Export-Csv</span></span>
- <span data-ttu-id="82b16-232">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="82b16-232">Export-PSSession</span></span>
- <span data-ttu-id="82b16-233">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="82b16-233">Format-Hex</span></span>
- <span data-ttu-id="82b16-234">Get-Content</span><span class="sxs-lookup"><span data-stu-id="82b16-234">Get-Content</span></span>
- <span data-ttu-id="82b16-235">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="82b16-235">Import-Csv</span></span>
- <span data-ttu-id="82b16-236">Out-File</span><span class="sxs-lookup"><span data-stu-id="82b16-236">Out-File</span></span>
- <span data-ttu-id="82b16-237">Select-String</span><span class="sxs-lookup"><span data-stu-id="82b16-237">Select-String</span></span>
- <span data-ttu-id="82b16-238">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="82b16-238">Send-MailMessage</span></span>
- <span data-ttu-id="82b16-239">Set-Content</span><span class="sxs-lookup"><span data-stu-id="82b16-239">Set-Content</span></span>

<span data-ttu-id="82b16-240">これらのコマンドレットも更新され、`-Encoding` パラメーターで `System.Text.Encoding` が一般に受け入れられるようになりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-240">These cmdlets have also been updated so that the `-Encoding` parameter universally accepts `System.Text.Encoding`.</span></span>

<span data-ttu-id="82b16-241">`$OutputEncoding` の既定値も UTF-8 に変更されました。</span><span class="sxs-lookup"><span data-stu-id="82b16-241">The default value of `$OutputEncoding` has also been changed to UTF-8.</span></span>

<span data-ttu-id="82b16-242">ベスト プラクティスとして、`-Encoding` パラメーターを使用してスクリプトに明示的にエンコードを設定し、プラットフォーム間の動作が決定的なものになるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b16-242">As a best practice, you should explicitly set encodings in scripts using the `-Encoding` parameter to produce deterministic behavior across platforms.</span></span>

<span data-ttu-id="82b16-243">`New-ModuleManifest` コマンドレットには **Encoding** パラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="82b16-243">`New-ModuleManifest` cmdlet does not have **Encoding** parameter.</span></span> <span data-ttu-id="82b16-244">`New-ModuleManifest` コマンドレットで作成されたモジュール マニフェスト (.psd1) ファイルのエンコーディングは、環境によって異なります。Linux で動作する PowerShell Core の場合、エンコーディングは UTF-8 (BOM なし) です。それ以外の場合、エンコーディングは UTF-16 (BOM あり) です。</span><span class="sxs-lookup"><span data-stu-id="82b16-244">The encoding of the module manifest (.psd1) file created with `New-ModuleManifest` cmdlet depends on environment: if it is PowerShell Core running on Linux then encoding is UTF-8 (no BOM); otherwise encoding is UTF-16 (with BOM).</span></span> <span data-ttu-id="82b16-245">(#3940)</span><span class="sxs-lookup"><span data-stu-id="82b16-245">(#3940)</span></span>

## <a name="support-backgrounding-of-pipelines-with-ampersand--3360"></a><span data-ttu-id="82b16-246">アンパサンド (`&`) を使用するパイプラインのバックグラウンドでの実行サポート (#3360)</span><span class="sxs-lookup"><span data-stu-id="82b16-246">Support backgrounding of pipelines with ampersand (`&`) (#3360)</span></span>

<span data-ttu-id="82b16-247">パイプラインの最後に `&` を配置すると、パイプラインが PowerShell ジョブとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-247">Putting `&` at the end of a pipeline causes the pipeline to be run as a PowerShell job.</span></span>
<span data-ttu-id="82b16-248">パイプラインをバックグラウンドで実行すると、ジョブ オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-248">When a pipeline is backgrounded, a job object is returned.</span></span>
<span data-ttu-id="82b16-249">パイプラインがジョブとして実行されている場合は、標準の `*-Job` コマンドレットをすべてジョブの管理のために使用できます。</span><span class="sxs-lookup"><span data-stu-id="82b16-249">Once the pipeline is running as a job, all of the standard `*-Job` cmdlets can be used to manage the job.</span></span>
<span data-ttu-id="82b16-250">パイプラインで使用される変数 (プロセス固有の変数は無視) は、`Copy-Item $foo $bar &` のみが機能するようにジョブに自動的にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="82b16-250">Variables (ignoring process-specific variables) used in the pipeline are automatically copied to the job so `Copy-Item $foo $bar &` just works.</span></span>
<span data-ttu-id="82b16-251">また、ジョブは、ユーザーのホーム ディレクトリではなく、現在のディレクトリで実行されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-251">The job is also run in the current directory instead of the user's home directory.</span></span>
<span data-ttu-id="82b16-252">PowerShell ジョブの詳細については、「[about_Jobs](https://msdn.microsoft.com/powershell/reference/6/about/about_jobs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b16-252">For more information about PowerShell jobs, see [about_Jobs](https://msdn.microsoft.com/powershell/reference/6/about/about_jobs).</span></span>

## <a name="semantic-versioning"></a><span data-ttu-id="82b16-253">セマンティック バージョニング</span><span class="sxs-lookup"><span data-stu-id="82b16-253">Semantic versioning</span></span>

- <span data-ttu-id="82b16-254">`SemanticVersion` に `SemVer 2.0` との互換性を持たせました。</span><span class="sxs-lookup"><span data-stu-id="82b16-254">Made `SemanticVersion` compatible with `SemVer 2.0`.</span></span> <span data-ttu-id="82b16-255">(#5037) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-255">(#5037) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="82b16-256">SemVer に合わせて `New-ModuleManifest` の既定の `ModuleVersion` を `0.0.1` に変更しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-256">Changed default `ModuleVersion` in `New-ModuleManifest` to `0.0.1` to align with SemVer.</span></span> <span data-ttu-id="82b16-257">(#4842) (@LDSpits に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-257">(#4842) (Thanks @LDSpits)</span></span>
- <span data-ttu-id="82b16-258">`System.Management.Automation.SemanticVersion` の型のアクセラレータとして `semver` を追加しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-258">Added `semver` as a type accelerator for `System.Management.Automation.SemanticVersion`.</span></span> <span data-ttu-id="82b16-259">(#4142) (@oising に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-259">(#4142) (Thanks to @oising!)</span></span>
- <span data-ttu-id="82b16-260">`SemanticVersion` インスタンスと、`Major` と `Minor` のバージョン値のみで構築される `Version` インスタンスを比較できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-260">Enabled comparison between a `SemanticVersion` instance and a `Version` instance that is constructed only with `Major` and `Minor` version values.</span></span>

## <a name="language-updates"></a><span data-ttu-id="82b16-261">言語の更新</span><span class="sxs-lookup"><span data-stu-id="82b16-261">Language updates</span></span>

- <span data-ttu-id="82b16-262">ユーザーが Unicode 文字を引数、文字列、または変数名として使用できるように、Unicode エスケープ解析を実装します。</span><span class="sxs-lookup"><span data-stu-id="82b16-262">Implement Unicode escape parsing so that users can use Unicode characters as arguments, strings, or variable names.</span></span> <span data-ttu-id="82b16-263">(#3958) (@rkeithhill に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-263">(#3958) (Thanks to @rkeithhill!)</span></span>
- <span data-ttu-id="82b16-264">ESC の新しいエスケープ文字 (`` `e``) を追加しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-264">Added new escape character for ESC: `` `e``</span></span>
- <span data-ttu-id="82b16-265">列挙型を文字列に変換するサポートを追加しました。(#4318) (@KirkMunro に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-265">Added support for converting enums to string (#4318) (Thanks @KirkMunro)</span></span>
- <span data-ttu-id="82b16-266">ジェネリック コレクションへの単一の要素配列のキャストを修正しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-266">Fixed casting single element array to a generic collection.</span></span> <span data-ttu-id="82b16-267">(#3170)</span><span class="sxs-lookup"><span data-stu-id="82b16-267">(#3170)</span></span>
- <span data-ttu-id="82b16-268">`'a'..'z'` が 'a' から 'z' までの文字を返すように、`..` 演算子に文字範囲のオーバーロードを追加しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-268">Added character range overload to the `..` operator, so `'a'..'z'` returns characters from 'a' to 'z'.</span></span> <span data-ttu-id="82b16-269">(#5026) (@IISResetMe に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-269">(#5026) (Thanks @IISResetMe!)</span></span>
- <span data-ttu-id="82b16-270">読み取り専用の変数を上書きしないように変数代入を修正しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-270">Fixed variable assignment to not overwrite read-only variables</span></span>
- <span data-ttu-id="82b16-271">スクリプト コマンドレットをドットで表す場合に、'DottedScopes' に自動変数のローカルをプッシュします。(#4709)</span><span class="sxs-lookup"><span data-stu-id="82b16-271">Push locals of automatic variables to 'DottedScopes' when dotting script cmdlets (#4709)</span></span>
- <span data-ttu-id="82b16-272">分割演算子で 'Singleline, Multiline' オプションを使用できるようにします。(#4721) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-272">Enable use of 'Singleline, Multiline' option in split operator (#4721) (Thanks @iSazonov)</span></span>

## <a name="engine-updates"></a><span data-ttu-id="82b16-273">エンジンの更新</span><span class="sxs-lookup"><span data-stu-id="82b16-273">Engine updates</span></span>

- <span data-ttu-id="82b16-274">`$PSVersionTable` には、次の 4 つの新しいプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="82b16-274">`$PSVersionTable` has four new properties:</span></span>
  - <span data-ttu-id="82b16-275">`PSEdition`: これは、PowerShell Core では `Core` に、Windows PowerShell では `Desktop` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-275">`PSEdition`: This is set to `Core` on PowerShell Core and `Desktop` on Windows PowerShell</span></span>
  - <span data-ttu-id="82b16-276">`GitCommitId`: これは、PowerShell が構築された Git ブランチまたはタグの Git コミット ID です。</span><span class="sxs-lookup"><span data-stu-id="82b16-276">`GitCommitId`: This is the Git commit ID of the Git branch or tag where PowerShell was built.</span></span>
    <span data-ttu-id="82b16-277">リリースされたビルドでは、`PSVersion` と同じになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82b16-277">On released builds, it will likely be the same as `PSVersion`.</span></span>
  - <span data-ttu-id="82b16-278">`OS`: これは、`[System.Runtime.InteropServices.RuntimeInformation]::OSDescription` によって返される OS バージョンの文字列です。</span><span class="sxs-lookup"><span data-stu-id="82b16-278">`OS`: This is an OS version string returned by `[System.Runtime.InteropServices.RuntimeInformation]::OSDescription`</span></span>
  - <span data-ttu-id="82b16-279">`Platform`: これは `[System.Environment]::OSVersion.Platform` によって返されます。Windows では `Win32NT` に、macOs では `Unix` に、Linux では `Unix` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-279">`Platform`: This is returned by `[System.Environment]::OSVersion.Platform` It is set to `Win32NT` on Windows, `Unix` on macOS, and `Unix` on Linux.</span></span>
- <span data-ttu-id="82b16-280">`$PSVersionTable` から `BuildVersion` プロパティを削除しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-280">Removed the `BuildVersion` property from `$PSVersionTable`.</span></span>
  <span data-ttu-id="82b16-281">このプロパティは、Windows のビルド バージョンに強く関連付けられていました。</span><span class="sxs-lookup"><span data-stu-id="82b16-281">This property was strongly tied to the Windows build version.</span></span>
  <span data-ttu-id="82b16-282">代わりに、`GitCommitId` を使用して、PowerShell Core の正確なビルド バージョンを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82b16-282">Instead, we recommend that you use `GitCommitId` to retrieve the exact build version of PowerShell Core.</span></span> <span data-ttu-id="82b16-283">(#3877) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-283">(#3877) (Thanks to @iSazonov!)</span></span>
- <span data-ttu-id="82b16-284">`$PSVersionTable` から `ClrVersion` プロパティを削除しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-284">Remove `ClrVersion` property from `$PSVersionTable`.</span></span>
  <span data-ttu-id="82b16-285">このプロパティは .NET Core には適しておらず、PowerShell に適用できない特定のレガシー用にのみ .NET Core で保持されました。</span><span class="sxs-lookup"><span data-stu-id="82b16-285">This property is irrelevant for .NET Core, and was only preserved in .NET Core for specific legacy purposes that are inapplicable to PowerShell.</span></span>
- <span data-ttu-id="82b16-286">PowerShell が特定の OS で実行されているかどうかを判断するために、新しく 3 つの自動変数 (`$IsWindows`、`$IsMacOs`、`$IsLinux`) を追加しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-286">Added three new automatic variables to determine whether PowerShell is running in a given OS: `$IsWindows`, `$IsMacOs`, and `$IsLinux`.</span></span>
- <span data-ttu-id="82b16-287">PowerShell Core のバナーに `GitCommitId` を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-287">Add `GitCommitId` to PowerShell Core banner.</span></span>
  <span data-ttu-id="82b16-288">バージョンを取得するために PowerShell を起動してすぐに `$PSVersionTable` を実行する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-288">Now you don't have to run `$PSVersionTable` as soon as you start PowerShell to get the version!</span></span> <span data-ttu-id="82b16-289">(#3916) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-289">(#3916) (Thanks to @iSazonov!)</span></span>
- <span data-ttu-id="82b16-290">起動時刻の前に必要ないくつかの設定を格納するために、`$PSHome` の `powershell.config.json` という JSON 構成ファイルを追加します (`ExecutionPolicy` など)。</span><span class="sxs-lookup"><span data-stu-id="82b16-290">Add a JSON config file called `powershell.config.json` in `$PSHome` to store some settings required before startup time (e.g. `ExecutionPolicy`).</span></span>
- <span data-ttu-id="82b16-291">Windows EXE の実行中はパイプラインをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="82b16-291">Don't block pipeline when running Windows EXE's</span></span>
- <span data-ttu-id="82b16-292">COM コレクションの列挙が有効になりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-292">Enabled enumeration of COM collections.</span></span> <span data-ttu-id="82b16-293">(#4553)</span><span class="sxs-lookup"><span data-stu-id="82b16-293">(#4553)</span></span>

## <a name="cmdlet-updates"></a><span data-ttu-id="82b16-294">コマンドレットの更新</span><span class="sxs-lookup"><span data-stu-id="82b16-294">Cmdlet updates</span></span>

### <a name="new-cmdlets"></a><span data-ttu-id="82b16-295">新しいコマンドレット</span><span class="sxs-lookup"><span data-stu-id="82b16-295">New cmdlets</span></span>

- <span data-ttu-id="82b16-296">`Get-Uptime` を `Microsoft.PowerShell.Utility` に追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-296">Add `Get-Uptime` to `Microsoft.PowerShell.Utility`.</span></span>
- <span data-ttu-id="82b16-297">`Remove-Alias` コマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-297">Add `Remove-Alias` Command.</span></span> <span data-ttu-id="82b16-298">(#5143) (@PowershellNinja に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-298">(#5143) (Thanks @PowershellNinja!)</span></span>
- <span data-ttu-id="82b16-299">`Remove-Service` を管理モジュールに追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-299">Add `Remove-Service` to Management module.</span></span> <span data-ttu-id="82b16-300">(#4858) (@joandrsn に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-300">(#4858) (Thanks @joandrsn!)</span></span>

### <a name="web-cmdlets"></a><span data-ttu-id="82b16-301">Web コマンドレット</span><span class="sxs-lookup"><span data-stu-id="82b16-301">Web cmdlets</span></span>

- <span data-ttu-id="82b16-302">Web コマンドレットの証明書認証サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-302">Add certificate authentication support for web cmdlets.</span></span> <span data-ttu-id="82b16-303">(#4646) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-303">(#4646) (Thanks @markekraus)</span></span>
- <span data-ttu-id="82b16-304">Web コマンドレットにコンテンツ ヘッダーのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-304">Add support for content headers to web cmdlets.</span></span> <span data-ttu-id="82b16-305">(#4494 と #4640) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-305">(#4494 & #4640) (Thanks @markekraus)</span></span>
- <span data-ttu-id="82b16-306">Web コマンドレットに複数のリンク ヘッダー サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-306">Add multiple link header support to Web Cmdlets.</span></span> <span data-ttu-id="82b16-307">(#5265) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-307">(#5265) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="82b16-308">Web コマンドレットでの Link ヘッダーの改ページのサポート (#3828)</span><span class="sxs-lookup"><span data-stu-id="82b16-308">Support Link header pagination in web cmdlets (#3828)</span></span>
  - <span data-ttu-id="82b16-309">`Invoke-WebRequest` では、応答にリンク ヘッダーが含まれている場合、URL と `rel` 属性を表す Dictionary として RelationLink プロパティを作成し、開発者が使いやすいように URL を絶対 URL にします。</span><span class="sxs-lookup"><span data-stu-id="82b16-309">For `Invoke-WebRequest`, when the response includes a Link header we create a RelationLink property as a Dictionary representing the URLs and `rel` attributes and ensure the URLs are absolute to make it easier for the developer to use.</span></span>
  - <span data-ttu-id="82b16-310">`Invoke-RestMethod` では、応答に Link ヘッダーが含まれている場合、`-FollowRelLink` スイッチを公開し、存在しなくなるか、省略可能な `-MaximumFollowRelLink` パラメーター値にヒットするまで、`next` `rel` リンクに自動的に従うようにします。</span><span class="sxs-lookup"><span data-stu-id="82b16-310">For `Invoke-RestMethod`, when the response includes a Link header we expose a `-FollowRelLink` switch to automatically follow `next` `rel` links until they no longer exist or once we hit the optional `-MaximumFollowRelLink` parameter value.</span></span>
- <span data-ttu-id="82b16-311">標準以外のメソッドの動詞で使用できるように、Web コマンドレットに `-CustomMethod` パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-311">Add `-CustomMethod` parameter to web cmdlets to allow for non-standard method verbs.</span></span> <span data-ttu-id="82b16-312">(#3142) (@Lee303 に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-312">(#3142) (Thanks to @Lee303!)</span></span>
- <span data-ttu-id="82b16-313">Web コマンドレットに `SslProtocol` サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-313">Add `SslProtocol` support to Web Cmdlets.</span></span> <span data-ttu-id="82b16-314">(#5329) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-314">(#5329) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="82b16-315">Web コマンドレットにマルチパートのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-315">Add Multipart support to web cmdlets.</span></span> <span data-ttu-id="82b16-316">(#4782) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-316">(#4782) (Thanks @markekraus)</span></span>
- <span data-ttu-id="82b16-317">システム全体のプロキシ設定が無視されるように、Web コマンドレットに `-NoProxy` を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-317">Add `-NoProxy` to web cmdlets so that they ignore the system-wide proxy setting.</span></span> <span data-ttu-id="82b16-318">(#3447) (@TheFlyingCorpse に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-318">(#3447) (Thanks to @TheFlyingCorpse!)</span></span>
- <span data-ttu-id="82b16-319">Web コマンドレットのユーザー エージェントで OS プラットフォームがレポートされるようになりました。(#4937) (@LDSpits に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-319">User Agent of Web Cmdlets now reports the OS platform (#4937) (Thanks @LDSpits)</span></span>
- <span data-ttu-id="82b16-320">ヘッダー値を検証せずにヘッダーを追加できるように、Web コマンドレットに `-SkipHeaderValidation` スイッチを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-320">Add `-SkipHeaderValidation` switch to web cmdlets to support adding headers without validating the header value.</span></span> <span data-ttu-id="82b16-321">(#4085)</span><span class="sxs-lookup"><span data-stu-id="82b16-321">(#4085)</span></span>
- <span data-ttu-id="82b16-322">必要に応じて、Web コマンドレットでサーバーの HTTPS 証明書を検証しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="82b16-322">Enable web cmdlets to not validate the HTTPS certificate of the server if required.</span></span>
- <span data-ttu-id="82b16-323">Web コマンドレットに認証パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-323">Add authentication parameters to web cmdlets.</span></span> <span data-ttu-id="82b16-324">(#5052) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-324">(#5052) (Thanks @markekraus)</span></span>
  - <span data-ttu-id="82b16-325">3 つのオプション (Basic、OAuth、Bearer) を提供する `-Authentication` を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-325">Add `-Authentication` that provides three options: Basic, OAuth, and Bearer.</span></span>
  - <span data-ttu-id="82b16-326">OAuth および Bearer オプションのベアラー トークンを取得するために、`-Token` を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-326">Add `-Token` to get the bearer token for OAuth and Bearer options.</span></span>
  - <span data-ttu-id="82b16-327">HTTPS ではなく、任意のトランスポート スキームに対して指定される認証をバイパスするために、`-AllowUnencryptedAuthentication` を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-327">Add `-AllowUnencryptedAuthentication` to bypass authentication that is provided for any transport scheme other than HTTPS.</span></span>
- <span data-ttu-id="82b16-328">応答ヘッダーのキャプチャを有効にするために、`Invoke-RestMethod` に `-ResponseHeadersVariable` を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-328">Add `-ResponseHeadersVariable` to `Invoke-RestMethod` to enable the capture of response headers.</span></span> <span data-ttu-id="82b16-329">(#4888) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-329">(#4888) (Thanks @markekraus)</span></span>
- <span data-ttu-id="82b16-330">応答ステータス コードが成功でない場合は例外に HTTP 応答を含めるように、Web コマンドレットを修正します。</span><span class="sxs-lookup"><span data-stu-id="82b16-330">Fix web cmdlets to include the HTTP response in the exception when the response status code is not success.</span></span> <span data-ttu-id="82b16-331">(#3201)</span><span class="sxs-lookup"><span data-stu-id="82b16-331">(#3201)</span></span>
- <span data-ttu-id="82b16-332">Web コマンドレット `UserAgent` を `WindowsPowerShell` から `PowerShell` に変更します。</span><span class="sxs-lookup"><span data-stu-id="82b16-332">Change web cmdlets `UserAgent` from `WindowsPowerShell` to `PowerShell`.</span></span> <span data-ttu-id="82b16-333">(#4914) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-333">(#4914) (Thanks @markekraus)</span></span>
- <span data-ttu-id="82b16-334">明示的な `ContentType` 検出を `Invoke-RestMethod` に追加します。(#4692)</span><span class="sxs-lookup"><span data-stu-id="82b16-334">Add explicit `ContentType` detection to `Invoke-RestMethod` (#4692)</span></span>
- <span data-ttu-id="82b16-335">標準以外の User-Agent ヘッダーを操作するために、Web コマンドレット `-SkipHeaderValidation` を修正します。</span><span class="sxs-lookup"><span data-stu-id="82b16-335">Fix web cmdlets `-SkipHeaderValidation` to work with non-standard User-Agent headers.</span></span> <span data-ttu-id="82b16-336">(#4479 および #4512) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-336">(#4479 & #4512) (Thanks @markekraus)</span></span>

### <a name="json-cmdlets"></a><span data-ttu-id="82b16-337">JSON コマンドレット</span><span class="sxs-lookup"><span data-stu-id="82b16-337">JSON cmdlets</span></span>

- <span data-ttu-id="82b16-338">代わりに `Hashtable` を返すように `ConvertFrom-Json` に `-AsHashtable` を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-338">Add `-AsHashtable` to `ConvertFrom-Json` to return a `Hashtable` instead.</span></span> <span data-ttu-id="82b16-339">(#5043) (@bergmeister に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-339">(#5043) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="82b16-340">`ConvertTo-Json` 出力でよりわかりやすいフォーマッタを使用します。</span><span class="sxs-lookup"><span data-stu-id="82b16-340">Use prettier formatter with `ConvertTo-Json` output.</span></span> <span data-ttu-id="82b16-341">(#2787) (@kittholland に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-341">(#2787) (Thanks to @kittholland!)</span></span>
- <span data-ttu-id="82b16-342">`ConvertTo-Json` に `Jobject` のシリアル化サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-342">Add `Jobject` serialization support to `ConvertTo-Json`.</span></span> <span data-ttu-id="82b16-343">(#5141)</span><span class="sxs-lookup"><span data-stu-id="82b16-343">(#5141)</span></span>
- <span data-ttu-id="82b16-344">完全な JSON 文字列を一緒に構築する、パイプラインからの文字列配列の逆シリアル化を行うために `ConvertFrom-Json` を修正します。</span><span class="sxs-lookup"><span data-stu-id="82b16-344">Fix `ConvertFrom-Json` to deserialize an array of strings from the pipeline that together construct a complete JSON string.</span></span>
  <span data-ttu-id="82b16-345">この修正により、改行で JSON 解析が中断される場合があります。</span><span class="sxs-lookup"><span data-stu-id="82b16-345">This fixes some cases where newlines would break JSON parsing.</span></span> <span data-ttu-id="82b16-346">(#3823)</span><span class="sxs-lookup"><span data-stu-id="82b16-346">(#3823)</span></span>
- <span data-ttu-id="82b16-347">`System.Array` に定義されている `AliasProperty "Count"` を削除します。</span><span class="sxs-lookup"><span data-stu-id="82b16-347">Remove the `AliasProperty "Count"` defined for `System.Array`.</span></span>
  <span data-ttu-id="82b16-348">これにより、一部の `Count` 出力の無関係な `ConvertFrom-Json` プロパティが削除されます。</span><span class="sxs-lookup"><span data-stu-id="82b16-348">This removes the extraneous `Count` property on some `ConvertFrom-Json` output.</span></span> <span data-ttu-id="82b16-349">(#3231) (@PetSerAl に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-349">(#3231) (Thanks to @PetSerAl!)</span></span>

### <a name="csv-cmdlets"></a><span data-ttu-id="82b16-350">CSV のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="82b16-350">CSV cmdlets</span></span>

- <span data-ttu-id="82b16-351">`Import-Csv` と `ConvertFrom-Csv` の `PSTypeName` サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-351">Add `PSTypeName` Support for `Import-Csv` and `ConvertFrom-Csv`.</span></span> <span data-ttu-id="82b16-352">(#5389) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-352">(#5389) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="82b16-353">`Import-Csv` で行区切り文字として `CR`、`LF`、`CRLF` を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="82b16-353">Make `Import-Csv` support `CR`, `LF`, and `CRLF` as line delimiters.</span></span> <span data-ttu-id="82b16-354">(#5363) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-354">(#5363) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="82b16-355">`Export-Csv` と `ConvertTo-Csv` で `-NoTypeInformation` を既定値にします。</span><span class="sxs-lookup"><span data-stu-id="82b16-355">Make `-NoTypeInformation` the default on `Export-Csv` and `ConvertTo-Csv`.</span></span> <span data-ttu-id="82b16-356">(#5164) (@markekraus に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-356">(#5164) (Thanks @markekraus)</span></span>

### <a name="service-cmdlets"></a><span data-ttu-id="82b16-357">サービスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="82b16-357">Service cmdlets</span></span>

- <span data-ttu-id="82b16-358">プロパティの `UserName`、`Description`、`DelayedAutoStart`、`BinaryPathName`、`StartupType` を、`Get-Service` によって返される `ServiceController` オブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-358">Add properties `UserName`, `Description`, `DelayedAutoStart`, `BinaryPathName`, and `StartupType` to the `ServiceController` objects returned by `Get-Service`.</span></span> <span data-ttu-id="82b16-359">(#4907) (@joandrsn に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-359">(#4907) (Thanks @joandrsn)</span></span>
- <span data-ttu-id="82b16-360">`Set-Service` コマンドで資格情報を設定するための機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-360">Add functionality to set credentials on `Set-Service` command.</span></span> <span data-ttu-id="82b16-361">(#4844) (@joandrsn に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-361">(#4844) (Thanks @joandrsn)</span></span>

### <a name="other-cmdlets"></a><span data-ttu-id="82b16-362">その他のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="82b16-362">Other cmdlets</span></span>

- <span data-ttu-id="82b16-363">リンク ループを確認し、必要に応じて symlink をトラバースする `-FollowSymlink` という `Get-ChildItem` にパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-363">Add a parameter to `Get-ChildItem` called `-FollowSymlink` that traverses symlinks on demand, with checks for link loops.</span></span> <span data-ttu-id="82b16-364">(#4020)</span><span class="sxs-lookup"><span data-stu-id="82b16-364">(#4020)</span></span>
- <span data-ttu-id="82b16-365">`CSharpVersion7` をサポートするために `Add-Type` を更新します。</span><span class="sxs-lookup"><span data-stu-id="82b16-365">Update `Add-Type` to support `CSharpVersion7`.</span></span> <span data-ttu-id="82b16-366">(#3933) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-366">(#3933) (Thanks to @iSazonov)</span></span>
- <span data-ttu-id="82b16-367">より優れたソリューションが見つかるまでサポートされていない API を使用するため、`Microsoft.PowerShell.LocalAccounts` モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="82b16-367">Remove the `Microsoft.PowerShell.LocalAccounts` module due to the use of unsupported APIs until a better solution is found.</span></span> <span data-ttu-id="82b16-368">(#4302)</span><span class="sxs-lookup"><span data-stu-id="82b16-368">(#4302)</span></span>
- <span data-ttu-id="82b16-369">より優れたソリューションが見つかるまでサポートされていない API を使用するため、`Microsoft.PowerShell.Diagnostics` の `*-Counter` コマンドレットを削除します。</span><span class="sxs-lookup"><span data-stu-id="82b16-369">Remove the `*-Counter` cmdlets in `Microsoft.PowerShell.Diagnostics` due to the use of unsupported APIs until a better solution is found.</span></span> <span data-ttu-id="82b16-370">(#4303)</span><span class="sxs-lookup"><span data-stu-id="82b16-370">(#4303)</span></span>
- <span data-ttu-id="82b16-371">`Invoke-Item -Path <folder>` のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-371">Add support for `Invoke-Item -Path <folder>`.</span></span> <span data-ttu-id="82b16-372">(#4262)</span><span class="sxs-lookup"><span data-stu-id="82b16-372">(#4262)</span></span>
- <span data-ttu-id="82b16-373">ファイル名拡張子とファイル名の残りの部分の間のパスを分割できるように、`Split-Path` に `-Extension` および `-LeafBase` スイッチを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-373">Add `-Extension` and `-LeafBase` switches to `Split-Path` so that you can split paths between the filename extension and the rest of the filename.</span></span> <span data-ttu-id="82b16-374">(#2721) (@powercode に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-374">(#2721) (Thanks to @powercode!)</span></span>
- <span data-ttu-id="82b16-375">Top/Bottom N Sort のために `Sort-Object` にパラメーターの `-Top` と `-Bottom` を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-375">Add parameters `-Top` and `-Bottom` to `Sort-Object` for Top/Bottom N sort</span></span>
- <span data-ttu-id="82b16-376">`CodeProperty "Parent"` を `System.Diagnostics.Process` に追加して、プロセスの親プロセスを公開します。</span><span class="sxs-lookup"><span data-stu-id="82b16-376">Expose a process' parent process by adding the `CodeProperty "Parent"` to `System.Diagnostics.Process`.</span></span> <span data-ttu-id="82b16-377">(#2850) (@powercode に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-377">(#2850) (Thanks to @powercode!)</span></span>
- <span data-ttu-id="82b16-378">`Get-Process` のメモリ列で、KB ではなく MB を使用します。</span><span class="sxs-lookup"><span data-stu-id="82b16-378">Use MB instead of KB for memory columns of `Get-Process`</span></span>
- <span data-ttu-id="82b16-379">`Out-String` の `-NoNewLine` スイッチを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-379">Add `-NoNewLine` switch for `Out-String`.</span></span> <span data-ttu-id="82b16-380">(#5056) (@raghav710 に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-380">(#5056) (Thanks @raghav710)</span></span>
- <span data-ttu-id="82b16-381">`Move-Item` コマンドレットで `-Include`、`-Exclude`、`-Filter` のパラメーターを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="82b16-381">`Move-Item` cmdlet honors `-Include`, `-Exclude`, and `-Filter` parameters.</span></span> <span data-ttu-id="82b16-382">(#3878)</span><span class="sxs-lookup"><span data-stu-id="82b16-382">(#3878)</span></span>
- <span data-ttu-id="82b16-383">`Remove-Item` のレジストリ パスで `*` を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="82b16-383">Allow `*` to be used in registry path for `Remove-Item`.</span></span> <span data-ttu-id="82b16-384">(#4866)</span><span class="sxs-lookup"><span data-stu-id="82b16-384">(#4866)</span></span>
- <span data-ttu-id="82b16-385">`-Title` を `Get-Credential` に追加して、プラットフォーム間のプロンプト エクスペリエンスを統合します。</span><span class="sxs-lookup"><span data-stu-id="82b16-385">Add `-Title` to `Get-Credential` and unify the prompt experience across platforms.</span></span>
- <span data-ttu-id="82b16-386">`-TimeOut` パラメーターを `Test-Connection` に追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-386">Add the `-TimeOut` parameter to `Test-Connection`.</span></span> <span data-ttu-id="82b16-387">(#2492)</span><span class="sxs-lookup"><span data-stu-id="82b16-387">(#2492)</span></span>
- <span data-ttu-id="82b16-388">`Get-AuthenticodeSignature` コマンドレットで、ファイルの署名タイムスタンプを取得できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-388">`Get-AuthenticodeSignature` cmdlets can now get file signature timestamp.</span></span> <span data-ttu-id="82b16-389">(#4061)</span><span class="sxs-lookup"><span data-stu-id="82b16-389">(#4061)</span></span>
- <span data-ttu-id="82b16-390">`Get-Help` からサポートされていない `-ShowWindow` スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="82b16-390">Remove unsupported `-ShowWindow` switch from `Get-Help`.</span></span> <span data-ttu-id="82b16-391">(#4903)</span><span class="sxs-lookup"><span data-stu-id="82b16-391">(#4903)</span></span>
- <span data-ttu-id="82b16-392">返される配列要素に区切り文字が含まれないように `Get-Content -Delimiter` を修正します。(#3706) (@mklement0 に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-392">Fix `Get-Content -Delimiter` to not include the delimiter in the array elements returned (#3706) (Thanks @mklement0)</span></span>
- <span data-ttu-id="82b16-393">`Meta`、`Charset`、`Transitional` パラメーターを `ConvertTo-HTML` に追加します。(#4184) (@ergo3114 に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-393">Add `Meta`, `Charset`, and `Transitional` parameters to `ConvertTo-HTML` (#4184) (Thanks @ergo3114)</span></span>
- <span data-ttu-id="82b16-394">`Get-ComputerInfo` 結果に `WindowsUBR` および `WindowsVersion` プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-394">Add `WindowsUBR` and `WindowsVersion` properties to `Get-ComputerInfo` result</span></span>
- <span data-ttu-id="82b16-395">`-Group` パラメーターを `Get-Verb` に追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-395">Add `-Group` parameter to `Get-Verb`</span></span>
- <span data-ttu-id="82b16-396">`ShouldProcess` のサポートを `New-FileCatalog` と `Test-FileCatalog` に追加します (`-WhatIf` と `-Confirm` を修正)。</span><span class="sxs-lookup"><span data-stu-id="82b16-396">Add `ShouldProcess` support to `New-FileCatalog` and `Test-FileCatalog` (fixes `-WhatIf` and `-Confirm`).</span></span> <span data-ttu-id="82b16-397">(#3074) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-397">(#3074) (Thanks to @iSazonov!)</span></span>
- <span data-ttu-id="82b16-398">`-WhatIf` スイッチを `Start-Process` コマンドレットに追加します。(#4735) (@sarithsutha に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-398">Add `-WhatIf` switch to `Start-Process` cmdlet (#4735) (Thanks @sarithsutha)</span></span>
- <span data-ttu-id="82b16-399">`ValidateNotNullOrEmpty` を多くの既存のパラメーターに追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-399">Add `ValidateNotNullOrEmpty` too many existing parameters.</span></span>

## <a name="tab-completion"></a><span data-ttu-id="82b16-400">Tab 補完機能</span><span class="sxs-lookup"><span data-stu-id="82b16-400">Tab completion</span></span>

- <span data-ttu-id="82b16-401">ランタイム変数の値に基づいて、Tab 補完機能の型推論を改善しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-401">Enhanced the type inference in tab completion based on runtime variable values.</span></span> <span data-ttu-id="82b16-402">(#2744) (@powercode に感謝)これにより、次のような場合に Tab 補完機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="82b16-402">(#2744) (Thanks to @powercode!) This enables tab completion in situations like:</span></span>

  ```powershell
  $p = Get-Process
  $p | Foreach-Object Prio<tab>
  ```

- <span data-ttu-id="82b16-403">`Select-Object` の `-Property` にハッシュテーブルの Tab 補完機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="82b16-403">Add Hashtable tab completion for `-Property` of `Select-Object`.</span></span> <span data-ttu-id="82b16-404">(#3625) (@powercode に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-404">(#3625) (Thanks to @powercode)</span></span>
- <span data-ttu-id="82b16-405">`Select-Object` の `-ExcludeProperty` と `-ExpandProperty` で引数のオートコンプリートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="82b16-405">Enable argument auto-completion for `-ExcludeProperty` and `-ExpandProperty` of `Select-Object`.</span></span> <span data-ttu-id="82b16-406">(#3443) (@iSazonov に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-406">(#3443) (Thanks to @iSazonov!)</span></span>
- <span data-ttu-id="82b16-407">ネイティブ コンプリーターに対する `native.exe --<tab>` 呼び出しを行うために、Tab 補完機能のバグを修正します。</span><span class="sxs-lookup"><span data-stu-id="82b16-407">Fix a bug in tab completion to make `native.exe --<tab>` call into native completer.</span></span> <span data-ttu-id="82b16-408">(#3633) (@powercode に感謝)</span><span class="sxs-lookup"><span data-stu-id="82b16-408">(#3633) (Thanks to @powercode!)</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="82b16-409">重大な変更</span><span class="sxs-lookup"><span data-stu-id="82b16-409">Breaking changes</span></span>

<span data-ttu-id="82b16-410">PowerShell Core 6.0 には多くの重大な変更が導入されています。</span><span class="sxs-lookup"><span data-stu-id="82b16-410">We've introduced a number of breaking changes in PowerShell Core 6.0.</span></span>
<span data-ttu-id="82b16-411">その詳細については、[PowerShell Core 6.0 の重大な変更][breaking-changes]に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b16-411">To read more about them in detail, see [Breaking Changes in PowerShell Core 6.0][breaking-changes].</span></span>

## <a name="debugging"></a><span data-ttu-id="82b16-412">デバッグ</span><span class="sxs-lookup"><span data-stu-id="82b16-412">Debugging</span></span>

- <span data-ttu-id="82b16-413">`Invoke-Command -ComputerName` でのリモート ステップイン デバッグをサポートします。</span><span class="sxs-lookup"><span data-stu-id="82b16-413">Support for remote step-in debugging for `Invoke-Command -ComputerName`.</span></span> <span data-ttu-id="82b16-414">(#3015)</span><span class="sxs-lookup"><span data-stu-id="82b16-414">(#3015)</span></span>
- <span data-ttu-id="82b16-415">PowerShell Core でのバインダー デバッグ ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="82b16-415">Enable binder debug logging in PowerShell Core</span></span>

## <a name="filesystem-updates"></a><span data-ttu-id="82b16-416">FileSystem の更新</span><span class="sxs-lookup"><span data-stu-id="82b16-416">Filesystem updates</span></span>

- <span data-ttu-id="82b16-417">UNC パスからの FileSystem プロバイダーの使用を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82b16-417">Enable usage of the Filesystem provider from a UNC path.</span></span> <span data-ttu-id="82b16-418">($4998)</span><span class="sxs-lookup"><span data-stu-id="82b16-418">($4998)</span></span>
- <span data-ttu-id="82b16-419">`Split-Path` で UNC ルートを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-419">`Split-Path` now works with UNC roots</span></span>
- <span data-ttu-id="82b16-420">引数なしの `cd` が `cd ~` として動作するようになりました。</span><span class="sxs-lookup"><span data-stu-id="82b16-420">`cd` with no arguments now behaves as `cd ~`</span></span>
- <span data-ttu-id="82b16-421">260 文字を超えるパスを使用できるように PowerShell Core を修正しました。</span><span class="sxs-lookup"><span data-stu-id="82b16-421">Fixed PowerShell Core to allow use of paths that are more than 260 characters long.</span></span> <span data-ttu-id="82b16-422">(#3960)</span><span class="sxs-lookup"><span data-stu-id="82b16-422">(#3960)</span></span>

## <a name="bug-fixes-and-performance-improvements"></a><span data-ttu-id="82b16-423">バグの修正とパフォーマンスの改善</span><span class="sxs-lookup"><span data-stu-id="82b16-423">Bug fixes and performance improvements</span></span>

<span data-ttu-id="82b16-424">起動時刻、さまざまな組み込みコマンドレット、ネイティブ バイナリの操作など、PowerShell 全体のパフォーマンスについて*多く*の改善を行いました。</span><span class="sxs-lookup"><span data-stu-id="82b16-424">We've made *many* improvements to performance across PowerShell, including in startup time, various built-in cmdlets, and interaction with native binaries.</span></span>

<span data-ttu-id="82b16-425">PowerShell Core 内の多くのバグの修正も行いました。</span><span class="sxs-lookup"><span data-stu-id="82b16-425">We've also fixed a number of bugs within PowerShell Core.</span></span>
<span data-ttu-id="82b16-426">修正と変更の完全なリストについては、GitHub の[変更ログ][]に関するページを確認してください。</span><span class="sxs-lookup"><span data-stu-id="82b16-426">For a complete list of fixes and changes, check out our [changelog][] on GitHub.</span></span>

## <a name="telemetry"></a><span data-ttu-id="82b16-427">テレメトリ</span><span class="sxs-lookup"><span data-stu-id="82b16-427">Telemetry</span></span>

- <span data-ttu-id="82b16-428">PowerShell Core 6.0 では、次の 2 つの値をレポートするためにコンソール ホストにテレメトリが追加されました。(#3620)</span><span class="sxs-lookup"><span data-stu-id="82b16-428">PowerShell Core 6.0 added telemetry to the console host to report two values (#3620):</span></span>
  - <span data-ttu-id="82b16-429">OS のプラットフォーム (`$PSVersionTable.OSDescription`)</span><span class="sxs-lookup"><span data-stu-id="82b16-429">the OS platform (`$PSVersionTable.OSDescription`)</span></span>
  - <span data-ttu-id="82b16-430">PowerShell の正確なバージョン (`$PSVersionTable.GitCommitId`)</span><span class="sxs-lookup"><span data-stu-id="82b16-430">the exact version of PowerShell (`$PSVersionTable.GitCommitId`)</span></span>

<span data-ttu-id="82b16-431">このテレメトリをオプトアウトする場合は、単に `$PSHome\DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY` を削除するか、または `POWERSHELL_TELEMETRY_OPTOUT` 環境変数を作成して値を `true`、`1`、または `yes` のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="82b16-431">If you want to opt-out of this telemetry, simply delete `$PSHome\DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY` or create `POWERSHELL_TELEMETRY_OPTOUT` environment variable with one of the following values: `true`, `1` or `yes`.</span></span>
<span data-ttu-id="82b16-432">このファイルを削除するか変数を作成すると、PowerShell を初めて実行する前であっても、すべてのテレメトリがバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="82b16-432">Deleting this file or creating the variable bypasses all telemetry even before the first run of PowerShell.</span></span>
<span data-ttu-id="82b16-433">[コミュニティ ダッシュボード][community-dashboard]のテレメトリから収集される、このテレメトリ データと洞察を公開することも予定しています。</span><span class="sxs-lookup"><span data-stu-id="82b16-433">We also plan on exposing this telemetry data and the insights we glean from the telemetry in the [community dashboard][community-dashboard].</span></span>
<span data-ttu-id="82b16-434">このデータの使用方法の詳細については、こちらの[ブログの投稿][telemetry-blog]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b16-434">You can find out more about how we use this data in this [blog post][telemetry-blog].</span></span>

[github]: https://github.com/PowerShell/PowerShell
[.NET Core 2.0]: https://docs.microsoft.com/dotnet/core/
[.NET Standard]: https://docs.microsoft.com/en-us/dotnet/standard/net-standard
[os_log]: https://developer.apple.com/documentation/os/logging
[Syslog]: https://en.wikipedia.org/wiki/Syslog
[ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md
[breaking-changes]: breaking-changes-ps6.md
[変更ログ]: https://github.com/PowerShell/PowerShell/tree/master/CHANGELOG.md
[changelog]: https://github.com/PowerShell/PowerShell/tree/master/CHANGELOG.md
[community-dashboard]: https://aka.ms/PSGitHubBI
[telemetry-blog]: https://blogs.msdn.microsoft.com/powershell/2017/01/31/powershell-open-source-community-dashboard/
[.NET Standard]: https://docs.microsoft.com/dotnet/standard/net-standard
[.NET ブログ]: https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard
[.NET Blog]: https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard
[YouTube]: https://www.youtube.com/watch?v=YI4MurjfMn8&list=PLRAdsfhKI4OWx321A_pr-7HhRNk7wOLLY
[FAQ]: https://github.com/dotnet/standard/blob/master/docs/faq.md
[CDXML]: https://msdn.microsoft.com/library/jj542525(v=vs.85).aspx
[docker-hub]: https://hub.docker.com/r/microsoft/powershell/
[docker]: https://github.com/PowerShell/PowerShell/tree/master/docker
[windowspsmodulepath]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[semi-annual]: https://docs.microsoft.com/windows-server/get-started/semi-annual-channel-overview
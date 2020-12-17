---
title: PowerShell 7.1 の新機能
description: PowerShell 7.1 でリリースされた新機能と変更
ms.date: 11/11/2020
ms.openlocfilehash: 5596d3ca69f5d8ea47f01ff0915e6fa33c1c463f
ms.sourcegitcommit: fb1a4bc4b249afd3513663de2e1ba3025d63467e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "94625722"
---
# <a name="whats-new-in-powershell-71"></a>PowerShell 7.1 の新機能

PowerShell 7.1 は、異種環境とハイブリッド クラウドを管理するために構築された、PowerShell のオープンソースのクロスプラットフォーム (Windows、macOS、Linux) エディションです。

PowerShell 7.0 において確立された基盤が基になっており、コミュニティの問題に関する作業が重点的に行われ、さまざまな改善と修正が含まれています。 PowerShell が安定した高性能なプラットフォームとして維持されるよう取り組んでいます。

PowerShell 7.1 には、PSReadLine 2.1.0 も組み込まれています。 このバージョンには、Predictive IntelliSense が含まれています。 Predictive IntelliSense 機能の詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/)を参照してください。

## <a name="where-can-i-install-powershell"></a>PowerShell をインストールできる場所

<!-- TODO: Update list of OS below - make sure this is consistent across all docs -->

現在、x64 で PowerShell 7.1 によりサポートされているオペレーティング システムは次のとおりです。

- Windows 8.1/10 (ARM64 を含む)
- Windows Server 2012 R2、2016、2019、および半期チャネル (SAC)
- Ubuntu 16.04/18.04/20.04 (ARM64 を含む)
- Ubuntu 19.10 (スナップ パッケージを使用)
- Debian 9/10
- CentOS と RHEL 7/8
- Fedora 32
- Alpine 3.11 以降 (ARM64 を含む)
- macOS 10.13 以降

また、次のコミュニティがサポートされています。

- Arch Linux
- Raspbian Linux
- Kali Linux

サポートされているオペレーティング システムとサポート ライフサイクルの最新情報については、[PowerShell サポート ライフサイクル](/powershell/scripting/powershell-support-lifecycle)に関するページをご覧ください

PowerShell 7.1 が Microsoft Store に公開されています。 PowerShell リリースは [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) Web サイトまたは Windows の Store アプリケーションで見つけることができます。

Microsoft Store パッケージの利点:

- Windows 10 に直接組み込まれた自動更新
- Intune や SCCM など、他のソフトウェア配布メカニズムとの統合

> [!NOTE]
> `$PSHOME` に格納されているシステムレベルの構成設定は変更できません。 これには WSMAN 構成が含まれます。 これにより、リモート セッションが PowerShell のストアベース インストールに接続できなくなります。 ユーザーレベル構成と SSH リモート処理がサポートされていません。

任意のオペレーティング システムのインストール手順を確認してください。

- [Windows](/powershell/scripting/install/installing-powershell-core-on-windows)
- [macOS](/powershell/scripting/install/installing-powershell-core-on-macos)
- [Linux](/powershell/scripting/install/installing-powershell-core-on-linux)

さらに、PowerShell 7.1 では、Debian、Ubuntu、ARM64 Alpine Linux の ARM32 および ARM64 フレーバーもサポートされています。

公式にはサポートされていませんが、コミュニティでは、[Arch](https://aur.archlinux.org/packages/powershell/) および Kali Linux 用のパッケージも提供しています。

> [!NOTE]
> Debian 10 以降、CentOS 8 以降、Ubuntu 20.04、Alpine、Arm では、WinRM リモート処理はサポートされていません。 SSH ベースのリモート処理設定の詳細については、「[SSH 経由の PowerShell リモート処理](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)」を参照してください。

## <a name="running-powershell-71"></a>PowerShell 7.1 の実行

PowerShell 7.1 は新しいディレクトリにインストールされ、Windows PowerShell 5.1 と side-by-side 実行されます。
PowerShell 7.1 はインプレース アップグレードであり、PowerShell Core 6.x または PowerShell 7.0 が置き換えられます。

- PowerShell 7.1 は `%programfiles%\PowerShell\7` にインストールされます
- `%programfiles%\PowerShell\7` フォルダーは `$env:PATH` に追加されます

PowerShell 7.1 インストーラー パッケージにより、以前のバージョンの PowerShell Core 6.x がアップグレードされます。

- Windows 上の PowerShell Core 6.x: `%programfiles%\PowerShell\6` が `%programfiles%\PowerShell\7` に置き換えられます
- Linux: `/opt/microsoft/powershell/6` が `/opt/microsoft/powershell/7` に置き換えられます
- macOS: `/usr/local/microsoft/powershell/6` が `/usr/local/microsoft/powershell/7` に置き換えられます

> [!NOTE]
> Windows PowerShell では、PowerShell を起動する実行可能ファイルには `powershell.exe` という名前が付けられます。 バージョン 6 以降、この実行可能ファイルは、side-by-side 実行をサポートするように変更されています。 PowerShell 7.1 を起動する新しい実行可能ファイルは `pwsh.exe` です。 プレビュー ビルドは、7-preview ディレクトリで `pwsh` ではなく `pwsh-preview` としてインプレースのままです。

## <a name="breaking-changes-and-improvements"></a>破壊的変更と機能強化

変更と改善に関する最新情報については、GitHub リポジトリの「[CHANGELOG](https://github.com/PowerShell/PowerShell/tree/master/CHANGELOG)」(変更ログ) を参照してください。

### <a name="breaking-changes"></a>重大な変更

<!-- TODO: Add descriptions for each breaking change - this might need to be a separate article that we link to -->

- ネイティブ コマンドによって `stderr` に書き込まれるときに、`$?` が `$false` にならないように修正されました (#13395)
- Unix 時間を入力できるように、`Get-Date` で `-FromUnixTime` の名前が `-UnixTimeSeconds` に変更されました (#13084) (@aetos382 に感謝します)
- `$ErrorActionPreference` がネイティブ コマンドの `stderr` 出力に影響を与えないようになりました (#13361)
- 明示的に指定された名前付きパラメーターで、ハッシュテーブル スプラッティングからの同じものを置き換えることができるようになりました (#13162)
- `Split-Path` でスイッチ パラメーター `-Qualifier` が位置指定ではなくなりました (#12960) (@yecril71pl に感謝します)
- `Start-Process` で、作業ディレクトリが指定されていない場合はリテラル パスとして解決されるようになりました (#11946) (@NoMoreFood に感謝します)
- Web コマンドレットの `-OutFile` パラメーターが `-LiteralPath` のように機能するようになりました (#11701) (@iSazonov に感謝します)
- `BigInteger` 数値リテラルに対する文字列パラメーターのバインドが修正されました (#11634) (@vexx32 に感謝します)
- Windows では、`Start-Process` により現在のセッションからのすべての環境変数を使用してプロセス環境が作成され、`-UseNewEnvironment` を使用すると新しい既定のプロセス環境が作成されるようになりました (#10830) (@iSazonov に感謝します)
- ScriptBlock をデリゲートに変換するときに、戻り値の結果が `PSObject` にラップされなくなりました (#10619)
- `-replace` 演算子に対してインバリアント カルチャ文字列変換が使用されるようになりました (#10954) (@iSazonov に感謝します)

### <a name="experimental-features"></a>試験的な機能

試験的な機能の詳細については、[試験的機能の使用](../learn/experimental-features.md)に関するページを参照してください。

- `PSNullConditionalOperators` の機能が試験的ではなくなりました (#13529)
- `PSUnixFileStat` の機能が試験的ではなくなりました
- すべての `*-PSBreakpoint` コマンドレットに `-Runspace` パラメーターが追加されました (#10492) (@KirkMunro に感謝します)
- ネイティブ コマンドへの `PSPath` の引き渡しをサポートするために `PSNativePSPathResolution` が追加されました (#12386)
- `-replace` 演算子に対してインバリアント カルチャ文字列変換が使用されるようになりました (#10954) (@iSazonov に感謝します)
- 将来の Predictive IntelliSense プラグインをサポートするために `PSSubsystemPluginModel` が追加されました

### <a name="general-cmdlet-updates-and-fixes"></a>一般的なコマンドレットの更新と修正

- `ConvertTo-Json` が `-Depth` の値を超えた場合、警告が出力されるようになりました (#13692)
- Windows で例外メッセージに ``"`n"`` しか含まれない事例が修正されました (#13684)
- `CONOUT$` と `CONIN$` が予約されたデバイス名として認識されるようになりました (#13508) (@davidreis97 に感謝します)
- エラーを書き込むときの対話型の高度な関数に対する `ConciseView` が修正されました (#13623)
- Web コマンドレットで `TLS` 1.3 のサポートが追加されました (#13409) (@iSazonov に感謝します)
- `CommandLineParser` の `args` に対する null チェックが追加されました (#13451) (@iSazonov に感謝します)
- Microsoft Store アプリケーションの再解析ポイントが処理されるようになりました (#13481) (@iSazonov に感謝します)
- コンテナーに PowerShell ダイレクトを使用するとき、`ObRoot` のプロパティが存在しない場合はフィールドが使用されるようになりました (#13375) (@hemisphera に感謝します)
- `UTF-7` の古い警告が表示されなくなりました (#13484)
- `Compiler.cs` で `IEnumerable<Expression>` インスタンスの複数の列挙が回避されるようになりました (#13491)
- `ConsoleApplication` と `WindowsApplication` をサポートしないように `Add-Type -OutputType` が変更されました (#13440)
- エンコードとして `UTF-7` が指定されると警告が作成されるようになりました (#13430)
- ターゲットが見つからない新しいシンボリック リンクからのエラー メッセージが修正されました (#13085) (@yecril71pl に感謝します)
- パブリック `ConsoleHost` API でパラメーター `args` が null 非許容になりました (#13429)
- `CancellationTokenSource` の不足している破棄が追加されました (#13420) (@Youssef1313 に感謝します)
- パラメーターでワイルドカードがサポートされている場合に正しく表示されない `Get-Help` が修正されました (#13353) (@ThomasNieto に感謝します)
- `-InputFormat` パラメーターに対する `pwsh` のヘルプが更新されました (#13355) (@sethvs に感謝します)
- Roslyn からコピーされたファイルの MIT ライセンスが宣言されるようになりました (#13305) (@xtqqczze に感謝します)
- `BigInteger` のキャスト動作が改善されました (#12629) (@vexx32 に感謝します)
- `Get-Acl -LiteralPath "HKLM:Software\Classes\*"` の動作が修正されました (#13107) (@Shriram0908 に感謝します)
- ビジター インターフェイスとクラスに `DefaultVisit` メソッドが追加されました (#13258)
- `pwsh` に対する短縮形スイッチ `-s` (STA) の競合が修正されました (#13262) (@iSazonov に感謝します)
- 既存の `SecureString` パスを使用するがプレーンテキストとして返すように `Read-Host -MaskInput` が変更されました (#13256)
- `IEnumerator` を使用する COM オブジェクトが .NET 5.0 でサポートされるようになったため `ComEnumerator` が削除されました (#13259)
- "HOME" 環境変数が定義されていないとき、実行空間のスタートアップ時に一時的な個人用パスが使用されるようになりました (#13239)
- 同じ履歴エントリの再帰呼び出しを検出するように `Invoke-Command` が修正されました (#13197)
- `-interactive` との競合を修正するため、`pwsh` 実行可能ファイルの `-inputformat` スイッチ プレフィックス `-in` が `-inp` に変更されました (#13205) (@iSazonov に感謝します)
- ファイルのセキュリティ ゾーンを分析するときに、WSL ファイル システム パスが処理されるようになりました (#13120)
- `Split-Path` で他のスイッチが必須になりました (#13150) (@kvprasoon に感謝します)
- PowerShell 7 用の新しい Fluent デザイン アイコン (#13100) (@sarthakmalik に感謝します)
- Unix でのクロスマウント移動をサポートするように `Move-Item` が修正されました (#13044)
- `CommandSearcher.GetNextCmdlet` での `NullReferenceException` が修正されました (#12659) (@powercode に感謝します)
- テスト フックがアクティブになっている Unix コンピューターのコマンドレットで `NullReferenceException` が発生しなくなりました (#12651) (@vexx32 に感謝します)
- `Hashtable` メンバー (`Keys` など) を `-Property` または `-ExpandProperty` と共に使用できない `Select-Object` の問題が修正されました (#11097) (@vexx32 に感謝します)
- pwsh に対する短縮形スイッチ `-w` の競合が修正されました (#12945)
- `CimCmdlet` リソース ファイルの名前が変更されました (#12955) (@iSazonov に感謝します)
- `ConciseView` で `Test-Path` が使用されなくなりました (#12778)
- `default` スイッチ ステートメント条件句にキーワードとしてフラグが設定されました (#10487) (@msftrncs に感謝します)
- `Test-Json` コマンドレットにパラメーター `SchemaFile` が追加されました (#11934) (@beatcracker に感謝します)
- 証明書プロバイダーのパラメーターが元に戻されました (#10622) (@iSazonov に感謝します)
- 相対パス ターゲットへのシンボリック リンクを作成するように `New-Item` が修正されました (#12797) (@iSazonov に感謝します)
- Process に `CommandLine` プロパティが追加されました (#12288) (@iSazonov に感謝します)
- `Read-Host` に `-MaskInput` パラメーターが追加されました (#10908) (@davinci26 に感謝します)
- `AliasAttribute` を使用するように `CimCmdlets` が変更されました (#12617) (@thlac に感謝します)
- ParameterBinderBase の書式文字列での不適切なインデックスが修正されました (#12630) (@powercode に感謝します)
- `Command.Clone()` で `CommandInfo` プロパティがコピーされるようになりました (#12301) (@TylerLeonhardt に感謝します)
- `-ExcludeDifferent` が指定されているとき、`Compare-Object` で `-IncludeEqual` が適用されるようになりました (#12317) (@davidseibel に感謝します)
- 出力を書き込む前にファイル ハンドルを閉じるように `Get-FileHash` が変更されました (#12474) (@HumanEquivalentUnit に感謝します)
- `-replace` 演算子での一貫性のない例外メッセージが修正されました (#12388) (@jackdcasey に感謝します)
- PowerShell 7 モジュールを高い優先度で処理するように `WinCompat` モジュールの読み込みが修正されました (#12269)
- `ForEach-Object -Parallel` 実行空間の再利用が実装されました (#12122)
- コレクションの列挙中にそれを変更しないように `Get-Service` が修正されました (#11851) (@NextTurn に感謝します)
- PowerShell の終了時に IPC 名前付きパイプがクリーンアップされるようになりました (#12187)
- Web コマンドレットでの `<img />` 検出の正規表現が修正されました (#12099) (@vexx32 に感謝します)
- 適切な型サフィックスが付いている短い符号付き 16 進数リテラルが許可されるようになりました (#11844) (@vexx32 に感謝します)
- Windows での `Start-Process` コマンドレットの `UseNewEnvironment` パラメーターの動作が更新されました (#10830) (@iSazonov に感謝します)
- `Get-Random` コマンドに `-Shuffle` スイッチが追加されました (#11093) (@eugenesmlv に感謝します)
- `GetWindowsPowerShellModulePath` が複数の PS のインストールと互換性を持つようになりました (#12280)
- Windows PowerShell が既定のシェルとして登録されていないシステムで動作するように `Start-Job` が修正されました (#12296)
- `Get-Command` にエイリアスと `-Syntax` を指定すると、エイリアス化されたコマンド構文が返されるようになりました (#10784) (@ChrisLGardner に感謝します)
- `-AsNeeded` を使用していて、不完全な行があるときに、CSV コマンドレットが機能するようになりました (#12281) (@iSazonov に感謝します)
- ローカルの呼び出しで、すべての書式データを表示するために `Get-FormatData` で `-PowerShellVersion 5.1` が必要なくなりました。 (#11270) (@mklement0 に感謝します)
- ビッグ エンディアン `UTF-32` のサポートが追加されました (#11947) (@NoMoreFood に感謝します)
- `ForEach-Object -Parallel` で PowerShell オブジェクトの破棄がリークする競合の可能性を修正しました (#12227)
- Unix 時間を入力できるように、`Get-Date` に `-FromUnixTime` が追加されました (#12179) (@jackdcasey に感謝します)
- コントラストが向上するように、進行状況の既定の前景色と背景色が変更されました (#11455) (@rkeithhill に感謝します)
- 現在のドライブを使用できないときの `foreach -parallel` が修正されました (#12197)
- `ScriptBlock` を `delegate` に変換するときに、戻り値の結果が `PSObject` にラップされなくなりました (#10619)
- `Test-Connection -Quiet` で DNS 解決エラーが書き込まれなくなりました (#12204) (@vexx32 に感謝します)
- アウト プロセス ジョブに対する子プロセスからのリダイレクトされた出力とエラー ストリームを読み取るために、専用のスレッドが使用されるようになりました (#11713)
- バインダー コードでの演算子の優先順位の問題が修正されました (#12075) (@DamirAinullin に感謝します)
- `ActionPreference` 型の共通パラメーターをバインドするときの `NullReferenceException` が修正されました (#12124)
- 逆シリアル化された `MatchInfo` の既定の書式が修正されました (#11728) (@iSazonov に感謝します)
- `Invoke-RestMethod` で非同期ストリームが使用されるようになりました (#11095) (@iSazonov に感謝します)
- `Get-Content -Tail` での UTF-8 の検出に対応するようになりました (#11899) (@NoMoreFood に感謝します)
- `Get-FileHash` での `IOException` が処理されるようになりました (#11944) (@iSazonov に感謝します)
- リソース文字列で `PowerShell Core` が `PowerShell` に変更されました (#11928) (@alexandair に感謝します)
- `PSHostProcessInfo` で `MainWindowTitle` が元に戻されました (#11885) (@iSazonov に感謝します)
- Windows の互換性に関するその他の小さい更新 (#11980)
- `[Environment]::NewLine` を使用して `PositionMessage` を分割するように `ConciseView` が修正されました (#12010)
- 対話型セッションに対するネットワーク ホップの制限がなくなりました (#11920)
- `SuspendStoppingPipeline()` と `RestoreStoppingPipeline()` での `NullReferenceException` が修正されました (#11870) (@iSazonov に感謝します)
- 指定されていない場合、`FormatViewDefinition` `InstanceId` の GUID が生成されるようになりました (#11896)
- エラー メッセージがウィンドウの幅より広く、空白文字が含まれない場合の `ConciseView` が修正されました (#11880)
- クロスプラットフォームの `CAPI-compatible` リモート キーの交換が許可されるようになりました (#11185) (@silijon に感謝します)
- エラー メッセージが修正されました (#11862) (@NextTurn に感謝します)
- 幅を取得するコンソールがない場合を処理するように `ConciseView` が修正されました (#11784)
- ストアと証明書プロバイダーの比較を使用するように `CmsCommands` が更新されました (#11643) (@mikeTWC1984 に感謝します)
- `mpr.dll` と STA を使用できない Windows システムで `pwsh` が動作するようになりました (#11748)
- `Un*x` と macOS に対する `Restart-Computer` がリファクタリングされて実装されました (#11319)
- Linux と macOS 用の `Stop-Computer` の実装が追加されました (#11151)
- 使用する前に `less` を使用できるかどうかを確認するように、`help` 関数が修正されました (#11737)
- `certificate_format_ps1.xml` での `PSPath` が更新されました (#11603) (@xtqqczze に感謝します)
- リンク ヘッダー内の引用符のない relation-types を照合するように正規表現が変更されました (#11711) (@Marusyk に感謝します)
- シンボリック リンクの削除中のエラー メッセージが修正されました (#11331)
- `Select-Object` で `PSCustomObject` にカスタム `Selected.*` 型が 1 回だけ追加されるようになりました (#11548) (@iSazonov に感謝します)
- `Get-Date` コマンドレットに `-AsUTC` が追加されました (#11611)
- `Format-Hex` でのブール値に関するグループ化の動作が修正されました (#11587) (@vexx32 に感謝します)
- ping 要求を送信するために、`Test-Connection` で常に既定の同期コンテキストが使用されるようになりました (#11517)
- 起動時のエラー メッセージが修正されました (#11473) (@iSazonov に感謝します)
- Web コマンドレットで null 値を含むヘッダーが無視されるようになりました (#11424) (@iSazonov に感謝します)
- `Invoke-Command` ジョブの破棄のチェックが再度追加されました。 (#11388)
- "内容が空の場合に改行を書き込まないようにフォーマッタが更新されました (#11193)" が元に戻されました (#11342) (@iSazonov に感謝します)
- `AST` またはスクリプトに一致する関数定義がある場合に、`ArgumentCompleter` からの結果を `CompleteInput` で返すことができるようになりました (#10574) (@M1kep に感謝します)
- 内容が空の場合に改行を書き込まないようにフォーマッタが更新されました (#11193)

<!-- TODO: add more general contributor thank you listing -->

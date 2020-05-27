---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.x のリリース ノート
ms.openlocfilehash: 3fc712dbcbe184c60ae248b260c8f6800f111fdd
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809878"
---
# <a name="windows-management-framework-wmf-5x-release-notes"></a>Windows Management Framework (WMF) 5.x リリース ノート

## <a name="wmf-50-changes"></a>WMF 5.0 の変更点

- PowerShell 5.0 への新しい構造化された**情報**ストリームの追加
- 次の 4 つの新しい DSC リソースを含む、DSC への機能強化
  - WindowsFeatureSet
  - WindowsOptionalFeatureSet
  - ServiceSet
  - ProcessSet
- PowerShell のリモート処理でのロールベースの管理を可能にする Just Enough Administration の追加
- PowerShell 5.0 の言語へのユーザー定義のクラスと列挙型の追加による機能拡張
- PowerShell ISE のデバッグ機能の強化とリモート デバッグの追加
- PowerShellGet モジュールと PackageManagement モジュールの追加
- PowerShell スクリプトのログ記録とトランスクリプトの拡張
- Cryptographic Message Syntax コマンドレットの追加
- WMF 5.0 への Windows 用の NetworkSwitchManager モジュールの追加
- Microsoft.PowerShell.ODataUtils モジュールの追加
- ソフトウェア インベントリ ログ (SIL) のサポートの追加
- ユーザーの要求と問題への応答によるサーバーの新規または更新されたコマンドレット

## <a name="wmf-51-changes"></a>WMF 5.1 の変更点

WMF 5.1 には、Windows Server 2016 でリリースされた PowerShell、WMI、WinRM、ソフトウェア インベントリ ログ (SIL) のコンポーネントが含まれています。 WMF 5.1 は、Windows 7、Windows 8.1、Windows Server 2008 R2、2012、および 2012 R2 にインストールすることができ、WMF 5.0 と比較すると次のいくつかの機能強化があります。

- 新しいコマンドレット
- PowerShellGet では、署名付きモジュールの適用や JEA モジュールのインストールなどの機能強化が行われています。
- PackageManagement では、コンテナー、CBS セットアップ、EXE ベースのセットアップ、CAB パッケージをサポートするようになりました。
- DSC および PowerShell クラスにおけるデバッグ機能の強化
- セキュリティの機能強化としては、プル サーバーからもたらされるカタログ署名付きモジュールの適用、PowerShellGet コマンドレットを使用するタイミングなどが挙げられます。
- さまざまなユーザー要求と問題への対応

> [!IMPORTANT]
> Windows Server 2008 または Windows 7 に WMF 5.1 をインストールする前に、WMF 3.0 がインストールされていないことを確認します。 詳細については、「[Windows Server 2008 R2 SP1 および Windows 7 SP1 での WMF 5.1 の前提条件](../setup/install-configure.md#wmf-51-prerequisites-for-windows-server-2008-r2-sp1-and-windows-7-sp1)」を参照してください。

## <a name="powershell-editions"></a>PowerShell のエディション

バージョン 5.1 から、PowerShell は機能セットとプラットフォーム互換性が異なるさまざまなエディションで利用できるようになりました。

- **Desktop Edition:**.NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。
- **Core Edition:**.NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。

### <a name="learn-more-about-using-powershell-editions"></a>PowerShell のエディションの使用に関する詳細

- [$PSVersionTable を使用して PowerShell の実行エディションを特定する](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [PSEdition パラメーターを使用して CompatiblePSEditions で Get-Module の結果をフィルター処理する](/powershell/module/microsoft.powershell.core/get-module)
- [互換性のある PowerShell のエディションで実行しない場合はスクリプトを実行させない](/powershell/scripting/gallery/concepts/script-psedition-support)
- [特定の PowerShell バージョンに対するモジュールの互換性を宣言する](/powershell/scripting/gallery/concepts/module-psedition-support)

## <a name="module-analysis-cache"></a>モジュール分析キャッシュ

WMF 5.1 以降の PowerShell では、エクスポートするコマンドなど、モジュールに関するデータのキャッシュに使用されるファイルを制御できます。

既定では、このキャッシュは `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` ファイルに格納されます。 キャッシュは、通常、起動時にコマンドを検索するときに読み取られ、モジュールのインポート後しばらくしてバックグラウンド スレッドで書き込まれます。

キャッシュの既定の場所を変更するには、PowerShell を開始する前に、環境変数 `$env:PSModuleAnalysisCachePath` を設定します。 この環境変数の変更は、子プロセスのみに影響します。 値には、PowerShell がファイルの作成および書き込みアクセス許可を持つ完全なパス (ファイル名を含む) を指定する必要があります。 ファイル キャッシュを無効にするには、たとえば次のような無効な場所をこの値に設定します。

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

これは、パスを無効なデバイスに設定します。 PowerShell がパスに書き込めない場合、エラーは返されませんが、トレーサーでエラー レポートを見ることができます。

```powershell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

キャッシュの書き込み時、PowerShell は存在しなくなったモジュールを確認することで、キャッシュが不必要に大きくなるのを防ぎます。 このような確認が望ましくないことがあり、その場合は無効に設定できます。

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

この環境変数の設定は、現在のプロセスで直ちに有効になります。

## <a name="specifying-module-version"></a>モジュールのバージョンの指定

WMF 5.1 では、`using module` は PowerShell の他のモジュール関連構造と同様に動作します。
以前は、モジュールの特定のバージョンを指定する方法はありませんでした。複数のバージョンが存在する場合、エラーが発生しました。

WMF 5.1 では次のようになります。

- [ModuleSpecification コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) を使用できます。

  このハッシュ テーブルの形式は `Get-Module -FullyQualifiedName` と同じです。

  **例:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

- モジュールに複数のバージョンがある場合、PowerShell は**同じ解決ロジック**を `Import-Module` として使用し、エラーを返しません。`Import-Module` および `Import-DscResource` と同じ動作です。

## <a name="improvements-to-pester"></a>Pester の機能強化

WMF 5.1 では、PowerShell で出荷される Pester のバージョンが 3.3.5 から 3.4.0 に更新されました。
この更新プログラムにより、Nano Server での Pester の動作が改善されます。

Pest の変更は、GitHub リポジトリの [ChangeLog](https://github.com/pester/Pester/blob/master/CHANGELOG.md) で確認できます。

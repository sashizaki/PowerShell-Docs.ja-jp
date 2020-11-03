---
description: Windows PowerShell 5.1 に含まれる新機能について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/17/2018
online version: https://docs.microsoft.com/powershell/module/?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_5。1
ms.openlocfilehash: 567af048dd137c0287c6eba4ccc42a77055c0c92
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224907"
---
# <a name="about_windows_powershell_51"></a>about_Windows_PowerShell_5。1

## <a name="short-description"></a>概要

Windows PowerShell 5.1 に含まれる新機能について説明します。

## <a name="long-description"></a>詳細説明

Windows PowerShell 5.1 には、その用途を拡大し、使いやすさを向上させ、Windows ベースの環境をより簡単かつ包括的に制御および管理できるようにする重要な新機能が含まれています。

Windows PowerShell 5.1 には下位互換性があります。 Windows PowerShell 4.0、Windows PowerShell 3.0、および Windows PowerShell 2.0 向けに設計されたコマンドレット、プロバイダー、モジュール、スナップイン、スクリプト、関数、およびプロファイルは、通常、変更なしで Windows PowerShell 5.1 で動作します。

- 新しいコマンドレット: ローカル ユーザーとグループ、Get-ComputerInfo
- PowerShellGet では、署名付きモジュールの適用や JEA モジュールのインストールなどの機能強化が行われています。
- PackageManagement では、コンテナー、CBS セットアップ、EXE ベースのセットアップ、CAB パッケージをサポートするようになりました。
- DSC および PowerShell クラスにおけるデバッグ機能の強化
- セキュリティの機能強化としては、プル サーバーからもたらされるカタログ署名付きモジュールの適用、PowerShellGet コマンドレットを使用するタイミングなどが挙げられます。
- さまざまなユーザー要求と問題への対応

Windows PowerShell 5.1 は、windows Server 2016 と Windows 10 に既定でインストールされます。 Windows Server 2012 R2、Windows 8.1 Enterprise、または Windows 8.1 Pro に Windows PowerShell 5.1 をインストールするには、「 [WMF 5.1 のインストールと構成](/powershell/scripting/wmf/setup/install-configure)」を参照してください。
Windows Management Framework 5.1 をインストールする前に、ダウンロードの詳細を読み、すべてのシステム要件を満たしていることを確認してください。

「 [Windows powershell の新機能](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50)」で、windows powershell 5.1 の変更点を確認することもできます。

## <a name="new-scenarios-and-features-in-wmf-51"></a>WMF 5.1 の新しいシナリオと機能

> 注意: この情報は暫定版であり、変更することがあります。

### <a name="powershell-editions"></a>PowerShell のエディション
PowerShell は、バージョン 5.1 以降、機能セットとプラットフォーム互換性が異なるさまざまなエディションが提供されるようになりました。

- **Desktop Edition:** .NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。
- **Core Edition:**.NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。

**PowerShell のエディションの使用に関する詳細**

- [$PSVersionTable を使用して PowerShell の実行エディションを特定する](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [PSEdition パラメーターを使用して CompatiblePSEditions で Get-Module の結果をフィルター処理する](/powershell/module/microsoft.powershell.core/get-module)
- [互換性のある PowerShell のエディションで実行しない場合はスクリプトを実行させない](/powershell/scripting/gallery/concepts/script-psedition-support)
- [特定の PowerShell バージョンに対するモジュールの互換性を宣言する](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a>カタログ コマンドレット

[Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)) モジュールに新しいコマンドレットが 2 つ追加されました。Windows カタログ ファイルを生成し、検証するコマンドレットです。

#### <a name="new-filecatalog"></a>New-FileCatalog

New-FileCatalog は、一連のフォルダーやファイルに対して Windows カタログ ファイルを作成します。
このカタログ ファイルには、指定されたパスのすべてのファイルのハッシュが含まれています。 ユーザーは一連のフォルダーと共に、それらのフォルダーを表すカタログ ファイルを配信できます。 カタログ作成時刻以降、フォルダーに変更が加えられたかどうかを検証するとき、この情報が役立ちます。

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

カタログ バージョン 1 と 2 がサポートされています。 バージョン 1 は SHA1 ハッシュ アルゴリズムを使用して、バージョン 2 は SHA256 ハッシュ アルゴリズムを使用してファイル ハッシュを作成します。 *Windows Server 2008 R2* と *Windows 7* はカタログ バージョン 2 に対応していません。 カタログ バージョン 2 は *Windows 8* 、 *Windows Server 2012* 以降のオペレーティング システムで利用する必要があります。

カタログ ファイルの整合性を検証するために (上記の例では Pester.cat)、[Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) コマンドレットで署名します。

#### <a name="test-filecatalog"></a>Test-FileCatalog

Test-FileCatalog は、一連のフォルダーを表すカタログを検証します。

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

このコマンドレットは、 *カタログ* で見つかったすべてのファイル ハッシュとその相対パスを *ディスク* のそれらと比較します。 ファイル ハッシュとパスの間に不一致が検出された場合、 *ValidationFailed* というステータスを返します。 *-Detailed* パラメーターを利用し、この情報をすべて取得できます。 *署名* プロパティには、カタログの署名ステータスも表示されます。これは、カタログ ファイルで [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) コマンドレットを呼び出すことと同じです。 *-FilesToSkip* パラメーターを利用し、検証中にファイルをスキップすることもできます。

### <a name="module-analysis-cache"></a>モジュール分析キャッシュ

WMF 5.1 以降の PowerShell では、エクスポートするコマンドなど、モジュールに関するデータのキャッシュに使用されるファイルを制御できます。

既定では、このキャッシュは `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` ファイルに格納されます。 キャッシュは、通常、起動時にコマンドを検索するときに読み取られ、モジュールのインポート後しばらくしてバックグラウンド スレッドで書き込まれます。

キャッシュの既定の場所を変更するには、PowerShell を開始する前に、環境変数 `$env:PSModuleAnalysisCachePath` を設定します。 この環境変数の変更は、子プロセスのみに影響します。 値には、PowerShell がファイルの作成および書き込みアクセス許可を持つ完全なパス (ファイル名を含む) を指定する必要があります。 ファイル キャッシュを無効にするには、たとえば次のような無効な場所をこの値に設定します。

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

これは、パスを無効なデバイスに設定します。 PowerShell がパスに書き込めない場合、エラーは返されませんが、トレーサーでエラー レポートを見ることができます。

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

キャッシュの書き込み時、PowerShell は存在しなくなったモジュールを確認することで、キャッシュが不必要に大きくなるのを防ぎます。 このような確認が望ましくないことがあり、その場合は無効に設定できます。

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

この環境変数の設定は、現在のプロセスで直ちに有効になります。

### <a name="specifying-module-version"></a>モジュールのバージョンの指定

WMF 5.1 では、`using module` は PowerShell の他のモジュール関連構造と同様に動作します。 以前は、モジュールの特定のバージョンを指定する方法はありませんでした。複数のバージョンが存在する場合、エラーが発生しました。

WMF 5.1 では次のようになります。

* [ModuleSpecification コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor) を使用できます。
  このハッシュ テーブルの形式は `Get-Module -FullyQualifiedName` と同じです。

  **例:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

* モジュールに複数のバージョンがある場合、PowerShell は **同じ解決ロジック** を `Import-Module` として使用し、エラーを返しません。`Import-Module` および `Import-DscResource` と同じ動作です。

### <a name="improvements-to-pester"></a>Pester の機能強化

WMF 5.1 では、PowerShell に付属するバージョンの pester が3.4.0 からに更新され、GitHub [PR # 484](https://github.com/pester/Pester/pull/484)が追加されました。これにより、Nano Server での pester の動作が向上します。

バージョン 3.3.5 から 3.4.0 の変更点については、https://github.com/pester/Pester/blob/master/CHANGELOG.md の ChangeLog.md ファイルを参照してください。

## <a name="keywords"></a>KEYWORDS

Windows PowerShell 5.1 の新機能

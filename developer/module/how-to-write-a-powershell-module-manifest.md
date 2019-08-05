---
title: PowerShell モジュールのマニフェストを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e082c2e3-12ce-4032-9caf-bf6b2e0dcf81
caps.latest.revision: 23
ms.openlocfilehash: 93a8c11099a9883127bca87422e1acaebfd2c093
ms.sourcegitcommit: 00cf9a99972ce40db7c25b9a3fc6152dec6bddb6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64670292"
---
# <a name="how-to-write-a-powershell-module-manifest"></a>PowerShell モジュール マニフェストを記述する方法

作成した後、Windows PowerShell モジュールでは、必要に応じて、モジュール マニフェストを追加することができます。 モジュール マニフェストは、モジュールに関する情報を含める使用できる PowerShell スクリプト ファイルです。 たとえば、著者について説明します、スクリプトを実行して、ユーザーの環境のカスタマイズ (入れ子になったモジュールの場合) など、モジュール内のファイルは、型と書式設定ファイルの読み込み、システム要件を定義し、モジュールがエクスポートするメンバーを制限を指定できます。

## <a name="creating-a-module-manifest"></a>モジュール マニフェストを作成します。

A*モジュール マニフェスト*Windows PowerShell データ ファイル (.psd1)、モジュールの内容を記述し、モジュールの処理方法を決定します。 マニフェスト ファイル自体は、キーと値のハッシュ テーブルを含むテキスト ファイルです。 マニフェスト ファイルをモジュールにリンクするには、モジュールと同じ名前と、モジュール ディレクトリのルートに配置することで。

1 つの .psm1 またはバイナリ アセンブリのみを含む単純なモジュール、モジュール マニフェストは省略可能です。 ただし、コードを整理するために、バージョン管理情報を維持するために便利ですが、可能であれば、モジュール マニフェストを使用することをお勧めします。 さらに、グローバル アセンブリ キャッシュにインストールされているアセンブリをエクスポートするには、モジュール マニフェストが必要です。 モジュール マニフェストは、更新可能なヘルプ機能をサポートするモジュールの必要もあります。 つまり、更新可能なヘルプは使用して、 **HelpInfoUri**モジュールの更新されたヘルプ ファイルの場所を含むヘルプ情報 (HelpInfo XML) ファイルを検索するモジュール マニフェストでキー。 更新可能なヘルプについては、次を参照してください。[更新可能なヘルプをサポートしている](./supporting-updatable-help.md)します。

### <a name="to-create-and-use-a-module-manifest"></a>作成して、モジュール マニフェストを使用するには

1. モジュール マニフェストを作成するには、いくつかのオプションがあります。

   1. 直接、必要な最小限の情報をハッシュ テーブルを作成し、モジュールと同じ名前を持つ .psd1 ファイルに保存します。 これを実行して後、は、ファイルを開きの適切な値を手動で追加することができます。

      `'@{ModuleVersion="1.0"}' > myModuleName.psd1`

   2. か、または、 [New-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest)パラメーターとして渡されたコマンドレットは、既定値の 1 つ以上とします。 (なお、だけで、ファイルの名前は、ただし、マニフェストを生成するために必要です)。マニフェストの値を指定した明示的に指定し、適切な既定値を含む rest を使用したモジュール マニフェストが作成されます。

      `New-ModuleManifest myModuleName.psd1 -ModuleVersion "2.0" -Author "YourNameHere"`

   3. 最後も空の .psd1 ファイルを作成し、このトピックの下部にあるテンプレート ファイルにコピーでき、関連する値を入力できます。 この場合、唯一の要件は、ファイルのモジュールと同じ名前があることを確認できるようになります。

2. ファイルであるマニフェストに追加の要素に追加します。

   一般的に言えば、これはおそらく行えますメモ帳など、必要に応じて任意のテキスト エディターで。 ただし、実際のスクリプト環境または開発環境、PowerShell ISE などで編集するためのコードを含むスクリプト ファイルは技術的には。 もう一度、マニフェスト ファイルのすべての要素は、ModuleVersion 数を除き、省略可能なことに注意してください。

   キーと値のモジュール マニフェストであることができますの説明については、次を参照してください。、**モジュール マニフェスト要素**以下。 詳細については、パラメーターの説明を参照してください、 [New-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest)コマンドレット。

3. 必要に応じて、基本のモジュール マニフェストの要素が含まれないすべてのシナリオに対処する、モジュール マニフェストに追加のコードを追加することができます。

   セキュリティの懸念事項により PowerShell は、モジュール マニフェスト ファイルで、使用可能な操作のごく一部のみを実行します。 一般に、使用、**場合**ステートメント、算術演算子および比較演算子、および PowerShell の基本的なデータ型。

4. モジュール マニフェストを作成した後への呼び出しでテストする (マニフェストはで説明されているすべてのパスが正しいことを確認するには) することができます[Test-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/Test-ModuleManifest)します。

   `Test-ModuleManifest myModuleName.psd1`

5. モジュールを格納するディレクトリの最上位レベルで、モジュール マニフェストがあることを確認します。

   システムにモジュールをコピー、インポートすると、PowerShell は、モジュールをインポートするのにモジュール マニフェストを使用します。

6. 呼び出しで、モジュール マニフェストを直接テストする必要に応じて、 [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)ドット ソース マニフェスト自体でします。

   `Import-Module .\myModuleName.psd1`

## <a name="module-manifest-elements"></a>モジュール マニフェストの要素

次の表に、モジュール マニフェストに要素

|要素|既定|説明|
|-------------|-------------|-----------------|
|RootModule<br /><br /> Type: string|' '|スクリプト モジュールまたはバイナリ モジュール ファイルこのマニフェストに関連付けられています。 PowerShell の以前のバージョンでは、この要素に、ModuleToProcess が呼び出されます。<br /><br /> ルート モジュールの種類を空にすることができます (このように、**マニフェスト**モジュール)、スクリプト モジュールの名前 (これにより、.psm1、**スクリプト**モジュール)、またはバイナリ モジュール (.exe または .dll の名前これは、これにより、**バイナリ**モジュール)。 モジュール マニフェスト (.psd1) ファイルまたはスクリプト ファイル (.ps1) の名前をこの要素に配置すると、発生するエラーが発生します。|
|ModuleVersion<br /><br /> Type: string|1.0|このモジュールのバージョン番号。 文字列は、[System.Version] に変換できる必要があります。 つまり、' #。 #。 #。 #。 #' です。 `Import-Module` 上で見つかった最初のモジュールを読み込む、 **$psModulePath**を名と一致して、少なくともの ModuleVersion を持つ、`-MinimumVersion`パラメーター。 特定のバージョンをインポートするには、使用、`-RequiredVersion`パラメーターを代わりにします。<br /><br /> 例: `ModuleVersion = '1.0'`|
|GUID<br /><br /> Type: string|自動生成された GUID|このモジュールを一意に識別するために使用される ID。 GUID のモジュールをインポートすることはできません現在に注意してください。<br /><br /> 例: `GUID = 'cfc45206-1e49-459d-a8ad-5b571ef94857'`|
|Author<br /><br /> Type: string|None|このモジュールの作成者です。<br /><br /> 例: `Author = 'AuthorNameHere'`|
|CompanyName<br /><br /> Type: string|Unknown の中から 1 つ以上を指定します|企業またはこのモジュールのベンダー。<br /><br /> 例: `CompanyName = 'Fabrikam'`|
|Copyright<br /><br /> Type: string|(c) [currentYear] [Author]。 All rights reserved.|このモジュールの著作権情報。<br /><br /> 例: `Copyright = '2016 AuthorName. All rights reserved.'`|
|Description<br /><br /> Type: string|' '|このモジュールによって提供される機能の説明です。<br /><br /> 例: `Description = 'This is a description of a module.'`|
|PowerShellVersion<br /><br /> Type: string|' '|このモジュールに必要な Windows PowerShell エンジンの最小バージョン。 現在の有効な値は、1.0、2.0、3.0、4.0、および 5.0 です。<br /><br /> 例: `PowerShellVersion = '5.0'`|
|PowerShellHostName<br /><br /> Type: string|' '|モジュールに必要な Windows PowerShell ホストの名前を指定します。 この名前は、Windows PowerShell によって提供されます。 プログラムのホスト プログラムの名前を検索する入力:`$host.name`します。<br /><br /> 例: `PowerShellHostName = 'Windows PowerShell ISE Host'`|
|PowerShellHostVersion<br /><br /> Type: string|' '|このモジュールに必要な Windows PowerShell ホストの最小バージョン。<br /><br /> 例: `PowerShellHostVersion = '2.0'`|
|DotNetFrameworkVersion<br /><br /> Type: string|' '|このモジュールに必要な Microsoft .NET Framework の最小バージョン。<br /><br /> 例: `DotNetFrameworkVersion = '3.5'`|
|CLRVersion<br /><br /> Type: string|' '|このモジュールに必要な共通言語ランタイム (CLR) の最小バージョン。<br /><br /> 例: `CLRVersion = '3.5'`|
|ProcessorArchitecture<br /><br /> Type: string|' '|プロセッサ アーキテクチャ (None、X86、Amd64) モジュールが必要です。 有効な値は x86、AMD64、IA64、および None (不明または未指定) です。<br /><br /> 例: `ProcessorArchitecture = 'x86'`|
|RequiredModules<br /><br /> Type: [string[]]|@()|このモジュールをインポートする前にグローバル環境にインポートする必要がありますモジュールです。 既に読み込まれている場合を除き、表示されているすべてのモジュールが読み込まれます。 (たとえば、一部のモジュール可能性があるによって既に読み込まれて別のモジュール。)。 使用して読み込む特定のバージョンを指定することも`RequiredVersion`なく`ModuleVersion`します。 使用する場合`ModuleVersion`指定されているバージョンの最小値で使用可能な最新バージョンが読み込まれます。<br /><br /> 例: `RequiredModules = @(@{ModuleName="myDependentModule"; ModuleVersion="2.0"; Guid="cfc45206-1e49-459d-a8ad-5b571ef94857"})`<br /><br /> 例: `RequiredModules = @(@{ModuleName="myDependentModule"; RequiredVersion="1.5"; Guid="cfc45206-1e49-459d-a8ad-5b571ef94857"})`|
|RequiredAssemblies<br /><br /> Type: [string[]]|@()|このモジュールをインポートする前に読み込む必要があるアセンブリ。<br /><br /> なお RequiredModules とは異なり、PowerShell は、既に読み込まれていない場合、RequiredAssemblies に読み込まれます。|
|ScriptsToProcess<br /><br /> Type: [string[]]|@()|モジュールがインポートされるときに、呼び出し元のセッション状態で実行されるスクリプト (.ps1) ファイル。 これにより、グローバル セッション状態や、入れ子になったモジュール、別のモジュールのセッション状態の可能性があります。 これらのスクリプトを使用して、ログイン スクリプトを使用する場合と同様に、環境を準備することができます。<br /><br /> これらのスクリプトは、マニフェストにリストされているモジュールのいずれかが読み込まれる前に実行されます。|
|TypesToProcess<br /><br /> Type: [Object[]]|@()|このモジュールをインポートするときに読み込まれるファイル (.ps1xml) を入力します。|
|FormatsToProcess<br /><br /> Type: [Object[]]|@()|このモジュールをインポートするときに読み込まれるファイル (.ps1xml) をフォーマットします。|
|NestedModules<br /><br /> Type: [Object[]]|@()|RootModule/ModuleToProcess で指定されたモジュールの入れ子になったモジュールとしてインポートするモジュールです。<br /><br /> 呼び出しに似ていますがこの要素にモジュール名を追加する`Import-Module`からスクリプトやアセンブリ コード内で。 主な違いは、マニフェスト ファイルでは、ここを読み込むものを確認しやすくなります。 また、モジュールは、ここで読み込みに失敗した場合、まだが読み込まれていない、実際のモジュール。<br /><br /> 他のモジュールに加え、スクリプト (.ps1) ファイルをロードすることもします。 これらのファイルは、ルート モジュールのコンテキストで実行されます。 (これは、ルート モジュール内のスクリプトをソーシング ドットに相当) です。|
|FunctionsToExport<br /><br /> Type: String|'*'|呼び出し元のセッション状態モジュールが (ワイルドカード文字を使用) をエクスポートする関数を指定します。 既定では、すべての関数がエクスポートされます。 このキーを使用して、モジュールによってエクスポートされる関数を制限することができます。<br /><br /> 呼び出し元のセッション状態は、グローバル セッション状態や、入れ子になったモジュールは、別のモジュールのセッション状態を指定できます。 入れ子になったモジュールを連鎖チェーン内のモジュールが FunctionsToExport キーを使用して、関数を制限しない限り、入れ子になったモジュールによってエクスポートされるすべての関数はグローバル セッション状態にエクスポートされます。<br /><br /> マニフェストも、関数のエイリアスをエクスポートする場合は、このキーは AliasesToExport キーでは、関数のエイリアスの一覧が表示されますを削除できますが、このキーは、一覧に関数のエイリアスを追加することはできません。|
|CmdletsToExport<br /><br /> Type: String|'*'|モジュールが (ワイルドカード文字を使用) をエクスポートするコマンドレットを指定します。 既定では、すべてのコマンドレットがエクスポートされます。 このキーを使用して、モジュールによってエクスポートされるコマンドレットを制限することができます。<br /><br /> 呼び出し元のセッション状態は、グローバル セッション状態や、入れ子になったモジュールは、別のモジュールのセッション状態を指定できます。 入れ子になったモジュールを連鎖しているときに入れ子になったモジュールによってエクスポートされるすべてのコマンドレットが最終的にエクスポートされますグローバル セッション状態をチェーン内のモジュールが CmdletsToExport キーを使用して、コマンドレットを制限しない限り。<br /><br /> マニフェストも、コマンドレットのエイリアスをエクスポートする場合は、このキーは AliasesToExport キーでは、コマンドレットのエイリアスの一覧が表示されますを削除できますが、このキーは、一覧にコマンドレットのエイリアスを追加することはできません。|
|VariablesToExport<br /><br /> Type: String|'*'|呼び出し元のセッション状態モジュールが (ワイルドカード文字を使用) をエクスポートする変数を指定します。 既定では、すべての変数がエクスポートされます。 このキーを使用して、モジュールによってエクスポートされる変数を制限することができます。<br /><br /> 呼び出し元のセッション状態は、グローバル セッション状態や、入れ子になったモジュールは、別のモジュールのセッション状態を指定できます。 入れ子になったモジュールを連鎖しているときに、チェーン内のモジュールが VariablesToExport キーを使用して、変数を制限しない限り、入れ子になったモジュールによってエクスポートされるすべての変数はグローバル セッション状態にエクスポートされます。<br /><br /> マニフェストも、変数のエイリアスをエクスポートする場合は、このキーは AliasesToExport キーでは、変数がエイリアスの一覧が表示されますを削除できますが、このキーは、一覧に変数のエイリアスを追加することはできません。|
|AliasesToExport<br /><br /> Type: String|'*'|呼び出し元のセッション状態モジュールが (ワイルドカード文字を使用) をエクスポートするエイリアスを指定します。 既定では、すべてのエイリアスがエクスポートされます。 このキーを使用して、モジュールによってエクスポートされるエイリアスを制限することができます。<br /><br /> 呼び出し元のセッション状態は、グローバル セッション状態や、入れ子になったモジュールは、別のモジュールのセッション状態を指定できます。 入れ子になったモジュールを連鎖しているときに入れ子になったモジュールによってエクスポートされるすべてのエイリアスが最終的にエクスポートされますグローバル セッション状態をチェーン内のモジュールが AliasesToExport キーを使用してエイリアスを制限しない限り。|
|ModuleList<br /><br /> Type: [string[]]|@()|このモジュールでは、パッケージ化するすべてのモジュールを指定します。 これらのモジュールは、ModuleName と GUID のキーを持つ名前 (コンマ区切り文字列) またはハッシュ テーブルとして入力できます。 ハッシュ テーブルには、オプションの ModuleVersion キーをこともできます。 ModuleList キーは、モジュール インベントリとして設計されています。 これらのモジュールは自動的に処理されません。|
|ファイル一覧<br /><br /> Type: [string[]]|@()|このモジュールでパッケージ化されたすべてのファイルの一覧です。 として ModuleList、FileList に役立つ、インベントリ リストとしてし、は、それ以外の場合は処理されません。|
|PrivateData<br /><br /> Type: [object]|' '|RootModule/ModuleToProcess キーで指定された、ルート モジュールに渡される必要があるプライベート データを指定します。|
|HelpInfoURI<br /><br /> Type: string|' '|このモジュールの HelpInfo URI。|
|DefaultCommandPrefix<br /><br /> Type: string|' '|コマンドの既定のプレフィックスは、このモジュールからエクスポートされます。 既定のプレフィックスを使用して、オーバーライド`Import-Module`のプレフィックス。|

## <a name="sample-module-manifest"></a>モジュール マニフェストのサンプル

次のサンプル モジュール マニフェストは、モジュール マニフェストでキーと既定値を示します。 この例を使用して作成された、 `New-ModuleManifest` Windows PowerShell 3.0 でのコマンドレット。 複数のモジュールを作成する場合は、さまざまなモジュールに対するし変更できるマニフェスト テンプレートを作成するこのコマンドレットを使用できます。

```powershell
#
# Module manifest for module 'myManifest'
#
# Generated by: User01
#
# Generated on: 1/24/2012
#

@{

# Script module or binary module file associated with this manifest
#RootModule = ''

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = 'd0a9150d-b6a4-4b17-a325-e3a24fed0aa9'

# Author of this module
Author = 'User01'

# Company or vendor of this module
CompanyName = 'Unknown'

# Copyright statement for this module
Copyright = '(c) 2012 User01. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the Windows PowerShell engine required by this module
# PowerShellVersion = ''

# Name of the Windows PowerShell host required by this module
# PowerShellHostName = ''

# Minimum version of the Windows PowerShell host required by this module
# PowerShellHostVersion = ''

# Minimum version of the .NET Framework required by this module
# DotNetFrameworkVersion = ''

# Minimum version of the common language runtime (CLR) required by this module
# CLRVersion = ''

# Processor architecture (None, X86, Amd64) required by this module
# ProcessorArchitecture = ''

# Modules that must be imported into the global environment prior to importing this module
# RequiredModules = @()

# Assemblies that must be loaded prior to importing this module
# RequiredAssemblies = @()

# Script files (.ps1) that are run in the caller's environment prior to importing this module
# ScriptsToProcess = @()

# Type files (.ps1xml) to be loaded when importing this module
# TypesToProcess = @()

# Format files (.ps1xml) to be loaded when importing this module
# FormatsToProcess = @()

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
# NestedModules = @()

# Functions to export from this module
FunctionsToExport = '*'

# Cmdlets to export from this module
CmdletsToExport = '*'

# Variables to export from this module
VariablesToExport = '*'

# Aliases to export from this module
AliasesToExport = '*'

# List of all modules packaged with this module
# ModuleList = @()

# List of all files packaged with this module
# FileList = @()

# Private data to pass to the module specified in RootModule/ModuleToProcess
# PrivateData = ''

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}

```

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの記述](./writing-a-windows-powershell-module.md)

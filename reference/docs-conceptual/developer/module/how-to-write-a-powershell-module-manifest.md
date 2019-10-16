---
title: PowerShell モジュールマニフェストを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e082c2e3-12ce-4032-9caf-bf6b2e0dcf81
caps.latest.revision: 23
ms.openlocfilehash: 1265855b82b0bfaa7b2717c8eb348b822c19f561
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367101"
---
# <a name="how-to-write-a-powershell-module-manifest"></a>PowerShell モジュール マニフェストを記述する方法

Windows PowerShell モジュールを作成したら、必要に応じてモジュールマニフェストを追加できます。 モジュールマニフェストは、モジュールに関する情報を含めるために使用できる PowerShell スクリプトファイルです。 たとえば、作成者を記述したり、モジュール内のファイル (入れ子になったモジュールなど) を指定したり、スクリプトを実行してユーザーの環境をカスタマイズしたり、種類とフォーマットファイルを読み込んだり、システム要件を定義したり、モジュールによってエクスポートされるメンバーを制限したりすることができます。

## <a name="creating-a-module-manifest"></a>モジュールマニフェストの作成

*モジュールマニフェスト*は、モジュールの内容を記述し、モジュールの処理方法を決定する Windows PowerShell データファイル (.psd1) です。 マニフェストファイル自体は、キーと値のハッシュテーブルを含むテキストファイルです。 モジュールにマニフェストファイルをリンクするには、モジュールと同じ名前を付け、モジュールディレクトリのルートに配置します。

Hbase-runner.psm1 またはバイナリアセンブリを1つだけ含む単純なモジュールの場合、モジュールマニフェストは省略可能です。 ただし、可能な限りモジュールマニフェストを使用することをお勧めします。これは、コードを整理したり、バージョン管理情報を維持したりするのに役立ちます。 また、グローバルアセンブリキャッシュにインストールされているアセンブリをエクスポートするには、モジュールマニフェストが必要です。 モジュールマニフェストは、更新可能なヘルプ機能をサポートするモジュールにも必要です。 つまり、更新可能なヘルプでは、モジュールマニフェストの**Helpinfouri**キーを使用して、モジュールの更新されたヘルプファイルの場所を含むヘルプ情報 (HelpInfo XML) ファイルを検索します。 更新可能なヘルプの詳細については、「[更新可能なヘルプのサポート](./supporting-updatable-help.md)」を参照してください。

### <a name="to-create-and-use-a-module-manifest"></a>モジュールマニフェストを作成して使用するには

1. モジュールマニフェストを作成するには、いくつかのオプションがあります。

   1. 必要最小限の情報でハッシュテーブルを直接作成し、モジュールと同じ名前の .psd1 ファイルに保存します。 これが完了したら、ファイルを開き、適切な値を手動で追加できます。

      `'@{ModuleVersion="1.0"}' > myModuleName.psd1`

   2. または、パラメーターとして渡された既定値の1つ以上を使用して、 [new-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest)コマンドレットを呼び出します。 (ただし、マニフェストを生成するにはファイルの名前のみが必要であることに注意してください)。これにより、明示的に指定したすべてのマニフェスト値と、適切な既定値を含む残りのマニフェスト値を持つモジュールマニフェストが作成されます。

      `New-ModuleManifest myModuleName.psd1 -ModuleVersion "2.0" -Author "YourNameHere"`

   3. 最後に、空の .psd1 ファイルを作成し、このトピックの下部にあるテンプレートをファイルにコピーして、関連する値を入力することもできます。 この場合の実際の要件は、ファイルの名前がモジュールと同じであることを確認することだけです。

2. ファイルに追加する要素をマニフェストに追加します。

   一般に、これは、メモ帳などの任意のテキストエディターで行うことができます。 ただし、技術的にはコードを含むスクリプトファイルであるため、Visual Studio Code などの実際のスクリプトまたは開発環境で編集することもできます。 ここでも、ModuleVersion 番号を除き、マニフェストファイルのすべての要素は省略可能であることに注意してください。

   モジュールマニフェストで使用できるキーと値の説明については、以下の**モジュールマニフェスト要素**を参照してください。 詳細については、 [new-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest)コマンドレットのパラメーターの説明を参照してください。

3. 必要に応じて、モジュールマニフェストに追加のコードを追加して、基本モジュールマニフェスト要素で対応できないシナリオに対処することもできます。

   セキュリティ上の問題により、PowerShell はモジュールマニフェストファイル内で使用可能な操作のごく一部のみを実行します。 一般に、 **if**ステートメント、算術演算子、比較演算子、および基本的な PowerShell データ型を使用できます。

4. モジュールマニフェストを作成したら、(マニフェストに記述されているパスが正しいことを確認するために) [new-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/Test-ModuleManifest)の呼び出しでテストできます。

   `Test-ModuleManifest myModuleName.psd1`

5. モジュールマニフェストが、モジュールが格納されているディレクトリの最上位レベルにあることを確認してください。

   モジュールをシステムにコピーしてインポートすると、PowerShell はモジュールマニフェストを使用してモジュールをインポートします。

6. 必要に応じて、マニフェスト[自体をドットソーシングすること](/powershell/module/Microsoft.PowerShell.Core/Import-Module)で、モジュールマニフェストを直接テストできます。

   `Import-Module .\myModuleName.psd1`

## <a name="module-manifest-elements"></a>モジュールマニフェスト要素

次の表では、モジュールマニフェストに含めることができる要素について説明します。

|要素|既定|[説明]|
|-------------|-------------|-----------------|
|RootModule<br /><br /> 型: 文字列|' '|このマニフェストに関連付けられているスクリプトモジュールまたはバイナリモジュールファイル。 以前のバージョンの PowerShell では、この要素が ModuleToProcess と呼ばれていました。<br /><br /> ルートモジュールには、空にすることができます (これは**マニフェスト**モジュールになります)。スクリプトモジュールの名前 (. hbase-runner.psm1、これは**スクリプト**モジュールになります)、またはバイナリモジュール (.exe または .dll) の名前 (これにより**バイナリ**モジュールになります)。 この要素にモジュールマニフェスト (.psd1) またはスクリプトファイル (ps1) の名前を配置すると、エラーが発生します。|
|ModuleVersion<br /><br /> 型: 文字列|1.0|このモジュールのバージョン番号。 文字列を [system.string] に変換できる必要があります。 つまり、' #. #. #. #. # ' となります。 `Import-Module` を指定すると、その名前に一致する最初のモジュールが **$psModulePath**に読み込まれ、少なくとも少なくとも1つの @no__t のパラメーターとして含まれます。 特定のバージョンをインポートするには、代わりに @ no__t-0 パラメーターを使用します。<br /><br /> 例: `ModuleVersion = '1.0'`|
|GUID<br /><br /> 型: 文字列|自動生成 GUID|このモジュールを一意に識別するために使用する ID。 現在、GUID によってモジュールをインポートすることはできません。<br /><br /> 例: `GUID = 'cfc45206-1e49-459d-a8ad-5b571ef94857'`|
|作成者<br /><br /> 型: 文字列|None|このモジュールの作成者。<br /><br /> 例: `Author = 'AuthorNameHere'`|
|CompanyName<br /><br /> 型: 文字列|Unknown の中から 1 つ以上を指定します|このモジュールの会社またはベンダー。<br /><br /> 例: `CompanyName = 'Fabrikam'`|
|著作権<br /><br /> 型: 文字列|(c) [currentYear] [Author]。 All rights reserved.|このモジュールの著作権に関する声明。<br /><br /> 例: `Copyright = '2016 AuthorName. All rights reserved.'`|
|[説明]<br /><br /> 型: 文字列|' '|このモジュールによって提供される機能の説明です。<br /><br /> 例: `Description = 'This is a description of a module.'`|
|PowerShellVersion<br /><br /> 型: 文字列|' '|このモジュールで必要な Windows PowerShell エンジンの最小バージョン。 現在有効な値は、1.0、2.0、3.0、4.0、および5.0 です。<br /><br /> 例: `PowerShellVersion = '5.0'`|
|PowerShellHostName<br /><br /> 型: 文字列|' '|モジュールに必要な Windows PowerShell ホストの名前を指定します。 この名前は Windows PowerShell によって提供されます。 ホストプログラムの名前を検索するには、プログラムで「: `$host.name`」と入力します。<br /><br /> 例: `PowerShellHostName = 'Windows PowerShell ISE Host'`|
|PowerShellHostVersion<br /><br /> 型: 文字列|' '|このモジュールで必要な Windows PowerShell ホストの最小バージョン。<br /><br /> 例: `PowerShellHostVersion = '2.0'`|
|DotNetFrameworkVersion<br /><br /> 型: 文字列|' '|このモジュールで必要な Microsoft .NET Framework の最小バージョン。<br /><br /> 例: `DotNetFrameworkVersion = '3.5'`|
|CLRVersion<br /><br /> 型: 文字列|' '|このモジュールで必要な共通言語ランタイム (CLR) の最小バージョン。<br /><br /> 例: `CLRVersion = '3.5'`|
|ProcessorArchitecture<br /><br /> 型: 文字列|' '|このモジュールに必要なプロセッサアーキテクチャ (None、X86、Amd64)。 有効な値は x86、AMD64、IA64、および None (不明または未指定) です。<br /><br /> 例: `ProcessorArchitecture = 'x86'`|
|RequiredModules<br /><br /> 型: [string []]|@()|このモジュールをインポートする前に、グローバル環境にインポートする必要があるモジュール。 これにより、既に読み込まれている場合を除き、すべてのモジュールが読み込まれます。 (たとえば、別のモジュールによって一部のモジュールが既に読み込まれている場合があります。)。 また、`ModuleVersion` ではなく `RequiredVersion` を使用して、読み込む特定のバージョンを指定することもできます。 @No__t-0 を使用すると、指定された最小バージョンで使用可能な最新バージョンが読み込まれます。<br /><br /> 例: `RequiredModules = @(@{ModuleName="myDependentModule"; ModuleVersion="2.0"; Guid="cfc45206-1e49-459d-a8ad-5b571ef94857"})`<br /><br /> 例: `RequiredModules = @(@{ModuleName="myDependentModule"; RequiredVersion="1.5"; Guid="cfc45206-1e49-459d-a8ad-5b571ef94857"})`|
|RequiredAssemblies<br /><br /> 型: [string []]|@()|このモジュールをインポートする前に読み込む必要があるアセンブリ。<br /><br /> RequiredModules とは異なり、PowerShell は、RequiredAssemblies がまだ読み込まれていなければ、そのアセンブリを読み込みます。|
|ScriptsToProcess<br /><br /> 型: [string []]|@()|モジュールがインポートされたときに、呼び出し元のセッション状態で実行されるスクリプト (ps1) ファイル。 グローバルなセッション状態、または入れ子になったモジュールの場合は、別のモジュールのセッション状態になります。 これらのスクリプトを使用すると、ログインスクリプトを使用する場合と同様に、環境を準備できます。<br /><br /> これらのスクリプトは、マニフェストに示されているモジュールのいずれかが読み込まれる前に実行されます。|
|TypesToProcess<br /><br /> 型: [string []]|@()|このモジュールをインポートするときに読み込まれる型ファイル (types.ps1xml)。|
|列挙<br /><br /> 型: [string []]|@()|このモジュールをインポートするときに読み込まれるフォーマットファイル (types.ps1xml)。|
|NestedModules<br /><br /> 型: [string []]|@()|RootModule/ModuleToProcess で指定されたモジュールの入れ子になったモジュールとしてインポートするモジュール。<br /><br /> モジュール名をこの要素に追加することは、スクリプトまたはアセンブリコード内から `Import-Module` を呼び出すことと似ています。 主な違いは、マニフェストファイルに読み込んでいる内容を簡単に確認できることです。 また、モジュールがここで読み込めない場合、実際のモジュールはまだ読み込まれていません。<br /><br /> 他のモジュールに加えて、スクリプト (ps1) ファイルをここに読み込むこともできます。 これらのファイルは、ルートモジュールのコンテキストで実行されます。 (これは、ルートモジュール内のスクリプトを作成するドットに相当します)。|
|FunctionsToExport<br /><br /> 型: [string []]|@()|呼び出し元のセッション状態に対して、モジュールがエクスポートする関数を指定します (ワイルドカード文字は許可されますが、推奨されません)。 既定では、関数はエクスポートされません。 このキーを使用すると、モジュールによってエクスポートされる関数の一覧を表示できます。<br /><br /> 呼び出し元のセッション状態は、グローバルなセッション状態にすることも、入れ子になったモジュールの場合は別のモジュールのセッション状態にすることもできます。 入れ子になったモジュールを連結する場合、チェーン内のモジュールが FunctionsToExport キーを使用して関数を制限しない限り、入れ子になったモジュールによってエクスポートされたすべての関数がグローバルセッション状態にエクスポートされます。<br /><br /> マニフェストによって関数のエイリアスもエクスポートされる場合、このキーを使用すると、一致するエイリアスが含まれている関数を削除できます。ただし、このキーでは、一覧に関数エイリアスを追加することはできません。|
|CmdletsToExport<br /><br /> 型: [string []]|@()|モジュールによってエクスポートされるコマンドレットを指定します (ワイルドカード文字は許可されますが、推奨されません)。 既定では、コマンドレットはエクスポートされません。 このキーを使用すると、モジュールによってエクスポートされたコマンドレットを一覧表示できます。<br /><br /> 呼び出し元のセッション状態は、グローバルなセッション状態にすることも、入れ子になったモジュールの場合は別のモジュールのセッション状態にすることもできます。 入れ子になったモジュールをチェーンする場合は、チェーン内のモジュールがコマンドレットをコマンドレットによって制限しない限り、入れ子になったモジュールによってエクスポートされるすべてのコマンドレットが最終的にグローバルセッション状態にエクスポートされます。<br /><br /> マニフェストによってコマンドレットのエイリアスもエクスポートされる場合、このキーを使用すると、リストにエイリアスが含まれているコマンドレットを削除できます。ただし、このキーでは、コマンドレットのエイリアスを一覧に追加することはできません。|
|変数 Stoexport<br /><br /> 型: 文字列|'*'|モジュールによってエクスポートされる (ワイルドカード文字が許可される) 変数を呼び出し元のセッション状態に指定します。 既定では、すべての変数がエクスポートされます。 このキーを使用すると、モジュールによってエクスポートされる変数を制限できます。<br /><br /> 呼び出し元のセッション状態は、グローバルなセッション状態にすることも、入れ子になったモジュールの場合は別のモジュールのセッション状態にすることもできます。 入れ子になったモジュールをチェーンする場合は、チェーン内のモジュールが variables Stoexport キーを使用して変数を制限しない限り、入れ子になったモジュールによってエクスポートされるすべての変数がグローバルセッション状態にエクスポートされます。<br /><br /> マニフェストによって変数のエイリアスもエクスポートされる場合、このキーを使用すると、リストに含まれている別名を持つ変数を削除できますが、このキーでは、変数エイリアスを一覧に追加することはできません。|
|AliasesToExport<br /><br /> 型: [string []]|@()|モジュールがエクスポートするエイリアスを指定します (ワイルドカード文字は許可されますが、呼び出し元のセッション状態には使用できません)。 既定では、エイリアスはエクスポートされません。 このキーを使用すると、モジュールによってエクスポートされるエイリアスを一覧表示できます。<br /><br /> 呼び出し元のセッション状態は、グローバルなセッション状態にすることも、入れ子になったモジュールの場合は別のモジュールのセッション状態にすることもできます。 入れ子になったモジュールをチェーンしている場合、チェーン内のモジュールが、このキーを使用して別名を制限しない限り、入れ子になったモジュールによってエクスポートされたすべてのエイリアスが最終的にグローバルセッション状態にエクスポートされます。|
|ModuleList<br /><br /> 型: [string []]|@()|このモジュールでパッケージ化されているすべてのモジュールを指定します。 これらのモジュールは、名前 (コンマ区切り文字列) で入力することも、ModuleName キーと GUID キーを持つハッシュテーブルとして入力することもできます。 ハッシュテーブルには、省略可能な ModuleVersion キーを含めることもできます。 ModuleList キーは、モジュールインベントリとして機能するように設計されています。 これらのモジュールは自動的に処理されません。|
|FileList<br /><br /> 型: [string []]|@()|このモジュールでパッケージ化されたすべてのファイルの一覧。 ModuleList と同様に、FileList は在庫リストとしての使用を支援するものであり、それ以外の処理は行われません。|
|PrivateData<br /><br /> 型: [オブジェクト]|@{...}|RootModule/ModuleToProcess キーによって指定されたルートモジュールに渡す必要があるプライベートデータを指定します。|
|HelpInfoURI<br /><br /> 型: 文字列|' '|このモジュールの HelpInfo URI。|
|DefaultCommandPrefix<br /><br /> 型: 文字列|' '|このモジュールからエクスポートされたコマンドの既定のプレフィックス。 @No__t-0-Prefix を使用して既定のプレフィックスをオーバーライドします。|

## <a name="sample-module-manifest"></a>サンプルモジュールマニフェスト

次のサンプルモジュールマニフェストは、モジュールマニフェストのキーと既定値を示しています。 この例は、Windows PowerShell 3.0 の `New-ModuleManifest` コマンドレットを使用して作成されました。 複数のモジュールを作成する場合は、このコマンドレットを使用して、さまざまなモジュールに対して変更できるマニフェストテンプレートを作成できます。

```powershell
#
# Module manifest for module 'myManifest'
#
# Generated by: User01
#
# Generated on: 2019-10-09
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '1.0'

# Supported PSEditions
# CompatiblePSEditions = @()

# ID used to uniquely identify this module
GUID = 'b888e5a2-8578-4c0b-938d-0cd9b5b836ba'

# Author of this module
Author = 'User01'

# Company or vendor of this module
CompanyName = 'Unknown'

# Copyright statement for this module
Copyright = '(c) 2019 User01. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the Windows PowerShell engine required by this module
# PowerShellVersion = ''

# Name of the Windows PowerShell host required by this module
# PowerShellHostName = ''

# Minimum version of the Windows PowerShell host required by this module
# PowerShellHostVersion = ''

# Minimum version of Microsoft .NET Framework required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# DotNetFrameworkVersion = ''

# Minimum version of the common language runtime (CLR) required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# CLRVersion = ''

# Processor architecture (None, X86, Amd64) required by this module
# ProcessorArchitecture = ''

# Modules that must be imported into the global environment prior to importing this module
# RequiredModules = @()

# Assemblies that must be loaded prior to importing this module
# RequiredAssemblies = @()

# Script files (.ps1) that are run in the caller's environment prior to importing this module.
# ScriptsToProcess = @()

# Type files (.ps1xml) to be loaded when importing this module
# TypesToProcess = @()

# Format files (.ps1xml) to be loaded when importing this module
# FormatsToProcess = @()

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
# NestedModules = @()

# Functions to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no functions to export.
FunctionsToExport = @()

# Cmdlets to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no cmdlets to export.
CmdletsToExport = @()

# Variables to export from this module
VariablesToExport = '*'

# Aliases to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no aliases to export.
AliasesToExport = @()

# DSC resources to export from this module
# DscResourcesToExport = @()

# List of all modules packaged with this module
# ModuleList = @()

# List of all files packaged with this module
# FileList = @()

# Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell.
PrivateData = @{

    PSData = @{

        # Tags applied to this module. These help with module discovery in online galleries.
        # Tags = @()

        # A URL to the license for this module.
        # LicenseUri = ''

        # A URL to the main website for this project.
        # ProjectUri = ''

        # A URL to an icon representing this module.
        # IconUri = ''

        # ReleaseNotes of this module
        # ReleaseNotes = ''

    } # End of PSData hashtable

} # End of PrivateData hashtable

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}

```

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの作成](./writing-a-windows-powershell-module.md)

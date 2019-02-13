---
ms.date: 12/14/2018
keywords: PowerShell, コマンドレット
title: 移植可能なモジュールの作成
ms.openlocfilehash: 38a93b5b030d58784b91292e2cd060b3a2c19a00
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55682551"
---
# <a name="portable-modules"></a>移植可能なモジュール

Windows PowerShell が用に記述された[.NET Framework][]用の PowerShell Core の書き込み中に[.NET Core][]します。 移植可能なモジュールとは、Windows PowerShell と PowerShell Core の両方で動作するモジュールです。 .NET Framework と .NET Core は互換性が高いが、2 つの利用可能な Api の違いがあります。 違いが、Api で Windows PowerShell と PowerShell Core で使用できます。 モジュールの両方の環境で使用するものでは、これらの違いを意識する必要があります。

## <a name="porting-an-existing-module"></a>既存のモジュールの移植

### <a name="porting-a-pssnapin"></a>PSSnapIn の移植

PowerShell スナップイン (PSSnapIn) は、PowerShell Core でサポートされていません。 ただし、PSSnapIn を PowerShell モジュールに変換する単純なは。 派生したクラスの 1 つのソース ファイルで PSSnapIn 登録コードは、通常、 [PSSnapIn][]します。 このソース ファイル、ビルドから削除します。これが不要になった。

使用[New-modulemanifest][] PSSnapIn 登録コードの必要性を置換する新しいモジュール マニフェストを作成します。 (説明) などの PSSnapIn から値の一部は、モジュール マニフェスト内で再利用できます。

`RootModule`コマンドレットを実装するアセンブリ (dll) の名前に、モジュール マニフェスト内のプロパティを設定する必要があります。

### <a name="the-net-portability-analyzer-aka-apiport"></a>.NET Portability Analyzer (APIPort とも呼ばれます)

PowerShell Core で動作、開始して Windows PowerShell 用に記述されたモジュールをポートに、 [.NET Portability Analyzer][]します。 モジュールで使用される .NET Api が .NET Framework、.NET Core、およびその他の .NET ランタイムと互換性があるかを判断するコンパイル済みのアセンブリに対してこのツールを実行します。 このツールは、存在する場合の代替 Api をお勧めします。 追加する必要がありますそれ以外の場合、[ランタイム チェック][]し、特定のランタイムで使用できない機能を制限します。

## <a name="creating-a-new-module"></a>新しいモジュールの作成

使用する推奨事項は、新しいモジュールを作成する場合、 [.NET CLI][]します。

### <a name="installing-the-powershell-standard-module-template"></a>標準の PowerShell モジュールのテンプレートをインストールします。

.NET CLI がインストールされると、単純な PowerShell モジュールを生成するテンプレート ライブラリをインストールします。
モジュールは、Windows PowerShell、PowerShell Core、Windows、Linux、および macOS の操作に互換性があります。

次の例では、テンプレートをインストールする方法を示します。

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
```

```output
  Restoring packages for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj...
  Installing Microsoft.PowerShell.Standard.Module.Template 0.1.3.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.targets.
  Restore completed in 1.66 sec for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj.

Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.
  -n, --name          The name for the output being created. If no name is specified, the name of the current directory is used.
  -o, --output        Location to place the generated output.
  -i, --install       Installs a source or a template pack.
  -u, --uninstall     Uninstalls a source or a template pack.
  --nuget-source      Specifies a NuGet source to use during install.
  --type              Filters templates based on available types. Predefined values are "project", "item" or "other".
  --force             Forces content to be generated even if it would change existing files.
  -lang, --language   Filters templates based on language and specifies the language of the template to create.


Templates                                         Short Name         Language          Tags
----------------------------------------------------------------------------------------------------------------------------
Console Application                               console            [C#], F#, VB      Common/Console
Class library                                     classlib           [C#], F#, VB      Common/Library
PowerShell Standard Module                        psmodule           [C#]              Library/PowerShell/Module
...
```

### <a name="creating-a-new-module-project"></a>新しいモジュール プロジェクトの作成

テンプレートをインストールした後は、そのテンプレートを使用して、新しい PowerShell モジュール プロジェクトを作成できます。 この例では、サンプル モジュールが 'myModule' と呼ばれます。

```
PS> mkdir myModule

    Directory: C:\Users\Steve

Mode LastWriteTime Length Name
---- ------------- ------ ----
d----- 8/3/2018 2:41 PM myModule

PS> cd myModule
PS C:\Users\Steve\myModule> dotnet new psmodule

The template "PowerShell Standard Module" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\Users\Steve\myModule\myModule.csproj...
  Restoring packages for C:\Users\Steve\myModule\myModule.csproj...
  Installing PowerShellStandard.Library 5.1.0.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.targets.
  Restore completed in 1.76 sec for C:\Users\Steve\myModule\myModule.csproj.

Restore succeeded.
```

### <a name="building-the-module"></a>モジュールの構築

プロジェクトをビルドするのにには、標準の .NET CLI コマンドを使用します。

```powershell
dotnet build
```

```output
PS C:\Users\Steve\myModule> dotnet build
Microsoft (R) Build Engine version 15.7.179.6572 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 76.85 ms for C:\Users\Steve\myModule\myModule.csproj.
  myModule -> C:\Users\Steve\myModule\bin\Debug\netstandard2.0\myModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:05.40
```

### <a name="testing-the-module"></a>モジュールのテスト

モジュールをビルドした後は、インポートし、サンプルのコマンドレットを実行できます。

```powershell
ipmo .\bin\Debug\netstandard2.0\myModule.dll
Test-SampleCmdlet -?
Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat
```

```output
PS C:\Users\Steve\myModule> ipmo .\bin\Debug\netstandard2.0\myModule.dll
PS C:\Users\Steve\myModule> Test-SampleCmdlet -?

NAME
    Test-SampleCmdlet

SYNTAX
    Test-SampleCmdlet [-FavoriteNumber] <int> [[-FavoritePet] {Cat | Dog | Horse}] [<CommonParameters>]


ALIASES
    None


REMARKS
    None


PS C:\Users\Steve\myModule> Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat

FavoriteNumber FavoritePet
-------------- -----------
             7 Cat
```

次のセクションについて詳しく説明このテンプレートで使用されるテクノロジの一部です。

## <a name="net-standard-library"></a>.NET 標準ライブラリ

[.NET standard][]はすべての .NET 実装で使用できる .NET Api の正式な仕様です。 .NET Standard のバージョンと互換性のある .NET Framework と .NET Core のバージョンで動作を .NET Standard をターゲットとするコードを管理します。

> [!NOTE]
> .NET Core での API の実装が .NET standard API が存在する可能性があります、スローする可能性が、 `PlatformNotSupportedException` 、実行時にように Windows PowerShell および PowerShell Core との互換性を確認するベスト プラクティスは、モジュール内での両方の環境のテストを実行します。
> クロスプラット フォーム対応にするものでは、モジュールの場合は、Linux と macOS でテストを実行します。

.NET Standard をターゲットとにより、モジュールの進化に伴って、互換性のない Api しない誤って取得に導入されたモジュール。 非互換性は、ランタイムではなくコンパイル時に検出されます。

ただし、必須ではなく .NET 標準モジュールの Windows PowerShell と PowerShell Core の両方を使用するターゲットに互換性のある Api を使用する限り。 中間言語 (IL) は、2 つのランタイムとの間に互換性があります。 .NET Framework 4.6.1 を対象 .NET Standard 2.0 と互換性があることができます。 .NET Standard 2.0 以外の Api を使用しないし、モジュールは、再コンパイルせずに PowerShell Core 6 では機能します。

## <a name="powershell-standard-library"></a>PowerShell の標準ライブラリ

[PowerShell の標準][]ライブラリは、その標準のバージョン以上のすべての PowerShell バージョンで利用可能な PowerShell Api の正式な仕様。

たとえば、[PowerShell の標準 5.1][]は、Windows PowerShell 5.1 と PowerShell Core 6.0 の両方と互換性のある以降です。

PowerShell の標準ライブラリを使用して、モジュールをコンパイルすることをお勧めします。 ライブラリにより、Api が使用可能で Windows PowerShell と PowerShell Core 6 の両方に実装されているようになります。
PowerShell の標準は、常に上位互換になります。 標準ライブラリ 5.1 の PowerShell を使用して構築されたモジュールは、PowerShell の将来のバージョンと互換性のある常になります。

## <a name="module-manifest"></a>モジュール マニフェスト

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a>Windows PowerShell および PowerShell Core との互換性を示す

モジュールが Windows PowerShell と PowerShell Core の両方で動作するかを検証した後、モジュール マニフェストが明示的に示す互換性を使用して、 [CompatiblePSEditions][]プロパティ。 値`Desktop`モジュールが Windows PowerShell では、値の中に互換性があることを意味`Core`モジュールが PowerShell Core と互換性があることを意味します。 両方を含む`Desktop`と`Core`モジュールが Windows PowerShell と PowerShell Core の両方と互換性があることを意味します。

> [!NOTE]
> `Core` わけではありません、モジュールが、Windows、Linux、および macOS と互換性があります。
> **CompatiblePSEditions**プロパティは PowerShell v5 で導入されました。 モジュール マニフェストを使用して、 **CompatiblePSEditions**プロパティは、PowerShell v5 以前のバージョンでの読み込みに失敗します。

### <a name="indicating-os-compatibility"></a>OS の互換性を示す

最初に、Linux と macOS で、モジュールが動作する検証します。 次に、モジュール マニフェストでこれらのオペレーティング システムとの互換性を示します。 これにより、ユーザーに発行されると、オペレーティング システムのモジュールを見つけやすく、 [PowerShell ギャラリー][]します。

モジュール マニフェスト内で、`PrivateData`プロパティは、`PSData`サブプロパティ。 省略可能な`Tags`プロパティの`PSData`は PowerShell ギャラリーに表示される値の配列を受け取ります。 PowerShell ギャラリーには、次の互換性の値がサポートされています。

| タグ               | 説明                                |
|-------------------|--------------------------------------------|
| PSEdition_Core    | PowerShell Core 6 と互換性があります。          |
| PSEdition_Desktop | Windows PowerShell との互換性         |
| Windows           | Windows と互換性があります。                    |
| Linux             | Linux (特定のディストリビューションがありません) との互換性 |
| macOS             | MacOS と互換性があります。                      |

次に例を示します。

```powershell
@{
    GUID = "4ae9fd46-338a-459c-8186-07f910774cb8"
    Author = "Microsoft Corporation"
    CompanyName = "Microsoft Corporation"
    Copyright = "(C) Microsoft Corporation. All rights reserved."
    HelpInfoUri = "https://go.microsoft.com/fwlink/?linkid=855962"
    ModuleVersion = "1.2.4"
    PowerShellVersion = "3.0"
    ClrVersion = "4.0"
    RootModule = "PackageManagement.psm1"
    Description = 'PackageManagement (a.k.a. OneGet) is a new way to discover and install software packages from around the web.
 It is a manager or multiplexer of existing package managers (also called package providers) that unifies Windows package management with a single Windows PowerShell interface. With PackageManagement, you can do the following.
  - Manage a list of software repositories in which packages can be searched, acquired and installed
  - Discover software packages
  - Seamlessly install, uninstall, and inventory packages from one or more software repositories'

    CmdletsToExport = @(
        'Find-Package',
        'Get-Package',
        'Get-PackageProvider',
        'Get-PackageSource',
        'Install-Package',
        'Import-PackageProvider'
        'Find-PackageProvider'
        'Install-PackageProvider'
        'Register-PackageSource',
        'Set-PackageSource',
        'Unregister-PackageSource',
        'Uninstall-Package'
        'Save-Package'
    )

    FormatsToProcess  = @('PackageManagement.format.ps1xml')

    PrivateData = @{
        PSData = @{
            Tags = @('PackageManagement', 'PSEdition_Core', 'PSEdition_Desktop', 'Windows', 'Linux', 'macOS')
            ProjectUri = 'https://oneget.org'
        }
    }
}
```

<!-- reference links -->
[.NET Framework]: /dotnet/framework/
[.NET Core]: /dotnet/core/
[PSSnapIn]: /dotnet/api/system.management.automation.pssnapin
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[ランタイム チェック]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[.NET CLI]: /dotnet/core/tools/?tabs=netcore2x
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell の標準]: https://github.com/PowerShell/PowerShellStandard
[PowerShell の標準 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[PowerShell ギャラリー]: https://www.powershellgallery.com
[.NET portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/gallery/concepts/module-psedition-support

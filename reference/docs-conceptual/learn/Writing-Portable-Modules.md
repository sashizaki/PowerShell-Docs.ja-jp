---
ms.date: 12/14/2018
keywords: PowerShell, コマンドレット
title: 移植可能なモジュールの作成
ms.openlocfilehash: 7871f524495c1ce5283b30696a24185d427edebf
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417651"
---
# <a name="portable-modules"></a>移植可能なモジュール

Windows PowerShell が [.NET Framework][] 用であるのに対し、PowerShell Core は [.NET Core][] 用に作成されています。 移植可能なモジュールとは、Windows PowerShell と PowerShell Core の両方で動作するモジュールです。 .NET Framework と .NET Core の間には高い互換性がありますが、使用可能な API には違いがあります。 また、Windows PowerShell と PowerShell Core でも使用できる API が異なります。 両方の環境で使用するモジュールを作成するときは、これらの違いを意識する必要があります。

## <a name="porting-an-existing-module"></a>既存のモジュールの移植

### <a name="porting-a-pssnapin"></a>PSSnapIn の移植

PowerShell [スナップイン](/powershell/scripting/developer/cmdlet/modules-and-snap-ins)は、PowerShell Core ではサポートされていません。 ただし、PSSnapIn を PowerShell モジュールに変換するのは簡単です。 通常、PSSnapIn の登録コードは、[PSSnapIn][] の派生クラスの単一のソース ファイルに含まれます。
このソース ファイルは、必要ありませんので、ビルドから削除します。

[New-ModuleManifest][] を使って、PSSnapIn 登録コードに必要なものを置き換える新しいモジュール マニフェストを作成します。 **PSSnapIn** の値の一部 (**Description** など) は、モジュール マニフェスト内で再利用できます。

モジュール マニフェストの **RootModule** プロパティは、コマンドレットを実装するアセンブリ (dll) の名前に設定する必要があります。

### <a name="the-net-portability-analyzer-aka-apiport"></a>.NET Portability Analyzer (別名 APIPort)

Windows PowerShell 用に記述されたモジュールを PowerShell Core で動作するように移植するには、最初に [.NET Portability Analyzer][] を使用します。 コンパイル済みアセンブリに対してこのツールを実行し、モジュールで使われている .NET API が .NET Framework、.NET Core、および他の .NET ランタイムと互換性があるかどうかを判断します。 このツールでは、代替 API がある場合は指摘されます。 それ以外の場合は、[ランタイム チェック][]を追加し、特定のランタイムで使用できない機能を制限することが必要な場合があります。

## <a name="creating-a-new-module"></a>新しいモジュールの作成

新しいモジュールを作成する場合に推奨されるのは、[.NET CLI][] の使用です。

### <a name="installing-the-powershell-standard-module-template"></a>PowerShell 標準モジュール テンプレートのインストール

.NET CLI をインストールした後、簡単な PowerShell モジュールを生成するためのテンプレート ライブラリをインストールします。
そのモジュールは、Windows PowerShell、PowerShell Core、Windows、Linux、および macOS と互換性を持つようになります。

次の例では、テンプレートのインストール方法を示します。

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

テンプレートをインストールした後は、そのテンプレートを使用して新しい PowerShell モジュール プロジェクトを作成できます。 この例のサンプル モジュールの名前は "myModule" です。

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

### <a name="building-the-module"></a>モジュールのビルド

標準の .NET CLI コマンドを使用して、プロジェクトをビルドします。

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

モジュールをビルドした後は、それをインポートしてサンプルのコマンドレットを実行できます。

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

次のセクションでは、このテンプレートで使用されているテクノロジの一部について詳しく説明します。

## <a name="net-standard-library"></a>.NET 標準ライブラリ

[.NET Standard][] は、すべての .NET 実装で使用できる .NET API の正式な仕様です。 .NET Standard をターゲットとするマネージド コードは、.NET Standard のそのバージョンと互換性のある .NET Framework および .NET Core のバージョンで動作します。

> [!NOTE]
> .NET Standard に API が存在していても、.NET Core での API の実装で実行時に `PlatformNotSupportedException` がスローされる可能性があるので、Windows PowerShell および PowerShell Core との互換性を確認するため、両方の環境内でモジュールのテストを実行するのがベスト プラクティスです。
> クロスプラットフォームを意図したモジュールの場合は、Linux と macOS でもテストを実行します。

.NET Standard をターゲットにすると、モジュールが進化しても、互換性のない API が誤ってモジュールに導入されないことが保証されます。 非互換性は、実行時ではなくコンパイル時に検出されます。

ただし、互換性のある API を使用してさえいれば、.NET Standard をターゲットにしなくても、モジュールは Windows PowerShell と PowerShell Core の両方で動作します。 中間言語 (IL) は、2 つのランタイムの間で互換性があります。 .NET Framework 4.6.1 をターゲットにでき、これは .NET Standard 2.0 と互換性があります。 .NET Standard 2.0 の対象外の API を使用していなければ、モジュールは再コンパイルしなくても PowerShell Core 6 で動作します。

## <a name="powershell-standard-library"></a>PowerShell Standard ライブラリ

[PowerShell Standard][] ライブラリは、その標準のバージョン以降のすべての PowerShell のバージョンで利用可能な PowerShell API の正式な仕様です。

たとえば、[PowerShell Standard 5.1][] は、Windows PowerShell 5.1 および PowerShell Core 6.0 以降の両方と互換性があります。

PowerShell Standard ライブラリを使用してモジュールをコンパイルすることをお勧めします。 ライブラリにより、API が使用可能で、Windows PowerShell と PowerShell Core 6 の両方で実装されていることが保証されます。
PowerShell Standard は、常に上位互換性があるように意図されています。 PowerShell Standard ライブラリ 5.1 を使用してビルドされたモジュールは、PowerShell の将来のバージョンと常に互換性があります。

## <a name="module-manifest"></a>モジュール マニフェスト

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a>Windows PowerShell および PowerShell Core との互換性を示す

モジュールが Windows PowerShell と PowerShell Core の両方で動作することを検証した後は、モジュール マニフェストで [CompatiblePSEditions][] プロパティを使用して、互換性を明示的に示す必要があります。 値 `Desktop` はモジュールに Windows PowerShell との互換性があることを意味し、値 `Core` はモジュールに PowerShell Core との互換性があることを意味します。 `Desktop` と `Core` の両方を含めると、モジュールに Windows PowerShell および PowerShell Core の両方との互換性があることを意味します。

> [!NOTE]
> `Core` によってモジュールに Windows、Linux、macOS との互換性があることが自動的に示されることはありません。
> PowerShell v5 では **CompatiblePSEditions** プロパティが導入されました。 **CompatiblePSEditions** プロパティを使用しているモジュール マニフェストは、PowerShell v5 より前のバージョンに読み込むことができません。

### <a name="indicating-os-compatibility"></a>OS の互換性を示す

最初に、モジュールが Linux と macOS で動作することを検証します。 次に、モジュール マニフェストでこれらのオペレーティング システムとの互換性を示します。 これにより、[PowerShell ギャラリー][]に発行した後で、ユーザーがオペレーティング システム用のモジュールを見つけやすくなります。

モジュール マニフェスト内で、`PrivateData` プロパティには `PSData` サブプロパティがあります。 `PSData` の省略可能な `Tags` プロパティは、PowerShell ギャラリーに表示される値の配列を受け取ります。 PowerShell ギャラリーでは、次の互換性の値がサポートされています。

| タグ               | 説明                                |
|-------------------|--------------------------------------------|
| PSEdition_Core    | PowerShell Core 6 と互換性があります          |
| PSEdition_Desktop | Windows PowerShell と互換性があります         |
| Windows           | Windows と互換性があります                    |
| Linux             | Linux と互換性があります (特定のディストリビューションはなし) |
| macOS             | macOS と互換性があります                      |

例:

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
[PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[PowerShell ギャラリー]: https://www.powershellgallery.com
[.NET Portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/scripting/gallery/concepts/module-psedition-support

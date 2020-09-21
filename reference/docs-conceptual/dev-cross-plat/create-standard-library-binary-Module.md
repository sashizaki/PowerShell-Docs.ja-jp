---
title: 標準ライブラリのバイナリ モジュールの作成方法
description: PowerShell 標準ライブラリを使用すると、PowerShell Core と Windows PowerShell 5.1 の両方で動作するクロスプラットフォーム モジュールを作成できます。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: ff6a49f70a3fb77f5a30cc909d53bb77b3cd7d43
ms.sourcegitcommit: 8c01e56f0c10ff2637955dc892ea78432d563a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "88702747"
---
# <a name="how-to-create-a-standard-library-binary-module"></a>標準ライブラリのバイナリ モジュールの作成方法

私は先日、バイナリ モジュールとして実装したいモジュールのアイデアを思いつきました。 [PowerShell 標準ライブラリ][]を使用して作成したことはまだないため、これは良い機会のように思われました。 私は[クロスプラットフォーム バイナリ モジュールの作成][]に関するガイドを使用して、問題なくこのモジュールを作成しました。
ここではその同じプロセスについて説明し、その過程で多少のコメントを追加します。

> [!NOTE]
> この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログ記事です。 このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。 [PowerShellExplained.com][] のブログをご確認ください。

## <a name="what-is-the-powershell-standard-library"></a>PowerShell 標準ライブラリとは

PowerShell 標準ライブラリを使用すると、PowerShell Core と Windows PowerShell 5.1 (または 3.0) の両方で動作するクロスプラットフォーム モジュールを作成できます。

## <a name="planning-our-module"></a>モジュールを計画する

このモジュールの計画は、C# コード用の `src` フォルダーを作成し、スクリプト モジュールの場合と同様に残りの構造を作成することです。 これには、ビルド スクリプトを使用してすべてを `output` フォルダーにコンパイルする作業も含まれます。 フォルダー構造は、次のようになります。

```
MyModule
├───src
├───Output
│   └───MyModule
├───MyModule
│   ├───Data
│   ├───Private
│   └───Public
└───Tests
```

## <a name="getting-started"></a>作業の開始

私は通常 Plaster テンプレートを使用しますが、現在のテンプレートにはバイナリ モジュールのサポートがまだありません。 大した問題ではありません。 ここでは、これを手動で作成します。

まず、フォルダーを作成し、git リポジトリを作成する必要があります。 モジュール名のプレースホルダーとして `$module` を使用します。 これにより、必要に応じてこれらの例を再利用しやすくなります。

```powershell
$module = 'MyModule'
New-Item -Path $module -Type Directory
Set-Location $module
git init
```

次に、ルート レベル フォルダーを作成します。

```powershell
New-Item -Path 'src' -Type Directory
New-Item -Path 'Output' -Type Directory
New-Item -Path 'Tests' -Type Directory
New-Item -Path $module -Type Directory
```

### <a name="binary-module-setup"></a>バイナリ モジュールのセットアップ

この記事ではバイナリ モジュールに重点を置くため、ここから開始します。 このセクションでは、[クロスプラットフォーム バイナリ モジュールの作成][]に関するガイドからの例を利用します。 詳細を知りたい場合や問題が発生した場合は、このガイドを確認してください。

最初に行う必要があるのは、インストールした [dotnet core SDK][] のバージョンを確認することです。 私は 2.1.4 を使用していますが、2.0.0 以降をインストールしてから続行する必要があります。

```powershell
PS> dotnet --version
2.1.4
```

このセクションでは、`src` フォルダーから作業します。

```powershell
Set-Location 'src'
```

dotnet コマンドを使用して、新しいクラス ライブラリを作成します。

```powershell
dotnet new classlib --name $module
```

これにより、サブフォルダーにライブラリ プロジェクトが作成されましたが、この追加された入れ子のレベルは不要です。 これらのファイルを 1 つ上のレベルに移動します。

```powershell
Move-Item -Path .\$module\* -Destination .\
Remove-Item $module -Recurse
```

プロジェクトに .NET Core SDK のバージョンを設定します。 2\.1 SDK があるので、私は 2.1.0 を指定します。
2\.0 SDK を使用している場合は、2.0.0 を使用してください。

```powershell
dotnet new globaljson --sdk-version 2.1.0
```

PowerShell 標準ライブラリの [NuGet パッケージ][]をプロジェクトに追加します。 必要な互換性レベルにおいて使用できる最新のバージョンを使用するようにしてください。 私は最新バージョンを既定値に設定しますが、このモジュールで PowerShell 3.0 より新しい機能が活用されることはないはずです。

```powershell
dotnet add package PowerShellStandard.Library --version 7.0.0-preview.1
```

src フォルダーは次のようになるはずです。

```powershell
PS> Get-ChildItem
    Directory: \MyModule\src

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        7/14/2018   9:51 PM                obj
-a----        7/14/2018   9:51 PM             86 Class1.cs
-a----        7/14/2018  10:03 PM            259 MyModule.csproj
-a----        7/14/2018  10:05 PM             45 global.json
```

これで、独自のコードをプロジェクトに追加する準備ができました。

### <a name="building-a-binary-cmdlet"></a>バイナリ コマンドレットのビルド

次のスターター コマンドレットを含むように `src\Class1.cs` を更新する必要があります。

```csharp
using System;
using System.Management.Automation;

namespace MyModule
{
    [Cmdlet( VerbsDiagnostic.Resolve , "MyCmdlet")]
    public class ResolveMyCmdletCommand : PSCmdlet
    {
        [Parameter(Position=0)]
        public Object InputObject { get; set; }

        protected override void EndProcessing()
        {
            this.WriteObject(this.InputObject);
            base.EndProcessing();
        }
    }
}
```

クラス名と一致するようにファイル名を変更します。

```powershell
Rename-Item .\Class1.cs .\ResolveMyCmdletCommand.cs
```

次に、モジュールをビルドできます。

```powershell
PS> dotnet build

Microsoft (R) Build Engine version 15.5.180.51428 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

Restore completed in 18.19 ms for C:\workspace\MyModule\src\MyModule.csproj.
MyModule -> C:\workspace\MyModule\src\bin\Debug\netstandard2.0\MyModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:02.19
```

新しい dll に対して `Import-Module` を呼び出し、新しいコマンドレットを読み込むことができます。

```powershell
PS> Import-Module .\bin\Debug\netstandard2.0\$module.dll
PS> Get-Command -Module $module

CommandType Name                    Version Source
----------- ----                    ------- ------
Cmdlet      Resolve-MyCmdlet        1.0.0.0 MyModule
```

ご自分のシステムでインポートに失敗した場合は、.NET を 4.7.1 以降に更新してみてください。 [クロスプラットフォーム バイナリ モジュールの作成][]に関するガイドでは、.NET のサポートと旧バージョンの .NET の互換性について詳しく説明しています。

### <a name="module-manifest"></a>モジュール マニフェスト

dll をインポートして、作業モジュールを用意することができたら便利です。 これを継続し、モジュール マニフェストを作成してみたいと思います。 後で PSGallery に発行する場合は、マニフェストが必要です。

プロジェクトのルートから次のコマンドを実行して、必要なモジュール マニフェストを作成できます。

```powershell
$manifestSplat = @{
    Path              = ".\$module\$module.psd1"
    Author            = 'Kevin Marquette'
    NestedModules     = @('bin\MyModule.dll')
    RootModule        = "$module.psm1"
    FunctionsToExport = @('Resolve-MyCmdlet')
}
New-ModuleManifest @manifestSplat
```

また、今後の PowerShell 関数用に、空のルート モジュールも作成します。

```powershell
Set-Content -Value '' -Path ".\$module\$module.psm1"
```

これにより、通常の PowerShell 関数とバイナリ コマンドレットの両方を同じプロジェクトに混在させることができます。

### <a name="building-the-full-module"></a>完全なモジュールのビルド

すべてを 1 つの出力フォルダーにコンパイルします。 そのためには、ビルド スクリプトを作成する必要があります。 通常は、これを `Invoke-Build` スクリプトに追加するのですが、この例ではこれをシンプルにしておくことができます。 これをプロジェクトのルートにある `build.ps1` に追加します。

```powershell
$module = 'MyModule'
Push-Location $PSScriptRoot

dotnet build $PSScriptRoot\src -o $PSScriptRoot\output\$module\bin
Copy-Item "$PSScriptRoot\$module\*" "$PSScriptRoot\output\$module" -Recurse -Force

Import-Module "$PSScriptRoot\Output\$module\$module.psd1"
Invoke-Pester "$PSScriptRoot\Tests"
```

これらのコマンドにより、DLL がビルドされ、`output\$module\bin` フォルダーに配置されます。 その後、その他のモジュール ファイルが適切な場所にコピーされます。

```
Output
└───MyModule
    │   MyModule.psd1
    │   MyModule.psm1
    │
    └───bin
            MyModule.deps.json
            MyModule.dll
            MyModule.pdb
```

この時点で、psd1 ファイルを使用してモジュールをインポートできます。

```powershell
Import-Module ".\Output\$module\$module.psd1"
```

ここから、`.\Output\$module` フォルダーを `$env:PSModulePath` ディレクトリに追加することができ、これにより必要な時にいつでもコマンドが自動的に読み込まれます。

### <a name="update-dotnet-new-psmodule"></a>更新: dotnet new PSModule

`dotnet` ツールには `PSModule` テンプレートがあることがわかりました。

上記で説明したすべての手順はまだ有効ですが、このテンプレートによってその多くが省略されます。これはまだかなり新しいテンプレートであり、依然として改良が加えられています。 これからも改良が続けられていくでしょう。

PSModule テンプレートをインストールして使用する方法を次に示します。

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
dotnet new psmodule
dotnet build
Import-Module "bin\Debug\netstandard2.0\$module.dll"
Get-Module $module
```

この実用最小限のテンプレートによって、.NET SDK と PowerShell 標準ライブラリの追加が処理され、プロジェクトにクラスの例が作成されます。 すぐにこれをビルドして実行することができます。

## <a name="important-details"></a>重要な詳細

この記事を終了する前に、言及する価値のあるその他の詳細についていくつか説明します。

### <a name="unloading-dlls"></a>DLL のアンロード

バイナリ モジュールが読み込まれると、それを実際にアンロードすることはできません。 DLL ファイルは、これをアンロードするまでロックされます。 これは開発時にはわずらわしい場合があります。変更を加えてビルドしようとするたびに、ファイルがしばしばロックされているためです。 これを解決する唯一の信頼性の高い方法は、DLL を読み込んだ PowerShell セッションを閉じることです。

### <a name="vs-code-reload-window-action"></a>VS Code のウィンドウの再読み込み操作

私は、PowerShell の開発作業のほとんどを [VS Code][] で行っています。 バイナリ モジュール (またはクラスを含むモジュール) に取り組んでいるときは、ビルドするたびに VS Code を再読み込みする習慣を持っています。
<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> キーを押すとコマンド ウィンドウがポップアップ表示され、`Reload Window` は常に一覧の先頭にあります。

### <a name="nested-powershell-sessions"></a>入れ子になった PowerShell セッション

もう 1 つの選択肢は、適切な Pester テスト カバレッジを使用することです。 次に、新しい PowerShell セッションを開始するように build.ps1 スクリプトを調整して、ビルドを実行し、テストを実行して、セッションを閉じることができます。

### <a name="updating-installed-modules"></a>インストールされているモジュールの更新

ローカルにインストールされているモジュールを更新しようとする場合、このロックが面倒になる可能性があります。 これがいずれかのセッションで読み込まれている場合は、それを見つけて閉じる必要があります。 PSGallery からインストールする場合、これはあまり問題にはなりません。モジュールのバージョン管理によって新しいものが異なるフォルダーに配置されるためです。

ローカルの PSGallery を設定し、ビルドの一部としてそれに発行することができます。 その後、その PSGallery からローカル インストールを実行します。 これは多くの作業のように聞こえますが、docker コンテナーを起動する場合と同じように簡単にできます。 [PSRepository 用に NuGet サーバーを使用する][]に関する投稿で、これを行う方法が説明されています。

## <a name="why-binary-modules"></a>バイナリ モジュールを使用する理由

バイナリ モジュールを作成する方法について説明しましたが、それを作成する理由については触れませんでした。 実際には、ユーザーは C# で記述し、PowerShell コマンドレットと関数への簡単なアクセスをあきらめます。 これが、私がすぐにバイナリ モジュールに移行しなかった主な理由です。

ただし、他の多くの PowerShell コマンドに依存しないモジュールを作成する場合は、大きなパフォーマンス上の利点を得られる可能性があります。 C# を使用することで、PowerShell によって追加されるオーバーヘッドを軽減できます。 PowerShell は、コンピューターではなく管理者向けに最適化されたため、オーバーヘッドがわずかに増加しています。

私たちの職場には、JSON とハッシュテーブルを使用する多くの作業を行う重要なプロセスがあります。 私たちは PowerShell を可能な限り最適化しましたが、このプロセスは依然として 12 分間実行されました。 モジュールには、既に多数の C# スタイルの PowerShell が含まれていました。 これにより、バイナリ モジュールへの変換がクリーンかつ実行しやすくなりました。 この変換によって、そのプロセスが 12 分以上から 4 分以内に短縮されました。

### <a name="hybrid-modules"></a>ハイブリッド モジュール

バイナリ コマンドレットと PowerShell 拡張関数を混在させることができます。 これはまさにこのガイドで行われていることです。 スクリプト モジュールについて知っているすべてのことを利用できます。これらはすべて同じ方法で適用されます。
今回作成した空の `psm1` ファイルは、単に後で他の PowerShell 関数を追加することが目的です。

作成したコンパイル済みのコマンドレットのほとんどが、最初は PowerShell 関数として開始されています。 すべてのバイナリ モジュールは、実際にはハイブリッド モジュールです。

### <a name="build-scripts"></a>ビルド スクリプト

ここでは、ビルド スクリプトをシンプルな状態にしておきました。 私は通常、CI/CD パイプラインの一部として大きな `Invoke-Build` スクリプトを使用します。 これにより、さらに多くの機能を実行できます。たとえば、Pester テストの実行、PSScriptAnalyzer の実行、バージョン管理、PSGallery への発行などです。 自分のモジュール用にビルド スクリプトを使い始めると、これに追加するものを多数発見できました。

## <a name="final-thoughts"></a>最後に

バイナリ モジュールは簡単に作成できます。 コマンドレットを作成するための C# の構文には触れませんでしたが、[Windows PowerShell SDK][] にはこれに関する多くのドキュメントがあります。 これは、より高度な C# への足掛かりとして、ぜひ試してみる価値があります。

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[PowerShell 標準ライブラリ]: https://github.com/PowerShell/PowerShellStandard
[クロスプラットフォーム バイナリ モジュールの作成]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[dotnet core SDK]: https://www.microsoft.com/net/download/core
[PSRepository 用に NuGet サーバーを使用する]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell-reference
[VS Code]: https://code.visualstudio.com
[nuget パッケージ]: https://www.nuget.org/packages/PowerShellStandard.Library/

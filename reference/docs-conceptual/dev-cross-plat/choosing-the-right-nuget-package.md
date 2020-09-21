---
title: .NET プロジェクトに適した PowerShell NuGet パッケージの選択
description: PowerShell チームによって、各 PowerShell リリースで公開された実行可能パッケージと共に、NuGet から入手できるいくつかのパッケージも保持されます。 これらのパッケージを使用すると、.NET の API プラットフォームとして PowerShell をターゲットにすることができます。
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 39369ed872faa76ad2c41d813da5e0a98cf1c078
ms.sourcegitcommit: d0461273abb6db099c5e784ef00f57fd551be4a6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85795321"
---
# <a name="choosing-the-right-powershell-nuget-package-for-your-net-project"></a>.NET プロジェクトに適した PowerShell NuGet パッケージの選択

PowerShell チームによって、各 PowerShell リリースで公開された `pwsh` 実行可能パッケージと共に、[NuGet][] から入手できるいくつかのパッケージも保持されます。 これらのパッケージを使用すると、.NET の API プラットフォームとして PowerShell をターゲットにすることができます。

API を提供し、独自のもの (バイナリ モジュール) を実装する .NET ライブラリを読み込むことが想定される .NET アプリケーションとして、PowerShell を NuGet パッケージの形式で使用できるようにすることが不可欠です。

現時点で、何らかの表示形式で PowerShell API サーフェス領域を提供する NuGet パッケージがいくつかあります。 特定のプロジェクトで使用するパッケージが常に明確になっているわけではありません。 この記事では、PowerShell をターゲットとする .NET プロジェクトのいくつかの一般的なシナリオと、PowerShell 指向の .NET プロジェクトのターゲットとなる適切な NuGet パッケージを選択する方法を明確にします。

## <a name="hosting-vs-referencing"></a>ホスティングと参照

.NET プロジェクトには、既存の PowerShell ランタイム (`pwsh`、`powershell.exe`、PowerShell 統合コンソールまたは ISE など) に読み込まれるコードを記述しようとするものもあれば、独自のアプリケーションで PowerShell を実行する必要があるものもあります。

- **参照**は、プロジェクト (通常はモジュール) が PowerShell に読み込まれることを想定している場合です。
  これは、やりとりするために PowerShell によって提供される API に対してコンパイルする必要がありますが、PowerShell の実装は、それを読み込む PowerShell プロセスによって提供されます。 参照の場合、プロジェクトで[参照アセンブリ][]または実際のランタイム アセンブリをコンパイル ターゲットとして使用できますが、そのビルドでこれらのいずれも公開されていないことを確実にする必要があります。
- **ホスティング**は、プロジェクトで独自の PowerShell の実装が必要な場合です。これは、通常、PowerShell を実行する必要があるスタンドアロン アプリケーションであるためです。 この場合、純粋な参照アセンブリは使用できません。 代わりに、PowerShell の具象実装に依存する必要があります。 PowerShell の具象実装を使用する必要があるため、ホスト用に特定のバージョンの PowerShell を選択する必要があります。単一のホスト アプリケーションで、PowerShell の複数のバージョンをターゲットにすることはできません。

### <a name="publishing-projects-that-target-powershell-as-a-reference"></a>参照として PowerShell をターゲットとするプロジェクトの公開

> [!NOTE]
> この記事では、**公開**という用語は、`dotnet publish` を実行することを指します。これにより、.NET ライブラリがそのすべての依存関係を持つディレクトリに配置され、特定のランタイムに展開できるようになります。

コンパイル参照ターゲットとしてのみ使用されているプロジェクトの依存関係を公開しないようにするために、[PrivateAssets 属性][]を設定することをお勧めします。

```xml
<PackageReference Include="PowerShellStandard.Library" Version="5.1.0.0" PrivateAssets="all" />
```

この操作を忘れた場合に、参照アセンブリをターゲットとして使用すると、実際の実装ではなく、参照アセンブリの既定の実装の使用に関する問題が発生する可能性があります。 参照アセンブリでは多くの場合、`null` を返すだけで実装 API がモックされるため、これは `NullReferenceException` の形式になることがあります。

## <a name="key-kinds-of-powershell-targeting-net-projects"></a>PowerShell をターゲットとする .NET プロジェクト主な種類

任意の .NET ライブラリまたはアプリケーションで PowerShell を埋め込むことはできますが、PowerShell API を使用する一般的なシナリオがいくつかあります。

- **PowerShell バイナリ モジュールの実装**

  PowerShell バイナリ モジュールは、PowerShell によって読み込まれる .NET ライブラリであり、それぞれコマンドレットやプロバイダーを公開するために、[PSCmdlet][] や [CmdletProvider][] 型などの PowerShell API を実装する必要があります。 これらが読み込まれるため、モジュールによって、そのビルドで公開することなく、PowerShell への参照に対するコンパイルが試みられます。 また、モジュールでは、理想的にはディスク領域、複雑さ、または反復実装のオーバーヘッドが最小限に抑えられる、複数の PowerShell バージョンとプラットフォームをサポートする必要があるのが一般的です。 モジュールの詳細については、「[about_Modules][]」を参照してください。

- **PowerShell ホストの実装**

  PowerShell ホストによって、PowerShell ランタイムの相互作用レイヤーが提供されます。 これは特定の形式の "_ホスト_" であり、この場合、[PSHost][] は PowerShell への新しいユーザー インターフェイスとして実装されます。 たとえば、PowerShell ConsoleHost では、PowerShell 実行可能ファイル用のターミナル ユーザー インターフェイスが提供されます。一方、PowerShell エディター サービス ホストと ISE ホストの両方では、PowerShell に関する、エディターに部分的に統合されたグラフィカル ユーザー インターフェイスが提供されます。 既存の PowerShell プロセスにホストを読み込むことはできますが、ホストの実装は、PowerShell エンジンを再配布するスタンドアロンの PowerShell の実装として機能するのがより一般的です。

- **別の .NET アプリケーションからの PowerShell の呼び出し**

  他のアプリケーションと同様に、PowerShell をサブプロセスとして呼び出し、ワークロードを実行することができます。 しかし、.NET アプリケーションとして、PowerShell をインプロセスで呼び出して、呼び出し元のアプリケーション内で使用する完全な .NET オブジェクトを取得することもできます。 これは、より一般的な形式の "_ホスト_" であり、この場合、アプリケーションによって、内部使用のためにその独自の PowerShell 実装が保持されます。 この例として、マシンの状態を管理するために PowerShell を実行するサービスやデーモン、あるいはクラウド配置の管理などの操作の要求に応じて PowerShell を実行する Web アプリケーションなどがあります。

- **.NET からの PowerShell モジュールの単体テスト**

  PowerShell に機能を公開するように設計されているモジュールとその他のライブラリは、主に PowerShell からテストする必要があります ([Pester][] を推奨)。場合によっては、.NET から PowerShell モジュール用に記述された API の単体テストが必要になることがあります。 このような状況では、モジュール コードでいくつかの PowerShell バージョンをターゲットにすることが試行されますが、テストでは特定の具象実装で実行する必要があります。

## <a name="powershell-nuget-packages-at-a-glance"></a>PowerShell NuGet パッケージの概要

この記事では、PowerShell API を公開する次の NuGet パッケージについて説明します。

- [PowerShellStandard.Library][]。これは、複数の PowerShell ランタイムによって読み込むことができる単一のアセンブリのビルドを可能にする参照アセンブリです。
- [Microsoft.PowerShell.SDK][]。これは、PowerShell SDK 全体をターゲットとし、再ホストする方法です
- [System.Management.Automation][] パッケージ。これは、コア PowerShell ランタイムとエンジンの実装であり、最小限のホストされた実装と、バージョン固有のターゲット シナリオで役立ちます。
- **Windows PowerShell 参照アセンブリ**。これは、Windows PowerShell (PowerShell バージョン 5.1 以下) をターゲットとし、効果的に再ホストする方法です。

> [!NOTE]
> [PowerShell NuGet][] パッケージは .NET ライブラリ パッケージではありませんが、代わりに PowerShell dotnet グローバル ツールの実装が提供されます。 これは、実行可能ファイルのみが提供されるため、どのプロジェクトでも使用できません。

## <a name="powershellstandardlibrary"></a>PowerShellStandard.Library

PowerShell Standard ライブラリは、PowerShell バージョン 7、6、および 5.1 の API の共通部分をキャプチャする参照アセンブリです。 これにより、.NET コードをコンパイルするためにコンパイル時にチェックされる API サーフェスが提供され、.NET プロジェクトによって、そこに存在しない API を呼び出すリスクを負うことなく、PowerShell バージョン 7、6、5.1 をターゲットにすることができます。

PowerShell Standard は、PowerShell モジュールを記述することを目的としています。また、PowerShell プロセスに読み込まれた後に実行することのみを目的とした他のコードを記述することもできます。 これは参照アセンブリであるため、PowerShell Standard 自体には実装は含まれていません。したがって、スタンドアロン アプリケーション用の機能は提供されません。

### <a name="using-powershell-standard-with-different-net-runtimes"></a>異なる .NET ランタイムでの PowerShell Standard の使用

PowerShell Standard は、[.NET Standard 2.0][] ターゲット ランタイムをターゲットとしています。これは、.NET Framework および .NET Core によって共有される共通のサーフェス領域を提供するように設計されたファサード ランタイムです。 これにより、単一のランタイムをターゲットとし、複数の PowerShell バージョンで動作する単一のアセンブリを生成できますが、次のような影響があります。

- モジュールまたはライブラリを読み込む PowerShell では、少なくとも .NET 4.6.1 を実行する必要があります。 .NET 4.6 と .NET 4.5.2 では、.NET Standard はサポートされていません。 新しい Windows PowerShell のバージョンは、新しい .NET Framework のバージョンを意味するわけではないことにご注意ください。Windows PowerShell 5.1 は、.NET 4.5.2 で実行される場合があります。
- 4\.7.1 以下の .NET Framework が実行されている PowerShell を使用するには、.NET 4.6.1 [NETStandard.Library][] の実装が必要です。これにより、古いバージョンの .NET Framework で netstandard .dll とその他の shim アセンブリが提供されます。

PowerShell 6 以降によって、.NET Framework 4.6.1 (以上) から .NET Core に型転送するための独自の shim アセンブリが提供されます。 これは、.NET Core に存在する API のみがモジュールで使用されている限り、PowerShell 6 以降が、.NET Framework 4.6.1 (`net461` ランタイム ターゲット) 用にビルドされている場合、それを読み込んで実行できることを意味します。

つまり、公開された単一の DLL を持つ複数の PowerShell バージョンをターゲットとするために PowerShell Standard を使用するバイナリ モジュールには、次の 2 つのオプションがあります。

1. `net461` ターゲット ランタイム用にビルドされたアセンブリの公開。 これには以下が含まれます。
   - `net461` ランタイム用のプロジェクトの公開
   - また、使用されているすべての API が .NET Core にも存在することを保証するための、(ビルド出力を使用しない) `netstandard2.0` ランタイムに対するコンパイル。

1. `netstandard2.0` ターゲット ランタイム用にビルドされたアセンブリの公開。 これには以下が必要です。
   - `netstandard2.0` ランタイム用のプロジェクトの公開
   - NETStandard.Library の `net461` 依存関係の取得と、プロジェクト アセンブリの公開場所へのコピー。これにより、アセンブリは .NET Framework で適切に型転送されるようになります。

古いバージョンの .NET Framework をターゲットとする PowerShell モジュールまたはライブラリをビルドするために、複数の .NET ランタイムをターゲットにすることをお勧めします。 これにより、ターゲット ランタイムごとにアセンブリが公開されます。また、適切なアセンブリをモジュールの読み込み時に読み込む必要があります (たとえば、ルート モジュールとして小さな psm1 を使用する場合)。

### <a name="testing-powershell-standard-projects-in-net"></a>.NET での PowerShell Standard プロジェクトのテスト

xUnit のような .NET テスト ランナーでのモジュールのテストに関しては、コンパイル時のチェックでしかないことにご注意ください。 モジュールは、関連する PowerShell プラットフォームに対してテストする必要があります。

.NET で PowerShell Standard に対してビルドされた API をテストするには、`Microsoft.Powershell.SDK` を .NET Core とのテスト依存関係として (バージョンが目的の PowerShell バージョンと一致するように設定する)、また、.NET Framework に適した Windows PowerShell 参照アセンブリを追加する必要があります。

PowerShell Standard と、それを使用して複数の PowerShell バージョンで動作するバイナリ モジュールを記述する方法について詳しくは、[こちらのブログ記事][]を参照してください。 GitHub の [PowerShell Standard リポジトリ][]も参照してください。

## <a name="microsoftpowershellsdk"></a>Microsoft.PowerShell.SDK

`Microsoft.PowerShell.SDK` は、PowerShell SDK のすべてのコンポーネントを単一の NuGet パッケージにまとめたメタパッケージです。 自己完結型の .NET アプリケーションにより、外部の PowerShell インストールまたはライブラリに依存することなく、任意の PowerShell 機能を実行するために Microsoft.PowerShell.SDK を使用できます。

> [!NOTE]
> PowerShell SDK は単に、PowerShell を構成し、PowerShell での .NET の開発に使用できる、すべてのコンポーネント パッケージを示すものです。

特定の `Microsoft.Powershell.SDK` バージョンには、同じバージョンの PowerShell アプリケーションの具象実装が含まれています。バージョン 7.0 には、PowerShell 7.0 の実装が含まれており、それを使用してコマンドまたはスクリプトを実行すると、PowerShell 7.0 で実行する場合とほとんど同じ動作になります。

SDK から PowerShell コマンドを実行することは、`pwsh` から実行する場合とほとんど同じですが、まったく同じではありません。 たとえば、[Start-Job][] は現在、使用可能な `pwsh` 実行可能ファイルに依存しているため、既定では `Microsoft.Powershell.SDK` と連動しません。

.NET アプリケーションから `Microsoft.Powershell.SDK` をターゲットとして設定することで、`System.Management.Automation`、`Microsoft.PowerShell.Management`、およびその他のモジュール アセンブリなど、PowerShell のすべての実装アセンブリと統合できます。

`Microsoft.Powershell.SDK` をターゲットとするアプリケーションの公開には、これらのすべてのアセンブリと、PowerShell に必要なすべての依存関係が含まれます。 また、`Microsoft.PowerShell.*` モジュールのモジュール マニフェストや、[Add-Type][] で必要な `ref` ディレクトリなど、PowerShell でそのビルドに必要だった他のアセットも含まれます。

`Microsoft.Powershell.SDK` の完全性を考えると、次の場合に最適です。

- PowerShell ホストの実装。
- PowerShell 参照アセンブリをターゲットとするライブラリの xUnit テスト。
- .NET アプリケーションからの PowerShell のインプロセス呼び出し。

`Microsoft.PowerShell.SDK` を参照ターゲットとして使用することもできます。その場合、.NET プロジェクトがモジュールとして使用されるか、PowerShell によって読み込まれることが意図されますが、特定のバージョンの PowerShell にのみ存在する API に依存します。 特定のバージョンの `Microsoft.PowerShell.SDK` に対して公開されたアセンブリは、そのバージョンの PowerShell でのみ、安全に読み込んで使用できることにご注意ください。 特定の API を使用して複数の PowerShell バージョンをターゲットにするには、複数のビルドが必要であり、それぞれが独自のバージョンの `Microsoft.Powershell.SDK` をターゲットとします。

> [!NOTE]
> PowerShell SDK は、PowerShell バージョン 6 以上でのみ使用できます。 Windows PowerShell と同等の機能を提供するには、以下に説明する Windows PowerShell 参照アセンブリを使用します。

## <a name="systemmanagementautomation"></a>System.Management.Automation

`System.Management.Automation` パッケージは、PowerShell SDK の中核となるものです。 これは主に、プルする `Microsoft.Powershell.SDK` のアセットとして NuGet に存在します。 しかし、小規模なホスティング シナリオやバージョンをターゲットとするモジュールのパッケージとして直接使用することもできます。

具体的には、次のような場合に、PowerShell 機能を提供するのに `System.Management.Automation` パッケージが適していることがあります。

- PowerShell パーサー、AST、AST ビジター API (たとえば、PowerShell の静的分析用) などの PowerShell 言語機能のみを (`System.Management.Automation.Language` 名前空間で) 使用しようとしている。
- `Microsoft.PowerShell.Core` モジュールから特定のコマンドのみを実行したいと考えており、[CreateDefault2][] ファクトリ メソッドで作成されたセッション状態で実行することができる。

また、`System.Management.Automation` は、次の場合に便利な参照アセンブリです。

- 特定の PowerShell バージョン内にのみ存在する API をターゲットにしたい
- `System.Management.Automation` アセンブリの外部で発生する型 (たとえば、`Microsoft.PowerShell.*` モジュールのコマンドレットによってエクスポートされた型) には依存しない。

## <a name="windows-powershell-reference-assemblies"></a>Windows PowerShell 参照アセンブリ

PowerShell バージョン 5.1 以前 (Windows PowerShell) では、Windows PowerShell の実装は Windows の一部であるため、PowerShell の実装を提供する SDK はありません。

代わりに、Windows PowerShell 参照アセンブリでは、参照ターゲットと、Windows PowerShell を再ホストする方法の両方が提供されます。これは、バージョン 6 以上での PowerShell SDK の場合と同じように動作します。

Windows PowerShell 参照アセンブリには、バージョンで区別されるのではなく、Windows PowerShell のバージョンごとに異なるパッケージがあります。

- [PowerShell 5.1](https://www.nuget.org/packages/Microsoft.PowerShell.5.ReferenceAssemblies/)
- [PowerShell 4](https://www.nuget.org/packages/Microsoft.PowerShell.4.ReferenceAssemblies/)
- [PowerShell 3](https://www.nuget.org/packages/Microsoft.PowerShell.3.ReferenceAssemblies/)

Windows PowerShell 参照アセンブリの使用方法については、[Windows PowerShell SDK][] に関するページを参照してください。

## <a name="real-world-examples-using-these-nuget-packages"></a>これらの NuGet パッケージを使用した実際の例

異なる PowerShell ツール プロジェクトでは、それぞれのニーズに応じて異なる PowerShell NuGet パッケージがターゲットとなります。 いくつかの注目すべき例の一覧を以下に示します。

### <a name="psreadline"></a>PSReadLine

[PSReadLine][] は、PowerShell の豊富なコンソール エクスペリエンスの多くを提供する PowerShell モジュールであり、特定の PowerShell バージョンではなく、依存関係として PowerShell Standard をターゲットとし、その [csproj][] の `net461` .NET ランタイムをターゲットとします。

PowerShell 6 以降では独自の shim アセンブリが提供されます。これを使用すれば、`net461` ランタイムをターゲットとする DLL を、(.NET Framework の `mscorlib.dll` へのバインドを関連する .NET Core アセンブリにリダイレクトすることによって) 読み込まれたときに "のみ動作" させることができます。

これにより、PSReadLine のモジュール レイアウトと配信が大幅に簡素化されます。これは、PowerShell Standard により、使用される API のみが PowerShell 5.1 と PowerShell 6 以降の両方に存在することが保証されるだけでなく、単一のアセンブリのみにモジュールを同梱できるためです。

.NET 4.6.1 ターゲットは、.NET 4.5.2 と .NET 4.6 で実行されている Windows PowerShell がサポートされないことを意味します。

### <a name="powershell-editor-services"></a>PowerShell エディター サービス

[PowerShell エディター サービス][] (PSES) は、[Visual Studio Code][] 用の [PowerShell の拡張機能][]のバックエンドです。実際には、PowerShell モジュールの一種であり、PowerShell 実行可能ファイルによって読み込まれ、そのプロセスを引き継いでそれ自体の中に PowerShell を再ホストし、同時に言語サービス プロトコルとデバッグ アダプターの機能も提供します。

PSES によって、PowerShell 6 以降がターゲットとされる場合は `netcoreapp2.1` (PowerShell 7 の `netcoreapp3.1` ランタイムは下位互換性があるため)、Windows PowerShell 5.1 がターゲットとされる場合は `net461` の具象実装ターゲットが提供されますが、そのロジックのほとんどは、`netstandard2.0` と PowerShell Standard をターゲットとする 2 番目のアセンブリに含まれています。 これにより、.NET Core と .NET Framework プラットフォームに必要な依存関係をプルしながら、統一された抽象化の背後にあるコードベースのほとんどを簡略化できます。

PSES は PowerShell Standard に対してビルドされているため、正しくテストするには PowerShell のランタイム実装が必要です。 これを行うには、テスト環境で PowerShell 実装を提供するために、[PSES の xUnit][] テストで `Microsoft.PowerShell.SDK` および `Microsoft.PowerShell.5.ReferenceAssemblies` をプルします。

PSReadLine と同様に、PSES により .NET 4.6 以下はサポートされませんが、下位の .NET Framework ランタイムでクラッシュする可能性がある API のいずれかを呼び出す前に、実行時に[チェックが実行されます][]。

### <a name="psscriptanalyzer"></a>PSScriptAnalyzer

PowerShell のリンターである、[PSScriptAnalyzer][] では、特定のバージョンの PowerShell で導入された構文要素のみをターゲットにする必要があります。 これらの構文要素の認識は [AstVisitor2][] を実装することによって行われるため、PowerShellStandard を使用したり、また、新しい PowerShell 構文用に AST ビジター メソッドを実装したりすることはできません。

代わりに、PSScriptAnalyzer では、ビルド構成として[各 PowerShell バージョンをターゲットとします][]。また、それぞれに対して個別の DLL を生成します。 これにより、ビルドのサイズと複雑さが増しますが、次のことが可能になります。

- バージョン固有の API ターゲット設定
- 基本的にランタイム コストなしでのバージョン固有の機能の実装
- .NET Framework 4.5.2 に至るまでの Windows PowerShell の全面サポート

## <a name="summary"></a>まとめ

この記事では、PowerShell を使用する .NET プロジェクトを実装するときにターゲットとして使用可能な NuGet パッケージと、一方を他方より優先して使用する理由を一覧にして説明しました。

まとめまでスキップした場合、次のような広範な推奨事項がいくつかあります。

- PowerShell **モジュール**は、異なる PowerShell バージョンに共通する API のみが必要な場合、PowerShell Standard に対してコンパイルする必要があります。
- PowerShell を内部的に実行する必要がある PowerShell の**ホストとアプリケーション**では、PowerShell 6 以降用の PowerShell SDK、または Windows PowerShell 用の関連する Windows PowerShell 参照アセンブリをターゲットにする必要があります。
- **バージョン固有の API** を必要とする PowerShell モジュールでは、必要な PowerShell バージョン用の PowerShell SDK または Windows PowerShell 参照アセンブリをターゲットにする必要があります。これらは参照アセンブリとして使用されます (つまり、PowerShell の依存関係は公開されません)。

<!--link references -->

[.NET Standard 2.0]: /dotnet/standard/net-standard
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[Add-Type]: /powershell/module/microsoft.powershell.utility/add-type
[AstVisitor2]: /dotnet/api/system.management.automation.language.astvisitor2
[CmdletProvider]: /dotnet/api/system.management.automation.provider.cmdletprovider
[CreateDefault2]: /dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2
[csproj]: https://github.com/PowerShell/PSReadLine/blob/master/PSReadLine/PSReadLine.csproj
[Microsoft.PowerShell.SDK]: https://www.nuget.org/packages/Microsoft.PowerShell.SDK/
[NETStandard.Library]: https://www.nuget.org/packages/NETStandard.Library/
[NuGet]: https://www.nuget.org/
[チェックが実行されます]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/src/PowerShellEditorServices.Hosting/EditorServicesLoader.cs#L231-L251
[Pester]: https://github.com/Pester/Pester
[PowerShell エディター サービス]: https://github.com/PowerShell/PowerShellEditorServices/
[PowerShell の拡張機能]: https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[PowerShell NuGet]: https://www.nuget.org/packages/PowerShell/
[PowerShell Standard リポジトリ]: https://github.com/PowerShell/PowerShellStandard
[PowerShellStandard.Library]: https://www.nuget.org/packages/PowerShellStandard.Library/
[PSCmdlet]: /dotnet/api/system.management.automation.pscmdlet
[PSES の xUnit]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/test/PowerShellEditorServices.Test/PowerShellEditorServices.Test.csproj#L15-L20
[PSHost]: /dotnet/api/system.management.automation.host.pshost
[PrivateAssets 属性]: /dotnet/core/tools/csproj#packagereference
[PSReadLine]: https://github.com/PowerShell/PSReadLine
[PSScriptAnalyzer]: https://github.com/powershell/psscriptanalyzer
[参照アセンブリ]: https://github.com/dotnet/standard/blob/master/docs/history/evolution-of-design-time-assemblies.md#definitions
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[System.Management.Automation]: https://www.nuget.org/packages/System.Management.Automation/
[各 PowerShell バージョンをターゲットとします]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/Engine/Engine.csproj
[こちらのブログ記事]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
[Visual Studio Code]: https://code.visualstudio.com/
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell

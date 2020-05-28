---
ms.date: 05/22/2020
keywords: powershell,コマンドレット
title: PowerShell とは
ms.openlocfilehash: 267b2938a0892c99c3a961bc7107f573df40a683
ms.sourcegitcommit: 38215ad49e237b219e62bb5a5f0eb3b6b048df1e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "83868481"
---
# <a name="what-is-powershell"></a>PowerShell とは

PowerShell は、コマンドライン シェルとスクリプト言語で構成される、クロスプラットフォームのタスク自動化および構成管理フレームワークです。 .NET の共通言語ランタイム (CLR) を基に構築されている PowerShell は、テキストを受け取ってテキストを返す多くのシェルとは異なり、.NET オブジェクトを受け取って返します。 この根本的な変更により、自動化のためのまったく新しいツールと方法になっています。

<!-- removing images until we can get replacements
:::row:::
   :::column span="":::
      Windows
      [![PowerShell on Windows](media/overview/windows-desktop-660.gif)](media/overview/windows-desktop.gif#lightbox)
      [Install on Windows](install/installing-powershell-core-on-windows.md)
   :::column-end:::
   :::column span="":::
      Linux
      [![PowerShell on Linux](media/overview/linux-desktop-660.gif)](media/overview/linux-desktop.gif#lightbox)
      [Install on Linux](install/installing-powershell-core-on-linux.md)
   :::column-end:::
   :::column span="":::
      macOS
      [![PowerShell on macOS](media/overview/macos-desktop-660.gif)](media/overview/macos-desktop.gif#lightbox)
      [Install on macOS](install/installing-powershell-core-on-macos.md)
   :::column-end:::
:::row-end:::
-->

## <a name="output-is-object-based"></a>オブジェクト ベースの出力

従来のコマンドライン インターフェイスとは異なり、 PowerShell コマンドレットは、オブジェクトを扱うように設計されています。
オブジェクトは、画面上に表示される文字による単なる文字列ではない、より詳細な構造化された情報です。 コマンドの実行結果は、常に補足的な情報と共に出力され、必要に応じてこの情報を活用できます。

テキスト処理ツールを使用して過去のデータを処理すると、PowerShell で使用された場合とは異なる動作になることがわかるでしょう。 ほとんどの場合、テキスト処理ツールを使用して特定の情報を抽出する必要はありません。 標準の PowerShell オブジェクト構文を使用して、データの一部に直接アクセスします。

## <a name="the-command-family-is-extensible"></a>拡張可能なコマンド ファミリ

`cmd.exe` などのインターフェイスには、組み込みのコマンド セットを直接拡張する手段がありません。 `cmd.exe` 内で実行される外部のコマンドライン ツールを作成する必要があります。 しかし、これらの外部ツールには、ヘルプの統合などのサービスがありません。 `cmd.exe` は、これらの外部ツールが有効なコマンドであることを自動認識しません。

PowerShell のコマンドは_コマンドレット_と呼ばれています。 各コマンドレットは個別に使用することもできますが、組み合わせて使い複雑なタスクを実行すると、その力を実感できます。 多くのシェルと同じように、PowerShell ではコンピューター上のファイル システムにアクセスできます。 PowerShell の_プロバイダー_を使うと、レジストリや証明書ストアなどのその他のデータ ストアに、ファイル システムとほぼ同様に簡単にアクセスできるようになります。

コンパイル済みのコードまたはスクリプトを使用すると、あなた独自のコマンドレットや関数モジュールを作成できます。 モジュールは、シェルにコマンドレットとプロバイダーを追加できます。 また、PowerShell では、UNIX のシェル スクリプトや `cmd.exe` のバッチ ファイルに似たスクリプトもサポートしています。

## <a name="support-for-command-aliases"></a>コマンドのエイリアスをサポートします

PowerShell では、代替名でコマンドを参照するエイリアスをサポートしています。 エイリアスがあることで、他のシェルの経験があるユーザーは、既に知っている一般的なコマンド名を PowerShell のほぼ同じ操作に利用できます。

エイリアスは、新しい名前を別のコマンドに関連付けます。 たとえば、PowerShell には、出力ウィンドウをクリアする `Clear-Host` という内部関数があります。 コマンド プロンプトに `cls` または `clear` エイリアスのどちらかを入力できます。 PowerShell はこれらのエイリアスを解釈して、`Clear-Host` 関数を実行します。

この機能は、ユーザーが PowerShell を習得するうえで役立ちます。 まず、ほとんどの `cmd.exe` および Unix ユーザーは、既に名前は知っている多数のコマンドのレパートリーを持っています。 同等の PowerShell のコマンドでは、同一の結果が得られない場合があります。 しかし、十分に近い結果になるので、PowerShell のコマンド名を知らなくてもユーザーが既知のコマンドを利用することは可能です。 新しいコマンド シェルを習得する上でのもう 1 つの主なストレス要因は、"身体が覚えている" ことです。 長年にわたって `cmd.exe` を使用してきた場合、画面をクリアするのに、反射的に `cls` コマンドを入力してしまうでしょう。 `Clear-Host` のエイリアスがなければ、エラー メッセージを受け取ってしまい、出力をクリアするにはどうすればいいかわからないでしょう。

## <a name="powershell-handles-console-input-and-display"></a>PowerShell によってコンソールの入力と表示が処理される

コマンドを入力すると、常に、コマンドラインの入力が PowerShell によって直接処理されます。 また、PowerShell では、出力を画面上で確認できるように書式設定します。 各コマンドレットで必要な作業が減るため、これは大きな差になります。 どのコマンドレットでも常に同じように作業できることが、保証されます。 コマンドレットの開発者は、コマンドライン引数の解析や出力形式の設定のために、コードを記述する必要はありません。

従来のコマンドライン ツールでは、ヘルプの要求と表示に独自の体系が採用されていました。 一部のコマンドライン ツールでは、`/?` を使用してヘルプを表示します。他では、`-?`、`/H`、または `//` を使用します。 ヘルプがコンソール画面に表示される代わりに、GUI のウィンドウに表示されるものもあります。 間違ったパラメーターを使用すると、入力内容が無視され、タスクの実行が自動的に開始される場合もあります。
PowerShell はコマンドラインを自動的に解析して処理するため、`-?` パラメーターは常に "このコマンドのヘルプを表示する" ことを意味します。

> [!NOTE]
> PowerShell でグラフィック アプリケーションを実行した場合は、そのアプリケーションのウィンドウが開きます。
> PowerShell が介在するのは、ユーザーによって指定されたコマンドライン入力を処理するときと、コンソール ウィンドウに返されたアプリケーション出力を処理するときだけです。 アプリケーション内部の動作には影響しません。

## <a name="powershell-has-a-pipeline"></a>PowerShell にはパイプラインがある

パイプラインは、コマンドライン インターフェイスで使用される最も重要な概念と言っても過言ではありません。 パイプラインは、適切に利用すれば、複雑なコマンドを使用する負荷を軽減し、より簡単に作業フローを確認できます。 パイプライン内の各コマンドは、項目ごとに次のコマンドに出力を渡します。 コマンドでは、一度に複数の項目を処理する必要がなくなります。 結果として、リソース使用量が減り、出力をすぐに取得できるようになります。

パイプラインで使用される表記は、他のシェルで使用される表記とほぼ同じです。 PowerShell でのパイプラインの違いは、一目見ただけではわかりにくいかもしれません。 画面にはテキストが表示されますが、PowerShell は、コマンド間ではテキストではなくオブジェクトを受け渡します。

たとえば、`Out-Host` コマンドレットを使用して、別のコマンドからの出力をページ単位で表示させると、通常のテキストがページごとに分割されて画面上に表示されているだけのように見えます。

```powershell
Get-ChildItem | Out-Host -Paging
```

```Output
    Directory: /mnt/c/Git/PS-Docs/PowerShell-Docs/reference/7.0/Microsoft.PowerShell.Core

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          05/22/2020    08:30                About
-----          05/20/2020    14:36           9044 Add-History.md
-----          05/20/2020    14:36          12227 Clear-History.md
-----          05/20/2020    14:36           3566 Clear-Host.md
-----          05/20/2020    14:36          29087 Connect-PSSession.md
-----          05/20/2020    14:36           5705 Debug-Job.md
-----          05/20/2020    14:36           3515 Disable-ExperimentalFeature.md
-----          05/20/2020    14:36          25531 Disable-PSRemoting.md
-----          05/20/2020    14:36           7852 Disable-PSSessionConfiguration.md
-----          05/20/2020    14:36          25355 Disconnect-PSSession.md
-----          05/20/2020    14:36           3491 Enable-ExperimentalFeature.md
-----          05/20/2020    14:36          13310 Enable-PSRemoting.md
-----          05/20/2020    14:36           8401 Enable-PSSessionConfiguration.md
-----          05/20/2020    14:36           9531 Enter-PSHostProcess.md
...
<SPACE> next page; <CR> next line; Q quit
```

また、表示する完全なページが準備できると、`Out-Host` コマンドレットに処理が転送されるため、ページングによって CPU 使用率が低下します。 パイプライン内で先行するコマンドレットは、次のページの出力が利用可能になるまで、実行を一時停止します。

### <a name="objects-in-the-pipeline"></a>パイプライン内のオブジェクト

PowerShell でコマンドレットを実行した場合、コンソール ウィンドウではオブジェクトをテキストで表す必要があるため、テキストが表示されます。 テキスト出力では、出力されるオブジェクトのすべてのプロパティが必ず表示されるわけではありません。

たとえば、`Get-Location` コマンドレットについて考えてみます。 テキストの出力は情報の要約であり、`Get-Location` から返されたオブジェクトの完全な表現ではありません。 出力の見出しは、画面の表示用にデータを書式設定する処理によって、追加されます。

```powershell
Get-Location
```

```Output
Path
----
C:\
```

出力を `Get-Member` コマンドレットにパイプ処理すると、`Get-Location` から返されたオブジェクトに関する情報が表示されます。

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

`Get-Location` は、現在のパスとその他の情報を含む **PathInfo** オブジェクトを返します。

## <a name="built-in-help-system"></a>組み込みのヘルプ システム

PowerShell には、Unix の `man` ページと似た PowerShell の概念とコマンド構文を詳細に説明するヘルプ記事があります。 [Get-Help][] コマンドレットを使用すると、これらの記事をコマンド プロンプトで表示できます。PowerShell ドキュメント オンラインでは、これらの記事の最新版を参照できます。

## <a name="next-steps"></a>次のステップ

PowerShell の詳細については、このサイトの「**PowerShell の習得**」のセクションを参照してください。

<!-- link references -->

[Get-Help]: /powershell/module/microsoft.powershell.core/Get-Help

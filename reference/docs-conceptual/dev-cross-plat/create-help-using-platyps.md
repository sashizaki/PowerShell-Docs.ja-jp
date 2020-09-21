---
title: PlatyPS を使用して XML ベースのヘルプを作成する
description: PlatyPS の使用は、XML ベースのヘルプを作成するための高速で効率的な方法です。
ms.date: 07/21/2020
ms.openlocfilehash: 79cf8c077a07bf1e7aa8ea1ea799be5f8d4af12c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972584"
---
# <a name="create-xml-based-help-using-platyps"></a>PlatyPS を使用して XML ベースのヘルプを作成する

PowerShell モジュールを作成するときは、作成するコマンドレットの詳細なヘルプを必ず含めることをお勧めします。 コンパイル済みのコードにコマンドレットが実装されている場合は、XML ベースのヘルプを使用する必要があります。 この XML 形式は、Microsoft Assistance Markup Language (MAML) と呼ばれています。

従来の PowerShell SDK のドキュメントでは、モジュールにパッケージ化された PowerShell コマンドレットのヘルプを作成する方法の詳細について説明しています。 ただし、PowerShell には、XML ベースのヘルプを作成するためのツールは用意されていません。 SDK ドキュメントでは、MAML ヘルプの構造について説明していますが、複雑で深く入れ子になった MAML コンテンツを作成するタスクは手動で行う必要があります。

ここで [PlatyPS][] モジュールが役に立ちます。

## <a name="what-is-platyps"></a>PlatyPS とは

PlatyPS は、MAML の作成とメンテナンスを容易にするために "_ハッカソン_" プロジェクトとして始まった、[オープンソース][platyps-repo]のツールです。 PlatyPS を使用すると、ご自身のモジュール内の各コマンドレットについて、パラメーター セットの構文と個々のパラメーターを文書化できます。 PlatyPS によって、構文情報を含む構造化された[マークダウン][] ファイルが作成されます。 説明が作成されたり、例が提供されたりすることはありません。

PlatyPS によって、説明と例を入力するためのプレースホルダーが作成されます。 必要な情報を追加した後、PlatyPS でマークダウン ファイルを MAML ファイルにコンパイルします。 PowerShell のヘルプ システムでは、プレーンテキストの概念説明ヘルプ ファイル (about トピック) も使用できます。 PlatyPS には、新しい _about_ ファイル用の構造化された Markdown テンプレートを作成するためのコマンドレットがありますが、これらの `about_*.help.txt` ファイルは手動でメンテナンスする必要があります。

モジュールには、MAML とテキストのヘルプ ファイルを含めることができます。 PlatyPS を使用して、ヘルプ ファイルを CAB パッケージにコンパイルし、更新可能なヘルプ用にホストすることもできます。

## <a name="get-started-using-platyps"></a>PlatyPS を使用して開始する

まず、PowerShell ギャラリーから PlatyPS をインストールする必要があります。

```powershell
Install-Module platyps -Force
Import-Module platyps
```

次のフローチャートは、PowerShell のリファレンス コンテンツを作成または更新するプロセスの概要を示しています。

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="PlatyPS を使用して XML ベースのヘルプを作成するためのワークフロー":::

##  <a name="create-markdown-content-for-a-powershell-module"></a>PowerShell モジュールの Markdown コンテンツを作成する

1. 新しいモジュールをセッションにインポートします。 文書化する必要があるモジュールごとに、この手順を繰り返します。

   次のコマンドを実行してモジュールをインポートします。

   ```powershell
   Import-Module <your module name>
   ```

1. PlatyPS を使用して、モジュール ページのマークダウン ファイルと、モジュール内の関連するすべてのコマンドレットを生成します。 文書化する必要があるモジュールごとに、この手順を繰り返します。

   ```powershell
   $OutputFolder = <output path>
   $parameters = @{
       Module = <ModuleName>
       OutputFolder = $OutputFolder
       AlphabeticParamsOrder = $true
       WithModulePage = $true
       ExcludeDontShow = $true
       Encoding = 'UTF8BOM'
   }
   New-MarkdownHelp @parameters

   New-MarkdownAboutHelp -OutputFolder $OutputFolder -AboutName "topic_name"
   ```

   出力フォルダーが存在しない場合は、`New-MarkdownHelp` によって作成されます。 この例では、`New-MarkdownHelp` によって、モジュール内のコマンドレットごとにマークダウン ファイルが作成されます。 また、`<ModuleName>.md` という名前のファイル内に "_モジュール ページ_" も作成されます。 このモジュール ページには、モジュールに含まれるコマンドレットの一覧と、**概要**説明のプレースホルダーが含まれています。 モジュール ページのメタデータは、モジュール マニフェストから取得され、PlatyPS で HelpInfo XML ファイルを作成するために使用されます ([以下](#creating-an-updateable-help-package)を参照)。

   `New-MarkdownAboutHelp` によって、`about_topic_name.md` という名前の _about_ ファイルが作成されます。

   詳細については、「[New-MarkdownHelp][]」と「[New-MarkdownAboutHelp][]」を参照してください。

### <a name="update-existing-markdown-content-when-the-module-changes"></a>モジュールを変更したときに既存の Markdown コンテンツを更新する

PlatyPS を使用して、モジュールの既存のマークダウン ファイルを更新することもできます。 この手順は、新しいコマンドレット、新しいパラメーター、または変更されたパラメーターを持つ既存のモジュールを更新するために使用します。

1. 新しいモジュールをセッションにインポートします。 文書化する必要があるモジュールごとに、この手順を繰り返します。

   次のコマンドを実行してモジュールをインポートします。

   ```powershell
   Import-Module <your module name>
   ```

1. PlatyPS を使用して、モジュールのランディング ページのマークダウン ファイルと、モジュール内のすべての関連コマンドレットを更新します。 文書化する必要があるモジュールごとに、この手順を繰り返します。

   ```powershell
   $parameters = @{
       Path = <folder with Markdown>
       RefreshModulePage = $true
       AlphabeticParamsOrder = $true
       UpdateInputOutput = $true
       ExcludeDontShow = $true
       LogPath = <path to store log file>
       Encoding = 'UTF8BOM'
   }
   Update-MarkdownHelpModule @parameters
   ```

   `Update-MarkdownHelpModule` によって、指定したフォルダー内のコマンドレットとモジュールのマークダウン ファイルが更新されます。
   `about_*.md` ファイルは更新されません。 モジュール ファイル (`ModuleName.md`) に、コマンドレット ファイルに追加された新しい**概要**のテキストが渡されます。 コマンドレット ファイルの更新には、次の変更が含まれます。

   - 新しいパラメーター セット
   - 新しいパラメーター
   - 更新されたパラメーターのメタデータ
   - 更新された入力および出力の種類の情報

   詳細については、「[Update-MarkdownHelpModule][]」を参照してください。

## <a name="edit-the-new-or-updated-markdown-files"></a>新しいまたは更新されたマークダウン ファイルを編集する

PlatyPS によって、パラメーター セットの構文と個々のパラメーターが文書化されます。 説明が作成されたり、例が提供されたりすることはありません。 コンテンツが必要な特定の領域は、中かっこ内に含まれています。 例: `{{ Fill in the Description }}`

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="VS Code にプレースホルダーが表示されている Markdown テンプレート":::

概要、コマンドレットの説明、各パラメーターの説明、および少なくとも 1 つの例を追加する必要があります。

PowerShell コンテンツの記述の詳細については、次の記事を参照してください。

- [PowerShell のスタイル ガイド](/powershell/scripting/community/contributing/powershell-style-guide)
- [参照記事の編集](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> PlatyPS には、コマンドレット リファレンスに使用する特定のスキーマがあります。 そのスキーマでは、ドキュメントの特定のセクションの特定の Markdown ブロックのみが許可されます。 コンテンツを間違った場所に配置すると、PlatyPS のビルド ステップは失敗します。 詳細については、PlatyPS リポジトリにある[スキーマ][]のドキュメントを参照してください。 整形式のコマンドレット リファレンスの完全な例については、「[Get-Item][]」を参照してください。

各コマンドレットに必要なコンテンツを指定したら、モジュールのランディング ページを必ず更新する必要があります。 `<module-name>.md` ファイル内の YAML メタデータでモジュールの `Module Guid` と `Download Help Link` の値が正しいことを確認します。 不足しているメタデータがあれば追加します。

また、一部のコマンドレットに**概要** (_短い説明_) がないことに気付く場合もあります。 次のコマンドを実行すると、モジュールのランディング ページが**概要**説明のテキストで更新されます。 モジュールのランディング ページを開いて、説明を確認します。

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

すべてのコンテンツを入力したので、PowerShell コンソールで `Get-Help` によって表示される MAML ヘルプ ファイルを作成できます。

## <a name="create-the-external-help-files"></a>外部ヘルプ ファイルを作成する

この手順では、PowerShell コンソールで `Get-Help` によって表示される MAML ヘルプ ファイルを作成します。

MAML ファイルをビルドするには、次のコマンドを実行します。

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

`New-ExternalHelp` によって、すべてのコマンドレット マークダウン ファイルが 1 つ以上の MAML ファイルに変換されます。 概要ファイルは、`about_topic_name.help.txt` という形式の名前を持つプレーンテキスト ファイルに変換されます。
Markdown コンテンツは、PlatyPS スキーマの要件を満たしている必要があります。 コンテンツがスキーマに従っていない場合、`New-ExternalHelp` はエラーで終了します。 ファイルを編集してスキーマ違反を修正する必要があります。

> [!CAUTION]
> PlatyPS は、`about_*.md` ファイルのプレーンテキストへの変換には適していません。 許容できる結果を得るには、非常に単純な Markdown を使用する必要があります。 ファイルを PlatyPS で変換するのではなく、プレーンテキストの `about_topic_name.help.txt` 形式のままにすることも検討してください。

この手順が完了すると、出力先フォルダーに `*-help.xml` と `about_*.help.txt` ファイルが表示されます。

詳細については、「[New-ExternalHelp][]」を参照してください。

### <a name="test-the-compiled-help-files"></a>コンパイル済みヘルプ ファイルをテストする

[Get-HelpPreview][] コマンドレットを使用して、コンテンツを確認できます。

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

このコマンドレットによって、コンパイルされた MAML ファイルが読み取られ、`Get-Help` から返されるのと同じ形式でコンテンツが出力されます。 これにより、結果を検査して、マークダウン ファイルが正しくコンパイルされていて必要な結果が生成されることを確認できます。 エラーが見つかった場合は、マークダウン ファイルを再編集して MAML を再コンパイルします。

これで、ヘルプ ファイルを公開する準備ができました。

## <a name="publishing-your-help"></a>ヘルプを公開する

これでマークダウン ファイルが PowerShell ヘルプ ファイルにコンパイルされたので、ファイルをユーザーが使用できるようにすることができます。 PowerShell コンソールでヘルプを提供するには、2 つのオプションがあります。

- ヘルプ ファイルをモジュールと共にパッケージ化する
- `Update-Help` コマンドレットを使用して、ユーザーがインストールする更新可能なヘルプ パッケージを作成する

### <a name="packaging-help-with-the-module"></a>ヘルプをモジュールと共にパッケージ化する

ヘルプ ファイルは、モジュールと共にパッケージ化することができます。 フォルダー構造の詳細については、[モジュールのヘルプの記述][]に関するページを参照してください。 モジュール マニフェストの **FileList** キーの値にヘルプ ファイルのリストを含める必要があります。

### <a name="creating-an-updateable-help-package"></a>更新可能なヘルプ パッケージを作成する

更新可能なヘルプを作成する手順は大まかに次のとおりです。

1. ヘルプ ファイルをホストするインターネット サイトを検索する
1. **HelpInfoURI** キーをモジュール マニフェストに追加する
1. HelpInfo XML ファイルを作成する
1. CAB ファイルを作成する
1. ファイルをアップロードする

詳細については、[更新可能なヘルプのサポート: ステップバイステップ][step-by-step]に関するページを参照してください。

PlatyPS によって、これらの手順の一部が支援されます。

**HelpInfoURI** は、ヘルプ ファイルがインターネット上でホストされている場所を指す URL です。 モジュール マニフェスト内にこの値を構成します。 `Update-Help` によって、モジュール マニフェストが読み取られ、この URL が取得されて、更新可能なヘルプ コンテンツがダウンロードされます。 この URL は、個別のファイルではなく、フォルダーの場所のみを指している必要があります。 `Update-Help` を使用すると、モジュール マニフェストと HelpInfo XML ファイルにあるその他の情報に基づいて、ダウンロードするファイル名を構築できます。

> [!IMPORTANT]
> **HelpInfoURI** は、スラッシュ (`/`) で終わる必要があります。 この文字がない場合、`Update-Help` によって、コンテンツをダウンロードするための正しいファイル パスが作成されません。 また、ほとんどの HTTP ベースのファイル サービスでは大文字と小文字が区別されます。 HelpInfo XML ファイル内のモジュール メタデータでは、大文字と小文字を適切に区別した文字が含まれていることが重要です。

`New-ExternalHelp` コマンドレットによって、HelpInfo XML ファイルが出力フォルダーに作成されます。 HelpInfo XML ファイルは、モジュールのマークダウン ファイル (`ModuleName.md`) に含まれている YAML メタデータを使用して構築されます。

`New-ExternalHelpCab` コマンドレットによって、コンパイルした MAML ファイルと `about_*.help.txt` ファイルを含む ZIP ファイルと CAB ファイルが作成されます。 CAB ファイルは、PowerShell のすべてのバージョンと互換性があります。
PowerShell 6 以降では、ZIP ファイルを使用できます。

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

ZIP ファイルと CAB ファイルを作成した後、ZIP、CAB、および HelpInfo XML ファイルを HTTP ファイル サーバーにアップロードします。 **HelpInfoURI** によって示されている場所にファイルを配置します。

詳細については、「[New-ExternalHelpCab][]」を参照してください。

### <a name="other-publishing-options"></a>その他の公開オプション

Markdown は、公開するために他の形式に簡単に変換できる、汎用性のある形式です。 [Pandoc][] などのツールを使用すると、Markdown のヘルプ ファイルを、プレーンテキスト、HTML、PDF、Office ドキュメント形式などのさまざまなドキュメント形式に変換できます。

また、PowerShell 6 以降では、コマンドレット [ConvertFrom-Markdown][] と [Show-Markdown][] を使用して、Markdown を HTML に変換したり、PowerShell コンソールにカラフルな表示を作成したりすることができます。

## <a name="known-issues"></a>既知の問題

PlatyPS は、作成およびコンパイルするマークダウン ファイルの構造の[スキーマ][]が非常に厳密に認識されます。 有効な Markdown を記述し、それがこのスキーマに違反していることがよくあります。 詳細については、[PowerShell のスタイル ガイド][]に関するページと「[参照記事の編集][]」を参照してください。

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[schema]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[PowerShell のスタイル ガイド]: /powershell/scripting/community/contributing/powershell-style-guide
[参照記事の編集]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[モジュールのヘルプの記述]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown

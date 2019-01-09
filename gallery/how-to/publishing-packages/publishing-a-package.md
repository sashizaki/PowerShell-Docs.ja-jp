---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: アイテムの作成と公開
ms.openlocfilehash: 70696535a3bf540ff75a2dc43bca80cb1adf8f45
ms.sourcegitcommit: 9df29dfc637191b62ca591893c251c1e02d4eb4c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54012536"
---
# <a name="creating-and-publishing-an-item"></a>アイテムの作成と公開

PowerShell ギャラリーとは、広範な PowerShell ユーザー コミュニティを通じて、安定した PowerShell モジュール、スクリプト、および DSC リソースを公開および共有する場所です。

この記事では、スクリプトまたはモジュールを準備して PowerShell ギャラリーに公開するまでの仕組みと重要な手順について説明します。 [公開ガイドライン](../../concepts/publishing-guidelines.md)を確認して、公開したアイテムがより多くの PowerShell ギャラリー ユーザーに受け入れられるようにする方法を理解しておくことを強くお勧めします。

アイテムを PowerShell ギャラリーに公開するための最小要件は以下の通りです。

- PowerShell ギャラリー アカウントを持っていて、API キーが関連付けられている
- 必要なメタデータがアイテムに含まれていることを確認する
- 事前検証ツールを使用して、アイテムが公開できる状態であることを確認する
- Publish-Module コマンドおよび Publish-Script コマンドを使用して、アイテムを PowerShell ギャラリーに公開する
- 質問やアイテムに関する懸念事項への対応

PowerShell ギャラリーは、PowerShell モジュールおよび PowerShell スクリプトを受け入れます。 ここでスクリプトとは、大規模モジュールの一部ではなく、1 つのファイルである PowerShell スクリプトを意味しています。

## <a name="powershell-gallery-account-and-api-key"></a>PowerShell ギャラリー アカウントと API キー

PowerShell ギャラリー アカウントの設定方法については、「[Creating a PowerShell Gallery Account (PowerShell ギャラリー アカウントを作成する)](/powershell/gallery/how-to/publishing-packages/creating-an-account)」をご覧ください。

アカウントを作成したら、アイテムの公開に必要な API キーを取得できます。 アカウントでサインインすると、PowerShell ギャラリー ページの上部で [Register]\(登録\) の代わりにユーザー名が表示されます。 ユーザー名をクリックすると、[My Account]\(マイ アカウント\) ページに移動します。そこで API キーを確認できます。

注: API キーは、ログインとパスワードとして安全に処理する必要があります。
このキーを使用すると、PowerShell ギャラリーで所有しているあらゆるアイテムを、自分だけでなく他のユーザーも更新できます。
キーは定期的に更新することをお勧めします。[My Account]\(マイ アカウント\) ページの [Reset Key]\(キーをリセットする\) を使用して更新できます。

## <a name="required-metadata-for-items-published-to-the-powershell-gallery"></a>PowerShell ギャラリーで公開するアイテムに必要なメタデータ

PowerShell ギャラリーでは、スクリプトまたはモジュールのマニフェストに含まれているメタデータ フィールドから抽出した情報を、ギャラリーのユーザーに提供します。 PowerShell ギャラリーに公開するアイテムを作成または変更するには、アイテムのマニフェストに含める情報についていくつかの要件があります。
[公開ガイドライン](../../concepts/publishing-guidelines.md)のアイテム メタデータに関するセクションを確認して、アイテムを使ってユーザーに対して最適な情報を提供する方法を理解することを強くお勧めします。

[New-ModuleManifest](/powershell/module/microsoft.powershell.core/new-modulemanifest) および [New-ScriptFileInfo](/powershell/module/PowerShellGet/New-ScriptFileInfo) コマンドレットは、すべてのマニフェスト要素のプレースホルダーが用意されたマニフェスト テンプレートを作成します。

両方のマニフェストでは、PrivateData の主キー データと PSData エリアを発行するために重要な 2 つのセクションがあります。 PowerShell モジュールのマニフェストで主キー データは、PrivateData セクション外のすべてです。 主キーのセットは、使用している PowerShell のバージョンに関連付けられており、未定義はサポートされません。 PrivateData は新しいキーの追加をサポートしているので、PowerShell ギャラリーに固有の要素は PSData にあります。


PowerShell ギャラリーに公開するアイテムについて提供する最も重要なマニフェスト要素は次のとおりです。

- スクリプト名またはモジュール名 - これらは、スクリプトの .PS1 の名前、またはモジュールの .PSD1 の名前から取得されます。
- バージョン - これは、必須の主キー、形式は SemVer ガイドラインに従う必要があります。 詳細については、ベスト プラクティスを参照してください。
- 作成者 - これは必須の主キーと項目に関連する名前が含まれています。
作成者と所有者は以下を参照してください。
- 説明 - これは必須の主キーで、このアイテムの実行内容と使用にあたっての要件を簡単に説明するのに使用します。
- ProjectURI - これは強くお勧めする PSData 内の URI フィールドで、アイテムの開発を行う Github リポジトリや同様の場所へのリンクを提供します。
- タグの PSEditions とプラットフォームとの互換性に基づくパッケージのタグを付けるための強力な推奨事項になります。 詳細については、次を参照してください。、[発行のガイドライン](../../concepts/publishing-guidelines.md#tag-your-package-with-the-compatible-pseditions-and-platforms)します。

PowerShell ギャラリーでは、アイテムの作成者と所有者は関連する概念ですが、常に一致するわけではありません。 アイテムの所有者とは、PowerShell ギャラリー アカウントを持ち、アイテムを管理するアクセス許可を有するユーザーです。 アイテムを更新できる所有者が多数いることもあります。 所有者は PowerShell ギャラリーからのみ使用されるもので、アイテムがあるシステムから別のシステムにコピーされると失われます。 作成者は、マニフェスト データに組み込まれている文字列のため、常にアイテムに含まれます。 Microsoft 製品からのアイテムに関する推奨事項は次のとおりです。

- 複数の所有者を設定し、そのうち少なくとも 1 つは、そのアイテムを作成するチームの名前にする。
- 作成者は、よく知られているチーム名 (Azure SDK チームなど) または Microsoft Corporation とする。


## <a name="pre-validate-your-item"></a>アイテムを事前検証する

PowerShell ギャラリーにアイテムを公開する前に、コードに対して実行する必要があるツールがいくつかあります。

- PowerShell ギャラリー内にある [PowerShell Script Analyzer](https://www.powershellgallery.com/packages/PSScriptAnalyzer/)
- モジュールには、PowerShell の一部である Test-ModuleManifest
- スクリプトには、PowerShell Get に付属している Test-ScriptFileInfo

[PowerShell Script Analyzer](https://www.powershellgallery.com/packages/PSScriptAnalyzer/) は静的コード分析ツールで、コードをスキャンして、PowerShell のコーディングの基本的なガイドラインを満たしていることを確認します。 このツールはコードに含まれる一般的で重大な問題を特定するもので、アイテムを公開できるようにするために、開発中に定期的に実行する必要があります。 PowerShell Script Analyzer は、エラー、警告、および情報として特定した問題を一覧で提供します。 エラーはすべて、PowerShell ギャラリーに公開する前に対処する必要があります。 警告は確認する必要があり、大半を処理する必要があります。 PowerShell Script Analyzer は、PowerShell ギャラリーでアイテムが公開または更新されるたびに実行されます。 ギャラリー運用チームは、エラーが検出されると対処のためにアイテムの所有者に連絡します。

アイテムに含まれるマニフェスト情報が PowerShell ギャラリー インフラストラクチャで読み取れない場合、公開することはできません。
[Test-ModuleManifest](/powershell/module/microsoft.powershell.core/test-modulemanifest) は、インストールするとそのモジュールが使用できなくなるような、一般的な問題を検出します。 これはすべてのモジュールについて、PowerShell ギャラリーに公開する前に実行する必要があります。

同様に、[Test-ScriptFileInfo](/powershell/module/PowerShellGet/test-scriptfileinfo) はスクリプトに含まれるメタデータを検証するもので、すべてのスクリプト (モジュールとは別に公開された) で、PowerShell ギャラリーに公開する前に実行する必要があります。


## <a name="publishing-items"></a>アイテムを公開する

PowerShell ギャラリーにアイテムを公開するには、[Publish-Script](/powershell/module/PowerShellGet/publish-script) または [Publish-Module](/powershell/module/PowerShellGet/publish-module) を使用する必要があります。 これらのコマンドは、どちらも以下が必要です。

- 公開するアイテムへのパス。 モジュールの場合、モジュールの名前が付いたフォルダーを使用します。 同じモジュールの複数のバージョンを含むフォルダーを指定する場合は、RequiredVersion を指定する必要があります。
- Nuget API キー。 これは、PowerShell ギャラリーの [My Account]\(マイ アカウント\)ページにある API キーです。

コマンド ラインのその他のオプションは、そのほとんどが公開するアイテムのマニフェスト データに含まれるので、コマンドで指定する必要はありません。

エラーを回避するには、公開の前に、-Whatif -Verbose を使用してコマンドを実行することを強くお勧めします。 これによって、かなりの時間を節約することができます。PowerShell ギャラリーに公開するたびに、アイテムのマニフェスト セクションでバージョン番号を更新する必要があるからです。

例は次のようになります。

* `Publish-Module -Path ".\MyModule" -NugetAPIKey "GUID" -Whatif -Verbose`
* `Publish-Script -Path ".\MyScriptFile.PS1" -NugetAPIKey "GUID" -Whatif -Verbose`

出力を注意深く確認し、エラーや警告がない場合は、-Whatif を付けずにコマンドを再実行します。

PowerShell ギャラリーに公開されるすべてのアイテムは、ウイルスのスキャンが行われ、PowerShell Script Analyzer を使用して分析されます。 その時点で発生した問題は、解決するよう公開者に送り返されます。

PowerShell ギャラリーにアイテムを公開したら、アイテムに関するフィードバックがないか注視する必要があります。

- 公開に使用したアカウントに関連付けられている電子メール アドレスをチェックするようにします。 ユーザーおよび PowerShell ギャラリー オペレーション チームは、そのアカウントを使用して、フィードバックや、PowerShell Script Analyzer またはウイルス対策スキャンからの問題を提供します。 [使用条件](https://www.powershellgallery.com/policies/Terms)に記載されているように、電子メール アカウントが無効である、または、アカウントに深刻な問題が報告されたのに長期間にわたり未解決のままである場合は、アイテムは放棄されたとみなされ、PowerShell ギャラリーから削除されます。
- 公開した PowerShell ギャラリー アイテムの各々について、コメントをサブスクライブすることをお勧めします。 こうすると、PowerShell ギャラリーのアイテムに誰かがコメントしたときに通知されます。 LiveFyre でアカウントを作成する必要があるため、この設定はオプションです。

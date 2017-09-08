---
ms.date: 2017-06-12
contributor: JKeithB
ms.topic: conceptual
keywords: "ギャラリー, PowerShell, コマンドレット, PSGallery"
description: "パブリッシャー向けのガイドライン"
title: "PowerShell ギャラリーへの公開に関するガイドラインとベスト プラクティス"
ms.openlocfilehash: 85486c409382472420a67fc124bd07a30486cb62
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
# <a name="powershellgallery-publishing-guidelines-and-best-practices"></a>PowerShell ギャラリーへの公開に関するガイドラインとベスト プラクティス

このトピックでは、PowerShell ギャラリーでのマニフェスト データの処理方法に基づいて、また多数の PowerShell ギャラリー ユーザーからのフィードバックに基づいて、PowerShell ギャラリーに公開したアイテムがユーザーに広く受け入れられ、高い価値をもたらすことができるように、Microsoft チームが行っている推奨の手順をご説明します。
このガイドラインに従ってアイテムを公開すると、そのアイテムは信用されてインストールされやすくなるとともに、より多くのユーザーに興味を持ってもらうことができます。

PowerShell ギャラリーの良質なアイテムを作成する上で大事なこと、オプションのマニフェスト設定で最も重要なこと、初期のレビュー担当者や [PowerShell Script Analyzer](https://aka.ms/psscriptanalyzer) からのフィードバックに基づいたコードの改善、モジュールのバージョン管理、ドキュメント、共有済みアイテムのテストと使用方法のサンプルなどに関するガイドラインを以下に示します。
このドキュメントの大部分は、[高品質な DSC リソース モジュール](https://github.com/PowerShell/DscResources/blob/master/HighQualityModuleGuidelines.md)を公開するためのガイドラインを基にしています。

PowerShell ギャラリーへのアイテムの公開の仕組みについては、「[アイテムの作成と公開](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/creating-and-publishing-an-item)」をご覧ください。

このガイドラインについてのフィードバックをお寄せください。 フィードバックをお送りいただく場合は、Microsoft の [GitHub ドキュメント リポジトリ](https://github.com/powershell/powershell-docs/) で Issue を作成してください。

## <a name="best-practices-for-publishing-items"></a>アイテムの公開に関するベスト プラクティス

以下に、PowerShell ギャラリーのアイテムのユーザーが重要と考えるベスト プラクティスを、名目上の優先度順に並べて示します。
アイテムは、以下のガイドラインに準拠していると、ユーザーにダウンロードされ使用される可能性がかなり高くなります。

* PSScriptAnalyzer を使用する
* ドキュメントとサンプルを含める
* フィードバックに素早く対応する
* スクリプトではなくモジュールを提供する
* バージョン管理に関する SemVer ガイドラインに従う
* プロジェクト サイトへのリンクを提供する
* モジュールにテストを含める
* ライセンス条項を含めるか、ライセンス条項へのリンクを提供する (またはその両方)
* コードに署名する
* バージョン管理に関する SemVer ガイドラインに従う
* 一般的な PowerShell ギャラリー タグに関する記事で説明されている一般的なタグを使用する
* ローカル リポジトリを使用して公開に関するテストを行う

これらのベスト プラクティスのそれぞれについて、以下のセクションで簡単に説明します。

## <a name="use-psscriptanalyzer"></a>PSScriptAnalyzer を使用する

[PSScriptAnalyzer](https://www.powershellgallery.com/packages/PSScriptAnalyzer) は、PowerShell コードに対応した無料の静的コード分析ツールです。
PSScriptAnalyzer では PowerShell のコードで頻繁に見られる問題が特定され、多くの場合、問題の推奨解決方法も示されます。
このツールの使用は簡単であり、問題はエラー (重大であり対処が必須)、警告 (確認が必要であり対処した方がよい)、情報 (ベスト プラクティスの観点からチェックに値する) に分類されます。
PowerShell ギャラリーに公開したアイテムはすべて PSScriptAnalyzer によりスキャンされます。エラーがある場合には所有者に報告されるので、対処を行ってください。

`-Recurse` と `-Severity` として警告を指定して、`Invoke-ScriptAnalyzer` を実行することをお勧めします。

結果を確認して以下を行います。

* すべてのエラーを修正するか、ドキュメントに記載する
* すべての警告を確認し、必要に応じて対処する

PowerShell ギャラリーからアイテムを取得したユーザーには、PSScriptAnalyzer を実行してすべてのエラーと警告を確認することが強く推奨されています。
PSScriptAnalyzer でエラーが報告された場合、おそらくユーザーはアイテムの所有者に問い合わせるでしょう。
エラーのフラグが付けられているアイテムのコードをそのままにしておかなければならない理由がある場合は、その旨をドキュメントに追加することで、同じ質問を何度も受けるのを回避できます。

## <a name="include-documentation-and-examples"></a>ドキュメントとサンプルを含める

ユーザーに共有コードを確実に活用してもらう一番の方法は、ドキュメントとサンプルを用意することです。

ドキュメントは、PowerShell ギャラリーに公開するアイテムに含めておくと非常に役立ちます。
アイテムにドキュメントが含まれていない場合、アイテムの中身と使用方法を理解するには代わりにコードを読まなければならないため、ほとんどのユーザーに敬遠されてしまいます。
PowerShell のアイテムと合わせてドキュメントを提供する方法に関する次のような記事が MSDN に掲載されています。

* 「[How to Write Cmdlet Help (コマンドレット ヘルプの書き方)](https://go.microsoft.com/fwlink/?LinkID=123415)」内のヘルプの提供に関するガイドライン
* コマンドレット ヘルプの作成。コマンドレット ヘルプは、すべての PowerShell スクリプト、関数、コマンドレットを理解するために最適な手段です。
  コマンドレット ヘルプの作成方法の詳細については、まず MSDN ライブラリの「[How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415)」 (コマンドレット ヘルプの書き方) をご覧ください。
  スクリプト内にヘルプを追加する方法については、「[About Comment Based Help (コメント ベースのヘルプの概要)](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_comment_based_help)」をご覧ください。
* また、多くのモジュールには、テキスト形式のドキュメント (MarkDown ファイルなど) が含まれています。
  MarkDown 形式が頻繁に使用されている GitHub にプロジェクト サイトを設置する場合、この方法は特に役立ちます。
  [GitHub 用の Markdown](https://help.github.com/categories/writing-on-github/) を使用することをお勧めします。

サンプルでは、アイテムの用途をユーザーに説明します。
多くの開発者は、使用方法を確認する場合、ドキュメントの前にサンプルを見ると述べています。
基本的な使い方に加えて実際の使用例のシミュレーションを示し、コードに適切なコメントを付けると最適なサンプルになります。
PowerShell ギャラリーに公開するモジュールのサンプルは、モジュールのルートの下の Examples フォルダーに配置することをお勧めします。

サンプルの推奨パターンは、[PSDscResource モジュール](https://www.powershellgallery.com/packages/PSDscResources) の Examples\RegistryResource フォルダーにあります。
各ファイルの冒頭には、4 つのサンプルの使用例とともに、サンプルの内容を示す簡単な説明が記載されています。

## <a name="respond-to-feedback"></a>フィードバックに対応する

アイテム所有者としてフィードバックに適切に対応すると、コミュニティでの評価が高くなります。
建設的なフィードバックを提供してくれるユーザーは、アイテムに高い関心を持っており改善の手助けをしてくれますので、必ず対応しましょう。

PowerShell ギャラリーでフィードバックを行う方法は 2 つあります。

* 所有者への連絡: この方法では、ユーザーはアイテムの所有者にメールを送信できます。 アイテムの所有者は、PowerShell ギャラリーアイテムで使用しているメール アドレスをチェックし、寄せられた問題に対応することが推奨されます。 この方法の 1 つのデメリットは、問い合わせをしたユーザーと所有者しか会話を見られないため、所有者は同じ質問に何度も答えなければならない可能性があることです。
* コメント: アイテムのページの最下部には [Comment]\(コメント\) フィールドがあります。
  この方法のメリットは、他のユーザーもコメントと回答を確認できるため、同一の質問に答えなければならない回数を少なくできることです。
  アイテムの所有者には、各アイテムに寄せられたコメントを Follow (フォロー) することが強く推奨されます。
フォロー方法の詳細については、「[Providing Feedback via Social Media or Comments (ソーシャル メディアやコメントを使用したフィードバックの提供)](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/psgallery-SocialMediaFeedback)」をご覧ください。

フィードバックに建設的に対応すると、コミュニティで高い評価を得られます。
この報告の機会を利用して、必要に応じて詳細情報を求めたり、回避策を提示したり、更新によって問題が修正されるかどうかを確認したりしましょう。

これらの連絡方法のいずれかで不適切な振る舞いが見られた場合には、PowerShell ギャラリーの Report Abuse (迷惑行為の報告) 機能を使用して、ギャラリーの管理者に連絡してください。

## <a name="modules-versus-scripts"></a>モジュールとスクリプト

他のユーザーとのスクリプトの共有は便利であり、生じる可能性のある問題の解決方法の例を提示できます。
問題は、PowerShell ギャラリーではスクリプトは単一のファイルとなり、個別のドキュメントやサンプル、テストを提供できないことです。

PowerShell モジュールはフォルダー構造となっており、複数のフォルダーやファイルをパッケージ内に含めることができます。
こうしたモジュールの構造であれば、ベスト プラクティスとして示したコマンドレット ヘルプ、ドキュメント、サンプル、テストなどのアイテムも含めることができます。
最大のデメリットは、モジュール内のスクリプトを公開し関数として使用する必要があることです。
モジュールの作成方法については、「[Writing a Windows PowerShell Module (Windows PowerShell モジュールの作成)](http://go.microsoft.com/fwlink/?LinkId=144916)」をご覧ください。

特に DSC 構成などで、スクリプトを提供すると、ユーザー エクスペリエンスを改善できる場合があります。
DSC 構成のベスト プラクティスとして、ドキュメント、サンプル、テストが含まれる付属モジュールと合わせて、構成をスクリプトとして公開することをお勧めします。
このスクリプトには、RequiredModules = @(モジュール名) 形式で付随モジュールの一覧を記載します。
この方法はどのようなスクリプトでも使用できます。

スタンドアロン スクリプトの場合、その他のベスト プラクティスに従うことで別のユーザーに大きな価値を提供できます。
スクリプトを PowerShell ギャラリーに公開する場合、コメント ベースのドキュメントとプロジェクト サイトへのリンクを提供することが強く推奨されます。

## <a name="provide-a-link-to-a-project-site"></a>プロジェクト サイトへのリンクを提供する

プロジェクト サイトは、パブリッシャーとパブリッシャーの PowerShell ギャラリー アイテムのユーザーが直接やりとりできる場所です。
プロジェクト サイトではアイテムの情報をより簡単に得られるため、このサイトを備えたアイテムの方がユーザーに選ばれやすくなります。
PowerShell ギャラリーのアイテムの多くは GitHub で開発されていますが、専用の Web サイトを持つ組織が提供しているものもあります。
こうしたサイトのそれぞれがプロジェクト サイトとなります。

リンクを追加するには、次のようにマニフェストの PSData セクションに ProjectURI を記載します。

        # A URL to the main website for this project.
        ProjectUri = 'https://github.com/powershell/powershell'

ProjectURI が記載されている場合、PowerShell ギャラリーではアイテム ページの左側にプロジェクト サイトへのリンクが表示されます。

## <a name="include-tests"></a>テストを含める

オープンソースのコードにテストを含めると、検証内容を保証できるとともに、コードの仕組みに関する情報を提供できるため、ユーザーにとって非常に役立ちます。 また、ユーザーはコードを自分の環境に合わせて変更した場合でも元の機能が損なわれないことをテストによって確認できます。

テストは、PowerShell 専用に設計された Pester テスト フレームワークを使用して作成することを強くお勧めします。
Pester は [GitHub](https://github.com/Pester/Pester) と [PowerShell ギャラリー](https://www.powershellgallery.com/packages/Pester/)で入手できます。また、Windows 10、Windows Server 2016、WMF 5.0、WMF 5.1 に同梱されています。

[GitHub の Pester のプロジェクト サイト](https://github.com/Pester/Pester)では、概要を始めベスト プラクティスに至るまで、Pester でのテストの作成方法が詳しく説明されています。

テスト範囲の目標値は[高品質のリソース モジュール](https://github.com/PowerShell/DscResources/blob/master/HighQualityModuleGuidelines.md)に関するドキュメントに記載されており、単体テストでのコード カバレッジの推奨値は 70% です。

## <a name="include-andor-link-to-license-terms"></a>ライセンス条項を含めるか、ライセンス条項へのリンクを提供する (またはその両方)

PowerShell ギャラリーに公開するすべてのアイテムについて、ライセンス条項を指定するか、「[Terms of Use (使用条件)](https://www.powershellgallery.com/policies/Terms)」の「Exhibit A (別紙 A)」に記載されているライセンスで拘束する必要があります。
別のライセンスを指定する最適な方法は、PSData の LicenseURI を利用してライセンスへのリンクを提供することです。
サンプルは、推奨されるマニフェスト フィールドに関するトピックに記載されています。

```powershell
PrivateData = @{
    PSData = @{

        # Tags applied to this module. These help with module discovery in online galleries.
        Tags = @('.net','acl','active-directory')

        # A URL to the license for this module.
        LicenseUri = 'http://www.apache.org/licenses/LICENSE-2.0'
```

## <a name="sign-your-code"></a>コードに署名する

コードに署名することで、アイテムの公開者について、またユーザーが取得したコードのコピーは公開者が公開したものに間違いないということを、ユーザーに対して最も確実に保証できます。
コードへの一般的な署名方法の詳細については、「[Introduction to Code Signing (コード署名の概要)](http://go.microsoft.com/fwlink/?LinkId=106296)」をご覧ください。
PowerShell では、コード署名について 2 つの主な検証方法がサポートされています。

* スクリプト ファイルへの署名
* モジュールへのカタログ署名

PowerShell ファイルに署名することで、実行するコードが信頼できる作成元で作成されており、変更されていないことを確実に保証できます。
PowerShell スクリプト ファイルへの署名方法の詳細については、「[About Signing (署名について)](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_signing)」をご覧ください。
署名はすべての .PS1 ファイルに追加することができ、スクリプトのロード時に PowerShell により検証されます。
[実行ポリシー](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/about/about_execution_policies) コマンドレットを使用して、署名済みのスクリプトのみが使用されるように PowerShell を制限できます。

モジュールへのカタログ署名は、バージョン 5.1 で PowerShell に追加された機能です。
モジュールへの署名方法については、「[カタログ コマンドレット](https://msdn.microsoft.com/en-us/powershell/wmf/5.1/catalog-cmdlets)」をご覧ください。
カタログ署名は、モジュール内の全ファイルのハッシュ値を含むカタログ ファイルを作成してそのファイルに署名することで行います。
PowerShellGet の publish-module、install-module、save-module、update-module の各コマンドレットにより、署名が有効であることがチェックされ、各アイテムのハッシュ値がカタログに記載されているものと一致するか確認されます。
システムに旧バージョンのモジュールがインストールされている場合、新バージョンの署名機関がインストール済みのものと一致することが install-module によって確認されます。
カタログ署名は、スクリプト ファイルへの署名と併用できますが、代わりになるものではありません。 PowerShell では、モジュールのロード時にカタログ署名の検証は行われません。

## <a name="follow-semver-guidelines-for-versioning"></a>バージョン管理に関する SemVer ガイドラインに従う

[SemVer](http://semver.org/) は、変更内容を簡単に判別できるようにする、バージョンの構造化と変更の方法を定めた一般的な規則です。
マニフェスト データには、アイテムのバージョンを含める必要があります。

* バージョンは 0.1.1 や 4.11.192 のように、3 つの数字ブロックをピリオドで区切って構造化する
* "0" から始まるバージョンはアイテムがまだ運用環境に対応していないことを示す。先頭の数字のみを使用する場合は、"0" から始める必要がある
* 先頭の数字の変更 (1.9.9999 から 2.0.0) は、バージョン間で重大な変更が行われたことを示す
* 2 番目の数字の変更 (1.01 から 1.02) は、モジュールへの新しいコマンドレットの追加など、機能レベルでの変更を示す
* 3 番目の数字の変更は、パラメーターの新規追加、サンプルの更新、テストの新規追加など、小規模な変更を示す
* バージョンを一覧化すると、PowerShell ではバージョンは文字列として並び替えられるため、1.01.0 は 1.001.0 より大きいものと扱われる

PowerShell は SemVer の公開前に作成されたため、SemVer の大半の要素をサポートしてはいますが、以下のようにサポートされていない要素もあります。

* バージョン番号のプレリリース文字列はサポートされません。 プレリリース文字列は、パブリッシャーがバージョン 1.0.0 の提供後に新しいメジャー バージョンを提供したい場合に役立ちます。 この文字列は、PowerShell ギャラリーと PowerShellGet コマンドレットの今後のリリースでサポートされます。
* PowerShell と PowerShell ギャラリーでは、数字ブロックが 1 つ、2 つ、4 つのバージョン文字列を使用できます。 初期のモジュールの多くは SemVer ガイドラインに従っていませんでした。また Microsoft からの製品リリースでは、ビルド情報が 4 番目の数字ブロックとして含められています (例: 5.1.14393.1066)。 バージョン管理の観点では、こうした違いは無視できます。

## <a name="test-using-a-local-repository"></a>ローカル リポジトリを使用してテストする

PowerShell ギャラリーは、公開プロセスのテストの対象となっていません。
PowerShell ギャラリーへのエンドツーエンドの公開プロセスをテストする最良の方法は、独自のローカル リポジトリを設定して使用することです。
これは、次のいくつかの方法で行うことができます。

* Github で [PS プライベート ギャラリー プロジェクト](https://github.com/PowerShell/PSPrivateGallery)を使用して、PowerShell ギャラリーのローカル インスタンスを設定します。 このプレビュー プロジェクトでは、制御可能でありテスト対象である PowerShell ギャラリーのインスタンスを容易に設定することができます。
* [Nuget 内部リポジトリ](https://blogs.msdn.microsoft.com/powershell/2014/05/20/setting-up-an-internal-powershellget-repository/)を設定します。 これには追加の設定作業が必要です。ただし、利点として、API キーの使用を検証したり、公開時にターゲット内に依存関係が存在するかどうかを検証したりするなど、追加の要件をいくつか検証することができます。
* ファイル共有をテスト "リポジトリ" として設定します。 この設定は簡単ですが、ファイル共有であるため、上記の検証は行われません。 この場合の潜在的な利点の 1 つは、ファイル共有で (必須の) API キーが確認されないため、PowerShell ギャラリーに公開するのと同じキーを使用できるということです。

これらのソリューションでは、Register-PSRepository を使用して、新しい "リポジトリ" を定義します。これは、Publish-Module の -Repository プロパティで使用します。

テストの公開に関する追加のポイント: PowerShell ギャラリーに公開したアイテムはオペレーション チームの支援がなければ、削除できません。オペレーション チームは、公開するアイテムに何も依存していないことを確認します。
そのため、弊社では PowerShell ギャラリーをテストの対象としてサポートしておらず、テストを行っている公開元に問い合わせします。

## <a name="recommended-workflow"></a>推奨ワークフロー

PowerShell ギャラリーにアイテムを公開する上で最も効果的と考えられる方法を次に示します。

* 初期の開発はオープンソースのプロジェクト サイトで行う。 PowerShell チームでは Github を使用しています。
* レビュー担当者と [PowerShell Script Analyzer](https://aka.ms/psscriptanalyzer) からのフィードバックを活用してコードを安定化させる
* 他のユーザーがアイテムの使用方法を知ることができるようにドキュメントを含める
* ローカル リポジトリを使用して公開動作をテストします。
* PowerShell ギャラリーには安定版またはアルファ リリースを公開し、必ずドキュメントとプロジェクト サイトへのリンクを記載する
* プロジェクト サイトでフィードバックを集めてコードを反復開発し、安定した更新版を PowerShell ギャラリーに公開する
* プロジェクトとモジュールにサンプルと Pester テストを追加する
* アイテムのコード署名を行うかどうかを決定する
* プロジェクトが運用環境で使用できるようになったと思われる場合は、1.0.0 バージョンを PowerShell ギャラリーに公開する
* 引き続きフィードバックを収集し、ユーザーの意見に基づいてコードを反復開発する

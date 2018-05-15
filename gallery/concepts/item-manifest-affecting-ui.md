---
ms.date: 06/09/2017
schema: 2.0.0
keywords: powershell
title: PowerShell ギャラリー UI に影響を与えるアイテム マニフェストの値
ms.openlocfilehash: 39522396b179c54b981e6292cddacec27b32506c
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="item-manifest-values-that-impact-the-powershell-gallery-ui"></a>PowerShell ギャラリー UI に影響を与えるアイテム マニフェストの値

このトピックでは、マニフェストを PowerShell ギャラリー公開用に変更し、PowerShellGet コマンドレットの機能や PowerShell ギャラリー UI に反映させる方法の概要を発行者向けに説明します。
このコンテンツは、変更が表示される場所ごとに編成されており、中央のセクションから始まり、その後左側のナビゲーション領域に移動します。 タグについて説明する詳細セクションがあり、そこでは重要なタグやよく使用されるタグの一部を紹介します。
マニフェストの例を示す次の 2 つのトピックがあります。

- モジュールについては、[モジュール マニフェストの更新](https://docs.microsoft.com/powershell/gallery/psget/module/psget_update-modulemanifest)に関するトピックをご覧ください。
- スクリプトについては、[メタデータを持つスクリプト ファイルの作成](https://docs.microsoft.com/powershell/gallery/psget/script/psget_new-scriptfileinfo)に関するトピックをご覧ください。

## <a name="powershell-gallery-feature-elements-controlled-by-the-manifest"></a>マニフェストによって制御される PowerShell ギャラリー機能の要素

次の表に、公開者によって制御される PowerShell ギャラリー アイテム ページの UI 要素を示します。
UI 要素がモジュール マニフェストによって制御されるか、スクリプト マニフェストによって制御されるかを項目ごとに表示しています。

| UI 要素 | 説明 | モジュール | スクリプト |
| --- | --- | --- | --- |
| **タイトル** | ギャラリーに公開されるアイテムの名前です  | いいえ | いいえ |
| **バージョン** | 表示されるバージョンはメタデータ内のバージョン文字列で、指定されている場合、プレリリースです。 モジュール マニフェストでのバージョンの基本部分は、ModuleVersion です。 スクリプトの場合、.VERSION として指定されます。 プレリリース バージョンの文字列が指定されている場合、その文字列は、モジュールでは ModuleVersion に追加され、スクリプトでは .VERSION の一部として指定されます。 [モジュール](https://docs.microsoft.com/en-us/powershell/gallery/psget/module/prereleasemodule)や[スクリプト](https://docs.microsoft.com/en-us/powershell/gallery/psget/script/prereleasescript)でプレリリースの文字列を指定するためのドキュメントがあります。 | 可 | 可 |
| **説明** | モジュール マニフェストでの説明です。スクリプト ファイル マニフェストでは .DESCRIPTION となります。 | 可 | 可 |
| **ライセンス同意リクエスト** | モジュールはユーザーのライセンス同意をリクエストできます。そのためには、モジュール マニフェストを RequireLicenseAcceptance = $true に変更し、LicenseURI を指定し、モジュール フォルダーのルートに license.txt ファイルを置きます。 詳細な情報については、「[ライセンス同意リクエスト](https://docs.microsoft.com/en-us/powershell/gallery/psgallery/psgallery_requires_license_acceptance)」のトピックで説明しています。 | 可 | いいえ |
| **リリース ノート** | モジュールの場合、この情報は PSData\PrivateData の ReleaseNotes セクションから取得されます。 スクリプト マニフェストでは、.RELEASENOTES 要素です。 | 可 | 可 |
| **所有者** | 所有者は、アイテムを更新できる PowerShell ギャラリー内のユーザーの一覧です。 アイテム マニフェストには、所有者の一覧は含まれていません。 他のドキュメントで、[アイテムの所有者を管理する](https://docs.microsoft.com/en-us/powershell/gallery/psgallery/managing-item-owners)方法について説明しています。 | いいえ | いいえ |
| **作成者** | これは、モジュール マニフェストに作成者として指定されます。スクリプト マニフェストでは .AUTHOR として指定されます。 [作成者] フィールドは、アイテムに関連する会社や組織を指定する場合によく使用されます。 | 可 | 可 |
| **著作権** | モジュール マニフェストの [著作権] フィールドです。スクリプト マニフェストでは .COPYRIGHT です。 | 可 | 可 |
| **FileList** | PowerShell ギャラリーへの公開時に、パッケージからこのファイル一覧が取得されます。 マニフェストの情報で制御することはできません。 注: PowerShell ギャラリーで各アイテムと共に表示される追加の .nuspec ファイルがあります。これは、システムにアイテムをインストールした後には存在しません。 これはアイテムの Nuget パッケージ マニフェストであり、無視してかまいません。 | いいえ | いいえ |
| **タグ** | モジュールの場合、タグは PSData\PrivateData に置かれています。 スクリプトの場合は、このセクションは .TAGS とラベル付けされています。 タグにはスペースを含めることはできません。タグを引用符で囲っても同様です。 タグには詳細な要件と意味があります。これについては、このトピックの後半の「タグの詳細」セクションで説明します。 | 可 | 可 |
| **コマンドレット** | モジュール マニフェストの CmdletsToExport で指定されます。 ワイルドカード “*” を使用せずに項目を明示的に表示すると、ユーザーのロードモジュール パフォーマンスが向上するため、この方法が推奨されます。 | 可 | いいえ |
| **関数** | モジュール マニフェストの FunctionsToExport で指定されます。 ワイルドカード “*” を使用せずに項目を明示的に表示すると、ユーザーのロードモジュール パフォーマンスが向上するため、この方法が推奨されます。 | 可 | いいえ |
| **DSC リソース** | PowerShell バージョン 5.0 以降で使用されるモジュールの場合、これはマニフェストの DscResourcesToExport で指定されます。 モジュールが PowerShell 4 で使用される場合には、DSCResourcesToExport はサポート対象外のマニフェスト キーであるため、使用できません  (PowerShell 4 以前には DSC が提供されていませんでした)。 | 可 | いいえ |
| **ワークフロー** | ワークフローは PowerShell ギャラリーにスクリプトとして公開され、コードにワークフローとして指定されます (例については、[Connect-AzureVM](https://www.powershellgallery.com/packages/Connect-AzureVM/1.0/Content/Connect-AzureVM.ps1) に関するページをご覧ください)。 これは、マニフェストによって制御されません。 | いいえ | いいえ |
| **ロール機能** | PowerShell ギャラリーに公開されたモジュールに 1 つ以上のロール機能 (.psrc) ファイルが含まれる場合に表示されます。このファイルは JEA で使用されます。 [ロール機能](https://docs.microsoft.com/en-us/powershell/jea/role-capabilities)の詳細については、JEA のドキュメントをご覧ください。 | 可 | いいえ |
| **PowerShell のエディション** | スクリプト マニフェストまたはモジュール マニフェスト内で指定されます。 PowerShell 5.0 で使用するように設計されたモジュールの場合は、タグを使用して制御されます。 デスクトップの場合には PSEdition_Desktop タグを使用し、コアの場合には PSEdition_Core タグを使用します。 PowerShell 5.1 以降でのみ使用されるモジュールの場合には、メイン マニフェストに CompatiblePSEditions キーが存在します。 詳細については [PowerShell Get のドキュメント](https://docs.microsoft.com/en-us/powershell/gallery/psget/module/modulewithpseditionsupport)で、PS のエディションの機能について確認してください。 | 可 | 可 |
| **依存関係** | 依存関係は、モジュール マニフェストの RequiredModules かスクリプト マニフェストの #Requires –Module (name) のいずれかで宣言される、PowerShell ギャラリー内のモジュールです。 | 可 | 可 |
| **Powershell の最小バージョン** | これは、モジュール マニフェストの PowerShellVersion で指定できます。 | 可 | いいえ |
| **バージョン履歴** | バージョン履歴は、モジュールに加えられた更新を PowerShell ギャラリーに反映します。 削除機能を使用してアイテムのバージョンを非表示にしている場合、アイテムの所有者以外には、アイテムのバージョンはバージョン履歴に表示されません。 | いいえ | いいえ |
| **プロジェクト サイト** | プロジェクト サイトは、モジュールでは ProjectURI を指定することにより、モジュール マニフェストの Privatedata\PSData セクション内で指定されます。 スクリプト マニフェストでは、.PROJECTURI を指定することにより制御されます。 | 可 | 可 |
| **ライセンス** | ライセンス リンクは、モジュールでは LicenseURI を指定することにより、モジュール マニフェストの Privatedata\PSData セクション内で指定されます。 スクリプト マニフェストでは、.LICENSEURI を指定することにより制御されます。 LicenseURI を通してライセンスが指定されていない、またはモジュール内にライセンスが指定されていない場合には、PowerShell ギャラリーの使用条件によってアイテムの使用条件が指定されることに注意する必要があります。 詳細については、使用条件をご覧ください。 | 可 | 可 |

## <a name="editing-item-details"></a>アイテムの詳細の編集

PowerShell ギャラリー アイテム編集ページでは、公開者は表示されるアイテムのフィールドの一部を個別に変更できます。

- Title
- 説明
- 要約
- アイコン URL
- プロジェクト ホーム ページの URL
- 作成者
- 著作権
- タグ
- リリース ノート
- ライセンス リクエスト

この方法は、古いバージョンのモジュールについて表示される内容を修正する必要がある場合以外は、一般的には推奨されません。
モジュールを取得するユーザーに表示されるメタデータは PowerShell ギャラリーに表示される内容と一致しないため、そのアイテムに関する問題が発生します。
その結果、アイテムの所有者に変更について確認する問い合わせが頻繁に発生することになります。
この方法を使用する場合はいつでも、同様に変更された新しいバージョンのアイテムを公開することを強くお勧めします。

## <a name="tag-details"></a>タグの詳細

タグは、利用者がアイテムを探すのに使用する単純な文字列です。
タグは、同じトピックに関連する多くのアイテムで一貫して使用される場合に、最も価値が発揮されます。 同じ語の複数の変化形を使用する場合 (たとえば database と databases、あるいは test と testing など) は、通常メリットはほとんどありません。
タグは、大文字と小文字の区別のない単語の文字列で、空白を含めることはできません。 ユーザーが検索すると思われる語句がある場合には、それをアイテムの説明に追加すると、検索結果に表示されます。 読みやすさを改善する場合は、パスカル ケース、ハイフン、アンダースコア、またはピリオドを使用します。 長くて複雑な珍しいタグを作成すると、スペルミスが多くなるため注意してください。

PowerShell ギャラリーと PowerShellGet コマンドレットが独自に扱うタグがありますので注意が必要です。 PSEdition_Desktop と PSEdition_Core がその具体例で、上記で説明しています。

前述のように、タグは具体的であると同時に多くのアイテムで一貫して使用される場合に、最も価値が発揮されます。
公開者が使用すべき最適なタグを探す場合には、検討しているタグを PowerShell ギャラリーで探すのが最も簡単な方法です。
多数のアイテムが返され、アイテムの説明が対象キーワードの使用方法に合わせて調整されるのが理想的です。

参考に、2017 年 12 月 14 日の時点で最もよく使用されるタグの一部を次に示します。
場合によっては、そのタグと比べて似てはいるが最適とは言えないような候補が表示されることもあります。
お勧めの方法は優先タグを使用することです。そうすると、ノイズが軽減され、利用者にとってより望ましい検索結果が返されます。


| **優先タグ** | **代替タグと注意事項** |
| --- | --- |
| **Azure** |  |
| **DSC** | DesiredStateConfiguration は長すぎるため推奨されません |
| **ResourceManager** | ARM は、プロセッサのグループを表す場合に使用します。Azure Resource Manager には使用しないでください | **DSCResourceKit** |  |
| **SQL** |  |
| **AWS** |  |
| **DSCResource** |  |
| **Automation** |  |
| **REST** |  |
| **ActiveDirectory** | AD はそれ自体が現在使用されていません  |
| **SQLServer** |  |
| **DBA** |  |
| **セキュリティ** | Defense は精度が低くなります |
| **Database** | Databases (複数) は推奨されません |
| **DevOps** |  |
| **Windows** |  |
| **Build** |  |
| **Deployment** | Deploy の使用頻度はやや低めです |
| **Cloud** |  |
| **GIT** |  |
| **Test** | Testing は推奨されません |
| **VersionControl** | Version はこれよりも頻繁に使用されますが、精度が低くなります  |
| **Logging** | Logging はアクションとしての使用が推奨されます |
| **Log** | Log は物としての使用が推奨されます |
| **Backup** |  |
| **IaaS** |  |
| **Linux** |  |
| **IIS** |  |
| **AzureAutomation** |  |
| **Storage** |  |
| **GitHub** |  |
| **Json** |  |
| **Exchange** |  |
| **Network** | Networking も同様ですが、使用頻度は低めです |
| **SharePoint** |  |
| **Reporting** | Reporting はアクションで、Report は物です |
| **Report** | Report は物です |
| **WinRM** |  |
| **Monitoring** |  |
| **VSTS** |  |
| **Excel** |  |
| **Google** |  |
| **Color** |  |
| **DNS** |  |
| **Office365** | Office と綴ることをお勧めします。 O365 はこれより短いですが、使用頻度は低めです | **Gitlab** |  |
| **Pester** |  |
| **AzureAD** |  |
| **HTML** |  |
| **Hyper-V** | HyperV は、タグとしてはこれほど一般的ではありません |
| **Configuration** |  |
| **ChatOps** |  |
| **PackageManagement** |  |
| **WMI** |  |
| **Firewall** |  |
| **Docker** |  |
| **Appveyor** |  |
| **AzureRm** | AzureRM モジュールで主に使用されます |
| **Zip** |  |
| **MSI** |  |
| **Mac** |  |
| **PoshBot** |  |
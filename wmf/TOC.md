# [WMF リリース ノートの概要](releasenotes.md)

# [インストールの詳細](requirements.md)

# [製品の互換性の状態](productincompat.md)

# [フィードバック](feedback.md)

# [WMF 5.0 で可能なシナリオ]()
## [Just Enough Administration (JEA)](jea_overview.md)
### [JEA エンドポイントの作成および接続](jea_endpoint.md)
### [JEA のレポート](jea_report.md)

## [PowerShell クラスを使用したカスタム型の作成](class_overview.md)
### [カスタム型の定義](class_newtype.md)
### [基本クラスの宣言](class_base.md)
### [実装されたインターフェイスの宣言](class_interface.md)
### [基本クラス コンストラクターの呼び出し](class_baseconstructor.md)
### [基本クラス メソッドの呼び出し](class_basemethod.md)

## [PowerShell スクリプト デバッグの強化](debug_overview.md)

## [Desired State Configuration (DSC) の機能強化](dsc_improvements.md)
### [構成]()
#### [ノードの相互依存関係の指定](dsc_waitfor.md)
#### [暗号化された MOF](dsc_encryptedmof.md)
#### [DSC 構成に関するヘルプ サポート](dsc_confighelp.md)
#### [PowerShell ISE を使ったオーサリングの強化](dsc_authoring.md)
#### [構成における同一重複リソースの許容](dsc_identicalduplicate.md)
#### [-moduleversion パラメーターをサポートする Import-DscResource キーワード](dsc_importdscresource.md)
#### [構成キーワードの WOW64 サポート](dsc_wow64.md)
### [参照情報]()
#### [クラスベースの DSC リソース](dsc_classbasedresource.md)
#### [DSC リソース スクリプトのデバッグ](dsc_resourcedebugging.md)
#### [DSC リソースの自動 RunAs サポート](dsc_runas.md)
#### [DSC リソースの Side-By-Side バージョン管理サポート](dsc_sxsresource.md)
#### [新しいインボックス リソース](dsc_newresources.md)
### [ローカル構成マネージャー]()
#### [複数の構成フラグメントによるノードの構成](dsc_partialconfig.md)
##### [RefreshMode の混在のサポート](dsc_partialconfig_mixedmode.md)
#### [新しい属性を使用した DSC エンジンの構成](dsc_metaconfiguration.md)
#### [LCM 状態に関する詳細情報](dsc_lcmstate.md)
#### [RefreshMode と ConfigurationMode の出現頻度は互いの倍数である必要はない](dsc_freqnomultiple.md)
#### [RefreshMode プロパティの追加の値](dsc_refreshmode.md)
### [コマンドレット]()
#### [構成状況の詳細](dsc_getconfigurationstatus.md)
#### [Test-DscConfiguration コマンドレットでの参照構成のサポート](dsc_testconfiguration.md)
#### [DSC リソース メソッドへの直接アクセス](dsc_directaccess.md)
#### [適用することなく構成ドキュメントを提供する](dsc_publishconfig.md)
#### [DSC ドキュメントの削除](dsc_removeconfigdoc.md)
#### [統一された一貫性のある状態とステータスの表現](dsc_statestatus.md)
#### [Set-DscLocalConfigurationManager コマンドレットでの -force パラメーターのサポート](dsc_setdsclcm.md)
### [プル モード]()
#### [DSC 構成のオンデマンド プル](dsc_updateconfig.md)
#### [ノード ID と構成 ID の分離](dsc_nodeid.md)
#### [構成、リソース、およびレポートのリポジトリの分離](dsc_repository.md)
#### [構成の状態を中央の場所にレポートする](dsc_reporting.md)

## [トランスクリプトおよびログを使用した PowerShell の使用状況の監査](audit_overview.md)
### [強化されたトランスクリプション オプション](audit_transcript.md)
### [スクリプトのトレースとログ](audit_script.md)
### [Cryptographic Message Syntax (CMS) コマンドレット](audit_cms.md)

## [PackageManagement によるソフトウェアの検出、インストール、およびインベントリ](oneget_overview.md)
### [PackageManagement コマンドレット](oneget_cmdlets.md)

## [PowerShellGet による PowerShell モジュールの検出、インストール、およびインベントリ](psget_module_overview.md)
### [PowerShell リポジトリの登録](psget_psrepository.md)
### [PowerShell 5.0 以降の Side-by-Side バージョン サポート](psget_modulesxsinstall.md)
### [モジュールの依存関係のインストール](psget_moduledependency.md)
### [モジュール管理用の PowerShellGet コマンドレット](psget_modulecmdlets.md)

## [PowerShellGet による PowerShell スクリプトの検出、インストール、および管理](psget_script_overview.md)
### [スクリプト管理用の PowerShellGet コマンドレット](psget_scriptcmdlets.md)

## [コミュニティからのフィードバックに基づいて更新されたコマンドレットと新規コマンドレット ](feedback_cmdlets.md)
### [Item コマンドレットを使用したシンボリック リンク](feedback_symbolic.md)
### [アーカイブのコマンドレット](feedback_archive.md)
### [クリップボードのコマンドレット](feedback_clipboard.md)
### [Convert-String](feedback_convertstring.md)
### [文字列から構造化オブジェクトを抽出して分析する](feedback_convertfromString.md)
### [Format-Hex](feedback_formathex.md)
### [NoNewLine パラメーター](feedback_nonewline.md)
### [New-TemporaryFile](feedback_tempfile.md)
### [New-Guid](feedback_newguid.md)
### [Get-ChildItem の -Depth パラメーター](feedback_getchilditem.md)
### [FileInfo オブジェクトの更新](feedback_fileinfo.md)
### [バージョン範囲 (1. * など) の宣言をサポートするモジュール](feedback_moduleversionranges.md)

## [情報ストリーム](informationstream_overview.md)

## [OData エンドポイントに基づく PowerShell コマンドレットの生成](odata_overview.md)

## [PowerShell を使用したネットワーク スイッチの管理](networkswitch_overview.md)

## [ソフトウェア インベントリ ログ (SIL)](sil_overview.md)

# [既知の問題と制限事項](limitation_overview.md)
## [Desired State Configuration (DSC) の既知の問題](limitation_dsc.md)


<!--HONumber=May16_HO4-->



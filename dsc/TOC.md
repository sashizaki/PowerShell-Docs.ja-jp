# [概要](overview.md)

# [構成](configurations.md)
## [構成の適用](enactingConfigurations.md)
## [複数のバージョンがあるリソースの使用](sxsResource.md)
## [ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)
## [ノードの相互依存関係の指定](crossNodeDependencies.md)
## [構成データ](configData.md)
### [構成データでの資格情報オプション](configDataCredentials.md)
## [構成 MOF ファイルのセキュリティ保護](secureMOF.md)
## [部分構成](partialConfigs.md)
## [DSC 構成のヘルプの作成](configHelp.md)

# [参照情報](resources.md)
## [組み込みリソース](builtInResource.md)
### [アーカイブ リソース](archiveResource.md)
### [環境リソース](environmentResource.md)
### [ファイル リソース](fileResource.md)
### [グループ リソース](groupResource.md)
### [ログ リソース](logResource.md)
### [パッケージ リソース](packageResource.md)
### [レジストリ リソース](registryResource.md)
### [スクリプト リソース](scriptResource.md)
### [サービス リソース](serviceResource.md)
### [[ユーザー リソース]](userResource.md)
### [WindowsFeature リソース](windowsfeatureResource.md)
### [WindowsProcess リソース](windowsProcessResource.md)
## [カスタム リソースの作成](authoringResource.md) 
### [MOF ベースのカスタム リソース](authoringResourceMOF.md)
#### [C 言語での MOF ベースのリソース#](authoringResourceMofCS.md)
### [クラスに基づくカスタム リソース](authoringResourceClass.md)
### [複合リソース](authoringResourceComposite.md)
### [単一インスタンスの DSC リソースを記述する (ベスト プラクティス)](singleInstance.md)
### [リソース作成のチェックリスト](resourceAuthoringChecklist.md)
## [DSC リソースのデバッグ](debugResource.md)
## [DSC リソース メソッドの直接呼び出し](directCallResource.md)

# [ローカル構成マネージャー (LCM) の構成](metaConfig.md)
## [PowerShell 4.0 での LCM の構成](metaConfig4.md)

# DSC プル モデル
## [Web プル サーバーのセットアップ](pullServer.md)
## [DSC SMB プル サーバーのセットアップ](pullServerSMB.md)
## [プル クライアントのセットアップ](pullClient.md)
### [構成名を使用したプル クライアントのセットアップ](pullClientConfigNames.md)
### [構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID.md)
## [DSC レポート サーバーの使用](reportServer.md)
## [プル サーバーのベスト プラクティス](secureServer.md)

# [DSC のトラブルシューティング](troubleshooting.md)

# [DSC on Nano Server の使用](nanoDsc.md)

# Linux での DSC
## [Linux 用 DSC の概要](lnxGettingStarted.md)
## [Linux 用組み込みリソース](lnxBuiltInResources.md)
### [nxArchive リソース](lnxArchiveResource.md)
### [nxEnvironment リソース](lnxEnvironmentResource.md)
### [nxFile リソース](lnxFileResource.md)
### [nxFileLine リソース](lnxFileLineResource.md)
### [nxGroup リソース](lnxGroupResource.md)
### [nxPackage リソース](lnxPackageResource.md)
### [nxService リソース](lnxServiceResource.md)
### [nxSshAuthorizedKeys リソース](lnxSshAuthorizedKeysResource.md)
### [nxUser リソース](lnxUserResource.md)

# DSC MOF の参照
## [MSFT_DSCLocalConfigurationManager クラス](msft-dsclocalconfigurationmanager.md)
### [MSFT_DSCLocalConfigurationManager クラスの ApplyConfiguration メソッド](msft-dsclocalconfigurationmanager-applyconfiguration.md)
### [MSFT_DSCLocalConfigurationManager クラスの DisableDebugConfiguration メソッド](msft-dsclocalconfigurationmanager-disabledebugconfiguration.md)
### [MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド](msft-dsclocalconfigurationmanager-enabledebugconfiguration.md)
### [MSFT_DSCLocalConfigurationManager クラスの GetConfiguration メソッド](msft-dsclocalconfigurationmanager-getconfiguration.md)
### [MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド](msft-dsclocalconfigurationmanager-getconfigurationresultoutput.md)
### [MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド](msft-dsclocalconfigurationmanager-getconfigurationstatus.md)
### [MSFT_DSCLocalConfigurationManager クラスの GetMetaConfiguration メソッド](msft-dsclocalconfigurationmanager-getmetaconfiguration.md)
### [MSFT_DSCLocalConfigurationManager クラスの PerformRequiredConfigurationChecks メソッド](msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)
### [MSFT_DSCLocalConfigurationManager クラスの RemoveConfiguration メソッド](msft-dsclocalconfigurationmanager-removeconfiguration.md)
### [MSFT_DSCLocalConfigurationManager クラスの ResourceGet メソッド](msft-dsclocalconfigurationmanager-resourceget.md)
### [MSFT_DSCLocalConfigurationManager クラスの ResourceSet メソッド](msft-dsclocalconfigurationmanager-resourceset.md)
### [MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド](msft-dsclocalconfigurationmanager-resourcetest.md)
### [MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド](msft-dsclocalconfigurationmanager-rollback.md)
### [MSFT_DSCLocalConfigurationManager クラスの SendConfiguration メソッド](msft-dsclocalconfigurationmanager-sendconfiguration.md)
### [MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApply メソッド](msft-dsclocalconfigurationmanager-sendconfigurationapply.md)
### [MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド](msft-dsclocalconfigurationmanager-sendconfigurationapplyasync.md)
### [MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド](msft-dsclocalconfigurationmanager-sendmetaconfigurationapply.md)
### [MSFT_DSCLocalConfigurationManager クラスの StopConfiguration メソッド](msft-dsclocalconfigurationmanager-stopconfiguration.md)
### [MSFT_DSCLocalConfigurationManager クラスの TestConfiguration メソッド](msft-dsclocalconfigurationmanager-testconfiguration.md)

# その他のリソース
## [ホワイトペーパー](whitepapers.md)



<!--HONumber=Jun16_HO4-->



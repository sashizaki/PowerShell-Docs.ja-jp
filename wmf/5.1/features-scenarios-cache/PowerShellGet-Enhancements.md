---
title: "機能またはシナリオ書き込みのテンプレート例"
contributor: KeithB
translationtype: Human Translation
ms.sourcegitcommit: 8c55ca4b972c8d708a09b922f27eec585ddc33d0
ms.openlocfilehash: 025565404b60cebefac27e51c70d70edb5e47bc9

---

>注: わかりやすいタイトルと簡単な説明を提供します

## PowerShellGet の機能拡張 ##
PowerShellGet モジュールのコマンドレットは、WMF 5.1 で大幅に更新されています。 現在、次の IDN シナリオがサポートされています。

- **プロキシのサポート:** 現在、PowerShellGet コマンドレットと内部プロキシの併用がサポートされており、Proxy と ProxyCredential パラメーターが PowerShellGet モジュール (例: Find-Module、Install-Module、Save-Module、Publish-Module) で Find-、Install-、Save-、Publish- コマンドレットに追加されています。 
- **カタログ署名の適用:** 現在、すべての PowerShellGet コマンドレットで、署名されたモジュールの更新の適用がチェックされます。 新しい Catalog コマンドレットで署名されたモジュールは、PowerShellGet コマンドレットでチェックされ、そのモジュールが転送中に変更されていないこと、モジュールに対する更新が元の発行元からのものであることが確認されます。 これは Install-Module および Update-Module コマンドレットに反映されます。 
- **ロール機能の共有と取得:** ロール機能は、Just Enough Administration の制限を設定するためのエンドポイント定義であり、PowerShell モジュールの PowerShell ギャラリーによって共有されます。 コマンドレットには Find-RoleCapability と New-PSRoleCapabilityFile が含まれます。 
- **Find コマンド:** Find コマンドにより、ユーザーが探しているコマンドを含む PowerShell ギャラリーでモジュールを検索できます。 
- **認証済みリポジトリ:** Visual Studio パッケージ管理のフィードには、現時点で PowerShellGet コマンドレットでサポートされている認証が必要です。

ユーザーからのフィードバックでは、次のように 5.1 で対処された追加領域について触れています。

- **Install-Script の変更:** Install-script で使用していた場所は、5.1 では自動でユーザー パスに追加されません。 これは PowerShellGet のスタンドアロン バージョンで変更され、WMF 5.1 に含まれています。
- **既存のスクリプトへのメタデータ フィールドの追加:** Update-ScriptFileInfo は、既存のスクリプトで、PowerShellGallery への公開に必要な既定のメタデータ フィールドの追加に使用できます。 これまでは、ユーザーが手動でこれを既存のスクリプトにマージする必要がありました。
- **低いバージョンで管理されるモジュールをギャラリーに公開する:** 現在は、最上位バージョンよりも低いバージョン番号のモジュールは、Publish-Module を使用してギャラリーに公開できるようになりました。 たとえば、発行元が 1.x バージョンから大幅に変更を加え、バージョン 2.0.0 をリリースした場合、バージョン 1.5.0 への修正は簡単にはリリースできませんでした。 現在は、モジュール保持のサポートを改善する 1.5.1 を PowerShell ギャラリーで公開できるようになりました。 
- **スクリプトとモジュールをインストールするときのコマンド上書きのチェック:** Install-Module および Install-Script では、システムに既にあるコマンドが含まれているかどうかを確認し、ある場合は、既定でエラーにします。 
- **Publish- コマンドレットによる Nuget のブートストラップ:** これまでは、Publish-Module または Publish-Script を使用した Nuget プロバイダーは、特定の自動タスクが非常に困難なため自動的にインストールする方法はありませんでした。 現在、ユーザーは -Force を Publish- コマンドに追加してこのプロンプトをバイパスできるようになりました。 

>注: 新しい概念、実装、例などに関する追加詳細は正規のテクニカル ドキュメントにリンクしてください。

**PowerShellGet の使用に関する詳細**
- [About-CatalogSigning]()
- []()
- [CompatiblePSEditions で Get-Module の結果をフィルターする]()
- [互換性のある PowerShell のエディションで実行しない場合はスクリプトを実行させない]()






<!--HONumber=Aug16_HO3-->



---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: psgallery_gettingstarted
ms.openlocfilehash: c3aafe9e76eda9acdd4787f63dc0f8c71a20d02a
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="get-started-with-the-powershell-gallery"></a>PowerShell ギャラリーの概要

PowerShell ギャラリーからシステムに項目をダウンロードするには、[PowerShellGet](/powershell/module/powershellget) モジュールが必要です。 PowerShellGet モジュールは次のいずれかで見つかります。 PowerShell ギャラリーから項目をダウンロードするのにサインインする必要はありません。

## <a name="discovering-items-from-the-powershell-gallery"></a>PowerShell ギャラリーでの項目の検出

この Web サイトで**検索**コントロールを使用するか、[モジュールとスクリプト] ページを閲覧すると PowerShell ギャラリーの項目が見つかります。 また、[Find-Module][] および [Find-Script][] コマンドレットを、アイテムの種類に応じて `-Repository PSGallery` を指定して実行すると、PowerShell ギャラリーからアイテムを検索できます。

次のパラメーターを使用すると、ギャラリーからの結果をフィルター処理できます。

- 名前
- AllVersions
- MinimumVersion
- RequiredVersion
- タグ
- Includes
- DscResource
- RoleCapability
- コマンド
- フィルター

ギャラリー内の特定の DSC リソースのみを検出したい場合は、[Find-DscResource] コマンドレットを実行します。 Find-DscResource では、ギャラリーに含まれている DSC リソースのデータが返されます。
DSC リソースは常にモジュールの一部として配布されるため、この DSC リソースをインストールする場合も [Install-Module][] を実行する必要があります。

## <a name="learning-about-items-in-the-powershell-gallery"></a>PowerShell ギャラリーの項目の詳細

関心のある項目を特定できたら、その詳細を入手することができます。 これは、ギャラリー上で項目の特定のページを調べると見つかります。 そのページでは、その項目と共にアップロードされているメタデータをすべて参照することができます。 この項目のメタデータは項目の作成者が提供するものであり、Microsoft で検証したものではありません。 項目の所有者は、項目の公開に使用したギャラリーのアカウントと厳密に関連付けられており、[作成者] フィールドよりも信頼性があります。

誠意をもって公開されていると思われない項目が見つかった場合は、その項目のページの **[不正使用を報告]** をクリックします。

[Find-Module][] または [Find-Script][] を実行している場合、返される PSGetModuleInfo オブジェクトにこのデータが表示されます。 たとえば、`Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` を実行すると、ギャラリーの PSReadLine モジュールのデータが返されます。

## <a name="downloading-items-from-the-powershell-gallery"></a>PowerShell ギャラリーでの項目のダウンロード

PowerShell ギャラリーから項目をダウンロードするとき、次のプロセスをお勧めします。

### <a name="inspect"></a>検査

検査のためにギャラリーから項目をダウンロードするには、項目の種類に応じて [Save-Module][] または [Save-Script][] コマンドレットを実行します。 これにより、項目をインストールすることなくローカルに保存し、項目の内容を検査することができます。 保存した項目は必ず手動で削除してください。

この項目の一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。
このギャラリーの項目の内容とコードは、インストールする前に確認することをお勧めします。

誠意をもって公開されていると思われない項目が見つかった場合は、その項目のページの **[不正使用を報告]** をクリックします。

### <a name="install"></a>[インストール]

使用のためにギャラリーから項目をインストールするには、項目の種類に応じて [Install-Module][] または [Install-Script][] コマンドレットを実行します。

[Install-Module][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Modules` にモジュールをインストールします。
これには管理者アカウントが必要です。 `-Scope CurrentUser` パラメーターを追加する場合は、モジュールは `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` にインストールされます。

[Install-Script][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Scripts` にスクリプトをインストールします。
これには管理者アカウントが必要です。 `-Scope CurrentUser` パラメーターを追加する場合は、スクリプトは `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` にインストールされます。

既定では、[Install-Module][] および [Install-Script][] は項目の最新バージョンをインストールします。
前のバージョンのアイテムをインストールするには、 `-RequiredVersion` パラメーターを追加します。

### <a name="deploy"></a>展開

項目を PowerShell ギャラリーから Azure Automation にデプロイするには、項目の詳細ページで **[Azure Automation にデプロイする]** をクリックします。 Azure 管理ポータルにリダイレクトされるため、そこでAzure アカウント資格情報を使用してサインインします。 依存関係のある項目をデプロイすると、すべての依存関係が Azure Automation にデプロイされることに注意してください。 [Azure Automation にデプロイする] ボタンは、**AzureAutomationNotSupported** タグを項目のメタデータに追加すると無効にできます。

Azure Automation の詳細については、[Azure Automation](/azure/automation) のドキュメントをご覧ください。

## <a name="updating-items-from-the-powershell-gallery"></a>PowerShell ギャラリーからの項目の更新

PowerShell ギャラリーからインストールされたアイテムを更新するには、[Update-Module][] または [Update-Script][] コマンドレットを実行します。 パラメーターを追加せずに [Update-Module][] を実行すると、[Install-Module][] を実行してインストールされた各モジュールが更新されます。 モジュールを選択して更新するには、`-Name` パラメーターを追加します。

同様に、パラメーターを追加せずに [Update-Script][] を実行すると、[Install-Script][] を実行してインストールされた各スクリプトが更新されます。 スクリプトを選択して更新するには、`-Name` パラメーターを追加します。

## <a name="list-items-that-you-have-installed-from-the-powershell-gallery"></a>PowerShell ギャラリーからインストールした項目の一覧

PowerShell ギャラリーからどのモジュールをインストールしたかを調べるには、[Get-InstalledModule][] コマンドレットを実行します。 このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるモジュールをすべて一覧表示します。

同様に、PowerShell ギャラリーからどのスクリプトをインストールしたかを調べるには、[Get-InstalledScript][] コマンドレットを実行します。 このコマンドは、PowerShell ギャラリーから直接インストールした、システム上にあるスクリプトをすべて一覧表示します。

[Find-DscResource]: /powershell/module/powershellget/Find-DscResource
[Find-Module]: /powershell/module/powershellget/Find-Module
[Find-Script]: /powershell/module/powershellget/Find-Script
[Get-InstalledModule]: /powershell/module/powershellget/Get-InstalledModule
[Get-InstalledScript]: /powershell/module/powershellget/Get-InstalledScript
[Install-Module]: /powershell/module/powershellget/Install-Module
[Install-Script]: /powershell/module/powershellget/Install-Script
[Publish-Module]: /powershell/module/powershellget/Publish-Module
[Publish-Script]: /powershell/module/powershellget/Publish-Script
[Register-PSRepository]: /powershell/module/powershellget/Register-Repository
[Save-Module]: /powershell/module/powershellget/Save-Module
[Save-Script]: /powershell/module/powershellget/Save-Script
---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリーの概要
ms.openlocfilehash: c8beba3009e462ce52cdecd34fc0313d9234f289
ms.sourcegitcommit: 1082b13115c5c5be4b76574ba55307b3e567983f
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "52576891"
---
# <a name="getting-started-with-the-powershell-gallery"></a>PowerShell ギャラリーの概要

PowerShell ギャラリーは、スクリプト、モジュール、およびダウンロードして利用できる DSC リソースを含むパッケージ リポジトリです。 コマンドレットを使用する、 [PowerShellGet](/powershell/module/powershellget)モジュールを PowerShell ギャラリーからパッケージをインストールします。 PowerShell ギャラリーから項目をダウンロードするのにサインインする必要はありません。

> [!NOTE]
> PowerShell ギャラリーから直接パッケージをダウンロードすることもできますが、この方法はお勧めできません。
> 詳細については、「[パッケージの手動ダウンロード](/powershell/gallery/how-to/working-with-packages/manual-download)」を参照してください。

## <a name="discovering-packages-from-the-powershell-gallery"></a>PowerShell ギャラリーでのパッケージの検出

使用して、PowerShell ギャラリーでパッケージを見つけることができます、**検索**PowerShell ギャラリーの上のコントロール[ホーム ページ](https://www.powershellgallery.com)、またはモジュールおよびスクリプトを参照してから、[パッケージ ページ](https://www.powershellgallery.com/packages). 実行して、PowerShell ギャラリーからパッケージを検索することもできます、 [Find-module][]、 [Find-dscresource]、および[Find-script][]コマンドレットは、パッケージの種類に応じて`-Repository PSGallery`します。

次のパラメーターを使用して、ギャラリーからの結果をフィルター処理できます。

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

## <a name="learning-about-packages-in-the-powershell-gallery"></a>PowerShell ギャラリーのパッケージの詳細

関心のあるパッケージを特定できたら、その詳細を入手することができます。 これは、ギャラリー上でパッケージの特定のページを調べると見つかります。 そのページでは、そのパッケージと共にアップロードされているメタデータをすべて参照することができます。 このメタデータはパッケージの作成者が提供するものであり、Microsoft で検証したものではありません。 パッケージの所有者は、パッケージの公開に使用したギャラリーのアカウントと厳密に関連付けられており、[作成者] フィールドよりも信頼性があります。

誠意をもって公開されていると思われないパッケージが見つかった場合は、そのパッケージのページの **[不正使用を報告]** をクリックします。

[Find-Module][] または [Find-Script][] を実行している場合、返される PSGetModuleInfo オブジェクトにこのデータが表示されます。 たとえば、`Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` を実行すると、
ギャラリーの PSReadLine モジュールのデータが返されます。

## <a name="downloading-packages-from-the-powershell-gallery"></a>PowerShell ギャラリーでのパッケージのダウンロード

PowerShell ギャラリーからパッケージをダウンロードするとき、次のプロセスをお勧めします。

### <a name="inspect"></a>検査

検査のためにギャラリーからパッケージをダウンロードするには、パッケージの種類に応じて [Save-Module][] または [Save-Script][] コマンドレットを実行します。 これにより、パッケージをインストールすることなくローカルに保存し、パッケージの内容を検査することができます。 保存したパッケージは必ず手動で削除してください。

このパッケージの一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。
このギャラリーのパッケージの内容とコードは、インストールする前に確認することをお勧めします。

誠意をもって公開されていると思われないパッケージが見つかった場合は、そのパッケージのページの **[不正使用を報告]** をクリックします。

### <a name="install"></a>インストール

使用のためにギャラリーからパッケージをインストールするには、パッケージの種類に応じて [Install-Module][] または [Install-Script][] コマンドレットを実行します。

[Install-Module][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Modules` にモジュールをインストールします。
これには管理者アカウントが必要です。 `-Scope CurrentUser` パラメーターを追加する場合は、モジュールは `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` にインストールされます。

[Install-Script][] は、既定では `$env:ProgramFiles\WindowsPowerShell\Scripts` にスクリプトをインストールします。
これには管理者アカウントが必要です。 `-Scope CurrentUser` パラメーターを追加する場合は、スクリプトは `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` にインストールされます。

既定では、[Install-Module][] および [Install-Script][] は最新バージョンのパッケージをインストールします。
前のバージョンのパッケージをインストールするには、`-RequiredVersion` パラメーターを追加します。

### <a name="deploy"></a>展開

Azure Automation に PowerShell ギャラリーからパッケージを展開する をクリックして**Azure Automation**、順にクリックします**Azure Automation にデプロイする**パッケージ詳細ページにします。 Azure 管理ポータル、Azure アカウント資格情報を使用してサインインする場所にリダイレクトされます。 Azure Automation にすべての依存関係を配置依存関係を持つパッケージを展開することに注意してください。 [Azure Automation にデプロイする] ボタンは、**AzureAutomationNotSupported** タグをパッケージのメタデータに追加すると無効にできます。

Azure Automation の詳細については、[Azure Automation](/azure/automation) のドキュメントをご覧ください。

## <a name="updating-packages-from-the-powershell-gallery"></a>PowerShell ギャラリーからのパッケージの更新

PowerShell ギャラリーからインストールされたパッケージを更新するには、[Update-Module][] または [Update-Script][] コマンドレットを実行します。 [Update-module] を実行してインストールされているすべてのモジュールを更新しようとしたときに、追加パラメーターなしで実行、 [Install-module][]します。 モジュールを選択して更新するには、`-Name` パラメーターを追加します。 

同様に、その他のパラメーターなしで実行時に [更新スクリプト] のが更新されますを実行してインストールされているすべてのスクリプト[Install-script][]します。 スクリプトを選択して更新するには、`-Name` パラメーターを追加します。

## <a name="list-packages-that-you-have-installed-from-the-powershell-gallery"></a>PowerShell ギャラリーからインストールしたパッケージの一覧

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

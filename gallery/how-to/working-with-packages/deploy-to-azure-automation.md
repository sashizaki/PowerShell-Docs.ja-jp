---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: Azure Automation にデプロイする
ms.openlocfilehash: dc382b1cf3ceaa787f54c555d01e6bd9ba70e680
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003769"
---
# <a name="deploy-to-azure-automation"></a>Azure Automation にデプロイする

パッケージの詳細ページの [Azure Automation にデプロイする] ボタンでは、PowerShell ギャラリーから Azure Automation にパッケージがデプロイされます。

![[Azure Automation にデプロイする] ボタン](../../Images/DeployToAzureAutomationButton.png)

クリックすると Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。
パッケージに依存関係がある場合、すべての依存関係も Azure Automation にデプロイされます。

> [!WARNING]
> お使いの Automation アカウントに既に同じパッケージとバージョンがある場合、PowerShell ギャラリーからこれを再度デプロイすると、Automation アカウントのパッケージが上書きされます。

モジュールをデプロイする場合は、[Azure Automation] の [モジュール] セクションに表示されます。  スクリプトをデプロイする場合は、[Azure Automation] の [Runbooks] セクションに表示されます。

[Azure Automation にデプロイする] ボタンは、AzureAutomationNotSupported タグをパッケージのメタデータに追加すると無効にできます。

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Azure Automation へのデプロイに表示されるライセンス同意リクエスト

Azure Automation へデプロイするモジュールでライセンスへの同意が必要な場合、ポータルの UI に、"このモジュールには、ライセンスの同意が必要です。 [OK] をクリックすると、ライセンス条項に同意します。" という警告が表示されます。

![ライセンスへの同意が必要な Azure Automation へのデプロイ](../../Images/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>詳細情報

- [PowerShellGet でのライセンス同意リクエスト](../../concepts/module-license-acceptance.md)
- [PowerShell ギャラリーでのライセンス同意リクエスト](packages-that-require-license-acceptance.md)
- [Azure Automation の Web サイト](http://azure.microsoft.com/services/automation/)

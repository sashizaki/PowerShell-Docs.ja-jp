---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: Azure Automation にデプロイする
ms.openlocfilehash: ced67809387a85e089259edf6b091d68e58ba6a7
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219336"
---
# <a name="deploy-to-azure-automation"></a>Azure Automation にデプロイする

項目の詳細ページの [Azure Automation にデプロイする] ボタンでは、PowerShell ギャラリーから Azure Automation に項目がデプロイされます。

![[Azure Automation にデプロイする] ボタン](../../Images/DeployToAzureAutomationButton.png)

クリックすると Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。
項目に依存関係がある場合、すべての依存関係も Azure Automation にデプロイされます。

> [!WARNING]
> お使いの Automation アカウントに既に同じ項目とバージョンがある場合、PowerShell ギャラリーからこれを再度展開すると、Automation アカウントの項目が上書きされます。

モジュールをデプロイする場合は、[Azure Automation] の [モジュール] セクションに表示されます。  スクリプトをデプロイする場合は、[Azure Automation] の [Runbooks] セクションに表示されます。

[Azure Automation にデプロイする] ボタンは、AzureAutomationNotSupported タグを項目のメタデータに追加すると無効にできます。

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Azure Automation へのデプロイに表示されるライセンス同意リクエスト

Azure Automation へデプロイするモジュールでライセンスへの同意が必要な場合、ポータルの UI に、"このモジュールには、ライセンスの同意が必要です。 [OK] をクリックすると、ライセンス条項に同意します。" という警告が表示されます。

![ライセンスへの同意が必要な Azure Automation へのデプロイ](../../Images/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>詳細情報

- [PowerShellGet でのライセンス同意リクエスト](../../concepts/module-license-acceptance.md)
- [PowerShell ギャラリーでのライセンス同意リクエスト](items-that-require-license-acceptance.md)
- [Azure Automation の Web サイト](http://azure.microsoft.com/services/automation/)

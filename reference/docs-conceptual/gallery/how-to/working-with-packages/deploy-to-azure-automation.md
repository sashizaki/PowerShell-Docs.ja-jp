---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: Azure Automation にデプロイする
ms.openlocfilehash: 5d09a0777c59b642400d683c8cb6f881319fb881
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78278743"
---
# <a name="deploy-to-azure-automation"></a>Azure Automation にデプロイする

パッケージの詳細ページの [Azure Automation にデプロイする] ボタンでは、PowerShell ギャラリーから Azure Automation にパッケージがデプロイされます。

![[Azure Automation にデプロイする] ボタン](media/deploy-to-azure-automation/DeployToAzureAutomationButton.png)

クリックすると Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。
パッケージに依存関係がある場合、すべての依存関係も Azure Automation にデプロイされます。

> [!WARNING]
> お使いの Automation アカウントに既に同じパッケージとバージョンがある場合、PowerShell ギャラリーからこれを再度デプロイすると、Automation アカウントのパッケージが上書きされます。

モジュールをデプロイする場合は、[Azure Automation] の [モジュール] セクションに表示されます。  スクリプトをデプロイする場合は、[Azure Automation] の [Runbooks] セクションに表示されます。

[Azure Automation にデプロイする] ボタンは、AzureAutomationNotSupported タグをパッケージのメタデータに追加すると無効にできます。

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Azure Automation へのデプロイに表示されるライセンス同意リクエスト

Azure Automation へデプロイするモジュールでライセンスへの同意が必要な場合、ポータルの UI に、"このモジュールには、ライセンスの同意が必要です。 [OK] をクリックすると、ライセンス条項に同意します。" という警告が表示されます。

![ライセンスへの同意が必要な Azure Automation へのデプロイ](media/deploy-to-azure-automation/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>詳細

- [PowerShellGet でのライセンス同意リクエスト](../../concepts/module-license-acceptance.md)
- [PowerShell ギャラリーでのライセンス同意リクエスト](packages-that-require-license-acceptance.md)
- [Azure Automation の Web サイト](https://azure.microsoft.com/services/automation/)

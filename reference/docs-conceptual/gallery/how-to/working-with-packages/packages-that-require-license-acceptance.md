---
ms.date: 06/12/2017
contributor: Farehar
keywords: ギャラリー, PowerShell, PSGallery
title: ライセンス同意リクエスト
ms.openlocfilehash: eaed248895d14bd455d2d8d3c2222d8848eeccae
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71328213"
---
# <a name="require-license-acceptance"></a>ライセンス同意リクエスト

ライセンス同意リクエストのテキストは、ライセンスへの同意が必要なモジュールのアイテム詳細ページに表示されます。 [License.txt を表示] リンクをクリックすると、モジュールのライセンスを確認できます。

![ライセンス同意リクエスト](../../Images/RequireLicenseAcceptance.png)

PowerShellGet を使用してモジュールのインストール、保存、更新を行う場合、または Azure Automation へのデプロイを行う場合、ユーザーにはライセンスへの同意が求められます。

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Azure Automation へのデプロイに表示されるライセンス同意リクエスト

Azure Automation へデプロイするモジュールでライセンスへの同意が必要な場合、ポータルの UI に、"このモジュールには、ライセンスの同意が必要です。 [OK] をクリックすると、ライセンス条項に同意します。" という警告が表示されます。

![ライセンスへの同意が必要な Azure Automation へのデプロイ](../../Images/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>詳細情報

[PowerShellGet でのライセンス同意リクエスト](../../concepts/module-license-acceptance.md)
[Azure Automation Web サイト](/azure/automation)

---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: psgallery_deploy_to_azure_automation
ms.openlocfilehash: 8da4eabead6a419dc0c01c74335c06bf8be25d0c
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
<a name="deploy-to-azure-automation"></a>Azure Automation にデプロイする
===========================

項目の詳細ページの [Azure Automation にデプロイする] ボタンでは、PowerShell ギャラリーから Azure Automation に項目がデプロイされます。

![[Azure Automation にデプロイする] ボタン](Images/DeployToAzureAutomationButton.png)

クリックすると Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。
項目に依存関係がある場合、すべての依存関係も Azure Automation にデプロイされます。

警告: Automation アカウントに既に同じ項目とバージョンがある場合、PowerShell ギャラリーからこれを再度デプロイすると、Automation アカウントの項目が上書きされます。

モジュールをデプロイする場合は、[Azure Automation] の [モジュール] セクションに表示されます。  スクリプトをデプロイする場合は、[Azure Automation] の [Runbooks] セクションに表示されます。

[Azure Automation にデプロイする] ボタンは、AzureAutomationNotSupported タグを項目のメタデータに追加すると無効にできます。

Azure Automation の詳細については、Azure Automation の Web サイト [Azure Automation の Web サイト](http://azure.microsoft.com/services/automation/) をご覧ください。
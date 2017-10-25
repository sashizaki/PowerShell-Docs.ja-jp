---
ms.date: 2017-06-12
contributor: JKeithB
ms.topic: conceptual
keywords: "ギャラリー, PowerShell, コマンドレット, PSGallery"
title: psgallery_deploy_to_azure_automation
ms.openlocfilehash: 91f48fb43d7fb099e34ce5d3b3b632e3cb119d64
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
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

Azure Automation の詳細については、Azure Automation の Web サイト [Azure Automation の Web サイト](http://azure.microsoft.com/en-us/services/automation/) をご覧ください。


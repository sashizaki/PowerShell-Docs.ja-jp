---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,コマンドレット,ギャラリー"
ms.date: 2016-10-14
contributor: manikb
title: psgallery_deploy_to_azure_automation
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: c028bf6145b41c13bccda9543a782b838bd730ff

---

Azure Automation にデプロイする
===========================

項目の詳細ページの [Azure Automation にデプロイする] ボタンでは、PowerShell ギャラリーから Azure Automation に項目がデプロイされます。

![[Azure Automation にデプロイする] ボタン](Images/DeployToAzureAutomationButton.png)

クリックすると Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。
項目に依存関係がある場合、すべての依存関係も Azure Automation にデプロイされます。

警告: Automation アカウントに既に同じ項目とバージョンがある場合、PowerShell ギャラリーからこれを再度デプロイすると、Automation アカウントの項目が上書きされます。

モジュールをデプロイする場合は、[Azure Automation] の [モジュール] セクションに表示されます。  スクリプトをデプロイする場合は、[Azure Automation] の [Runbooks] セクションに表示されます。

[Azure Automation にデプロイする] ボタンは、AzureAutomationNotSupported タグを項目のメタデータに追加すると無効にできます。

Azure Automation の詳細については、Azure Automation の Web サイト [Azure Automation の Web サイト](http://azure.microsoft.com/en-us/services/automation/) をご覧ください。




<!--HONumber=Oct16_HO2-->



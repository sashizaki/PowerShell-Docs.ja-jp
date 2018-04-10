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
<a name="deploy-to-azure-automation"></a><span data-ttu-id="a59f8-103">Azure Automation にデプロイする</span><span class="sxs-lookup"><span data-stu-id="a59f8-103">Deploy to Azure Automation</span></span>
===========================

<span data-ttu-id="a59f8-104">項目の詳細ページの [Azure Automation にデプロイする] ボタンでは、PowerShell ギャラリーから Azure Automation に項目がデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="a59f8-104">The Deploy to Azure Automation button on the item details page will deploy the item from the PowerShell Gallery to Azure Automation.</span></span>

![[Azure Automation にデプロイする] ボタン](Images/DeployToAzureAutomationButton.png)

<span data-ttu-id="a59f8-106">クリックすると Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a59f8-106">When clicked, it will redirect you to the Azure Management Portal, where you sign in using your Azure account credentials.</span></span>
<span data-ttu-id="a59f8-107">項目に依存関係がある場合、すべての依存関係も Azure Automation にデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="a59f8-107">If the item includes dependencies, all the dependencies will be deployed to Azure Automation as well.</span></span>

<span data-ttu-id="a59f8-108">警告: Automation アカウントに既に同じ項目とバージョンがある場合、PowerShell ギャラリーからこれを再度デプロイすると、Automation アカウントの項目が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a59f8-108">WARNING:  If the same item and version already exist in your Automation account, deploying it again from the PowerShell Gallery will overwrite the item in your Automation account.</span></span>

<span data-ttu-id="a59f8-109">モジュールをデプロイする場合は、[Azure Automation] の [モジュール] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a59f8-109">If you deploy a module, it will appear in the Modules section of Azure Automation.</span></span>  <span data-ttu-id="a59f8-110">スクリプトをデプロイする場合は、[Azure Automation] の [Runbooks] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a59f8-110">If you deploy a script, it will appear in the Runbooks section of Azure Automation.</span></span>

<span data-ttu-id="a59f8-111">[Azure Automation にデプロイする] ボタンは、AzureAutomationNotSupported タグを項目のメタデータに追加すると無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a59f8-111">The Deploy to Azure Automation button can be disabled by adding the AzureAutomationNotSupported tag to the item metadata.</span></span>

<span data-ttu-id="a59f8-112">Azure Automation の詳細については、Azure Automation の Web サイト [Azure Automation の Web サイト](http://azure.microsoft.com/services/automation/) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a59f8-112">To learn more about Azure Automation, see the Azure Automation website [Azure Automation website](http://azure.microsoft.com/services/automation/).</span></span>
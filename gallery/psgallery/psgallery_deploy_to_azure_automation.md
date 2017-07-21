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
<a name="deploy-to-azure-automation"></a><span data-ttu-id="33904-103">Azure Automation にデプロイする</span><span class="sxs-lookup"><span data-stu-id="33904-103">Deploy to Azure Automation</span></span>
===========================

<span data-ttu-id="33904-104">項目の詳細ページの [Azure Automation にデプロイする] ボタンでは、PowerShell ギャラリーから Azure Automation に項目がデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="33904-104">The Deploy to Azure Automation button on the item details page will deploy the item from the PowerShell Gallery to Azure Automation.</span></span>

![[Azure Automation にデプロイする] ボタン](Images/DeployToAzureAutomationButton.png)

<span data-ttu-id="33904-106">クリックすると Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="33904-106">When clicked, it will redirect you to the Azure Management Portal, where you sign in using your Azure account credentials.</span></span>
<span data-ttu-id="33904-107">項目に依存関係がある場合、すべての依存関係も Azure Automation にデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="33904-107">If the item includes dependencies, all the dependencies will be deployed to Azure Automation as well.</span></span>

<span data-ttu-id="33904-108">警告: Automation アカウントに既に同じ項目とバージョンがある場合、PowerShell ギャラリーからこれを再度デプロイすると、Automation アカウントの項目が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="33904-108">WARNING:  If the same item and version already exist in your Automation account, deploying it again from the PowerShell Gallery will overwrite the item in your Automation account.</span></span>

<span data-ttu-id="33904-109">モジュールをデプロイする場合は、[Azure Automation] の [モジュール] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="33904-109">If you deploy a module, it will appear in the Modules section of Azure Automation.</span></span>  <span data-ttu-id="33904-110">スクリプトをデプロイする場合は、[Azure Automation] の [Runbooks] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="33904-110">If you deploy a script, it will appear in the Runbooks section of Azure Automation.</span></span>

<span data-ttu-id="33904-111">[Azure Automation にデプロイする] ボタンは、AzureAutomationNotSupported タグを項目のメタデータに追加すると無効にできます。</span><span class="sxs-lookup"><span data-stu-id="33904-111">The Deploy to Azure Automation button can be disabled by adding the AzureAutomationNotSupported tag to the item metadata.</span></span>

<span data-ttu-id="33904-112">Azure Automation の詳細については、Azure Automation の Web サイト [Azure Automation の Web サイト](http://azure.microsoft.com/en-us/services/automation/) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="33904-112">To learn more about Azure Automation, see the Azure Automation website [Azure Automation website](http://azure.microsoft.com/en-us/services/automation/).</span></span>


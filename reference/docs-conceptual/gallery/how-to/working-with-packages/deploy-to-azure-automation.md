---
ms.date: 06/12/2017
title: Azure Automation にデプロイする
description: この記事では、PowerShell ギャラリーを使用して Azure Automation にパッケージをデプロイする方法について説明します。
ms.openlocfilehash: e9de079ee6cc950c8a268423b9eabd515959b718
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662365"
---
# <a name="deploy-to-azure-automation"></a><span data-ttu-id="dd6b9-103">Azure Automation にデプロイする</span><span class="sxs-lookup"><span data-stu-id="dd6b9-103">Deploy to Azure Automation</span></span>

<span data-ttu-id="dd6b9-104">パッケージの詳細ページの [Azure Automation にデプロイする] ボタンでは、PowerShell ギャラリーから Azure Automation にパッケージがデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="dd6b9-104">The Deploy to Azure Automation button on the package details page will deploy the package from the PowerShell Gallery to Azure Automation.</span></span>

![[Azure Automation にデプロイする] ボタン](media/deploy-to-azure-automation/DeployToAzureAutomationButton.png)

<span data-ttu-id="dd6b9-106">クリックすると Azure 管理ポータルにリダイレクトされるため、そこで Azure アカウント資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="dd6b9-106">When clicked, it will redirect you to the Azure Management Portal, where you sign in using your Azure account credentials.</span></span> <span data-ttu-id="dd6b9-107">パッケージに依存関係がある場合、すべての依存関係も Azure Automation にデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="dd6b9-107">If the package includes dependencies, all the dependencies will be deployed to Azure Automation as well.</span></span>

> [!WARNING]
> <span data-ttu-id="dd6b9-108">お使いの Automation アカウントに既に同じパッケージとバージョンがある場合、PowerShell ギャラリーからこれを再度デプロイすると、Automation アカウントのパッケージが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="dd6b9-108">If the same package and version already exist in your Automation account, deploying it again from the PowerShell Gallery will overwrite the package in your Automation account.</span></span>

<span data-ttu-id="dd6b9-109">モジュールをデプロイする場合は、[Azure Automation] の [モジュール] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd6b9-109">If you deploy a module, it will appear in the Modules section of Azure Automation.</span></span> <span data-ttu-id="dd6b9-110">スクリプトをデプロイする場合は、[Azure Automation] の [Runbooks] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd6b9-110">If you deploy a script, it will appear in the Runbooks section of Azure Automation.</span></span>

<span data-ttu-id="dd6b9-111">[Azure Automation にデプロイする] ボタンは、AzureAutomationNotSupported タグをパッケージのメタデータに追加すると無効にできます。</span><span class="sxs-lookup"><span data-stu-id="dd6b9-111">The Deploy to Azure Automation button can be disabled by adding the AzureAutomationNotSupported tag to the package metadata.</span></span>

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a><span data-ttu-id="dd6b9-112">Azure Automation へのデプロイに表示されるライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="dd6b9-112">Require License Acceptance on Deploy to Azure Automation</span></span>

<span data-ttu-id="dd6b9-113">Azure Automation へデプロイするモジュールでライセンスへの同意が必要な場合、ポータルの UI に、"このモジュールには、ライセンスの同意が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd6b9-113">If the module being deployed to Azure Automation requires license acceptance, portal UI will show a disclaimer saying 'This module requires license acceptance.</span></span> <span data-ttu-id="dd6b9-114">[OK] をクリックすると、ライセンス条項に同意します。" という警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd6b9-114">By clicking OK, you are accepting license terms.'</span></span>

![ライセンスへの同意が必要な Azure Automation へのデプロイ](media/deploy-to-azure-automation/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a><span data-ttu-id="dd6b9-116">詳細</span><span class="sxs-lookup"><span data-stu-id="dd6b9-116">More details</span></span>

- [<span data-ttu-id="dd6b9-117">PowerShellGet でのライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="dd6b9-117">Require License Acceptance in PowerShellGet</span></span>](../../concepts/module-license-acceptance.md)
- [<span data-ttu-id="dd6b9-118">PowerShell ギャラリーでのライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="dd6b9-118">Require License Acceptance in PowerShell Gallery</span></span>](packages-that-require-license-acceptance.md)
- [<span data-ttu-id="dd6b9-119">Azure Automation の Web サイト</span><span class="sxs-lookup"><span data-stu-id="dd6b9-119">Azure Automation website</span></span>](https://azure.microsoft.com/services/automation/)

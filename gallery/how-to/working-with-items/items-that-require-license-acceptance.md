---
ms.date: 06/12/2017
contributor: Farehar
keywords: ギャラリー, PowerShell, PSGallery
title: ライセンス同意リクエスト
ms.openlocfilehash: 69787cdb12aa47223072551c9b68fc046573f022
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34218401"
---
# <a name="require-license-acceptance"></a><span data-ttu-id="2abf7-103">ライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="2abf7-103">Require license acceptance</span></span>

<span data-ttu-id="2abf7-104">ライセンス同意リクエストのテキストは、ライセンスへの同意が必要なモジュールのアイテム詳細ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2abf7-104">Require License Acceptance text shows up on item details page for modules that require license acceptance.</span></span> <span data-ttu-id="2abf7-105">[License.txt を表示] リンクをクリックすると、モジュールのライセンスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2abf7-105">License for module can be viewed by clicking on 'View License.txt' link.</span></span>

![ライセンス同意リクエスト](../../Images/RequireLicenseAcceptance.png)

<span data-ttu-id="2abf7-107">PowerShellGet を使用してモジュールのインストール、保存、更新を行う場合、または Azure Automation へのデプロイを行う場合、ユーザーにはライセンスへの同意が求められます。</span><span class="sxs-lookup"><span data-stu-id="2abf7-107">Users will be prompted to accept the license when installing, saving or updating the module through PowerShellGet or when deploying to Azure Automation.</span></span>

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a><span data-ttu-id="2abf7-108">Azure Automation へのデプロイに表示されるライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="2abf7-108">Require License Acceptance on Deploy to Azure Automation</span></span>

<span data-ttu-id="2abf7-109">Azure Automation へデプロイするモジュールでライセンスへの同意が必要な場合、ポータルの UI に、"このモジュールには、ライセンスの同意が必要です。</span><span class="sxs-lookup"><span data-stu-id="2abf7-109">If the module being deployed to Azure Automation requires license acceptance, portal UI will show a disclaimer saying 'This module requires license acceptance.</span></span> <span data-ttu-id="2abf7-110">[OK] をクリックすると、ライセンス条項に同意します。" という警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2abf7-110">By clicking OK, you are accepting license terms.'</span></span>

![ライセンスへの同意が必要な Azure Automation へのデプロイ](../../Images/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a><span data-ttu-id="2abf7-112">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2abf7-112">More details</span></span>

<span data-ttu-id="2abf7-113">[PowerShellGet でのライセンス同意リクエスト](../../concepts/module-license-acceptance.md)
[Azure Automation Web サイト](/azure/automation)</span><span class="sxs-lookup"><span data-stu-id="2abf7-113">[Require License Acceptance in PowerShellGet](../../concepts/module-license-acceptance.md)
[Azure Automation website](/azure/automation)</span></span>
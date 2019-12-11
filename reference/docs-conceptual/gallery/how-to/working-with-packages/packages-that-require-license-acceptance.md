---
ms.date: 06/12/2017
contributor: Farehar
keywords: ギャラリー, PowerShell, PSGallery
title: ライセンス同意リクエスト
ms.openlocfilehash: eaed248895d14bd455d2d8d3c2222d8848eeccae
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328213"
---
# <a name="require-license-acceptance"></a><span data-ttu-id="e0d40-103">ライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="e0d40-103">Require license acceptance</span></span>

<span data-ttu-id="e0d40-104">ライセンス同意リクエストのテキストは、ライセンスへの同意が必要なモジュールのアイテム詳細ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0d40-104">Require License Acceptance text shows up on item details page for modules that require license acceptance.</span></span> <span data-ttu-id="e0d40-105">[License.txt を表示] リンクをクリックすると、モジュールのライセンスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e0d40-105">License for module can be viewed by clicking on 'View License.txt' link.</span></span>

![ライセンス同意リクエスト](../../Images/RequireLicenseAcceptance.png)

<span data-ttu-id="e0d40-107">PowerShellGet を使用してモジュールのインストール、保存、更新を行う場合、または Azure Automation へのデプロイを行う場合、ユーザーにはライセンスへの同意が求められます。</span><span class="sxs-lookup"><span data-stu-id="e0d40-107">Users will be prompted to accept the license when installing, saving or updating the module through PowerShellGet or when deploying to Azure Automation.</span></span>

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a><span data-ttu-id="e0d40-108">Azure Automation へのデプロイに表示されるライセンス同意リクエスト</span><span class="sxs-lookup"><span data-stu-id="e0d40-108">Require License Acceptance on Deploy to Azure Automation</span></span>

<span data-ttu-id="e0d40-109">Azure Automation へデプロイするモジュールでライセンスへの同意が必要な場合、ポータルの UI に、"このモジュールには、ライセンスの同意が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0d40-109">If the module being deployed to Azure Automation requires license acceptance, portal UI will show a disclaimer saying 'This module requires license acceptance.</span></span> <span data-ttu-id="e0d40-110">[OK] をクリックすると、ライセンス条項に同意します。" という警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0d40-110">By clicking OK, you are accepting license terms.'</span></span>

![ライセンスへの同意が必要な Azure Automation へのデプロイ](../../Images/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a><span data-ttu-id="e0d40-112">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e0d40-112">More details</span></span>

<span data-ttu-id="e0d40-113">[PowerShellGet でのライセンス同意リクエスト](../../concepts/module-license-acceptance.md)
[Azure Automation Web サイト](/azure/automation)</span><span class="sxs-lookup"><span data-stu-id="e0d40-113">[Require License Acceptance in PowerShellGet](../../concepts/module-license-acceptance.md)
[Azure Automation website](/azure/automation)</span></span>

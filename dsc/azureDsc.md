---
ms.date: 03/15/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: Microsoft Azure での DSC の使用
ms.openlocfilehash: d35488c3f66895e930eaa84360f3d3ec9d74e9c7
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34221886"
---
# <a name="using-dsc-on-microsoft-azure"></a><span data-ttu-id="b69f7-103">Microsoft Azure での DSC の使用</span><span class="sxs-lookup"><span data-stu-id="b69f7-103">Using DSC on Microsoft Azure</span></span>

<span data-ttu-id="b69f7-104">Microsoft Azure の Desired State Configuration (DSC) は、[Azure Desired State Configuration 拡張機能ハンドラー](/azure/virtual-machines/virtual-machines-windows-extensions-dsc-overview)および [Azure Automation DSC](/azure/automation/automation-dsc-overview) によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b69f7-104">Desired State Configuration (DSC) is supported in Microsoft Azure through the [Azure Desired State Configuration extension handler](/azure/virtual-machines/virtual-machines-windows-extensions-dsc-overview) and through [Azure Automation DSC](/azure/automation/automation-dsc-overview).</span></span>

## <a name="azure-desired-state-configuration-extension-handler"></a><span data-ttu-id="b69f7-105">Azure Desired State Configuration 拡張機能ハンドラー</span><span class="sxs-lookup"><span data-stu-id="b69f7-105">Azure Desired State Configuration extension handler</span></span>

<span data-ttu-id="b69f7-106">Azure DSC 拡張機能を使用すると、Microsoft Azure でホストされている VM を DSC で管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b69f7-106">The Azure DSC extension allows VMs hosted in Microsoft Azure to be managed with DSC.</span></span>
<span data-ttu-id="b69f7-107">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69f7-107">For more information, see the following topics:</span></span>

- [<span data-ttu-id="b69f7-108">Azure Desired State Configuration 拡張機能ハンドラーの概要</span><span class="sxs-lookup"><span data-stu-id="b69f7-108">Azure Desired State Configuration extension handler</span></span>](/azure/virtual-machines/virtual-machines-windows-extensions-dsc-overview)
- [<span data-ttu-id="b69f7-109">Azure Resource Manager テンプレートを使用した Windows VMSS および Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="b69f7-109">Windows VMSS and Desired State Configuration with Azure Resource Manager templates</span></span>](/azure/virtual-machines/virtual-machines-windows-extensions-dsc-template)
- [<span data-ttu-id="b69f7-110">資格情報を Azure DSC 拡張機能ハンドラーに渡す</span><span class="sxs-lookup"><span data-stu-id="b69f7-110">Passing credentials to the Azure DSC extension handler</span></span>](/azure/virtual-machines/virtual-machines-windows-extensions-dsc-credentials)
- [<span data-ttu-id="b69f7-111">Azure Desired State Configuration 拡張機能の履歴</span><span class="sxs-lookup"><span data-stu-id="b69f7-111">Azure Desired State Configuration extension history</span></span>](azureDscexthistory.md)

## <a name="azure-automation-dsc"></a><span data-ttu-id="b69f7-112">Azure Automation DSC</span><span class="sxs-lookup"><span data-stu-id="b69f7-112">Azure Automation DSC</span></span>

<span data-ttu-id="b69f7-113">[Azure Automation サービス](https://azure.microsoft.com/services/automation/) を使用すると、DSC 構成、リソース、管理対象ノードを Azure 内で管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b69f7-113">The [Azure Automation service](https://azure.microsoft.com/services/automation/) allows you to manage DSC configurations, resources, and managed nodes from within Azure.</span></span> <span data-ttu-id="b69f7-114">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69f7-114">For more information, see the following topics:</span></span>

- [<span data-ttu-id="b69f7-115">Azure Automation DSC</span><span class="sxs-lookup"><span data-stu-id="b69f7-115">Azure Automation DSC</span></span>](/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="b69f7-116">Azure Automation DSC の使用</span><span class="sxs-lookup"><span data-stu-id="b69f7-116">Getting started with Azure Automation DSC</span></span>](/azure/automation/automation-dsc-getting-started)
- [<span data-ttu-id="b69f7-117">Azure Automation DSC による管理のためのマシンのオンボード</span><span class="sxs-lookup"><span data-stu-id="b69f7-117">Onboarding machines for management by Azure Automation DSC</span></span>](/azure/automation/automation-dsc-onboarding)
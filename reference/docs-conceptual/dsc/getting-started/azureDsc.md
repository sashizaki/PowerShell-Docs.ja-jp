---
ms.date: 03/15/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: Microsoft Azure での DSC の使用
ms.openlocfilehash: 54a317a415ff12c3d270897f414cba88716f0728
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953959"
---
# <a name="using-dsc-on-microsoft-azure"></a>Microsoft Azure での DSC の使用

Microsoft Azure の Desired State Configuration (DSC) は、[Azure Desired State Configuration 拡張機能ハンドラー](/azure/virtual-machines/extensions/dsc-overview)および [Azure Automation DSC](/azure/automation/automation-dsc-overview) によってサポートされています。

## <a name="azure-desired-state-configuration-extension-handler"></a>Azure Desired State Configuration 拡張機能ハンドラー

Azure DSC 拡張機能を使用すると、Microsoft Azure でホストされている VM を DSC で管理することができます。
詳細については、次のトピックを参照してください。

- [Azure Desired State Configuration 拡張機能ハンドラーの概要](/azure/virtual-machines/extensions/dsc-overview)
- [Azure Resource Manager テンプレートを使用した Windows VMSS および Desired State Configuration](/azure/virtual-machines/extensions/dsc-template)
- [資格情報を Azure DSC 拡張機能ハンドラーに渡す](/azure/virtual-machines/extensions/dsc-credentials)
- [Azure Desired State Configuration 拡張機能の履歴](azureDscexthistory.md)

## <a name="azure-automation-dsc"></a>Azure Automation DSC

[Azure Automation サービス](https://azure.microsoft.com/en-us/services/automation/) を使用すると、DSC 構成、リソース、管理対象ノードを Azure 内で管理することができます。 詳細については、次のトピックを参照してください。

- [Azure Automation DSC](/azure/automation/automation-dsc-overview)
- [Azure Automation DSC の使用](/azure/automation/automation-dsc-getting-started)
- [Azure Automation DSC による管理のためのマシンのオンボード](/azure/automation/automation-dsc-onboarding)
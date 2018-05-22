---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: f929ce4684bb53c3039238ecd465f1c0e432f741
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="deliver-a-configuration-document-without-applying"></a>適用することなく構成ドキュメントを提供する

[Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) コマンドレットでは、構成の MOF ファイルをターゲット ノードにコピーしますが、その構成は適用されません。
この構成が適用されるは、次の一貫性パス中、または [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx) コマンドレットの実行時です。

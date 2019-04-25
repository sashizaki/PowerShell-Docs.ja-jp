---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: db4543b788ad0a5c7aa32706246446533b901d09
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085815"
---
# <a name="deliver-a-configuration-document-without-applying"></a>適用することなく構成ドキュメントを提供する

[Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) コマンドレットでは、構成の MOF ファイルをターゲット ノードにコピーしますが、その構成は適用されません。
この構成が適用されるは、次の一貫性パス中、または [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx) コマンドレットの実行時です。

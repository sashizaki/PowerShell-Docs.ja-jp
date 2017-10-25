---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: e921a5ead21f52b7e0d9efd9335c44b99d7d6802
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="deliver-a-configuration-document-without-applying"></a>適用することなく構成ドキュメントを提供する

[Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) コマンドレットでは、構成の MOF ファイルをターゲット ノードにコピーしますが、その構成は適用されません。 この構成が適用されるは、次の一貫性パス中、または [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx) コマンドレットの実行時です。


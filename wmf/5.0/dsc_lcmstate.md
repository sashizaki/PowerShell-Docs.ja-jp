---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 4fc146f84588d368ac3eb819e3acb4cb8c5d8793
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="detailed-information-about-lcm-state"></a>LCM 状態に関する詳細情報

LCM 状態に関する詳細情報を公開する機能が強化されました。 Get-DscLocalConfigurationManager によって返される LCMState には、次の値が含まれるようになりました。

* **Idle**
* **Busy**
* **PendingReboot**
* **PendingConfiguration**

また、状態に関するさらに詳細な情報を含む LCMStateDetail プロパティも追加されました。


---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 57152e9f62c34600df63a2db8e9683928e825d93
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085798"
---
# <a name="detailed-information-about-lcm-state"></a>LCM 状態に関する詳細情報

LCM 状態に関する詳細情報を公開する機能が強化されました。 Get-DscLocalConfigurationManager によって返される LCMState には、次の値が含まれるようになりました。

* **Idle**
* **Busy**
* **PendingReboot**
* **PendingConfiguration**

また、状態に関するさらに詳細な情報を含む LCMStateDetail プロパティも追加されました。

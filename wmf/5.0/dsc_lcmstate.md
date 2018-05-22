---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: db9b48c188b3bfe2e20c06875606a285922f55a6
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="detailed-information-about-lcm-state"></a>LCM 状態に関する詳細情報

LCM 状態に関する詳細情報を公開する機能が強化されました。 Get-DscLocalConfigurationManager によって返される LCMState には、次の値が含まれるようになりました。

* **Idle**
* **Busy**
* **PendingReboot**
* **PendingConfiguration**

また、状態に関するさらに詳細な情報を含む LCMStateDetail プロパティも追加されました。

---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: baa35e9acd24d6f6155acf617a0d2c2210742af7
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="detailed-information-about-lcm-state"></a>LCM 状態に関する詳細情報

LCM 状態に関する詳細情報を公開する機能が強化されました。 Get-DscLocalConfigurationManager によって返される LCMState には、次の値が含まれるようになりました。

* **Idle**
* **Busy**
* **PendingReboot**
* **PendingConfiguration**

また、状態に関するさらに詳細な情報を含む LCMStateDetail プロパティも追加されました。
---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSCAutomationHostEnabled レジストリ キー
ms.openlocfilehash: 0f35a798e5b7d51fdfb66e4e79ceab0e36ccea5b
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808335"
---
# <a name="dscautomationhostenabled-registry-key"></a>DSCAutomationHostEnabled レジストリ キー

> 適用対象:Windows PowerShell 5.0

DSC は、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** の下の **DSCAutomationHostEnabled** というレジストリ キーを使用してコンピューターの起動時の構成を有効にします。
**DSCAutomationHostEnabled** は 3 つのモードをサポートしています。

|  DSCAutomationHostEnabled の値  |  説明   |
|---|---|
0 | 起動時にコンピューターの構成を行いません。 |
1 | 起動時にコンピューターの構成を行います。 |
2 | コンピューターの構成は、DSC の状態が保留中または最新の場合にのみ行います。 これが既定値です。 |

## <a name="see-also"></a>参照

この機能を使用して初回起動時に構成を実行する方法の例については、「[DSC を使用した初回起動時の仮想マシンの構成](bootstrapDsc.md)」をご覧ください。

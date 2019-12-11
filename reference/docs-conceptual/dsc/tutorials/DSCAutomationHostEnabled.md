---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSCAutomationHostEnabled レジストリ キー
ms.openlocfilehash: 2bccd2738b9f61efd656fdf0f98cf71affdbe781
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954269"
---
>適用先:Windows PowerShell 5.0

# <a name="dscautomationhostenabled-registry-key"></a>DSCAutomationHostEnabled レジストリ キー

DSC は、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** の下の **DSCAutomationHostEnabled** というレジストリ キーを使用してコンピューターの起動時の構成を有効にします。
**DSCAutomationHostEnabled** は 3 つのモードをサポートしています。

|  DSCAutomationHostEnabled の値  |  説明   |
|---|---|
0 | 起動時にコンピューターの構成を行いません。 |
1 で保護されたプロセスとして起動されました | 起動時にコンピューターの構成を行います。 |
2 | コンピューターの構成は、DSC の状態が保留中または最新の場合にのみ行います。 これは、既定値です。 |

## <a name="see-also"></a>参照

この機能を使用して初回起動時に構成を実行する方法の例については、「[DSC を使用した初回起動時の仮想マシンの構成](bootstrapDsc.md)」をご覧ください。

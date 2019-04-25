---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 424e0b7a4d62fc35e5040a7e425950e887021d7e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085883"
---
# <a name="call-base-class-constructor"></a>基本クラス コンストラクターの呼び出し

サブクラスから基本クラス コンストラクターを呼び出すには、キーワード **base** を使用します。

```powershell
class A
{
    [int]$a

    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

[B]::new().a # return 103
```

基本クラスに既定の (パラメーターなし) コンストラクターがある場合は、明示的なコンストラクター呼び出しを省略できます。

```powershell
class C : B
{
    C([int]$c) {}
}
```

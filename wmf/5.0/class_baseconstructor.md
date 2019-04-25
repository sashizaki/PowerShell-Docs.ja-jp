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
# <a name="call-base-class-constructor"></a><span data-ttu-id="905dd-102">基本クラス コンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="905dd-102">Call Base Class Constructor</span></span>

<span data-ttu-id="905dd-103">サブクラスから基本クラス コンストラクターを呼び出すには、キーワード **base** を使用します。</span><span class="sxs-lookup"><span data-stu-id="905dd-103">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

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

<span data-ttu-id="905dd-104">基本クラスに既定の (パラメーターなし) コンストラクターがある場合は、明示的なコンストラクター呼び出しを省略できます。</span><span class="sxs-lookup"><span data-stu-id="905dd-104">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```

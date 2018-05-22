---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 9486fdbaeca66c83551564c76ce47482f77c36b9
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="call-base-class-constructor"></a><span data-ttu-id="507ef-102">基本クラス コンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="507ef-102">Call Base Class Constructor</span></span>

<span data-ttu-id="507ef-103">サブクラスから基本クラス コンストラクターを呼び出すには、キーワード **base** を使用します。</span><span class="sxs-lookup"><span data-stu-id="507ef-103">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

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

<span data-ttu-id="507ef-104">基本クラスに既定の (パラメーターなし) コンストラクターがある場合は、明示的なコンストラクター呼び出しを省略できます。</span><span class="sxs-lookup"><span data-stu-id="507ef-104">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```

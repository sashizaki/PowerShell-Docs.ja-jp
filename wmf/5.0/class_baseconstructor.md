---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 3269c8cc871f22488b64fb072dac72698983f360
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="call-base-class-constructor"></a><span data-ttu-id="70b42-102">基本クラス コンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="70b42-102">Call Base Class Constructor</span></span>

<span data-ttu-id="70b42-103">サブクラスから基本クラス コンストラクターを呼び出すには、キーワード **base** を使用します。</span><span class="sxs-lookup"><span data-stu-id="70b42-103">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

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

<span data-ttu-id="70b42-104">基本クラスに既定の (パラメーターなし) コンストラクターがある場合は、明示的なコンストラクター呼び出しを省略できます。</span><span class="sxs-lookup"><span data-stu-id="70b42-104">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```
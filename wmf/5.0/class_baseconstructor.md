---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 403a79e17b832b5c58fd21a138fcebb8adb76d40
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="call-base-class-constructor"></a><span data-ttu-id="abe55-102">基本クラス コンストラクターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="abe55-102">Call Base Class Constructor</span></span>

<span data-ttu-id="abe55-103">サブクラスから基本クラス コンストラクターを呼び出すには、キーワード **base** を使用します。</span><span class="sxs-lookup"><span data-stu-id="abe55-103">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

```PowerShell
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

<span data-ttu-id="abe55-104">基本クラスに既定の (パラメーターなし) コンストラクターがある場合は、明示的なコンストラクター呼び出しを省略できます。</span><span class="sxs-lookup"><span data-stu-id="abe55-104">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```PowerShell
class C : B
{
    C([int]$c) {}
}
```


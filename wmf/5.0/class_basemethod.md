---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: d7aec1a2ba8964e877ddd7406609fe135b1eb462
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="call-base-class-method"></a><span data-ttu-id="7d5a7-102">基本クラス メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="7d5a7-102">Call Base Class Method</span></span>

<span data-ttu-id="7d5a7-103">サブクラスで既存のメソッドをオーバーライドすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d5a7-103">You can override existing methods in subclasses.</span></span> <span data-ttu-id="7d5a7-104">そのためには、同じ名前およびシグネチャを使用してメソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="7d5a7-104">To do this, declare methods by using the same name and signature:</span></span>

```powershell
class baseClass
{
    [int]foo() {return 100500}
}

class childClass1 : baseClass
{
    [int]foo() {return 200600}
}

[childClass1]::new().foo() # return 200600
```

<span data-ttu-id="7d5a7-105">オーバーライドされた実装から基本クラス メソッドを呼び出すには、呼び出し時に基本クラスにキャストします ([baseClass]$this)。</span><span class="sxs-lookup"><span data-stu-id="7d5a7-105">To call base class methods from overridden implementations, cast to the base class ([baseClass]$this) on invocation:</span></span>

```powershell
class childClass2 : baseClass
{
    [int]foo()
    {
        return 3 * ([baseClass]$this).foo()
    }
}

[childClass2]::new().foo() # return 301500
```

<span data-ttu-id="7d5a7-106">すべての PowerShell メソッドは仮想です。</span><span class="sxs-lookup"><span data-stu-id="7d5a7-106">All PowerShell methods are virtual.</span></span> <span data-ttu-id="7d5a7-107">オーバーライドの場合と同じ構文を使用して、サブクラスで非仮想 .NET メソッドを非表示にできます。同じ名前およびシグネチャを持つメソッドを宣言するだけです。</span><span class="sxs-lookup"><span data-stu-id="7d5a7-107">You can hide non-virtual .NET methods in a subclass by using the same syntax as you do for an override: just declare methods with same name and signature.</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{
    # Add is final in system.collections.generic.list
    [void] Add([int]$arg)
    {
        ([system.collections.generic.list[int]]$this).Add($arg * 2)
    }
}

$list = [MyIntList]::new()
$list.Add(100)
$list[0] # return 200
```

---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: d7aec1a2ba8964e877ddd7406609fe135b1eb462
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219744"
---
# <a name="call-base-class-method"></a>基本クラス メソッドの呼び出し

サブクラスで既存のメソッドをオーバーライドすることができます。 そのためには、同じ名前およびシグネチャを使用してメソッドを宣言します。

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

オーバーライドされた実装から基本クラス メソッドを呼び出すには、呼び出し時に基本クラスにキャストします ([baseClass]$this)。

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

すべての PowerShell メソッドは仮想です。 オーバーライドの場合と同じ構文を使用して、サブクラスで非仮想 .NET メソッドを非表示にできます。同じ名前およびシグネチャを持つメソッドを宣言するだけです。

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

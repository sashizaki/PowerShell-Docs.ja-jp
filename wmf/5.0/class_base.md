---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 8b3ebd22e03bf9bdd5f26965137a1b1ce9f47c3e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058779"
---
# <a name="declare-base-class"></a><span data-ttu-id="a5a70-102">基本クラスの宣言</span><span class="sxs-lookup"><span data-stu-id="a5a70-102">Declare Base Class</span></span>
<span data-ttu-id="a5a70-103">Windows PowerShell クラスを別の Windows PowerShell クラスの基本型として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a5a70-103">You can declare a Windows PowerShell class as a base type for another Windows PowerShell class.</span></span>

```powershell
class bar
{
   [int]foo()
       {
           return 100500
       }
}

class baz : bar {}

[baz]::new().foo() # return 100500
```

<span data-ttu-id="a5a70-104">既存の .NET Framework 型を基本クラスとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5a70-104">You can also use existing .NET Framework types as base classes:</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{

}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```

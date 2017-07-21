---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: fc517cd204b8f2647b824f0b9ee8f0f8f62fb821
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="declare-base-class"></a><span data-ttu-id="c597f-102">基本クラスの宣言</span><span class="sxs-lookup"><span data-stu-id="c597f-102">Declare Base Class</span></span>
<span data-ttu-id="c597f-103">Windows PowerShell クラスを別の Windows PowerShell クラスの基本型として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c597f-103">You can declare a Windows PowerShell class as a base type for another Windows PowerShell class.</span></span>

```PowerShell
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

<span data-ttu-id="c597f-104">既存の .NET Framework 型を基本クラスとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c597f-104">You can also use existing .NET Framework types as base classes:</span></span>

```PowerShell
class MyIntList : system.collections.generic.list[int]
{
    
}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```


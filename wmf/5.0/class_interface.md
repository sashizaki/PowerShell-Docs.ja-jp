---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: e503f9a4462e94fce42ffcdcc0976d261c051f87
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="declare-implemented-interface"></a><span data-ttu-id="177a3-102">実装されたインターフェイスの宣言</span><span class="sxs-lookup"><span data-stu-id="177a3-102">Declare Implemented Interface</span></span>

<span data-ttu-id="177a3-103">基本型が指定されていない場合、基本型の後、またはコロン (:) の直後に、実装されたインターフェイスを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="177a3-103">You can declare implemented interfaces after base types, or immediately after a colon (:), if there is no base type specified.</span></span> <span data-ttu-id="177a3-104">コンマを使用してすべての型名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="177a3-104">Separate all type names by using commas.</span></span> <span data-ttu-id="177a3-105">C# の構文とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="177a3-105">It’s very similar to C# syntax.</span></span>

```PowerShell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableBar : bar, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```


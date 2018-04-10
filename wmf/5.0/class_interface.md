---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 2c007321789ae22b4a2e048d2d64162b065f9a75
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="declare-implemented-interface"></a><span data-ttu-id="319b5-102">実装されたインターフェイスの宣言</span><span class="sxs-lookup"><span data-stu-id="319b5-102">Declare Implemented Interface</span></span>

<span data-ttu-id="319b5-103">基本型が指定されていない場合、基本型の後、またはコロン (:) の直後に、実装されたインターフェイスを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="319b5-103">You can declare implemented interfaces after base types, or immediately after a colon (:), if there is no base type specified.</span></span> <span data-ttu-id="319b5-104">コンマを使用してすべての型名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="319b5-104">Separate all type names by using commas.</span></span> <span data-ttu-id="319b5-105">C# の構文とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="319b5-105">It’s very similar to C# syntax.</span></span>

```powershell
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
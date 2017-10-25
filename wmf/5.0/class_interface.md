---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 968e78beb8df77588a08a9ce8732e4abcadde4d0
ms.sourcegitcommit: a5c0795ca6ec9332967bff9c151a8572feb1a53a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2017
---
# <a name="declare-implemented-interface"></a><span data-ttu-id="80d39-102">実装されたインターフェイスの宣言</span><span class="sxs-lookup"><span data-stu-id="80d39-102">Declare Implemented Interface</span></span>

<span data-ttu-id="80d39-103">基本型が指定されていない場合、基本型の後、またはコロン (:) の直後に、実装されたインターフェイスを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="80d39-103">You can declare implemented interfaces after base types, or immediately after a colon (:), if there is no base type specified.</span></span> <span data-ttu-id="80d39-104">コンマを使用してすべての型名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="80d39-104">Separate all type names by using commas.</span></span> <span data-ttu-id="80d39-105">C# の構文とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="80d39-105">It’s very similar to C# syntax.</span></span>

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


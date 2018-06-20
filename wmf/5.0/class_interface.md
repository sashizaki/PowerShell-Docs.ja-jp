---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 116f79a95126d0a1c579a95ec99eb5d8b75cc1e0
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34225489"
---
# <a name="declare-implemented-interface"></a><span data-ttu-id="1614f-102">実装されたインターフェイスの宣言</span><span class="sxs-lookup"><span data-stu-id="1614f-102">Declare Implemented Interface</span></span>

<span data-ttu-id="1614f-103">基本型が指定されていない場合、基本型の後、またはコロン (:) の直後に、実装されたインターフェイスを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="1614f-103">You can declare implemented interfaces after base types, or immediately after a colon (:), if there is no base type specified.</span></span> <span data-ttu-id="1614f-104">コンマを使用してすべての型名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="1614f-104">Separate all type names by using commas.</span></span> <span data-ttu-id="1614f-105">C# の構文とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="1614f-105">It’s very similar to C# syntax.</span></span>

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

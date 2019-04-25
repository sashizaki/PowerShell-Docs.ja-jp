---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 4b593e9a1eca43ee7ad85fc921ae3c1d62722db9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085863"
---
# <a name="declare-implemented-interface"></a><span data-ttu-id="1af7a-102">実装されたインターフェイスの宣言</span><span class="sxs-lookup"><span data-stu-id="1af7a-102">Declare Implemented Interface</span></span>

<span data-ttu-id="1af7a-103">基本型が指定されていない場合、基本型の後、またはコロン (:) の直後に、実装されたインターフェイスを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="1af7a-103">You can declare implemented interfaces after base types, or immediately after a colon (:), if there is no base type specified.</span></span> <span data-ttu-id="1af7a-104">コンマを使用してすべての型名を区切ります。</span><span class="sxs-lookup"><span data-stu-id="1af7a-104">Separate all type names by using commas.</span></span> <span data-ttu-id="1af7a-105">C# の構文とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="1af7a-105">It’s very similar to C# syntax.</span></span>

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

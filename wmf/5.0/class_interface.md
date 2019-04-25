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
# <a name="declare-implemented-interface"></a>実装されたインターフェイスの宣言

基本型が指定されていない場合、基本型の後、またはコロン (:) の直後に、実装されたインターフェイスを宣言することができます。 コンマを使用してすべての型名を区切ります。 C# の構文とよく似ています。

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

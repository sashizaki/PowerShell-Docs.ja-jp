---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 5dbaa126cf9ae3917c3a8787ffc5ef5ac77b19c1
ms.sourcegitcommit: a5c0795ca6ec9332967bff9c151a8572feb1a53a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2017
---
# <a name="declare-base-class"></a>基本クラスの宣言
Windows PowerShell クラスを別の Windows PowerShell クラスの基本型として宣言できます。

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

既存の .NET Framework 型を基本クラスとして使用することもできます。

```powershell
class MyIntList : system.collections.generic.list[int]
{
    
}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```


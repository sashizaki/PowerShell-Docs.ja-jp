---
title: 表示データの書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38971643-2a3d-4f5b-a1fa-6334c162b8ed
caps.latest.revision: 4
ms.openlocfilehash: e915ac71feb50cb58cfa9195f0de94763affdb77
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363701"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="5df26-102">表示されるデータの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="5df26-102">Formatting Displayed Data</span></span>

<span data-ttu-id="5df26-103">リスト、テーブル、またはワイドビュー内の個々のデータポイントを表示する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5df26-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="5df26-104">ビューの項目を定義するときに `FormatString` 要素を使用することも、`ScriptBlock` 要素を使用してデータに対して `FormatString` メソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="5df26-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="5df26-105">FormatString 要素の使用</span><span class="sxs-lookup"><span data-stu-id="5df26-105">Using the FormatString Element</span></span>

<span data-ttu-id="5df26-106">次の例で[は、system.string オブジェクトの](/dotnet/api/System.Diagnostics.Process)`TotalProcessorTime` プロパティの値が FormatString 要素を使用して書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="5df26-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="5df26-107">`TotalProcessorTime` プロパティ</span><span class="sxs-lookup"><span data-stu-id="5df26-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```




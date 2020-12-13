---
ms.date: 09/12/2016
ms.topic: reference
title: 表示されるデータの書式を設定する
description: 表示されるデータの書式を設定する
ms.openlocfilehash: 40f6b3b4fa36062ee0bad3f197ad159f571445c8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667863"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="98349-103">表示されるデータの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="98349-103">Formatting Displayed Data</span></span>

<span data-ttu-id="98349-104">リスト、テーブル、またはワイドビュー内の個々のデータポイントを表示する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="98349-104">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="98349-105">ビューの項目を定義するときに要素を使用することも、要素を使用して `FormatString` `ScriptBlock` `FormatString` データに対してメソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="98349-105">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="98349-106">FormatString 要素の使用</span><span class="sxs-lookup"><span data-stu-id="98349-106">Using the FormatString Element</span></span>

<span data-ttu-id="98349-107">次の例では、system.string `TotalProcessorTime` オブジェクトのプロパティの[](/dotnet/api/System.Diagnostics.Process)値が FormatString 要素を使用して書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="98349-107">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="98349-108">`TotalProcessorTime`プロパティ</span><span class="sxs-lookup"><span data-stu-id="98349-108">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```

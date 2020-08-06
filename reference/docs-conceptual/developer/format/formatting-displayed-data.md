---
title: 表示データの書式設定 |Microsoft Docs
ms.date: 09/12/2016
ms.openlocfilehash: 97d23b3079b2779e518b6b6d2f2ac0c5e9d1f3a3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781513"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="94359-102">表示されるデータの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="94359-102">Formatting Displayed Data</span></span>

<span data-ttu-id="94359-103">リスト、テーブル、またはワイドビュー内の個々のデータポイントを表示する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="94359-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="94359-104">ビューの項目を定義するときに要素を使用することも、要素を使用して `FormatString` `ScriptBlock` `FormatString` データに対してメソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="94359-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="94359-105">FormatString 要素の使用</span><span class="sxs-lookup"><span data-stu-id="94359-105">Using the FormatString Element</span></span>

<span data-ttu-id="94359-106">次の例では、system.string `TotalProcessorTime` オブジェクトのプロパティの[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)値が FormatString 要素を使用して書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="94359-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="94359-107">`TotalProcessorTime`プロパティ</span><span class="sxs-lookup"><span data-stu-id="94359-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```

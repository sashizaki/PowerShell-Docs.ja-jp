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
ms.openlocfilehash: 9f3a3176ae16ac7c014cadce6b4e856f9bd3b5da
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560391"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="79ed9-102">表示されるデータの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="79ed9-102">Formatting Displayed Data</span></span>

<span data-ttu-id="79ed9-103">リスト、テーブル、またはワイドビュー内の個々のデータポイントを表示する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="79ed9-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="79ed9-104">ビューの項目を定義するときに要素を使用することも、要素を使用して `FormatString` `ScriptBlock` `FormatString` データに対してメソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="79ed9-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="79ed9-105">FormatString 要素の使用</span><span class="sxs-lookup"><span data-stu-id="79ed9-105">Using the FormatString Element</span></span>

<span data-ttu-id="79ed9-106">次の例では、system.string `TotalProcessorTime` オブジェクトのプロパティの[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)値が FormatString 要素を使用して書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="79ed9-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="79ed9-107">`TotalProcessorTime`プロパティ</span><span class="sxs-lookup"><span data-stu-id="79ed9-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```

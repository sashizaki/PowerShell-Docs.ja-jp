---
title: 表示されるデータの書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38971643-2a3d-4f5b-a1fa-6334c162b8ed
caps.latest.revision: 4
ms.openlocfilehash: e915ac71feb50cb58cfa9195f0de94763affdb77
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065667"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="b200a-102">表示されるデータの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="b200a-102">Formatting Displayed Data</span></span>

<span data-ttu-id="b200a-103">一覧、テーブル、または表示幅が広い個々 のデータ ポイントの表示方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b200a-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="b200a-104">使用することができます、 `FormatString` 、ビューのアイテムを定義するときに要素を使用できます、`ScriptBlock`要素を呼び出す、`FormatString`データ上のメソッド。</span><span class="sxs-lookup"><span data-stu-id="b200a-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="b200a-105">FormatString 要素の使用</span><span class="sxs-lookup"><span data-stu-id="b200a-105">Using the FormatString Element</span></span>

<span data-ttu-id="b200a-106">次の例では、値での`TotalProcessorTime`のプロパティ、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) FormatString 要素を使用して、オブジェクトが書式設定します。</span><span class="sxs-lookup"><span data-stu-id="b200a-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="b200a-107">`TotalProcessorTime`プロパティ</span><span class="sxs-lookup"><span data-stu-id="b200a-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```




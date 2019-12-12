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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363701"
---
# <a name="formatting-displayed-data"></a>表示されるデータの書式を設定する

リスト、テーブル、またはワイドビュー内の個々のデータポイントを表示する方法を指定できます。 ビューの項目を定義するときに `FormatString` 要素を使用することも、`ScriptBlock` 要素を使用してデータの `FormatString` メソッドを呼び出すこともできます。

## <a name="using-the-formatstring-element"></a>FormatString 要素の使用

次の例で[は、system.string オブジェクトの](/dotnet/api/System.Diagnostics.Process)`TotalProcessorTime` プロパティの値が FormatString 要素を使用して書式設定されています。 `TotalProcessorTime` プロパティ

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```




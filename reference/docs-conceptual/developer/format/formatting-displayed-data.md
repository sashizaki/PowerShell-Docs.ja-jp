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
# <a name="formatting-displayed-data"></a>表示されるデータの書式を設定する

リスト、テーブル、またはワイドビュー内の個々のデータポイントを表示する方法を指定できます。 ビューの項目を定義するときに要素を使用することも、要素を使用して `FormatString` `ScriptBlock` `FormatString` データに対してメソッドを呼び出すこともできます。

## <a name="using-the-formatstring-element"></a>FormatString 要素の使用

次の例では、system.string `TotalProcessorTime` オブジェクトのプロパティの[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)値が FormatString 要素を使用して書式設定されています。 `TotalProcessorTime`プロパティ

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```

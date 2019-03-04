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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854988"
---
# <a name="formatting-displayed-data"></a>表示されるデータの書式を設定する

一覧、テーブル、または表示幅が広い個々 のデータ ポイントの表示方法を指定できます。 使用することができます、 `FormatString` 、ビューのアイテムを定義するときに要素を使用できます、`ScriptBlock`要素を呼び出す、`FormatString`データ上のメソッド。

## <a name="using-the-formatstring-element"></a>FormatString 要素の使用

次の例では、値での`TotalProcessorTime`のプロパティ、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) FormatString 要素を使用して、オブジェクトが書式設定します。 `TotalProcessorTime`プロパティ

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```




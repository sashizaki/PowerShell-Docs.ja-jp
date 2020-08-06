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

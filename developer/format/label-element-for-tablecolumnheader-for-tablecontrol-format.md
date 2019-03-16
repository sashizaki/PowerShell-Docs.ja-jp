---
title: TableControl (形式) の TableColumnHeader の要素にラベルを付ける |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7196f039-2f6a-41fd-b252-5b1623ebb9f9
caps.latest.revision: 11
ms.openlocfilehash: 09183a538c179f19347c3f1ed45b4ad38c2ca451
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054511"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a>TableControl の TableColumnHeader の Label 要素 (書式)

列の上部に表示されるラベルを定義します。 この要素は、テーブル ビューを定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableHeaders 要素の要素に TableControl (形式) TableColumnHeader TableHeaders の TableControl (形式) ラベル要素のTableControl (形式) の TableColumnHeader

## <a name="syntax"></a>構文

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Label`要素。 1 つだけのラベルには、各列は使用できます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableControl (形式) の TableHeaders TableColumnHeader 要素](./tablecolumnheader-element-format.md)|ラベル、幅、およびテーブルの列のデータのアラインメントを定義します。|

## <a name="text-value"></a>テキスト値

テーブルの列の上部に表示されるテキストを指定します。 列のラベルの文字の制限はありません。

## <a name="remarks"></a>コメント

ラベルが指定されていない場合は、行の値を持つが表示されるプロパティの名前が使用されます。

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="example"></a>例

この例では、`TableColumnHeader`要素のラベルは"Column 1"です。

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>参照

[テーブル ビューを作成します。](./creating-a-table-view.md)

[TableColumnHeader 要素 (形式)](./tablecolumnheader-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

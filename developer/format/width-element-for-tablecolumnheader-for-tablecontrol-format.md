---
title: TableControl (形式) の TableColumnHeader 幅要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94eb0535-8002-4f17-9a2b-4be75ec20e5c
caps.latest.revision: 18
ms.openlocfilehash: a38fcbef457e69e3ea08d25ba3a9843621036f1e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853108"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a>TableControl の TableColumnHeader の Width 要素 (書式)

列の幅 (文字) で定義します。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableHeaders の構成要素の Width 要素によって TableControl (形式) の TableColumnHeader 要素 TableHeaders を TableControl (形式)TableControl (形式) の TableColumnHeader

## <a name="syntax"></a>構文

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Width`列ヘッダーを定義するときに使用される要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TbleControl (形式) の TableHeaders TableColumnHeader 要素](./tablecolumnheader-element-format.md)|ラベル、幅、およびテーブルの列のデータのアラインメントを定義します。|

## <a name="text-value"></a>テキスト値

すべての可能なである場合に、表示されるプロパティの値の長さを超えている (文字) で幅を指定します。

## <a name="remarks"></a>コメント

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="example"></a>例

次の例は、`TableColumnHeader`要素の幅が 16 文字です。

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>参照

[テーブル ビューを作成します。](./creating-a-table-view.md)

[TableControl (形式) の TableHeader TableColumnHeader 要素](./tablecolumnheader-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
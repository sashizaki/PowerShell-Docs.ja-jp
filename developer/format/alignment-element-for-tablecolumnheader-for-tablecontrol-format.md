---
title: TableColumnHeader TableControl (形式) の要素の配置 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff85e83a-c9c2-4c37-accc-e6a27c182f3c
caps.latest.revision: 19
ms.openlocfilehash: 16b41535109ca503e679a135f5ba30054e33de5b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853758"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a>TableControl の TableColumnHeader の Alignment 要素 (書式)

列ヘッダー内のデータを表示する方法を定義します。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableHeaders 要素 (形式) TableColumnHeader 要素 (形式) の配置の構成要素 TableColumnHeader (形式)

## <a name="syntax"></a>構文

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Alignment`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableColumnHeader 要素 (形式)](./tablecolumnheader-element-format.md)|ラベル、幅、およびテーブルの列のデータのアラインメントを定義します。|

## <a name="text-value"></a>テキスト値

次の値のいずれかを指定します。 これらの値は区別されません。

この要素が指定されていない場合、既定値は、これは、左寄せで左側の列にデータが表示されます。

データは右寄せで右側の列に表示されます。

中央揃えの列に表示されるデータ。

## <a name="remarks"></a>コメント

テーブル ビューのコンポーネントに関する詳細については、[テーブル ビューを作成する](./creating-a-table-view.md)を参照してください。

## <a name="example"></a>例

この例では、`TableColumnHeader`要素のデータは、左側に揃えて配置します。

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

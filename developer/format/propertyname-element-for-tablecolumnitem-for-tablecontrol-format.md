---
title: TableControl (形式) の TableColumnItem PropertyName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb26d72c-2f77-4801-badf-0537ccc55e31
caps.latest.revision: 10
ms.openlocfilehash: 6e86b6a0874b385703121802bc8108a0410442cd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064615"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a>TableControl の TableColumnItem の PropertyName 要素 (書式)

行の列で値が表示されるプロパティを指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) TableColumnItems 要素 (形式) TableColumnItem 要素 (形式)TableColumnItem (形式) の PropertyName 要素

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableColumnItem 要素 (形式)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|プロパティまたは値を持つが、行の列に表示されているスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

値が表示されるプロパティの名前を指定します。

## <a name="remarks"></a>コメント

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="example"></a>例

この例では、`TableColumnItem`要素を指定する、`Status`のプロパティ、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>参照

[テーブル ビューを作成します。](./creating-a-table-view.md)

[TableColumnItem 要素 (形式)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

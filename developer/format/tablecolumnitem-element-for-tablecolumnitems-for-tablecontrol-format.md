---
title: TableControl (形式) の TableColumnItems TableColumnItem 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef8395aa-4b31-48c0-a0b8-b481fd0b3738
caps.latest.revision: 15
ms.openlocfilehash: 159f943f6bfb33c5403b5714380631351523789f
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056993"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a>TableControl の TableColumnItems の TableColumnItem 要素 (書式)

プロパティまたは値を持つが、行の列に表示されているスクリプトを定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素の要素に TableControl (形式) TableRowEntry TableRowEntries TableControl (形式) 用のTableControl (形式) の TableColumnItems の TableControl (形式) TableColumnItem 要素 TableControlEntry TableColumnItems 要素

## <a name="syntax"></a>構文

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`TableColumnItem`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[TableControl (形式) の TableColumnItem の alignment 要素](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> 行の列のデータを表示する方法を定義します。|
|[TableControl (形式) の TableColumnItem の FormatString 要素](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|行の列のデータを書式設定に使用される書式パターンを指定します。|
|[TableControl (形式) の TableColumnItem PropertyName 要素](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> 値が表示されるプロパティの名前を指定します。|
|[TableControl (形式) の TableColumnItem の ScriptBlock 要素](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> 行の列で値が表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableControl (形式) の TableControlEntry TableColumnItems 要素](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|プロパティまたは行の表示が値を持つスクリプトを定義します。|

## <a name="remarks"></a>コメント

行の各列では、オブジェクトまたはスクリプトのプロパティを指定できます。 子要素が指定されていない場合は、項目が、プレース ホルダーとデータは表示されません。

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="example"></a>例

この例では、`TableColumnItem`要素の値を表示する、`Status`のプロパティ、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a>参照

[テーブル ビューを作成します。](./creating-a-table-view.md)

[TableControl (形式) の TableColumnItem の alignment 要素](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[TableColumnItems 要素 (形式)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[TableControl (形式) の TableColumnItem の FormatString 要素](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[TableControl (形式) の TableColumnItem PropertyName 要素](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[TableControl (形式) の TableColumnItem の ScriptBlock 要素](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

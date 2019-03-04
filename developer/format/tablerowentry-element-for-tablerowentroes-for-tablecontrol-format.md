---
title: TableControl (形式) の TableRowEntroes TableRowEntry 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18d86af7-7ff9-4968-81be-2caa61937d49
caps.latest.revision: 10
ms.openlocfilehash: 001d46debde61f928c338b2f68112fb201f96216
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853588"
---
# <a name="tablerowentry-element-for-tablerowentroes-for-tablecontrol-format"></a>TableControl の TableRowEntries の TableRowEntry 要素 (書式)

テーブルの行に表示されるデータを定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素の要素に TableControl (形式) TableRowEntry TableRowEntries TableControl (形式) 用の

## <a name="syntax"></a>構文

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`TableRowEntry`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[TableControl (形式) の TableRowEntry EntrySelectedBy 要素](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|必須の要素。<br /><br /> プロパティ値が行に表示されるオブジェクトを定義します。|
|[TableControl (形式) の TableRowEntry TableColumnItems 要素](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|必須の要素。<br /><br /> プロパティまたは表示値を持つスクリプトを定義します。|
|[TableRowEntry の TableCntrol (形式) の要素にラップします。](./wrap-element-for-tablerowentry-for-tablecontrl-format.md)|省略可能な要素です。<br /><br /> 次の行を列の幅を超えるテキストが表示されることを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TableControl (形式) の TableRowEntries 要素](./tablerowentries-element-for-tablecontrol-format.md)|テーブルの行を定義します。|

## <a name="remarks"></a>コメント

1 つ`TableColumnItems`要素と 1 つ`EntrySelectedBy`要素を指定する必要があります。

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="example"></a>例

次の例は、`TableRowEntry`の 2 つのプロパティの値を表示する行を定義する要素、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName> Property for first column</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName> Property for second column</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a>参照

[テーブル ビューを作成します。](./creating-a-table-view.md)

[TableControl (形式) の TableRowEntry EntrySelectedBy 要素](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[TableControl (形式) の TableRowEntry TableColumnItems 要素](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[TableControl (形式) の TableRowEntries 要素](./tablerowentries-element-for-tablecontrol-format.md)

[TableControl (形式) の TableRowEntries TableRowEntry 要素](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)

[TableRowEntry の TableCntrol (形式) の要素にラップします。](./wrap-element-for-tablerowentry-for-tablecontrl-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

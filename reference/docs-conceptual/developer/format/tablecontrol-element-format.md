---
title: TableControl 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1550b068-dfbc-4ae0-9aa1-72c9a680ec59
caps.latest.revision: 15
ms.openlocfilehash: 3942c008e026b0b99db3c77af4a0152b50fffc4e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368201"
---
# <a name="tablecontrol-element-format"></a>TableControl 要素 (書式)

ビューのテーブル形式を定義します。

ViewDefinitions 要素 (Format) ビュー要素 (Format) TableControl 要素 (Format)

## <a name="syntax"></a>構文

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TableControl` 要素の属性、子要素、および親要素について説明します。 テーブルの行を指定する必要があります。 その他のすべての子要素は省略可能です。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[TableControl の AutoSize 要素 (Format)](./autosize-element-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。|
|[TableControl (Format) の HideTableHeaders 要素](./hidetableheaders-element-format.md)|省略可能な要素。<br /><br /> テーブルのヘッダーが表示されていないかどうかを示します。|
|[TableControl の TableHeaders 要素 (Format)](./tableheaders-element-format.md)|必須の要素です。<br /><br /> テーブルビューの列のデータのラベル、幅、および配置を定義します。|
|[TableControl (Format) の TableRowEntries 要素](./tablerowentries-element-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> テーブルビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[View 要素 (Format)](./view-element-format.md)|1つ以上のオブジェクトのメンバーを表示するために使用されるビューを定義します。|

## <a name="remarks"></a>コメント

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="example"></a>例

この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのプロパティを表示するために使用される @no__t 0 の要素を示しています。

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[View 要素 (Format)](./view-element-format.md)

[TableControl の AutoSize 要素 (Format)](./autosize-element-for-tablecontrol-format.md)

[HideTableHeaders 要素 (形式)](./hidetableheaders-element-format.md)

[TableHeaders 要素 (書式)](./tableheaders-element-format.md)

[TableRowEntries 要素 (Format)](./tablerowentries-element-for-tablecontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

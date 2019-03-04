---
title: TableControl 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1550b068-dfbc-4ae0-9aa1-72c9a680ec59
caps.latest.revision: 15
ms.openlocfilehash: dd48e82452e83f93e2e005c9db53bbc51d8b2eb4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858918"
---
# <a name="tablecontrol-element-format"></a>TableControl 要素 (書式)

ビューのテーブル形式を定義します。

ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式)

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

次のセクションでは、属性、子要素、およびの親要素について説明します、`TableControl`要素。 テーブルの行を指定する必要があります。 その他のすべての子要素は省略可能です。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[TableControl (形式) の AutoSize 要素](./autosize-element-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> かどうか、列のサイズと列の数が調整のデータのサイズを指定します。|
|[TableControl (形式) の HideTableHeaders 要素](./hidetableheaders-element-format.md)|省略可能な要素です。<br /><br /> テーブルのヘッダーは表示されないかどうかを示します。|
|[TableControl (形式) の TableHeaders 要素](./tableheaders-element-format.md)|必須の要素。<br /><br /> ラベル、幅、およびテーブル ビューの列のデータの配置を定義します。|
|[TableCotrol (形式) の TableRowEntries 要素](./tablerowentries-element-for-tablecontrol-format.md)|省略可能な要素です。<br /><br /> テーブル ビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー要素 (形式)](./view-element-format.md)|1 つまたは複数のオブジェクトのメンバーを表示するために使用するビューを定義します。|

## <a name="remarks"></a>コメント

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="example"></a>例

この例では、`TableControl`要素のプロパティを表示するために使用される、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。

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

[テーブル ビューを作成します。](./creating-a-table-view.md)

[ビュー要素 (形式)](./view-element-format.md)

[TableControl (形式) の AutoSize 要素](./autosize-element-for-tablecontrol-format.md)

[HideTableHeaders 要素 (形式)](./hidetableheaders-element-format.md)

[TableHeaders 要素 (形式)](./tableheaders-element-format.md)

[TableRowEntries 要素 (形式)](./tablerowentries-element-for-tablecontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

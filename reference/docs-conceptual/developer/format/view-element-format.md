---
title: View 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361461"
---
# <a name="view-element-format"></a>View 要素 (書式)

1つ以上の .NET オブジェクトを表示するビューを定義します。 書式設定ファイルで定義できるビューの数に制限はありません。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式)

## <a name="syntax"></a>構文

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`View` 要素の属性、子要素、および親要素について説明します。 コントロールの子要素を1つだけ指定し、ビューの名前とビューを使用するオブジェクトを指定する必要があります。 カスタムコントロールの定義、オブジェクトのグループ化、およびビューが帯域外であるかどうかの指定はオプションです。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[View (Format) の Controls 要素](./controls-element-for-view-format.md)|省略可能な要素。<br /><br /> ビュー内から名前で参照できるコントロールのセットを定義します。|
|[CustomControl 要素 (Format)](./customcontrol-element-for-groupby-format.md)|省略可能な要素。<br /><br /> ビューのカスタムコントロール形式を定義します。|
|[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)|省略可能な要素。<br /><br /> .NET オブジェクトのメンバーをグループ化する方法を定義します。|
|[ListControl 要素 (Format)](./listcontrol-element-format.md)|省略可能な要素。<br /><br /> ビューのリスト形式を定義します。|
|[ビューの Name 要素 (Format)](./name-element-for-view-format.md)|必須の要素です。<br /><br /> ビューを参照するために使用する名前を指定します。|
|[TableControl 要素 (形式)](./tablecontrol-element-format.md)|省略可能な要素。<br /><br /> ビューのテーブル形式を定義します。|
|[View (Format) の ViewSelectedBy 要素](./viewselectedby-element-format.md)|必須の要素です。<br /><br /> このビューに表示される .NET オブジェクトを定義します。|
|[WideControl 要素 (Format)](./widecontrol-element-format.md)|省略可能な要素。<br /><br /> ビューのワイド (単一値) リスト形式を定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ViewDefinitions 要素 (形式)](./viewdefinitions-element-format.md)|オブジェクトを表示するために使用するビューを定義します。|

## <a name="remarks"></a>コメント

さまざまなビューとカスタムコントロールのコンポーネントの詳細については、次のトピックを参照してください。

- [テーブルビューのコンポーネント](./creating-a-table-view.md)

- [リストビューのコンポーネント](./creating-a-list-view.md)

- [ワイドビューコンポーネント](./creating-a-wide-view.md)

- [カスタムコントロール](./creating-custom-controls.md)

## <a name="example"></a>例

この例は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのテーブルビューを定義する @no__t 0 の要素を示しています。

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a>参照

[ViewDefinitions 要素 (形式)](./viewdefinitions-element-format.md)

[ビューの Name 要素 (Format)](./name-element-for-view-format.md)

[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)

[View (Format) の Controls 要素](./controls-element-for-view-format.md)

[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

[TableControl 要素 (形式)](./tablecontrol-element-format.md)

[ListControl 要素 (Format)](./listcontrol-element-format.md)

[WideControl 要素 (Format)](./widecontrol-element-format.md)

[CustomControl 要素 (Format)](./customcontrol-element-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

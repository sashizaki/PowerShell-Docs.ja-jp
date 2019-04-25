---
title: 要素 (形式) の表示 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083724"
---
# <a name="view-element-format"></a>View 要素 (書式)

1 つまたは複数の .NET オブジェクトを表示するビューを定義します。 書式設定ファイルで定義できるビューの数に制限はありません。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式)

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

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`View`要素。 コントロールの子要素の 1 つだけを指定する必要があり、ビューとビューを使用しているオブジェクトの名前を指定する必要があります。 カスタム コントロールを定義するには、オブジェクトをグループ化する方法、および、帯域外のかどうか、ビューには指定は省略可能です。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) のコントロール要素](./controls-element-for-view-format.md)|省略可能な要素です。<br /><br /> ビュー内からの名前で参照できるコントロールのセットを定義します。|
|[カスタム コントロール要素 (形式)](./customcontrol-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> ビューのカスタム コントロールの書式を定義します。|
|[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)|省略可能な要素です。<br /><br /> .NET オブジェクトのメンバーをグループ化する方法を定義します。|
|[ListControl 要素 (形式)](./listcontrol-element-format.md)|省略可能な要素です。<br /><br /> ビューの一覧の形式を定義します。|
|[ビュー (形式) の name 要素](./name-element-for-view-format.md)|必須の要素。<br /><br /> ビューを参照するための名前を指定します。|
|[TableControl 要素 (形式)](./tablecontrol-element-format.md)|省略可能な要素です。<br /><br /> ビューのテーブル形式を定義します。|
|[表示 (形式) ViewSelectedBy 要素](./viewselectedby-element-format.md)|必須の要素。<br /><br /> このビューを表示する .NET オブジェクトを定義します。|
|[WideControl 要素 (形式)](./widecontrol-element-format.md)|省略可能な要素です。<br /><br /> ワイド (1 つの値) を定義するビューの一覧の形式。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ViewDefinitions 要素 (形式)](./viewdefinitions-element-format.md)|オブジェクトを表示するために使用するビューを定義します。|

## <a name="remarks"></a>コメント

さまざまなビューとカスタム コントロールのコンポーネントに関する詳細については、次のトピックを参照してください。

- [テーブル ビュー コンポーネント](./creating-a-table-view.md)

- [ビュー コンポーネントの一覧](./creating-a-list-view.md)

- [表示幅が広いコンポーネント](./creating-a-wide-view.md)

- [カスタム コントロール](./creating-custom-controls.md)

## <a name="example"></a>例

この例では、`View`のテーブル ビューを定義する要素、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。

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

[ビュー (形式) の name 要素](./name-element-for-view-format.md)

[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)

[ビュー (形式) のコントロール要素](./controls-element-for-view-format.md)

[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)

[TableControl 要素 (形式)](./tablecontrol-element-format.md)

[ListControl 要素 (形式)](./listcontrol-element-format.md)

[WideControl 要素 (形式)](./widecontrol-element-format.md)

[カスタム コントロール要素 (形式)](./customcontrol-element-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

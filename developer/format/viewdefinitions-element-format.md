---
title: ViewDefinitions 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29840c10-2b30-4bb1-a8a0-ddf84d19c2d0
caps.latest.revision: 18
ms.openlocfilehash: c5ec80350c7707ccd41112ab5e1952e5dc198cca
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083707"
---
# <a name="viewdefinitions-element-format"></a>ViewDefinitions 要素 (書式)

.NET オブジェクトを表示するために使用するビューを定義します。 これらのビューでは、プロパティとオブジェクトのスクリプトの値をテーブル形式、一覧の形式、ワイド形式、およびカスタム コントロールの形式で表示できます。

構成要素 (形式) (XML 形式) ViewDefinitions 要素

## <a name="syntax"></a>構文

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ViewDefinitions`要素。 書式設定ファイルで定義できるビューの数に制限はありませんし、任意の順序で追加できます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ビュー要素 (形式)](./view-element-format.md)|1 つまたは複数の .NET オブジェクトを表示するために使用するビューを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成要素 (形式)](./configuration-element-format.md)|書式設定ファイルの最上位の要素を表します。|

## <a name="remarks"></a>コメント

ビューのさまざまな種類のコンポーネントの詳細については、次のトピックを参照してください。

- [テーブル ビューを作成します。](./creating-a-table-view.md)

- [リスト ビューの作成](./creating-a-list-view.md)

- [ワイド ビューを作成します。](./creating-a-wide-view.md)

- [カスタム コントロール](./creating-custom-controls.md)

## <a name="example"></a>例

この例では、`ViewDefinitions`テーブル ビューとリスト ビューの親要素を含む要素。

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a>参照

[構成要素 (形式)](./configuration-element-format.md)

[ビュー要素 (形式)](./view-element-format.md)

[テーブル ビューを作成します。](./creating-a-table-view.md)

[リスト ビューの作成](./creating-a-list-view.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[カスタム コントロール](./creating-custom-controls.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

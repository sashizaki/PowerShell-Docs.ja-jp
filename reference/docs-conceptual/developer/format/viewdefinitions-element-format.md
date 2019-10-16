---
title: ViewDefinitions 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29840c10-2b30-4bb1-a8a0-ddf84d19c2d0
caps.latest.revision: 18
ms.openlocfilehash: c5ec80350c7707ccd41112ab5e1952e5dc198cca
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361421"
---
# <a name="viewdefinitions-element-format"></a>ViewDefinitions 要素 (書式)

.NET オブジェクトの表示に使用するビューを定義します。 これらのビューでは、オブジェクトのプロパティとスクリプト値をテーブル形式、リスト形式、ワイド形式、およびカスタムコントロール形式で表示できます。

Configuration 要素 (Format) ViewDefinitions (フォーマット XML) 要素

## <a name="syntax"></a>構文

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ViewDefinitions` 要素の属性、子要素、および親要素について説明します。 書式設定ファイルで定義できるビューの数に制限はありません。また、任意の順序で追加することもできます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[View 要素 (Format)](./view-element-format.md)|1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration 要素 (形式)](./configuration-element-format.md)|書式設定ファイルのトップレベルの要素を表します。|

## <a name="remarks"></a>コメント

さまざまな種類のビューのコンポーネントの詳細については、次のトピックを参照してください。

- [テーブルビューの作成](./creating-a-table-view.md)

- [リストビューの作成](./creating-a-list-view.md)

- [ワイドビューの作成](./creating-a-wide-view.md)

- [カスタムコントロール](./creating-custom-controls.md)

## <a name="example"></a>例

この例は、テーブルビューとリストビューの親要素を含む @no__t 0 の要素を示しています。

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

[Configuration 要素 (形式)](./configuration-element-format.md)

[View 要素 (Format)](./view-element-format.md)

[テーブルビューの作成](./creating-a-table-view.md)

[リストビューの作成](./creating-a-list-view.md)

[ワイドビューの作成](./creating-a-wide-view.md)

[カスタムコントロール](./creating-custom-controls.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

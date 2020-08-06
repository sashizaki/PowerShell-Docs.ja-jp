---
title: ViewDefinitions 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a108c4f8b03e3dec3905181b390aee2c82ab0028
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772486"
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

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ViewDefinitions` ます。 書式設定ファイルで定義できるビューの数に制限はありません。また、任意の順序で追加することもできます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[View 要素 (書式)](./view-element-format.md)|1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[Configuration 要素 (書式)](./configuration-element-format.md)|書式設定ファイルのトップレベルの要素を表します。|

## <a name="remarks"></a>解説

さまざまな種類のビューのコンポーネントの詳細については、次のトピックを参照してください。

- [テーブル ビューを作成する](./creating-a-table-view.md)

- [リスト ビューを作成する](./creating-a-list-view.md)

- [ワイド ビューを作成する](./creating-a-wide-view.md)

- [カスタムコントロール](./creating-custom-controls.md)

## <a name="example"></a>例

この例は、 `ViewDefinitions` テーブルビューとリストビューの親要素を含む要素を示しています。

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

[Configuration 要素 (書式)](./configuration-element-format.md)

[View 要素 (書式)](./view-element-format.md)

[テーブル ビューを作成する](./creating-a-table-view.md)

[リスト ビューを作成する](./creating-a-list-view.md)

[ワイド ビューを作成する](./creating-a-wide-view.md)

[カスタムコントロール](./creating-custom-controls.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

---
title: ビューの Name 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a31010d-1db9-44ae-a7f3-6ed32cb641cb
caps.latest.revision: 16
ms.openlocfilehash: 097d20cb6a04635124d1f96823248df6095ca1af
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362641"
---
# <a name="name-element-for-view-format"></a>View の Name 要素 (書式)

ビューを識別するために使用される名前を指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) Name 要素 (形式)

## <a name="syntax"></a>構文

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Name` 要素の属性、子要素、および親要素について説明します。 各ビューには、1つの `Name` 要素のみが許可されます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View 要素 (Format)](./view-element-format.md)|1つ以上の .NET オブジェクトのメンバーを表示するために使用されるビューを定義します。|

## <a name="text-value"></a>テキスト値

ビューの一意の表示名を指定します。 この名前には、ビューの種類 (テーブルビューやリストビューなど) への参照、ビューを使用するオブジェクトまたはオブジェクトのセット、オブジェクトを返すコマンド、またはこれらの組み合わせを含めることができます。

## <a name="remarks"></a>コメント

さまざまな種類のビューの詳細については、次のトピックを参照してください。[テーブルビュー](./creating-a-table-view.md)、[リストビュー](./creating-a-list-view.md)、[ワイドビュー](./creating-a-wide-view.md)、および[カスタムビュー](./creating-custom-controls.md)です。

## <a name="example"></a>例

[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトのテーブルビューを定義する `View` 要素の例を次に示します。 ビューの名前は "service" です。

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a>関連項目

[リストビューの作成](./creating-a-list-view.md)

[テーブルビューの作成](./creating-a-table-view.md)

[ワイドビューの作成](./creating-a-wide-view.md)

[カスタムコントロールの作成](./creating-custom-controls.md)

[View 要素 (Format)](./view-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

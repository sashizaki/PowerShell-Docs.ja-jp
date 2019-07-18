---
title: ViewSelectedBy 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083826"
---
# <a name="viewselectedby-element-format"></a>ViewSelectedBy 要素 (書式)

ビューが表示されている .NET オブジェクトを定義します。 それぞれのビューには、少なくとも 1 つの .NET オブジェクトを指定する必要があります。

ViewDefinitions 要素 (形式) 表示要素 (形式) ViewSelectedBy 要素 (形式)

## <a name="syntax"></a>構文

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ViewSelectedBy`要素。 この要素には、少なくとも 1 つ含める必要があります`TypeName`または`SelectionSetName`子要素。 指定できる子要素の数に制限はありません、順序は重要ではもします。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ViewSelectedBy (形式) の TypeName 要素](./typename-element-for-viewselectedby-format.md)|省略可能な要素です。<br /><br /> ビューが表示されている .NET オブジェクトを指定します。|
|[ViewSelectedBy (形式) の SelectionSetName 要素](./selectionsetname-element-for-viewselectedby-format.md)|省略可能な要素です。<br /><br /> ビューが表示されている .NET オブジェクトのセットを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー要素 (形式)](./view-element-format.md)|1 つまたは複数の .NET オブジェクトを表示するビューを定義します。|

## <a name="remarks"></a>コメント

さまざまなビューでこの要素の使用方法の詳細については、次を参照してください[テーブル ビュー コンポーネント](./creating-a-table-view.md)、[一覧ビュー コンポーネント](./creating-a-list-view.md)、[ワイド ビュー コンポーネント](./creating-a-wide-view.md)、および[。カスタム コントロール コンポーネント](./creating-custom-controls.md)します。

`SelectionSetName`要素が書式設定ファイルが複数のビューによって表示されるオブジェクトのセットを定義する場合に使用されます。 選択範囲のセットを定義し、参照する方法の詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。

## <a name="example"></a>例

次の例は、指定する方法を示します、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)のリスト ビューのオブジェクト。 テーブルの幅をカスタム ビューに同じスキーマが使用されます。

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>参照

[リスト ビューの作成](./creating-a-list-view.md)

[テーブル ビューを作成します。](./creating-a-table-view.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[カスタム コントロールの作成](./creating-custom-controls.md)

[選択範囲のセットを定義します。](./defining-selection-sets.md)

[ViewSelectedBy (形式) の SelectionSetName 要素](./selectionsetname-element-for-viewselectedby-format.md)

[TypeName 要素 (形式)](./typename-element-for-viewselectedby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

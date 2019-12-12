---
title: ViewSelectedBy 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367971"
---
# <a name="viewselectedby-element-format"></a>ViewSelectedBy 要素 (書式)

ビューに表示される .NET オブジェクトを定義します。 各ビューには、少なくとも1つの .NET オブジェクトを指定する必要があります。

ViewDefinitions 要素 (Format) ビュー要素 (形式) ViewSelectedBy 要素 (形式)

## <a name="syntax"></a>構文

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`ViewSelectedBy` 要素の属性、子要素、および親要素について説明します。 この要素には、少なくとも1つの `TypeName` または `SelectionSetName` 子要素が含まれている必要があります。 指定できる子要素の数に制限はありません。また、順序が重要でもありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[ViewSelectedBy (Format) の TypeName 要素](./typename-element-for-viewselectedby-format.md)|省略可能な要素です。<br /><br /> ビューに表示される .NET オブジェクトを指定します。|
|[ViewSelectedBy (Format) の SelectionSetName 要素](./selectionsetname-element-for-viewselectedby-format.md)|省略可能な要素です。<br /><br /> ビューに表示される一連の .NET オブジェクトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[View 要素 (Format)](./view-element-format.md)|1つ以上の .NET オブジェクトを表示するビューを定義します。|

## <a name="remarks"></a>コメント

この要素をさまざまなビューで使用する方法の詳細については、「[テーブルビューコンポーネント](./creating-a-table-view.md)」、「[リストビュー](./creating-a-list-view.md)コンポーネント」、「[ワイドビューコンポーネント](./creating-a-wide-view.md)」、および「[カスタムコントロールコンポーネント](./creating-custom-controls.md)」を参照してください。

`SelectionSetName` 要素は、書式設定ファイルが複数のビューによって表示されるオブジェクトのセットを定義する場合に使用されます。 選択セットを定義および参照する方法の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

## <a name="example"></a>例

リストビューの[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトを指定する方法を次の例に示します。 テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。

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

[リストビューの作成](./creating-a-list-view.md)

[テーブルビューの作成](./creating-a-table-view.md)

[ワイドビューの作成](./creating-a-wide-view.md)

[カスタム コントロールの作成](./creating-custom-controls.md)

[選択セットの定義](./defining-selection-sets.md)

[ViewSelectedBy (Format) の SelectionSetName 要素](./selectionsetname-element-for-viewselectedby-format.md)

[TypeName 要素 (Format)](./typename-element-for-viewselectedby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

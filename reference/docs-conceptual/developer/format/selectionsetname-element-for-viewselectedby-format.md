---
title: ViewSelectedBy (Format) の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ab0f033-df09-4435-a8bd-76ec2d01f13b
caps.latest.revision: 13
ms.openlocfilehash: d1de2b30860bac80bf17508f40eec33c2794c4b2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368261"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a>ViewSelectedBy の SelectionSetName 要素 (書式)

ビューに表示される一連の .NET オブジェクトを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) ViewSelectedBy Element (Format) SelectionSetName 要素 (形式)

## <a name="syntax"></a>構文

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)|ビューに表示される .NET オブジェクトを定義します。|

## <a name="text-value"></a>テキスト値

選択セットの `Name` 要素によって定義される選択セットの名前を指定します。

## <a name="remarks"></a>コメント

継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。 選択セットの定義と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

## <a name="example"></a>例

次の例では、リストビューの選択セットを指定する方法を示します。 テーブル、ワイド、およびカスタムビューでも同じスキーマが使用されます。

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a>参照

[選択セットの定義](./defining-selection-sets.md)

[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

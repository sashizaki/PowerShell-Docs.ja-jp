---
title: ViewSelectedBy (形式) の要素を SelectionSetName |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ab0f033-df09-4435-a8bd-76ec2d01f13b
caps.latest.revision: 13
ms.openlocfilehash: d1de2b30860bac80bf17508f40eec33c2794c4b2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076227"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a>ViewSelectedBy の SelectionSetName 要素 (書式)

ビューが表示されている .NET オブジェクトのセットを指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ViewSelectedBy 要素 (形式) SelectionSetName 要素を ViewSelectedBy (形式)

## <a name="syntax"></a>構文

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)|ビューが表示されている .NET オブジェクトを定義します。|

## <a name="text-value"></a>テキスト値

定義されている選択セットの名前を指定、`Name`選択セットの要素。

## <a name="remarks"></a>コメント

継承によって関連付けられているオブジェクトのセットなどの 1 つの名前を使用して参照する関連のオブジェクトのセットがある場合は、選択範囲のセットを使用できます。 定義と参照セットの選択の詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。

## <a name="example"></a>例

次の例では、選択のリスト ビューのセットを指定する方法を示します。 テーブルの幅をカスタム ビューに同じスキーマが使用されます。

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

[選択範囲のセットを定義します。](./defining-selection-sets.md)

[ViewSelectedBy 要素 (形式)](./viewselectedby-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

---
title: ListItem の ListControl (形式) の要素にラベルを付ける |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c693ff46-d1ad-4dc7-93ac-41ff2fc6c103
caps.latest.revision: 9
ms.openlocfilehash: c1293d5a1f942704ac01388c66bd9009fd340e82
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854778"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a>ListControl の ListItem の Label 要素 (書式)

行のプロパティまたはスクリプトの値の左側に表示されるラベルを指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListControl 要素 (の ListEntry の ListControl (形式) のリスト項目のListControl (形式) を ListItem ListControl (形式) Label 要素の ListItems の ListItem 要素の形式)

## <a name="syntax"></a>構文

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Label`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListControl (形式) のリスト項目の ListItem 要素](./listitem-element-for-listitems-for-listcontrol-format.md)|プロパティまたはリスト ビューの行の値が表示されているスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

プロパティまたはスクリプトの値の左側に表示されるラベルを指定します。

## <a name="remarks"></a>コメント

ラベルが指定されていない場合、プロパティまたはスクリプトの名前が表示されます。 リスト ビューでのラベルの使用に関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。

## <a name="example"></a>例

次の例では、行にラベルを追加する方法を示します。

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a>参照

[リスト ビューの作成](./creating-a-list-view.md)

[ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

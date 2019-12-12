---
title: ListControl の ListItem の Label 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c693ff46-d1ad-4dc7-93ac-41ff2fc6c103
caps.latest.revision: 9
ms.openlocfilehash: c1293d5a1f942704ac01388c66bd9009fd340e82
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362891"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a>ListControl の ListItem の Label 要素 (書式)

行内のプロパティまたはスクリプト値の左側に表示されるラベルを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListEntries 要素の ListControl (format) ListEntry 要素の ListControl (Format) ListItems for ListEntry 要素 (Format) ListControl の ListItem の ListItems for ListControl (Format) Label 要素の ListItem 要素をフォーマットします。

## <a name="syntax"></a>構文

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Label` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ListControl の ListItems の ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)|リストビューの行に表示される値を持つプロパティまたはスクリプトを定義します。|

## <a name="text-value"></a>テキスト値

プロパティまたはスクリプト値の左側に表示するラベルを指定します。

## <a name="remarks"></a>コメント

ラベルが指定されていない場合は、プロパティまたはスクリプトの名前が表示されます。 リストビューでのラベルの使用の詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。

## <a name="example"></a>例

次の例では、ラベルを行に追加する方法を示します。

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a>参照

[リストビューの作成](./creating-a-list-view.md)

[ListItem 要素 (形式)](./listitem-element-for-listitems-for-listcontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

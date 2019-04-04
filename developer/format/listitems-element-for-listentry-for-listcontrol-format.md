---
title: ListEntry ListControl (形式) のリスト項目要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2c1da6d-acc7-4fe8-9e7d-6dcddc2787cd
caps.latest.revision: 9
ms.openlocfilehash: c25f18489d9c7abd8889758499dbbacd6ee29304
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858588"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a>ListControl の ListEntry の ListItems 要素 (書式)

リスト ビュー内の行の表示が値を持つスクリプトとプロパティを定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素リスト コントロール (形式) ListEntry ListControl (形式) のリスト項目要素を ListControl (形式)

## <a name="syntax"></a>構文

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ListItems`要素。 指定できる子要素の数に制限はありません。 子要素の順序は、値がリスト ビューに表示される順序を定義します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ListControl (形式) を ListItem 要素](./listitem-element-for-listitems-for-listcontrol-format.md)|必須の要素。<br /><br /> プロパティまたは値がリスト ビューで表示されているスクリプトを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ListControl (形式) の ListEntry 要素](./listentry-element-for-listcontrol-format.md)|リスト ビューの定義を提供します。|

## <a name="remarks"></a>コメント

この種類のビューの詳細については、[リスト ビューを作成する](./creating-a-list-view.md)を参照してください。

## <a name="example"></a>例

この例では、リスト ビューの 3 つの行を定義する XML 要素を示します。

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>.NetTypeProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>.NetTypeProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
  </ListEntry>
```

## <a name="see-also"></a>参照

[ListControl (形式) の ListEntry 要素](./listentry-element-for-listcontrol-format.md)

[ListControl (形式) を ListItem 要素](./listitem-element-for-listitems-for-listcontrol-format.md)

[リスト ビューの作成](./creating-a-list-view.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

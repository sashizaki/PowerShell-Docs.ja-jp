---
title: GroupBy (形式) のカスタム コントロールの要素を CustomEntry |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2987cb45-f646-45d4-b81b-7871e77af36f
caps.latest.revision: 5
ms.openlocfilehash: dcf4f8b2bbd422067ffdf9b3b4972e279e91edf9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860368"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a>GroupBy の CustomControl の CustomEntry 要素 (書式)

コントロールの定義を提供します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) のカスタム コントロール

## <a name="syntax"></a>構文

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntry`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) の CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-groupby-format.md)|省略可能な要素です。<br /><br /> このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。|
|[GroupBy (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-groupby-format.md)|必須の要素。<br /><br /> コントロールがデータを表示する方法を定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-groupby-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[GroupBy (形式) の CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-groupby-format.md)

[GroupBy (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-groupby-format.md)

[GroupBy (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

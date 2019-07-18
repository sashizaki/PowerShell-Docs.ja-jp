---
title: コントロールが表示されます (形式) の CustomEntries CustomEntry 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6739205-2bc9-4507-b2af-d19d548c2057
caps.latest.revision: 6
ms.openlocfilehash: b92b99d88992cf13dbf7bfbe88aad603615f3138
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066500"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a>View の Controls の CustomEntries の CustomEntry 要素 (書式)

コントロールの定義を提供します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールコントロールが表示されます (形式) の CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロール

## <a name="syntax"></a>構文

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntry`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|省略可能な要素です。<br /><br /> このコントロールの定義または条件を使用するには、この定義が存在する必要がありますを使用する .NET 型を定義します。|
|[コントロールが表示されます (形式) の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-view-format.md)|必須の要素。<br /><br /> コントロールがデータを表示する方法を定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-view-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[ビュー (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

---
title: ビュー (形式) のカスタム コントロールの CustomEntries CustomEntry 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3c0a25-f2ca-4e28-b3dc-9cb06a76d92a
caps.latest.revision: 11
ms.openlocfilehash: 7804155bffeb1f0df8339f797bf59f8def56a3fc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861818"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a>View の CustomControl の CustomEntries の CustomEntry 要素 (書式)

カスタム コントロールのビューの定義を提供します。

要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素の表示 (形式) CustomEntries ビュー (形式) CustomEntry 要素のカスタム コントロール

## <a name="syntax"></a>構文

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntry`要素。 定義によって表示される項目を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[表示 (形式) CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> カスタム コントロールのビューまたはこの定義を使用するのに必要な条件の定義を使用する .NET 型を定義します。|
|[表示 (形式) CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|カスタム コントロールの定義については、コントロールを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-view-format.md)|カスタム コントロールのビューの定義を提供します。 カスタム コントロールのビューには、1 つまたは複数の定義を指定する必要があります。|

## <a name="remarks"></a>コメント

ほとんどの場合、1 つだけ定義が必要ですがカスタム コントロールのビューごとに、同じビューを使用して、さまざまな .NET オブジェクトを表示する場合、複数の定義を指定することができます。 その場合の各オブジェクトまたはオブジェクトのセットを別の定義を行うことができます。

## <a name="see-also"></a>参照

[カスタム コントロールの要素のビュー (形式)](./customcontrol-element-for-view-format.md)

[表示 (形式) CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[表示 (形式) CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

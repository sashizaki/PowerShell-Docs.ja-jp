---
title: CustomControl の CustomEntry 要素 (構成用コントロール用) (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfba86f-29b2-473c-9e98-9d679176acce
caps.latest.revision: 11
ms.openlocfilehash: 497485a388d1cdc834ecc1d1079b0714a7d7f9db
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364071"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a>Configuration の Controls の CustomControl の CustomEntry 要素 (書式)

コモンコントロールの定義を提供します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成用のコントロール (形式)

## <a name="syntax"></a>構文

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`CustomEntry` 要素の親要素について説明します。 定義によって表示される項目を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration 用のコントロール用の CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|省略可能な要素。<br /><br /> コモンコントロールの定義、またはこのコントロールを使用するために存在する必要がある条件を使用する .NET 型を定義します。|
|[構成のための CustomEntry コントロールの CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|必須の要素です。<br /><br /> コントロールによって表示されるデータとその表示方法を定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration の CustomControl の CustomEntries 要素 (形式)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|コモンコントロールの定義を提供します。|

## <a name="remarks"></a>コメント

ほとんどの場合、共通のカスタムコントロールごとに1つの定義のみが必要ですが、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を持つことができます。 このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。

## <a name="see-also"></a>参照

[Configuration の CustomControl の CustomEntries 要素 (形式)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[構成のための CustomEntry コントロールの CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

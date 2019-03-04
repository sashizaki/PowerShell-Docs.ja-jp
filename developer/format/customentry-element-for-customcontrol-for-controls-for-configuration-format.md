---
title: 構成 (形式) のコントロールのカスタム コントロールの要素を CustomEntry |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfba86f-29b2-473c-9e98-9d679176acce
caps.latest.revision: 11
ms.openlocfilehash: 497485a388d1cdc834ecc1d1079b0714a7d7f9db
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859808"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a>Configuration の Controls の CustomControl の CustomEntry 要素 (書式)

コモン コントロールの定義を提供します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールのカスタム コントロールの形式) CustomEntry 要素

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
|[構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 一般的なコントロールまたは使用するには、このコントロールに必要な条件の定義を使用する .NET 型を定義します。|
|[コントロールの構成の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|必須の要素。<br /><br /> どのようなデータが、コントロールによって表示され、表示方法を定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|コモン コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

ほとんどの場合、1 つだけ定義が必要ですが、各の一般的なカスタム コントロールのさまざまな .NET オブジェクトを表示する同じコントロールを使用する場合、複数の定義を指定することができます。 その場合の各オブジェクトまたはオブジェクトのセットを別の定義を行うことができます。

## <a name="see-also"></a>参照

[構成 (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[コントロールの構成の CustomEntry CustomItem 要素](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

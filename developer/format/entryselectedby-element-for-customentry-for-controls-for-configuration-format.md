---
title: 構成 (形式) のコントロールの CustomEntry EntrySelectedBy 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059220"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a>Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)

一般的なコントロールまたは使用するには、このコントロールに必要な条件の定義を使用する .NET 型を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素構成 (形式) のコントロールの CustomEntry の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの形式) CustomEntry 要素

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`EntrySelectedBy`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 使用する一般的なコントロールの定義を満たす必要がある条件を定義します。|
|[構成 (形式) のコントロールの EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コモン コントロールのこの定義を使用する .NET 型のセットを指定します。|
|[構成 (形式) のコントロールの EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コモン コントロールのこの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|コモン コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

少なくとも、各定義は、少なくとも 1 つの .NET 型、選択範囲のセット、または指定された選択条件が必要です。 型、選択範囲のセット、または指定できる選択条件の数に上限はありません。

## <a name="see-also"></a>参照

[構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの EntrySelectedBy SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの EntrySelectedBy の TypeName 要素](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

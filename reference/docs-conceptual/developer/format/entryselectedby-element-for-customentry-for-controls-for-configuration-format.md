---
title: Configuration 用のコントロール用の CustomEntry 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30abae8f-c7f7-479d-ad85-19e07ddef204
caps.latest.revision: 10
ms.openlocfilehash: 81eca4f66f0057074612f2d60482b45adc36357b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368771"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a>Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)

コモンコントロールの定義、またはこのコントロールを使用するために存在する必要がある条件を使用する .NET 型を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素Format) CustomControl の CustomEntry 要素を構成するためのコントロール用の CustomEntry 要素 (形式) を構成するために、CustomEntry のコントロールの EntrySelectedBy 要素

## <a name="syntax"></a>構文

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`EntrySelectedBy` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> 共通のコントロール定義を使用するために必要な条件を定義します。|
|[構成用のコントロール (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コモンコントロールのこの定義を使用する一連の .NET 型を指定します。|
|[構成用のコントロール (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コモンコントロールのこの定義を使用する .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|コモンコントロールの定義を提供します。|

## <a name="remarks"></a>コメント

少なくとも、各定義には、少なくとも1つの .NET 型、選択セット、または選択条件が指定されている必要があります。 指定できる型、選択セット、または選択条件の数に上限はありません。

## <a name="see-also"></a>参照

[構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[構成用のコントロール (Format) の EntrySelectedBy の SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[構成用のコントロール (Format) の EntrySelectedBy の TypeName 要素](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

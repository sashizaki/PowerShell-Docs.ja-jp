---
title: GroupBy (Format) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8b6739b-770c-432a-95ab-551c7507c51f
caps.latest.revision: 6
ms.openlocfilehash: 3b5ce60d3a0d76988af48f49445a5478a415d498
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361671"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a>GroupBy の EntrySelectedBy の TypeName 要素 (書式)

カスタムコントロールのこの定義を使用する .NET 型を指定します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl の Entryselectedby 要素のエントリ名を指定します。 groupby (形式) の EntrySelectedBy の TypeName 要素

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-customentry-for-groupby-format.md)|このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。

## <a name="remarks"></a>コメント

各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。

カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。

## <a name="see-also"></a>参照

[カスタムコントロールの作成](./creating-custom-controls.md)

[GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-customentry-for-groupby-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

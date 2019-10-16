---
title: ビュー (Format) のコントロールに対する EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b594a064-746f-4900-99e4-7be7bf5aa5a2
caps.latest.revision: 7
ms.openlocfilehash: d540c99707f4e0796b2d408f2161a9208257ab32
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368351"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a>View の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)

コントロールのこの定義を使用する .NET 型のセットを指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビュー用のコントロール用の CustomControl (format) CustomEntry 要素のコントロール用の CustomEntries のコントロールのためのコントロールのためのコントロールのためのコントロールのためのコントロールのためのコントロールのためのコントロールのための Entryselectedby の SelectionSetName 要素を表示するためのコントロール (形式

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。

### <a name="attributes"></a>属性

None

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューのコントロールに対する CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

選択セットの名前を指定します。

## <a name="remarks"></a>コメント

各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。

選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。 選択セットの定義の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。

## <a name="see-also"></a>参照

[ビューのコントロールに対する CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

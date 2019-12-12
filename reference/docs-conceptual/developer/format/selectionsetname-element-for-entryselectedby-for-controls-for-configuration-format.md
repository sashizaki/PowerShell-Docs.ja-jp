---
title: 構成用のコントロール (Format) の EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42143d1e-7cda-4c4a-b568-fa1951bb9417
caps.latest.revision: 6
ms.openlocfilehash: 9060ee54d6f88c7f910b16cf5c9b87f37844b736
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364791"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a>Configuration の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)

コントロールのこの定義を使用する .NET 型のセットを指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素Format) CustomControl 用の CustomEntry 要素を構成するためのコントロール用の customentry 要素の構成 (形式) を構成するために、EntrySelectedBy の configuration (format) SelectionSetName 要素を構成するためのコントロール (形式)

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

None

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration 用のコントロール用の CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

選択セットの名前を指定します。

## <a name="remarks"></a>コメント

各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。

選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。 選択セットの定義の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。

## <a name="see-also"></a>参照

[Configuration 用のコントロール用の CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

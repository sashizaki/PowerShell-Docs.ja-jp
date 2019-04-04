---
title: WideControl (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9c6e18f-6cca-465c-bd20-3969e7897a96
caps.latest.revision: 10
ms.openlocfilehash: 6b6a4a4647412d11d947f1dc4ea12d1e05ff536e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856798"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a>WideControl の EntrySelectedBy の SelectionSetName 要素 (書式)

一連の定義については、.NET オブジェクトを指定します。 これらのオブジェクトのいずれかが表示されるたびに、定義を使用します。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素の WideEntry (形式) SelectionSetName 要素EntrySelectedBy WideEntry (形式) の

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-wideentry-format.md)|このワイド エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。|

## <a name="text-value"></a>テキスト値

選択範囲のセットの名前を指定します。

## <a name="remarks"></a>コメント

各定義には、1 つの型名、選択範囲のセット、または選択条件を指定する必要があります。

複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。 たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。 選択範囲のセットを定義する詳細については、[を定義する設定のビューのオブジェクトを](./defining-selection-sets.md)を参照してください。

ワイド ビューの他のコンポーネントに関する詳細については、[ワイド ビューを作成する](./creating-a-wide-view.md)を参照してください。

## <a name="see-also"></a>参照

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[選択範囲のセットを定義します。](./defining-selection-sets.md)

[WideEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-wideentry-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

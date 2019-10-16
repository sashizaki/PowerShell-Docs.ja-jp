---
title: WideControl (Format) の ColumnNumber 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe9eb5f9-a193-41a4-ad47-a96ba3f8d7e3
caps.latest.revision: 8
ms.openlocfilehash: 49f501538b8f72777984a5e575b999866abcdebf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364221"
---
# <a name="columnnumber-element-for-widecontrol-format"></a>WideControl の ColumnNumber 要素 (書式)

ワイドビューに表示される列の数を指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (format) WideControl の ColumnNumber 要素 (Format)

## <a name="syntax"></a>構文

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`ColumnNumber` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[WideControl 要素 (Format)](./widecontrol-element-format.md)|ビューのワイド (単一値) リスト形式を定義します。|

## <a name="text-value"></a>テキスト値

正の整数値を指定してください。

## <a name="remarks"></a>コメント

ワイドビューを定義する場合は、`AutoSize` 要素または `ColumnNumber` 要素を追加できますが、両方を追加することはできません。

ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

ワイドビューの例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。

## <a name="see-also"></a>参照

[WideControl の Autosize 要素 (形式)](./autosize-element-for-widecontrol-format.md)

[ワイドビューの作成](./creating-a-wide-view.md)

[ワイドビュー (基本)](./wide-view-basic.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

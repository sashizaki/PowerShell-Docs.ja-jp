---
title: ColumnNumber 要素 WideControl (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe9eb5f9-a193-41a4-ad47-a96ba3f8d7e3
caps.latest.revision: 8
ms.openlocfilehash: 49f501538b8f72777984a5e575b999866abcdebf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066908"
---
# <a name="columnnumber-element-for-widecontrol-format"></a>WideControl の ColumnNumber 要素 (書式)

表示幅が広いに表示される列の数を指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) WideControl 要素 (形式) ColumnNumber 要素を WideControl (形式)

## <a name="syntax"></a>構文

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`ColumnNumber`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideControl 要素 (形式)](./widecontrol-element-format.md)|ワイド (1 つの値) を定義するビューの一覧の形式。|

## <a name="text-value"></a>テキスト値

正の整数値を指定します。

## <a name="remarks"></a>コメント

ワイド ビューを定義するときに追加できます、`AutoSize`要素、または`ColumnNumber`は、要素は両方で追加できません。

ワイド ビューのコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。

ワイド ビューの例は、次を参照してください。[表示 (Basic) の幅が広い](./wide-view-basic.md)します。

## <a name="see-also"></a>参照

[WideControl (形式) の Autosize 要素](./autosize-element-for-widecontrol-format.md)

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[表示幅が広い (Basic)](./wide-view-basic.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

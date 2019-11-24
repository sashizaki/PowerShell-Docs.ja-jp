---
title: WideControl の AutoSize 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: def37479-7b6e-40cf-bc81-0f7cbc651b31
caps.latest.revision: 11
ms.openlocfilehash: 6dbaef5886a0600bd9fe96dbc8d21f00a674dfcf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369051"
---
# <a name="autosize-element-for-widecontrol-format"></a>WideControl の AutoSize 要素 (書式)

データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (Format) WideControl の Autosize 要素 (Format)

## <a name="syntax"></a>構文

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`AutoSize` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

None

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideControl 要素 (Format)](./widecontrol-element-format.md)|ビューのワイド (単一値) リスト形式を定義します。|

## <a name="remarks"></a>コメント

ワイドビューを定義する場合は、`AutoSize` 要素または[Columnnumber](./columnnumber-element-for-widecontrol-format.md)要素を追加できますが、両方を追加することはできません。

ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

ワイドビューの例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。

## <a name="see-also"></a>関連項目

[WideControl の ColumnNumber 要素 (形式)](./columnnumber-element-for-widecontrol-format.md)

[ワイドビューの作成](./creating-a-wide-view.md)

[WideControl 要素 (Format)](./widecontrol-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

---
title: GroupBy (Format) の CustomControlName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368881"
---
# <a name="customcontrolname-element-for-groupby-format"></a>GroupBy の CustomControlName 要素 (書式)

新しいグループを表示するために使用されるカスタムコントロールの名前を指定します。 この要素は、テーブル、リスト、ワイド、またはカスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) GroupBy 要素 (format) の CustomControlName 要素を指定します。

## <a name="syntax"></a>構文

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomControlName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)|Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。|

## <a name="text-value"></a>テキスト値

新しいグループの表示に使用されるカスタムコントロールの名前を指定します。

## <a name="remarks"></a>コメント

書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。 次の要素は、これらのカスタムコントロールの名前を指定します。

- [構成用コントロールのコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [ビューのコントロールに対する Control の Name 要素 (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>参照

[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

[構成用コントロールのコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[ビューのコントロールに対する Control の Name 要素 (Format)](./name-element-for-control-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

---
title: Expand 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: faa0314b-f6f1-44fd-ad2b-b00cbe38923f
caps.latest.revision: 9
ms.openlocfilehash: 8b924c989133b47e4d95d8429778003c76595d58
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368741"
---
# <a name="expand-element-format"></a>Expand 要素 (書式)

この定義に対してコレクションオブジェクトを展開する方法を指定します。

Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Ableexpand 要素 (format) 列挙 Ableexpand 要素 (format) Expand 要素 (形式)

## <a name="syntax"></a>構文

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、`Expand` 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able展開要素 (形式)](./enumerableexpansion-element-format.md)|特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。|

## <a name="text-value"></a>テキスト値

次のいずれかの値を指定します。

- EnumOnly: コレクション内のオブジェクトのプロパティのみを表示します。

- CoreOnly: コレクションオブジェクトのプロパティのみを表示します。

- Both: コレクション内のオブジェクトのプロパティと、コレクションオブジェクトのプロパティを表示します。

## <a name="remarks"></a>コメント

この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。 この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。

既定の動作では、コレクション内のオブジェクトのプロパティのみが表示されます。

## <a name="see-also"></a>参照

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

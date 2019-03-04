---
title: 要素 (形式) の展開 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: faa0314b-f6f1-44fd-ad2b-b00cbe38923f
caps.latest.revision: 9
ms.openlocfilehash: 8b924c989133b47e4d95d8429778003c76595d58
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858578"
---
# <a name="expand-element-format"></a>Expand 要素 (書式)

この定義のコレクション オブジェクトを展開する方法を指定します。

要素 (形式) を展開する構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式)

## <a name="syntax"></a>構文

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Expand`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion 要素 (形式)](./enumerableexpansion-element-format.md)|ビューに表示されているときに、オブジェクトが展開されます、特定の .NET コレクションを定義します。|

## <a name="text-value"></a>テキスト値

次の値のいずれかを指定します。

- Enumonly です。コレクション内のオブジェクトのプロパティのみを表示します。

- CoreOnly:コレクション オブジェクトのプロパティのみが表示されます。

- 両方とも：コレクションおよびコレクション オブジェクトのプロパティのオブジェクトのプロパティを表示します。

## <a name="remarks"></a>コメント

この要素を使用して、コレクション オブジェクトと、コレクション内のオブジェクトを表示する方法を定義します。 コレクション オブジェクトをサポートする任意のオブジェクトを指すここで、 **System.Collections.ICollection**インターフェイス。

既定の動作では、コレクション内のオブジェクトのプロパティのみを表示します。

## <a name="see-also"></a>参照

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

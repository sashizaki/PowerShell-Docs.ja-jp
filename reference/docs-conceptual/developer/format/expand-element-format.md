---
title: Expand 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: deee832254bb8a774ee2c1f5bd451d3ced1bd47a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783655"
---
# <a name="expand-element-format"></a>Expand 要素 (書式)

この定義に対してコレクションオブジェクトを展開する方法を指定します。

Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Ableexpand 要素 (format) 列挙 Ableexpand 要素 (format) Expand 要素 (形式)

## <a name="syntax"></a>構文

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `Expand` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion 要素 (書式)](./enumerableexpansion-element-format.md)|特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。|

## <a name="text-value"></a>テキスト値

次のいずれかの値を指定します。

- EnumOnly: コレクション内のオブジェクトのプロパティのみを表示します。

- CoreOnly: コレクションオブジェクトのプロパティのみを表示します。

- Both: コレクション内のオブジェクトのプロパティと、コレクションオブジェクトのプロパティを表示します。

## <a name="remarks"></a>解説

この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。 この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。

既定の動作では、コレクション内のオブジェクトのプロパティのみが表示されます。

## <a name="see-also"></a>参照

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

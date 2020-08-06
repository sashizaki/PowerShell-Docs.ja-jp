---
title: 列挙 Able展開要素 (形式) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 81a8959c19502a2e56f4cfa48a1e480509d84b6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774050"
---
# <a name="enumerableexpansion-element-format"></a>EnumerableExpansion 要素 (書式)

特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。

Configuration 要素 (Format) DefaultSettings 要素 (Format) Enumerableexpansions 要素 (format) の列挙 Ablesize 拡張要素 (形式)

## <a name="syntax"></a>構文

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `EnumerableExpansion` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion の EntrySelectedBy 要素 (書式)](./entryselectedby-element-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> この定義によって展開される .NET コレクションオブジェクトを定義します。|
|[Expand 要素 (書式)](./expand-element-format.md)|この定義に対してコレクションオブジェクトを展開する方法を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansions 要素 (書式)](./enumerableexpansions-element-format.md)|ビューに表示される .NET コレクションオブジェクトを拡張するさまざまな方法を定義します。|

## <a name="remarks"></a>解説

この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。 この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。

既定の動作では、コレクション内のオブジェクトのプロパティのみが表示されます。

## <a name="see-also"></a>参照

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

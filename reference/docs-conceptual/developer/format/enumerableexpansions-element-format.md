---
title: 列挙 Able展開要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2b536b1ab9b34b0089d0a38d3c5dc7a937176443
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774016"
---
# <a name="enumerableexpansions-element-format"></a>EnumerableExpansions 要素 (書式)

.NET コレクションオブジェクトがビューに表示されるときの展開方法を定義します。

Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Able展開要素 (形式)

## <a name="syntax"></a>構文

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `EnumerableExpansions` ます。 使用できる子要素の数に制限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion 要素 (書式)](./enumerableexpansion-element-format.md)|省略可能な要素です。<br /><br /> ビューに表示されるときに展開される特定の .NET コレクションオブジェクトを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[DefaultSettings 要素 (書式)](./defaultsettings-element-format.md)|書式設定ファイルのすべてのビューに適用される共通設定を定義します。|

## <a name="remarks"></a>解説

この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。 この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。

## <a name="see-also"></a>参照

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

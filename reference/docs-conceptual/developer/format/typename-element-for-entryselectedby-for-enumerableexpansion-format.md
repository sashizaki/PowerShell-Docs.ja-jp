---
title: 列挙型拡張に対する EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 670aeb0986b07c8b7834a9f4f9510f1757a62186
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785083"
---
# <a name="typename-element-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の TypeName 要素 (書式)

この定義によって展開される .NET 型を指定します。 この要素は、既定の設定を定義するときに使用されます。

Configuration 要素 (Format) DefaultSettings Element (Format) 列挙型拡張要素 (format) 列挙型拡張要素 (format) の entryselectedby 要素 (format) を指定します。 EntrySelectedBy の EntrySelectedBy の TypeName 要素 (Format)

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion の EntrySelectedBy 要素 (書式)](./entryselectedby-element-for-enumerableexpansion-format.md)|この定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[EnumerableExpansion の EntrySelectedBy 要素 (書式)](./entryselectedby-element-for-enumerableexpansion-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

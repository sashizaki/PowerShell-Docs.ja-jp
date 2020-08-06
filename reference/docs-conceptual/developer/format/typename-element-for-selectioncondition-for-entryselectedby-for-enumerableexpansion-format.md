---
title: 列挙型拡張に対する EntrySelectedBy の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f47384be10705b913d52b5cc8cb4ecf9ba83f17c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787344"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。

Configuration 要素 DefaultSettings (Format) 列挙型の拡張要素 (format) 列挙型の展開要素 (形式) entryselectedby 要素 (format) entryselectedby の要素 (format) を指定します。 entryselectedby の selectionselectedby は、entryselectedby の Selectionselectedby に対する SelectionCondition の selectioncondition 要素を指定します。

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
|[EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|この定義のコレクションオブジェクトを展開するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

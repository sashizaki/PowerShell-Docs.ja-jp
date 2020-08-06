---
title: WideEntry (Format) の EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9af443067467f590df824b28636f57b807a4fc94
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780187"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a>WideEntry の EntrySelectedBy の TypeName 要素 (書式)

定義の .NET 型を指定します。 このオブジェクトが表示されるたびに、定義が使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry の WideEntry (Format) TypeName 要素の EntrySelectedBy Element (Format)

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
|[WideEntry の EntrySelectedBy 要素 (書式)](./entryselectedby-element-for-wideentry-format.md)|このワイドエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。

## <a name="remarks"></a>解説

各ワイドエントリでは、1つまたは複数の .NET 型、選択セット、または定義を使用するために存在する必要がある選択条件を指定する必要があります。

ワイドビューのその他のコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

## <a name="see-also"></a>参照

[ワイド ビューを作成する](./creating-a-wide-view.md)

[WideEntry の EntrySelectedBy 要素 (書式)](./entryselectedby-element-for-wideentry-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

---
title: 列挙型拡張に対する EntrySelectedBy の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0506928-db92-4ec4-855f-6f3592a383ae
caps.latest.revision: 6
ms.openlocfilehash: 5ead806d956ebbef95eeffc42bb39ef784208017
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361751"
---
# <a name="typename-element-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の TypeName 要素 (書式)

この定義によって展開される .NET 型を指定します。 この要素は、既定の設定を定義するときに使用されます。

Configuration 要素 (Format) DefaultSettings 要素 (format) 列挙型拡張要素 (format) 列挙型拡張要素 (format) の EntrySelectedBy に対する Entryselectedby の TypeName 要素の EntrySelectedBy 要素列挙 Able展開 (形式)

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able展開 (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)|この定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[列挙 Able展開 (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

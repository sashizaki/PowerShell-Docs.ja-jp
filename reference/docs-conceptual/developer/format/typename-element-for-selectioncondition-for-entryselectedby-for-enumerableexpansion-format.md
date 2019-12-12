---
title: 列挙型拡張に対する EntrySelectedBy の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9100ab7-fbdc-4c0d-bb56-57669ef42b95
caps.latest.revision: 9
ms.openlocfilehash: 316e54d11647aedc1552a0bb74b943de7e4e3588
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361581"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。

Configuration 要素 DefaultSettings Element (Format) 列挙 Able膨張要素 (format) 列挙 able展開要素 (format) Entryselectedby 要素 (format) の EntrySelectedBy (Format) の SelectionCondition 要素を指定します。列挙型拡張 (Format) の EntrySelectedBy の SelectionCondition に対する列挙型拡張 (Format) TypeName 要素

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
|[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|この定義のコレクションオブジェクトを展開するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

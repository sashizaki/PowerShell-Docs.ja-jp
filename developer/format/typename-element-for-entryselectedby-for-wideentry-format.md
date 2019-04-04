---
title: EntrySelectedBy WideEntry (形式) 用の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81a91c74-6229-4b64-aa2b-9123e8b7e9e5
caps.latest.revision: 11
ms.openlocfilehash: be35f6e9e2ad0b2d9a21a91c053aa0f70cafaf9c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862648"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a>WideEntry の EntrySelectedBy の TypeName 要素 (書式)

定義の .NET 型を指定します。 このオブジェクトが表示されるたびに、定義を使用します。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素 WideEntry (の TypeName 要素を WideEntry (形式)形式)

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[WideEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-wideentry-format.md)|このワイド エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。

## <a name="remarks"></a>コメント

各ワイド エントリには、1 つまたは複数の .NET 型を選択し、セットまたは選択条件を使用する定義が存在する必要がありますを指定する必要があります。

ワイド ビューの他のコンポーネントに関する詳細については、[ワイド ビューを作成する](./creating-a-wide-view.md)を参照してください。

## <a name="see-also"></a>参照

[ワイド ビューを作成します。](./creating-a-wide-view.md)

[WideEntry (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-wideentry-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

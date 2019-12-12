---
title: ビュー (Format) のコントロールに対する EntrySelectedBy の TypeName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52003450-07ca-41e5-b075-8b6b03fc6e88
caps.latest.revision: 6
ms.openlocfilehash: 30215734ef832d778b08d3d7be224ff8d88b0579
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361781"
---
# <a name="typename-element-for-entryselectedby-for-controls-for-view-format"></a>View の Controls の EntrySelectedBy の TypeName 要素 (書式)

コントロールのこの定義を使用する .NET 型を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビュー用のコントロールの CustomControl (書式) の CustomEntry 要素のコントロールのためのコントロールのためのコントロールのための、ビュー (形式) のコントロールに対する EntrySelectedBy の TypeName 要素の設定

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
|[ビューのコントロールに対する CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[ビューのコントロールに対する CustomEntry 要素 (形式)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

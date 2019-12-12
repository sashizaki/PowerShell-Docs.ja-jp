---
title: 構成用のコントロールの SelectionCondition の TypeName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477c8711-fffc-4f92-af45-6d4f80990474
caps.latest.revision: 7
ms.openlocfilehash: 60f02f3240c5574e1b1f9027b060bd9af89a11d2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361611"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a>Configuration の Controls の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの構成 (形式) のコントロール要素の構成 (書式設定) 要素構成 (Format) CustomEntry 要素の CustomControl のためのコントロール用の構成 (形式) の構成 (形式) のために、customentry に対して EntrySelectedBy の Configuration (Format) SelectionCondition 要素を指定します。構成 (形式) のコントロールの SelectionCondition の構成 (形式) TypeName 要素

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
|[CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|コントロール定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

---
title: CustomEntry for ビュー (Format) の EntrySelectedBy の TypeName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76548af7-05bd-4d12-bf71-6fb69c434ef2
caps.latest.revision: 10
ms.openlocfilehash: c3dd761cd9b6c468d4833ea35b897ba5d425f598
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368071"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a>View の CustomEntry の EntrySelectedBy の TypeName 要素 (書式)

カスタムコントロールビューのこの定義を使用する .NET 型を指定します。 定義に指定できる型の数に制限はありません。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素の CustomControl for view (format) EntrySelectedBy 要素 for view (Format) EntrySelectedByCustomentry for ビューの EntrySelectedBy ビュー (形式) のための CustomEntry for ビュー (形式) の TypeName 要素の要素

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
|[CustomEntry for ビューの EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|このカスタムコントロールビュー定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。

## <a name="remarks"></a>コメント

各カスタムコントロールビュー定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。

カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。

## <a name="see-also"></a>参照

[カスタム コントロールの作成](./creating-custom-controls.md)

[CustomEntry for ビューの EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

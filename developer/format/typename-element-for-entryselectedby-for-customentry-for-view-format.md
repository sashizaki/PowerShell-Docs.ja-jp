---
title: TypeName 要素の表示 (形式) CustomEntry EntrySelectedBy |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76548af7-05bd-4d12-bf71-6fb69c434ef2
caps.latest.revision: 10
ms.openlocfilehash: c3dd761cd9b6c468d4833ea35b897ba5d425f598
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858838"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a>View の CustomEntry の EntrySelectedBy の TypeName 要素 (書式)

このカスタム コントロールのビューの定義を使用する .NET 型を指定します。 定義に指定できる型の数に制限はありません。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) EntrySelectedBy CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry EntrySelectedBy CustomEntry ビュー (形式) のためのビュー (形式) TypeName 要素の要素

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
|[表示 (形式) CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|このカスタム コントロールのビュー定義を使用する .NET 型または条件を使用するには、この定義が存在する必要がありますを定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。

## <a name="remarks"></a>コメント

各カスタム コントロールのビュー定義に少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。

カスタム コントロールのビューのコンポーネントに関する詳細については、次を参照してください。[カスタム コントロールを作成する](./creating-custom-controls.md)します。

## <a name="see-also"></a>参照

[カスタム コントロールの作成](./creating-custom-controls.md)

[表示 (形式) CustomEntry EntrySelectedBy 要素](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

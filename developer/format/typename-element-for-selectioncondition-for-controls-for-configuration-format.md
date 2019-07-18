---
title: TypeName 要素の構成 (形式) のコントロールの SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477c8711-fffc-4f92-af45-6d4f80990474
caps.latest.revision: 7
ms.openlocfilehash: 60f02f3240c5574e1b1f9027b060bd9af89a11d2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083945"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a>Configuration の Controls の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

コントロールのコントロールのカスタム コントロールの構成 (形式) CustomEntries 要素の構成 (形式) のカスタム コントロール要素のコントロールの構成 (形式) のコントロール要素の構成要素 (形式) のコントロール要素CustomEntry EntrySelectedBy CustomEntry のための構成 (形式) SelectionCondition 要素のコントロール用の構成 (形式) EntrySelectedBy 要素のコントロールのカスタム コントロールの構成 (形式) CustomEntry 要素構成 (形式) のコントロールの SelectionCondition の構成 (形式) TypeName 要素

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) の CustomEntry EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|コントロールの定義を使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[構成 (形式) の CustomEntry EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

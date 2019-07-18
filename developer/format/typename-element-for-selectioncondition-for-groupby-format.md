---
title: GroupBy (形式) の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 290d38e3-b9bd-4382-9671-2e28b32b7260
caps.latest.revision: 6
ms.openlocfilehash: a4036b1e9de85da7e0029e02cca9e0eaed462f70
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083775"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a>GroupBy の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の SelectionCondition の GroupBy (形式) の TypeName 要素 EntrySelectedBy の GroupBy (形式) SelectionCondition 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール

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
|[GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|コントロールの定義を使用するのに必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。

## <a name="remarks"></a>コメント

この要素が指定されている場合は指定できません、`SelectionSetName`要素。 選択条件を定義する詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。

## <a name="see-also"></a>参照

[GroupBy (形式) の EntrySelectedBy SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

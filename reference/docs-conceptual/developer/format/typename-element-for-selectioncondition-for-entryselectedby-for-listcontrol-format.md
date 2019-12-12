---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd025a3a-3780-40db-a068-873e7df38015
caps.latest.revision: 9
ms.openlocfilehash: 2b76b040b39088cc9c3b9d6890c38df3c533b39f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361561"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>ListControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。 この型が存在する場合は、リストエントリが使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListEntry 要素の ListControl (format) 要素の listentries 要素の listentries to ElementListControl (Format) の EntrySelectedBy の ListControl (Format) TypeName 要素の EntrySelectedBy の ListEntry for ListControl (format) SelectionCondition 要素

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
|[ListControl (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|このリストエントリが使用されるために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

`System.IO.DirectoryInfo`など、.NET 型の完全修飾名を指定します。

## <a name="remarks"></a>コメント

選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。

## <a name="see-also"></a>参照

[リストビューの作成](./creating-a-list-view.md)

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[ListControl (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

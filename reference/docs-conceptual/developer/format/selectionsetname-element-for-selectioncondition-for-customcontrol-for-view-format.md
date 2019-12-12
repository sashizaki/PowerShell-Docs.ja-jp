---
title: View (Format) の CustomControl の SelectionCondition の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52b05a9-762e-4f1c-ad57-9d1710149722
caps.latest.revision: 10
ms.openlocfilehash: 25d46665ca5df3ddf49af5718d513b84c77988c8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368271"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a>View の CustomControl の SelectionCondition の SelectionSetName 要素 (書式)

条件をトリガーする .NET 型のセットを指定します。 このセット内のいずれかの型が存在する場合、条件が満たされ、このコントロールを使用してオブジェクトが表示されます。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素の CustomControl for view (format) EntrySelectedBy 要素 for view (Format) EntrySelectedByCustomEntry for ビューの要素 (形式)

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|コントロール定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

選択セットの名前を指定します。

## <a name="remarks"></a>コメント

選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。 選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[選択セットの定義](./defining-selection-sets.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

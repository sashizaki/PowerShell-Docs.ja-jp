---
title: 列挙 Able展開の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 71fd969fd3e5c0a4e39762c9a026982a8ca2a9d1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785372"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。

Configuration 要素 (Format) DefaultSettings 要素 (format) の列挙 able膨張要素 (format) 列挙 able膨張拡張要素 (format) の entryselectedby 要素 (format) に対して、enumerableexpansions (format) に対して、entryselectedby の Selectionselectedby を指定します。

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|この定義のコレクションオブジェクトを展開するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>解説

選択条件では、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[EnumerableExpansion の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

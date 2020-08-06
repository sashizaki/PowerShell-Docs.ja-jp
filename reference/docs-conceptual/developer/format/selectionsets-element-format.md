---
title: SelectionSets 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 718b08e02220f285ef215fdca727492fd4407466
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785202"
---
# <a name="selectionsets-element-format"></a>SelectionSets 要素 (書式)

書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。 書式設定ファイルのビューおよびコントロールは、選択セットの名前のみを使用して、オブジェクトの完全なセットを参照できます。

構成要素 SelectionSets 要素の形式

## <a name="syntax"></a>構文

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSets` ます。 各子要素は、セットの名前で参照できるオブジェクトのセットを定義します。 子要素の順序は重要ではありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[SelectionSet 要素 (書式)](./selectionset-element-format.md)|必須の要素です。<br /><br /> セットの名前で参照できる .NET オブジェクトの1つのセットを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[Configuration 要素](./configuration-element-format.md)|書式設定ファイルのトップレベルの要素を表します。|

## <a name="remarks"></a>解説

継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。 ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。

共通選択セットは、書式設定ファイルのビューまたはビューの定義を定義するときに、名前によって指定されます。 このような場合、 `SelectionSetName` 要素と要素の子要素は、 `ViewSelectedBy` `EntrySelectedBy` 使用するセットを指定します。 選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。

## <a name="see-also"></a>参照

[Configuration 要素](./configuration-element-format.md)

[選択セットを定義する](./defining-selection-sets.md)

[SelectionSet 要素 (書式)](./selectionset-element-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

---
title: 構成用のコントロールの SelectionCondition の TypeName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2db856d1b84dded315204d8c8574ae86acb63515
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780068"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a>Configuration の Controls の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) コントロールの構成 (format) コントロールの要素の構成 (format) CustomControl 要素の構成のためのコントロールの CustomControl の構成 (形式) の CustomEntries 要素については、CustomControl for Controls の CustomEntry 要素を構成します。構成 (形式) のために、CustomEntry 用の configuration (形式) の SelectionCondition 要素を構成するための entryselectedby for configuration (format) の SelectionCondition 要素を構成するためのコントロールの SelectionCondition (形式)

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|コントロール定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[CustomEntry for 構成 (形式) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

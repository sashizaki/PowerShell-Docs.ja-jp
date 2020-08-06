---
title: View (Format) の CustomControl の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 28409604b8905440890161f66981264748bc2c33
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785066"
---
# <a name="typename-element-for-selectioncondition-for-customcontrol-for-view--format"></a>View の CustomControl の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (format) CustomControl のビュー (形式) の CustomEntries 要素の CustomControl for view (format) の CustomEntries の要素の CustomControl for ビューの CustomEntries に使用します。 (フォーマット) CustomControl for View (Format) の SelectionCondition の CustomControl for View (format) TypeName 要素の EntrySelectedBy for CustomControl for view (format) の SelectionCondition 要素を指定します。

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
|[CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|コントロール定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

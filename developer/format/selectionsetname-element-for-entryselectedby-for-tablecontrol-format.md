---
title: TableControl (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dd0bd5d-f206-4cc6-a0f8-70700ee2c4b7
caps.latest.revision: 8
ms.openlocfilehash: 819906127e81355c45103ede85ef3608e1c1cfeb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063923"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a>TableControl の EntrySelectedBy の SelectionSetName 要素 (書式)

一連の .NET 型、使用して、テーブル ビューのこのエントリを指定します。 エントリに指定できる選択セットの数に制限はありません。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素 (形式) SelectionSetName の構成要素EntrySelectedBy TableRowEntry (形式) の

## <a name="syntax"></a>構文

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|このエントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。|

## <a name="text-value"></a>テキスト値

選択範囲のセットの名前を指定します。

## <a name="remarks"></a>コメント

複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。 たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。 選択範囲のセットを定義する詳細については、次を参照してください。[ビューのオブジェクトのセットを定義する](./defining-selection-sets.md)します。

選択のエントリのセットを指定する場合は、型名を指定できません。 .NET 型を指定する方法の詳細については、次を参照してください。 [TableRowEntry (形式) の EntrySelectedBy の TypeName 要素](./typename-element-for-entryselectedby-for-tablecontrol-format.md)します。

テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。

## <a name="see-also"></a>参照

[EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[ビューのオブジェクトのセットを定義します。](./defining-selection-sets.md)

[テーブル ビューを作成します。](./creating-a-table-view.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

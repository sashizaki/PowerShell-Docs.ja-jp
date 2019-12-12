---
title: CustomEntry for Controls for Controls の CustomItem 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364031"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a>Configuration の Controls の CustomEntry の CustomItem 要素 (書式)

コントロールによって表示されるデータとその表示方法を定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式) CustomControl の CustomEntry 要素を構成するための管理用の Configuration (形式) CustomItem 要素を構成するためのコントロール用に設定します。

## <a name="syntax"></a>構文

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomItem` 要素の属性、子要素、および親要素について説明します。 詳細については、「解説」を参照してください。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[構成用のコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[構成用のコントロールの CustomItem の Frame 要素 (形式)](./frame-element-for-customitem-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> データを左右に移動するなど、データの表示方法を定義します。|
|[構成用のコントロールの CustomItem の改行要素 (形式)](./newline-element-for-customitem-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> コントロールの表示に空白行を追加します。|
|[構成用のコントロールの CustomItem のテキスト要素 (形式)](./text-element-for-customitem-for-controls-for-configuration-format.md)|省略可能な要素です。<br /><br /> かっこや角かっこなどのテキストをコントロールの表示に追加します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|コントロールの定義を提供します。|

## <a name="remarks"></a>コメント

`CustomItem` 要素の子要素を指定する場合は、次の点に注意してください。

- 子要素は、`ExpressionBinding`、`NewLine`、`Text`、および `Frame`の順に追加する必要があります。

- 指定できるシーケンスの数に上限はありません。

- 各シーケンスには、使用できる `ExpressionBinding` 要素の数に上限はありません。

## <a name="see-also"></a>参照

[構成用のコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[構成用のコントロールの CustomItem の Frame 要素 (形式)](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[構成用のコントロールの CustomItem の改行要素 (形式)](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[構成用のコントロールの CustomItem のテキスト要素 (形式)](./text-element-for-customitem-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

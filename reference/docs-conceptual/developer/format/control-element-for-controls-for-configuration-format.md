---
title: Configuration のコントロールの Control 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369011"
---
# <a name="control-element-for-controls-for-configuration-format"></a>Configuration の Controls の Control 要素 (書式)

書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。

Configuration 要素 (Format) コントロールの構成 (書式) のコントロール要素の Configuration (書式) コントロール要素

## <a name="syntax"></a>構文

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Control` 要素の属性、子要素、および親要素について説明します。 各子要素のうち1つだけを指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[構成用コントロールのコントロールの CustomControl 要素 (形式)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|必須の要素です。<br /><br /> コントロールを定義します。|
|[Configuration のコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-configuration-format.md)|必須の要素です。<br /><br /> コントロールを参照するために使用する名前を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration の Controls 要素 (Format)](./controls-element-for-configuration-format.md)|書式設定ファイルのすべてのビューまたはその他のコントロールで使用できるコモンコントロールを定義します。|

## <a name="remarks"></a>コメント

このコントロールに指定される名前は、次の要素で参照できます。

- [CustomItem の式のバインド要素 (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

## <a name="see-also"></a>参照

[Configuration の Controls 要素 (Format)](./controls-element-for-configuration-format.md)

[構成用のコントロールの CustomControl 要素 (形式)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[CustomItem の式のバインド要素 (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

[構成用コントロールのコントロールの Name 要素 (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

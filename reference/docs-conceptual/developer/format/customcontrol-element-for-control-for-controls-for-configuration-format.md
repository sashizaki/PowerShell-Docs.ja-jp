---
title: 構成用コントロールのコントロールの CustomControl 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9d92a9e-c680-46ca-962e-e82452726953
caps.latest.revision: 10
ms.openlocfilehash: 1d72ce5b18e89bd81c7f81b27f4b8c60bed99764
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368971"
---
# <a name="customcontrol-element-for-control-for-controls-for-configuration-format"></a>Configuration の Controls の Control の CustomControl 要素 (書式)

コントロールを定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) コントロールの構成 (format) CustomControl 要素のコントロール要素の構成 (形式) のコントロールの要素

## <a name="syntax"></a>構文

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomControl` 要素の属性、子要素、および親要素について説明します。 この要素には、少なくとも1つの子要素が必要です。 指定できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration の CustomControl の CustomEntries 要素 (形式)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|必須の要素です。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration のコントロールの Control 要素 (Format)](./control-element-for-controls-for-configuration-format.md)|書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[Configuration のコントロールの Control 要素 (Format)](./control-element-for-controls-for-configuration-format.md)

[Configuration の CustomControl の CustomEntries 要素 (形式)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

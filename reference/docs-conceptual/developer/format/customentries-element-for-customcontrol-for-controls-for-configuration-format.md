---
title: Configuration 用のコントロールの CustomControl の CustomEntries 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fc4de2-208f-4506-9a6a-c2675bb83be4
caps.latest.revision: 11
ms.openlocfilehash: abef6c91500f665c2366f221496d4cfd6444f5c9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368821"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a>Configuration の Controls の CustomControl の CustomEntries 要素 (書式)

コモンコントロールの定義を提供します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) 構成用の CustomControl の Configuration (format) CustomEntries 要素の構成 (形式) の CustomControl 要素の構成 (書式設定) 要素のコントロール要素形式

## <a name="syntax"></a>構文

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`CustomEntries` 要素の属性、子要素、および親要素について説明します。 1つまたは複数の子要素を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|コモンコントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[構成用のコントロールの CustomControl 要素 (形式)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|共通コントロールを定義します。|

## <a name="remarks"></a>コメント

ほとんどの場合、コントロールには定義が1つだけあります。定義は1つの `CustomEntry` 要素で定義されます。 ただし、同じコントロールを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を含めることができます。 このような場合は、オブジェクトまたはオブジェクトのセットごとに `CustomEntry` 要素を定義できます。

## <a name="see-also"></a>参照

[構成用のコントロールの CustomControl 要素 (形式)](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[CustomControl の CustomEntry 要素 (構成用コントロール用) (形式)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

---
title: 構成用コントロールのコントロールの Name 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4371d45-49a4-4303-8384-5b54105bd0d6
caps.latest.revision: 8
ms.openlocfilehash: 2704a530e0ae269efb772ac10e531bcbb12f6eff
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362711"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a>Configuration の Controls の Control の Name 要素 (書式)

コントロールの名前を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) コントロールの構成 (書式) のコントロール要素の構成 (format) コントロールの要素の構成 (形式) コントロールの要素

## <a name="syntax"></a>構文

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Name` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration のコントロールの Control 要素 (Format)](./control-element-for-controls-for-configuration-format.md)|書式設定ファイルのすべてのビューおよびコントロールを参照するために使用される名前によって使用できるコモンコントロールを定義します。|

## <a name="text-value"></a>テキスト値

このコントロールを参照するために使用する名前を指定します。

## <a name="remarks"></a>コメント

ここで指定した名前は、このコントロールを参照するために次の要素で使用できます。

- テーブル、リスト、ワイドコントロール、またはカスタムコントロールビューを作成するときに、コントロールを指定するには、次の要素を使用します。 [GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

- 別のコモンコントロールを作成するときに、このコントロールを指定するには、次の要素を使用します。[構成するコントロールの CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)です。

- ビューで使用できるコントロールを作成する場合、このコントロールは、[ビュー (Format) のコントロールの CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)によって指定できます。

## <a name="see-also"></a>参照

[Configuration のコントロールの Control 要素 (Format)](./control-element-for-controls-for-configuration-format.md)

[構成用のコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[ビューのコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

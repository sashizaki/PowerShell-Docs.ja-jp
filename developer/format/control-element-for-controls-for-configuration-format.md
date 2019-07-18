---
title: コントロールの構成 (形式) の control 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066795"
---
# <a name="control-element-for-controls-for-configuration-format"></a>Configuration の Controls の Control 要素 (書式)

書式設定ファイルと、コントロールを参照するために使用される名前のすべてのビューで使用できる一般的なコントロールを定義します。

構成 (形式) のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素

## <a name="syntax"></a>構文

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、および親要素について説明します、`Control`要素。 各子要素の 1 つだけを指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールのコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|必須の要素。<br /><br /> コントロールを定義します。|
|[構成 (形式) のコントロールの name 要素](./name-element-for-control-for-controls-for-configuration-format.md)|必須の要素。<br /><br /> コントロールを参照するための名前を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロール要素](./controls-element-for-configuration-format.md)|書式設定ファイルのすべてのビューで、またはその他のコントロールで使用できる一般的なコントロールを定義します。|

## <a name="remarks"></a>コメント

このコントロールに指定された名前は、次の要素で参照できます。

- [ExpressionBinding 要素 CustomItem (形式)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [View(Format) の GroupBy 要素](./groupby-element-for-view-format.md)

## <a name="see-also"></a>参照

[構成 (形式) のコントロール要素](./controls-element-for-configuration-format.md)

[構成 (形式) のコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[ExpressionBinding 要素 CustomItem (形式)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[View(Format) の GroupBy 要素](./groupby-element-for-view-format.md)

[構成 (形式) のコントロールのコントロールの name 要素](./name-element-for-control-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

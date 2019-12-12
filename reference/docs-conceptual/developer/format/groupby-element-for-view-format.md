---
title: ビューの GroupBy 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a2b061-2a4a-4ad1-84f9-cdbefb64aaab
caps.latest.revision: 8
ms.openlocfilehash: abb8b91626128b3deaa2db24a9fd8b34a6563410
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363631"
---
# <a name="groupby-element-for-view-format"></a>View の GroupBy 要素 (書式)

オブジェクトの新しいグループをどのように表示するかを定義します。 この要素は、テーブル、リスト、ワイド、またはカスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (形式) GroupBy 要素ビュー (形式)

## <a name="syntax"></a>構文

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a>属性と要素

以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[GroupBy (Format) の CustomControl 要素](./customcontrol-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> 新しいグループを表示するカスタムコントロールを定義します。|
|[GroupBy (Format) の CustomControlName 要素](./customcontrolname-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> 新しいグループを表示するために使用するコントロールの名前を指定します。|
|[GroupBy (Format) の Label 要素](./label-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> 新しいグループが検出されたときに表示されるラベルを指定します。|
|[GroupBy (Format) の PropertyName 要素](./propertyname-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> .NET プロパティの値が変更されるたびに、によって新しいグループが開始されることを指定します。|
|[GroupBy (Format) の ScriptBlock 要素](./scriptblock-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> 値が変更されるたびに新しいグループを開始するスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[View 要素 (Format)](./view-element-format.md)|1つ以上の .NET オブジェクトを表示するビューを定義します。|

## <a name="remarks"></a>コメント

新しいオブジェクトのグループをどのように表示するかを定義するときには、新しいグループを開始するプロパティまたはスクリプトを指定する必要があります。ただし、両方を指定することはできません。

## <a name="see-also"></a>参照

[GroupBy (Format) の CustomControlName 要素](./customcontrolname-element-for-groupby-format.md)

[GroupBy (Format) の Label 要素](./label-element-for-groupby-format.md)

[GroupBy (Format) の PropertyName 要素](./propertyname-element-for-groupby-format.md)

[GroupBy (Format) の ScriptBlock 要素](./scriptblock-element-for-groupby-format.md)

[View 要素 (Format)](./view-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

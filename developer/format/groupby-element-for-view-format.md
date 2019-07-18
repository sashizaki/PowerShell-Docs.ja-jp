---
title: GroupBy 要素 (形式) の表示 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a2b061-2a4a-4ad1-84f9-cdbefb64aaab
caps.latest.revision: 8
ms.openlocfilehash: abb8b91626128b3deaa2db24a9fd8b34a6563410
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065545"
---
# <a name="groupby-element-for-view-format"></a>View の GroupBy 要素 (書式)

オブジェクトの新しいグループを表示する方法を定義します。 この要素は、テーブル、リスト、幅、またはカスタム コントロールのビューを定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) のビュー (形式) の GroupBy 要素

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

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) のカスタム コントロール要素](./customcontrol-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> 新しいグループを表示するカスタム コントロールを定義します。|
|[GroupBy (形式) の CustomControlName 要素](./customcontrolname-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> 新しいグループを表示するために使用するコントロールの名前を指定します。|
|[GroupBy (形式) のラベル要素](./label-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> 新しいグループが発生したときに表示されるラベルを指定します。|
|[GroupBy (形式) の PropertyName 要素](./propertyname-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> .NET プロパティを開始を示す値が変更されるたびに、新しいグループ。|
|[GroupBy (形式) の ScriptBlock 要素](./scriptblock-element-for-groupby-format.md)|省略可能な要素です。<br /><br /> その値が変更されるたびに、新しいグループを開始するスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー要素 (形式)](./view-element-format.md)|1 つまたは複数の .NET オブジェクトを表示するビューを定義します。|

## <a name="remarks"></a>コメント

オブジェクトの新しいグループを表示する方法を定義するときは、プロパティまたは新しいグループを開始するスクリプトを指定する必要があります。ただし、両方を指定することはできません。

## <a name="see-also"></a>参照

[GroupBy (形式) の CustomControlName 要素](./customcontrolname-element-for-groupby-format.md)

[GroupBy (形式) のラベル要素](./label-element-for-groupby-format.md)

[GroupBy (形式) の PropertyName 要素](./propertyname-element-for-groupby-format.md)

[GroupBy (形式) の ScriptBlock 要素](./scriptblock-element-for-groupby-format.md)

[ビュー要素 (形式)](./view-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

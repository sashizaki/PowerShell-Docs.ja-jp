---
title: 構成 (形式) の要素をコントロールのコントロールの名前 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4371d45-49a4-4303-8384-5b54105bd0d6
caps.latest.revision: 8
ms.openlocfilehash: 2704a530e0ae269efb772ac10e531bcbb12f6eff
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065191"
---
# <a name="name-element-for-control-for-controls-for-configuration-format"></a>Configuration の Controls の Control の Name 要素 (書式)

コントロールの名前を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (形式) のコントロールのコントロールの構成 (形式) の Name 要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素

## <a name="syntax"></a>構文

```xml
<Name>NameOfControl</Name>

```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Name`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールのコントロール要素](./control-element-for-controls-for-configuration-format.md)|書式設定ファイルと、コントロールを参照するために使用される名前のすべてのビューで使用できる一般的なコントロールを定義します。|

## <a name="text-value"></a>テキスト値

このコントロールを参照するために使用される名前を指定します。

## <a name="remarks"></a>コメント

ここで指定した名前は、このコントロールを参照する、次の要素で使用できます。

- テーブル、リスト、ワイドまたはカスタム コントロールのビューを作成する場合は、次の要素によって、コントロールを指定できます。[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)

- 別の一般的なコントロールを作成するときにこのコントロールは、次の要素によって指定できます。[構成 (形式) のコントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- コントロールの作成は、ビューで使用できますが、ときにこのコントロールは、次の要素によって指定できます。[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

## <a name="see-also"></a>参照

[構成 (形式) のコントロールのコントロール要素](./control-element-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールの CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

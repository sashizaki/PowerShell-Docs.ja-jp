---
title: コントロールのコントロールのビュー (形式) の要素を名前 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065104"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a>View の Controls の Control の Name 要素 (書式)

コントロールの名前を指定します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) 要素 (形式) コントロールの Controls 要素のコントロールのビュー (形式) の名前の要素のコントロールのビュー (形式)

## <a name="syntax"></a>構文

```xml
<Name>ControlName</Name>
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
|[コントロールが表示されます (形式) のコントロール要素](./control-element-for-controls-for-view-format.md)|ビューとコントロールを参照するために使用される名前で使用できるコントロールを定義します。|

## <a name="text-value"></a>テキスト値

コントロールを参照するために使用される名前を指定します。

## <a name="remarks"></a>コメント

ここで指定した名前は、このコントロールを参照する、次の要素で使用できます。

- テーブル、リスト、ワイドまたはカスタム コントロールのビューを作成する場合は、次の要素によって、コントロールを指定できます。[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)

- 別のコントロールの作成は、ビューで使用できますが、ときにこのコントロールは、次の要素によって指定できます。[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

## <a name="see-also"></a>参照

[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)

[コントロールが表示されます (形式) の CustomItem ExpressionBinding 要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[コントロールが表示されます (形式) のコントロール要素](./control-element-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

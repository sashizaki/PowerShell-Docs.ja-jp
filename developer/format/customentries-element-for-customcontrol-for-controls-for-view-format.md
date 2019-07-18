---
title: コントロールが表示されます (形式) のカスタム コントロールの要素を CustomEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3485958a-ba87-4932-907c-a8f140c4abdb
caps.latest.revision: 8
ms.openlocfilehash: 4856aee930285781a101868bd6cb67824585bce1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066585"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a>View の Controls の CustomControl の CustomEntries 要素 (書式)

コントロールの定義を提供します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールコントロールが表示されます (形式) のカスタム コントロール

## <a name="syntax"></a>構文

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntries`要素。 指定できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) の CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)|必須の要素。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[コントロールが表示されます (形式) のコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-view-format.md)|ビューで使用されるコントロールを定義します。|

## <a name="remarks"></a>コメント

ほとんどの場合、コントロールが 1 つの指定された 1 つだけ定義`CustomEntry`要素。 ただし、同じコントロールを使用して、さまざまな .NET オブジェクトを表示する場合は、複数の定義を提供することができます。 その場合で定義できますを`CustomEntry`要素の各オブジェクトまたはオブジェクトのセット。

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) の CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)

[コントロールが表示されます (形式) のコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

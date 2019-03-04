---
title: GroupBy (形式) のカスタム コントロールの要素を CustomEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853678"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a>GroupBy の CustomControl の CustomEntries 要素 (書式)

コントロールの定義を提供します。 この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) の GroupBy (形式) のカスタム コントロールの GroupBy (形式) CustomEntries 要素のビュー (形式) のカスタム コントロール要素の GroupBy 要素

## <a name="syntax"></a>構文

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntries`要素。 指定できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) のカスタム コントロールの CustomEntry 要素](./customentry-element-for-customcontrol-for-groupby-format.md)|必須の要素。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) のカスタム コントロール要素](./customcontrol-element-for-groupby-format.md)|新しいグループを表示するカスタム コントロールを定義します。|

## <a name="remarks"></a>コメント

ほとんどの場合、コントロールが 1 つの指定された 1 つだけ定義`CustomEntry`要素。 ただし、別のグループを表示する同じコントロールを使用する場合は、複数の定義を提供することができます。 その場合で定義できますを`CustomEntry`グループの要素。

## <a name="see-also"></a>参照

[コントロールが表示されます (形式) の CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-controls-for-view-format.md)

[GroupBy (形式) のカスタム コントロール要素](./customcontrol-element-for-groupby-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

---
title: GroupBy (形式) の要素をカスタム コントロール |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2472e256-8f4f-4288-8b67-a3300649dafa
caps.latest.revision: 9
ms.openlocfilehash: 2e84e770a345e272d4c5917b00afe7520840e1db
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853748"
---
# <a name="customcontrol-element-for-groupby-format"></a>GroupBy の CustomControl 要素 (書式)

新しいグループを表示するカスタム コントロールを定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) の GroupBy (形式) のビュー (形式) のカスタム コントロール要素の GroupBy 要素

## <a name="syntax"></a>構文

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
<CustomControl>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControl`要素。 子要素の任意の数を指定し、それらを任意の順序で一覧表示できます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-groupby-format.md)|必須の要素。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)|Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[GroupBy (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-groupby-format.md)

[ビュー (形式) の GroupBy 要素](./groupby-element-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

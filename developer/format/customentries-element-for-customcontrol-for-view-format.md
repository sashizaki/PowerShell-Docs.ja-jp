---
title: ビュー (形式) のカスタム コントロールの要素を CustomEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb412831-94f7-4054-b19e-32c1b14c66dd
caps.latest.revision: 11
ms.openlocfilehash: 827baacd22ef258dd9b0c8a383a23fce7d975f7f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861698"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a>View の CustomControl の CustomEntries 要素 (書式)

カスタム コントロールのビューの定義を提供します。 カスタム コントロールのビューには、1 つまたは複数の定義を指定する必要があります。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries 要素をビュー (形式) のカスタム コントロール

## <a name="syntax"></a>構文

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControlEntries`要素。 1 つまたは複数の子要素を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[表示 (形式) CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|必須の要素。<br /><br /> カスタム コントロールのビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[カスタム コントロールの要素のビュー (形式)](./customcontrol-element-for-view-format.md)|必須の要素。<br /><br /> ビューのカスタム コントロールの書式を定義します。|

## <a name="remarks"></a>コメント

ほとんどの場合、コントロールが、1 つで定義されている、1 つだけ定義`CustomEntry`要素。 ただし別の .NET オブジェクトを表示する同じコントロールを使用する場合は、複数の定義を含めることは可能です。 その場合で定義できますを`CustomEntry`要素の各オブジェクトまたはオブジェクトのセット。

## <a name="see-also"></a>参照

[カスタム コントロールの要素のビュー (形式)](./customcontrol-element-for-view-format.md)

[表示 (形式) CustomEntries CustomEntry 要素](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

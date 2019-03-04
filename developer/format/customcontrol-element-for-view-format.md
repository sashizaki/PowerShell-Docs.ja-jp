---
title: ビュー (形式) の要素をカスタム コントロール |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2edac16c-0b30-4985-ac84-0821aa9a9f6d
caps.latest.revision: 12
ms.openlocfilehash: bd0f7ca4de8dede97d1553cd62884ea45876e0c7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861258"
---
# <a name="customcontrol-element-for-view-format"></a>View の CustomControl 要素 (書式)

ビューのカスタム コントロールの書式を定義します。

構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式)

## <a name="syntax"></a>構文

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControl`要素。 1 つの子要素を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ビュー (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-view-format.md)|必須の要素。<br /><br /> カスタム コントロールのビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[ビュー要素 (形式)](./view-element-format.md)|1 つまたは複数の .NET オブジェクトを表示するために使用するビューを定義します。|

## <a name="remarks"></a>コメント

ほとんどの場合、1 つだけ定義がそれぞれのコントロール ビューに必要なが同じビューを使用して、さまざまな .NET オブジェクトを表示する場合は、複数の定義を提供することは。 その場合の各オブジェクトまたはオブジェクトのセットを別の定義を行うことができます。

## <a name="see-also"></a>参照

[ビュー (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-view-format.md)

[ビュー要素 (形式)](./view-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

---
title: 構成 (形式) のコントロールのカスタム コントロールの要素を CustomEntries |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fc4de2-208f-4506-9a6a-c2675bb83be4
caps.latest.revision: 11
ms.openlocfilehash: abef6c91500f665c2366f221496d4cfd6444f5c9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856308"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a>Configuration の Controls の CustomControl の CustomEntries 要素 (書式)

コモン コントロールの定義を提供します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (カスタム コントロールの構成 (形式) CustomEntries 要素のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素形式)

## <a name="syntax"></a>構文

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomEntries`要素。 1 つまたは複数の子要素を指定する必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|コモン コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|一般的なコントロールを定義します。|

## <a name="remarks"></a>コメント

ほとんどの場合、コントロールが、1 つで定義されている、1 つだけ定義`CustomEntry`要素。 ただし別の .NET オブジェクトを表示する同じコントロールを使用する場合は、複数の定義を含めることは可能です。 その場合で定義できますを`CustomEntry`要素の各オブジェクトまたはオブジェクトのセット。

## <a name="see-also"></a>参照

[構成 (形式) のコントロールのカスタム コントロール要素](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[構成 (形式) のコントロールのカスタム コントロールの CustomEntry 要素](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

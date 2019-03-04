---
title: 構成 (形式) のコントロールのコントロールの要素をカスタム コントロール |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9d92a9e-c680-46ca-962e-e82452726953
caps.latest.revision: 10
ms.openlocfilehash: 1d72ce5b18e89bd81c7f81b27f4b8c60bed99764
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857668"
---
# <a name="customcontrol-element-for-control-for-controls-for-configuration-format"></a>Configuration の Controls の Control の CustomControl 要素 (書式)

コントロールを定義します。 この要素は、書式設定ファイル内のすべてのビューで使用できる一般的なコントロールを定義するときに使用されます。

構成 (形式) のコントロールの構成 (形式) のカスタム コントロール要素のコントロールのコントロール要素の構成 (形式) の構成要素 (形式) のコントロール要素

## <a name="syntax"></a>構文

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`CustomControl`要素。 この要素は、少なくとも 1 つの子要素をいる必要があります。 指定できる子要素の数に上限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|必須の要素。<br /><br /> コントロールの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールのコントロール要素](./control-element-for-controls-for-configuration-format.md)|書式設定ファイルと、コントロールを参照するために使用される名前のすべてのビューで使用できる一般的なコントロールを定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[構成 (形式) のコントロールのコントロール要素](./control-element-for-controls-for-configuration-format.md)

[構成 (形式) のカスタム コントロールの CustomEntries 要素](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

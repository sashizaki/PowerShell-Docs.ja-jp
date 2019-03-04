---
title: 構成 (形式) の controls 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861178"
---
# <a name="controls-element-for-configuration-format"></a>Configuration の Controls 要素 (書式)

書式設定ファイルのすべてのビューで使用できる一般的なコントロールを定義します。

構成 (形式) の構成要素 (形式) のコントロール要素

## <a name="syntax"></a>構文

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Controls`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロールのコントロール要素](./control-element-for-controls-for-configuration-format.md)|必須の要素。<br /><br /> 書式設定ファイルのすべてのビューで使用できる一般的なコントロールを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[構成要素 (形式)](./configuration-element-format.md)|書式設定ファイルの最上位の要素を表します。|

## <a name="remarks"></a>コメント

任意の数のコモン コントロールを作成することができます。 コントロールごとに、コントロールとコントロールのコンポーネントを参照するために使用される名前を指定する必要があります。

## <a name="see-also"></a>参照

[構成要素 (形式)](./configuration-element-format.md)

[構成 (形式) のコントロールのコントロール要素](./control-element-for-controls-for-configuration-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

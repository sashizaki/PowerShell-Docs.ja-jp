---
title: Configuration の Controls 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369001"
---
# <a name="controls-element-for-configuration-format"></a>Configuration の Controls 要素 (書式)

書式設定ファイルのすべてのビューで使用できる共通コントロールを定義します。

Configuration 要素 (Format) コントロールの構成要素 (形式)

## <a name="syntax"></a>構文

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Controls` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration のコントロールの Control 要素 (Format)](./control-element-for-controls-for-configuration-format.md)|必須の要素です。<br /><br /> 書式設定ファイルのすべてのビューで使用できるコモンコントロールを定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration 要素 (形式)](./configuration-element-format.md)|書式設定ファイルのトップレベルの要素を表します。|

## <a name="remarks"></a>コメント

任意の数のコモンコントロールを作成できます。 コントロールごとに、コントロールとそのコンポーネントを参照するために使用する名前を指定する必要があります。

## <a name="see-also"></a>参照

[Configuration 要素 (形式)](./configuration-element-format.md)

[Configuration のコントロールの Control 要素 (Format)](./control-element-for-controls-for-configuration-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

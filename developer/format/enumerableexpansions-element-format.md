---
title: EnumerableExpansions 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50c33892-2ade-44c2-906c-81e5f5ca21f2
caps.latest.revision: 9
ms.openlocfilehash: 1ecbda8a3b623757517019105e3b1ee46ccbb55c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066092"
---
# <a name="enumerableexpansions-element-format"></a>EnumerableExpansions 要素 (書式)

ビューに表示されているときに .NET コレクション オブジェクトを展開する方法を定義します。

構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式)

## <a name="syntax"></a>構文

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`EnumerableExpansions`要素。 使用できる子要素の数に制限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion 要素 (形式)](./enumerableexpansion-element-format.md)|省略可能な要素です。<br /><br /> ビューに表示されているときに展開される特定の .NET コレクション オブジェクトを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[DefaultSettings 要素 (形式)](./defaultsettings-element-format.md)|書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。|

## <a name="remarks"></a>コメント

この要素を使用して、コレクション オブジェクトと、コレクション内のオブジェクトを表示する方法を定義します。 コレクション オブジェクトをサポートする任意のオブジェクトを指すここで、 **System.Collections.ICollection**インターフェイス。

## <a name="see-also"></a>参照

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

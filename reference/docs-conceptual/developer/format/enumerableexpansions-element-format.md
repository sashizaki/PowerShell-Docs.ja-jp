---
title: 列挙 Able展開要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50c33892-2ade-44c2-906c-81e5f5ca21f2
caps.latest.revision: 9
ms.openlocfilehash: 1ecbda8a3b623757517019105e3b1ee46ccbb55c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363301"
---
# <a name="enumerableexpansions-element-format"></a>EnumerableExpansions 要素 (書式)

.NET コレクションオブジェクトがビューに表示されるときの展開方法を定義します。

Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Able展開要素 (形式)

## <a name="syntax"></a>構文

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`EnumerableExpansions` 要素の属性、子要素、および親要素について説明します。 使用できる子要素の数に制限はありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able展開要素 (形式)](./enumerableexpansion-element-format.md)|省略可能な要素です。<br /><br /> ビューに表示されるときに展開される特定の .NET コレクションオブジェクトを定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[DefaultSettings 要素 (Format)](./defaultsettings-element-format.md)|書式設定ファイルのすべてのビューに適用される共通設定を定義します。|

## <a name="remarks"></a>コメント

この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。 この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。

## <a name="see-also"></a>参照

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

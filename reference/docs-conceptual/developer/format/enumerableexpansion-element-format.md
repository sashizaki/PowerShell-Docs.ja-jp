---
title: 列挙 Able展開要素 (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93d27173-9ae4-46e5-bb78-90525915cd70
caps.latest.revision: 9
ms.openlocfilehash: bc1e58c00ca8419f9204076f0a46050281e704db
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368751"
---
# <a name="enumerableexpansion-element-format"></a>EnumerableExpansion 要素 (書式)

特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。

Configuration 要素 (Format) DefaultSettings 要素 (Format) Enumerableexpansions 要素 (format) の列挙 Ablesize 拡張要素 (形式)

## <a name="syntax"></a>構文

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`EnumerableExpansion` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able展開 (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> この定義によって展開される .NET コレクションオブジェクトを定義します。|
|[要素の展開 (形式)](./expand-element-format.md)|この定義に対してコレクションオブジェクトを展開する方法を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[列挙 Able展開要素 (形式)](./enumerableexpansions-element-format.md)|ビューに表示される .NET コレクションオブジェクトを拡張するさまざまな方法を定義します。|

## <a name="remarks"></a>コメント

この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。 この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。

既定の動作では、コレクション内のオブジェクトのプロパティのみが表示されます。

## <a name="see-also"></a>参照

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

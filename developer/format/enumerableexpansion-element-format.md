---
title: EnumerableExpansion 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93d27173-9ae4-46e5-bb78-90525915cd70
caps.latest.revision: 9
ms.openlocfilehash: bc1e58c00ca8419f9204076f0a46050281e704db
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066143"
---
# <a name="enumerableexpansion-element-format"></a>EnumerableExpansion 要素 (書式)

ビューに表示されているときに、オブジェクトが展開されます、特定の .NET コレクションを定義します。

構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式)

## <a name="syntax"></a>構文

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`EnumerableExpansion`要素。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansion (形式) の EntrySelectedBy 要素](./entryselectedby-element-for-enumerableexpansion-format.md)|省略可能な要素です。<br /><br /> .NET コレクション オブジェクトの拡張機能では、この定義を定義します。|
|[要素 (形式) の展開します。](./expand-element-format.md)|この定義のコレクション オブジェクトを展開する方法を指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[EnumerableExpansions 要素 (形式)](./enumerableexpansions-element-format.md)|オブジェクトは、ビューに表示されているときに展開されますが、その .NET コレクションにさまざまな方法を定義します。|

## <a name="remarks"></a>コメント

この要素を使用して、コレクション オブジェクトと、コレクション内のオブジェクトを表示する方法を定義します。 コレクション オブジェクトをサポートする任意のオブジェクトを指すここで、 **System.Collections.ICollection**インターフェイス。

既定の動作では、コレクション内のオブジェクトのプロパティのみを表示します。

## <a name="see-also"></a>参照

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

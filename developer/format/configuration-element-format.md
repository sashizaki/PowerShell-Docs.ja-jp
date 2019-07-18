---
title: 構成要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066823"
---
# <a name="configuration-element-format"></a>Configuration 要素 (書式)

書式設定ファイルの最上位の要素を表します。

構成要素

## <a name="syntax"></a>構文

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、属性、子要素、およびの親要素について説明します、`Configuration`要素。 この要素は、書式設定ファイルごとにルート要素である必要があり、この要素は、少なくとも 1 つの子要素を含める必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[構成 (形式) のコントロール要素](./controls-element-for-configuration-format.md)|省略可能な要素です。<br /><br /> 書式設定ファイルのすべてのビューで使用できる一般的なコントロールを定義します。|
|[DefaultSettings 要素 (形式)](./defaultsettings-element-format.md)|省略可能な要素です。<br /><br /> 書式設定ファイルのすべてのビューに適用される一般的な設定を定義します。|
|[SelectionSets 要素の形式](./selectionsets-element-format.md)|省略可能な要素です。<br /><br /> 書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。|
|[ViewDefinitions 要素 (形式)](./viewdefinitions-element-format.md)|省略可能な要素です。<br /><br /> オブジェクトを表示するために使用するビューを定義します。|

### <a name="parent-elements"></a>親要素

なし。

## <a name="remarks"></a>コメント

書式設定ファイルでは、オブジェクトの表示方法を定義します。 このルート要素を含むほとんどの場合、 [ViewDefinitions](./viewdefinitions-element-format.md)テーブル、リスト、および書式設定ファイルの全体のビューを定義する要素。 書式設定ファイルには、ビューの定義に加えて、一般的な選択範囲を設定、設定、およびそれらのビューが使用できるコントロールを定義できます。

## <a name="see-also"></a>参照

[構成 (形式) のコントロール要素](./controls-element-for-configuration-format.md)

[DefaultSettings 要素 (形式)](./defaultsettings-element-format.md)

[SelectionSets 要素 (形式)](./selectionsets-element-format.md)

[ViewDefinitions 要素 (形式)](./viewdefinitions-element-format.md)

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)

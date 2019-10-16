---
title: Configuration 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363501"
---
# <a name="configuration-element-format"></a>Configuration 要素 (書式)

書式設定ファイルのトップレベルの要素を表します。

Configuration 要素

## <a name="syntax"></a>構文

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Configuration` 要素の属性、子要素、および親要素について説明します。 この要素は、各書式設定ファイルのルート要素である必要があり、この要素には少なくとも1つの子要素が含まれている必要があります。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[Configuration の Controls 要素 (Format)](./controls-element-for-configuration-format.md)|省略可能な要素。<br /><br /> 書式設定ファイルのすべてのビューで使用できる共通コントロールを定義します。|
|[DefaultSettings 要素 (Format)](./defaultsettings-element-format.md)|省略可能な要素。<br /><br /> 書式設定ファイルのすべてのビューに適用される共通設定を定義します。|
|[SelectionSets 要素の形式](./selectionsets-element-format.md)|省略可能な要素。<br /><br /> 書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。|
|[ViewDefinitions 要素 (形式)](./viewdefinitions-element-format.md)|省略可能な要素。<br /><br /> オブジェクトを表示するために使用するビューを定義します。|

### <a name="parent-elements"></a>親要素

なし。

## <a name="remarks"></a>コメント

書式設定ファイルは、オブジェクトの表示方法を定義します。 ほとんどの場合、このルート要素には、書式設定ファイルのテーブル、リスト、およびワイドビューを定義する[Viewdefinitions](./viewdefinitions-element-format.md)要素が含まれています。 ビュー定義に加えて、書式設定ファイルでは、これらのビューで使用できる共通の選択セット、設定、およびコントロールを定義できます。

## <a name="see-also"></a>参照

[Configuration の Controls 要素 (Format)](./controls-element-for-configuration-format.md)

[DefaultSettings 要素 (Format)](./defaultsettings-element-format.md)

[SelectionSets 要素 (Format)](./selectionsets-element-format.md)

[ViewDefinitions 要素 (形式)](./viewdefinitions-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

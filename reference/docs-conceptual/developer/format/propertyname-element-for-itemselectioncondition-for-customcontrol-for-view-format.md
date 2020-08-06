---
title: View (Format) の CustomControl の ItemSelectionCondition の PropertyName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0131fa86be4be4daec1d9d24b50397fb8529f050
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785576"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)

条件をトリガーする .NET プロパティを指定します。 このプロパティが存在する場合、またはと評価された場合 `true` 、条件が満たされ、コントロールが使用されます。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) CustomControl for view (format) の CustomEntries for ビュー (形式) の CustomEntries を指定します。 Mentry for view (format) 式のバインド要素の CustomControl for view (format) ItemSelectionCondition 要素の式のバインドの CustomControl for view (format) の PropertyName 要素の CustomControl for ビューの ItemSelectionCondition (形式)

## <a name="syntax"></a>構文

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|このコントロールを使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

条件をトリガーする .NET プロパティの名前を指定します。

## <a name="remarks"></a>解説

この要素が使用されている場合、選択条件を定義するときに[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[View の CustomControl の ItemSelectionCondition の ScriptBlock 要素 (書式)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

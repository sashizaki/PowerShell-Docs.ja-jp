---
title: View (Format) の Controls 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 26b7e73afd465b1be9632cd71a75e4be6cc4aeca
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786171"
---
# <a name="controls-element-for-view-format"></a>View の Controls 要素 (書式)

特定のビューで使用できるビューコントロールを定義します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (書式) コントロール要素ビュー (形式)

## <a name="syntax"></a>構文

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `Controls` ます。 この要素には、少なくとも1つの子要素が必要です。 子要素の最大数はなく、順序は重要でもありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[ビューのコントロールの Control 要素 (Format)](./control-element-for-controls-for-view-format.md)|ビューで使用できるコントロールを定義します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View 要素 (書式)](./view-element-format.md)|1つ以上の .NET オブジェクトのメンバーを表示するために使用されるビューを定義します。|

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[Control 要素 (Format)](./control-element-for-controls-for-view-format.md)

[View 要素 (書式)](./view-element-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

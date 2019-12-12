---
title: ビューのコントロールのコントロールの Name 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26437467-d578-4e8d-8cdd-17dfe644957a
caps.latest.revision: 7
ms.openlocfilehash: 7e24aa60f7abae5768707d2527826c452b709002
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365101"
---
# <a name="name-element-for-control-for-controls-for-view-format"></a>View の Controls の Control の Name 要素 (書式)

コントロールの名前を指定します。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素 (format) を表示するコントロールの要素 (書式)

## <a name="syntax"></a>構文

```xml
<Name>ControlName</Name>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Name` 要素の属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[ビューのコントロールの Control 要素 (Format)](./control-element-for-controls-for-view-format.md)|ビューで使用できるコントロールと、コントロールを参照するために使用される名前を定義します。|

## <a name="text-value"></a>テキスト値

コントロールを参照するために使用する名前を指定します。

## <a name="remarks"></a>コメント

ここで指定した名前は、このコントロールを参照するために次の要素で使用できます。

- テーブル、リスト、ワイドコントロール、またはカスタムコントロールビューを作成するときに、コントロールを指定するには、次の要素を使用します。 [GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

- ビューで使用できる別のコントロールを作成する場合、このコントロールは、[ビュー (Format) のコントロールの CustomItem の式のバインド要素](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)によって指定できます。

## <a name="see-also"></a>参照

[ビューの GroupBy 要素 (Format)](./groupby-element-for-view-format.md)

[ビューのコントロールに対する CustomItem の式のバインド要素 (形式)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[ビューのコントロールの Control 要素 (Format)](./control-element-for-controls-for-view-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)

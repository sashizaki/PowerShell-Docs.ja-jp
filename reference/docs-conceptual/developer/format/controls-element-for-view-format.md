---
title: View (Format) の Controls 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd82666-447f-40fe-bd87-c8b182522f4f
caps.latest.revision: 14
ms.openlocfilehash: 477b8b54c8edd2fa0e6939041d04322d861197c9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363391"
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

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`Controls` 要素の属性、子要素、および親要素について説明します。 この要素には、少なくとも1つの子要素が必要です。 子要素の最大数はなく、順序は重要でもありません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[ビューのコントロールの Control 要素 (Format)](./control-element-for-controls-for-view-format.md)|ビューで使用できるコントロールを定義します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[View 要素 (Format)](./view-element-format.md)|1つ以上の .NET オブジェクトのメンバーを表示するために使用されるビューを定義します。|

## <a name="remarks"></a>コメント

## <a name="see-also"></a>参照

[Control 要素 (Format)](./control-element-for-controls-for-view-format.md)

[View 要素 (Format)](./view-element-format.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
